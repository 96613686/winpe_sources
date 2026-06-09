# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x140006f3c`
- end: `0x140006fd7`
- name: `??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z`
- size: `155`
- prototype: `_LocaleUpdate *__fastcall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400071b0`
- `0x140008e18`
- `0x14000b11c`

## callees

- `0x140005fe8`
- `0x140006f3c`
- `0x14000a3d4`
- `0x14000a440`

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
  if ( !dword_14001A478 )
  {
    v4 = *(_OWORD *)&off_140019788;
    goto LABEL_5;
  }
  v5 = sub_140005FE8();
  *(_QWORD *)this = v5;
  *(_QWORD *)v3 = *(_QWORD *)(v5 + 144);
  *((_QWORD *)this + 2) = *(_QWORD *)(v5 + 136);
  sub_14000A3D4(v5, v3);
  sub_14000A440(*(_QWORD *)this, (char *)this + 16);
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
0x140006f3c  mov     [rsp+arg_0], rbx
0x140006f41  mov     [rsp+arg_8], rsi
0x140006f46  push    rdi
0x140006f47  sub     rsp, 20h
0x140006f4b  mov     byte ptr [rcx+18h], 0
0x140006f4f  mov     rdi, rcx
0x140006f52  lea     rsi, [rcx+8]
0x140006f56  test    rdx, rdx
0x140006f59  jz      short loc_140006F60
0x140006f5b  movups  xmm0, xmmword ptr [rdx]
0x140006f5e  jmp     short loc_140006F70
0x140006f60  cmp     cs:dword_14001A478, 0
0x140006f67  jnz     short loc_140006F76
0x140006f69  movups  xmm0, xmmword ptr cs:off_140019788
0x140006f70  movdqu  xmmword ptr [rsi], xmm0
0x140006f74  jmp     short loc_140006FC4
0x140006f76  call    sub_140005FE8
0x140006f7b  mov     [rdi], rax
0x140006f7e  mov     rdx, rsi
0x140006f81  mov     rcx, [rax+90h]
0x140006f88  mov     [rsi], rcx
0x140006f8b  mov     rcx, [rax+88h]
0x140006f92  mov     [rdi+10h], rcx
0x140006f96  mov     rcx, rax
0x140006f99  call    sub_14000A3D4
0x140006f9e  mov     rcx, [rdi]
0x140006fa1  lea     rdx, [rdi+10h]
0x140006fa5  call    sub_14000A440
0x140006faa  mov     rcx, [rdi]
0x140006fad  mov     eax, [rcx+3A8h]
0x140006fb3  test    al, 2
0x140006fb5  jnz     short loc_140006FC4
0x140006fb7  or      eax, 2
0x140006fba  mov     [rcx+3A8h], eax
0x140006fc0  mov     byte ptr [rdi+18h], 1
0x140006fc4  mov     rbx, [rsp+28h+arg_0]
0x140006fc9  mov     rax, rdi
0x140006fcc  mov     rsi, [rsp+28h+arg_8]
0x140006fd1  add     rsp, 20h
0x140006fd5  pop     rdi
0x140006fd6  retn
```
