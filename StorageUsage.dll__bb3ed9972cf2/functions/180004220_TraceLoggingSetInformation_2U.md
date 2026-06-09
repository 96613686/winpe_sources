# TraceLoggingSetInformation_2U

- ea: `0x180004220`
- end: `0x1800042e3`
- name: `TraceLoggingSetInformation_2U`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000417c`

## callees

- `0x180004220`
- `0x1800050f0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800042b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800042b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004260`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004278`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004260`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004278`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000428e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000428e`

## string_xrefs

- `0x180004251`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x180004271`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall TraceLoggingSetInformation_2U(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v7; // ebx
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+30h] [rbp-28h] BYREF

  phModule = 0;
  v7 = 50;
  if ( !GetModuleHandleExW(0, L"api-ms-win-eventing-provider-l1-1-0.dll", &phModule)
    && !GetModuleHandleExW(0, L"advapi32.dll", &phModule) )
  {
    return (unsigned __int16)v7 | 0x80070000;
  }
  ProcAddress = GetProcAddress(phModule, "EventSetInformation");
  if ( ProcAddress )
    v7 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _QWORD))ProcAddress)(*(_QWORD *)(a1 + 32), 2, a3, a4);
  FreeLibrary(phModule);
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004220  mov     [rsp+arg_8], rbx
0x180004225  push    rbp
0x180004226  push    rsi
0x180004227  push    rdi
0x180004228  sub     rsp, 40h
0x18000422c  mov     rax, cs:__security_cookie
0x180004233  xor     rax, rsp
0x180004236  mov     [rsp+58h+var_20], rax
0x18000423b  mov     rsi, r8
0x18000423e  mov     [rsp+58h+phModule], 0
0x180004247  mov     rdi, rcx
0x18000424a  lea     r8, [rsp+58h+phModule]; phModule
0x18000424f  xor     ecx, ecx; dwFlags
0x180004251  lea     rdx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x180004258  mov     ebp, r9d
0x18000425b  mov     ebx, 32h ; '2'
0x180004260  call    cs:__imp_GetModuleHandleExW
0x180004266  test    eax, eax
0x180004268  jnz     short loc_180004282
0x18000426a  lea     r8, [rsp+58h+phModule]; phModule
0x18000426f  xor     ecx, ecx; dwFlags
0x180004271  lea     rdx, aAdvapi32Dll; "advapi32.dll"
0x180004278  call    cs:__imp_GetModuleHandleExW
0x18000427e  test    eax, eax
0x180004280  jz      short loc_1800042BE
0x180004282  mov     rcx, [rsp+58h+phModule]; hModule
0x180004287  lea     rdx, ProcName; "EventSetInformation"
0x18000428e  call    cs:__imp_GetProcAddress
0x180004294  test    rax, rax
0x180004297  jz      short loc_1800042AF
0x180004299  mov     rcx, [rdi+20h]
0x18000429d  mov     r9d, ebp
0x1800042a0  mov     r8, rsi
0x1800042a3  mov     edx, 2
0x1800042a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042ad  mov     ebx, eax
0x1800042af  mov     rcx, [rsp+58h+phModule]; hLibModule
0x1800042b4  call    cs:__imp_FreeLibrary
0x1800042ba  test    ebx, ebx
0x1800042bc  jle     short loc_1800042C7
0x1800042be  movzx   ebx, bx
0x1800042c1  or      ebx, 80070000h
0x1800042c7  mov     eax, ebx
0x1800042c9  mov     rcx, [rsp+58h+var_20]
0x1800042ce  xor     rcx, rsp; StackCookie
0x1800042d1  call    __security_check_cookie
0x1800042d6  mov     rbx, [rsp+58h+arg_8]
0x1800042db  add     rsp, 40h
0x1800042df  pop     rdi
0x1800042e0  pop     rsi
0x1800042e1  pop     rbp
0x1800042e2  retn
```
