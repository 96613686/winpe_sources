# _updatetlocinfoEx_nolock

- ea: `0x18000fb8c`
- end: `0x18000fbf1`
- name: `_updatetlocinfoEx_nolock`
- size: `101`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000fb1c`
- `0x18000fc54`
- `0x18000fd90`
- `0x18000ff20`
- `0x1800101c4`
- `0x1800101f4`
- `0x180010264`

## callees

- `0x18000f7e8`
- `0x18000f874`
- `0x18000fa74`
- `0x18000fb8c`

## pseudocode

```c
__int64 __fastcall updatetlocinfoEx_nolock(__int64 *a1, __int64 a2)
{
  __int64 v3; // rbx

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
      if ( !*(_DWORD *)(v3 + 16) && (wchar_t **)v3 != &_acrt_initial_locale_data )
        _acrt_free_locale(v3);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18000fb8c  mov     [rsp+arg_0], rbx
0x18000fb91  push    rdi
0x18000fb92  sub     rsp, 20h
0x18000fb96  mov     rdi, rdx
0x18000fb99  test    rdx, rdx
0x18000fb9c  jz      short loc_18000FBE4
0x18000fb9e  test    rcx, rcx
0x18000fba1  jz      short loc_18000FBE4
0x18000fba3  mov     rbx, [rcx]
0x18000fba6  cmp     rbx, rdx
0x18000fba9  jnz     short loc_18000FBB0
0x18000fbab  mov     rax, rdi
0x18000fbae  jmp     short loc_18000FBE6
0x18000fbb0  mov     [rcx], rdi
0x18000fbb3  mov     rcx, rdi
0x18000fbb6  call    __acrt_add_locale_ref
0x18000fbbb  test    rbx, rbx
0x18000fbbe  jz      short loc_18000FBAB
0x18000fbc0  mov     rcx, rbx
0x18000fbc3  call    __acrt_release_locale_ref
0x18000fbc8  cmp     dword ptr [rbx+10h], 0
0x18000fbcc  jnz     short loc_18000FBAB
0x18000fbce  lea     rax, __acrt_initial_locale_data
0x18000fbd5  cmp     rbx, rax
0x18000fbd8  jz      short loc_18000FBAB
0x18000fbda  mov     rcx, rbx
0x18000fbdd  call    __acrt_free_locale
0x18000fbe2  jmp     short loc_18000FBAB
0x18000fbe4  xor     eax, eax
0x18000fbe6  mov     rbx, [rsp+28h+arg_0]
0x18000fbeb  add     rsp, 20h
0x18000fbef  pop     rdi
0x18000fbf0  retn
```
