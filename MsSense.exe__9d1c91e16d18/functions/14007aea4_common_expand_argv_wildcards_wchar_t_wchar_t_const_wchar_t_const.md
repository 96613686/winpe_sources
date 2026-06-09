# common_expand_argv_wildcards<wchar_t>(wchar_t * * const,wchar_t * * * const)

- ea: `0x14007aea4`
- end: `0x14007b2a1`
- name: `??$common_expand_argv_wildcards@_W@@YAHQEAPEA_WQEAPEAPEA_W@Z_0`
- size: `1021`
- prototype: `__int64 __fastcall(const WCHAR **, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14007b42c`

## callees

- `0x140051ba0`
- `0x140061534`
- `0x140061554`
- `0x1400616b4`
- `0x140066da0`
- `0x14006ee10`
- `0x140070bb4`
- `0x140072280`
- `0x140078580`
- `0x14007aea4`
- `0x14007b2a4`
- `0x1400802f0`

## import_xrefs

- `KERNEL32!FindClose` at `0x14007b0d2`
- `KERNEL32!FindClose` at `0x14007b110`
- `KERNEL32!FindClose` at `0x14007b0d2`
- `KERNEL32!FindClose` at `0x14007b110`
- `KERNEL32!FindNextFileW` at `0x14007b095`
- `KERNEL32!FindNextFileW` at `0x14007b095`
- `KERNEL32!FindFirstFileExW` at `0x14007b00c`
- `KERNEL32!FindFirstFileExW` at `0x14007b00c`

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
      v7 = sub_140078580(v4, &v38);
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
        sub_1400802F0(&FindFileData, 0, 592);
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
            sub_14006EE10((char *)Block[0] + 8 * v16, v17 - v16, 8, unknown_libname_94);
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
        if ( (unsigned int)sub_140066DA0(v28, v20 - ((v28 - v26) >> 1), v29, v31) )
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
    *(_DWORD *)sub_1400616B4() = 22;
    invalid_parameter_noinfo();
    return 22;
  }
}

