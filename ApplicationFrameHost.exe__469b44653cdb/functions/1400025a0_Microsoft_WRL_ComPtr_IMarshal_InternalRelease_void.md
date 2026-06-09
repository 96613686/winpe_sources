# Microsoft::WRL::ComPtr<IMarshal>::InternalRelease(void)

- ea: `0x1400025a0`
- end: `0x1400025cd`
- name: `?InternalRelease@?$ComPtr@UIMarshal@@@WRL@Microsoft@@IEAAKXZ`
- size: `45`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001d80`
- `0x140009fd0`

## callees

- `0x1400025a0`
- `0x14000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IMarshal>::InternalRelease(__int64 *a1)
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
0x1400025a0  sub     rsp, 28h
0x1400025a4  mov     rax, rcx
0x1400025a7  xor     edx, edx
0x1400025a9  mov     rcx, [rcx]
0x1400025ac  test    rcx, rcx
0x1400025af  jz      short loc_1400025C6
0x1400025b1  mov     [rax], rdx
0x1400025b4  mov     rax, [rcx]
0x1400025b7  mov     rax, [rax+10h]
0x1400025bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025c0  nop
0x1400025c1  add     rsp, 28h
0x1400025c5  retn
0x1400025c6  mov     eax, edx
0x1400025c8  add     rsp, 28h
0x1400025cc  retn
```
