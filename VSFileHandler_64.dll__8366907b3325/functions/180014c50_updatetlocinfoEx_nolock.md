# _updatetlocinfoEx_nolock

- ea: `0x180014c50`
- end: `0x180014cb5`
- name: `_updatetlocinfoEx_nolock`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180011c7c`
- `0x180014be0`

## callees

- `0x1800148ac`
- `0x180014938`
- `0x180014b38`
- `0x180014c50`

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
0x180014c50  mov     [rsp+arg_0], rbx
0x180014c55  push    rdi
0x180014c56  sub     rsp, 20h
0x180014c5a  mov     rdi, rdx
0x180014c5d  test    rdx, rdx
0x180014c60  jz      short loc_180014CA8
0x180014c62  test    rcx, rcx
0x180014c65  jz      short loc_180014CA8
0x180014c67  mov     rbx, [rcx]
0x180014c6a  cmp     rbx, rdx
0x180014c6d  jnz     short loc_180014C74
0x180014c6f  mov     rax, rdi
0x180014c72  jmp     short loc_180014CAA
0x180014c74  mov     [rcx], rdi
0x180014c77  mov     rcx, rdi
0x180014c7a  call    __acrt_add_locale_ref
0x180014c7f  test    rbx, rbx
0x180014c82  jz      short loc_180014C6F
0x180014c84  mov     rcx, rbx
0x180014c87  call    __acrt_release_locale_ref
0x180014c8c  cmp     dword ptr [rbx+10h], 0
0x180014c90  jnz     short loc_180014C6F
0x180014c92  lea     rax, __acrt_initial_locale_data
0x180014c99  cmp     rbx, rax
0x180014c9c  jz      short loc_180014C6F
0x180014c9e  mov     rcx, rbx
0x180014ca1  call    __acrt_free_locale
0x180014ca6  jmp     short loc_180014C6F
0x180014ca8  xor     eax, eax
0x180014caa  mov     rbx, [rsp+28h+arg_0]
0x180014caf  add     rsp, 20h
0x180014cb3  pop     rdi
0x180014cb4  retn
```
