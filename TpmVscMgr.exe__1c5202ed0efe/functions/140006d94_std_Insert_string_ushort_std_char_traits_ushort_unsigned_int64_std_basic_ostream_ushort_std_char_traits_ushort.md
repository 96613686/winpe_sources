# std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort,std::char_traits<ushort>> &,ushort const * const,unsigned __int64)

- ea: `0x140006d94`
- end: `0x140006f12`
- name: `??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z`
- size: `382`
- prototype: `__int64 *__fastcall(__int64 *, __int64, unsigned __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14000641c`
- `0x140008784`
- `0x14000b5b4`
- `0x14000e510`
- `0x14000e62c`
- `0x14000eb60`
- `0x14000f54c`

## callees

- `0x140006d94`
- `0x140007f94`
- `0x140013010`

## import_xrefs

- `msvcp_win!?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z` at `0x140006e8e`
- `msvcp_win!?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z` at `0x140006e8e`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x140006e27`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x140006e52`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x140006e27`
- `msvcp_win!?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x140006e52`
- `msvcp_win!?uncaught_exception@std@@YA_NXZ` at `0x140006ec4`
- `msvcp_win!?uncaught_exception@std@@YA_NXZ` at `0x140006ec4`
- `msvcp_win!?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ` at `0x140006ed3`
- `msvcp_win!?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ` at `0x140006ed3`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140006ebd`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140006ebd`

## pseudocode

```c
__int64 *__fastcall std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(
        __int64 *a1,
        __int64 a2,
        unsigned __int64 a3)
{
  unsigned int v6; // edi
  __int64 v7; // rsi
  unsigned __int64 v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-38h] BYREF
  char v13; // [rsp+28h] [rbp-30h]

  v6 = 0;
  v7 = *(__int64 *)((char *)a1 + *(int *)(*a1 + 4) + 40);
  if ( v7 <= 0 || v7 <= a3 )
    v8 = 0;
  else
    v8 = v7 - a3;
  std::basic_ostream<unsigned short>::sentry::sentry(&v12, a1);
  if ( v13 )
  {
    v9 = *a1;
    if ( (*(_DWORD *)((_BYTE *)a1 + *(int *)(*a1 + 4) + 24) & 0x1C0) != 0x40 )
    {
      while ( v8 )
      {
        if ( (unsigned __int16)std::basic_streambuf<unsigned short>::sputc(
                                 *(__int64 *)((char *)a1 + *(int *)(*a1 + 4) + 72),
                                 *(unsigned __int16 *)((char *)a1 + *(int *)(*a1 + 4) + 88)) == 0xFFFF )
        {
          v6 = 4;
          goto LABEL_11;
        }
        --v8;
      }
      v9 = *a1;
    }
    if ( std::basic_streambuf<unsigned short>::sputn(*(__int64 *)((char *)a1 + *(int *)(v9 + 4) + 72), a2, a3) == a3 )
    {
LABEL_11:
      while ( v8 )
      {
        if ( (unsigned __int16)std::basic_streambuf<unsigned short>::sputc(
                                 *(__int64 *)((char *)a1 + *(int *)(*a1 + 4) + 72),
                                 *(unsigned __int16 *)((char *)a1 + *(int *)(*a1 + 4) + 88)) == 0xFFFF )
        {
          v6 |= 4u;
          break;
        }
        --v8;
      }
    }
    else
    {
      v6 = 4;
    }
    *(__int64 *)((char *)a1 + *(int *)(*a1 + 4) + 40) = 0;
  }
  else
  {
    v6 = 4;
  }
  std::basic_ios<unsigned short>::setstate((char *)a1 + *(int *)(*a1 + 4), v6, 0);
  if ( !std::uncaught_exception() )
    std::basic_ostream<unsigned short>::_Osfx(v12);
  v10 = *(_QWORD *)(*(int *)(*(_QWORD *)v12 + 4LL) + v12 + 72);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return a1;
}

