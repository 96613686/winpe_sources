# UTSemReadWriteES::UnlockWrite(void)

- ea: `0x18000d15c`
- end: `0x18000d27d`
- name: `?UnlockWrite@UTSemReadWriteES@@QEAAXXZ`
- size: `289`
- prototype: `void __fastcall(UTSemReadWriteES *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bed0`
- `0x18000cab0`
- `0x18000cd8c`
- `0x18000cf88`
- `0x180040210`

## callees

- `0x18000d15c`
- `0x180012654`
- `0x180028c88`
- `0x180029130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d20c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d20c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000d1e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000d1e0`

## string_xrefs

- `0x18000d226`: `com\complus\src\events\shared\utsem.cpp`
- `0x18000d249`: `com\complus\src\events\shared\utsem.cpp`
- `0x18000d26c`: `com\complus\src\events\shared\utsem.cpp`
- `0x18000d23d`: `(m_dwFlag & WRITERS_MASK) == WRITERS_INCR`
- `0x18000d21a`: `(m_dwFlag & READERS_MASK) == 0`
- `0x18000d260`: `(dwFlag & WRITEWAITERS_MASK) != 0`

## pseudocode

```c
void __fastcall UTSemReadWriteES::UnlockWrite(UTSemReadWriteES *this)
{
  unsigned __int32 v2; // edi
  LONG v3; // esi
  void *WaiterSemaphore; // rax
  void *v5; // rax

  if ( (*((_DWORD *)this + 1) & 0x3FF) != 0 )
    InternalAssert(L"com\\complus\\src\\events\\shared\\utsem.cpp", 0x200u, 0x10u, L"(m_dwFlag & READERS_MASK) == 0");
  if ( (*((_DWORD *)this + 1) & 0xC00) != 0x400 )
    InternalAssert(
      L"com\\complus\\src\\events\\shared\\utsem.cpp",
      0x201u,
      0x10u,
      L"(m_dwFlag & WRITERS_MASK) == WRITERS_INCR");
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v2 = *((_DWORD *)this + 1);
        if ( v2 != 1024 )
          break;
        if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 1, 0, 1024) == 1024 )
          return;
      }
      if ( (v2 & 0x3FF000) == 0 )
        break;
      v3 = (v2 >> 12) & 0x3FF;
      if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v2 - 4095 * v3 - 1024, v2) )
      {
        WaiterSemaphore = UTSemReadWriteES::GetReadWaiterSemaphore(this);
        ReleaseSemaphore(WaiterSemaphore, v3, 0);
        return;
      }
    }
    if ( (v2 & 0xFFC00000) == 0 )
      InternalAssert(
        L"com\\complus\\src\\events\\shared\\utsem.cpp",
        0x21Au,
        0x10u,
        L"(dwFlag & WRITEWAITERS_MASK) != 0");
  }
  while ( v2 != _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v2 - 0x400000, v2) );
  v5 = UTSemReadWriteES::GetWriteWaiterEvent(this);
  SetEvent(v5);
}

```

## disassembly

```asm
0x18000d15c  push    rbx
0x18000d15e  push    rbp
0x18000d15f  push    rsi
0x18000d160  push    rdi
0x18000d161  sub     rsp, 28h
0x18000d165  mov     eax, [rcx+4]
0x18000d168  mov     rbx, rcx
0x18000d16b  test    eax, 3FFh
0x18000d170  jnz     loc_18000D214
0x18000d176  mov     eax, [rbx+4]
0x18000d179  mov     ebp, 400h
0x18000d17e  and     eax, 0C00h
0x18000d183  cmp     eax, ebp
0x18000d185  jnz     loc_18000D237
0x18000d18b  mov     edi, [rbx+4]
0x18000d18e  cmp     edi, ebp
0x18000d190  jnz     short loc_18000D1A6
0x18000d192  xor     ecx, ecx
0x18000d194  mov     eax, ebp
0x18000d196  lock cmpxchg [rbx+4], ecx
0x18000d19b  jnz     short loc_18000D18B
0x18000d19d  add     rsp, 28h
0x18000d1a1  pop     rdi
0x18000d1a2  pop     rsi
0x18000d1a3  pop     rbp
0x18000d1a4  pop     rbx
0x18000d1a5  retn
0x18000d1a6  test    edi, 3FF000h
0x18000d1ac  jz      short loc_18000D1E8
0x18000d1ae  mov     esi, edi
0x18000d1b0  mov     ecx, edi
0x18000d1b2  shr     esi, 0Ch
0x18000d1b5  and     esi, 3FFh
0x18000d1bb  imul    eax, esi, 0FFFh
0x18000d1c1  sub     ecx, eax
0x18000d1c3  mov     eax, edi
0x18000d1c5  sub     ecx, ebp
0x18000d1c7  lock cmpxchg [rbx+4], ecx
0x18000d1cc  cmp     edi, eax
0x18000d1ce  jnz     short loc_18000D18B
0x18000d1d0  mov     rcx, rbx; this
0x18000d1d3  call    ?GetReadWaiterSemaphore@UTSemReadWriteES@@AEAAPEAXXZ; UTSemReadWriteES::GetReadWaiterSemaphore(void)
0x18000d1d8  mov     rcx, rax; hSemaphore
0x18000d1db  xor     r8d, r8d; lpPreviousCount
0x18000d1de  mov     edx, esi; lReleaseCount
0x18000d1e0  call    cs:__imp_ReleaseSemaphore
0x18000d1e6  jmp     short loc_18000D19D
0x18000d1e8  test    edi, 0FFC00000h
0x18000d1ee  jz      short loc_18000D25A
0x18000d1f0  lea     ecx, [rdi-400000h]
0x18000d1f6  mov     eax, edi
0x18000d1f8  lock cmpxchg [rbx+4], ecx
0x18000d1fd  cmp     edi, eax
0x18000d1ff  jnz     short loc_18000D18B
0x18000d201  mov     rcx, rbx; this
0x18000d204  call    ?GetWriteWaiterEvent@UTSemReadWriteES@@AEAAPEAXXZ; UTSemReadWriteES::GetWriteWaiterEvent(void)
0x18000d209  mov     rcx, rax; hEvent
0x18000d20c  call    cs:__imp_SetEvent
0x18000d212  jmp     short loc_18000D19D
0x18000d214  mov     r8d, 10h; unsigned __int16
0x18000d21a  lea     r9, aMDwflagReaders; "(m_dwFlag & READERS_MASK) == 0"
0x18000d221  mov     edx, 200h; unsigned int
0x18000d226  lea     rcx, aComComplusSrcE_23; "com\\complus\\src\\events\\shared\\utse"...
0x18000d22d  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18000d232  jmp     loc_18000D176
0x18000d237  mov     r8d, 10h; unsigned __int16
0x18000d23d  lea     r9, aMDwflagWriters_0; "(m_dwFlag & WRITERS_MASK) == WRITERS_IN"...
0x18000d244  mov     edx, 201h; unsigned int
0x18000d249  lea     rcx, aComComplusSrcE_23; "com\\complus\\src\\events\\shared\\utse"...
0x18000d250  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18000d255  jmp     loc_18000D18B
0x18000d25a  mov     r8d, 10h; unsigned __int16
0x18000d260  lea     r9, aDwflagWritewai; "(dwFlag & WRITEWAITERS_MASK) != 0"
0x18000d267  mov     edx, 21Ah; unsigned int
0x18000d26c  lea     rcx, aComComplusSrcE_23; "com\\complus\\src\\events\\shared\\utse"...
0x18000d273  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18000d278  jmp     loc_18000D1F0
```
