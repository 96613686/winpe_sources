# uus::Session::GetFullPath(wchar_t const *)

- ea: `0x140044500`
- end: `0x14004463a`
- name: `?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEB_W@Z`
- size: `314`
- prototype: `struct std::filesystem::path __high(const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140040ef8`

## callees

- `0x1400071c0`
- `0x1400073f0`
- `0x140043a98`
- `0x140043c40`
- `0x140044450`
- `0x140044500`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400445dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400445dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall uus::Session::GetFullPath(__int64 a1, _QWORD *a2, _WORD *a3)
{
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // r8
  __int64 v8; // rcx
  _WORD *v9; // rax
  LPVOID pv[2]; // [rsp+20h] [rbp-39h] BYREF
  __int128 Src; // [rsp+30h] [rbp-29h] BYREF
  __int64 v13; // [rsp+40h] [rbp-19h]
  __int64 v14; // [rsp+48h] [rbp-11h]
  __int128 v15; // [rsp+50h] [rbp-9h] BYREF
  __int64 v16; // [rsp+60h] [rbp+7h]
  __int64 v17; // [rsp+68h] [rbp+Fh]
  __int128 v18; // [rsp+70h] [rbp+17h] BYREF
  __int64 v19; // [rsp+80h] [rbp+27h]
  __int64 v20; // [rsp+88h] [rbp+2Fh]

  pv[0] = a2;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  v18 = 0;
  v19 = 0;
  v20 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v18, a3, v7);
  v8 = *(_QWORD *)(a1 + 8);
  if ( v8 )
  {
    v9 = (_WORD *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
    do
      ++v6;
    while ( v9[v6] );
    Src = 0;
    v13 = 0;
    v14 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src, v9, v6);
  }
  else
  {
    pv[0] = 0;
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>((char *)pv);
    do
      ++v6;
    while ( *((_WORD *)pv[0] + v6) );
    v15 = 0;
    v16 = 0;
    v17 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v15, pv[0], v6);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    uus::Utility::GetGuestOrNativeArchFolder(&Src, &v15);
    std::wstring::~wstring(&v15);
  }
  std::filesystem::operator/(a2, &Src, &v18);
  std::wstring::~wstring(&Src);
  std::wstring::~wstring(&v18);
  return a2;
}

```

## disassembly

```asm
0x140044500  mov     [rsp-8+arg_10], rbx
0x140044505  mov     [rsp-8+arg_18], rsi
0x14004450a  push    rbp
0x14004450b  push    rdi
0x14004450c  push    r14
0x14004450e  lea     rbp, [rsp-47h]
0x140044513  sub     rsp, 0A0h
0x14004451a  mov     rax, r8
0x14004451d  mov     rdi, rdx
0x140044520  mov     rsi, rcx
0x140044523  mov     [rbp+57h+pv], rdx
0x140044527  xor     r14d, r14d
0x14004452a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14004452e  mov     r8, rbx
0x140044531  inc     r8
0x140044534  cmp     [rax+r8*2], r14w
0x140044539  jnz     short loc_140044531
0x14004453b  xorps   xmm0, xmm0
0x14004453e  movups  [rbp+57h+var_40], xmm0
0x140044542  mov     [rbp+57h+var_30], r14
0x140044546  mov     [rbp+57h+var_28], r14
0x14004454a  mov     rdx, rax
0x14004454d  lea     rcx, [rbp+57h+var_40]
0x140044551  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140044556  nop
0x140044557  mov     rcx, [rsi+8]
0x14004455b  test    rcx, rcx
0x14004455e  jz      short loc_14004459B
0x140044560  mov     rax, [rcx]
0x140044563  mov     edx, 1
0x140044568  mov     rax, [rax+28h]
0x14004456c  call    _guard_dispatch_icall
0x140044571  inc     rbx
0x140044574  cmp     [rax+rbx*2], r14w
0x140044579  jnz     short loc_140044571
0x14004457b  xorps   xmm0, xmm0
0x14004457e  movups  [rbp+57h+Src], xmm0
0x140044582  mov     [rbp+57h+var_70], r14
0x140044586  mov     [rbp+57h+var_68], r14
0x14004458a  mov     r8, rbx
0x14004458d  mov     rdx, rax
0x140044590  lea     rcx, [rbp+57h+Src]
0x140044594  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140044599  jmp     short loc_1400445FB
0x14004459b  mov     [rbp+57h+pv], r14
0x14004459f  lea     rcx, [rbp+57h+pv]
0x1400445a3  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x1400445a8  nop
0x1400445a9  mov     rdx, [rbp+57h+pv]
0x1400445ad  inc     rbx
0x1400445b0  cmp     [rdx+rbx*2], r14w
0x1400445b5  jnz     short loc_1400445AD
0x1400445b7  xorps   xmm0, xmm0
0x1400445ba  movups  [rbp+57h+var_60], xmm0
0x1400445be  mov     [rbp+57h+var_50], r14
0x1400445c2  mov     [rbp+57h+var_48], r14
0x1400445c6  mov     r8, rbx
0x1400445c9  lea     rcx, [rbp+57h+var_60]
0x1400445cd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400445d2  nop
0x1400445d3  mov     rcx, [rbp+57h+pv]; pv
0x1400445d7  test    rcx, rcx
0x1400445da  jz      short loc_1400445E3
0x1400445dc  call    cs:__imp_CoTaskMemFree
0x1400445e2  nop
0x1400445e3  lea     rdx, [rbp+57h+var_60]
0x1400445e7  lea     rcx, [rbp+57h+Src]
0x1400445eb  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x1400445f0  nop
0x1400445f1  lea     rcx, [rbp+57h+var_60]; void *
0x1400445f5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400445fa  nop
0x1400445fb  lea     r8, [rbp+57h+var_40]; void *
0x1400445ff  lea     rdx, [rbp+57h+Src]; Src
0x140044603  mov     rcx, rdi; void *
0x140044606  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x14004460b  nop
0x14004460c  lea     rcx, [rbp+57h+Src]; void *
0x140044610  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140044615  nop
0x140044616  lea     rcx, [rbp+57h+var_40]; void *
0x14004461a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004461f  mov     rax, rdi
0x140044622  lea     r11, [rsp+0B0h+var_10]
0x14004462a  mov     rbx, [r11+30h]
0x14004462e  mov     rsi, [r11+38h]
0x140044632  mov     rsp, r11
0x140044635  pop     r14
0x140044637  pop     rdi
0x140044638  pop     rbp
0x140044639  retn
```
