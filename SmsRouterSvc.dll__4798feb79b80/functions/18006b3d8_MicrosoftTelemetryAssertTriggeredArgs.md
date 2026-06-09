# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x18006b3d8`
- end: `0x18006b499`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `193`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d80c`

## callees

- `0x18006b3d8`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18006b40c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18006b40c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b426`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b426`

## string_xrefs

- `0x18006b45f`: `smsroutersvc.dll`
- `0x18006b400`: `ntdll.dll`

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
        v7[4] = "smsroutersvc.dll";
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
0x18006b3d8  mov     [rsp-8+arg_8], rbx
0x18006b3dd  mov     [rsp-8+arg_10], rdi
0x18006b3e2  mov     [rsp-8+phModule], rcx
0x18006b3e7  push    rbp
0x18006b3e8  mov     rbp, rsp
0x18006b3eb  sub     rsp, 60h
0x18006b3ef  mov     ebx, r8d
0x18006b3f2  mov     [rbp+phModule], 0
0x18006b3fa  mov     edi, edx
0x18006b3fc  lea     r8, [rbp+phModule]; phModule
0x18006b400  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18006b407  mov     ecx, 2; dwFlags
0x18006b40c  call    cs:__imp_GetModuleHandleExA
0x18006b412  test    eax, eax
0x18006b414  jz      short loc_18006B487
0x18006b416  mov     rcx, [rbp+phModule]; hModule
0x18006b41a  test    rcx, rcx
0x18006b41d  jz      short loc_18006B487
0x18006b41f  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18006b426  call    cs:__imp_GetProcAddress
0x18006b42c  mov     rdx, rax
0x18006b42f  test    rax, rax
0x18006b432  jz      short loc_18006B487
0x18006b434  xor     eax, eax
0x18006b436  lea     rcx, [rbp+var_40]
0x18006b43a  mov     [rbp+var_10], eax
0x18006b43d  xorps   xmm0, xmm0
0x18006b440  movups  [rbp+var_20], xmm0
0x18006b444  lea     rax, __ImageBase
0x18006b44b  movups  [rbp+var_40], xmm0
0x18006b44f  mov     qword ptr [rbp+var_40+8], rax
0x18006b453  mov     rax, [rbp+8]
0x18006b457  movups  [rbp+var_30], xmm0
0x18006b45b  mov     qword ptr [rbp+var_30], rax
0x18006b45f  lea     rax, aSmsroutersvcDl_0; "smsroutersvc.dll"
0x18006b466  mov     qword ptr [rbp+var_20], rax
0x18006b46a  mov     rax, rdx
0x18006b46d  mov     dword ptr [rbp+var_40], 0Bh
0x18006b474  mov     byte ptr [rbp+var_10], 1
0x18006b478  mov     byte ptr [rbp+var_30+8], 1
0x18006b47c  mov     dword ptr [rbp+var_20+8], edi
0x18006b47f  mov     dword ptr [rbp+var_20+0Ch], ebx
0x18006b482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b487  lea     r11, [rsp+60h+var_s0]
0x18006b48c  mov     rbx, [r11+18h]
0x18006b490  mov     rdi, [r11+20h]
0x18006b494  mov     rsp, r11
0x18006b497  pop     rbp
0x18006b498  retn
```
