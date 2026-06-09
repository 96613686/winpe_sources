# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x18000601c`
- end: `0x180006042`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004d54`
- `0x1800108d4`

## callees

- `0x18000601c`
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
0x18000601c  sub     rsp, 28h
0x180006020  mov     rdx, rcx
0x180006023  xor     eax, eax
0x180006025  mov     rcx, [rcx]
0x180006028  test    rcx, rcx
0x18000602b  jz      short loc_18000603D
0x18000602d  mov     [rdx], rax
0x180006030  mov     rax, [rcx]
0x180006033  mov     rax, [rax+10h]
0x180006037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000603c  nop
0x18000603d  add     rsp, 28h
0x180006041  retn
```
