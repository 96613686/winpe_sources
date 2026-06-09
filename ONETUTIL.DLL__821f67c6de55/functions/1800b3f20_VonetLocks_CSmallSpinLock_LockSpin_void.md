# VonetLocks::CSmallSpinLock::_LockSpin(void)

- ea: `0x1800b3f20`
- end: `0x1800b406b`
- name: `?_LockSpin@CSmallSpinLock@VonetLocks@@AEAAXXZ`
- size: `331`
- prototype: `void __fastcall(VonetLocks::CSmallSpinLock *__hidden this)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004050`
- `0x1800055d0`
- `0x180074cd0`
- `0x180074f70`
- `0x1800751b0`
- `0x180075520`
- `0x1800756c0`
- `0x180075ed0`
- `0x180076140`
- `0x180076300`
- `0x1800766e0`
- `0x180077420`
- `0x180077980`
- `0x180077f00`
- `0x180078030`

## callees

- `0x1800b3f20`

## import_xrefs

- `KERNEL32!SwitchToThread` at `0x1800b3fc9`
- `KERNEL32!SwitchToThread` at `0x1800b4021`
- `KERNEL32!SwitchToThread` at `0x1800b3fc9`
- `KERNEL32!SwitchToThread` at `0x1800b4021`
- `KERNEL32!Sleep` at `0x1800b3fd5`
- `KERNEL32!Sleep` at `0x1800b402d`
- `KERNEL32!Sleep` at `0x1800b3fd5`
- `KERNEL32!Sleep` at `0x1800b402d`
- `KERNEL32!GetCurrentThreadId` at `0x1800b3f49`
- `KERNEL32!GetCurrentThreadId` at `0x1800b3f81`
- `KERNEL32!GetCurrentThreadId` at `0x1800b3f99`
- `KERNEL32!GetCurrentThreadId` at `0x1800b3f49`
- `KERNEL32!GetCurrentThreadId` at `0x1800b3f81`
- `KERNEL32!GetCurrentThreadId` at `0x1800b3f99`

## pseudocode

```c
void __fastcall VonetLocks::CSmallSpinLock::_LockSpin(VonetLocks::CSmallSpinLock *this)
{
  __int64 v1; // rbx
  DWORD v3; // edi
  unsigned int v4; // ebp
  __int64 i; // rsi
  unsigned int v7; // ecx
  __m128i v8; // xmm0
  int v9; // eax

  v1 = VonetLocks::CSmallSpinLock::sm_wDefaultSpinCount;
  v3 = 0;
  v4 = (int)((double)(int)v1 * *(double *)&qword_18018AF20[GetCurrentThreadId() % 0xD]);
  GetCurrentThreadId();
  for ( i = 0;
        *(_DWORD *)this || _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId(), 0) != 0;
        i = (unsigned int)(i + 1) )
  {
    if ( v1 )
    {
      v7 = v4;
      while ( *(_DWORD *)this )
      {
        if ( (--v7 & 0x80000000) != 0 )
        {
          if ( v3 || !SwitchToThread() )
            Sleep(v3);
          v8 = _mm_cvtsi32_si128(v4);
          v3 = 100;
          v4 = 100;
          v9 = (int)(_mm_cvtepi32_pd(v8).m128d_f64[0] * VonetLocks::CSmallSpinLock::sm_dblDfltSpinAdjFctr);
          if ( v9 > 10000 )
            v9 = 10000;
          if ( v9 > 100 )
            v4 = v9;
          v7 = v4;
          if ( (unsigned int)i < 4 )
            v3 = dword_18018AF08[i];
        }
      }
    }
    else
    {
      if ( v3 || !SwitchToThread() )
        Sleep(v3);
      v3 = 100;
      if ( (unsigned int)i < 4 )
        v3 = dword_18018AF08[i];
    }
  }
}

```

## disassembly

