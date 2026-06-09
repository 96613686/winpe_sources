# common_expand_argv_wildcards<wchar_t>(wchar_t * * const,wchar_t * * * const)

- ea: `0x1400069b4`
- end: `0x140006db1`
- name: `??$common_expand_argv_wildcards@_W@@YAHQEAPEA_WQEAPEAPEA_W@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140006fd8`

## callees

- `0x140001350`
- `0x1400048e8`
- `0x140006544`
- `0x140006564`
- `0x140006640`
- `0x14000689c`
- `0x140006940`
- `0x1400069b4`
- `0x140006db4`
- `0x140008dc0`
- `0x14000aa50`
- `0x14000d030`

## import_xrefs

- `KERNEL32!FindClose` at `0x140006be2`
- `KERNEL32!FindClose` at `0x140006c20`
- `KERNEL32!FindClose` at `0x140006be2`
- `KERNEL32!FindClose` at `0x140006c20`
- `KERNEL32!FindFirstFileExW` at `0x140006b1c`
- `KERNEL32!FindFirstFileExW` at `0x140006b1c`
- `KERNEL32!FindNextFileW` at `0x140006ba5`
- `KERNEL32!FindNextFileW` at `0x140006ba5`

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
      v7 = sub_140008DC0(v4, &v38);
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
        sub_14000D030(&FindFileData, 0, 592);
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
            sub_14000AA50((char *)Block[0] + 8 * v16, v17 - v16, 8, unknown_libname_15);
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
        if ( (unsigned int)sub_140006640(v28, v20 - ((v28 - v26) >> 1), v29, v31) )
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
    *(_DWORD *)sub_14000689C() = 22;
    invalid_parameter_noinfo();
    return 22;
  }
}

