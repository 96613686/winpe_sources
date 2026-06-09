# Uev::Repository::IsCurrentRepositoryPath(boost::filesystem::path const &)

- ea: `0x14008b878`
- end: `0x14008ba2e`
- name: `?IsCurrentRepositoryPath@Repository@Uev@@AEBA_NAEBVpath@filesystem@boost@@@Z`
- size: `438`
- prototype: `bool __fastcall(Uev::Repository *__hidden this, const struct boost::filesystem::path *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14008a6fc`

## callees

- `0x140003e50`
- `0x14000ba60`
- `0x14000d7b4`
- `0x1400203ac`
- `0x140020568`
- `0x140046e04`
- `0x140046f94`
- `0x14008a5dc`
- `0x14008b878`
- `0x14008cd48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008b9df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008b9df`

## string_xrefs

- `0x14008b8dd`: `Repository::GetCurrentRepositoryPath`
- `0x14008b8a5`: `Repository::IsRepositoryPathCurrent`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall Uev::Repository::IsCurrentRepositoryPath(
        Uev::Repository *this,
        const struct boost::filesystem::path *a2)
{
  char v3; // si
  __m128i si128; // xmm6
  __int128 *v5; // rcx
  __int64 v6; // rax
  Uev::Repository *v7; // rcx
  char v8; // di
  __int128 *v9; // rcx
  Uev::Repository *v10; // rcx
  _OWORD v12[2]; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v15; // [rsp+60h] [rbp-A8h]
  unsigned __int64 v16; // [rsp+68h] [rbp-A0h]
  __int128 v17; // [rsp+70h] [rbp-98h] BYREF
  __int64 v18; // [rsp+80h] [rbp-88h]
  __int64 v19; // [rsp+88h] [rbp-80h]
  _BYTE v20[128]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v21[128]; // [rsp+118h] [rbp+10h] BYREF

  Uev::ScopeTracker::ScopeTracker((Uev::ScopeTracker *)v21, L"CscChangeManager", L"Repository::IsRepositoryPathCurrent");
  v3 = 0;
  v14 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v16 = si128.m128i_u64[1];
  LOWORD(v14) = 0;
  Uev::ScopeTracker::ScopeTracker(
    (Uev::ScopeTracker *)v20,
    L"CscChangeManager",
    L"Repository::GetCurrentRepositoryPath");
  v17 = 0;
  v18 = 0;
  v19 = 7;
  LOWORD(v17) = 0;
  v13 = 0;
  v15 = 0;
  v5 = &v14;
  if ( si128.m128i_i64[1] > 7uLL )
    v5 = (__int128 *)v14;
  *(_WORD *)v5 = 0;
  v6 = Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance(v5);
  v8 = Uev::Setting<std::wstring>::Get(v6 + 18960, &v17, &v13);
  if ( v8 )
  {
    if ( v18 )
    {
      v8 = 1;
      std::wstring::operator=(&v14, &v17);
    }
    else
    {
      v8 = 0;
    }
  }
  else if ( (_DWORD)v13 != 2 )
  {
    v12[0] = 0;
    v12[1] = si128;
    LOWORD(v12[0]) = 0;
    Uev::Repository::SetCurrentRepositoryPath(v7, (const struct boost::filesystem::path *)v12);
    std::wstring::_Tidy_deallocate(v12);
  }
  std::wstring::_Tidy_deallocate(&v17);
  Uev::ScopeTracker::~ScopeTracker((Uev::ScopeTracker *)v20);
  if ( v8 )
  {
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const struct boost::filesystem::path **)a2;
    v9 = &v14;
    if ( v16 > 7 )
      v9 = (__int128 *)v14;
    if ( (unsigned int)_o__wcsicmp(v9, a2) )
      Uev::Repository::ClearCurrentRepositoryPath(v10);
    else
      v3 = 1;
  }
  std::wstring::_Tidy_deallocate(&v14);
  Uev::ScopeTracker::~ScopeTracker((Uev::ScopeTracker *)v21);
  return v3;
}

