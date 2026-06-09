# MdmTaskRequestParserImpl::CheckDataIntegrity(_CRYPTOAPI_BLOB,_CRYPTOAPI_BLOB,_CRYPTOAPI_BLOB)

- ea: `0x18000685c`
- end: `0x1800069e0`
- name: `?CheckDataIntegrity@MdmTaskRequestParserImpl@@AEAAJU_CRYPTOAPI_BLOB@@00@Z`
- size: `388`
- prototype: `int(MdmTaskRequestParserImpl *__hidden this, struct _CRYPTOAPI_BLOB *__struct_ptr, struct _CRYPTOAPI_BLOB *__struct_ptr, struct _CRYPTOAPI_BLOB *__struct_ptr)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180006b24`

## callees

- `0x180001544`
- `0x1800065c0`
- `0x18000685c`
- `0x180007974`
- `0x18001dbe4`

## string_xrefs

- `0x1800069b7`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmtaskrequestparserimpl.cpp`
- `0x180006935`: `CHR(MdmCrypto::ComputeHMAC(blobData, blobSharedSecret, &blobHashed))`
- `0x18000696a`: `CBR(blobHashed.cbData == c_rgdwCommandInfo[CmdInfo_Hash][1])`
- `0x1800069a0`: `CBR(0 == memcmp(blobHash.pbData, blobHashed.pbData, c_rgdwCommandInfo[CmdInfo_Hash][1]))`

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
        "CBR(blobHash.cbData > 0)");
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
        "CBR(blobSharedSecret.cbData > 0)");
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
        "CBR(blobData.cbData > 0)");
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
      v10);
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
      "CBR(blobHashed.cbData == c_rgdwCommandInfo[CmdInfo_Hash][1])");
LABEL_20:
  if ( Buf2[1] )
    operator delete(Buf2[1], (unsigned __int64)a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000685c  mov     [rsp+arg_0], rbx
0x180006861  push    rdi
0x180006862  sub     rsp, 40h
0x180006866  cmp     dword ptr [rdx], 0
0x180006869  xorps   xmm0, xmm0
0x18000686c  movups  xmmword ptr [rsp+48h+Buf2], xmm0
0x180006871  mov     rax, r8
0x180006874  mov     rdi, rdx
0x180006877  ja      short loc_1800068A8
0x180006879  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180006880  mov     r8d, 80070057h
0x180006886  mov     ebx, r8d
0x180006889  jz      loc_1800069C3
0x18000688f  lea     rax, aCbrBlobhashCbd; "CBR(blobHash.cbData > 0)"
0x180006896  mov     [rsp+48h+var_20], rax
0x18000689b  mov     dword ptr [rsp+48h+var_28], 2B7h
0x1800068a3  jmp     loc_1800069B7
0x1800068a8  cmp     dword ptr [r8], 0
0x1800068ac  ja      short loc_1800068DD
0x1800068ae  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800068b5  mov     r8d, 80070057h
0x1800068bb  mov     ebx, r8d
0x1800068be  jz      loc_1800069C3
0x1800068c4  lea     rax, aCbrBlobshareds; "CBR(blobSharedSecret.cbData > 0)"
0x1800068cb  mov     [rsp+48h+var_20], rax
0x1800068d0  mov     dword ptr [rsp+48h+var_28], 2B8h
0x1800068d8  jmp     loc_1800069B7
0x1800068dd  cmp     dword ptr [r9], 0
0x1800068e1  ja      short loc_180006912
0x1800068e3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800068ea  mov     r8d, 80070057h
0x1800068f0  mov     ebx, r8d
0x1800068f3  jz      loc_1800069C3
0x1800068f9  lea     rax, aCbrBlobdataCbd; "CBR(blobData.cbData > 0)"
0x180006900  mov     [rsp+48h+var_20], rax
0x180006905  mov     dword ptr [rsp+48h+var_28], 2B9h
0x18000690d  jmp     loc_1800069B7
0x180006912  lea     r8, [rsp+48h+Buf2]; pdwDataLen
0x180006917  mov     rdx, rax; struct _CRYPTOAPI_BLOB *
0x18000691a  mov     rcx, r9; struct _CRYPTOAPI_BLOB *
0x18000691d  call    ?ComputeHMAC@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@0PEAU2@@Z; MdmCrypto::ComputeHMAC(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)
0x180006922  mov     ebx, eax
0x180006924  test    eax, eax
0x180006926  jns     short loc_18000694B
0x180006928  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000692f  jz      loc_1800069C3
0x180006935  lea     rax, aChrMdmcryptoCo; "CHR(MdmCrypto::ComputeHMAC(blobData, bl"...
0x18000693c  mov     [rsp+48h+var_20], rax
0x180006941  mov     dword ptr [rsp+48h+var_28], 2BCh
0x180006949  jmp     short loc_1800069B4
0x18000694b  mov     r8d, 20h ; ' '; Size
0x180006951  cmp     dword ptr [rsp+48h+Buf2], r8d
0x180006956  jz      short loc_180006980
0x180006958  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000695f  mov     r8d, 80070057h
0x180006965  mov     ebx, r8d
0x180006968  jz      short loc_1800069C3
0x18000696a  lea     rax, aCbrBlobhashedC; "CBR(blobHashed.cbData == c_rgdwCommandI"...
0x180006971  mov     [rsp+48h+var_20], rax
0x180006976  mov     dword ptr [rsp+48h+var_28], 2C3h
0x18000697e  jmp     short loc_1800069B7
0x180006980  mov     rdx, [rsp+48h+Buf2+8]; Buf2
0x180006985  mov     rcx, [rdi+8]; Buf1
0x180006989  call    memcmp_0
0x18000698e  test    eax, eax
0x180006990  jz      short loc_1800069C3
0x180006992  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180006999  mov     ebx, 80070005h
0x18000699e  jz      short loc_1800069C3
0x1800069a0  lea     rax, aCbr0MemcmpBlob; "CBR(0 == memcmp(blobHash.pbData, blobHa"...
0x1800069a7  mov     [rsp+48h+var_20], rax
0x1800069ac  mov     dword ptr [rsp+48h+var_28], 2C6h
0x1800069b4  mov     r8d, ebx
0x1800069b7  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800069be  call    McTemplateU0dsqs_EventWriteTransfer
0x1800069c3  mov     rcx, [rsp+48h+Buf2+8]; void *
0x1800069c8  test    rcx, rcx
0x1800069cb  jz      short loc_1800069D2
0x1800069cd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800069d2  mov     eax, ebx
0x1800069d4  mov     rbx, [rsp+48h+arg_0]
0x1800069d9  add     rsp, 40h
0x1800069dd  pop     rdi
0x1800069de  retn
```
