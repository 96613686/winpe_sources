# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180025ecc`
- end: `0x180025f6e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dc20`
- `0x18000de90`
- `0x18001a02c`
- `0x18001a6ac`
- `0x18001f9f0`
- `0x180020ec0`

## callees

- `0x180025ecc`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025f07`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025f07`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180025eed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180025eed`

## string_xrefs

- `0x180025ee1`: `ntdll.dll`

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
0x180025ecc  push    rbp
0x180025ece  mov     rbp, rsp
0x180025ed1  sub     rsp, 60h
0x180025ed5  lea     r8, [rbp+phModule]; phModule
0x180025ed9  mov     [rbp+phModule], 0
0x180025ee1  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180025ee8  mov     ecx, 2; dwFlags
0x180025eed  call    cs:__imp_GetModuleHandleExA
0x180025ef3  test    eax, eax
0x180025ef5  jz      short loc_180025F68
0x180025ef7  mov     rcx, [rbp+phModule]; hModule
0x180025efb  test    rcx, rcx
0x180025efe  jz      short loc_180025F68
0x180025f00  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x180025f07  call    cs:__imp_GetProcAddress
0x180025f0d  mov     rdx, rax
0x180025f10  test    rax, rax
0x180025f13  jz      short loc_180025F68
0x180025f15  xor     eax, eax
0x180025f17  lea     rcx, [rbp+var_40]
0x180025f1b  mov     [rbp+var_10], eax
0x180025f1e  xorps   xmm0, xmm0
0x180025f21  movups  [rbp+var_20], xmm0
0x180025f25  lea     rax, __ImageBase
0x180025f2c  movups  [rbp+var_40], xmm0
0x180025f30  mov     qword ptr [rbp+var_40+8], rax
0x180025f34  mov     rax, [rbp+8]
0x180025f38  movups  [rbp+var_30], xmm0
0x180025f3c  mov     qword ptr [rbp+var_30], rax
0x180025f40  or      eax, 0FFFFFFFFh
0x180025f43  mov     dword ptr [rbp+var_20+8], eax
0x180025f46  mov     dword ptr [rbp+var_20+0Ch], eax
0x180025f49  mov     rax, rdx
0x180025f4c  mov     dword ptr [rbp+var_40], 0Bh
0x180025f53  mov     byte ptr [rbp+var_10], 1
0x180025f57  mov     byte ptr [rbp+var_30+8], 0
0x180025f5b  mov     qword ptr [rbp+var_20], 0
0x180025f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f68  add     rsp, 60h
0x180025f6c  pop     rbp
0x180025f6d  retn
```
