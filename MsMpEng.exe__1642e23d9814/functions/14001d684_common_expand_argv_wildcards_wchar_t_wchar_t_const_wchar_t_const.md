# common_expand_argv_wildcards<wchar_t>(wchar_t * * const,wchar_t * * * const)

- ea: `0x14001d684`
- end: `0x14001da81`
- name: `??$common_expand_argv_wildcards@_W@@YAHQEAPEA_WQEAPEAPEA_W@Z`
- size: `1021`
- prototype: `__int64 __fastcall(const WCHAR **, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14001dc0c`

## callees

- `0x14000a640`
- `0x14001609c`
- `0x1400160bc`
- `0x140016ea0`
- `0x140017ea8`
- `0x140019930`
- `0x14001d520`
- `0x14001d684`
- `0x14001da84`
- `0x14001eab0`
- `0x140022b90`
- `0x14002a310`

## import_xrefs

- `KERNEL32!FindNextFileW` at `0x14001d875`
- `KERNEL32!FindNextFileW` at `0x14001d875`
- `KERNEL32!FindFirstFileExW` at `0x14001d7ec`
- `KERNEL32!FindFirstFileExW` at `0x14001d7ec`
- `KERNEL32!FindClose` at `0x14001d8b2`
- `KERNEL32!FindClose` at `0x14001d8f0`
- `KERNEL32!FindClose` at `0x14001d8b2`
- `KERNEL32!FindClose` at `0x14001d8f0`

## pseudocode

