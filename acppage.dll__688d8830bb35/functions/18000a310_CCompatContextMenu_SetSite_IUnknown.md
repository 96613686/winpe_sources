# CCompatContextMenu::SetSite(IUnknown *)

- ea: `0x18000a310`
- end: `0x18000a360`
- name: `?SetSite@CCompatContextMenu@@UEAAJPEAUIUnknown@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(CCompatContextMenu *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a310`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CCompatContextMenu::SetSite(CCompatContextMenu *this, struct IUnknown *a2)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 74);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_QWORD *)this + 74) = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  return 0;
}

```

## disassembly

```asm
0x18000a310  mov     [rsp+arg_0], rbx
0x18000a315  push    rdi
0x18000a316  sub     rsp, 20h
0x18000a31a  mov     rdi, rcx
0x18000a31d  mov     rbx, rdx
0x18000a320  mov     rcx, [rcx+250h]
0x18000a327  test    rcx, rcx
0x18000a32a  jz      short loc_18000A338
0x18000a32c  mov     rax, [rcx]
0x18000a32f  mov     rax, [rax+10h]
0x18000a333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a338  mov     [rdi+250h], rbx
0x18000a33f  test    rbx, rbx
0x18000a342  jz      short loc_18000A353
0x18000a344  mov     rax, [rbx]
0x18000a347  mov     rcx, rbx
0x18000a34a  mov     rax, [rax+8]
0x18000a34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a353  mov     rbx, [rsp+28h+arg_0]
0x18000a358  xor     eax, eax
0x18000a35a  add     rsp, 20h
0x18000a35e  pop     rdi
0x18000a35f  retn
```
