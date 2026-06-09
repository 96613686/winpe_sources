# Microsoft::WRL::ComPtr<IPCLmWriter>::InternalRelease(void)

- ea: `0x18000df30`
- end: `0x18000df56`
- name: `?InternalRelease@?$ComPtr@UIPCLmWriter@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d9f0`
- `0x18000da18`
- `0x18000da7c`
- `0x18000dca0`
- `0x18000f728`
- `0x18000fd5c`
- `0x180017350`

## callees

- `0x18000df30`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IPCLmWriter>::InternalRelease(__int64 *a1)
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
0x18000df30  sub     rsp, 28h
0x18000df34  mov     rdx, rcx
0x18000df37  xor     eax, eax
0x18000df39  mov     rcx, [rcx]
0x18000df3c  test    rcx, rcx
0x18000df3f  jz      short loc_18000DF51
0x18000df41  mov     [rdx], rax
0x18000df44  mov     rax, [rcx]
0x18000df47  mov     rax, [rax+10h]
0x18000df4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df50  nop
0x18000df51  add     rsp, 28h
0x18000df55  retn
```
