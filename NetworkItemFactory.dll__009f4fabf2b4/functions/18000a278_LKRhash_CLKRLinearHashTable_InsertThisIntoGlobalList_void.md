# LKRhash::CLKRLinearHashTable::_InsertThisIntoGlobalList(void)

- ea: `0x18000a278`
- end: `0x18000a327`
- name: `?_InsertThisIntoGlobalList@CLKRLinearHashTable@LKRhash@@AEAAXXZ`
- size: `175`
- prototype: `void __fastcall(LKRhash::CLKRLinearHashTable *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800088a4`

## callees

- `0x1800077fc`
- `0x18000a278`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000a29d`
- `KERNEL32!GetCurrentThreadId` at `0x18000a2b7`
- `KERNEL32!GetCurrentThreadId` at `0x18000a29d`
- `KERNEL32!GetCurrentThreadId` at `0x18000a2b7`

## pseudocode

```c
void __fastcall LKRhash::CLKRLinearHashTable::_InsertThisIntoGlobalList(LKRhash::CLKRLinearHashTable *this)
{
  char *v1; // rbx
  _QWORD *v2; // rax

  if ( !*((_QWORD *)this + 17) )
  {
    v1 = (char *)this + 160;
    if ( LKRhash::CLKRLinearHashTable::sm_llGlobalList
      || _InterlockedCompareExchange(
           (volatile signed __int32 *)&LKRhash::CLKRLinearHashTable::sm_llGlobalList,
           GetCurrentThreadId() & 0xFFFFFFFC | 1,
           0) )
    {
      if ( (LKRhash::CLKRLinearHashTable::sm_llGlobalList & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
        _InterlockedExchange(
          (volatile __int32 *)&LKRhash::CLKRLinearHashTable::sm_llGlobalList,
          LKRhash::CLKRLinearHashTable::sm_llGlobalList + 1);
      else
        CSpinLock::_LockSpin((CSpinLock *)&LKRhash::CLKRLinearHashTable::sm_llGlobalList);
    }
    *((_QWORD *)v1 + 1) = &off_180011038;
    v2 = off_180011038;
    *(_QWORD *)v1 = off_180011038;
    v2[1] = v1;
    off_180011038 = v1;
    _InterlockedExchange(
      (volatile __int32 *)&LKRhash::CLKRLinearHashTable::sm_llGlobalList,
      ((LKRhash::CLKRLinearHashTable::sm_llGlobalList - 1) & 3) != 0
    ? LKRhash::CLKRLinearHashTable::sm_llGlobalList - 1
    : 0);
  }
}

```

## disassembly

```asm
0x18000a278  push    rbx
0x18000a27a  sub     rsp, 20h
0x18000a27e  cmp     qword ptr [rcx+88h], 0
0x18000a286  jnz     loc_18000A321
0x18000a28c  mov     eax, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x18000a292  lea     rbx, [rcx+0A0h]
0x18000a299  test    eax, eax
0x18000a29b  jnz     short loc_18000A2B7
0x18000a29d  call    cs:__imp_GetCurrentThreadId
0x18000a2a3  mov     ecx, eax
0x18000a2a5  and     ecx, 0FFFFFFFDh
0x18000a2a8  or      ecx, 1
0x18000a2ab  xor     eax, eax
0x18000a2ad  lock cmpxchg cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A, ecx; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x18000a2b5  jz      short loc_18000A2E9
0x18000a2b7  call    cs:__imp_GetCurrentThreadId
0x18000a2bd  mov     ecx, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x18000a2c3  and     eax, 0FFFFFFFCh
0x18000a2c6  and     ecx, 0FFFFFFFCh
0x18000a2c9  cmp     ecx, eax
0x18000a2cb  jnz     short loc_18000A2DD
0x18000a2cd  mov     eax, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x18000a2d3  inc     eax
0x18000a2d5  xchg    eax, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x18000a2db  jmp     short loc_18000A2E9
0x18000a2dd  lea     rcx, ?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; this
0x18000a2e4  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x18000a2e9  lea     rax, off_180011038
0x18000a2f0  mov     [rbx+8], rax
0x18000a2f4  mov     rax, cs:off_180011038
0x18000a2fb  mov     [rbx], rax
0x18000a2fe  mov     [rax+8], rbx
0x18000a302  mov     edx, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x18000a308  dec     edx
0x18000a30a  mov     cs:off_180011038, rbx
0x18000a311  mov     eax, edx
0x18000a313  and     al, 3
0x18000a315  neg     al
0x18000a317  sbb     ecx, ecx
0x18000a319  and     ecx, edx
0x18000a31b  xchg    ecx, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x18000a321  add     rsp, 20h
0x18000a325  pop     rbx
0x18000a326  retn
```
