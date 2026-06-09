# EnsureDirectoryExistsHr(wil::basic_zstring_view<wchar_t> const &)

- ea: `0x18002c298`
- end: `0x18002c4e3`
- name: `?EnsureDirectoryExistsHr@@YAJAEBV?$basic_zstring_view@_W@wil@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017498`
- `0x18001dc34`
- `0x18001f660`
- `0x180021c88`
- `0x180024334`
- `0x180024bbc`
- `0x18002c4ec`
- `0x1800f3aa0`

## callees

- `0x1800031d0`
- `0x180008aa8`
- `0x180009750`
- `0x18000ccb8`
- `0x180016df0`
- `0x18001d650`
- `0x180022a18`
- `0x1800296a4`
- `0x18002c100`
- `0x18002c298`
- `0x18002cdf8`
- `0x18002d214`
- `0x18004f088`
- `0x18004fcf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c48c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c48c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002c376`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002c47c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002c376`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002c47c`

## string_xrefs

- `0x18002c334`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x18002c440`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnsureDirectoryExistsHr(__int64 a1)
{
  bool *v2; // rdx
  void *v3; // rbx
  int CanSetSystemOwner; // eax
  struct _SECURITY_DESCRIPTOR **v5; // rdx
  __int64 v6; // rdx
  int v7; // eax
  unsigned int v8; // ebx
  const WCHAR *p_lpPathName; // rcx
  DWORD LastError; // eax
  __int128 *v11; // rax
  __int64 Directory; // rax
  __int64 v13; // rdx
  __int128 *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rdi
  const WCHAR *v18; // rcx
  unsigned int v20; // [rsp+28h] [rbp-49h] BYREF
  _QWORD v21[3]; // [rsp+30h] [rbp-41h] BYREF
  _BYTE v22[32]; // [rsp+48h] [rbp-29h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-9h] BYREF
  __int128 lpPathName; // [rsp+80h] [rbp+Fh] BYREF
  __int64 v25; // [rsp+90h] [rbp+1Fh]
  unsigned __int64 v26; // [rsp+98h] [rbp+27h]
  __int128 v27; // [rsp+A0h] [rbp+2Fh] BYREF
  __int64 v28; // [rsp+B0h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v21[2] = -2;
  GetCanonicalUNCPath(&lpPathName, (LPCWSTR *)a1);
  v27 = 0;
  v28 = 0;
  if ( !*(_QWORD *)(a1 + 8) || (unsigned __int8)DirectoryExists(a1) )
  {
LABEL_37:
    v8 = 0;
    goto LABEL_38;
  }
  v3 = 0;
  v21[0] = 0;
  LOBYTE(v20) = 0;
  CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
                        (Windows::WCP::Implementation::Rtl *)&v20,
                        v2);
  if ( CanSetSystemOwner >= 0 )
  {
    if ( (_BYTE)v20 )
    {
      CanSetSystemOwner = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                            (Windows::WCP::Implementation::Rtl *)v21,
                            v5);
      if ( CanSetSystemOwner < 0 )
      {
        v6 = 502;
        goto LABEL_8;
      }
      v3 = (void *)v21[0];
    }
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = v3;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    while ( 1 )
    {
      p_lpPathName = (const WCHAR *)&lpPathName;
      if ( v26 > 7 )
        p_lpPathName = (const WCHAR *)lpPathName;
      if ( CreateDirectoryW(p_lpPathName, &SecurityAttributes) || (LastError = GetLastError(), LastError == 183) )
      {
        v16 = *((_QWORD *)&v27 + 1);
        v17 = v27;
        while ( v16 != v17 )
        {
          v16 -= 32;
          if ( *(_QWORD *)(v16 + 24) <= 7u )
            v18 = (const WCHAR *)v16;
          else
            v18 = *(const WCHAR **)v16;
          if ( !CreateDirectoryW(v18, &SecurityAttributes) )
          {
            LastError = GetLastError();
            if ( LastError != 183 && LastError )
            {
              v15 = 536;
              goto LABEL_27;
            }
            goto LABEL_37;
          }
        }
        goto LABEL_37;
      }
      if ( LastError != 3 )
        break;
      if ( *((_QWORD *)&v27 + 1) == v28 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v27, *((_QWORD *)&v27 + 1), &lpPathName);
      }
      else
      {
        std::wstring::wstring(*((_QWORD *)&v27 + 1), &lpPathName);
        *((_QWORD *)&v27 + 1) += 32LL;
      }
      v11 = &lpPathName;
      if ( v26 > 7 )
        v11 = (__int128 *)lpPathName;
      v21[0] = v11;
      v21[1] = v25;
      Directory = GetDirectory(v22, v21);
      std::wstring::operator=(&lpPathName, Directory);
      std::wstring::~wstring(v22);
      v13 = --v25;
      v14 = &lpPathName;
      if ( v26 > 7 )
        v14 = (__int128 *)lpPathName;
      *((_WORD *)v14 + v13) = 0;
    }
    if ( !LastError )
      goto LABEL_37;
    v15 = 523;
LABEL_27:
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v15,
           (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
           (const char *)LastError,
           v20);
    goto LABEL_9;
  }
  v6 = 497;
LABEL_8:
  v7 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)v6,
         (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
         (const char *)(unsigned int)CanSetSystemOwner,
         v20);
LABEL_9:
  v8 = v7;
LABEL_38:
  std::vector<std::wstring>::_Tidy(&v27);
  std::wstring::~wstring(&lpPathName);
  return v8;
}

```