```

## disassembly

```asm
0x14007aea4  mov     [rsp-8+arg_10], rbx
0x14007aea9  push    rbp
0x14007aeaa  push    rsi
0x14007aeab  push    rdi
0x14007aeac  push    r12
0x14007aeae  push    r13
0x14007aeb0  push    r14
0x14007aeb2  push    r15
0x14007aeb4  lea     rbp, [rsp-1C0h]
0x14007aebc  sub     rsp, 2C0h
0x14007aec3  mov     rax, cs:__security_cookie
0x14007aeca  xor     rax, rsp
0x14007aecd  mov     [rbp+1F0h+var_38], rax
0x14007aed4  xor     r12d, r12d
0x14007aed7  mov     [rsp+2F0h+var_2A0], rdx
0x14007aedc  mov     r15, rcx
0x14007aedf  test    rdx, rdx
0x14007aee2  jnz     short loc_14007AEFC
0x14007aee4  call    sub_1400616B4
0x14007aee9  lea     ebx, [r12+16h]
0x14007aeee  mov     [rax], ebx
0x14007aef0  call    _invalid_parameter_noinfo
0x14007aef5  mov     eax, ebx
0x14007aef7  jmp     loc_14007B264
0x14007aefc  xorps   xmm0, xmm0
0x14007aeff  mov     [rdx], r12
0x14007af02  mov     rax, [rcx]
0x14007af05  movdqu  xmmword ptr [rsp+2F0h+Block], xmm0
0x14007af0b  mov     rsi, [rsp+2F0h+Block+8]
0x14007af10  mov     rdi, [rsp+2F0h+Block]
0x14007af15  mov     [rsp+2F0h+var_2B0], r12
0x14007af1a  test    rax, rax
0x14007af1d  jz      loc_14007B13E
0x14007af23  lea     rdx, [rbp+1F0h+var_40]
0x14007af2a  mov     dword ptr [rbp+1F0h+var_40], 3F002Ah
0x14007af34  mov     rcx, rax
0x14007af37  mov     word ptr [rbp+1F0h+var_40+4], r12w
0x14007af3f  mov     rbx, 200000000801h
0x14007af49  call    sub_140078580
0x14007af4e  mov     r14, [r15]
0x14007af51  mov     rcx, rax
0x14007af54  test    rax, rax
0x14007af57  jnz     short loc_14007AF84
0x14007af59  lea     r9, [rsp+2F0h+Block]
0x14007af5e  xor     r8d, r8d
0x14007af61  xor     edx, edx
0x14007af63  mov     rcx, r14
0x14007af66  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x14007af6b  mov     rdi, [rsp+2F0h+Block]
0x14007af70  mov     esi, eax
0x14007af72  test    eax, eax
0x14007af74  jnz     loc_14007B0E7
0x14007af7a  mov     rsi, [rsp+2F0h+Block+8]
0x14007af7f  jmp     loc_14007B0DB
0x14007af84  cmp     rax, r14
0x14007af87  jz      short loc_14007AFA8
0x14007af89  movzx   eax, word ptr [rcx]
0x14007af8c  sub     ax, 2Fh ; '/'
0x14007af90  cmp     ax, 2Dh ; '-'
0x14007af94  ja      short loc_14007AF9F
0x14007af96  movzx   eax, ax
0x14007af99  bt      rbx, rax
0x14007af9d  jb      short loc_14007AFA8
0x14007af9f  sub     rcx, 2
0x14007afa3  cmp     rcx, r14
0x14007afa6  jnz     short loc_14007AF89
0x14007afa8  movzx   edx, word ptr [rcx]
0x14007afab  cmp     dx, 3Ah ; ':'
0x14007afaf  jnz     short loc_14007AFBA
0x14007afb1  lea     rax, [r14+2]
0x14007afb5  cmp     rcx, rax
0x14007afb8  jnz     short loc_14007B01B
0x14007afba  sub     dx, 2Fh ; '/'
0x14007afbe  cmp     dx, 2Dh ; '-'
0x14007afc2  ja      short loc_14007AFCF
0x14007afc4  movzx   eax, dx
0x14007afc7  bt      rbx, rax
0x14007afcb  mov     al, 1
0x14007afcd  jb      short loc_14007AFD2
0x14007afcf  mov     al, r12b
0x14007afd2  sub     rcx, r14
0x14007afd5  mov     r8d, 250h
0x14007afdb  sar     rcx, 1
0x14007afde  inc     rcx
0x14007afe1  neg     al
0x14007afe3  sbb     r13, r13
0x14007afe6  xor     edx, edx
0x14007afe8  and     r13, rcx
0x14007afeb  lea     rcx, [rsp+2F0h+FindFileData]
0x14007aff0  call    sub_1400802F0
0x14007aff5  xor     r9d, r9d; fSearchOp
0x14007aff8  mov     [rsp+2F0h+dwAdditionalFlags], r12d; dwAdditionalFlags
0x14007affd  lea     r8, [rsp+2F0h+FindFileData]; lpFindFileData
0x14007b002  mov     [rsp+2F0h+lpSearchFilter], r12; lpSearchFilter
0x14007b007  xor     edx, edx; fInfoLevelId
0x14007b009  mov     rcx, r14; lpFileName
0x14007b00c  call    cs:FindFirstFileExW
0x14007b012  mov     rbx, rax
0x14007b015  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007b019  jnz     short loc_14007B047
0x14007b01b  lea     r9, [rsp+2F0h+Block]
0x14007b020  mov     r8, r12
0x14007b023  mov     rdx, r12
0x14007b026  mov     rcx, r14
0x14007b029  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x14007b02e  mov     esi, eax
0x14007b030  test    eax, eax
0x14007b032  jnz     loc_14007B116
0x14007b038  mov     rsi, [rsp+2F0h+Block+8]
0x14007b03d  mov     rdi, [rsp+2F0h+Block]
0x14007b042  jmp     loc_14007B0DB
0x14007b047  sub     rsi, rdi
0x14007b04a  sar     rsi, 3
0x14007b04e  mov     r12, rsi
0x14007b051  xor     edi, edi
0x14007b053  cmp     [rbp+1F0h+var_264], 2Eh ; '.'
0x14007b058  jnz     short loc_14007B06F
0x14007b05a  movzx   eax, [rbp+1F0h+var_262]
0x14007b05e  test    ax, ax
0x14007b061  jz      short loc_14007B08D
0x14007b063  cmp     ax, 2Eh ; '.'
0x14007b067  jnz     short loc_14007B06F
0x14007b069  cmp     [rbp+1F0h+var_260], di
0x14007b06d  jz      short loc_14007B08D
0x14007b06f  lea     r9, [rsp+2F0h+Block]
0x14007b074  mov     r8, r13
0x14007b077  mov     rdx, r14
0x14007b07a  lea     rcx, [rbp+1F0h+var_264]
0x14007b07e  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x14007b083  mov     esi, eax
0x14007b085  test    eax, eax
0x14007b087  jnz     loc_14007B10D
0x14007b08d  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x14007b092  mov     rcx, rbx; hFindFile
0x14007b095  call    cs:FindNextFileW
0x14007b09b  test    eax, eax
0x14007b09d  jnz     short loc_14007B053
0x14007b09f  mov     rsi, [rsp+2F0h+Block+8]
0x14007b0a4  mov     rdi, [rsp+2F0h+Block]
0x14007b0a9  mov     rdx, rsi
0x14007b0ac  sub     rdx, rdi
0x14007b0af  sar     rdx, 3
0x14007b0b3  cmp     r12, rdx
0x14007b0b6  jz      short loc_14007B0CF
0x14007b0b8  sub     rdx, r12
0x14007b0bb  lea     rcx, [rdi+r12*8]
0x14007b0bf  lea     r9, unknown_libname_94; Microsoft VisualC 64bit universal runtime
0x14007b0c6  lea     r8d, [rax+8]
0x14007b0ca  call    sub_14006EE10
0x14007b0cf  mov     rcx, rbx; hFindFile
0x14007b0d2  call    cs:FindClose
0x14007b0d8  xor     r12d, r12d
0x14007b0db  add     r15, 8
0x14007b0df  mov     rax, [r15]
0x14007b0e2  jmp     loc_14007AF1A
0x14007b0e7  mov     rbx, rdi
0x14007b0ea  cmp     rdi, [rsp+2F0h+Block+8]
0x14007b0ef  jz      loc_14007B1B2
0x14007b0f5  mov     rcx, [rbx]; Block
0x14007b0f8  call    _free_base
0x14007b0fd  add     rbx, 8
0x14007b101  cmp     rbx, [rsp+2F0h+Block+8]
0x14007b106  jnz     short loc_14007B0F5
0x14007b108  jmp     loc_14007B1B2
0x14007b10d  mov     rcx, rbx; hFindFile
0x14007b110  call    cs:FindClose
0x14007b116  mov     rdi, [rsp+2F0h+Block]
0x14007b11b  mov     rbx, rdi
0x14007b11e  cmp     rdi, [rsp+2F0h+Block+8]
0x14007b123  jz      loc_14007B1B2
0x14007b129  mov     rcx, [rbx]; Block
0x14007b12c  call    _free_base
0x14007b131  add     rbx, 8
0x14007b135  cmp     rbx, [rsp+2F0h+Block+8]
0x14007b13a  jnz     short loc_14007B129
0x14007b13c  jmp     short loc_14007B1B2
0x14007b13e  mov     r14, rsi
0x14007b141  mov     r13, r12
0x14007b144  sub     r14, rdi
0x14007b147  mov     rax, rdi
0x14007b14a  sar     r14, 3
0x14007b14e  inc     r14
0x14007b151  cmp     rdi, rsi
0x14007b154  jz      short loc_14007B176
0x14007b156  mov     rdx, [rax]
0x14007b159  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14007b15d  inc     rcx
0x14007b160  cmp     [rdx+rcx*2], r12w
0x14007b165  jnz     short loc_14007B15D
0x14007b167  inc     r13
0x14007b16a  add     rax, 8
0x14007b16e  add     r13, rcx
0x14007b171  cmp     rax, rsi
0x14007b174  jnz     short loc_14007B156
0x14007b176  mov     r8d, 2
0x14007b17c  mov     rdx, r13
0x14007b17f  mov     rcx, r14
0x14007b182  call    __acrt_allocate_buffer_for_argv
0x14007b187  mov     rbx, rax
0x14007b18a  test    rax, rax
0x14007b18d  jnz     short loc_14007B1C1
0x14007b18f  xor     ecx, ecx; Block
0x14007b191  call    _free_base
0x14007b196  mov     rbx, rdi
0x14007b199  cmp     rdi, rsi
0x14007b19c  jz      short loc_14007B1AF
0x14007b19e  mov     rcx, [rbx]; Block
0x14007b1a1  call    _free_base
0x14007b1a6  add     rbx, 8
0x14007b1aa  cmp     rbx, rsi
0x14007b1ad  jnz     short loc_14007B19E
0x14007b1af  or      esi, 0FFFFFFFFh
0x14007b1b2  mov     rcx, rdi; Block
0x14007b1b5  call    _free_base
0x14007b1ba  mov     eax, esi
0x14007b1bc  jmp     loc_14007B264
0x14007b1c1  lea     rcx, [rax+r14*8]
0x14007b1c5  mov     r14, rdi
0x14007b1c8  mov     [rsp+2F0h+var_2A8], rcx
0x14007b1cd  mov     r12, rcx
0x14007b1d0  cmp     rdi, rsi
0x14007b1d3  jz      short loc_14007B232
0x14007b1d5  sub     rax, rdi
0x14007b1d8  mov     [rbp+1F0h+var_40], rax
0x14007b1df  mov     r8, [r14]
0x14007b1e2  or      r15, 0FFFFFFFFFFFFFFFFh
0x14007b1e6  xor     eax, eax
0x14007b1e8  inc     r15
0x14007b1eb  cmp     [r8+r15*2], ax
0x14007b1f0  jnz     short loc_14007B1E8
0x14007b1f2  mov     rax, r12
0x14007b1f5  inc     r15
0x14007b1f8  sub     rax, rcx
0x14007b1fb  mov     rdx, r13
0x14007b1fe  sar     rax, 1
0x14007b201  mov     r9, r15
0x14007b204  sub     rdx, rax
0x14007b207  mov     rcx, r12
0x14007b20a  call    sub_140066DA0
0x14007b20f  xor     ecx, ecx; Expression
0x14007b211  test    eax, eax
0x14007b213  jnz     short loc_14007B28E
0x14007b215  mov     rax, [rbp+1F0h+var_40]
0x14007b21c  mov     rcx, [rsp+2F0h+var_2A8]
0x14007b221  mov     [rax+r14], r12
0x14007b225  add     r14, 8
0x14007b229  lea     r12, [r12+r15*2]
0x14007b22d  cmp     r14, rsi
0x14007b230  jnz     short loc_14007B1DF
0x14007b232  mov     rax, [rsp+2F0h+var_2A0]
0x14007b237  xor     ecx, ecx; Block
0x14007b239  mov     [rax], rbx
0x14007b23c  call    _free_base
0x14007b241  mov     rbx, rdi
0x14007b244  cmp     rdi, rsi
0x14007b247  jz      short loc_14007B25A
0x14007b249  mov     rcx, [rbx]; Block
0x14007b24c  call    _free_base
0x14007b251  add     rbx, 8
0x14007b255  cmp     rbx, rsi
0x14007b258  jnz     short loc_14007B249
0x14007b25a  mov     rcx, rdi; Block
0x14007b25d  call    _free_base
0x14007b262  xor     eax, eax
0x14007b264  mov     rcx, [rbp+1F0h+var_38]
0x14007b26b  xor     rcx, rsp; StackCookie
0x14007b26e  call    __security_check_cookie
0x14007b273  mov     rbx, [rsp+2F0h+arg_10]
0x14007b27b  add     rsp, 2C0h
0x14007b282  pop     r15
0x14007b284  pop     r14
0x14007b286  pop     r13
0x14007b288  pop     r12
0x14007b28a  pop     rdi
0x14007b28b  pop     rsi
0x14007b28c  pop     rbp
0x14007b28d  retn
0x14007b28e  xor     r9d, r9d; LineNo
0x14007b291  mov     [rsp+2F0h+lpSearchFilter], rcx; Reserved
0x14007b296  xor     r8d, r8d; FileName
0x14007b299  xor     edx, edx; FunctionName
0x14007b29b  call    _invoke_watson
```
