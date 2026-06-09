# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x18001fa00`
- end: `0x18001fa26`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f818`
- `0x18001fa2c`
- `0x18001ff04`
- `0x18001ffec`
- `0x1800386a4`
- `0x180041c08`
- `0x180041d48`
- `0x18004249c`
- `0x180042638`
- `0x180042de4`
- `0x180042e28`
- `0x180042ff0`

## callees

- `0x18001fa00`
- `0x18004d010`

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
0x18001fa00  sub     rsp, 28h
0x18001fa04  mov     rdx, rcx
0x18001fa07  xor     eax, eax
0x18001fa09  mov     rcx, [rcx]
0x18001fa0c  test    rcx, rcx
0x18001fa0f  jz      short loc_18001FA21
0x18001fa11  mov     [rdx], rax
0x18001fa14  mov     rax, [rcx]
0x18001fa17  mov     rax, [rax+10h]
0x18001fa1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa20  nop
0x18001fa21  add     rsp, 28h
0x18001fa25  retn
```
