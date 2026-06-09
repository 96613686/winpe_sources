# _updatetlocinfoEx_nolock

- ea: `0x1400132e8`
- end: `0x14001334d`
- name: `_updatetlocinfoEx_nolock`
- size: `101`
- prototype: `wchar_t **__fastcall(wchar_t ***, wchar_t **)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14001037c`
- `0x140013278`

## callees

- `0x140012f44`
- `0x140012fd0`
- `0x1400131d0`
- `0x1400132e8`

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
      if ( !*((_DWORD *)v3 + 4) && v3 != &off_1400D5000 )
        _acrt_free_locale(v3);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1400132e8  mov     [rsp+arg_0], rbx
0x1400132ed  push    rdi
0x1400132ee  sub     rsp, 20h
0x1400132f2  mov     rdi, rdx
0x1400132f5  test    rdx, rdx
0x1400132f8  jz      short loc_140013340
0x1400132fa  test    rcx, rcx
0x1400132fd  jz      short loc_140013340
0x1400132ff  mov     rbx, [rcx]
0x140013302  cmp     rbx, rdx
0x140013305  jnz     short loc_14001330C
0x140013307  mov     rax, rdi
0x14001330a  jmp     short loc_140013342
0x14001330c  mov     [rcx], rdi
0x14001330f  mov     rcx, rdi
0x140013312  call    __acrt_add_locale_ref
0x140013317  test    rbx, rbx
0x14001331a  jz      short loc_140013307
0x14001331c  mov     rcx, rbx
0x14001331f  call    __acrt_release_locale_ref
0x140013324  cmp     dword ptr [rbx+10h], 0
0x140013328  jnz     short loc_140013307
0x14001332a  lea     rax, off_1400D5000
0x140013331  cmp     rbx, rax
0x140013334  jz      short loc_140013307
0x140013336  mov     rcx, rbx; Block
0x140013339  call    __acrt_free_locale
0x14001333e  jmp     short loc_140013307
0x140013340  xor     eax, eax
0x140013342  mov     rbx, [rsp+28h+arg_0]
0x140013347  add     rsp, 20h
0x14001334b  pop     rdi
0x14001334c  retn
```
