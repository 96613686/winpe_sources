# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180022230`
- end: `0x1800222d2`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017f40`

## callees

- `0x180022230`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180022251`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180022251`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002226b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002226b`

## string_xrefs

- `0x180022245`: `ntdll.dll`

## pseudocode

```c
int MicrosoftTelemetryAssertTriggeredNoArgs()
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
0x180022230  push    rbp
0x180022232  mov     rbp, rsp
0x180022235  sub     rsp, 60h
0x180022239  lea     r8, [rbp+phModule]; phModule
0x18002223d  mov     [rbp+phModule], 0
0x180022245  lea     rdx, ModuleName; "ntdll.dll"
0x18002224c  mov     ecx, 2; dwFlags
0x180022251  call    cs:__imp_GetModuleHandleExA
0x180022257  test    eax, eax
0x180022259  jz      short loc_1800222CC
0x18002225b  mov     rcx, [rbp+phModule]; hModule
0x18002225f  test    rcx, rcx
0x180022262  jz      short loc_1800222CC
0x180022264  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18002226b  call    cs:__imp_GetProcAddress
0x180022271  mov     rdx, rax
0x180022274  test    rax, rax
0x180022277  jz      short loc_1800222CC
0x180022279  xor     eax, eax
0x18002227b  lea     rcx, [rbp+var_40]
0x18002227f  mov     [rbp+var_10], eax
0x180022282  xorps   xmm0, xmm0
0x180022285  movups  [rbp+var_20], xmm0
0x180022289  lea     rax, __ImageBase
0x180022290  movups  [rbp+var_40], xmm0
0x180022294  mov     qword ptr [rbp+var_40+8], rax
0x180022298  mov     rax, [rbp+8]
0x18002229c  movups  [rbp+var_30], xmm0
0x1800222a0  mov     qword ptr [rbp+var_30], rax
0x1800222a4  or      eax, 0FFFFFFFFh
0x1800222a7  mov     dword ptr [rbp+var_20+8], eax
0x1800222aa  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800222ad  mov     rax, rdx
0x1800222b0  mov     dword ptr [rbp+var_40], 0Bh
0x1800222b7  mov     byte ptr [rbp+var_10], 1
0x1800222bb  mov     byte ptr [rbp+var_30+8], 0
0x1800222bf  mov     qword ptr [rbp+var_20], 0
0x1800222c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222cc  add     rsp, 60h
0x1800222d0  pop     rbp
0x1800222d1  retn
```
