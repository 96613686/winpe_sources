# Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)

- ea: `0x1800071a4`
- end: `0x1800071c9`
- name: `?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `37`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007030`
- `0x1800075a0`
- `0x180007bc0`
- `0x180008b68`
- `0x1800092a8`
- `0x180009474`
- `0x1800096e8`
- `0x180009af8`
- `0x180009fc0`

## callees

- `0x1800071a4`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(
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
0x1800071a4  sub     rsp, 28h
0x1800071a8  mov     rdx, rcx
0x1800071ab  xor     eax, eax
0x1800071ad  mov     rcx, [rcx]
0x1800071b0  test    rcx, rcx
0x1800071b3  jz      short loc_1800071C4
0x1800071b5  mov     [rdx], rax
0x1800071b8  mov     rax, [rcx]
0x1800071bb  mov     rax, [rax+10h]
0x1800071bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071c4  add     rsp, 28h
0x1800071c8  retn
```
