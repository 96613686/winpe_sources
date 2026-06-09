# _NDFRepairConversionClosure::operator()_::_1_::catch$1

- ea: `0x180010e92`
- end: `0x180010ec7`
- name: `_NDFRepairConversionClosure::operator()_::_1_::catch$1`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000257c`
- `0x18000ee10`

## pseudocode

```c
void __fastcall __noreturn NDFRepairConversionClosure::operator()_::_1_::catch_1(__int64 a1, __int64 a2)
{
  FreeTestMemory(*(LPVOID *)(*(_QWORD *)(*(_QWORD *)(a2 + 96) + 8LL) + 24LL));
  *(_DWORD *)(a2 + 36) = *(_DWORD *)(a2 + 44);
  throw (TestException *)(a2 + 36);
}

```

## disassembly

```asm
0x180010e92  mov     [rsp+arg_8], rdx
0x180010e97  push    rbp
0x180010e98  sub     rsp, 20h
0x180010e9c  mov     rbp, rdx
0x180010e9f  mov     rax, [rbp+60h]
0x180010ea3  mov     rcx, [rax+8]
0x180010ea7  mov     rcx, [rcx+18h]; pv
0x180010eab  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x180010eb0  mov     eax, [rbp+2Ch]
0x180010eb3  mov     [rbp+24h], eax
0x180010eb6  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x180010ebd  lea     rcx, [rbp+24h]; pExceptionObject
0x180010ec1  call    _CxxThrowException_0
```
