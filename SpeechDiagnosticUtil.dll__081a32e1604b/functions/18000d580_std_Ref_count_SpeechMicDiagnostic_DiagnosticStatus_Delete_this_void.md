# std::_Ref_count<SpeechMicDiagnostic::DiagnosticStatus>::_Delete_this(void)

- ea: `0x18000d580`
- end: `0x18000d5a0`
- name: `?_Delete_this@?$_Ref_count@VDiagnosticStatus@SpeechMicDiagnostic@@@std@@EEAAXXZ`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000d580`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count<SpeechMicDiagnostic::DiagnosticStatus>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x18000d580  sub     rsp, 28h
0x18000d584  test    rcx, rcx
0x18000d587  jz      short loc_18000D59A
0x18000d589  mov     rax, [rcx]
0x18000d58c  mov     edx, 1
0x18000d591  mov     rax, [rax+10h]
0x18000d595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d59a  add     rsp, 28h
0x18000d59e  retn
```
