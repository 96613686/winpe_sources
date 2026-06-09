# LKRhash::CLKRHashTable::~CLKRHashTable(void)

- ea: `0x180007d18`
- end: `0x180007e12`
- name: `??1CLKRHashTable@LKRhash@@QEAA@XZ`
- size: `250`
- prototype: `void __fastcall(LKRhash::CLKRHashTable *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002f90`

## callees

- `0x1800077fc`
- `0x180007d18`
- `0x180007e18`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180007d7f`
- `KERNEL32!GetCurrentThreadId` at `0x180007d99`
- `KERNEL32!GetCurrentThreadId` at `0x180007d7f`
- `KERNEL32!GetCurrentThreadId` at `0x180007d99`

## pseudocode

```c
void __fastcall LKRhash::CLKRHashTable::~CLKRHashTable(LKRhash::CLKRHashTable *this)
{
  __int64 i; // rbp
  LKRhash::CLKRLinearHashTable *v3; // rbx
  _QWORD *v4; // rax
  __int64 v5; // rcx

  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 5); i = (unsigned int)(i + 1) )
  {
    v3 = *(LKRhash::CLKRLinearHashTable **)(*((_QWORD *)this + 3) + 8 * i);
    LKRhash::CLKRLinearHashTable::~CLKRLinearHashTable(v3);
    (*(void (__fastcall **)(_QWORD, LKRhash::CLKRLinearHashTable *, __int64))(**((_QWORD **)this + 7) + 8LL))(
      *((_QWORD *)this + 7),
      v3,
      6);
  }
  (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 7) + 8LL))(
    *((_QWORD *)this + 7),
    *((_QWORD *)this + 3),
    5);
  if ( LKRhash::CLKRHashTable::sm_llGlobalList
    || _InterlockedCompareExchange(
         (volatile signed __int32 *)&LKRhash::CLKRHashTable::sm_llGlobalList,
         GetCurrentThreadId() & 0xFFFFFFFC | 1,
         0) )
  {
    if ( (LKRhash::CLKRHashTable::sm_llGlobalList & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
      _InterlockedExchange(
        (volatile __int32 *)&LKRhash::CLKRHashTable::sm_llGlobalList,
        LKRhash::CLKRHashTable::sm_llGlobalList + 1);
    else
      CSpinLock::_LockSpin((CSpinLock *)&LKRhash::CLKRHashTable::sm_llGlobalList);
  }
  v4 = (_QWORD *)*((_QWORD *)this + 9);
  if ( v4 )
  {
    v5 = *((_QWORD *)this + 8);
    if ( v5 )
    {
      *v4 = v5;
      *(_QWORD *)(v5 + 8) = v4;
    }
  }
  _InterlockedExchange(
    (volatile __int32 *)&LKRhash::CLKRHashTable::sm_llGlobalList,
    ((LKRhash::CLKRHashTable::sm_llGlobalList - 1) & 3) != 0 ? LKRhash::CLKRHashTable::sm_llGlobalList - 1 : 0);
  *(_DWORD *)this = 2018003788;
  *((_DWORD *)this + 12) = -99;
}

```

## disassembly

```asm
0x180007d18  push    rbx
0x180007d1a  push    rbp
0x180007d1b  push    rsi
0x180007d1c  push    rdi
0x180007d1d  sub     rsp, 28h
0x180007d21  mov     rdi, rcx
0x180007d24  xor     ebp, ebp
0x180007d26  cmp     [rcx+14h], ebp
0x180007d29  jbe     short loc_180007D5B
0x180007d2b  mov     rax, [rdi+18h]
0x180007d2f  mov     rbx, [rax+rbp*8]
0x180007d33  mov     rcx, rbx; this
0x180007d36  call    ??1CLKRLinearHashTable@LKRhash@@QEAA@XZ; LKRhash::CLKRLinearHashTable::~CLKRLinearHashTable(void)
0x180007d3b  mov     rcx, [rdi+38h]
0x180007d3f  mov     rax, [rcx]
0x180007d42  mov     r8d, 6
0x180007d48  mov     rdx, rbx
0x180007d4b  mov     rax, [rax+8]
0x180007d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d54  inc     ebp
0x180007d56  cmp     ebp, [rdi+14h]
0x180007d59  jb      short loc_180007D2B
0x180007d5b  mov     rcx, [rdi+38h]
0x180007d5f  mov     rax, [rcx]
0x180007d62  mov     r8d, 5
0x180007d68  mov     rdx, [rdi+18h]
0x180007d6c  mov     rax, [rax+8]
0x180007d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d75  mov     eax, cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007d7b  test    eax, eax
0x180007d7d  jnz     short loc_180007D99
0x180007d7f  call    cs:__imp_GetCurrentThreadId
0x180007d85  mov     ecx, eax
0x180007d87  and     ecx, 0FFFFFFFDh
0x180007d8a  or      ecx, 1
0x180007d8d  xor     eax, eax
0x180007d8f  lock cmpxchg cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A, ecx; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007d97  jz      short loc_180007DCB
0x180007d99  call    cs:__imp_GetCurrentThreadId
0x180007d9f  and     eax, 0FFFFFFFCh
0x180007da2  mov     ecx, cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007da8  and     ecx, 0FFFFFFFCh
0x180007dab  cmp     ecx, eax
0x180007dad  jnz     short loc_180007DBF
0x180007daf  mov     eax, cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007db5  inc     eax
0x180007db7  xchg    eax, cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007dbd  jmp     short loc_180007DCB
0x180007dbf  lea     rcx, ?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; this
0x180007dc6  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x180007dcb  mov     rax, [rdi+48h]
0x180007dcf  test    rax, rax
0x180007dd2  jz      short loc_180007DE4
0x180007dd4  mov     rcx, [rdi+40h]
0x180007dd8  test    rcx, rcx
0x180007ddb  jz      short loc_180007DE4
0x180007ddd  mov     [rax], rcx
0x180007de0  mov     [rcx+8], rax
0x180007de4  mov     edx, cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007dea  dec     edx
0x180007dec  mov     eax, edx
0x180007dee  and     al, 3
0x180007df0  neg     al
0x180007df2  sbb     ecx, ecx
0x180007df4  and     ecx, edx
0x180007df6  xchg    ecx, cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007dfc  mov     dword ptr [rdi], 78484B4Ch
0x180007e02  mov     dword ptr [rdi+30h], 0FFFFFF9Dh
0x180007e09  add     rsp, 28h
0x180007e0d  pop     rdi
0x180007e0e  pop     rsi
0x180007e0f  pop     rbp
0x180007e10  pop     rbx
0x180007e11  retn
```
