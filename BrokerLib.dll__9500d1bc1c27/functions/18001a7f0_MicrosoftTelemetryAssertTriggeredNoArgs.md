# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18001a7f0`
- end: `0x18001a892`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b510`
- `0x18000bfd0`
- `0x180014a7c`
- `0x18001a584`

## callees

- `0x18001a7f0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001a811`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001a811`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a82b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a82b`

## string_xrefs

- `0x18001a805`: `ntdll.dll`

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
0x18001a7f0  push    rbp
0x18001a7f2  mov     rbp, rsp
0x18001a7f5  sub     rsp, 60h
0x18001a7f9  lea     r8, [rbp+phModule]; phModule
0x18001a7fd  mov     [rbp+phModule], 0
0x18001a805  lea     rdx, ModuleName; "ntdll.dll"
0x18001a80c  mov     ecx, 2; dwFlags
0x18001a811  call    cs:__imp_GetModuleHandleExA
0x18001a817  test    eax, eax
0x18001a819  jz      short loc_18001A88C
0x18001a81b  mov     rcx, [rbp+phModule]; hModule
0x18001a81f  test    rcx, rcx
0x18001a822  jz      short loc_18001A88C
0x18001a824  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18001a82b  call    cs:__imp_GetProcAddress
0x18001a831  mov     rdx, rax
0x18001a834  test    rax, rax
0x18001a837  jz      short loc_18001A88C
0x18001a839  xor     eax, eax
0x18001a83b  lea     rcx, [rbp+var_40]
0x18001a83f  mov     [rbp+var_10], eax
0x18001a842  xorps   xmm0, xmm0
0x18001a845  movups  [rbp+var_20], xmm0
0x18001a849  lea     rax, __ImageBase
0x18001a850  movups  [rbp+var_40], xmm0
0x18001a854  mov     qword ptr [rbp+var_40+8], rax
0x18001a858  mov     rax, [rbp+8]
0x18001a85c  movups  [rbp+var_30], xmm0
0x18001a860  mov     qword ptr [rbp+var_30], rax
0x18001a864  or      eax, 0FFFFFFFFh
0x18001a867  mov     dword ptr [rbp+var_20+8], eax
0x18001a86a  mov     dword ptr [rbp+var_20+0Ch], eax
0x18001a86d  mov     rax, rdx
0x18001a870  mov     dword ptr [rbp+var_40], 0Bh
0x18001a877  mov     byte ptr [rbp+var_10], 1
0x18001a87b  mov     byte ptr [rbp+var_30+8], 0
0x18001a87f  mov     qword ptr [rbp+var_20], 0
0x18001a887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a88c  add     rsp, 60h
0x18001a890  pop     rbp
0x18001a891  retn
```
