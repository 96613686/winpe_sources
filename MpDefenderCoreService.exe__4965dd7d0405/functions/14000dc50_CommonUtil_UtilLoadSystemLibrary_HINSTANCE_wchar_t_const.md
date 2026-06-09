# CommonUtil::UtilLoadSystemLibrary(HINSTANCE__ * *,wchar_t const *)

- ea: `0x14000dc50`
- end: `0x14000dde3`
- name: `?UtilLoadSystemLibrary@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEB_W@Z`
- size: `403`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, HINSTANCE *, const wchar_t *)`
- caller_count: `6`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14000b2f0`
- `0x14000b460`
- `0x14000bdbc`
- `0x14000d8a4`
- `0x1400187cc`
- `0x1400e1ac4`

## callees

- `0x14000dbb4`
- `0x14000dc50`
- `0x14001373c`
- `0x140013920`
- `0x140014b10`
- `0x14003a130`
- `0x14003a5c0`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x14000dc84`
- `KERNEL32!GetSystemDirectoryW` at `0x14000dd2d`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilLoadSystemLibrary(CommonUtil *this, HINSTANCE *a2, const wchar_t *a3)
{
  const struct std::nothrow_t *v5; // rdx
  int WindowsPath; // ebx
  HINSTANCE *v8; // rbx
  unsigned int v9; // r9d
  const struct std::nothrow_t *v10; // rdx
  int Library; // edi
  void *v12; // rdi
  const struct std::nothrow_t *v13; // rdx
  int IsFileExists; // esi
  HINSTANCE *v15; // [rsp+20h] [rbp-20h] BYREF
  void *v16; // [rsp+28h] [rbp-18h] BYREF

  v15 = 0;
  WindowsPath = CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v15, a2, 1);
  if ( WindowsPath < 0 )
  {
LABEL_2:
    if ( v15 )
      operator delete(v15, v5);
    return (unsigned int)WindowsPath;
  }
  v8 = v15;
  if ( (int)CommonUtil::UtilIsFileExists((CommonUtil *)v15, (const wchar_t *)v5) >= 0 )
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
      operator delete(v12, v5);
    goto LABEL_2;
  }
  v8 = v15;
  IsFileExists = CommonUtil::UtilIsFileExists((CommonUtil *)v15, (const wchar_t *)v5);
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
0x14000dc50  mov     [rsp-18h+arg_10], rbx
0x14000dc55  mov     [rsp-18h+arg_18], rsi
0x14000dc5a  push    rbp
0x14000dc5b  push    rdi
0x14000dc5c  push    r14
0x14000dc5e  mov     rbp, rsp
0x14000dc61  sub     rsp, 40h
0x14000dc65  mov     rax, cs:__security_cookie
0x14000dc6c  xor     rax, rsp
0x14000dc6f  mov     [rbp+var_10], rax
0x14000dc73  mov     rdi, rdx
0x14000dc76  mov     [rbp+var_20], 0
0x14000dc7e  mov     r14, rcx
0x14000dc81  mov     r8, rdx
0x14000dc84  mov     rcx, cs:__imp_GetSystemDirectoryW
0x14000dc8b  lea     rdx, [rbp+var_20]
0x14000dc8f  mov     esi, 1
0x14000dc94  mov     r9d, esi
0x14000dc97  call    CommonUtil__UtilGetWindowsPath
0x14000dc9c  mov     ecx, eax
0x14000dc9e  mov     ebx, eax
0x14000dca0  shr     ecx, 1Fh
0x14000dca3  test    cl, cl
0x14000dca5  jz      short loc_14000DCBC
0x14000dca7  mov     rcx, [rbp+var_20]; void *
0x14000dcab  test    rcx, rcx
0x14000dcae  jz      short loc_14000DCB5
0x14000dcb0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dcb5  mov     eax, ebx
0x14000dcb7  jmp     loc_14000DDC4
0x14000dcbc  mov     rbx, [rbp+var_20]
0x14000dcc0  mov     rcx, rbx; this
0x14000dcc3  call    ?UtilIsFileExists@CommonUtil@@YAJPEB_W@Z; CommonUtil::UtilIsFileExists(wchar_t const *)
0x14000dcc8  shr     eax, 1Fh
0x14000dccb  test    al, al
0x14000dccd  jz      loc_14000DDA2
0x14000dcd3  mov     r8, rdi; wchar_t *
0x14000dcd6  mov     [rbp+var_18], 0
0x14000dcde  lea     rdx, aForwardersLs; "forwarders\\%ls"
0x14000dce5  lea     rcx, [rbp+var_18]; this
0x14000dce9  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x14000dcee  mov     ecx, eax
0x14000dcf0  mov     edi, eax
0x14000dcf2  shr     ecx, 1Fh
0x14000dcf5  test    cl, cl
0x14000dcf7  jz      short loc_14000DD10
0x14000dcf9  mov     rcx, [rbp+var_18]; void *
0x14000dcfd  test    rcx, rcx
0x14000dd00  jz      loc_14000DDB5
0x14000dd06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dd0b  jmp     loc_14000DDB5
0x14000dd10  test    rbx, rbx
0x14000dd13  jz      short loc_14000DD25
0x14000dd15  mov     rcx, rbx; void *
0x14000dd18  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dd1d  mov     [rbp+var_20], 0
0x14000dd25  mov     rdi, [rbp+var_18]
0x14000dd29  lea     rdx, [rbp+var_20]
0x14000dd2d  mov     rcx, cs:__imp_GetSystemDirectoryW
0x14000dd34  mov     r8, rdi
0x14000dd37  mov     r9d, esi
0x14000dd3a  call    CommonUtil__UtilGetWindowsPath
0x14000dd3f  mov     ecx, eax
0x14000dd41  mov     ebx, eax
0x14000dd43  shr     ecx, 1Fh
0x14000dd46  test    cl, cl
0x14000dd48  jz      short loc_14000DD60
0x14000dd4a  test    rdi, rdi
0x14000dd4d  jz      loc_14000DCA7
0x14000dd53  mov     rcx, rdi; void *
0x14000dd56  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dd5b  jmp     loc_14000DCA7
0x14000dd60  mov     rbx, [rbp+var_20]
0x14000dd64  mov     rcx, rbx; this
0x14000dd67  call    ?UtilIsFileExists@CommonUtil@@YAJPEB_W@Z; CommonUtil::UtilIsFileExists(wchar_t const *)
0x14000dd6c  mov     ecx, eax
0x14000dd6e  mov     esi, eax
0x14000dd70  shr     ecx, 1Fh
0x14000dd73  test    cl, cl
0x14000dd75  jz      short loc_14000DD95
0x14000dd77  test    rdi, rdi
0x14000dd7a  jz      short loc_14000DD84
0x14000dd7c  mov     rcx, rdi; void *
0x14000dd7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dd84  test    rbx, rbx
0x14000dd87  jz      short loc_14000DD91
0x14000dd89  mov     rcx, rbx; void *
0x14000dd8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dd91  mov     eax, esi
0x14000dd93  jmp     short loc_14000DDC4
0x14000dd95  test    rdi, rdi
0x14000dd98  jz      short loc_14000DDA2
0x14000dd9a  mov     rcx, rdi; void *
0x14000dd9d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dda2  mov     r8d, 8; wchar_t *
0x14000dda8  mov     rdx, rbx; HINSTANCE *
0x14000ddab  mov     rcx, r14; this
0x14000ddae  call    ?UtilLoadLibraryEx@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEB_WK@Z; CommonUtil::UtilLoadLibraryEx(HINSTANCE__ * *,wchar_t const *,ulong)
0x14000ddb3  mov     edi, eax
0x14000ddb5  test    rbx, rbx
0x14000ddb8  jz      short loc_14000DDC2
0x14000ddba  mov     rcx, rbx; void *
0x14000ddbd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ddc2  mov     eax, edi
0x14000ddc4  mov     rcx, [rbp+var_10]
0x14000ddc8  xor     rcx, rsp; StackCookie
0x14000ddcb  call    __security_check_cookie
0x14000ddd0  mov     rbx, [rsp+40h+arg_10]
0x14000ddd5  mov     rsi, [rsp+40h+arg_18]
0x14000ddda  add     rsp, 40h
0x14000ddde  pop     r14
0x14000dde0  pop     rdi
0x14000dde1  pop     rbp
0x14000dde2  retn
```
