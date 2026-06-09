# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1800165c4`
- end: `0x180016666`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004938`
- `0x180009450`
- `0x18000c1c4`
- `0x18000c960`
- `0x1800101d0`
- `0x180010e30`
- `0x180011aa4`
- `0x180012410`
- `0x180013ec0`
- `0x180015020`
- `0x1800152a0`
- `0x180015dc0`
- `0x180016670`
- `0x180016700`
- `0x1800180d0`
- `0x180018110`
- `0x180018150`
- `0x1800184d0`

## callees

- `0x1800165c4`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800165e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800165e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800165ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800165ff`

## string_xrefs

- `0x1800165d9`: `ntdll.dll`

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
0x1800165c4  push    rbp
0x1800165c6  mov     rbp, rsp
0x1800165c9  sub     rsp, 60h
0x1800165cd  lea     r8, [rbp+phModule]; phModule
0x1800165d1  mov     [rbp+phModule], 0
0x1800165d9  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800165e0  mov     ecx, 2; dwFlags
0x1800165e5  call    cs:__imp_GetModuleHandleExA
0x1800165eb  test    eax, eax
0x1800165ed  jz      short loc_180016660
0x1800165ef  mov     rcx, [rbp+phModule]; hModule
0x1800165f3  test    rcx, rcx
0x1800165f6  jz      short loc_180016660
0x1800165f8  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800165ff  call    cs:__imp_GetProcAddress
0x180016605  mov     rdx, rax
0x180016608  test    rax, rax
0x18001660b  jz      short loc_180016660
0x18001660d  xor     eax, eax
0x18001660f  lea     rcx, [rbp+var_40]
0x180016613  mov     [rbp+var_10], eax
0x180016616  xorps   xmm0, xmm0
0x180016619  movups  [rbp+var_20], xmm0
0x18001661d  lea     rax, __ImageBase
0x180016624  movups  [rbp+var_40], xmm0
0x180016628  mov     qword ptr [rbp+var_40+8], rax
0x18001662c  mov     rax, [rbp+8]
0x180016630  movups  [rbp+var_30], xmm0
0x180016634  mov     qword ptr [rbp+var_30], rax
0x180016638  or      eax, 0FFFFFFFFh
0x18001663b  mov     dword ptr [rbp+var_20+8], eax
0x18001663e  mov     dword ptr [rbp+var_20+0Ch], eax
0x180016641  mov     rax, rdx
0x180016644  mov     dword ptr [rbp+var_40], 0Bh
0x18001664b  mov     byte ptr [rbp+var_10], 1
0x18001664f  mov     byte ptr [rbp+var_30+8], 0
0x180016653  mov     qword ptr [rbp+var_20], 0
0x18001665b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016660  add     rsp, 60h
0x180016664  pop     rbp
0x180016665  retn
```
