# Microsoft::WRL::ComPtr<Windows::System::Internal::Clip::ISubscriptionsManager>::~ComPtr<Windows::System::Internal::Clip::ISubscriptionsManager>(void)

- ea: `0x140005c70`
- end: `0x140005c97`
- name: `??1?$ComPtr@UISubscriptionsManager@Clip@Internal@System@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `39`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007dcc`

## callees

- `0x140005c70`
- `0x140014010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::System::Internal::Clip::ISubscriptionsManager>::~ComPtr<Windows::System::Internal::Clip::ISubscriptionsManager>(
        _QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x140005c70  sub     rsp, 28h
0x140005c74  mov     rax, rcx
0x140005c77  mov     rcx, [rcx]
0x140005c7a  test    rcx, rcx
0x140005c7d  jz      short loc_140005C92
0x140005c7f  mov     qword ptr [rax], 0
0x140005c86  mov     rax, [rcx]
0x140005c89  mov     rax, [rax+10h]
0x140005c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c92  add     rsp, 28h
0x140005c96  retn
```
