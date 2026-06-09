# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x18001b9b0`
- end: `0x18001ba66`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002c80`
- `0x180004720`

## callees

- `0x18001b9b0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001b9dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001b9dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b9f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b9f6`

## string_xrefs

- `0x18001ba2f`: `cldapi.dll`
- `0x18001b9cc`: `ntdll.dll`

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
        v5[4] = "cldapi.dll";
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
0x18001b9b0  mov     [rsp-8+arg_8], rbx
0x18001b9b5  mov     [rsp-8+phModule], rcx
0x18001b9ba  push    rbp
0x18001b9bb  mov     rbp, rsp
0x18001b9be  sub     rsp, 60h
0x18001b9c2  mov     ebx, edx
0x18001b9c4  mov     [rbp+phModule], 0
0x18001b9cc  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18001b9d3  mov     ecx, 2; dwFlags
0x18001b9d8  lea     r8, [rbp+phModule]; phModule
0x18001b9dc  call    cs:__imp_GetModuleHandleExA
0x18001b9e2  test    eax, eax
0x18001b9e4  jz      short loc_18001BA5B
0x18001b9e6  mov     rcx, [rbp+phModule]; hModule
0x18001b9ea  test    rcx, rcx
0x18001b9ed  jz      short loc_18001BA5B
0x18001b9ef  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18001b9f6  call    cs:__imp_GetProcAddress
0x18001b9fc  mov     rdx, rax
0x18001b9ff  test    rax, rax
0x18001ba02  jz      short loc_18001BA5B
0x18001ba04  xor     eax, eax
0x18001ba06  lea     rcx, [rbp+var_40]
0x18001ba0a  mov     [rbp+var_10], eax
0x18001ba0d  xorps   xmm0, xmm0
0x18001ba10  movups  [rbp+var_20], xmm0
0x18001ba14  lea     rax, __ImageBase
0x18001ba1b  movups  [rbp+var_40], xmm0
0x18001ba1f  mov     qword ptr [rbp+var_40+8], rax
0x18001ba23  mov     rax, [rbp+8]
0x18001ba27  movups  [rbp+var_30], xmm0
0x18001ba2b  mov     qword ptr [rbp+var_30], rax
0x18001ba2f  lea     rax, aCldapiDll_0; "cldapi.dll"
0x18001ba36  mov     qword ptr [rbp+var_20], rax
0x18001ba3a  mov     rax, rdx
0x18001ba3d  mov     dword ptr [rbp+var_40], 0Bh
0x18001ba44  mov     byte ptr [rbp+var_10], 1
0x18001ba48  mov     byte ptr [rbp+var_30+8], 1
0x18001ba4c  mov     dword ptr [rbp+var_20+8], ebx
0x18001ba4f  mov     dword ptr [rbp+var_20+0Ch], 0
0x18001ba56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba5b  mov     rbx, [rsp+60h+arg_8]
0x18001ba60  add     rsp, 60h
0x18001ba64  pop     rbp
0x18001ba65  retn
```
