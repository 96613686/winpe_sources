# _CommonUtil::HrFromStdException_::_1_::catch$0

- ea: `0x1800099ce`
- end: `0x180009a09`
- name: `_CommonUtil::HrFromStdException_::_1_::catch$0`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a010`

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
0x1800099ce  mov     [rsp+arg_8], rdx
0x1800099d3  push    rbp
0x1800099d4  sub     rsp, 20h
0x1800099d8  mov     rbp, rdx
0x1800099db  mov     rcx, [rbp+20h]
0x1800099df  mov     rax, [rcx]
0x1800099e2  mov     rax, [rax+10h]
0x1800099e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099eb  mov     ecx, 8000FFFFh
0x1800099f0  test    eax, eax
0x1800099f2  cmovns  eax, ecx
0x1800099f5  mov     [rbp+60h], eax
0x1800099f8  mov     rax, 0
0x180009a02  add     rsp, 20h
0x180009a06  pop     rbp
0x180009a07  retn
```
