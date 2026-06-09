# CSystemPopupWindow::_DestroyWindow(void)

- ea: `0x140008698`
- end: `0x1400086db`
- name: `?_DestroyWindow@CSystemPopupWindow@@AEAAXXZ`
- size: `67`
- prototype: `void __fastcall(CSystemPopupWindow *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140008124`
- `0x1400086f0`

## callees

- `0x140008698`
- `0x14000a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSystemPopupWindow::_DestroyWindow(CSystemPopupWindow *this)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    *(_QWORD *)this = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 304LL))(v1);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  }
}

```

## disassembly

```asm
0x140008698  push    rbx
0x14000869a  sub     rsp, 30h
0x14000869e  mov     rbx, [rcx]
0x1400086a1  test    rbx, rbx
0x1400086a4  jz      short loc_1400086D5
0x1400086a6  mov     [rsp+38h+var_18], rbx
0x1400086ab  mov     qword ptr [rcx], 0
0x1400086b2  mov     rax, [rbx]
0x1400086b5  mov     rcx, rbx
0x1400086b8  mov     rax, [rax+130h]
0x1400086bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086c4  nop
0x1400086c5  mov     rax, [rbx]
0x1400086c8  mov     rcx, rbx
0x1400086cb  mov     rax, [rax+10h]
0x1400086cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086d4  nop
0x1400086d5  add     rsp, 30h
0x1400086d9  pop     rbx
0x1400086da  retn
```
