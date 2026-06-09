# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1800116f4`
- end: `0x180011796`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b580`

## callees

- `0x1800116f4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180011715`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180011715`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001172f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001172f`

## string_xrefs

- `0x180011709`: `ntdll.dll`

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
0x1800116f4  push    rbp
0x1800116f6  mov     rbp, rsp
0x1800116f9  sub     rsp, 60h
0x1800116fd  lea     r8, [rbp+phModule]; phModule
0x180011701  mov     [rbp+phModule], 0
0x180011709  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180011710  mov     ecx, 2; dwFlags
0x180011715  call    cs:__imp_GetModuleHandleExA
0x18001171b  test    eax, eax
0x18001171d  jz      short loc_180011790
0x18001171f  mov     rcx, [rbp+phModule]; hModule
0x180011723  test    rcx, rcx
0x180011726  jz      short loc_180011790
0x180011728  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18001172f  call    cs:__imp_GetProcAddress
0x180011735  mov     rdx, rax
0x180011738  test    rax, rax
0x18001173b  jz      short loc_180011790
0x18001173d  xor     eax, eax
0x18001173f  lea     rcx, [rbp+var_40]
0x180011743  mov     [rbp+var_10], eax
0x180011746  xorps   xmm0, xmm0
0x180011749  movups  [rbp+var_20], xmm0
0x18001174d  lea     rax, __ImageBase
0x180011754  movups  [rbp+var_40], xmm0
0x180011758  mov     qword ptr [rbp+var_40+8], rax
0x18001175c  mov     rax, [rbp+8]
0x180011760  movups  [rbp+var_30], xmm0
0x180011764  mov     qword ptr [rbp+var_30], rax
0x180011768  or      eax, 0FFFFFFFFh
0x18001176b  mov     dword ptr [rbp+var_20+8], eax
0x18001176e  mov     dword ptr [rbp+var_20+0Ch], eax
0x180011771  mov     rax, rdx
0x180011774  mov     dword ptr [rbp+var_40], 0Bh
0x18001177b  mov     byte ptr [rbp+var_10], 1
0x18001177f  mov     byte ptr [rbp+var_30+8], 0
0x180011783  mov     qword ptr [rbp+var_20], 0
0x18001178b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011790  add     rsp, 60h
0x180011794  pop     rbp
0x180011795  retn
```
