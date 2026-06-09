# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x18003993c`
- end: `0x1800399f2`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `182`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000463c`
- `0x18001aecc`
- `0x18001ba5c`
- `0x180026c50`
- `0x18002abec`
- `0x18002d1c0`
- `0x18002f040`
- `0x180034460`

## callees

- `0x18003993c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039982`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039982`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180039968`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180039968`

## string_xrefs

- `0x180039958`: `ntdll.dll`
- `0x1800399bb`: `fwpolicyiomgr.dll`

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
        v5[1] = _ImageBase;
        v5[3] = 1;
        v5[2] = retaddr;
        v5[4] = "fwpolicyiomgr.dll";
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
0x18003993c  mov     [rsp-8+arg_8], rbx
0x180039941  mov     [rsp-8+phModule], rcx
0x180039946  push    rbp
0x180039947  mov     rbp, rsp
0x18003994a  sub     rsp, 60h
0x18003994e  mov     ebx, edx
0x180039950  mov     [rbp+phModule], 0
0x180039958  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18003995f  mov     ecx, 2; dwFlags
0x180039964  lea     r8, [rbp+phModule]; phModule
0x180039968  call    cs:__imp_GetModuleHandleExA
0x18003996e  test    eax, eax
0x180039970  jz      short loc_1800399E7
0x180039972  mov     rcx, [rbp+phModule]; hModule
0x180039976  test    rcx, rcx
0x180039979  jz      short loc_1800399E7
0x18003997b  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180039982  call    cs:__imp_GetProcAddress
0x180039988  mov     rdx, rax
0x18003998b  test    rax, rax
0x18003998e  jz      short loc_1800399E7
0x180039990  xor     eax, eax
0x180039992  lea     rcx, [rbp+var_40]
0x180039996  mov     [rbp+var_10], eax
0x180039999  xorps   xmm0, xmm0
0x18003999c  movups  [rbp+var_20], xmm0
0x1800399a0  lea     rax, __ImageBase
0x1800399a7  movups  [rbp+var_40], xmm0
0x1800399ab  mov     qword ptr [rbp+var_40+8], rax
0x1800399af  mov     rax, [rbp+8]
0x1800399b3  movups  [rbp+var_30], xmm0
0x1800399b7  mov     qword ptr [rbp+var_30], rax
0x1800399bb  lea     rax, aFwpolicyiomgrD_0; "fwpolicyiomgr.dll"
0x1800399c2  mov     qword ptr [rbp+var_20], rax
0x1800399c6  mov     rax, rdx
0x1800399c9  mov     dword ptr [rbp+var_40], 0Bh
0x1800399d0  mov     byte ptr [rbp+var_10], 1
0x1800399d4  mov     byte ptr [rbp+var_30+8], 1
0x1800399d8  mov     dword ptr [rbp+var_20+8], ebx
0x1800399db  mov     dword ptr [rbp+var_20+0Ch], 0
0x1800399e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399e7  mov     rbx, [rsp+60h+arg_8]
0x1800399ec  add     rsp, 60h
0x1800399f0  pop     rbp
0x1800399f1  retn
```
