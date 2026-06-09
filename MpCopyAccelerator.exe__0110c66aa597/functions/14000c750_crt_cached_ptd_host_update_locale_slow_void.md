# __crt_cached_ptd_host::update_locale_slow(void)

- ea: `0x14000c750`
- end: `0x14000c7c6`
- name: `?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `14`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000e8d4`
- `0x14000f240`
- `0x14000f6b0`
- `0x14000fd18`
- `0x14000ff74`
- `0x1400102c4`
- `0x140010578`
- `0x140014058`
- `0x1400141d0`
- `0x140014650`
- `0x140014ae8`
- `0x140014da4`
- `0x14001a20c`
- `0x14001ab58`

## callees

- `0x14000bb70`
- `0x14000c750`
- `0x140013d68`
- `0x140013dd4`

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
0x14000c750  mov     [rsp+arg_0], rbx
0x14000c755  mov     [rsp+arg_8], rsi
0x14000c75a  push    rdi
0x14000c75b  sub     rsp, 20h
0x14000c75f  mov     rdi, rcx
0x14000c762  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ
0x14000c767  lea     rdx, [rdi+18h]
0x14000c76b  mov     rcx, rax
0x14000c76e  mov     rsi, rax
0x14000c771  mov     r8, [rax+90h]
0x14000c778  mov     [rdx], r8
0x14000c77b  mov     r8, [rax+88h]
0x14000c782  mov     [rdi+20h], r8
0x14000c786  mov     r8, [rdi+8]
0x14000c78a  call    __acrt_update_locale_info_explicit
0x14000c78f  mov     r8, [rdi+8]
0x14000c793  lea     rdx, [rdi+20h]
0x14000c797  mov     rcx, rsi
0x14000c79a  call    __acrt_update_multibyte_info_explicit
0x14000c79f  mov     eax, [rsi+3A8h]
0x14000c7a5  test    al, 2
0x14000c7a7  jnz     short loc_14000C7B6
0x14000c7a9  or      eax, 2
0x14000c7ac  mov     [rsi+3A8h], eax
0x14000c7b2  mov     byte ptr [rdi+28h], 2
0x14000c7b6  mov     rbx, [rsp+28h+arg_0]
0x14000c7bb  mov     rsi, [rsp+28h+arg_8]
0x14000c7c0  add     rsp, 20h
0x14000c7c4  pop     rdi
0x14000c7c5  retn
```
