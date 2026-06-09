# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x18000df00`
- end: `0x18000dfa5`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000df00`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000df83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000df83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000df6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000df6c`

## string_xrefs

- `0x18000df65`: `ntdll.dll`

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
  v5[0] = 11;
  v5[1] = 0x180000000uLL;
  v6 = (unsigned __int64)a2;
  v7 = 0;
  v8 = -1;
  ProcAddress = (FARPROC)`wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert;
  if ( `wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert )
    goto LABEL_5;
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x18000df00  push    rbp
0x18000df02  mov     rbp, rsp
0x18000df05  sub     rsp, 60h
0x18000df09  xorps   xmm0, xmm0
0x18000df0c  xor     eax, eax
0x18000df0e  movups  [rbp+var_40], xmm0
0x18000df12  movups  [rbp+var_30], xmm0
0x18000df16  movups  [rbp+var_20], xmm0
0x18000df1a  mov     [rbp+var_10], rax
0x18000df1e  mov     dword ptr [rbp+var_40], 0Bh
0x18000df25  lea     rax, cs:180000000h
0x18000df2c  mov     qword ptr [rbp+var_40+8], rax
0x18000df30  mov     qword ptr [rbp+var_30], rdx
0x18000df34  mov     byte ptr [rbp+var_30+8], 0
0x18000df38  mov     qword ptr [rbp+var_20], 0
0x18000df40  or      eax, 0FFFFFFFFh
0x18000df43  mov     dword ptr [rbp+var_20+8], eax
0x18000df46  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000df49  mov     byte ptr [rbp+var_10], 1
0x18000df4d  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000df54  test    rax, rax
0x18000df57  jnz     short loc_18000DF95
0x18000df59  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000df60  test    rax, rax
0x18000df63  jnz     short loc_18000DF79
0x18000df65  lea     rcx, ModuleName; "ntdll.dll"
0x18000df6c  call    cs:__imp_GetModuleHandleW
0x18000df72  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000df79  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000df80  mov     rcx, rax; hModule
0x18000df83  call    cs:__imp_GetProcAddress
0x18000df89  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000df90  test    rax, rax
0x18000df93  jz      short loc_18000DF9F
0x18000df95  lea     rcx, [rbp+var_40]
0x18000df99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df9e  nop
0x18000df9f  add     rsp, 60h
0x18000dfa3  pop     rbp
0x18000dfa4  retn
```
