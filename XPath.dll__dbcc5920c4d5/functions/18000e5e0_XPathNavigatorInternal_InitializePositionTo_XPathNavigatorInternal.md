# XPathNavigatorInternal::InitializePositionTo(XPathNavigatorInternal &)

- ea: `0x18000e5e0`
- end: `0x18000e661`
- name: `?InitializePositionTo@XPathNavigatorInternal@@QEAAJAEAV1@@Z`
- size: `129`
- prototype: `__int64 __fastcall(struct IUnknown **this, struct XPathNavigatorInternal *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cc54`
- `0x18000d7f0`
- `0x18000d8a0`

## callees

- `0x180004b84`
- `0x18000e5e0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathNavigatorInternal::InitializePositionTo(
        struct IUnknown **this,
        struct XPathNavigatorInternal *a2)
{
  __int64 v3; // rcx
  __int64 v5; // rcx
  __int64 result; // rax

  *((_BYTE *)this + 16) = 0;
  v3 = (__int64)*this;
  if ( !v3 )
  {
    v5 = *(_QWORD *)a2;
    goto LABEL_3;
  }
  result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 168LL))(v3, *(_QWORD *)a2);
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)result != 1 )
    {
LABEL_4:
      *((_BYTE *)this + 16) = *((_BYTE *)a2 + 16);
      *((_DWORD *)this + 3) = *((_DWORD *)a2 + 3);
      *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
      return 0;
    }
    if ( *this )
      ATL::AtlComPtrAssign(this, 0);
    v5 = *(_QWORD *)a2;
LABEL_3:
    result = (*(__int64 (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v5 + 88LL))(v5, this);
    if ( (int)result < 0 )
      return result;
    goto LABEL_4;
  }
  return result;
}

```

## disassembly

```asm
0x18000e5e0  mov     [rsp+arg_0], rbx
0x18000e5e5  push    rdi
0x18000e5e6  sub     rsp, 20h
0x18000e5ea  mov     rbx, rcx
0x18000e5ed  mov     byte ptr [rcx+10h], 0
0x18000e5f1  mov     rcx, [rcx]
0x18000e5f4  mov     rdi, rdx
0x18000e5f7  test    rcx, rcx
0x18000e5fa  jnz     short loc_18000E631
0x18000e5fc  mov     rcx, [rdx]
0x18000e5ff  mov     rax, [rcx]
0x18000e602  mov     rdx, rbx
0x18000e605  mov     rax, [rax+58h]
0x18000e609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e60e  test    eax, eax
0x18000e610  js      short loc_18000E626
0x18000e612  mov     al, [rdi+10h]
0x18000e615  mov     [rbx+10h], al
0x18000e618  mov     eax, [rdi+0Ch]
0x18000e61b  mov     [rbx+0Ch], eax
0x18000e61e  mov     eax, [rdi+8]
0x18000e621  mov     [rbx+8], eax
0x18000e624  xor     eax, eax
0x18000e626  mov     rbx, [rsp+28h+arg_0]
0x18000e62b  add     rsp, 20h
0x18000e62f  pop     rdi
0x18000e630  retn
0x18000e631  mov     rax, [rcx]
0x18000e634  mov     rdx, [rdx]
0x18000e637  mov     rax, [rax+0A8h]
0x18000e63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e643  test    eax, eax
0x18000e645  js      short loc_18000E626
0x18000e647  cmp     eax, 1
0x18000e64a  jnz     short loc_18000E612
0x18000e64c  cmp     qword ptr [rbx], 0
0x18000e650  jz      short loc_18000E65C
0x18000e652  xor     edx, edx; struct IUnknown *
0x18000e654  mov     rcx, rbx; struct IUnknown **
0x18000e657  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000e65c  mov     rcx, [rdi]
0x18000e65f  jmp     short loc_18000E5FF
```
