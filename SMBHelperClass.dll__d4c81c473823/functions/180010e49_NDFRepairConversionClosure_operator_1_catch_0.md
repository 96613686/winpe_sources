# _NDFRepairConversionClosure::operator()_::_1_::catch$0

- ea: `0x180010e49`
- end: `0x180010e8c`
- name: `_NDFRepairConversionClosure::operator()_::_1_::catch$0`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000257c`
- `0x18000ee10`

## pseudocode

```c
void __fastcall __noreturn NDFRepairConversionClosure::operator()_::_1_::catch_0(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx

  v3 = *(_QWORD *)(a2 + 96);
  FreeTestMemory(*(LPVOID *)(*(_QWORD *)(v3 + 8) + 24LL));
  FreeTestMemory(*(LPVOID *)(*(_QWORD *)(v3 + 8) + 16LL));
  *(_DWORD *)(a2 + 32) = *(_DWORD *)(a2 + 40);
  throw (TestException *)(a2 + 32);
}

```

## disassembly

```asm
0x180010e49  mov     [rsp+arg_8], rdx
0x180010e4e  push    rbx
0x180010e4f  push    rbp
0x180010e50  sub     rsp, 28h
0x180010e54  mov     rbp, rdx
0x180010e57  mov     rbx, [rbp+60h]
0x180010e5b  mov     rcx, [rbx+8]
0x180010e5f  mov     rcx, [rcx+18h]; pv
0x180010e63  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x180010e68  mov     rcx, [rbx+8]
0x180010e6c  mov     rcx, [rcx+10h]; pv
0x180010e70  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x180010e75  mov     eax, [rbp+28h]
0x180010e78  mov     [rbp+20h], eax
0x180010e7b  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x180010e82  lea     rcx, [rbp+20h]; pExceptionObject
0x180010e86  call    _CxxThrowException_0
```
