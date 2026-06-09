# std::_Pop_heap_hole_unchecked<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,ScheduledUmpMessage,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,ScheduledUmpMessage &&,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &))

- ea: `0x18000a08c`
- end: `0x18000a1de`
- name: `??$_Pop_heap_hole_unchecked@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UScheduledUmpMessage@@@std@@@std@@@std@@UScheduledUmpMessage@@P6A_NAEAU3@0@Z@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UScheduledUmpMessage@@@std@@@std@@@0@00$$QEAUScheduledUmpMessage@@P6A_NAEAU2@2@Z@Z`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000af80`

## callees

- `0x18000a08c`
- `0x18000a1e4`
- `0x18000a99c`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall std::_Pop_heap_hole_unchecked<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,ScheduledUmpMessage,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3,
        int a4,
        unsigned __int8 (__fastcall *a5)(_QWORD, _QWORD))
{
  __int64 v5; // rsi
  __int64 v6; // r14
  __int64 v7; // r13
  int v8; // r8d
  int v9; // r15d
  __int64 v10; // rdi
  int v11; // ebx
  __int64 v12; // rbp
  __int64 i; // rbx
  _QWORD v15[9]; // [rsp+30h] [rbp-48h] BYREF

  v5 = *a1;
  v6 = a1[1];
  v7 = *(_QWORD *)(a2 + 8);
  ScheduledUmpMessage::operator=(
    *(_QWORD *)(*(_QWORD *)(*a3 + 8LL) + 8 * (a3[1] & (*(_QWORD *)(*a3 + 16LL) - 1LL))),
    *(_QWORD *)(*(_QWORD *)(*a1 + 8LL) + 8 * (v6 & (*(_QWORD *)(*a1 + 16LL) - 1LL))));
  v9 = v7 - v6;
  v10 = 0;
  v11 = v7 - v6 - 1;
  v12 = (v7 - v6 - 1) >> 1;
  if ( v12 > 0 )
  {
    for ( i = 0; i < v12; v10 = i )
    {
      i = 2LL
        - (a5(
             *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8 * ((*(_QWORD *)(v5 + 16) - 1LL) & (2 * i + v6 + 2))),
             *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8 * ((*(_QWORD *)(v5 + 16) - 1LL) & (2 * i + v6 + 1)))) != 0)
        + 2 * i;
      ScheduledUmpMessage::operator=(
        *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8 * ((*(_QWORD *)(v5 + 16) - 1LL) & (v6 + v10))),
        *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8 * ((*(_QWORD *)(v5 + 16) - 1LL) & (i + v6))));
    }
    v11 = v9 - 1;
  }
  if ( v10 == v12 && (v9 & 1) == 0 )
  {
    ScheduledUmpMessage::operator=(
      *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8 * ((*(_QWORD *)(v5 + 16) - 1LL) & (v6 + v10))),
      *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8 * ((*(_QWORD *)(v5 + 16) - 1LL) & (v7 - 1))));
    LODWORD(v10) = v11;
  }
  v15[0] = v5;
  v15[1] = v6;
  return std::_Push_heap_by_index<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,ScheduledUmpMessage,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>(
           (unsigned int)v15,
           v10,
           v8,
           a4,
           (__int64)a5);
}

```

## disassembly

