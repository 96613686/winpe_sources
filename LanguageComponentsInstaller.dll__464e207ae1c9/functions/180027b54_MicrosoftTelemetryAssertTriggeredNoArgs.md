# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180027b54`
- end: `0x180027bf6`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007594`
- `0x18001d0f0`
- `0x180025d20`
- `0x180026020`

## callees

- `0x180027b54`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027b8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027b8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180027b75`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180027b75`

## string_xrefs

- `0x180027b69`: `ntdll.dll`

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
0x180027b54  push    rbp
0x180027b56  mov     rbp, rsp
0x180027b59  sub     rsp, 60h
0x180027b5d  lea     r8, [rbp+phModule]; phModule
0x180027b61  mov     [rbp+phModule], 0
0x180027b69  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180027b70  mov     ecx, 2; dwFlags
0x180027b75  call    cs:__imp_GetModuleHandleExA
0x180027b7b  test    eax, eax
0x180027b7d  jz      short loc_180027BF0
0x180027b7f  mov     rcx, [rbp+phModule]; hModule
0x180027b83  test    rcx, rcx
0x180027b86  jz      short loc_180027BF0
0x180027b88  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180027b8f  call    cs:__imp_GetProcAddress
0x180027b95  mov     rdx, rax
0x180027b98  test    rax, rax
0x180027b9b  jz      short loc_180027BF0
0x180027b9d  xor     eax, eax
0x180027b9f  lea     rcx, [rbp+var_40]
0x180027ba3  mov     [rbp+var_10], eax
0x180027ba6  xorps   xmm0, xmm0
0x180027ba9  movups  [rbp+var_20], xmm0
0x180027bad  lea     rax, __ImageBase
0x180027bb4  movups  [rbp+var_40], xmm0
0x180027bb8  mov     qword ptr [rbp+var_40+8], rax
0x180027bbc  mov     rax, [rbp+8]
0x180027bc0  movups  [rbp+var_30], xmm0
0x180027bc4  mov     qword ptr [rbp+var_30], rax
0x180027bc8  or      eax, 0FFFFFFFFh
0x180027bcb  mov     dword ptr [rbp+var_20+8], eax
0x180027bce  mov     dword ptr [rbp+var_20+0Ch], eax
0x180027bd1  mov     rax, rdx
0x180027bd4  mov     dword ptr [rbp+var_40], 0Bh
0x180027bdb  mov     byte ptr [rbp+var_10], 1
0x180027bdf  mov     byte ptr [rbp+var_30+8], 0
0x180027be3  mov     qword ptr [rbp+var_20], 0
0x180027beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bf0  add     rsp, 60h
0x180027bf4  pop     rbp
0x180027bf5  retn
```
