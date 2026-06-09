# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180027440`
- end: `0x1800274ef`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000eaac`

## callees

- `0x180027440`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180027461`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180027461`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027481`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027481`

## string_xrefs

- `0x180027455`: `ntdll.dll`

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
0x180027440  push    rbp
0x180027442  mov     rbp, rsp
0x180027445  sub     rsp, 60h
0x180027449  lea     r8, [rbp+phModule]; phModule
0x18002744d  mov     [rbp+phModule], 0
0x180027455  lea     rdx, aNtdllDll; "ntdll.dll"
0x18002745c  mov     ecx, 2; dwFlags
0x180027461  call    cs:__imp_GetModuleHandleExA
0x180027468  nop     dword ptr [rax+rax+00h]
0x18002746d  test    eax, eax
0x18002746f  jz      short loc_1800274E8
0x180027471  mov     rcx, [rbp+phModule]; hModule
0x180027475  test    rcx, rcx
0x180027478  jz      short loc_1800274E8
0x18002747a  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180027481  call    cs:__imp_GetProcAddress
0x180027488  nop     dword ptr [rax+rax+00h]
0x18002748d  mov     rdx, rax
0x180027490  test    rax, rax
0x180027493  jz      short loc_1800274E8
0x180027495  xor     eax, eax
0x180027497  lea     rcx, [rbp+var_40]
0x18002749b  mov     [rbp+var_10], eax
0x18002749e  xorps   xmm0, xmm0
0x1800274a1  movups  [rbp+var_20], xmm0
0x1800274a5  lea     rax, __ImageBase
0x1800274ac  movups  [rbp+var_40], xmm0
0x1800274b0  mov     qword ptr [rbp+var_40+8], rax
0x1800274b4  mov     rax, [rbp+8]
0x1800274b8  movups  [rbp+var_30], xmm0
0x1800274bc  mov     qword ptr [rbp+var_30], rax
0x1800274c0  or      eax, 0FFFFFFFFh
0x1800274c3  mov     dword ptr [rbp+var_20+8], eax
0x1800274c6  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800274c9  mov     rax, rdx
0x1800274cc  mov     dword ptr [rbp+var_40], 0Bh
0x1800274d3  mov     byte ptr [rbp+var_10], 1
0x1800274d7  mov     byte ptr [rbp+var_30+8], 0
0x1800274db  mov     qword ptr [rbp+var_20], 0
0x1800274e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274e8  add     rsp, 60h
0x1800274ec  pop     rbp
0x1800274ed  retn
```
