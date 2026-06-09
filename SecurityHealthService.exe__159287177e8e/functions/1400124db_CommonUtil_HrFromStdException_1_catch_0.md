# _CommonUtil::HrFromStdException_::_1_::catch$0

- ea: `0x1400124db`
- end: `0x140012516`
- name: `_CommonUtil::HrFromStdException_::_1_::catch$0`
- size: `59`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140013010`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrFromStdException_::_1_::catch_0(__int64 a1, __int64 a2)
{
  int v3; // eax

  v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 32) + 16LL))(*(_QWORD *)(a2 + 32));
  if ( v3 >= 0 )
    v3 = -2147418113;
  *(_DWORD *)(a2 + 96) = v3;
  return 0;
}

```

## disassembly

```asm
0x1400124db  mov     [rsp+arg_8], rdx
0x1400124e0  push    rbp
0x1400124e1  sub     rsp, 20h
0x1400124e5  mov     rbp, rdx
0x1400124e8  mov     rcx, [rbp+20h]
0x1400124ec  mov     rax, [rcx]
0x1400124ef  mov     rax, [rax+10h]
0x1400124f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400124f8  mov     ecx, 8000FFFFh
0x1400124fd  test    eax, eax
0x1400124ff  cmovns  eax, ecx
0x140012502  mov     [rbp+60h], eax
0x140012505  mov     rax, 0
0x14001250f  add     rsp, 20h
0x140012513  pop     rbp
0x140012514  retn
```
