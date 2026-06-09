# Microsoft::Windows::Autopilot::JsonHelpers::RemoveTrailingNulls(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x18001f2dc`
- end: `0x18001f439`
- name: `?RemoveTrailingNulls@JsonHelpers@Autopilot@Windows@Microsoft@@SAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001f440`

## callees

- `0x1800045d4`
- `0x1800049f4`
- `0x180009740`
- `0x18000994b`
- `0x180009957`
- `0x180013908`
- `0x18001f2dc`
- `0x18001f788`

## pseudocode

```c
void __fastcall Microsoft::Windows::Autopilot::JsonHelpers::RemoveTrailingNulls(const void **a1)
{
  bool v1; // cc
  char *v3; // rax
  char *v4; // rcx
  char *v5; // rsi
  char *v6; // rdx
  char *v7; // rcx
  __int64 trivial_1; // rax
  char *v9; // rcx
  char *v10; // rsi
  __int64 v11; // r9
  unsigned __int64 v12; // rdx
  char *v13; // rax
  unsigned __int64 v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned __int64 v18; // rdi
  size_t v19; // rcx
  char *v20; // rax
  char *v21; // rsi
  char *v22; // rcx
  _BYTE *v23; // rax

  v1 = (unsigned __int64)a1[3] <= 0xF;
  if ( (unsigned __int64)a1[3] <= 0xF )
    v3 = (char *)a1;
  else
    v3 = (char *)*a1;
  v4 = (char *)a1[2];
  v5 = &v3[(_QWORD)v4];
  if ( v1 )
  {
    v6 = (char *)a1 + (_QWORD)v4;
    v7 = (char *)a1;
  }
  else
  {
    v6 = (char *)*a1 + (_QWORD)v4;
    v7 = (char *)*a1;
  }
  trivial_1 = _std_find_trivial_1(v7, v6, 0);
  if ( (unsigned __int64)a1[3] <= 0xF )
    v9 = (char *)a1;
  else
    v9 = (char *)*a1;
  v10 = &v5[-trivial_1];
  v11 = trivial_1 - (_QWORD)v9;
  v12 = (unsigned __int64)a1[2] - (trivial_1 - (_QWORD)v9);
  if ( v12 >= (unsigned __int64)v10 )
    v12 = (unsigned __int64)v10;
  if ( (unsigned __int64)a1[3] <= 0xF )
    v13 = (char *)a1;
  else
    v13 = (char *)*a1;
  v14 = (unsigned __int64)a1[2] - v12;
  memmove_0(&v13[v11], &v13[v11 + v12], v14 - v11 + 1);
  a1[2] = (const void *)v14;
  if ( (unsigned __int64)a1[3] > 0xF )
  {
    if ( v14 > 0xF )
    {
      v18 = v14 | 0xF;
      if ( v18 > 0x7FFFFFFFFFFFFFFFLL )
        v18 = 0x7FFFFFFFFFFFFFFFLL;
      if ( v18 < (unsigned __int64)a1[3] )
      {
        v19 = v18 + 1;
        if ( v18 + 1 < 0x1000 )
          v20 = (char *)operator new(v19);
        else
          v20 = (char *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v19, v15, v16, v17);
        v21 = v20;
        memcpy_0(v20, *a1, (size_t)a1[2] + 1);
        v22 = (char *)*a1;
        if ( (unsigned __int64)a1[3] + 1 < 0x1000 )
        {
          v23 = *a1;
        }
        else
        {
          v23 = (_BYTE *)*((_QWORD *)v22 - 1);
          if ( (unsigned __int64)(v22 - v23 - 8) > 0x1F )
            __fastfail(5u);
        }
        operator delete(v23);
        *a1 = v21;
        a1[3] = (const void *)v18;
      }
    }
    else
    {
      std::string::_Become_small(a1);
    }
  }
}

```

## disassembly

