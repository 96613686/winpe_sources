# _updatetlocinfoEx_nolock

- ea: `0x140078b9c`
- end: `0x140078c01`
- name: `_updatetlocinfoEx_nolock`
- size: `101`
- prototype: `wchar_t **__fastcall(wchar_t ***, wchar_t **)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14006d08c`
- `0x14006d1c8`
- `0x140078b2c`

## callees

- `0x1400787f8`
- `0x140078884`
- `0x140078a84`
- `0x140078b9c`

## pseudocode

```c
wchar_t **__fastcall updatetlocinfoEx_nolock(wchar_t ***a1, wchar_t **a2)
{
  wchar_t **v3; // rbx

  if ( !a2 || !a1 )
    return 0;
  v3 = *a1;
  if ( *a1 != a2 )
  {
    *a1 = a2;
    _acrt_add_locale_ref(a2);
    if ( v3 )
    {
      _acrt_release_locale_ref(v3);
      if ( !*((_DWORD *)v3 + 4) && v3 != &off_1400BE060 )
        _acrt_free_locale(v3);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140078b9c  mov     [rsp+arg_0], rbx
0x140078ba1  push    rdi
0x140078ba2  sub     rsp, 20h
0x140078ba6  mov     rdi, rdx
0x140078ba9  test    rdx, rdx
0x140078bac  jz      short loc_140078BF4
0x140078bae  test    rcx, rcx
0x140078bb1  jz      short loc_140078BF4
0x140078bb3  mov     rbx, [rcx]
0x140078bb6  cmp     rbx, rdx
0x140078bb9  jnz     short loc_140078BC0
0x140078bbb  mov     rax, rdi
0x140078bbe  jmp     short loc_140078BF6
0x140078bc0  mov     [rcx], rdi
0x140078bc3  mov     rcx, rdi
0x140078bc6  call    __acrt_add_locale_ref
0x140078bcb  test    rbx, rbx
0x140078bce  jz      short loc_140078BBB
0x140078bd0  mov     rcx, rbx
0x140078bd3  call    __acrt_release_locale_ref
0x140078bd8  cmp     dword ptr [rbx+10h], 0
0x140078bdc  jnz     short loc_140078BBB
0x140078bde  lea     rax, off_1400BE060
0x140078be5  cmp     rbx, rax
0x140078be8  jz      short loc_140078BBB
0x140078bea  mov     rcx, rbx; Block
0x140078bed  call    __acrt_free_locale
0x140078bf2  jmp     short loc_140078BBB
0x140078bf4  xor     eax, eax
0x140078bf6  mov     rbx, [rsp+28h+arg_0]
0x140078bfb  add     rsp, 20h
0x140078bff  pop     rdi
0x140078c00  retn
```
