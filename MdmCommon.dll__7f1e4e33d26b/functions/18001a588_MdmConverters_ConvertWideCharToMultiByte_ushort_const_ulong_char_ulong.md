# MdmConverters::ConvertWideCharToMultiByte(ushort const *,ulong,char * *,ulong *)

- ea: `0x18001a588`
- end: `0x18001a7b8`
- name: `?ConvertWideCharToMultiByte@MdmConverters@@SAJPEBGKPEAPEADPEAK@Z`
- size: `560`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, int cchWideChar, char **, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b394`
- `0x18001c298`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x180006548`
- `0x18001a588`
- `0x18001a7c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a72d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a72d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001a6a9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001a723`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001a6a9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001a723`

## string_xrefs

- `0x18001a5d1`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmconverters.cpp`
- `0x18001a75a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmconverters.cpp`

## pseudocode

```c
__int64 __fastcall MdmConverters::ConvertWideCharToMultiByte(
        LPCWCH lpWideCharStr,
        int cchWideChar,
        char **a3,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rbp
  int cbMultiByte; // r12d
  CHAR *lpMultiByteStr; // rax
  int v13; // edx
  int v14; // ecx
  char *v15; // rsi
  signed int LastError; // eax
  int v17; // edx
  int v18; // ecx

  if ( lpWideCharStr )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        if ( *a3 )
        {
          v8 = -2147024809;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              (_DWORD)lpWideCharStr,
              cchWideChar,
              -2147024809,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmconverters.cpp",
              108,
              (__int64)"CBR(*ppszArray == nullptr)");
        }
        else
        {
          v9 = WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, cchWideChar, 0, 0, 0, 0);
          v10 = v9;
          cbMultiByte = v9 + 1;
          lpMultiByteStr = (CHAR *)operator new[](v9 + 1, (const struct std::nothrow_t *)&std::nothrow);
          v15 = lpMultiByteStr;
          if ( lpMultiByteStr )
          {
            if ( WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, cchWideChar, lpMultiByteStr, cbMultiByte, 0, 0) )
            {
              v8 = 0;
              v15[v10] = 0;
              *a3 = v15;
              *a4 = v10;
            }
            else
            {
              LastError = GetLastError();
              v8 = LastError;
              if ( LastError > 0 )
                v8 = (unsigned __int16)LastError | 0x80070000;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v18,
                  v17,
                  v8,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmconverters.cpp",
                  135,
                  (__int64)"CBR(0 != WideCharToMultiByte( 65001, 0, pwszArray, cchwszArray, pMultiByte, cbNeededLen + 1, "
                           "nullptr, nullptr))");
              operator delete(v15);
            }
          }
          else
          {
            v8 = -2147024882;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v14,
                v13,
                -2147024882,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmconverters.cpp",
                123,
                (__int64)"CBR(pMultiByte != nullptr)");
          }
        }
      }
      else
      {
        v8 = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            (_DWORD)lpWideCharStr,
            cchWideChar,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmconverters.cpp",
            107,
            (__int64)"CPR(pcbArray)");
      }
    }
    else
    {
      v8 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)lpWideCharStr,
          cchWideChar,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmconverters.cpp",
          106,
          (__int64)"CPR(ppszArray)");
    }
  }
  else
  {
    v8 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        cchWideChar,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmconverters.cpp",
        105,
        (__int64)"CPR(pwszArray)");
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McTemplateU0dzs_EventWriteTransfer(
      (unsigned int)*a3,
      (unsigned int)MDMCOMMON_WIDE_TO_MULTIBYTE_CONVERSION,
      v8,
      (_DWORD)lpWideCharStr,
      (__int64)*a3);
  return v8;
}

```

## disassembly

