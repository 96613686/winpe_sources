# Wallet::WalletDatabaseESE::Open(char const *)

- ea: `0x1800110f0`
- end: `0x1800112af`
- name: `?Open@WalletDatabaseESE@Wallet@@UEAAJPEBD@Z`
- size: `447`
- prototype: `__int64 __fastcall(Wallet::WalletDatabaseESE *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180002e54`
- `0x18000fe14`
- `0x1800102c0`
- `0x1800110f0`
- `0x18001b2e0`
- `0x18001b49c`
- `0x18001be00`
- `0x18001d50c`
- `0x180036948`
- `0x180043052`
- `0x180043090`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800111ac`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800111bf`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800111ac`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800111bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011229`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011229`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001121f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001121f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180011139`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180011139`

## pseudocode

```c
__int64 __fastcall Wallet::WalletDatabaseESE::Open(Wallet::WalletDatabaseESE *this, const char *a2)
{
  WalletEncrypter *v2; // rdi
  BCRYPT_ALG_HANDLE *v5; // rax
  NTSTATUS v6; // eax
  int Directory; // ebx
  char *v8; // rdi
  _QWORD *v9; // rbx
  void *v10; // rcx
  const unsigned __int16 *v11; // rdx
  signed int LastError; // eax
  const unsigned __int16 *v13; // rdx
  int Database; // eax
  char v16; // [rsp+30h] [rbp-248h] BYREF
  WCHAR WideCharStr[2]; // [rsp+40h] [rbp-238h] BYREF
  _BYTE v18[524]; // [rsp+44h] [rbp-234h] BYREF

  v2 = (Wallet::WalletDatabaseESE *)((char *)this + 56);
  if ( *((_DWORD *)this + 24)
    && ((v5 = (BCRYPT_ALG_HANDLE *)tlx::replace<tlx::handle_traits<void *,long (*)(void * const &),&long wp::detail::_WpBCryptCloseAlgorithmProvider(void * const &),0>>(v2),
         v6 = BCryptOpenAlgorithmProvider(v5, L"AES", 0, 0),
         Directory = v6 | 0x10000000,
         v6 < 0)
     || (Directory = WalletEncrypter::InitializeKey(v2), Directory < 0)) )
  {
    WalletEncrypter::Cleanup(v2);
  }
  else
  {
    v8 = (char *)this + 104;
    if ( *((_QWORD *)this + 13) )
      goto LABEL_32;
    v9 = operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v9 )
      *v9 = &Wallet::JetDB::`vftable';
    else
      v9 = 0;
    if ( v8 == &v16 )
    {
      if ( v9 )
        operator delete(v9);
    }
    else
    {
      v10 = *(void **)v8;
      if ( v9 != *(_QWORD **)v8 )
      {
        if ( v10 )
          operator delete(v10);
        *(_QWORD *)v8 = v9;
      }
    }
    if ( *(_QWORD *)v8 )
    {
LABEL_32:
      if ( *((_DWORD *)this + 2) )
      {
        return (unsigned int)-2147418113;
      }
      else
      {
        *(_DWORD *)WideCharStr = 0;
        memset_0(v18, 0, 0x204u);
        if ( MultiByteToWideChar(0xFDE9u, 0, a2, -1, WideCharStr, 260) )
        {
          Directory = Wallet::FileUtils::RecursiveCreateDirectory(WideCharStr, v11);
          if ( Directory >= 0 )
          {
            Directory = Wallet::ServerUtils::HideAndRestrictFolder(WideCharStr, v13);
            if ( Directory >= 0 )
            {
              Database = Wallet::WalletDatabaseESE::LoadDatabase(this, a2);
              Directory = Wallet::WalletDatabaseESE::JetErrToHR(Database);
              if ( Directory >= 0 )
              {
                Directory = 0;
                *((_DWORD *)this + 2) = 1;
              }
            }
          }
        }
        else
        {
          LastError = GetLastError();
          Directory = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              return (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            return (unsigned int)-2143748092;
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)Directory;
}

```

## disassembly

```asm
0x1800110f0  mov     [rsp+arg_10], rbx
0x1800110f5  push    rbp
0x1800110f6  push    rsi
0x1800110f7  push    rdi
0x1800110f8  sub     rsp, 260h
0x1800110ff  mov     rax, cs:__security_cookie
0x180011106  xor     rax, rsp
0x180011109  mov     [rsp+278h+var_28], rax
0x180011111  lea     rdi, [rcx+38h]
0x180011115  mov     rbp, rdx
0x180011118  cmp     dword ptr [rdi+28h], 0
0x18001111c  mov     rsi, rcx
0x18001111f  jz      short loc_180011164
0x180011121  mov     rcx, rdi
0x180011124  call    ??$replace@U?$handle_traits@PEAXP6AJAEBQEAX@Z$1?_WpBCryptCloseAlgorithmProvider@detail@wp@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6AJAEBQEAX@Z$1?_WpBCryptCloseAlgorithmProvider@detail@wp@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,long (*)(void * const &),&wp::detail::_WpBCryptCloseAlgorithmProvider(void * const &),0>>(tlx::unique_any<tlx::handle_traits<void *,long (*)(void * const &),&wp::detail::_WpBCryptCloseAlgorithmProvider(void * const &),0>> &)
0x180011129  mov     rcx, rax; phAlgorithm
0x18001112c  lea     rdx, pszAlgId; "AES"
0x180011133  xor     r9d, r9d; dwFlags
0x180011136  xor     r8d, r8d; pszImplementation
0x180011139  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001113f  mov     ebx, eax
0x180011141  or      ebx, 10000000h
0x180011147  jl      short loc_180011157
0x180011149  mov     rcx, rdi; this
0x18001114c  call    ?InitializeKey@WalletEncrypter@@AEAAJXZ; WalletEncrypter::InitializeKey(void)
0x180011151  mov     ebx, eax
0x180011153  test    eax, eax
0x180011155  jns     short loc_180011164
0x180011157  mov     rcx, rdi; this
0x18001115a  call    ?Cleanup@WalletEncrypter@@AEAAXXZ; WalletEncrypter::Cleanup(void)
0x18001115f  jmp     loc_18001128A
0x180011164  lea     rdi, [rsi+68h]
0x180011168  cmp     qword ptr [rdi], 0
0x18001116c  jnz     short loc_1800111D5
0x18001116e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011175  mov     ecx, 8; unsigned __int64
0x18001117a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001117f  mov     rbx, rax
0x180011182  test    rax, rax
0x180011185  jz      short loc_180011193
0x180011187  lea     rax, ??_7JetDB@Wallet@@6B@; const Wallet::JetDB::`vftable'
0x18001118e  mov     [rbx], rax
0x180011191  jmp     short loc_180011195
0x180011193  xor     ebx, ebx
0x180011195  lea     rax, [rsp+278h+var_248]
0x18001119a  cmp     rdi, rax
0x18001119d  jz      short loc_1800111B7
0x18001119f  mov     rcx, [rdi]
0x1800111a2  cmp     rbx, rcx
0x1800111a5  jz      short loc_1800111C5
0x1800111a7  test    rcx, rcx
0x1800111aa  jz      short loc_1800111B2
0x1800111ac  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800111b2  mov     [rdi], rbx
0x1800111b5  jmp     short loc_1800111C5
0x1800111b7  test    rbx, rbx
0x1800111ba  jz      short loc_1800111C5
0x1800111bc  mov     rcx, rbx
0x1800111bf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800111c5  cmp     qword ptr [rdi], 0
0x1800111c9  jnz     short loc_1800111D5
0x1800111cb  mov     ebx, 8007000Eh
0x1800111d0  jmp     loc_18001128A
0x1800111d5  cmp     dword ptr [rsi+8], 0
0x1800111d9  jz      short loc_1800111E5
0x1800111db  mov     ebx, 8000FFFFh
0x1800111e0  jmp     loc_18001128A
0x1800111e5  xor     edx, edx; Val
0x1800111e7  mov     dword ptr [rsp+278h+WideCharStr], 0
0x1800111ef  mov     r8d, 204h; Size
0x1800111f5  lea     rcx, [rsp+278h+var_234]; void *
0x1800111fa  call    memset_0
0x1800111ff  lea     rax, [rsp+278h+WideCharStr]
0x180011204  mov     [rsp+278h+cchWideChar], 104h; cchWideChar
0x18001120c  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180011210  mov     [rsp+278h+lpWideCharStr], rax; lpWideCharStr
0x180011215  mov     r8, rbp; lpMultiByteStr
0x180011218  xor     edx, edx; dwFlags
0x18001121a  mov     ecx, 0FDE9h; CodePage
0x18001121f  call    cs:__imp_MultiByteToWideChar
0x180011225  test    eax, eax
0x180011227  jnz     short loc_180011249
0x180011229  call    cs:__imp_GetLastError
0x18001122f  mov     ebx, eax
0x180011231  test    eax, eax
0x180011233  jz      short loc_180011242
0x180011235  jle     short loc_18001128A
0x180011237  movzx   ebx, ax
0x18001123a  or      ebx, 80070000h
0x180011240  jmp     short loc_18001128A
0x180011242  mov     ebx, 80390004h
0x180011247  jmp     short loc_18001128A
0x180011249  lea     rcx, [rsp+278h+WideCharStr]; this
0x18001124e  call    ?RecursiveCreateDirectory@FileUtils@Wallet@@YAJPEBG@Z; Wallet::FileUtils::RecursiveCreateDirectory(ushort const *)
0x180011253  mov     ebx, eax
0x180011255  test    eax, eax
0x180011257  js      short loc_18001128A
0x180011259  lea     rcx, [rsp+278h+WideCharStr]; lpFileName
0x18001125e  call    ?HideAndRestrictFolder@ServerUtils@Wallet@@YAJPEBG@Z; Wallet::ServerUtils::HideAndRestrictFolder(ushort const *)
0x180011263  mov     ebx, eax
0x180011265  test    eax, eax
0x180011267  js      short loc_18001128A
0x180011269  mov     rdx, rbp; char *
0x18001126c  mov     rcx, rsi; this
0x18001126f  call    ?LoadDatabase@WalletDatabaseESE@Wallet@@AEAAJPEBD@Z; Wallet::WalletDatabaseESE::LoadDatabase(char const *)
0x180011274  mov     ecx, eax; int
0x180011276  call    ?JetErrToHR@WalletDatabaseESE@Wallet@@CAJJ@Z; Wallet::WalletDatabaseESE::JetErrToHR(long)
0x18001127b  mov     ebx, eax
0x18001127d  test    eax, eax
0x18001127f  js      short loc_18001128A
0x180011281  xor     ebx, ebx
0x180011283  mov     dword ptr [rsi+8], 1
0x18001128a  mov     eax, ebx
0x18001128c  mov     rcx, [rsp+278h+var_28]
0x180011294  xor     rcx, rsp; StackCookie
0x180011297  call    __security_check_cookie
0x18001129c  mov     rbx, [rsp+278h+arg_10]
0x1800112a4  add     rsp, 260h
0x1800112ab  pop     rdi
0x1800112ac  pop     rsi
0x1800112ad  pop     rbp
0x1800112ae  retn
```
