# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1800135cc`
- end: `0x18001366e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `43`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002934`
- `0x180002998`
- `0x180002ab4`
- `0x180003b58`
- `0x180003fc0`
- `0x180004320`
- `0x180004d08`
- `0x180006004`
- `0x1800060d0`
- `0x180006320`
- `0x180006470`
- `0x1800064a8`
- `0x1800065e0`
- `0x180006640`
- `0x1800066b0`
- `0x180006714`
- `0x180006904`
- `0x180007380`
- `0x18000768c`
- `0x180007c14`
- `0x180007ff0`
- `0x18000838c`
- `0x18000913c`
- `0x18000b02c`
- `0x18000b244`
- `0x18000b324`
- `0x18000b3fc`
- `0x18000b7a0`
- `0x18000b96c`
- `0x18000bbb8`
- `0x18000c820`
- `0x18000ca5c`
- `0x18000cc50`
- `0x18000dabc`
- `0x18000f070`
- `0x18000f4c8`
- `0x18000f6bc`
- `0x18000f94c`
- `0x18000fd5c`
- `0x18001015c`
- `0x18001031c`
- `0x180010eac`
- `0x180011fb0`

## callees

- `0x1800135cc`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180013607`
- `KERNEL32!GetProcAddress` at `0x180013607`
- `KERNEL32!GetModuleHandleExA` at `0x1800135ed`
- `KERNEL32!GetModuleHandleExA` at `0x1800135ed`

## string_xrefs

- `0x1800135e1`: `ntdll.dll`

## pseudocode

```c
int __fastcall MicrosoftTelemetryAssertTriggeredNoArgs()
{
  FARPROC ProcAddress; // rax
  _QWORD v2[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v3; // [rsp+30h] [rbp-30h]
  __int64 v4; // [rsp+40h] [rbp-20h]
  __int64 v5; // [rsp+48h] [rbp-18h]
  int v6; // [rsp+50h] [rbp-10h]
  unsigned __int64 retaddr; // [rsp+68h] [rbp+8h]
  HMODULE phModule; // [rsp+70h] [rbp+10h] BYREF

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExA(2u, "ntdll.dll", &phModule);
  if ( (_DWORD)ProcAddress )
  {
    if ( phModule )
    {
      ProcAddress = GetProcAddress(phModule, "MicrosoftTelemetryAssertTriggeredUM");
      if ( ProcAddress )
      {
        v6 = 1;
        v2[1] = &_ImageBase;
        v3 = retaddr;
        v5 = -1;
        v2[0] = 11;
        v4 = 0;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v2);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x1800135cc  push    rbp
0x1800135ce  mov     rbp, rsp
0x1800135d1  sub     rsp, 60h
0x1800135d5  lea     r8, [rbp+phModule]; phModule
0x1800135d9  mov     [rbp+phModule], 0
0x1800135e1  lea     rdx, ModuleName; "ntdll.dll"
0x1800135e8  mov     ecx, 2; dwFlags
0x1800135ed  call    cs:__imp_GetModuleHandleExA
0x1800135f3  test    eax, eax
0x1800135f5  jz      short loc_180013668
0x1800135f7  mov     rcx, [rbp+phModule]; hModule
0x1800135fb  test    rcx, rcx
0x1800135fe  jz      short loc_180013668
0x180013600  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x180013607  call    cs:__imp_GetProcAddress
0x18001360d  mov     rdx, rax
0x180013610  test    rax, rax
0x180013613  jz      short loc_180013668
0x180013615  xor     eax, eax
0x180013617  lea     rcx, [rbp+var_40]
0x18001361b  mov     [rbp+var_10], eax
0x18001361e  xorps   xmm0, xmm0
0x180013621  movups  [rbp+var_20], xmm0
0x180013625  lea     rax, __ImageBase
0x18001362c  movups  [rbp+var_40], xmm0
0x180013630  mov     qword ptr [rbp+var_40+8], rax
0x180013634  mov     rax, [rbp+8]
0x180013638  movups  [rbp+var_30], xmm0
0x18001363c  mov     qword ptr [rbp+var_30], rax
0x180013640  or      eax, 0FFFFFFFFh
0x180013643  mov     dword ptr [rbp+var_20+8], eax
0x180013646  mov     dword ptr [rbp+var_20+0Ch], eax
0x180013649  mov     rax, rdx
0x18001364c  mov     dword ptr [rbp+var_40], 0Bh
0x180013653  mov     byte ptr [rbp+var_10], 1
0x180013657  mov     byte ptr [rbp+var_30+8], 0
0x18001365b  mov     qword ptr [rbp+var_20], 0
0x180013663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013668  add     rsp, 60h
0x18001366c  pop     rbp
0x18001366d  retn
```
