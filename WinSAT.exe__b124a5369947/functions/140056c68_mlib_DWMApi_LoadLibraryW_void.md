# mlib::DWMApi::LoadLibraryW(void)

- ea: `0x140056c68`
- end: `0x140056ce5`
- name: `?LoadLibraryW@DWMApi@mlib@@QEAAKXZ`
- size: `125`
- prototype: `unsigned int __fastcall(mlib::DWMApi *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400127ac`

## callees

- `0x140056c68`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140056c9c`
- `KERNEL32!GetProcAddress` at `0x140056cb5`
- `KERNEL32!GetProcAddress` at `0x140056cce`
- `KERNEL32!GetProcAddress` at `0x140056c9c`
- `KERNEL32!GetProcAddress` at `0x140056cb5`
- `KERNEL32!GetProcAddress` at `0x140056cce`
- `KERNEL32!LoadLibraryW` at `0x140056c78`
- `KERNEL32!LoadLibraryW` at `0x140056c78`
- `KERNEL32!GetLastError` at `0x140056c8b`

## string_xrefs

- `0x140056c71`: `dwmapi.dll`
- `0x140056c92`: `DwmEnableComposition`
- `0x140056cae`: `DwmIsCompositionEnabled`
- `0x140056cc7`: `DwmpRestartComposition`

## pseudocode

```c
DWORD __fastcall mlib::DWMApi::LoadLibraryW(mlib::DWMApi *this)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax

  LibraryW = LoadLibraryW(L"dwmapi.dll");
  *(_QWORD *)this = LibraryW;
  if ( LibraryW
    && (ProcAddress = GetProcAddress(LibraryW, "DwmEnableComposition"), (*((_QWORD *)this + 1) = ProcAddress) != 0)
    && (v5 = GetProcAddress(*(HMODULE *)this, "DwmIsCompositionEnabled"), (*((_QWORD *)this + 2) = v5) != 0)
    && (v6 = GetProcAddress(*(HMODULE *)this, "DwmpRestartComposition"), (*((_QWORD *)this + 3) = v6) != 0) )
  {
    return 0;
  }
  else
  {
    return GetLastError();
  }
}

```

## disassembly

```asm
0x140056c68  push    rbx
0x140056c6a  sub     rsp, 20h
0x140056c6e  mov     rbx, rcx
0x140056c71  lea     rcx, LibFileName; "dwmapi.dll"
0x140056c78  call    cs:__imp_LoadLibraryW
0x140056c7e  mov     [rbx], rax
0x140056c81  test    rax, rax
0x140056c84  jnz     short loc_140056C92
0x140056c86  add     rsp, 20h
0x140056c8a  pop     rbx
0x140056c8b  jmp     cs:__imp_GetLastError
0x140056c92  lea     rdx, aDwmenablecompo; "DwmEnableComposition"
0x140056c99  mov     rcx, rax; hModule
0x140056c9c  call    cs:__imp_GetProcAddress
0x140056ca2  mov     [rbx+8], rax
0x140056ca6  test    rax, rax
0x140056ca9  jz      short loc_140056C86
0x140056cab  mov     rcx, [rbx]; hModule
0x140056cae  lea     rdx, aDwmiscompositi; "DwmIsCompositionEnabled"
0x140056cb5  call    cs:__imp_GetProcAddress
0x140056cbb  mov     [rbx+10h], rax
0x140056cbf  test    rax, rax
0x140056cc2  jz      short loc_140056C86
0x140056cc4  mov     rcx, [rbx]; hModule
0x140056cc7  lea     rdx, aDwmprestartcom; "DwmpRestartComposition"
0x140056cce  call    cs:__imp_GetProcAddress
0x140056cd4  mov     [rbx+18h], rax
0x140056cd8  test    rax, rax
0x140056cdb  jz      short loc_140056C86
0x140056cdd  xor     eax, eax
0x140056cdf  add     rsp, 20h
0x140056ce3  pop     rbx
0x140056ce4  retn
```
