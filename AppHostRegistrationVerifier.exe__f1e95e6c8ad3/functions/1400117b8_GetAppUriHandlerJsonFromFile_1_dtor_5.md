# _GetAppUriHandlerJsonFromFile_::_1_::dtor$5

- ea: `0x1400117b8`
- end: `0x1400117de`
- name: `_GetAppUriHandlerJsonFromFile_::_1_::dtor$5`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140009e48`
- `0x1400117b8`

## pseudocode

```c
__int64 __fastcall GetAppUriHandlerJsonFromFile_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(*(_QWORD *)(a2 + 72));
  }
  return result;
}

```

## disassembly

```asm
0x1400117b8  push    rbp
0x1400117ba  sub     rsp, 20h
0x1400117be  mov     rbp, rdx
0x1400117c1  mov     eax, [rbp+30h]
0x1400117c4  and     eax, 1
0x1400117c7  test    eax, eax
0x1400117c9  jz      short loc_1400117D8
0x1400117cb  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x1400117cf  mov     rcx, [rbp+48h]
0x1400117d3  call    ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
0x1400117d8  add     rsp, 20h
0x1400117dc  pop     rbp
0x1400117dd  retn
```
