# GetNameAndFQDNDomain

- ea: `0x1400639cc`
- end: `0x140063d75`
- name: `GetNameAndFQDNDomain`
- size: `937`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400640a4`

## callees

- `0x140004280`
- `0x140005f50`
- `0x1400060e8`
- `0x140006304`
- `0x140013cc0`
- `0x140018bec`
- `0x140019da0`
- `0x14001a08c`
- `0x14001a100`
- `0x140039dfc`
- `0x14003e4dc`
- `0x14006393c`
- `0x1400639cc`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x140063a1b`
- `ADVAPI32!SetThreadToken` at `0x140063a1b`
- `KERNEL32!GetLastError` at `0x140063a5b`
- `KERNEL32!GetLastError` at `0x140063aab`
- `KERNEL32!GetLastError` at `0x140063b52`
- `KERNEL32!GetLastError` at `0x140063a5b`
- `KERNEL32!GetLastError` at `0x140063aab`
- `KERNEL32!GetLastError` at `0x140063b52`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063a32`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063ac4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063b29`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063cee`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063a32`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063ac4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063b29`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140063cee`
- `Secur32!GetUserNameExW` at `0x140063a9d`
- `Secur32!GetUserNameExW` at `0x140063b13`
- `Secur32!GetUserNameExW` at `0x140063a9d`
- `Secur32!GetUserNameExW` at `0x140063b13`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int64 __fastcall GetNameAndFQDNDomain(HANDLE Token, char **a2, char **a3)
{
  BOOL v6; // eax
  char *v7; // rax
  const char *v8; // rax
  unsigned __int64 FileId; // rbx
  __int64 v10; // rdi
  DWORD LastError; // eax
  unsigned __int64 v12; // rbx
  char *v13; // rax
  const char *v14; // rax
  unsigned __int64 v15; // rdi
  __int64 v16; // rax
  char *v17; // rax
  const char *v18; // rax
  unsigned __int64 v19; // rbx
  unsigned __int64 v21; // r14
  unsigned __int64 v22; // r8
  __int128 *v23; // rsi
  char *v24; // rbx
  __int64 trivial_2; // rax
  unsigned __int64 v26; // rdi
  unsigned __int64 v27; // rcx
  __int128 *v28; // rax
  __int128 *v29; // rdx
  char *v30; // rax
  const char *v31; // rax
  unsigned __int64 v32; // rbx
  ULONG nSize; // [rsp+20h] [rbp-59h] BYREF
  LPWSTR lpNameBuffer[3]; // [rsp+28h] [rbp-51h] BYREF
  BOOL v35; // [rsp+40h] [rbp-39h] BYREF
  char v36[16]; // [rsp+48h] [rbp-31h] BYREF
  __int128 v37; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int64 v38; // [rsp+68h] [rbp-11h]
  unsigned __int64 v39; // [rsp+70h] [rbp-9h]
  __int128 v40; // [rsp+78h] [rbp-1h] BYREF
  __int128 v41; // [rsp+88h] [rbp+Fh]

  softgrid::shared::revert_to_self::revert_to_self((softgrid::shared::revert_to_self *)v36);
  v6 = SetThreadToken(0, Token);
  v35 = v6;
  if ( !v6 )
  {
    v7 = strrchr("admin\\appman\\appv\\shared\\user\\userinfo.cpp", 92);
    if ( v7 )
      v8 = v7 + 1;
    else
      v8 = "admin\\appman\\appv\\shared\\user\\userinfo.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v8);
    v10 = (FileId << 52) | GetLastError() | 0x162500000000LL;
    goto LABEL_20;
  }
  nSize = 256;
  std::vector<wchar_t>::vector<wchar_t>(lpNameBuffer, 256);
  if ( !GetUserNameExW(NameDnsDomain, lpNameBuffer[0], &nSize) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError != 234 )
    {
      v13 = strrchr("admin\\appman\\appv\\shared\\user\\userinfo.cpp", 92);
      if ( v13 )
        v14 = v13 + 1;
      else
        v14 = "admin\\appman\\appv\\shared\\user\\userinfo.cpp";
      v15 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v14) << 52;
      v16 = 0x172500000000LL;
LABEL_19:
      v10 = v16 | v12 | v15;
      std::vector<wchar_t>::~vector<wchar_t>((char **)lpNameBuffer);
LABEL_20:
      softgrid::shared::impersonate_user::~impersonate_user((softgrid::shared::impersonate_user *)&v35);
      return v10;
    }
    std::vector<wchar_t>::resize(lpNameBuffer);
    if ( !GetUserNameExW(NameDnsDomain, lpNameBuffer[0], &nSize) )
    {
      v17 = strrchr("admin\\appman\\appv\\shared\\user\\userinfo.cpp", 92);
      if ( v17 )
        v18 = v17 + 1;
      else
        v18 = "admin\\appman\\appv\\shared\\user\\userinfo.cpp";
      v19 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v18);
      v15 = GetLastError();
      v12 = v19 << 52;
      v16 = 0x182500000000LL;
      goto LABEL_19;
    }
  }
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v21 = -1;
  v22 = -1;
  do
    ++v22;
  while ( lpNameBuffer[0][v22] );
  std::wstring::_Construct<1,wchar_t const *>((char **)&v37, lpNameBuffer[0], v22);
  v23 = &v37;
  if ( v39 > 7 )
    v23 = (__int128 *)v37;
  if ( !v38
    || (v24 = (char *)v23 + 2 * v38, trivial_2 = _std_find_trivial_2(v23, v24, 92), (char *)trivial_2 == v24)
    || (v26 = (trivial_2 - (__int64)v23) >> 1, v26 == -1)
    || (v27 = v26 + 1, v26 + 1 == v38)
    || !v26 )
  {
    v30 = strrchr("admin\\appman\\appv\\shared\\user\\userinfo.cpp", 92);
    if ( v30 )
      v31 = v30 + 1;
    else
      v31 = "admin\\appman\\appv\\shared\\user\\userinfo.cpp";
    v32 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v31) << 52)
        | 0x19250000000DLL;
    std::wstring::~wstring((char **)&v37);
    std::vector<wchar_t>::~vector<wchar_t>((char **)lpNameBuffer);
    softgrid::shared::impersonate_user::~impersonate_user((softgrid::shared::impersonate_user *)&v35);
    return v32;
  }
  else
  {
    v40 = 0;
    v41 = 0;
    if ( v38 < v27 )
      std::_String_val<std::_Simple_types<wchar_t>>::_Xran(v27);
    if ( v38 - v27 != -1 )
      v21 = v38 - v27;
    v28 = &v37;
    if ( v39 > 7 )
      v28 = (__int128 *)v37;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v40, (char *)v28 + 2 * v27, v21);
    std::wstring::operator=(a2, (__int64)&v40);
    std::wstring::~wstring((char **)&v40);
    v40 = 0;
    v41 = 0;
    if ( v38 < v26 )
      v26 = v38;
    v29 = &v37;
    if ( v39 > 7 )
      v29 = (__int128 *)v37;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v40, v29, v26);
    std::wstring::operator=(a3, (__int64)&v40);
    std::wstring::~wstring((char **)&v40);
    std::wstring::~wstring((char **)&v37);
    std::vector<wchar_t>::~vector<wchar_t>((char **)lpNameBuffer);
    softgrid::shared::impersonate_user::~impersonate_user((softgrid::shared::impersonate_user *)&v35);
    return 0x8000000000LL;
  }
}

