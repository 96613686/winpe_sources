# Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)

- ea: `0x1800171d0`
- end: `0x1800171f6`
- name: `?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001209c`
- `0x180012350`
- `0x180013f20`
- `0x1800155ec`
- `0x180016f20`
- `0x18001be24`
- `0x18001d7c4`
- `0x18001e664`

## callees

- `0x1800171d0`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(__int64 *a1)
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
0x1800171d0  sub     rsp, 28h
0x1800171d4  mov     rdx, rcx
0x1800171d7  xor     eax, eax
0x1800171d9  mov     rcx, [rcx]
0x1800171dc  test    rcx, rcx
0x1800171df  jz      short loc_1800171F1
0x1800171e1  mov     [rdx], rax
0x1800171e4  mov     rax, [rcx]
0x1800171e7  mov     rax, [rax+10h]
0x1800171eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171f0  nop
0x1800171f1  add     rsp, 28h
0x1800171f5  retn
```
