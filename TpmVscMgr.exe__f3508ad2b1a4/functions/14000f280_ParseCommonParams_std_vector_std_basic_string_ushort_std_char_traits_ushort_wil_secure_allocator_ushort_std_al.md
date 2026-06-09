# ParseCommonParams(std::vector<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>> &,InputInfo *)

- ea: `0x14000f280`
- end: `0x14000f546`
- name: `?ParseCommonParams@@YA_NAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@2@@std@@PEAVInputInfo@@@Z`
- size: `710`
- prototype: `char __fastcall(__int64, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000ded8`

## callees

- `0x1400016a0`
- `0x14000641c`
- `0x14000d858`
- `0x14000d974`
- `0x14000dab8`
- `0x14000ef04`
- `0x14000f280`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000f2e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000f378`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000f414`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000f2e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000f378`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000f414`

## pseudocode

```c
char __fastcall ParseCommonParams(__int64 a1, _BYTE *a2)
{
  _QWORD *v4; // rdi
  _QWORD *v5; // r14
  __int128 *v6; // rdx
  _QWORD *v7; // rcx
  int v8; // ebx
  _QWORD *v9; // r14
  _QWORD *v10; // r14
  _QWORD *i; // rbx
  _QWORD *j; // rdi
  __int128 *v13; // rdx
  _QWORD *v14; // rcx
  int v15; // ebx
  _QWORD *v16; // r14
  _QWORD *v17; // r14
  _QWORD *k; // rbx
  _QWORD *m; // rdi
  __int128 *v20; // rdx
  _QWORD *v21; // rcx
  int v22; // ebx
  __int128 *v23; // rcx
  _QWORD *v24; // rbx
  _QWORD *v25; // r14
  _QWORD *v26; // r14
  _QWORD *n; // rbx
  __int128 v29; // [rsp+20h] [rbp-30h] BYREF
  __int128 v30; // [rsp+30h] [rbp-20h]

  v4 = *(_QWORD **)a1;
  v5 = *(_QWORD **)(a1 + 8);
  while ( v4 != v5 )
  {
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(
      &v29,
      L"/?");
    v6 = &v29;
    if ( *((_QWORD *)&v30 + 1) > 7u )
      v6 = (__int128 *)v29;
    v7 = v4[3] <= 7u ? v4 : (_QWORD *)*v4;
    v8 = _o__wcsicmp(v7, v6);
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(&v29);
    if ( !v8 )
      break;
    v4 += 4;
  }
  v9 = *(_QWORD **)(a1 + 8);
  if ( v4 != v9 )
  {
    *a2 = 1;
    v10 = *(_QWORD **)(a1 + 8);
    for ( i = v4 + 4; i != v10; i += 4 )
    {
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::operator=(
        v4,
        i);
      v4 += 4;
    }
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(*(_QWORD *)(a1 + 8) - 32LL);
    *(_QWORD *)(a1 + 8) -= 32LL;
    v9 = *(_QWORD **)(a1 + 8);
  }
  for ( j = *(_QWORD **)a1; j != v9; j += 4 )
  {
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(
      &v29,
      L"/quiet");
    v13 = &v29;
    if ( *((_QWORD *)&v30 + 1) > 7u )
      v13 = (__int128 *)v29;
    v14 = j[3] <= 7u ? j : (_QWORD *)*j;
    v15 = _o__wcsicmp(v14, v13);
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(&v29);
    if ( !v15 )
      break;
  }
  v16 = *(_QWORD **)(a1 + 8);
  if ( j != v16 )
  {
    a2[256] = 1;
    v17 = *(_QWORD **)(a1 + 8);
    for ( k = j + 4; k != v17; k += 4 )
    {
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::operator=(
        j,
        k);
      j += 4;
    }
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(*(_QWORD *)(a1 + 8) - 32LL);
    *(_QWORD *)(a1 + 8) -= 32LL;
    v16 = *(_QWORD **)(a1 + 8);
  }
  for ( m = *(_QWORD **)a1; m != v16; m += 4 )
  {
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(
      &v29,
      L"/machine");
    v20 = &v29;
    if ( *((_QWORD *)&v30 + 1) > 7u )
      v20 = (__int128 *)v29;
    v21 = m[3] <= 7u ? m : (_QWORD *)*m;
    v22 = _o__wcsicmp(v21, v20);
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(&v29);
    if ( !v22 )
      break;
  }
  if ( m == *(_QWORD **)(a1 + 8) )
    return 1;
  v23 = (__int128 *)(m + 4);
  if ( m + 4 != *(_QWORD **)(a1 + 8) && m[6] )
  {
    v29 = *v23;
    v30 = *((_OWORD *)m + 3);
    m[6] = 0;
    m[7] = 7;
    *(_WORD *)v23 = 0;
    v24 = m + 8;
    if ( m != m + 8 )
    {
      v25 = *(_QWORD **)(a1 + 8);
      while ( v24 != v25 )
      {
        std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::operator=(
          m,
          v24);
        m += 4;
        v24 += 4;
      }
      v26 = *(_QWORD **)(a1 + 8);
      for ( n = m; n != v26; n += 4 )
        std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(n);
      *(_QWORD *)(a1 + 8) = m;
    }
    if ( a2[296] )
    {
      a2[296] = 0;
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(a2 + 264);
    }
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(
      a2 + 264,
      &v29);
    a2[296] = 1;
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(&v29);
    return 1;
  }
  *(_QWORD *)&v29 = L"/machine";
  *((_QWORD *)&v29 + 1) = L"parameterName";
  *(_QWORD *)&v30 = L"";
  Output::DisplayErrorResource<unsigned short const *>(v23, 422, &v29);
  return 0;
}

```

