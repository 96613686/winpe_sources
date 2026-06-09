# std::_List_alloc<0,std::_List_base_types<CommandSet,std::allocator<CommandSet>>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)

- ea: `0x140009328`
- end: `0x140009375`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z`
- size: `77`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008120`
- `0x140008290`
- `0x140008b38`
- `0x1400090ec`
- `0x140009ecc`

## callees

- `0x140001864`
- `0x140009328`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140009351`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140009351`

## pseudocode

```c
_QWORD *__fastcall std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *result; // rax

  result = operator new(0x48u);
  if ( !result )
  {
    std::_Xbad_alloc();
    __debugbreak();
  }
  if ( !a2 )
  {
    a2 = result;
    a3 = result;
  }
  *result = a2;
  result[1] = a3;
  return result;
}

```

## disassembly

```asm
0x140009328  mov     [rsp+arg_8], rbx
0x14000932d  mov     [rsp+arg_0], rcx
0x140009332  push    rdi
0x140009333  sub     rsp, 20h
0x140009337  mov     rdi, r8
0x14000933a  mov     rbx, rdx
0x14000933d  mov     ecx, 48h ; 'H'; Size
0x140009342  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009347  mov     [rsp+28h+arg_0], rax
0x14000934c  test    rax, rax
0x14000934f  jnz     short loc_140009358
0x140009351  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140009357  int     3; Trap to Debugger
0x140009358  test    rbx, rbx
0x14000935b  jnz     short loc_140009363
0x14000935d  mov     rbx, rax
0x140009360  mov     rdi, rax
0x140009363  mov     [rax], rbx
0x140009366  mov     [rax+8], rdi
0x14000936a  mov     rbx, [rsp+28h+arg_8]
0x14000936f  add     rsp, 20h
0x140009373  pop     rdi
0x140009374  retn
```
