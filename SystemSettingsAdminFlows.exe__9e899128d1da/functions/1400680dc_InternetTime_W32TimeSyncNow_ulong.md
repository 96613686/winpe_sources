# InternetTime_W32TimeSyncNow(ulong)

- ea: `0x1400680dc`
- end: `0x140068158`
- name: `?InternetTime_W32TimeSyncNow@@YAJK@Z`
- size: `124`
- prototype: `int(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140036b20`

## callees

- `0x14002996c`
- `0x1400680dc`
- `0x14007d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140068108`
- `KERNEL32!GetProcAddress` at `0x140068108`
- `KERNEL32!FreeLibrary` at `0x140068145`
- `KERNEL32!FreeLibrary` at `0x140068145`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400680f2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400680f2`

## string_xrefs

- `0x1400680e6`: `w32time.DLL`
- `0x14006812e`: `shell\cpls\utc\inettimecommon.cpp`

## pseudocode

```c
__int64 InternetTime_W32TimeSyncNow()
{
  unsigned int v0; // ebx
  HMODULE LibraryW; // rax
  HMODULE v2; // rdi
  FARPROC ProcAddress; // rax
  int v4; // eax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = -2147467259;
  LibraryW = LoadLibraryW(L"w32time.DLL");
  v2 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0x19);
    if ( ProcAddress )
    {
      v4 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(0, 1, 18);
      v0 = v4;
      if ( v4 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5B,
          (unsigned int)"shell\\cpls\\utc\\inettimecommon.cpp",
          (const char *)(unsigned int)v4,
          v6);
    }
    FreeLibrary(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x1400680dc  mov     [rsp+arg_0], rbx
0x1400680e1  push    rdi; int
0x1400680e2  sub     rsp, 20h
0x1400680e6  lea     rcx, aW32timeDll; "w32time.DLL"
0x1400680ed  mov     ebx, 80004005h
0x1400680f2  call    cs:__imp_LoadLibraryW
0x1400680f8  mov     rdi, rax
0x1400680fb  test    rax, rax
0x1400680fe  jz      short loc_14006814B
0x140068100  mov     edx, 19h; lpProcName
0x140068105  mov     rcx, rax; hModule
0x140068108  call    cs:__imp_GetProcAddress
0x14006810e  test    rax, rax
0x140068111  jz      short loc_140068142
0x140068113  mov     edx, 1
0x140068118  xor     ecx, ecx
0x14006811a  lea     r8d, [rdx+11h]
0x14006811e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140068123  mov     ebx, eax
0x140068125  test    eax, eax
0x140068127  jns     short loc_140068142
0x140068129  mov     rcx, [rsp+28h]; this
0x14006812e  lea     r8, aShellCplsUtcIn; "shell\\cpls\\utc\\inettimecommon.cpp"
0x140068135  mov     r9d, eax; char *
0x140068138  mov     edx, 5Bh ; '['; void *
0x14006813d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140068142  mov     rcx, rdi; hLibModule
0x140068145  call    cs:__imp_FreeLibrary
0x14006814b  mov     eax, ebx
0x14006814d  mov     rbx, [rsp+28h+arg_0]
0x140068152  add     rsp, 20h
0x140068156  pop     rdi
0x140068157  retn
```
