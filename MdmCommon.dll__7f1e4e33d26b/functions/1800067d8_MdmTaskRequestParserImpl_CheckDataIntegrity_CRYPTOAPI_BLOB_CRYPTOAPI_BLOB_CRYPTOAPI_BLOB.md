# MdmTaskRequestParserImpl::CheckDataIntegrity(_CRYPTOAPI_BLOB,_CRYPTOAPI_BLOB,_CRYPTOAPI_BLOB)

- ea: `0x1800067d8`
- end: `0x18000695b`
- name: `?CheckDataIntegrity@MdmTaskRequestParserImpl@@AEAAJU_CRYPTOAPI_BLOB@@00@Z`
- size: `387`
- prototype: `__int64 __fastcall(MdmTaskRequestParserImpl *this, struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180006aa0`

## callees

- `0x180001544`
- `0x180006548`
- `0x1800067d8`
- `0x1800078ec`
- `0x18001d504`

## string_xrefs

- `0x180006933`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmtaskrequestparserimpl.cpp`
- `0x1800068b1`: `CHR(MdmCrypto::ComputeHMAC(blobData, blobSharedSecret, &blobHashed))`
- `0x1800068e6`: `CBR(blobHashed.cbData == c_rgdwCommandInfo[CmdInfo_Hash][1])`
- `0x18000691c`: `CBR(0 == memcmp(blobHash.pbData, blobHashed.pbData, c_rgdwCommandInfo[CmdInfo_Hash][1]))`

## pseudocode

```c
__int64 __fastcall MdmTaskRequestParserImpl::CheckDataIntegrity(
        MdmTaskRequestParserImpl *this,
        struct _CRYPTOAPI_BLOB *a2,
        struct _CRYPTOAPI_BLOB *a3,
        struct _CRYPTOAPI_BLOB *a4)
{
  bool v4; // zf
  int v6; // ebx
  int v7; // ecx
  char v9; // [rsp+20h] [rbp-28h]
  const char *v10; // [rsp+28h] [rbp-20h]
  void *Buf2[2]; // [rsp+30h] [rbp-18h] BYREF

  v4 = a2->cbData == 0;
  *(_OWORD *)Buf2 = 0;
  if ( v4 )
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
        183,
        (__int64)"CBR(blobHash.cbData > 0)");
    goto LABEL_20;
  }
  if ( !a3->cbData )
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
        184,
        (__int64)"CBR(blobSharedSecret.cbData > 0)");
    goto LABEL_20;
  }
  if ( !a4->cbData )
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
        185,
        (__int64)"CBR(blobData.cbData > 0)");
    goto LABEL_20;
  }
  v6 = MdmCrypto::ComputeHMAC(a4, a3, (DWORD *)Buf2);
  if ( v6 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_20;
    v10 = "CHR(MdmCrypto::ComputeHMAC(blobData, blobSharedSecret, &blobHashed))";
    v9 = -68;
    goto LABEL_19;
  }
  if ( LODWORD(Buf2[0]) == 32 )
  {
    if ( !memcmp_0(a2->pbData, Buf2[1], 0x20u) )
      goto LABEL_20;
    v6 = -2147024891;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_20;
    v10 = "CBR(0 == memcmp(blobHash.pbData, blobHashed.pbData, c_rgdwCommandInfo[CmdInfo_Hash][1]))";
    v9 = -58;
LABEL_19:
    McTemplateU0dsqs_EventWriteTransfer(
      v7,
      (_DWORD)a2,
      v6,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
      v9,
      (__int64)v10);
    goto LABEL_20;
  }
  v6 = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v7,
      (_DWORD)a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
      195,
      (__int64)"CBR(blobHashed.cbData == c_rgdwCommandInfo[CmdInfo_Hash][1])");
