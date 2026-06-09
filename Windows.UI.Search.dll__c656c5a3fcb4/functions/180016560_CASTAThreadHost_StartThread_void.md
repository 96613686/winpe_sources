# CASTAThreadHost::StartThread(void)

- ea: `0x180016560`
- end: `0x1800165fb`
- name: `?StartThread@CASTAThreadHost@@EEAAJXZ`
- size: `155`
- prototype: `__int64 __fastcall(CASTAThreadHost *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180010fd0`
- `0x180016560`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016572`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016572`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800165d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800165d5`
- `SHCORE!SHCreateThreadWithHandle` at `0x1800165b9`
- `SHCORE!SHCreateThreadWithHandle` at `0x1800165b9`

## pseudocode

```c
__int64 __fastcall CASTAThreadHost::StartThread(RTL_SRWLOCK *this)
{
  int Ptr; // ebx
  __int64 v3; // rax

  Ptr = 0;
  AcquireSRWLockExclusive(this + 4);
  if ( !this[7].Ptr )
  {
    v3 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)this[3].Ptr + 24LL))(this[3].Ptr);
    if ( SHCreateThreadWithHandle(
           (LPTHREAD_START_ROUTINE)CASTAThreadHost::s_ASTAThreadHostThreadProc,
           &this[-9],
           (*(_DWORD *)(v3 + 40) & 2 | 1) << 14,
           (LPTHREAD_START_ROUTINE)CASTAThreadHost::s_ASTAThreadHostStartThreadProc,
           &this[7].Ptr)
      || (Ptr = ResultFromKnownLastError(), Ptr >= 0) )
    {
      Ptr = (int)this[8].Ptr;
    }
  }
  ReleaseSRWLockExclusive(this + 4);
  if ( Ptr < 0 )
    (*((void (__fastcall **)(RTL_SRWLOCK *, _QWORD))this->Ptr + 4))(this, 0);
  return (unsigned int)Ptr;
}

```

## disassembly

```asm
0x180016560  push    rbx
0x180016562  push    rbp
0x180016563  push    rsi
0x180016564  push    rdi
0x180016565  sub     rsp, 38h
0x180016569  mov     rdi, rcx
0x18001656c  xor     ebx, ebx
0x18001656e  add     rcx, 20h ; ' '; SRWLock
0x180016572  call    cs:__imp_AcquireSRWLockExclusive
0x180016578  cmp     [rdi+38h], rbx
0x18001657c  jnz     short loc_1800165D1
0x18001657e  mov     rcx, [rdi+18h]
0x180016582  lea     rbx, [rdi+38h]
0x180016586  mov     rax, [rcx]
0x180016589  mov     rax, [rax+18h]
0x18001658d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016592  lea     r9, ?s_ASTAThreadHostStartThreadProc@CASTAThreadHost@@CAKPEAX@Z; pfnCallback
0x180016599  mov     [rsp+58h+pHandle], rbx; pHandle
0x18001659e  lea     rdx, [rdi-48h]; pData
0x1800165a2  lea     rcx, ?s_ASTAThreadHostThreadProc@CASTAThreadHost@@CAKPEAX@Z; pfnThreadProc
0x1800165a9  mov     r8d, [rax+28h]
0x1800165ad  and     r8d, 2
0x1800165b1  or      r8d, 1
0x1800165b5  shl     r8d, 0Eh; flags
0x1800165b9  call    cs:__imp_SHCreateThreadWithHandle
0x1800165bf  test    eax, eax
0x1800165c1  jnz     short loc_1800165CE
0x1800165c3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800165c8  mov     ebx, eax
0x1800165ca  test    eax, eax
0x1800165cc  js      short loc_1800165D1
0x1800165ce  mov     ebx, [rdi+40h]
0x1800165d1  lea     rcx, [rdi+20h]; SRWLock
0x1800165d5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800165db  test    ebx, ebx
0x1800165dd  jns     short loc_1800165F0
0x1800165df  mov     rcx, [rdi]
0x1800165e2  xor     edx, edx
0x1800165e4  mov     rax, [rcx+20h]
0x1800165e8  mov     rcx, rdi
0x1800165eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165f0  mov     eax, ebx
0x1800165f2  add     rsp, 38h
0x1800165f6  pop     rdi
0x1800165f7  pop     rsi
0x1800165f8  pop     rbp
0x1800165f9  pop     rbx
0x1800165fa  retn
```
