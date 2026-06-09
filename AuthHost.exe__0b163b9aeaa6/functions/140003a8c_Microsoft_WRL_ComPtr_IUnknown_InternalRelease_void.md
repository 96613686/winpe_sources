# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x140003a8c`
- end: `0x140003ab2`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003a80`
- `0x1400047f4`
- `0x140004ac0`
- `0x140005f18`
- `0x140006418`
- `0x140006c44`
- `0x140007080`
- `0x140007700`
- `0x140007750`
- `0x140007a60`
- `0x140007cd4`
- `0x140008244`
- `0x1400082a8`
- `0x140008890`
- `0x14000893c`
- `0x140008998`
- `0x140008b30`
- `0x14000b308`
- `0x14000be88`
- `0x14000c0c0`
- `0x1400104f0`
- `0x140011aa4`

## callees

- `0x140003a8c`
- `0x140014010`

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
0x140003a8c  sub     rsp, 28h
0x140003a90  mov     rdx, rcx
0x140003a93  xor     eax, eax
0x140003a95  mov     rcx, [rcx]
0x140003a98  test    rcx, rcx
0x140003a9b  jz      short loc_140003AAD
0x140003a9d  mov     [rdx], rax
0x140003aa0  mov     rax, [rcx]
0x140003aa3  mov     rax, [rax+10h]
0x140003aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003aac  nop
0x140003aad  add     rsp, 28h
0x140003ab1  retn
```
