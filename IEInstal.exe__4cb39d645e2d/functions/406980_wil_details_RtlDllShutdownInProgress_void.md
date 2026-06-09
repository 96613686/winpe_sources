# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x406980`
- end: `0x4069b3`
- name: `?RtlDllShutdownInProgress@details@wil@@YGEXZ`
- size: `51`
- prototype: `unsigned __int8()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x406901`
- `0x406980`
- `0x40d1d0`

## string_xrefs

- `0x40698d`: `RtlDllShutdownInProgress`

## pseudocode

```c
unsigned __int8 wil::details::RtlDllShutdownInProgress()
{
  int (__stdcall *NtDllProcedureAddress)(); // esi
  const char *v2; // [esp+0h] [ebp-4h]

  NtDllProcedureAddress = (int (__stdcall *)())`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return ((int (__thiscall *)(int (__stdcall *)()))NtDllProcedureAddress)(NtDllProcedureAddress);
  NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress(v2);
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (int)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return ((int (__thiscall *)(int (__stdcall *)()))NtDllProcedureAddress)(NtDllProcedureAddress);
  else
    return 0;
}

```

## disassembly

```asm
0x406980  mov     edi, edi
0x406982  push    esi; char *
0x406983  mov     esi, ?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YGEXZ@4P6GEX_EA
0x406989  test    esi, esi
0x40698b  jnz     short loc_4069A7
0x40698d  mov     ecx, offset aRtldllshutdown; "RtlDllShutdownInProgress"
0x406992  call    ?wil_details_GetNtDllProcedureAddress@@YGP6GHXZPBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x406997  mov     esi, eax
0x406999  mov     ?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YGEXZ@4P6GEX_EA, esi
0x40699f  test    esi, esi
0x4069a1  jnz     short loc_4069A7
0x4069a3  xor     al, al
0x4069a5  pop     esi
0x4069a6  retn
0x4069a7  mov     ecx, esi
0x4069a9  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x4069af  call    esi ; ?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YGEXZ@4P6GEX_EA
0x4069b1  pop     esi
0x4069b2  retn
```
