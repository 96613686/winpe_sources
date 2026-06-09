# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1800261f4`
- end: `0x180026296`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e3d0`

## callees

- `0x1800261f4`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180026215`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180026215`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002622f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002622f`

## string_xrefs

- `0x180026209`: `ntdll.dll`

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
0x1800261f4  push    rbp
0x1800261f6  mov     rbp, rsp
0x1800261f9  sub     rsp, 60h
0x1800261fd  lea     r8, [rbp+phModule]; phModule
0x180026201  mov     [rbp+phModule], 0
0x180026209  lea     rdx, aNtdllDll; "ntdll.dll"
0x180026210  mov     ecx, 2; dwFlags
0x180026215  call    cs:__imp_GetModuleHandleExA
0x18002621b  test    eax, eax
0x18002621d  jz      short loc_180026290
0x18002621f  mov     rcx, [rbp+phModule]; hModule
0x180026223  test    rcx, rcx
0x180026226  jz      short loc_180026290
0x180026228  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18002622f  call    cs:__imp_GetProcAddress
0x180026235  mov     rdx, rax
0x180026238  test    rax, rax
0x18002623b  jz      short loc_180026290
0x18002623d  xor     eax, eax
0x18002623f  lea     rcx, [rbp+var_40]
0x180026243  mov     [rbp+var_10], eax
0x180026246  xorps   xmm0, xmm0
0x180026249  movups  [rbp+var_20], xmm0
0x18002624d  lea     rax, __ImageBase
0x180026254  movups  [rbp+var_40], xmm0
0x180026258  mov     qword ptr [rbp+var_40+8], rax
0x18002625c  mov     rax, [rbp+8]
0x180026260  movups  [rbp+var_30], xmm0
0x180026264  mov     qword ptr [rbp+var_30], rax
0x180026268  or      eax, 0FFFFFFFFh
0x18002626b  mov     dword ptr [rbp+var_20+8], eax
0x18002626e  mov     dword ptr [rbp+var_20+0Ch], eax
0x180026271  mov     rax, rdx
0x180026274  mov     dword ptr [rbp+var_40], 0Bh
0x18002627b  mov     byte ptr [rbp+var_10], 1
0x18002627f  mov     byte ptr [rbp+var_30+8], 0
0x180026283  mov     qword ptr [rbp+var_20], 0
0x18002628b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026290  add     rsp, 60h
0x180026294  pop     rbp
0x180026295  retn
```
