# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x1400072d0`
- end: `0x14000737d`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `173`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400072d0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000735b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000735b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007344`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007344`

## string_xrefs

- `0x14000733d`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilInternalTelAssertUM(wil::details *this, const char *a2, const void *a3)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  _QWORD v5[2]; // [rsp+28h] [rbp-38h] BYREF
  __int128 v6; // [rsp+38h] [rbp-28h]
  __int64 v7; // [rsp+48h] [rbp-18h]
  __int64 v8; // [rsp+50h] [rbp-10h]
  __int64 v9; // [rsp+58h] [rbp-8h]

  v9 = 1;
  v5[0] = 11;
  v5[1] = 0x140000000uLL;
  v6 = (unsigned __int64)a2;
  v7 = 0;
  v8 = -1;
  ProcAddress = (FARPROC)`wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert;
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
0x1400072d0  push    rbp
0x1400072d2  mov     rbp, rsp
0x1400072d5  sub     rsp, 60h
0x1400072d9  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x1400072e1  xorps   xmm0, xmm0
0x1400072e4  xor     eax, eax
0x1400072e6  movups  [rbp+var_38], xmm0
0x1400072ea  movups  [rbp+var_28], xmm0
0x1400072ee  movups  [rbp+var_18], xmm0
0x1400072f2  mov     [rbp+var_8], rax
0x1400072f6  mov     dword ptr [rbp+var_38], 0Bh
0x1400072fd  lea     rax, cs:140000000h
0x140007304  mov     qword ptr [rbp+var_38+8], rax
0x140007308  mov     qword ptr [rbp+var_28], rdx
0x14000730c  mov     byte ptr [rbp+var_28+8], 0
0x140007310  mov     qword ptr [rbp+var_18], 0
0x140007318  or      eax, 0FFFFFFFFh
0x14000731b  mov     dword ptr [rbp+var_18+8], eax
0x14000731e  mov     dword ptr [rbp+var_18+0Ch], eax
0x140007321  mov     byte ptr [rbp+var_8], 1
0x140007325  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x14000732c  test    rax, rax
0x14000732f  jnz     short loc_14000736D
0x140007331  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007338  test    rax, rax
0x14000733b  jnz     short loc_140007351
0x14000733d  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140007344  call    cs:__imp_GetModuleHandleW
0x14000734a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007351  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x140007358  mov     rcx, rax; hModule
0x14000735b  call    cs:__imp_GetProcAddress
0x140007361  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x140007368  test    rax, rax
0x14000736b  jz      short loc_140007377
0x14000736d  lea     rcx, [rbp+var_38]
0x140007371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007376  nop
0x140007377  add     rsp, 60h
0x14000737b  pop     rbp
0x14000737c  retn
```
