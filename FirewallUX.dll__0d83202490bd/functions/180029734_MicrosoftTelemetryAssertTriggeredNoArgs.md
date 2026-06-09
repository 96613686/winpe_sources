# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180029734`
- end: `0x1800297d6`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010264`
- `0x180012c04`
- `0x1800176e4`
- `0x180018568`
- `0x18001cdc0`
- `0x18001f27c`
- `0x18001f45c`
- `0x18001f53c`
- `0x18001f898`
- `0x18001f9d4`
- `0x1800209d4`

## callees

- `0x180029734`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002976f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002976f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180029755`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180029755`

## string_xrefs

- `0x180029749`: `ntdll.dll`

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
0x180029734  push    rbp
0x180029736  mov     rbp, rsp
0x180029739  sub     rsp, 60h
0x18002973d  lea     r8, [rbp+phModule]; phModule
0x180029741  mov     [rbp+phModule], 0
0x180029749  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180029750  mov     ecx, 2; dwFlags
0x180029755  call    cs:__imp_GetModuleHandleExA
0x18002975b  test    eax, eax
0x18002975d  jz      short loc_1800297D0
0x18002975f  mov     rcx, [rbp+phModule]; hModule
0x180029763  test    rcx, rcx
0x180029766  jz      short loc_1800297D0
0x180029768  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18002976f  call    cs:__imp_GetProcAddress
0x180029775  mov     rdx, rax
0x180029778  test    rax, rax
0x18002977b  jz      short loc_1800297D0
0x18002977d  xor     eax, eax
0x18002977f  lea     rcx, [rbp+var_40]
0x180029783  mov     [rbp+var_10], eax
0x180029786  xorps   xmm0, xmm0
0x180029789  movups  [rbp+var_20], xmm0
0x18002978d  lea     rax, __ImageBase
0x180029794  movups  [rbp+var_40], xmm0
0x180029798  mov     qword ptr [rbp+var_40+8], rax
0x18002979c  mov     rax, [rbp+8]
0x1800297a0  movups  [rbp+var_30], xmm0
0x1800297a4  mov     qword ptr [rbp+var_30], rax
0x1800297a8  or      eax, 0FFFFFFFFh
0x1800297ab  mov     dword ptr [rbp+var_20+8], eax
0x1800297ae  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800297b1  mov     rax, rdx
0x1800297b4  mov     dword ptr [rbp+var_40], 0Bh
0x1800297bb  mov     byte ptr [rbp+var_10], 1
0x1800297bf  mov     byte ptr [rbp+var_30+8], 0
0x1800297c3  mov     qword ptr [rbp+var_20], 0
0x1800297cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297d0  add     rsp, 60h
0x1800297d4  pop     rbp
0x1800297d5  retn
```
