# CTSReaderWriterLock::_LockSpin(CTSReaderWriterLock::SPIN_TYPE)

- ea: `0x180082804`
- end: `0x180082903`
- name: `?_LockSpin@CTSReaderWriterLock@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `255`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180043ecc`
- `0x180082560`

## callees

- `0x180043f18`
- `0x180043fd4`
- `0x180082804`
- `0x18008290c`

## import_xrefs

- `RDPBASE!PAL_System_ThreadGetId` at `0x180082822`
- `RDPBASE!PAL_System_ThreadGetId` at `0x180082822`
- `RDPBASE!PAL_System_SwitchToThread` at `0x1800828cc`
- `RDPBASE!PAL_System_SwitchToThread` at `0x1800828cc`
- `RDPBASE!PAL_System_Sleep` at `0x1800828d8`
- `RDPBASE!PAL_System_Sleep` at `0x1800828d8`

## pseudocode

```c
__int64 __fastcall CTSReaderWriterLock::_LockSpin(CTSReaderWriterLock *a1, int a2)
{
  unsigned int v3; // ebp
  double v5; // xmm0_8
  int v6; // ebx
  int v7; // edi
  __int64 result; // rax
  unsigned int v9; // [rsp+68h] [rbp+10h] BYREF

  v3 = 0;
  v9 = 0;
  PAL_System_ThreadGetId(&v9);
  v5 = *(double *)&`CTSReaderWriterLock::_RandomBackoffFactor'::`2'::s_aFactors[v9 % 0xD] * 4000.0;
LABEL_2:
  v6 = (int)v5;
  if ( (int)v5 <= 10000 )
  {
    if ( v6 <= 100 )
      v6 = 100;
  }
  else
  {
    v6 = 10000;
  }
  v7 = 1;
  if ( *((_DWORD *)a1 + 3) )
    v7 = v6;
  while ( 1 )
  {
    if ( a2 == 1 )
    {
      result = CTSReaderWriterLock::_TryWriteLock(a1, 0);
    }
    else if ( a2 == 2 )
    {
      result = CTSReaderWriterLock::_TryReadLock(a1);
    }
    else
    {
      result = (unsigned __int16)*(_DWORD *)a1 != 0xFFFF
            && (unsigned int)CTSReaderWriterLock::_CmpExch(a1, *(_DWORD *)a1 + 1, *(_DWORD *)a1);
    }
    if ( (_DWORD)result )
      return result;
    if ( !--v7 )
    {
      if ( !(unsigned int)PAL_System_SwitchToThread() )
        PAL_System_Sleep(v3);
      v3 ^= 1u;
      v5 = (double)v6 * 0.5;
      goto LABEL_2;
    }
  }
}

```

## disassembly

```asm
0x180082804  push    rbx
0x180082806  push    rbp
0x180082807  push    rsi
0x180082808  push    rdi
0x180082809  push    r13
0x18008280b  push    r14
0x18008280d  sub     rsp, 28h
0x180082811  mov     rsi, rcx
0x180082814  xor     ebp, ebp
0x180082816  lea     rcx, [rsp+58h+arg_8]
0x18008281b  mov     [rsp+58h+arg_8], ebp
0x18008281f  mov     r14d, edx
0x180082822  call    cs:__imp_PAL_System_ThreadGetId
0x180082828  mov     r8d, [rsp+58h+arg_8]
0x18008282d  lea     rcx, ?s_aFactors@?1??_RandomBackoffFactor@CTSReaderWriterLock@@AEAANXZ@4QBNB; double const near * const `CTSReaderWriterLock::_RandomBackoffFactor(void)'::`2'::s_aFactors
0x180082834  mov     eax, 4EC4EC4Fh
0x180082839  lea     r13d, [rbp+64h]
0x18008283d  mul     r8d
0x180082840  shr     edx, 2
0x180082843  imul    eax, edx, 0Dh
0x180082846  sub     r8d, eax
0x180082849  movsd   xmm0, qword ptr [rcx+r8*8]
0x18008284f  mulsd   xmm0, cs:__real@40af400000000000
0x180082857  cvttsd2si ebx, xmm0
0x18008285b  cmp     ebx, 2710h
0x180082861  jle     short loc_18008286A
0x180082863  mov     ebx, 2710h
0x180082868  jmp     short loc_180082871
0x18008286a  cmp     ebx, r13d
0x18008286d  cmovle  ebx, r13d
0x180082871  cmp     dword ptr [rsi+0Ch], 0
0x180082875  mov     edi, 1
0x18008287a  cmovnz  edi, ebx
0x18008287d  cmp     r14d, 1
0x180082881  jnz     short loc_18008288F
0x180082883  xor     edx, edx; int
0x180082885  mov     rcx, rsi; this
0x180082888  call    ?_TryWriteLock@CTSReaderWriterLock@@AEAAHJ@Z; CTSReaderWriterLock::_TryWriteLock(long)
0x18008288d  jmp     short loc_1800828C3
0x18008288f  cmp     r14d, 2
0x180082893  jnz     short loc_18008289F
0x180082895  mov     rcx, rsi; this
0x180082898  call    ?_TryReadLock@CTSReaderWriterLock@@AEAAHXZ; CTSReaderWriterLock::_TryReadLock(void)
0x18008289d  jmp     short loc_1800828C3
0x18008289f  mov     r8d, [rsi]; int
0x1800828a2  cmp     r8w, 0FFFFh
0x1800828a8  jz      short loc_1800828C1
0x1800828aa  lea     edx, [r8+1]; int
0x1800828ae  mov     rcx, rsi; this
0x1800828b1  call    ?_CmpExch@CTSReaderWriterLock@@AEAAHJJ@Z; CTSReaderWriterLock::_CmpExch(long,long)
0x1800828b6  test    eax, eax
0x1800828b8  jz      short loc_1800828C1
0x1800828ba  mov     eax, 1
0x1800828bf  jmp     short loc_1800828C3
0x1800828c1  xor     eax, eax
0x1800828c3  test    eax, eax
0x1800828c5  jnz     short loc_1800828F6
0x1800828c7  sub     edi, 1
0x1800828ca  jnz     short loc_18008287D
0x1800828cc  call    cs:__imp_PAL_System_SwitchToThread
0x1800828d2  test    eax, eax
0x1800828d4  jnz     short loc_1800828DE
0x1800828d6  mov     ecx, ebp
0x1800828d8  call    cs:__imp_PAL_System_Sleep
0x1800828de  movd    xmm0, ebx
0x1800828e2  xor     ebp, 1
0x1800828e5  cvtdq2pd xmm0, xmm0
0x1800828e9  mulsd   xmm0, cs:__real@3fe0000000000000
0x1800828f1  jmp     loc_180082857
0x1800828f6  add     rsp, 28h
0x1800828fa  pop     r14
0x1800828fc  pop     r13
0x1800828fe  pop     rdi
0x1800828ff  pop     rsi
0x180082900  pop     rbp
0x180082901  pop     rbx
0x180082902  retn
```
