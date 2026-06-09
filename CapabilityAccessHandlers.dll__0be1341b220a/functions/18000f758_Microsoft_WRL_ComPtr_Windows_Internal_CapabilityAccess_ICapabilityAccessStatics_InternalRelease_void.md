# Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)

- ea: `0x18000f758`
- end: `0x18000f77e`
- name: `?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f530`
- `0x18000f954`
- `0x18001018c`
- `0x180010a5c`
- `0x18001248c`

## callees

- `0x18000f758`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(
        __int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x18000f758  sub     rsp, 28h
0x18000f75c  mov     rdx, rcx
0x18000f75f  xor     eax, eax
0x18000f761  mov     rcx, [rcx]
0x18000f764  test    rcx, rcx
0x18000f767  jz      short loc_18000F779
0x18000f769  mov     [rdx], rax
0x18000f76c  mov     rax, [rcx]
0x18000f76f  mov     rax, [rax+10h]
0x18000f773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f778  nop
0x18000f779  add     rsp, 28h
0x18000f77d  retn
```
