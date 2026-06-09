# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x18000bd80`
- end: `0x18000be47`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `199`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003870`
- `0x18000bd80`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000be02`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000be02`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000be19`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000be19`

## string_xrefs

- `0x18000bdfb`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilInternalTelAssertUM(wil::details *this, const char *a2, const void *a3)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  _QWORD v5[2]; // [rsp+28h] [rbp-48h] BYREF
  __int128 v6; // [rsp+38h] [rbp-38h]
  __int64 v7; // [rsp+48h] [rbp-28h]
  __int64 v8; // [rsp+50h] [rbp-20h]
  __int64 v9; // [rsp+58h] [rbp-18h]

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
0x18000bd80  push    rbp
0x18000bd82  mov     rbp, rsp
0x18000bd85  sub     rsp, 70h
0x18000bd89  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x18000bd91  mov     rax, cs:__security_cookie
0x18000bd98  xor     rax, rsp
0x18000bd9b  mov     [rbp+var_10], rax
0x18000bd9f  xorps   xmm0, xmm0
0x18000bda2  xor     eax, eax
0x18000bda4  movups  [rbp+var_48], xmm0
0x18000bda8  movups  [rbp+var_38], xmm0
0x18000bdac  movups  [rbp+var_28], xmm0
0x18000bdb0  mov     [rbp+var_18], rax
0x18000bdb4  mov     dword ptr [rbp+var_48], 0Bh
0x18000bdbb  lea     rax, cs:180000000h
0x18000bdc2  mov     qword ptr [rbp+var_48+8], rax
0x18000bdc6  mov     qword ptr [rbp+var_38], rdx
0x18000bdca  mov     byte ptr [rbp+var_38+8], 0
0x18000bdce  mov     qword ptr [rbp+var_28], 0
0x18000bdd6  or      eax, 0FFFFFFFFh
0x18000bdd9  mov     dword ptr [rbp+var_28+8], eax
0x18000bddc  mov     dword ptr [rbp+var_28+0Ch], eax
0x18000bddf  mov     byte ptr [rbp+var_18], 1
0x18000bde3  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000bdea  test    rax, rax
0x18000bded  jnz     short loc_18000BE2B
0x18000bdef  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bdf6  test    rax, rax
0x18000bdf9  jnz     short loc_18000BE0F
0x18000bdfb  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000be02  call    cs:__imp_GetModuleHandleW
0x18000be08  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000be0f  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000be16  mov     rcx, rax; hModule
0x18000be19  call    cs:__imp_GetProcAddress
0x18000be1f  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000be26  test    rax, rax
0x18000be29  jz      short loc_18000BE35
0x18000be2b  lea     rcx, [rbp+var_48]
0x18000be2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be34  nop
0x18000be35  mov     rcx, [rbp+var_10]
0x18000be39  xor     rcx, rsp; StackCookie
0x18000be3c  call    __security_check_cookie
0x18000be41  add     rsp, 70h
0x18000be45  pop     rbp
0x18000be46  retn
```
