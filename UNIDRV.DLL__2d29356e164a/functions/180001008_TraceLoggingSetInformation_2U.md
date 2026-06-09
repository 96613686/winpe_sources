# TraceLoggingSetInformation_2U

- ea: `0x180001008`
- end: `0x1800010a8`
- name: `TraceLoggingSetInformation_2U`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003f114`

## callees

- `0x180001008`
- `0x180075010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000108a`
- `KERNEL32!FreeLibrary` at `0x18000108a`
- `KERNEL32!GetProcAddress` at `0x180001064`
- `KERNEL32!GetProcAddress` at `0x180001064`
- `KERNEL32!GetModuleHandleExW` at `0x180001036`
- `KERNEL32!GetModuleHandleExW` at `0x18000104e`
- `KERNEL32!GetModuleHandleExW` at `0x180001036`
- `KERNEL32!GetModuleHandleExW` at `0x18000104e`

## string_xrefs

- `0x180001047`: `advapi32.dll`
- `0x180001027`: `api-ms-win-eventing-provider-l1-1-0.dll`

## pseudocode

```c
__int64 __fastcall TraceLoggingSetInformation_2U(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v7; // ebx
  FARPROC ProcAddress; // rax
  HMODULE phModule[7]; // [rsp+30h] [rbp-38h] BYREF

  phModule[0] = 0;
  v7 = 50;
  if ( !GetModuleHandleExW(0, L"api-ms-win-eventing-provider-l1-1-0.dll", phModule)
    && !GetModuleHandleExW(0, L"advapi32.dll", phModule) )
  {
    return (unsigned __int16)v7 | 0x80070000;
  }
  ProcAddress = GetProcAddress(phModule[0], "EventSetInformation");
  if ( ProcAddress )
    v7 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _QWORD))ProcAddress)(*(_QWORD *)(a1 + 32), 2, a3, a4);
  FreeLibrary(phModule[0]);
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180001008  push    rbx
0x18000100a  push    rbp
0x18000100b  push    rsi
0x18000100c  push    rdi
0x18000100d  sub     rsp, 48h
0x180001011  mov     rsi, r8
0x180001014  mov     [rsp+68h+phModule], 0
0x18000101d  mov     rbp, rcx
0x180001020  lea     r8, [rsp+68h+phModule]; phModule
0x180001025  xor     ecx, ecx; dwFlags
0x180001027  lea     rdx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x18000102e  mov     edi, r9d
0x180001031  mov     ebx, 32h ; '2'
0x180001036  call    cs:__imp_GetModuleHandleExW
0x18000103c  test    eax, eax
0x18000103e  jnz     short loc_180001058
0x180001040  lea     r8, [rsp+68h+phModule]; phModule
0x180001045  xor     ecx, ecx; dwFlags
0x180001047  lea     rdx, aAdvapi32Dll_0; "advapi32.dll"
0x18000104e  call    cs:__imp_GetModuleHandleExW
0x180001054  test    eax, eax
0x180001056  jz      short loc_180001094
0x180001058  mov     rcx, [rsp+68h+phModule]; hModule
0x18000105d  lea     rdx, ProcName; "EventSetInformation"
0x180001064  call    cs:__imp_GetProcAddress
0x18000106a  test    rax, rax
0x18000106d  jz      short loc_180001085
0x18000106f  mov     rcx, [rbp+20h]
0x180001073  mov     r9d, edi
0x180001076  mov     r8, rsi
0x180001079  mov     edx, 2
0x18000107e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001083  mov     ebx, eax
0x180001085  mov     rcx, [rsp+68h+phModule]; hLibModule
0x18000108a  call    cs:__imp_FreeLibrary
0x180001090  test    ebx, ebx
0x180001092  jle     short loc_18000109D
0x180001094  movzx   ebx, bx
0x180001097  or      ebx, 80070000h
0x18000109d  mov     eax, ebx
0x18000109f  add     rsp, 48h
0x1800010a3  pop     rdi
0x1800010a4  pop     rsi
0x1800010a5  pop     rbp
0x1800010a6  pop     rbx
0x1800010a7  retn
```
