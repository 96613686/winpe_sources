# Apx::ApfDevice_ReadyProcess::`vector deleting destructor'(uint)

- ea: `0x18000e980`
- end: `0x18000e9ab`
- name: `??_EApfDevice_ReadyProcess@Apx@@UEAAPEAXI@Z`
- size: `43`
- prototype: `Apx::ApfDevice_ReadyProcess *__fastcall(Apx::ApfDevice_ReadyProcess *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002100`
- `0x18000e980`

## pseudocode

```c
Apx::ApfDevice_ReadyProcess *__fastcall Apx::ApfDevice_ReadyProcess::`vector deleting destructor'(
        Apx::ApfDevice_ReadyProcess *this,
        char a2)
{
  *(_QWORD *)this = &Apx::ApfWorkItemBase::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x10);
  return this;
}

```

## disassembly

```asm
0x18000e980  push    rbx
0x18000e982  sub     rsp, 20h
0x18000e986  lea     rax, ??_7ApfWorkItemBase@Apx@@6B@; const Apx::ApfWorkItemBase::`vftable'
0x18000e98d  mov     rbx, rcx
0x18000e990  mov     [rcx], rax
0x18000e993  test    dl, 1
0x18000e996  jz      short loc_18000E9A2
0x18000e998  mov     edx, 10h; struct std::nothrow_t *
0x18000e99d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e9a2  mov     rax, rbx
0x18000e9a5  add     rsp, 20h
0x18000e9a9  pop     rbx
0x18000e9aa  retn
```
