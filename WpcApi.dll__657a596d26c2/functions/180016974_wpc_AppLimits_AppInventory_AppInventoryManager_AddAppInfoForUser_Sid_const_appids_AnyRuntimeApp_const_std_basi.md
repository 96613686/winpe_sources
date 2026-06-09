# wpc::AppLimits::AppInventory::AppInventoryManager::AddAppInfoForUser(Sid const &,appids::AnyRuntimeApp const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180016974`
- end: `0x180016bf4`
- name: `?AddAppInfoForUser@AppInventoryManager@AppInventory@AppLimits@wpc@@QEAAXAEBVSid@@AEBVAnyRuntimeApp@appids@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `640`
- prototype: `__int64 __fastcall(_QWORD *, const struct Sid *, const struct appids::AnyRuntimeApp *, char **)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation`

## callers

- `0x180014600`

## callees

- `0x1800032a0`
- `0x1800032c4`
- `0x180005a04`
- `0x180005f9c`
- `0x18000f100`
- `0x1800154dc`
- `0x180015728`
- `0x180015888`
- `0x180015a54`
- `0x180015d60`
- `0x1800160ac`
- `0x180016574`
- `0x1800165f0`
- `0x180016974`
- `0x180018d94`
- `0x18001944c`
- `0x18001ca8c`
- `0x18001cad0`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall wpc::AppLimits::AppInventory::AppInventoryManager::AddAppInfoForUser(
        _QWORD *a1,
        const struct Sid *a2,
        const struct appids::AnyRuntimeApp *a3,
        char **a4)
{
  __int64 v8; // rbx
  appids::AnyRuntimeApp *v9; // rax
  __int64 Current; // rax
  const wchar_t *v11; // rax
  _QWORD *v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rdx
  _QWORD *v15; // rax
  __int128 v17; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t **v19; // [rsp+38h] [rbp-C8h]
  _QWORD v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[80]; // [rsp+70h] [rbp-90h] BYREF
  char **v23; // [rsp+C0h] [rbp-40h]
  char *v24[5]; // [rsp+C8h] [rbp-38h] BYREF
  char *v25[14]; // [rsp+F0h] [rbp-10h] BYREF
  char *v26[4]; // [rsp+160h] [rbp+60h] BYREF
  char v27; // [rsp+180h] [rbp+80h]
  _BYTE v28[32]; // [rsp+188h] [rbp+88h] BYREF
  char v29; // [rsp+1A8h] [rbp+A8h]
  _BYTE v30[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v31; // [rsp+1D0h] [rbp+D0h]

  v23 = a4;
  v20[0] = v21;
  v8 = std::wstring::wstring((__int64)v21, (__int64)a4);
  v9 = appids::AnyRuntimeApp::AnyRuntimeApp((appids::AnyRuntimeApp *)v22, a3);
  wpc::AppLimits::AppInventory::AppInfo::AppInfo(v25, v9, v8);
  Current = DateTime::GetCurrent(&v17);
  DateTime::Serialize(Current, v24);
  if ( v27 )
  {
    std::wstring::operator=(v26, v24);
  }
  else
  {
    std::wstring::wstring((__int64)v26, (__int64)v24);
    v27 = 1;
  }
  if ( v29 )
  {
    std::wstring::operator=(v28, v24);
  }
  else
  {
    std::wstring::wstring((__int64)v28, (__int64)v24);
    v29 = 1;
  }
  (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 48LL))(*a1, &v18);
  v11 = std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::_Find<Sid>(
          v19,
          (__int64)a2);
  if ( v11 == *v19 )
  {
    v17 = 0;
    v15 = operator new(0x158u);
    *v15 = v15;
    v15[1] = v15;
    v15[2] = v15;
    *((_WORD *)v15 + 12) = 257;
    *(_QWORD *)&v17 = v15;
    ((void (__fastcall *)(__int128 *, _QWORD *, const struct appids::AnyRuntimeApp *, char **))std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::emplace<appids::AnyRuntimeApp const &,wpc::AppLimits::AppInventory::AppInfo &>)(
      &v17,
      v20,
      a3,
      v25);
    std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::emplace<Sid const &,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo> &>(
      (__int64 *)v19,
      (__int64)v20,
      (__int64)a2,
      &v17);
    std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::~_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>((void **)&v17);
  }
  else
  {
    v12 = v11 + 68;
    std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::find(
      v11 + 68,
      v20,
      a3);
    v13 = v20[0];
    if ( v20[0] == *v12 )
    {
      ((void (__fastcall *)(_QWORD *, __int128 *, const struct appids::AnyRuntimeApp *, char **))std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::emplace<appids::AnyRuntimeApp const &,wpc::AppLimits::AppInventory::AppInfo &>)(
        v12,
        &v17,
        a3,
        v25);
    }
    else
    {
      v14 = v20[0] + 224LL;
      if ( *(_BYTE *)(v20[0] + 256LL) )
      {
        if ( v27 )
        {
          std::wstring::operator=(v26, v14);
        }
        else
        {
          std::wstring::wstring((__int64)v26, v14);
          v27 = 1;
        }
      }
      else if ( v27 )
      {
        std::wstring::~wstring(v26);
        v27 = 0;
      }
      if ( v31 )
      {
        std::wstring::operator=(v30, v24);
      }
      else
      {
        std::wstring::wstring((__int64)v30, (__int64)v24);
        v31 = 1;
      }
      wpc::AppLimits::AppInventory::AppInfo::operator=(v13 + 112, v25);
    }
  }
  wpc::AppLimits::AppInventory::AppInventoryStorage::WriteAppInfoForUser(
    a2,
    (const struct wpc::AppLimits::AppInventory::AppInfo *)v25);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 24LL))(v18);
    v18 = 0;
  }
  std::wstring::~wstring(v24);
  wpc::AppLimits::AppInventory::AppInfo::~AppInfo(v25);
  return std::wstring::~wstring(a4);
}

```

