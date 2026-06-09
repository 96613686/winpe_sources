# Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>>(void)

- ea: `0x140004794`
- end: `0x1400047bc`
- name: `??1?$ComPtr@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowSizeChangedEventArgs@234@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013101`
- `0x1400132dd`
- `0x140013301`
- `0x14001336d`
- `0x1400138a2`
- `0x1400138c6`

## callees

- `0x140004794`
- `0x140014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>>(
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
0x140004794  sub     rsp, 28h
0x140004798  mov     rax, rcx
0x14000479b  mov     rcx, [rcx]
0x14000479e  test    rcx, rcx
0x1400047a1  jz      short loc_1400047B7
0x1400047a3  mov     qword ptr [rax], 0
0x1400047aa  mov     rax, [rcx]
0x1400047ad  mov     rax, [rax+10h]
0x1400047b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047b6  nop
0x1400047b7  add     rsp, 28h
0x1400047bb  retn
```
