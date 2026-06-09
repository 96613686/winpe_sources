# LKRhash::CLKRLinearHashTable::~CLKRLinearHashTable(void)

- ea: `0x180007e18`
- end: `0x180007f2f`
- name: `??1CLKRLinearHashTable@LKRhash@@QEAA@XZ`
- size: `279`
- prototype: `void __fastcall(LKRhash::CLKRLinearHashTable *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007a34`
- `0x180007d18`

## callees

- `0x180003ca0`
- `0x1800077fc`
- `0x180007e18`
- `0x1800089a4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180007e94`
- `KERNEL32!GetCurrentThreadId` at `0x180007eae`
- `KERNEL32!GetCurrentThreadId` at `0x180007e94`
- `KERNEL32!GetCurrentThreadId` at `0x180007eae`

## pseudocode

```c
void __fastcall LKRhash::CLKRLinearHashTable::~CLKRLinearHashTable(LKRhash::CLKRLinearHashTable *this)
{
  volatile __int32 *v2; // rdi
  int v3; // edx
  bool v4; // zf
  volatile __int32 v5; // edx
  _QWORD *v6; // rax
  __int64 v7; // rcx

  v2 = (volatile __int32 *)((char *)this + 24);
  if ( *((_BYTE *)this + 153) )
    CReaderWriterLock3::WriteLock((LKRhash::CLKRLinearHashTable *)((char *)this + 24));
  LKRhash::CLKRLinearHashTable::_Clear(this, 0);
  if ( *((_BYTE *)this + 153) )
  {
    v3 = *((_DWORD *)v2 + 1) - 1;
    v4 = (((*((_BYTE *)v2 + 4) - 1) & 3) != 0 ? v3 : 0) == 0;
    _InterlockedExchange(v2 + 1, ((*((_BYTE *)v2 + 4) - 1) & 3) != 0 ? v3 : 0);
    if ( v4 )
    {
      _m_prefetchw((const void *)v2);
      do
        v5 = *v2;
      while ( v5 != _InterlockedCompareExchange(v2, (*v2 - 0x10000) & 0xFFFF0000, *v2) );
    }
  }
  if ( !*((_QWORD *)this + 17) )
  {
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
    v6 = (_QWORD *)*((_QWORD *)this + 21);
    if ( v6 )
    {
      v7 = *((_QWORD *)this + 20);
      if ( v7 )
      {
        *v6 = v7;
        *(_QWORD *)(v7 + 8) = v6;
      }
    }
    _InterlockedExchange(
      (volatile __int32 *)&LKRhash::CLKRLinearHashTable::sm_llGlobalList,
      ((LKRhash::CLKRLinearHashTable::sm_llGlobalList - 1) & 3) != 0
    ? LKRhash::CLKRLinearHashTable::sm_llGlobalList - 1
    : 0);
  }
  *(_DWORD *)this = 2018265932;
  *((_DWORD *)this + 5) = -99;
}

```

## disassembly

```asm
0x180007e18  mov     [rsp+arg_8], rbx
0x180007e1d  push    rdi
0x180007e1e  sub     rsp, 20h
0x180007e22  mov     rbx, rcx
0x180007e25  lea     rdi, [rcx+18h]
0x180007e29  cmp     byte ptr [rcx+99h], 0
0x180007e30  jz      short loc_180007E3A
0x180007e32  mov     rcx, rdi; this
0x180007e35  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180007e3a  xor     edx, edx; bool
0x180007e3c  mov     rcx, rbx; this
0x180007e3f  call    ?_Clear@CLKRLinearHashTable@LKRhash@@AEAAX_N@Z; LKRhash::CLKRLinearHashTable::_Clear(bool)
0x180007e44  cmp     byte ptr [rbx+99h], 0
0x180007e4b  jz      short loc_180007E7C
0x180007e4d  mov     edx, [rdi+4]
0x180007e50  dec     edx
0x180007e52  mov     eax, edx
0x180007e54  and     al, 3
0x180007e56  neg     al
0x180007e58  sbb     ecx, ecx
0x180007e5a  and     ecx, edx
0x180007e5c  xchg    ecx, [rdi+4]
0x180007e5f  jnz     short loc_180007E7C
0x180007e61  prefetchw byte ptr [rdi]
0x180007e64  mov     edx, [rdi]
0x180007e66  lea     ecx, [rdx-10000h]
0x180007e6c  and     ecx, 0FFFF0000h
0x180007e72  mov     eax, edx
0x180007e74  lock cmpxchg [rdi], ecx
0x180007e78  cmp     edx, eax
0x180007e7a  jnz     short loc_180007E64
0x180007e7c  cmp     qword ptr [rbx+88h], 0
0x180007e84  jnz     loc_180007F17
0x180007e8a  mov     eax, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180007e90  test    eax, eax
0x180007e92  jnz     short loc_180007EAE
0x180007e94  call    cs:__imp_GetCurrentThreadId
0x180007e9a  mov     ecx, eax
0x180007e9c  and     ecx, 0FFFFFFFDh
0x180007e9f  or      ecx, 1
0x180007ea2  xor     eax, eax
0x180007ea4  lock cmpxchg cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A, ecx; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180007eac  jz      short loc_180007EE0
0x180007eae  call    cs:__imp_GetCurrentThreadId
0x180007eb4  and     eax, 0FFFFFFFCh
0x180007eb7  mov     ecx, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180007ebd  and     ecx, 0FFFFFFFCh
0x180007ec0  cmp     ecx, eax
0x180007ec2  jnz     short loc_180007ED4
0x180007ec4  mov     eax, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180007eca  inc     eax
0x180007ecc  xchg    eax, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180007ed2  jmp     short loc_180007EE0
0x180007ed4  lea     rcx, ?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; this
0x180007edb  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x180007ee0  mov     rax, [rbx+0A8h]
0x180007ee7  test    rax, rax
0x180007eea  jz      short loc_180007EFF
0x180007eec  mov     rcx, [rbx+0A0h]
0x180007ef3  test    rcx, rcx
0x180007ef6  jz      short loc_180007EFF
0x180007ef8  mov     [rax], rcx
0x180007efb  mov     [rcx+8], rax
0x180007eff  mov     edx, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180007f05  dec     edx
0x180007f07  mov     eax, edx
0x180007f09  and     al, 3
0x180007f0b  neg     al
0x180007f0d  sbb     ecx, ecx
0x180007f0f  and     ecx, edx
0x180007f11  xchg    ecx, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180007f17  mov     dword ptr [rbx], 784C4B4Ch
0x180007f1d  mov     dword ptr [rbx+14h], 0FFFFFF9Dh
0x180007f24  mov     rbx, [rsp+28h+arg_8]
0x180007f29  add     rsp, 20h
0x180007f2d  pop     rdi
0x180007f2e  retn
```
