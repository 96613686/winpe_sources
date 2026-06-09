# TraceLoggingRegisterEx_EventRegister_2U

- ea: `0x180001008`
- end: `0x180001130`
- name: `TraceLoggingRegisterEx_EventRegister_2U`
- size: `296`
- prototype: `__int64 __fastcall(_QWORD *CallbackContext)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000a268`
- `0x180037ca4`

## callees

- `0x180001008`
- `0x180001f20`
- `0x18005f010`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x180001064`
- `ADVAPI32!EventRegister` at `0x180001064`
- `KERNEL32!FreeLibrary` at `0x18000110b`
- `KERNEL32!FreeLibrary` at `0x18000110b`
- `KERNEL32!GetProcAddress` at `0x1800010e2`
- `KERNEL32!GetProcAddress` at `0x1800010e2`
- `KERNEL32!GetModuleHandleExW` at `0x1800010a8`
- `KERNEL32!GetModuleHandleExW` at `0x1800010c6`
- `KERNEL32!GetModuleHandleExW` at `0x1800010a8`
- `KERNEL32!GetModuleHandleExW` at `0x1800010c6`

## string_xrefs

- `0x180001093`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x1800010bf`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall TraceLoggingRegisterEx_EventRegister_2U(ULONGLONG *CallbackContext)
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
  ProviderId = *(GUID *)(CallbackContext[1] - 16);
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
0x180001008  push    rbx
0x18000100a  push    rbp
0x18000100b  push    rsi
0x18000100c  push    rdi
0x18000100d  sub     rsp, 58h
0x180001011  mov     rax, cs:__security_cookie
0x180001018  xor     rax, rsp
0x18000101b  mov     [rsp+78h+var_30], rax
0x180001020  mov     rax, [rcx+8]
0x180001024  lea     rsi, [rcx+20h]
0x180001028  cmp     qword ptr [rsi], 0
0x18000102c  mov     rdi, rcx
0x18000102f  movups  xmm0, xmmword ptr [rax-10h]
0x180001033  movdqu  xmmword ptr [rsp+78h+ProviderId.Data1], xmm0
0x180001039  jz      short loc_180001042
0x18000103b  mov     ecx, 5
0x180001040  int     29h; Win8: RtlFailFast(ecx)
0x180001042  mov     r9, rsi; RegHandle
0x180001045  mov     qword ptr [rdi+28h], 0
0x18000104d  mov     r8, rdi; CallbackContext
0x180001050  mov     qword ptr [rdi+30h], 0
0x180001058  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000105f  lea     rcx, [rsp+78h+ProviderId]; ProviderId
0x180001064  call    cs:__imp_EventRegister
0x18000106b  nop     dword ptr [rax+rax+00h]
0x180001070  mov     ebx, eax
0x180001072  test    eax, eax
0x180001074  jz      short loc_18000108A
0x180001076  jle     loc_180001117
0x18000107c  movzx   ebx, ax
0x18000107f  or      ebx, 80070000h
0x180001085  jmp     loc_180001117
0x18000108a  mov     rdi, [rdi+8]
0x18000108e  lea     r8, [rsp+78h+phModule]; phModule
0x180001093  lea     rdx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x18000109a  mov     [rsp+78h+phModule], 0
0x1800010a3  xor     ecx, ecx; dwFlags
0x1800010a5  movzx   ebp, word ptr [rdi]
0x1800010a8  call    cs:__imp_GetModuleHandleExW
0x1800010af  nop     dword ptr [rax+rax+00h]
0x1800010b4  test    eax, eax
0x1800010b6  jnz     short loc_1800010D6
0x1800010b8  lea     r8, [rsp+78h+phModule]; phModule
0x1800010bd  xor     ecx, ecx; dwFlags
0x1800010bf  lea     rdx, aAdvapi32Dll_0; "advapi32.dll"
0x1800010c6  call    cs:__imp_GetModuleHandleExW
0x1800010cd  nop     dword ptr [rax+rax+00h]
0x1800010d2  test    eax, eax
0x1800010d4  jz      short loc_180001117
0x1800010d6  mov     rcx, [rsp+78h+phModule]; hModule
0x1800010db  lea     rdx, ProcName; "EventSetInformation"
0x1800010e2  call    cs:__imp_GetProcAddress
0x1800010e9  nop     dword ptr [rax+rax+00h]
0x1800010ee  test    rax, rax
0x1800010f1  jz      short loc_180001106
0x1800010f3  mov     rcx, [rsi]
0x1800010f6  mov     r9d, ebp
0x1800010f9  mov     r8, rdi
0x1800010fc  mov     edx, 2
0x180001101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001106  mov     rcx, [rsp+78h+phModule]; hLibModule
0x18000110b  call    cs:__imp_FreeLibrary
0x180001112  nop     dword ptr [rax+rax+00h]
0x180001117  mov     eax, ebx
0x180001119  mov     rcx, [rsp+78h+var_30]
0x18000111e  xor     rcx, rsp; StackCookie
0x180001121  call    __security_check_cookie
0x180001126  add     rsp, 58h
0x18000112a  pop     rdi
0x18000112b  pop     rsi
0x18000112c  pop     rbp
0x18000112d  pop     rbx
0x18000112e  retn
```
