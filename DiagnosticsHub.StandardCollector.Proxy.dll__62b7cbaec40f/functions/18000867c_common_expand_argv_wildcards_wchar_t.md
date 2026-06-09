# common_expand_argv_wildcards_wchar_t_

- ea: `0x18000867c`
- end: `0x180008a79`
- name: `common_expand_argv_wildcards_wchar_t_`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180009d8c`

## callees

- `0x180002810`
- `0x180004ca0`
- `0x180007c00`
- `0x180007c50`
- `0x180007ee8`
- `0x180008040`
- `0x18000867c`
- `0x180008c00`
- `0x180012820`
- `0x180012d00`
- `0x180012e50`
- `0x180060550`

## import_xrefs

- `KERNEL32!FindClose` at `0x1800088aa`
- `KERNEL32!FindClose` at `0x1800088e8`
- `KERNEL32!FindClose` at `0x1800088aa`
- `KERNEL32!FindClose` at `0x1800088e8`
- `KERNEL32!FindFirstFileExW` at `0x1800087e4`
- `KERNEL32!FindFirstFileExW` at `0x1800087e4`
- `KERNEL32!FindNextFileW` at `0x18000886d`
- `KERNEL32!FindNextFileW` at `0x18000886d`

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
0x18000867c  mov     [rsp-8+arg_10], rbx
0x180008681  push    rbp
0x180008682  push    rsi
0x180008683  push    rdi
0x180008684  push    r12
0x180008686  push    r13
0x180008688  push    r14
0x18000868a  push    r15
0x18000868c  lea     rbp, [rsp-1C0h]
0x180008694  sub     rsp, 2C0h
0x18000869b  mov     rax, cs:__security_cookie
0x1800086a2  xor     rax, rsp
0x1800086a5  mov     [rbp+1F0h+var_38], rax
0x1800086ac  xor     r12d, r12d
0x1800086af  mov     [rsp+2F0h+var_2A0], rdx
0x1800086b4  mov     r15, rcx
0x1800086b7  test    rdx, rdx
0x1800086ba  jnz     short loc_1800086D4
0x1800086bc  call    _errno
0x1800086c1  lea     ebx, [r12+16h]
0x1800086c6  mov     [rax], ebx
0x1800086c8  call    _invalid_parameter_noinfo
0x1800086cd  mov     eax, ebx
0x1800086cf  jmp     loc_180008A3C
0x1800086d4  xorps   xmm0, xmm0
0x1800086d7  mov     [rdx], r12
0x1800086da  mov     rax, [rcx]
0x1800086dd  movdqu  xmmword ptr [rsp+2F0h+Block], xmm0
0x1800086e3  mov     rsi, [rsp+2F0h+Block+8]
0x1800086e8  mov     rdi, [rsp+2F0h+Block]
0x1800086ed  mov     [rsp+2F0h+var_2B0], r12
0x1800086f2  test    rax, rax
0x1800086f5  jz      loc_180008916
0x1800086fb  lea     rdx, [rbp+1F0h+Control]; Control
0x180008702  mov     dword ptr [rbp+1F0h+Control], 3F002Ah
0x18000870c  mov     rcx, rax; String
0x18000870f  mov     [rbp+1F0h+Control+4], r12w
0x180008717  mov     rbx, 200000000801h
0x180008721  call    wcspbrk
0x180008726  mov     r14, [r15]
0x180008729  mov     rcx, rax
0x18000872c  test    rax, rax
0x18000872f  jnz     short loc_18000875C
0x180008731  lea     r9, [rsp+2F0h+Block]
0x180008736  xor     r8d, r8d; MaxCount
0x180008739  xor     edx, edx; wchar_t *
0x18000873b  mov     rcx, r14; Source
0x18000873e  call    copy_and_add_argument_to_buffer_wchar_t_
0x180008743  mov     rdi, [rsp+2F0h+Block]
0x180008748  mov     esi, eax
0x18000874a  test    eax, eax
0x18000874c  jnz     loc_1800088BF
0x180008752  mov     rsi, [rsp+2F0h+Block+8]
0x180008757  jmp     loc_1800088B3
0x18000875c  cmp     rax, r14
0x18000875f  jz      short loc_180008780
0x180008761  movzx   eax, word ptr [rcx]
0x180008764  sub     ax, 2Fh ; '/'
0x180008768  cmp     ax, 2Dh ; '-'
0x18000876c  ja      short loc_180008777
0x18000876e  movzx   eax, ax
0x180008771  bt      rbx, rax
0x180008775  jb      short loc_180008780
0x180008777  sub     rcx, 2
0x18000877b  cmp     rcx, r14
0x18000877e  jnz     short loc_180008761
0x180008780  movzx   edx, word ptr [rcx]
0x180008783  cmp     dx, 3Ah ; ':'
0x180008787  jnz     short loc_180008792
0x180008789  lea     rax, [r14+2]
0x18000878d  cmp     rcx, rax
0x180008790  jnz     short loc_1800087F3
0x180008792  sub     dx, 2Fh ; '/'
0x180008796  cmp     dx, 2Dh ; '-'
0x18000879a  ja      short loc_1800087A7
0x18000879c  movzx   eax, dx
0x18000879f  bt      rbx, rax
0x1800087a3  mov     al, 1
0x1800087a5  jb      short loc_1800087AA
0x1800087a7  mov     al, r12b
0x1800087aa  sub     rcx, r14
0x1800087ad  mov     r8d, 250h; Size
0x1800087b3  sar     rcx, 1
0x1800087b6  inc     rcx
0x1800087b9  neg     al
0x1800087bb  sbb     r13, r13
0x1800087be  xor     edx, edx; Val
0x1800087c0  and     r13, rcx
0x1800087c3  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x1800087c8  call    memset
0x1800087cd  xor     r9d, r9d; fSearchOp
0x1800087d0  mov     [rsp+2F0h+dwAdditionalFlags], r12d; dwAdditionalFlags
0x1800087d5  lea     r8, [rsp+2F0h+FindFileData]; lpFindFileData
0x1800087da  mov     [rsp+2F0h+lpSearchFilter], r12; lpSearchFilter
0x1800087df  xor     edx, edx; fInfoLevelId
0x1800087e1  mov     rcx, r14; lpFileName
0x1800087e4  call    cs:__imp_FindFirstFileExW
0x1800087ea  mov     rbx, rax
0x1800087ed  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800087f1  jnz     short loc_18000881F
0x1800087f3  lea     r9, [rsp+2F0h+Block]
0x1800087f8  mov     r8, r12; MaxCount
0x1800087fb  mov     rdx, r12; wchar_t *
0x1800087fe  mov     rcx, r14; Source
0x180008801  call    copy_and_add_argument_to_buffer_wchar_t_
0x180008806  mov     esi, eax
0x180008808  test    eax, eax
0x18000880a  jnz     loc_1800088EE
0x180008810  mov     rsi, [rsp+2F0h+Block+8]
0x180008815  mov     rdi, [rsp+2F0h+Block]
0x18000881a  jmp     loc_1800088B3
0x18000881f  sub     rsi, rdi
0x180008822  sar     rsi, 3
0x180008826  mov     r12, rsi
0x180008829  xor     edi, edi
0x18000882b  cmp     [rbp+1F0h+Source], 2Eh ; '.'
0x180008830  jnz     short loc_180008847
0x180008832  movzx   eax, [rbp+1F0h+var_262]
0x180008836  test    ax, ax
0x180008839  jz      short loc_180008865
0x18000883b  cmp     ax, 2Eh ; '.'
0x18000883f  jnz     short loc_180008847
0x180008841  cmp     [rbp+1F0h+var_260], di
0x180008845  jz      short loc_180008865
0x180008847  lea     r9, [rsp+2F0h+Block]
0x18000884c  mov     r8, r13; MaxCount
0x18000884f  mov     rdx, r14; wchar_t *
0x180008852  lea     rcx, [rbp+1F0h+Source]; Source
0x180008856  call    copy_and_add_argument_to_buffer_wchar_t_
0x18000885b  mov     esi, eax
0x18000885d  test    eax, eax
0x18000885f  jnz     loc_1800088E5
0x180008865  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x18000886a  mov     rcx, rbx; hFindFile
0x18000886d  call    cs:__imp_FindNextFileW
0x180008873  test    eax, eax
0x180008875  jnz     short loc_18000882B
0x180008877  mov     rsi, [rsp+2F0h+Block+8]
0x18000887c  mov     rdi, [rsp+2F0h+Block]
0x180008881  mov     rdx, rsi
0x180008884  sub     rdx, rdi
0x180008887  sar     rdx, 3
0x18000888b  cmp     r12, rdx
0x18000888e  jz      short loc_1800088A7
0x180008890  sub     rdx, r12; NumOfElements
0x180008893  lea     rcx, [rdi+r12*8]; Base
0x180008897  lea     r9, _lambda_861af8918f661c876f88da8747958ced____lambda_invoker_cdecl_; CompareFunction
0x18000889e  lea     r8d, [rax+8]; SizeOfElements
0x1800088a2  call    qsort
0x1800088a7  mov     rcx, rbx; hFindFile
0x1800088aa  call    cs:__imp_FindClose
0x1800088b0  xor     r12d, r12d
0x1800088b3  add     r15, 8
0x1800088b7  mov     rax, [r15]
0x1800088ba  jmp     loc_1800086F2
0x1800088bf  mov     rbx, rdi
0x1800088c2  cmp     rdi, [rsp+2F0h+Block+8]
0x1800088c7  jz      loc_18000898A
0x1800088cd  mov     rcx, [rbx]; Block
0x1800088d0  call    _free_base
0x1800088d5  add     rbx, 8
0x1800088d9  cmp     rbx, [rsp+2F0h+Block+8]
0x1800088de  jnz     short loc_1800088CD
0x1800088e0  jmp     loc_18000898A
0x1800088e5  mov     rcx, rbx; hFindFile
0x1800088e8  call    cs:__imp_FindClose
0x1800088ee  mov     rdi, [rsp+2F0h+Block]
0x1800088f3  mov     rbx, rdi
0x1800088f6  cmp     rdi, [rsp+2F0h+Block+8]
0x1800088fb  jz      loc_18000898A
0x180008901  mov     rcx, [rbx]; Block
0x180008904  call    _free_base
0x180008909  add     rbx, 8
0x18000890d  cmp     rbx, [rsp+2F0h+Block+8]
0x180008912  jnz     short loc_180008901
0x180008914  jmp     short loc_18000898A
0x180008916  mov     r14, rsi
0x180008919  mov     r13, r12
0x18000891c  sub     r14, rdi
0x18000891f  mov     rax, rdi
0x180008922  sar     r14, 3
0x180008926  inc     r14
0x180008929  cmp     rdi, rsi
0x18000892c  jz      short loc_18000894E
0x18000892e  mov     rdx, [rax]
0x180008931  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008935  inc     rcx
0x180008938  cmp     [rdx+rcx*2], r12w
0x18000893d  jnz     short loc_180008935
0x18000893f  inc     r13
0x180008942  add     rax, 8
0x180008946  add     r13, rcx
0x180008949  cmp     rax, rsi
0x18000894c  jnz     short loc_18000892E
0x18000894e  mov     r8d, 2
0x180008954  mov     rdx, r13
0x180008957  mov     rcx, r14
0x18000895a  call    __acrt_allocate_buffer_for_argv
0x18000895f  mov     rbx, rax
0x180008962  test    rax, rax
0x180008965  jnz     short loc_180008999
0x180008967  xor     ecx, ecx; Block
0x180008969  call    _free_base
0x18000896e  mov     rbx, rdi
0x180008971  cmp     rdi, rsi
0x180008974  jz      short loc_180008987
0x180008976  mov     rcx, [rbx]; Block
0x180008979  call    _free_base
0x18000897e  add     rbx, 8
0x180008982  cmp     rbx, rsi
0x180008985  jnz     short loc_180008976
0x180008987  or      esi, 0FFFFFFFFh
0x18000898a  mov     rcx, rdi; Block
0x18000898d  call    _free_base
0x180008992  mov     eax, esi
0x180008994  jmp     loc_180008A3C
0x180008999  lea     rcx, [rax+r14*8]
0x18000899d  mov     r14, rdi
0x1800089a0  mov     [rsp+2F0h+var_2A8], rcx
0x1800089a5  mov     r12, rcx
0x1800089a8  cmp     rdi, rsi
0x1800089ab  jz      short loc_180008A0A
0x1800089ad  sub     rax, rdi
0x1800089b0  mov     qword ptr [rbp+1F0h+Control], rax
0x1800089b7  mov     r8, [r14]; Source
0x1800089ba  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800089be  xor     eax, eax
0x1800089c0  inc     r15
0x1800089c3  cmp     [r8+r15*2], ax
0x1800089c8  jnz     short loc_1800089C0
0x1800089ca  mov     rax, r12
0x1800089cd  inc     r15
0x1800089d0  sub     rax, rcx
0x1800089d3  mov     rdx, r13
0x1800089d6  sar     rax, 1
0x1800089d9  mov     r9, r15; MaxCount
0x1800089dc  sub     rdx, rax; SizeInWords
0x1800089df  mov     rcx, r12; Destination
0x1800089e2  call    wcsncpy_s
0x1800089e7  xor     ecx, ecx; Expression
0x1800089e9  test    eax, eax
0x1800089eb  jnz     short loc_180008A66
0x1800089ed  mov     rax, qword ptr [rbp+1F0h+Control]
0x1800089f4  mov     rcx, [rsp+2F0h+var_2A8]
0x1800089f9  mov     [rax+r14], r12
0x1800089fd  add     r14, 8
0x180008a01  lea     r12, [r12+r15*2]
0x180008a05  cmp     r14, rsi
0x180008a08  jnz     short loc_1800089B7
0x180008a0a  mov     rax, [rsp+2F0h+var_2A0]
0x180008a0f  xor     ecx, ecx; Block
0x180008a11  mov     [rax], rbx
0x180008a14  call    _free_base
0x180008a19  mov     rbx, rdi
0x180008a1c  cmp     rdi, rsi
0x180008a1f  jz      short loc_180008A32
0x180008a21  mov     rcx, [rbx]; Block
0x180008a24  call    _free_base
0x180008a29  add     rbx, 8
0x180008a2d  cmp     rbx, rsi
0x180008a30  jnz     short loc_180008A21
0x180008a32  mov     rcx, rdi; Block
0x180008a35  call    _free_base
0x180008a3a  xor     eax, eax
0x180008a3c  mov     rcx, [rbp+1F0h+var_38]
0x180008a43  xor     rcx, rsp; StackCookie
0x180008a46  call    __security_check_cookie
0x180008a4b  mov     rbx, [rsp+2F0h+arg_10]
0x180008a53  add     rsp, 2C0h
0x180008a5a  pop     r15
0x180008a5c  pop     r14
0x180008a5e  pop     r13
0x180008a60  pop     r12
0x180008a62  pop     rdi
0x180008a63  pop     rsi
0x180008a64  pop     rbp
0x180008a65  retn
0x180008a66  xor     r9d, r9d; LineNo
0x180008a69  mov     [rsp+2F0h+lpSearchFilter], rcx; Reserved
0x180008a6e  xor     r8d, r8d; FileName
0x180008a71  xor     edx, edx; FunctionName
0x180008a73  call    _invoke_watson
```
