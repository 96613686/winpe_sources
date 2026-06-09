# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x140016948`
- end: `0x1400169ea`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400091f0`
- `0x14000c3e0`
- `0x140015ff8`
- `0x14001c160`
- `0x14001c274`
- `0x14001c2c8`
- `0x14001c564`

## callees

- `0x140016948`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140016983`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140016983`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExA` at `0x140016969`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExA` at `0x140016969`

## string_xrefs

- `0x14001695d`: `ntdll.dll`

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
0x140016948  push    rbp
0x14001694a  mov     rbp, rsp
0x14001694d  sub     rsp, 60h
0x140016951  lea     r8, [rbp+phModule]; phModule
0x140016955  mov     [rbp+phModule], 0
0x14001695d  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x140016964  mov     ecx, 2; dwFlags
0x140016969  call    cs:__imp_GetModuleHandleExA
0x14001696f  test    eax, eax
0x140016971  jz      short loc_1400169E4
0x140016973  mov     rcx, [rbp+phModule]; hModule
0x140016977  test    rcx, rcx
0x14001697a  jz      short loc_1400169E4
0x14001697c  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x140016983  call    cs:__imp_GetProcAddress
0x140016989  mov     rdx, rax
0x14001698c  test    rax, rax
0x14001698f  jz      short loc_1400169E4
0x140016991  xor     eax, eax
0x140016993  lea     rcx, [rbp+var_40]
0x140016997  mov     [rbp+var_10], eax
0x14001699a  xorps   xmm0, xmm0
0x14001699d  movups  [rbp+var_20], xmm0
0x1400169a1  lea     rax, cs:140000000h
0x1400169a8  movups  [rbp+var_40], xmm0
0x1400169ac  mov     qword ptr [rbp+var_40+8], rax
0x1400169b0  mov     rax, [rbp+8]
0x1400169b4  movups  [rbp+var_30], xmm0
0x1400169b8  mov     qword ptr [rbp+var_30], rax
0x1400169bc  or      eax, 0FFFFFFFFh
0x1400169bf  mov     dword ptr [rbp+var_20+8], eax
0x1400169c2  mov     dword ptr [rbp+var_20+0Ch], eax
0x1400169c5  mov     rax, rdx
0x1400169c8  mov     dword ptr [rbp+var_40], 0Bh
0x1400169cf  mov     byte ptr [rbp+var_10], 1
0x1400169d3  mov     byte ptr [rbp+var_30+8], 0
0x1400169d7  mov     qword ptr [rbp+var_20], 0
0x1400169df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400169e4  add     rsp, 60h
0x1400169e8  pop     rbp
0x1400169e9  retn
```
