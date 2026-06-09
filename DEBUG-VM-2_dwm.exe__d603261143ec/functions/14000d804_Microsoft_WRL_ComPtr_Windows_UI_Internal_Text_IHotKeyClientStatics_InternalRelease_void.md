# Microsoft::WRL::ComPtr<Windows::UI::Internal::Text::IHotKeyClientStatics>::InternalRelease(void)

- ea: `0x14000d804`
- end: `0x14000d829`
- name: `?InternalRelease@?$ComPtr@UIHotKeyClientStatics@Text@Internal@UI@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d87c`

## callees

- `0x14000d804`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::UI::Internal::Text::IHotKeyClientStatics>::InternalRelease(
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
0x14000d804  sub     rsp, 28h
0x14000d808  mov     rdx, rcx
0x14000d80b  xor     eax, eax
0x14000d80d  mov     rcx, [rcx]
0x14000d810  test    rcx, rcx
0x14000d813  jz      short loc_14000D824
0x14000d815  mov     [rdx], rax
0x14000d818  mov     rax, [rcx]
0x14000d81b  mov     rax, [rax+10h]
0x14000d81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d824  add     rsp, 28h
0x14000d828  retn
```
