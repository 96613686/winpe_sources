# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1800342bc`
- end: `0x18003435e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800099f0`
- `0x18000abc0`
- `0x1800107a0`

## callees

- `0x1800342bc`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800342f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800342f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800342dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800342dd`

## string_xrefs

- `0x1800342d1`: `ntdll.dll`

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
0x1800342bc  push    rbp
0x1800342be  mov     rbp, rsp
0x1800342c1  sub     rsp, 60h
0x1800342c5  lea     r8, [rbp+phModule]; phModule
0x1800342c9  mov     [rbp+phModule], 0
0x1800342d1  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800342d8  mov     ecx, 2; dwFlags
0x1800342dd  call    cs:__imp_GetModuleHandleExA
0x1800342e3  test    eax, eax
0x1800342e5  jz      short loc_180034358
0x1800342e7  mov     rcx, [rbp+phModule]; hModule
0x1800342eb  test    rcx, rcx
0x1800342ee  jz      short loc_180034358
0x1800342f0  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800342f7  call    cs:__imp_GetProcAddress
0x1800342fd  mov     rdx, rax
0x180034300  test    rax, rax
0x180034303  jz      short loc_180034358
0x180034305  xor     eax, eax
0x180034307  lea     rcx, [rbp+var_40]
0x18003430b  mov     [rbp+var_10], eax
0x18003430e  xorps   xmm0, xmm0
0x180034311  movups  [rbp+var_20], xmm0
0x180034315  lea     rax, __ImageBase
0x18003431c  movups  [rbp+var_40], xmm0
0x180034320  mov     qword ptr [rbp+var_40+8], rax
0x180034324  mov     rax, [rbp+8]
0x180034328  movups  [rbp+var_30], xmm0
0x18003432c  mov     qword ptr [rbp+var_30], rax
0x180034330  or      eax, 0FFFFFFFFh
0x180034333  mov     dword ptr [rbp+var_20+8], eax
0x180034336  mov     dword ptr [rbp+var_20+0Ch], eax
0x180034339  mov     rax, rdx
0x18003433c  mov     dword ptr [rbp+var_40], 0Bh
0x180034343  mov     byte ptr [rbp+var_10], 1
0x180034347  mov     byte ptr [rbp+var_30+8], 0
0x18003434b  mov     qword ptr [rbp+var_20], 0
0x180034353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034358  add     rsp, 60h
0x18003435c  pop     rbp
0x18003435d  retn
```
