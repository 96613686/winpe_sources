# Broker::TimerWheel::Remove(std::shared_ptr<Broker::TimeEvent>)

- ea: `0x180006070`
- end: `0x1800061d1`
- name: `?Remove@TimerWheel@Broker@@QEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z`
- size: `353`
- prototype: `void __fastcall(__int64 **, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800061e0`
- `0x18001579c`

## callees

- `0x180006070`
- `0x180007830`
- `0x1800131e4`
- `0x18001c010`

## pseudocode

```c
void __fastcall Broker::TimerWheel::Remove(__int64 **a1, _QWORD *a2)
{
  __int64 v4; // rbx
  _BYTE *v5; // rdx
  __int64 v6; // r8
  __int64 **v7; // r9
  __int64 v8; // rax
  __int64 **v9; // rsi
  volatile signed __int32 *v10; // rdi
  volatile signed __int32 *v11; // rbx
  __int64 i; // rax

  v4 = **a1;
  while ( (__int64 *)v4 != *a1 )
  {
    v5 = *(_BYTE **)(v4 + 16);
    v6 = v4;
    v7 = (__int64 **)v4;
    if ( v5[25] )
    {
      for ( i = *(_QWORD *)(v4 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
      {
        if ( v4 != *(_QWORD *)(i + 16) )
          break;
        v4 = i;
      }
      v4 = i;
    }
    else
    {
      v8 = *(_QWORD *)v5;
      if ( *(_BYTE *)(*(_QWORD *)v5 + 25LL) )
      {
        v4 = *(_QWORD *)(v4 + 16);
      }
      else
      {
        do
        {
          v4 = v8;
          v8 = *(_QWORD *)v8;
        }
        while ( !*(_BYTE *)(v8 + 25) );
      }
    }
    if ( *(_QWORD *)(v6 + 40) == *a2 )
    {
      v9 = std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(
             a1,
             v7);
      v10 = (volatile signed __int32 *)v9[6];
      if ( v10 && _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
      operator delete(v9);
    }
  }
  v11 = (volatile signed __int32 *)a2[1];
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
}

```

## disassembly

```asm
0x180006070  push    rbx
0x180006072  push    rbp
0x180006073  sub     rsp, 28h
0x180006077  mov     rbx, [rcx]
0x18000607a  mov     ebp, 0FFFFFFFFh
0x18000607f  mov     [rsp+38h+arg_10], r14
0x180006084  mov     r14, rcx
0x180006087  mov     [rsp+38h+var_18], r15
0x18000608c  mov     r15, rdx
0x18000608f  mov     [rsp+38h+arg_0], rsi
0x180006094  mov     rbx, [rbx]
0x180006097  mov     [rsp+38h+arg_8], rdi
0x18000609c  nop     dword ptr [rax+00h]
0x1800060a0  cmp     rbx, [r14]
0x1800060a3  jz      short loc_18000611A
0x1800060a5  mov     rdx, [rbx+10h]
0x1800060a9  mov     r8, rbx
0x1800060ac  mov     r9, rbx
0x1800060af  cmp     byte ptr [rdx+19h], 0
0x1800060b3  jnz     loc_18000614A
0x1800060b9  mov     rax, [rdx]
0x1800060bc  cmp     byte ptr [rax+19h], 0
0x1800060c0  jnz     loc_1800061C9
0x1800060c6  nop     word ptr [rax+rax+00000000h]
0x1800060d0  mov     rcx, [rax]
0x1800060d3  mov     rbx, rax
0x1800060d6  mov     rax, rcx
0x1800060d9  cmp     byte ptr [rcx+19h], 0
0x1800060dd  jz      short loc_1800060D0
0x1800060df  mov     rax, [r15]
0x1800060e2  cmp     [r8+28h], rax
0x1800060e6  jnz     short loc_1800060A0
0x1800060e8  mov     rdx, r9
0x1800060eb  mov     rcx, r14
0x1800060ee  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>,std::_Iterator_base0>)
0x1800060f3  mov     rsi, rax
0x1800060f6  mov     rdi, [rax+30h]
0x1800060fa  test    rdi, rdi
0x1800060fd  jz      short loc_18000610B
0x1800060ff  mov     ecx, ebp
0x180006101  lock xadd [rdi+8], ecx
0x180006106  cmp     ecx, 1
0x180006109  jz      short loc_18000616F
0x18000610b  mov     edx, 38h ; '8'; unsigned __int64
0x180006110  mov     rcx, rsi; void *
0x180006113  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006118  jmp     short loc_1800060A0
0x18000611a  mov     rbx, [r15+8]
0x18000611e  mov     r15, [rsp+38h+var_18]
0x180006123  mov     r14, [rsp+38h+arg_10]
0x180006128  mov     rdi, [rsp+38h+arg_8]
0x18000612d  mov     rsi, [rsp+38h+arg_0]
0x180006132  test    rbx, rbx
0x180006135  jz      short loc_180006143
0x180006137  mov     eax, ebp
0x180006139  lock xadd [rbx+8], eax
0x18000613e  cmp     eax, 1
0x180006141  jz      short loc_18000619D
0x180006143  add     rsp, 28h
0x180006147  pop     rbp
0x180006148  pop     rbx
0x180006149  retn
0x18000614a  mov     rax, [rbx+8]
0x18000614e  cmp     byte ptr [rax+19h], 0
0x180006152  jnz     short loc_180006167
0x180006154  cmp     rbx, [rax+10h]
0x180006158  jnz     short loc_180006167
0x18000615a  mov     rbx, rax
0x18000615d  mov     rax, [rax+8]
0x180006161  cmp     byte ptr [rax+19h], 0
0x180006165  jz      short loc_180006154
0x180006167  mov     rbx, rax
0x18000616a  jmp     loc_1800060DF
0x18000616f  mov     rdx, [rdi]
0x180006172  mov     rcx, rdi
0x180006175  mov     rax, [rdx]
0x180006178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000617d  mov     eax, ebp
0x18000617f  lock xadd [rdi+0Ch], eax
0x180006184  cmp     eax, 1
0x180006187  jnz     short loc_18000610B
0x180006189  mov     rax, [rdi]
0x18000618c  mov     rcx, rdi
0x18000618f  mov     rax, [rax+8]
0x180006193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006198  jmp     loc_18000610B
0x18000619d  mov     rax, [rbx]
0x1800061a0  mov     rcx, rbx
0x1800061a3  mov     rax, [rax]
0x1800061a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ab  lock xadd [rbx+0Ch], ebp
0x1800061b0  cmp     ebp, 1
0x1800061b3  jnz     short loc_180006143
0x1800061b5  mov     rax, [rbx]
0x1800061b8  mov     rcx, rbx
0x1800061bb  mov     rax, [rax+8]
0x1800061bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061c4  jmp     loc_180006143
0x1800061c9  mov     rbx, rdx
0x1800061cc  jmp     loc_1800060DF
```
