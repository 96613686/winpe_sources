# MdmConverters::ConvertWideCharToMultiByte(ushort const *,ulong,char * *,ulong *)

- ea: `0x18001aac0`
- end: `0x18001ad03`
- name: `?ConvertWideCharToMultiByte@MdmConverters@@SAJPEBGKPEAPEADPEAK@Z`
- size: `579`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, int cchWideChar, char **, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b924`
- `0x18001c8d0`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x1800065c0`
- `0x18001aac0`
- `0x18001ad0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac71`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001abe1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001ac61`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001abe1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001ac61`

## string_xrefs

- `0x18001ab09`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmconverters.cpp`
- `0x18001aca4`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmconverters.cpp`

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
  unsigned __int64 v17; // rdx
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
              operator delete(v15, v17);
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
0x18001aac0  push    rbx
0x18001aac2  push    rbp
0x18001aac3  push    rsi
0x18001aac4  push    rdi
0x18001aac5  push    r12
0x18001aac7  push    r14
0x18001aac9  push    r15
0x18001aacb  sub     rsp, 40h
0x18001aacf  mov     r14, r9
0x18001aad2  mov     rdi, r8
0x18001aad5  mov     ebx, edx
0x18001aad7  mov     r15, rcx
0x18001aada  test    rcx, rcx
0x18001aadd  jnz     short loc_18001AB1A
0x18001aadf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001aae6  mov     r8d, 80070057h
0x18001aaec  mov     ebx, r8d
0x18001aaef  jz      loc_18001ACCE
0x18001aaf5  lea     rax, aCprPwszarray; "CPR(pwszArray)"
0x18001aafc  mov     qword ptr [rsp+78h+cbMultiByte], rax
0x18001ab01  mov     dword ptr [rsp+78h+lpMultiByteStr], 69h ; 'i'
0x18001ab09  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001ab10  call    McTemplateU0dsqs_EventWriteTransfer
0x18001ab15  jmp     loc_18001ACCE
0x18001ab1a  test    rdi, rdi
0x18001ab1d  jnz     short loc_18001AB4B
0x18001ab1f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ab26  mov     r8d, 80070057h
0x18001ab2c  mov     ebx, r8d
0x18001ab2f  jz      loc_18001ACCE
0x18001ab35  lea     rax, aCprPpszarray; "CPR(ppszArray)"
0x18001ab3c  mov     qword ptr [rsp+78h+cbMultiByte], rax
0x18001ab41  mov     dword ptr [rsp+78h+lpMultiByteStr], 6Ah ; 'j'
0x18001ab49  jmp     short loc_18001AB09
0x18001ab4b  test    r14, r14
0x18001ab4e  jnz     short loc_18001AB7C
0x18001ab50  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ab57  mov     r8d, 80070057h
0x18001ab5d  mov     ebx, r8d
0x18001ab60  jz      loc_18001ACCE
0x18001ab66  lea     rax, aCprPcbarray; "CPR(pcbArray)"
0x18001ab6d  mov     qword ptr [rsp+78h+cbMultiByte], rax
0x18001ab72  mov     dword ptr [rsp+78h+lpMultiByteStr], 6Bh ; 'k'
0x18001ab7a  jmp     short loc_18001AB09
0x18001ab7c  cmp     qword ptr [r8], 0
0x18001ab80  jz      short loc_18001ABB1
0x18001ab82  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ab89  mov     r8d, 80070057h
0x18001ab8f  mov     ebx, r8d
0x18001ab92  jz      loc_18001ACCE
0x18001ab98  lea     rax, aCbrPpszarrayNu; "CBR(*ppszArray == nullptr)"
0x18001ab9f  mov     qword ptr [rsp+78h+cbMultiByte], rax
0x18001aba4  mov     dword ptr [rsp+78h+lpMultiByteStr], 6Ch ; 'l'
0x18001abac  jmp     loc_18001AB09
0x18001abb1  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001abba  mov     r9d, ebx; cchWideChar
0x18001abbd  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x18001abc6  mov     r8, r15; lpWideCharStr
0x18001abc9  mov     [rsp+78h+cbMultiByte], 0; cbMultiByte
0x18001abd1  xor     edx, edx; dwFlags
0x18001abd3  mov     ecx, 0FDE9h; CodePage
0x18001abd8  mov     [rsp+78h+lpMultiByteStr], 0; lpMultiByteStr
0x18001abe1  call    cs:__imp_WideCharToMultiByte
0x18001abe8  nop     dword ptr [rax+rax+00h]
0x18001abed  mov     ebp, eax
0x18001abef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001abf6  lea     r12d, [rbp+1]
0x18001abfa  mov     ecx, r12d; unsigned __int64
0x18001abfd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ac02  mov     rsi, rax
0x18001ac05  test    rax, rax
0x18001ac08  jnz     short loc_18001AC38
0x18001ac0a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ac11  mov     ebx, 8007000Eh
0x18001ac16  jz      loc_18001ACCE
0x18001ac1c  lea     rax, aCbrPmultibyteN; "CBR(pMultiByte != nullptr)"
0x18001ac23  mov     r8d, ebx
0x18001ac26  mov     qword ptr [rsp+78h+cbMultiByte], rax
0x18001ac2b  mov     dword ptr [rsp+78h+lpMultiByteStr], 7Bh ; '{'
0x18001ac33  jmp     loc_18001AB09
0x18001ac38  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001ac41  mov     r9d, ebx; cchWideChar
0x18001ac44  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x18001ac4d  mov     r8, r15; lpWideCharStr
0x18001ac50  mov     [rsp+78h+cbMultiByte], r12d; cbMultiByte
0x18001ac55  xor     edx, edx; dwFlags
0x18001ac57  mov     ecx, 0FDE9h; CodePage
0x18001ac5c  mov     [rsp+78h+lpMultiByteStr], rsi; lpMultiByteStr
0x18001ac61  call    cs:__imp_WideCharToMultiByte
0x18001ac68  nop     dword ptr [rax+rax+00h]
0x18001ac6d  test    eax, eax
0x18001ac6f  jnz     short loc_18001ACC2
0x18001ac71  call    cs:__imp_GetLastError
0x18001ac78  nop     dword ptr [rax+rax+00h]
0x18001ac7d  mov     ebx, eax
0x18001ac7f  test    eax, eax
0x18001ac81  jle     short loc_18001AC8C
0x18001ac83  movzx   ebx, ax
0x18001ac86  or      ebx, 80070000h
0x18001ac8c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ac93  jz      short loc_18001ACB8
0x18001ac95  lea     rax, aCbr0Widecharto; "CBR(0 != WideCharToMultiByte( 65001, 0,"...
0x18001ac9c  mov     r8d, ebx
0x18001ac9f  mov     qword ptr [rsp+78h+cbMultiByte], rax
0x18001aca4  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001acab  mov     dword ptr [rsp+78h+lpMultiByteStr], 87h
0x18001acb3  call    McTemplateU0dsqs_EventWriteTransfer
0x18001acb8  mov     rcx, rsi; void *
0x18001acbb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001acc0  jmp     short loc_18001ACCE
0x18001acc2  xor     ebx, ebx
0x18001acc4  mov     [rbp+rsi+0], bl
0x18001acc8  mov     [rdi], rsi
0x18001accb  mov     [r14], ebp
0x18001acce  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x18001acd5  jz      short loc_18001ACF1
0x18001acd7  mov     rcx, [rdi]
0x18001acda  lea     rdx, MDMCOMMON_WIDE_TO_MULTIBYTE_CONVERSION
0x18001ace1  mov     r9, r15
0x18001ace4  mov     [rsp+78h+lpMultiByteStr], rcx
0x18001ace9  mov     r8d, ebx
0x18001acec  call    McTemplateU0dzs_EventWriteTransfer
0x18001acf1  mov     eax, ebx
0x18001acf3  add     rsp, 40h
0x18001acf7  pop     r15
0x18001acf9  pop     r14
0x18001acfb  pop     r12
0x18001acfd  pop     rdi
0x18001acfe  pop     rsi
0x18001acff  pop     rbp
0x18001ad00  pop     rbx
0x18001ad01  retn
```
