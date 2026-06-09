# _updatetlocinfoEx_nolock

- ea: `0x14001eeac`
- end: `0x14001ef11`
- name: `_updatetlocinfoEx_nolock`
- size: `101`
- prototype: `wchar_t **__fastcall(wchar_t ***, wchar_t **)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140018918`
- `0x14001ee3c`

## callees

- `0x14001eb08`
- `0x14001eb94`
- `0x14001ed94`
- `0x14001eeac`

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
      if ( !*((_DWORD *)v3 + 4) && v3 != &off_14003C7A0 )
        _acrt_free_locale(v3);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x14001eeac  mov     [rsp+arg_0], rbx
0x14001eeb1  push    rdi
0x14001eeb2  sub     rsp, 20h
0x14001eeb6  mov     rdi, rdx
0x14001eeb9  test    rdx, rdx
0x14001eebc  jz      short loc_14001EF04
0x14001eebe  test    rcx, rcx
0x14001eec1  jz      short loc_14001EF04
0x14001eec3  mov     rbx, [rcx]
0x14001eec6  cmp     rbx, rdx
0x14001eec9  jnz     short loc_14001EED0
0x14001eecb  mov     rax, rdi
0x14001eece  jmp     short loc_14001EF06
0x14001eed0  mov     [rcx], rdi
0x14001eed3  mov     rcx, rdi
0x14001eed6  call    __acrt_add_locale_ref
0x14001eedb  test    rbx, rbx
0x14001eede  jz      short loc_14001EECB
0x14001eee0  mov     rcx, rbx
0x14001eee3  call    __acrt_release_locale_ref
0x14001eee8  cmp     dword ptr [rbx+10h], 0
0x14001eeec  jnz     short loc_14001EECB
0x14001eeee  lea     rax, off_14003C7A0
0x14001eef5  cmp     rbx, rax
0x14001eef8  jz      short loc_14001EECB
0x14001eefa  mov     rcx, rbx; Block
0x14001eefd  call    __acrt_free_locale
0x14001ef02  jmp     short loc_14001EECB
0x14001ef04  xor     eax, eax
0x14001ef06  mov     rbx, [rsp+28h+arg_0]
0x14001ef0b  add     rsp, 20h
0x14001ef0f  pop     rdi
0x14001ef10  retn
```