```

## disassembly

```asm
0x140006d94  mov     [rsp+arg_8], rbx
0x140006d99  mov     [rsp+arg_0], rcx
0x140006d9e  push    rsi
0x140006d9f  push    rdi
0x140006da0  push    r12
0x140006da2  push    r14
0x140006da4  push    r15
0x140006da6  sub     rsp, 30h
0x140006daa  mov     r14, r8
0x140006dad  mov     r12, rdx
0x140006db0  mov     rbx, rcx
0x140006db3  xor     edi, edi
0x140006db5  mov     [rsp+58h+arg_18], edi
0x140006db9  mov     rax, [rcx]
0x140006dbc  movsxd  r9, dword ptr [rax+4]
0x140006dc0  mov     rsi, [r9+rcx+28h]
0x140006dc5  test    rsi, rsi
0x140006dc8  jle     short loc_140006DD4
0x140006dca  cmp     rsi, r8
0x140006dcd  jbe     short loc_140006DD4
0x140006dcf  sub     rsi, r8
0x140006dd2  jmp     short loc_140006DD6
0x140006dd4  xor     esi, esi
0x140006dd6  mov     rdx, rbx
0x140006dd9  lea     rcx, [rsp+58h+var_38]
0x140006dde  call    ??0sentry@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@AEAV12@@Z; std::basic_ostream<ushort>::sentry::sentry(std::basic_ostream<ushort> &)
0x140006de3  nop
0x140006de4  cmp     [rsp+58h+var_30], 0
0x140006de9  jnz     short loc_140006DF5
0x140006deb  mov     edi, 4
0x140006df0  jmp     loc_140006EAE
0x140006df5  mov     rdx, [rbx]
0x140006df8  movsxd  rax, dword ptr [rdx+4]
0x140006dfc  mov     ecx, [rax+rbx+18h]
0x140006e00  and     ecx, 1C0h
0x140006e06  mov     r15d, 0FFFFh
0x140006e0c  cmp     ecx, 40h ; '@'
0x140006e0f  jz      short loc_140006E7F
0x140006e11  test    rsi, rsi
0x140006e14  jz      short loc_140006E7C
0x140006e16  mov     rax, [rbx]
0x140006e19  movsxd  rcx, dword ptr [rax+4]
0x140006e1d  movzx   edx, word ptr [rcx+rbx+58h]
0x140006e22  mov     rcx, [rcx+rbx+48h]
0x140006e27  call    cs:__imp_?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_streambuf<ushort>::sputc(ushort)
0x140006e2d  cmp     r15w, ax
0x140006e31  jnz     short loc_140006E77
0x140006e33  mov     edi, 4
0x140006e38  mov     [rsp+58h+arg_18], edi
0x140006e3c  test    rsi, rsi
0x140006e3f  jz      short loc_140006E65
0x140006e41  mov     rax, [rbx]
0x140006e44  movsxd  rcx, dword ptr [rax+4]
0x140006e48  movzx   edx, word ptr [rcx+rbx+58h]
0x140006e4d  mov     rcx, [rcx+rbx+48h]
0x140006e52  call    cs:__imp_?sputc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_streambuf<ushort>::sputc(ushort)
0x140006e58  cmp     r15w, ax
0x140006e5c  jnz     short loc_140006EA0
0x140006e5e  or      edi, 4
0x140006e61  mov     [rsp+58h+arg_18], edi
0x140006e65  mov     rax, [rbx]
0x140006e68  movsxd  rcx, dword ptr [rax+4]
0x140006e6c  mov     qword ptr [rcx+rbx+28h], 0
0x140006e75  jmp     short loc_140006EAE
0x140006e77  dec     rsi
0x140006e7a  jmp     short loc_140006E11
0x140006e7c  mov     rdx, [rbx]
0x140006e7f  movsxd  rcx, dword ptr [rdx+4]
0x140006e83  mov     r8, r14
0x140006e86  mov     rdx, r12
0x140006e89  mov     rcx, [rcx+rbx+48h]
0x140006e8e  call    cs:__imp_?sputn@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEAA_JPEBG_J@Z; std::basic_streambuf<ushort>::sputn(ushort const *,__int64)
0x140006e94  cmp     rax, r14
0x140006e97  jz      short loc_140006E3C
0x140006e99  mov     edi, 4
0x140006e9e  jmp     short loc_140006E61
0x140006ea0  dec     rsi
0x140006ea3  jmp     short loc_140006E3C
0x140006ea5  mov     rbx, [rsp+58h+arg_0]
0x140006eaa  mov     edi, [rsp+58h+arg_18]
0x140006eae  mov     rax, [rbx]
0x140006eb1  movsxd  rcx, dword ptr [rax+4]
0x140006eb5  add     rcx, rbx
0x140006eb8  xor     r8d, r8d
0x140006ebb  mov     edx, edi
0x140006ebd  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x140006ec3  nop
0x140006ec4  call    cs:__imp_?uncaught_exception@std@@YA_NXZ; std::uncaught_exception(void)
0x140006eca  test    al, al
0x140006ecc  jnz     short loc_140006EDA
0x140006ece  mov     rcx, [rsp+58h+var_38]
0x140006ed3  call    cs:__imp_?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ostream<ushort>::_Osfx(void)
0x140006ed9  nop
0x140006eda  mov     rdx, [rsp+58h+var_38]
0x140006edf  mov     rax, [rdx]
0x140006ee2  movsxd  rcx, dword ptr [rax+4]
0x140006ee6  mov     rcx, [rcx+rdx+48h]
0x140006eeb  test    rcx, rcx
0x140006eee  jz      short loc_140006EFD
0x140006ef0  mov     rax, [rcx]
0x140006ef3  mov     rax, [rax+10h]
0x140006ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006efc  nop
0x140006efd  mov     rax, rbx
0x140006f00  mov     rbx, [rsp+58h+arg_8]
0x140006f05  add     rsp, 30h
0x140006f09  pop     r15
0x140006f0b  pop     r14
0x140006f0d  pop     r12
0x140006f0f  pop     rdi
0x140006f10  pop     rsi
0x140006f11  retn
```