```asm
0x18001a588  push    rbx
0x18001a58a  push    rbp
0x18001a58b  push    rsi
0x18001a58c  push    rdi
0x18001a58d  push    r12
0x18001a58f  push    r14
0x18001a591  push    r15
0x18001a593  sub     rsp, 40h
0x18001a597  mov     r14, r9
0x18001a59a  mov     rdi, r8
0x18001a59d  mov     ebx, edx
0x18001a59f  mov     r15, rcx
0x18001a5a2  test    rcx, rcx
0x18001a5a5  jnz     short loc_18001A5E2
0x18001a5a7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a5ae  mov     r8d, 80070057h
0x18001a5b4  mov     ebx, r8d
0x18001a5b7  jz      loc_18001A784
0x18001a5bd  lea     rax, aCprPwszarray; "CPR(pwszArray)"
0x18001a5c4  mov     qword ptr [rsp+78h+cbMultiByte], rax
0x18001a5c9  mov     dword ptr [rsp+78h+lpMultiByteStr], 69h ; 'i'
0x18001a5d1  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001a5d8  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a5dd  jmp     loc_18001A784
0x18001a5e2  test    rdi, rdi
0x18001a5e5  jnz     short loc_18001A613
0x18001a5e7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a5ee  mov     r8d, 80070057h
0x18001a5f4  mov     ebx, r8d
0x18001a5f7  jz      loc_18001A784
0x18001a5fd  lea     rax, aCprPpszarray; "CPR(ppszArray)"
0x18001a604  mov     qword ptr [rsp+78h+cbMultiByte], rax
0x18001a609  mov     dword ptr [rsp+78h+lpMultiByteStr], 6Ah ; 'j'
0x18001a611  jmp     short loc_18001A5D1
0x18001a613  test    r14, r14
0x18001a616  jnz     short loc_18001A644
0x18001a618  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a61f  mov     r8d, 80070057h
0x18001a625  mov     ebx, r8d
0x18001a628  jz      loc_18001A784
0x18001a62e  lea     rax, aCprPcbarray; "CPR(pcbArray)"
0x18001a635  mov     qword ptr [rsp+78h+cbMultiByte], rax
0x18001a63a  mov     dword ptr [rsp+78h+lpMultiByteStr], 6Bh ; 'k'
0x18001a642  jmp     short loc_18001A5D1
0x18001a644  cmp     qword ptr [r8], 0
0x18001a648  jz      short loc_18001A679
0x18001a64a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a651  mov     r8d, 80070057h
0x18001a657  mov     ebx, r8d
0x18001a65a  jz      loc_18001A784
0x18001a660  lea     rax, aCbrPpszarrayNu; "CBR(*ppszArray == nullptr)"
0x18001a667  mov     qword ptr [rsp+78h+cbMultiByte], rax
0x18001a66c  mov     dword ptr [rsp+78h+lpMultiByteStr], 6Ch ; 'l'
0x18001a674  jmp     loc_18001A5D1
0x18001a679  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001a682  mov     r9d, ebx; cchWideChar
0x18001a685  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x18001a68e  mov     r8, r15; lpWideCharStr
0x18001a691  mov     [rsp+78h+cbMultiByte], 0; cbMultiByte
0x18001a699  xor     edx, edx; dwFlags
0x18001a69b  mov     ecx, 0FDE9h; CodePage
0x18001a6a0  mov     [rsp+78h+lpMultiByteStr], 0; lpMultiByteStr
0x18001a6a9  call    cs:__imp_WideCharToMultiByte
0x18001a6af  mov     ebp, eax
0x18001a6b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a6b8  lea     r12d, [rbp+1]
0x18001a6bc  mov     ecx, r12d; unsigned __int64
0x18001a6bf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001a6c4  mov     rsi, rax
0x18001a6c7  test    rax, rax
0x18001a6ca  jnz     short loc_18001A6FA
0x18001a6cc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a6d3  mov     ebx, 8007000Eh
0x18001a6d8  jz      loc_18001A784
0x18001a6de  lea     rax, aCbrPmultibyteN; "CBR(pMultiByte != nullptr)"
0x18001a6e5  mov     r8d, ebx
0x18001a6e8  mov     qword ptr [rsp+78h+cbMultiByte], rax
0x18001a6ed  mov     dword ptr [rsp+78h+lpMultiByteStr], 7Bh ; '{'
0x18001a6f5  jmp     loc_18001A5D1
0x18001a6fa  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001a703  mov     r9d, ebx; cchWideChar
0x18001a706  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x18001a70f  mov     r8, r15; lpWideCharStr
0x18001a712  mov     [rsp+78h+cbMultiByte], r12d; cbMultiByte
0x18001a717  xor     edx, edx; dwFlags
0x18001a719  mov     ecx, 0FDE9h; CodePage
0x18001a71e  mov     [rsp+78h+lpMultiByteStr], rsi; lpMultiByteStr
0x18001a723  call    cs:__imp_WideCharToMultiByte
0x18001a729  test    eax, eax
0x18001a72b  jnz     short loc_18001A778
0x18001a72d  call    cs:__imp_GetLastError
0x18001a733  mov     ebx, eax
0x18001a735  test    eax, eax
0x18001a737  jle     short loc_18001A742
0x18001a739  movzx   ebx, ax
0x18001a73c  or      ebx, 80070000h
0x18001a742  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001a749  jz      short loc_18001A76E
0x18001a74b  lea     rax, aCbr0Widecharto; "CBR(0 != WideCharToMultiByte( 65001, 0,"...
0x18001a752  mov     r8d, ebx
0x18001a755  mov     qword ptr [rsp+78h+cbMultiByte], rax
0x18001a75a  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001a761  mov     dword ptr [rsp+78h+lpMultiByteStr], 87h
0x18001a769  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a76e  mov     rcx, rsi; void *
0x18001a771  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a776  jmp     short loc_18001A784
0x18001a778  xor     ebx, ebx
0x18001a77a  mov     [rbp+rsi+0], bl
0x18001a77e  mov     [rdi], rsi
0x18001a781  mov     [r14], ebp
0x18001a784  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x18001a78b  jz      short loc_18001A7A7
0x18001a78d  mov     rcx, [rdi]
0x18001a790  lea     rdx, MDMCOMMON_WIDE_TO_MULTIBYTE_CONVERSION
0x18001a797  mov     r9, r15
0x18001a79a  mov     [rsp+78h+lpMultiByteStr], rcx
0x18001a79f  mov     r8d, ebx
0x18001a7a2  call    McTemplateU0dzs_EventWriteTransfer
0x18001a7a7  mov     eax, ebx
0x18001a7a9  add     rsp, 40h
0x18001a7ad  pop     r15
0x18001a7af  pop     r14
0x18001a7b1  pop     r12
0x18001a7b3  pop     rdi
0x18001a7b4  pop     rsi
0x18001a7b5  pop     rbp
0x18001a7b6  pop     rbx
0x18001a7b7  retn
```
