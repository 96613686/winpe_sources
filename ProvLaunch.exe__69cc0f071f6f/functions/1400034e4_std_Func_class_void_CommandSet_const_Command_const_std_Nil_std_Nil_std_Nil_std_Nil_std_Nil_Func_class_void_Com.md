# std::_Func_class<void,CommandSet const &,Command const &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::~_Func_class<void,CommandSet const &,Command const &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>(void)

- ea: `0x1400034e4`
- end: `0x140003516`
- name: `??1?$_Func_class@XAEBUCommandSet@@AEBUCommand@@U_Nil@std@@U34@U34@U34@U34@@std@@QEAA@XZ`
- size: `50`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a9cd`
- `0x14000a9df`

## callees

- `0x1400034e4`
- `0x14000b010`

## pseudocode

```c
__int64 __fastcall std::_Func_class<void,CommandSet const &,Command const &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::~_Func_class<void,CommandSet const &,Command const &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *(_QWORD *)(a1 + 24);
  if ( v3 )
  {
    LOBYTE(a2) = v3 != a1;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, a2);
    *(_QWORD *)(a1 + 24) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400034e4  push    rbx
0x1400034e6  sub     rsp, 20h
0x1400034ea  mov     rbx, rcx
0x1400034ed  mov     rcx, [rcx+18h]
0x1400034f1  test    rcx, rcx
0x1400034f4  jz      short loc_140003510
0x1400034f6  mov     rax, [rcx]
0x1400034f9  cmp     rcx, rbx
0x1400034fc  setnz   dl
0x1400034ff  mov     rax, [rax+20h]
0x140003503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003508  mov     qword ptr [rbx+18h], 0
0x140003510  add     rsp, 20h
0x140003514  pop     rbx
0x140003515  retn
```
