# uus::Session::GetFullPath(wchar_t const *)

- ea: `0x180002f78`
- end: `0x1800030b3`
- name: `?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEB_W@Z`
- size: `315`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003128`

## callees

- `0x180001fe4`
- `0x18000297c`
- `0x180002f78`
- `0x180004348`
- `0x18000593c`
- `0x1800078ac`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003055`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void *__fastcall uus::Session::GetFullPath(__int64 a1, void *a2)
{
  __int64 v4; // rbx
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rax
  LPVOID pv[2]; // [rsp+20h] [rbp-39h] BYREF
  __int128 v10; // [rsp+30h] [rbp-29h] BYREF
  __int64 v11; // [rsp+40h] [rbp-19h]
  __int64 v12; // [rsp+48h] [rbp-11h]
  __int128 v13; // [rsp+50h] [rbp-9h] BYREF
  __int64 v14; // [rsp+60h] [rbp+7h]
  __int64 v15; // [rsp+68h] [rbp+Fh]
  __int128 v16; // [rsp+70h] [rbp+17h] BYREF
  __int64 v17; // [rsp+80h] [rbp+27h]
  __int64 v18; // [rsp+88h] [rbp+2Fh]

  pv[0] = a2;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( *(&Src + v5) );
  v16 = 0;
  v17 = 0;
  v18 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v16, &Src, v5);
  v6 = *(_QWORD *)(a1 + 8);
  if ( v6 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 40LL))(v6, 1);
    do
      ++v4;
    while ( *(_WORD *)(v7 + 2 * v4) );
    v10 = 0;
    v11 = 0;
    v12 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v10, v7, v4);
  }
  else
  {
    pv[0] = 0;
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(pv);
    do
      ++v4;
    while ( *((_WORD *)pv[0] + v4) );
    v13 = 0;
    v14 = 0;
    v15 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v13, pv[0], v4);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    uus::Utility::GetGuestOrNativeArchFolder(&v10, &v13);
    std::wstring::~wstring(&v13);
  }
  std::filesystem::operator/(a2, (struct std::filesystem::path *)&v10, &v16);
  std::wstring::~wstring(&v10);
  std::wstring::~wstring(&v16);
  return a2;
}

```

## disassembly

```asm
0x180002f78  mov     [rsp-8+arg_10], rbx
0x180002f7d  mov     [rsp-8+arg_18], rsi
0x180002f82  push    rbp
0x180002f83  push    rdi
0x180002f84  push    r14
0x180002f86  lea     rbp, [rsp-47h]
0x180002f8b  sub     rsp, 0A0h
0x180002f92  mov     rdi, rdx
0x180002f95  mov     rsi, rcx
0x180002f98  mov     [rbp+57h+pv], rdx
0x180002f9c  xor     r14d, r14d
0x180002f9f  lea     rdx, Src
0x180002fa6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002faa  mov     r8, rbx
0x180002fad  inc     r8
0x180002fb0  cmp     [rdx+r8*2], r14w
0x180002fb5  jnz     short loc_180002FAD
0x180002fb7  xorps   xmm0, xmm0
0x180002fba  movups  [rbp+57h+var_40], xmm0
0x180002fbe  mov     [rbp+57h+var_30], r14
0x180002fc2  mov     [rbp+57h+var_28], r14
0x180002fc6  lea     rcx, [rbp+57h+var_40]
0x180002fca  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002fcf  nop
0x180002fd0  mov     rcx, [rsi+8]
0x180002fd4  test    rcx, rcx
0x180002fd7  jz      short loc_180003014
0x180002fd9  mov     rax, [rcx]
0x180002fdc  mov     edx, 1
0x180002fe1  mov     rax, [rax+28h]
0x180002fe5  call    _guard_dispatch_icall
0x180002fea  inc     rbx
0x180002fed  cmp     [rax+rbx*2], r14w
0x180002ff2  jnz     short loc_180002FEA
0x180002ff4  xorps   xmm0, xmm0
0x180002ff7  movups  [rbp+57h+var_80], xmm0
0x180002ffb  mov     [rbp+57h+var_70], r14
0x180002fff  mov     [rbp+57h+var_68], r14
0x180003003  mov     r8, rbx
0x180003006  mov     rdx, rax
0x180003009  lea     rcx, [rbp+57h+var_80]
0x18000300d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180003012  jmp     short loc_180003074
0x180003014  mov     [rbp+57h+pv], r14
0x180003018  lea     rcx, [rbp+57h+pv]
0x18000301c  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180003021  nop
0x180003022  mov     rdx, [rbp+57h+pv]
0x180003026  inc     rbx
0x180003029  cmp     [rdx+rbx*2], r14w
0x18000302e  jnz     short loc_180003026
0x180003030  xorps   xmm0, xmm0
0x180003033  movups  [rbp+57h+var_60], xmm0
0x180003037  mov     [rbp+57h+var_50], r14
0x18000303b  mov     [rbp+57h+var_48], r14
0x18000303f  mov     r8, rbx
0x180003042  lea     rcx, [rbp+57h+var_60]
0x180003046  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000304b  nop
0x18000304c  mov     rcx, [rbp+57h+pv]; pv
0x180003050  test    rcx, rcx
0x180003053  jz      short loc_18000305C
0x180003055  call    cs:__imp_CoTaskMemFree
0x18000305b  nop
0x18000305c  lea     rdx, [rbp+57h+var_60]
0x180003060  lea     rcx, [rbp+57h+var_80]
0x180003064  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x180003069  nop
0x18000306a  lea     rcx, [rbp+57h+var_60]
0x18000306e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180003073  nop
0x180003074  lea     r8, [rbp+57h+var_40]; void *
0x180003078  lea     rdx, [rbp+57h+var_80]; struct std::filesystem::path *
0x18000307c  mov     rcx, rdi; Src
0x18000307f  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180003084  nop
0x180003085  lea     rcx, [rbp+57h+var_80]
0x180003089  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000308e  nop
0x18000308f  lea     rcx, [rbp+57h+var_40]
0x180003093  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180003098  mov     rax, rdi
0x18000309b  lea     r11, [rsp+0B0h+var_10]
0x1800030a3  mov     rbx, [r11+30h]
0x1800030a7  mov     rsi, [r11+38h]
0x1800030ab  mov     rsp, r11
0x1800030ae  pop     r14
0x1800030b0  pop     rdi
0x1800030b1  pop     rbp
0x1800030b2  retn
```
