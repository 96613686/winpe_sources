# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x18000539c`
- end: `0x1800053c2`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003c7c`
- `0x180003f30`
- `0x180004060`
- `0x180006e90`
- `0x180009920`
- `0x180009970`

## callees

- `0x18000539c`
- `0x18000b010`

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
0x18000539c  sub     rsp, 28h
0x1800053a0  mov     rdx, rcx
0x1800053a3  xor     eax, eax
0x1800053a5  mov     rcx, [rcx]
0x1800053a8  test    rcx, rcx
0x1800053ab  jz      short loc_1800053BD
0x1800053ad  mov     [rdx], rax
0x1800053b0  mov     rax, [rcx]
0x1800053b3  mov     rax, [rax+10h]
0x1800053b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053bc  nop
0x1800053bd  add     rsp, 28h
0x1800053c1  retn
```
