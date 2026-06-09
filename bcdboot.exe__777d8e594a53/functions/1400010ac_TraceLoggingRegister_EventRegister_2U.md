# TraceLoggingRegister_EventRegister_2U

- ea: `0x1400010ac`
- end: `0x1400011b2`
- name: `TraceLoggingRegister_EventRegister_2U`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD *CallbackContext)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000f2a0`

## callees

- `0x1400010ac`
- `0x140026650`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140001171`
- `KERNEL32!GetProcAddress` at `0x140001171`
- `KERNEL32!FreeLibrary` at `0x140001194`
- `KERNEL32!FreeLibrary` at `0x140001194`
- `KERNEL32!GetModuleHandleExW` at `0x140001143`
- `KERNEL32!GetModuleHandleExW` at `0x14000115b`
- `KERNEL32!GetModuleHandleExW` at `0x140001143`
- `KERNEL32!GetModuleHandleExW` at `0x14000115b`
- `ADVAPI32!EventRegister` at `0x140001108`
- `ADVAPI32!EventRegister` at `0x140001108`

## string_xrefs

- `0x140001154`: `advapi32.dll`
- `0x14000112e`: `api-ms-win-eventing-provider-l1-1-0.dll`

## pseudocode

```c
__int64 __fastcall TraceLoggingRegister_EventRegister_2U(_QWORD *CallbackContext)
{
  _QWORD *v1; // rsi
  bool v2; // zf
  signed int v4; // eax
  unsigned int v5; // ebx
  unsigned __int16 *v6; // rdi
  unsigned int v7; // ebp
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+30h] [rbp-48h] BYREF
  GUID ProviderId; // [rsp+38h] [rbp-40h] BYREF

  v1 = CallbackContext + 4;
  v2 = CallbackContext[4] == 0;
  ProviderId = *(GUID *)(CallbackContext[1] - 16LL);
  if ( !v2 )
    __fastfail(5u);
  CallbackContext[5] = 0;
  CallbackContext[6] = 0;
  v4 = EventRegister(&ProviderId, (PENABLECALLBACK)tlgEnableCallback, CallbackContext, CallbackContext + 4);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    v6 = (unsigned __int16 *)CallbackContext[1];
    phModule = 0;
    v7 = *v6;
    if ( GetModuleHandleExW(0, L"api-ms-win-eventing-provider-l1-1-0.dll", &phModule)
      || GetModuleHandleExW(0, L"advapi32.dll", &phModule) )
    {
      ProcAddress = GetProcAddress(phModule, "EventSetInformation");
      if ( ProcAddress )
        ((void (__fastcall *)(_QWORD, __int64, unsigned __int16 *, _QWORD))ProcAddress)(*v1, 2, v6, v7);
      FreeLibrary(phModule);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1400010ac  push    rbx
0x1400010ae  push    rbp
0x1400010af  push    rsi
0x1400010b0  push    rdi
0x1400010b1  sub     rsp, 58h
0x1400010b5  mov     rax, cs:__security_cookie
0x1400010bc  xor     rax, rsp
0x1400010bf  mov     [rsp+78h+var_30], rax
0x1400010c4  mov     rax, [rcx+8]
0x1400010c8  lea     rsi, [rcx+20h]
0x1400010cc  cmp     qword ptr [rsi], 0
0x1400010d0  mov     rdi, rcx
0x1400010d3  movups  xmm0, xmmword ptr [rax-10h]
0x1400010d7  movdqu  xmmword ptr [rsp+78h+ProviderId.Data1], xmm0
0x1400010dd  jz      short loc_1400010E6
0x1400010df  mov     ecx, 5
0x1400010e4  int     29h; Win8: RtlFailFast(ecx)
0x1400010e6  mov     r9, rsi; RegHandle
0x1400010e9  mov     qword ptr [rdi+28h], 0
0x1400010f1  mov     r8, rdi; CallbackContext
0x1400010f4  mov     qword ptr [rdi+30h], 0
0x1400010fc  lea     rdx, _tlgEnableCallback; EnableCallback
0x140001103  lea     rcx, [rsp+78h+ProviderId]; ProviderId
0x140001108  call    cs:__imp_EventRegister
0x14000110e  mov     ebx, eax
0x140001110  test    eax, eax
0x140001112  jz      short loc_140001125
0x140001114  jle     loc_14000119A
0x14000111a  movzx   ebx, ax
0x14000111d  or      ebx, 80070000h
0x140001123  jmp     short loc_14000119A
0x140001125  mov     rdi, [rdi+8]
0x140001129  lea     r8, [rsp+78h+phModule]; phModule
0x14000112e  lea     rdx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x140001135  mov     [rsp+78h+phModule], 0
0x14000113e  xor     ecx, ecx; dwFlags
0x140001140  movzx   ebp, word ptr [rdi]
0x140001143  call    cs:__imp_GetModuleHandleExW
0x140001149  test    eax, eax
0x14000114b  jnz     short loc_140001165
0x14000114d  lea     r8, [rsp+78h+phModule]; phModule
0x140001152  xor     ecx, ecx; dwFlags
0x140001154  lea     rdx, aAdvapi32Dll_0; "advapi32.dll"
0x14000115b  call    cs:__imp_GetModuleHandleExW
0x140001161  test    eax, eax
0x140001163  jz      short loc_14000119A
0x140001165  mov     rcx, [rsp+78h+phModule]; hModule
0x14000116a  lea     rdx, ProcName; "EventSetInformation"
0x140001171  call    cs:__imp_GetProcAddress
0x140001177  test    rax, rax
0x14000117a  jz      short loc_14000118F
0x14000117c  mov     rcx, [rsi]
0x14000117f  mov     r9d, ebp
0x140001182  mov     r8, rdi
0x140001185  mov     edx, 2
0x14000118a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000118f  mov     rcx, [rsp+78h+phModule]; hLibModule
0x140001194  call    cs:__imp_FreeLibrary
0x14000119a  mov     eax, ebx
0x14000119c  mov     rcx, [rsp+78h+var_30]
0x1400011a1  xor     rcx, rsp; StackCookie
0x1400011a4  call    __security_check_cookie
0x1400011a9  add     rsp, 58h
0x1400011ad  pop     rdi
0x1400011ae  pop     rsi
0x1400011af  pop     rbp
0x1400011b0  pop     rbx
0x1400011b1  retn
```
