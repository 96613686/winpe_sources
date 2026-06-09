# Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)

- ea: `0x180017348`
- end: `0x18001736f`
- name: `?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `39`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014e1c`
- `0x180015034`
- `0x180015c2c`
- `0x1800169b8`
- `0x18001d800`
- `0x18001da10`

## callees

- `0x180017348`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(
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
0x180017348  sub     rsp, 28h
0x18001734c  mov     rdx, rcx
0x18001734f  xor     eax, eax
0x180017351  mov     rcx, [rcx]
0x180017354  test    rcx, rcx
0x180017357  jz      short loc_180017369
0x180017359  mov     [rdx], rax
0x18001735c  mov     rax, [rcx]
0x18001735f  mov     rax, [rax+10h]
0x180017363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017368  nop
0x180017369  add     rsp, 28h
0x18001736d  retn
```