```c
__int64 __fastcall common_expand_argv_wildcards<wchar_t>(const WCHAR **a1, __int64 *a2)
{
  const WCHAR **v2; // r15
  const WCHAR *v4; // rax
  __int128 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  const WCHAR *v8; // r14
  const WCHAR *v9; // rcx
  int v10; // eax
  unsigned __int16 v11; // ax
  unsigned __int16 v12; // dx
  char v13; // al
  __int64 v14; // r13
  HANDLE FirstFile; // rbx
  __int64 v16; // r12
  signed __int64 v17; // rdx
  void **j; // rbx
  void **i; // rbx
  __int64 v20; // r13
  _QWORD *k; // rax
  __int64 v22; // rcx
  __int64 buffer_for_argv; // rax
  __int64 v24; // rbx
  void **m; // rbx
  __int64 v26; // rcx
  __int64 *v27; // r14
  __int64 v28; // r12
  __int64 v29; // r8
  __int64 v30; // r15
  __int64 v31; // r15
  void **n; // rbx
  void *Block[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v34; // [rsp+40h] [rbp-C0h]
  __int64 v35; // [rsp+48h] [rbp-B8h]
  __int64 *v36; // [rsp+50h] [rbp-B0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+2B0h] [rbp+1B0h] BYREF

  v36 = a2;
  v2 = a1;
  if ( a2 )
  {
    *a2 = 0;
    v4 = *a1;
    *(_OWORD *)Block = 0;
    v5 = 0;
    v34 = 0;
    while ( v4 )
    {
      LODWORD(v38) = 4128810;
      WORD2(v38) = 0;
      v6 = 0x200000000801LL;
      v7 = sub_14001EAB0(v4, &v38);
      v8 = *v2;
      v9 = (const WCHAR *)v7;
      if ( v7 )
      {
        if ( (const WCHAR *)v7 != v8 )
        {
          do
          {
            v11 = *v9 - 47;
            if ( v11 <= 0x2Du && _bittest64(&v6, v11) )
              break;
            --v9;
          }
          while ( v9 != v8 );
        }
        if ( *v9 == 58 && v9 != v8 + 1 )
          goto LABEL_18;
        v12 = *v9 - 47;
        if ( v12 > 0x2Du || (v13 = 1, !_bittest64(&v6, v12)) )
          v13 = 0;
        v14 = (v9 - v8 + 1) & -(__int64)(v13 != 0);
        sub_14002A310(&FindFileData, 0, 592);
        FirstFile = FindFirstFileExW(v8, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 0);
        if ( FirstFile == (HANDLE)-1LL )
        {
LABEL_18:
          DWORD2(v5) = copy_and_add_argument_to_buffer<wchar_t>(v8, 0, 0, Block);
          if ( DWORD2(v5) )
          {
LABEL_35:
            *(void **)&v5 = Block[0];
            for ( i = (void **)Block[0]; i != Block[1]; ++i )
              free_base(*i);
            goto LABEL_46;
          }
          v5 = *(_OWORD *)Block;
        }
        else
        {
          v16 = (__int64)(*((_QWORD *)&v5 + 1) - v5) >> 3;
          do
          {
            if ( FindFileData.cFileName[0] != 46
              || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
            {
              DWORD2(v5) = copy_and_add_argument_to_buffer<wchar_t>(FindFileData.cFileName, v8, v14, Block);
              if ( DWORD2(v5) )
              {
                FindClose(FirstFile);
                goto LABEL_35;
              }
            }
          }
          while ( FindNextFileW(FirstFile, &FindFileData) );
          v5 = *(_OWORD *)Block;
          v17 = ((char *)Block[1] - (char *)Block[0]) >> 3;
          if ( v16 != v17 )
            sub_140022B90((char *)Block[0] + 8 * v16, v17 - v16, 8, unknown_libname_46);
          FindClose(FirstFile);
        }
      }
      else
      {
        v10 = copy_and_add_argument_to_buffer<wchar_t>(*v2, 0, 0, Block);
        *(void **)&v5 = Block[0];
        DWORD2(v5) = v10;
        if ( v10 )
        {
          for ( j = (void **)Block[0]; j != Block[1]; ++j )
            free_base(*j);
LABEL_46:
          free_base((void *)v5);
          return DWORD2(v5);
        }
        *((void **)&v5 + 1) = Block[1];
      }
      v4 = *++v2;
    }
    v20 = 0;
    for ( k = (_QWORD *)v5; k != *((_QWORD **)&v5 + 1); v20 += v22 + 1 )
    {
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(*k + 2 * v22) );
      ++k;
    }
    buffer_for_argv = _acrt_allocate_buffer_for_argv(((__int64)(*((_QWORD *)&v5 + 1) - v5) >> 3) + 1, v20, 2);
    v24 = buffer_for_argv;
    if ( !buffer_for_argv )
    {
      free_base(0);
      for ( m = (void **)v5; m != *((void ***)&v5 + 1); ++m )
        free_base(*m);
      DWORD2(v5) = -1;
      goto LABEL_46;
    }
    v26 = buffer_for_argv + 8 * (((__int64)(*((_QWORD *)&v5 + 1) - v5) >> 3) + 1);
    v27 = (__int64 *)v5;
    v35 = v26;
    v28 = v26;
    if ( (_QWORD)v5 != *((_QWORD *)&v5 + 1) )
    {
      v38 = buffer_for_argv - v5;
      do
      {
        v29 = *v27;
        v30 = -1;
        do
          ++v30;
        while ( *(_WORD *)(v29 + 2 * v30) );
        v31 = v30 + 1;
        if ( (unsigned int)sub_14001D520(v28, v20 - ((v28 - v26) >> 1), v29, v31) )
          invoke_watson(0, 0, 0, 0, 0);
        v26 = v35;
        *(__int64 *)((char *)v27++ + v38) = v28;
        v28 += 2 * v31;
      }
      while ( v27 != *((__int64 **)&v5 + 1) );
    }
    *v36 = v24;
    free_base(0);
    for ( n = (void **)v5; n != *((void ***)&v5 + 1); ++n )
      free_base(*n);
    free_base((void *)v5);
    return 0;
  }
  else
  {
    *(_DWORD *)sub_140016EA0() = 22;
    invalid_parameter_noinfo();
    return 22;
  }
}

```

## disassembly

