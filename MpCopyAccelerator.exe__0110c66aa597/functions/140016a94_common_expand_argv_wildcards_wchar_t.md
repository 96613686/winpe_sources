# common_expand_argv_wildcards_wchar_t_

- ea: `0x140016a94`
- end: `0x140016e91`
- name: `common_expand_argv_wildcards_wchar_t_`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14001701c`

## callees

- `0x140005c20`
- `0x14000bf5c`
- `0x14000bf7c`
- `0x1400120dc`
- `0x1400124a8`
- `0x140013e10`
- `0x140016930`
- `0x140016a94`
- `0x140016e94`
- `0x140017cc0`
- `0x14001ae90`
- `0x140024cc0`

## import_xrefs

- `KERNEL32!FindClose` at `0x140016cc2`
- `KERNEL32!FindClose` at `0x140016d00`
- `KERNEL32!FindClose` at `0x140016cc2`
- `KERNEL32!FindClose` at `0x140016d00`
- `KERNEL32!FindFirstFileExW` at `0x140016bfc`
- `KERNEL32!FindFirstFileExW` at `0x140016bfc`
- `KERNEL32!FindNextFileW` at `0x140016c85`
- `KERNEL32!FindNextFileW` at `0x140016c85`

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
  wchar_t *v9; // rcx
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
0x140016a94  mov     [rsp-8+arg_10], rbx
0x140016a99  push    rbp
0x140016a9a  push    rsi
0x140016a9b  push    rdi
0x140016a9c  push    r12
0x140016a9e  push    r13
0x140016aa0  push    r14
0x140016aa2  push    r15
0x140016aa4  lea     rbp, [rsp-1C0h]
0x140016aac  sub     rsp, 2C0h
0x140016ab3  mov     rax, cs:__security_cookie
0x140016aba  xor     rax, rsp
0x140016abd  mov     [rbp+1F0h+var_38], rax
0x140016ac4  xor     r12d, r12d
0x140016ac7  mov     [rsp+2F0h+var_2A0], rdx
0x140016acc  mov     r15, rcx
0x140016acf  test    rdx, rdx
0x140016ad2  jnz     short loc_140016AEC
0x140016ad4  call    _errno
0x140016ad9  lea     ebx, [r12+16h]
0x140016ade  mov     [rax], ebx
0x140016ae0  call    _invalid_parameter_noinfo
0x140016ae5  mov     eax, ebx
0x140016ae7  jmp     loc_140016E54
0x140016aec  xorps   xmm0, xmm0
0x140016aef  mov     [rdx], r12
0x140016af2  mov     rax, [rcx]
0x140016af5  movdqu  xmmword ptr [rsp+2F0h+Block], xmm0
0x140016afb  mov     rsi, [rsp+2F0h+Block+8]
0x140016b00  mov     rdi, [rsp+2F0h+Block]
0x140016b05  mov     [rsp+2F0h+var_2B0], r12
0x140016b0a  test    rax, rax
0x140016b0d  jz      loc_140016D2E
0x140016b13  lea     rdx, [rbp+1F0h+Control]; Control
0x140016b1a  mov     dword ptr [rbp+1F0h+Control], 3F002Ah
0x140016b24  mov     rcx, rax; String
0x140016b27  mov     [rbp+1F0h+Control+4], r12w
0x140016b2f  mov     rbx, 200000000801h
0x140016b39  call    wcspbrk
0x140016b3e  mov     r14, [r15]
0x140016b41  mov     rcx, rax
0x140016b44  test    rax, rax
0x140016b47  jnz     short loc_140016B74
0x140016b49  lea     r9, [rsp+2F0h+Block]
0x140016b4e  xor     r8d, r8d; MaxCount
0x140016b51  xor     edx, edx; wchar_t *
0x140016b53  mov     rcx, r14; Source
0x140016b56  call    copy_and_add_argument_to_buffer_wchar_t_
0x140016b5b  mov     rdi, [rsp+2F0h+Block]
0x140016b60  mov     esi, eax
0x140016b62  test    eax, eax
0x140016b64  jnz     loc_140016CD7
0x140016b6a  mov     rsi, [rsp+2F0h+Block+8]
0x140016b6f  jmp     loc_140016CCB
0x140016b74  cmp     rax, r14
0x140016b77  jz      short loc_140016B98
0x140016b79  movzx   eax, word ptr [rcx]
0x140016b7c  sub     ax, 2Fh ; '/'
0x140016b80  cmp     ax, 2Dh ; '-'
0x140016b84  ja      short loc_140016B8F
0x140016b86  movzx   eax, ax
0x140016b89  bt      rbx, rax
0x140016b8d  jb      short loc_140016B98
0x140016b8f  sub     rcx, 2
0x140016b93  cmp     rcx, r14
0x140016b96  jnz     short loc_140016B79
0x140016b98  movzx   edx, word ptr [rcx]
0x140016b9b  cmp     dx, 3Ah ; ':'
0x140016b9f  jnz     short loc_140016BAA
0x140016ba1  lea     rax, [r14+2]
0x140016ba5  cmp     rcx, rax
0x140016ba8  jnz     short loc_140016C0B
0x140016baa  sub     dx, 2Fh ; '/'
0x140016bae  cmp     dx, 2Dh ; '-'
0x140016bb2  ja      short loc_140016BBF
0x140016bb4  movzx   eax, dx
0x140016bb7  bt      rbx, rax
0x140016bbb  mov     al, 1
0x140016bbd  jb      short loc_140016BC2
0x140016bbf  mov     al, r12b
0x140016bc2  sub     rcx, r14
0x140016bc5  mov     r8d, 250h; Size
0x140016bcb  sar     rcx, 1
0x140016bce  inc     rcx
0x140016bd1  neg     al
0x140016bd3  sbb     r13, r13
0x140016bd6  xor     edx, edx; Val
0x140016bd8  and     r13, rcx
0x140016bdb  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x140016be0  call    memset
0x140016be5  xor     r9d, r9d; fSearchOp
0x140016be8  mov     [rsp+2F0h+dwAdditionalFlags], r12d; dwAdditionalFlags
0x140016bed  lea     r8, [rsp+2F0h+FindFileData]; lpFindFileData
0x140016bf2  mov     [rsp+2F0h+lpSearchFilter], r12; lpSearchFilter
0x140016bf7  xor     edx, edx; fInfoLevelId
0x140016bf9  mov     rcx, r14; lpFileName
0x140016bfc  call    cs:__imp_FindFirstFileExW
0x140016c02  mov     rbx, rax
0x140016c05  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140016c09  jnz     short loc_140016C37
0x140016c0b  lea     r9, [rsp+2F0h+Block]
0x140016c10  mov     r8, r12; MaxCount
0x140016c13  mov     rdx, r12; wchar_t *
0x140016c16  mov     rcx, r14; Source
0x140016c19  call    copy_and_add_argument_to_buffer_wchar_t_
0x140016c1e  mov     esi, eax
0x140016c20  test    eax, eax
0x140016c22  jnz     loc_140016D06
0x140016c28  mov     rsi, [rsp+2F0h+Block+8]
0x140016c2d  mov     rdi, [rsp+2F0h+Block]
0x140016c32  jmp     loc_140016CCB
0x140016c37  sub     rsi, rdi
0x140016c3a  sar     rsi, 3
0x140016c3e  mov     r12, rsi
0x140016c41  xor     edi, edi
0x140016c43  cmp     [rbp+1F0h+Source], 2Eh ; '.'
0x140016c48  jnz     short loc_140016C5F
0x140016c4a  movzx   eax, [rbp+1F0h+var_262]
0x140016c4e  test    ax, ax
0x140016c51  jz      short loc_140016C7D
0x140016c53  cmp     ax, 2Eh ; '.'
0x140016c57  jnz     short loc_140016C5F
0x140016c59  cmp     [rbp+1F0h+var_260], di
0x140016c5d  jz      short loc_140016C7D
0x140016c5f  lea     r9, [rsp+2F0h+Block]
0x140016c64  mov     r8, r13; MaxCount
0x140016c67  mov     rdx, r14; wchar_t *
0x140016c6a  lea     rcx, [rbp+1F0h+Source]; Source
0x140016c6e  call    copy_and_add_argument_to_buffer_wchar_t_
0x140016c73  mov     esi, eax
0x140016c75  test    eax, eax
0x140016c77  jnz     loc_140016CFD
0x140016c7d  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x140016c82  mov     rcx, rbx; hFindFile
0x140016c85  call    cs:__imp_FindNextFileW
0x140016c8b  test    eax, eax
0x140016c8d  jnz     short loc_140016C43
0x140016c8f  mov     rsi, [rsp+2F0h+Block+8]
0x140016c94  mov     rdi, [rsp+2F0h+Block]
0x140016c99  mov     rdx, rsi
0x140016c9c  sub     rdx, rdi
0x140016c9f  sar     rdx, 3
0x140016ca3  cmp     r12, rdx
0x140016ca6  jz      short loc_140016CBF
0x140016ca8  sub     rdx, r12; NumOfElements
0x140016cab  lea     rcx, [rdi+r12*8]; Base
0x140016caf  lea     r9, _lambda_861af8918f661c876f88da8747958ced____lambda_invoker_cdecl_; CompareFunction
0x140016cb6  lea     r8d, [rax+8]; SizeOfElements
0x140016cba  call    qsort
0x140016cbf  mov     rcx, rbx; hFindFile
0x140016cc2  call    cs:__imp_FindClose
0x140016cc8  xor     r12d, r12d
0x140016ccb  add     r15, 8
0x140016ccf  mov     rax, [r15]
0x140016cd2  jmp     loc_140016B0A
0x140016cd7  mov     rbx, rdi
0x140016cda  cmp     rdi, [rsp+2F0h+Block+8]
0x140016cdf  jz      loc_140016DA2
0x140016ce5  mov     rcx, [rbx]; Block
0x140016ce8  call    _free_base
0x140016ced  add     rbx, 8
0x140016cf1  cmp     rbx, [rsp+2F0h+Block+8]
0x140016cf6  jnz     short loc_140016CE5
0x140016cf8  jmp     loc_140016DA2
0x140016cfd  mov     rcx, rbx; hFindFile
0x140016d00  call    cs:__imp_FindClose
0x140016d06  mov     rdi, [rsp+2F0h+Block]
0x140016d0b  mov     rbx, rdi
0x140016d0e  cmp     rdi, [rsp+2F0h+Block+8]
0x140016d13  jz      loc_140016DA2
0x140016d19  mov     rcx, [rbx]; Block
0x140016d1c  call    _free_base
0x140016d21  add     rbx, 8
0x140016d25  cmp     rbx, [rsp+2F0h+Block+8]
0x140016d2a  jnz     short loc_140016D19
0x140016d2c  jmp     short loc_140016DA2
0x140016d2e  mov     r14, rsi
0x140016d31  mov     r13, r12
0x140016d34  sub     r14, rdi
0x140016d37  mov     rax, rdi
0x140016d3a  sar     r14, 3
0x140016d3e  inc     r14
0x140016d41  cmp     rdi, rsi
0x140016d44  jz      short loc_140016D66
0x140016d46  mov     rdx, [rax]
0x140016d49  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140016d4d  inc     rcx
0x140016d50  cmp     [rdx+rcx*2], r12w
0x140016d55  jnz     short loc_140016D4D
0x140016d57  inc     r13
0x140016d5a  add     rax, 8
0x140016d5e  add     r13, rcx
0x140016d61  cmp     rax, rsi
0x140016d64  jnz     short loc_140016D46
0x140016d66  mov     r8d, 2
0x140016d6c  mov     rdx, r13
0x140016d6f  mov     rcx, r14
0x140016d72  call    __acrt_allocate_buffer_for_argv
0x140016d77  mov     rbx, rax
0x140016d7a  test    rax, rax
0x140016d7d  jnz     short loc_140016DB1
0x140016d7f  xor     ecx, ecx; Block
0x140016d81  call    _free_base
0x140016d86  mov     rbx, rdi
0x140016d89  cmp     rdi, rsi
0x140016d8c  jz      short loc_140016D9F
0x140016d8e  mov     rcx, [rbx]; Block
0x140016d91  call    _free_base
0x140016d96  add     rbx, 8
0x140016d9a  cmp     rbx, rsi
0x140016d9d  jnz     short loc_140016D8E
0x140016d9f  or      esi, 0FFFFFFFFh
0x140016da2  mov     rcx, rdi; Block
0x140016da5  call    _free_base
0x140016daa  mov     eax, esi
0x140016dac  jmp     loc_140016E54
0x140016db1  lea     rcx, [rax+r14*8]
0x140016db5  mov     r14, rdi
0x140016db8  mov     [rsp+2F0h+var_2A8], rcx
0x140016dbd  mov     r12, rcx
0x140016dc0  cmp     rdi, rsi
0x140016dc3  jz      short loc_140016E22
0x140016dc5  sub     rax, rdi
0x140016dc8  mov     qword ptr [rbp+1F0h+Control], rax
0x140016dcf  mov     r8, [r14]; Source
0x140016dd2  or      r15, 0FFFFFFFFFFFFFFFFh
0x140016dd6  xor     eax, eax
0x140016dd8  inc     r15
0x140016ddb  cmp     [r8+r15*2], ax
0x140016de0  jnz     short loc_140016DD8
0x140016de2  mov     rax, r12
0x140016de5  inc     r15
0x140016de8  sub     rax, rcx
0x140016deb  mov     rdx, r13
0x140016dee  sar     rax, 1
0x140016df1  mov     r9, r15; MaxCount
0x140016df4  sub     rdx, rax; SizeInWords
0x140016df7  mov     rcx, r12; Destination
0x140016dfa  call    wcsncpy_s
0x140016dff  xor     ecx, ecx; Expression
0x140016e01  test    eax, eax
0x140016e03  jnz     short loc_140016E7E
0x140016e05  mov     rax, qword ptr [rbp+1F0h+Control]
0x140016e0c  mov     rcx, [rsp+2F0h+var_2A8]
0x140016e11  mov     [rax+r14], r12
0x140016e15  add     r14, 8
0x140016e19  lea     r12, [r12+r15*2]
0x140016e1d  cmp     r14, rsi
0x140016e20  jnz     short loc_140016DCF
0x140016e22  mov     rax, [rsp+2F0h+var_2A0]
0x140016e27  xor     ecx, ecx; Block
0x140016e29  mov     [rax], rbx
0x140016e2c  call    _free_base
0x140016e31  mov     rbx, rdi
0x140016e34  cmp     rdi, rsi
0x140016e37  jz      short loc_140016E4A
0x140016e39  mov     rcx, [rbx]; Block
0x140016e3c  call    _free_base
0x140016e41  add     rbx, 8
0x140016e45  cmp     rbx, rsi
0x140016e48  jnz     short loc_140016E39
0x140016e4a  mov     rcx, rdi; Block
0x140016e4d  call    _free_base
0x140016e52  xor     eax, eax
0x140016e54  mov     rcx, [rbp+1F0h+var_38]
0x140016e5b  xor     rcx, rsp; StackCookie
0x140016e5e  call    __security_check_cookie
0x140016e63  mov     rbx, [rsp+2F0h+arg_10]
0x140016e6b  add     rsp, 2C0h
0x140016e72  pop     r15
0x140016e74  pop     r14
0x140016e76  pop     r13
0x140016e78  pop     r12
0x140016e7a  pop     rdi
0x140016e7b  pop     rsi
0x140016e7c  pop     rbp
0x140016e7d  retn
0x140016e7e  xor     r9d, r9d; LineNo
0x140016e81  mov     [rsp+2F0h+lpSearchFilter], rcx; Reserved
0x140016e86  xor     r8d, r8d; FileName
0x140016e89  xor     edx, edx; FunctionName
0x140016e8b  call    _invoke_watson
```
