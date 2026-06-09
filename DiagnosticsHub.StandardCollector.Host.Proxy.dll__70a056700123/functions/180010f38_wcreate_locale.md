# _wcreate_locale

- ea: `0x180010f38`
- end: `0x180011080`
- name: `_wcreate_locale`
- size: `328`
- prototype: `_locale_t __cdecl(int Category, const wchar_t *Locale)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800108d4`

## callees

- `0x180007788`
- `0x180007860`
- `0x1800078e0`
- `0x18000a540`
- `0x18000f874`
- `0x18000fa74`
- `0x180010814`
- `0x180010f38`
- `0x180011378`

## pseudocode

```c
_locale_t __cdecl wcreate_locale(int Category, const wchar_t *Locale)
{
  __crt_locale_pointers *v4; // rbp
  __crt_locale_pointers *v5; // rsi
  unsigned int *v6; // rbx
  struct __crt_multibyte_data *v7; // rdi
  struct __crt_multibyte_data *v8; // rax
  __crt_locale_pointers *v9; // rax
  unsigned int *v10; // rcx

  if ( (unsigned int)Category > 5 )
    return 0;
  v4 = 0;
  if ( !Locale )
    return 0;
  v5 = (__crt_locale_pointers *)calloc_base(1u, 0x10u);
  if ( v5 )
  {
    v6 = (unsigned int *)calloc_base(1u, 0x158u);
    if ( v6 )
    {
      v7 = (struct __crt_multibyte_data *)calloc_base(1u, 0x228u);
      if ( v7 )
      {
        copytlocinfo_nolock(v6, &_acrt_initial_locale_data);
        if ( !wsetlocale_nolock(v6, (unsigned int)Category, Locale) || (unsigned int)setmbcp_nolock(v6[3], v7) )
        {
          _acrt_release_locale_ref(v6);
          v10 = v6;
          v6 = 0;
          _acrt_free_locale(v10);
        }
        else
        {
          *(_DWORD *)v7 = 1;
          v5->locinfo = (struct __crt_locale_data *)v6;
          v6 = 0;
          v8 = v7;
          v7 = 0;
          v5->mbcinfo = v8;
          v9 = v5;
          v5 = 0;
          v4 = v9;
        }
      }
      else
      {
        *errno() = 12;
      }
      free_base(v7);
    }
    else
    {
      *errno() = 12;
    }
    free_base(v6);
  }
  else
  {
    *errno() = 12;
  }
  free_base(v5);
  return v4;
}

```

## disassembly

```asm
0x180010f38  mov     rax, rsp
0x180010f3b  mov     [rax+8], rbx
0x180010f3f  mov     [rax+10h], rbp
0x180010f43  mov     [rax+18h], rsi
0x180010f47  mov     [rax+20h], rdi
0x180010f4b  push    r12
0x180010f4d  push    r14
0x180010f4f  push    r15
0x180010f51  sub     rsp, 20h
0x180010f55  mov     r14, rdx
0x180010f58  mov     r15d, ecx
0x180010f5b  cmp     ecx, 5
0x180010f5e  ja      loc_18001105F
0x180010f64  xor     ebp, ebp
0x180010f66  test    rdx, rdx
0x180010f69  jz      loc_18001105F
0x180010f6f  lea     r12d, [rbp+1]
0x180010f73  mov     ecx, r12d; Count
0x180010f76  lea     edx, [rbp+10h]; Size
0x180010f79  call    _calloc_base
0x180010f7e  mov     rsi, rax
0x180010f81  test    rax, rax
0x180010f84  jnz     short loc_180010F96
0x180010f86  call    _errno
0x180010f8b  mov     dword ptr [rax], 0Ch
0x180010f91  jmp     loc_180011052
0x180010f96  mov     edx, 158h; Size
0x180010f9b  mov     rcx, r12; Count
0x180010f9e  call    _calloc_base
0x180010fa3  mov     rbx, rax
0x180010fa6  test    rax, rax
0x180010fa9  jnz     short loc_180010FBB
0x180010fab  call    _errno
0x180010fb0  mov     dword ptr [rax], 0Ch
0x180010fb6  jmp     loc_18001104A
0x180010fbb  mov     edx, 228h; Size
0x180010fc0  mov     rcx, r12; Count
0x180010fc3  call    _calloc_base
0x180010fc8  mov     rdi, rax
0x180010fcb  test    rax, rax
0x180010fce  jnz     short loc_180010FDD
0x180010fd0  call    _errno
0x180010fd5  mov     dword ptr [rax], 0Ch
0x180010fdb  jmp     short loc_180011042
0x180010fdd  lea     rdx, __acrt_initial_locale_data
0x180010fe4  mov     rcx, rbx
0x180010fe7  call    _copytlocinfo_nolock
0x180010fec  mov     r8, r14
0x180010fef  mov     edx, r15d
0x180010ff2  mov     rcx, rbx
0x180010ff5  call    _wsetlocale_nolock
0x180010ffa  test    rax, rax
0x180010ffd  jz      short loc_18001102F
0x180010fff  mov     ecx, [rbx+0Ch]
0x180011002  mov     rdx, rdi
0x180011005  call    _setmbcp_nolock
0x18001100a  test    eax, eax
0x18001100c  jnz     short loc_18001102F
0x18001100e  mov     rax, rbx
0x180011011  mov     [rdi], r12d
0x180011014  mov     [rsi], rax
0x180011017  mov     rbx, rbp
0x18001101a  mov     rax, rdi
0x18001101d  mov     rdi, rbp
0x180011020  mov     [rsi+8], rax
0x180011024  mov     rax, rsi
0x180011027  mov     rsi, rbp
0x18001102a  mov     rbp, rax
0x18001102d  jmp     short loc_180011042
0x18001102f  mov     rcx, rbx
0x180011032  call    __acrt_release_locale_ref
0x180011037  mov     rcx, rbx
0x18001103a  mov     rbx, rbp
0x18001103d  call    __acrt_free_locale
0x180011042  mov     rcx, rdi; Block
0x180011045  call    _free_base
0x18001104a  mov     rcx, rbx; Block
0x18001104d  call    _free_base
0x180011052  mov     rcx, rsi; Block
0x180011055  call    _free_base
0x18001105a  mov     rax, rbp
0x18001105d  jmp     short loc_180011061
0x18001105f  xor     eax, eax
0x180011061  mov     rbx, [rsp+38h+arg_0]
0x180011066  mov     rbp, [rsp+38h+arg_8]
0x18001106b  mov     rsi, [rsp+38h+arg_10]
0x180011070  mov     rdi, [rsp+38h+arg_18]
0x180011075  add     rsp, 20h
0x180011079  pop     r15
0x18001107b  pop     r14
0x18001107d  pop     r12
0x18001107f  retn
```
