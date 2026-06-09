# CReaderWriterLock2::_LockSpin(bool)

- ea: `0x1800075f0`
- end: `0x1800076c0`
- name: `?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z`
- size: `208`
- prototype: `void __fastcall(CReaderWriterLock2 *__hidden this, bool)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008070`
- `0x1800089a4`
- `0x180008bf4`
- `0x1800091b0`
- `0x180009574`
- `0x1800098d4`
- `0x180009c78`
- `0x18000a018`

## callees

- `0x180007588`
- `0x1800075c0`
- `0x1800075f0`

## pseudocode

```c
void __fastcall CReaderWriterLock2::_LockSpin(CReaderWriterLock2 *this, char a2)
{
  DWORD v4; // ebp
  __int64 v5; // rdi
  int v6; // ebx
  int v7; // r8d
  signed __int32 v8; // edx
  signed __int32 v9; // ecx
  char v10; // al

  v4 = 0;
  v5 = 0;
  v6 = (int)(RandomBackoffFactor() * 4000.0);
LABEL_2:
  v7 = v6;
  if ( g_cProcessors < 2 )
  {
    v7 = 0;
    goto LABEL_4;
  }
  do
  {
    if ( --v7 < 0 )
    {
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
      goto LABEL_2;
    }
LABEL_4:
    v8 = *(_DWORD *)this;
    if ( a2 )
    {
      if ( (_WORD)v8 )
        goto LABEL_11;
      v9 = v8 | 0xFFFF;
    }
    else
    {
      if ( (v8 & 0xFFFF8000) != 0 )
        goto LABEL_11;
      v9 = v8 + 1;
    }
    if ( v8 == _InterlockedCompareExchange((volatile signed __int32 *)this, v9, v8) )
    {
      v10 = 1;
      continue;
    }
LABEL_11:
    v10 = 0;
  }
  while ( !v10 );
}

```

## disassembly

```asm
0x1800075f0  push    rbx
0x1800075f2  push    rbp
0x1800075f3  push    rsi
0x1800075f4  push    rdi
0x1800075f5  push    r14
0x1800075f7  push    r15
0x1800075f9  sub     rsp, 28h
0x1800075fd  mov     r14b, dl
0x180007600  mov     rsi, rcx
0x180007603  xor     ebp, ebp
0x180007605  call    ?RandomBackoffFactor@@YANXZ; RandomBackoffFactor(void)
0x18000760a  mulsd   xmm0, cs:__real@40af400000000000
0x180007612  lea     r15d, [rbp+64h]
0x180007616  xor     edi, edi
0x180007618  cvttsd2si ebx, xmm0
0x18000761c  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180007623  mov     r8d, ebx
0x180007626  jnb     short loc_180007660
0x180007628  xor     r8d, r8d
0x18000762b  mov     edx, [rsi]
0x18000762d  test    r14b, r14b
0x180007630  jz      short loc_180007641
0x180007632  test    dx, dx
0x180007635  jnz     short loc_18000765A
0x180007637  mov     ecx, edx
0x180007639  or      ecx, 0FFFFh
0x18000763f  jmp     short loc_18000764C
0x180007641  test    edx, 0FFFF8000h
0x180007647  jnz     short loc_18000765A
0x180007649  lea     ecx, [rdx+1]
0x18000764c  mov     eax, edx
0x18000764e  lock cmpxchg [rsi], ecx
0x180007652  cmp     edx, eax
0x180007654  jnz     short loc_18000765A
0x180007656  mov     al, 1
0x180007658  jmp     short loc_18000765C
0x18000765a  xor     al, al
0x18000765c  test    al, al
0x18000765e  jnz     short loc_1800076B3
0x180007660  sub     r8d, 1
0x180007664  jns     short loc_18000762B
0x180007666  mov     ecx, ebp; dwMilliseconds
0x180007668  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18000766d  cmp     edi, 4
0x180007670  jb      short loc_180007677
0x180007672  mov     ebp, r15d
0x180007675  jmp     short loc_180007682
0x180007677  lea     rbp, qword_18000E4D8
0x18000767e  mov     ebp, [rbp+rdi*4+0]
0x180007682  movd    xmm0, ebx
0x180007686  cvtdq2pd xmm0, xmm0
0x18000768a  mulsd   xmm0, cs:__real@3fe0000000000000
0x180007692  cvttsd2si ebx, xmm0
0x180007696  cmp     ebx, 2710h
0x18000769c  jle     short loc_1800076A5
0x18000769e  mov     ebx, 2710h
0x1800076a3  jmp     short loc_1800076AC
0x1800076a5  cmp     ebx, r15d
0x1800076a8  cmovle  ebx, r15d
0x1800076ac  inc     edi
0x1800076ae  jmp     loc_18000761C
0x1800076b3  add     rsp, 28h
0x1800076b7  pop     r15
0x1800076b9  pop     r14
0x1800076bb  pop     rdi
0x1800076bc  pop     rsi
0x1800076bd  pop     rbp
0x1800076be  pop     rbx
0x1800076bf  retn
```
