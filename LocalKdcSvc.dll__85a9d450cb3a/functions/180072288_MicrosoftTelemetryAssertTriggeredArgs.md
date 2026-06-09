# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x180072288`
- end: `0x180072331`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `169`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bf18`
- `0x180028d24`
- `0x180036d70`
- `0x180060c24`
- `0x18006e1e8`

## callees

- `0x180072288`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800722ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800722ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800722b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800722b4`

## string_xrefs

- `0x1800722a8`: `ntdll.dll`

## pseudocode

```c
int __fastcall MicrosoftTelemetryAssertTriggeredArgs(__int64 a1, int a2, int a3)
{
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v9[5]; // [rsp+28h] [rbp-40h] BYREF
  int v10; // [rsp+50h] [rbp-18h]
  int v11; // [rsp+54h] [rbp-14h]
  int v12; // [rsp+58h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+20h]

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExA(2u, "ntdll.dll", &phModule);
  if ( (_DWORD)ProcAddress )
  {
    if ( phModule )
    {
      ProcAddress = GetProcAddress(phModule, "MicrosoftTelemetryAssertTriggeredUM");
      if ( ProcAddress )
      {
        v12 = 1;
        v9[1] = &_ImageBase;
        v9[3] = 1;
        v9[2] = retaddr;
        v9[0] = 11;
        v9[4] = a1;
        v10 = a2;
        v11 = a3;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v9);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x180072288  push    rbp
0x18007228a  push    rbx
0x18007228b  push    rsi
0x18007228c  push    rdi
0x18007228d  mov     rbp, rsp
0x180072290  sub     rsp, 68h
0x180072294  mov     ebx, r8d
0x180072297  mov     [rbp+phModule], 0
0x18007229f  mov     edi, edx
0x1800722a1  lea     r8, [rbp+phModule]; phModule
0x1800722a5  mov     rsi, rcx
0x1800722a8  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800722af  mov     ecx, 2; dwFlags
0x1800722b4  call    cs:__imp_GetModuleHandleExA
0x1800722ba  test    eax, eax
0x1800722bc  jz      short loc_180072328
0x1800722be  mov     rcx, [rbp+phModule]; hModule
0x1800722c2  test    rcx, rcx
0x1800722c5  jz      short loc_180072328
0x1800722c7  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800722ce  call    cs:__imp_GetProcAddress
0x1800722d4  mov     rdx, rax
0x1800722d7  test    rax, rax
0x1800722da  jz      short loc_180072328
0x1800722dc  xor     eax, eax
0x1800722de  lea     rcx, [rbp+var_40]
0x1800722e2  mov     [rbp+var_10], eax
0x1800722e5  xorps   xmm0, xmm0
0x1800722e8  movups  [rbp+var_20], xmm0
0x1800722ec  lea     rax, __ImageBase
0x1800722f3  movups  [rbp+var_40], xmm0
0x1800722f7  mov     qword ptr [rbp+var_40+8], rax
0x1800722fb  mov     rax, [rbp+20h]
0x1800722ff  movups  [rbp+var_30], xmm0
0x180072303  mov     qword ptr [rbp+var_30], rax
0x180072307  mov     rax, rdx
0x18007230a  mov     dword ptr [rbp+var_40], 0Bh
0x180072311  mov     byte ptr [rbp+var_10], 1
0x180072315  mov     byte ptr [rbp+var_30+8], 1
0x180072319  mov     qword ptr [rbp+var_20], rsi
0x18007231d  mov     dword ptr [rbp+var_20+8], edi
0x180072320  mov     dword ptr [rbp+var_20+0Ch], ebx
0x180072323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072328  add     rsp, 68h
0x18007232c  pop     rdi
0x18007232d  pop     rsi
0x18007232e  pop     rbx
0x18007232f  pop     rbp
0x180072330  retn
```
