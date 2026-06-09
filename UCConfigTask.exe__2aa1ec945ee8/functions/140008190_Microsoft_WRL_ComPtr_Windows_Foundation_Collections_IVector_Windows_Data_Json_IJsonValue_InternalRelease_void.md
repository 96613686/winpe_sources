# Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)

- ea: `0x140008190`
- end: `0x1400081b6`
- name: `?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007e24`
- `0x140007ef4`
- `0x1400081bc`

## callees

- `0x140008190`
- `0x140009010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(
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
0x140008190  sub     rsp, 28h
0x140008194  mov     rdx, rcx
0x140008197  xor     eax, eax
0x140008199  mov     rcx, [rcx]
0x14000819c  test    rcx, rcx
0x14000819f  jz      short loc_1400081B1
0x1400081a1  mov     [rdx], rax
0x1400081a4  mov     rax, [rcx]
0x1400081a7  mov     rax, [rax+10h]
0x1400081ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400081b0  nop
0x1400081b1  add     rsp, 28h
0x1400081b5  retn
```
