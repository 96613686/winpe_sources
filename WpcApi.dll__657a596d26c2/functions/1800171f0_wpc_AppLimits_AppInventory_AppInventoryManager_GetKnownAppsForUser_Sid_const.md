# wpc::AppLimits::AppInventory::AppInventoryManager::GetKnownAppsForUser(Sid const &)

- ea: `0x1800171f0`
- end: `0x1800174ad`
- name: `?GetKnownAppsForUser@AppInventoryManager@AppInventory@AppLimits@wpc@@QEAA?AV?$vector@UAppInfo@AppInventory@AppLimits@wpc@@V?$allocator@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@std@@AEBVSid@@@Z`
- size: `701`
- prototype: `__int64 __fastcall(wpc::AppLimits::AppInventory::AppInventoryManager::impl **, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x18000f638`

## callees

- `0x1800032a0`
- `0x180003d14`
- `0x180005950`
- `0x180005f9c`
- `0x18000dc7c`
- `0x18000f100`
- `0x180014f2c`
- `0x1800154dc`
- `0x180015a54`
- `0x180015ca4`
- `0x180017178`
- `0x1800171f0`
- `0x180017ee0`
- `0x1800236e0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800173ca`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800173ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wpc::AppLimits::AppInventory::AppInventoryManager::GetKnownAppsForUser(
        wpc::AppLimits::AppInventory::AppInventoryManager::impl **a1,
        __int64 a2,
        __int64 a3)
{
  const wchar_t **v6; // rbx
  const wchar_t *v7; // rax
  __int64 *v8; // rbx
  __int64 **v9; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  Private::Format *v12; // rbx
  unsigned __int64 v13; // r8
  const unsigned __int16 *v14; // rdx
  __int64 v16; // [rsp+28h] [rbp-D8h] BYREF
  const wchar_t **v17; // [rsp+30h] [rbp-D0h]
  __int64 v18; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v19[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v21; // [rsp+60h] [rbp-A0h]
  char *v22[5]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v23[4]; // [rsp+90h] [rbp-70h] BYREF
  char *v24; // [rsp+98h] [rbp-68h] BYREF
  char v25; // [rsp+B8h] [rbp-48h]
  char *v26; // [rsp+C0h] [rbp-40h] BYREF
  char *v27[30]; // [rsp+E0h] [rbp-20h] BYREF

  v18 = a2;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  wpc::AppLimits::AppInventory::AppInventoryManager::impl::RefreshAppInventoryLocalCache(*a1);
  (*(void (__fastcall **)(wpc::AppLimits::AppInventory::AppInventoryManager::impl *, __int64 *))(*(_QWORD *)*a1 + 40LL))(
    *a1,
    &v16);
  v6 = v17;
  v7 = std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::_Find<Sid>(
         v17,
         a3);
  if ( v7 != *v6 && v7 != (const wchar_t *)-136LL )
  {
    v8 = (__int64 *)**((_QWORD **)v7 + 17);
    while ( !*((_BYTE *)v8 + 25) )
    {
      appids::AnyRuntimeApp::AnyRuntimeApp((appids::AnyRuntimeApp *)v23, (const struct appids::AnyRuntimeApp *)(v8 + 4));
      wpc::AppLimits::AppInventory::AppInfo::AppInfo(
        (wpc::AppLimits::AppInventory::AppInfo *)v27,
        (const struct wpc::AppLimits::AppInventory::AppInfo *)(v8 + 14));
      if ( *(_QWORD *)(a2 + 8) == *(_QWORD *)(a2 + 16) )
      {
        std::vector<wpc::AppLimits::AppInventory::AppInfo>::_Emplace_reallocate<wpc::AppLimits::AppInventory::AppInfo const &>(
          a2,
          *(_QWORD *)(a2 + 8),
          v27);
      }
      else
      {
        wpc::AppLimits::AppInventory::AppInfo::AppInfo(
          *(wpc::AppLimits::AppInventory::AppInfo **)(a2 + 8),
          (const struct wpc::AppLimits::AppInventory::AppInfo *)v27);
        *(_QWORD *)(a2 + 8) += 232LL;
      }
      wpc::AppLimits::AppInventory::AppInfo::~AppInfo(v27);
      std::wstring::~wstring(&v26);
      if ( v25 != -1 )
        std::wstring::~wstring(&v24);
      v9 = (__int64 **)v8[2];
      if ( *((_BYTE *)v9 + 25) )
      {
        for ( i = (__int64 *)v8[1]; !*((_BYTE *)i + 25) && v8 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v8 = i;
        v8 = i;
      }
      else
      {
        v8 = (__int64 *)v8[2];
        for ( j = *v9; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v8 = j;
      }
    }
  }
  *(_OWORD *)v19 = 0;
  v20 = 0;
  v21 = 0;
  std::wstring::_Construct<1,unsigned short const *>(v19, L"GetKnownApps returned #apps = {0}", 0x21u);
  v12 = (Private::Format *)StringAlgo::FormatString(v22, v19);
  memset_0(v23, 0, 0x82u);
  _o__ui64tow_s(0x34F72C234F72C235LL * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 3), v23, 65);
  *(_OWORD *)v19 = 0;
  v20 = 0;
  v21 = 0;
  v13 = -1;
  do
    ++v13;
  while ( v23[v13] );
  std::wstring::_Construct<1,unsigned short const *>(v19, v23, v13);
  v14 = (const unsigned __int16 *)v19;
  if ( v21 > 7 )
    v14 = v19[0];
  Private::Format::Replace(v12, v14);
  std::wstring::~wstring((char **)v19);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    if ( *((_QWORD *)v12 + 3) > 7u )
      v12 = *(Private::Format **)v12;
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_e79369f3d8d632091aecb665c0941012_Traceguids, v12);
  }
  std::wstring::~wstring(v22);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
  return a2;
}

