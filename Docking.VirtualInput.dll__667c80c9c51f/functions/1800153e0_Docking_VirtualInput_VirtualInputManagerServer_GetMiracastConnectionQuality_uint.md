# Docking::VirtualInput::VirtualInputManagerServer::GetMiracastConnectionQuality(uint *)

- ea: `0x1800153e0`
- end: `0x18001547e`
- name: `?GetMiracastConnectionQuality@VirtualInputManagerServer@VirtualInput@Docking@@EEAAJPEAI@Z`
- size: `158`
- prototype: `__int64 __fastcall(Docking::VirtualInput::VirtualInputManagerServer *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800153e0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015463`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015463`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015424`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015424`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180015405`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180015405`

## string_xrefs

- `0x1800153fe`: `ShellChromeApi.dll`

## pseudocode

```c
__int64 __fastcall Docking::VirtualInput::VirtualInputManagerServer::GetMiracastConnectionQuality(
        Docking::VirtualInput::VirtualInputManagerServer *this,
        unsigned int *a2)
{
  unsigned int v3; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v4; // [rsp+24h] [rbp-34h]
  HMODULE hModule; // [rsp+28h] [rbp-30h]
  FARPROC ProcAddress; // [rsp+30h] [rbp-28h]
  FARPROC v7; // [rsp+38h] [rbp-20h]
  FARPROC v8; // [rsp+40h] [rbp-18h]

  v4 = 0;
  v3 = 0;
  hModule = LoadLibraryW(L"ShellChromeApi.dll");
  if ( hModule )
  {
    ProcAddress = GetProcAddress(hModule, "Shell_GetMiracastConnectionQuality");
    if ( ProcAddress )
    {
      v7 = ProcAddress;
      v8 = ProcAddress;
      v4 = ((__int64 (__fastcall *)(unsigned int *))ProcAddress)(&v3);
    }
    FreeLibrary(hModule);
  }
  *a2 = v3;
  return v4;
}

```

## disassembly

```asm
0x1800153e0  mov     [rsp+arg_8], rdx
0x1800153e5  mov     [rsp+arg_0], rcx
0x1800153ea  sub     rsp, 58h
0x1800153ee  mov     [rsp+58h+var_34], 0
0x1800153f6  mov     [rsp+58h+var_38], 0
0x1800153fe  lea     rcx, LibFileName; "ShellChromeApi.dll"
0x180015405  call    cs:__imp_LoadLibraryW
0x18001540b  mov     [rsp+58h+hModule], rax
0x180015410  cmp     [rsp+58h+hModule], 0
0x180015416  jz      short loc_18001546A
0x180015418  lea     rdx, ProcName; "Shell_GetMiracastConnectionQuality"
0x18001541f  mov     rcx, [rsp+58h+hModule]; hModule
0x180015424  call    cs:__imp_GetProcAddress
0x18001542a  mov     [rsp+58h+var_28], rax
0x18001542f  cmp     [rsp+58h+var_28], 0
0x180015435  jz      short loc_18001545E
0x180015437  mov     rax, [rsp+58h+var_28]
0x18001543c  mov     [rsp+58h+var_20], rax
0x180015441  mov     rax, [rsp+58h+var_20]
0x180015446  mov     [rsp+58h+var_18], rax
0x18001544b  lea     rcx, [rsp+58h+var_38]
0x180015450  mov     rax, [rsp+58h+var_18]
0x180015455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001545a  mov     [rsp+58h+var_34], eax
0x18001545e  mov     rcx, [rsp+58h+hModule]; hLibModule
0x180015463  call    cs:__imp_FreeLibrary
0x180015469  nop
0x18001546a  mov     rax, [rsp+58h+arg_8]
0x18001546f  mov     ecx, [rsp+58h+var_38]
0x180015473  mov     [rax], ecx
0x180015475  mov     eax, [rsp+58h+var_34]
0x180015479  add     rsp, 58h
0x18001547d  retn
```
