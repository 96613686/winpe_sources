# CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)

- ea: `0x18002ecf4`
- end: `0x18002ee3a`
- name: `?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `326`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004080`
- `0x1800041c0`
- `0x180005240`
- `0x18002f194`

## callees

- `0x180005340`
- `0x18002eb74`
- `0x18002eb94`
- `0x18002ecf4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ed0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ed8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ed0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ed8d`

## pseudocode

```c
bool __fastcall CReaderWriterLock3::_LockSpin(volatile signed __int32 *a1, int a2)
{
  DWORD v3; // r15d
  DWORD CurrentThreadId; // eax
  unsigned __int16 v6; // cx
  unsigned int v7; // ebp
  int v8; // edi
  int v9; // esi
  signed __int32 v10; // edx
  bool result; // al
  signed __int32 v12; // edx

  v3 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
  v7 = 0;
  v8 = (int)((double)CReaderWriterLock3::sm_wDefaultSpinCount * *(double *)&qword_18004EB20[CurrentThreadId % 0xD]);
LABEL_2:
  v9 = v8;
  if ( g_cProcessors < 2 || !v6 )
    v9 = 1;
  while ( 1 )
  {
    if ( --v9 < 0 )
    {
      SwitchOrSleep(v3);
      v3 = SleepTime(v7);
      v8 = (int)((double)v8 * CReaderWriterLock3::sm_dblDfltSpinAdjFctr);
      if ( v8 <= 10000 )
      {
        if ( v8 <= 100 )
          v8 = 100;
      }
      else
      {
        v8 = 10000;
      }
      v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
      ++v7;
      goto LABEL_2;
    }
    if ( a2 != 1 )
    {
      v12 = *a1;
      if ( a2 == 2 )
      {
        if ( (v12 & 0xFFFF8000) == 0 )
        {
LABEL_16:
          result = 1;
          if ( v12 == _InterlockedCompareExchange(a1, v12 + 1, v12) )
            goto LABEL_18;
        }
      }
      else if ( (_WORD)v12 != 0xFFFF )
      {
        goto LABEL_16;
      }
      result = 0;
      goto LABEL_18;
    }
    if ( *((_DWORD *)a1 + 1)
      || (unsigned __int16)*a1
      || (v10 = *a1, v10 != _InterlockedCompareExchange(a1, v10 | 0xFFFF, v10)) )
    {
      result = CReaderWriterLock3::_TryWriteLock2((CReaderWriterLock3 *)a1);
    }
    else
    {
      _InterlockedExchange(a1 + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
      result = 1;
    }
LABEL_18:
    if ( result )
      return result;
    _mm_pause();
  }
}

```

## disassembly