```

## disassembly

```asm
0x1400639cc  mov     [rsp-8+arg_18], rbx
0x1400639d1  push    rbp
0x1400639d2  push    rsi
0x1400639d3  push    rdi
0x1400639d4  push    r12
0x1400639d6  push    r13
0x1400639d8  push    r14
0x1400639da  push    r15
0x1400639dc  lea     rbp, [rsp-27h]
0x1400639e1  sub     rsp, 0A0h
0x1400639e8  mov     rax, cs:__security_cookie
0x1400639ef  xor     rax, rsp
0x1400639f2  mov     [rbp+57h+var_38], rax
0x1400639f6  mov     r12, r8
0x1400639f9  mov     r15, rdx
0x1400639fc  mov     rbx, rcx
0x1400639ff  xor     r13d, r13d
0x140063a02  mov     [rbp+57h+var_90], r13d
0x140063a06  lea     rcx, [rbp+57h+var_88]; this
0x140063a0a  call    ??0revert_to_self@shared@softgrid@@QEAA@XZ; softgrid::shared::revert_to_self::revert_to_self(void)
0x140063a0f  mov     eax, [rbp+57h+var_90]
0x140063a12  test    eax, eax
0x140063a14  jnz     short loc_140063A24
0x140063a16  mov     rdx, rbx; Token
0x140063a19  xor     ecx, ecx; Thread
0x140063a1b  call    cs:__imp_SetThreadToken
0x140063a21  mov     [rbp+57h+var_90], eax
0x140063a24  test    eax, eax
0x140063a26  jnz     short loc_140063A7C
0x140063a28  lea     edx, [rax+5Ch]; Ch
0x140063a2b  lea     rcx, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063a32  call    cs:__imp_strrchr
0x140063a38  test    rax, rax
0x140063a3b  jz      short loc_140063A42
0x140063a3d  inc     rax
0x140063a40  jmp     short loc_140063A49
0x140063a42  lea     rax, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063a49  mov     rdx, rax; char *
0x140063a4c  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140063a53  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140063a58  mov     rbx, rax
0x140063a5b  call    cs:__imp_GetLastError
0x140063a61  mov     edi, eax
0x140063a63  shl     rbx, 34h
0x140063a67  or      rdi, rbx
0x140063a6a  mov     rax, 162500000000h
0x140063a74  or      rdi, rax
0x140063a77  jmp     loc_140063B78
0x140063a7c  mov     edx, 100h
0x140063a81  mov     [rbp+57h+nSize], edx
0x140063a84  lea     rcx, [rbp+57h+lpNameBuffer]
0x140063a88  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x140063a8d  nop
0x140063a8e  lea     r8, [rbp+57h+nSize]; nSize
0x140063a92  mov     rdx, [rbp+57h+lpNameBuffer]; lpNameBuffer
0x140063a96  mov     edi, 0Ch
0x140063a9b  mov     ecx, edi; NameFormat
0x140063a9d  call    cs:__imp_GetUserNameExW
0x140063aa3  test    al, al
0x140063aa5  jnz     loc_140063B89
0x140063aab  call    cs:__imp_GetLastError
0x140063ab1  mov     ebx, eax
0x140063ab3  cmp     eax, 0EAh
0x140063ab8  jz      short loc_140063AFD
0x140063aba  lea     edx, [rdi+50h]; Ch
0x140063abd  lea     rcx, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063ac4  call    cs:__imp_strrchr
0x140063aca  test    rax, rax
0x140063acd  jz      short loc_140063AD4
0x140063acf  inc     rax
0x140063ad2  jmp     short loc_140063ADB
0x140063ad4  lea     rax, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063adb  mov     rdx, rax; char *
0x140063ade  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140063ae5  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140063aea  mov     rdi, rax
0x140063aed  shl     rdi, 34h
0x140063af1  mov     rax, 172500000000h
0x140063afb  jmp     short loc_140063B68
0x140063afd  mov     edx, [rbp+57h+nSize]
0x140063b00  lea     rcx, [rbp+57h+lpNameBuffer]
0x140063b04  call    ?resize@?$vector@_WV?$allocator@_W@std@@@std@@QEAAX_K@Z; std::vector<wchar_t>::resize(unsigned __int64)
0x140063b09  lea     r8, [rbp+57h+nSize]; nSize
0x140063b0d  mov     rdx, [rbp+57h+lpNameBuffer]; lpNameBuffer
0x140063b11  mov     ecx, edi; NameFormat
0x140063b13  call    cs:__imp_GetUserNameExW
0x140063b19  test    al, al
0x140063b1b  jnz     short loc_140063B89
0x140063b1d  mov     edx, 5Ch ; '\'; Ch
0x140063b22  lea     rcx, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063b29  call    cs:__imp_strrchr
0x140063b2f  test    rax, rax
0x140063b32  jz      short loc_140063B39
0x140063b34  inc     rax
0x140063b37  jmp     short loc_140063B40
0x140063b39  lea     rax, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063b40  mov     rdx, rax; char *
0x140063b43  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140063b4a  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140063b4f  mov     rbx, rax
0x140063b52  call    cs:__imp_GetLastError
0x140063b58  mov     edi, eax
0x140063b5a  shl     rbx, 34h
0x140063b5e  mov     rax, 182500000000h
0x140063b68  or      rdi, rbx
0x140063b6b  or      rdi, rax
0x140063b6e  lea     rcx, [rbp+57h+lpNameBuffer]
0x140063b72  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x140063b77  nop
0x140063b78  lea     rcx, [rbp+57h+var_90]; this
0x140063b7c  call    ??1impersonate_user@shared@softgrid@@QEAA@XZ; softgrid::shared::impersonate_user::~impersonate_user(void)
0x140063b81  mov     rax, rdi
0x140063b84  jmp     loc_140063D48
0x140063b89  mov     rdx, [rbp+57h+lpNameBuffer]
0x140063b8d  xorps   xmm0, xmm0
0x140063b90  movups  [rbp+57h+var_78], xmm0
0x140063b94  mov     [rbp+57h+var_68], r13
0x140063b98  mov     [rbp+57h+var_60], r13
0x140063b9c  or      r14, 0FFFFFFFFFFFFFFFFh
0x140063ba0  mov     r8, r14
0x140063ba3  inc     r8
0x140063ba6  cmp     [rdx+r8*2], r13w
0x140063bab  jnz     short loc_140063BA3
0x140063bad  lea     rcx, [rbp+57h+var_78]
0x140063bb1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140063bb6  nop
0x140063bb7  mov     rax, [rbp+57h+var_68]
0x140063bbb  lea     rsi, [rbp+57h+var_78]
0x140063bbf  cmp     [rbp+57h+var_60], 7
0x140063bc4  cmova   rsi, qword ptr [rbp+57h+var_78]
0x140063bc9  test    rax, rax
0x140063bcc  jz      loc_140063CE2
0x140063bd2  lea     rbx, [rsi+rax*2]
0x140063bd6  mov     r8d, 5Ch ; '\'
0x140063bdc  mov     rdx, rbx
0x140063bdf  mov     rcx, rsi
0x140063be2  call    __std_find_trivial_2
0x140063be7  mov     rdi, rax
0x140063bea  cmp     rax, rbx
0x140063bed  jz      loc_140063CE2
0x140063bf3  sub     rdi, rsi
0x140063bf6  sar     rdi, 1
0x140063bf9  cmp     rdi, r14
0x140063bfc  jz      loc_140063CE2
0x140063c02  mov     rax, [rbp+57h+var_68]
0x140063c06  lea     rcx, [rdi+1]
0x140063c0a  cmp     rcx, rax
0x140063c0d  jz      loc_140063CE2
0x140063c13  test    rdi, rdi
0x140063c16  jz      loc_140063CE2
0x140063c1c  xorps   xmm0, xmm0
0x140063c1f  movups  [rbp+57h+var_58], xmm0
0x140063c23  xorps   xmm1, xmm1
0x140063c26  movdqu  [rbp+57h+var_48], xmm1
0x140063c2b  cmp     rax, rcx
0x140063c2e  jb      loc_140063D6F
0x140063c34  sub     rax, rcx
0x140063c37  cmp     rax, r14
0x140063c3a  cmovb   r14, rax
0x140063c3e  lea     rax, [rbp+57h+var_78]
0x140063c42  cmp     [rbp+57h+var_60], 7
0x140063c47  cmova   rax, qword ptr [rbp+57h+var_78]
0x140063c4c  lea     rdx, [rax+rcx*2]
0x140063c50  mov     r8, r14
0x140063c53  lea     rcx, [rbp+57h+var_58]
0x140063c57  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140063c5c  lea     rdx, [rbp+57h+var_58]
0x140063c60  mov     rcx, r15
0x140063c63  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140063c68  lea     rcx, [rbp+57h+var_58]
0x140063c6c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140063c71  xorps   xmm0, xmm0
0x140063c74  movups  [rbp+57h+var_58], xmm0
0x140063c78  xorps   xmm1, xmm1
0x140063c7b  movdqu  [rbp+57h+var_48], xmm1
0x140063c80  cmp     [rbp+57h+var_68], rdi
0x140063c84  cmovb   rdi, [rbp+57h+var_68]
0x140063c89  lea     rdx, [rbp+57h+var_78]
0x140063c8d  cmp     [rbp+57h+var_60], 7
0x140063c92  cmova   rdx, qword ptr [rbp+57h+var_78]
0x140063c97  mov     r8, rdi
0x140063c9a  lea     rcx, [rbp+57h+var_58]
0x140063c9e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140063ca3  lea     rdx, [rbp+57h+var_58]
0x140063ca7  mov     rcx, r12
0x140063caa  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140063caf  lea     rcx, [rbp+57h+var_58]
0x140063cb3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140063cb8  nop
0x140063cb9  lea     rcx, [rbp+57h+var_78]
0x140063cbd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140063cc2  nop
0x140063cc3  lea     rcx, [rbp+57h+lpNameBuffer]
0x140063cc7  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x140063ccc  nop
0x140063ccd  lea     rcx, [rbp+57h+var_90]; this
0x140063cd1  call    ??1impersonate_user@shared@softgrid@@QEAA@XZ; softgrid::shared::impersonate_user::~impersonate_user(void)
0x140063cd6  mov     rax, 8000000000h
0x140063ce0  jmp     short loc_140063D48
0x140063ce2  mov     edx, 5Ch ; '\'; Ch
0x140063ce7  lea     rcx, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063cee  call    cs:__imp_strrchr
0x140063cf4  test    rax, rax
0x140063cf7  jz      short loc_140063CFE
0x140063cf9  inc     rax
0x140063cfc  jmp     short loc_140063D05
0x140063cfe  lea     rax, aAdminAppmanApp_9; "admin\\appman\\appv\\shared\\user\\user"...
0x140063d05  mov     rdx, rax; char *
0x140063d08  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140063d0f  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140063d14  mov     rbx, rax
0x140063d17  shl     rbx, 34h
0x140063d1b  mov     rax, 19250000000Dh
0x140063d25  or      rbx, rax
0x140063d28  lea     rcx, [rbp+57h+var_78]
0x140063d2c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140063d31  nop
0x140063d32  lea     rcx, [rbp+57h+lpNameBuffer]
0x140063d36  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x140063d3b  nop
0x140063d3c  lea     rcx, [rbp+57h+var_90]; this
0x140063d40  call    ??1impersonate_user@shared@softgrid@@QEAA@XZ; softgrid::shared::impersonate_user::~impersonate_user(void)
0x140063d45  mov     rax, rbx
0x140063d48  mov     rcx, [rbp+57h+var_38]
0x140063d4c  xor     rcx, rsp; StackCookie
0x140063d4f  call    __security_check_cookie
0x140063d54  mov     rbx, [rsp+0D0h+arg_18]
0x140063d5c  add     rsp, 0A0h
0x140063d63  pop     r15
0x140063d65  pop     r14
0x140063d67  pop     r13
0x140063d69  pop     r12
0x140063d6b  pop     rdi
0x140063d6c  pop     rsi
0x140063d6d  pop     rbp
0x140063d6e  retn
0x140063d6f  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
