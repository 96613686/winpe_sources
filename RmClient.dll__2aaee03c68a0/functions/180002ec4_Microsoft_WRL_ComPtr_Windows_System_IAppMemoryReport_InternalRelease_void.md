# Microsoft::WRL::ComPtr<Windows::System::IAppMemoryReport>::InternalRelease(void)

- ea: `0x180002ec4`
- end: `0x180002ee1`
- name: `?InternalRelease@?$ComPtr@UIAppMemoryReport@System@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `29`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002320`

## callees

- `0x180002ec4`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::System::IAppMemoryReport>::InternalRelease(__int64 *a1)
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
0x180002ec4  mov     rdx, rcx
0x180002ec7  xor     eax, eax
0x180002ec9  mov     rcx, [rcx]
0x180002ecc  test    rcx, rcx
0x180002ecf  jnz     short loc_180002ED2
0x180002ed1  retn
0x180002ed2  mov     [rdx], rax
0x180002ed5  mov     rax, [rcx]
0x180002ed8  mov     rax, [rax+10h]
0x180002edc  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
