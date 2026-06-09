# Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)

- ea: `0x14000d49c`
- end: `0x14000d4c2`
- name: `?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `25`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008814`
- `0x140008850`
- `0x140008984`
- `0x140008f1c`
- `0x1400090ac`
- `0x140009a84`
- `0x140009e48`
- `0x14000a2ec`
- `0x14000a330`
- `0x14000a4f0`
- `0x14000a500`
- `0x14000a670`
- `0x14000a934`
- `0x14000ae54`
- `0x14000b114`
- `0x14000bc30`
- `0x14000be20`
- `0x14000bef8`
- `0x14000c3ec`
- `0x14000c848`
- `0x14000cc94`
- `0x14000eb7c`
- `0x14000ed9c`
- `0x14000f3b8`
- `0x140011851`

## callees

- `0x14000d49c`
- `0x140012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(
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
0x14000d49c  sub     rsp, 28h
0x14000d4a0  mov     rdx, rcx
0x14000d4a3  xor     eax, eax
0x14000d4a5  mov     rcx, [rcx]
0x14000d4a8  test    rcx, rcx
0x14000d4ab  jz      short loc_14000D4BD
0x14000d4ad  mov     [rdx], rax
0x14000d4b0  mov     rax, [rcx]
0x14000d4b3  mov     rax, [rax+10h]
0x14000d4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d4bc  nop
0x14000d4bd  add     rsp, 28h
0x14000d4c1  retn
```
