# common_expand_argv_wildcards<wchar_t>(wchar_t * * const,wchar_t * * * const)

- ea: `0x140023604`
- end: `0x140023a01`
- name: `??$common_expand_argv_wildcards@_W@@YAHQEAPEA_WQEAPEAPEA_W@Z`
- size: `1021`
- prototype: `__int64 __fastcall(const wchar_t **, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140023b8c`

## callees

- `0x1400046cc`
- `0x14000471c`
- `0x140004958`
- `0x14000fa6c`
- `0x1400107c4`
- `0x1400147e8`
- `0x14001bf00`
- `0x14001e2d0`
- `0x140022648`
- `0x140023050`
- `0x140023604`
- `0x140023a04`

## import_xrefs

- `KERNEL32!FindNextFileW` at `0x1400237f5`
- `KERNEL32!FindNextFileW` at `0x1400237f5`
- `KERNEL32!FindClose` at `0x140023832`
- `KERNEL32!FindClose` at `0x140023870`
- `KERNEL32!FindClose` at `0x140023832`
- `KERNEL32!FindClose` at `0x140023870`
- `KERNEL32!FindFirstFileExW` at `0x14002376c`
- `KERNEL32!FindFirstFileExW` at `0x14002376c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall common_expand_argv_wildcards<wchar_t>(const wchar_t **a1, __int64 *a2)
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
  size_t v13; // r13
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
  size_t v27; // r15
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
          DWORD2(v5) = copy_and_add_argument_to_buffer<wchar_t>(v8, 0, 0);
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
              DWORD2(v5) = copy_and_add_argument_to_buffer<wchar_t>(FindFileData.cFileName, v8, v13);
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
            sub_140023050(8 * v15, -v15, 8, unknown_libname_76);
          FindClose(FirstFile);
        }
      }
      else
      {
        *(_QWORD *)&v5 = 0;
        DWORD2(v5) = copy_and_add_argument_to_buffer<wchar_t>(*v2, 0, 0);
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
    *(_DWORD *)sub_14000FA6C() = 22;
    invalid_parameter_noinfo();
    return 22;
  }
}

```

## disassembly