```

## disassembly

```asm
0x1400069b4  mov     [rsp-8+arg_10], rbx
0x1400069b9  push    rbp
0x1400069ba  push    rsi
0x1400069bb  push    rdi
0x1400069bc  push    r12
0x1400069be  push    r13
0x1400069c0  push    r14
0x1400069c2  push    r15
0x1400069c4  lea     rbp, [rsp-1C0h]
0x1400069cc  sub     rsp, 2C0h
0x1400069d3  mov     rax, cs:__security_cookie
0x1400069da  xor     rax, rsp
0x1400069dd  mov     [rbp+1F0h+var_38], rax
0x1400069e4  xor     r12d, r12d
0x1400069e7  mov     [rsp+2F0h+var_2A0], rdx
0x1400069ec  mov     r15, rcx
0x1400069ef  test    rdx, rdx
0x1400069f2  jnz     short loc_140006A0C
0x1400069f4  call    sub_14000689C
0x1400069f9  lea     ebx, [r12+16h]
0x1400069fe  mov     [rax], ebx
0x140006a00  call    _invalid_parameter_noinfo
0x140006a05  mov     eax, ebx
0x140006a07  jmp     loc_140006D74
0x140006a0c  xorps   xmm0, xmm0
0x140006a0f  mov     [rdx], r12
0x140006a12  mov     rax, [rcx]
0x140006a15  movdqu  xmmword ptr [rsp+2F0h+Block], xmm0
0x140006a1b  mov     rsi, [rsp+2F0h+Block+8]
0x140006a20  mov     rdi, [rsp+2F0h+Block]
0x140006a25  mov     [rsp+2F0h+var_2B0], r12
0x140006a2a  test    rax, rax
0x140006a2d  jz      loc_140006C4E
0x140006a33  lea     rdx, [rbp+1F0h+var_40]
0x140006a3a  mov     dword ptr [rbp+1F0h+var_40], 3F002Ah
0x140006a44  mov     rcx, rax
0x140006a47  mov     word ptr [rbp+1F0h+var_40+4], r12w
0x140006a4f  mov     rbx, 200000000801h
0x140006a59  call    sub_140008DC0
0x140006a5e  mov     r14, [r15]
0x140006a61  mov     rcx, rax
0x140006a64  test    rax, rax
0x140006a67  jnz     short loc_140006A94
0x140006a69  lea     r9, [rsp+2F0h+Block]
0x140006a6e  xor     r8d, r8d
0x140006a71  xor     edx, edx
0x140006a73  mov     rcx, r14
0x140006a76  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x140006a7b  mov     rdi, [rsp+2F0h+Block]
0x140006a80  mov     esi, eax
0x140006a82  test    eax, eax
0x140006a84  jnz     loc_140006BF7
0x140006a8a  mov     rsi, [rsp+2F0h+Block+8]
0x140006a8f  jmp     loc_140006BEB
0x140006a94  cmp     rax, r14
0x140006a97  jz      short loc_140006AB8
0x140006a99  movzx   eax, word ptr [rcx]
0x140006a9c  sub     ax, 2Fh ; '/'
0x140006aa0  cmp     ax, 2Dh ; '-'
0x140006aa4  ja      short loc_140006AAF
0x140006aa6  movzx   eax, ax
0x140006aa9  bt      rbx, rax
0x140006aad  jb      short loc_140006AB8
0x140006aaf  sub     rcx, 2
0x140006ab3  cmp     rcx, r14
0x140006ab6  jnz     short loc_140006A99
0x140006ab8  movzx   edx, word ptr [rcx]
0x140006abb  cmp     dx, 3Ah ; ':'
0x140006abf  jnz     short loc_140006ACA
0x140006ac1  lea     rax, [r14+2]
0x140006ac5  cmp     rcx, rax
0x140006ac8  jnz     short loc_140006B2B
0x140006aca  sub     dx, 2Fh ; '/'
0x140006ace  cmp     dx, 2Dh ; '-'
0x140006ad2  ja      short loc_140006ADF
0x140006ad4  movzx   eax, dx
0x140006ad7  bt      rbx, rax
0x140006adb  mov     al, 1
0x140006add  jb      short loc_140006AE2
0x140006adf  mov     al, r12b
0x140006ae2  sub     rcx, r14
0x140006ae5  mov     r8d, 250h
0x140006aeb  sar     rcx, 1
0x140006aee  inc     rcx
0x140006af1  neg     al
0x140006af3  sbb     r13, r13
0x140006af6  xor     edx, edx
0x140006af8  and     r13, rcx
0x140006afb  lea     rcx, [rsp+2F0h+FindFileData]
0x140006b00  call    sub_14000D030
0x140006b05  xor     r9d, r9d; fSearchOp
0x140006b08  mov     [rsp+2F0h+dwAdditionalFlags], r12d; dwAdditionalFlags
0x140006b0d  lea     r8, [rsp+2F0h+FindFileData]; lpFindFileData
0x140006b12  mov     [rsp+2F0h+lpSearchFilter], r12; lpSearchFilter
0x140006b17  xor     edx, edx; fInfoLevelId
0x140006b19  mov     rcx, r14; lpFileName
0x140006b1c  call    cs:FindFirstFileExW
0x140006b22  mov     rbx, rax
0x140006b25  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140006b29  jnz     short loc_140006B57
0x140006b2b  lea     r9, [rsp+2F0h+Block]
0x140006b30  mov     r8, r12
0x140006b33  mov     rdx, r12
0x140006b36  mov     rcx, r14
0x140006b39  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x140006b3e  mov     esi, eax
0x140006b40  test    eax, eax
0x140006b42  jnz     loc_140006C26
0x140006b48  mov     rsi, [rsp+2F0h+Block+8]
0x140006b4d  mov     rdi, [rsp+2F0h+Block]
0x140006b52  jmp     loc_140006BEB
0x140006b57  sub     rsi, rdi
0x140006b5a  sar     rsi, 3
0x140006b5e  mov     r12, rsi
0x140006b61  xor     edi, edi
0x140006b63  cmp     [rbp+1F0h+var_264], 2Eh ; '.'
0x140006b68  jnz     short loc_140006B7F
0x140006b6a  movzx   eax, [rbp+1F0h+var_262]
0x140006b6e  test    ax, ax
0x140006b71  jz      short loc_140006B9D
0x140006b73  cmp     ax, 2Eh ; '.'
0x140006b77  jnz     short loc_140006B7F
0x140006b79  cmp     [rbp+1F0h+var_260], di
0x140006b7d  jz      short loc_140006B9D
0x140006b7f  lea     r9, [rsp+2F0h+Block]
0x140006b84  mov     r8, r13
0x140006b87  mov     rdx, r14
0x140006b8a  lea     rcx, [rbp+1F0h+var_264]
0x140006b8e  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x140006b93  mov     esi, eax
0x140006b95  test    eax, eax
0x140006b97  jnz     loc_140006C1D
0x140006b9d  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x140006ba2  mov     rcx, rbx; hFindFile
0x140006ba5  call    cs:FindNextFileW
0x140006bab  test    eax, eax
0x140006bad  jnz     short loc_140006B63
0x140006baf  mov     rsi, [rsp+2F0h+Block+8]
0x140006bb4  mov     rdi, [rsp+2F0h+Block]
0x140006bb9  mov     rdx, rsi
0x140006bbc  sub     rdx, rdi
0x140006bbf  sar     rdx, 3
0x140006bc3  cmp     r12, rdx
0x140006bc6  jz      short loc_140006BDF
0x140006bc8  sub     rdx, r12
0x140006bcb  lea     rcx, [rdi+r12*8]
0x140006bcf  lea     r9, unknown_libname_15; Microsoft VisualC 64bit universal runtime
0x140006bd6  lea     r8d, [rax+8]
0x140006bda  call    sub_14000AA50
0x140006bdf  mov     rcx, rbx; hFindFile
0x140006be2  call    cs:FindClose
0x140006be8  xor     r12d, r12d
0x140006beb  add     r15, 8
0x140006bef  mov     rax, [r15]
0x140006bf2  jmp     loc_140006A2A
0x140006bf7  mov     rbx, rdi
0x140006bfa  cmp     rdi, [rsp+2F0h+Block+8]
0x140006bff  jz      loc_140006CC2
0x140006c05  mov     rcx, [rbx]; Block
0x140006c08  call    _free_base
0x140006c0d  add     rbx, 8
0x140006c11  cmp     rbx, [rsp+2F0h+Block+8]
0x140006c16  jnz     short loc_140006C05
0x140006c18  jmp     loc_140006CC2
0x140006c1d  mov     rcx, rbx; hFindFile
0x140006c20  call    cs:FindClose
0x140006c26  mov     rdi, [rsp+2F0h+Block]
0x140006c2b  mov     rbx, rdi
0x140006c2e  cmp     rdi, [rsp+2F0h+Block+8]
0x140006c33  jz      loc_140006CC2
0x140006c39  mov     rcx, [rbx]; Block
0x140006c3c  call    _free_base
0x140006c41  add     rbx, 8
0x140006c45  cmp     rbx, [rsp+2F0h+Block+8]
0x140006c4a  jnz     short loc_140006C39
0x140006c4c  jmp     short loc_140006CC2
0x140006c4e  mov     r14, rsi
0x140006c51  mov     r13, r12
0x140006c54  sub     r14, rdi
0x140006c57  mov     rax, rdi
0x140006c5a  sar     r14, 3
0x140006c5e  inc     r14
0x140006c61  cmp     rdi, rsi
0x140006c64  jz      short loc_140006C86
0x140006c66  mov     rdx, [rax]
0x140006c69  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140006c6d  inc     rcx
0x140006c70  cmp     [rdx+rcx*2], r12w
0x140006c75  jnz     short loc_140006C6D
0x140006c77  inc     r13
0x140006c7a  add     rax, 8
0x140006c7e  add     r13, rcx
0x140006c81  cmp     rax, rsi
0x140006c84  jnz     short loc_140006C66
0x140006c86  mov     r8d, 2
0x140006c8c  mov     rdx, r13
0x140006c8f  mov     rcx, r14
0x140006c92  call    __acrt_allocate_buffer_for_argv
0x140006c97  mov     rbx, rax
0x140006c9a  test    rax, rax
0x140006c9d  jnz     short loc_140006CD1
0x140006c9f  xor     ecx, ecx; Block
0x140006ca1  call    _free_base
0x140006ca6  mov     rbx, rdi
0x140006ca9  cmp     rdi, rsi
0x140006cac  jz      short loc_140006CBF
0x140006cae  mov     rcx, [rbx]; Block
0x140006cb1  call    _free_base
0x140006cb6  add     rbx, 8
0x140006cba  cmp     rbx, rsi
0x140006cbd  jnz     short loc_140006CAE
0x140006cbf  or      esi, 0FFFFFFFFh
0x140006cc2  mov     rcx, rdi; Block
0x140006cc5  call    _free_base
0x140006cca  mov     eax, esi
0x140006ccc  jmp     loc_140006D74
0x140006cd1  lea     rcx, [rax+r14*8]
0x140006cd5  mov     r14, rdi
0x140006cd8  mov     [rsp+2F0h+var_2A8], rcx
0x140006cdd  mov     r12, rcx
0x140006ce0  cmp     rdi, rsi
0x140006ce3  jz      short loc_140006D42
0x140006ce5  sub     rax, rdi
0x140006ce8  mov     [rbp+1F0h+var_40], rax
0x140006cef  mov     r8, [r14]
0x140006cf2  or      r15, 0FFFFFFFFFFFFFFFFh
0x140006cf6  xor     eax, eax
0x140006cf8  inc     r15
0x140006cfb  cmp     [r8+r15*2], ax
0x140006d00  jnz     short loc_140006CF8
0x140006d02  mov     rax, r12
0x140006d05  inc     r15
0x140006d08  sub     rax, rcx
0x140006d0b  mov     rdx, r13
0x140006d0e  sar     rax, 1
0x140006d11  mov     r9, r15
0x140006d14  sub     rdx, rax
0x140006d17  mov     rcx, r12
0x140006d1a  call    sub_140006640
0x140006d1f  xor     ecx, ecx; Expression
0x140006d21  test    eax, eax
0x140006d23  jnz     short loc_140006D9E
0x140006d25  mov     rax, [rbp+1F0h+var_40]
0x140006d2c  mov     rcx, [rsp+2F0h+var_2A8]
0x140006d31  mov     [rax+r14], r12
0x140006d35  add     r14, 8
0x140006d39  lea     r12, [r12+r15*2]
0x140006d3d  cmp     r14, rsi
0x140006d40  jnz     short loc_140006CEF
0x140006d42  mov     rax, [rsp+2F0h+var_2A0]
0x140006d47  xor     ecx, ecx; Block
0x140006d49  mov     [rax], rbx
0x140006d4c  call    _free_base
0x140006d51  mov     rbx, rdi
0x140006d54  cmp     rdi, rsi
0x140006d57  jz      short loc_140006D6A
0x140006d59  mov     rcx, [rbx]; Block
0x140006d5c  call    _free_base
0x140006d61  add     rbx, 8
0x140006d65  cmp     rbx, rsi
0x140006d68  jnz     short loc_140006D59
0x140006d6a  mov     rcx, rdi; Block
0x140006d6d  call    _free_base
0x140006d72  xor     eax, eax
0x140006d74  mov     rcx, [rbp+1F0h+var_38]
0x140006d7b  xor     rcx, rsp; StackCookie
0x140006d7e  call    __security_check_cookie
0x140006d83  mov     rbx, [rsp+2F0h+arg_10]
0x140006d8b  add     rsp, 2C0h
0x140006d92  pop     r15
0x140006d94  pop     r14
0x140006d96  pop     r13
0x140006d98  pop     r12
0x140006d9a  pop     rdi
0x140006d9b  pop     rsi
0x140006d9c  pop     rbp
0x140006d9d  retn
0x140006d9e  xor     r9d, r9d; LineNo
0x140006da1  mov     [rsp+2F0h+lpSearchFilter], rcx; Reserved
0x140006da6  xor     r8d, r8d; FileName
0x140006da9  xor     edx, edx; FunctionName
0x140006dab  call    _invoke_watson
```
