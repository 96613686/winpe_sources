# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x18000c5a4`
- end: `0x18000c63f`
- name: `??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z`
- size: `155`
- prototype: `_LocaleUpdate *__fastcall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `26`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000c07c`
- `0x18000e8b8`
- `0x18000ebbc`
- `0x18000f264`
- `0x18000f554`
- `0x180010690`
- `0x180010818`
- `0x180010d58`
- `0x1800111c8`
- `0x18001139c`
- `0x1800127dc`
- `0x180012c08`
- `0x180012ee4`
- `0x180013788`
- `0x18001479c`
- `0x180014cb8`
- `0x180016c18`
- `0x1800179c0`
- `0x180017d6c`
- `0x180017ff8`
- `0x180019af0`
- `0x18001a57c`
- `0x18001e320`
- `0x18001e72c`
- `0x180023c2c`
- `0x180023d3c`

## callees

- `0x18000c5a4`
- `0x1800102a4`
- `0x180010cf0`
- `0x180010d24`

## pseudocode

```c
_LocaleUpdate *__fastcall _LocaleUpdate::_LocaleUpdate(_LocaleUpdate *this, struct __crt_locale_pointers *const a2)
{
  _OWORD *v3; // rsi
  __int128 v4; // xmm0
  __int64 v5; // rax
  int v6; // eax

  *((_BYTE *)this + 24) = 0;
  v3 = (_OWORD *)((char *)this + 8);
  if ( a2 )
  {
    v4 = (__int128)*a2;
LABEL_5:
    *v3 = v4;
    return this;
  }
  if ( !_acrt_locale_changed_data )
  {
    v4 = *(_OWORD *)&_acrt_initial_locale_pointers;
    goto LABEL_5;
  }
  v5 = _acrt_getptd();
  *(_QWORD *)this = v5;
  *(_QWORD *)v3 = *(_QWORD *)(v5 + 144);
  *((_QWORD *)this + 2) = *(_QWORD *)(v5 + 136);
  _acrt_update_locale_info(v5, v3);
  _acrt_update_multibyte_info(*(_QWORD *)this, (char *)this + 16);
  v6 = *(_DWORD *)(*(_QWORD *)this + 936LL);
  if ( (v6 & 2) == 0 )
  {
    *(_DWORD *)(*(_QWORD *)this + 936LL) = v6 | 2;
    *((_BYTE *)this + 24) = 1;
  }
  return this;
}

```

## disassembly

```asm
0x18000c5a4  mov     [rsp+arg_0], rbx
0x18000c5a9  mov     [rsp+arg_8], rsi
0x18000c5ae  push    rdi
0x18000c5af  sub     rsp, 20h
0x18000c5b3  mov     byte ptr [rcx+18h], 0
0x18000c5b7  mov     rdi, rcx
0x18000c5ba  lea     rsi, [rcx+8]
0x18000c5be  test    rdx, rdx
0x18000c5c1  jz      short loc_18000C5C8
0x18000c5c3  movups  xmm0, xmmword ptr [rdx]
0x18000c5c6  jmp     short loc_18000C5D8
0x18000c5c8  cmp     cs:__acrt_locale_changed_data, 0
0x18000c5cf  jnz     short loc_18000C5DE
0x18000c5d1  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x18000c5d8  movdqu  xmmword ptr [rsi], xmm0
0x18000c5dc  jmp     short loc_18000C62C
0x18000c5de  call    __acrt_getptd
0x18000c5e3  mov     [rdi], rax
0x18000c5e6  mov     rdx, rsi
0x18000c5e9  mov     rcx, [rax+90h]
0x18000c5f0  mov     [rsi], rcx
0x18000c5f3  mov     rcx, [rax+88h]
0x18000c5fa  mov     [rdi+10h], rcx
0x18000c5fe  mov     rcx, rax
0x18000c601  call    __acrt_update_locale_info
0x18000c606  mov     rcx, [rdi]
0x18000c609  lea     rdx, [rdi+10h]
0x18000c60d  call    __acrt_update_multibyte_info
0x18000c612  mov     rcx, [rdi]
0x18000c615  mov     eax, [rcx+3A8h]
0x18000c61b  test    al, 2
0x18000c61d  jnz     short loc_18000C62C
0x18000c61f  or      eax, 2
0x18000c622  mov     [rcx+3A8h], eax
0x18000c628  mov     byte ptr [rdi+18h], 1
0x18000c62c  mov     rbx, [rsp+28h+arg_0]
0x18000c631  mov     rax, rdi
0x18000c634  mov     rsi, [rsp+28h+arg_8]
0x18000c639  add     rsp, 20h
0x18000c63d  pop     rdi
0x18000c63e  retn
```
