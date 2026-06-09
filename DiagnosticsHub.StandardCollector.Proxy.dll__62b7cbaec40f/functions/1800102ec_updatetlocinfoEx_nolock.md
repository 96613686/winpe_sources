# _updatetlocinfoEx_nolock

- ea: `0x1800102ec`
- end: `0x180010351`
- name: `_updatetlocinfoEx_nolock`
- size: `101`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001027c`
- `0x1800103b4`
- `0x1800104f0`
- `0x180010680`
- `0x180010924`
- `0x180010954`
- `0x1800109c4`

## callees

- `0x18000ff48`
- `0x18000ffd4`
- `0x1800101d4`
- `0x1800102ec`

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
0x1800102ec  mov     [rsp+arg_0], rbx
0x1800102f1  push    rdi
0x1800102f2  sub     rsp, 20h
0x1800102f6  mov     rdi, rdx
0x1800102f9  test    rdx, rdx
0x1800102fc  jz      short loc_180010344
0x1800102fe  test    rcx, rcx
0x180010301  jz      short loc_180010344
0x180010303  mov     rbx, [rcx]
0x180010306  cmp     rbx, rdx
0x180010309  jnz     short loc_180010310
0x18001030b  mov     rax, rdi
0x18001030e  jmp     short loc_180010346
0x180010310  mov     [rcx], rdi
0x180010313  mov     rcx, rdi
0x180010316  call    __acrt_add_locale_ref
0x18001031b  test    rbx, rbx
0x18001031e  jz      short loc_18001030B
0x180010320  mov     rcx, rbx
0x180010323  call    __acrt_release_locale_ref
0x180010328  cmp     dword ptr [rbx+10h], 0
0x18001032c  jnz     short loc_18001030B
0x18001032e  lea     rax, __acrt_initial_locale_data
0x180010335  cmp     rbx, rax
0x180010338  jz      short loc_18001030B
0x18001033a  mov     rcx, rbx
0x18001033d  call    __acrt_free_locale
0x180010342  jmp     short loc_18001030B
0x180010344  xor     eax, eax
0x180010346  mov     rbx, [rsp+28h+arg_0]
0x18001034b  add     rsp, 20h
0x18001034f  pop     rdi
0x180010350  retn
```
