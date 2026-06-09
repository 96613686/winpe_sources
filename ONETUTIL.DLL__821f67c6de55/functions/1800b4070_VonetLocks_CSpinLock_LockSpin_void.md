# VonetLocks::CSpinLock::_LockSpin(void)

- ea: `0x1800b4070`
- end: `0x1800b41eb`
- name: `?_LockSpin@CSpinLock@VonetLocks@@AEAAXXZ`
- size: `379`
- prototype: `void __fastcall(VonetLocks::CSpinLock *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004220`
- `0x1800042b0`
- `0x180004310`

## callees

- `0x1800b4070`

## import_xrefs

- `KERNEL32!SwitchToThread` at `0x1800b4104`
- `KERNEL32!SwitchToThread` at `0x1800b416a`
- `KERNEL32!SwitchToThread` at `0x1800b4104`
- `KERNEL32!SwitchToThread` at `0x1800b416a`
- `KERNEL32!Sleep` at `0x1800b4110`
- `KERNEL32!Sleep` at `0x1800b4176`
- `KERNEL32!Sleep` at `0x1800b4110`
- `KERNEL32!Sleep` at `0x1800b4176`
- `KERNEL32!GetCurrentThreadId` at `0x1800b409d`
- `KERNEL32!GetCurrentThreadId` at `0x1800b419e`
- `KERNEL32!GetCurrentThreadId` at `0x1800b409d`
- `KERNEL32!GetCurrentThreadId` at `0x1800b419e`

## pseudocode

```c
void __fastcall VonetLocks::CSpinLock::_LockSpin(VonetLocks::CSpinLock *this)
{
  char v1; // bp
  DWORD v3; // edi
  unsigned int v4; // ebx
  unsigned int v5; // r14d
  unsigned int v6; // ecx
  __m128i v7; // xmm0
  int v8; // eax
  bool v9; // cl
  char v10; // [rsp+58h] [rbp+10h]

  v1 = 0;
  v10 = 0;
  v3 = 0;
  v4 = 0;
  v5 = (int)((double)VonetLocks::CSpinLock::sm_wDefaultSpinCount
           * *(double *)&qword_18018AF20[GetCurrentThreadId() % 0xD]);
  do
  {
    if ( VonetLocks::CSpinLock::sm_wDefaultSpinCount )
    {
      v6 = v5;
      if ( *(_DWORD *)this )
      {
        do
        {
          if ( (--v6 & 0x80000000) != 0 )
          {
            if ( v3 || !SwitchToThread() )
              Sleep(v3);
            v7 = _mm_cvtsi32_si128(v5);
            v5 = 100;
            v8 = (int)(_mm_cvtepi32_pd(v7).m128d_f64[0] * VonetLocks::CSpinLock::sm_dblDfltSpinAdjFctr);
            if ( v8 > 10000 )
              v8 = 10000;
            if ( v8 > 100 )
              v5 = v8;
            v6 = v5;
            if ( v4 < 4 )
              v3 = dword_18018AF08[v4];
            else
              v3 = 100;
          }
        }
        while ( *(_DWORD *)this );
        v1 = v10;
      }
    }
    else
    {
      if ( v3 || !SwitchToThread() )
        Sleep(v3);
      if ( v4 < 4 )
        v3 = dword_18018AF08[v4];
      else
        v3 = 100;
    }
    if ( *(_DWORD *)this )
      v9 = 0;
    else
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFFC | 1, 0) == 0;
    if ( v9 )
      v1 = 1;
    ++v4;
    v10 = v1;
  }
  while ( !v1 );
}

```

## disassembly

