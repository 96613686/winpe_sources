# Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)

- ea: `0x18001b270`
- end: `0x18001b295`
- name: `?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b060`
- `0x18001b168`

## callees

- `0x18001b270`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(__int64 *a1)
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
0x18001b270  sub     rsp, 28h
0x18001b274  mov     rdx, rcx
0x18001b277  xor     eax, eax
0x18001b279  mov     rcx, [rcx]
0x18001b27c  test    rcx, rcx
0x18001b27f  jz      short loc_18001B290
0x18001b281  mov     [rdx], rax
0x18001b284  mov     rax, [rcx]
0x18001b287  mov     rax, [rax+10h]
0x18001b28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b290  add     rsp, 28h
0x18001b294  retn
```
