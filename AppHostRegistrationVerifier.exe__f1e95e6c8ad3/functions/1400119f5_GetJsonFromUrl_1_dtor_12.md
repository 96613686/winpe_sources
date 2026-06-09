# _GetJsonFromUrl_::_1_::dtor$12

- ea: `0x1400119f5`
- end: `0x140011a1e`
- name: `_GetJsonFromUrl_::_1_::dtor$12`
- size: `41`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140009e48`
- `0x1400119f5`

## pseudocode

```c
__int64 __fastcall GetJsonFromUrl_::_1_::dtor_12(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 96) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 96) &= ~1u;
    return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(*(_QWORD *)(a2 + 128));
  }
  return result;
}

```

## disassembly

```asm
0x1400119f5  push    rbp
0x1400119f7  sub     rsp, 20h
0x1400119fb  mov     rbp, rdx
0x1400119fe  mov     eax, [rbp+60h]
0x140011a01  and     eax, 1
0x140011a04  test    eax, eax
0x140011a06  jz      short loc_140011A18
0x140011a08  and     dword ptr [rbp+60h], 0FFFFFFFEh
0x140011a0c  mov     rcx, [rbp+80h]
0x140011a13  call    ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
0x140011a18  add     rsp, 20h
0x140011a1c  pop     rbp
0x140011a1d  retn
```
