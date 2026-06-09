# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180006324`
- end: `0x18000634a`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f038`
- `0x18000f2cc`
- `0x180010360`
- `0x180010b28`
- `0x180010e70`

## callees

- `0x180006324`
- `0x18001c010`

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
0x180006324  sub     rsp, 28h
0x180006328  mov     rdx, rcx
0x18000632b  xor     eax, eax
0x18000632d  mov     rcx, [rcx]
0x180006330  test    rcx, rcx
0x180006333  jz      short loc_180006345
0x180006335  mov     [rdx], rax
0x180006338  mov     rax, [rcx]
0x18000633b  mov     rax, [rax+10h]
0x18000633f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006344  nop
0x180006345  add     rsp, 28h
0x180006349  retn
```