```asm
0x1800b4070  mov     [rsp+arg_0], rbx
0x1800b4075  mov     [rsp+arg_10], rbp
0x1800b407a  push    rsi
0x1800b407b  push    rdi
0x1800b407c  push    r13
0x1800b407e  push    r14
0x1800b4080  push    r15
0x1800b4082  sub     rsp, 20h
0x1800b4086  movzx   ebx, cs:?sm_wDefaultSpinCount@CSpinLock@VonetLocks@@1GA; ushort VonetLocks::CSpinLock::sm_wDefaultSpinCount
0x1800b408d  xor     r15d, r15d
0x1800b4090  mov     bpl, r15b
0x1800b4093  mov     rsi, rcx
0x1800b4096  mov     [rsp+48h+arg_8], ebp
0x1800b409a  mov     edi, r15d
0x1800b409d  call    cs:GetCurrentThreadId
0x1800b40a3  movd    xmm0, ebx
0x1800b40a7  lea     rcx, __ImageBase
0x1800b40ae  mov     r9d, eax
0x1800b40b1  lea     r13d, [r15+1]
0x1800b40b5  mov     eax, 4EC4EC4Fh
0x1800b40ba  mov     ebx, r15d
0x1800b40bd  mul     r9d
0x1800b40c0  cvtdq2pd xmm0, xmm0
0x1800b40c4  shr     edx, 2
0x1800b40c7  imul    r8d, edx, 0Dh
0x1800b40cb  sub     r9d, r8d
0x1800b40ce  mulsd   xmm0, ds:rva qword_18018AF20[rcx+r9*8]
0x1800b40d8  cvttsd2si r14d, xmm0
0x1800b40dd  cmp     cs:?sm_wDefaultSpinCount@CSpinLock@VonetLocks@@1GA, r15w; ushort VonetLocks::CSpinLock::sm_wDefaultSpinCount
0x1800b40e5  jz      short loc_1800B4166
0x1800b40e7  mov     eax, [rsi]
0x1800b40e9  mov     ecx, r14d
0x1800b40ec  test    eax, eax
0x1800b40ee  jz      loc_1800B4198
0x1800b40f4  lea     rbp, __ImageBase
0x1800b40fb  sub     ecx, r13d
0x1800b40fe  jns     short loc_1800B415A
0x1800b4100  test    edi, edi
0x1800b4102  jnz     short loc_1800B410E
0x1800b4104  call    cs:SwitchToThread
0x1800b410a  test    eax, eax
0x1800b410c  jnz     short loc_1800B4116
0x1800b410e  mov     ecx, edi; dwMilliseconds
0x1800b4110  call    cs:Sleep
0x1800b4116  movd    xmm0, r14d
0x1800b411b  mov     edx, 2710h
0x1800b4120  mov     r14d, 64h ; 'd'
0x1800b4126  cvtdq2pd xmm0, xmm0
0x1800b412a  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CSpinLock@VonetLocks@@1NA; double VonetLocks::CSpinLock::sm_dblDfltSpinAdjFctr
0x1800b4132  cvttsd2si eax, xmm0
0x1800b4136  cmp     eax, edx
0x1800b4138  cmovg   eax, edx
0x1800b413b  cmp     eax, r14d
0x1800b413e  cmovg   r14d, eax
0x1800b4142  mov     ecx, r14d
0x1800b4145  cmp     ebx, 4
0x1800b4148  jb      short loc_1800B4151
0x1800b414a  mov     edi, 64h ; 'd'
0x1800b414f  jmp     short loc_1800B415A
0x1800b4151  mov     eax, ebx
0x1800b4153  mov     edi, ss:rva dword_18018AF08[rbp+rax*4]
0x1800b415a  mov     eax, [rsi]
0x1800b415c  test    eax, eax
0x1800b415e  jnz     short loc_1800B40FB
0x1800b4160  mov     ebp, [rsp+48h+arg_8]
0x1800b4164  jmp     short loc_1800B4198
0x1800b4166  test    edi, edi
0x1800b4168  jnz     short loc_1800B4174
0x1800b416a  call    cs:SwitchToThread
0x1800b4170  test    eax, eax
0x1800b4172  jnz     short loc_1800B417C
0x1800b4174  mov     ecx, edi; dwMilliseconds
0x1800b4176  call    cs:Sleep
0x1800b417c  cmp     ebx, 4
0x1800b417f  jb      short loc_1800B4188
0x1800b4181  mov     edi, 64h ; 'd'
0x1800b4186  jmp     short loc_1800B4198
0x1800b4188  mov     eax, ebx
0x1800b418a  lea     rcx, __ImageBase
0x1800b4191  mov     edi, ds:rva dword_18018AF08[rcx+rax*4]
0x1800b4198  mov     eax, [rsi]
0x1800b419a  test    eax, eax
0x1800b419c  jnz     short loc_1800B41B7
0x1800b419e  call    cs:GetCurrentThreadId
0x1800b41a4  mov     ecx, eax
0x1800b41a6  and     ecx, 0FFFFFFFDh
0x1800b41a9  or      ecx, r13d
0x1800b41ac  xor     eax, eax
0x1800b41ae  lock cmpxchg [rsi], ecx
0x1800b41b2  setz    cl
0x1800b41b5  jmp     short loc_1800B41BA
0x1800b41b7  mov     cl, r15b
0x1800b41ba  test    cl, cl
0x1800b41bc  movzx   ebp, bpl
0x1800b41c0  cmovnz  ebp, r13d
0x1800b41c4  add     ebx, r13d
0x1800b41c7  mov     [rsp+48h+arg_8], ebp
0x1800b41cb  test    bpl, bpl
0x1800b41ce  jz      loc_1800B40DD
0x1800b41d4  mov     rbx, [rsp+48h+arg_0]
0x1800b41d9  mov     rbp, [rsp+48h+arg_10]
0x1800b41de  add     rsp, 20h
0x1800b41e2  pop     r15
0x1800b41e4  pop     r14
0x1800b41e6  pop     r13
0x1800b41e8  pop     rdi
0x1800b41e9  pop     rsi
0x1800b41ea  retn
```
