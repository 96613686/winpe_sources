# ATL::CAtlComModule::ExecuteObjectMain(bool)

- ea: `0x18000f614`
- end: `0x18000f660`
- name: `?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z`
- size: `76`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001040`
- `0x18000f000`

## callees

- `0x18000f614`
- `0x180014010`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::ExecuteObjectMain(ATL::CAtlComModule *this, char a2)
{
  __int64 *v2; // rbx
  __int64 *v4; // rax

  v2 = off_18001C230[0];
  v4 = off_18001C238;
  while ( v2 < v4 )
  {
    if ( *v2 )
    {
      LOBYTE(this) = a2;
      (*(void (__fastcall **)(ATL::CAtlComModule *))(*v2 + 64))(this);
      v4 = off_18001C238;
    }
    ++v2;
  }
}

```

## disassembly

```asm
0x18000f614  mov     [rsp+arg_0], rbx
0x18000f619  push    rdi
0x18000f61a  sub     rsp, 20h
0x18000f61e  mov     rbx, cs:off_18001C230
0x18000f625  mov     dil, dl
0x18000f628  mov     rax, cs:off_18001C238
0x18000f62f  jmp     short loc_18000F650
0x18000f631  mov     r8, [rbx]
0x18000f634  test    r8, r8
0x18000f637  jz      short loc_18000F64C
0x18000f639  mov     rax, [r8+40h]
0x18000f63d  mov     cl, dil
0x18000f640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f645  mov     rax, cs:off_18001C238
0x18000f64c  add     rbx, 8
0x18000f650  cmp     rbx, rax
0x18000f653  jb      short loc_18000F631
0x18000f655  mov     rbx, [rsp+28h+arg_0]
0x18000f65a  add     rsp, 20h
0x18000f65e  pop     rdi
0x18000f65f  retn
```
