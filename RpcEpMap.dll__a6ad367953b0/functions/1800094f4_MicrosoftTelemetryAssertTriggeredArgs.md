# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x1800094f4`
- end: `0x1800095aa`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `182`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006758`

## callees

- `0x1800094f4`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000953a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000953a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180009520`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180009520`

## string_xrefs

- `0x180009573`: `rpcepmap.dll`
- `0x180009510`: `ntdll.dll`

## pseudocode

```c
int __fastcall MicrosoftTelemetryAssertTriggeredArgs(__int64 a1, unsigned int a2)
{
  FARPROC ProcAddress; // rax
  _QWORD v5[6]; // [rsp+20h] [rbp-40h] BYREF
  int v6; // [rsp+50h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+8h]
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
        v5[1] = &_ImageBase;
        v5[3] = 1;
        v5[2] = retaddr;
        v5[4] = "rpcepmap.dll";
        v5[0] = 11;
        v5[5] = a2;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v5);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x1800094f4  mov     [rsp-8+arg_8], rbx
0x1800094f9  mov     [rsp-8+phModule], rcx
0x1800094fe  push    rbp
0x1800094ff  mov     rbp, rsp
0x180009502  sub     rsp, 60h
0x180009506  mov     ebx, edx
0x180009508  mov     [rbp+phModule], 0
0x180009510  lea     rdx, ModuleName; "ntdll.dll"
0x180009517  mov     ecx, 2; dwFlags
0x18000951c  lea     r8, [rbp+phModule]; phModule
0x180009520  call    cs:__imp_GetModuleHandleExA
0x180009526  test    eax, eax
0x180009528  jz      short loc_18000959F
0x18000952a  mov     rcx, [rbp+phModule]; hModule
0x18000952e  test    rcx, rcx
0x180009531  jz      short loc_18000959F
0x180009533  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000953a  call    cs:__imp_GetProcAddress
0x180009540  mov     rdx, rax
0x180009543  test    rax, rax
0x180009546  jz      short loc_18000959F
0x180009548  xor     eax, eax
0x18000954a  lea     rcx, [rbp+var_40]
0x18000954e  mov     [rbp+var_10], eax
0x180009551  xorps   xmm0, xmm0
0x180009554  movups  [rbp+var_20], xmm0
0x180009558  lea     rax, __ImageBase
0x18000955f  movups  [rbp+var_40], xmm0
0x180009563  mov     qword ptr [rbp+var_40+8], rax
0x180009567  mov     rax, [rbp+8]
0x18000956b  movups  [rbp+var_30], xmm0
0x18000956f  mov     qword ptr [rbp+var_30], rax
0x180009573  lea     rax, aRpcepmapDll; "rpcepmap.dll"
0x18000957a  mov     qword ptr [rbp+var_20], rax
0x18000957e  mov     rax, rdx
0x180009581  mov     dword ptr [rbp+var_40], 0Bh
0x180009588  mov     byte ptr [rbp+var_10], 1
0x18000958c  mov     byte ptr [rbp+var_30+8], 1
0x180009590  mov     dword ptr [rbp+var_20+8], ebx
0x180009593  mov     dword ptr [rbp+var_20+0Ch], 0
0x18000959a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000959f  mov     rbx, [rsp+60h+arg_8]
0x1800095a4  add     rsp, 60h
0x1800095a8  pop     rbp
0x1800095a9  retn
```
