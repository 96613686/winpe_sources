# VonetLocks::CReaderWriterLock3::_LockSpin(VonetLocks::CReaderWriterLock3::SPIN_TYPE)

- ea: `0x1800b44f0`
- end: `0x1800b468a`
- name: `?_LockSpin@CReaderWriterLock3@VonetLocks@@AEAAXW4SPIN_TYPE@12@@Z`
- size: `410`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004cb0`
- `0x180004e30`
- `0x180004e60`
- `0x180005b90`
- `0x180005d80`
- `0x180005e60`
- `0x180075820`
- `0x180075a40`
- `0x180078450`
- `0x1800b0c70`
- `0x1800b33a8`
- `0x1800b3554`
- `0x1800b44b0`
- `0x1800fd780`

## callees

- `0x1800b44f0`

## import_xrefs

- `KERNEL32!SwitchToThread` at `0x1800b45dc`
- `KERNEL32!SwitchToThread` at `0x1800b45dc`
- `KERNEL32!Sleep` at `0x1800b45e8`
- `KERNEL32!Sleep` at `0x1800b45e8`
- `KERNEL32!GetCurrentThreadId` at `0x1800b4518`
- `KERNEL32!GetCurrentThreadId` at `0x1800b459a`
- `KERNEL32!GetCurrentThreadId` at `0x1800b465e`
- `KERNEL32!GetCurrentThreadId` at `0x1800b4518`
- `KERNEL32!GetCurrentThreadId` at `0x1800b459a`
- `KERNEL32!GetCurrentThreadId` at `0x1800b465e`

## pseudocode

```c
DWORD __fastcall VonetLocks::CReaderWriterLock3::_LockSpin(volatile signed __int32 *a1, int a2)
{
  DWORD v3; // edi
  DWORD CurrentThreadId; // eax
  unsigned __int16 v6; // cx
  unsigned int v7; // ebp
  unsigned int v8; // r14d
  DWORD result; // eax
  DWORD v10; // esi
  signed __int32 v11; // edx
  signed __int32 v12; // edx
  char v13; // cl
  __m128i v14; // xmm0
  int v15; // eax

  v3 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v6 = VonetLocks::CReaderWriterLock3::sm_wDefaultSpinCount;
  v7 = 0;
  v8 = (int)((double)VonetLocks::CReaderWriterLock3::sm_wDefaultSpinCount
           * *(double *)&qword_18018AF20[CurrentThreadId % 0xD]);
  while ( 1 )
  {
    result = v8;
    if ( !v6 )
      result = 1;
    v10 = result - 1;
    if ( (int)(result - 1) >= 0 )
      break;
LABEL_16:
    if ( v3 || !SwitchToThread() )
      Sleep(v3);
    if ( v7 < 4 )
      v3 = dword_18018AF08[v7];
    else
      v3 = 100;
    v6 = VonetLocks::CReaderWriterLock3::sm_wDefaultSpinCount;
    v14 = _mm_cvtsi32_si128(v8);
    v8 = 100;
    v15 = (int)(_mm_cvtepi32_pd(v14).m128d_f64[0] * VonetLocks::CReaderWriterLock3::sm_dblDfltSpinAdjFctr);
    if ( v15 > 10000 )
      v15 = 10000;
    if ( v15 > 100 )
      v8 = v15;
    ++v7;
  }
  while ( a2 != 1 )
  {
    v12 = *a1;
    if ( a2 == 2 )
    {
      if ( (v12 & 0xFFFF8000) != 0 )
        goto LABEL_13;
    }
    else if ( (_WORD)v12 == 0xFFFF )
    {
      goto LABEL_13;
    }
    result = _InterlockedCompareExchange(a1, v12 + 1, v12);
    if ( v12 == result )
      goto LABEL_23;
LABEL_13:
    v13 = 0;
LABEL_14:
    if ( v13 )
      return result;
    if ( (--v10 & 0x80000000) != 0 )
      goto LABEL_16;
  }
  if ( *((_DWORD *)a1 + 1)
    || (unsigned __int16)*a1
    || (v11 = *a1, v11 != _InterlockedCompareExchange(a1, v11 | 0xFFFF, v11)) )
  {
    result = GetCurrentThreadId();
    if ( ((result ^ *((_DWORD *)a1 + 1)) & 0xFFFFFFFC) == 0 )
    {
      result = _InterlockedExchange(a1 + 1, *((_DWORD *)a1 + 1) + 1);
LABEL_23:
      v13 = 1;
      goto LABEL_14;
    }
    goto LABEL_13;
  }
  return _InterlockedExchange(a1 + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
}

```

## disassembly

```asm
0x1800b44f0  mov     [rsp+arg_0], rbx
0x1800b44f5  mov     [rsp+arg_8], rbp
0x1800b44fa  mov     [rsp+arg_10], rsi
0x1800b44ff  push    rdi
0x1800b4500  push    r12
0x1800b4502  push    r13
0x1800b4504  push    r14
0x1800b4506  push    r15
0x1800b4508  sub     rsp, 20h
0x1800b450c  xor     r12d, r12d
0x1800b450f  mov     r15d, edx
0x1800b4512  mov     edi, r12d
0x1800b4515  mov     rbx, rcx
0x1800b4518  call    cs:GetCurrentThreadId
0x1800b451e  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@VonetLocks@@1GA; ushort VonetLocks::CReaderWriterLock3::sm_wDefaultSpinCount
0x1800b4525  lea     r13d, [r12+1]
0x1800b452a  mov     r9d, eax
0x1800b452d  mov     ebp, r12d
0x1800b4530  mov     eax, 4EC4EC4Fh
0x1800b4535  mul     r9d
0x1800b4538  movd    xmm0, ecx
0x1800b453c  cvtdq2pd xmm0, xmm0
0x1800b4540  shr     edx, 2
0x1800b4543  imul    r8d, edx, 0Dh
0x1800b4547  lea     rdx, __ImageBase
0x1800b454e  sub     r9d, r8d
0x1800b4551  mulsd   xmm0, ds:rva qword_18018AF20[rdx+r9*8]
0x1800b455b  cvttsd2si r14d, xmm0
0x1800b4560  test    cx, cx
0x1800b4563  mov     eax, r14d
0x1800b4566  cmovz   eax, r13d
0x1800b456a  lea     esi, [rax-1]
0x1800b456d  test    esi, esi
0x1800b456f  js      short loc_1800B45D8
0x1800b4571  cmp     r15d, r13d
0x1800b4574  jnz     short loc_1800B45B8
0x1800b4576  mov     eax, [rbx+4]
0x1800b4579  test    eax, eax
0x1800b457b  jnz     short loc_1800B459A
0x1800b457d  mov     edx, [rbx]
0x1800b457f  test    dx, dx
0x1800b4582  jnz     short loc_1800B459A
0x1800b4584  mov     ecx, edx
0x1800b4586  mov     eax, edx
0x1800b4588  or      ecx, 0FFFFh
0x1800b458e  lock cmpxchg [rbx], ecx
0x1800b4592  cmp     edx, eax
0x1800b4594  jz      loc_1800B465E
0x1800b459a  call    cs:GetCurrentThreadId
0x1800b45a0  mov     ecx, [rbx+4]
0x1800b45a3  xor     ecx, eax
0x1800b45a5  test    ecx, 0FFFFFFFCh
0x1800b45ab  jnz     short loc_1800B45C8
0x1800b45ad  mov     eax, [rbx+4]
0x1800b45b0  add     eax, r13d
0x1800b45b3  xchg    eax, [rbx+4]
0x1800b45b6  jmp     short loc_1800B460E
0x1800b45b8  mov     edx, [rbx]
0x1800b45ba  cmp     r15d, 2
0x1800b45be  jnz     short loc_1800B45FA
0x1800b45c0  test    edx, 0FFFF8000h
0x1800b45c6  jz      short loc_1800B4601
0x1800b45c8  mov     cl, r12b
0x1800b45cb  test    cl, cl
0x1800b45cd  jnz     loc_1800B466D
0x1800b45d3  sub     esi, r13d
0x1800b45d6  jns     short loc_1800B4571
0x1800b45d8  test    edi, edi
0x1800b45da  jnz     short loc_1800B45E6
0x1800b45dc  call    cs:SwitchToThread
0x1800b45e2  test    eax, eax
0x1800b45e4  jnz     short loc_1800B45EE
0x1800b45e6  mov     ecx, edi; dwMilliseconds
0x1800b45e8  call    cs:Sleep
0x1800b45ee  cmp     ebp, 4
0x1800b45f1  jb      short loc_1800B4613
0x1800b45f3  mov     edi, 64h ; 'd'
0x1800b45f8  jmp     short loc_1800B4623
0x1800b45fa  cmp     dx, 0FFFFh
0x1800b45ff  jz      short loc_1800B45C8
0x1800b4601  mov     eax, edx
0x1800b4603  lea     ecx, [rdx+1]
0x1800b4606  lock cmpxchg [rbx], ecx
0x1800b460a  cmp     edx, eax
0x1800b460c  jnz     short loc_1800B45C8
0x1800b460e  mov     cl, r13b
0x1800b4611  jmp     short loc_1800B45CB
0x1800b4613  mov     eax, ebp
0x1800b4615  lea     rcx, __ImageBase
0x1800b461c  mov     edi, ds:rva dword_18018AF08[rcx+rax*4]
0x1800b4623  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@VonetLocks@@1GA; ushort VonetLocks::CReaderWriterLock3::sm_wDefaultSpinCount
0x1800b462a  mov     edx, 2710h
0x1800b462f  movd    xmm0, r14d
0x1800b4634  mov     r14d, 64h ; 'd'
0x1800b463a  cvtdq2pd xmm0, xmm0
0x1800b463e  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock3@VonetLocks@@1NA; double VonetLocks::CReaderWriterLock3::sm_dblDfltSpinAdjFctr
0x1800b4646  cvttsd2si eax, xmm0
0x1800b464a  cmp     eax, edx
0x1800b464c  cmovg   eax, edx
0x1800b464f  cmp     eax, r14d
0x1800b4652  cmovg   r14d, eax
0x1800b4656  add     ebp, r13d
0x1800b4659  jmp     loc_1800B4560
0x1800b465e  call    cs:GetCurrentThreadId
0x1800b4664  and     eax, 0FFFFFFFDh
0x1800b4667  or      eax, r13d
0x1800b466a  xchg    eax, [rbx+4]
0x1800b466d  mov     rbx, [rsp+48h+arg_0]
0x1800b4672  mov     rbp, [rsp+48h+arg_8]
0x1800b4677  mov     rsi, [rsp+48h+arg_10]
0x1800b467c  add     rsp, 20h
0x1800b4680  pop     r15
0x1800b4682  pop     r14
0x1800b4684  pop     r13
0x1800b4686  pop     r12
0x1800b4688  pop     rdi
0x1800b4689  retn
```
