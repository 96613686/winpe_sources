# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180034cb8`
- end: `0x180034d5a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014250`

## callees

- `0x180034cb8`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180034cd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180034cd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034cf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034cf3`

## string_xrefs

- `0x180034ccd`: `ntdll.dll`

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
0x180034cb8  push    rbp
0x180034cba  mov     rbp, rsp
0x180034cbd  sub     rsp, 60h
0x180034cc1  lea     r8, [rbp+phModule]; phModule
0x180034cc5  mov     [rbp+phModule], 0
0x180034ccd  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180034cd4  mov     ecx, 2; dwFlags
0x180034cd9  call    cs:__imp_GetModuleHandleExA
0x180034cdf  test    eax, eax
0x180034ce1  jz      short loc_180034D54
0x180034ce3  mov     rcx, [rbp+phModule]; hModule
0x180034ce7  test    rcx, rcx
0x180034cea  jz      short loc_180034D54
0x180034cec  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180034cf3  call    cs:__imp_GetProcAddress
0x180034cf9  mov     rdx, rax
0x180034cfc  test    rax, rax
0x180034cff  jz      short loc_180034D54
0x180034d01  xor     eax, eax
0x180034d03  lea     rcx, [rbp+var_40]
0x180034d07  mov     [rbp+var_10], eax
0x180034d0a  xorps   xmm0, xmm0
0x180034d0d  movups  [rbp+var_20], xmm0
0x180034d11  lea     rax, __ImageBase
0x180034d18  movups  [rbp+var_40], xmm0
0x180034d1c  mov     qword ptr [rbp+var_40+8], rax
0x180034d20  mov     rax, [rbp+8]
0x180034d24  movups  [rbp+var_30], xmm0
0x180034d28  mov     qword ptr [rbp+var_30], rax
0x180034d2c  or      eax, 0FFFFFFFFh
0x180034d2f  mov     dword ptr [rbp+var_20+8], eax
0x180034d32  mov     dword ptr [rbp+var_20+0Ch], eax
0x180034d35  mov     rax, rdx
0x180034d38  mov     dword ptr [rbp+var_40], 0Bh
0x180034d3f  mov     byte ptr [rbp+var_10], 1
0x180034d43  mov     byte ptr [rbp+var_30+8], 0
0x180034d47  mov     qword ptr [rbp+var_20], 0
0x180034d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d54  add     rsp, 60h
0x180034d58  pop     rbp
0x180034d59  retn
```
