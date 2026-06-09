# __acrt_update_thread_locale_data

- ea: `0x140013278`
- end: `0x1400132e6`
- name: `__acrt_update_thread_locale_data`
- size: `110`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400102a4`
- `0x1400102d8`

## callees

- `0x14000ff40`
- `0x1400104cc`
- `0x140013278`
- `0x1400132e8`
- `0x140013398`
- `0x1400133f8`

## pseudocode

```c
__int64 _acrt_update_thread_locale_data()
{
  __int64 v0; // rax
  __int64 *v1; // rdi
  __int64 v2; // rbx

  v0 = _acrt_getptd();
  v1 = (__int64 *)(v0 + 144);
  if ( (*(_DWORD *)(v0 + 936) & dword_1400D67C0) == 0 || (v2 = *v1) == 0 )
  {
    sub_140013398(4);
    v2 = updatetlocinfoEx_nolock(v1, qword_1400D6990);
    sub_1400133F8(4);
    if ( !v2 )
      abort();
  }
  return v2;
}

```

## disassembly

```asm
0x140013278  mov     [rsp+arg_0], rbx
0x14001327d  push    rdi
0x14001327e  sub     rsp, 20h
0x140013282  call    __acrt_getptd
0x140013287  lea     rdi, [rax+90h]
0x14001328e  mov     ecx, [rax+3A8h]
0x140013294  mov     eax, cs:dword_1400D67C0
0x14001329a  test    eax, ecx
0x14001329c  jz      short loc_1400132A6
0x14001329e  mov     rbx, [rdi]
0x1400132a1  test    rbx, rbx
0x1400132a4  jnz     short loc_1400132D2
0x1400132a6  mov     ecx, 4
0x1400132ab  call    sub_140013398
0x1400132b0  nop
0x1400132b1  mov     rdx, cs:qword_1400D6990
0x1400132b8  mov     rcx, rdi
0x1400132bb  call    _updatetlocinfoEx_nolock
0x1400132c0  mov     rbx, rax
0x1400132c3  mov     ecx, 4
0x1400132c8  call    sub_1400133F8
0x1400132cd  test    rbx, rbx
0x1400132d0  jz      short loc_1400132E0
0x1400132d2  mov     rax, rbx
0x1400132d5  mov     rbx, [rsp+28h+arg_0]
0x1400132da  add     rsp, 20h
0x1400132de  pop     rdi
0x1400132df  retn
0x1400132e0  call    abort
0x1400ae235  push    rbp; Microsoft VisualC 64bit universal runtime
0x1400ae237  sub     rsp, 20h
0x1400ae23b  mov     rbp, rdx
0x1400ae23e  mov     ecx, 4
0x1400ae243  add     rsp, 20h
0x1400ae247  pop     rbp
0x1400ae248  jmp     sub_1400133F8
```
