# Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)

- ea: `0x1400052b4`
- end: `0x1400052da`
- name: `?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003198`
- `0x140003ae0`

## callees

- `0x1400052b4`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(__int64 *a1)
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
0x1400052b4  sub     rsp, 28h
0x1400052b8  mov     rdx, rcx
0x1400052bb  xor     eax, eax
0x1400052bd  mov     rcx, [rcx]
0x1400052c0  test    rcx, rcx
0x1400052c3  jz      short loc_1400052D5
0x1400052c5  mov     [rdx], rax
0x1400052c8  mov     rax, [rcx]
0x1400052cb  mov     rax, [rax+10h]
0x1400052cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052d4  nop
0x1400052d5  add     rsp, 28h
0x1400052d9  retn
```
