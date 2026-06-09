# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x180008c44`
- end: `0x180008cdf`
- name: `??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z`
- size: `155`
- prototype: `_LocaleUpdate *__fastcall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `17`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180008628`
- `0x180008eb0`
- `0x180009404`
- `0x1800094b8`
- `0x18000984c`
- `0x180009dc0`
- `0x18000a4dc`
- `0x18000a890`
- `0x18000aa10`
- `0x180012f08`
- `0x180012ff4`
- `0x1800134e0`
- `0x180013bf4`
- `0x18001a7ac`
- `0x18001d0c0`
- `0x180020888`
- `0x1800218ac`

## callees

- `0x180006790`
- `0x180008c44`
- `0x180012e28`
- `0x180012e94`

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
0x180008c44  mov     [rsp+arg_0], rbx
0x180008c49  mov     [rsp+arg_8], rsi
0x180008c4e  push    rdi
0x180008c4f  sub     rsp, 20h
0x180008c53  mov     byte ptr [rcx+18h], 0
0x180008c57  mov     rdi, rcx
0x180008c5a  lea     rsi, [rcx+8]
0x180008c5e  test    rdx, rdx
0x180008c61  jz      short loc_180008C68
0x180008c63  movups  xmm0, xmmword ptr [rdx]
0x180008c66  jmp     short loc_180008C78
0x180008c68  cmp     cs:__acrt_locale_changed_data, 0
0x180008c6f  jnz     short loc_180008C7E
0x180008c71  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180008c78  movdqu  xmmword ptr [rsi], xmm0
0x180008c7c  jmp     short loc_180008CCC
0x180008c7e  call    __acrt_getptd
0x180008c83  mov     [rdi], rax
0x180008c86  mov     rdx, rsi
0x180008c89  mov     rcx, [rax+90h]
0x180008c90  mov     [rsi], rcx
0x180008c93  mov     rcx, [rax+88h]
0x180008c9a  mov     [rdi+10h], rcx
0x180008c9e  mov     rcx, rax
0x180008ca1  call    __acrt_update_locale_info
0x180008ca6  mov     rcx, [rdi]
0x180008ca9  lea     rdx, [rdi+10h]
0x180008cad  call    __acrt_update_multibyte_info
0x180008cb2  mov     rcx, [rdi]
0x180008cb5  mov     eax, [rcx+3A8h]
0x180008cbb  test    al, 2
0x180008cbd  jnz     short loc_180008CCC
0x180008cbf  or      eax, 2
0x180008cc2  mov     [rcx+3A8h], eax
0x180008cc8  mov     byte ptr [rdi+18h], 1
0x180008ccc  mov     rbx, [rsp+28h+arg_0]
0x180008cd1  mov     rax, rdi
0x180008cd4  mov     rsi, [rsp+28h+arg_8]
0x180008cd9  add     rsp, 20h
0x180008cdd  pop     rdi
0x180008cde  retn
```
