# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x180036294`
- end: `0x180036362`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032398`

## callees

- `0x180036294`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800362e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800362e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800362c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800362c8`

## string_xrefs

- `0x180036327`: `rdpidd.dll`
- `0x1800362bc`: `ntdll.dll`

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
        v7[1] = 0x180000000uLL;
        v7[3] = 1;
        v7[2] = retaddr;
        v7[4] = "rdpidd.dll";
        v7[0] = 11;
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
0x180036294  mov     [rsp-8+arg_8], rbx
0x180036299  mov     [rsp-8+arg_10], rdi
0x18003629e  mov     [rsp-8+phModule], rcx
0x1800362a3  push    rbp
0x1800362a4  mov     rbp, rsp
0x1800362a7  sub     rsp, 60h
0x1800362ab  mov     ebx, r8d
0x1800362ae  mov     [rbp+phModule], 0
0x1800362b6  mov     edi, edx
0x1800362b8  lea     r8, [rbp+phModule]; phModule
0x1800362bc  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800362c3  mov     ecx, 2; dwFlags
0x1800362c8  call    cs:__imp_GetModuleHandleExA
0x1800362cf  nop     dword ptr [rax+rax+00h]
0x1800362d4  test    eax, eax
0x1800362d6  jz      short loc_18003634F
0x1800362d8  mov     rcx, [rbp+phModule]; hModule
0x1800362dc  test    rcx, rcx
0x1800362df  jz      short loc_18003634F
0x1800362e1  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800362e8  call    cs:__imp_GetProcAddress
0x1800362ef  nop     dword ptr [rax+rax+00h]
0x1800362f4  mov     rdx, rax
0x1800362f7  test    rax, rax
0x1800362fa  jz      short loc_18003634F
0x1800362fc  xor     eax, eax
0x1800362fe  lea     rcx, [rbp+var_40]
0x180036302  mov     [rbp+var_10], eax
0x180036305  xorps   xmm0, xmm0
0x180036308  movups  [rbp+var_20], xmm0
0x18003630c  lea     rax, cs:180000000h
0x180036313  movups  [rbp+var_40], xmm0
0x180036317  mov     qword ptr [rbp+var_40+8], rax
0x18003631b  mov     rax, [rbp+8]
0x18003631f  movups  [rbp+var_30], xmm0
0x180036323  mov     qword ptr [rbp+var_30], rax
0x180036327  lea     rax, aRdpiddDll_0; "rdpidd.dll"
0x18003632e  mov     qword ptr [rbp+var_20], rax
0x180036332  mov     rax, rdx
0x180036335  mov     dword ptr [rbp+var_40], 0Bh
0x18003633c  mov     byte ptr [rbp+var_10], 1
0x180036340  mov     byte ptr [rbp+var_30+8], 1
0x180036344  mov     dword ptr [rbp+var_20+8], edi
0x180036347  mov     dword ptr [rbp+var_20+0Ch], ebx
0x18003634a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003634f  lea     r11, [rsp+60h+var_s0]
0x180036354  mov     rbx, [r11+18h]
0x180036358  mov     rdi, [r11+20h]
0x18003635c  mov     rsp, r11
0x18003635f  pop     rbp
0x180036360  retn
```
