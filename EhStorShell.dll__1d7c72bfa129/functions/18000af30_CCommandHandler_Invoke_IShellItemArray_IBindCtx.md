# CCommandHandler::Invoke(IShellItemArray *,IBindCtx *)

- ea: `0x18000af30`
- end: `0x18000af68`
- name: `?Invoke@CCommandHandler@@UEAAJPEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `56`
- prototype: `__int64 __fastcall(CCommandHandler *__hidden this, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af30`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CCommandHandler::Invoke(CCommandHandler *this, struct IShellItemArray *a2, struct IBindCtx *a3)
{
  if ( *((_DWORD *)this + 16) == 1 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IBindCtx *))(**((_QWORD **)this + 5) + 32LL))(
             *((_QWORD *)this + 5),
             (unsigned int)(*((_DWORD *)this + 16) - 1),
             a3);
  if ( *((_DWORD *)this + 16) == 2 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 5) + 24LL))(
             *((_QWORD *)this + 5),
             0,
             0);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000af30  mov     edx, [rcx+40h]
0x18000af33  sub     edx, 1
0x18000af36  jz      short loc_18000AF58
0x18000af38  cmp     edx, 1
0x18000af3b  jz      short loc_18000AF43
0x18000af3d  mov     eax, 80004005h
0x18000af42  retn
0x18000af43  mov     rcx, [rcx+28h]
0x18000af47  xor     r8d, r8d
0x18000af4a  xor     edx, edx
0x18000af4c  mov     rax, [rcx]
0x18000af4f  mov     rax, [rax+18h]
0x18000af53  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000af58  mov     rcx, [rcx+28h]
0x18000af5c  mov     rax, [rcx]
0x18000af5f  mov     rax, [rax+20h]
0x18000af63  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
