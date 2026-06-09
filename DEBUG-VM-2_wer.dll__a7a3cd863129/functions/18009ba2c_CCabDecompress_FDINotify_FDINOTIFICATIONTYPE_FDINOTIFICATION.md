# CCabDecompress::FDINotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x18009ba2c`
- end: `0x18009bd59`
- name: `?FDINotify@CCabDecompress@@IEAA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `813`
- prototype: `__int64 __fastcall(CCabDecompress *__hidden this, enum FDINOTIFICATIONTYPE, struct FDINOTIFICATION *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18009bfa0`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18000bc10`
- `0x18000dad0`
- `0x180013730`
- `0x180014720`
- `0x18001fe24`
- `0x180076f44`
- `0x180098790`
- `0x18009b968`
- `0x18009b9f8`
- `0x18009ba2c`
- `0x18009bef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bc48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bc48`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009ba69`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009ba69`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009bc87`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009bc87`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009bc20`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009bc20`

## pseudocode

```c
_BOOL8 __fastcall CCabDecompress::FDINotify(HANDLE *this, enum FDINOTIFICATIONTYPE a2, struct FDINOTIFICATION *a3)
{
  __int64 v6; // rsi
  wchar_t *v7; // rcx
  __int64 v8; // rdx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  __int64 v12; // r8
  int v13; // eax
  int UniquePath; // eax
  HANDLE **v15; // rbx
  HANDLE *FileW; // rax
  DWORD LastError; // eax
  char v18; // al
  wchar_t *v19; // rcx
  _QWORD v21[4]; // [rsp+40h] [rbp-19h] BYREF
  LPCWSTR lpFileName[10]; // [rsp+60h] [rbp+7h] BYREF
  HANDLE **v23; // [rsp+D0h] [rbp+77h] BYREF

  v6 = -1;
  if ( !a3 || !a3->pv )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v8 = 65;
      goto LABEL_48;
    }
    return v6;
  }
  if ( !WaitForSingleObject(*this, 0) )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v8 = 66;
LABEL_48:
      WPP_SF_(*((_QWORD *)v7 + 2), v8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids);
      return v6;
    }
    return v6;
  }
  v9 = a2 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( !v11 )
        return CCabDecompress::static_FDIClose(a3->hf) == 0;
      if ( v11 != 1 )
        return 0;
      goto LABEL_42;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v21);
    v6 = 0;
    v21[1] = v21[0];
    v12 = -1;
    *(_WORD *)v21[0] = 0;
    do
      ++v12;
    while ( a3->psz1[v12] );
    v13 = tlx::_AppendMbcsImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(v21);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          WPP_79ef5c27a1f136def879418ea58f312b_Traceguids,
          (unsigned int)v13);
      goto LABEL_19;
    }
    UniquePath = UtilGetUniquePath(this[1], v21[0], lpFileName);
    if ( UniquePath < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)WPP_79ef5c27a1f136def879418ea58f312b_Traceguids,
          v21[0],
          UniquePath);
      goto LABEL_19;
    }
    utl::make_unique<CCabDecompress::_DECOMP_FILE_HANDLE,,0>(&v23);
    v15 = v23;
    if ( !v23 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)((_DWORD)v23 + 69),
          WPP_79ef5c27a1f136def879418ea58f312b_Traceguids,
          v21[0]);
      goto LABEL_28;
    }
    *v23 = this;
    FileW = (HANDLE *)CreateFileW(lpFileName[0], 0xC0000000, 7u, 0, 1u, 0x80u, 0);
    v15[1] = FileW;
    if ( FileW == (HANDLE *)-1LL )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        v18 = ERROR_HR_FROM_WIN32(LastError);
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          (unsigned int)WPP_79ef5c27a1f136def879418ea58f312b_Traceguids,
          lpFileName[0],
          v18);
      }
      goto LABEL_28;
    }
    if ( !SetFileAttributesW(lpFileName[0], 0x2080u) )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
      {
LABEL_41:
        v6 = (__int64)v15;
        v23 = 0;
LABEL_28:
        utl::unique_ptr<CCabDecompress::_DECOMP_FILE_HANDLE,utl::default_delete<CCabDecompress::_DECOMP_FILE_HANDLE>>::~unique_ptr<CCabDecompress::_DECOMP_FILE_HANDLE,utl::default_delete<CCabDecompress::_DECOMP_FILE_HANDLE>>(&v23);
LABEL_19:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v21);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
        return v6;
      }
      if ( (WPP_GLOBAL_Control[14] & 2) == 0 )
      {
LABEL_38:
        if ( v19 != (wchar_t *)&WPP_GLOBAL_Control && (v19[14] & 4) != 0 )
          WPP_SF_S(*((_QWORD *)v19 + 2), 72, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, lpFileName[0]);
        goto LABEL_41;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids);
    }
    v19 = WPP_GLOBAL_Control;
    goto LABEL_38;
  }
LABEL_42:
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v8 = 73;
    goto LABEL_48;
  }
  return v6;
}

```

## disassembly

```asm
0x18009ba2c  push    rbp
0x18009ba2e  push    rbx
0x18009ba2f  push    rsi
0x18009ba30  push    rdi
0x18009ba31  push    r12
0x18009ba33  push    r14
0x18009ba35  lea     rbp, [rsp-2Fh]
0x18009ba3a  sub     rsp, 88h
0x18009ba41  or      r12, 0FFFFFFFFFFFFFFFFh
0x18009ba45  mov     rdi, r8
0x18009ba48  mov     ebx, edx
0x18009ba4a  mov     r14, rcx
0x18009ba4d  mov     rsi, r12
0x18009ba50  test    r8, r8
0x18009ba53  jz      loc_18009BD18
0x18009ba59  cmp     qword ptr [r8+20h], 0
0x18009ba5e  jz      loc_18009BD18
0x18009ba64  mov     rcx, [rcx]; hHandle
0x18009ba67  xor     edx, edx; dwMilliseconds
0x18009ba69  call    cs:__imp_WaitForSingleObject
0x18009ba6f  test    eax, eax
0x18009ba71  jnz     short loc_18009BA9C
0x18009ba73  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ba7a  lea     rdi, WPP_GLOBAL_Control
0x18009ba81  cmp     rcx, rdi
0x18009ba84  jz      loc_18009BD46
0x18009ba8a  test    byte ptr [rcx+1Ch], 4
0x18009ba8e  jz      loc_18009BD46
0x18009ba94  lea     edx, [rax+42h]
0x18009ba97  jmp     loc_18009BD36
0x18009ba9c  sub     ebx, 1
0x18009ba9f  jz      loc_18009BCF8
0x18009baa5  sub     ebx, 1
0x18009baa8  jz      short loc_18009BAD5
0x18009baaa  sub     ebx, 1
0x18009baad  jz      short loc_18009BABF
0x18009baaf  cmp     ebx, 1
0x18009bab2  jz      loc_18009BCF8
0x18009bab8  xor     esi, esi
0x18009baba  jmp     loc_18009BD46
0x18009babf  mov     rcx, [rdi+28h]; hf
0x18009bac3  call    ?static_FDIClose@CCabDecompress@@KAH_J@Z; CCabDecompress::static_FDIClose(__int64)
0x18009bac8  xor     esi, esi
0x18009baca  test    eax, eax
0x18009bacc  setz    sil
0x18009bad0  jmp     loc_18009BD46
0x18009bad5  lea     rcx, [rbp+57h+lpFileName]; void *
0x18009bad9  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009bade  lea     rcx, [rbp+57h+var_70]; void *
0x18009bae2  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009bae7  mov     rcx, [rbp+57h+var_70]
0x18009baeb  xor     esi, esi
0x18009baed  xor     eax, eax
0x18009baef  mov     [rbp+57h+var_68], rcx
0x18009baf3  mov     r8, r12
0x18009baf6  mov     [rcx], ax
0x18009baf9  mov     rdx, [rdi+8]
0x18009bafd  inc     r8
0x18009bb00  cmp     [rdx+r8], al
0x18009bb04  jnz     short loc_18009BAFD
0x18009bb06  lea     rcx, [rbp+57h+var_70]
0x18009bb0a  call    ??$_AppendMbcsImpl@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEBD_KII@Z; tlx::_AppendMbcsImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,char const *,unsigned __int64,uint,uint)
0x18009bb0f  test    eax, eax
0x18009bb11  jns     short loc_18009BB5B
0x18009bb13  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bb1a  lea     rdi, WPP_GLOBAL_Control
0x18009bb21  cmp     rcx, rdi
0x18009bb24  jz      short loc_18009BB44
0x18009bb26  test    byte ptr [rcx+1Ch], 1
0x18009bb2a  jz      short loc_18009BB44
0x18009bb2c  mov     rcx, [rcx+10h]
0x18009bb30  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bb37  mov     edx, 43h ; 'C'
0x18009bb3c  mov     r9d, eax
0x18009bb3f  call    WPP_SF_d
0x18009bb44  lea     rcx, [rbp+57h+var_70]; void *
0x18009bb48  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009bb4d  lea     rcx, [rbp+57h+lpFileName]; void *
0x18009bb51  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009bb56  jmp     loc_18009BD46
0x18009bb5b  mov     rdx, [rbp+57h+var_70]
0x18009bb5f  lea     r8, [rbp+57h+lpFileName]
0x18009bb63  mov     rcx, [r14+8]
0x18009bb67  call    ?UtilGetUniquePath@@YAJPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetUniquePath(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18009bb6c  test    eax, eax
0x18009bb6e  jns     short loc_18009BBA8
0x18009bb70  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bb77  lea     rdi, WPP_GLOBAL_Control
0x18009bb7e  cmp     rcx, rdi
0x18009bb81  jz      short loc_18009BB44
0x18009bb83  test    byte ptr [rcx+1Ch], 1
0x18009bb87  jz      short loc_18009BB44
0x18009bb89  mov     r9, [rbp+57h+var_70]
0x18009bb8d  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bb94  mov     rcx, [rcx+10h]
0x18009bb98  mov     edx, 44h ; 'D'
0x18009bb9d  mov     [rsp+0B0h+dwCreationDisposition], eax
0x18009bba1  call    WPP_SF_SD
0x18009bba6  jmp     short loc_18009BB44
0x18009bba8  lea     rcx, [rbp+57h+arg_10]
0x18009bbac  call    ??$make_unique@U_DECOMP_FILE_HANDLE@CCabDecompress@@$$V$0A@@utl@@YA?AV?$unique_ptr@U_DECOMP_FILE_HANDLE@CCabDecompress@@U?$default_delete@U_DECOMP_FILE_HANDLE@CCabDecompress@@@utl@@@0@XZ; utl::make_unique<CCabDecompress::_DECOMP_FILE_HANDLE,,0>(void)
0x18009bbb1  mov     rbx, [rbp+57h+arg_10]
0x18009bbb5  test    rbx, rbx
0x18009bbb8  jnz     short loc_18009BBF8
0x18009bbba  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bbc1  lea     rdi, WPP_GLOBAL_Control
0x18009bbc8  cmp     rcx, rdi
0x18009bbcb  jz      short loc_18009BBEA
0x18009bbcd  test    byte ptr [rcx+1Ch], 1
0x18009bbd1  jz      short loc_18009BBEA
0x18009bbd3  mov     r9, [rbp+57h+var_70]
0x18009bbd7  lea     edx, [rbx+45h]
0x18009bbda  mov     rcx, [rcx+10h]
0x18009bbde  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bbe5  call    WPP_SF_S
0x18009bbea  lea     rcx, [rbp+57h+arg_10]
0x18009bbee  call    ??1?$unique_ptr@U_DECOMP_FILE_HANDLE@CCabDecompress@@U?$default_delete@U_DECOMP_FILE_HANDLE@CCabDecompress@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CCabDecompress::_DECOMP_FILE_HANDLE,utl::default_delete<CCabDecompress::_DECOMP_FILE_HANDLE>>::~unique_ptr<CCabDecompress::_DECOMP_FILE_HANDLE,utl::default_delete<CCabDecompress::_DECOMP_FILE_HANDLE>>(void)
0x18009bbf3  jmp     loc_18009BB44
0x18009bbf8  xor     r9d, r9d; lpSecurityAttributes
0x18009bbfb  mov     [rbx], r14
0x18009bbfe  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18009bc02  mov     edx, 0C0000000h; dwDesiredAccess
0x18009bc07  mov     [rsp+0B0h+hTemplateFile], rsi; hTemplateFile
0x18009bc0c  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009bc14  lea     r8d, [r9+7]; dwShareMode
0x18009bc18  mov     [rsp+0B0h+dwCreationDisposition], 1; dwCreationDisposition
0x18009bc20  call    cs:__imp_CreateFileW
0x18009bc26  mov     [rbx+8], rax
0x18009bc2a  cmp     rax, r12
0x18009bc2d  jnz     short loc_18009BC7E
0x18009bc2f  mov     rax, cs:WPP_GLOBAL_Control
0x18009bc36  lea     rdi, WPP_GLOBAL_Control
0x18009bc3d  cmp     rax, rdi
0x18009bc40  jz      short loc_18009BBEA
0x18009bc42  test    byte ptr [rax+1Ch], 1
0x18009bc46  jz      short loc_18009BBEA
0x18009bc48  call    cs:__imp_GetLastError
0x18009bc4e  mov     ecx, eax; unsigned int
0x18009bc50  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009bc55  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bc5c  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bc63  mov     r9, [rbp+57h+lpFileName]
0x18009bc67  mov     edx, 46h ; 'F'
0x18009bc6c  mov     [rsp+0B0h+dwCreationDisposition], eax
0x18009bc70  mov     rcx, [rcx+10h]
0x18009bc74  call    WPP_SF_SD
0x18009bc79  jmp     loc_18009BBEA
0x18009bc7e  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18009bc82  mov     edx, 2080h; dwFileAttributes
0x18009bc87  call    cs:__imp_SetFileAttributesW
0x18009bc8d  lea     rdi, WPP_GLOBAL_Control
0x18009bc94  test    eax, eax
0x18009bc96  jnz     short loc_18009BCBD
0x18009bc98  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bc9f  cmp     rcx, rdi
0x18009bca2  jz      short loc_18009BCE8
0x18009bca4  test    byte ptr [rcx+1Ch], 2
0x18009bca8  jz      short loc_18009BCC4
0x18009bcaa  mov     rcx, [rcx+10h]
0x18009bcae  lea     edx, [rax+47h]
0x18009bcb1  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bcb8  call    WPP_SF_
0x18009bcbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bcc4  cmp     rcx, rdi
0x18009bcc7  jz      short loc_18009BCE8
0x18009bcc9  test    byte ptr [rcx+1Ch], 4
0x18009bccd  jz      short loc_18009BCE8
0x18009bccf  mov     r9, [rbp+57h+lpFileName]
0x18009bcd3  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bcda  mov     rcx, [rcx+10h]
0x18009bcde  mov     edx, 48h ; 'H'
0x18009bce3  call    WPP_SF_S
0x18009bce8  mov     rsi, rbx
0x18009bceb  mov     [rbp+57h+arg_10], 0
0x18009bcf3  jmp     loc_18009BBEA
0x18009bcf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bcff  lea     rdi, WPP_GLOBAL_Control
0x18009bd06  cmp     rcx, rdi
0x18009bd09  jz      short loc_18009BD46
0x18009bd0b  test    byte ptr [rcx+1Ch], 1
0x18009bd0f  jz      short loc_18009BD46
0x18009bd11  mov     edx, 49h ; 'I'
0x18009bd16  jmp     short loc_18009BD36
0x18009bd18  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bd1f  lea     rdi, WPP_GLOBAL_Control
0x18009bd26  cmp     rcx, rdi
0x18009bd29  jz      short loc_18009BD46
0x18009bd2b  test    byte ptr [rcx+1Ch], 1
0x18009bd2f  jz      short loc_18009BD46
0x18009bd31  mov     edx, 41h ; 'A'
0x18009bd36  mov     rcx, [rcx+10h]
0x18009bd3a  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009bd41  call    WPP_SF_
0x18009bd46  mov     rax, rsi
0x18009bd49  add     rsp, 88h
0x18009bd50  pop     r14
0x18009bd52  pop     r12
0x18009bd54  pop     rdi
0x18009bd55  pop     rsi
0x18009bd56  pop     rbx
0x18009bd57  pop     rbp
0x18009bd58  retn
```
