# _tlgDataDescInit<_tlgIndexSequence<1,0>>::Fill<_tlgWrapperByVal<4>>(_EVENT_DATA_DESCRIPTOR *,_tlgWrapperByVal<4> const &)

- ea: `0x180002f9c`
- end: `0x180002fd9`
- name: `??$Fill@U?$_tlgWrapperByVal@$03@@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$00$0A@@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002fe0`

## callees

- `0x180001ae4`
- `0x180002f90`

## pseudocode

```c
__int64 __fastcall _tlgDataDescInit<_tlgIndexSequence<1,0>>::Fill<_tlgWrapperByVal<4>>(_QWORD *a1, __int64 a2)
{
  _QWORD *v2; // rax

  v2 = _tlgWrapperByVal<4>::Fill(a2, a1);
  return wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ControllerHostLogging,_TlgReflectorTag_Param0IsProviderType>::OnStopped(v2);
}

```

## disassembly

```asm
0x180002f9c  mov     [rsp+arg_8], rdx
0x180002fa1  mov     [rsp+arg_0], rcx
0x180002fa6  sub     rsp, 28h
0x180002faa  mov     eax, 10h
0x180002faf  imul    rax, 0
0x180002fb3  mov     rcx, [rsp+28h+arg_0]
0x180002fb8  add     rcx, rax
0x180002fbb  mov     rax, rcx
0x180002fbe  mov     rdx, rax
0x180002fc1  mov     rcx, [rsp+28h+arg_8]
0x180002fc6  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z
0x180002fcb  mov     rcx, rax
0x180002fce  call    ?OnStopped@?$ActivityData@VControllerHostLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXXZ
0x180002fd3  nop
0x180002fd4  add     rsp, 28h
0x180002fd8  retn
```
