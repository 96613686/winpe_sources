# ATL::CAtlComModule::ExecuteObjectMain(bool)

- ea: `0x14000d4e0`
- end: `0x14000d52c`
- name: `?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z`
- size: `76`
- prototype: `void __fastcall(ATL::CAtlComModule *this, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000ca6c`
- `0x14000cb68`

## callees

- `0x14000d4e0`
- `0x140017010`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::ExecuteObjectMain(ATL::CAtlComModule *this, char a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v4; // rax

  v2 = off_1400211F0;
  v4 = off_1400211F8;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 )
  {
    if ( *v2 )
    {
      LOBYTE(this) = a2;
      (*((void (__fastcall **)(ATL::CAtlComModule *))*v2 + 8))(this);
      v4 = off_1400211F8;
    }
    ++v2;
  }
}

```

## disassembly

```asm
0x14000d4e0  mov     [rsp+arg_0], rbx
0x14000d4e5  push    rdi
0x14000d4e6  sub     rsp, 20h
0x14000d4ea  mov     rbx, cs:off_1400211F0
0x14000d4f1  mov     dil, dl
0x14000d4f4  mov     rax, cs:off_1400211F8
0x14000d4fb  jmp     short loc_14000D51C
0x14000d4fd  mov     r8, [rbx]
0x14000d500  test    r8, r8
0x14000d503  jz      short loc_14000D518
0x14000d505  mov     rax, [r8+40h]
0x14000d509  mov     cl, dil
0x14000d50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d511  mov     rax, cs:off_1400211F8
0x14000d518  add     rbx, 8
0x14000d51c  cmp     rbx, rax
0x14000d51f  jb      short loc_14000D4FD
0x14000d521  mov     rbx, [rsp+28h+arg_0]
0x14000d526  add     rsp, 20h
0x14000d52a  pop     rdi
0x14000d52b  retn
```
