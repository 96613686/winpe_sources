# VerifyFinalFilePath(void *,wchar_t const *)

- ea: `0x14000f5ac`
- end: `0x14000f907`
- name: `?VerifyFinalFilePath@@YAJPEAXPEB_W@Z`
- size: `859`
- prototype: `int __fastcall(HANDLE hFile, PCNZWCH lpString1)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14000e788`
- `0x14000f910`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x14000ce30`
- `0x14000ce9c`
- `0x14000e194`
- `0x14000e4d0`
- `0x14000f5ac`
- `0x140011290`
- `0x1400113a4`
- `0x1400114ac`
- `0x1400154b4`
- `0x140045a74`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000f753`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000f7c9`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000f753`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000f7c9`

## string_xrefs

- `0x14000f6ea`: `Input path: %ws, is not under the secure SusBaseDirectory path for this system. Performing redirection checks.`
- `0x14000f840`: `Unexpected path detected! Input path: %ws ; Final resolved path: %ws`

## pseudocode

```c
int __fastcall VerifyFinalFilePath(HANDLE hFile, PCNZWCH lpString1)
{
  unsigned __int64 v2; // rbx
  __int64 v5; // rdx
  DWORD v6; // r12d
  __int64 v7; // rdx
  unsigned int *v8; // r9
  int SusBaseDirectoryW; // ebx
  BOOL v10; // ecx
  WCHAR *p_String1; // rdx
  DWORD FinalPathNameByHandleW; // eax
  const char *v14; // r9
  unsigned int v15; // r14d
  WCHAR *v16; // rbx
  unsigned int v17; // esi
  const char *v18; // r9
  int LastError; // eax
  const WCHAR *v20; // rsi
  unsigned int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  unsigned int v23; // [rsp+20h] [rbp-E0h]
  unsigned int v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t v25[12]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String1; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v27; // [rsp+68h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v2 = -1;
  if ( hFile == (HANDLE)-1LL )
  {
    v5 = 1642;
LABEL_45:
    SusBaseDirectoryW = -2147024809;
    goto LABEL_46;
  }
  if ( !lpString1 || !*lpString1 )
  {
    v5 = 1643;
    goto LABEL_45;
  }
  v6 = 0;
  wcscpy(v25, L"\\\\?\\");
  do
    ++v2;
  while ( lpString1[v2] );
  if ( v2 < 2 || (unsigned int)WUCompareStringCchI(lpString1, v25, 4u) == 2 && v2 - 4 < 2 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x678,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
             (const char *)0xA1,
             v21);
  SusBaseDirectoryW = GetSusBaseDirectoryW(&String1, v7, 0, v8);
  if ( SusBaseDirectoryW >= 0 )
  {
    *(_QWORD *)v24 = 0;
    v10 = SusStrCchLen(v25, 0x7FFFFFFFu, (unsigned __int64 *)v24) >= 0
       && WUCompareStringCchI(&String1, v25, v24[0]) == 2;
    p_String1 = &String1;
    if ( v10 )
      p_String1 = &v27;
    if ( (int)WUStringContainsI(lpString1, p_String1) >= 0 )
      return 0;
    WUTrace(
      0,
      0,
      32,
      5,
      0,
      L"Input path: %ws, is not under the secure SusBaseDirectory path for this system. Performing redirection checks.");
    if ( ((unsigned int)WUCompareStringCchI(lpString1, v25, 4u) != 2 || !iswalpha(lpString1[4]) || lpString1[5] != 58)
      && (!iswalpha(*lpString1) || lpString1[1] != 58) )
    {
      v6 = 4;
    }
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, v6);
    v15 = FinalPathNameByHandleW;
    if ( !FinalPathNameByHandleW )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x6A7,
               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
               v14);
    v16 = (WCHAR *)SafeSusAllocArray(FinalPathNameByHandleW, 2u);
    v17 = v16 == 0 ? 0x8007000E : 0;
    if ( v16 )
    {
      if ( GetFinalPathNameByHandleW(hFile, v16, v15, v6) )
      {
        v20 = v16;
        if ( iswalpha(*lpString1) && lpString1[1] == 58 && (unsigned int)WUCompareStringCchI(v16, v25, 4u) == 2 )
        {
          v20 = v16 + 4;
          v15 -= 4;
        }
        if ( (unsigned int)WUCompareStringCchI(v20, lpString1, v15) == 2 )
        {
          v17 = 0;
          goto LABEL_41;
        }
        WUTrace(0, 0, 32, 3, 0, L"Unexpected path detected! Input path: %ws ; Final resolved path: %ws");
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x6C1,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
                      (const char *)0xA1,
                      v23);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x6AC,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
                      v18);
      }
      v17 = LastError;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6AB,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
        (const char *)v17,
        v22);
    }
    if ( !v16 )
      return v17;
