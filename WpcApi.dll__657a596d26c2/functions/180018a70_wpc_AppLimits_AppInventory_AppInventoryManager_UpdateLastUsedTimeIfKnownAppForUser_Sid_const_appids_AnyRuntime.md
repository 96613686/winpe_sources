# wpc::AppLimits::AppInventory::AppInventoryManager::UpdateLastUsedTimeIfKnownAppForUser(Sid const &,appids::AnyRuntimeApp const &)

- ea: `0x180018a70`
- end: `0x180018d8e`
- name: `?UpdateLastUsedTimeIfKnownAppForUser@AppInventoryManager@AppInventory@AppLimits@wpc@@QEAA_NAEBVSid@@AEBVAnyRuntimeApp@appids@@@Z`
- size: `798`
- prototype: `bool(wpc::AppLimits::AppInventory::AppInventoryManager *__hidden this, const struct Sid *, const struct appids::AnyRuntimeApp *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180014370`

## callees

- `0x1800032a0`
- `0x180005950`
- `0x180005a04`
- `0x180005f9c`
- `0x18000dc7c`
- `0x180014d98`
- `0x1800154dc`
- `0x180017178`
- `0x1800184e8`
- `0x180018a70`
- `0x18001944c`
- `0x18001bae4`
- `0x18001c724`
- `0x18001ca8c`
- `0x18002c010`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x180018b32`
- `KERNEL32!CompareFileTime` at `0x180018c56`
- `KERNEL32!CompareFileTime` at `0x180018b32`
- `KERNEL32!CompareFileTime` at `0x180018c56`

## string_xrefs

- `0x180018b5e`: `App {0} will update for user {1}`
- `0x180018c82`: `App {0} will update for user {1}`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall wpc::AppLimits::AppInventory::AppInventoryManager::UpdateLastUsedTimeIfKnownAppForUser(
        wpc::AppLimits::AppInventory::AppInventoryManager *this,
        const struct Sid *a2,
        const struct appids::AnyRuntimeApp *a3)
{
  const wchar_t *v5; // rax
  _QWORD *v6; // rdi
  __int64 v7; // rbx
  _QWORD *v8; // rdx
  const FILETIME *v9; // rax
  Private::Format *v10; // rbx
  Private::Format *v11; // rbx
  _QWORD *v12; // rax
  _QWORD *v13; // rdx
  const FILETIME *v14; // rax
  Private::Format *v15; // rbx
  Private::Format *v16; // rbx
  _QWORD *v17; // rax
  _QWORD v19[2]; // [rsp+20h] [rbp-79h] BYREF
  __int64 v20; // [rsp+30h] [rbp-69h] BYREF
  const wchar_t **v21; // [rsp+38h] [rbp-61h]
  FILETIME FileTime1; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v23[16]; // [rsp+50h] [rbp-49h] BYREF
  __int128 v24; // [rsp+60h] [rbp-39h] BYREF
  __int64 v25; // [rsp+70h] [rbp-29h]
  __int64 v26; // [rsp+78h] [rbp-21h]
  char *v27[4]; // [rsp+80h] [rbp-19h] BYREF
  char *v28[5]; // [rsp+A0h] [rbp+7h] BYREF

  (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)this + 48LL))(*(_QWORD *)this, &v20);
  v5 = std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::_Find<Sid>(
         v21,
         (__int64)a2);
  if ( v5 == *v21
    || (v6 = v5 + 68,
        std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::find(
          v5 + 68,
          v19,
          a3),
        v7 = v19[0],
        v19[0] == *v6) )
  {
LABEL_26:
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
    return 0;
  }
  DateTime::GetCurrent((__int64)&FileTime1);
  if ( *(_BYTE *)(v7 + 336) )
  {
    v8 = (_QWORD *)(v7 + 304);
    if ( *(_QWORD *)(v7 + 328) > 7u )
      v8 = (_QWORD *)*v8;
    DateTime::Deserialize((__int64)v19, v8);
    v9 = (const FILETIME *)DateTime::operator+(v19, v23, &qword_18004A3B8);
    if ( CompareFileTime(&FileTime1, v9) > -1 )
    {
      v24 = 0;
      v25 = 0;
      v26 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v24, L"App {0} will update for user {1}", 0x20u);
      v10 = (Private::Format *)StringAlgo::FormatString(v28, &v24);
      std::wstring::wstring((__int64)v27, (__int64)a3 + 48);
      v11 = (Private::Format *)Private::Format::operator%<std::wstring>(v10);
      std::wstring::wstring((__int64)&v24, (__int64)a2 + 72);
      v12 = (_QWORD *)Private::Format::operator%<std::wstring>(v11);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        if ( v12[3] > 7u )
          v12 = (_QWORD *)*v12;
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_e79369f3d8d632091aecb665c0941012_Traceguids, v12);
      }
      std::wstring::~wstring((char **)&v24);
      std::wstring::~wstring(v27);
      std::wstring::~wstring(v28);
      goto LABEL_26;
    }
  }
  else if ( *(_BYTE *)(v7 + 256) )
  {
    v13 = (_QWORD *)(v7 + 224);
    if ( *(_QWORD *)(v7 + 248) > 7u )
      v13 = (_QWORD *)*v13;
    DateTime::Deserialize((__int64)v19, v13);
    v14 = (const FILETIME *)DateTime::operator+(v19, v23, &qword_18004A3A8);
    if ( CompareFileTime(&FileTime1, v14) > -1 )
    {
      v24 = 0;
      v25 = 0;
      v26 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v24, L"App {0} will update for user {1}", 0x20u);
      v15 = (Private::Format *)StringAlgo::FormatString(v28, &v24);
      std::wstring::wstring((__int64)&v24, (__int64)a3 + 48);
      v16 = (Private::Format *)Private::Format::operator%<std::wstring>(v15);
      std::wstring::wstring((__int64)v27, (__int64)a2 + 72);
      v17 = (_QWORD *)Private::Format::operator%<std::wstring>(v16);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        if ( v17[3] > 7u )
          v17 = (_QWORD *)*v17;
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_e79369f3d8d632091aecb665c0941012_Traceguids, v17);
      }
      std::wstring::~wstring(v27);
      std::wstring::~wstring((char **)&v24);
      std::wstring::~wstring(v28);
      goto LABEL_26;
    }
  }
  wpc::AppLimits::AppInventory::AppInventoryStorage::UpdateLastUsedTimeForUserApp(
    a2,
    (struct wpc::AppLimits::AppInventory::AppInfo *)(v7 + 112));
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
  return 1;
}

```

