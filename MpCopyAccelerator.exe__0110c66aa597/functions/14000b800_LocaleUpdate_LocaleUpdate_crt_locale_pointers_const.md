# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x14000b800`
- end: `0x14000b8b5`
- name: `??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z`
- size: `181`
- prototype: `_LocaleUpdate *__fastcall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400112c4`
- `0x140011640`
- `0x140015c30`
- `0x140016664`

## callees

- `0x14000b800`
- `0x140013b68`
- `0x140013d34`
- `0x140013da0`

## pseudocode

```c
_LocaleUpdate *__fastcall _LocaleUpdate::_LocaleUpdate(_LocaleUpdate *this, struct __crt_locale_pointers *const a2)
{
  _LocaleUpdate *result; // rax
  __int64 v4; // rax
  int v5; // eax

  *((_BYTE *)this + 24) = 0;
  if ( a2 )
  {
    result = this;
    *(struct __crt_locale_pointers *)((char *)this + 8) = *a2;
  }
  else if ( _acrt_locale_changed_data )
  {
    v4 = _acrt_getptd();
    *(_QWORD *)this = v4;
    *((_QWORD *)this + 1) = *(_QWORD *)(v4 + 144);
    *((_QWORD *)this + 2) = *(_QWORD *)(v4 + 136);
    _acrt_update_locale_info(v4, (char *)this + 8);
    _acrt_update_multibyte_info(*(_QWORD *)this, (char *)this + 16);
    v5 = *(_DWORD *)(*(_QWORD *)this + 936LL);
    if ( (v5 & 2) == 0 )
    {
      *(_DWORD *)(*(_QWORD *)this + 936LL) = v5 | 2;
      *((_BYTE *)this + 24) = 1;
    }
    return this;
  }
  else
  {
    result = this;
    *(_OWORD *)((char *)this + 8) = *(_OWORD *)&_acrt_initial_locale_pointers;
  }
  return result;
}

```

## disassembly

```asm
0x14000b800  mov     [rsp+arg_8], rsi
0x14000b805  push    rdi
0x14000b806  sub     rsp, 20h
0x14000b80a  mov     byte ptr [rcx+18h], 0
0x14000b80e  mov     rdi, rcx
0x14000b811  test    rdx, rdx
0x14000b814  jz      short loc_14000B82B
0x14000b816  movups  xmm0, xmmword ptr [rdx]
0x14000b819  mov     rax, rcx
0x14000b81c  movups  xmmword ptr [rcx+8], xmm0
0x14000b820  mov     rsi, [rsp+28h+arg_8]
0x14000b825  add     rsp, 20h
0x14000b829  pop     rdi
0x14000b82a  retn
0x14000b82b  cmp     cs:__acrt_locale_changed_data, 0
0x14000b832  jnz     short loc_14000B84D
0x14000b834  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x14000b83b  mov     rax, rdi
0x14000b83e  movups  xmmword ptr [rcx+8], xmm0
0x14000b842  mov     rsi, [rsp+28h+arg_8]
0x14000b847  add     rsp, 20h
0x14000b84b  pop     rdi
0x14000b84c  retn
0x14000b84d  mov     [rsp+28h+arg_0], rbx
0x14000b852  call    __acrt_getptd
0x14000b857  mov     [rdi], rax
0x14000b85a  lea     rdx, [rdi+8]
0x14000b85e  mov     rcx, [rax+90h]
0x14000b865  mov     [rdi+8], rcx
0x14000b869  mov     rcx, [rax+88h]
0x14000b870  mov     [rdi+10h], rcx
0x14000b874  mov     rcx, rax
0x14000b877  call    __acrt_update_locale_info
0x14000b87c  mov     rcx, [rdi]
0x14000b87f  lea     rdx, [rdi+10h]
0x14000b883  call    __acrt_update_multibyte_info
0x14000b888  mov     rcx, [rdi]
0x14000b88b  mov     rbx, [rsp+28h+arg_0]
0x14000b890  mov     eax, [rcx+3A8h]
0x14000b896  test    al, 2
0x14000b898  jnz     short loc_14000B8A7
0x14000b89a  or      eax, 2
0x14000b89d  mov     [rcx+3A8h], eax
0x14000b8a3  mov     byte ptr [rdi+18h], 1
0x14000b8a7  mov     rsi, [rsp+28h+arg_8]
0x14000b8ac  mov     rax, rdi
0x14000b8af  add     rsp, 20h
0x14000b8b3  pop     rdi
0x14000b8b4  retn
```
