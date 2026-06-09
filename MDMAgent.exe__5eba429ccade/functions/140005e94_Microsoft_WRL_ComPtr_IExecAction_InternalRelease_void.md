# Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)

- ea: `0x140005e94`
- end: `0x140005eba`
- name: `?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000384c`
- `0x14000481c`
- `0x140007f34`
- `0x140012704`
- `0x140012754`
- `0x1400127a4`
- `0x140012bd0`
- `0x14001464c`

## callees

- `0x140005e94`
- `0x140019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(__int64 *a1)
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
0x140005e94  sub     rsp, 28h
0x140005e98  mov     rdx, rcx
0x140005e9b  xor     eax, eax
0x140005e9d  mov     rcx, [rcx]
0x140005ea0  test    rcx, rcx
0x140005ea3  jz      short loc_140005EB5
0x140005ea5  mov     [rdx], rax
0x140005ea8  mov     rax, [rcx]
0x140005eab  mov     rax, [rax+10h]
0x140005eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005eb4  nop
0x140005eb5  add     rsp, 28h
0x140005eb9  retn
```
