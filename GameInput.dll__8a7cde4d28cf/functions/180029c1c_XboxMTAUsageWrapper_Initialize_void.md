# XboxMTAUsageWrapper::Initialize(void)

- ea: `0x180029c1c`
- end: `0x180029cef`
- name: `?Initialize@XboxMTAUsageWrapper@@QEAAJXZ`
- size: `211`
- prototype: `__int64 __fastcall(XboxMTAUsageWrapper *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002b60c`
- `0x18002b7ac`

## callees

- `0x180029c1c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029c97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029cb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029c97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029cb6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029c4d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029c4d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180029c30`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180029c30`

## pseudocode

```c
__int64 __fastcall XboxMTAUsageWrapper::Initialize(HMODULE *this)
{
  HMODULE LibraryW; // rdi
  signed int LastError; // eax
  signed int v4; // ecx
  __int64 result; // rax
  FARPROC ProcAddress; // rax
  FARPROC v7; // rax

  LibraryW = LoadLibraryW(L"ole32");
  if ( LibraryW == *this )
  {
    LibraryW = *this;
  }
  else
  {
    if ( *this )
      FreeLibrary(*this);
    *this = LibraryW;
  }
  if ( LibraryW
    && (ProcAddress = GetProcAddress(LibraryW, "CoIncrementMTAUsage"), (this[1] = (HMODULE)ProcAddress) != 0)
    && (v7 = GetProcAddress(*this, "CoDecrementMTAUsage"), (this[2] = (HMODULE)v7) != 0) )
  {
    result = ((__int64 (__fastcall *)(char *))this[1])((char *)this + 24);
    *((_BYTE *)this + 32) = (int)result >= 0;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    result = 2147549183LL;
    if ( v4 < 0 )
      return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x180029c1c  mov     [rsp+arg_0], rbx
0x180029c21  push    rdi
0x180029c22  sub     rsp, 20h
0x180029c26  mov     rbx, rcx
0x180029c29  lea     rcx, aOle32; "ole32"
0x180029c30  call    cs:__imp_LoadLibraryW
0x180029c37  nop     dword ptr [rax+rax+00h]
0x180029c3c  mov     rdi, rax
0x180029c3f  cmp     rax, [rbx]
0x180029c42  jz      short loc_180029C5E
0x180029c44  cmp     qword ptr [rbx], 0
0x180029c48  jz      short loc_180029C59
0x180029c4a  mov     rcx, [rbx]; hLibModule
0x180029c4d  call    cs:__imp_FreeLibrary
0x180029c54  nop     dword ptr [rax+rax+00h]
0x180029c59  mov     [rbx], rdi
0x180029c5c  jmp     short loc_180029C61
0x180029c5e  mov     rdi, [rbx]
0x180029c61  test    rdi, rdi
0x180029c64  jnz     short loc_180029C8D
0x180029c66  call    cs:__imp_GetLastError
0x180029c6d  nop     dword ptr [rax+rax+00h]
0x180029c72  mov     ecx, eax
0x180029c74  test    eax, eax
0x180029c76  jle     short loc_180029C81
0x180029c78  movzx   ecx, ax
0x180029c7b  or      ecx, 80070000h
0x180029c81  test    ecx, ecx
0x180029c83  mov     eax, 8000FFFFh
0x180029c88  cmovs   eax, ecx
0x180029c8b  jmp     short loc_180029CE3
0x180029c8d  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x180029c94  mov     rcx, rdi; hModule
0x180029c97  call    cs:__imp_GetProcAddress
0x180029c9e  nop     dword ptr [rax+rax+00h]
0x180029ca3  mov     [rbx+8], rax
0x180029ca7  test    rax, rax
0x180029caa  jz      short loc_180029C66
0x180029cac  mov     rcx, [rbx]; hModule
0x180029caf  lea     rdx, aCodecrementmta; "CoDecrementMTAUsage"
0x180029cb6  call    cs:__imp_GetProcAddress
0x180029cbd  nop     dword ptr [rax+rax+00h]
0x180029cc2  mov     [rbx+10h], rax
0x180029cc6  test    rax, rax
0x180029cc9  jz      short loc_180029C66
0x180029ccb  mov     rax, [rbx+8]
0x180029ccf  lea     rcx, [rbx+18h]
0x180029cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cd8  mov     ecx, eax
0x180029cda  shr     ecx, 1Fh
0x180029cdd  xor     cl, 1
0x180029ce0  mov     [rbx+20h], cl
0x180029ce3  mov     rbx, [rsp+28h+arg_0]
0x180029ce8  add     rsp, 20h
0x180029cec  pop     rdi
0x180029ced  retn
```
