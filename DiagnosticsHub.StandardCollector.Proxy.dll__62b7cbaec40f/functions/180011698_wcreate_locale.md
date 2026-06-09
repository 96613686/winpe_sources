# _wcreate_locale

- ea: `0x180011698`
- end: `0x1800117e0`
- name: `_wcreate_locale`
- size: `328`
- prototype: `_locale_t __cdecl(int Category, const wchar_t *Locale)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180011034`

## callees

- `0x180007ee8`
- `0x180007fc0`
- `0x180008040`
- `0x18000aca0`
- `0x18000ffd4`
- `0x1800101d4`
- `0x180010f74`
- `0x180011698`
- `0x180011ad8`

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
0x180011698  mov     rax, rsp
0x18001169b  mov     [rax+8], rbx
0x18001169f  mov     [rax+10h], rbp
0x1800116a3  mov     [rax+18h], rsi
0x1800116a7  mov     [rax+20h], rdi
0x1800116ab  push    r12
0x1800116ad  push    r14
0x1800116af  push    r15
0x1800116b1  sub     rsp, 20h
0x1800116b5  mov     r14, rdx
0x1800116b8  mov     r15d, ecx
0x1800116bb  cmp     ecx, 5
0x1800116be  ja      loc_1800117BF
0x1800116c4  xor     ebp, ebp
0x1800116c6  test    rdx, rdx
0x1800116c9  jz      loc_1800117BF
0x1800116cf  lea     r12d, [rbp+1]
0x1800116d3  mov     ecx, r12d; Count
0x1800116d6  lea     edx, [rbp+10h]; Size
0x1800116d9  call    _calloc_base
0x1800116de  mov     rsi, rax
0x1800116e1  test    rax, rax
0x1800116e4  jnz     short loc_1800116F6
0x1800116e6  call    _errno
0x1800116eb  mov     dword ptr [rax], 0Ch
0x1800116f1  jmp     loc_1800117B2
0x1800116f6  mov     edx, 158h; Size
0x1800116fb  mov     rcx, r12; Count
0x1800116fe  call    _calloc_base
0x180011703  mov     rbx, rax
0x180011706  test    rax, rax
0x180011709  jnz     short loc_18001171B
0x18001170b  call    _errno
0x180011710  mov     dword ptr [rax], 0Ch
0x180011716  jmp     loc_1800117AA
0x18001171b  mov     edx, 228h; Size
0x180011720  mov     rcx, r12; Count
0x180011723  call    _calloc_base
0x180011728  mov     rdi, rax
0x18001172b  test    rax, rax
0x18001172e  jnz     short loc_18001173D
0x180011730  call    _errno
0x180011735  mov     dword ptr [rax], 0Ch
0x18001173b  jmp     short loc_1800117A2
0x18001173d  lea     rdx, __acrt_initial_locale_data
0x180011744  mov     rcx, rbx
0x180011747  call    _copytlocinfo_nolock
0x18001174c  mov     r8, r14
0x18001174f  mov     edx, r15d
0x180011752  mov     rcx, rbx
0x180011755  call    _wsetlocale_nolock
0x18001175a  test    rax, rax
0x18001175d  jz      short loc_18001178F
0x18001175f  mov     ecx, [rbx+0Ch]
0x180011762  mov     rdx, rdi
0x180011765  call    _setmbcp_nolock
0x18001176a  test    eax, eax
0x18001176c  jnz     short loc_18001178F
0x18001176e  mov     rax, rbx
0x180011771  mov     [rdi], r12d
0x180011774  mov     [rsi], rax
0x180011777  mov     rbx, rbp
0x18001177a  mov     rax, rdi
0x18001177d  mov     rdi, rbp
0x180011780  mov     [rsi+8], rax
0x180011784  mov     rax, rsi
0x180011787  mov     rsi, rbp
0x18001178a  mov     rbp, rax
0x18001178d  jmp     short loc_1800117A2
0x18001178f  mov     rcx, rbx
0x180011792  call    __acrt_release_locale_ref
0x180011797  mov     rcx, rbx
0x18001179a  mov     rbx, rbp
0x18001179d  call    __acrt_free_locale
0x1800117a2  mov     rcx, rdi; Block
0x1800117a5  call    _free_base
0x1800117aa  mov     rcx, rbx; Block
0x1800117ad  call    _free_base
0x1800117b2  mov     rcx, rsi; Block
0x1800117b5  call    _free_base
0x1800117ba  mov     rax, rbp
0x1800117bd  jmp     short loc_1800117C1
0x1800117bf  xor     eax, eax
0x1800117c1  mov     rbx, [rsp+38h+arg_0]
0x1800117c6  mov     rbp, [rsp+38h+arg_8]
0x1800117cb  mov     rsi, [rsp+38h+arg_10]
0x1800117d0  mov     rdi, [rsp+38h+arg_18]
0x1800117d5  add     rsp, 20h
0x1800117d9  pop     r15
0x1800117db  pop     r14
0x1800117dd  pop     r12
0x1800117df  retn
```
