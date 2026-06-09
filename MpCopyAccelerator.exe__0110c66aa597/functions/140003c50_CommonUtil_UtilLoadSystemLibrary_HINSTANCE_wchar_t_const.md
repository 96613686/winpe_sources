# CommonUtil::UtilLoadSystemLibrary(HINSTANCE__ * *,wchar_t const *)

- ea: `0x140003c50`
- end: `0x140003de3`
- name: `?UtilLoadSystemLibrary@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEB_W@Z`
- size: `403`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, HINSTANCE *, const wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140002cd0`
- `0x14000530c`

## callees

- `0x140003254`
- `0x140003bc0`
- `0x140003c50`
- `0x1400044d0`
- `0x140004540`
- `0x140005c20`
- `0x140005c40`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x140003c84`
- `KERNEL32!GetSystemDirectoryW` at `0x140003d2d`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilLoadSystemLibrary(CommonUtil *this, HINSTANCE *a2, const wchar_t *a3)
{
  const wchar_t *v5; // rdx
  int WindowsPath; // ebx
  HINSTANCE *v8; // rbx
  unsigned int v9; // r9d
  unsigned __int64 v10; // rdx
  int Library; // edi
  void *v12; // rdi
  unsigned __int64 v13; // rdx
  int IsFileExists; // esi
  HINSTANCE *v15; // [rsp+20h] [rbp-20h] BYREF
  void *v16; // [rsp+28h] [rbp-18h] BYREF

  v15 = 0;
  WindowsPath = CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v15, a2, 1);
  if ( WindowsPath < 0 )
  {
LABEL_2:
    if ( v15 )
      operator delete(v15, (unsigned __int64)v5);
    return (unsigned int)WindowsPath;
  }
  v8 = v15;
  if ( (int)CommonUtil::UtilIsFileExists((CommonUtil *)v15, v5) >= 0 )
    goto LABEL_22;
  v16 = 0;
  Library = CommonUtil::NewSprintfW((CommonUtil *)&v16, (wchar_t **)L"forwarders\\%ls", (const wchar_t *)a2);
  if ( Library < 0 )
  {
    if ( v16 )
      operator delete(v16, v10);
    goto LABEL_23;
  }
  if ( v8 )
  {
    operator delete(v8, v10);
    v15 = 0;
  }
  v12 = v16;
  WindowsPath = CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v15, v16, 1);
  if ( WindowsPath < 0 )
  {
    if ( v12 )
      operator delete(v12, (unsigned __int64)v5);
    goto LABEL_2;
  }
  v8 = v15;
  IsFileExists = CommonUtil::UtilIsFileExists((CommonUtil *)v15, v5);
  if ( IsFileExists >= 0 )
  {
    if ( v12 )
      operator delete(v12, v13);
LABEL_22:
    Library = CommonUtil::UtilLoadLibraryEx(this, v8, (const wchar_t *)8, v9);
LABEL_23:
    if ( v8 )
      operator delete(v8, v10);
    return (unsigned int)Library;
  }
  if ( v12 )
    operator delete(v12, v13);
  if ( v8 )
    operator delete(v8, v13);
  return (unsigned int)IsFileExists;
}

