# CComPointer<IStorage>::operator=(IStorage *)

- ea: `0x180005f00`
- end: `0x180005f35`
- name: `??4?$CComPointer@UIStorage@@@@QEAAAEAV0@PEAUIStorage@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ba20`

## callees

- `0x180005f00`
- `0x18000e010`

## pseudocode

```c
_QWORD *__fastcall CComPointer<IStorage>::operator=(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rcx
  _QWORD *result; // rax

  v4 = *a1;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  result = a1;
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x180005f00  mov     [rsp+arg_0], rbx
0x180005f05  push    rdi
0x180005f06  sub     rsp, 20h
0x180005f0a  mov     rbx, rcx
0x180005f0d  mov     rdi, rdx
0x180005f10  mov     rcx, [rcx]
0x180005f13  test    rcx, rcx
0x180005f16  jz      short loc_180005F24
0x180005f18  mov     rax, [rcx]
0x180005f1b  mov     rax, [rax+10h]
0x180005f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f24  mov     rax, rbx
0x180005f27  mov     [rbx], rdi
0x180005f2a  mov     rbx, [rsp+28h+arg_0]
0x180005f2f  add     rsp, 20h
0x180005f33  pop     rdi
0x180005f34  retn
```