```asm
0x14001d684  mov     [rsp-8+arg_10], rbx
0x14001d689  push    rbp
0x14001d68a  push    rsi
0x14001d68b  push    rdi
0x14001d68c  push    r12
0x14001d68e  push    r13
0x14001d690  push    r14
0x14001d692  push    r15
0x14001d694  lea     rbp, [rsp-1C0h]
0x14001d69c  sub     rsp, 2C0h
0x14001d6a3  mov     rax, cs:__security_cookie
0x14001d6aa  xor     rax, rsp
0x14001d6ad  mov     [rbp+1F0h+var_38], rax
0x14001d6b4  xor     r12d, r12d
0x14001d6b7  mov     [rsp+2F0h+var_2A0], rdx
0x14001d6bc  mov     r15, rcx
0x14001d6bf  test    rdx, rdx
0x14001d6c2  jnz     short loc_14001D6DC
0x14001d6c4  call    sub_140016EA0
0x14001d6c9  lea     ebx, [r12+16h]
0x14001d6ce  mov     [rax], ebx
0x14001d6d0  call    _invalid_parameter_noinfo
0x14001d6d5  mov     eax, ebx
0x14001d6d7  jmp     loc_14001DA44
0x14001d6dc  xorps   xmm0, xmm0
0x14001d6df  mov     [rdx], r12
0x14001d6e2  mov     rax, [rcx]
0x14001d6e5  movdqu  xmmword ptr [rsp+2F0h+Block], xmm0
0x14001d6eb  mov     rsi, [rsp+2F0h+Block+8]
0x14001d6f0  mov     rdi, [rsp+2F0h+Block]
0x14001d6f5  mov     [rsp+2F0h+var_2B0], r12
0x14001d6fa  test    rax, rax
0x14001d6fd  jz      loc_14001D91E
0x14001d703  lea     rdx, [rbp+1F0h+var_40]
0x14001d70a  mov     dword ptr [rbp+1F0h+var_40], 3F002Ah
0x14001d714  mov     rcx, rax
0x14001d717  mov     word ptr [rbp+1F0h+var_40+4], r12w
0x14001d71f  mov     rbx, 200000000801h
0x14001d729  call    sub_14001EAB0
0x14001d72e  mov     r14, [r15]
0x14001d731  mov     rcx, rax
0x14001d734  test    rax, rax
0x14001d737  jnz     short loc_14001D764
0x14001d739  lea     r9, [rsp+2F0h+Block]
0x14001d73e  xor     r8d, r8d
0x14001d741  xor     edx, edx
0x14001d743  mov     rcx, r14
0x14001d746  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x14001d74b  mov     rdi, [rsp+2F0h+Block]
0x14001d750  mov     esi, eax
0x14001d752  test    eax, eax
0x14001d754  jnz     loc_14001D8C7
0x14001d75a  mov     rsi, [rsp+2F0h+Block+8]
0x14001d75f  jmp     loc_14001D8BB
0x14001d764  cmp     rax, r14
0x14001d767  jz      short loc_14001D788
0x14001d769  movzx   eax, word ptr [rcx]
0x14001d76c  sub     ax, 2Fh ; '/'
0x14001d770  cmp     ax, 2Dh ; '-'
0x14001d774  ja      short loc_14001D77F
0x14001d776  movzx   eax, ax
0x14001d779  bt      rbx, rax
0x14001d77d  jb      short loc_14001D788
0x14001d77f  sub     rcx, 2
0x14001d783  cmp     rcx, r14
0x14001d786  jnz     short loc_14001D769
0x14001d788  movzx   edx, word ptr [rcx]
0x14001d78b  cmp     dx, 3Ah ; ':'
0x14001d78f  jnz     short loc_14001D79A
0x14001d791  lea     rax, [r14+2]
0x14001d795  cmp     rcx, rax
0x14001d798  jnz     short loc_14001D7FB
0x14001d79a  sub     dx, 2Fh ; '/'
0x14001d79e  cmp     dx, 2Dh ; '-'
0x14001d7a2  ja      short loc_14001D7AF
0x14001d7a4  movzx   eax, dx
0x14001d7a7  bt      rbx, rax
0x14001d7ab  mov     al, 1
0x14001d7ad  jb      short loc_14001D7B2
0x14001d7af  mov     al, r12b
0x14001d7b2  sub     rcx, r14
0x14001d7b5  mov     r8d, 250h
0x14001d7bb  sar     rcx, 1
0x14001d7be  inc     rcx
0x14001d7c1  neg     al
0x14001d7c3  sbb     r13, r13
0x14001d7c6  xor     edx, edx
0x14001d7c8  and     r13, rcx
0x14001d7cb  lea     rcx, [rsp+2F0h+FindFileData]
0x14001d7d0  call    sub_14002A310
0x14001d7d5  xor     r9d, r9d; fSearchOp
0x14001d7d8  mov     [rsp+2F0h+dwAdditionalFlags], r12d; dwAdditionalFlags
0x14001d7dd  lea     r8, [rsp+2F0h+FindFileData]; lpFindFileData
0x14001d7e2  mov     [rsp+2F0h+lpSearchFilter], r12; lpSearchFilter
0x14001d7e7  xor     edx, edx; fInfoLevelId
0x14001d7e9  mov     rcx, r14; lpFileName
0x14001d7ec  call    cs:FindFirstFileExW
0x14001d7f2  mov     rbx, rax
0x14001d7f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001d7f9  jnz     short loc_14001D827
0x14001d7fb  lea     r9, [rsp+2F0h+Block]
0x14001d800  mov     r8, r12
0x14001d803  mov     rdx, r12
0x14001d806  mov     rcx, r14
0x14001d809  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x14001d80e  mov     esi, eax
0x14001d810  test    eax, eax
0x14001d812  jnz     loc_14001D8F6
0x14001d818  mov     rsi, [rsp+2F0h+Block+8]
0x14001d81d  mov     rdi, [rsp+2F0h+Block]
0x14001d822  jmp     loc_14001D8BB
0x14001d827  sub     rsi, rdi
0x14001d82a  sar     rsi, 3
0x14001d82e  mov     r12, rsi
0x14001d831  xor     edi, edi
0x14001d833  cmp     [rbp+1F0h+var_264], 2Eh ; '.'
0x14001d838  jnz     short loc_14001D84F
0x14001d83a  movzx   eax, [rbp+1F0h+var_262]
0x14001d83e  test    ax, ax
0x14001d841  jz      short loc_14001D86D
0x14001d843  cmp     ax, 2Eh ; '.'
0x14001d847  jnz     short loc_14001D84F
0x14001d849  cmp     [rbp+1F0h+var_260], di
0x14001d84d  jz      short loc_14001D86D
0x14001d84f  lea     r9, [rsp+2F0h+Block]
0x14001d854  mov     r8, r13
0x14001d857  mov     rdx, r14
0x14001d85a  lea     rcx, [rbp+1F0h+var_264]
0x14001d85e  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x14001d863  mov     esi, eax
0x14001d865  test    eax, eax
0x14001d867  jnz     loc_14001D8ED
0x14001d86d  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x14001d872  mov     rcx, rbx; hFindFile
0x14001d875  call    cs:FindNextFileW
0x14001d87b  test    eax, eax
0x14001d87d  jnz     short loc_14001D833
0x14001d87f  mov     rsi, [rsp+2F0h+Block+8]
0x14001d884  mov     rdi, [rsp+2F0h+Block]
0x14001d889  mov     rdx, rsi
0x14001d88c  sub     rdx, rdi
0x14001d88f  sar     rdx, 3
0x14001d893  cmp     r12, rdx
0x14001d896  jz      short loc_14001D8AF
0x14001d898  sub     rdx, r12
0x14001d89b  lea     rcx, [rdi+r12*8]
0x14001d89f  lea     r9, unknown_libname_46; Microsoft VisualC 64bit universal runtime
0x14001d8a6  lea     r8d, [rax+8]
0x14001d8aa  call    sub_140022B90
0x14001d8af  mov     rcx, rbx; hFindFile
0x14001d8b2  call    cs:FindClose
0x14001d8b8  xor     r12d, r12d
0x14001d8bb  add     r15, 8
0x14001d8bf  mov     rax, [r15]
0x14001d8c2  jmp     loc_14001D6FA
0x14001d8c7  mov     rbx, rdi
0x14001d8ca  cmp     rdi, [rsp+2F0h+Block+8]
0x14001d8cf  jz      loc_14001D992
0x14001d8d5  mov     rcx, [rbx]; Block
0x14001d8d8  call    _free_base
0x14001d8dd  add     rbx, 8
0x14001d8e1  cmp     rbx, [rsp+2F0h+Block+8]
0x14001d8e6  jnz     short loc_14001D8D5
0x14001d8e8  jmp     loc_14001D992
0x14001d8ed  mov     rcx, rbx; hFindFile
0x14001d8f0  call    cs:FindClose
0x14001d8f6  mov     rdi, [rsp+2F0h+Block]
0x14001d8fb  mov     rbx, rdi
0x14001d8fe  cmp     rdi, [rsp+2F0h+Block+8]
0x14001d903  jz      loc_14001D992
0x14001d909  mov     rcx, [rbx]; Block
0x14001d90c  call    _free_base
0x14001d911  add     rbx, 8
0x14001d915  cmp     rbx, [rsp+2F0h+Block+8]
0x14001d91a  jnz     short loc_14001D909
0x14001d91c  jmp     short loc_14001D992
0x14001d91e  mov     r14, rsi
0x14001d921  mov     r13, r12
0x14001d924  sub     r14, rdi
0x14001d927  mov     rax, rdi
0x14001d92a  sar     r14, 3
0x14001d92e  inc     r14
0x14001d931  cmp     rdi, rsi
0x14001d934  jz      short loc_14001D956
0x14001d936  mov     rdx, [rax]
0x14001d939  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14001d93d  inc     rcx
0x14001d940  cmp     [rdx+rcx*2], r12w
0x14001d945  jnz     short loc_14001D93D
0x14001d947  inc     r13
0x14001d94a  add     rax, 8
0x14001d94e  add     r13, rcx
0x14001d951  cmp     rax, rsi
0x14001d954  jnz     short loc_14001D936
0x14001d956  mov     r8d, 2
0x14001d95c  mov     rdx, r13
0x14001d95f  mov     rcx, r14
0x14001d962  call    __acrt_allocate_buffer_for_argv
0x14001d967  mov     rbx, rax
0x14001d96a  test    rax, rax
0x14001d96d  jnz     short loc_14001D9A1
0x14001d96f  xor     ecx, ecx; Block
0x14001d971  call    _free_base
0x14001d976  mov     rbx, rdi
0x14001d979  cmp     rdi, rsi
0x14001d97c  jz      short loc_14001D98F
0x14001d97e  mov     rcx, [rbx]; Block
0x14001d981  call    _free_base
0x14001d986  add     rbx, 8
0x14001d98a  cmp     rbx, rsi
0x14001d98d  jnz     short loc_14001D97E
0x14001d98f  or      esi, 0FFFFFFFFh
0x14001d992  mov     rcx, rdi; Block
0x14001d995  call    _free_base
0x14001d99a  mov     eax, esi
0x14001d99c  jmp     loc_14001DA44
0x14001d9a1  lea     rcx, [rax+r14*8]
0x14001d9a5  mov     r14, rdi
0x14001d9a8  mov     [rsp+2F0h+var_2A8], rcx
0x14001d9ad  mov     r12, rcx
0x14001d9b0  cmp     rdi, rsi
0x14001d9b3  jz      short loc_14001DA12
0x14001d9b5  sub     rax, rdi
0x14001d9b8  mov     [rbp+1F0h+var_40], rax
0x14001d9bf  mov     r8, [r14]
0x14001d9c2  or      r15, 0FFFFFFFFFFFFFFFFh
0x14001d9c6  xor     eax, eax
0x14001d9c8  inc     r15
0x14001d9cb  cmp     [r8+r15*2], ax
0x14001d9d0  jnz     short loc_14001D9C8
0x14001d9d2  mov     rax, r12
0x14001d9d5  inc     r15
0x14001d9d8  sub     rax, rcx
0x14001d9db  mov     rdx, r13
0x14001d9de  sar     rax, 1
0x14001d9e1  mov     r9, r15
0x14001d9e4  sub     rdx, rax
0x14001d9e7  mov     rcx, r12
0x14001d9ea  call    sub_14001D520
0x14001d9ef  xor     ecx, ecx; Expression
0x14001d9f1  test    eax, eax
0x14001d9f3  jnz     short loc_14001DA6E
0x14001d9f5  mov     rax, [rbp+1F0h+var_40]
0x14001d9fc  mov     rcx, [rsp+2F0h+var_2A8]
0x14001da01  mov     [rax+r14], r12
0x14001da05  add     r14, 8
0x14001da09  lea     r12, [r12+r15*2]
0x14001da0d  cmp     r14, rsi
0x14001da10  jnz     short loc_14001D9BF
0x14001da12  mov     rax, [rsp+2F0h+var_2A0]
0x14001da17  xor     ecx, ecx; Block
0x14001da19  mov     [rax], rbx
0x14001da1c  call    _free_base
0x14001da21  mov     rbx, rdi
0x14001da24  cmp     rdi, rsi
0x14001da27  jz      short loc_14001DA3A
0x14001da29  mov     rcx, [rbx]; Block
0x14001da2c  call    _free_base
0x14001da31  add     rbx, 8
0x14001da35  cmp     rbx, rsi
0x14001da38  jnz     short loc_14001DA29
0x14001da3a  mov     rcx, rdi; Block
0x14001da3d  call    _free_base
0x14001da42  xor     eax, eax
0x14001da44  mov     rcx, [rbp+1F0h+var_38]
0x14001da4b  xor     rcx, rsp; StackCookie
0x14001da4e  call    __security_check_cookie
0x14001da53  mov     rbx, [rsp+2F0h+arg_10]
0x14001da5b  add     rsp, 2C0h
0x14001da62  pop     r15
0x14001da64  pop     r14
0x14001da66  pop     r13
0x14001da68  pop     r12
0x14001da6a  pop     rdi
0x14001da6b  pop     rsi
0x14001da6c  pop     rbp
0x14001da6d  retn
0x14001da6e  xor     r9d, r9d; LineNo
0x14001da71  mov     [rsp+2F0h+lpSearchFilter], rcx; Reserved
0x14001da76  xor     r8d, r8d; FileName
0x14001da79  xor     edx, edx; FunctionName
0x14001da7b  call    _invoke_watson
```
