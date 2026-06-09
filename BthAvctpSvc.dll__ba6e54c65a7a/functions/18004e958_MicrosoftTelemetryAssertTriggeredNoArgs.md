# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18004e958`
- end: `0x18004e9fa`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026ce0`
- `0x180040f00`
- `0x180041708`
- `0x18004209c`
- `0x180044814`

## callees

- `0x18004e958`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004e993`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004e993`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18004e979`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18004e979`

## string_xrefs

- `0x18004e96d`: `ntdll.dll`

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
0x18004e958  push    rbp
0x18004e95a  mov     rbp, rsp
0x18004e95d  sub     rsp, 60h
0x18004e961  lea     r8, [rbp+phModule]; phModule
0x18004e965  mov     [rbp+phModule], 0
0x18004e96d  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18004e974  mov     ecx, 2; dwFlags
0x18004e979  call    cs:__imp_GetModuleHandleExA
0x18004e97f  test    eax, eax
0x18004e981  jz      short loc_18004E9F4
0x18004e983  mov     rcx, [rbp+phModule]; hModule
0x18004e987  test    rcx, rcx
0x18004e98a  jz      short loc_18004E9F4
0x18004e98c  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18004e993  call    cs:__imp_GetProcAddress
0x18004e999  mov     rdx, rax
0x18004e99c  test    rax, rax
0x18004e99f  jz      short loc_18004E9F4
0x18004e9a1  xor     eax, eax
0x18004e9a3  lea     rcx, [rbp+var_40]
0x18004e9a7  mov     [rbp+var_10], eax
0x18004e9aa  xorps   xmm0, xmm0
0x18004e9ad  movups  [rbp+var_20], xmm0
0x18004e9b1  lea     rax, cs:180000000h
0x18004e9b8  movups  [rbp+var_40], xmm0
0x18004e9bc  mov     qword ptr [rbp+var_40+8], rax
0x18004e9c0  mov     rax, [rbp+8]
0x18004e9c4  movups  [rbp+var_30], xmm0
0x18004e9c8  mov     qword ptr [rbp+var_30], rax
0x18004e9cc  or      eax, 0FFFFFFFFh
0x18004e9cf  mov     dword ptr [rbp+var_20+8], eax
0x18004e9d2  mov     dword ptr [rbp+var_20+0Ch], eax
0x18004e9d5  mov     rax, rdx
0x18004e9d8  mov     dword ptr [rbp+var_40], 0Bh
0x18004e9df  mov     byte ptr [rbp+var_10], 1
0x18004e9e3  mov     byte ptr [rbp+var_30+8], 0
0x18004e9e7  mov     qword ptr [rbp+var_20], 0
0x18004e9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9f4  add     rsp, 60h
0x18004e9f8  pop     rbp
0x18004e9f9  retn
```
