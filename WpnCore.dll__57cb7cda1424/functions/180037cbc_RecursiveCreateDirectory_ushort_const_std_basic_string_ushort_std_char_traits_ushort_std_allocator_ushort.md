# RecursiveCreateDirectory(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180037cbc`
- end: `0x180037f71`
- name: `?RecursiveCreateDirectory@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(const WCHAR *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180037600`
- `0x18004761c`

## callees

- `0x18002ee38`
- `0x1800372d0`
- `0x180037cbc`
- `0x1800af0a4`
- `0x1800be924`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ddc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180037df8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180037df8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180037dd2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180037dd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037dae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037dae`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x180037d1e`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x180037d1e`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180037d0a`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180037d0a`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180037ce5`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180037ce5`

## string_xrefs

- `0x180037d7a`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180037e4d`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180037eb3`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180037f1f`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180037d67`: `PathCchRemoveBackslash`
- `0x180037f0c`: `CreateDirectory`
- `0x180037ea0`: `PathCchSkipRoot`
- `0x180037e3a`: `PathAllocCanonicalize`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall RecursiveCreateDirectory(const WCHAR *a1, __int64 a2)
{
  int v3; // ebx
  __int64 v4; // rdx
  PCWSTR v5; // rcx
  BOOL v6; // edi
  _QWORD *v7; // rcx
  signed int LastError; // eax
  DWORD FileAttributesW; // eax
  __int64 v11; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  PCWSTR ppszRootEnd; // [rsp+60h] [rbp+40h] BYREF
  PWSTR ppszPathOut; // [rsp+68h] [rbp+48h] BYREF

  ppszRootEnd = 0;
  ppszPathOut = 0;
  v3 = PathAllocCanonicalize(a1, 1u, &ppszPathOut);
  if ( v3 < 0 )
  {
    std::wstring::assign(a2, L"PathAllocCanonicalize");
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x62F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v3,
      savedregs);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_12;
    v11 = 54;
LABEL_42:
    WPP_SF_d(v7[2], v11, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids, (unsigned int)v3);
    goto LABEL_12;
  }
  v4 = -1;
  do
    ++v4;
  while ( ppszPathOut[v4] );
  v3 = PathCchRemoveBackslash(ppszPathOut, v4 + 1);
  if ( v3 < 0 )
  {
    std::wstring::_Assign<unsigned short>(a2, L"PathCchRemoveBackslash", 22);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x63B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v3,
      savedregs);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_12;
    v11 = 55;
    goto LABEL_42;
  }
  v3 = PathCchSkipRoot(ppszPathOut, &ppszRootEnd);
  if ( v3 >= 0 )
  {
    v5 = ppszRootEnd;
    v6 = *ppszRootEnd == 0;
    while ( 1 )
    {
      if ( v6 )
        goto LABEL_12;
      if ( *v5 )
      {
        if ( *v5 != 92 )
          goto LABEL_10;
        *v5 = 0;
      }
      else
      {
        v6 = 1;
      }
      if ( !CreateDirectoryW(ppszPathOut, 0) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 != -2147024713 && v3 != -2147024891 )
        {
          if ( v3 == -2147024893 )
          {
            v3 = -2147024713;
LABEL_39:
            std::wstring::assign(a2, L"CreateDirectory");
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x680,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
              (const char *)(unsigned int)v3,
              savedregs);
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              v11 = 57;
              goto LABEL_42;
            }
            goto LABEL_12;
          }
LABEL_23:
          if ( v3 < 0 )
            goto LABEL_39;
          goto LABEL_24;
        }
        FileAttributesW = GetFileAttributesW(ppszPathOut);
        if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
          goto LABEL_23;
        v3 = 0;
      }
LABEL_24:
      if ( !v6 )
        *ppszRootEnd = 92;
      v5 = ppszRootEnd;
LABEL_10:
      ppszRootEnd = ++v5;
    }
  }
  std::wstring::assign(a2, L"PathCchSkipRoot");
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x645,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
    (const char *)(unsigned int)v3,
    savedregs);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v11 = 56;
    goto LABEL_42;
  }
LABEL_12:
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180037cbc  mov     [rsp-28h+arg_0], rbx
0x180037cc1  push    rbp
0x180037cc2  push    rsi
0x180037cc3  push    rdi
0x180037cc4  push    r12
0x180037cc6  push    r14; int
0x180037cc8  mov     rbp, rsp
0x180037ccb  sub     rsp, 20h
0x180037ccf  xor     r14d, r14d
0x180037cd2  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x180037cd6  mov     rsi, rdx
0x180037cd9  mov     [rbp+ppszRootEnd], r14
0x180037cdd  mov     [rbp+ppszPathOut], r14
0x180037ce1  lea     edx, [r14+1]; dwFlags
0x180037ce5  call    cs:__imp_PathAllocCanonicalize
0x180037ceb  mov     ebx, eax
0x180037ced  test    eax, eax
0x180037cef  js      loc_180037E3A
0x180037cf5  mov     rcx, [rbp+ppszPathOut]; pszPath
0x180037cf9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180037cfd  inc     rdx
0x180037d00  cmp     [rcx+rdx*2], r14w
0x180037d05  jnz     short loc_180037CFD
0x180037d07  inc     rdx; cchPath
0x180037d0a  call    cs:__imp_PathCchRemoveBackslash
0x180037d10  mov     ebx, eax
0x180037d12  test    eax, eax
0x180037d14  js      short loc_180037D61
0x180037d16  mov     rcx, [rbp+ppszPathOut]; pszPath
0x180037d1a  lea     rdx, [rbp+ppszRootEnd]; ppszRootEnd
0x180037d1e  call    cs:__imp_PathCchSkipRoot
0x180037d24  mov     ebx, eax
0x180037d26  test    eax, eax
0x180037d28  js      loc_180037EA0
0x180037d2e  mov     rcx, [rbp+ppszRootEnd]
0x180037d32  mov     edi, r14d
0x180037d35  mov     r12d, 5Ch ; '\'
0x180037d3b  cmp     r14w, [rcx]
0x180037d3f  setz    dil
0x180037d43  test    edi, edi
0x180037d45  jnz     short loc_180037DA5
0x180037d47  cmp     r14w, [rcx]
0x180037d4b  jz      short loc_180037DC7
0x180037d4d  cmp     r12w, [rcx]
0x180037d51  jz      loc_180037E29
0x180037d57  add     rcx, 2
0x180037d5b  mov     [rbp+ppszRootEnd], rcx
0x180037d5f  jmp     short loc_180037D43
0x180037d61  mov     r8d, 16h
0x180037d67  lea     rdx, aPathcchremoveb; "PathCchRemoveBackslash"
0x180037d6e  mov     rcx, rsi
0x180037d71  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180037d76  mov     rcx, [rbp+28h]; this
0x180037d7a  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180037d81  mov     r9d, ebx; char *
0x180037d84  mov     edx, 63Bh; void *
0x180037d89  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180037d95  lea     rax, WPP_GLOBAL_Control
0x180037d9c  cmp     rcx, rax
0x180037d9f  jnz     loc_180037E8C
0x180037da5  mov     rcx, [rbp+ppszPathOut]; hMem
0x180037da9  test    rcx, rcx
0x180037dac  jz      short loc_180037DB4
0x180037dae  call    cs:__imp_LocalFree
0x180037db4  mov     eax, ebx
0x180037db6  mov     rbx, [rsp+20h+arg_0]
0x180037dbb  add     rsp, 20h
0x180037dbf  pop     r14
0x180037dc1  pop     r12
0x180037dc3  pop     rdi
0x180037dc4  pop     rsi
0x180037dc5  pop     rbp
0x180037dc6  retn
0x180037dc7  mov     edi, 1
0x180037dcc  mov     rcx, [rbp+ppszPathOut]; lpPathName
0x180037dd0  xor     edx, edx; lpSecurityAttributes
0x180037dd2  call    cs:__imp_CreateDirectoryW
0x180037dd8  test    eax, eax
0x180037dda  jnz     short loc_180037E14
0x180037ddc  call    cs:__imp_GetLastError
0x180037de2  mov     ebx, eax
0x180037de4  test    eax, eax
0x180037de6  jg      short loc_180037E2F
0x180037de8  cmp     ebx, 800700B7h
0x180037dee  jnz     loc_180037EEF
0x180037df4  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x180037df8  call    cs:__imp_GetFileAttributesW
0x180037dfe  cmp     eax, 0FFFFFFFFh
0x180037e01  jz      short loc_180037E07
0x180037e03  test    al, 10h
0x180037e05  jz      short loc_180037E0C
0x180037e07  mov     ebx, r14d
0x180037e0a  jmp     short loc_180037E14
0x180037e0c  test    ebx, ebx
0x180037e0e  js      loc_180037F0C
0x180037e14  test    edi, edi
0x180037e16  jnz     short loc_180037E20
0x180037e18  mov     rax, [rbp+ppszRootEnd]
0x180037e1c  mov     [rax], r12w
0x180037e20  mov     rcx, [rbp+ppszRootEnd]
0x180037e24  jmp     loc_180037D57
0x180037e29  mov     [rcx], r14w
0x180037e2d  jmp     short loc_180037DCC
0x180037e2f  movzx   ebx, ax
0x180037e32  or      ebx, 80070000h
0x180037e38  jmp     short loc_180037DE8
0x180037e3a  lea     rdx, aPathalloccanon; "PathAllocCanonicalize"
0x180037e41  mov     rcx, rsi
0x180037e44  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180037e49  mov     rcx, [rbp+28h]; this
0x180037e4d  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180037e54  mov     r9d, ebx; char *
0x180037e57  mov     edx, 62Fh; void *
0x180037e5c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037e61  mov     rcx, cs:WPP_GLOBAL_Control
0x180037e68  lea     rax, WPP_GLOBAL_Control
0x180037e6f  cmp     rcx, rax
0x180037e72  jz      loc_180037DA5
0x180037e78  test    byte ptr [rcx+1Ch], 80h
0x180037e7c  jz      loc_180037DA5
0x180037e82  mov     edx, 36h ; '6'
0x180037e87  jmp     loc_180037F59
0x180037e8c  test    byte ptr [rcx+1Ch], 80h
0x180037e90  jz      loc_180037DA5
0x180037e96  mov     edx, 37h ; '7'
0x180037e9b  jmp     loc_180037F59
0x180037ea0  lea     rdx, aPathcchskiproo; "PathCchSkipRoot"
0x180037ea7  mov     rcx, rsi
0x180037eaa  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180037eaf  mov     rcx, [rbp+28h]; this
0x180037eb3  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180037eba  mov     r9d, ebx; char *
0x180037ebd  mov     edx, 645h; void *
0x180037ec2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ece  lea     rax, WPP_GLOBAL_Control
0x180037ed5  cmp     rcx, rax
0x180037ed8  jz      loc_180037DA5
0x180037ede  test    byte ptr [rcx+1Ch], 80h
0x180037ee2  jz      loc_180037DA5
0x180037ee8  mov     edx, 38h ; '8'
0x180037eed  jmp     short loc_180037F59
0x180037eef  cmp     ebx, 80070005h
0x180037ef5  jz      loc_180037DF4
0x180037efb  cmp     ebx, 80070003h
0x180037f01  jnz     loc_180037E0C
0x180037f07  mov     ebx, 800700B7h
0x180037f0c  lea     rdx, aCreatedirector; "CreateDirectory"
0x180037f13  mov     rcx, rsi
0x180037f16  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180037f1b  mov     rcx, [rbp+28h]; this
0x180037f1f  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180037f26  mov     r9d, ebx; char *
0x180037f29  mov     edx, 680h; void *
0x180037f2e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037f33  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f3a  lea     rax, WPP_GLOBAL_Control
0x180037f41  cmp     rcx, rax
0x180037f44  jz      loc_180037DA5
0x180037f4a  test    byte ptr [rcx+1Ch], 80h
0x180037f4e  jz      loc_180037DA5
0x180037f54  mov     edx, 39h ; '9'
0x180037f59  mov     rcx, [rcx+10h]
0x180037f5d  lea     r8, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids
0x180037f64  mov     r9d, ebx
0x180037f67  call    WPP_SF_d
0x180037f6c  jmp     loc_180037DA5
```
