# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1800281fc`
- end: `0x18002829e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011dc0`
- `0x1800164e4`

## callees

- `0x1800281fc`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028237`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028237`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002821d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002821d`

## string_xrefs

- `0x180028211`: `ntdll.dll`

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
0x1800281fc  push    rbp
0x1800281fe  mov     rbp, rsp
0x180028201  sub     rsp, 60h
0x180028205  lea     r8, [rbp+phModule]; phModule
0x180028209  mov     [rbp+phModule], 0
0x180028211  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180028218  mov     ecx, 2; dwFlags
0x18002821d  call    cs:__imp_GetModuleHandleExA
0x180028223  test    eax, eax
0x180028225  jz      short loc_180028298
0x180028227  mov     rcx, [rbp+phModule]; hModule
0x18002822b  test    rcx, rcx
0x18002822e  jz      short loc_180028298
0x180028230  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180028237  call    cs:__imp_GetProcAddress
0x18002823d  mov     rdx, rax
0x180028240  test    rax, rax
0x180028243  jz      short loc_180028298
0x180028245  xor     eax, eax
0x180028247  lea     rcx, [rbp+var_40]
0x18002824b  mov     [rbp+var_10], eax
0x18002824e  xorps   xmm0, xmm0
0x180028251  movups  [rbp+var_20], xmm0
0x180028255  lea     rax, __ImageBase
0x18002825c  movups  [rbp+var_40], xmm0
0x180028260  mov     qword ptr [rbp+var_40+8], rax
0x180028264  mov     rax, [rbp+8]
0x180028268  movups  [rbp+var_30], xmm0
0x18002826c  mov     qword ptr [rbp+var_30], rax
0x180028270  or      eax, 0FFFFFFFFh
0x180028273  mov     dword ptr [rbp+var_20+8], eax
0x180028276  mov     dword ptr [rbp+var_20+0Ch], eax
0x180028279  mov     rax, rdx
0x18002827c  mov     dword ptr [rbp+var_40], 0Bh
0x180028283  mov     byte ptr [rbp+var_10], 1
0x180028287  mov     byte ptr [rbp+var_30+8], 0
0x18002828b  mov     qword ptr [rbp+var_20], 0
0x180028293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028298  add     rsp, 60h
0x18002829c  pop     rbp
0x18002829d  retn
```
