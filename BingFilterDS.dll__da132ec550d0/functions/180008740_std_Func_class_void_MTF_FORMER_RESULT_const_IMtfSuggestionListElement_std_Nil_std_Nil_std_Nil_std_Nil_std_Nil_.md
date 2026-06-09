# std::_Func_class<void,_MTF_FORMER_RESULT const &,IMtfSuggestionListElement *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::~_Func_class<void,_MTF_FORMER_RESULT const &,IMtfSuggestionListElement *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>(void)

- ea: `0x180008740`
- end: `0x180008772`
- name: `??1?$_Func_class@XAEBU_MTF_FORMER_RESULT@@PEAUIMtfSuggestionListElement@@U_Nil@std@@U34@U34@U34@U34@@std@@QEAA@XZ`
- size: `50`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cdc3`
- `0x18000ce13`
- `0x18000cea3`

## callees

- `0x180008740`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall std::_Func_class<void,_MTF_FORMER_RESULT const &,IMtfSuggestionListElement *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::~_Func_class<void,_MTF_FORMER_RESULT const &,IMtfSuggestionListElement *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>(
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
0x180008740  push    rbx
0x180008742  sub     rsp, 20h
0x180008746  mov     rbx, rcx
0x180008749  mov     rcx, [rcx+18h]
0x18000874d  test    rcx, rcx
0x180008750  jz      short loc_18000876C
0x180008752  mov     rax, [rcx]
0x180008755  cmp     rcx, rbx
0x180008758  setnz   dl
0x18000875b  mov     rax, [rax+20h]
0x18000875f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008764  mov     qword ptr [rbx+18h], 0
0x18000876c  add     rsp, 20h
0x180008770  pop     rbx
0x180008771  retn
```
