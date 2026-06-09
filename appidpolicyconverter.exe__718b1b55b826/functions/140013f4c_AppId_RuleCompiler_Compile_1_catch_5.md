# _AppId::RuleCompiler::Compile_::_1_::catch$5

- ea: `0x140013f4c`
- end: `0x140013f76`
- name: `_AppId::RuleCompiler::Compile_::_1_::catch$5`
- size: `42`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008018`

## pseudocode

```c
__int64 __fastcall AppId::RuleCompiler::Compile_::_1_::catch_5(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 32) = Sharp::Util::HResultFromStdException(*(Sharp::Util **)(a2 + 48), (const struct exception *)a2);
  return 0;
}

```

## disassembly

```asm
0x140013f4c  mov     [rsp+arg_8], rdx
0x140013f51  push    rbp
0x140013f52  sub     rsp, 20h
0x140013f56  mov     rbp, rdx
0x140013f59  mov     rcx, [rbp+30h]; this
0x140013f5d  call    ?HResultFromStdException@Util@Sharp@@YAJAEBVexception@@@Z; Sharp::Util::HResultFromStdException(exception const &)
0x140013f62  mov     [rbp+20h], eax
0x140013f65  mov     rax, 0
0x140013f6f  add     rsp, 20h
0x140013f73  pop     rbp
0x140013f74  retn
```
