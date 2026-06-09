# CSpinLock::_LockSpin(void)

- ea: `0x1800077fc`
- end: `0x1800078c6`
- name: `?_LockSpin@CSpinLock@@AEAAXXZ`
- size: `202`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007a34`
- `0x180007d18`
- `0x180007e18`
- `0x18000a278`

## callees

- `0x180007588`
- `0x1800075c0`
- `0x1800077fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000789b`
- `KERNEL32!GetCurrentThreadId` at `0x18000789b`

## pseudocode

```c
void __fastcall CSpinLock::_LockSpin(CSpinLock *this)
{
  DWORD v2; // edi
  __int64 v3; // rsi
  int v4; // ebx
  int v5; // ecx

  v2 = 0;
  v3 = 0;
  v4 = (int)(RandomBackoffFactor() * 4000.0);
  while ( 1 )
  {
    if ( g_cProcessors <= 1 )
    {
      SwitchOrSleep(v2);
      v2 = 100;
      if ( (unsigned int)v3 < 4 )
        v2 = *((_DWORD *)qword_18000E4D8 + v3);
    }
    else
    {
      v5 = v4;
      while ( *(_DWORD *)this )
      {
        if ( --v5 < 0 )
        {
          SwitchOrSleep(v2);
          v4 = (int)((double)v4 * 0.5);
          if ( v4 <= 10000 )
          {
            if ( v4 <= 100 )
              v4 = 100;
          }
          else
          {
            v4 = 10000;
          }
          v5 = v4;
          v2 = 100;
          if ( (unsigned int)v3 < 4 )
            v2 = *((_DWORD *)qword_18000E4D8 + v3);
        }
      }
    }
    if ( !*(_DWORD *)this
      && !_InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFFC | 1, 0) )
    {
      break;
    }
    v3 = (unsigned int)(v3 + 1);
  }
}

```

## disassembly

```asm
0x1800077fc  push    rbx
0x1800077fe  push    rbp
0x1800077ff  push    rsi
0x180007800  push    rdi
0x180007801  push    r12
0x180007803  push    r14
0x180007805  sub     rsp, 28h
0x180007809  mov     r14, rcx
0x18000780c  xor     edi, edi
0x18000780e  call    ?RandomBackoffFactor@@YANXZ; RandomBackoffFactor(void)
0x180007813  mulsd   xmm0, cs:__real@40af400000000000
0x18000781b  lea     ebp, [rdi+64h]
0x18000781e  xor     esi, esi
0x180007820  lea     r12, qword_18000E4D8
0x180007827  cvttsd2si ebx, xmm0
0x18000782b  cmp     cs:?g_cProcessors@@3KA, 1; ulong g_cProcessors
0x180007832  jbe     short loc_180007882
0x180007834  mov     ecx, ebx
0x180007836  jmp     short loc_180007879
0x180007838  sub     ecx, 1
0x18000783b  jns     short loc_180007879
0x18000783d  mov     ecx, edi; dwMilliseconds
0x18000783f  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x180007844  movd    xmm0, ebx
0x180007848  cvtdq2pd xmm0, xmm0
0x18000784c  mulsd   xmm0, cs:__real@3fe0000000000000
0x180007854  cvttsd2si ebx, xmm0
0x180007858  cmp     ebx, 2710h
0x18000785e  jle     short loc_180007867
0x180007860  mov     ebx, 2710h
0x180007865  jmp     short loc_18000786C
0x180007867  cmp     ebx, ebp
0x180007869  cmovle  ebx, ebp
0x18000786c  mov     ecx, ebx
0x18000786e  mov     edi, ebp
0x180007870  cmp     esi, 4
0x180007873  jnb     short loc_180007879
0x180007875  mov     edi, [r12+rsi*4]
0x180007879  mov     eax, [r14]
0x18000787c  test    eax, eax
0x18000787e  jnz     short loc_180007838
0x180007880  jmp     short loc_180007894
0x180007882  mov     ecx, edi; dwMilliseconds
0x180007884  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x180007889  mov     edi, ebp
0x18000788b  cmp     esi, 4
0x18000788e  jnb     short loc_180007894
0x180007890  mov     edi, [r12+rsi*4]
0x180007894  mov     eax, [r14]
0x180007897  test    eax, eax
0x180007899  jnz     short loc_1800078B2
0x18000789b  call    cs:__imp_GetCurrentThreadId
0x1800078a1  mov     ecx, eax
0x1800078a3  and     ecx, 0FFFFFFFDh
0x1800078a6  or      ecx, 1
0x1800078a9  xor     eax, eax
0x1800078ab  lock cmpxchg [r14], ecx
0x1800078b0  jz      short loc_1800078B9
0x1800078b2  inc     esi
0x1800078b4  jmp     loc_18000782B
0x1800078b9  add     rsp, 28h
0x1800078bd  pop     r14
0x1800078bf  pop     r12
0x1800078c1  pop     rdi
0x1800078c2  pop     rsi
0x1800078c3  pop     rbp
0x1800078c4  pop     rbx
0x1800078c5  retn
```
