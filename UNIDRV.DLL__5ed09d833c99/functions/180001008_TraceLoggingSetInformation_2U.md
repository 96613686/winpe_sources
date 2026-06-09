# TraceLoggingSetInformation_2U

- ea: `0x180001008`
- end: `0x1800010c1`
- name: `TraceLoggingSetInformation_2U`
- size: `185`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180040240`

## callees

- `0x180001008`
- `0x180077010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000109c`
- `KERNEL32!FreeLibrary` at `0x18000109c`
- `KERNEL32!GetProcAddress` at `0x180001070`
- `KERNEL32!GetProcAddress` at `0x180001070`
- `KERNEL32!GetModuleHandleExW` at `0x180001036`
- `KERNEL32!GetModuleHandleExW` at `0x180001054`
- `KERNEL32!GetModuleHandleExW` at `0x180001036`
- `KERNEL32!GetModuleHandleExW` at `0x180001054`

## string_xrefs

- `0x18000104d`: `advapi32.dll`
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
0x18000103d  nop     dword ptr [rax+rax+00h]
0x180001042  test    eax, eax
0x180001044  jnz     short loc_180001064
0x180001046  lea     r8, [rsp+68h+phModule]; phModule
0x18000104b  xor     ecx, ecx; dwFlags
0x18000104d  lea     rdx, aAdvapi32Dll_0; "advapi32.dll"
0x180001054  call    cs:__imp_GetModuleHandleExW
0x18000105b  nop     dword ptr [rax+rax+00h]
0x180001060  test    eax, eax
0x180001062  jz      short loc_1800010AC
0x180001064  mov     rcx, [rsp+68h+phModule]; hModule
0x180001069  lea     rdx, ProcName; "EventSetInformation"
0x180001070  call    cs:__imp_GetProcAddress
0x180001077  nop     dword ptr [rax+rax+00h]
0x18000107c  test    rax, rax
0x18000107f  jz      short loc_180001097
0x180001081  mov     rcx, [rbp+20h]
0x180001085  mov     r9d, edi
0x180001088  mov     r8, rsi
0x18000108b  mov     edx, 2
0x180001090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001095  mov     ebx, eax
0x180001097  mov     rcx, [rsp+68h+phModule]; hLibModule
0x18000109c  call    cs:__imp_FreeLibrary
0x1800010a3  nop     dword ptr [rax+rax+00h]
0x1800010a8  test    ebx, ebx
0x1800010aa  jle     short loc_1800010B5
0x1800010ac  movzx   ebx, bx
0x1800010af  or      ebx, 80070000h
0x1800010b5  mov     eax, ebx
0x1800010b7  add     rsp, 48h
0x1800010bb  pop     rdi
0x1800010bc  pop     rsi
0x1800010bd  pop     rbp
0x1800010be  pop     rbx
0x1800010bf  retn
```
