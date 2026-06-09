# std::_Push_heap_by_index<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,ScheduledUmpMessage,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,__int64,__int64,ScheduledUmpMessage &&,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &))

- ea: `0x18000a1e4`
- end: `0x18000a298`
- name: `??$_Push_heap_by_index@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UScheduledUmpMessage@@@std@@@std@@@std@@UScheduledUmpMessage@@P6A_NAEAU3@0@Z@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UScheduledUmpMessage@@@std@@@std@@@0@_J1$$QEAUScheduledUmpMessage@@P6A_NAEAU2@3@Z@Z`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a08c`
- `0x18000a518`

## callees

- `0x18000a1e4`
- `0x18000a99c`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall std::_Push_heap_by_index<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,ScheduledUmpMessage,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 (__fastcall *a5)(_QWORD, __int64))
{
  __int64 v6; // rdi
  __int64 v8; // rsi
  __int64 v9; // r15
  __int64 v10; // r14

  v6 = a2;
  if ( a2 > 0 )
  {
    v8 = *a1;
    v9 = a1[1];
    do
    {
      v10 = (v6 - 1) >> 1;
      if ( !a5(*(_QWORD *)(*(_QWORD *)(v8 + 8) + 8 * ((v10 + v9) & (*(_QWORD *)(v8 + 16) - 1LL))), a4) )
        break;
      ScheduledUmpMessage::operator=(
        *(_QWORD *)(*(_QWORD *)(v8 + 8) + 8 * ((*(_QWORD *)(v8 + 16) - 1LL) & (v9 + v6))),
        *(_QWORD *)(*(_QWORD *)(v8 + 8) + 8 * ((v10 + v9) & (*(_QWORD *)(v8 + 16) - 1LL))));
      v6 = (v6 - 1) >> 1;
    }
    while ( v10 > 0 );
  }
  return ScheduledUmpMessage::operator=(
           *(_QWORD *)(*(_QWORD *)(*a1 + 8LL) + 8 * ((*(_QWORD *)(*a1 + 16LL) - 1LL) & (v6 + a1[1]))),
           a4);
}

```

## disassembly

```asm
0x18000a1e4  push    rbx
0x18000a1e6  push    rbp
0x18000a1e7  push    rsi
0x18000a1e8  push    rdi
0x18000a1e9  push    r12
0x18000a1eb  push    r14
0x18000a1ed  push    r15
0x18000a1ef  sub     rsp, 20h
0x18000a1f3  mov     rbp, r9
0x18000a1f6  mov     rdi, rdx
0x18000a1f9  mov     rbx, rcx
0x18000a1fc  test    rdx, rdx
0x18000a1ff  jle     short loc_18000A266
0x18000a201  mov     rsi, [rcx]
0x18000a204  mov     r15, [rcx+8]
0x18000a208  mov     rax, [rsi+10h]
0x18000a20c  lea     r14, [rdi-1]
0x18000a210  mov     rcx, [rsi+8]
0x18000a214  dec     rax
0x18000a217  sar     r14, 1
0x18000a21a  mov     rdx, rbp
0x18000a21d  lea     r12, [r14+r15]
0x18000a221  and     rax, r12
0x18000a224  mov     rcx, [rcx+rax*8]
0x18000a228  mov     rax, [rsp+58h+arg_20]
0x18000a230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a235  test    al, al
0x18000a237  jz      short loc_18000A266
0x18000a239  mov     r8, [rsi+8]
0x18000a23d  lea     rcx, [r15+rdi]
0x18000a241  mov     rax, [rsi+10h]
0x18000a245  dec     rax
0x18000a248  mov     rdx, rax
0x18000a24b  and     rcx, rax
0x18000a24e  and     rdx, r12
0x18000a251  mov     rcx, [r8+rcx*8]
0x18000a255  mov     rdx, [r8+rdx*8]
0x18000a259  call    ??4ScheduledUmpMessage@@QEAAAEAU0@$$QEAU0@@Z; ScheduledUmpMessage::operator=(ScheduledUmpMessage &&)
0x18000a25e  mov     rdi, r14
0x18000a261  test    r14, r14
0x18000a264  jg      short loc_18000A208
0x18000a266  mov     rcx, [rbx]
0x18000a269  mov     rdx, rbp
0x18000a26c  mov     r8, [rbx+8]
0x18000a270  add     r8, rdi
0x18000a273  mov     rax, [rcx+10h]
0x18000a277  mov     rcx, [rcx+8]
0x18000a27b  dec     rax
0x18000a27e  and     r8, rax
0x18000a281  mov     rcx, [rcx+r8*8]
0x18000a285  add     rsp, 20h
0x18000a289  pop     r15
0x18000a28b  pop     r14
0x18000a28d  pop     r12
0x18000a28f  pop     rdi
0x18000a290  pop     rsi
0x18000a291  pop     rbp
0x18000a292  pop     rbx
0x18000a293  jmp     ??4ScheduledUmpMessage@@QEAAAEAU0@$$QEAU0@@Z; ScheduledUmpMessage::operator=(ScheduledUmpMessage &&)
```