## disassembly

```asm
0x14000f280  mov     [rsp-28h+arg_10], rbx
0x14000f285  mov     [rsp-28h+arg_18], rsi
0x14000f28a  push    rbp
0x14000f28b  push    rdi
0x14000f28c  push    r13
0x14000f28e  push    r14
0x14000f290  push    r15
0x14000f292  mov     rbp, rsp
0x14000f295  sub     rsp, 50h
0x14000f299  mov     rax, cs:__security_cookie
0x14000f2a0  xor     rax, rsp
0x14000f2a3  mov     [rbp+var_10], rax
0x14000f2a7  mov     r15, rdx
0x14000f2aa  mov     rsi, rcx
0x14000f2ad  mov     rdi, [rcx]
0x14000f2b0  mov     r14, [rcx+8]
0x14000f2b4  jmp     short loc_14000F2FC
0x14000f2b6  lea     rdx, asc_140015300; "/?"
0x14000f2bd  lea     rcx, [rbp+var_30]
0x14000f2c1  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(ushort const * const)
0x14000f2c6  lea     rdx, [rbp+var_30]
0x14000f2ca  cmp     qword ptr [rbp+var_20+8], 7
0x14000f2cf  cmova   rdx, qword ptr [rbp+var_30]
0x14000f2d4  cmp     qword ptr [rdi+18h], 7
0x14000f2d9  jbe     short loc_14000F2E0
0x14000f2db  mov     rcx, [rdi]
0x14000f2de  jmp     short loc_14000F2E3
0x14000f2e0  mov     rcx, rdi
0x14000f2e3  call    cs:__imp__o__wcsicmp
0x14000f2e9  mov     ebx, eax
0x14000f2eb  lea     rcx, [rbp+var_30]
0x14000f2ef  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000f2f4  test    ebx, ebx
0x14000f2f6  jz      short loc_14000F301
0x14000f2f8  add     rdi, 20h ; ' '
0x14000f2fc  cmp     rdi, r14
0x14000f2ff  jnz     short loc_14000F2B6
0x14000f301  mov     r14, [rsi+8]
0x14000f305  cmp     rdi, r14
0x14000f308  jz      short loc_14000F346
0x14000f30a  mov     byte ptr [r15], 1
0x14000f30e  mov     r14, [rsi+8]
0x14000f312  lea     rbx, [rdi+20h]
0x14000f316  jmp     short loc_14000F32B
0x14000f318  mov     rdx, rbx
0x14000f31b  mov     rcx, rdi
0x14000f31e  call    ??4?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::operator=(std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>> &&)
0x14000f323  add     rdi, 20h ; ' '
0x14000f327  add     rbx, 20h ; ' '
0x14000f32b  cmp     rbx, r14
0x14000f32e  jnz     short loc_14000F318
0x14000f330  mov     rcx, [rsi+8]
0x14000f334  sub     rcx, 20h ; ' '
0x14000f338  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000f33d  add     qword ptr [rsi+8], 0FFFFFFFFFFFFFFE0h
0x14000f342  mov     r14, [rsi+8]
0x14000f346  mov     rdi, [rsi]
0x14000f349  jmp     short loc_14000F391
0x14000f34b  lea     rdx, aQuiet; "/quiet"
0x14000f352  lea     rcx, [rbp+var_30]
0x14000f356  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(ushort const * const)
0x14000f35b  lea     rdx, [rbp+var_30]
0x14000f35f  cmp     qword ptr [rbp+var_20+8], 7
0x14000f364  cmova   rdx, qword ptr [rbp+var_30]
0x14000f369  cmp     qword ptr [rdi+18h], 7
0x14000f36e  jbe     short loc_14000F375
0x14000f370  mov     rcx, [rdi]
0x14000f373  jmp     short loc_14000F378
0x14000f375  mov     rcx, rdi
0x14000f378  call    cs:__imp__o__wcsicmp
0x14000f37e  mov     ebx, eax
0x14000f380  lea     rcx, [rbp+var_30]
0x14000f384  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000f389  test    ebx, ebx
0x14000f38b  jz      short loc_14000F396
0x14000f38d  add     rdi, 20h ; ' '
0x14000f391  cmp     rdi, r14
0x14000f394  jnz     short loc_14000F34B
0x14000f396  mov     r14, [rsi+8]
0x14000f39a  cmp     rdi, r14
0x14000f39d  jz      short loc_14000F3DF
0x14000f39f  mov     byte ptr [r15+100h], 1
0x14000f3a7  mov     r14, [rsi+8]
0x14000f3ab  lea     rbx, [rdi+20h]
0x14000f3af  jmp     short loc_14000F3C4
0x14000f3b1  mov     rdx, rbx
0x14000f3b4  mov     rcx, rdi
0x14000f3b7  call    ??4?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::operator=(std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>> &&)
0x14000f3bc  add     rdi, 20h ; ' '
0x14000f3c0  add     rbx, 20h ; ' '
0x14000f3c4  cmp     rbx, r14
0x14000f3c7  jnz     short loc_14000F3B1
0x14000f3c9  mov     rcx, [rsi+8]
0x14000f3cd  sub     rcx, 20h ; ' '
0x14000f3d1  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000f3d6  add     qword ptr [rsi+8], 0FFFFFFFFFFFFFFE0h
0x14000f3db  mov     r14, [rsi+8]
0x14000f3df  mov     rdi, [rsi]
0x14000f3e2  lea     r13, aMachine; "/machine"
0x14000f3e9  jmp     short loc_14000F42D
0x14000f3eb  mov     rdx, r13
0x14000f3ee  lea     rcx, [rbp+var_30]
0x14000f3f2  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(ushort const * const)
0x14000f3f7  lea     rdx, [rbp+var_30]
0x14000f3fb  cmp     qword ptr [rbp+var_20+8], 7
0x14000f400  cmova   rdx, qword ptr [rbp+var_30]
0x14000f405  cmp     qword ptr [rdi+18h], 7
0x14000f40a  jbe     short loc_14000F411
0x14000f40c  mov     rcx, [rdi]
0x14000f40f  jmp     short loc_14000F414
0x14000f411  mov     rcx, rdi
0x14000f414  call    cs:__imp__o__wcsicmp
0x14000f41a  mov     ebx, eax
0x14000f41c  lea     rcx, [rbp+var_30]
0x14000f420  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000f425  test    ebx, ebx
0x14000f427  jz      short loc_14000F432
0x14000f429  add     rdi, 20h ; ' '
0x14000f42d  cmp     rdi, r14
0x14000f430  jnz     short loc_14000F3EB
0x14000f432  cmp     rdi, [rsi+8]
0x14000f436  jz      loc_14000F4F3
0x14000f43c  lea     rcx, [rdi+20h]
0x14000f440  cmp     rcx, [rsi+8]
0x14000f444  jz      loc_14000F4F7
0x14000f44a  cmp     qword ptr [rcx+10h], 0
0x14000f44f  jz      loc_14000F4F7
0x14000f455  movups  xmm0, xmmword ptr [rcx]
0x14000f458  movups  [rbp+var_30], xmm0
0x14000f45c  movups  xmm1, xmmword ptr [rcx+10h]
0x14000f460  movups  [rbp+var_20], xmm1
0x14000f464  mov     qword ptr [rcx+10h], 0
0x14000f46c  mov     qword ptr [rcx+18h], 7
0x14000f474  xor     eax, eax
0x14000f476  mov     [rcx], ax
0x14000f479  lea     rbx, [rcx+20h]
0x14000f47d  cmp     rdi, rbx
0x14000f480  jz      short loc_14000F4C1
0x14000f482  mov     r14, [rsi+8]
0x14000f486  jmp     short loc_14000F49B
0x14000f488  mov     rdx, rbx
0x14000f48b  mov     rcx, rdi
0x14000f48e  call    ??4?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::operator=(std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>> &&)
0x14000f493  add     rdi, 20h ; ' '
0x14000f497  add     rbx, 20h ; ' '
0x14000f49b  cmp     rbx, r14
0x14000f49e  jnz     short loc_14000F488
0x14000f4a0  mov     r14, [rsi+8]
0x14000f4a4  mov     rbx, rdi
0x14000f4a7  cmp     rdi, r14
0x14000f4aa  jz      short loc_14000F4BD
0x14000f4ac  mov     rcx, rbx
0x14000f4af  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000f4b4  add     rbx, 20h ; ' '
0x14000f4b8  cmp     rbx, r14
0x14000f4bb  jnz     short loc_14000F4AC
0x14000f4bd  mov     [rsi+8], rdi
0x14000f4c1  lea     rbx, [r15+108h]
0x14000f4c8  cmp     byte ptr [rbx+20h], 0
0x14000f4cc  jz      short loc_14000F4DA
0x14000f4ce  mov     byte ptr [rbx+20h], 0
0x14000f4d2  mov     rcx, rbx
0x14000f4d5  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000f4da  lea     rdx, [rbp+var_30]
0x14000f4de  mov     rcx, rbx
0x14000f4e1  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@AEBV01@@Z; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>> const &)
0x14000f4e6  mov     byte ptr [rbx+20h], 1
0x14000f4ea  lea     rcx, [rbp+var_30]
0x14000f4ee  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000f4f3  mov     al, 1
0x14000f4f5  jmp     short loc_14000F521
0x14000f4f7  mov     qword ptr [rbp+var_30], r13
0x14000f4fb  lea     rax, aParametername; "parameterName"
0x14000f502  mov     qword ptr [rbp+var_30+8], rax
0x14000f506  lea     rax, aParametername+1Ah; ""
0x14000f50d  mov     qword ptr [rbp+var_20], rax
0x14000f511  lea     r8, [rbp+var_30]
0x14000f515  mov     edx, 1A6h
0x14000f51a  call    ??$DisplayErrorResource@PEBG@Output@@QEBAXHAEBV?$tuple@V?$range@PEBG@rangelib@@PEBG@std@@@Z; Output::DisplayErrorResource<ushort const *>(int,std::tuple<rangelib::range<ushort const *>,ushort const *> const &)
0x14000f51f  xor     al, al
0x14000f521  mov     rcx, [rbp+var_10]
0x14000f525  xor     rcx, rsp; StackCookie
0x14000f528  call    __security_check_cookie
0x14000f52d  lea     r11, [rsp+50h+var_s0]
0x14000f532  mov     rbx, [r11+40h]
0x14000f536  mov     rsi, [r11+48h]
0x14000f53a  mov     rsp, r11
0x14000f53d  pop     r15
0x14000f53f  pop     r14
0x14000f541  pop     r13
0x14000f543  pop     rdi
0x14000f544  pop     rbp
0x14000f545  retn
```
