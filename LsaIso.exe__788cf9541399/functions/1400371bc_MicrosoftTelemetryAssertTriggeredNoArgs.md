# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1400371bc`
- end: `0x14003725e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400180d0`
- `0x140019210`
- `0x14001a2b0`
- `0x14001a4a0`

## callees

- `0x1400371bc`
- `0x14003a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400371f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400371f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1400371dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1400371dd`

## string_xrefs

- `0x1400371d1`: `ntdll.dll`

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
        v2[1] = 0x140000000uLL;
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
0x1400371bc  push    rbp
0x1400371be  mov     rbp, rsp
0x1400371c1  sub     rsp, 60h
0x1400371c5  lea     r8, [rbp+phModule]; phModule
0x1400371c9  mov     [rbp+phModule], 0
0x1400371d1  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1400371d8  mov     ecx, 2; dwFlags
0x1400371dd  call    cs:__imp_GetModuleHandleExA
0x1400371e3  test    eax, eax
0x1400371e5  jz      short loc_140037258
0x1400371e7  mov     rcx, [rbp+phModule]; hModule
0x1400371eb  test    rcx, rcx
0x1400371ee  jz      short loc_140037258
0x1400371f0  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1400371f7  call    cs:__imp_GetProcAddress
0x1400371fd  mov     rdx, rax
0x140037200  test    rax, rax
0x140037203  jz      short loc_140037258
0x140037205  xor     eax, eax
0x140037207  lea     rcx, [rbp+var_40]
0x14003720b  mov     [rbp+var_10], eax
0x14003720e  xorps   xmm0, xmm0
0x140037211  movups  [rbp+var_20], xmm0
0x140037215  lea     rax, cs:140000000h
0x14003721c  movups  [rbp+var_40], xmm0
0x140037220  mov     qword ptr [rbp+var_40+8], rax
0x140037224  mov     rax, [rbp+8]
0x140037228  movups  [rbp+var_30], xmm0
0x14003722c  mov     qword ptr [rbp+var_30], rax
0x140037230  or      eax, 0FFFFFFFFh
0x140037233  mov     dword ptr [rbp+var_20+8], eax
0x140037236  mov     dword ptr [rbp+var_20+0Ch], eax
0x140037239  mov     rax, rdx
0x14003723c  mov     dword ptr [rbp+var_40], 0Bh
0x140037243  mov     byte ptr [rbp+var_10], 1
0x140037247  mov     byte ptr [rbp+var_30+8], 0
0x14003724b  mov     qword ptr [rbp+var_20], 0
0x140037253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037258  add     rsp, 60h
0x14003725c  pop     rbp
0x14003725d  retn
```
