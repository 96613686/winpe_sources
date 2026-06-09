# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x140004340`
- end: `0x140004366`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000722c`
- `0x1400072ec`
- `0x140007354`
- `0x140007544`
- `0x14000759c`
- `0x140007a30`
- `0x140007ad0`
- `0x140008a10`
- `0x140008ed0`
- `0x140008fdc`

## callees

- `0x140004340`
- `0x14000a010`

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
0x140004340  sub     rsp, 28h
0x140004344  mov     rdx, rcx
0x140004347  xor     eax, eax
0x140004349  mov     rcx, [rcx]
0x14000434c  test    rcx, rcx
0x14000434f  jz      short loc_140004361
0x140004351  mov     [rdx], rax
0x140004354  mov     rax, [rcx]
0x140004357  mov     rax, [rax+10h]
0x14000435b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004360  nop
0x140004361  add     rsp, 28h
0x140004365  retn
```
