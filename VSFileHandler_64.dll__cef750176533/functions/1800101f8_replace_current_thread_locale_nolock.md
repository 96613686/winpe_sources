# replace_current_thread_locale_nolock

- ea: `0x1800101f8`
- end: `0x18001025f`
- name: `replace_current_thread_locale_nolock`
- size: `103`
- prototype: `wchar_t **__fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ff1c`
- `0x18000ff5c`

## callees

- `0x1800101f8`
- `0x1800148ac`
- `0x180014938`
- `0x180014b38`

## pseudocode

```c
wchar_t **__fastcall replace_current_thread_locale_nolock(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  wchar_t **result; // rax
  __int64 v6; // rcx

  v4 = *(_QWORD *)(a1 + 144);
  if ( v4 )
  {
    result = (wchar_t **)_acrt_release_locale_ref(v4);
    v6 = *(_QWORD *)(a1 + 144);
    if ( v6 != _acrt_current_locale_data )
    {
      result = &_acrt_initial_locale_data;
      if ( (wchar_t **)v6 != &_acrt_initial_locale_data && !*(_DWORD *)(v6 + 16) )
        result = (wchar_t **)_acrt_free_locale(v6);
    }
  }
  *(_QWORD *)(a1 + 144) = a2;
  if ( a2 )
    return (wchar_t **)_acrt_add_locale_ref(a2);
  return result;
}

```

## disassembly

```asm
0x1800101f8  mov     [rsp+arg_0], rbx
0x1800101fd  push    rdi
0x1800101fe  sub     rsp, 20h
0x180010202  mov     rdi, rcx
0x180010205  mov     rbx, rdx
0x180010208  mov     rcx, [rcx+90h]
0x18001020f  test    rcx, rcx
0x180010212  jz      short loc_180010240
0x180010214  call    __acrt_release_locale_ref
0x180010219  mov     rcx, [rdi+90h]
0x180010220  cmp     rcx, cs:__acrt_current_locale_data
0x180010227  jz      short loc_180010240
0x180010229  lea     rax, __acrt_initial_locale_data
0x180010230  cmp     rcx, rax
0x180010233  jz      short loc_180010240
0x180010235  cmp     dword ptr [rcx+10h], 0
0x180010239  jnz     short loc_180010240
0x18001023b  call    __acrt_free_locale
0x180010240  mov     [rdi+90h], rbx
0x180010247  test    rbx, rbx
0x18001024a  jz      short loc_180010254
0x18001024c  mov     rcx, rbx
0x18001024f  call    __acrt_add_locale_ref
0x180010254  mov     rbx, [rsp+28h+arg_0]
0x180010259  add     rsp, 20h
0x18001025d  pop     rdi
0x18001025e  retn
```
