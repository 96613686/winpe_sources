# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x1400068e8`
- end: `0x14000690d`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `37`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006580`
- `0x140006844`
- `0x1400068a0`
- `0x14000aa7c`
- `0x14000ad80`
- `0x14000add0`

## callees

- `0x1400068e8`
- `0x140010010`

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
0x1400068e8  sub     rsp, 28h
0x1400068ec  mov     rdx, rcx
0x1400068ef  xor     eax, eax
0x1400068f1  mov     rcx, [rcx]
0x1400068f4  test    rcx, rcx
0x1400068f7  jz      short loc_140006908
0x1400068f9  mov     [rdx], rax
0x1400068fc  mov     rax, [rcx]
0x1400068ff  mov     rax, [rax+10h]
0x140006903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006908  add     rsp, 28h
0x14000690c  retn
```