```

## disassembly

```asm
0x14008b878  mov     rax, rsp
0x14008b87b  push    rbp
0x14008b87c  push    rbx
0x14008b87d  push    rsi
0x14008b87e  push    rdi
0x14008b87f  lea     rbp, [rax-0D8h]
0x14008b886  sub     rsp, 1B8h
0x14008b88d  movaps  xmmword ptr [rax-38h], xmm6
0x14008b891  mov     rax, cs:__security_cookie
0x14008b898  xor     rax, rsp
0x14008b89b  mov     [rbp+0D0h+var_40], rax
0x14008b8a2  mov     rbx, rdx
0x14008b8a5  lea     r8, aRepositoryIsre; "Repository::IsRepositoryPathCurrent"
0x14008b8ac  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008b8b3  lea     rcx, [rbp+0D0h+var_C0]; this
0x14008b8b7  call    ??0ScopeTracker@Uev@@QEAA@PEB_W0@Z; Uev::ScopeTracker::ScopeTracker(wchar_t const *,wchar_t const *)
0x14008b8bc  nop
0x14008b8bd  xor     sil, sil
0x14008b8c0  xorps   xmm0, xmm0
0x14008b8c3  movups  [rsp+1D0h+var_190+8], xmm0
0x14008b8c8  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14008b8d0  movdqu  [rsp+1D0h+var_180+8], xmm6
0x14008b8d6  xor     eax, eax
0x14008b8d8  mov     word ptr [rsp+1D0h+var_190+8], ax
0x14008b8dd  lea     r8, aRepositoryGetc; "Repository::GetCurrentRepositoryPath"
0x14008b8e4  lea     rdx, aCscchangemanag; "CscChangeManager"
0x14008b8eb  lea     rcx, [rbp+0D0h+var_140]; this
0x14008b8ef  call    ??0ScopeTracker@Uev@@QEAA@PEB_W0@Z; Uev::ScopeTracker::ScopeTracker(wchar_t const *,wchar_t const *)
0x14008b8f4  nop
0x14008b8f5  xorps   xmm0, xmm0
0x14008b8f8  movups  [rsp+1D0h+var_170+8], xmm0
0x14008b8fd  mov     [rsp+1D0h+var_158], 0
0x14008b906  mov     [rbp+0D0h+var_150], 7
0x14008b90e  xor     eax, eax
0x14008b910  mov     word ptr [rsp+1D0h+var_170+8], ax
0x14008b915  mov     qword ptr [rsp+1D0h+var_190], rax
0x14008b91a  mov     qword ptr [rsp+1D0h+var_180+8], rax
0x14008b91f  lea     rcx, [rsp+1D0h+var_190+8]
0x14008b924  cmp     qword ptr [rsp+1D0h+var_170], 7
0x14008b92a  cmova   rcx, qword ptr [rsp+1D0h+var_190+8]
0x14008b930  mov     [rcx], ax
0x14008b933  call    ?Instance@?$Singleton@VConfiguration@Uev@@V12@@Uev@@SAPEAVConfiguration@2@XZ; Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance(void)
0x14008b938  lea     rcx, [rax+4A10h]
0x14008b93f  lea     r8, [rsp+1D0h+var_190]
0x14008b944  lea     rdx, [rsp+1D0h+var_170+8]
0x14008b949  call    ?Get@?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Uev@@QEBA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUSettingInfo@2@@Z; Uev::Setting<std::wstring>::Get(std::wstring &,Uev::SettingInfo &)
0x14008b94e  mov     dil, al
0x14008b951  test    al, al
0x14008b953  jz      short loc_14008B976
0x14008b955  cmp     [rsp+1D0h+var_158], 0
0x14008b95b  jz      short loc_14008B971
0x14008b95d  mov     dil, 1
0x14008b960  lea     rdx, [rsp+1D0h+var_170+8]
0x14008b965  lea     rcx, [rsp+1D0h+var_190+8]
0x14008b96a  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14008b96f  jmp     short loc_14008B9A8
0x14008b971  xor     dil, dil
0x14008b974  jmp     short loc_14008B9A8
0x14008b976  cmp     dword ptr [rsp+1D0h+var_190], 2
0x14008b97b  jz      short loc_14008B9A8
0x14008b97d  xorps   xmm0, xmm0
0x14008b980  movups  [rsp+1D0h+var_1B8+8], xmm0
0x14008b985  movdqu  [rsp+1D0h+var_1A8+8], xmm6
0x14008b98b  xor     eax, eax
0x14008b98d  mov     word ptr [rsp+1D0h+var_1B8+8], ax
0x14008b992  lea     rdx, [rsp+1D0h+var_1B8+8]; struct boost::filesystem::path *
0x14008b997  call    ?SetCurrentRepositoryPath@Repository@Uev@@AEBAXAEBVpath@filesystem@boost@@@Z; Uev::Repository::SetCurrentRepositoryPath(boost::filesystem::path const &)
0x14008b99c  nop
0x14008b99d  lea     rcx, [rsp+1D0h+var_1B8+8]
0x14008b9a2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008b9a7  nop
0x14008b9a8  lea     rcx, [rsp+1D0h+var_170+8]
0x14008b9ad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008b9b2  nop
0x14008b9b3  lea     rcx, [rbp+0D0h+var_140]; this
0x14008b9b7  call    ??1ScopeTracker@Uev@@UEAA@XZ; Uev::ScopeTracker::~ScopeTracker(void)
0x14008b9bc  test    dil, dil
0x14008b9bf  jz      short loc_14008B9F4
0x14008b9c1  cmp     qword ptr [rbx+18h], 7
0x14008b9c6  jbe     short loc_14008B9CB
0x14008b9c8  mov     rbx, [rbx]
0x14008b9cb  lea     rcx, [rsp+1D0h+var_190+8]
0x14008b9d0  cmp     qword ptr [rsp+1D0h+var_170], 7
0x14008b9d6  cmova   rcx, qword ptr [rsp+1D0h+var_190+8]
0x14008b9dc  mov     rdx, rbx
0x14008b9df  call    cs:__imp__o__wcsicmp
0x14008b9e5  test    eax, eax
0x14008b9e7  jnz     short loc_14008B9EE
0x14008b9e9  mov     sil, 1
0x14008b9ec  jmp     short loc_14008B9F4
0x14008b9ee  call    ?ClearCurrentRepositoryPath@Repository@Uev@@AEBAXXZ; Uev::Repository::ClearCurrentRepositoryPath(void)
0x14008b9f3  nop
0x14008b9f4  lea     rcx, [rsp+1D0h+var_190+8]
0x14008b9f9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008b9fe  nop
0x14008b9ff  lea     rcx, [rbp+0D0h+var_C0]; this
0x14008ba03  call    ??1ScopeTracker@Uev@@UEAA@XZ; Uev::ScopeTracker::~ScopeTracker(void)
0x14008ba08  mov     al, sil
0x14008ba0b  mov     rcx, [rbp+0D0h+var_40]
0x14008ba12  xor     rcx, rsp; StackCookie
0x14008ba15  call    __security_check_cookie
0x14008ba1a  movaps  xmm6, [rsp+1D0h+var_38+8]
0x14008ba22  add     rsp, 1B8h
0x14008ba29  pop     rdi
0x14008ba2a  pop     rsi
0x14008ba2b  pop     rbx
0x14008ba2c  pop     rbp
0x14008ba2d  retn
```
