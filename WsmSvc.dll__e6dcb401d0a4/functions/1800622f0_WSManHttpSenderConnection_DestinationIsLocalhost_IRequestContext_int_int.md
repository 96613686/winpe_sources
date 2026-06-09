# WSManHttpSenderConnection::DestinationIsLocalhost(IRequestContext *,int *,int *)

- ea: `0x1800622f0`
- end: `0x180062617`
- name: `?DestinationIsLocalhost@WSManHttpSenderConnection@@AEAAKPEAVIRequestContext@@PEAH1@Z`
- size: `807`
- prototype: `unsigned int(WSManHttpSenderConnection *__hidden this, struct IRequestContext *, int *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180060afc`

## callees

- `0x180005d10`
- `0x1800622f0`
- `0x180079b98`
- `0x1801123a8`
- `0x18011a6d4`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800623d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006245c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800624d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800625ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800623d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006245c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800624d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800625ad`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800623c7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062452`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800624cd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800625a3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800623c7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180062452`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800624cd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800625a3`

## pseudocode

```c
__int64 __fastcall WSManHttpSenderConnection::DestinationIsLocalhost(
        WSManHttpSenderConnection *this,
        struct IRequestContext *a2,
        int *a3,
        int *a4)
{
  const unsigned __int16 *v8; // r8
  __int64 v9; // rdx
  unsigned int v10; // ebx
  int v12; // eax
  __int64 LastError; // rdi
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  int v17; // eax
  const WCHAR *ComputerNameW; // rcx
  unsigned int v19; // eax
  int v20; // eax
  struct IRequestContext *lpString2; // [rsp+20h] [rbp-48h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
  if ( !a2 )
  {
    lpString2 = 0;
    v8 = L"1791";
    v9 = 1791;
LABEL_6:
    v10 = 1359;
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", v9, v8, 0x54Fu, lpString2);
    return v10;
  }
  if ( !a3 )
  {
    lpString2 = a2;
    v8 = L"1792";
    v9 = 1792;
    goto LABEL_6;
  }
  *a4 = 0;
  v12 = CompareStringW(
          0x7Fu,
          1u,
          *(PCNZWCH *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 536LL),
          -1,
          L"localhost",
          -1);
  if ( !v12 )
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, LastError);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return (unsigned int)LastError;
    v15 = 102;
LABEL_14:
    WPP_SF_d(v14[2], v15, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, (unsigned int)LastError);
    return (unsigned int)LastError;
  }
  if ( v12 == 2 )
    goto LABEL_38;
  v16 = CompareStringW(
          0x7Fu,
          1u,
          *(PCNZWCH *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 536LL),
          -1,
          L"127.0.0.1",
          -1);
  if ( !v16 )
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, LastError);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return (unsigned int)LastError;
    v15 = 103;
    goto LABEL_14;
  }
  if ( v16 == 2 )
    goto LABEL_38;
  v17 = CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 536LL), -1, L"[::1]", -1);
  if ( !v17 )
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, LastError);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return (unsigned int)LastError;
    v15 = 104;
    goto LABEL_14;
  }
  if ( v17 == 2 )
  {
LABEL_38:
    *a3 = 1;
  }
  else
  {
    ComputerNameW = GetComputerNameW(a2);
    if ( !ComputerNameW )
    {
      v19 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
      v10 = v19;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, v19);
      return v10;
    }
    v20 = CompareStringW(
            0x7Fu,
            1u,
            *(PCNZWCH *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 536LL),
            -1,
            ComputerNameW,
            -1);
    if ( !v20 )
    {
      LastError = GetLastError();
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, LastError);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        return (unsigned int)LastError;
      v15 = 106;
      goto LABEL_14;
    }
    if ( v20 == 2 )
    {
      *a3 = 1;
      *a4 = 1;
    }
    else
    {
      *a3 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800622f0  push    rbx
0x1800622f2  push    rsi
0x1800622f3  push    rdi
0x1800622f4  push    r12
0x1800622f6  push    r13
0x1800622f8  push    r14
0x1800622fa  push    r15
0x1800622fc  sub     rsp, 30h
0x180062300  mov     r14, r9
0x180062303  mov     rdi, r8
0x180062306  mov     rbx, rdx
0x180062309  mov     rsi, rcx
0x18006230c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062313  lea     r13, WPP_GLOBAL_Control
0x18006231a  lea     r15, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x180062321  cmp     rcx, r13
0x180062324  jz      short loc_180062343
0x180062326  test    dword ptr [rcx+1Ch], 400h
0x18006232d  jz      short loc_180062343
0x18006232f  mov     rcx, [rcx+10h]
0x180062333  mov     edx, 65h ; 'e'
0x180062338  mov     r9, rsi
0x18006233b  mov     r8, r15
0x18006233e  call    WPP_SF_q
0x180062343  test    rbx, rbx
0x180062346  jnz     short loc_180062374
0x180062348  mov     [rsp+68h+lpString2], rbx; struct IRequestContext *
0x18006234d  lea     r8, a1791; "1791"
0x180062354  mov     edx, 6FFh; unsigned int
0x180062359  mov     ebx, 54Fh
0x18006235e  lea     rcx, aOnecoreAdminWm_105; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x180062365  mov     r9d, ebx; unsigned int
0x180062368  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18006236d  mov     eax, ebx
0x18006236f  jmp     loc_180062607
0x180062374  test    rdi, rdi
0x180062377  jnz     short loc_18006238C
0x180062379  mov     [rsp+68h+lpString2], rbx
0x18006237e  lea     r8, a1792; "1792"
0x180062385  mov     edx, 700h
0x18006238a  jmp     short loc_180062359
0x18006238c  or      ecx, 0FFFFFFFFh
0x18006238f  mov     dword ptr [r14], 0
0x180062396  mov     rax, [rsi+28h]
0x18006239a  mov     r9d, ecx; cchCount1
0x18006239d  mov     [rsp+68h+cchCount2], ecx; cchCount2
0x1800623a1  lea     r12d, [rcx+2]
0x1800623a5  mov     r8, [rax+80h]
0x1800623ac  lea     ecx, [r12+7Eh]; Locale
0x1800623b1  lea     rax, aLocalhost; "localhost"
0x1800623b8  mov     edx, r12d; dwCmpFlags
0x1800623bb  mov     [rsp+68h+lpString2], rax; lpString2
0x1800623c0  mov     r8, [r8+218h]; lpString1
0x1800623c7  call    cs:__imp_CompareStringW
0x1800623cd  test    eax, eax
0x1800623cf  jnz     short loc_18006241A
0x1800623d1  call    cs:__imp_GetLastError
0x1800623d7  mov     rcx, [rbx]
0x1800623da  mov     edi, eax
0x1800623dc  mov     edx, edi
0x1800623de  mov     rax, [rcx+48h]
0x1800623e2  mov     rcx, rbx
0x1800623e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800623ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800623f1  cmp     rcx, r13
0x1800623f4  jz      short loc_180062413
0x1800623f6  test    dword ptr [rcx+1Ch], 200h
0x1800623fd  jz      short loc_180062413
0x1800623ff  lea     edx, [r12+65h]
0x180062404  mov     rcx, [rcx+10h]
0x180062408  mov     r9d, edi
0x18006240b  mov     r8, r15
0x18006240e  call    WPP_SF_d
0x180062413  mov     eax, edi
0x180062415  jmp     loc_180062607
0x18006241a  cmp     eax, 2
0x18006241d  jz      loc_180062602
0x180062423  mov     rax, [rsi+28h]
0x180062427  or      r9d, 0FFFFFFFFh; cchCount1
0x18006242b  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x180062430  mov     edx, r12d; dwCmpFlags
0x180062433  mov     ecx, 7Fh; Locale
0x180062438  mov     r8, [rax+80h]
0x18006243f  lea     rax, pswzServerName; "127.0.0.1"
0x180062446  mov     [rsp+68h+lpString2], rax; lpString2
0x18006244b  mov     r8, [r8+218h]; lpString1
0x180062452  call    cs:__imp_CompareStringW
0x180062458  test    eax, eax
0x18006245a  jnz     short loc_180062494
0x18006245c  call    cs:__imp_GetLastError
0x180062462  mov     rcx, [rbx]
0x180062465  mov     edi, eax
0x180062467  mov     edx, edi
0x180062469  mov     rax, [rcx+48h]
0x18006246d  mov     rcx, rbx
0x180062470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062475  mov     rcx, cs:WPP_GLOBAL_Control
0x18006247c  cmp     rcx, r13
0x18006247f  jz      short loc_180062413
0x180062481  test    dword ptr [rcx+1Ch], 200h
0x180062488  jz      short loc_180062413
0x18006248a  mov     edx, 67h ; 'g'
0x18006248f  jmp     loc_180062404
0x180062494  cmp     eax, 2
0x180062497  jz      loc_180062602
0x18006249d  mov     rax, [rsi+28h]
0x1800624a1  or      ecx, 0FFFFFFFFh
0x1800624a4  mov     [rsp+68h+cchCount2], ecx; cchCount2
0x1800624a8  mov     r9d, ecx; cchCount1
0x1800624ab  mov     edx, r12d; dwCmpFlags
0x1800624ae  mov     ecx, 7Fh; Locale
0x1800624b3  mov     r8, [rax+80h]
0x1800624ba  lea     rax, a1_0; "[::1]"
0x1800624c1  mov     [rsp+68h+lpString2], rax; lpString2
0x1800624c6  mov     r8, [r8+218h]; lpString1
0x1800624cd  call    cs:__imp_CompareStringW
0x1800624d3  test    eax, eax
0x1800624d5  jnz     short loc_180062517
0x1800624d7  call    cs:__imp_GetLastError
0x1800624dd  mov     rcx, [rbx]
0x1800624e0  mov     edi, eax
0x1800624e2  mov     edx, edi
0x1800624e4  mov     rax, [rcx+48h]
0x1800624e8  mov     rcx, rbx
0x1800624eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800624f7  cmp     rcx, r13
0x1800624fa  jz      loc_180062413
0x180062500  test    dword ptr [rcx+1Ch], 200h
0x180062507  jz      loc_180062413
0x18006250d  mov     edx, 68h ; 'h'
0x180062512  jmp     loc_180062404
0x180062517  cmp     eax, 2
0x18006251a  jz      loc_180062602
0x180062520  mov     rcx, rbx; struct IRequestContext *
0x180062523  call    ?GetComputerNameW@@YAPEBGAEAVIRequestContext@@@Z; GetComputerNameW(IRequestContext &)
0x180062528  mov     rcx, rax
0x18006252b  test    rax, rax
0x18006252e  jnz     short loc_18006257A
0x180062530  mov     rax, [rbx]
0x180062533  mov     rcx, rbx
0x180062536  mov     rax, [rax+98h]
0x18006253d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062542  mov     ebx, eax
0x180062544  mov     rcx, cs:WPP_GLOBAL_Control
0x18006254b  cmp     rcx, r13
0x18006254e  jz      loc_18006236D
0x180062554  test    dword ptr [rcx+1Ch], 200h
0x18006255b  jz      loc_18006236D
0x180062561  mov     rcx, [rcx+10h]
0x180062565  mov     edx, 69h ; 'i'
0x18006256a  mov     r9d, eax
0x18006256d  mov     r8, r15
0x180062570  call    WPP_SF_d
0x180062575  jmp     loc_18006236D
0x18006257a  mov     rax, [rsi+28h]
0x18006257e  mov     edx, r12d; dwCmpFlags
0x180062581  mov     r8, [rax+80h]
0x180062588  or      eax, 0FFFFFFFFh
0x18006258b  mov     [rsp+68h+cchCount2], eax; cchCount2
0x18006258f  mov     r9d, eax; cchCount1
0x180062592  mov     [rsp+68h+lpString2], rcx; lpString2
0x180062597  mov     ecx, 7Fh; Locale
0x18006259c  mov     r8, [r8+218h]; lpString1
0x1800625a3  call    cs:__imp_CompareStringW
0x1800625a9  test    eax, eax
0x1800625ab  jnz     short loc_1800625ED
0x1800625ad  call    cs:__imp_GetLastError
0x1800625b3  mov     rcx, [rbx]
0x1800625b6  mov     edi, eax
0x1800625b8  mov     edx, edi
0x1800625ba  mov     rax, [rcx+48h]
0x1800625be  mov     rcx, rbx
0x1800625c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800625cd  cmp     rcx, r13
0x1800625d0  jz      loc_180062413
0x1800625d6  test    dword ptr [rcx+1Ch], 200h
0x1800625dd  jz      loc_180062413
0x1800625e3  mov     edx, 6Ah ; 'j'
0x1800625e8  jmp     loc_180062404
0x1800625ed  cmp     eax, 2
0x1800625f0  jnz     short loc_1800625FA
0x1800625f2  mov     [rdi], r12d
0x1800625f5  mov     [r14], r12d
0x1800625f8  jmp     short loc_180062605
0x1800625fa  mov     dword ptr [rdi], 0
0x180062600  jmp     short loc_180062605
0x180062602  mov     [rdi], r12d
0x180062605  xor     eax, eax
0x180062607  add     rsp, 30h
0x18006260b  pop     r15
0x18006260d  pop     r14
0x18006260f  pop     r13
0x180062611  pop     r12
0x180062613  pop     rdi
0x180062614  pop     rsi
0x180062615  pop     rbx
0x180062616  retn
```
