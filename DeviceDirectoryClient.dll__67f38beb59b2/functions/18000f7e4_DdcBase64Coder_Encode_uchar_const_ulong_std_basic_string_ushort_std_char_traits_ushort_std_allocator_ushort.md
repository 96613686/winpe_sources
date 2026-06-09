# DdcBase64Coder::Encode(uchar const *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000f7e4`
- end: `0x18000f93f`
- name: `?Encode@DdcBase64Coder@@QEAAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(DdcBase64Coder *, const unsigned __int8 *, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012c94`
- `0x180013004`
- `0x1800132e4`

## callees

- `0x180004e10`
- `0x1800050b8`
- `0x18000f7e4`
- `0x18000f948`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f924`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f924`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000f895`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000f895`

## string_xrefs

- `0x18000f836`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcbase64coder.cpp`
- `0x18000f900`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcbase64coder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdcBase64Coder::Encode(DdcBase64Coder *a1, const unsigned __int8 *a2, unsigned int a3, __int64 a4)
{
  int v7; // ebx
  int v8; // edx
  int v9; // ecx
  int v10; // edx
  DdcBase64Coder *v11; // rcx
  unsigned __int16 *v12; // rdi
  int v13; // edx
  int v14; // ecx
  unsigned __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  v16 = 0;
  if ( a2 )
  {
    v7 = DdcBase64Coder::_Encode(a1, a2, a3, 0, &v16);
    if ( v7 >= 0 )
    {
      ++v16;
      v12 = (unsigned __int16 *)malloc(2 * v16);
      if ( v12 )
      {
        v7 = DdcBase64Coder::_Encode(v11, a2, a3, v12, &v16);
        if ( v7 >= 0 )
        {
          std::wstring::assign(a4, v12);
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v14,
            v13,
            v7,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcbase64coder.cpp",
            77,
            (__int64)"CHR(_Encode( pbBinaryData, cbBinaryData, pszBuffer, cchEncodedData ))");
        }
        free(v12);
      }
      else
      {
        v7 = -2147024882;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            (_DWORD)v11,
            v10,
            -2147024882,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcbase64coder.cpp",
            69,
            (__int64)"CBR(0 != pszBuffer)");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        v7,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcbase64coder.cpp",
        61,
        (__int64)"CHR(_Encode(pbBinaryData, cbBinaryData, 0, cchEncodedData))");
    }
  }
  else
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcbase64coder.cpp",
        57,
        (__int64)"CPR(pbBinaryData)");
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f7e4  mov     r11, rsp
0x18000f7e7  mov     [r11+10h], rbx
0x18000f7eb  mov     [r11+18h], rbp
0x18000f7ef  mov     [r11+8], rcx
0x18000f7f3  push    rsi
0x18000f7f4  push    rdi
0x18000f7f5  push    r14
0x18000f7f7  sub     rsp, 30h
0x18000f7fb  mov     qword ptr [r11+8], 0
0x18000f803  mov     r14, r9
0x18000f806  mov     ebp, r8d
0x18000f809  mov     rsi, rdx
0x18000f80c  test    rdx, rdx
0x18000f80f  jnz     short loc_18000F84A
0x18000f811  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f818  mov     ebx, 80070057h
0x18000f81d  jz      loc_18000F92A
0x18000f823  lea     rax, aCprPbbinarydat; "CPR(pbBinaryData)"
0x18000f82a  mov     [r11-20h], rax
0x18000f82e  mov     dword ptr [rsp+48h+var_28], 39h ; '9'
0x18000f836  lea     r9, aOnecoreuapShel_11; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000f83d  mov     r8d, ebx
0x18000f840  call    McTemplateU0dsqs_EventWriteTransfer
0x18000f845  jmp     loc_18000F92A
0x18000f84a  lea     rax, [rsp+48h+arg_0]
0x18000f84f  xor     r9d, r9d; unsigned __int16 *
0x18000f852  mov     [rsp+48h+var_28], rax; unsigned __int64 *
0x18000f857  call    ?_Encode@DdcBase64Coder@@AEAAJPEBEKPEAGAEA_K@Z; DdcBase64Coder::_Encode(uchar const *,ulong,ushort *,unsigned __int64 &)
0x18000f85c  mov     ebx, eax
0x18000f85e  test    eax, eax
0x18000f860  jns     short loc_18000F885
0x18000f862  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f869  jz      loc_18000F92A
0x18000f86f  lea     rax, aChrEncodePbbin_0; "CHR(_Encode(pbBinaryData, cbBinaryData,"...
0x18000f876  mov     [rsp+48h+var_20], rax
0x18000f87b  mov     dword ptr [rsp+48h+var_28], 3Dh ; '='
0x18000f883  jmp     short loc_18000F836
0x18000f885  mov     rcx, [rsp+48h+arg_0]
0x18000f88a  inc     rcx
0x18000f88d  mov     [rsp+48h+arg_0], rcx
0x18000f892  add     rcx, rcx; Size
0x18000f895  call    cs:__imp_malloc
0x18000f89b  mov     rdi, rax
0x18000f89e  test    rax, rax
0x18000f8a1  jnz     short loc_18000F8CA
0x18000f8a3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f8aa  mov     ebx, 8007000Eh
0x18000f8af  jz      short loc_18000F92A
0x18000f8b1  lea     rax, aCbr0Pszbuffer; "CBR(0 != pszBuffer)"
0x18000f8b8  mov     [rsp+48h+var_20], rax
0x18000f8bd  mov     dword ptr [rsp+48h+var_28], 45h ; 'E'
0x18000f8c5  jmp     loc_18000F836
0x18000f8ca  lea     rax, [rsp+48h+arg_0]
0x18000f8cf  mov     r9, rdi; unsigned __int16 *
0x18000f8d2  mov     r8d, ebp; unsigned int
0x18000f8d5  mov     [rsp+48h+var_28], rax; unsigned __int64 *
0x18000f8da  mov     rdx, rsi; unsigned __int8 *
0x18000f8dd  call    ?_Encode@DdcBase64Coder@@AEAAJPEBEKPEAGAEA_K@Z; DdcBase64Coder::_Encode(uchar const *,ulong,ushort *,unsigned __int64 &)
0x18000f8e2  mov     ebx, eax
0x18000f8e4  test    eax, eax
0x18000f8e6  jns     short loc_18000F916
0x18000f8e8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f8ef  jz      short loc_18000F921
0x18000f8f1  lea     rax, aChrEncodePbbin; "CHR(_Encode( pbBinaryData, cbBinaryData"...
0x18000f8f8  mov     r8d, ebx
0x18000f8fb  mov     [rsp+48h+var_20], rax
0x18000f900  lea     r9, aOnecoreuapShel_11; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000f907  mov     dword ptr [rsp+48h+var_28], 4Dh ; 'M'
0x18000f90f  call    McTemplateU0dsqs_EventWriteTransfer
0x18000f914  jmp     short loc_18000F921
0x18000f916  mov     rdx, rdi
0x18000f919  mov     rcx, r14
0x18000f91c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18000f921  mov     rcx, rdi; Block
0x18000f924  call    cs:__imp_free
0x18000f92a  mov     rbp, [rsp+48h+arg_10]
0x18000f92f  mov     eax, ebx
0x18000f931  mov     rbx, [rsp+48h+arg_8]
0x18000f936  add     rsp, 30h
0x18000f93a  pop     r14
0x18000f93c  pop     rdi
0x18000f93d  pop     rsi
0x18000f93e  retn
```
