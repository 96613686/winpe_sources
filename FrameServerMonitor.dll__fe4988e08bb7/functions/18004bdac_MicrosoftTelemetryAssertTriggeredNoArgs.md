# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18004bdac`
- end: `0x18004be4e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031af0`

## callees

- `0x18004bdac`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bde7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bde7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18004bdcd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18004bdcd`

## string_xrefs

- `0x18004bdc1`: `ntdll.dll`

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
0x18004bdac  push    rbp
0x18004bdae  mov     rbp, rsp
0x18004bdb1  sub     rsp, 60h
0x18004bdb5  lea     r8, [rbp+phModule]; phModule
0x18004bdb9  mov     [rbp+phModule], 0
0x18004bdc1  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18004bdc8  mov     ecx, 2; dwFlags
0x18004bdcd  call    cs:__imp_GetModuleHandleExA
0x18004bdd3  test    eax, eax
0x18004bdd5  jz      short loc_18004BE48
0x18004bdd7  mov     rcx, [rbp+phModule]; hModule
0x18004bddb  test    rcx, rcx
0x18004bdde  jz      short loc_18004BE48
0x18004bde0  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18004bde7  call    cs:__imp_GetProcAddress
0x18004bded  mov     rdx, rax
0x18004bdf0  test    rax, rax
0x18004bdf3  jz      short loc_18004BE48
0x18004bdf5  xor     eax, eax
0x18004bdf7  lea     rcx, [rbp+var_40]
0x18004bdfb  mov     [rbp+var_10], eax
0x18004bdfe  xorps   xmm0, xmm0
0x18004be01  movups  [rbp+var_20], xmm0
0x18004be05  lea     rax, __ImageBase
0x18004be0c  movups  [rbp+var_40], xmm0
0x18004be10  mov     qword ptr [rbp+var_40+8], rax
0x18004be14  mov     rax, [rbp+8]
0x18004be18  movups  [rbp+var_30], xmm0
0x18004be1c  mov     qword ptr [rbp+var_30], rax
0x18004be20  or      eax, 0FFFFFFFFh
0x18004be23  mov     dword ptr [rbp+var_20+8], eax
0x18004be26  mov     dword ptr [rbp+var_20+0Ch], eax
0x18004be29  mov     rax, rdx
0x18004be2c  mov     dword ptr [rbp+var_40], 0Bh
0x18004be33  mov     byte ptr [rbp+var_10], 1
0x18004be37  mov     byte ptr [rbp+var_30+8], 0
0x18004be3b  mov     qword ptr [rbp+var_20], 0
0x18004be43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be48  add     rsp, 60h
0x18004be4c  pop     rbp
0x18004be4d  retn
```
