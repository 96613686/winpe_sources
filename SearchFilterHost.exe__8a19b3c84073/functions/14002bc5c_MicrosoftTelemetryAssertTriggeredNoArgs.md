# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x14002bc5c`
- end: `0x14002bcfe`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400294e4`
- `0x14002a98c`

## callees

- `0x14002bc5c`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x14002bc7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x14002bc7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002bc97`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002bc97`

## string_xrefs

- `0x14002bc71`: `ntdll.dll`

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
0x14002bc5c  push    rbp
0x14002bc5e  mov     rbp, rsp
0x14002bc61  sub     rsp, 60h
0x14002bc65  lea     r8, [rbp+phModule]; phModule
0x14002bc69  mov     [rbp+phModule], 0
0x14002bc71  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x14002bc78  mov     ecx, 2; dwFlags
0x14002bc7d  call    cs:__imp_GetModuleHandleExA
0x14002bc83  test    eax, eax
0x14002bc85  jz      short loc_14002BCF8
0x14002bc87  mov     rcx, [rbp+phModule]; hModule
0x14002bc8b  test    rcx, rcx
0x14002bc8e  jz      short loc_14002BCF8
0x14002bc90  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x14002bc97  call    cs:__imp_GetProcAddress
0x14002bc9d  mov     rdx, rax
0x14002bca0  test    rax, rax
0x14002bca3  jz      short loc_14002BCF8
0x14002bca5  xor     eax, eax
0x14002bca7  lea     rcx, [rbp+var_40]
0x14002bcab  mov     [rbp+var_10], eax
0x14002bcae  xorps   xmm0, xmm0
0x14002bcb1  movups  [rbp+var_20], xmm0
0x14002bcb5  lea     rax, __ImageBase
0x14002bcbc  movups  [rbp+var_40], xmm0
0x14002bcc0  mov     qword ptr [rbp+var_40+8], rax
0x14002bcc4  mov     rax, [rbp+8]
0x14002bcc8  movups  [rbp+var_30], xmm0
0x14002bccc  mov     qword ptr [rbp+var_30], rax
0x14002bcd0  or      eax, 0FFFFFFFFh
0x14002bcd3  mov     dword ptr [rbp+var_20+8], eax
0x14002bcd6  mov     dword ptr [rbp+var_20+0Ch], eax
0x14002bcd9  mov     rax, rdx
0x14002bcdc  mov     dword ptr [rbp+var_40], 0Bh
0x14002bce3  mov     byte ptr [rbp+var_10], 1
0x14002bce7  mov     byte ptr [rbp+var_30+8], 0
0x14002bceb  mov     qword ptr [rbp+var_20], 0
0x14002bcf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bcf8  add     rsp, 60h
0x14002bcfc  pop     rbp
0x14002bcfd  retn
```
