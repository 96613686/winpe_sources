# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x4069c0`
- end: `0x406a8d`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YGXPAUFailureInfo@2@@Z`
- size: `205`
- prototype: `void __stdcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4069c0`
- `0x40d1d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x406a38`
- `KERNEL32!GetProcAddress` at `0x406a38`
- `KERNEL32!GetModuleHandleW` at `0x406a23`
- `KERNEL32!GetModuleHandleW` at `0x406a23`

## string_xrefs

- `0x406a1e`: `kernelbase.dll`

## pseudocode

```c
void __stdcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC WilFailureNotifyWatchers; // edi
  HMODULE ModuleHandleW; // eax
  _DWORD v4[2]; // [esp+4h] [ebp-24h] BYREF
  char v5; // [esp+Ch] [ebp-1Ch]
  __int16 v6; // [esp+Eh] [ebp-1Ah]
  __int16 v7; // [esp+10h] [ebp-18h]
  int v8; // [esp+14h] [ebp-14h]
  int v9; // [esp+18h] [ebp-10h]
  int v10; // [esp+1Ch] [ebp-Ch]
  __int64 v11; // [esp+20h] [ebp-8h] BYREF

  WilFailureNotifyWatchers = (FARPROC)`wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers;
  v8 = 0;
  v4[0] = *((_DWORD *)this + 2);
  v4[1] = *((_DWORD *)this + 5);
  v5 = *(_BYTE *)this;
  v6 = wil::g_moduleFailureReportFlags;
  v7 = *((_WORD *)this + 20);
  v9 = *((_DWORD *)this + 9);
  v10 = *((_DWORD *)this + 19);
  v11 = 0;
  if ( `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers )
    goto LABEL_6;
  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle
    || (ModuleHandleW = GetModuleHandleW(L"kernelbase.dll"),
        (`wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW) != 0) )
  {
    WilFailureNotifyWatchers = GetProcAddress(ModuleHandleW, "WilFailureNotifyWatchers");
  }
  `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers = (int)WilFailureNotifyWatchers;
  if ( WilFailureNotifyWatchers )
LABEL_6:
    ((void (__thiscall *)(FARPROC, _DWORD, _DWORD *, __int64 *))WilFailureNotifyWatchers)(
      WilFailureNotifyWatchers,
      0,
      v4,
      &v11);
  *((_DWORD *)this + 4) = v11;
  switch ( BYTE4(v11) )
  {
    case 1u:
      *((_DWORD *)this + 1) |= 1u;
      break;
    case 2u:
      *((_DWORD *)this + 1) |= 2u;
      break;
    case 3u:
      *((_DWORD *)this + 1) |= 4u;
      break;
  }
}

```

## disassembly

```asm
0x4069c0  mov     edi, edi
0x4069c2  push    ebp
0x4069c3  mov     ebp, esp
0x4069c5  sub     esp, 24h
0x4069c8  push    esi
0x4069c9  mov     esi, [ebp+this]
0x4069cc  xorps   xmm0, xmm0
0x4069cf  push    edi
0x4069d0  mov     edi, ?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YGXIPBUWilFailureReport@@PAUWilFailureReportInformation@@@Z@4P6GXI01@_EA
0x4069d6  mov     [ebp+var_14], 0
0x4069dd  mov     eax, [esi+8]
0x4069e0  mov     [ebp+var_24], eax
0x4069e3  mov     eax, [esi+14h]
0x4069e6  mov     [ebp+var_20], eax
0x4069e9  mov     al, [esi]
0x4069eb  mov     [ebp+var_1C], al
0x4069ee  mov     ax, ?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x4069f4  mov     [ebp+var_1A], ax
0x4069f8  mov     ax, [esi+28h]
0x4069fc  mov     [ebp+var_18], ax
0x406a00  mov     eax, [esi+24h]
0x406a03  mov     [ebp+var_10], eax
0x406a06  mov     eax, [esi+4Ch]
0x406a09  mov     [ebp+var_C], eax
0x406a0c  movlpd  [ebp+var_8], xmm0
0x406a11  test    edi, edi
0x406a13  jnz     short loc_406A4A
0x406a15  mov     eax, ?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YGP6GHXZPBD@Z@4PAUHINSTANCE__@@A; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x406a1a  test    eax, eax
0x406a1c  jnz     short loc_406A32
0x406a1e  push    offset ModuleName; "kernelbase.dll"
0x406a23  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x406a29  mov     ?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YGP6GHXZPBD@Z@4PAUHINSTANCE__@@A, eax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x406a2e  test    eax, eax
0x406a30  jz      short loc_406A40
0x406a32  push    offset aWilfailurenoti; "WilFailureNotifyWatchers"
0x406a37  push    eax; hModule
0x406a38  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x406a3e  mov     edi, eax
0x406a40  mov     ?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YGXIPBUWilFailureReport@@PAUWilFailureReportInformation@@@Z@4P6GXI01@_EA, edi
0x406a46  test    edi, edi
0x406a48  jz      short loc_406A5E
0x406a4a  lea     eax, [ebp+var_8]
0x406a4d  mov     ecx, edi
0x406a4f  push    eax
0x406a50  lea     eax, [ebp+var_24]
0x406a53  push    eax
0x406a54  push    0
0x406a56  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x406a5c  call    edi ; ?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YGXIPBUWilFailureReport@@PAUWilFailureReportInformation@@@Z@4P6GXI01@_EA
0x406a5e  mov     eax, dword ptr [ebp+var_8]
0x406a61  mov     [esi+10h], eax
0x406a64  movzx   eax, byte ptr [ebp+var_8+4]
0x406a68  sub     eax, 1
0x406a6b  jz      short loc_406A83
0x406a6d  sub     eax, 1
0x406a70  jz      short loc_406A7D
0x406a72  sub     eax, 1
0x406a75  jnz     short loc_406A87
0x406a77  or      dword ptr [esi+4], 4
0x406a7b  jmp     short loc_406A87
0x406a7d  or      dword ptr [esi+4], 2
0x406a81  jmp     short loc_406A87
0x406a83  or      dword ptr [esi+4], 1
0x406a87  pop     edi
0x406a88  pop     esi
0x406a89  leave
0x406a8a  retn    4
```
