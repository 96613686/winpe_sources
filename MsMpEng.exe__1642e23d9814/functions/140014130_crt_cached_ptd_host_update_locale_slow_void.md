# __crt_cached_ptd_host::update_locale_slow(void)

- ea: `0x140014130`
- end: `0x1400141a6`
- name: `?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `15`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140012108`
- `0x140012d30`
- `0x1400131a0`
- `0x140013808`
- `0x140013a64`
- `0x140013db4`
- `0x140014068`
- `0x1400154c8`
- `0x1400199f0`
- `0x140019e88`
- `0x14001a144`
- `0x14001a7e8`
- `0x14001a998`
- `0x140020ed4`
- `0x1400218b8`

## callees

- `0x140011f80`
- `0x140014130`
- `0x140019858`
- `0x1400198c4`

## pseudocode

```c
void __fastcall __crt_cached_ptd_host::update_locale_slow(__crt_cached_ptd_host *this)
{
  __int64 v2; // rsi
  int v3; // eax

  v2 = unknown_libname_33();
  *((_QWORD *)this + 3) = *(_QWORD *)(v2 + 144);
  *((_QWORD *)this + 4) = *(_QWORD *)(v2 + 136);
  sub_140019858(v2, (char *)this + 24, *((_QWORD *)this + 1));
  sub_1400198C4(v2, (char *)this + 32, *((_QWORD *)this + 1));
  v3 = *(_DWORD *)(v2 + 936);
  if ( (v3 & 2) == 0 )
  {
    *(_DWORD *)(v2 + 936) = v3 | 2;
    *((_BYTE *)this + 40) = 2;
  }
}

```

## disassembly

```asm
0x140014130  mov     [rsp+arg_0], rbx
0x140014135  mov     [rsp+arg_8], rsi
0x14001413a  push    rdi
0x14001413b  sub     rsp, 20h
0x14001413f  mov     rdi, rcx
0x140014142  call    unknown_libname_33; Microsoft VisualC 64bit universal runtime
0x140014147  lea     rdx, [rdi+18h]
0x14001414b  mov     rcx, rax
0x14001414e  mov     rsi, rax
0x140014151  mov     r8, [rax+90h]
0x140014158  mov     [rdx], r8
0x14001415b  mov     r8, [rax+88h]
0x140014162  mov     [rdi+20h], r8
0x140014166  mov     r8, [rdi+8]
0x14001416a  call    sub_140019858
0x14001416f  mov     r8, [rdi+8]
0x140014173  lea     rdx, [rdi+20h]
0x140014177  mov     rcx, rsi
0x14001417a  call    sub_1400198C4
0x14001417f  mov     eax, [rsi+3A8h]
0x140014185  test    al, 2
0x140014187  jnz     short loc_140014196
0x140014189  or      eax, 2
0x14001418c  mov     [rsi+3A8h], eax
0x140014192  mov     byte ptr [rdi+28h], 2
0x140014196  mov     rbx, [rsp+28h+arg_0]
0x14001419b  mov     rsi, [rsp+28h+arg_8]
0x1400141a0  add     rsp, 20h
0x1400141a4  pop     rdi
0x1400141a5  retn
```
