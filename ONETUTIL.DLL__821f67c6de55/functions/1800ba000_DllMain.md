# DllMain

- ea: `0x1800ba000`
- end: `0x1800ba167`
- name: `DllMain`
- size: `359`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801505ec`

## callees

- `0x180084d74`
- `0x1800962c0`
- `0x1800b9e5c`
- `0x1800b9f48`
- `0x1800ba000`
- `0x1800db960`
- `0x18014146c`
- `0x18014eff8`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800ba12b`
- `KERNEL32!SetEvent` at `0x1800ba12b`
- `KERNEL32!CreateEventA` at `0x1800ba03e`
- `KERNEL32!CreateEventA` at `0x1800ba03e`
- `KERNEL32!DisableThreadLibraryCalls` at `0x1800ba070`
- `KERNEL32!DisableThreadLibraryCalls` at `0x1800ba070`
- `KERNEL32!TlsFree` at `0x1800ba14b`
- `KERNEL32!TlsFree` at `0x1800ba14b`
- `KERNEL32!TlsAlloc` at `0x1800ba027`
- `KERNEL32!TlsAlloc` at `0x1800ba027`
- `KERNEL32!InitializeCriticalSection` at `0x1800ba052`
- `KERNEL32!InitializeCriticalSection` at `0x1800ba052`
- `KERNEL32!LeaveCriticalSection` at `0x1800ba0aa`
- `KERNEL32!LeaveCriticalSection` at `0x1800ba0aa`
- `KERNEL32!EnterCriticalSection` at `0x1800ba096`
- `KERNEL32!EnterCriticalSection` at `0x1800ba096`
- `KERNEL32!DeleteCriticalSection` at `0x1800ba0b7`
- `KERNEL32!DeleteCriticalSection` at `0x1800ba0b7`
- `KERNEL32!CloseHandle` at `0x1800ba138`
- `KERNEL32!CloseHandle` at `0x1800ba138`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      if ( dwTlsIndex == -1 )
        dwTlsIndex = TlsAlloc();
      hEvent = CreateEventA(0, 0, 1, 0);
      InitializeCriticalSection(&CriticalSection);
      dword_1802B0410 = sub_1800B9E5C();
      sub_1800B9F48();
      sub_180084D74();
      DisableThreadLibraryCalls(hinstDLL);
    }
  }
  else
  {
    if ( _InterlockedCompareExchange(&dword_1802B0040, 0, 1) == 1 )
      sub_18014EFF8(hinstDLL, fdwReason, lpvReserved);
    EnterCriticalSection(&CriticalSection);
    qword_1802AFF90 = 0;
    LeaveCriticalSection(&CriticalSection);
    DeleteCriticalSection(&CriticalSection);
    if ( qword_1802B2008 )
    {
      sub_18014146C();
      qword_1802B2008 = 0;
    }
    if ( dword_1802B0410 )
    {
      VprocessGlobals::acquireFPGlobalCriticalSection();
      if ( (*((_DWORD *)qword_1802B0430 + 63))-- == 1 )
      {
        sub_1800DB960();
        if ( qword_1802B0430 )
          (**(void (__fastcall ***)(struct COWSThreadHandler *, __int64))qword_1802B0430)(qword_1802B0430, 1);
        qword_1802B0430 = 0;
      }
      if ( !--word_1802B00B8 )
        SetEvent(hEvent);
    }
    CloseHandle(hEvent);
    if ( dwTlsIndex != -1 )
    {
      TlsFree(dwTlsIndex);
      dwTlsIndex = -1;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800ba000  mov     [rsp+arg_0], rbx
0x1800ba005  push    rdi
0x1800ba006  sub     rsp, 20h
0x1800ba00a  xor     ebx, ebx
0x1800ba00c  mov     rdi, rcx
0x1800ba00f  test    edx, edx
0x1800ba011  jz      short loc_1800BA07B
0x1800ba013  cmp     edx, 1
0x1800ba016  jnz     loc_1800BA157
0x1800ba01c  or      ebx, 0FFFFFFFFh
0x1800ba01f  cmp     cs:dwTlsIndex, ebx
0x1800ba025  jnz     short loc_1800BA033
0x1800ba027  call    cs:TlsAlloc
0x1800ba02d  mov     cs:dwTlsIndex, eax
0x1800ba033  xor     r9d, r9d; lpName
0x1800ba036  xor     edx, edx; bManualReset
0x1800ba038  xor     ecx, ecx; lpEventAttributes
0x1800ba03a  lea     r8d, [r9+1]; bInitialState
0x1800ba03e  call    cs:CreateEventA
0x1800ba044  lea     rcx, CriticalSection; lpCriticalSection
0x1800ba04b  mov     cs:hEvent, rax
0x1800ba052  call    cs:InitializeCriticalSection
0x1800ba058  call    sub_1800B9E5C
0x1800ba05d  mov     cs:dword_1802B0410, eax
0x1800ba063  call    sub_1800B9F48
0x1800ba068  call    sub_180084D74
0x1800ba06d  mov     rcx, rdi; hLibModule
0x1800ba070  call    cs:DisableThreadLibraryCalls
0x1800ba076  jmp     loc_1800BA157
0x1800ba07b  mov     eax, 1
0x1800ba080  lock cmpxchg cs:dword_1802B0040, ebx
0x1800ba088  jnz     short loc_1800BA08F
0x1800ba08a  call    sub_18014EFF8
0x1800ba08f  lea     rcx, CriticalSection; lpCriticalSection
0x1800ba096  call    cs:EnterCriticalSection
0x1800ba09c  lea     rcx, CriticalSection; lpCriticalSection
0x1800ba0a3  mov     cs:qword_1802AFF90, rbx
0x1800ba0aa  call    cs:LeaveCriticalSection
0x1800ba0b0  lea     rcx, CriticalSection; lpCriticalSection
0x1800ba0b7  call    cs:DeleteCriticalSection
0x1800ba0bd  mov     rcx, cs:qword_1802B2008
0x1800ba0c4  test    rcx, rcx
0x1800ba0c7  jz      short loc_1800BA0D5
0x1800ba0c9  call    sub_18014146C
0x1800ba0ce  mov     cs:qword_1802B2008, rbx
0x1800ba0d5  cmp     cs:dword_1802B0410, ebx
0x1800ba0db  jz      short loc_1800BA131
0x1800ba0dd  call    ?acquireFPGlobalCriticalSection@VprocessGlobals@@SAXXZ; VprocessGlobals::acquireFPGlobalCriticalSection(void)
0x1800ba0e2  mov     rcx, cs:qword_1802B0430
0x1800ba0e9  or      edi, 0FFFFFFFFh
0x1800ba0ec  add     [rcx+0FCh], edi
0x1800ba0f2  jnz     short loc_1800BA11B
0x1800ba0f4  call    sub_1800DB960
0x1800ba0f9  mov     rcx, cs:qword_1802B0430
0x1800ba100  test    rcx, rcx
0x1800ba103  jz      short loc_1800BA114
0x1800ba105  mov     rax, [rcx]
0x1800ba108  lea     edx, [rdi+2]
0x1800ba10b  mov     rax, [rax]
0x1800ba10e  call    cs:__guard_dispatch_icall_fptr
0x1800ba114  mov     cs:qword_1802B0430, rbx
0x1800ba11b  add     cs:word_1802B00B8, di
0x1800ba122  jnz     short loc_1800BA131
0x1800ba124  mov     rcx, cs:hEvent; hEvent
0x1800ba12b  call    cs:SetEvent
0x1800ba131  mov     rcx, cs:hEvent; hObject
0x1800ba138  call    cs:CloseHandle
0x1800ba13e  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800ba144  or      ebx, 0FFFFFFFFh
0x1800ba147  cmp     ecx, ebx
0x1800ba149  jz      short loc_1800BA157
0x1800ba14b  call    cs:TlsFree
0x1800ba151  mov     cs:dwTlsIndex, ebx
0x1800ba157  mov     eax, 1
0x1800ba15c  mov     rbx, [rsp+28h+arg_0]
0x1800ba161  add     rsp, 20h
0x1800ba165  pop     rdi
0x1800ba166  retn
```
