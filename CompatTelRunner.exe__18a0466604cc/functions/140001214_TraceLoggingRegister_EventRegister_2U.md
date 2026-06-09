# TraceLoggingRegister_EventRegister_2U

- ea: `0x140001214`
- end: `0x140001331`
- name: `TraceLoggingRegister_EventRegister_2U`
- size: `285`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140011880`

## callees

- `0x140001214`
- `0x140001ba0`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400012e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400012e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400012b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400012cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400012b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400012cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000130c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000130c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140001279`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140001279`

## string_xrefs

- `0x1400012a2`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x1400012c8`: `advapi32.dll`

## pseudocode

```c
__int64 TraceLoggingRegister_EventRegister_2U()
{
  signed int v0; // eax
  unsigned int v1; // ebx
  void *v2; // rdi
  unsigned int v3; // esi
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+30h] [rbp-28h] BYREF
  GUID ProviderId; // [rsp+38h] [rbp-20h] BYREF

  ProviderId = (GUID)*((_OWORD *)off_1400C7ED8 - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_1400C7EF8 = 0;
  v0 = EventRegister(&ProviderId, (PENABLECALLBACK)tlgEnableCallback, &dword_1400C7ED0, &RegHandle);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 > 0 )
      return (unsigned __int16)v0 | 0x80070000;
  }
  else
  {
    v2 = off_1400C7ED8;
    phModule = 0;
    v3 = *(unsigned __int16 *)off_1400C7ED8;
    if ( GetModuleHandleExW(0, L"api-ms-win-eventing-provider-l1-1-0.dll", &phModule)
      || GetModuleHandleExW(0, L"advapi32.dll", &phModule) )
    {
      ProcAddress = GetProcAddress(phModule, "EventSetInformation");
      if ( ProcAddress )
        ((void (__fastcall *)(ULONGLONG, __int64, void *, _QWORD))ProcAddress)(RegHandle, 2, v2, v3);
      FreeLibrary(phModule);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140001214  mov     [rsp+arg_0], rbx
0x140001219  mov     [rsp+arg_8], rsi
0x14000121e  push    rdi
0x14000121f  sub     rsp, 50h
0x140001223  mov     rax, cs:__security_cookie
0x14000122a  xor     rax, rsp
0x14000122d  mov     [rsp+58h+var_10], rax
0x140001232  cmp     cs:RegHandle, 0
0x14000123a  mov     rax, cs:off_1400C7ED8; "9"
0x140001241  movups  xmm0, xmmword ptr [rax-10h]
0x140001245  movdqu  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x14000124b  jz      short loc_140001254
0x14000124d  mov     ecx, 5
0x140001252  int     29h; Win8: RtlFailFast(ecx)
0x140001254  xorps   xmm0, xmm0
0x140001257  lea     r9, RegHandle; RegHandle
0x14000125e  lea     r8, dword_1400C7ED0; CallbackContext
0x140001265  lea     rdx, _tlgEnableCallback; EnableCallback
0x14000126c  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x140001271  movdqu  cs:xmmword_1400C7EF8, xmm0
0x140001279  call    cs:__imp_EventRegister
0x14000127f  mov     ebx, eax
0x140001281  test    eax, eax
0x140001283  jz      short loc_140001296
0x140001285  jle     loc_140001312
0x14000128b  movzx   ebx, ax
0x14000128e  or      ebx, 80070000h
0x140001294  jmp     short loc_140001312
0x140001296  mov     rdi, cs:off_1400C7ED8; "9"
0x14000129d  lea     r8, [rsp+58h+phModule]; phModule
0x1400012a2  lea     rdx, ModuleName; "api-ms-win-eventing-provider-l1-1-0.dll"
0x1400012a9  mov     [rsp+58h+phModule], 0
0x1400012b2  xor     ecx, ecx; dwFlags
0x1400012b4  movzx   esi, word ptr [rdi]
0x1400012b7  call    cs:__imp_GetModuleHandleExW
0x1400012bd  test    eax, eax
0x1400012bf  jnz     short loc_1400012D9
0x1400012c1  lea     r8, [rsp+58h+phModule]; phModule
0x1400012c6  xor     ecx, ecx; dwFlags
0x1400012c8  lea     rdx, aAdvapi32Dll; "advapi32.dll"
0x1400012cf  call    cs:__imp_GetModuleHandleExW
0x1400012d5  test    eax, eax
0x1400012d7  jz      short loc_140001312
0x1400012d9  mov     rcx, [rsp+58h+phModule]; hModule
0x1400012de  lea     rdx, ProcName; "EventSetInformation"
0x1400012e5  call    cs:__imp_GetProcAddress
0x1400012eb  test    rax, rax
0x1400012ee  jz      short loc_140001307
0x1400012f0  mov     rcx, cs:RegHandle
0x1400012f7  mov     r9d, esi
0x1400012fa  mov     r8, rdi
0x1400012fd  mov     edx, 2
0x140001302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001307  mov     rcx, [rsp+58h+phModule]; hLibModule
0x14000130c  call    cs:__imp_FreeLibrary
0x140001312  mov     eax, ebx
0x140001314  mov     rcx, [rsp+58h+var_10]
0x140001319  xor     rcx, rsp; StackCookie
0x14000131c  call    __security_check_cookie
0x140001321  mov     rbx, [rsp+58h+arg_0]
0x140001326  mov     rsi, [rsp+58h+arg_8]
0x14000132b  add     rsp, 50h
0x14000132f  pop     rdi
0x140001330  retn
```
