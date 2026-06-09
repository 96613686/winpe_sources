# RegRow::UnlockRead(void)

- ea: `0x18001e970`
- end: `0x18001ea7f`
- name: `?UnlockRead@RegRow@@UEAAJXZ`
- size: `271`
- prototype: `__int64 __fastcall(RegRow *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180012654`
- `0x18001e970`
- `0x180028c88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001ea74`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001ea74`

## string_xrefs

- `0x18001e9c4`: `com\complus\src\events\shared\utsem.cpp`
- `0x18001e9e4`: `com\complus\src\events\shared\utsem.cpp`
- `0x18001ea22`: `com\complus\src\events\shared\utsem.cpp`
- `0x18001ea48`: `com\complus\src\events\shared\utsem.cpp`
- `0x18001e9b8`: `(m_dwFlag & READERS_MASK) != 0`
- `0x18001e9d8`: `(m_dwFlag & WRITERS_MASK) == 0`
- `0x18001ea16`: `(dwFlag & READERS_MASK) == READERS_INCR`
- `0x18001ea3c`: `(dwFlag & WRITEWAITERS_MASK) != 0`

## pseudocode

```c
__int64 __fastcall RegRow::UnlockRead(RegRow *this)
{
  volatile signed __int32 *v1; // rbx
  signed __int32 v2; // edi
  unsigned int v4; // eax
  void *v5; // rax

  v1 = (volatile signed __int32 *)((char *)this + 24);
  if ( (*((_DWORD *)this + 7) & 0x3FF) == 0 )
    InternalAssert(L"com\\complus\\src\\events\\shared\\utsem.cpp", 0x1B3u, 0x10u, L"(m_dwFlag & READERS_MASK) != 0");
  if ( (v1[1] & 0xC00) != 0 )
    InternalAssert(L"com\\complus\\src\\events\\shared\\utsem.cpp", 0x1B4u, 0x10u, L"(m_dwFlag & WRITERS_MASK) == 0");
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v2 = *((_DWORD *)v1 + 1);
        if ( v2 != 1 )
          break;
        if ( _InterlockedCompareExchange(v1 + 1, 0, 1) == 1 )
          return 0;
      }
      v4 = v1[1] & 0x3FF;
      if ( v4 <= 1 )
        break;
      if ( v2 == _InterlockedCompareExchange(v1 + 1, v2 - 1, v2) )
        return 0;
    }
    if ( v4 != 1 )
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
  while ( v2 != _InterlockedCompareExchange(v1 + 1, v2 - 4193281, v2) );
  v5 = UTSemReadWriteES::GetWriteWaiterEvent((UTSemReadWriteES *)v1);
  SetEvent(v5);
  return 0;
}

```

## disassembly

```asm
0x18001e970  mov     [rsp+arg_8], rbx
0x18001e975  push    rdi
0x18001e976  sub     rsp, 20h
0x18001e97a  mov     eax, [rcx+1Ch]
0x18001e97d  lea     rbx, [rcx+18h]
0x18001e981  test    eax, 3FFh
0x18001e986  jz      short loc_18001E9B2
0x18001e988  mov     eax, [rbx+4]
0x18001e98b  test    eax, 0C00h
0x18001e990  jnz     short loc_18001E9D2
0x18001e992  mov     edi, [rbx+4]
0x18001e995  cmp     edi, 1
0x18001e998  jnz     short loc_18001E9F2
0x18001e99a  xor     ecx, ecx
0x18001e99c  mov     eax, edi
0x18001e99e  lock cmpxchg [rbx+4], ecx
0x18001e9a3  jnz     short loc_18001E992
0x18001e9a5  mov     rbx, [rsp+28h+arg_8]
0x18001e9aa  xor     eax, eax
0x18001e9ac  add     rsp, 20h
0x18001e9b0  pop     rdi
0x18001e9b1  retn
0x18001e9b2  mov     r8d, 10h; unsigned __int16
0x18001e9b8  lea     r9, aMDwflagReaders_0; "(m_dwFlag & READERS_MASK) != 0"
0x18001e9bf  mov     edx, 1B3h; unsigned int
0x18001e9c4  lea     rcx, aComComplusSrcE_23; "com\\complus\\src\\events\\shared\\utse"...
0x18001e9cb  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18001e9d0  jmp     short loc_18001E988
0x18001e9d2  mov     r8d, 10h; unsigned __int16
0x18001e9d8  lea     r9, aMDwflagWriters; "(m_dwFlag & WRITERS_MASK) == 0"
0x18001e9df  mov     edx, 1B4h; unsigned int
0x18001e9e4  lea     rcx, aComComplusSrcE_23; "com\\complus\\src\\events\\shared\\utse"...
0x18001e9eb  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18001e9f0  jmp     short loc_18001E992
0x18001e9f2  mov     eax, edi
0x18001e9f4  and     eax, 3FFh
0x18001e9f9  cmp     eax, 1
0x18001e9fc  jbe     short loc_18001EA0E
0x18001e9fe  lea     ecx, [rdi-1]
0x18001ea01  mov     eax, edi
0x18001ea03  lock cmpxchg [rbx+4], ecx
0x18001ea08  cmp     edi, eax
0x18001ea0a  jnz     short loc_18001E992
0x18001ea0c  jmp     short loc_18001E9A5
0x18001ea0e  jz      short loc_18001EA2E
0x18001ea10  mov     r8d, 10h; unsigned __int16
0x18001ea16  lea     r9, aDwflagReadersM; "(dwFlag & READERS_MASK) == READERS_INCR"
0x18001ea1d  mov     edx, 1C8h; unsigned int
0x18001ea22  lea     rcx, aComComplusSrcE_23; "com\\complus\\src\\events\\shared\\utse"...
0x18001ea29  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18001ea2e  test    edi, 0FFC00000h
0x18001ea34  jnz     short loc_18001EA54
0x18001ea36  mov     r8d, 10h; unsigned __int16
0x18001ea3c  lea     r9, aDwflagWritewai; "(dwFlag & WRITEWAITERS_MASK) != 0"
0x18001ea43  mov     edx, 1C9h; unsigned int
0x18001ea48  lea     rcx, aComComplusSrcE_23; "com\\complus\\src\\events\\shared\\utse"...
0x18001ea4f  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18001ea54  lea     ecx, [rdi-3FFC01h]
0x18001ea5a  mov     eax, edi
0x18001ea5c  lock cmpxchg [rbx+4], ecx
0x18001ea61  cmp     edi, eax
0x18001ea63  jnz     loc_18001E992
0x18001ea69  mov     rcx, rbx; this
0x18001ea6c  call    ?GetWriteWaiterEvent@UTSemReadWriteES@@AEAAPEAXXZ; UTSemReadWriteES::GetWriteWaiterEvent(void)
0x18001ea71  mov     rcx, rax; hEvent
0x18001ea74  call    cs:__imp_SetEvent
0x18001ea7a  jmp     loc_18001E9A5
```
