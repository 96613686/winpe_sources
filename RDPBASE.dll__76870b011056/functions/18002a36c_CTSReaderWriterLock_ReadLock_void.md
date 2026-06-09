# CTSReaderWriterLock::ReadLock(void)

- ea: `0x18002a36c`
- end: `0x18002a435`
- name: `?ReadLock@CTSReaderWriterLock@@QEAAXXZ`
- size: `201`
- prototype: `void __fastcall(CTSReaderWriterLock *__hidden this)`
- caller_count: `42`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180029ed0`
- `0x18002a198`
- `0x18002a2d0`
- `0x180048670`
- `0x180067c8c`
- `0x180068cb0`
- `0x180068e70`
- `0x1800693f0`
- `0x18006ae14`
- `0x18006bcf8`
- `0x18006d400`
- `0x1800ba3b0`
- `0x1800ba550`
- `0x1800bb100`
- `0x1800bb330`
- `0x1800be9e0`
- `0x1800cfca0`
- `0x1800d0900`
- `0x1800d0c70`
- `0x180119b4c`
- `0x180119d2c`
- `0x18011a510`
- `0x18011b0d0`
- `0x18011b500`
- `0x18011b6a0`
- `0x18011b8a0`
- `0x18011baa0`
- `0x18011c720`
- `0x18011c844`
- `0x18011d410`
- `0x18011d57c`
- `0x18012053c`
- `0x1801235e0`
- `0x1801241a0`
- `0x1801287d0`
- `0x180128840`
- `0x18012db7c`
- `0x18012dd30`
- `0x18012de70`
- `0x180144c40`
- `0x180148c44`
- `0x180149f14`

## callees

- `0x18002a36c`
- `0x18002a43c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18002a407`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x18002a407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a3a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a3a1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a413`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a413`

## pseudocode

```c
void __fastcall CTSReaderWriterLock::ReadLock(CTSReaderWriterLock *this)
{
  signed __int32 v1; // r8d
  DWORD v3; // esi
  double v4; // xmm0_8
  int v5; // ebx
  int v6; // r9d

  if ( (*(_DWORD *)this & 0xFFFF8000) != 0
    || (v1 = *(_DWORD *)this, v1 != _InterlockedCompareExchange((volatile signed __int32 *)this, v1 + 1, v1)) )
  {
    v3 = 0;
    v4 = *(double *)&`CTSReaderWriterLock::_RandomBackoffFactor'::`2'::s_aFactors[GetCurrentThreadId() % 0xD] * 4000.0;
LABEL_5:
    v5 = (int)v4;
    if ( (int)v4 > 10000 )
    {
      v5 = 10000;
    }
    else if ( v5 <= 100 )
    {
      v5 = 100;
    }
    while ( !(unsigned int)CTSReaderWriterLock::_TryReadLock(this) )
    {
      if ( v6 == 1 )
      {
        if ( !SwitchToThread() )
          Sleep(v3);
        v3 ^= 1u;
        v4 = (double)v5 * 0.5;
        goto LABEL_5;
      }
    }
  }
}

```

## disassembly

```asm
0x18002a36c  push    rbx
0x18002a36e  push    rsi
0x18002a36f  push    rdi
0x18002a370  push    r14
0x18002a372  sub     rsp, 28h
0x18002a376  mov     r8d, [rcx]
0x18002a379  mov     rdi, rcx
0x18002a37c  test    r8d, 0FFFF8000h
0x18002a383  jnz     short loc_18002A39F
0x18002a385  lea     edx, [r8+1]
0x18002a389  mov     eax, r8d
0x18002a38c  lock cmpxchg [rcx], edx
0x18002a390  cmp     r8d, eax
0x18002a393  jnz     short loc_18002A39F
0x18002a395  add     rsp, 28h
0x18002a399  pop     r14
0x18002a39b  pop     rdi
0x18002a39c  pop     rsi
0x18002a39d  pop     rbx
0x18002a39e  retn
0x18002a39f  xor     esi, esi
0x18002a3a1  call    cs:__imp_GetCurrentThreadId
0x18002a3a7  mov     r8d, eax
0x18002a3aa  mov     eax, 4EC4EC4Fh
0x18002a3af  lea     r14d, [rsi+64h]
0x18002a3b3  mul     r8d
0x18002a3b6  shr     edx, 2
0x18002a3b9  imul    ecx, edx, 0Dh
0x18002a3bc  sub     r8d, ecx
0x18002a3bf  lea     rcx, ?s_aFactors@?1??_RandomBackoffFactor@CTSReaderWriterLock@@AEAANXZ@4QBNB; double const near * const `CTSReaderWriterLock::_RandomBackoffFactor(void)'::`2'::s_aFactors
0x18002a3c6  movsd   xmm0, qword ptr [rcx+r8*8]
0x18002a3cc  mulsd   xmm0, cs:__real@40af400000000000
0x18002a3d4  cvttsd2si ebx, xmm0
0x18002a3d8  cmp     ebx, 2710h
0x18002a3de  jg      short loc_18002A42E
0x18002a3e0  cmp     ebx, r14d
0x18002a3e3  cmovle  ebx, r14d
0x18002a3e7  cmp     dword ptr [rdi+0Ch], 0
0x18002a3eb  mov     r9d, 1
0x18002a3f1  cmovnz  r9d, ebx
0x18002a3f5  mov     rcx, rdi; this
0x18002a3f8  call    ?_TryReadLock@CTSReaderWriterLock@@AEAAHXZ; CTSReaderWriterLock::_TryReadLock(void)
0x18002a3fd  test    eax, eax
0x18002a3ff  jnz     short loc_18002A395
0x18002a401  sub     r9d, 1
0x18002a405  jnz     short loc_18002A3F5
0x18002a407  call    cs:__imp_SwitchToThread
0x18002a40d  test    eax, eax
0x18002a40f  jnz     short loc_18002A419
0x18002a411  mov     ecx, esi; dwMilliseconds
0x18002a413  call    cs:__imp_Sleep
0x18002a419  movd    xmm0, ebx
0x18002a41d  xor     esi, 1
0x18002a420  cvtdq2pd xmm0, xmm0
0x18002a424  mulsd   xmm0, cs:__real@3fe0000000000000
0x18002a42c  jmp     short loc_18002A3D4
0x18002a42e  mov     ebx, 2710h
0x18002a433  jmp     short loc_18002A3E7
```
