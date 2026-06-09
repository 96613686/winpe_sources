# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180006158`
- end: `0x18000617e`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000837c`
- `0x180008530`
- `0x1800086b0`
- `0x180008740`
- `0x18001b004`

## callees

- `0x180006158`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
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
0x180006158  sub     rsp, 28h
0x18000615c  mov     rdx, rcx
0x18000615f  xor     eax, eax
0x180006161  mov     rcx, [rcx]
0x180006164  test    rcx, rcx
0x180006167  jz      short loc_180006179
0x180006169  mov     [rdx], rax
0x18000616c  mov     rax, [rcx]
0x18000616f  mov     rax, [rax+10h]
0x180006173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006178  nop
0x180006179  add     rsp, 28h
0x18000617d  retn
```
