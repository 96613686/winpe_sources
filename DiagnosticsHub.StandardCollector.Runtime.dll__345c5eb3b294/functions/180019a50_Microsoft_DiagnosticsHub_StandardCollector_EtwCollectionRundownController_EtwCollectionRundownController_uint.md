# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController::EtwCollectionRundownController(uint)

- ea: `0x180019a50`
- end: `0x180019b87`
- name: `??0EtwCollectionRundownController@StandardCollector@DiagnosticsHub@Microsoft@@IEAA@I@Z`
- size: `311`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a850`

## callees

- `0x180019a50`
- `0x18004a03c`
- `0x18004a088`
- `0x18004b640`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180019a98`
- `KERNEL32!CreateEventW` at `0x180019a98`
- `KERNEL32!GetLastError` at `0x180019aa9`
- `KERNEL32!GetLastError` at `0x180019ac2`
- `KERNEL32!GetLastError` at `0x180019aa9`
- `KERNEL32!GetLastError` at `0x180019ac2`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController *__fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController::EtwCollectionRundownController(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController *this)
{
  char *v2; // rsi
  HANDLE EventW; // rax
  signed int v4; // eax
  unsigned int v5; // ecx
  DWORD LastError; // eax
  _DWORD *v7; // rbx
  __int64 v8; // rcx
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController *result; // rax
  int v10; // [rsp+30h] [rbp-28h] BYREF

  *(_QWORD *)this = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController::`vftable';
  *((_QWORD *)this + 1) = 0;
  v2 = (char *)this + 16;
  *((_QWORD *)this + 2) = -1;
  *((_DWORD *)this + 6) = 0;
  EventW = CreateEventW(0, 1, 1, 0);
  *(_QWORD *)v2 = EventW;
  if ( EventW )
  {
    LastError = GetLastError();
    if ( LastError == 183 )
      *((_DWORD *)v2 + 2) = 1;
  }
  else
  {
    *(_QWORD *)v2 = -1;
    v4 = GetLastError();
    v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 <= 0 )
      v5 = v4;
    *((_DWORD *)v2 + 2) = v5;
  }
  try
  {
    v7 = operator new(0xE8u);
    v7[4] = 1;
    *((_QWORD *)v7 + 1) = &CModuleRefCount::`vftable';
    if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&CModuleRefCount::s_ulcModuleRef) >= 0x7FFFFFFF )
      __fastfail(0xEu);
    *(_QWORD *)v7 = &Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::`vftable'{for `IStandardCollectorEtwAgent'};
    *((_QWORD *)v7 + 1) = &Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::`vftable'{for `CModuleRefCount'};
    `eh vector constructor iterator'(
      v7 + 6,
      0x40u,
      3u,
      (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::RundownInstance::RundownInstance,
      (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::RundownInstance::~RundownInstance);
    *((_QWORD *)v7 + 27) = v2;
    v7[56] = 0;
    v8 = *((_QWORD *)this + 1);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)this + 1) = v7;
    result = this;
  }
  catch ( std::bad_alloc )
  {
    v10 = -2147024882;
    throw (long *)&v10;
  }
  return result;
}

```

## disassembly

