# CacheWriter::AllocateDataAligned(uint,uint,uint *)

- ea: `0x18002c068`
- end: `0x18002c107`
- name: `?AllocateDataAligned@CacheWriter@@QEAAPEAXIIPEAI@Z`
- size: `159`
- prototype: `void *__fastcall(CacheWriter *__hidden this, unsigned int, unsigned int, unsigned int *)`
- caller_count: `23`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002a760`
- `0x18002aa00`
- `0x18002b050`
- `0x18002c110`
- `0x18002c984`
- `0x18002cce0`
- `0x18002ed40`
- `0x1800415e0`
- `0x1800423e0`
- `0x180054e80`
- `0x180054f90`
- `0x18005531c`
- `0x180055540`
- `0x180088cc0`
- `0x18008ae9c`
- `0x18008b490`
- `0x180095970`
- `0x180099f50`
- `0x18009ccc0`
- `0x1800c6460`
- `0x1800c65d0`
- `0x1800c673c`
- `0x1800c7a20`

## callees

- `0x18002c068`
- `0x18004385c`
- `0x180076ca4`
- `0x18008b1ac`
- `0x18008fe80`
- `0x18009e458`
- `0x1800a34b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c0c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c0c1`

## string_xrefs

- `0x18002c0d7`: `cachew`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int8 *__fastcall CacheWriter::AllocateDataAligned(
        CacheWriter *this,
        int a2,
        unsigned int a3,
        unsigned int *a4)
{
  unsigned int v8; // eax
  __int64 v9; // r14
  unsigned int v10; // edi
  unsigned __int8 *v11; // rbx
  __int64 v13; // rbx
  IntegerOverflowException *v14; // rax
  _BYTE v15[8]; // [rsp+20h] [rbp-48h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v17[56]; // [rsp+30h] [rbp-38h] BYREF

  LockHolder::LockHolder((LockHolder *)&lpCriticalSection, (CacheWriter *)((char *)this + 32));
  v8 = Align<unsigned int>(*(unsigned int *)(*((_QWORD *)this + 9) + 16LL), a3);
  v9 = v8;
  v10 = v8 + a2;
  if ( v10 < v8 )
  {
    v13 = *(_QWORD *)EventTag::EventTag((EventTag *)v17, (const char (*)[7])"cachew");
    v14 = IntegerOverflowException::IntegerOverflowException((IntegerOverflowException *)v15);
    LogAndThrow<IntegerOverflowException>(v14, v13, 465);
  }
  v11 = CacheWriter::GrowCommittedSize(this, v10);
  *(_DWORD *)(*((_QWORD *)this + 9) + 16LL) = v10;
  *a4 = v9;
  LeaveCriticalSection(lpCriticalSection);
  return &v11[v9];
}

```

## disassembly

```asm
0x18002c068  push    rbx
0x18002c06a  push    rsi
0x18002c06b  push    rdi
0x18002c06c  push    r14
0x18002c06e  push    r15
0x18002c070  sub     rsp, 40h
0x18002c074  mov     r15, r9
0x18002c077  mov     ebx, r8d
0x18002c07a  mov     edi, edx
0x18002c07c  mov     rsi, rcx
0x18002c07f  lea     rdx, [rcx+20h]; struct Lock *
0x18002c083  lea     rcx, [rsp+68h+lpCriticalSection]; this
0x18002c088  call    ??0LockHolder@@QEAA@AEAVLock@@@Z; LockHolder::LockHolder(Lock &)
0x18002c08d  nop
0x18002c08e  mov     edx, ebx
0x18002c090  mov     rcx, [rsi+48h]
0x18002c094  mov     ecx, [rcx+10h]
0x18002c097  call    ??$Align@I@@YAII_K@Z; Align<uint>(uint,unsigned __int64)
0x18002c09c  mov     r14d, eax
0x18002c09f  add     edi, eax
0x18002c0a1  cmp     edi, eax
0x18002c0a3  jb      short loc_18002C0D7
0x18002c0a5  mov     edx, edi; unsigned int
0x18002c0a7  mov     rcx, rsi; this
0x18002c0aa  call    ?GrowCommittedSize@CacheWriter@@AEAAPEAEI@Z; CacheWriter::GrowCommittedSize(uint)
0x18002c0af  mov     rbx, rax
0x18002c0b2  mov     rcx, [rsi+48h]
0x18002c0b6  mov     [rcx+10h], edi
0x18002c0b9  mov     [r15], r14d
0x18002c0bc  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x18002c0c1  call    cs:__imp_LeaveCriticalSection
0x18002c0c7  lea     rax, [rbx+r14]
0x18002c0cb  add     rsp, 40h
0x18002c0cf  pop     r15
0x18002c0d1  pop     r14
0x18002c0d3  pop     rdi
0x18002c0d4  pop     rsi
0x18002c0d5  pop     rbx
0x18002c0d6  retn
0x18002c0d7  lea     rdx, aCachew; "cachew"
0x18002c0de  lea     rcx, [rsp+68h+var_38]; this
0x18002c0e3  call    ??0EventTag@@QEAA@AEAY06$$CBD@Z; EventTag::EventTag(char const (&)[7])
0x18002c0e8  mov     rbx, [rax]
0x18002c0eb  lea     rcx, [rsp+68h+var_48]; this
0x18002c0f0  call    ??0IntegerOverflowException@@QEAA@XZ; IntegerOverflowException::IntegerOverflowException(void)
0x18002c0f5  mov     r8d, 1D1h
0x18002c0fb  mov     rdx, rbx
0x18002c0fe  mov     rcx, rax
0x18002c101  call    ??$LogAndThrow@VIntegerOverflowException@@@@YAXAEBVIntegerOverflowException@@VEventTag@@I@Z; LogAndThrow<IntegerOverflowException>(IntegerOverflowException const &,EventTag,uint)
```
