# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x1800093a4`
- end: `0x18000943f`
- name: `??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z`
- size: `155`
- prototype: `_LocaleUpdate *__fastcall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `17`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180008d88`
- `0x180009610`
- `0x180009b64`
- `0x180009c18`
- `0x180009fac`
- `0x18000a520`
- `0x18000ac3c`
- `0x18000aff0`
- `0x18000b170`
- `0x180013668`
- `0x180013754`
- `0x180013c40`
- `0x180014354`
- `0x18001af0c`
- `0x18001d820`
- `0x180020fe8`
- `0x18002200c`

## callees

- `0x180006ef0`
- `0x1800093a4`
- `0x180013588`
- `0x1800135f4`

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
0x1800093a4  mov     [rsp+arg_0], rbx
0x1800093a9  mov     [rsp+arg_8], rsi
0x1800093ae  push    rdi
0x1800093af  sub     rsp, 20h
0x1800093b3  mov     byte ptr [rcx+18h], 0
0x1800093b7  mov     rdi, rcx
0x1800093ba  lea     rsi, [rcx+8]
0x1800093be  test    rdx, rdx
0x1800093c1  jz      short loc_1800093C8
0x1800093c3  movups  xmm0, xmmword ptr [rdx]
0x1800093c6  jmp     short loc_1800093D8
0x1800093c8  cmp     cs:__acrt_locale_changed_data, 0
0x1800093cf  jnz     short loc_1800093DE
0x1800093d1  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x1800093d8  movdqu  xmmword ptr [rsi], xmm0
0x1800093dc  jmp     short loc_18000942C
0x1800093de  call    __acrt_getptd
0x1800093e3  mov     [rdi], rax
0x1800093e6  mov     rdx, rsi
0x1800093e9  mov     rcx, [rax+90h]
0x1800093f0  mov     [rsi], rcx
0x1800093f3  mov     rcx, [rax+88h]
0x1800093fa  mov     [rdi+10h], rcx
0x1800093fe  mov     rcx, rax
0x180009401  call    __acrt_update_locale_info
0x180009406  mov     rcx, [rdi]
0x180009409  lea     rdx, [rdi+10h]
0x18000940d  call    __acrt_update_multibyte_info
0x180009412  mov     rcx, [rdi]
0x180009415  mov     eax, [rcx+3A8h]
0x18000941b  test    al, 2
0x18000941d  jnz     short loc_18000942C
0x18000941f  or      eax, 2
0x180009422  mov     [rcx+3A8h], eax
0x180009428  mov     byte ptr [rdi+18h], 1
0x18000942c  mov     rbx, [rsp+28h+arg_0]
0x180009431  mov     rax, rdi
0x180009434  mov     rsi, [rsp+28h+arg_8]
0x180009439  add     rsp, 20h
0x18000943d  pop     rdi
0x18000943e  retn
```
