# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180003fa0`
- end: `0x180003fca`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `42`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003e84`
- `0x180006650`
- `0x180009db0`
- `0x18000aff8`
- `0x18000b304`
- `0x180010b28`
- `0x180011184`
- `0x180011afc`
- `0x1800132c0`
- `0x180013400`
- `0x180017774`
- `0x1800199f8`
- `0x180019acc`
- `0x18001bc00`
- `0x18001bc0c`
- `0x18001c214`
- `0x18001dac0`
- `0x18001df88`
- `0x18001ecb0`
- `0x18001f090`
- `0x18001f350`
- `0x1800200dc`
- `0x180020a90`
- `0x180020d50`
- `0x1800219ec`
- `0x180024090`

## callees

- `0x180003fa0`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( !v2 )
    return 0;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
}

```

## disassembly

```asm
0x180003fa0  sub     rsp, 28h
0x180003fa4  mov     rax, rcx
0x180003fa7  xor     edx, edx
0x180003fa9  mov     rcx, [rcx]
0x180003fac  test    rcx, rcx
0x180003faf  jz      short loc_180003FC6
0x180003fb1  mov     [rax], rdx
0x180003fb4  mov     rax, [rcx]
0x180003fb7  mov     rax, [rax+10h]
0x180003fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fc0  nop
0x180003fc1  add     rsp, 28h
0x180003fc5  retn
0x180003fc6  mov     eax, edx
0x180003fc8  jmp     short loc_180003FC1
```
