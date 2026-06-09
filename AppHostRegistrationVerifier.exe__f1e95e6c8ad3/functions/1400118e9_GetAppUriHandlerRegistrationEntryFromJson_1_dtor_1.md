# _GetAppUriHandlerRegistrationEntryFromJson_::_1_::dtor$1

- ea: `0x1400118e9`
- end: `0x14001190f`
- name: `_GetAppUriHandlerRegistrationEntryFromJson_::_1_::dtor$1`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140009e48`
- `0x1400118e9`

## pseudocode

```c
__int64 __fastcall GetAppUriHandlerRegistrationEntryFromJson_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 64) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~1u;
    return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(*(_QWORD *)(a2 + 72));
  }
  return result;
}

```

## disassembly

```asm
0x1400118e9  push    rbp
0x1400118eb  sub     rsp, 20h
0x1400118ef  mov     rbp, rdx
0x1400118f2  mov     eax, [rbp+40h]
0x1400118f5  and     eax, 1
0x1400118f8  test    eax, eax
0x1400118fa  jz      short loc_140011909
0x1400118fc  and     dword ptr [rbp+40h], 0FFFFFFFEh
0x140011900  mov     rcx, [rbp+48h]
0x140011904  call    ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
0x140011909  add     rsp, 20h
0x14001190d  pop     rbp
0x14001190e  retn
```
