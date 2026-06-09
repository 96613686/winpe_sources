# Microsoft::WRL::ComPtr<IOpenControlPanel>::InternalRelease(void)

- ea: `0x18000a1ec`
- end: `0x18000a212`
- name: `?InternalRelease@?$ComPtr@UIOpenControlPanel@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008a74`
- `0x18000d7d0`

## callees

- `0x18000a1ec`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IOpenControlPanel>::InternalRelease(__int64 *a1)
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
0x18000a1ec  sub     rsp, 28h
0x18000a1f0  mov     rdx, rcx
0x18000a1f3  xor     eax, eax
0x18000a1f5  mov     rcx, [rcx]
0x18000a1f8  test    rcx, rcx
0x18000a1fb  jz      short loc_18000A20D
0x18000a1fd  mov     [rdx], rax
0x18000a200  mov     rax, [rcx]
0x18000a203  mov     rax, [rax+10h]
0x18000a207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a20c  nop
0x18000a20d  add     rsp, 28h
0x18000a211  retn
```
