# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x140066ee4`
- end: `0x140066f7f`
- name: `??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z`
- size: `155`
- prototype: `_LocaleUpdate *__fastcall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `9`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140066fd8`
- `0x14006707c`
- `0x14006b534`
- `0x14006c4d8`
- `0x14006ed00`
- `0x14006f378`
- `0x14007505c`
- `0x1400785d8`
- `0x14007a9d4`

## callees

- `0x140066ee4`
- `0x1400720a8`
- `0x140072340`
- `0x1400723ac`

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
  if ( !dword_1400C43C8 )
  {
    v4 = *(_OWORD *)&off_1400BE1B8;
    goto LABEL_5;
  }
  v5 = sub_1400720A8();
  *(_QWORD *)this = v5;
  *(_QWORD *)v3 = *(_QWORD *)(v5 + 144);
  *((_QWORD *)this + 2) = *(_QWORD *)(v5 + 136);
  sub_140072340(v5, v3);
  sub_1400723AC(*(_QWORD *)this, (char *)this + 16);
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
0x140066ee4  mov     [rsp+arg_0], rbx
0x140066ee9  mov     [rsp+arg_8], rsi
0x140066eee  push    rdi
0x140066eef  sub     rsp, 20h
0x140066ef3  mov     byte ptr [rcx+18h], 0
0x140066ef7  mov     rdi, rcx
0x140066efa  lea     rsi, [rcx+8]
0x140066efe  test    rdx, rdx
0x140066f01  jz      short loc_140066F08
0x140066f03  movups  xmm0, xmmword ptr [rdx]
0x140066f06  jmp     short loc_140066F18
0x140066f08  cmp     cs:dword_1400C43C8, 0
0x140066f0f  jnz     short loc_140066F1E
0x140066f11  movups  xmm0, xmmword ptr cs:off_1400BE1B8
0x140066f18  movdqu  xmmword ptr [rsi], xmm0
0x140066f1c  jmp     short loc_140066F6C
0x140066f1e  call    sub_1400720A8
0x140066f23  mov     [rdi], rax
0x140066f26  mov     rdx, rsi
0x140066f29  mov     rcx, [rax+90h]
0x140066f30  mov     [rsi], rcx
0x140066f33  mov     rcx, [rax+88h]
0x140066f3a  mov     [rdi+10h], rcx
0x140066f3e  mov     rcx, rax
0x140066f41  call    sub_140072340
0x140066f46  mov     rcx, [rdi]
0x140066f49  lea     rdx, [rdi+10h]
0x140066f4d  call    sub_1400723AC
0x140066f52  mov     rcx, [rdi]
0x140066f55  mov     eax, [rcx+3A8h]
0x140066f5b  test    al, 2
0x140066f5d  jnz     short loc_140066F6C
0x140066f5f  or      eax, 2
0x140066f62  mov     [rcx+3A8h], eax
0x140066f68  mov     byte ptr [rdi+18h], 1
0x140066f6c  mov     rbx, [rsp+28h+arg_0]
0x140066f71  mov     rax, rdi
0x140066f74  mov     rsi, [rsp+28h+arg_8]
0x140066f79  add     rsp, 20h
0x140066f7d  pop     rdi
0x140066f7e  retn
```
