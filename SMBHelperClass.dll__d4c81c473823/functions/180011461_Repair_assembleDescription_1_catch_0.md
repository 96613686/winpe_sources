# _Repair::assembleDescription_::_1_::catch$0

- ea: `0x180011461`
- end: `0x18001149c`
- name: `_Repair::assembleDescription_::_1_::catch$0`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000257c`
- `0x18000ee10`
- `0x180011461`

## pseudocode

```c
void __fastcall __noreturn Repair::assembleDescription_::_1_::catch_0(__int64 a1, __int64 a2)
{
  if ( (*(_QWORD *)(*(_QWORD *)(a2 + 64) + 32LL) & 0xFFFFFFFFFFFF0000uLL) == 0 )
    FreeTestMemory(*(LPVOID *)(a2 + 80));
  *(_DWORD *)(a2 + 32) = *(_DWORD *)(a2 + 36);
  throw (TestException *)(a2 + 32);
}

```

## disassembly

```asm
0x180011461  mov     [rsp+arg_8], rdx
0x180011466  push    rbp
0x180011467  sub     rsp, 20h
0x18001146b  mov     rbp, rdx
0x18001146e  mov     rax, [rbp+40h]
0x180011472  test    qword ptr [rax+20h], 0FFFFFFFFFFFF0000h
0x18001147a  jnz     short loc_180011485
0x18001147c  mov     rcx, [rbp+50h]; pv
0x180011480  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x180011485  mov     eax, [rbp+24h]
0x180011488  mov     [rbp+20h], eax
0x18001148b  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x180011492  lea     rcx, [rbp+20h]; pExceptionObject
0x180011496  call    _CxxThrowException_0
```
