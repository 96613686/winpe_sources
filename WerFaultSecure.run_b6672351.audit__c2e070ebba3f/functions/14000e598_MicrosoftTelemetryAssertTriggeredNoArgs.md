# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x14000e598`
- end: `0x14000e63a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400051b8`
- `0x140005210`
- `0x140005590`
- `0x140006428`
- `0x140006ba0`
- `0x140007a4c`
- `0x14000e8c4`
- `0x14000f4b0`
- `0x14000f680`
- `0x14000f81c`
- `0x14000fb3c`
- `0x1400106cc`
- `0x140010880`
- `0x140010bd0`

## callees

- `0x14000e598`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e5d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e5d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x14000e5b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x14000e5b9`

## string_xrefs

- `0x14000e5ad`: `ntdll.dll`

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
0x14000e598  push    rbp
0x14000e59a  mov     rbp, rsp
0x14000e59d  sub     rsp, 60h
0x14000e5a1  lea     r8, [rbp+phModule]; phModule
0x14000e5a5  mov     [rbp+phModule], 0
0x14000e5ad  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x14000e5b4  mov     ecx, 2; dwFlags
0x14000e5b9  call    cs:__imp_GetModuleHandleExA
0x14000e5bf  test    eax, eax
0x14000e5c1  jz      short loc_14000E634
0x14000e5c3  mov     rcx, [rbp+phModule]; hModule
0x14000e5c7  test    rcx, rcx
0x14000e5ca  jz      short loc_14000E634
0x14000e5cc  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x14000e5d3  call    cs:__imp_GetProcAddress
0x14000e5d9  mov     rdx, rax
0x14000e5dc  test    rax, rax
0x14000e5df  jz      short loc_14000E634
0x14000e5e1  xor     eax, eax
0x14000e5e3  lea     rcx, [rbp+var_40]
0x14000e5e7  mov     [rbp+var_10], eax
0x14000e5ea  xorps   xmm0, xmm0
0x14000e5ed  movups  [rbp+var_20], xmm0
0x14000e5f1  lea     rax, __ImageBase
0x14000e5f8  movups  [rbp+var_40], xmm0
0x14000e5fc  mov     qword ptr [rbp+var_40+8], rax
0x14000e600  mov     rax, [rbp+8]
0x14000e604  movups  [rbp+var_30], xmm0
0x14000e608  mov     qword ptr [rbp+var_30], rax
0x14000e60c  or      eax, 0FFFFFFFFh
0x14000e60f  mov     dword ptr [rbp+var_20+8], eax
0x14000e612  mov     dword ptr [rbp+var_20+0Ch], eax
0x14000e615  mov     rax, rdx
0x14000e618  mov     dword ptr [rbp+var_40], 0Bh
0x14000e61f  mov     byte ptr [rbp+var_10], 1
0x14000e623  mov     byte ptr [rbp+var_30+8], 0
0x14000e627  mov     qword ptr [rbp+var_20], 0
0x14000e62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e634  add     rsp, 60h
0x14000e638  pop     rbp
0x14000e639  retn
```