```asm
0x18002ecf4  push    rbx
0x18002ecf6  push    rbp
0x18002ecf7  push    rsi
0x18002ecf8  push    rdi
0x18002ecf9  push    r13
0x18002ecfb  push    r14
0x18002ecfd  push    r15
0x18002ecff  sub     rsp, 20h
0x18002ed03  xor     r13d, r13d
0x18002ed06  mov     r14d, edx
0x18002ed09  mov     r15d, r13d
0x18002ed0c  mov     rbx, rcx
0x18002ed0f  call    cs:__imp_GetCurrentThreadId
0x18002ed15  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x18002ed1c  mov     ebp, r13d
0x18002ed1f  mov     r9d, eax
0x18002ed22  mov     eax, 4EC4EC4Fh
0x18002ed27  mul     r9d
0x18002ed2a  movd    xmm0, ecx
0x18002ed2e  cvtdq2pd xmm0, xmm0
0x18002ed32  shr     edx, 2
0x18002ed35  imul    r8d, edx, 0Dh
0x18002ed39  lea     rdx, qword_18004EB20
0x18002ed40  sub     r9d, r8d
0x18002ed43  mulsd   xmm0, qword ptr [rdx+r9*8]
0x18002ed49  cvttsd2si edi, xmm0
0x18002ed4d  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x18002ed54  mov     esi, edi
0x18002ed56  jb      short loc_18002ED5D
0x18002ed58  test    cx, cx
0x18002ed5b  jnz     short loc_18002ED62
0x18002ed5d  mov     esi, 1
0x18002ed62  sub     esi, 1
0x18002ed65  js      short loc_18002EDDE
0x18002ed67  cmp     r14d, 1
0x18002ed6b  jnz     short loc_18002EDAB
0x18002ed6d  mov     eax, [rbx+4]
0x18002ed70  test    eax, eax
0x18002ed72  jnz     short loc_18002EDA1
0x18002ed74  mov     edx, [rbx]
0x18002ed76  test    dx, dx
0x18002ed79  jnz     short loc_18002EDA1
0x18002ed7b  mov     ecx, edx
0x18002ed7d  mov     eax, edx
0x18002ed7f  or      ecx, 0FFFFh
0x18002ed85  lock cmpxchg [rbx], ecx
0x18002ed89  cmp     edx, eax
0x18002ed8b  jnz     short loc_18002EDA1
0x18002ed8d  call    cs:__imp_GetCurrentThreadId
0x18002ed93  and     eax, 0FFFFFFFCh
0x18002ed96  or      eax, r14d
0x18002ed99  xchg    eax, [rbx+4]
0x18002ed9c  mov     al, r14b
0x18002ed9f  jmp     short loc_18002EDD6
0x18002eda1  mov     rcx, rbx; this
0x18002eda4  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x18002eda9  jmp     short loc_18002EDD6
0x18002edab  mov     edx, [rbx]
0x18002edad  cmp     r14d, 2
0x18002edb1  jnz     short loc_18002EDBD
0x18002edb3  test    edx, 0FFFF8000h
0x18002edb9  jnz     short loc_18002EDD3
0x18002edbb  jmp     short loc_18002EDC4
0x18002edbd  cmp     dx, 0FFFFh
0x18002edc2  jz      short loc_18002EDD3
0x18002edc4  mov     eax, edx
0x18002edc6  lea     ecx, [rdx+1]
0x18002edc9  lock cmpxchg [rbx], ecx
0x18002edcd  cmp     edx, eax
0x18002edcf  mov     al, 1
0x18002edd1  jz      short loc_18002EDD6
0x18002edd3  mov     al, r13b
0x18002edd6  test    al, al
0x18002edd8  jnz     short loc_18002EE2B
0x18002edda  pause
0x18002eddc  jmp     short loc_18002ED62
0x18002edde  mov     ecx, r15d; dwMilliseconds
0x18002ede1  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18002ede6  mov     ecx, ebp; unsigned int
0x18002ede8  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18002eded  movd    xmm0, edi
0x18002edf1  mov     r15d, eax
0x18002edf4  cvtdq2pd xmm0, xmm0
0x18002edf8  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock3@@1NA; double CReaderWriterLock3::sm_dblDfltSpinAdjFctr
0x18002ee00  cvttsd2si edi, xmm0
0x18002ee04  cmp     edi, 2710h
0x18002ee0a  jle     short loc_18002EE13
0x18002ee0c  mov     edi, 2710h
0x18002ee11  jmp     short loc_18002EE1D
0x18002ee13  mov     eax, 64h ; 'd'
0x18002ee18  cmp     edi, eax
0x18002ee1a  cmovle  edi, eax
0x18002ee1d  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x18002ee24  inc     ebp
0x18002ee26  jmp     loc_18002ED4D
0x18002ee2b  add     rsp, 20h
0x18002ee2f  pop     r15
0x18002ee31  pop     r14
0x18002ee33  pop     r13
0x18002ee35  pop     rdi
0x18002ee36  pop     rsi
0x18002ee37  pop     rbp
0x18002ee38  pop     rbx
0x18002ee39  retn
```
