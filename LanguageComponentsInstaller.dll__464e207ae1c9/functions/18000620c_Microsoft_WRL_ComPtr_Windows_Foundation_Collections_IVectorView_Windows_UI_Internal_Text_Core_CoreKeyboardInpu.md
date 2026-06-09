# Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>>::~ComPtr<Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>>(void)

- ea: `0x18000620c`
- end: `0x180006234`
- name: `??1?$ComPtr@U?$IVectorView@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180027eca`
- `0x180027f22`
- `0x18002804b`
- `0x18002805d`
- `0x18002806f`
- `0x180028081`
- `0x180028401`
- `0x180029111`
- `0x18002914f`
- `0x18002931b`
- `0x18002932d`
- `0x180029363`
- `0x180029387`
- `0x1800297b4`

## callees

- `0x18000620c`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>>::~ComPtr<Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>>(
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
0x18000620c  sub     rsp, 28h
0x180006210  mov     rax, rcx
0x180006213  mov     rcx, [rcx]
0x180006216  test    rcx, rcx
0x180006219  jz      short loc_18000622F
0x18000621b  mov     qword ptr [rax], 0
0x180006222  mov     rax, [rcx]
0x180006225  mov     rax, [rax+10h]
0x180006229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000622e  nop
0x18000622f  add     rsp, 28h
0x180006233  retn
```