```asm
0x18001f2dc  mov     [rsp+arg_0], rbx
0x18001f2e1  mov     [rsp+arg_8], rsi
0x18001f2e6  push    rdi
0x18001f2e7  sub     rsp, 20h
0x18001f2eb  cmp     qword ptr [rcx+18h], 0Fh
0x18001f2f0  mov     rbx, rcx
0x18001f2f3  jbe     short loc_18001F2FA
0x18001f2f5  mov     rax, [rcx]
0x18001f2f8  jmp     short loc_18001F2FD
0x18001f2fa  mov     rax, rbx
0x18001f2fd  mov     rcx, [rcx+10h]
0x18001f301  lea     rsi, [rcx+rax]
0x18001f305  ja      short loc_18001F310
0x18001f307  lea     rdx, [rcx+rbx]
0x18001f30b  mov     rcx, rbx
0x18001f30e  jmp     short loc_18001F31A
0x18001f310  mov     rax, [rbx]
0x18001f313  lea     rdx, [rcx+rax]
0x18001f317  mov     rcx, rax
0x18001f31a  xor     r8d, r8d
0x18001f31d  call    __std_find_trivial_1
0x18001f322  cmp     qword ptr [rbx+18h], 0Fh
0x18001f327  jbe     short loc_18001F32E
0x18001f329  mov     rcx, [rbx]
0x18001f32c  jmp     short loc_18001F331
0x18001f32e  mov     rcx, rbx
0x18001f331  mov     rdi, [rbx+10h]
0x18001f335  sub     rsi, rax
0x18001f338  mov     r9, rax
0x18001f33b  mov     rdx, rdi
0x18001f33e  sub     r9, rcx
0x18001f341  sub     rdx, r9
0x18001f344  cmp     rdx, rsi
0x18001f347  cmovnb  rdx, rsi
0x18001f34b  cmp     qword ptr [rbx+18h], 0Fh
0x18001f350  jbe     short loc_18001F357
0x18001f352  mov     rax, [rbx]
0x18001f355  jmp     short loc_18001F35A
0x18001f357  mov     rax, rbx
0x18001f35a  sub     rdi, rdx
0x18001f35d  lea     rcx, [r9+rax]; void *
0x18001f361  mov     r8, rdi
0x18001f364  add     rdx, rcx; Src
0x18001f367  sub     r8, r9
0x18001f36a  inc     r8; Size
0x18001f36d  call    memmove_0
0x18001f372  mov     [rbx+10h], rdi
0x18001f376  cmp     qword ptr [rbx+18h], 0Fh
0x18001f37b  jbe     loc_18001F429
0x18001f381  cmp     rdi, 0Fh
0x18001f385  ja      short loc_18001F394
0x18001f387  mov     rcx, rbx
0x18001f38a  call    ?_Become_small@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Become_small(void)
0x18001f38f  jmp     loc_18001F429
0x18001f394  or      rdi, 0Fh
0x18001f398  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001f3a2  cmp     rdi, rax
0x18001f3a5  cmova   rdi, rax
0x18001f3a9  cmp     rdi, [rbx+18h]
0x18001f3ad  jnb     short loc_18001F429
0x18001f3af  lea     rcx, [rdi+1]; Size
0x18001f3b3  test    rcx, rcx
0x18001f3b6  jnz     short loc_18001F3BC
0x18001f3b8  xor     esi, esi
0x18001f3ba  jmp     short loc_18001F3D4
0x18001f3bc  cmp     rcx, 1000h
0x18001f3c3  jb      short loc_18001F3CC
0x18001f3c5  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x18001f3ca  jmp     short loc_18001F3D1
0x18001f3cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f3d1  mov     rsi, rax
0x18001f3d4  mov     r8, [rbx+10h]
0x18001f3d8  mov     rcx, rsi; void *
0x18001f3db  mov     rdx, [rbx]; Src
0x18001f3de  inc     r8; Size
0x18001f3e1  call    memcpy_0
0x18001f3e6  mov     rdx, [rbx+18h]
0x18001f3ea  mov     rcx, [rbx]
0x18001f3ed  inc     rdx
0x18001f3f0  cmp     rdx, 1000h
0x18001f3f7  jb      short loc_18001F417
0x18001f3f9  mov     rax, [rcx-8]
0x18001f3fd  sub     rcx, rax
0x18001f400  sub     rcx, 8
0x18001f404  cmp     rcx, 1Fh
0x18001f408  ja      short loc_18001F410
0x18001f40a  add     rdx, 27h ; '''
0x18001f40e  jmp     short loc_18001F41A
0x18001f410  mov     ecx, 5
0x18001f415  int     29h; Win8: RtlFailFast(ecx)
0x18001f417  mov     rax, rcx
0x18001f41a  mov     rcx, rax; Block
0x18001f41d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f422  mov     [rbx], rsi
0x18001f425  mov     [rbx+18h], rdi
0x18001f429  mov     rbx, [rsp+28h+arg_0]
0x18001f42e  mov     rsi, [rsp+28h+arg_8]
0x18001f433  add     rsp, 20h
0x18001f437  pop     rdi
0x18001f438  retn
```
