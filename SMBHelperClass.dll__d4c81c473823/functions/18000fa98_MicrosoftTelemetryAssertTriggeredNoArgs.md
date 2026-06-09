# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000fa98`
- end: `0x18000fb3a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005910`
- `0x18000b890`
- `0x18000bee0`
- `0x18000bf40`
- `0x18000bf90`
- `0x18000bfe0`
- `0x18000c100`
- `0x18000c140`
- `0x18000c1c0`

## callees

- `0x18000fa98`
- `0x180012010`

## import_xrefs

- `KERNEL32!GetModuleHandleExA` at `0x18000fab9`
- `KERNEL32!GetModuleHandleExA` at `0x18000fab9`
- `KERNEL32!GetProcAddress` at `0x18000fad3`
- `KERNEL32!GetProcAddress` at `0x18000fad3`

## string_xrefs

- `0x18000faad`: `ntdll.dll`

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
0x18000fa98  push    rbp
0x18000fa9a  mov     rbp, rsp
0x18000fa9d  sub     rsp, 60h
0x18000faa1  lea     r8, [rbp+phModule]; phModule
0x18000faa5  mov     [rbp+phModule], 0
0x18000faad  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18000fab4  mov     ecx, 2; dwFlags
0x18000fab9  call    cs:__imp_GetModuleHandleExA
0x18000fabf  test    eax, eax
0x18000fac1  jz      short loc_18000FB34
0x18000fac3  mov     rcx, [rbp+phModule]; hModule
0x18000fac7  test    rcx, rcx
0x18000faca  jz      short loc_18000FB34
0x18000facc  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000fad3  call    cs:__imp_GetProcAddress
0x18000fad9  mov     rdx, rax
0x18000fadc  test    rax, rax
0x18000fadf  jz      short loc_18000FB34
0x18000fae1  xor     eax, eax
0x18000fae3  lea     rcx, [rbp+var_40]
0x18000fae7  mov     [rbp+var_10], eax
0x18000faea  xorps   xmm0, xmm0
0x18000faed  movups  [rbp+var_20], xmm0
0x18000faf1  lea     rax, cs:180000000h
0x18000faf8  movups  [rbp+var_40], xmm0
0x18000fafc  mov     qword ptr [rbp+var_40+8], rax
0x18000fb00  mov     rax, [rbp+8]
0x18000fb04  movups  [rbp+var_30], xmm0
0x18000fb08  mov     qword ptr [rbp+var_30], rax
0x18000fb0c  or      eax, 0FFFFFFFFh
0x18000fb0f  mov     dword ptr [rbp+var_20+8], eax
0x18000fb12  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000fb15  mov     rax, rdx
0x18000fb18  mov     dword ptr [rbp+var_40], 0Bh
0x18000fb1f  mov     byte ptr [rbp+var_10], 1
0x18000fb23  mov     byte ptr [rbp+var_30+8], 0
0x18000fb27  mov     qword ptr [rbp+var_20], 0
0x18000fb2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb34  add     rsp, 60h
0x18000fb38  pop     rbp
0x18000fb39  retn
```
