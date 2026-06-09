# UTSemReadWriteES::UnlockRead(void)

- ea: `0x18000e050`
- end: `0x18000e15c`
- name: `?UnlockRead@UTSemReadWriteES@@QEAAXXZ`
- size: `268`
- prototype: `void __fastcall(UTSemReadWriteES *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000dc70`
- `0x18000e330`
- `0x18001cb30`
- `0x180024ac0`
- `0x1800254b4`
- `0x180025870`
- `0x180040330`

## callees

- `0x18000e050`
- `0x180012654`
- `0x180028c88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e151`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e151`

## string_xrefs

- `0x18000e0a1`: `com\complus\src\events\shared\utsem.cpp`
- `0x18000e0c1`: `com\complus\src\events\shared\utsem.cpp`
- `0x18000e0ff`: `com\complus\src\events\shared\utsem.cpp`
- `0x18000e125`: `com\complus\src\events\shared\utsem.cpp`
- `0x18000e095`: `(m_dwFlag & READERS_MASK) != 0`
- `0x18000e0b5`: `(m_dwFlag & WRITERS_MASK) == 0`
- `0x18000e0f3`: `(dwFlag & READERS_MASK) == READERS_INCR`
- `0x18000e119`: `(dwFlag & WRITEWAITERS_MASK) != 0`

## pseudocode

```c
void __fastcall UTSemReadWriteES::UnlockRead(UTSemReadWriteES *this)
{
  signed __int32 v2; // edi
  unsigned int v3; // eax
  void *v4; // rax

  if ( (*((_DWORD *)this + 1) & 0x3FF) == 0 )
    InternalAssert(L"com\\complus\\src\\events\\shared\\utsem.cpp", 0x1B3u, 0x10u, L"(m_dwFlag & READERS_MASK) != 0");
  if ( (*((_DWORD *)this + 1) & 0xC00) != 0 )
    InternalAssert(L"com\\complus\\src\\events\\shared\\utsem.cpp", 0x1B4u, 0x10u, L"(m_dwFlag & WRITERS_MASK) == 0");
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v2 = *((_DWORD *)this + 1);
        if ( v2 != 1 )
          break;
        if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 1, 0, 1) == 1 )
          return;
      }
      v3 = *((_DWORD *)this + 1) & 0x3FF;
      if ( v3 <= 1 )
        break;
      if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v2 - 1, v2) )
        return;
    }
    if ( v3 != 1 )
      InternalAssert(
        L"com\\complus\\src\\events\\shared\\utsem.cpp",
        0x1C8u,
        0x10u,
        L"(dwFlag & READERS_MASK) == READERS_INCR");
    if ( (v2 & 0xFFC00000) == 0 )
      InternalAssert(
        L"com\\complus\\src\\events\\shared\\utsem.cpp",
        0x1C9u,
        0x10u,
        L"(dwFlag & WRITEWAITERS_MASK) != 0");
  }
  while ( v2 != _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v2 - 4193281, v2) );
  v4 = UTSemReadWriteES::GetWriteWaiterEvent(this);
  SetEvent(v4);
}

```

## disassembly

```asm
0x18000e050  mov     [rsp+arg_8], rbx
0x18000e055  push    rdi
0x18000e056  sub     rsp, 20h
0x18000e05a  mov     eax, [rcx+4]
0x18000e05d  mov     rbx, rcx
0x18000e060  test    eax, 3FFh
0x18000e065  jz      short loc_18000E08F
0x18000e067  mov     eax, [rbx+4]
0x18000e06a  test    eax, 0C00h
0x18000e06f  jnz     short loc_18000E0AF
0x18000e071  mov     edi, [rbx+4]
0x18000e074  cmp     edi, 1
0x18000e077  jnz     short loc_18000E0CF
0x18000e079  xor     ecx, ecx
0x18000e07b  mov     eax, edi
0x18000e07d  lock cmpxchg [rbx+4], ecx
0x18000e082  jnz     short loc_18000E071
0x18000e084  mov     rbx, [rsp+28h+arg_8]
0x18000e089  add     rsp, 20h
0x18000e08d  pop     rdi
0x18000e08e  retn
0x18000e08f  mov     r8d, 10h; unsigned __int16
0x18000e095  lea     r9, aMDwflagReaders_0; "(m_dwFlag & READERS_MASK) != 0"
0x18000e09c  mov     edx, 1B3h; unsigned int
0x18000e0a1  lea     rcx, aComComplusSrcE_23; "com\\complus\\src\\events\\shared\\utse"...
0x18000e0a8  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18000e0ad  jmp     short loc_18000E067
0x18000e0af  mov     r8d, 10h; unsigned __int16
0x18000e0b5  lea     r9, aMDwflagWriters; "(m_dwFlag & WRITERS_MASK) == 0"
0x18000e0bc  mov     edx, 1B4h; unsigned int
0x18000e0c1  lea     rcx, aComComplusSrcE_23; "com\\complus\\src\\events\\shared\\utse"...
0x18000e0c8  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18000e0cd  jmp     short loc_18000E071
0x18000e0cf  mov     eax, edi
0x18000e0d1  and     eax, 3FFh
0x18000e0d6  cmp     eax, 1
0x18000e0d9  jbe     short loc_18000E0EB
0x18000e0db  lea     ecx, [rdi-1]
0x18000e0de  mov     eax, edi
0x18000e0e0  lock cmpxchg [rbx+4], ecx
0x18000e0e5  cmp     edi, eax
0x18000e0e7  jnz     short loc_18000E071
0x18000e0e9  jmp     short loc_18000E084
0x18000e0eb  jz      short loc_18000E10B
0x18000e0ed  mov     r8d, 10h; unsigned __int16
0x18000e0f3  lea     r9, aDwflagReadersM; "(dwFlag & READERS_MASK) == READERS_INCR"
0x18000e0fa  mov     edx, 1C8h; unsigned int
0x18000e0ff  lea     rcx, aComComplusSrcE_23; "com\\complus\\src\\events\\shared\\utse"...
0x18000e106  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18000e10b  test    edi, 0FFC00000h
0x18000e111  jnz     short loc_18000E131
0x18000e113  mov     r8d, 10h; unsigned __int16
0x18000e119  lea     r9, aDwflagWritewai; "(dwFlag & WRITEWAITERS_MASK) != 0"
0x18000e120  mov     edx, 1C9h; unsigned int
0x18000e125  lea     rcx, aComComplusSrcE_23; "com\\complus\\src\\events\\shared\\utse"...
0x18000e12c  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18000e131  lea     ecx, [rdi-3FFC01h]
0x18000e137  mov     eax, edi
0x18000e139  lock cmpxchg [rbx+4], ecx
0x18000e13e  cmp     edi, eax
0x18000e140  jnz     loc_18000E071
0x18000e146  mov     rcx, rbx; this
0x18000e149  call    ?GetWriteWaiterEvent@UTSemReadWriteES@@AEAAPEAXXZ; UTSemReadWriteES::GetWriteWaiterEvent(void)
0x18000e14e  mov     rcx, rax; hEvent
0x18000e151  call    cs:__imp_SetEvent
0x18000e157  jmp     loc_18000E084
```