```asm
0x180019a50  mov     [rsp+arg_8], rbx
0x180019a55  mov     [rsp+arg_0], rcx
0x180019a5a  push    rsi
0x180019a5b  push    rdi
0x180019a5c  push    r14
0x180019a5e  sub     rsp, 40h
0x180019a62  mov     rdi, rcx
0x180019a65  lea     rax, ??_7EtwCollectionRundownController@StandardCollector@DiagnosticsHub@Microsoft@@6B@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController::`vftable'
0x180019a6c  mov     [rcx], rax
0x180019a6f  mov     qword ptr [rcx+8], 0
0x180019a77  lea     rsi, [rcx+10h]
0x180019a7b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180019a7f  mov     [rsi], rbx
0x180019a82  mov     dword ptr [rsi+8], 0
0x180019a89  xor     r9d, r9d; lpName
0x180019a8c  lea     r14d, [rbx+2]
0x180019a90  mov     r8d, r14d; bInitialState
0x180019a93  mov     edx, r14d; bManualReset
0x180019a96  xor     ecx, ecx; lpEventAttributes
0x180019a98  call    cs:__imp_CreateEventW
0x180019a9e  mov     [rsi], rax
0x180019aa1  test    rax, rax
0x180019aa4  jnz     short loc_180019AC2
0x180019aa6  mov     [rsi], rbx
0x180019aa9  call    cs:__imp_GetLastError
0x180019aaf  movzx   ecx, ax
0x180019ab2  or      ecx, 80070000h
0x180019ab8  test    eax, eax
0x180019aba  cmovle  ecx, eax
0x180019abd  mov     [rsi+8], ecx
0x180019ac0  jmp     short loc_180019AD3
0x180019ac2  call    cs:__imp_GetLastError
0x180019ac8  cmp     eax, 0B7h
0x180019acd  jnz     short loc_180019AD3
0x180019acf  mov     [rsi+8], r14d
0x180019ad3  mov     ecx, 0E8h; Size
0x180019ad8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019add  mov     rbx, rax
0x180019ae0  mov     [rsp+58h+arg_10], rax
0x180019ae5  mov     [rax+10h], r14d
0x180019ae9  lea     rax, ??_7CModuleRefCount@@6B@; const CModuleRefCount::`vftable'
0x180019af0  mov     [rbx+8], rax
0x180019af4  mov     ecx, r14d
0x180019af7  lock xadd cs:?s_ulcModuleRef@CModuleRefCount@@0KA, ecx; ulong CModuleRefCount::s_ulcModuleRef
0x180019aff  add     ecx, r14d
0x180019b02  cmp     ecx, 7FFFFFFFh
0x180019b08  jb      short loc_180019B11
0x180019b0a  mov     ecx, 0Eh
0x180019b0f  int     29h; Win8: RtlFailFast(ecx)
0x180019b11  lea     rax, ??_7RundownAgent@StandardCollector@DiagnosticsHub@Microsoft@@6BIStandardCollectorEtwAgent@@@; const Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::`vftable'{for `IStandardCollectorEtwAgent'}
0x180019b18  mov     [rbx], rax
0x180019b1b  lea     rax, ??_7RundownAgent@StandardCollector@DiagnosticsHub@Microsoft@@6BCModuleRefCount@@@; const Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::`vftable'{for `CModuleRefCount'}
0x180019b22  mov     [rbx+8], rax
0x180019b26  lea     rcx, [rbx+18h]; void *
0x180019b2a  lea     rax, ??1RundownInstance@RundownAgent@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::RundownAgent::RundownInstance::~RundownInstance(void)
0x180019b31  mov     [rsp+58h+var_38], rax; void (*)(void *)
0x180019b36  lea     r9, ??0RundownInstance@RundownAgent@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; void (*)(void *)
0x180019b3d  mov     edx, 40h ; '@'; unsigned __int64
0x180019b42  lea     r8d, [rdx-3Dh]; unsigned __int64
0x180019b46  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180019b4b  mov     [rbx+0D8h], rsi
0x180019b52  mov     dword ptr [rbx+0E0h], 0
0x180019b5c  mov     rcx, [rdi+8]
0x180019b60  test    rcx, rcx
0x180019b63  jz      short loc_180019B72
0x180019b65  mov     rax, [rcx]
0x180019b68  mov     rax, [rax+10h]
0x180019b6c  call    cs:__guard_dispatch_icall_fptr
0x180019b72  mov     [rdi+8], rbx
0x180019b76  mov     rax, rdi
0x180019b79  mov     rbx, [rsp+58h+arg_8]
0x180019b7e  add     rsp, 40h
0x180019b82  pop     r14
0x180019b84  pop     rdi
0x180019b85  pop     rsi
0x180019b86  retn
```
