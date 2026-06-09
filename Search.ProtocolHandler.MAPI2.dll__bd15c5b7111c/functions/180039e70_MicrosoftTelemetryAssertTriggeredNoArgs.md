# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180039e70`
- end: `0x180039f12`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b80c`

## callees

- `0x180039e70`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039eab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039eab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180039e91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180039e91`

## string_xrefs

- `0x180039e85`: `ntdll.dll`

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
0x180039e70  push    rbp
0x180039e72  mov     rbp, rsp
0x180039e75  sub     rsp, 60h
0x180039e79  lea     r8, [rbp+phModule]; phModule
0x180039e7d  mov     [rbp+phModule], 0
0x180039e85  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180039e8c  mov     ecx, 2; dwFlags
0x180039e91  call    cs:__imp_GetModuleHandleExA
0x180039e97  test    eax, eax
0x180039e99  jz      short loc_180039F0C
0x180039e9b  mov     rcx, [rbp+phModule]; hModule
0x180039e9f  test    rcx, rcx
0x180039ea2  jz      short loc_180039F0C
0x180039ea4  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180039eab  call    cs:__imp_GetProcAddress
0x180039eb1  mov     rdx, rax
0x180039eb4  test    rax, rax
0x180039eb7  jz      short loc_180039F0C
0x180039eb9  xor     eax, eax
0x180039ebb  lea     rcx, [rbp+var_40]
0x180039ebf  mov     [rbp+var_10], eax
0x180039ec2  xorps   xmm0, xmm0
0x180039ec5  movups  [rbp+var_20], xmm0
0x180039ec9  lea     rax, __ImageBase
0x180039ed0  movups  [rbp+var_40], xmm0
0x180039ed4  mov     qword ptr [rbp+var_40+8], rax
0x180039ed8  mov     rax, [rbp+8]
0x180039edc  movups  [rbp+var_30], xmm0
0x180039ee0  mov     qword ptr [rbp+var_30], rax
0x180039ee4  or      eax, 0FFFFFFFFh
0x180039ee7  mov     dword ptr [rbp+var_20+8], eax
0x180039eea  mov     dword ptr [rbp+var_20+0Ch], eax
0x180039eed  mov     rax, rdx
0x180039ef0  mov     dword ptr [rbp+var_40], 0Bh
0x180039ef7  mov     byte ptr [rbp+var_10], 1
0x180039efb  mov     byte ptr [rbp+var_30+8], 0
0x180039eff  mov     qword ptr [rbp+var_20], 0
0x180039f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f0c  add     rsp, 60h
0x180039f10  pop     rbp
0x180039f11  retn
```