## disassembly

```asm
0x18002c298  mov     rax, rsp
0x18002c29b  push    rbp
0x18002c29c  lea     rbp, [rax-5Fh]
0x18002c2a0  sub     rsp, 0C0h
0x18002c2a7  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x18002c2af  mov     [rax+10h], rbx
0x18002c2b3  mov     [rax+18h], rdi
0x18002c2b7  mov     rax, cs:__security_cookie
0x18002c2be  xor     rax, rsp
0x18002c2c1  mov     [rbp+57h+var_10], rax
0x18002c2c5  mov     rbx, rcx
0x18002c2c8  mov     rdx, rcx
0x18002c2cb  lea     rcx, [rbp+57h+lpPathName]
0x18002c2cf  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x18002c2d4  nop
0x18002c2d5  xorps   xmm0, xmm0
0x18002c2d8  movdqu  [rbp+57h+var_28], xmm0
0x18002c2dd  mov     [rbp+57h+var_18], 0
0x18002c2e5  cmp     qword ptr [rbx+8], 0
0x18002c2ea  jz      loc_18002C4AA
0x18002c2f0  mov     rcx, rbx
0x18002c2f3  call    ?DirectoryExists@@YA_NAEBV?$basic_zstring_view@_W@wil@@@Z; DirectoryExists(wil::basic_zstring_view<wchar_t> const &)
0x18002c2f8  test    al, al
0x18002c2fa  jnz     loc_18002C4AA
0x18002c300  xor     ebx, ebx
0x18002c302  mov     [rbp+57h+var_98], rbx
0x18002c306  mov     byte ptr [rbp+57h+var_A0], bl
0x18002c309  lea     rcx, [rbp+57h+var_A0]; this
0x18002c30d  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x18002c312  test    eax, eax
0x18002c314  jns     short loc_18002C31D
0x18002c316  mov     edx, 1F1h
0x18002c31b  jmp     short loc_18002C334
0x18002c31d  cmp     byte ptr [rbp+57h+var_A0], bl
0x18002c320  jz      short loc_18002C352
0x18002c322  lea     rcx, [rbp+57h+var_98]; this
0x18002c326  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x18002c32b  test    eax, eax
0x18002c32d  jns     short loc_18002C34E
0x18002c32f  mov     edx, 1F6h; void *
0x18002c334  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002c33b  mov     r9d, eax; char *
0x18002c33e  mov     rcx, [rbp+5Fh]; this
0x18002c342  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002c347  mov     ebx, eax
0x18002c349  jmp     loc_18002C4AC
0x18002c34e  mov     rbx, [rbp+57h+var_98]
0x18002c352  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x18002c35a  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rbx
0x18002c35e  xor     eax, eax
0x18002c360  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x18002c364  lea     rcx, [rbp+57h+lpPathName]
0x18002c368  cmp     [rbp+57h+var_30], 7
0x18002c36d  cmova   rcx, qword ptr [rbp+57h+lpPathName]; lpPathName
0x18002c372  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18002c376  call    cs:__imp_CreateDirectoryW
0x18002c37d  nop     dword ptr [rax+rax+00h]
0x18002c382  test    eax, eax
0x18002c384  jnz     loc_18002C458
0x18002c38a  call    cs:__imp_GetLastError
0x18002c391  nop     dword ptr [rax+rax+00h]
0x18002c396  cmp     eax, 0B7h
0x18002c39b  jz      loc_18002C458
0x18002c3a1  cmp     eax, 3
0x18002c3a4  jnz     loc_18002C437
0x18002c3aa  mov     rax, qword ptr [rbp+57h+var_28+8]
0x18002c3ae  cmp     rax, [rbp+57h+var_18]
0x18002c3b2  jz      short loc_18002C3C7
0x18002c3b4  lea     rdx, [rbp+57h+lpPathName]
0x18002c3b8  mov     rcx, rax
0x18002c3bb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c3c0  add     qword ptr [rbp+57h+var_28+8], 20h ; ' '
0x18002c3c5  jmp     short loc_18002C3D7
0x18002c3c7  lea     r8, [rbp+57h+lpPathName]
0x18002c3cb  mov     rdx, rax
0x18002c3ce  lea     rcx, [rbp+57h+var_28]
0x18002c3d2  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18002c3d7  mov     rcx, [rbp+57h+var_38]
0x18002c3db  lea     rax, [rbp+57h+lpPathName]
0x18002c3df  cmp     [rbp+57h+var_30], 7
0x18002c3e4  cmova   rax, qword ptr [rbp+57h+lpPathName]
0x18002c3e9  mov     [rbp+57h+var_98], rax
0x18002c3ed  mov     [rbp+57h+var_90], rcx
0x18002c3f1  lea     rdx, [rbp+57h+var_98]
0x18002c3f5  lea     rcx, [rbp+57h+var_80]
0x18002c3f9  call    ?GetDirectory@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetDirectory(wil::basic_zstring_view<wchar_t> const &)
0x18002c3fe  mov     rdx, rax
0x18002c401  lea     rcx, [rbp+57h+lpPathName]
0x18002c405  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c40a  lea     rcx, [rbp+57h+var_80]; void *
0x18002c40e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c413  mov     rdx, [rbp+57h+var_38]
0x18002c417  dec     rdx
0x18002c41a  mov     [rbp+57h+var_38], rdx
0x18002c41e  lea     rcx, [rbp+57h+lpPathName]
0x18002c422  cmp     [rbp+57h+var_30], 7
0x18002c427  cmova   rcx, qword ptr [rbp+57h+lpPathName]
0x18002c42c  xor     eax, eax
0x18002c42e  mov     [rcx+rdx*2], ax
0x18002c432  jmp     loc_18002C364
0x18002c437  test    eax, eax
0x18002c439  jz      short loc_18002C4AA
0x18002c43b  mov     edx, 20Bh; void *
0x18002c440  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002c447  mov     r9d, eax; char *
0x18002c44a  mov     rcx, [rbp+5Fh]; this
0x18002c44e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002c453  jmp     loc_18002C347
0x18002c458  mov     rbx, qword ptr [rbp+57h+var_28+8]
0x18002c45c  mov     rdi, qword ptr [rbp+57h+var_28]
0x18002c460  cmp     rbx, rdi
0x18002c463  jz      short loc_18002C4AA
0x18002c465  add     rbx, 0FFFFFFFFFFFFFFE0h
0x18002c469  cmp     qword ptr [rbx+18h], 7
0x18002c46e  jbe     short loc_18002C475
0x18002c470  mov     rcx, [rbx]
0x18002c473  jmp     short loc_18002C478
0x18002c475  mov     rcx, rbx; lpPathName
0x18002c478  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18002c47c  call    cs:__imp_CreateDirectoryW
0x18002c483  nop     dword ptr [rax+rax+00h]
0x18002c488  test    eax, eax
0x18002c48a  jnz     short loc_18002C460
0x18002c48c  call    cs:__imp_GetLastError
0x18002c493  nop     dword ptr [rax+rax+00h]
0x18002c498  cmp     eax, 0B7h
0x18002c49d  jz      short loc_18002C4AA
0x18002c49f  test    eax, eax
0x18002c4a1  jz      short loc_18002C4AA
0x18002c4a3  mov     edx, 218h
0x18002c4a8  jmp     short loc_18002C440
0x18002c4aa  xor     ebx, ebx
0x18002c4ac  lea     rcx, [rbp+57h+var_28]
0x18002c4b0  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002c4b5  nop
0x18002c4b6  lea     rcx, [rbp+57h+lpPathName]; void *
0x18002c4ba  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c4bf  mov     eax, ebx
0x18002c4c1  mov     rcx, [rbp+57h+var_10]
0x18002c4c5  xor     rcx, rsp; StackCookie
0x18002c4c8  call    __security_check_cookie
0x18002c4cd  lea     r11, [rsp+0C0h+var_s0]
0x18002c4d5  mov     rbx, [r11+18h]
0x18002c4d9  mov     rdi, [r11+20h]
0x18002c4dd  mov     rsp, r11
0x18002c4e0  pop     rbp
0x18002c4e1  retn
```
