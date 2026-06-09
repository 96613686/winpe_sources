# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000b204`
- end: `0x18000b2a6`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009110`

## callees

- `0x18000b204`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b23f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b23f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000b225`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000b225`

## string_xrefs

- `0x18000b219`: `ntdll.dll`

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
0x18000b204  push    rbp
0x18000b206  mov     rbp, rsp
0x18000b209  sub     rsp, 60h
0x18000b20d  lea     r8, [rbp+phModule]; phModule
0x18000b211  mov     [rbp+phModule], 0
0x18000b219  lea     rdx, aNtdllDll; "ntdll.dll"
0x18000b220  mov     ecx, 2; dwFlags
0x18000b225  call    cs:__imp_GetModuleHandleExA
0x18000b22b  test    eax, eax
0x18000b22d  jz      short loc_18000B2A0
0x18000b22f  mov     rcx, [rbp+phModule]; hModule
0x18000b233  test    rcx, rcx
0x18000b236  jz      short loc_18000B2A0
0x18000b238  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000b23f  call    cs:__imp_GetProcAddress
0x18000b245  mov     rdx, rax
0x18000b248  test    rax, rax
0x18000b24b  jz      short loc_18000B2A0
0x18000b24d  xor     eax, eax
0x18000b24f  lea     rcx, [rbp+var_40]
0x18000b253  mov     [rbp+var_10], eax
0x18000b256  xorps   xmm0, xmm0
0x18000b259  movups  [rbp+var_20], xmm0
0x18000b25d  lea     rax, __ImageBase
0x18000b264  movups  [rbp+var_40], xmm0
0x18000b268  mov     qword ptr [rbp+var_40+8], rax
0x18000b26c  mov     rax, [rbp+8]
0x18000b270  movups  [rbp+var_30], xmm0
0x18000b274  mov     qword ptr [rbp+var_30], rax
0x18000b278  or      eax, 0FFFFFFFFh
0x18000b27b  mov     dword ptr [rbp+var_20+8], eax
0x18000b27e  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000b281  mov     rax, rdx
0x18000b284  mov     dword ptr [rbp+var_40], 0Bh
0x18000b28b  mov     byte ptr [rbp+var_10], 1
0x18000b28f  mov     byte ptr [rbp+var_30+8], 0
0x18000b293  mov     qword ptr [rbp+var_20], 0
0x18000b29b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2a0  add     rsp, 60h
0x18000b2a4  pop     rbp
0x18000b2a5  retn
```
