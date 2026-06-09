# Microsoft::Diagnostics::UtcApiWrapper::Initialize(ulong)

- ea: `0x14001a1dc`
- end: `0x14001a243`
- name: `?Initialize@UtcApiWrapper@Diagnostics@Microsoft@@QEAAJK@Z`
- size: `103`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcApiWrapper *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x14001a1dc`
- `0x14001f3b4`
- `0x14007d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14001a226`
- `KERNEL32!GetProcAddress` at `0x14001a226`
- `KERNEL32!LoadLibraryExW` at `0x14001a1f4`
- `KERNEL32!LoadLibraryExW` at `0x14001a1f4`

## string_xrefs

- `0x14001a1e7`: `utcapi.dll`
- `0x14001a21c`: `UtcCreateSessionHandle`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::UtcApiWrapper::Initialize(Microsoft::Diagnostics::UtcApiWrapper *this)
{
  HMODULE Library; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  FARPROC ProcAddress; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Library = LoadLibraryExW(L"utcapi.dll", 0, 0x800u);
  *((_QWORD *)this + 1) = Library;
  if ( !Library )
  {
    v4 = 88;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\internal\\base\\inc\\utcapiwrapperex.h",
             v3);
  }
  ProcAddress = GetProcAddress(Library, "UtcCreateSessionHandle");
  if ( !ProcAddress )
  {
    v4 = 91;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\internal\\base\\inc\\utcapiwrapperex.h",
             v3);
  }
  return ((__int64 (__fastcall *)(Microsoft::Diagnostics::UtcApiWrapper *))ProcAddress)(this);
}

```

## disassembly

```asm
0x14001a1dc  push    rbx
0x14001a1de  sub     rsp, 20h
0x14001a1e2  mov     rbx, rcx
0x14001a1e5  xor     edx, edx; hFile
0x14001a1e7  lea     rcx, aUtcapiDll; "utcapi.dll"
0x14001a1ee  mov     r8d, 800h; dwFlags
0x14001a1f4  call    cs:__imp_LoadLibraryExW
0x14001a1fa  mov     [rbx+8], rax
0x14001a1fe  test    rax, rax
0x14001a201  jnz     short loc_14001A21C
0x14001a203  lea     edx, [rax+58h]; void *
0x14001a206  mov     rcx, [rsp+28h]; this
0x14001a20b  lea     r8, aOnecoreInterna; "onecore\\internal\\base\\inc\\utcapiwra"...
0x14001a212  add     rsp, 20h
0x14001a216  pop     rbx
0x14001a217  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001a21c  lea     rdx, aUtccreatesessi; "UtcCreateSessionHandle"
0x14001a223  mov     rcx, rax; hModule
0x14001a226  call    cs:__imp_GetProcAddress
0x14001a22c  test    rax, rax
0x14001a22f  jnz     short loc_14001A236
0x14001a231  lea     edx, [rax+5Bh]
0x14001a234  jmp     short loc_14001A206
0x14001a236  mov     rcx, rbx
0x14001a239  add     rsp, 20h
0x14001a23d  pop     rbx
0x14001a23e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
