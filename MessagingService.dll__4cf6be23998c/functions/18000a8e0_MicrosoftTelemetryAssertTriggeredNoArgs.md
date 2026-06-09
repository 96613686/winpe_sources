# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000a8e0`
- end: `0x18000a982`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `int()`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000547c`
- `0x180005720`
- `0x180005a7c`

## callees

- `0x18000a8e0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a91b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a91b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000a901`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000a901`

## string_xrefs

- `0x18000a8f5`: `ntdll.dll`

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
        v2[1] = 0x180000000uLL;
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
0x18000a8e0  push    rbp
0x18000a8e2  mov     rbp, rsp
0x18000a8e5  sub     rsp, 60h
0x18000a8e9  lea     r8, [rbp+phModule]; phModule
0x18000a8ed  mov     [rbp+phModule], 0
0x18000a8f5  lea     rdx, ModuleName; "ntdll.dll"
0x18000a8fc  mov     ecx, 2; dwFlags
0x18000a901  call    cs:__imp_GetModuleHandleExA
0x18000a907  test    eax, eax
0x18000a909  jz      short loc_18000A97C
0x18000a90b  mov     rcx, [rbp+phModule]; hModule
0x18000a90f  test    rcx, rcx
0x18000a912  jz      short loc_18000A97C
0x18000a914  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18000a91b  call    cs:__imp_GetProcAddress
0x18000a921  mov     rdx, rax
0x18000a924  test    rax, rax
0x18000a927  jz      short loc_18000A97C
0x18000a929  xor     eax, eax
0x18000a92b  lea     rcx, [rbp+var_40]
0x18000a92f  mov     [rbp+var_10], eax
0x18000a932  xorps   xmm0, xmm0
0x18000a935  movups  [rbp+var_20], xmm0
0x18000a939  lea     rax, cs:180000000h
0x18000a940  movups  [rbp+var_40], xmm0
0x18000a944  mov     qword ptr [rbp+var_40+8], rax
0x18000a948  mov     rax, [rbp+8]
0x18000a94c  movups  [rbp+var_30], xmm0
0x18000a950  mov     qword ptr [rbp+var_30], rax
0x18000a954  or      eax, 0FFFFFFFFh
0x18000a957  mov     dword ptr [rbp+var_20+8], eax
0x18000a95a  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000a95d  mov     rax, rdx
0x18000a960  mov     dword ptr [rbp+var_40], 0Bh
0x18000a967  mov     byte ptr [rbp+var_10], 1
0x18000a96b  mov     byte ptr [rbp+var_30+8], 0
0x18000a96f  mov     qword ptr [rbp+var_20], 0
0x18000a977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a97c  add     rsp, 60h
0x18000a980  pop     rbp
0x18000a981  retn
```
