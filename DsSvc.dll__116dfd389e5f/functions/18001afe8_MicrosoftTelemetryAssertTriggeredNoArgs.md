# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18001afe8`
- end: `0x18001b08a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f740`
- `0x180019624`
- `0x180019720`
- `0x1800198f8`
- `0x180019a94`
- `0x180019b24`
- `0x180019fe8`
- `0x18001a1e8`
- `0x18001a498`
- `0x18001a518`
- `0x18001a5e4`
- `0x18001a654`
- `0x18001a7cc`

## callees

- `0x18001afe8`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b023`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b023`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001b009`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001b009`

## string_xrefs

- `0x18001affd`: `ntdll.dll`

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
0x18001afe8  push    rbp
0x18001afea  mov     rbp, rsp
0x18001afed  sub     rsp, 60h
0x18001aff1  lea     r8, [rbp+phModule]; phModule
0x18001aff5  mov     [rbp+phModule], 0
0x18001affd  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18001b004  mov     ecx, 2; dwFlags
0x18001b009  call    cs:__imp_GetModuleHandleExA
0x18001b00f  test    eax, eax
0x18001b011  jz      short loc_18001B084
0x18001b013  mov     rcx, [rbp+phModule]; hModule
0x18001b017  test    rcx, rcx
0x18001b01a  jz      short loc_18001B084
0x18001b01c  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18001b023  call    cs:__imp_GetProcAddress
0x18001b029  mov     rdx, rax
0x18001b02c  test    rax, rax
0x18001b02f  jz      short loc_18001B084
0x18001b031  xor     eax, eax
0x18001b033  lea     rcx, [rbp+var_40]
0x18001b037  mov     [rbp+var_10], eax
0x18001b03a  xorps   xmm0, xmm0
0x18001b03d  movups  [rbp+var_20], xmm0
0x18001b041  lea     rax, __ImageBase
0x18001b048  movups  [rbp+var_40], xmm0
0x18001b04c  mov     qword ptr [rbp+var_40+8], rax
0x18001b050  mov     rax, [rbp+8]
0x18001b054  movups  [rbp+var_30], xmm0
0x18001b058  mov     qword ptr [rbp+var_30], rax
0x18001b05c  or      eax, 0FFFFFFFFh
0x18001b05f  mov     dword ptr [rbp+var_20+8], eax
0x18001b062  mov     dword ptr [rbp+var_20+0Ch], eax
0x18001b065  mov     rax, rdx
0x18001b068  mov     dword ptr [rbp+var_40], 0Bh
0x18001b06f  mov     byte ptr [rbp+var_10], 1
0x18001b073  mov     byte ptr [rbp+var_30+8], 0
0x18001b077  mov     qword ptr [rbp+var_20], 0
0x18001b07f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b084  add     rsp, 60h
0x18001b088  pop     rbp
0x18001b089  retn
```
