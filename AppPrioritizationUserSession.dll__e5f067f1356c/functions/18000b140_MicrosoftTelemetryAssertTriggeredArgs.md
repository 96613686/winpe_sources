# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x18000b140`
- end: `0x18000b1fe`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009a30`

## callees

- `0x18000b140`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b18e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b18e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000b174`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000b174`

## string_xrefs

- `0x18000b168`: `ntdll.dll`

## pseudocode

```c
int __fastcall MicrosoftTelemetryAssertTriggeredArgs(__int64 a1, int a2, int a3)
{
  FARPROC ProcAddress; // rax
  _QWORD v7[5]; // [rsp+20h] [rbp-40h] BYREF
  int v8; // [rsp+48h] [rbp-18h]
  int v9; // [rsp+4Ch] [rbp-14h]
  int v10; // [rsp+50h] [rbp-10h]
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
        v10 = 1;
        v7[1] = &_ImageBase;
        v7[3] = 1;
        v7[2] = retaddr;
        v7[0] = 11;
        v7[4] = 0;
        v8 = a2;
        v9 = a3;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v7);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x18000b140  mov     [rsp-8+arg_8], rbx
0x18000b145  mov     [rsp-8+arg_10], rdi
0x18000b14a  mov     [rsp-8+phModule], rcx
0x18000b14f  push    rbp
0x18000b150  mov     rbp, rsp
0x18000b153  sub     rsp, 60h
0x18000b157  mov     ebx, r8d
0x18000b15a  mov     [rbp+phModule], 0
0x18000b162  mov     edi, edx
0x18000b164  lea     r8, [rbp+phModule]; phModule
0x18000b168  lea     rdx, aNtdllDll; "ntdll.dll"
0x18000b16f  mov     ecx, 2; dwFlags
0x18000b174  call    cs:__imp_GetModuleHandleExA
0x18000b17a  test    eax, eax
0x18000b17c  jz      short loc_18000B1EC
0x18000b17e  mov     rcx, [rbp+phModule]; hModule
0x18000b182  test    rcx, rcx
0x18000b185  jz      short loc_18000B1EC
0x18000b187  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000b18e  call    cs:__imp_GetProcAddress
0x18000b194  mov     rdx, rax
0x18000b197  test    rax, rax
0x18000b19a  jz      short loc_18000B1EC
0x18000b19c  xor     eax, eax
0x18000b19e  lea     rcx, [rbp+var_40]
0x18000b1a2  mov     [rbp+var_10], eax
0x18000b1a5  xorps   xmm0, xmm0
0x18000b1a8  movups  [rbp+var_20], xmm0
0x18000b1ac  lea     rax, __ImageBase
0x18000b1b3  movups  [rbp+var_40], xmm0
0x18000b1b7  mov     qword ptr [rbp+var_40+8], rax
0x18000b1bb  mov     rax, [rbp+8]
0x18000b1bf  movups  [rbp+var_30], xmm0
0x18000b1c3  mov     qword ptr [rbp+var_30], rax
0x18000b1c7  mov     rax, rdx
0x18000b1ca  mov     dword ptr [rbp+var_40], 0Bh
0x18000b1d1  mov     byte ptr [rbp+var_10], 1
0x18000b1d5  mov     byte ptr [rbp+var_30+8], 1
0x18000b1d9  mov     qword ptr [rbp+var_20], 0
0x18000b1e1  mov     dword ptr [rbp+var_20+8], edi
0x18000b1e4  mov     dword ptr [rbp+var_20+0Ch], ebx
0x18000b1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1ec  lea     r11, [rsp+60h+var_s0]
0x18000b1f1  mov     rbx, [r11+18h]
0x18000b1f5  mov     rdi, [r11+20h]
0x18000b1f9  mov     rsp, r11
0x18000b1fc  pop     rbp
0x18000b1fd  retn
```
