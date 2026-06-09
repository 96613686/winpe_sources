# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x14000405c`
- end: `0x1400040f7`
- name: `??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z`
- size: `155`
- prototype: `_LocaleUpdate *__fastcall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `9`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000418c`
- `0x1400047ec`
- `0x14000af08`
- `0x14000fab8`
- `0x140010590`
- `0x140013a14`
- `0x14001481c`
- `0x140017d80`
- `0x140022df0`

## callees

- `0x14000405c`
- `0x14000ff40`
- `0x1400102a4`
- `0x140010310`

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
  if ( !dword_1400D6988 )
  {
    v4 = *(_OWORD *)&off_1400D5158;
    goto LABEL_5;
  }
  v5 = _acrt_getptd();
  *(_QWORD *)this = v5;
  *(_QWORD *)v3 = *(_QWORD *)(v5 + 144);
  *((_QWORD *)this + 2) = *(_QWORD *)(v5 + 136);
  sub_1400102A4(v5, v3);
  sub_140010310(*(_QWORD *)this, (char *)this + 16);
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
0x14000405c  mov     [rsp+arg_0], rbx
0x140004061  mov     [rsp+arg_8], rsi
0x140004066  push    rdi
0x140004067  sub     rsp, 20h
0x14000406b  mov     byte ptr [rcx+18h], 0
0x14000406f  mov     rdi, rcx
0x140004072  lea     rsi, [rcx+8]
0x140004076  test    rdx, rdx
0x140004079  jz      short loc_140004080
0x14000407b  movups  xmm0, xmmword ptr [rdx]
0x14000407e  jmp     short loc_140004090
0x140004080  cmp     cs:dword_1400D6988, 0
0x140004087  jnz     short loc_140004096
0x140004089  movups  xmm0, xmmword ptr cs:off_1400D5158
0x140004090  movdqu  xmmword ptr [rsi], xmm0
0x140004094  jmp     short loc_1400040E4
0x140004096  call    __acrt_getptd
0x14000409b  mov     [rdi], rax
0x14000409e  mov     rdx, rsi
0x1400040a1  mov     rcx, [rax+90h]
0x1400040a8  mov     [rsi], rcx
0x1400040ab  mov     rcx, [rax+88h]
0x1400040b2  mov     [rdi+10h], rcx
0x1400040b6  mov     rcx, rax
0x1400040b9  call    sub_1400102A4
0x1400040be  mov     rcx, [rdi]
0x1400040c1  lea     rdx, [rdi+10h]
0x1400040c5  call    sub_140010310
0x1400040ca  mov     rcx, [rdi]
0x1400040cd  mov     eax, [rcx+3A8h]
0x1400040d3  test    al, 2
0x1400040d5  jnz     short loc_1400040E4
0x1400040d7  or      eax, 2
0x1400040da  mov     [rcx+3A8h], eax
0x1400040e0  mov     byte ptr [rdi+18h], 1
0x1400040e4  mov     rbx, [rsp+28h+arg_0]
0x1400040e9  mov     rax, rdi
0x1400040ec  mov     rsi, [rsp+28h+arg_8]
0x1400040f1  add     rsp, 20h
0x1400040f5  pop     rdi
0x1400040f6  retn
```
