# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x1400370f4`
- end: `0x1400371b5`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140014560`
- `0x1400180d0`

## callees

- `0x1400370f4`
- `0x14003a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140037142`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140037142`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x140037128`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x140037128`

## string_xrefs

- `0x14003711c`: `ntdll.dll`

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
        v7[1] = 0x140000000uLL;
        v7[3] = 1;
        v7[2] = retaddr;
        v7[4] = "lsaiso.exe";
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
0x1400370f4  mov     [rsp-8+arg_8], rbx
0x1400370f9  mov     [rsp-8+arg_10], rdi
0x1400370fe  mov     [rsp-8+phModule], rcx
0x140037103  push    rbp
0x140037104  mov     rbp, rsp
0x140037107  sub     rsp, 60h
0x14003710b  mov     ebx, r8d
0x14003710e  mov     [rbp+phModule], 0
0x140037116  mov     edi, edx
0x140037118  lea     r8, [rbp+phModule]; phModule
0x14003711c  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x140037123  mov     ecx, 2; dwFlags
0x140037128  call    cs:__imp_GetModuleHandleExA
0x14003712e  test    eax, eax
0x140037130  jz      short loc_1400371A3
0x140037132  mov     rcx, [rbp+phModule]; hModule
0x140037136  test    rcx, rcx
0x140037139  jz      short loc_1400371A3
0x14003713b  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x140037142  call    cs:__imp_GetProcAddress
0x140037148  mov     rdx, rax
0x14003714b  test    rax, rax
0x14003714e  jz      short loc_1400371A3
0x140037150  xor     eax, eax
0x140037152  lea     rcx, [rbp+var_40]
0x140037156  mov     [rbp+var_10], eax
0x140037159  xorps   xmm0, xmm0
0x14003715c  movups  [rbp+var_20], xmm0
0x140037160  lea     rax, cs:140000000h
0x140037167  movups  [rbp+var_40], xmm0
0x14003716b  mov     qword ptr [rbp+var_40+8], rax
0x14003716f  mov     rax, [rbp+8]
0x140037173  movups  [rbp+var_30], xmm0
0x140037177  mov     qword ptr [rbp+var_30], rax
0x14003717b  lea     rax, aLsaisoExe_0; "lsaiso.exe"
0x140037182  mov     qword ptr [rbp+var_20], rax
0x140037186  mov     rax, rdx
0x140037189  mov     dword ptr [rbp+var_40], 0Bh
0x140037190  mov     byte ptr [rbp+var_10], 1
0x140037194  mov     byte ptr [rbp+var_30+8], 1
0x140037198  mov     dword ptr [rbp+var_20+8], edi
0x14003719b  mov     dword ptr [rbp+var_20+0Ch], ebx
0x14003719e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400371a3  lea     r11, [rsp+60h+var_s0]
0x1400371a8  mov     rbx, [r11+18h]
0x1400371ac  mov     rdi, [r11+20h]
0x1400371b0  mov     rsp, r11
0x1400371b3  pop     rbp
0x1400371b4  retn
```
