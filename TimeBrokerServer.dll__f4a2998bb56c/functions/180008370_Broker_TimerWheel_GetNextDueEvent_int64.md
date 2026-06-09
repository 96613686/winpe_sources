# Broker::TimerWheel::GetNextDueEvent(__int64)

- ea: `0x180008370`
- end: `0x1800084dd`
- name: `?GetNextDueEvent@TimerWheel@Broker@@QEAA?AV?$shared_ptr@VTimeEvent@Broker@@@std@@_J@Z`
- size: `365`
- prototype: `_QWORD *__fastcall(__int64 **, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001579c`

## callees

- `0x180003840`
- `0x180007830`
- `0x180008370`
- `0x1800084e4`
- `0x180008530`
- `0x1800131e4`
- `0x18001c010`

## pseudocode

```c
_QWORD *__fastcall Broker::TimerWheel::GetNextDueEvent(__int64 **a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v4; // r9
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbp
  __int64 v8; // r15
  __int64 **v9; // r14
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // r8

  if ( !a1[1] )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_18bfb99d5b9e35a1ef7686c2072d1f59_Traceguids);
    goto LABEL_17;
  }
  v4 = (_QWORD *)**a1;
  v5 = v4[4];
  if ( v5 > a3 )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_qii(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, v4[5] + 248LL, v5, a3);
LABEL_17:
    *a2 = 0;
    a2[1] = 0;
    return a2;
  }
  v6 = v4[6];
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  v7 = v4[5];
  v8 = v4[6];
  v9 = std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(
         a1,
         (__int64 **)**a1);
  v10 = (volatile signed __int32 *)v9[6];
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  operator delete(v9);
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, v7 + 248);
  *a2 = v7;
  a2[1] = v8;
  return a2;
}

```

## disassembly

```asm
0x180008370  push    rbx
0x180008372  sub     rsp, 40h
0x180008376  cmp     qword ptr [rcx+8], 0
0x18000837b  mov     rbx, rdx
0x18000837e  jz      loc_1800084B3
0x180008384  mov     rax, [rcx]
0x180008387  mov     r9, [rax]
0x18000838a  mov     rax, [r9+20h]
0x18000838e  cmp     rax, r8
0x180008391  jg      loc_180008474
0x180008397  mov     rax, [r9+30h]
0x18000839b  mov     [rsp+48h+arg_0], rbp
0x1800083a0  mov     [rsp+48h+arg_10], rdi
0x1800083a5  mov     [rsp+48h+var_10], r14
0x1800083aa  mov     [rsp+48h+var_18], r15
0x1800083af  test    rax, rax
0x1800083b2  jz      short loc_1800083B8
0x1800083b4  lock inc dword ptr [rax+8]
0x1800083b8  mov     rdx, [rcx]
0x1800083bb  mov     rbp, [r9+28h]
0x1800083bf  mov     r15, [r9+30h]
0x1800083c3  mov     rdx, [rdx]
0x1800083c6  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>,std::_Iterator_base0>)
0x1800083cb  mov     r14, rax
0x1800083ce  mov     rdi, [rax+30h]
0x1800083d2  test    rdi, rdi
0x1800083d5  jz      short loc_1800083F2
0x1800083d7  mov     [rsp+48h+arg_8], rsi
0x1800083dc  mov     esi, 0FFFFFFFFh
0x1800083e1  mov     ecx, esi
0x1800083e3  lock xadd [rdi+8], ecx
0x1800083e8  cmp     ecx, 1
0x1800083eb  jz      short loc_180008448
0x1800083ed  mov     rsi, [rsp+48h+arg_8]
0x1800083f2  mov     edx, 38h ; '8'; unsigned __int64
0x1800083f7  mov     rcx, r14; void *
0x1800083fa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800083ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180008406  mov     r14, [rsp+48h+var_10]
0x18000840b  mov     rdi, [rsp+48h+arg_10]
0x180008410  test    byte ptr [rcx+1Ch], 80h
0x180008414  jnz     short loc_180008430
0x180008416  mov     [rbx], rbp
0x180008419  mov     rbp, [rsp+48h+arg_0]
0x18000841e  mov     [rbx+8], r15
0x180008422  mov     r15, [rsp+48h+var_18]
0x180008427  mov     rax, rbx
0x18000842a  add     rsp, 40h
0x18000842e  pop     rbx
0x18000842f  retn
0x180008430  cmp     byte ptr [rcx+19h], 5
0x180008434  jb      short loc_180008416
0x180008436  mov     rcx, [rcx+10h]
0x18000843a  lea     r9, [rbp+0F8h]
0x180008441  call    WPP_SF_q
0x180008446  jmp     short loc_180008416
0x180008448  mov     rdx, [rdi]
0x18000844b  mov     rcx, rdi
0x18000844e  mov     rax, [rdx]
0x180008451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008456  lock xadd [rdi+0Ch], esi
0x18000845b  cmp     esi, 1
0x18000845e  jnz     short loc_1800083ED
0x180008460  mov     rax, [rdi]
0x180008463  mov     rcx, rdi
0x180008466  mov     rax, [rax+8]
0x18000846a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000846f  jmp     loc_1800083ED
0x180008474  mov     rcx, cs:WPP_GLOBAL_Control
0x18000847b  test    byte ptr [rcx+1Ch], 80h
0x18000847f  jz      short loc_1800084A5
0x180008481  cmp     byte ptr [rcx+19h], 5
0x180008485  jb      short loc_1800084A5
0x180008487  mov     r9, [r9+28h]
0x18000848b  mov     rcx, [rcx+10h]
0x18000848f  add     r9, 0F8h
0x180008496  mov     [rsp+48h+var_20], r8
0x18000849b  mov     [rsp+48h+var_28], rax
0x1800084a0  call    WPP_SF_qii
0x1800084a5  xor     eax, eax
0x1800084a7  mov     [rbx], rax
0x1800084aa  mov     [rbx+8], rax
0x1800084ae  jmp     loc_180008427
0x1800084b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084ba  test    byte ptr [rcx+1Ch], 80h
0x1800084be  jz      short loc_1800084A5
0x1800084c0  cmp     byte ptr [rcx+19h], 5
0x1800084c4  jb      short loc_1800084A5
0x1800084c6  mov     rcx, [rcx+10h]
0x1800084ca  lea     r8, WPP_18bfb99d5b9e35a1ef7686c2072d1f59_Traceguids
0x1800084d1  mov     edx, 0Bh
0x1800084d6  call    WPP_SF_
0x1800084db  jmp     short loc_1800084A5
```
