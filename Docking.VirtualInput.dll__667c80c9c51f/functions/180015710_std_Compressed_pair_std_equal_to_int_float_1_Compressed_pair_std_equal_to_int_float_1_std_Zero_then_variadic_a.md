# std::_Compressed_pair<std::equal_to<int>,float,1>::_Compressed_pair<std::equal_to<int>,float,1>(std::_Zero_then_variadic_args_t,float &&)

- ea: `0x180015710`
- end: `0x180015743`
- name: `??$?0M@?$_Compressed_pair@U?$equal_to@H@std@@M$00@std@@QEAA@U_Zero_then_variadic_args_t@1@$$QEAM@Z`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015800`

## callees

- `0x18000b810`

## pseudocode

```c
_DWORD *__fastcall std::_Compressed_pair<std::equal_to<int>,float,1>::_Compressed_pair<std::equal_to<int>,float,1>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3)
{
  *a1 = *(_DWORD *)Microsoft::WRL::Details::Forward<std::nullptr_t>(a3);
  return a1;
}

```

## disassembly

```asm
0x180015710  mov     [rsp+arg_10], r8
0x180015715  mov     [rsp+arg_8], dl
0x180015719  mov     [rsp+arg_0], rcx
0x18001571e  sub     rsp, 28h
0x180015722  mov     rcx, [rsp+28h+arg_10]
0x180015727  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x18001572c  mov     rcx, [rsp+28h+arg_0]
0x180015731  movss   xmm0, dword ptr [rax]
0x180015735  movss   dword ptr [rcx], xmm0
0x180015739  mov     rax, [rsp+28h+arg_0]
0x18001573e  add     rsp, 28h
0x180015742  retn
```
