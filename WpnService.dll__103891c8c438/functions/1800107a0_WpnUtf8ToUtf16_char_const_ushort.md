# WpnUtf8ToUtf16(char const *,ushort * *)

- ea: `0x1800107a0`
- end: `0x1800109cc`
- name: `?WpnUtf8ToUtf16@@YAJPEBDPEAPEAG@Z`
- size: `556`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010620`
- `0x180010720`

## callees

- `0x1800107a0`
- `0x1800109d4`
- `0x1800341b4`
- `0x1800342bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001092a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001092a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001080b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001080b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001091c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001091c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108b3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800107e2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010839`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800107e2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010839`

## string_xrefs

- `0x180010872`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`
- `0x1800108cd`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`
- `0x180010977`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`

## pseudocode

```c
__int64 __fastcall WpnUtf8ToUtf16(LPCCH lpMultiByteStr, unsigned __int16 **a2)
{
  int v4; // eax
  __int64 cchWideChar; // rbp
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  unsigned __int16 *v8; // rdi
  signed int v10; // eax
  unsigned int v11; // ebx
  signed int LastError; // eax
  unsigned int v13; // ebx
  HANDLE v14; // rax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !lpMultiByteStr )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v4 = MultiByteToWideChar(0xFDE9u, 8u, lpMultiByteStr, -1, 0, 0);
  cchWideChar = v4;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2 * cchWideChar);
    v8 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      if ( MultiByteToWideChar(0xFDE9u, 8u, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
      {
        *a2 = v8;
        return 0;
      }
      else
      {
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        if ( (v13 & 0x80000000) == 0 )
          v13 = -2147467259;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xFD,
          (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
          (const char *)v13);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids, v13);
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v8);
        return v13;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF4,
        (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
        (const char *)0x8007000ELL);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids, 2147942414LL);
      return 2147942414LL;
    }
  }
  else
  {
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    if ( (v11 & 0x80000000) == 0 )
      v11 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xF1,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
      (const char *)v11);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids, v11);
    return v11;
  }
}

