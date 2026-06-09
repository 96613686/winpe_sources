# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000be90`
- end: `0x18000bf32`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `20`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013160`
- `0x1800131b0`
- `0x180013210`
- `0x180013250`
- `0x180013290`
- `0x1800132c0`
- `0x180013360`
- `0x1800133b0`
- `0x180013400`
- `0x1800134c0`
- `0x1800135e0`
- `0x180015da0`
- `0x18001ca54`
- `0x18001dac0`
- `0x18001eb90`
- `0x18001ecb0`
- `0x18001f090`
- `0x18001f210`
- `0x18001f350`
- `0x18001f6c0`

## callees

- `0x18000be90`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000beb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000beb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000becb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000becb`

## string_xrefs

- `0x18000bea5`: `ntdll.dll`

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
0x18000be90  push    rbp
0x18000be92  mov     rbp, rsp
0x18000be95  sub     rsp, 60h
0x18000be99  lea     r8, [rbp+phModule]; phModule
0x18000be9d  mov     [rbp+phModule], 0
0x18000bea5  lea     rdx, ModuleName; "ntdll.dll"
0x18000beac  mov     ecx, 2; dwFlags
0x18000beb1  call    cs:__imp_GetModuleHandleExA
0x18000beb7  test    eax, eax
0x18000beb9  jz      short loc_18000BF2C
0x18000bebb  mov     rcx, [rbp+phModule]; hModule
0x18000bebf  test    rcx, rcx
0x18000bec2  jz      short loc_18000BF2C
0x18000bec4  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18000becb  call    cs:__imp_GetProcAddress
0x18000bed1  mov     rdx, rax
0x18000bed4  test    rax, rax
0x18000bed7  jz      short loc_18000BF2C
0x18000bed9  xor     eax, eax
0x18000bedb  lea     rcx, [rbp+var_40]
0x18000bedf  mov     [rbp+var_10], eax
0x18000bee2  xorps   xmm0, xmm0
0x18000bee5  movups  [rbp+var_20], xmm0
0x18000bee9  lea     rax, __ImageBase
0x18000bef0  movups  [rbp+var_40], xmm0
0x18000bef4  mov     qword ptr [rbp+var_40+8], rax
0x18000bef8  mov     rax, [rbp+8]
0x18000befc  movups  [rbp+var_30], xmm0
0x18000bf00  mov     qword ptr [rbp+var_30], rax
0x18000bf04  or      eax, 0FFFFFFFFh
0x18000bf07  mov     dword ptr [rbp+var_20+8], eax
0x18000bf0a  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000bf0d  mov     rax, rdx
0x18000bf10  mov     dword ptr [rbp+var_40], 0Bh
0x18000bf17  mov     byte ptr [rbp+var_10], 1
0x18000bf1b  mov     byte ptr [rbp+var_30+8], 0
0x18000bf1f  mov     qword ptr [rbp+var_20], 0
0x18000bf27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf2c  add     rsp, 60h
0x18000bf30  pop     rbp
0x18000bf31  retn
```
