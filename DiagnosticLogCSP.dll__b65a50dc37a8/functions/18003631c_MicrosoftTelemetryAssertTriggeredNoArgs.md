# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18003631c`
- end: `0x1800363cb`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014d10`

## callees

- `0x18003631c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18003633d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18003633d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003635d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003635d`

## string_xrefs

- `0x180036331`: `ntdll.dll`

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
0x18003631c  push    rbp
0x18003631e  mov     rbp, rsp
0x180036321  sub     rsp, 60h
0x180036325  lea     r8, [rbp+phModule]; phModule
0x180036329  mov     [rbp+phModule], 0
0x180036331  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180036338  mov     ecx, 2; dwFlags
0x18003633d  call    cs:__imp_GetModuleHandleExA
0x180036344  nop     dword ptr [rax+rax+00h]
0x180036349  test    eax, eax
0x18003634b  jz      short loc_1800363C4
0x18003634d  mov     rcx, [rbp+phModule]; hModule
0x180036351  test    rcx, rcx
0x180036354  jz      short loc_1800363C4
0x180036356  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18003635d  call    cs:__imp_GetProcAddress
0x180036364  nop     dword ptr [rax+rax+00h]
0x180036369  mov     rdx, rax
0x18003636c  test    rax, rax
0x18003636f  jz      short loc_1800363C4
0x180036371  xor     eax, eax
0x180036373  lea     rcx, [rbp+var_40]
0x180036377  mov     [rbp+var_10], eax
0x18003637a  xorps   xmm0, xmm0
0x18003637d  movups  [rbp+var_20], xmm0
0x180036381  lea     rax, __ImageBase
0x180036388  movups  [rbp+var_40], xmm0
0x18003638c  mov     qword ptr [rbp+var_40+8], rax
0x180036390  mov     rax, [rbp+8]
0x180036394  movups  [rbp+var_30], xmm0
0x180036398  mov     qword ptr [rbp+var_30], rax
0x18003639c  or      eax, 0FFFFFFFFh
0x18003639f  mov     dword ptr [rbp+var_20+8], eax
0x1800363a2  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800363a5  mov     rax, rdx
0x1800363a8  mov     dword ptr [rbp+var_40], 0Bh
0x1800363af  mov     byte ptr [rbp+var_10], 1
0x1800363b3  mov     byte ptr [rbp+var_30+8], 0
0x1800363b7  mov     qword ptr [rbp+var_20], 0
0x1800363bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363c4  add     rsp, 60h
0x1800363c8  pop     rbp
0x1800363c9  retn
```
