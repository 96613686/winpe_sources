# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x180006380`
- end: `0x180006431`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `177`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006380`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800063ec`
- `KERNEL32!GetModuleHandleW` at `0x1800063ec`
- `KERNEL32!GetProcAddress` at `0x180006409`
- `KERNEL32!GetProcAddress` at `0x180006409`

## string_xrefs

- `0x1800063e5`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilInternalTelAssertUM(wil::details *this, const char *a2, const void *a3)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  _QWORD v5[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v6; // [rsp+30h] [rbp-30h]
  __int64 v7; // [rsp+40h] [rbp-20h]
  __int64 v8; // [rsp+48h] [rbp-18h]
  __int64 v9; // [rsp+50h] [rbp-10h]

  v9 = 1;
  v7 = 0;
  v5[1] = 0x180000000uLL;
  v8 = -1;
  ProcAddress = (FARPROC)`wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert;
  v5[0] = 11;
  v6 = (unsigned __int64)a2;
  if ( `wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert )
    goto LABEL_5;
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "MicrosoftTelemetryAssertTriggeredUM");
  `wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_5:
    ((void (__fastcall *)(_QWORD *, const char *, const void *))ProcAddress)(v5, a2, a3);
}

```

## disassembly

```asm
0x180006380  push    rbp
0x180006382  mov     rbp, rsp
0x180006385  sub     rsp, 60h
0x180006389  xor     eax, eax
0x18000638b  xorps   xmm0, xmm0
0x18000638e  mov     [rbp+var_10], rax
0x180006392  lea     rax, cs:180000000h
0x180006399  movups  [rbp+var_20], xmm0
0x18000639d  mov     qword ptr [rbp+var_20], 0
0x1800063a5  movups  [rbp+var_40], xmm0
0x1800063a9  mov     qword ptr [rbp+var_40+8], rax
0x1800063ad  or      eax, 0FFFFFFFFh
0x1800063b0  movups  [rbp+var_30], xmm0
0x1800063b4  mov     dword ptr [rbp+var_20+8], eax
0x1800063b7  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800063ba  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x1800063c1  mov     dword ptr [rbp+var_40], 0Bh
0x1800063c8  mov     qword ptr [rbp+var_30], rdx
0x1800063cc  mov     byte ptr [rbp+var_30+8], 0
0x1800063d0  mov     byte ptr [rbp+var_10], 1
0x1800063d4  test    rax, rax
0x1800063d7  jnz     short loc_180006421
0x1800063d9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800063e0  test    rax, rax
0x1800063e3  jnz     short loc_1800063FF
0x1800063e5  lea     rcx, ModuleName; "ntdll.dll"
0x1800063ec  call    cs:__imp_GetModuleHandleW
0x1800063f3  nop     dword ptr [rax+rax+00h]
0x1800063f8  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800063ff  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180006406  mov     rcx, rax; hModule
0x180006409  call    cs:__imp_GetProcAddress
0x180006410  nop     dword ptr [rax+rax+00h]
0x180006415  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000641c  test    rax, rax
0x18000641f  jz      short loc_18000642A
0x180006421  lea     rcx, [rbp+var_40]
0x180006425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000642a  add     rsp, 60h
0x18000642e  pop     rbp
0x18000642f  retn
```
