# Microsoft::WRL::ComPtr<IDesktopAppXActivator>::InternalRelease(void)

- ea: `0x1800096e0`
- end: `0x180009706`
- name: `?InternalRelease@?$ComPtr@UIDesktopAppXActivator@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800086a8`
- `0x180008d9c`
- `0x18000e84c`

## callees

- `0x1800096e0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IDesktopAppXActivator>::InternalRelease(__int64 *a1)
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
0x1800096e0  sub     rsp, 28h
0x1800096e4  mov     rdx, rcx
0x1800096e7  xor     eax, eax
0x1800096e9  mov     rcx, [rcx]
0x1800096ec  test    rcx, rcx
0x1800096ef  jz      short loc_180009701
0x1800096f1  mov     [rdx], rax
0x1800096f4  mov     rax, [rcx]
0x1800096f7  mov     rax, [rax+10h]
0x1800096fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009700  nop
0x180009701  add     rsp, 28h
0x180009705  retn
```
