# TraceLoggingRegister_EventRegister_2U

- ea: `0x18000124c`
- end: `0x180001369`
- name: `TraceLoggingRegister_EventRegister_2U`
- size: `285`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180048564`

## callees

- `0x18000124c`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800012ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180001307`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800012ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180001307`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001344`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001344`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000131d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000131d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800012b1`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800012b1`

## string_xrefs

- `0x1800012da`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x180001300`: `advapi32.dll`

## pseudocode

```c
__int64 TraceLoggingRegister_EventRegister_2U()
{
  signed int v0; // eax
  unsigned int v1; // ebx
  char *v2; // rdi
  unsigned int v3; // esi
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+30h] [rbp-28h] BYREF
  GUID ProviderId; // [rsp+38h] [rbp-20h] BYREF

  ProviderId = *(GUID *)&(*off_18007D040)[-16];
  if ( RegHandle )
    __fastfail(5u);
  xmmword_18007D060 = 0;
  v0 = EventRegister(&ProviderId, tlgEnableCallback, &dword_18007D038, &RegHandle);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 > 0 )
      return (unsigned __int16)v0 | 0x80070000;
  }
  else
  {
    v2 = (char *)off_18007D040;
    phModule = 0;
    v3 = *(unsigned __int16 *)off_18007D040;
    if ( GetModuleHandleExW(0, L"api-ms-win-eventing-provider-l1-1-0.dll", &phModule)
      || GetModuleHandleExW(0, L"advapi32.dll", &phModule) )
    {
      ProcAddress = GetProcAddress(phModule, "EventSetInformation");
      if ( ProcAddress )
        ((void (__fastcall *)(ULONGLONG, __int64, char *, _QWORD))ProcAddress)(RegHandle, 2, v2, v3);
      FreeLibrary(phModule);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000124c  mov     [rsp+arg_0], rbx
0x180001251  mov     [rsp+arg_8], rsi
0x180001256  push    rdi
0x180001257  sub     rsp, 50h
0x18000125b  mov     rax, cs:__security_cookie
0x180001262  xor     rax, rsp
0x180001265  mov     [rsp+58h+var_10], rax
0x18000126a  cmp     cs:RegHandle, 0
0x180001272  mov     rax, cs:off_18007D040
0x180001279  movups  xmm0, xmmword ptr [rax-10h]
0x18000127d  movdqu  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x180001283  jz      short loc_18000128C
0x180001285  mov     ecx, 5
0x18000128a  int     29h; Win8: RtlFailFast(ecx)
0x18000128c  xorps   xmm0, xmm0
0x18000128f  lea     r9, RegHandle; RegHandle
0x180001296  lea     r8, dword_18007D038; CallbackContext
0x18000129d  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800012a4  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x1800012a9  movdqu  cs:xmmword_18007D060, xmm0
0x1800012b1  call    cs:__imp_EventRegister
0x1800012b7  mov     ebx, eax
0x1800012b9  test    eax, eax
0x1800012bb  jz      short loc_1800012CE
0x1800012bd  jle     loc_18000134A
0x1800012c3  movzx   ebx, ax
0x1800012c6  or      ebx, 80070000h
0x1800012cc  jmp     short loc_18000134A
0x1800012ce  mov     rdi, cs:off_18007D040
0x1800012d5  lea     r8, [rsp+58h+phModule]; phModule
0x1800012da  lea     rdx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x1800012e1  mov     [rsp+58h+phModule], 0
0x1800012ea  xor     ecx, ecx; dwFlags
0x1800012ec  movzx   esi, word ptr [rdi]
0x1800012ef  call    cs:__imp_GetModuleHandleExW
0x1800012f5  test    eax, eax
0x1800012f7  jnz     short loc_180001311
0x1800012f9  lea     r8, [rsp+58h+phModule]; phModule
0x1800012fe  xor     ecx, ecx; dwFlags
0x180001300  lea     rdx, aAdvapi32Dll; "advapi32.dll"
0x180001307  call    cs:__imp_GetModuleHandleExW
0x18000130d  test    eax, eax
0x18000130f  jz      short loc_18000134A
0x180001311  mov     rcx, [rsp+58h+phModule]; hModule
0x180001316  lea     rdx, ProcName; "EventSetInformation"
0x18000131d  call    cs:__imp_GetProcAddress
0x180001323  test    rax, rax
0x180001326  jz      short loc_18000133F
0x180001328  mov     rcx, cs:RegHandle
0x18000132f  mov     r9d, esi
0x180001332  mov     r8, rdi
0x180001335  mov     edx, 2
0x18000133a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000133f  mov     rcx, [rsp+58h+phModule]; hLibModule
0x180001344  call    cs:__imp_FreeLibrary
0x18000134a  mov     eax, ebx
0x18000134c  mov     rcx, [rsp+58h+var_10]
0x180001351  xor     rcx, rsp; StackCookie
0x180001354  call    __security_check_cookie
0x180001359  mov     rbx, [rsp+58h+arg_0]
0x18000135e  mov     rsi, [rsp+58h+arg_8]
0x180001363  add     rsp, 50h
0x180001367  pop     rdi
0x180001368  retn
```
