# Microsoft::WRL::ComPtr<TimeUpdate>::InternalRelease(void)

- ea: `0x180007a30`
- end: `0x180007a56`
- name: `?InternalRelease@?$ComPtr@VTimeUpdate@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800053c4`
- `0x180008d7c`
- `0x18000a108`
- `0x180011790`

## callees

- `0x180007a30`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<TimeUpdate>::InternalRelease(__int64 *a1)
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
0x180007a30  sub     rsp, 28h
0x180007a34  mov     rdx, rcx
0x180007a37  xor     eax, eax
0x180007a39  mov     rcx, [rcx]
0x180007a3c  test    rcx, rcx
0x180007a3f  jz      short loc_180007A51
0x180007a41  mov     [rdx], rax
0x180007a44  mov     rax, [rcx]
0x180007a47  mov     rax, [rax+10h]
0x180007a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a50  nop
0x180007a51  add     rsp, 28h
0x180007a55  retn
```
