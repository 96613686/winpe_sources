# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180003574`
- end: `0x180003616`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001fb0`
- `0x1800020c0`
- `0x1800021b0`
- `0x180002430`
- `0x180002530`
- `0x1800029c8`
- `0x180003028`

## callees

- `0x180003574`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800035af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800035af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180003595`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180003595`

## string_xrefs

- `0x180003589`: `ntdll.dll`

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
        v2[1] = 0x180000000uLL;
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
0x180003574  push    rbp
0x180003576  mov     rbp, rsp
0x180003579  sub     rsp, 60h
0x18000357d  lea     r8, [rbp+phModule]; phModule
0x180003581  mov     [rbp+phModule], 0
0x180003589  lea     rdx, ModuleName; "ntdll.dll"
0x180003590  mov     ecx, 2; dwFlags
0x180003595  call    cs:__imp_GetModuleHandleExA
0x18000359b  test    eax, eax
0x18000359d  jz      short loc_180003610
0x18000359f  mov     rcx, [rbp+phModule]; hModule
0x1800035a3  test    rcx, rcx
0x1800035a6  jz      short loc_180003610
0x1800035a8  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x1800035af  call    cs:__imp_GetProcAddress
0x1800035b5  mov     rdx, rax
0x1800035b8  test    rax, rax
0x1800035bb  jz      short loc_180003610
0x1800035bd  xor     eax, eax
0x1800035bf  lea     rcx, [rbp+var_40]
0x1800035c3  mov     [rbp+var_10], eax
0x1800035c6  xorps   xmm0, xmm0
0x1800035c9  movups  [rbp+var_20], xmm0
0x1800035cd  lea     rax, cs:180000000h
0x1800035d4  movups  [rbp+var_40], xmm0
0x1800035d8  mov     qword ptr [rbp+var_40+8], rax
0x1800035dc  mov     rax, [rbp+8]
0x1800035e0  movups  [rbp+var_30], xmm0
0x1800035e4  mov     qword ptr [rbp+var_30], rax
0x1800035e8  or      eax, 0FFFFFFFFh
0x1800035eb  mov     dword ptr [rbp+var_20+8], eax
0x1800035ee  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800035f1  mov     rax, rdx
0x1800035f4  mov     dword ptr [rbp+var_40], 0Bh
0x1800035fb  mov     byte ptr [rbp+var_10], 1
0x1800035ff  mov     byte ptr [rbp+var_30+8], 0
0x180003603  mov     qword ptr [rbp+var_20], 0
0x18000360b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003610  add     rsp, 60h
0x180003614  pop     rbp
0x180003615  retn
```
