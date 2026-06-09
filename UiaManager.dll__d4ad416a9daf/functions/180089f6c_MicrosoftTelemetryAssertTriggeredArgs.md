# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x180089f6c`
- end: `0x18008a022`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022fbc`

## callees

- `0x180089f6c`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089fb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089fb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180089f98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180089f98`

## string_xrefs

- `0x180089feb`: `UiaCommon.lib`
- `0x180089f88`: `ntdll.dll`

## pseudocode

```c
int __fastcall MicrosoftTelemetryAssertTriggeredArgs(__int64 a1, unsigned int a2)
{
  FARPROC ProcAddress; // rax
  _QWORD v5[6]; // [rsp+20h] [rbp-40h] BYREF
  int v6; // [rsp+50h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+8h]
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
        v5[1] = &_ImageBase;
        v5[3] = 1;
        v5[2] = retaddr;
        v5[4] = "UiaCommon.lib";
        v5[0] = 11;
        v5[5] = a2;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v5);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x180089f6c  mov     [rsp-8+arg_8], rbx
0x180089f71  mov     [rsp-8+phModule], rcx
0x180089f76  push    rbp
0x180089f77  mov     rbp, rsp
0x180089f7a  sub     rsp, 60h
0x180089f7e  mov     ebx, edx
0x180089f80  mov     [rbp+phModule], 0
0x180089f88  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180089f8f  mov     ecx, 2; dwFlags
0x180089f94  lea     r8, [rbp+phModule]; phModule
0x180089f98  call    cs:__imp_GetModuleHandleExA
0x180089f9e  test    eax, eax
0x180089fa0  jz      short loc_18008A017
0x180089fa2  mov     rcx, [rbp+phModule]; hModule
0x180089fa6  test    rcx, rcx
0x180089fa9  jz      short loc_18008A017
0x180089fab  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180089fb2  call    cs:__imp_GetProcAddress
0x180089fb8  mov     rdx, rax
0x180089fbb  test    rax, rax
0x180089fbe  jz      short loc_18008A017
0x180089fc0  xor     eax, eax
0x180089fc2  lea     rcx, [rbp+var_40]
0x180089fc6  mov     [rbp+var_10], eax
0x180089fc9  xorps   xmm0, xmm0
0x180089fcc  movups  [rbp+var_20], xmm0
0x180089fd0  lea     rax, __ImageBase
0x180089fd7  movups  [rbp+var_40], xmm0
0x180089fdb  mov     qword ptr [rbp+var_40+8], rax
0x180089fdf  mov     rax, [rbp+8]
0x180089fe3  movups  [rbp+var_30], xmm0
0x180089fe7  mov     qword ptr [rbp+var_30], rax
0x180089feb  lea     rax, aUiacommonLib; "UiaCommon.lib"
0x180089ff2  mov     qword ptr [rbp+var_20], rax
0x180089ff6  mov     rax, rdx
0x180089ff9  mov     dword ptr [rbp+var_40], 0Bh
0x18008a000  mov     byte ptr [rbp+var_10], 1
0x18008a004  mov     byte ptr [rbp+var_30+8], 1
0x18008a008  mov     dword ptr [rbp+var_20+8], ebx
0x18008a00b  mov     dword ptr [rbp+var_20+0Ch], 0
0x18008a012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a017  mov     rbx, [rsp+60h+arg_8]
0x18008a01c  add     rsp, 60h
0x18008a020  pop     rbp
0x18008a021  retn
```
