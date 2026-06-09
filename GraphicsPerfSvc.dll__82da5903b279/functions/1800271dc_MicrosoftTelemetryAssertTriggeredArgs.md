# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x1800271dc`
- end: `0x180027285`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `169`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010880`
- `0x180011630`

## callees

- `0x1800271dc`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027222`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027222`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180027208`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180027208`

## string_xrefs

- `0x1800271fc`: `ntdll.dll`

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
        v9[1] = 0x180000000uLL;
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
0x1800271dc  push    rbp
0x1800271de  push    rbx
0x1800271df  push    rsi
0x1800271e0  push    rdi
0x1800271e1  mov     rbp, rsp
0x1800271e4  sub     rsp, 68h
0x1800271e8  mov     ebx, r8d
0x1800271eb  mov     [rbp+phModule], 0
0x1800271f3  mov     edi, edx
0x1800271f5  lea     r8, [rbp+phModule]; phModule
0x1800271f9  mov     rsi, rcx
0x1800271fc  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180027203  mov     ecx, 2; dwFlags
0x180027208  call    cs:__imp_GetModuleHandleExA
0x18002720e  test    eax, eax
0x180027210  jz      short loc_18002727C
0x180027212  mov     rcx, [rbp+phModule]; hModule
0x180027216  test    rcx, rcx
0x180027219  jz      short loc_18002727C
0x18002721b  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180027222  call    cs:__imp_GetProcAddress
0x180027228  mov     rdx, rax
0x18002722b  test    rax, rax
0x18002722e  jz      short loc_18002727C
0x180027230  xor     eax, eax
0x180027232  lea     rcx, [rbp+var_40]
0x180027236  mov     [rbp+var_10], eax
0x180027239  xorps   xmm0, xmm0
0x18002723c  movups  [rbp+var_20], xmm0
0x180027240  lea     rax, cs:180000000h
0x180027247  movups  [rbp+var_40], xmm0
0x18002724b  mov     qword ptr [rbp+var_40+8], rax
0x18002724f  mov     rax, [rbp+20h]
0x180027253  movups  [rbp+var_30], xmm0
0x180027257  mov     qword ptr [rbp+var_30], rax
0x18002725b  mov     rax, rdx
0x18002725e  mov     dword ptr [rbp+var_40], 0Bh
0x180027265  mov     byte ptr [rbp+var_10], 1
0x180027269  mov     byte ptr [rbp+var_30+8], 1
0x18002726d  mov     qword ptr [rbp+var_20], rsi
0x180027271  mov     dword ptr [rbp+var_20+8], edi
0x180027274  mov     dword ptr [rbp+var_20+0Ch], ebx
0x180027277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002727c  add     rsp, 68h
0x180027280  pop     rdi
0x180027281  pop     rsi
0x180027282  pop     rbx
0x180027283  pop     rbp
0x180027284  retn
```