```

## disassembly

```asm
0x1800171f0  push    rbp
0x1800171f2  push    rbx
0x1800171f3  push    rsi
0x1800171f4  push    rdi
0x1800171f5  push    r14
0x1800171f7  lea     rbp, [rsp-0E0h]
0x1800171ff  sub     rsp, 1E0h
0x180017206  mov     rax, cs:__security_cookie
0x18001720d  xor     rax, rsp
0x180017210  mov     [rbp+100h+var_30], rax
0x180017217  mov     rdi, r8
0x18001721a  mov     rsi, rdx
0x18001721d  mov     rbx, rcx
0x180017220  mov     [rsp+200h+var_1C8], rdx
0x180017225  xor     r14d, r14d
0x180017228  mov     [rsp+200h+var_1E0], r14d
0x18001722d  mov     [rdx], r14
0x180017230  mov     [rdx+8], r14
0x180017234  mov     [rdx+10h], r14
0x180017238  mov     [rsp+200h+var_1E0], 1
0x180017240  mov     rcx, [rcx]; this
0x180017243  call    ?RefreshAppInventoryLocalCache@impl@AppInventoryManager@AppInventory@AppLimits@wpc@@QEAAXXZ; wpc::AppLimits::AppInventory::AppInventoryManager::impl::RefreshAppInventoryLocalCache(void)
0x180017248  mov     rcx, [rbx]
0x18001724b  mov     rax, [rcx]
0x18001724e  lea     rdx, [rsp+200h+var_1D8]
0x180017253  mov     rax, [rax+28h]
0x180017257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001725c  nop
0x18001725d  mov     rbx, [rsp+200h+var_1D0]
0x180017262  mov     rdx, rdi
0x180017265  mov     rcx, rbx
0x180017268  call    ??$_Find@VSid@@@?$_Tree@V?$_Tmap_traits@VSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@U?$less@VSid@@@3@V?$allocator@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@3@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@1@AEBVSid@@@Z; std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::_Find<Sid>(Sid const &)
0x18001726d  cmp     rax, [rbx]
0x180017270  jz      loc_180017357
0x180017276  lea     rbx, [rax+88h]
0x18001727d  test    rbx, rbx
0x180017280  jz      loc_180017357
0x180017286  mov     rbx, [rbx]
0x180017289  mov     rbx, [rbx]
0x18001728c  cmp     [rbx+19h], r14b
0x180017290  jnz     loc_180017357
0x180017296  lea     rdx, [rbx+20h]; struct appids::AnyRuntimeApp *
0x18001729a  lea     rcx, [rbp+100h+var_170]; this
0x18001729e  call    ??0AnyRuntimeApp@appids@@QEAA@AEBV01@@Z; appids::AnyRuntimeApp::AnyRuntimeApp(appids::AnyRuntimeApp const &)
0x1800172a3  nop
0x1800172a4  lea     rdx, [rbx+70h]; struct wpc::AppLimits::AppInventory::AppInfo *
0x1800172a8  lea     rcx, [rbp+100h+var_120]; this
0x1800172ac  call    ??0AppInfo@AppInventory@AppLimits@wpc@@QEAA@AEBU0123@@Z; wpc::AppLimits::AppInventory::AppInfo::AppInfo(wpc::AppLimits::AppInventory::AppInfo const &)
0x1800172b1  nop
0x1800172b2  mov     rax, [rsi+8]
0x1800172b6  cmp     rax, [rsi+10h]
0x1800172ba  jz      short loc_1800172D2
0x1800172bc  lea     rdx, [rbp+100h+var_120]; struct wpc::AppLimits::AppInventory::AppInfo *
0x1800172c0  mov     rcx, rax; this
0x1800172c3  call    ??0AppInfo@AppInventory@AppLimits@wpc@@QEAA@AEBU0123@@Z; wpc::AppLimits::AppInventory::AppInfo::AppInfo(wpc::AppLimits::AppInventory::AppInfo const &)
0x1800172c8  add     qword ptr [rsi+8], 0E8h
0x1800172d0  jmp     short loc_1800172E2
0x1800172d2  lea     r8, [rbp+100h+var_120]
0x1800172d6  mov     rdx, rax
0x1800172d9  mov     rcx, rsi
0x1800172dc  call    ??$_Emplace_reallocate@AEBUAppInfo@AppInventory@AppLimits@wpc@@@?$vector@UAppInfo@AppInventory@AppLimits@wpc@@V?$allocator@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@std@@AEAAPEAUAppInfo@AppInventory@AppLimits@wpc@@QEAU2345@AEBU2345@@Z; std::vector<wpc::AppLimits::AppInventory::AppInfo>::_Emplace_reallocate<wpc::AppLimits::AppInventory::AppInfo const &>(wpc::AppLimits::AppInventory::AppInfo * const,wpc::AppLimits::AppInventory::AppInfo const &)
0x1800172e1  nop
0x1800172e2  lea     rcx, [rbp+100h+var_120]; this
0x1800172e6  call    ??1AppInfo@AppInventory@AppLimits@wpc@@QEAA@XZ; wpc::AppLimits::AppInventory::AppInfo::~AppInfo(void)
0x1800172eb  lea     rcx, [rbp+100h+var_140]
0x1800172ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800172f4  movsx   rax, [rbp+100h+var_148]
0x1800172f9  add     rax, 1
0x1800172fd  jz      short loc_180017308
0x1800172ff  lea     rcx, [rbp+100h+var_168]
0x180017303  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017308  mov     rcx, [rbx+10h]
0x18001730c  cmp     [rcx+19h], r14b
0x180017310  jz      short loc_180017333
0x180017312  mov     rax, [rbx+8]
0x180017316  jmp     short loc_180017325
0x180017318  cmp     rbx, [rax+10h]
0x18001731c  jnz     short loc_18001732B
0x18001731e  mov     rbx, rax
0x180017321  mov     rax, [rax+8]
0x180017325  cmp     [rax+19h], r14b
0x180017329  jz      short loc_180017318
0x18001732b  mov     rbx, rax
0x18001732e  jmp     loc_18001728C
0x180017333  mov     rbx, rcx
0x180017336  mov     rcx, [rcx]
0x180017339  cmp     [rcx+19h], r14b
0x18001733d  jnz     loc_18001728C
0x180017343  mov     rbx, rcx
0x180017346  mov     rax, [rcx]
0x180017349  mov     rcx, rax
0x18001734c  cmp     [rax+19h], r14b
0x180017350  jz      short loc_180017343
0x180017352  jmp     loc_18001728C
0x180017357  xorps   xmm0, xmm0
0x18001735a  movups  xmmword ptr [rsp+200h+var_1B8], xmm0
0x18001735f  mov     [rsp+200h+var_1A8], r14
0x180017364  mov     [rsp+200h+var_1A0], r14
0x180017369  mov     r8d, 21h ; '!'
0x18001736f  lea     rdx, aGetknownappsRe; "GetKnownApps returned #apps = {0}"
0x180017376  lea     rcx, [rsp+200h+var_1B8]
0x18001737b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017380  lea     rdx, [rsp+200h+var_1B8]
0x180017385  lea     rcx, [rsp+200h+var_198]
0x18001738a  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x18001738f  mov     rbx, rax
0x180017392  xor     edx, edx; Val
0x180017394  mov     r8d, 82h; Size
0x18001739a  lea     rcx, [rbp+100h+var_170]; void *
0x18001739e  call    memset_0
0x1800173a3  mov     rcx, [rsi+8]
0x1800173a7  sub     rcx, [rsi]
0x1800173aa  sar     rcx, 3
0x1800173ae  mov     rax, 34F72C234F72C235h
0x1800173b8  imul    rcx, rax
0x1800173bc  mov     r9d, 0Ah
0x1800173c2  lea     r8d, [r9+37h]
0x1800173c6  lea     rdx, [rbp+100h+var_170]
0x1800173ca  call    cs:__imp__o__ui64tow_s
0x1800173d0  xorps   xmm0, xmm0
0x1800173d3  movups  xmmword ptr [rsp+200h+var_1B8], xmm0
0x1800173d8  mov     [rsp+200h+var_1A8], r14
0x1800173dd  mov     [rsp+200h+var_1A0], r14
0x1800173e2  lea     rax, [rbp+100h+var_170]
0x1800173e6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800173ea  inc     r8
0x1800173ed  cmp     [rax+r8*2], r14w
0x1800173f2  jnz     short loc_1800173EA
0x1800173f4  lea     rdx, [rbp+100h+var_170]
0x1800173f8  lea     rcx, [rsp+200h+var_1B8]
0x1800173fd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017402  mov     [rsp+200h+var_1E0], 7
0x18001740a  lea     rdx, [rsp+200h+var_1B8]
0x18001740f  cmp     [rsp+200h+var_1A0], 7
0x180017415  cmova   rdx, [rsp+200h+var_1B8]; unsigned __int16 *
0x18001741b  mov     rcx, rbx; this
0x18001741e  call    ?Replace@Format@Private@@AEAAXPEBG@Z; Private::Format::Replace(ushort const *)
0x180017423  nop
0x180017424  lea     rcx, [rsp+200h+var_1B8]
0x180017429  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001742e  lea     rax, WPP_GLOBAL_Control
0x180017435  mov     rcx, cs:WPP_GLOBAL_Control
0x18001743c  cmp     rcx, rax
0x18001743f  jz      short loc_18001746A
0x180017441  test    byte ptr [rcx+1Ch], 4
0x180017445  jz      short loc_18001746A
0x180017447  cmp     qword ptr [rbx+18h], 7
0x18001744c  jbe     short loc_180017451
0x18001744e  mov     rbx, [rbx]
0x180017451  mov     edx, 0Dh
0x180017456  mov     r9, rbx
0x180017459  lea     r8, WPP_e79369f3d8d632091aecb665c0941012_Traceguids
0x180017460  mov     rcx, [rcx+10h]
0x180017464  call    WPP_SF_S
0x180017469  nop
0x18001746a  lea     rcx, [rsp+200h+var_198]
0x18001746f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017474  nop
0x180017475  mov     rcx, [rsp+200h+var_1D8]
0x18001747a  test    rcx, rcx
0x18001747d  jz      short loc_18001748C
0x18001747f  mov     rdx, [rcx]
0x180017482  mov     rax, [rdx+8]
0x180017486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001748b  nop
0x18001748c  mov     rax, rsi
0x18001748f  mov     rcx, [rbp+100h+var_30]
0x180017496  xor     rcx, rsp; StackCookie
0x180017499  call    __security_check_cookie
0x18001749e  add     rsp, 1E0h
0x1800174a5  pop     r14
0x1800174a7  pop     rdi
0x1800174a8  pop     rsi
0x1800174a9  pop     rbx
0x1800174aa  pop     rbp
0x1800174ab  retn
```