```asm
0x140023604  mov     [rsp-8+arg_10], rbx
0x140023609  push    rbp
0x14002360a  push    rsi
0x14002360b  push    rdi
0x14002360c  push    r12
0x14002360e  push    r13
0x140023610  push    r14
0x140023612  push    r15
0x140023614  lea     rbp, [rsp-1C0h]
0x14002361c  sub     rsp, 2C0h
0x140023623  mov     rax, cs:__security_cookie
0x14002362a  xor     rax, rsp
0x14002362d  mov     [rbp+1F0h+var_38], rax
0x140023634  xor     r12d, r12d
0x140023637  mov     [rsp+2F0h+var_2A0], rdx
0x14002363c  mov     r15, rcx
0x14002363f  test    rdx, rdx
0x140023642  jnz     short loc_14002365C
0x140023644  call    sub_14000FA6C
0x140023649  lea     ebx, [r12+16h]
0x14002364e  mov     [rax], ebx
0x140023650  call    _invalid_parameter_noinfo
0x140023655  mov     eax, ebx
0x140023657  jmp     loc_1400239C4
0x14002365c  xorps   xmm0, xmm0
0x14002365f  mov     [rdx], r12
0x140023662  mov     rax, [rcx]
0x140023665  movdqu  xmmword ptr [rsp+2F0h+Block], xmm0
0x14002366b  mov     rsi, [rsp+2F0h+Block+8]
0x140023670  mov     rdi, [rsp+2F0h+Block]
0x140023675  mov     [rsp+2F0h+var_2B0], r12
0x14002367a  test    rax, rax
0x14002367d  jz      loc_14002389E
0x140023683  lea     rdx, [rbp+1F0h+Control]; Control
0x14002368a  mov     dword ptr [rbp+1F0h+Control], 3F002Ah
0x140023694  mov     rcx, rax; Str
0x140023697  mov     [rbp+1F0h+Control+4], r12w
0x14002369f  mov     rbx, 200000000801h
0x1400236a9  call    wcspbrk
0x1400236ae  mov     r14, [r15]
0x1400236b1  mov     rcx, rax
0x1400236b4  test    rax, rax
0x1400236b7  jnz     short loc_1400236E4
0x1400236b9  lea     r9, [rsp+2F0h+Block]
0x1400236be  xor     r8d, r8d; MaxCount
0x1400236c1  xor     edx, edx; wchar_t *
0x1400236c3  mov     rcx, r14; Src
0x1400236c6  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x1400236cb  mov     rdi, [rsp+2F0h+Block]
0x1400236d0  mov     esi, eax
0x1400236d2  test    eax, eax
0x1400236d4  jnz     loc_140023847
0x1400236da  mov     rsi, [rsp+2F0h+Block+8]
0x1400236df  jmp     loc_14002383B
0x1400236e4  cmp     rax, r14
0x1400236e7  jz      short loc_140023708
0x1400236e9  movzx   eax, word ptr [rcx]
0x1400236ec  sub     ax, 2Fh ; '/'
0x1400236f0  cmp     ax, 2Dh ; '-'
0x1400236f4  ja      short loc_1400236FF
0x1400236f6  movzx   eax, ax
0x1400236f9  bt      rbx, rax
0x1400236fd  jb      short loc_140023708
0x1400236ff  sub     rcx, 2
0x140023703  cmp     rcx, r14
0x140023706  jnz     short loc_1400236E9
0x140023708  movzx   edx, word ptr [rcx]
0x14002370b  cmp     dx, 3Ah ; ':'
0x14002370f  jnz     short loc_14002371A
0x140023711  lea     rax, [r14+2]
0x140023715  cmp     rcx, rax
0x140023718  jnz     short loc_14002377B
0x14002371a  sub     dx, 2Fh ; '/'
0x14002371e  cmp     dx, 2Dh ; '-'
0x140023722  ja      short loc_14002372F
0x140023724  movzx   eax, dx
0x140023727  bt      rbx, rax
0x14002372b  mov     al, 1
0x14002372d  jb      short loc_140023732
0x14002372f  mov     al, r12b
0x140023732  sub     rcx, r14
0x140023735  mov     r8d, 250h; Size
0x14002373b  sar     rcx, 1
0x14002373e  inc     rcx
0x140023741  neg     al
0x140023743  sbb     r13, r13
0x140023746  xor     edx, edx; Val
0x140023748  and     r13, rcx
0x14002374b  lea     rcx, [rsp+2F0h+FindFileData]; Dst
0x140023750  call    memset
0x140023755  xor     r9d, r9d; fSearchOp
0x140023758  mov     [rsp+2F0h+dwAdditionalFlags], r12d; dwAdditionalFlags
0x14002375d  lea     r8, [rsp+2F0h+FindFileData]; lpFindFileData
0x140023762  mov     [rsp+2F0h+lpSearchFilter], r12; lpSearchFilter
0x140023767  xor     edx, edx; fInfoLevelId
0x140023769  mov     rcx, r14; lpFileName
0x14002376c  call    cs:FindFirstFileExW
0x140023772  mov     rbx, rax
0x140023775  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140023779  jnz     short loc_1400237A7
0x14002377b  lea     r9, [rsp+2F0h+Block]
0x140023780  mov     r8, r12; MaxCount
0x140023783  mov     rdx, r12; wchar_t *
0x140023786  mov     rcx, r14; Src
0x140023789  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x14002378e  mov     esi, eax
0x140023790  test    eax, eax
0x140023792  jnz     loc_140023876
0x140023798  mov     rsi, [rsp+2F0h+Block+8]
0x14002379d  mov     rdi, [rsp+2F0h+Block]
0x1400237a2  jmp     loc_14002383B
0x1400237a7  sub     rsi, rdi
0x1400237aa  sar     rsi, 3
0x1400237ae  mov     r12, rsi
0x1400237b1  xor     edi, edi
0x1400237b3  cmp     [rbp+1F0h+Src], 2Eh ; '.'
0x1400237b8  jnz     short loc_1400237CF
0x1400237ba  movzx   eax, [rbp+1F0h+var_262]
0x1400237be  test    ax, ax
0x1400237c1  jz      short loc_1400237ED
0x1400237c3  cmp     ax, 2Eh ; '.'
0x1400237c7  jnz     short loc_1400237CF
0x1400237c9  cmp     [rbp+1F0h+var_260], di
0x1400237cd  jz      short loc_1400237ED
0x1400237cf  lea     r9, [rsp+2F0h+Block]
0x1400237d4  mov     r8, r13; MaxCount
0x1400237d7  mov     rdx, r14; wchar_t *
0x1400237da  lea     rcx, [rbp+1F0h+Src]; Src
0x1400237de  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQEB_W0_KAEAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x1400237e3  mov     esi, eax
0x1400237e5  test    eax, eax
0x1400237e7  jnz     loc_14002386D
0x1400237ed  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x1400237f2  mov     rcx, rbx; hFindFile
0x1400237f5  call    cs:FindNextFileW
0x1400237fb  test    eax, eax
0x1400237fd  jnz     short loc_1400237B3
0x1400237ff  mov     rsi, [rsp+2F0h+Block+8]
0x140023804  mov     rdi, [rsp+2F0h+Block]
0x140023809  mov     rdx, rsi
0x14002380c  sub     rdx, rdi
0x14002380f  sar     rdx, 3
0x140023813  cmp     r12, rdx
0x140023816  jz      short loc_14002382F
0x140023818  sub     rdx, r12
0x14002381b  lea     rcx, [rdi+r12*8]
0x14002381f  lea     r9, unknown_libname_76; Microsoft VisualC 64bit universal runtime
0x140023826  lea     r8d, [rax+8]
0x14002382a  call    sub_140023050
0x14002382f  mov     rcx, rbx; hFindFile
0x140023832  call    cs:FindClose
0x140023838  xor     r12d, r12d
0x14002383b  add     r15, 8
0x14002383f  mov     rax, [r15]
0x140023842  jmp     loc_14002367A
0x140023847  mov     rbx, rdi
0x14002384a  cmp     rdi, [rsp+2F0h+Block+8]
0x14002384f  jz      loc_140023912
0x140023855  mov     rcx, [rbx]; Block
0x140023858  call    _free_base
0x14002385d  add     rbx, 8
0x140023861  cmp     rbx, [rsp+2F0h+Block+8]
0x140023866  jnz     short loc_140023855
0x140023868  jmp     loc_140023912
0x14002386d  mov     rcx, rbx; hFindFile
0x140023870  call    cs:FindClose
0x140023876  mov     rdi, [rsp+2F0h+Block]
0x14002387b  mov     rbx, rdi
0x14002387e  cmp     rdi, [rsp+2F0h+Block+8]
0x140023883  jz      loc_140023912
0x140023889  mov     rcx, [rbx]; Block
0x14002388c  call    _free_base
0x140023891  add     rbx, 8
0x140023895  cmp     rbx, [rsp+2F0h+Block+8]
0x14002389a  jnz     short loc_140023889
0x14002389c  jmp     short loc_140023912
0x14002389e  mov     r14, rsi
0x1400238a1  mov     r13, r12
0x1400238a4  sub     r14, rdi
0x1400238a7  mov     rax, rdi
0x1400238aa  sar     r14, 3
0x1400238ae  inc     r14
0x1400238b1  cmp     rdi, rsi
0x1400238b4  jz      short loc_1400238D6
0x1400238b6  mov     rdx, [rax]
0x1400238b9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400238bd  inc     rcx
0x1400238c0  cmp     [rdx+rcx*2], r12w
0x1400238c5  jnz     short loc_1400238BD
0x1400238c7  inc     r13
0x1400238ca  add     rax, 8
0x1400238ce  add     r13, rcx
0x1400238d1  cmp     rax, rsi
0x1400238d4  jnz     short loc_1400238B6
0x1400238d6  mov     r8d, 2
0x1400238dc  mov     rdx, r13
0x1400238df  mov     rcx, r14
0x1400238e2  call    __acrt_allocate_buffer_for_argv
0x1400238e7  mov     rbx, rax
0x1400238ea  test    rax, rax
0x1400238ed  jnz     short loc_140023921
0x1400238ef  xor     ecx, ecx; Block
0x1400238f1  call    _free_base
0x1400238f6  mov     rbx, rdi
0x1400238f9  cmp     rdi, rsi
0x1400238fc  jz      short loc_14002390F
0x1400238fe  mov     rcx, [rbx]; Block
0x140023901  call    _free_base
0x140023906  add     rbx, 8
0x14002390a  cmp     rbx, rsi
0x14002390d  jnz     short loc_1400238FE
0x14002390f  or      esi, 0FFFFFFFFh
0x140023912  mov     rcx, rdi; Block
0x140023915  call    _free_base
0x14002391a  mov     eax, esi
0x14002391c  jmp     loc_1400239C4
0x140023921  lea     rcx, [rax+r14*8]
0x140023925  mov     r14, rdi
0x140023928  mov     [rsp+2F0h+var_2A8], rcx
0x14002392d  mov     r12, rcx
0x140023930  cmp     rdi, rsi
0x140023933  jz      short loc_140023992
0x140023935  sub     rax, rdi
0x140023938  mov     qword ptr [rbp+1F0h+Control], rax
0x14002393f  mov     r8, [r14]; Src
0x140023942  or      r15, 0FFFFFFFFFFFFFFFFh
0x140023946  xor     eax, eax
0x140023948  inc     r15
0x14002394b  cmp     [r8+r15*2], ax
0x140023950  jnz     short loc_140023948
0x140023952  mov     rax, r12
0x140023955  inc     r15
0x140023958  sub     rax, rcx
0x14002395b  mov     rdx, r13
0x14002395e  sar     rax, 1
0x140023961  mov     r9, r15; MaxCount
0x140023964  sub     rdx, rax; DstSizeInChars
0x140023967  mov     rcx, r12; Dst
0x14002396a  call    wcsncpy_s
0x14002396f  xor     ecx, ecx; Expression
0x140023971  test    eax, eax
0x140023973  jnz     short loc_1400239EE
0x140023975  mov     rax, qword ptr [rbp+1F0h+Control]
0x14002397c  mov     rcx, [rsp+2F0h+var_2A8]
0x140023981  mov     [rax+r14], r12
0x140023985  add     r14, 8
0x140023989  lea     r12, [r12+r15*2]
0x14002398d  cmp     r14, rsi
0x140023990  jnz     short loc_14002393F
0x140023992  mov     rax, [rsp+2F0h+var_2A0]
0x140023997  xor     ecx, ecx; Block
0x140023999  mov     [rax], rbx
0x14002399c  call    _free_base
0x1400239a1  mov     rbx, rdi
0x1400239a4  cmp     rdi, rsi
0x1400239a7  jz      short loc_1400239BA
0x1400239a9  mov     rcx, [rbx]; Block
0x1400239ac  call    _free_base
0x1400239b1  add     rbx, 8
0x1400239b5  cmp     rbx, rsi
0x1400239b8  jnz     short loc_1400239A9
0x1400239ba  mov     rcx, rdi; Block
0x1400239bd  call    _free_base
0x1400239c2  xor     eax, eax
0x1400239c4  mov     rcx, [rbp+1F0h+var_38]
0x1400239cb  xor     rcx, rsp; StackCookie
0x1400239ce  call    __security_check_cookie
0x1400239d3  mov     rbx, [rsp+2F0h+arg_10]
0x1400239db  add     rsp, 2C0h
0x1400239e2  pop     r15
0x1400239e4  pop     r14
0x1400239e6  pop     r13
0x1400239e8  pop     r12
0x1400239ea  pop     rdi
0x1400239eb  pop     rsi
0x1400239ec  pop     rbp
0x1400239ed  retn
0x1400239ee  xor     r9d, r9d; LineNo
0x1400239f1  mov     [rsp+2F0h+lpSearchFilter], rcx; Reserved
0x1400239f6  xor     r8d, r8d; FileName
0x1400239f9  xor     edx, edx; FunctionName
0x1400239fb  call    _invoke_watson
```