## disassembly

```asm
0x180018a70  push    rbp
0x180018a72  push    rbx
0x180018a73  push    rsi
0x180018a74  push    rdi
0x180018a75  push    r14
0x180018a77  lea     rbp, [rsp-37h]
0x180018a7c  sub     rsp, 0D0h
0x180018a83  mov     rax, cs:__security_cookie
0x180018a8a  xor     rax, rsp
0x180018a8d  mov     [rbp+57h+var_28], rax
0x180018a91  mov     r14, r8
0x180018a94  mov     rsi, rdx
0x180018a97  mov     rcx, [rcx]
0x180018a9a  mov     rax, [rcx]
0x180018a9d  lea     rdx, [rbp+57h+var_C0]
0x180018aa1  mov     rax, [rax+30h]
0x180018aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018aaa  nop
0x180018aab  mov     rdx, rsi
0x180018aae  mov     rcx, [rbp+57h+var_B8]
0x180018ab2  call    ??$_Find@VSid@@@?$_Tree@V?$_Tmap_traits@VSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@U?$less@VSid@@@3@V?$allocator@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@3@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@1@AEBVSid@@@Z; std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::_Find<Sid>(Sid const &)
0x180018ab7  mov     rcx, [rbp+57h+var_B8]
0x180018abb  cmp     rax, [rcx]
0x180018abe  jz      loc_180018D5C
0x180018ac4  lea     rdi, [rax+88h]
0x180018acb  mov     r8, r14
0x180018ace  lea     rdx, [rbp+57h+var_D0]
0x180018ad2  mov     rcx, rdi
0x180018ad5  call    ?find@?$_Tree@V?$_Tmap_traits@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@std@@@std@@@2@AEBVAnyRuntimeApp@appids@@@Z; std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::find(appids::AnyRuntimeApp const &)
0x180018ada  mov     rbx, [rbp+57h+var_D0]
0x180018ade  cmp     rbx, [rdi]
0x180018ae1  jz      loc_180018D5C
0x180018ae7  lea     rcx, [rbp+57h+FileTime1]
0x180018aeb  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x180018af0  cmp     byte ptr [rbx+150h], 0
0x180018af7  jz      loc_180018C14
0x180018afd  lea     rdx, [rbx+130h]
0x180018b04  cmp     qword ptr [rdx+18h], 7
0x180018b09  jbe     short loc_180018B0E
0x180018b0b  mov     rdx, [rdx]
0x180018b0e  lea     rcx, [rbp+57h+var_D0]
0x180018b12  call    ?Deserialize@DateTime@@SA?AV1@QEBG@Z; DateTime::Deserialize(ushort const * const)
0x180018b17  lea     r8, qword_18004A3B8
0x180018b1e  lea     rdx, [rbp+57h+var_A0]
0x180018b22  lea     rcx, [rbp+57h+var_D0]
0x180018b26  call    ??HDateTime@@QEBA?AV0@AEBVTimeSpan@@@Z; DateTime::operator+(TimeSpan const &)
0x180018b2b  mov     rdx, rax; lpFileTime2
0x180018b2e  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180018b32  call    cs:__imp_CompareFileTime
0x180018b38  cmp     eax, 0FFFFFFFFh
0x180018b3b  jle     loc_180018D35
0x180018b41  xorps   xmm0, xmm0
0x180018b44  movups  [rbp+57h+var_90], xmm0
0x180018b48  mov     [rbp+57h+var_80], 0
0x180018b50  mov     [rbp+57h+var_78], 0
0x180018b58  mov     r8d, 20h ; ' '
0x180018b5e  lea     rdx, aApp0WillUpdate; "App {0} will update for user {1}"
0x180018b65  lea     rcx, [rbp+57h+var_90]
0x180018b69  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018b6e  lea     rdx, [rbp+57h+var_90]
0x180018b72  lea     rcx, [rbp+57h+var_50]
0x180018b76  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x180018b7b  mov     rbx, rax
0x180018b7e  lea     rdx, [r14+30h]
0x180018b82  lea     rcx, [rbp+57h+var_70]
0x180018b86  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018b8b  nop
0x180018b8c  lea     rdx, [rbp+57h+var_70]
0x180018b90  mov     rcx, rbx; this
0x180018b93  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x180018b98  mov     rbx, rax
0x180018b9b  lea     rdx, [rsi+48h]
0x180018b9f  lea     rcx, [rbp+57h+var_90]
0x180018ba3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018ba8  nop
0x180018ba9  lea     rdx, [rbp+57h+var_90]
0x180018bad  mov     rcx, rbx; this
0x180018bb0  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x180018bb5  lea     rdx, WPP_GLOBAL_Control
0x180018bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bc3  cmp     rcx, rdx
0x180018bc6  jz      short loc_180018BF1
0x180018bc8  test    byte ptr [rcx+1Ch], 4
0x180018bcc  jz      short loc_180018BF1
0x180018bce  cmp     qword ptr [rax+18h], 7
0x180018bd3  jbe     short loc_180018BD8
0x180018bd5  mov     rax, [rax]
0x180018bd8  mov     edx, 0Dh
0x180018bdd  mov     r9, rax
0x180018be0  lea     r8, WPP_e79369f3d8d632091aecb665c0941012_Traceguids
0x180018be7  mov     rcx, [rcx+10h]
0x180018beb  call    WPP_SF_S
0x180018bf0  nop
0x180018bf1  lea     rcx, [rbp+57h+var_90]
0x180018bf5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018bfa  nop
0x180018bfb  lea     rcx, [rbp+57h+var_70]
0x180018bff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018c04  nop
0x180018c05  lea     rcx, [rbp+57h+var_50]
0x180018c09  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018c0e  nop
0x180018c0f  jmp     loc_180018D5C
0x180018c14  cmp     byte ptr [rbx+100h], 0
0x180018c1b  jz      loc_180018D35
0x180018c21  lea     rdx, [rbx+0E0h]
0x180018c28  cmp     qword ptr [rdx+18h], 7
0x180018c2d  jbe     short loc_180018C32
0x180018c2f  mov     rdx, [rdx]
0x180018c32  lea     rcx, [rbp+57h+var_D0]
0x180018c36  call    ?Deserialize@DateTime@@SA?AV1@QEBG@Z; DateTime::Deserialize(ushort const * const)
0x180018c3b  lea     r8, qword_18004A3A8
0x180018c42  lea     rdx, [rbp+57h+var_A0]
0x180018c46  lea     rcx, [rbp+57h+var_D0]
0x180018c4a  call    ??HDateTime@@QEBA?AV0@AEBVTimeSpan@@@Z; DateTime::operator+(TimeSpan const &)
0x180018c4f  mov     rdx, rax; lpFileTime2
0x180018c52  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180018c56  call    cs:__imp_CompareFileTime
0x180018c5c  cmp     eax, 0FFFFFFFFh
0x180018c5f  jle     loc_180018D35
0x180018c65  xorps   xmm0, xmm0
0x180018c68  movups  [rbp+57h+var_90], xmm0
0x180018c6c  mov     [rbp+57h+var_80], 0
0x180018c74  mov     [rbp+57h+var_78], 0
0x180018c7c  mov     r8d, 20h ; ' '
0x180018c82  lea     rdx, aApp0WillUpdate; "App {0} will update for user {1}"
0x180018c89  lea     rcx, [rbp+57h+var_90]
0x180018c8d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018c92  lea     rdx, [rbp+57h+var_90]
0x180018c96  lea     rcx, [rbp+57h+var_50]
0x180018c9a  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x180018c9f  mov     rbx, rax
0x180018ca2  lea     rdx, [r14+30h]
0x180018ca6  lea     rcx, [rbp+57h+var_90]
0x180018caa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018caf  nop
0x180018cb0  lea     rdx, [rbp+57h+var_90]
0x180018cb4  mov     rcx, rbx; this
0x180018cb7  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x180018cbc  mov     rbx, rax
0x180018cbf  lea     rdx, [rsi+48h]
0x180018cc3  lea     rcx, [rbp+57h+var_70]
0x180018cc7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018ccc  nop
0x180018ccd  lea     rdx, [rbp+57h+var_70]
0x180018cd1  mov     rcx, rbx; this
0x180018cd4  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x180018cd9  lea     rdx, WPP_GLOBAL_Control
0x180018ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ce7  cmp     rcx, rdx
0x180018cea  jz      short loc_180018D15
0x180018cec  test    byte ptr [rcx+1Ch], 4
0x180018cf0  jz      short loc_180018D15
0x180018cf2  cmp     qword ptr [rax+18h], 7
0x180018cf7  jbe     short loc_180018CFC
0x180018cf9  mov     rax, [rax]
0x180018cfc  mov     edx, 0Dh
0x180018d01  mov     r9, rax
0x180018d04  lea     r8, WPP_e79369f3d8d632091aecb665c0941012_Traceguids
0x180018d0b  mov     rcx, [rcx+10h]
0x180018d0f  call    WPP_SF_S
0x180018d14  nop
0x180018d15  lea     rcx, [rbp+57h+var_70]
0x180018d19  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018d1e  nop
0x180018d1f  lea     rcx, [rbp+57h+var_90]
0x180018d23  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018d28  nop
0x180018d29  lea     rcx, [rbp+57h+var_50]
0x180018d2d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018d32  nop
0x180018d33  jmp     short loc_180018D5C
0x180018d35  lea     rdx, [rbx+70h]; struct wpc::AppLimits::AppInventory::AppInfo *
0x180018d39  mov     rcx, rsi; struct Sid *
0x180018d3c  call    ?UpdateLastUsedTimeForUserApp@AppInventoryStorage@AppInventory@AppLimits@wpc@@SAXAEBVSid@@AEAUAppInfo@234@@Z; wpc::AppLimits::AppInventory::AppInventoryStorage::UpdateLastUsedTimeForUserApp(Sid const &,wpc::AppLimits::AppInventory::AppInfo &)
0x180018d41  nop
0x180018d42  mov     rcx, [rbp+57h+var_C0]
0x180018d46  test    rcx, rcx
0x180018d49  jz      short loc_180018D58
0x180018d4b  mov     rax, [rcx]
0x180018d4e  mov     rax, [rax+18h]
0x180018d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d57  nop
0x180018d58  mov     al, 1
0x180018d5a  jmp     short loc_180018D74
0x180018d5c  mov     rcx, [rbp+57h+var_C0]
0x180018d60  test    rcx, rcx
0x180018d63  jz      short loc_180018D72
0x180018d65  mov     rax, [rcx]
0x180018d68  mov     rax, [rax+18h]
0x180018d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d71  nop
0x180018d72  xor     al, al
0x180018d74  mov     rcx, [rbp+57h+var_28]
0x180018d78  xor     rcx, rsp; StackCookie
0x180018d7b  call    __security_check_cookie
0x180018d80  add     rsp, 0D0h
0x180018d87  pop     r14
0x180018d89  pop     rdi
0x180018d8a  pop     rsi
0x180018d8b  pop     rbx
0x180018d8c  pop     rbp
0x180018d8d  retn
```
