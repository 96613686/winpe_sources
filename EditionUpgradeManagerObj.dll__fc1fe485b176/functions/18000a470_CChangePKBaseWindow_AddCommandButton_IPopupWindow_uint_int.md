# CChangePKBaseWindow::AddCommandButton(IPopupWindow *,uint,int)

- ea: `0x18000a470`
- end: `0x18000a489`
- name: `?AddCommandButton@CChangePKBaseWindow@@UEAAJPEAUIPopupWindow@@IH@Z`
- size: `25`
- prototype: `__int64 __fastcall(CChangePKBaseWindow *this, struct IPopupWindow *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180023010`

## pseudocode

```c
__int64 __fastcall CChangePKBaseWindow::AddCommandButton(
        CChangePKBaseWindow *this,
        struct IPopupWindow *a2,
        unsigned int a3)
{
  return (*(__int64 (__fastcall **)(CChangePKBaseWindow *, struct IPopupWindow *, _QWORD))(*(_QWORD *)this + 32LL))(
           this,
           a2,
           *((_DWORD *)this + 10) | a3);
}

```

## disassembly

```asm
0x18000a470  sub     rsp, 38h
0x18000a474  mov     rax, [rcx]
0x18000a477  or      r8d, [rcx+28h]
0x18000a47b  mov     rax, [rax+20h]
0x18000a47f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a484  add     rsp, 38h
0x18000a488  retn
```
