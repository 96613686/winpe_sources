# CTSReaderWriterLock::_TryWriteLock(long)

- ea: `0x180043f18`
- end: `0x180043fcc`
- name: `?_TryWriteLock@CTSReaderWriterLock@@AEAAHJ@Z`
- size: `180`
- prototype: `__int64 __fastcall(CTSReaderWriterLock *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180043ecc`
- `0x180082804`

## callees

- `0x180043f18`
- `0x180043fd4`

## import_xrefs

- `RDPBASE!PAL_System_ThreadGetId` at `0x180043f5c`
- `RDPBASE!PAL_System_ThreadGetId` at `0x180043fa6`
- `RDPBASE!PAL_System_ThreadGetId` at `0x180043f5c`
- `RDPBASE!PAL_System_ThreadGetId` at `0x180043fa6`
- `RDPBASE!PAL_System_AtomicCompareAndExchange` at `0x180043f6d`
- `RDPBASE!PAL_System_AtomicCompareAndExchange` at `0x180043f81`
- `RDPBASE!PAL_System_AtomicCompareAndExchange` at `0x180043f6d`
- `RDPBASE!PAL_System_AtomicCompareAndExchange` at `0x180043f81`
- `RDPBASE!PAL_System_AtomicIncrement` at `0x180043fbb`
- `RDPBASE!PAL_System_AtomicIncrement` at `0x180043fbb`

## pseudocode

```c
__int64 __fastcall CTSReaderWriterLock::_TryWriteLock(CTSReaderWriterLock *this, int a2)
{
  unsigned int v3; // ebx
  unsigned int v4; // ebx
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 1)
    || (unsigned __int16)*(_DWORD *)this
    || !(unsigned int)CTSReaderWriterLock::_CmpExch(this, (*(_DWORD *)this + a2) | 0xFFFFu, *(_DWORD *)this) )
  {
    v6 = 0;
    PAL_System_ThreadGetId(&v6);
    if ( *((_DWORD *)this + 1) == v6 )
    {
      PAL_System_AtomicIncrement((char *)this + 8);
      return 1;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    v3 = *((_DWORD *)this + 1);
    v6 = 0;
    PAL_System_ThreadGetId(&v6);
    PAL_System_AtomicCompareAndExchange((char *)this + 4, v6, v3);
    v4 = 1;
    PAL_System_AtomicCompareAndExchange((char *)this + 8, 1, *((unsigned int *)this + 2));
  }
  return v4;
}

```

## disassembly

```asm
0x180043f18  mov     [rsp+arg_8], rbx
0x180043f1d  mov     [rsp+arg_10], rsi
0x180043f22  push    rdi
0x180043f23  sub     rsp, 20h
0x180043f27  mov     eax, [rcx+4]
0x180043f2a  mov     rdi, rcx
0x180043f2d  test    eax, eax
0x180043f2f  jnz     short loc_180043F99
0x180043f31  mov     r8d, [rcx]; int
0x180043f34  test    r8w, r8w
0x180043f38  jnz     short loc_180043F99
0x180043f3a  add     edx, r8d
0x180043f3d  or      edx, 0FFFFh; int
0x180043f43  call    ?_CmpExch@CTSReaderWriterLock@@AEAAHJJ@Z; CTSReaderWriterLock::_CmpExch(long,long)
0x180043f48  test    eax, eax
0x180043f4a  jz      short loc_180043F99
0x180043f4c  mov     ebx, [rdi+4]
0x180043f4f  lea     rcx, [rsp+28h+arg_0]
0x180043f54  mov     [rsp+28h+arg_0], 0
0x180043f5c  call    cs:__imp_PAL_System_ThreadGetId
0x180043f62  mov     edx, [rsp+28h+arg_0]
0x180043f66  lea     rcx, [rdi+4]
0x180043f6a  mov     r8d, ebx
0x180043f6d  call    cs:__imp_PAL_System_AtomicCompareAndExchange
0x180043f73  lea     rcx, [rdi+8]
0x180043f77  mov     ebx, 1
0x180043f7c  mov     r8d, [rcx]
0x180043f7f  mov     edx, ebx
0x180043f81  call    cs:__imp_PAL_System_AtomicCompareAndExchange
0x180043f87  mov     rsi, [rsp+28h+arg_10]
0x180043f8c  mov     eax, ebx
0x180043f8e  mov     rbx, [rsp+28h+arg_8]
0x180043f93  add     rsp, 20h
0x180043f97  pop     rdi
0x180043f98  retn
0x180043f99  lea     rcx, [rsp+28h+arg_0]
0x180043f9e  mov     [rsp+28h+arg_0], 0
0x180043fa6  call    cs:__imp_PAL_System_ThreadGetId
0x180043fac  mov     ecx, [rsp+28h+arg_0]
0x180043fb0  mov     eax, [rdi+4]
0x180043fb3  cmp     eax, ecx
0x180043fb5  jnz     short loc_180043FC8
0x180043fb7  lea     rcx, [rdi+8]
0x180043fbb  call    cs:__imp_PAL_System_AtomicIncrement
0x180043fc1  mov     ebx, 1
0x180043fc6  jmp     short loc_180043F87
0x180043fc8  xor     ebx, ebx
0x180043fca  jmp     short loc_180043F87
```
