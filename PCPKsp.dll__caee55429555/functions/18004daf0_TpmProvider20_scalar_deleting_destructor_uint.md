# TpmProvider20::`scalar deleting destructor'(uint)

- ea: `0x18004daf0`
- end: `0x18004dbcf`
- name: `??_GTpmProvider20@@UEAAPEAXI@Z`
- size: `223`
- prototype: `void *__fastcall(TpmProvider20 *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18004daf0`
- `0x1800768a0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004db92`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004db92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004db32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004db72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004db32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004db72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004db1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004db45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004db1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004db45`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
TpmProvider20 *__fastcall TpmProvider20::`scalar deleting destructor'(TpmProvider20 *this, char a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi

  *(_QWORD *)this = &TpmProvider::`vftable';
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  if ( (*((_DWORD *)this + 3) & 1) == 0 )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( (*((_DWORD *)this + 3) & 1) == 0 )
    LeaveCriticalSection(v4);
  EnterCriticalSection(&g_TbsLock);
  if ( !--g_TbsRefCount && g_fpTpmClose )
    g_fpTpmClose();
  LeaveCriticalSection(&g_TbsLock);
  *(_QWORD *)this = &TpmObject::`vftable';
  if ( (*((_DWORD *)this + 3) & 1) == 0 )
    DeleteCriticalSection(v4);
  *(_QWORD *)this = &ObjectWithProperties::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x58);
  return this;
}

```

## disassembly

```asm
0x18004daf0  mov     [rsp+arg_0], rbx
0x18004daf5  mov     [rsp+arg_10], rsi
0x18004dafa  push    rdi
0x18004dafb  sub     rsp, 20h
0x18004daff  mov     esi, edx
0x18004db01  mov     rbx, rcx
0x18004db04  lea     rax, ??_7TpmProvider@@6B@; const TpmProvider::`vftable'
0x18004db0b  mov     [rcx], rax
0x18004db0e  lea     rdi, [rcx+10h]
0x18004db12  mov     eax, [rcx+0Ch]
0x18004db15  test    al, 1
0x18004db17  jnz     short loc_18004DB28
0x18004db19  mov     rcx, rdi; lpCriticalSection
0x18004db1c  call    cs:__imp_EnterCriticalSection
0x18004db23  nop     dword ptr [rax+rax+00h]
0x18004db28  mov     eax, [rbx+0Ch]
0x18004db2b  test    al, 1
0x18004db2d  jnz     short loc_18004DB3E
0x18004db2f  mov     rcx, rdi; lpCriticalSection
0x18004db32  call    cs:__imp_LeaveCriticalSection
0x18004db39  nop     dword ptr [rax+rax+00h]
0x18004db3e  lea     rcx, ?g_TbsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004db45  call    cs:__imp_EnterCriticalSection
0x18004db4c  nop     dword ptr [rax+rax+00h]
0x18004db51  add     cs:?g_TbsRefCount@@3KA, 0FFFFFFFFh; ulong g_TbsRefCount
0x18004db58  jnz     short loc_18004DB6B
0x18004db5a  mov     rax, cs:?g_fpTpmClose@@3P6AIXZEA; uint (*g_fpTpmClose)(void)
0x18004db61  test    rax, rax
0x18004db64  jz      short loc_18004DB6B
0x18004db66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db6b  lea     rcx, ?g_TbsLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004db72  call    cs:__imp_LeaveCriticalSection
0x18004db79  nop     dword ptr [rax+rax+00h]
0x18004db7e  lea     rax, ??_7TpmObject@@6B@; const TpmObject::`vftable'
0x18004db85  mov     [rbx], rax
0x18004db88  mov     eax, [rbx+0Ch]
0x18004db8b  test    al, 1
0x18004db8d  jnz     short loc_18004DB9E
0x18004db8f  mov     rcx, rdi; lpCriticalSection
0x18004db92  call    cs:__imp_DeleteCriticalSection
0x18004db99  nop     dword ptr [rax+rax+00h]
0x18004db9e  lea     rax, ??_7ObjectWithProperties@@6B@; const ObjectWithProperties::`vftable'
0x18004dba5  mov     [rbx], rax
0x18004dba8  test    sil, 1
0x18004dbac  jz      short loc_18004DBBB
0x18004dbae  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x18004dbb3  mov     rcx, rbx; void *
0x18004dbb6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004dbbb  mov     rax, rbx
0x18004dbbe  mov     rbx, [rsp+28h+arg_0]
0x18004dbc3  mov     rsi, [rsp+28h+arg_10]
0x18004dbc8  add     rsp, 20h
0x18004dbcc  pop     rdi
0x18004dbcd  retn
```
