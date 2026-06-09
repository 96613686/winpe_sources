# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x1800018c4`
- end: `0x1800018e9`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `37`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000145c`
- `0x18000166c`
- `0x180001780`
- `0x18000ad38`
- `0x18000ae70`
- `0x18000f3e0`
- `0x180014c00`
- `0x180017c34`
- `0x180017d78`
- `0x180017f8c`
- `0x180018000`
- `0x18001827c`
- `0x1800187b0`
- `0x180018840`

## callees

- `0x1800018c4`
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
0x1800018c4  sub     rsp, 28h
0x1800018c8  mov     rdx, rcx
0x1800018cb  xor     eax, eax
0x1800018cd  mov     rcx, [rcx]
0x1800018d0  test    rcx, rcx
0x1800018d3  jz      short loc_1800018E4
0x1800018d5  mov     [rdx], rax
0x1800018d8  mov     rax, [rcx]
0x1800018db  mov     rax, [rax+10h]
0x1800018df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018e4  add     rsp, 28h
0x1800018e8  retn
```
