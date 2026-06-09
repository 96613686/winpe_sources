# DllMain

- ea: `0x18000bc30`
- end: `0x18000bcf5`
- name: `DllMain`
- size: `197`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180013ad4`

## callees

- `0x18000bc30`
- `0x18000bd00`
- `0x18000bdb4`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000bc68`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000bc68`
- `ntdll!RtlDeleteCriticalSection` at `0x18000bcc0`
- `ntdll!RtlDeleteCriticalSection` at `0x18000bcc0`
- `ntdll!RtlInitializeSRWLock` at `0x18000bc87`
- `ntdll!RtlInitializeSRWLock` at `0x18000bc87`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL result; // eax

  if ( !fdwReason )
  {
    if ( qword_18002ED78 )
      (**(void (__fastcall ***)(__int64, __int64, LPVOID))qword_18002ED78)(qword_18002ED78, 1, lpvReserved);
    qword_18002ED78 = 0;
    RtlDeleteCriticalSection(&s_csProxy);
    TraceLoggingUnregister_EventUnregister(&dword_18002E000);
    TraceLoggingUnregister_EventUnregister(&dword_18002E038);
    return 1;
  }
  if ( fdwReason != 1 )
    return 1;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18002E000);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18002E038);
  DisableThreadLibraryCalls(hinstDLL);
  xmmword_18002ECB0 = 0;
  AcGlobals = 0;
  RtlInitializeSRWLock(&AcGlobals);
  result = 1;
  DWORD2(AcGlobals) = 0;
  return result;
}

```

## disassembly

```asm
0x18000bc30  push    rbx
0x18000bc32  sub     rsp, 20h
0x18000bc36  mov     rbx, rcx
0x18000bc39  test    edx, edx
0x18000bc3b  jz      short loc_18000BCA2
0x18000bc3d  cmp     edx, 1
0x18000bc40  jz      short loc_18000BC4D
0x18000bc42  mov     eax, 1
0x18000bc47  add     rsp, 20h
0x18000bc4b  pop     rbx
0x18000bc4c  retn
0x18000bc4d  lea     rcx, dword_18002E000; CallbackContext
0x18000bc54  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000bc59  lea     rcx, dword_18002E038; CallbackContext
0x18000bc60  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000bc65  mov     rcx, rbx; hLibModule
0x18000bc68  call    cs:__imp_DisableThreadLibraryCalls
0x18000bc6e  xorps   xmm0, xmm0
0x18000bc71  lea     rcx, AcGlobals
0x18000bc78  movdqu  cs:xmmword_18002ECB0, xmm0
0x18000bc80  movups  cs:AcGlobals, xmm0
0x18000bc87  call    cs:__imp_RtlInitializeSRWLock
0x18000bc8d  mov     eax, 1
0x18000bc92  mov     dword ptr cs:AcGlobals+8, 0
0x18000bc9c  add     rsp, 20h
0x18000bca0  pop     rbx
0x18000bca1  retn
0x18000bca2  mov     rcx, cs:qword_18002ED78
0x18000bca9  test    rcx, rcx
0x18000bcac  jnz     short loc_18000BCE3
0x18000bcae  lea     rcx, ?s_csProxy@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000bcb5  mov     cs:qword_18002ED78, 0
0x18000bcc0  call    cs:__imp_RtlDeleteCriticalSection
0x18000bcc6  lea     rcx, dword_18002E000
0x18000bccd  call    TraceLoggingUnregister_EventUnregister
0x18000bcd2  lea     rcx, dword_18002E038
0x18000bcd9  call    TraceLoggingUnregister_EventUnregister
0x18000bcde  jmp     loc_18000BC42
0x18000bce3  mov     rax, [rcx]
0x18000bce6  mov     edx, 1
0x18000bceb  mov     rax, [rax]
0x18000bcee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcf3  jmp     short loc_18000BCAE
```
