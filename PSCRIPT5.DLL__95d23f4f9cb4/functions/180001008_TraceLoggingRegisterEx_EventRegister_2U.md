# TraceLoggingRegisterEx_EventRegister_2U

- ea: `0x180001008`
- end: `0x18000110e`
- name: `TraceLoggingRegisterEx_EventRegister_2U`
- size: `262`
- prototype: `__int64 __fastcall(PVOID CallbackContext)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180009ee4`
- `0x180036454`

## callees

- `0x180001008`
- `0x180001ee0`
- `0x18005d010`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x180001064`
- `ADVAPI32!EventRegister` at `0x180001064`
- `KERNEL32!FreeLibrary` at `0x1800010f0`
- `KERNEL32!FreeLibrary` at `0x1800010f0`
- `KERNEL32!GetProcAddress` at `0x1800010cd`
- `KERNEL32!GetProcAddress` at `0x1800010cd`
- `KERNEL32!GetModuleHandleExW` at `0x18000109f`
- `KERNEL32!GetModuleHandleExW` at `0x1800010b7`
- `KERNEL32!GetModuleHandleExW` at `0x18000109f`
- `KERNEL32!GetModuleHandleExW` at `0x1800010b7`

## string_xrefs

- `0x18000108a`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x1800010b0`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall TraceLoggingRegisterEx_EventRegister_2U(_QWORD *CallbackContext)
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
  v4 = EventRegister(&ProviderId, tlgEnableCallback, CallbackContext, CallbackContext + 4);
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
0x18000106a  mov     ebx, eax
0x18000106c  test    eax, eax
0x18000106e  jz      short loc_180001081
0x180001070  jle     loc_1800010F6
0x180001076  movzx   ebx, ax
0x180001079  or      ebx, 80070000h
0x18000107f  jmp     short loc_1800010F6
0x180001081  mov     rdi, [rdi+8]
0x180001085  lea     r8, [rsp+78h+phModule]; phModule
0x18000108a  lea     rdx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x180001091  mov     [rsp+78h+phModule], 0
0x18000109a  xor     ecx, ecx; dwFlags
0x18000109c  movzx   ebp, word ptr [rdi]
0x18000109f  call    cs:__imp_GetModuleHandleExW
0x1800010a5  test    eax, eax
0x1800010a7  jnz     short loc_1800010C1
0x1800010a9  lea     r8, [rsp+78h+phModule]; phModule
0x1800010ae  xor     ecx, ecx; dwFlags
0x1800010b0  lea     rdx, aAdvapi32Dll_0; "advapi32.dll"
0x1800010b7  call    cs:__imp_GetModuleHandleExW
0x1800010bd  test    eax, eax
0x1800010bf  jz      short loc_1800010F6
0x1800010c1  mov     rcx, [rsp+78h+phModule]; hModule
0x1800010c6  lea     rdx, ProcName; "EventSetInformation"
0x1800010cd  call    cs:__imp_GetProcAddress
0x1800010d3  test    rax, rax
0x1800010d6  jz      short loc_1800010EB
0x1800010d8  mov     rcx, [rsi]
0x1800010db  mov     r9d, ebp
0x1800010de  mov     r8, rdi
0x1800010e1  mov     edx, 2
0x1800010e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010eb  mov     rcx, [rsp+78h+phModule]; hLibModule
0x1800010f0  call    cs:__imp_FreeLibrary
0x1800010f6  mov     eax, ebx
0x1800010f8  mov     rcx, [rsp+78h+var_30]
0x1800010fd  xor     rcx, rsp; StackCookie
0x180001100  call    __security_check_cookie
0x180001105  add     rsp, 58h
0x180001109  pop     rdi
0x18000110a  pop     rsi
0x18000110b  pop     rbp
0x18000110c  pop     rbx
0x18000110d  retn
```
