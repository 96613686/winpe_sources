# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000c168`
- end: `0x18000c20a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `int()`
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800043a0`
- `0x180004500`
- `0x180006ea0`
- `0x1800072b0`
- `0x180007310`
- `0x180007360`
- `0x1800073b0`
- `0x1800074e0`
- `0x180007520`
- `0x180007690`
- `0x180007714`
- `0x1800078ac`

## callees

- `0x18000c168`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000c189`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000c189`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1a3`

## string_xrefs

- `0x18000c17d`: `ntdll.dll`

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
0x18000c168  push    rbp
0x18000c16a  mov     rbp, rsp
0x18000c16d  sub     rsp, 60h
0x18000c171  lea     r8, [rbp+phModule]; phModule
0x18000c175  mov     [rbp+phModule], 0
0x18000c17d  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18000c184  mov     ecx, 2; dwFlags
0x18000c189  call    cs:__imp_GetModuleHandleExA
0x18000c18f  test    eax, eax
0x18000c191  jz      short loc_18000C204
0x18000c193  mov     rcx, [rbp+phModule]; hModule
0x18000c197  test    rcx, rcx
0x18000c19a  jz      short loc_18000C204
0x18000c19c  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18000c1a3  call    cs:__imp_GetProcAddress
0x18000c1a9  mov     rdx, rax
0x18000c1ac  test    rax, rax
0x18000c1af  jz      short loc_18000C204
0x18000c1b1  xor     eax, eax
0x18000c1b3  lea     rcx, [rbp+var_40]
0x18000c1b7  mov     [rbp+var_10], eax
0x18000c1ba  xorps   xmm0, xmm0
0x18000c1bd  movups  [rbp+var_20], xmm0
0x18000c1c1  lea     rax, cs:180000000h
0x18000c1c8  movups  [rbp+var_40], xmm0
0x18000c1cc  mov     qword ptr [rbp+var_40+8], rax
0x18000c1d0  mov     rax, [rbp+8]
0x18000c1d4  movups  [rbp+var_30], xmm0
0x18000c1d8  mov     qword ptr [rbp+var_30], rax
0x18000c1dc  or      eax, 0FFFFFFFFh
0x18000c1df  mov     dword ptr [rbp+var_20+8], eax
0x18000c1e2  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000c1e5  mov     rax, rdx
0x18000c1e8  mov     dword ptr [rbp+var_40], 0Bh
0x18000c1ef  mov     byte ptr [rbp+var_10], 1
0x18000c1f3  mov     byte ptr [rbp+var_30+8], 0
0x18000c1f7  mov     qword ptr [rbp+var_20], 0
0x18000c1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c204  add     rsp, 60h
0x18000c208  pop     rbp
0x18000c209  retn
```
