# CEditionUpgradeBroker::`scalar deleting destructor'(uint)

- ea: `0x180008570`
- end: `0x1800085c4`
- name: `??_GCEditionUpgradeBroker@@UEAAPEAXI@Z`
- size: `84`
- prototype: `CEditionUpgradeBroker *__fastcall(CEditionUpgradeBroker *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001cb0`
- `0x180008570`
- `0x180027010`

## pseudocode

```c
CEditionUpgradeBroker *__fastcall CEditionUpgradeBroker::`scalar deleting destructor'(
        CEditionUpgradeBroker *this,
        char a2)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 6);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 6) = 0;
  }
  *((_DWORD *)this + 9) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008570  mov     [rsp+arg_0], rbx
0x180008575  push    rdi
0x180008576  sub     rsp, 20h
0x18000857a  mov     rbx, rcx
0x18000857d  mov     edi, edx
0x18000857f  mov     rcx, [rcx+30h]
0x180008583  test    rcx, rcx
0x180008586  jz      short loc_18000859C
0x180008588  mov     rax, [rcx]
0x18000858b  mov     rax, [rax+10h]
0x18000858f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008594  mov     qword ptr [rbx+30h], 0
0x18000859c  mov     dword ptr [rbx+24h], 0C0000001h
0x1800085a3  test    dil, 1
0x1800085a7  jz      short loc_1800085B6
0x1800085a9  mov     edx, 38h ; '8'; unsigned __int64
0x1800085ae  mov     rcx, rbx; void *
0x1800085b1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800085b6  mov     rax, rbx
0x1800085b9  mov     rbx, [rsp+28h+arg_0]
0x1800085be  add     rsp, 20h
0x1800085c2  pop     rdi
0x1800085c3  retn
```