```asm
0x1800b3f20  mov     rax, rsp
0x1800b3f23  mov     [rax+8], rbx
0x1800b3f27  mov     [rax+10h], rbp
0x1800b3f2b  mov     [rax+18h], rsi
0x1800b3f2f  mov     [rax+20h], rdi
0x1800b3f33  push    r12
0x1800b3f35  push    r13
0x1800b3f37  push    r14
0x1800b3f39  sub     rsp, 20h
0x1800b3f3d  movzx   ebx, cs:?sm_wDefaultSpinCount@CSmallSpinLock@VonetLocks@@1GA; ushort VonetLocks::CSmallSpinLock::sm_wDefaultSpinCount
0x1800b3f44  mov     r14, rcx
0x1800b3f47  xor     edi, edi
0x1800b3f49  call    cs:GetCurrentThreadId
0x1800b3f4f  movd    xmm0, ebx
0x1800b3f53  lea     r12, __ImageBase
0x1800b3f5a  mov     r9d, eax
0x1800b3f5d  mov     eax, 4EC4EC4Fh
0x1800b3f62  mul     r9d
0x1800b3f65  cvtdq2pd xmm0, xmm0
0x1800b3f69  shr     edx, 2
0x1800b3f6c  imul    r8d, edx, 0Dh
0x1800b3f70  sub     r9d, r8d
0x1800b3f73  mulsd   xmm0, ds:rva qword_18018AF20[r12+r9*8]
0x1800b3f7d  cvttsd2si ebp, xmm0
0x1800b3f81  call    cs:GetCurrentThreadId
0x1800b3f87  mov     eax, [r14]
0x1800b3f8a  xor     esi, esi
0x1800b3f8c  mov     r13d, 2710h
0x1800b3f92  mov     eax, [r14]
0x1800b3f95  test    eax, eax
0x1800b3f97  jnz     short loc_1800B3FAD
0x1800b3f99  call    cs:GetCurrentThreadId
0x1800b3f9f  mov     ecx, eax
0x1800b3fa1  xor     eax, eax
0x1800b3fa3  lock cmpxchg [r14], ecx
0x1800b3fa8  setz    cl
0x1800b3fab  jmp     short loc_1800B3FAF
0x1800b3fad  xor     cl, cl
0x1800b3faf  test    cl, cl
0x1800b3fb1  jnz     loc_1800B404C
0x1800b3fb7  test    rbx, rbx
0x1800b3fba  jz      short loc_1800B401D
0x1800b3fbc  mov     ecx, ebp
0x1800b3fbe  jmp     short loc_1800B4014
0x1800b3fc0  sub     ecx, 1
0x1800b3fc3  jns     short loc_1800B4014
0x1800b3fc5  test    edi, edi
0x1800b3fc7  jnz     short loc_1800B3FD3
0x1800b3fc9  call    cs:SwitchToThread
0x1800b3fcf  test    eax, eax
0x1800b3fd1  jnz     short loc_1800B3FDB
0x1800b3fd3  mov     ecx, edi; dwMilliseconds
0x1800b3fd5  call    cs:Sleep
0x1800b3fdb  movd    xmm0, ebp
0x1800b3fdf  mov     edi, 64h ; 'd'
0x1800b3fe4  mov     ebp, 64h ; 'd'
0x1800b3fe9  cvtdq2pd xmm0, xmm0
0x1800b3fed  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CSmallSpinLock@VonetLocks@@1NA; double VonetLocks::CSmallSpinLock::sm_dblDfltSpinAdjFctr
0x1800b3ff5  cvttsd2si eax, xmm0
0x1800b3ff9  cmp     eax, r13d
0x1800b3ffc  cmovg   eax, r13d
0x1800b4000  cmp     eax, ebp
0x1800b4002  cmovg   ebp, eax
0x1800b4005  mov     ecx, ebp
0x1800b4007  cmp     esi, 4
0x1800b400a  jnb     short loc_1800B4014
0x1800b400c  mov     edi, ds:rva dword_18018AF08[r12+rsi*4]
0x1800b4014  mov     eax, [r14]
0x1800b4017  test    eax, eax
0x1800b4019  jnz     short loc_1800B3FC0
0x1800b401b  jmp     short loc_1800B4045
0x1800b401d  test    edi, edi
0x1800b401f  jnz     short loc_1800B402B
0x1800b4021  call    cs:SwitchToThread
0x1800b4027  test    eax, eax
0x1800b4029  jnz     short loc_1800B4033
0x1800b402b  mov     ecx, edi; dwMilliseconds
0x1800b402d  call    cs:Sleep
0x1800b4033  mov     edi, 64h ; 'd'
0x1800b4038  cmp     esi, 4
0x1800b403b  jnb     short loc_1800B4045
0x1800b403d  mov     edi, ds:rva dword_18018AF08[r12+rsi*4]
0x1800b4045  inc     esi
0x1800b4047  jmp     loc_1800B3F92
0x1800b404c  mov     rbx, [rsp+38h+arg_0]
0x1800b4051  mov     rbp, [rsp+38h+arg_8]
0x1800b4056  mov     rsi, [rsp+38h+arg_10]
0x1800b405b  mov     rdi, [rsp+38h+arg_18]
0x1800b4060  add     rsp, 20h
0x1800b4064  pop     r14
0x1800b4066  pop     r13
0x1800b4068  pop     r12
0x1800b406a  retn
```
