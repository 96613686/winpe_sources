# Broker::ApplicationIdentity::operator=(Broker::ApplicationIdentity &&)

- ea: `0x180016210`
- end: `0x180016311`
- name: `??4ApplicationIdentity@Broker@@QEAAAEAU01@$$QEAU01@@Z`
- size: `257`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001aee0`

## callees

- `0x18000bb50`
- `0x180016210`
- `0x180019130`

## pseudocode

```c
_QWORD *__fastcall Broker::ApplicationIdentity::operator=(_QWORD *a1, __int64 a2)
{
  _OWORD *v4; // r14
  void **v5; // rsi
  unsigned __int64 v6; // rdx
  __int64 v7; // rsi
  void **v8; // rbx
  unsigned __int64 v9; // rdx

  if ( a1 != (_QWORD *)a2 )
  {
    std::vector<unsigned char>::_Tidy(a1);
    *a1 = *(_QWORD *)a2;
    a1[1] = *(_QWORD *)(a2 + 8);
    a1[2] = *(_QWORD *)(a2 + 16);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_QWORD *)(a2 + 16) = 0;
  }
  v4 = (_OWORD *)(a2 + 24);
  v5 = (void **)(a1 + 3);
  if ( a1 + 3 != (_QWORD *)(a2 + 24) )
  {
    v6 = a1[6];
    if ( v6 > 7 )
      std::_Deallocate<16>(*v5, 2 * v6 + 2);
    a1[5] = 0;
    *(_WORD *)v5 = 0;
    a1[6] = 7;
    *(_OWORD *)v5 = *v4;
    *(_OWORD *)(a1 + 5) = *(_OWORD *)(a2 + 40);
    *(_QWORD *)(a2 + 40) = 0;
    *(_QWORD *)(a2 + 48) = 7;
    *(_WORD *)v4 = 0;
  }
  v7 = a2 + 56;
  v8 = (void **)(a1 + 7);
  if ( a1 + 7 != (_QWORD *)v7 )
  {
    v9 = a1[10];
    if ( v9 > 7 )
      std::_Deallocate<16>(*v8, 2 * v9 + 2);
    a1[9] = 0;
    *(_WORD *)v8 = 0;
    a1[10] = 7;
    *(_OWORD *)v8 = *(_OWORD *)v7;
    *(_OWORD *)(a1 + 9) = *(_OWORD *)(v7 + 16);
    *(_QWORD *)(v7 + 16) = 0;
    *(_QWORD *)(v7 + 24) = 7;
    *(_WORD *)v7 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180016210  push    rbx
0x180016212  push    rsi
0x180016213  push    rdi
0x180016214  push    r14
0x180016216  push    r15
0x180016218  sub     rsp, 20h
0x18001621c  mov     rbx, rdx
0x18001621f  mov     rdi, rcx
0x180016222  cmp     rcx, rdx
0x180016225  jz      short loc_180016259
0x180016227  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001622c  mov     rax, [rbx]
0x18001622f  mov     [rdi], rax
0x180016232  mov     rax, [rbx+8]
0x180016236  mov     [rdi+8], rax
0x18001623a  mov     rax, [rbx+10h]
0x18001623e  mov     [rdi+10h], rax
0x180016242  mov     qword ptr [rbx], 0
0x180016249  mov     qword ptr [rbx+8], 0
0x180016251  mov     qword ptr [rbx+10h], 0
0x180016259  lea     r14, [rbx+18h]
0x18001625d  mov     r15d, 7
0x180016263  lea     rsi, [rdi+18h]
0x180016267  cmp     rsi, r14
0x18001626a  jz      short loc_1800162B2
0x18001626c  mov     rdx, [rsi+18h]
0x180016270  cmp     rdx, r15
0x180016273  jbe     short loc_180016285
0x180016275  mov     rcx, [rsi]
0x180016278  lea     rdx, ds:2[rdx*2]
0x180016280  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016285  mov     qword ptr [rsi+10h], 0
0x18001628d  xor     eax, eax
0x18001628f  mov     [rsi], ax
0x180016292  mov     [rsi+18h], r15
0x180016296  movups  xmm0, xmmword ptr [r14]
0x18001629a  movups  xmmword ptr [rsi], xmm0
0x18001629d  movups  xmm1, xmmword ptr [r14+10h]
0x1800162a2  movups  xmmword ptr [rsi+10h], xmm1
0x1800162a6  mov     [r14+10h], rax
0x1800162aa  mov     [r14+18h], r15
0x1800162ae  mov     [r14], ax
0x1800162b2  lea     rsi, [rbx+38h]
0x1800162b6  lea     rbx, [rdi+38h]
0x1800162ba  cmp     rbx, rsi
0x1800162bd  jz      short loc_180016302
0x1800162bf  mov     rdx, [rbx+18h]
0x1800162c3  cmp     rdx, r15
0x1800162c6  jbe     short loc_1800162D8
0x1800162c8  mov     rcx, [rbx]
0x1800162cb  lea     rdx, ds:2[rdx*2]
0x1800162d3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800162d8  mov     qword ptr [rbx+10h], 0
0x1800162e0  xor     eax, eax
0x1800162e2  mov     [rbx], ax
0x1800162e5  mov     [rbx+18h], r15
0x1800162e9  movups  xmm0, xmmword ptr [rsi]
0x1800162ec  movups  xmmword ptr [rbx], xmm0
0x1800162ef  movups  xmm1, xmmword ptr [rsi+10h]
0x1800162f3  movups  xmmword ptr [rbx+10h], xmm1
0x1800162f7  mov     [rsi+10h], rax
0x1800162fb  mov     [rsi+18h], r15
0x1800162ff  mov     [rsi], ax
0x180016302  mov     rax, rdi
0x180016305  add     rsp, 20h
0x180016309  pop     r15
0x18001630b  pop     r14
0x18001630d  pop     rdi
0x18001630e  pop     rsi
0x18001630f  pop     rbx
0x180016310  retn
```
