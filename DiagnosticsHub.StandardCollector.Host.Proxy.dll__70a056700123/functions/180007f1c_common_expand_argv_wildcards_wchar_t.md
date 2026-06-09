# common_expand_argv_wildcards_wchar_t_

- ea: `0x180007f1c`
- end: `0x180008319`
- name: `common_expand_argv_wildcards_wchar_t_`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000962c`

## callees

- `0x180004544`
- `0x1800074a0`
- `0x1800074f0`
- `0x180007788`
- `0x1800078e0`
- `0x180007f1c`
- `0x1800084a0`
- `0x1800120c0`
- `0x1800125a0`
- `0x1800126f0`
- `0x180032370`
- `0x180060270`

## import_xrefs

- `KERNEL32!FindClose` at `0x18000814a`
- `KERNEL32!FindClose` at `0x180008188`
- `KERNEL32!FindClose` at `0x18000814a`
- `KERNEL32!FindClose` at `0x180008188`
- `KERNEL32!FindFirstFileExW` at `0x180008084`
- `KERNEL32!FindFirstFileExW` at `0x180008084`
- `KERNEL32!FindNextFileW` at `0x18000810d`
- `KERNEL32!FindNextFileW` at `0x18000810d`

## pseudocode

```c
__int64 __fastcall common_expand_argv_wildcards_wchar_t_(const wchar_t **a1, __int64 *a2)
{
  wchar_t **v2; // r15
  const wchar_t *v4; // rax
  __int128 v5; // rdi
  __int64 v6; // rbx
  wchar_t *v7; // rax
  WCHAR *v8; // r14
  WCHAR *v9; // rcx
  unsigned __int16 v10; // ax
  unsigned __int16 v11; // dx
  char v12; // al
  rsize_t v13; // r13
  HANDLE FirstFile; // rbx
  __int64 v15; // r12
  __int64 v16; // r13
  _QWORD *i; // rax
  __int64 v18; // rcx
  __int64 buffer_for_argv; // rax
  __int64 v20; // rbx
  void **j; // rbx
  wchar_t *v22; // rcx
  const wchar_t **v23; // r14
  wchar_t *v24; // r12
  const wchar_t *v25; // r8
  __int64 v26; // r15
  rsize_t v27; // r15
  void **k; // rbx
  wchar_t *v29; // [rsp+48h] [rbp-B8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Control[4]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v2 = (wchar_t **)a1;
  if ( a2 )
  {
    *a2 = 0;
    v4 = *a1;
    v5 = 0;
    while ( v4 )
    {
      wcscpy(Control, L"*?");
      v6 = 0x200000000801LL;
      v7 = wcspbrk(v4, Control);
      v8 = *v2;
      v9 = v7;
      if ( v7 )
      {
        if ( v7 != v8 )
        {
          do
          {
            v10 = *v9 - 47;
            if ( v10 <= 0x2Du && _bittest64(&v6, v10) )
              break;
            --v9;
          }
          while ( v9 != v8 );
        }
        if ( *v9 == 58 && v9 != v8 + 1 )
          goto LABEL_18;
        v11 = *v9 - 47;
        if ( v11 > 0x2Du || (v12 = 1, !_bittest64(&v6, v11)) )
          v12 = 0;
        v13 = (v9 - v8 + 1) & -(__int64)(v12 != 0);
        memset(&FindFileData, 0, sizeof(FindFileData));
        FirstFile = FindFirstFileExW(v8, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 0);
        if ( FirstFile == (HANDLE)-1LL )
        {
LABEL_18:
          DWORD2(v5) = copy_and_add_argument_to_buffer_wchar_t_(v8, 0, 0);
          if ( DWORD2(v5) )
          {
LABEL_33:
            *(_QWORD *)&v5 = 0;
LABEL_42:
            free_base((void *)v5);
            return DWORD2(v5);
          }
          v5 = 0;
        }
        else
        {
          v15 = (__int64)(*((_QWORD *)&v5 + 1) - v5) >> 3;
          do
          {
            if ( FindFileData.cFileName[0] != 46
              || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
            {
              DWORD2(v5) = copy_and_add_argument_to_buffer_wchar_t_(FindFileData.cFileName, v8, v13);
              if ( DWORD2(v5) )
              {
                FindClose(FirstFile);
                goto LABEL_33;
              }
            }
          }
          while ( FindNextFileW(FirstFile, &FindFileData) );
          v5 = 0;
          if ( v15 )
            qsort((void *)(8 * v15), -v15, 8u, lambda_861af8918f661c876f88da8747958ced_::_lambda_invoker_cdecl_);
          FindClose(FirstFile);
        }
      }
      else
      {
        *(_QWORD *)&v5 = 0;
        DWORD2(v5) = copy_and_add_argument_to_buffer_wchar_t_(*v2, 0, 0);
        if ( DWORD2(v5) )
          goto LABEL_42;
        *((_QWORD *)&v5 + 1) = 0;
      }
      v4 = *++v2;
    }
    v16 = 0;
    for ( i = (_QWORD *)v5; i != *((_QWORD **)&v5 + 1); v16 += v18 + 1 )
    {
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(*i + 2 * v18) );
      ++i;
    }
    buffer_for_argv = _acrt_allocate_buffer_for_argv(((__int64)(*((_QWORD *)&v5 + 1) - v5) >> 3) + 1, v16, 2);
    v20 = buffer_for_argv;
    if ( !buffer_for_argv )
    {
      free_base(0);
      for ( j = (void **)v5; j != *((void ***)&v5 + 1); ++j )
        free_base(*j);
      DWORD2(v5) = -1;
      goto LABEL_42;
    }
    v22 = (wchar_t *)(buffer_for_argv + 8 * (((__int64)(*((_QWORD *)&v5 + 1) - v5) >> 3) + 1));
    v23 = (const wchar_t **)v5;
    v29 = v22;
    v24 = v22;
    if ( (_QWORD)v5 != *((_QWORD *)&v5 + 1) )
    {
      *(_QWORD *)Control = buffer_for_argv - v5;
      do
      {
        v25 = *v23;
        v26 = -1;
        do
          ++v26;
        while ( v25[v26] );
        v27 = v26 + 1;
        if ( wcsncpy_s(v24, v16 - (v24 - v22), v25, v27) )
          invoke_watson(0, 0, 0, 0, 0);
        v22 = v29;
        *(const wchar_t **)((char *)v23++ + *(_QWORD *)Control) = v24;
        v24 += v27;
      }
      while ( v23 != *((const wchar_t ***)&v5 + 1) );
    }
    *a2 = v20;
    free_base(0);
    for ( k = (void **)v5; k != *((void ***)&v5 + 1); ++k )
      free_base(*k);
    free_base((void *)v5);
    return 0;
  }
  else
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    return 22;
  }
}