LABEL_41:
    SusFree(v16);
    return v17;
  }
  v5 = 1666;
LABEL_46:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
    (const char *)(unsigned int)SusBaseDirectoryW,
    v21);
  return SusBaseDirectoryW;
}

```

## disassembly

```asm
0x14000f5ac  mov     [rsp-8+arg_10], rbx
0x14000f5b1  push    rbp
0x14000f5b2  push    rsi
0x14000f5b3  push    rdi
0x14000f5b4  push    r12
0x14000f5b6  push    r13
0x14000f5b8  push    r14
0x14000f5ba  push    r15
0x14000f5bc  lea     rbp, [rsp-180h]
0x14000f5c4  sub     rsp, 280h
0x14000f5cb  mov     rax, cs:__security_cookie
0x14000f5d2  xor     rax, rsp
0x14000f5d5  mov     [rbp+1B0h+var_40], rax
0x14000f5dc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000f5e0  mov     rdi, rdx
0x14000f5e3  mov     r15, rcx
0x14000f5e6  cmp     rcx, rbx
0x14000f5e9  jnz     short loc_14000F5F5
0x14000f5eb  mov     edx, 66Ah
0x14000f5f0  jmp     loc_14000F8C0
0x14000f5f5  xor     r13d, r13d
0x14000f5f8  test    rdi, rdi
0x14000f5fb  jz      loc_14000F8BB
0x14000f601  cmp     [rdx], r13w
0x14000f605  jz      loc_14000F8BB
0x14000f60b  movsd   xmm0, qword ptr cs:asc_140054580; "\\\\?\\"
0x14000f613  mov     r12d, r13d
0x14000f616  movzx   eax, word ptr cs:asc_140054580+8; ""
0x14000f61d  movsd   qword ptr [rsp+2B0h+var_268], xmm0
0x14000f623  mov     [rsp+2B0h+var_260], ax
0x14000f628  inc     rbx
0x14000f62b  cmp     [rdx+rbx*2], r13w
0x14000f630  jnz     short loc_14000F628
0x14000f632  mov     esi, 2
0x14000f637  cmp     rbx, rsi
0x14000f63a  jb      loc_14000F89B
0x14000f640  lea     r14d, [rsi+2]
0x14000f644  mov     rcx, rdi; lpString1
0x14000f647  mov     r8d, r14d; unsigned int
0x14000f64a  lea     rdx, [rsp+2B0h+var_268]; wchar_t *
0x14000f64f  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x14000f654  cmp     eax, esi
0x14000f656  jnz     short loc_14000F665
0x14000f658  lea     rax, [rbx-4]
0x14000f65c  cmp     rax, rsi
0x14000f65f  jb      loc_14000F89B
0x14000f665  xor     r8d, r8d; wchar_t *
0x14000f668  lea     rcx, [rsp+2B0h+String1]; pszDest
0x14000f66d  call    ?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z; GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)
0x14000f672  mov     ebx, eax
0x14000f674  test    eax, eax
0x14000f676  jns     short loc_14000F682
0x14000f678  mov     edx, 682h
0x14000f67d  jmp     loc_14000F8C5
0x14000f682  lea     r8, [rsp+2B0h+var_270]; unsigned __int64 *
0x14000f687  mov     qword ptr [rsp+2B0h+var_270], r13
0x14000f68c  mov     edx, 7FFFFFFFh; unsigned __int64
0x14000f691  lea     rcx, [rsp+2B0h+var_268]; wchar_t *
0x14000f696  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x14000f69b  test    eax, eax
0x14000f69d  jns     short loc_14000F6A4
0x14000f69f  mov     ecx, r13d
0x14000f6a2  jmp     short loc_14000F6C0
0x14000f6a4  mov     r8d, [rsp+2B0h+var_270]; unsigned int
0x14000f6a9  lea     rdx, [rsp+2B0h+var_268]; wchar_t *
0x14000f6ae  lea     rcx, [rsp+2B0h+String1]; lpString1
0x14000f6b3  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x14000f6b8  cmp     eax, esi
0x14000f6ba  mov     ecx, r13d
0x14000f6bd  setz    cl
0x14000f6c0  test    ecx, ecx
0x14000f6c2  lea     rax, [rsp+2B0h+var_248]
0x14000f6c7  lea     rdx, [rsp+2B0h+String1]
0x14000f6cc  mov     rcx, rdi; lpString1
0x14000f6cf  cmovnz  rdx, rax; wchar_t *
0x14000f6d3  call    ?WUStringContainsI@@YAHPEB_W0@Z; WUStringContainsI(wchar_t const *,wchar_t const *)
0x14000f6d8  test    eax, eax
0x14000f6da  js      short loc_14000F6E3
0x14000f6dc  xor     eax, eax
0x14000f6de  jmp     loc_14000F8DD
0x14000f6e3  xor     edx, edx
0x14000f6e5  mov     [rsp+2B0h+var_280], rdi
0x14000f6ea  lea     rax, aInputPathWsIsN; "Input path: %ws, is not under the secur"...
0x14000f6f1  xor     ecx, ecx
0x14000f6f3  mov     [rsp+2B0h+var_288], rax
0x14000f6f8  mov     qword ptr [rsp+2B0h+var_290], r13; int
0x14000f6fd  lea     r9d, [rdx+5]
0x14000f701  lea     r8d, [rdx+20h]
0x14000f705  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14000f70a  mov     r8d, r14d; unsigned int
0x14000f70d  lea     rdx, [rsp+2B0h+var_268]; wchar_t *
0x14000f712  mov     rcx, rdi; lpString1
0x14000f715  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x14000f71a  cmp     eax, esi
0x14000f71c  jnz     short loc_14000F732
0x14000f71e  movzx   ecx, word ptr [rdi+8]; C
0x14000f722  call    iswalpha
0x14000f727  test    eax, eax
0x14000f729  jz      short loc_14000F732
0x14000f72b  cmp     word ptr [rdi+0Ah], 3Ah ; ':'
0x14000f730  jz      short loc_14000F748
0x14000f732  movzx   ecx, word ptr [rdi]; C
0x14000f735  call    iswalpha
0x14000f73a  test    eax, eax
0x14000f73c  jz      short loc_14000F745
0x14000f73e  cmp     word ptr [rdi+2], 3Ah ; ':'
0x14000f743  jz      short loc_14000F748
0x14000f745  mov     r12d, r14d
0x14000f748  mov     r9d, r12d; dwFlags
0x14000f74b  xor     r8d, r8d; cchFilePath
0x14000f74e  xor     edx, edx; lpszFilePath
0x14000f750  mov     rcx, r15; hFile
0x14000f753  call    cs:__imp_GetFinalPathNameByHandleW
0x14000f759  mov     r14d, eax
0x14000f75c  test    eax, eax
0x14000f75e  jnz     short loc_14000F77D
0x14000f760  mov     rcx, [rbp+1B8h]; this
0x14000f767  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000f76e  mov     edx, 6A7h; void *
0x14000f773  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000f778  jmp     loc_14000F8DD
0x14000f77d  mov     rcx, r14; unsigned __int64
0x14000f780  mov     rdx, rsi; unsigned __int64
0x14000f783  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x14000f788  mov     rbx, rax
0x14000f78b  neg     rax
0x14000f78e  sbb     esi, esi
0x14000f790  not     esi
0x14000f792  and     esi, 8007000Eh
0x14000f798  test    rbx, rbx
0x14000f79b  jnz     short loc_14000F7BD
0x14000f79d  mov     rcx, [rbp+1B8h]; this
0x14000f7a4  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000f7ab  mov     r9d, esi; char *
0x14000f7ae  mov     edx, 6ABh; void *
0x14000f7b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f7b8  jmp     loc_14000F885
0x14000f7bd  mov     r9d, r12d; dwFlags
0x14000f7c0  mov     r8d, r14d; cchFilePath
0x14000f7c3  mov     rdx, rbx; lpszFilePath
0x14000f7c6  mov     rcx, r15; hFile
0x14000f7c9  call    cs:__imp_GetFinalPathNameByHandleW
0x14000f7cf  test    eax, eax
0x14000f7d1  jnz     short loc_14000F7F0
0x14000f7d3  mov     rcx, [rbp+1B8h]; this
0x14000f7da  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000f7e1  mov     edx, 6ACh; void *
0x14000f7e6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000f7eb  jmp     loc_14000F883
0x14000f7f0  movzx   ecx, word ptr [rdi]; C
0x14000f7f3  mov     rsi, rbx
0x14000f7f6  call    iswalpha
0x14000f7fb  test    eax, eax
0x14000f7fd  jz      short loc_14000F826
0x14000f7ff  cmp     word ptr [rdi+2], 3Ah ; ':'
0x14000f804  jnz     short loc_14000F826
0x14000f806  mov     r8d, 4; unsigned int
0x14000f80c  lea     rdx, [rsp+2B0h+var_268]; wchar_t *
0x14000f811  mov     rcx, rbx; lpString1
0x14000f814  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x14000f819  cmp     eax, 2
0x14000f81c  jnz     short loc_14000F826
0x14000f81e  lea     rsi, [rbx+8]
0x14000f822  add     r14d, 0FFFFFFFCh
0x14000f826  mov     r8d, r14d; unsigned int
0x14000f829  mov     rdx, rdi; wchar_t *
0x14000f82c  mov     rcx, rsi; lpString1
0x14000f82f  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x14000f834  cmp     eax, 2
0x14000f837  jz      short loc_14000F88C
0x14000f839  xor     edx, edx
0x14000f83b  mov     [rsp+2B0h+var_278], rsi
0x14000f840  lea     rax, aUnexpectedPath; "Unexpected path detected! Input path: %"...
0x14000f847  mov     [rsp+2B0h+var_280], rdi
0x14000f84c  mov     [rsp+2B0h+var_288], rax
0x14000f851  xor     ecx, ecx
0x14000f853  mov     qword ptr [rsp+2B0h+var_290], r13; unsigned int
0x14000f858  lea     r9d, [rdx+3]
0x14000f85c  lea     r8d, [rdx+20h]
0x14000f860  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14000f865  mov     rcx, [rbp+1B8h]; this
0x14000f86c  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000f873  mov     r9d, 0A1h; char *
0x14000f879  mov     edx, 6C1h; void *
0x14000f87e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000f883  mov     esi, eax
0x14000f885  test    rbx, rbx
0x14000f888  jz      short loc_14000F897
0x14000f88a  jmp     short loc_14000F88F
0x14000f88c  mov     esi, r13d
0x14000f88f  mov     rcx, rbx; lpMem
0x14000f892  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14000f897  mov     eax, esi
0x14000f899  jmp     short loc_14000F8DD
0x14000f89b  mov     rcx, [rbp+1B8h]; this
0x14000f8a2  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000f8a9  mov     r9d, 0A1h; char *
0x14000f8af  mov     edx, 678h; void *
0x14000f8b4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000f8b9  jmp     short loc_14000F8DD
0x14000f8bb  mov     edx, 66Bh; void *
0x14000f8c0  mov     ebx, 80070057h
0x14000f8c5  mov     rcx, [rbp+1B8h]; this
0x14000f8cc  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000f8d3  mov     r9d, ebx; char *
0x14000f8d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f8db  mov     eax, ebx
0x14000f8dd  mov     rcx, [rbp+1B0h+var_40]
0x14000f8e4  xor     rcx, rsp; StackCookie
0x14000f8e7  call    __security_check_cookie
0x14000f8ec  mov     rbx, [rsp+2B0h+arg_10]
0x14000f8f4  add     rsp, 280h
0x14000f8fb  pop     r15
0x14000f8fd  pop     r14
0x14000f8ff  pop     r13
0x14000f901  pop     r12
0x14000f903  pop     rdi
0x14000f904  pop     rsi
0x14000f905  pop     rbp
0x14000f906  retn
```