```

## disassembly

```asm
0x1800107a0  push    rbx
0x1800107a2  push    rbp
0x1800107a3  push    rsi
0x1800107a4  push    r14
0x1800107a6  sub     rsp, 38h
0x1800107aa  mov     rsi, rdx
0x1800107ad  mov     rbx, rcx
0x1800107b0  test    rcx, rcx
0x1800107b3  jz      loc_180010937
0x1800107b9  test    rsi, rsi
0x1800107bc  jz      loc_180010941
0x1800107c2  xor     r14d, r14d
0x1800107c5  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800107cb  mov     [rsp+58h+cchWideChar], r14d; cchWideChar
0x1800107d0  mov     r8, rbx; lpMultiByteStr
0x1800107d3  mov     edx, 8; dwFlags
0x1800107d8  mov     [rsp+58h+lpWideCharStr], r14; int
0x1800107dd  mov     ecx, 0FDE9h; CodePage
0x1800107e2  call    cs:__imp_MultiByteToWideChar
0x1800107e8  movsxd  rbp, eax
0x1800107eb  test    eax, eax
0x1800107ed  jz      short loc_180010858
0x1800107ef  mov     [rsp+58h+arg_0], rdi
0x1800107f4  mov     rdi, rbp
0x1800107f7  add     rdi, rdi
0x1800107fa  call    cs:__imp_GetProcessHeap
0x180010800  mov     r8, rdi; dwBytes
0x180010803  mov     edx, 8; dwFlags
0x180010808  mov     rcx, rax; hHeap
0x18001080b  call    cs:__imp_HeapAlloc
0x180010811  mov     rdi, rax
0x180010814  test    rax, rax
0x180010817  jz      loc_180010972
0x18001081d  mov     [rsp+58h+cchWideChar], ebp; cchWideChar
0x180010821  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180010827  mov     r8, rbx; lpMultiByteStr
0x18001082a  mov     [rsp+58h+lpWideCharStr], rax; int
0x18001082f  mov     edx, 8; dwFlags
0x180010834  mov     ecx, 0FDE9h; CodePage
0x180010839  call    cs:__imp_MultiByteToWideChar
0x18001083f  test    eax, eax
0x180010841  jz      short loc_1800108B3
0x180010843  mov     [rsi], rdi
0x180010846  mov     eax, r14d
0x180010849  mov     rdi, [rsp+58h+arg_0]
0x18001084e  add     rsp, 38h
0x180010852  pop     r14
0x180010854  pop     rsi
0x180010855  pop     rbp
0x180010856  pop     rbx
0x180010857  retn
0x180010858  call    cs:__imp_GetLastError
0x18001085e  mov     ebx, eax
0x180010860  test    eax, eax
0x180010862  jle     short loc_18001086D
0x180010864  movzx   ebx, ax
0x180010867  or      ebx, 80070000h
0x18001086d  mov     rcx, [rsp+58h]; this
0x180010872  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010879  test    ebx, ebx
0x18001087b  mov     eax, 80004005h
0x180010880  mov     edx, 0F1h; void *
0x180010885  cmovns  ebx, eax
0x180010888  mov     r9d, ebx; char *
0x18001088b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010890  mov     rcx, cs:WPP_GLOBAL_Control
0x180010897  lea     rax, WPP_GLOBAL_Control
0x18001089e  cmp     rcx, rax
0x1800108a1  jnz     loc_18001094B
0x1800108a7  mov     eax, ebx
0x1800108a9  add     rsp, 38h
0x1800108ad  pop     r14
0x1800108af  pop     rsi
0x1800108b0  pop     rbp
0x1800108b1  pop     rbx
0x1800108b2  retn
0x1800108b3  call    cs:__imp_GetLastError
0x1800108b9  mov     ebx, eax
0x1800108bb  test    eax, eax
0x1800108bd  jle     short loc_1800108C8
0x1800108bf  movzx   ebx, ax
0x1800108c2  or      ebx, 80070000h
0x1800108c8  mov     rcx, [rsp+58h]; this
0x1800108cd  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800108d4  test    ebx, ebx
0x1800108d6  mov     eax, 80004005h
0x1800108db  mov     edx, 0FDh; void *
0x1800108e0  cmovns  ebx, eax
0x1800108e3  mov     r9d, ebx; char *
0x1800108e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800108eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108f2  lea     rax, WPP_GLOBAL_Control
0x1800108f9  cmp     rcx, rax
0x1800108fc  jz      short loc_18001091C
0x1800108fe  test    byte ptr [rcx+1Ch], 80h
0x180010902  jz      short loc_18001091C
0x180010904  mov     rcx, [rcx+10h]
0x180010908  lea     r8, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids
0x18001090f  mov     edx, 17h
0x180010914  mov     r9d, ebx
0x180010917  call    WPP_SF_D
0x18001091c  call    cs:__imp_GetProcessHeap
0x180010922  mov     r8, rdi; lpMem
0x180010925  xor     edx, edx; dwFlags
0x180010927  mov     rcx, rax; hHeap
0x18001092a  call    cs:__imp_HeapFree
0x180010930  mov     eax, ebx
0x180010932  jmp     loc_180010849
0x180010937  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001093c  jmp     loc_1800107B9
0x180010941  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010946  jmp     loc_1800107C2
0x18001094b  test    byte ptr [rcx+1Ch], 80h
0x18001094f  jz      loc_1800108A7
0x180010955  mov     rcx, [rcx+10h]
0x180010959  lea     r8, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids
0x180010960  mov     edx, 15h
0x180010965  mov     r9d, ebx
0x180010968  call    WPP_SF_D
0x18001096d  jmp     loc_1800108A7
0x180010972  mov     rcx, [rsp+58h]; this
0x180010977  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001097e  mov     r9d, 8007000Eh; char *
0x180010984  mov     edx, 0F4h; void *
0x180010989  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001098e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010995  lea     rax, WPP_GLOBAL_Control
0x18001099c  cmp     rcx, rax
0x18001099f  jz      short loc_1800109C2
0x1800109a1  test    byte ptr [rcx+1Ch], 80h
0x1800109a5  jz      short loc_1800109C2
0x1800109a7  mov     rcx, [rcx+10h]
0x1800109ab  lea     r8, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids
0x1800109b2  mov     edx, 16h
0x1800109b7  mov     r9d, 8007000Eh
0x1800109bd  call    WPP_SF_D
0x1800109c2  mov     eax, 8007000Eh
0x1800109c7  jmp     loc_180010849
```
