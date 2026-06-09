# MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)

- ea: `0x1800069e8`
- end: `0x180006b1c`
- name: `?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z`
- size: `308`
- prototype: `__int64 __fastcall(MdmTaskRequestParserImpl *this, const unsigned __int8 *, unsigned int, unsigned int, unsigned int, unsigned __int8 *Destination, rsize_t DestinationSize)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006b24`
- `0x1800074e4`

## callees

- `0x1800065c0`
- `0x180006698`
- `0x1800069e8`

## string_xrefs

- `0x180006a20`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmtaskrequestparserimpl.cpp`
- `0x180006a54`: `CBR(cbDataIn >= dwOffset + cbRead)`
- `0x180006abc`: `CBR(cbDataOut >= cbRead)`
- `0x180006af5`: `CBR(memcpy_s(pbDataOut, cbDataOut, pbDataIn + dwOffset, cbRead) == 0)`

## pseudocode

```c
__int64 __fastcall MdmTaskRequestParserImpl::CopyBytes(
        MdmTaskRequestParserImpl *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int8 *Destination,
        rsize_t DestinationSize)
{
  unsigned int v7; // ebx
  int v8; // edx
  int v9; // ecx

  if ( a2 )
  {
    if ( a3 >= a4 + a5 )
    {
      if ( Destination )
      {
        if ( DestinationSize >= a4 )
        {
          if ( memcpy_s(Destination, DestinationSize, &a2[a5], a4) )
          {
            v7 = -2147418113;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v9,
                v8,
                -2147418113,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
                146,
                (__int64)"CBR(memcpy_s(pbDataOut, cbDataOut, pbDataIn + dwOffset, cbRead) == 0)");
          }
          else
          {
            return 0;
          }
        }
        else
        {
          v7 = -2147024809;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              (_DWORD)Destination,
              a5,
              -2147024809,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
              144,
              (__int64)"CBR(cbDataOut >= cbRead)");
        }
      }
      else
      {
        v7 = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            0,
            a5,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
            143,
            (__int64)"CPR(pbDataOut)");
      }
    }
    else
    {
      v7 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)this,
          a5,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
          142,
          (__int64)"CBR(cbDataIn >= dwOffset + cbRead)");
    }
  }
  else
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
        141,
        (__int64)"CPR(pbDataIn)");
  }
  return v7;
}

```

## disassembly

```asm
0x1800069e8  push    rbx
0x1800069ea  sub     rsp, 30h
0x1800069ee  mov     r10, rdx
0x1800069f1  test    rdx, rdx
0x1800069f4  jnz     short loc_180006A31
0x1800069f6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800069fd  mov     r8d, 80070057h
0x180006a03  mov     ebx, r8d
0x180006a06  jz      loc_180006B13
0x180006a0c  lea     rax, aCprPbdatain; "CPR(pbDataIn)"
0x180006a13  mov     [rsp+38h+var_10], rax
0x180006a18  mov     [rsp+38h+var_18], 28Dh
0x180006a20  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180006a27  call    McTemplateU0dsqs_EventWriteTransfer
0x180006a2c  jmp     loc_180006B13
0x180006a31  mov     edx, [rsp+38h+arg_20]
0x180006a35  lea     eax, [r9+rdx]
0x180006a39  cmp     r8d, eax
0x180006a3c  jnb     short loc_180006A6A
0x180006a3e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180006a45  mov     r8d, 80070057h
0x180006a4b  mov     ebx, r8d
0x180006a4e  jz      loc_180006B13
0x180006a54  lea     rax, aCbrCbdatainDwo; "CBR(cbDataIn >= dwOffset + cbRead)"
0x180006a5b  mov     [rsp+38h+var_10], rax
0x180006a60  mov     [rsp+38h+var_18], 28Eh
0x180006a68  jmp     short loc_180006A20
0x180006a6a  mov     rcx, [rsp+38h+Destination]; Destination
0x180006a6f  test    rcx, rcx
0x180006a72  jnz     short loc_180006AA0
0x180006a74  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180006a7b  mov     r8d, 80070057h
0x180006a81  mov     ebx, r8d
0x180006a84  jz      loc_180006B13
0x180006a8a  lea     rax, aCprPbdataout; "CPR(pbDataOut)"
0x180006a91  mov     [rsp+38h+var_10], rax
0x180006a96  mov     [rsp+38h+var_18], 28Fh
0x180006a9e  jmp     short loc_180006A20
0x180006aa0  mov     r9d, r9d; SourceSize
0x180006aa3  cmp     [rsp+38h+DestinationSize], r9
0x180006aa8  jnb     short loc_180006AD5
0x180006aaa  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180006ab1  mov     r8d, 80070057h
0x180006ab7  mov     ebx, r8d
0x180006aba  jz      short loc_180006B13
0x180006abc  lea     rax, aCbrCbdataoutCb; "CBR(cbDataOut >= cbRead)"
0x180006ac3  mov     [rsp+38h+var_10], rax
0x180006ac8  mov     [rsp+38h+var_18], 290h
0x180006ad0  jmp     loc_180006A20
0x180006ad5  lea     r8, [r10+rdx]; Source
0x180006ad9  mov     rdx, [rsp+38h+DestinationSize]; DestinationSize
0x180006ade  call    memcpy_s
0x180006ae3  test    eax, eax
0x180006ae5  jz      short loc_180006B11
0x180006ae7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180006aee  mov     ebx, 8000FFFFh
0x180006af3  jz      short loc_180006B13
0x180006af5  lea     rax, aCbrMemcpySPbda; "CBR(memcpy_s(pbDataOut, cbDataOut, pbDa"...
0x180006afc  mov     r8d, ebx
0x180006aff  mov     [rsp+38h+var_10], rax
0x180006b04  mov     [rsp+38h+var_18], 292h
0x180006b0c  jmp     loc_180006A20
0x180006b11  xor     ebx, ebx
0x180006b13  mov     eax, ebx
0x180006b15  add     rsp, 30h
0x180006b19  pop     rbx
0x180006b1a  retn
```
