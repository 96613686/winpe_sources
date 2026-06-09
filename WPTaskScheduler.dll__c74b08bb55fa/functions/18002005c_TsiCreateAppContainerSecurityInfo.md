# TsiCreateAppContainerSecurityInfo

- ea: `0x18002005c`
- end: `0x18002019f`
- name: `TsiCreateAppContainerSecurityInfo`
- size: `323`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001ff70`

## callees

- `0x180005400`
- `0x180010094`
- `0x180010208`
- `0x18002005c`
- `0x1800201a8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002011d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002011d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180020114`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180020114`

## pseudocode

```c
__int64 __fastcall TsiCreateAppContainerSecurityInfo(_QWORD *a1, __int64 a2)
{
  void *v5; // rbx
  int UserSid; // edi
  unsigned __int64 v7; // rax
  unsigned int i; // esi
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // kr00_8
  _DWORD *v11; // rax
  _DWORD *v12; // rbp
  __int64 v13; // r15
  unsigned int j; // esi

  if ( !a2 )
    return 0;
  if ( !a1 )
    return 2147500035LL;
  v5 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
    return 2147942414LL;
  *(_OWORD *)v5 = 0;
  *((_QWORD *)v5 + 2) = 0;
  UserSid = TsiCreateUserSid(v5, *(_QWORD *)a2);
  if ( UserSid < 0 )
    goto LABEL_11;
  v7 = *(unsigned int *)(a2 + 16);
  *((_DWORD *)v5 + 4) = v7;
  if ( (_DWORD)v7 )
  {
    if ( !*(_QWORD *)(a2 + 8) )
    {
      UserSid = -2147467259;
LABEL_11:
      TsiFreeScheduleSid(*(void ***)v5);
      if ( *((_QWORD *)v5 + 1) )
      {
        for ( i = 0; i < *((_DWORD *)v5 + 4); ++i )
          TsiFreeScheduleSid(*(void ***)(*((_QWORD *)v5 + 1) + 16LL * i));
        operator delete[](*((void **)v5 + 1));
      }
      operator delete(v5);
      return (unsigned int)UserSid;
    }
    v10 = v7;
    v9 = 16 * v7;
    if ( !is_mul_ok(v10, 0x10u) )
      v9 = -1;
    v11 = operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
    *((_QWORD *)v5 + 1) = v11;
    v12 = v11;
    if ( !v11 )
    {
      UserSid = -2147024882;
      goto LABEL_11;
    }
    v13 = *(_QWORD *)(a2 + 8);
    for ( j = 0; j < *((_DWORD *)v5 + 4); ++j )
    {
      v12[2] = *(_DWORD *)(v13 + 8);
      UserSid = TsiCreateUserSid(v12, *(_QWORD *)v13);
      if ( UserSid < 0 )
        goto LABEL_11;
    }
  }
  *a1 = v5;
  return 0;
}

```

## disassembly

```asm
0x18002005c  push    rbx
0x18002005e  push    rbp
0x18002005f  push    rsi
0x180020060  push    rdi
0x180020061  push    r14
0x180020063  push    r15
0x180020065  sub     rsp, 28h
0x180020069  mov     rsi, rdx
0x18002006c  mov     r14, rcx
0x18002006f  test    rdx, rdx
0x180020072  jnz     short loc_18002007B
0x180020074  xor     eax, eax
0x180020076  jmp     loc_180020125
0x18002007b  test    r14, r14
0x18002007e  jnz     short loc_18002008A
0x180020080  mov     eax, 80004003h
0x180020085  jmp     loc_180020125
0x18002008a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020091  mov     ecx, 18h; unsigned __int64
0x180020096  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002009b  mov     rbx, rax
0x18002009e  test    rax, rax
0x1800200a1  jnz     short loc_1800200AA
0x1800200a3  mov     eax, 8007000Eh
0x1800200a8  jmp     short loc_180020125
0x1800200aa  xorps   xmm0, xmm0
0x1800200ad  xor     eax, eax
0x1800200af  movups  xmmword ptr [rbx], xmm0
0x1800200b2  mov     [rbx+10h], rax
0x1800200b6  mov     rcx, rbx
0x1800200b9  mov     rdx, [rsi]
0x1800200bc  call    TsiCreateUserSid
0x1800200c1  mov     edi, eax
0x1800200c3  test    eax, eax
0x1800200c5  js      short loc_1800200E1
0x1800200c7  mov     eax, [rsi+10h]
0x1800200ca  mov     [rbx+10h], eax
0x1800200cd  test    eax, eax
0x1800200cf  jz      loc_180020198
0x1800200d5  cmp     qword ptr [rsi+8], 0
0x1800200da  jnz     short loc_180020132
0x1800200dc  mov     edi, 80004005h
0x1800200e1  mov     rcx, [rbx]; struct _SCHEDULE_SID *
0x1800200e4  call    ?TsiFreeScheduleSid@@YAJPEAU_SCHEDULE_SID@@@Z; TsiFreeScheduleSid(_SCHEDULE_SID *)
0x1800200e9  cmp     qword ptr [rbx+8], 0
0x1800200ee  jz      short loc_18002011A
0x1800200f0  xor     esi, esi
0x1800200f2  cmp     [rbx+10h], esi
0x1800200f5  jbe     short loc_180020110
0x1800200f7  mov     rcx, [rbx+8]
0x1800200fb  mov     eax, esi
0x1800200fd  add     rax, rax
0x180020100  mov     rcx, [rcx+rax*8]; struct _SCHEDULE_SID *
0x180020104  call    ?TsiFreeScheduleSid@@YAJPEAU_SCHEDULE_SID@@@Z; TsiFreeScheduleSid(_SCHEDULE_SID *)
0x180020109  inc     esi
0x18002010b  cmp     esi, [rbx+10h]
0x18002010e  jb      short loc_1800200F7
0x180020110  mov     rcx, [rbx+8]
0x180020114  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002011a  mov     rcx, rbx
0x18002011d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020123  mov     eax, edi
0x180020125  add     rsp, 28h
0x180020129  pop     r15
0x18002012b  pop     r14
0x18002012d  pop     rdi
0x18002012e  pop     rsi
0x18002012f  pop     rbp
0x180020130  pop     rbx
0x180020131  retn
0x180020132  mov     rcx, rax
0x180020135  mov     eax, 10h
0x18002013a  mul     rcx
0x18002013d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180020144  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002014b  cmovb   rax, rcx
0x18002014f  mov     rcx, rax; unsigned __int64
0x180020152  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180020157  mov     [rbx+8], rax
0x18002015b  mov     rbp, rax
0x18002015e  test    rax, rax
0x180020161  jnz     short loc_18002016D
0x180020163  mov     edi, 8007000Eh
0x180020168  jmp     loc_1800200E1
0x18002016d  mov     r15, [rsi+8]
0x180020171  xor     esi, esi
0x180020173  cmp     esi, [rbx+10h]
0x180020176  jnb     short loc_180020198
0x180020178  mov     eax, [r15+8]
0x18002017c  mov     rcx, rbp
0x18002017f  mov     [rbp+8], eax
0x180020182  mov     rdx, [r15]
0x180020185  call    TsiCreateUserSid
0x18002018a  mov     edi, eax
0x18002018c  test    eax, eax
0x18002018e  js      loc_1800200E1
0x180020194  inc     esi
0x180020196  jmp     short loc_180020173
0x180020198  mov     [r14], rbx
0x18002019b  xor     edi, edi
0x18002019d  jmp     short loc_180020123
```
