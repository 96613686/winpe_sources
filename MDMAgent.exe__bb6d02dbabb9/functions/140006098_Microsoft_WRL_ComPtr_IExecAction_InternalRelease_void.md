# Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)

- ea: `0x140006098`
- end: `0x1400060bf`
- name: `?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ`
- size: `39`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400038ec`
- `0x1400048f4`
- `0x14000829c`
- `0x14001301c`
- `0x14001306c`
- `0x1400130bc`
- `0x14001351c`
- `0x1400151d8`

## callees

- `0x140006098`
- `0x14001a010`

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
0x140006098  sub     rsp, 28h
0x14000609c  mov     rdx, rcx
0x14000609f  xor     eax, eax
0x1400060a1  mov     rcx, [rcx]
0x1400060a4  test    rcx, rcx
0x1400060a7  jz      short loc_1400060B9
0x1400060a9  mov     [rdx], rax
0x1400060ac  mov     rax, [rcx]
0x1400060af  mov     rax, [rax+10h]
0x1400060b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060b8  nop
0x1400060b9  add     rsp, 28h
0x1400060bd  retn
```