```

## disassembly

```asm
0x140003c50  mov     [rsp-18h+arg_10], rbx
0x140003c55  mov     [rsp-18h+arg_18], rsi
0x140003c5a  push    rbp
0x140003c5b  push    rdi
0x140003c5c  push    r14
0x140003c5e  mov     rbp, rsp
0x140003c61  sub     rsp, 40h
0x140003c65  mov     rax, cs:__security_cookie
0x140003c6c  xor     rax, rsp
0x140003c6f  mov     [rbp+var_10], rax
0x140003c73  mov     rdi, rdx
0x140003c76  mov     [rbp+var_20], 0
0x140003c7e  mov     r14, rcx
0x140003c81  mov     r8, rdx
0x140003c84  mov     rcx, cs:__imp_GetSystemDirectoryW
0x140003c8b  lea     rdx, [rbp+var_20]
0x140003c8f  mov     esi, 1
0x140003c94  mov     r9d, esi
0x140003c97  call    CommonUtil__UtilGetWindowsPath
0x140003c9c  mov     ecx, eax
0x140003c9e  mov     ebx, eax
0x140003ca0  shr     ecx, 1Fh
0x140003ca3  test    cl, cl
0x140003ca5  jz      short loc_140003CBC
0x140003ca7  mov     rcx, [rbp+var_20]; void *
0x140003cab  test    rcx, rcx
0x140003cae  jz      short loc_140003CB5
0x140003cb0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003cb5  mov     eax, ebx
0x140003cb7  jmp     loc_140003DC4
0x140003cbc  mov     rbx, [rbp+var_20]
0x140003cc0  mov     rcx, rbx; this
0x140003cc3  call    ?UtilIsFileExists@CommonUtil@@YAJPEB_W@Z; CommonUtil::UtilIsFileExists(wchar_t const *)
0x140003cc8  shr     eax, 1Fh
0x140003ccb  test    al, al
0x140003ccd  jz      loc_140003DA2
0x140003cd3  mov     r8, rdi; wchar_t *
0x140003cd6  mov     [rbp+var_18], 0
0x140003cde  lea     rdx, aForwardersLs; "forwarders\\%ls"
0x140003ce5  lea     rcx, [rbp+var_18]; this
0x140003ce9  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x140003cee  mov     ecx, eax
0x140003cf0  mov     edi, eax
0x140003cf2  shr     ecx, 1Fh
0x140003cf5  test    cl, cl
0x140003cf7  jz      short loc_140003D10
0x140003cf9  mov     rcx, [rbp+var_18]; void *
0x140003cfd  test    rcx, rcx
0x140003d00  jz      loc_140003DB5
0x140003d06  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003d0b  jmp     loc_140003DB5
0x140003d10  test    rbx, rbx
0x140003d13  jz      short loc_140003D25
0x140003d15  mov     rcx, rbx; void *
0x140003d18  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003d1d  mov     [rbp+var_20], 0
0x140003d25  mov     rdi, [rbp+var_18]
0x140003d29  lea     rdx, [rbp+var_20]
0x140003d2d  mov     rcx, cs:__imp_GetSystemDirectoryW
0x140003d34  mov     r8, rdi
0x140003d37  mov     r9d, esi
0x140003d3a  call    CommonUtil__UtilGetWindowsPath
0x140003d3f  mov     ecx, eax
0x140003d41  mov     ebx, eax
0x140003d43  shr     ecx, 1Fh
0x140003d46  test    cl, cl
0x140003d48  jz      short loc_140003D60
0x140003d4a  test    rdi, rdi
0x140003d4d  jz      loc_140003CA7
0x140003d53  mov     rcx, rdi; void *
0x140003d56  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003d5b  jmp     loc_140003CA7
0x140003d60  mov     rbx, [rbp+var_20]
0x140003d64  mov     rcx, rbx; this
0x140003d67  call    ?UtilIsFileExists@CommonUtil@@YAJPEB_W@Z; CommonUtil::UtilIsFileExists(wchar_t const *)
0x140003d6c  mov     ecx, eax
0x140003d6e  mov     esi, eax
0x140003d70  shr     ecx, 1Fh
0x140003d73  test    cl, cl
0x140003d75  jz      short loc_140003D95
0x140003d77  test    rdi, rdi
0x140003d7a  jz      short loc_140003D84
0x140003d7c  mov     rcx, rdi; void *
0x140003d7f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003d84  test    rbx, rbx
0x140003d87  jz      short loc_140003D91
0x140003d89  mov     rcx, rbx; void *
0x140003d8c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003d91  mov     eax, esi
0x140003d93  jmp     short loc_140003DC4
0x140003d95  test    rdi, rdi
0x140003d98  jz      short loc_140003DA2
0x140003d9a  mov     rcx, rdi; void *
0x140003d9d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003da2  mov     r8d, 8; wchar_t *
0x140003da8  mov     rdx, rbx; HINSTANCE *
0x140003dab  mov     rcx, r14; this
0x140003dae  call    ?UtilLoadLibraryEx@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEB_WK@Z; CommonUtil::UtilLoadLibraryEx(HINSTANCE__ * *,wchar_t const *,ulong)
0x140003db3  mov     edi, eax
0x140003db5  test    rbx, rbx
0x140003db8  jz      short loc_140003DC2
0x140003dba  mov     rcx, rbx; void *
0x140003dbd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003dc2  mov     eax, edi
0x140003dc4  mov     rcx, [rbp+var_10]
0x140003dc8  xor     rcx, rsp; StackCookie
0x140003dcb  call    __security_check_cookie
0x140003dd0  mov     rbx, [rsp+40h+arg_10]
0x140003dd5  mov     rsi, [rsp+40h+arg_18]
0x140003dda  add     rsp, 40h
0x140003dde  pop     r14
0x140003de0  pop     rdi
0x140003de1  pop     rbp
0x140003de2  retn
```
