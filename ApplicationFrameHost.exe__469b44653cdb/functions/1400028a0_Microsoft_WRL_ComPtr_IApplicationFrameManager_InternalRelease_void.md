# Microsoft::WRL::ComPtr<IApplicationFrameManager>::InternalRelease(void)

- ea: `0x1400028a0`
- end: `0x1400028c6`
- name: `?InternalRelease@?$ComPtr@UIApplicationFrameManager@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140009fd0`

## callees

- `0x1400028a0`
- `0x14000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IApplicationFrameManager>::InternalRelease(__int64 *a1)
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
0x1400028a0  sub     rsp, 28h
0x1400028a4  mov     rdx, rcx
0x1400028a7  xor     eax, eax
0x1400028a9  mov     rcx, [rcx]
0x1400028ac  test    rcx, rcx
0x1400028af  jz      short loc_1400028C1
0x1400028b1  mov     [rdx], rax
0x1400028b4  mov     rax, [rcx]
0x1400028b7  mov     rax, [rax+10h]
0x1400028bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028c0  nop
0x1400028c1  add     rsp, 28h
0x1400028c5  retn
```