LABEL_20:
  if ( Buf2[1] )
    operator delete(Buf2[1], (unsigned __int64)a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800067d8  mov     [rsp+arg_0], rbx
0x1800067dd  push    rdi
0x1800067de  sub     rsp, 40h
0x1800067e2  cmp     dword ptr [rdx], 0
0x1800067e5  xorps   xmm0, xmm0
0x1800067e8  movups  xmmword ptr [rsp+48h+Buf2], xmm0
0x1800067ed  mov     rax, r8
0x1800067f0  mov     rdi, rdx
0x1800067f3  ja      short loc_180006824
0x1800067f5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800067fc  mov     r8d, 80070057h
0x180006802  mov     ebx, r8d
0x180006805  jz      loc_18000693F
0x18000680b  lea     rax, aCbrBlobhashCbd; "CBR(blobHash.cbData > 0)"
0x180006812  mov     [rsp+48h+var_20], rax
0x180006817  mov     dword ptr [rsp+48h+var_28], 2B7h
0x18000681f  jmp     loc_180006933
0x180006824  cmp     dword ptr [r8], 0
0x180006828  ja      short loc_180006859
0x18000682a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180006831  mov     r8d, 80070057h
0x180006837  mov     ebx, r8d
0x18000683a  jz      loc_18000693F
0x180006840  lea     rax, aCbrBlobshareds; "CBR(blobSharedSecret.cbData > 0)"
0x180006847  mov     [rsp+48h+var_20], rax
0x18000684c  mov     dword ptr [rsp+48h+var_28], 2B8h
0x180006854  jmp     loc_180006933
0x180006859  cmp     dword ptr [r9], 0
0x18000685d  ja      short loc_18000688E
0x18000685f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180006866  mov     r8d, 80070057h
0x18000686c  mov     ebx, r8d
0x18000686f  jz      loc_18000693F
0x180006875  lea     rax, aCbrBlobdataCbd; "CBR(blobData.cbData > 0)"
0x18000687c  mov     [rsp+48h+var_20], rax
0x180006881  mov     dword ptr [rsp+48h+var_28], 2B9h
0x180006889  jmp     loc_180006933
0x18000688e  lea     r8, [rsp+48h+Buf2]; pdwDataLen
0x180006893  mov     rdx, rax; struct _CRYPTOAPI_BLOB *
0x180006896  mov     rcx, r9; struct _CRYPTOAPI_BLOB *
0x180006899  call    ?ComputeHMAC@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@0PEAU2@@Z; MdmCrypto::ComputeHMAC(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)
0x18000689e  mov     ebx, eax
0x1800068a0  test    eax, eax
0x1800068a2  jns     short loc_1800068C7
0x1800068a4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800068ab  jz      loc_18000693F
0x1800068b1  lea     rax, aChrMdmcryptoCo; "CHR(MdmCrypto::ComputeHMAC(blobData, bl"...
0x1800068b8  mov     [rsp+48h+var_20], rax
0x1800068bd  mov     dword ptr [rsp+48h+var_28], 2BCh
0x1800068c5  jmp     short loc_180006930
0x1800068c7  mov     r8d, 20h ; ' '; Size
0x1800068cd  cmp     dword ptr [rsp+48h+Buf2], r8d
0x1800068d2  jz      short loc_1800068FC
0x1800068d4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800068db  mov     r8d, 80070057h
0x1800068e1  mov     ebx, r8d
0x1800068e4  jz      short loc_18000693F
0x1800068e6  lea     rax, aCbrBlobhashedC; "CBR(blobHashed.cbData == c_rgdwCommandI"...
0x1800068ed  mov     [rsp+48h+var_20], rax
0x1800068f2  mov     dword ptr [rsp+48h+var_28], 2C3h
0x1800068fa  jmp     short loc_180006933
0x1800068fc  mov     rdx, [rsp+48h+Buf2+8]; Buf2
0x180006901  mov     rcx, [rdi+8]; Buf1
0x180006905  call    memcmp_0
0x18000690a  test    eax, eax
0x18000690c  jz      short loc_18000693F
0x18000690e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180006915  mov     ebx, 80070005h
0x18000691a  jz      short loc_18000693F
0x18000691c  lea     rax, aCbr0MemcmpBlob; "CBR(0 == memcmp(blobHash.pbData, blobHa"...
0x180006923  mov     [rsp+48h+var_20], rax
0x180006928  mov     dword ptr [rsp+48h+var_28], 2C6h
0x180006930  mov     r8d, ebx
0x180006933  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000693a  call    McTemplateU0dsqs_EventWriteTransfer
0x18000693f  mov     rcx, [rsp+48h+Buf2+8]; void *
0x180006944  test    rcx, rcx
0x180006947  jz      short loc_18000694E
0x180006949  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000694e  mov     eax, ebx
0x180006950  mov     rbx, [rsp+48h+arg_0]
0x180006955  add     rsp, 40h
0x180006959  pop     rdi
0x18000695a  retn
```
