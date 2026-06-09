# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180072338`
- end: `0x1800723da`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `34`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bf18`
- `0x18001c944`
- `0x18001e930`
- `0x180021eb4`
- `0x180024ffc`
- `0x180027220`
- `0x180027e50`
- `0x180027eb8`
- `0x180029844`
- `0x18002b668`
- `0x18002b910`
- `0x180035ec8`
- `0x1800375bc`
- `0x1800485e4`
- `0x18004a000`
- `0x18004fdb0`
- `0x180050e78`
- `0x180054b24`
- `0x180057df0`
- `0x18005a5fc`
- `0x18005bbdc`
- `0x18005e9ac`
- `0x18005f318`
- `0x180061bbc`
- `0x18006349c`
- `0x1800635a8`
- `0x18006a7fc`
- `0x18006ad68`
- `0x18006afcc`
- `0x18006b520`
- `0x18006b57c`
- `0x18006d2e0`
- `0x18006e1e8`
- `0x18007869c`

## callees

- `0x180072338`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180072373`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180072373`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180072359`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180072359`

## string_xrefs

- `0x18007234d`: `ntdll.dll`

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
0x180072338  push    rbp
0x18007233a  mov     rbp, rsp
0x18007233d  sub     rsp, 60h
0x180072341  lea     r8, [rbp+phModule]; phModule
0x180072345  mov     [rbp+phModule], 0
0x18007234d  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180072354  mov     ecx, 2; dwFlags
0x180072359  call    cs:__imp_GetModuleHandleExA
0x18007235f  test    eax, eax
0x180072361  jz      short loc_1800723D4
0x180072363  mov     rcx, [rbp+phModule]; hModule
0x180072367  test    rcx, rcx
0x18007236a  jz      short loc_1800723D4
0x18007236c  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180072373  call    cs:__imp_GetProcAddress
0x180072379  mov     rdx, rax
0x18007237c  test    rax, rax
0x18007237f  jz      short loc_1800723D4
0x180072381  xor     eax, eax
0x180072383  lea     rcx, [rbp+var_40]
0x180072387  mov     [rbp+var_10], eax
0x18007238a  xorps   xmm0, xmm0
0x18007238d  movups  [rbp+var_20], xmm0
0x180072391  lea     rax, __ImageBase
0x180072398  movups  [rbp+var_40], xmm0
0x18007239c  mov     qword ptr [rbp+var_40+8], rax
0x1800723a0  mov     rax, [rbp+8]
0x1800723a4  movups  [rbp+var_30], xmm0
0x1800723a8  mov     qword ptr [rbp+var_30], rax
0x1800723ac  or      eax, 0FFFFFFFFh
0x1800723af  mov     dword ptr [rbp+var_20+8], eax
0x1800723b2  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800723b5  mov     rax, rdx
0x1800723b8  mov     dword ptr [rbp+var_40], 0Bh
0x1800723bf  mov     byte ptr [rbp+var_10], 1
0x1800723c3  mov     byte ptr [rbp+var_30+8], 0
0x1800723c7  mov     qword ptr [rbp+var_20], 0
0x1800723cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800723d4  add     rsp, 60h
0x1800723d8  pop     rbp
0x1800723d9  retn
```
