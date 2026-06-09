# CSpellerGlobalState::CreateThreadMgr(void)

- ea: `0x18027303c`
- end: `0x180273166`
- name: `?CreateThreadMgr@CSpellerGlobalState@@QEAAJXZ`
- size: `298`
- prototype: `__int64 __fastcall(CSpellerGlobalState *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x1802775a4`

## callees

- `0x18013bad0`
- `0x18027303c`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802730c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802730c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18027309f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18027309f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027311c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027311c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180273069`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180273069`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18027308c`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18027308c`

## string_xrefs

- `0x1802730b8`: `TF_GetThreadMgr`
- `0x18027307c`: `msctf.dll`

## pseudocode

```c
__int64 __fastcall CSpellerGlobalState::CreateThreadMgr(CSpellerGlobalState *this)
{
  signed int v2; // ebx
  HMODULE Library; // rax
  _QWORD *v4; // rdi
  FARPROC ProcAddress; // rax
  _QWORD *v6; // rsi
  signed int LastError; // eax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-248h] BYREF

  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 <= 0x102 )
  {
    v2 = 0;
    PathCchAppend(Buffer, 0x104u, L"msctf.dll");
    Library = LoadLibraryExW(Buffer, 0, 0x800u);
    v4 = (_QWORD *)((char *)this + 136);
    *((_QWORD *)this + 17) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "TF_GetThreadMgr");
      if ( ProcAddress )
      {
        v6 = (_QWORD *)((char *)this + 128);
        ((void (__fastcall *)(char *))ProcAddress)((char *)this + 128);
        if ( !*((_QWORD *)this + 16) )
          return (unsigned int)-2147467259;
        v2 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 16) + 24LL))(
               *((_QWORD *)this + 16),
               (char *)this + 144);
        if ( v2 < 0 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 16LL))(*v6);
          *v6 = 0;
          return (unsigned int)v2;
        }
      }
    }
    goto LABEL_11;
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  v4 = (_QWORD *)((char *)this + 136);
  if ( v2 >= 0 )
  {
LABEL_11:
    if ( !*v4 )
      return (unsigned int)-2147467263;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18027303c  push    rbx
0x18027303e  push    rbp
0x18027303f  push    rsi
0x180273040  push    rdi
0x180273041  sub     rsp, 248h
0x180273048  mov     rax, cs:__security_cookie
0x18027304f  xor     rax, rsp
0x180273052  mov     [rsp+268h+var_38], rax
0x18027305a  mov     rbp, rcx
0x18027305d  mov     edi, 104h
0x180273062  mov     edx, edi; uSize
0x180273064  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x180273069  call    cs:__imp_GetSystemDirectoryW
0x18027306f  dec     eax
0x180273071  cmp     eax, 102h
0x180273076  ja      loc_18027311C
0x18027307c  lea     r8, pszMore; "msctf.dll"
0x180273083  mov     edx, edi; cchPath
0x180273085  lea     rcx, [rsp+268h+Buffer]; pszPath
0x18027308a  xor     ebx, ebx
0x18027308c  call    cs:__imp_PathCchAppend
0x180273092  xor     edx, edx; hFile
0x180273094  lea     rcx, [rsp+268h+Buffer]; lpLibFileName
0x180273099  mov     r8d, 800h; dwFlags
0x18027309f  call    cs:__imp_LoadLibraryExW
0x1802730a5  lea     rdi, [rbp+88h]
0x1802730ac  mov     [rdi], rax
0x1802730af  test    rax, rax
0x1802730b2  jz      loc_18027313C
0x1802730b8  lea     rdx, aTfGetthreadmgr; "TF_GetThreadMgr"
0x1802730bf  mov     rcx, rax; hModule
0x1802730c2  call    cs:__imp_GetProcAddress
0x1802730c8  test    rax, rax
0x1802730cb  jz      short loc_18027313C
0x1802730cd  lea     rsi, [rbp+80h]
0x1802730d4  mov     rcx, rsi
0x1802730d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802730dc  mov     rcx, [rsi]
0x1802730df  test    rcx, rcx
0x1802730e2  jz      short loc_180273115
0x1802730e4  mov     rax, [rcx]
0x1802730e7  lea     rdx, [rbp+90h]
0x1802730ee  mov     rax, [rax+18h]
0x1802730f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802730f7  mov     ebx, eax
0x1802730f9  test    eax, eax
0x1802730fb  jns     short loc_18027313C
0x1802730fd  mov     rcx, [rsi]
0x180273100  mov     rdx, [rcx]
0x180273103  mov     rax, [rdx+10h]
0x180273107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027310c  mov     qword ptr [rsi], 0
0x180273113  jmp     short loc_180273148
0x180273115  mov     ebx, 80004005h
0x18027311a  jmp     short loc_180273148
0x18027311c  call    cs:__imp_GetLastError
0x180273122  mov     ebx, eax
0x180273124  test    eax, eax
0x180273126  jle     short loc_180273131
0x180273128  movzx   ebx, ax
0x18027312b  or      ebx, 80070000h
0x180273131  lea     rdi, [rbp+88h]
0x180273138  test    ebx, ebx
0x18027313a  js      short loc_180273148
0x18027313c  cmp     qword ptr [rdi], 0
0x180273140  mov     eax, 80004001h
0x180273145  cmovz   ebx, eax
0x180273148  mov     eax, ebx
0x18027314a  mov     rcx, [rsp+268h+var_38]
0x180273152  xor     rcx, rsp; StackCookie
0x180273155  call    __security_check_cookie
0x18027315a  add     rsp, 248h
0x180273161  pop     rdi
0x180273162  pop     rsi
0x180273163  pop     rbp
0x180273164  pop     rbx
0x180273165  retn
```