```

## disassembly

```asm
0x180007f1c  mov     [rsp-8+arg_10], rbx
0x180007f21  push    rbp
0x180007f22  push    rsi
0x180007f23  push    rdi
0x180007f24  push    r12
0x180007f26  push    r13
0x180007f28  push    r14
0x180007f2a  push    r15
0x180007f2c  lea     rbp, [rsp-1C0h]
0x180007f34  sub     rsp, 2C0h
0x180007f3b  mov     rax, cs:__security_cookie
0x180007f42  xor     rax, rsp
0x180007f45  mov     [rbp+1F0h+var_38], rax
0x180007f4c  xor     r12d, r12d
0x180007f4f  mov     [rsp+2F0h+var_2A0], rdx
0x180007f54  mov     r15, rcx
0x180007f57  test    rdx, rdx
0x180007f5a  jnz     short loc_180007F74
0x180007f5c  call    _errno
0x180007f61  lea     ebx, [r12+16h]
0x180007f66  mov     [rax], ebx
0x180007f68  call    _invalid_parameter_noinfo
0x180007f6d  mov     eax, ebx
0x180007f6f  jmp     loc_1800082DC
0x180007f74  xorps   xmm0, xmm0
0x180007f77  mov     [rdx], r12
0x180007f7a  mov     rax, [rcx]
0x180007f7d  movdqu  xmmword ptr [rsp+2F0h+Block], xmm0
0x180007f83  mov     rsi, [rsp+2F0h+Block+8]
0x180007f88  mov     rdi, [rsp+2F0h+Block]
0x180007f8d  mov     [rsp+2F0h+var_2B0], r12
0x180007f92  test    rax, rax
0x180007f95  jz      loc_1800081B6
0x180007f9b  lea     rdx, [rbp+1F0h+Control]; Control
0x180007fa2  mov     dword ptr [rbp+1F0h+Control], 3F002Ah
0x180007fac  mov     rcx, rax; String
0x180007faf  mov     [rbp+1F0h+Control+4], r12w
0x180007fb7  mov     rbx, 200000000801h
0x180007fc1  call    wcspbrk
0x180007fc6  mov     r14, [r15]
0x180007fc9  mov     rcx, rax
0x180007fcc  test    rax, rax
0x180007fcf  jnz     short loc_180007FFC
0x180007fd1  lea     r9, [rsp+2F0h+Block]
0x180007fd6  xor     r8d, r8d; MaxCount
0x180007fd9  xor     edx, edx; wchar_t *
0x180007fdb  mov     rcx, r14; Source
0x180007fde  call    copy_and_add_argument_to_buffer_wchar_t_
0x180007fe3  mov     rdi, [rsp+2F0h+Block]
0x180007fe8  mov     esi, eax
0x180007fea  test    eax, eax
0x180007fec  jnz     loc_18000815F
0x180007ff2  mov     rsi, [rsp+2F0h+Block+8]
0x180007ff7  jmp     loc_180008153
0x180007ffc  cmp     rax, r14
0x180007fff  jz      short loc_180008020
0x180008001  movzx   eax, word ptr [rcx]
0x180008004  sub     ax, 2Fh ; '/'
0x180008008  cmp     ax, 2Dh ; '-'
0x18000800c  ja      short loc_180008017
0x18000800e  movzx   eax, ax
0x180008011  bt      rbx, rax
0x180008015  jb      short loc_180008020
0x180008017  sub     rcx, 2
0x18000801b  cmp     rcx, r14
0x18000801e  jnz     short loc_180008001
0x180008020  movzx   edx, word ptr [rcx]
0x180008023  cmp     dx, 3Ah ; ':'
0x180008027  jnz     short loc_180008032
0x180008029  lea     rax, [r14+2]
0x18000802d  cmp     rcx, rax
0x180008030  jnz     short loc_180008093
0x180008032  sub     dx, 2Fh ; '/'
0x180008036  cmp     dx, 2Dh ; '-'
0x18000803a  ja      short loc_180008047
0x18000803c  movzx   eax, dx
0x18000803f  bt      rbx, rax
0x180008043  mov     al, 1
0x180008045  jb      short loc_18000804A
0x180008047  mov     al, r12b
0x18000804a  sub     rcx, r14
0x18000804d  mov     r8d, 250h; Size
0x180008053  sar     rcx, 1
0x180008056  inc     rcx
0x180008059  neg     al
0x18000805b  sbb     r13, r13
0x18000805e  xor     edx, edx; Val
0x180008060  and     r13, rcx
0x180008063  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x180008068  call    memset
0x18000806d  xor     r9d, r9d; fSearchOp
0x180008070  mov     [rsp+2F0h+dwAdditionalFlags], r12d; dwAdditionalFlags
0x180008075  lea     r8, [rsp+2F0h+FindFileData]; lpFindFileData
0x18000807a  mov     [rsp+2F0h+lpSearchFilter], r12; lpSearchFilter
0x18000807f  xor     edx, edx; fInfoLevelId
0x180008081  mov     rcx, r14; lpFileName
0x180008084  call    cs:__imp_FindFirstFileExW
0x18000808a  mov     rbx, rax
0x18000808d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008091  jnz     short loc_1800080BF
0x180008093  lea     r9, [rsp+2F0h+Block]
0x180008098  mov     r8, r12; MaxCount
0x18000809b  mov     rdx, r12; wchar_t *
0x18000809e  mov     rcx, r14; Source
0x1800080a1  call    copy_and_add_argument_to_buffer_wchar_t_
0x1800080a6  mov     esi, eax
0x1800080a8  test    eax, eax
0x1800080aa  jnz     loc_18000818E
0x1800080b0  mov     rsi, [rsp+2F0h+Block+8]
0x1800080b5  mov     rdi, [rsp+2F0h+Block]
0x1800080ba  jmp     loc_180008153
0x1800080bf  sub     rsi, rdi
0x1800080c2  sar     rsi, 3
0x1800080c6  mov     r12, rsi
0x1800080c9  xor     edi, edi
0x1800080cb  cmp     [rbp+1F0h+Source], 2Eh ; '.'
0x1800080d0  jnz     short loc_1800080E7
0x1800080d2  movzx   eax, [rbp+1F0h+var_262]
0x1800080d6  test    ax, ax
0x1800080d9  jz      short loc_180008105
0x1800080db  cmp     ax, 2Eh ; '.'
0x1800080df  jnz     short loc_1800080E7
0x1800080e1  cmp     [rbp+1F0h+var_260], di
0x1800080e5  jz      short loc_180008105
0x1800080e7  lea     r9, [rsp+2F0h+Block]
0x1800080ec  mov     r8, r13; MaxCount
0x1800080ef  mov     rdx, r14; wchar_t *
0x1800080f2  lea     rcx, [rbp+1F0h+Source]; Source
0x1800080f6  call    copy_and_add_argument_to_buffer_wchar_t_
0x1800080fb  mov     esi, eax
0x1800080fd  test    eax, eax
0x1800080ff  jnz     loc_180008185
0x180008105  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x18000810a  mov     rcx, rbx; hFindFile
0x18000810d  call    cs:__imp_FindNextFileW
0x180008113  test    eax, eax
0x180008115  jnz     short loc_1800080CB
0x180008117  mov     rsi, [rsp+2F0h+Block+8]
0x18000811c  mov     rdi, [rsp+2F0h+Block]
0x180008121  mov     rdx, rsi
0x180008124  sub     rdx, rdi
0x180008127  sar     rdx, 3
0x18000812b  cmp     r12, rdx
0x18000812e  jz      short loc_180008147
0x180008130  sub     rdx, r12; NumOfElements
0x180008133  lea     rcx, [rdi+r12*8]; Base
0x180008137  lea     r9, _lambda_861af8918f661c876f88da8747958ced____lambda_invoker_cdecl_; CompareFunction
0x18000813e  lea     r8d, [rax+8]; SizeOfElements
0x180008142  call    qsort
0x180008147  mov     rcx, rbx; hFindFile
0x18000814a  call    cs:__imp_FindClose
0x180008150  xor     r12d, r12d
0x180008153  add     r15, 8
0x180008157  mov     rax, [r15]
0x18000815a  jmp     loc_180007F92
0x18000815f  mov     rbx, rdi
0x180008162  cmp     rdi, [rsp+2F0h+Block+8]
0x180008167  jz      loc_18000822A
0x18000816d  mov     rcx, [rbx]; Block
0x180008170  call    _free_base
0x180008175  add     rbx, 8
0x180008179  cmp     rbx, [rsp+2F0h+Block+8]
0x18000817e  jnz     short loc_18000816D
0x180008180  jmp     loc_18000822A
0x180008185  mov     rcx, rbx; hFindFile
0x180008188  call    cs:__imp_FindClose
0x18000818e  mov     rdi, [rsp+2F0h+Block]
0x180008193  mov     rbx, rdi
0x180008196  cmp     rdi, [rsp+2F0h+Block+8]
0x18000819b  jz      loc_18000822A
0x1800081a1  mov     rcx, [rbx]; Block
0x1800081a4  call    _free_base
0x1800081a9  add     rbx, 8
0x1800081ad  cmp     rbx, [rsp+2F0h+Block+8]
0x1800081b2  jnz     short loc_1800081A1
0x1800081b4  jmp     short loc_18000822A
0x1800081b6  mov     r14, rsi
0x1800081b9  mov     r13, r12
0x1800081bc  sub     r14, rdi
0x1800081bf  mov     rax, rdi
0x1800081c2  sar     r14, 3
0x1800081c6  inc     r14
0x1800081c9  cmp     rdi, rsi
0x1800081cc  jz      short loc_1800081EE
0x1800081ce  mov     rdx, [rax]
0x1800081d1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800081d5  inc     rcx
0x1800081d8  cmp     [rdx+rcx*2], r12w
0x1800081dd  jnz     short loc_1800081D5
0x1800081df  inc     r13
0x1800081e2  add     rax, 8
0x1800081e6  add     r13, rcx
0x1800081e9  cmp     rax, rsi
0x1800081ec  jnz     short loc_1800081CE
0x1800081ee  mov     r8d, 2
0x1800081f4  mov     rdx, r13
0x1800081f7  mov     rcx, r14
0x1800081fa  call    __acrt_allocate_buffer_for_argv
0x1800081ff  mov     rbx, rax
0x180008202  test    rax, rax
0x180008205  jnz     short loc_180008239
0x180008207  xor     ecx, ecx; Block
0x180008209  call    _free_base
0x18000820e  mov     rbx, rdi
0x180008211  cmp     rdi, rsi
0x180008214  jz      short loc_180008227
0x180008216  mov     rcx, [rbx]; Block
0x180008219  call    _free_base
0x18000821e  add     rbx, 8
0x180008222  cmp     rbx, rsi
0x180008225  jnz     short loc_180008216
0x180008227  or      esi, 0FFFFFFFFh
0x18000822a  mov     rcx, rdi; Block
0x18000822d  call    _free_base
0x180008232  mov     eax, esi
0x180008234  jmp     loc_1800082DC
0x180008239  lea     rcx, [rax+r14*8]
0x18000823d  mov     r14, rdi
0x180008240  mov     [rsp+2F0h+var_2A8], rcx
0x180008245  mov     r12, rcx
0x180008248  cmp     rdi, rsi
0x18000824b  jz      short loc_1800082AA
0x18000824d  sub     rax, rdi
0x180008250  mov     qword ptr [rbp+1F0h+Control], rax
0x180008257  mov     r8, [r14]; Source
0x18000825a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000825e  xor     eax, eax
0x180008260  inc     r15
0x180008263  cmp     [r8+r15*2], ax
0x180008268  jnz     short loc_180008260
0x18000826a  mov     rax, r12
0x18000826d  inc     r15
0x180008270  sub     rax, rcx
0x180008273  mov     rdx, r13
0x180008276  sar     rax, 1
0x180008279  mov     r9, r15; MaxCount
0x18000827c  sub     rdx, rax; SizeInWords
0x18000827f  mov     rcx, r12; Destination
0x180008282  call    wcsncpy_s
0x180008287  xor     ecx, ecx; Expression
0x180008289  test    eax, eax
0x18000828b  jnz     short loc_180008306
0x18000828d  mov     rax, qword ptr [rbp+1F0h+Control]
0x180008294  mov     rcx, [rsp+2F0h+var_2A8]
0x180008299  mov     [rax+r14], r12
0x18000829d  add     r14, 8
0x1800082a1  lea     r12, [r12+r15*2]
0x1800082a5  cmp     r14, rsi
0x1800082a8  jnz     short loc_180008257
0x1800082aa  mov     rax, [rsp+2F0h+var_2A0]
0x1800082af  xor     ecx, ecx; Block
0x1800082b1  mov     [rax], rbx
0x1800082b4  call    _free_base
0x1800082b9  mov     rbx, rdi
0x1800082bc  cmp     rdi, rsi
0x1800082bf  jz      short loc_1800082D2
0x1800082c1  mov     rcx, [rbx]; Block
0x1800082c4  call    _free_base
0x1800082c9  add     rbx, 8
0x1800082cd  cmp     rbx, rsi
0x1800082d0  jnz     short loc_1800082C1
0x1800082d2  mov     rcx, rdi; Block
0x1800082d5  call    _free_base
0x1800082da  xor     eax, eax
0x1800082dc  mov     rcx, [rbp+1F0h+var_38]
0x1800082e3  xor     rcx, rsp; StackCookie
0x1800082e6  call    __security_check_cookie
0x1800082eb  mov     rbx, [rsp+2F0h+arg_10]
0x1800082f3  add     rsp, 2C0h
0x1800082fa  pop     r15
0x1800082fc  pop     r14
0x1800082fe  pop     r13
0x180008300  pop     r12
0x180008302  pop     rdi
0x180008303  pop     rsi
0x180008304  pop     rbp
0x180008305  retn
0x180008306  xor     r9d, r9d; LineNo
0x180008309  mov     [rsp+2F0h+lpSearchFilter], rcx; Reserved
0x18000830e  xor     r8d, r8d; FileName
0x180008311  xor     edx, edx; FunctionName
0x180008313  call    _invoke_watson
```
