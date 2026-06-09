# VerifyFinalFilePath(void *,wchar_t const *)

- ea: `0x180049984`
- end: `0x180049cdf`
- name: `?VerifyFinalFilePath@@YAJPEAXPEB_W@Z`
- size: `859`
- prototype: `__int64 __fastcall(HANDLE hFile, PCNZWCH lpString1)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180048c80`
- `0x180049ce8`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000871c`
- `0x180008830`
- `0x180008938`
- `0x180009438`
- `0x18000dce4`
- `0x18000dd60`
- `0x1800110fc`
- `0x180049984`
- `0x18004bd90`
- `0x1800618d4`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180049b2b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180049ba1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180049b2b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180049ba1`

## string_xrefs

- `0x180049c18`: `Unexpected path detected! Input path: %ws ; Final resolved path: %ws`
- `0x180049ac2`: `Input path: %ws, is not under the secure SusBaseDirectory path for this system. Performing redirection checks.`

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
  unsigned int v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t v23[12]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String1; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v25; // [rsp+68h] [rbp-98h] BYREF
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
  wcscpy(v23, L"\\\\?\\");
  do
    ++v2;
  while ( lpString1[v2] );
  if ( v2 < 2 || (unsigned int)WUCompareStringCchI(lpString1, v23, 4u) == 2 && v2 - 4 < 2 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x678,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
             (const char *)0xA1,
             v21);
  SusBaseDirectoryW = GetSusBaseDirectoryW(&String1, v7, 0, v8);
  if ( SusBaseDirectoryW >= 0 )
  {
    *(_QWORD *)v22 = 0;
    v10 = SusStrCchLen(v23, 0x7FFFFFFFu, (unsigned __int64 *)v22) >= 0
       && WUCompareStringCchI(&String1, v23, v22[0]) == 2;
    p_String1 = &String1;
    if ( v10 )
      p_String1 = &v25;
    if ( (int)WUStringContainsI(lpString1, p_String1) >= 0 )
      return 0;
    WUTrace(0, 0, 32, 5);
    if ( ((unsigned int)WUCompareStringCchI(lpString1, v23, 4u) != 2 || !iswalpha(lpString1[4]) || lpString1[5] != 58)
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
        if ( iswalpha(*lpString1) && lpString1[1] == 58 && (unsigned int)WUCompareStringCchI(v16, v23, 4u) == 2 )
        {
          v20 = v16 + 4;
          v15 -= 4;
        }
        if ( (unsigned int)WUCompareStringCchI(v20, lpString1, v15) == 2 )
        {
          v17 = 0;
          goto LABEL_41;
        }
        WUTrace(0, 0, 32, 3);
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x6C1,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
                      (const char *)0xA1,
                      0);
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
        0);
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
0x180049984  mov     [rsp-8+arg_10], rbx
0x180049989  push    rbp
0x18004998a  push    rsi
0x18004998b  push    rdi
0x18004998c  push    r12
0x18004998e  push    r13
0x180049990  push    r14
0x180049992  push    r15
0x180049994  lea     rbp, [rsp-180h]
0x18004999c  sub     rsp, 280h
0x1800499a3  mov     rax, cs:__security_cookie
0x1800499aa  xor     rax, rsp
0x1800499ad  mov     [rbp+1B0h+var_40], rax
0x1800499b4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800499b8  mov     rdi, rdx
0x1800499bb  mov     r15, rcx
0x1800499be  cmp     rcx, rbx
0x1800499c1  jnz     short loc_1800499CD
0x1800499c3  mov     edx, 66Ah
0x1800499c8  jmp     loc_180049C98
0x1800499cd  xor     r13d, r13d
0x1800499d0  test    rdi, rdi
0x1800499d3  jz      loc_180049C93
0x1800499d9  cmp     [rdx], r13w
0x1800499dd  jz      loc_180049C93
0x1800499e3  movsd   xmm0, qword ptr cs:asc_18007E738; "\\\\?\\"
0x1800499eb  mov     r12d, r13d
0x1800499ee  movzx   eax, word ptr cs:asc_18007E738+8; ""
0x1800499f5  movsd   qword ptr [rsp+2B0h+var_268], xmm0
0x1800499fb  mov     [rsp+2B0h+var_260], ax
0x180049a00  inc     rbx
0x180049a03  cmp     [rdx+rbx*2], r13w
0x180049a08  jnz     short loc_180049A00
0x180049a0a  mov     esi, 2
0x180049a0f  cmp     rbx, rsi
0x180049a12  jb      loc_180049C73
0x180049a18  lea     r14d, [rsi+2]
0x180049a1c  mov     rcx, rdi; lpString1
0x180049a1f  mov     r8d, r14d; unsigned int
0x180049a22  lea     rdx, [rsp+2B0h+var_268]; wchar_t *
0x180049a27  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x180049a2c  cmp     eax, esi
0x180049a2e  jnz     short loc_180049A3D
0x180049a30  lea     rax, [rbx-4]
0x180049a34  cmp     rax, rsi
0x180049a37  jb      loc_180049C73
0x180049a3d  xor     r8d, r8d; wchar_t *
0x180049a40  lea     rcx, [rsp+2B0h+String1]; wchar_t *
0x180049a45  call    ?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z; GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)
0x180049a4a  mov     ebx, eax
0x180049a4c  test    eax, eax
0x180049a4e  jns     short loc_180049A5A
0x180049a50  mov     edx, 682h
0x180049a55  jmp     loc_180049C9D
0x180049a5a  lea     r8, [rsp+2B0h+var_270]; unsigned __int64 *
0x180049a5f  mov     qword ptr [rsp+2B0h+var_270], r13
0x180049a64  mov     edx, 7FFFFFFFh; unsigned __int64
0x180049a69  lea     rcx, [rsp+2B0h+var_268]; wchar_t *
0x180049a6e  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180049a73  test    eax, eax
0x180049a75  jns     short loc_180049A7C
0x180049a77  mov     ecx, r13d
0x180049a7a  jmp     short loc_180049A98
0x180049a7c  mov     r8d, [rsp+2B0h+var_270]; unsigned int
0x180049a81  lea     rdx, [rsp+2B0h+var_268]; wchar_t *
0x180049a86  lea     rcx, [rsp+2B0h+String1]; lpString1
0x180049a8b  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x180049a90  cmp     eax, esi
0x180049a92  mov     ecx, r13d
0x180049a95  setz    cl
0x180049a98  test    ecx, ecx
0x180049a9a  lea     rax, [rsp+2B0h+var_248]
0x180049a9f  lea     rdx, [rsp+2B0h+String1]
0x180049aa4  mov     rcx, rdi; lpString1
0x180049aa7  cmovnz  rdx, rax; wchar_t *
0x180049aab  call    ?WUStringContainsI@@YAHPEB_W0@Z; WUStringContainsI(wchar_t const *,wchar_t const *)
0x180049ab0  test    eax, eax
0x180049ab2  js      short loc_180049ABB
0x180049ab4  xor     eax, eax
0x180049ab6  jmp     loc_180049CB5
0x180049abb  xor     edx, edx
0x180049abd  mov     [rsp+2B0h+var_280], rdi
0x180049ac2  lea     rax, aInputPathWsIsN; "Input path: %ws, is not under the secur"...
0x180049ac9  xor     ecx, ecx
0x180049acb  mov     [rsp+2B0h+var_288], rax
0x180049ad0  mov     qword ptr [rsp+2B0h+var_290], r13; int
0x180049ad5  lea     r9d, [rdx+5]
0x180049ad9  lea     r8d, [rdx+20h]
0x180049add  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180049ae2  mov     r8d, r14d; unsigned int
0x180049ae5  lea     rdx, [rsp+2B0h+var_268]; wchar_t *
0x180049aea  mov     rcx, rdi; lpString1
0x180049aed  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x180049af2  cmp     eax, esi
0x180049af4  jnz     short loc_180049B0A
0x180049af6  movzx   ecx, word ptr [rdi+8]; C
0x180049afa  call    iswalpha
0x180049aff  test    eax, eax
0x180049b01  jz      short loc_180049B0A
0x180049b03  cmp     word ptr [rdi+0Ah], 3Ah ; ':'
0x180049b08  jz      short loc_180049B20
0x180049b0a  movzx   ecx, word ptr [rdi]; C
0x180049b0d  call    iswalpha
0x180049b12  test    eax, eax
0x180049b14  jz      short loc_180049B1D
0x180049b16  cmp     word ptr [rdi+2], 3Ah ; ':'
0x180049b1b  jz      short loc_180049B20
0x180049b1d  mov     r12d, r14d
0x180049b20  mov     r9d, r12d; dwFlags
0x180049b23  xor     r8d, r8d; cchFilePath
0x180049b26  xor     edx, edx; lpszFilePath
0x180049b28  mov     rcx, r15; hFile
0x180049b2b  call    cs:__imp_GetFinalPathNameByHandleW
0x180049b31  mov     r14d, eax
0x180049b34  test    eax, eax
0x180049b36  jnz     short loc_180049B55
0x180049b38  mov     rcx, [rbp+1B8h]; this
0x180049b3f  lea     r8, aCW1SSrcClientL_29; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180049b46  mov     edx, 6A7h; void *
0x180049b4b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180049b50  jmp     loc_180049CB5
0x180049b55  mov     rcx, r14; unsigned __int64
0x180049b58  mov     rdx, rsi; unsigned __int64
0x180049b5b  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180049b60  mov     rbx, rax
0x180049b63  neg     rax
0x180049b66  sbb     esi, esi
0x180049b68  not     esi
0x180049b6a  and     esi, 8007000Eh
0x180049b70  test    rbx, rbx
0x180049b73  jnz     short loc_180049B95
0x180049b75  mov     rcx, [rbp+1B8h]; this
0x180049b7c  lea     r8, aCW1SSrcClientL_29; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180049b83  mov     r9d, esi; char *
0x180049b86  mov     edx, 6ABh; void *
0x180049b8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049b90  jmp     loc_180049C5D
0x180049b95  mov     r9d, r12d; dwFlags
0x180049b98  mov     r8d, r14d; cchFilePath
0x180049b9b  mov     rdx, rbx; lpszFilePath
0x180049b9e  mov     rcx, r15; hFile
0x180049ba1  call    cs:__imp_GetFinalPathNameByHandleW
0x180049ba7  test    eax, eax
0x180049ba9  jnz     short loc_180049BC8
0x180049bab  mov     rcx, [rbp+1B8h]; this
0x180049bb2  lea     r8, aCW1SSrcClientL_29; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180049bb9  mov     edx, 6ACh; void *
0x180049bbe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180049bc3  jmp     loc_180049C5B
0x180049bc8  movzx   ecx, word ptr [rdi]; C
0x180049bcb  mov     rsi, rbx
0x180049bce  call    iswalpha
0x180049bd3  test    eax, eax
0x180049bd5  jz      short loc_180049BFE
0x180049bd7  cmp     word ptr [rdi+2], 3Ah ; ':'
0x180049bdc  jnz     short loc_180049BFE
0x180049bde  mov     r8d, 4; unsigned int
0x180049be4  lea     rdx, [rsp+2B0h+var_268]; wchar_t *
0x180049be9  mov     rcx, rbx; lpString1
0x180049bec  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x180049bf1  cmp     eax, 2
0x180049bf4  jnz     short loc_180049BFE
0x180049bf6  lea     rsi, [rbx+8]
0x180049bfa  add     r14d, 0FFFFFFFCh
0x180049bfe  mov     r8d, r14d; unsigned int
0x180049c01  mov     rdx, rdi; wchar_t *
0x180049c04  mov     rcx, rsi; lpString1
0x180049c07  call    ?WUCompareStringCchI@@YAHPEB_W0I@Z; WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)
0x180049c0c  cmp     eax, 2
0x180049c0f  jz      short loc_180049C64
0x180049c11  xor     edx, edx
0x180049c13  mov     [rsp+2B0h+var_278], rsi
0x180049c18  lea     rax, aUnexpectedPath; "Unexpected path detected! Input path: %"...
0x180049c1f  mov     [rsp+2B0h+var_280], rdi
0x180049c24  mov     [rsp+2B0h+var_288], rax
0x180049c29  xor     ecx, ecx
0x180049c2b  mov     qword ptr [rsp+2B0h+var_290], r13; unsigned int
0x180049c30  lea     r9d, [rdx+3]
0x180049c34  lea     r8d, [rdx+20h]
0x180049c38  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180049c3d  mov     rcx, [rbp+1B8h]; this
0x180049c44  lea     r8, aCW1SSrcClientL_29; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180049c4b  mov     r9d, 0A1h; char *
0x180049c51  mov     edx, 6C1h; void *
0x180049c56  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180049c5b  mov     esi, eax
0x180049c5d  test    rbx, rbx
0x180049c60  jz      short loc_180049C6F
0x180049c62  jmp     short loc_180049C67
0x180049c64  mov     esi, r13d
0x180049c67  mov     rcx, rbx; lpMem
0x180049c6a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180049c6f  mov     eax, esi
0x180049c71  jmp     short loc_180049CB5
0x180049c73  mov     rcx, [rbp+1B8h]; this
0x180049c7a  lea     r8, aCW1SSrcClientL_29; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180049c81  mov     r9d, 0A1h; char *
0x180049c87  mov     edx, 678h; void *
0x180049c8c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180049c91  jmp     short loc_180049CB5
0x180049c93  mov     edx, 66Bh; void *
0x180049c98  mov     ebx, 80070057h
0x180049c9d  mov     rcx, [rbp+1B8h]; this
0x180049ca4  lea     r8, aCW1SSrcClientL_29; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180049cab  mov     r9d, ebx; char *
0x180049cae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049cb3  mov     eax, ebx
0x180049cb5  mov     rcx, [rbp+1B0h+var_40]
0x180049cbc  xor     rcx, rsp; StackCookie
0x180049cbf  call    __security_check_cookie
0x180049cc4  mov     rbx, [rsp+2B0h+arg_10]
0x180049ccc  add     rsp, 280h
0x180049cd3  pop     r15
0x180049cd5  pop     r14
0x180049cd7  pop     r13
0x180049cd9  pop     r12
0x180049cdb  pop     rdi
0x180049cdc  pop     rsi
0x180049cdd  pop     rbp
0x180049cde  retn
```
