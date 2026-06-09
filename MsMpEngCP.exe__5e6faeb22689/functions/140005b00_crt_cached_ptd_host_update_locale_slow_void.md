# __crt_cached_ptd_host::update_locale_slow(void)

- ea: `0x140005b00`
- end: `0x140005b76`
- name: `?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000a4ac`
- `0x14000b67c`
- `0x14000bfc8`

## callees

- `0x140005a90`
- `0x140005b00`
- `0x14000a408`
- `0x14000a474`

## pseudocode

```c
void __fastcall __crt_cached_ptd_host::update_locale_slow(__crt_cached_ptd_host *this)
{
  __int64 v2; // rsi
  int v3; // eax

  v2 = unknown_libname_14();
  *((_QWORD *)this + 3) = *(_QWORD *)(v2 + 144);
  *((_QWORD *)this + 4) = *(_QWORD *)(v2 + 136);
  sub_14000A408(v2, (char *)this + 24, *((_QWORD *)this + 1));
  sub_14000A474(v2, (char *)this + 32, *((_QWORD *)this + 1));
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
0x140005b00  mov     [rsp+arg_0], rbx
0x140005b05  mov     [rsp+arg_8], rsi
0x140005b0a  push    rdi
0x140005b0b  sub     rsp, 20h
0x140005b0f  mov     rdi, rcx
0x140005b12  call    unknown_libname_14; Microsoft VisualC 64bit universal runtime
0x140005b17  lea     rdx, [rdi+18h]
0x140005b1b  mov     rcx, rax
0x140005b1e  mov     rsi, rax
0x140005b21  mov     r8, [rax+90h]
0x140005b28  mov     [rdx], r8
0x140005b2b  mov     r8, [rax+88h]
0x140005b32  mov     [rdi+20h], r8
0x140005b36  mov     r8, [rdi+8]
0x140005b3a  call    sub_14000A408
0x140005b3f  mov     r8, [rdi+8]
0x140005b43  lea     rdx, [rdi+20h]
0x140005b47  mov     rcx, rsi
0x140005b4a  call    sub_14000A474
0x140005b4f  mov     eax, [rsi+3A8h]
0x140005b55  test    al, 2
0x140005b57  jnz     short loc_140005B66
0x140005b59  or      eax, 2
0x140005b5c  mov     [rsi+3A8h], eax
0x140005b62  mov     byte ptr [rdi+28h], 2
0x140005b66  mov     rbx, [rsp+28h+arg_0]
0x140005b6b  mov     rsi, [rsp+28h+arg_8]
0x140005b70  add     rsp, 20h
0x140005b74  pop     rdi
0x140005b75  retn
```
