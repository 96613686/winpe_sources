# _GetAppUriHandlerJsonFromWebHost_::_1_::dtor$0

- ea: `0x140011813`
- end: `0x140011839`
- name: `_GetAppUriHandlerJsonFromWebHost_::_1_::dtor$0`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140009e48`
- `0x140011813`

## pseudocode

```c
__int64 __fastcall GetAppUriHandlerJsonFromWebHost_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(*(_QWORD *)(a2 + 48));
  }
  return result;
}

```

## disassembly

```asm
0x140011813  push    rbp
0x140011815  sub     rsp, 20h
0x140011819  mov     rbp, rdx
0x14001181c  mov     eax, [rbp+20h]
0x14001181f  and     eax, 1
0x140011822  test    eax, eax
0x140011824  jz      short loc_140011833
0x140011826  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x14001182a  mov     rcx, [rbp+30h]
0x14001182e  call    ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
0x140011833  add     rsp, 20h
0x140011837  pop     rbp
0x140011838  retn
```
