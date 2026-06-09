# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180024718`
- end: `0x1800247ba`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014c90`

## callees

- `0x180024718`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180024739`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180024739`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024753`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024753`

## string_xrefs

- `0x18002472d`: `ntdll.dll`

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
0x180024718  push    rbp
0x18002471a  mov     rbp, rsp
0x18002471d  sub     rsp, 60h
0x180024721  lea     r8, [rbp+phModule]; phModule
0x180024725  mov     [rbp+phModule], 0
0x18002472d  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180024734  mov     ecx, 2; dwFlags
0x180024739  call    cs:__imp_GetModuleHandleExA
0x18002473f  test    eax, eax
0x180024741  jz      short loc_1800247B4
0x180024743  mov     rcx, [rbp+phModule]; hModule
0x180024747  test    rcx, rcx
0x18002474a  jz      short loc_1800247B4
0x18002474c  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180024753  call    cs:__imp_GetProcAddress
0x180024759  mov     rdx, rax
0x18002475c  test    rax, rax
0x18002475f  jz      short loc_1800247B4
0x180024761  xor     eax, eax
0x180024763  lea     rcx, [rbp+var_40]
0x180024767  mov     [rbp+var_10], eax
0x18002476a  xorps   xmm0, xmm0
0x18002476d  movups  [rbp+var_20], xmm0
0x180024771  lea     rax, __ImageBase
0x180024778  movups  [rbp+var_40], xmm0
0x18002477c  mov     qword ptr [rbp+var_40+8], rax
0x180024780  mov     rax, [rbp+8]
0x180024784  movups  [rbp+var_30], xmm0
0x180024788  mov     qword ptr [rbp+var_30], rax
0x18002478c  or      eax, 0FFFFFFFFh
0x18002478f  mov     dword ptr [rbp+var_20+8], eax
0x180024792  mov     dword ptr [rbp+var_20+0Ch], eax
0x180024795  mov     rax, rdx
0x180024798  mov     dword ptr [rbp+var_40], 0Bh
0x18002479f  mov     byte ptr [rbp+var_10], 1
0x1800247a3  mov     byte ptr [rbp+var_30+8], 0
0x1800247a7  mov     qword ptr [rbp+var_20], 0
0x1800247af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247b4  add     rsp, 60h
0x1800247b8  pop     rbp
0x1800247b9  retn
```
