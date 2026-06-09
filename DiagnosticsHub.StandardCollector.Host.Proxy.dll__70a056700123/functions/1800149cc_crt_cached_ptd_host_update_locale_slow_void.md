# __crt_cached_ptd_host::update_locale_slow(void)

- ea: `0x1800149cc`
- end: `0x180014a42`
- name: `?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `90`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180014998`
- `0x1800149b8`
- `0x180014ab0`
- `0x180014fdc`
- `0x180015610`
- `0x18001b18c`
- `0x18001b668`
- `0x18001b8a0`
- `0x18001dc44`
- `0x18001df20`
- `0x18001e6bc`
- `0x18001e998`
- `0x180021c20`
- `0x18004374c`
- `0x180043acc`
- `0x180043ee4`
- `0x180044268`
- `0x1800445d0`
- `0x1800449d0`
- `0x180046428`
- `0x18004657c`
- `0x1800466fc`
- `0x180046850`
- `0x18004699c`
- `0x180046b14`
- `0x180046ec4`
- `0x180046ff0`
- `0x18004711c`
- `0x180047248`
- `0x18004736c`
- `0x180047490`
- `0x1800477d0`
- `0x1800478b0`
- `0x180047990`
- `0x180047a70`
- `0x180047b4c`
- `0x180047c28`
- `0x180049434`
- `0x18004996c`
- `0x180049ebc`
- `0x18004a3f4`
- `0x18004a864`
- `0x18004ad14`
- `0x18004b184`
- `0x18004b780`
- `0x18004bdb8`
- `0x18004c3b4`
- `0x18004c92c`
- `0x18004ceb8`
- `0x18004de90`

## callees

- `0x180006fec`
- `0x180012e5c`
- `0x180012ec8`
- `0x1800149cc`

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
0x1800149cc  mov     [rsp+arg_0], rbx
0x1800149d1  mov     [rsp+arg_8], rsi
0x1800149d6  push    rdi
0x1800149d7  sub     rsp, 20h
0x1800149db  mov     rdi, rcx
0x1800149de  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800149e3  lea     rdx, [rdi+18h]
0x1800149e7  mov     rcx, rax
0x1800149ea  mov     rsi, rax
0x1800149ed  mov     r8, [rax+90h]
0x1800149f4  mov     [rdx], r8
0x1800149f7  mov     r8, [rax+88h]
0x1800149fe  mov     [rdi+20h], r8
0x180014a02  mov     r8, [rdi+8]
0x180014a06  call    __acrt_update_locale_info_explicit
0x180014a0b  mov     r8, [rdi+8]
0x180014a0f  lea     rdx, [rdi+20h]
0x180014a13  mov     rcx, rsi
0x180014a16  call    __acrt_update_multibyte_info_explicit
0x180014a1b  mov     eax, [rsi+3A8h]
0x180014a21  test    al, 2
0x180014a23  jnz     short loc_180014A32
0x180014a25  or      eax, 2
0x180014a28  mov     [rsi+3A8h], eax
0x180014a2e  mov     byte ptr [rdi+28h], 2
0x180014a32  mov     rbx, [rsp+28h+arg_0]
0x180014a37  mov     rsi, [rsp+28h+arg_8]
0x180014a3c  add     rsp, 20h
0x180014a40  pop     rdi
0x180014a41  retn
```