## disassembly

```asm
0x180016974  push    rbp
0x180016976  push    rbx
0x180016977  push    rsi
0x180016978  push    rdi
0x180016979  push    r14
0x18001697b  push    r15
0x18001697d  lea     rbp, [rsp-0F8h]
0x180016985  sub     rsp, 1F8h
0x18001698c  mov     rax, cs:__security_cookie
0x180016993  xor     rax, rsp
0x180016996  mov     [rbp+120h+var_40], rax
0x18001699d  mov     r15, r9
0x1800169a0  mov     rsi, r8
0x1800169a3  mov     r14, rdx
0x1800169a6  mov     rdi, rcx
0x1800169a9  mov     [rbp+120h+var_160], r9
0x1800169ad  lea     rax, [rsp+220h+var_1D0]
0x1800169b2  mov     [rsp+220h+var_1E0], rax
0x1800169b7  mov     rdx, r9
0x1800169ba  lea     rcx, [rsp+220h+var_1D0]
0x1800169bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800169c4  mov     rbx, rax
0x1800169c7  mov     rdx, rsi; struct appids::AnyRuntimeApp *
0x1800169ca  lea     rcx, [rsp+220h+var_1B0]; this
0x1800169cf  call    ??0AnyRuntimeApp@appids@@QEAA@AEBV01@@Z; appids::AnyRuntimeApp::AnyRuntimeApp(appids::AnyRuntimeApp const &)
0x1800169d4  nop
0x1800169d5  mov     r8, rbx
0x1800169d8  mov     rdx, rax
0x1800169db  lea     rcx, [rbp+120h+var_130]
0x1800169df  call    ??0AppInfo@AppInventory@AppLimits@wpc@@QEAA@VAnyRuntimeApp@appids@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::AppLimits::AppInventory::AppInfo::AppInfo(appids::AnyRuntimeApp,std::wstring)
0x1800169e4  nop
0x1800169e5  lea     rcx, [rsp+220h+var_200]
0x1800169ea  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x1800169ef  lea     rdx, [rbp+120h+var_158]
0x1800169f3  mov     rcx, rax
0x1800169f6  call    ?Serialize@DateTime@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DateTime::Serialize(void)
0x1800169fb  nop
0x1800169fc  lea     rdx, [rbp+120h+var_158]
0x180016a00  lea     rcx, [rbp+120h+var_C0]
0x180016a04  cmp     [rbp+120h+var_A0], 0
0x180016a0b  jz      short loc_180016A14
0x180016a0d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180016a12  jmp     short loc_180016A20
0x180016a14  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180016a19  mov     [rbp+120h+var_A0], 1
0x180016a20  lea     rdx, [rbp+120h+var_158]
0x180016a24  lea     rcx, [rbp+120h+var_98]
0x180016a2b  cmp     [rbp+120h+var_78], 0
0x180016a32  jz      short loc_180016A3B
0x180016a34  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180016a39  jmp     short loc_180016A47
0x180016a3b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180016a40  mov     [rbp+120h+var_78], 1
0x180016a47  mov     rcx, [rdi]
0x180016a4a  mov     rax, [rcx]
0x180016a4d  lea     rdx, [rsp+220h+var_1F0]
0x180016a52  mov     rax, [rax+30h]
0x180016a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a5b  nop
0x180016a5c  mov     rdx, r14
0x180016a5f  mov     rcx, [rsp+220h+var_1E8]
0x180016a64  call    ??$_Find@VSid@@@?$_Tree@V?$_Tmap_traits@VSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@U?$less@VSid@@@3@V?$allocator@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@3@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@1@AEBVSid@@@Z; std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::_Find<Sid>(Sid const &)
0x180016a69  mov     rcx, [rsp+220h+var_1E8]
0x180016a6e  cmp     rax, [rcx]
0x180016a71  jz      loc_180016B2C
0x180016a77  lea     rdi, [rax+88h]
0x180016a7e  mov     r8, rsi
0x180016a81  lea     rdx, [rsp+220h+var_1E0]
0x180016a86  mov     rcx, rdi
0x180016a89  call    ?find@?$_Tree@V?$_Tmap_traits@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@std@@@std@@@2@AEBVAnyRuntimeApp@appids@@@Z; std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::find(appids::AnyRuntimeApp const &)
0x180016a8e  mov     rbx, [rsp+220h+var_1E0]
0x180016a93  cmp     rbx, [rdi]
0x180016a96  jz      short loc_180016B16
0x180016a98  lea     rdx, [rbx+0E0h]
0x180016a9f  cmp     byte ptr [rdx+20h], 0
0x180016aa3  jz      short loc_180016AC7
0x180016aa5  lea     rcx, [rbp+120h+var_C0]
0x180016aa9  cmp     [rbp+120h+var_A0], 0
0x180016ab0  jz      short loc_180016AB9
0x180016ab2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180016ab7  jmp     short loc_180016AE0
0x180016ab9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180016abe  mov     [rbp+120h+var_A0], 1
0x180016ac5  jmp     short loc_180016AE0
0x180016ac7  cmp     [rbp+120h+var_A0], 0
0x180016ace  jz      short loc_180016AE0
0x180016ad0  lea     rcx, [rbp+120h+var_C0]
0x180016ad4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016ad9  mov     [rbp+120h+var_A0], 0
0x180016ae0  lea     rdx, [rbp+120h+var_158]
0x180016ae4  lea     rcx, [rbp+120h+var_70]
0x180016aeb  cmp     [rbp+120h+var_50], 0
0x180016af2  jz      short loc_180016AFB
0x180016af4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180016af9  jmp     short loc_180016B07
0x180016afb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180016b00  mov     [rbp+120h+var_50], 1
0x180016b07  lea     rcx, [rbx+70h]
0x180016b0b  lea     rdx, [rbp+120h+var_130]
0x180016b0f  call    ??4AppInfo@AppInventory@AppLimits@wpc@@QEAAAEAU0123@AEBU0123@@Z; wpc::AppLimits::AppInventory::AppInfo::operator=(wpc::AppLimits::AppInventory::AppInfo const &)
0x180016b14  jmp     short loc_180016B8D
0x180016b16  lea     r9, [rbp+120h+var_130]
0x180016b1a  mov     r8, rsi
0x180016b1d  lea     rdx, [rsp+220h+var_200]
0x180016b22  mov     rcx, rdi
0x180016b25  call    ??$emplace@AEBVAnyRuntimeApp@appids@@AEAUAppInfo@AppInventory@AppLimits@wpc@@@?$_Tree@V?$_Tmap_traits@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@std@@@std@@@std@@_N@1@AEBVAnyRuntimeApp@appids@@AEAUAppInfo@AppInventory@AppLimits@wpc@@@Z; std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::emplace<appids::AnyRuntimeApp const &,wpc::AppLimits::AppInventory::AppInfo &>(appids::AnyRuntimeApp const &,wpc::AppLimits::AppInventory::AppInfo &)
0x180016b2a  jmp     short loc_180016B8D
0x180016b2c  xorps   xmm0, xmm0
0x180016b2f  movdqu  [rsp+220h+var_200], xmm0
0x180016b35  mov     ecx, 158h; Size
0x180016b3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016b3f  mov     [rax], rax
0x180016b42  mov     [rax+8], rax
0x180016b46  mov     [rax+10h], rax
0x180016b4a  mov     word ptr [rax+18h], 101h
0x180016b50  mov     qword ptr [rsp+220h+var_200], rax
0x180016b55  lea     r9, [rbp+120h+var_130]
0x180016b59  mov     r8, rsi
0x180016b5c  lea     rdx, [rsp+220h+var_1E0]
0x180016b61  lea     rcx, [rsp+220h+var_200]
0x180016b66  call    ??$emplace@AEBVAnyRuntimeApp@appids@@AEAUAppInfo@AppInventory@AppLimits@wpc@@@?$_Tree@V?$_Tmap_traits@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@std@@@std@@@std@@_N@1@AEBVAnyRuntimeApp@appids@@AEAUAppInfo@AppInventory@AppLimits@wpc@@@Z; std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::emplace<appids::AnyRuntimeApp const &,wpc::AppLimits::AppInventory::AppInfo &>(appids::AnyRuntimeApp const &,wpc::AppLimits::AppInventory::AppInfo &)
0x180016b6b  lea     r9, [rsp+220h+var_200]
0x180016b70  mov     r8, r14
0x180016b73  lea     rdx, [rsp+220h+var_1E0]
0x180016b78  mov     rcx, [rsp+220h+var_1E8]
0x180016b7d  call    ??$emplace@AEBVSid@@AEAV?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@?$_Tree@V?$_Tmap_traits@VSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@U?$less@VSid@@@3@V?$allocator@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@std@@@std@@@std@@_N@1@AEBVSid@@AEAV?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@1@@Z; std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::emplace<Sid const &,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo> &>(Sid const &,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo> &)
0x180016b82  nop
0x180016b83  lea     rcx, [rsp+220h+var_200]
0x180016b88  call    ??1?$_Tree@V?$_Tmap_traits@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::~_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>(void)
0x180016b8d  lea     rdx, [rbp+120h+var_130]; struct wpc::AppLimits::AppInventory::AppInfo *
0x180016b91  mov     rcx, r14; struct Sid *
0x180016b94  call    ?WriteAppInfoForUser@AppInventoryStorage@AppInventory@AppLimits@wpc@@SAXAEBVSid@@AEBUAppInfo@234@@Z; wpc::AppLimits::AppInventory::AppInventoryStorage::WriteAppInfoForUser(Sid const &,wpc::AppLimits::AppInventory::AppInfo const &)
0x180016b99  nop
0x180016b9a  mov     rcx, [rsp+220h+var_1F0]
0x180016b9f  test    rcx, rcx
0x180016ba2  jz      short loc_180016BB9
0x180016ba4  mov     rax, [rcx]
0x180016ba7  mov     rax, [rax+18h]
0x180016bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bb0  mov     [rsp+220h+var_1F0], 0
0x180016bb9  lea     rcx, [rbp+120h+var_158]
0x180016bbd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016bc2  nop
0x180016bc3  lea     rcx, [rbp+120h+var_130]; this
0x180016bc7  call    ??1AppInfo@AppInventory@AppLimits@wpc@@QEAA@XZ; wpc::AppLimits::AppInventory::AppInfo::~AppInfo(void)
0x180016bcc  nop
0x180016bcd  mov     rcx, r15
0x180016bd0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016bd5  mov     rcx, [rbp+120h+var_40]
0x180016bdc  xor     rcx, rsp; StackCookie
0x180016bdf  call    __security_check_cookie
0x180016be4  add     rsp, 1F8h
0x180016beb  pop     r15
0x180016bed  pop     r14
0x180016bef  pop     rdi
0x180016bf0  pop     rsi
0x180016bf1  pop     rbx
0x180016bf2  pop     rbp
0x180016bf3  retn
```
