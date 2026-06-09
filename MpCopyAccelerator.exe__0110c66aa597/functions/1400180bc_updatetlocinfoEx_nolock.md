# _updatetlocinfoEx_nolock

- ea: `0x1400180bc`
- end: `0x140018121`
- name: `_updatetlocinfoEx_nolock`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140012e08`
- `0x14001804c`

## callees

- `0x140017d18`
- `0x140017da4`
- `0x140017fa4`
- `0x1400180bc`

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
0x1400180bc  mov     [rsp+arg_0], rbx
0x1400180c1  push    rdi
0x1400180c2  sub     rsp, 20h
0x1400180c6  mov     rdi, rdx
0x1400180c9  test    rdx, rdx
0x1400180cc  jz      short loc_140018114
0x1400180ce  test    rcx, rcx
0x1400180d1  jz      short loc_140018114
0x1400180d3  mov     rbx, [rcx]
0x1400180d6  cmp     rbx, rdx
0x1400180d9  jnz     short loc_1400180E0
0x1400180db  mov     rax, rdi
0x1400180de  jmp     short loc_140018116
0x1400180e0  mov     [rcx], rdi
0x1400180e3  mov     rcx, rdi
0x1400180e6  call    __acrt_add_locale_ref
0x1400180eb  test    rbx, rbx
0x1400180ee  jz      short loc_1400180DB
0x1400180f0  mov     rcx, rbx
0x1400180f3  call    __acrt_release_locale_ref
0x1400180f8  cmp     dword ptr [rbx+10h], 0
0x1400180fc  jnz     short loc_1400180DB
0x1400180fe  lea     rax, __acrt_initial_locale_data
0x140018105  cmp     rbx, rax
0x140018108  jz      short loc_1400180DB
0x14001810a  mov     rcx, rbx
0x14001810d  call    __acrt_free_locale
0x140018112  jmp     short loc_1400180DB
0x140018114  xor     eax, eax
0x140018116  mov     rbx, [rsp+28h+arg_0]
0x14001811b  add     rsp, 20h
0x14001811f  pop     rdi
0x140018120  retn
```
