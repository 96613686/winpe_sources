# _updatetlocinfoEx_nolock

- ea: `0x14000934c`
- end: `0x1400093b1`
- name: `_updatetlocinfoEx_nolock`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140005248`
- `0x1400092dc`

## callees

- `0x140008fa8`
- `0x140009034`
- `0x140009234`
- `0x14000934c`

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
      if ( !*((_DWORD *)v3 + 4) && v3 != &off_140019630 )
        _acrt_free_locale(v3);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x14000934c  mov     [rsp+arg_0], rbx
0x140009351  push    rdi
0x140009352  sub     rsp, 20h
0x140009356  mov     rdi, rdx
0x140009359  test    rdx, rdx
0x14000935c  jz      short loc_1400093A4
0x14000935e  test    rcx, rcx
0x140009361  jz      short loc_1400093A4
0x140009363  mov     rbx, [rcx]
0x140009366  cmp     rbx, rdx
0x140009369  jnz     short loc_140009370
0x14000936b  mov     rax, rdi
0x14000936e  jmp     short loc_1400093A6
0x140009370  mov     [rcx], rdi
0x140009373  mov     rcx, rdi
0x140009376  call    __acrt_add_locale_ref
0x14000937b  test    rbx, rbx
0x14000937e  jz      short loc_14000936B
0x140009380  mov     rcx, rbx
0x140009383  call    __acrt_release_locale_ref
0x140009388  cmp     dword ptr [rbx+10h], 0
0x14000938c  jnz     short loc_14000936B
0x14000938e  lea     rax, off_140019630
0x140009395  cmp     rbx, rax
0x140009398  jz      short loc_14000936B
0x14000939a  mov     rcx, rbx; Block
0x14000939d  call    __acrt_free_locale
0x1400093a2  jmp     short loc_14000936B
0x1400093a4  xor     eax, eax
0x1400093a6  mov     rbx, [rsp+28h+arg_0]
0x1400093ab  add     rsp, 20h
0x1400093af  pop     rdi
0x1400093b0  retn
```