```asm
0x18000a08c  mov     [rsp+arg_8], rbx
0x18000a091  mov     [rsp+arg_18], r9
0x18000a096  push    rbp
0x18000a097  push    rsi
0x18000a098  push    rdi
0x18000a099  push    r12
0x18000a09b  push    r13
0x18000a09d  push    r14
0x18000a09f  push    r15
0x18000a0a1  sub     rsp, 40h
0x18000a0a5  mov     rsi, [rcx]
0x18000a0a8  mov     r14, [rcx+8]
0x18000a0ac  mov     r11, [r8]
0x18000a0af  mov     r13, [rdx+8]
0x18000a0b3  mov     r10, [rsi+10h]
0x18000a0b7  mov     rdx, [rsi+8]
0x18000a0bb  dec     r10
0x18000a0be  mov     rax, [r11+10h]
0x18000a0c2  and     r10, r14
0x18000a0c5  mov     rcx, [r11+8]
0x18000a0c9  dec     rax
0x18000a0cc  and     rax, [r8+8]
0x18000a0d0  mov     rdx, [rdx+r10*8]
0x18000a0d4  mov     rcx, [rcx+rax*8]
0x18000a0d8  call    ??4ScheduledUmpMessage@@QEAAAEAU0@$$QEAU0@@Z; ScheduledUmpMessage::operator=(ScheduledUmpMessage &&)
0x18000a0dd  mov     r12, [rsp+78h+arg_20]
0x18000a0e5  mov     r15, r13
0x18000a0e8  sub     r15, r14
0x18000a0eb  xor     edi, edi
0x18000a0ed  lea     rbx, [r15-1]
0x18000a0f1  mov     rbp, rbx
0x18000a0f4  sar     rbp, 1
0x18000a0f7  test    rbp, rbp
0x18000a0fa  jle     short loc_18000A16E
0x18000a0fc  mov     ebx, edi
0x18000a0fe  mov     r8, [rsi+8]
0x18000a102  lea     rdx, [r14+1]
0x18000a106  mov     rax, [rsi+10h]
0x18000a10a  lea     rcx, [r14+2]
0x18000a10e  add     rbx, rbx
0x18000a111  dec     rax
0x18000a114  add     rdx, rbx
0x18000a117  add     rcx, rbx
0x18000a11a  and     rdx, rax
0x18000a11d  and     rcx, rax
0x18000a120  mov     rax, r12
0x18000a123  mov     rdx, [r8+rdx*8]
0x18000a127  mov     rcx, [r8+rcx*8]
0x18000a12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a130  mov     r8, [rsi+8]
0x18000a134  neg     al
0x18000a136  mov     rax, [rsi+10h]
0x18000a13a  sbb     rcx, rcx
0x18000a13d  add     rcx, 2
0x18000a141  add     rbx, rcx
0x18000a144  lea     rcx, [r14+rdi]
0x18000a148  dec     rax
0x18000a14b  and     rcx, rax
0x18000a14e  lea     rdx, [rbx+r14]
0x18000a152  and     rdx, rax
0x18000a155  mov     rcx, [r8+rcx*8]
0x18000a159  mov     rdx, [r8+rdx*8]
0x18000a15d  call    ??4ScheduledUmpMessage@@QEAAAEAU0@$$QEAU0@@Z; ScheduledUmpMessage::operator=(ScheduledUmpMessage &&)
0x18000a162  mov     rdi, rbx
0x18000a165  cmp     rbx, rbp
0x18000a168  jl      short loc_18000A0FE
0x18000a16a  lea     rbx, [r15-1]
0x18000a16e  cmp     rdi, rbp
0x18000a171  jnz     short loc_18000A1A2
0x18000a173  test    r15b, 1
0x18000a177  jnz     short loc_18000A1A2
0x18000a179  mov     r8, [rsi+8]
0x18000a17d  lea     rdx, [r13-1]
0x18000a181  mov     rax, [rsi+10h]
0x18000a185  lea     rcx, [r14+rdi]
0x18000a189  dec     rax
0x18000a18c  and     rdx, rax
0x18000a18f  and     rcx, rax
0x18000a192  mov     rdx, [r8+rdx*8]
0x18000a196  mov     rcx, [r8+rcx*8]
0x18000a19a  call    ??4ScheduledUmpMessage@@QEAAAEAU0@$$QEAU0@@Z; ScheduledUmpMessage::operator=(ScheduledUmpMessage &&)
0x18000a19f  mov     rdi, rbx
0x18000a1a2  mov     r9, [rsp+78h+arg_18]
0x18000a1aa  lea     rcx, [rsp+78h+var_48]
0x18000a1af  mov     rdx, rdi
0x18000a1b2  mov     [rsp+78h+var_48], rsi
0x18000a1b7  mov     [rsp+78h+var_40], r14
0x18000a1bc  mov     [rsp+78h+var_58], r12
0x18000a1c1  call    ??$_Push_heap_by_index@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UScheduledUmpMessage@@@std@@@std@@@std@@UScheduledUmpMessage@@P6A_NAEAU3@0@Z@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UScheduledUmpMessage@@@std@@@std@@@0@_J1$$QEAUScheduledUmpMessage@@P6A_NAEAU2@3@Z@Z; std::_Push_heap_by_index<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,ScheduledUmpMessage,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,__int64,__int64,ScheduledUmpMessage &&,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &))
0x18000a1c6  mov     rbx, [rsp+78h+arg_8]
0x18000a1ce  add     rsp, 40h
0x18000a1d2  pop     r15
0x18000a1d4  pop     r14
0x18000a1d6  pop     r13
0x18000a1d8  pop     r12
0x18000a1da  pop     rdi
0x18000a1db  pop     rsi
0x18000a1dc  pop     rbp
0x18000a1dd  retn
```
