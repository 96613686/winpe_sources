# CloudExperienceHostWAMExecuteCommand::SetSelection(IShellItemArray *)

- ea: `0x14000ca40`
- end: `0x14000ca7f`
- name: `?SetSelection@CloudExperienceHostWAMExecuteCommand@@UEAAJPEAUIShellItemArray@@@Z`
- size: `63`
- prototype: `__int64 __fastcall(CloudExperienceHostWAMExecuteCommand *__hidden this, struct IShellItemArray *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000ca40`
- `0x14000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloudExperienceHostWAMExecuteCommand::SetSelection(
        CloudExperienceHostWAMExecuteCommand *this,
        struct IShellItemArray *a2)
{
  __int64 v2; // rbx

  v2 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IShellItemArray *))a2->lpVtbl->AddRef)(a2);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x14000ca40  push    rbx
0x14000ca42  sub     rsp, 20h
0x14000ca46  mov     rbx, [rcx+10h]
0x14000ca4a  mov     [rcx+10h], rdx
0x14000ca4e  test    rdx, rdx
0x14000ca51  jz      short loc_14000CA62
0x14000ca53  mov     rax, [rdx]
0x14000ca56  mov     rcx, rdx
0x14000ca59  mov     rax, [rax+8]
0x14000ca5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca62  test    rbx, rbx
0x14000ca65  jz      short loc_14000CA77
0x14000ca67  mov     rax, [rbx]
0x14000ca6a  mov     rcx, rbx
0x14000ca6d  mov     rax, [rax+10h]
0x14000ca71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca76  nop
0x14000ca77  xor     eax, eax
0x14000ca79  add     rsp, 20h
0x14000ca7d  pop     rbx
0x14000ca7e  retn
```
