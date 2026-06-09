# Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)

- ea: `0x140005588`
- end: `0x1400055af`
- name: `?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003244`
- `0x140003c44`

## callees

- `0x140005588`
- `0x14000b010`

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
0x140005588  sub     rsp, 28h
0x14000558c  mov     rdx, rcx
0x14000558f  xor     eax, eax
0x140005591  mov     rcx, [rcx]
0x140005594  test    rcx, rcx
0x140005597  jz      short loc_1400055A9
0x140005599  mov     [rdx], rax
0x14000559c  mov     rax, [rcx]
0x14000559f  mov     rax, [rax+10h]
0x1400055a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055a8  nop
0x1400055a9  add     rsp, 28h
0x1400055ad  retn
```
