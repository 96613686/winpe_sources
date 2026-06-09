# _CommonUtil::HrFromStdException_::_1_::catch$0

- ea: `0x14000fdfe`
- end: `0x14000fe39`
- name: `_CommonUtil::HrFromStdException_::_1_::catch$0`
- size: `59`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140011010`

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
0x14000fdfe  mov     [rsp+arg_8], rdx
0x14000fe03  push    rbp
0x14000fe04  sub     rsp, 20h
0x14000fe08  mov     rbp, rdx
0x14000fe0b  mov     rcx, [rbp+20h]
0x14000fe0f  mov     rax, [rcx]
0x14000fe12  mov     rax, [rax+10h]
0x14000fe16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe1b  mov     ecx, 8000FFFFh
0x14000fe20  test    eax, eax
0x14000fe22  cmovns  eax, ecx
0x14000fe25  mov     [rbp+60h], eax
0x14000fe28  mov     rax, 0
0x14000fe32  add     rsp, 20h
0x14000fe36  pop     rbp
0x14000fe37  retn
```
