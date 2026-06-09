# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000634c`
- end: `0x1800063ee`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002460`

## callees

- `0x18000634c`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006387`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006387`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000636d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000636d`

## string_xrefs

- `0x180006361`: `ntdll.dll`

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
0x18000634c  push    rbp
0x18000634e  mov     rbp, rsp
0x180006351  sub     rsp, 60h
0x180006355  lea     r8, [rbp+phModule]; phModule
0x180006359  mov     [rbp+phModule], 0
0x180006361  lea     rdx, ModuleName; "ntdll.dll"
0x180006368  mov     ecx, 2; dwFlags
0x18000636d  call    cs:__imp_GetModuleHandleExA
0x180006373  test    eax, eax
0x180006375  jz      short loc_1800063E8
0x180006377  mov     rcx, [rbp+phModule]; hModule
0x18000637b  test    rcx, rcx
0x18000637e  jz      short loc_1800063E8
0x180006380  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x180006387  call    cs:__imp_GetProcAddress
0x18000638d  mov     rdx, rax
0x180006390  test    rax, rax
0x180006393  jz      short loc_1800063E8
0x180006395  xor     eax, eax
0x180006397  lea     rcx, [rbp+var_40]
0x18000639b  mov     [rbp+var_10], eax
0x18000639e  xorps   xmm0, xmm0
0x1800063a1  movups  [rbp+var_20], xmm0
0x1800063a5  lea     rax, __ImageBase
0x1800063ac  movups  [rbp+var_40], xmm0
0x1800063b0  mov     qword ptr [rbp+var_40+8], rax
0x1800063b4  mov     rax, [rbp+8]
0x1800063b8  movups  [rbp+var_30], xmm0
0x1800063bc  mov     qword ptr [rbp+var_30], rax
0x1800063c0  or      eax, 0FFFFFFFFh
0x1800063c3  mov     dword ptr [rbp+var_20+8], eax
0x1800063c6  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800063c9  mov     rax, rdx
0x1800063cc  mov     dword ptr [rbp+var_40], 0Bh
0x1800063d3  mov     byte ptr [rbp+var_10], 1
0x1800063d7  mov     byte ptr [rbp+var_30+8], 0
0x1800063db  mov     qword ptr [rbp+var_20], 0
0x1800063e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063e8  add     rsp, 60h
0x1800063ec  pop     rbp
0x1800063ed  retn
```
