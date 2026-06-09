# CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)

- ea: `0x1800076c8`
- end: `0x1800077f6`
- name: `?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `302`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800036a0`
- `0x180003780`
- `0x180003ca0`
- `0x180004524`
- `0x180006438`
- `0x1800064f4`
- `0x1800067b0`
- `0x1800098d4`

## callees

- `0x180007588`
- `0x1800075c0`
- `0x1800076c8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180007737`
- `KERNEL32!GetCurrentThreadId` at `0x18000774a`
- `KERNEL32!GetCurrentThreadId` at `0x180007737`
- `KERNEL32!GetCurrentThreadId` at `0x18000774a`

## pseudocode

```c
__int64 __fastcall CReaderWriterLock3::_LockSpin(volatile signed __int32 *a1, int a2)
{
  DWORD v4; // r14d
  __int64 v5; // rbp
  int v6; // edi
  __int64 result; // rax
  int v8; // esi
  signed __int32 v9; // edx
  DWORD v10; // eax
  char v11; // cl
  signed __int32 v12; // edx

  v4 = 0;
  v5 = 0;
  v6 = (int)(RandomBackoffFactor() * 4000.0);
  while ( 1 )
  {
    result = (unsigned int)v6;
    if ( g_cProcessors < 2 )
    {
      v8 = 0;
      goto LABEL_5;
    }
    v8 = v6 - 1;
    if ( v6 - 1 >= 0 )
      break;
LABEL_22:
    SwitchOrSleep(v4);
    if ( (unsigned int)v5 < 4 )
      v4 = *((_DWORD *)qword_18000E4D8 + v5);
    else
      v4 = 100;
    v6 = (int)((double)v6 * 0.5);
    if ( v6 <= 10000 )
    {
      if ( v6 <= 100 )
        v6 = 100;
    }
    else
    {
      v6 = 10000;
    }
    v5 = (unsigned int)(v5 + 1);
  }
  while ( 1 )
  {
LABEL_5:
    if ( a2 == 1 )
    {
      if ( !*((_DWORD *)a1 + 1) && !(unsigned __int16)*a1 )
      {
        v9 = *a1;
        if ( v9 == _InterlockedCompareExchange(a1, v9 | 0xFFFF, v9) )
        {
          v10 = GetCurrentThreadId() & 0xFFFFFFFC | 1;
LABEL_10:
          result = (unsigned int)_InterlockedExchange(a1 + 1, v10);
LABEL_11:
          v11 = 1;
          goto LABEL_20;
        }
      }
      result = GetCurrentThreadId() & 0xFFFFFFFC;
      if ( (a1[1] & 0xFFFFFFFC) == (_DWORD)result )
      {
        v10 = *((_DWORD *)a1 + 1) + 1;
        goto LABEL_10;
      }
    }
    else
    {
      v12 = *a1;
      if ( a2 == 2 )
      {
        if ( (v12 & 0xFFFF8000) != 0 )
          goto LABEL_19;
      }
      else if ( (_WORD)v12 == 0xFFFF )
      {
        goto LABEL_19;
      }
      result = (unsigned int)_InterlockedCompareExchange(a1, v12 + 1, v12);
      if ( v12 == (_DWORD)result )
        goto LABEL_11;
    }
LABEL_19:
    v11 = 0;
LABEL_20:
    if ( v11 )
      return result;
    if ( --v8 < 0 )
      goto LABEL_22;
  }
}

```

## disassembly

