# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180021d6c`
- end: `0x180021e0e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800102cc`
- `0x180015d50`
- `0x180017f70`
- `0x18001eb38`

## callees

- `0x180021d6c`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180021d8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180021d8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021da7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021da7`

## string_xrefs

- `0x180021d81`: `ntdll.dll`

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
0x180021d6c  push    rbp
0x180021d6e  mov     rbp, rsp
0x180021d71  sub     rsp, 60h
0x180021d75  lea     r8, [rbp+phModule]; phModule
0x180021d79  mov     [rbp+phModule], 0
0x180021d81  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180021d88  mov     ecx, 2; dwFlags
0x180021d8d  call    cs:__imp_GetModuleHandleExA
0x180021d93  test    eax, eax
0x180021d95  jz      short loc_180021E08
0x180021d97  mov     rcx, [rbp+phModule]; hModule
0x180021d9b  test    rcx, rcx
0x180021d9e  jz      short loc_180021E08
0x180021da0  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180021da7  call    cs:__imp_GetProcAddress
0x180021dad  mov     rdx, rax
0x180021db0  test    rax, rax
0x180021db3  jz      short loc_180021E08
0x180021db5  xor     eax, eax
0x180021db7  lea     rcx, [rbp+var_40]
0x180021dbb  mov     [rbp+var_10], eax
0x180021dbe  xorps   xmm0, xmm0
0x180021dc1  movups  [rbp+var_20], xmm0
0x180021dc5  lea     rax, __ImageBase
0x180021dcc  movups  [rbp+var_40], xmm0
0x180021dd0  mov     qword ptr [rbp+var_40+8], rax
0x180021dd4  mov     rax, [rbp+8]
0x180021dd8  movups  [rbp+var_30], xmm0
0x180021ddc  mov     qword ptr [rbp+var_30], rax
0x180021de0  or      eax, 0FFFFFFFFh
0x180021de3  mov     dword ptr [rbp+var_20+8], eax
0x180021de6  mov     dword ptr [rbp+var_20+0Ch], eax
0x180021de9  mov     rax, rdx
0x180021dec  mov     dword ptr [rbp+var_40], 0Bh
0x180021df3  mov     byte ptr [rbp+var_10], 1
0x180021df7  mov     byte ptr [rbp+var_30+8], 0
0x180021dfb  mov     qword ptr [rbp+var_20], 0
0x180021e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e08  add     rsp, 60h
0x180021e0c  pop     rbp
0x180021e0d  retn
```
