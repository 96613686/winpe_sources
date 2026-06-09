# __crt_cached_ptd_host::update_locale_slow(void)

- ea: `0x18001512c`
- end: `0x1800151a2`
- name: `?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `90`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800150f8`
- `0x180015118`
- `0x180015210`
- `0x18001573c`
- `0x180015d70`
- `0x18001b8ec`
- `0x18001bdc8`
- `0x18001c000`
- `0x18001e3a4`
- `0x18001e680`
- `0x18001ee1c`
- `0x18001f0f8`
- `0x180022380`
- `0x180043a2c`
- `0x180043dac`
- `0x1800441c4`
- `0x180044548`
- `0x1800448b0`
- `0x180044cb0`
- `0x180046708`
- `0x18004685c`
- `0x1800469dc`
- `0x180046b30`
- `0x180046c7c`
- `0x180046df4`
- `0x1800471a4`
- `0x1800472d0`
- `0x1800473fc`
- `0x180047528`
- `0x18004764c`
- `0x180047770`
- `0x180047ab0`
- `0x180047b90`
- `0x180047c70`
- `0x180047d50`
- `0x180047e2c`
- `0x180047f08`
- `0x180049714`
- `0x180049c4c`
- `0x18004a19c`
- `0x18004a6d4`
- `0x18004ab44`
- `0x18004aff4`
- `0x18004b464`
- `0x18004ba60`
- `0x18004c098`
- `0x18004c694`
- `0x18004cc0c`
- `0x18004d198`
- `0x18004e170`

## callees

- `0x18000774c`
- `0x1800135bc`
- `0x180013628`
- `0x18001512c`

## pseudocode

```c
void __fastcall __crt_cached_ptd_host::update_locale_slow(__crt_cached_ptd_host *this)
{
  struct __acrt_ptd *raw_ptd; // rsi
  int v3; // eax

  raw_ptd = __crt_cached_ptd_host::get_raw_ptd(this);
  *((_QWORD *)this + 3) = *((_QWORD *)raw_ptd + 18);
  *((_QWORD *)this + 4) = *((_QWORD *)raw_ptd + 17);
  _acrt_update_locale_info_explicit(raw_ptd, (char *)this + 24, *((_QWORD *)this + 1));
  _acrt_update_multibyte_info_explicit(raw_ptd, (char *)this + 32, *((_QWORD *)this + 1));
  v3 = *((_DWORD *)raw_ptd + 234);
  if ( (v3 & 2) == 0 )
  {
    *((_DWORD *)raw_ptd + 234) = v3 | 2;
    *((_BYTE *)this + 40) = 2;
  }
}

```

## disassembly

```asm
0x18001512c  mov     [rsp+arg_0], rbx
0x180015131  mov     [rsp+arg_8], rsi
0x180015136  push    rdi
0x180015137  sub     rsp, 20h
0x18001513b  mov     rdi, rcx
0x18001513e  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180015143  lea     rdx, [rdi+18h]
0x180015147  mov     rcx, rax
0x18001514a  mov     rsi, rax
0x18001514d  mov     r8, [rax+90h]
0x180015154  mov     [rdx], r8
0x180015157  mov     r8, [rax+88h]
0x18001515e  mov     [rdi+20h], r8
0x180015162  mov     r8, [rdi+8]
0x180015166  call    __acrt_update_locale_info_explicit
0x18001516b  mov     r8, [rdi+8]
0x18001516f  lea     rdx, [rdi+20h]
0x180015173  mov     rcx, rsi
0x180015176  call    __acrt_update_multibyte_info_explicit
0x18001517b  mov     eax, [rsi+3A8h]
0x180015181  test    al, 2
0x180015183  jnz     short loc_180015192
0x180015185  or      eax, 2
0x180015188  mov     [rsi+3A8h], eax
0x18001518e  mov     byte ptr [rdi+28h], 2
0x180015192  mov     rbx, [rsp+28h+arg_0]
0x180015197  mov     rsi, [rsp+28h+arg_8]
0x18001519c  add     rsp, 20h
0x1800151a0  pop     rdi
0x1800151a1  retn
```
