# MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)

- ea: `0x180006964`
- end: `0x180006a97`
- name: `?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z`
- size: `307`
- prototype: `__int64 __fastcall(MdmTaskRequestParserImpl *this, const unsigned __int8 *, unsigned int, unsigned int, unsigned int, unsigned __int8 *Destination, rsize_t DestinationSize)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006aa0`
- `0x18000745c`

## callees

- `0x180006548`
- `0x180006620`
- `0x180006964`

## string_xrefs

- `0x18000699c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmtaskrequestparserimpl.cpp`
- `0x1800069d0`: `CBR(cbDataIn >= dwOffset + cbRead)`
- `0x180006a38`: `CBR(cbDataOut >= cbRead)`
- `0x180006a71`: `CBR(memcpy_s(pbDataOut, cbDataOut, pbDataIn + dwOffset, cbRead) == 0)`

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
0x180006964  push    rbx
0x180006966  sub     rsp, 30h
0x18000696a  mov     r10, rdx
0x18000696d  test    rdx, rdx
0x180006970  jnz     short loc_1800069AD
0x180006972  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180006979  mov     r8d, 80070057h
0x18000697f  mov     ebx, r8d
0x180006982  jz      loc_180006A8F
0x180006988  lea     rax, aCprPbdatain; "CPR(pbDataIn)"
0x18000698f  mov     [rsp+38h+var_10], rax
0x180006994  mov     [rsp+38h+var_18], 28Dh
0x18000699c  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800069a3  call    McTemplateU0dsqs_EventWriteTransfer
0x1800069a8  jmp     loc_180006A8F
0x1800069ad  mov     edx, [rsp+38h+arg_20]
0x1800069b1  lea     eax, [r9+rdx]
0x1800069b5  cmp     r8d, eax
0x1800069b8  jnb     short loc_1800069E6
0x1800069ba  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800069c1  mov     r8d, 80070057h
0x1800069c7  mov     ebx, r8d
0x1800069ca  jz      loc_180006A8F
0x1800069d0  lea     rax, aCbrCbdatainDwo; "CBR(cbDataIn >= dwOffset + cbRead)"
0x1800069d7  mov     [rsp+38h+var_10], rax
0x1800069dc  mov     [rsp+38h+var_18], 28Eh
0x1800069e4  jmp     short loc_18000699C
0x1800069e6  mov     rcx, [rsp+38h+Destination]; Destination
0x1800069eb  test    rcx, rcx
0x1800069ee  jnz     short loc_180006A1C
0x1800069f0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800069f7  mov     r8d, 80070057h
0x1800069fd  mov     ebx, r8d
0x180006a00  jz      loc_180006A8F
0x180006a06  lea     rax, aCprPbdataout; "CPR(pbDataOut)"
0x180006a0d  mov     [rsp+38h+var_10], rax
0x180006a12  mov     [rsp+38h+var_18], 28Fh
0x180006a1a  jmp     short loc_18000699C
0x180006a1c  mov     r9d, r9d; SourceSize
0x180006a1f  cmp     [rsp+38h+DestinationSize], r9
0x180006a24  jnb     short loc_180006A51
0x180006a26  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180006a2d  mov     r8d, 80070057h
0x180006a33  mov     ebx, r8d
0x180006a36  jz      short loc_180006A8F
0x180006a38  lea     rax, aCbrCbdataoutCb; "CBR(cbDataOut >= cbRead)"
0x180006a3f  mov     [rsp+38h+var_10], rax
0x180006a44  mov     [rsp+38h+var_18], 290h
0x180006a4c  jmp     loc_18000699C
0x180006a51  lea     r8, [r10+rdx]; Source
0x180006a55  mov     rdx, [rsp+38h+DestinationSize]; DestinationSize
0x180006a5a  call    memcpy_s
0x180006a5f  test    eax, eax
0x180006a61  jz      short loc_180006A8D
0x180006a63  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180006a6a  mov     ebx, 8000FFFFh
0x180006a6f  jz      short loc_180006A8F
0x180006a71  lea     rax, aCbrMemcpySPbda; "CBR(memcpy_s(pbDataOut, cbDataOut, pbDa"...
0x180006a78  mov     r8d, ebx
0x180006a7b  mov     [rsp+38h+var_10], rax
0x180006a80  mov     [rsp+38h+var_18], 292h
0x180006a88  jmp     loc_18000699C
0x180006a8d  xor     ebx, ebx
0x180006a8f  mov     eax, ebx
0x180006a91  add     rsp, 30h
0x180006a95  pop     rbx
0x180006a96  retn
```