```asm
0x1800076c8  push    rbx
0x1800076ca  push    rbp
0x1800076cb  push    rsi
0x1800076cc  push    rdi
0x1800076cd  push    r12
0x1800076cf  push    r14
0x1800076d1  push    r15
0x1800076d3  sub     rsp, 20h
0x1800076d7  mov     r15d, edx
0x1800076da  mov     rbx, rcx
0x1800076dd  xor     r14d, r14d
0x1800076e0  call    ?RandomBackoffFactor@@YANXZ; RandomBackoffFactor(void)
0x1800076e5  mulsd   xmm0, cs:__real@40af400000000000
0x1800076ed  lea     r12d, [r14+64h]
0x1800076f1  xor     ebp, ebp
0x1800076f3  cvttsd2si edi, xmm0
0x1800076f7  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x1800076fe  mov     eax, edi
0x180007700  jnb     short loc_180007706
0x180007702  xor     esi, esi
0x180007704  jmp     short loc_180007711
0x180007706  lea     esi, [rax-1]
0x180007709  test    esi, esi
0x18000770b  js      loc_180007799
0x180007711  cmp     r15d, 1
0x180007715  jnz     short loc_180007764
0x180007717  mov     eax, [rbx+4]
0x18000771a  test    eax, eax
0x18000771c  jnz     short loc_18000774A
0x18000771e  mov     edx, [rbx]
0x180007720  test    dx, dx
0x180007723  jnz     short loc_18000774A
0x180007725  mov     ecx, edx
0x180007727  mov     eax, edx
0x180007729  or      ecx, 0FFFFh
0x18000772f  lock cmpxchg [rbx], ecx
0x180007733  cmp     edx, eax
0x180007735  jnz     short loc_18000774A
0x180007737  call    cs:__imp_GetCurrentThreadId
0x18000773d  and     eax, 0FFFFFFFCh
0x180007740  or      eax, r15d
0x180007743  xchg    eax, [rbx+4]
0x180007746  mov     cl, 1
0x180007748  jmp     short loc_18000778C
0x18000774a  call    cs:__imp_GetCurrentThreadId
0x180007750  mov     ecx, [rbx+4]
0x180007753  and     eax, 0FFFFFFFCh
0x180007756  and     ecx, 0FFFFFFFCh
0x180007759  cmp     ecx, eax
0x18000775b  jnz     short loc_18000778A
0x18000775d  mov     eax, [rbx+4]
0x180007760  inc     eax
0x180007762  jmp     short loc_180007743
0x180007764  mov     edx, [rbx]
0x180007766  cmp     r15d, 2
0x18000776a  jnz     short loc_180007776
0x18000776c  test    edx, 0FFFF8000h
0x180007772  jnz     short loc_18000778A
0x180007774  jmp     short loc_18000777D
0x180007776  cmp     dx, 0FFFFh
0x18000777b  jz      short loc_18000778A
0x18000777d  mov     eax, edx
0x18000777f  lea     ecx, [rdx+1]
0x180007782  lock cmpxchg [rbx], ecx
0x180007786  cmp     edx, eax
0x180007788  jz      short loc_180007746
0x18000778a  xor     cl, cl
0x18000778c  test    cl, cl
0x18000778e  jnz     short loc_1800077E7
0x180007790  sub     esi, 1
0x180007793  jns     loc_180007711
0x180007799  mov     ecx, r14d; dwMilliseconds
0x18000779c  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x1800077a1  cmp     ebp, 4
0x1800077a4  jb      short loc_1800077AB
0x1800077a6  mov     r14d, r12d
0x1800077a9  jmp     short loc_1800077B6
0x1800077ab  lea     r14, qword_18000E4D8
0x1800077b2  mov     r14d, [r14+rbp*4]
0x1800077b6  movd    xmm0, edi
0x1800077ba  cvtdq2pd xmm0, xmm0
0x1800077be  mulsd   xmm0, cs:__real@3fe0000000000000
0x1800077c6  cvttsd2si edi, xmm0
0x1800077ca  cmp     edi, 2710h
0x1800077d0  jle     short loc_1800077D9
0x1800077d2  mov     edi, 2710h
0x1800077d7  jmp     short loc_1800077E0
0x1800077d9  cmp     edi, r12d
0x1800077dc  cmovle  edi, r12d
0x1800077e0  inc     ebp
0x1800077e2  jmp     loc_1800076F7
0x1800077e7  add     rsp, 20h
0x1800077eb  pop     r15
0x1800077ed  pop     r14
0x1800077ef  pop     r12
0x1800077f1  pop     rdi
0x1800077f2  pop     rsi
0x1800077f3  pop     rbp
0x1800077f4  pop     rbx
0x1800077f5  retn
```
