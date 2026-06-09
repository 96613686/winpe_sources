# CBroadcastConfigManager::NotifyBroadcastConfigChangeCallback(void)

- ea: `0x1800640e0`
- end: `0x1800647c2`
- name: `?NotifyBroadcastConfigChangeCallback@CBroadcastConfigManager@@QEAAJXZ`
- size: `1762`
- prototype: `__int64 __fastcall(CBroadcastConfigManager *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800647d0`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x180003f50`
- `0x1800069f0`
- `0x180006c84`
- `0x180009898`
- `0x18000ae8c`
- `0x18000c4fc`
- `0x18000df8c`
- `0x1800334c4`
- `0x180033660`
- `0x180033978`
- `0x180038674`
- `0x180051628`
- `0x180062c88`
- `0x180063230`
- `0x180063348`
- `0x180063534`
- `0x1800635a4`
- `0x180063a54`
- `0x180063b94`
- `0x1800640e0`
- `0x18006f010`

## string_xrefs

- `0x18006474c`: `There are no pending BroadcastConfigChanges.`
- `0x1800646aa`: `CBroadcastConfigManager::NotifyBroadcastConfigChangeCallback`
- `0x180064758`: `CBroadcastConfigManager::NotifyBroadcastConfigChangeCallback`
- `0x18006469e`: `BroadcastConfigChange for SmsDevice %S`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CBroadcastConfigManager::NotifyBroadcastConfigChangeCallback(CBroadcastConfigManager *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax
  __int64 *v4; // rbx
  struct SmsRouterBroadcastConfig *v5; // rdi
  const wchar_t *v6; // r15
  const wchar_t *v7; // rsi
  __int64 v8; // rax
  __int64 v9; // r8
  _QWORD *v10; // rsi
  __int64 **v11; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 *v14; // rbx
  unsigned __int64 v15; // rsi
  size_t v16; // rsi
  struct SmsRouterBroadcastConfig *v17; // rdi
  void *v18; // rax
  const struct SmsRouterBroadcastConfig *v19; // r12
  const struct SmsRouterBroadcastConfig *v20; // rsi
  const struct SmsRouterBroadcastConfig *k; // r15
  _QWORD **v22; // rcx
  __int64 *v23; // r13
  const wchar_t *v24; // rsi
  __int64 v25; // rax
  __int64 **v26; // rcx
  __int64 *m; // rax
  __int64 *n; // rcx
  _QWORD *v29; // rdi
  char *v30; // rsi
  char **v31; // rbx
  __int64 *v32; // rbx
  const wchar_t *v33; // rsi
  const wchar_t *v34; // rdi
  const wchar_t *v35; // r9
  _QWORD *v36; // rax
  __int64 **v37; // rcx
  __int64 *ii; // rax
  __int64 *jj; // rcx
  void *v41[2]; // [rsp+20h] [rbp-E0h] BYREF
  void *v42[3]; // [rsp+30h] [rbp-D0h] BYREF
  struct SmsRouterBroadcastConfig *v43; // [rsp+48h] [rbp-B8h]
  struct SmsRouterBroadcastConfig **v44; // [rsp+50h] [rbp-B0h]
  void **v45; // [rsp+58h] [rbp-A8h]
  char *v46; // [rsp+60h] [rbp-A0h]
  struct SmsRouterBroadcastConfig **v47; // [rsp+68h] [rbp-98h]
  char *v48[4]; // [rsp+70h] [rbp-90h] BYREF
  struct SmsRouterBroadcastConfig *v49[2]; // [rsp+90h] [rbp-70h] BYREF
  char *v50; // [rsp+A0h] [rbp-60h]
  char *v51[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v52[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v53; // [rsp+E0h] [rbp-20h]
  char v54[16]; // [rsp+F0h] [rbp-10h] BYREF
  char v55[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v56[32]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD *v57; // [rsp+130h] [rbp+30h] BYREF
  _QWORD *v58; // [rsp+140h] [rbp+40h] BYREF

  v41[1] = 0;
  v2 = operator new(0x48u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  v41[0] = v2;
  SmsRouterBroadcastConfig::SmsRouterBroadcastConfig((SmsRouterBroadcastConfig *)v56);
  v42[1] = 0;
  v3 = operator new(0x80u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  v42[0] = v3;
  v45 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v46 = (char *)this + 40;
  (**((void (__fastcall ***)(char *))this + 5))((char *)this + 40);
  if ( !*((_DWORD *)this + 2) || !*((_DWORD *)this + 8) && !*((_QWORD *)this + 14) )
  {
    LogSmsRouterInfo(
      "CBroadcastConfigManager::NotifyBroadcastConfigChangeCallback",
      0xA9u,
      "There are no pending BroadcastConfigChanges.");
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 5) + 8LL))((char *)this + 40);
    goto LABEL_106;
  }
  v4 = (__int64 *)**((_QWORD **)this + 11);
  while ( !*((_BYTE *)v4 + 25) )
  {
    std::wstring::wstring((__int64)v48, (__int64)(v4 + 4));
    v5 = (struct SmsRouterBroadcastConfig *)v4[8];
    v49[0] = v5;
    if ( v5 )
    {
      (*(void (__fastcall **)(struct SmsRouterBroadcastConfig *))(*(_QWORD *)v5 + 8LL))(v5);
      v5 = v49[0];
    }
    if ( *((_DWORD *)this + 8) )
      goto LABEL_18;
    v6 = (const wchar_t *)*((_QWORD *)this + 13);
    v7 = (const wchar_t *)*((_QWORD *)v6 + 1);
    HIDWORD(v43) = 0;
    if ( !*((_BYTE *)v7 + 25) )
    {
      do
      {
        if ( (unsigned __int8)std::operator<<unsigned short>(v7 + 16, (const wchar_t *)v48) )
        {
          v7 = (const wchar_t *)*((_QWORD *)v7 + 2);
        }
        else
        {
          v6 = v7;
          v7 = *(const wchar_t **)v7;
        }
      }
      while ( !*((_BYTE *)v7 + 25) );
      v5 = v49[0];
    }
    if ( !*((_BYTE *)v6 + 25) )
    {
      if ( !(unsigned __int8)std::operator<<unsigned short>((const wchar_t *)v48, v6 + 16)
        && v6 != *((const wchar_t **)this + 13) )
      {
LABEL_18:
        v8 = std::map<std::wstring,SmsRouterBroadcastConfig>::operator[]((__int64 *)v42, (const wchar_t *)v48);
        std::wstring::operator=(v8, v48, v9);
        v10 = (_QWORD *)std::map<std::wstring,ATL::CComPtr<IBroadcastConfigChangeObserver>>::operator[](
                          (__int64 *)v41,
                          (const wchar_t *)v48);
        v5 = v49[0];
        if ( (struct SmsRouterBroadcastConfig *)*v10 == v49[0] )
          goto LABEL_25;
        if ( v49[0] )
          (*(void (__fastcall **)(struct SmsRouterBroadcastConfig *))(*(_QWORD *)v49[0] + 8LL))(v49[0]);
        if ( *v10 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
        *v10 = v5;
      }
      v5 = v49[0];
    }
LABEL_25:
    if ( v5 )
      (*(void (__fastcall **)(struct SmsRouterBroadcastConfig *))(*(_QWORD *)v5 + 16LL))(v5);
    std::wstring::~wstring(v48);
    v11 = (__int64 **)v4[2];
    if ( *((_BYTE *)v11 + 25) )
    {
      for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v4 = i;
      v4 = i;
    }
    else
    {
      v4 = (__int64 *)v4[2];
      for ( j = *v11; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v4 = j;
    }
  }
  v14 = (__int64 *)**((_QWORD **)this + 15);
LABEL_37:
  if ( !*((_BYTE *)v14 + 25) )
  {
    std::wstring::wstring((__int64)v48, (__int64)(v14 + 4));
    *(_OWORD *)v49 = 0;
    v50 = 0;
    v15 = (v14[9] - v14[8]) >> 6;
    if ( v15 )
    {
      if ( v15 > 0x3FFFFFFFFFFFFFFLL )
        std::vector<ATL::CComPtr<ISmsDevice>>::_Xlength();
      v16 = v15 << 6;
      if ( v16 )
      {
        if ( v16 < 0x1000 )
        {
          v17 = (struct SmsRouterBroadcastConfig *)operator new(v16);
        }
        else
        {
          if ( v16 + 39 < v16 )
            __scrt_throw_std_bad_array_new_length();
          v18 = operator new(v16 + 39);
          if ( !v18 )
            __fastfail(5u);
          v17 = (struct SmsRouterBroadcastConfig *)(((unsigned __int64)v18 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *((_QWORD *)v17 - 1) = v18;
        }
      }
      else
      {
        v17 = 0;
      }
      v49[0] = v17;
      v49[1] = v17;
      v50 = (char *)v17 + v16;
      v47 = v49;
      v19 = (const struct SmsRouterBroadcastConfig *)v14[9];
      v20 = (const struct SmsRouterBroadcastConfig *)v14[8];
      v42[2] = v17;
      v43 = v17;
      v44 = v49;
      while ( v20 != v19 )
      {
        SmsRouterBroadcastConfig::SmsRouterBroadcastConfig(v17, v20);
        v17 = (struct SmsRouterBroadcastConfig *)((char *)v17 + 64);
        v43 = v17;
        v20 = (const struct SmsRouterBroadcastConfig *)((char *)v20 + 64);
      }
      v49[1] = v17;
    }
    else
    {
      v17 = v49[1];
    }
    for ( k = v49[0]; ; k = (const struct SmsRouterBroadcastConfig *)((char *)k + 64) )
    {
      if ( k == v17 )
      {
        std::vector<SmsRouterBroadcastConfig>::_Tidy((__int64)v49);
        std::wstring::~wstring(v48);
        v26 = (__int64 **)v14[2];
        if ( *((_BYTE *)v26 + 25) )
        {
          for ( m = (__int64 *)v14[1]; !*((_BYTE *)m + 25) && v14 == (__int64 *)m[2]; m = (__int64 *)m[1] )
            v14 = m;
          v14 = m;
        }
        else
        {
          v14 = (__int64 *)v14[2];
          for ( n = *v26; !*((_BYTE *)n + 25); n = (__int64 *)*n )
            v14 = n;
        }
        goto LABEL_37;
      }
      SmsRouterBroadcastConfig::SmsRouterBroadcastConfig((SmsRouterBroadcastConfig *)v51, k);
      if ( !v51[2] )
        break;
      if ( *((_DWORD *)this + 8) )
        goto LABEL_64;
      v23 = (__int64 *)*((_QWORD *)this + 13);
      v24 = (const wchar_t *)v23[1];
      HIDWORD(v43) = 0;
      while ( !*((_BYTE *)v24 + 25) )
      {
        if ( (unsigned __int8)std::operator<<unsigned short>(v24 + 16, (const wchar_t *)v51) )
        {
          v24 = (const wchar_t *)*((_QWORD *)v24 + 2);
        }
        else
        {
          v23 = (__int64 *)v24;
          v24 = *(const wchar_t **)v24;
        }
      }
      if ( !*((_BYTE *)v23 + 25)
        && !(unsigned __int8)std::operator<<unsigned short>((const wchar_t *)v51, (const wchar_t *)v23 + 16)
        && v23 != *((__int64 **)this + 13) )
      {
LABEL_64:
        v25 = std::map<std::wstring,SmsRouterBroadcastConfig>::operator[]((__int64 *)v42, (const wchar_t *)v51);
        std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<unsigned long>>>>(
          v25 + 32,
          *(_QWORD *)v52[0],
          v52[0]);
        v22 = (_QWORD **)(std::map<std::wstring,SmsRouterBroadcastConfig>::operator[](
                            (__int64 *)v42,
                            (const wchar_t *)v51)
                        + 48);
        goto LABEL_65;
      }
LABEL_66:
      SmsRouterBroadcastConfig::~SmsRouterBroadcastConfig((SmsRouterBroadcastConfig *)v51);
    }
    std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<unsigned long>>>>(
      &v57,
      *(_QWORD *)v52[0],
      v52[0]);
    v22 = &v58;
LABEL_65:
    std::_Tree<std::_Tset_traits<enum SMS_BROADCAST_TYPES,std::less<enum SMS_BROADCAST_TYPES>,std::allocator<enum SMS_BROADCAST_TYPES>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<enum SMS_BROADCAST_TYPES>>>>(
      v22,
      *v53,
      v53);
    goto LABEL_66;
  }
  *((_DWORD *)this + 8) = 0;
  v29 = (_QWORD *)*((_QWORD *)this + 13);
  v30 = (char *)v29[1];
  while ( !v30[25] )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,int>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,int>,void *>>>(
      (char *)this + 104,
      (char *)this + 104,
      *((_QWORD *)v30 + 2));
    v31 = (char **)v30;
    v30 = *(char **)v30;
    std::wstring::~wstring(v31 + 4);
    operator delete(v31);
  }
  v29[1] = v29;
  *v29 = v29;
  v29[2] = v29;
  *((_QWORD *)this + 14) = 0;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v46 + 8LL))(v46);
  v32 = *(__int64 **)v42[0];
  while ( !*((_BYTE *)v32 + 25) )
  {
    std::wstring::wstring((__int64)v51, (__int64)(v32 + 4));
    SmsRouterBroadcastConfig::SmsRouterBroadcastConfig(
      (SmsRouterBroadcastConfig *)v52,
      (const struct SmsRouterBroadcastConfig *)(v32 + 8));
    v33 = (const wchar_t *)v41[0];
    v34 = (const wchar_t *)*((_QWORD *)v41[0] + 1);
    while ( !*((_BYTE *)v34 + 25) )
    {
      if ( (unsigned __int8)std::operator<<unsigned short>(v34 + 16, (const wchar_t *)v51) )
      {
        v34 = (const wchar_t *)*((_QWORD *)v34 + 2);
      }
      else
      {
        v33 = v34;
        v34 = *(const wchar_t **)v34;
      }
    }
    if ( !*((_BYTE *)v33 + 25)
      && !(unsigned __int8)std::operator<<unsigned short>((const wchar_t *)v51, v33 + 16)
      && v33 != v41[0]
      && *(_QWORD *)std::map<std::wstring,ATL::CComPtr<IBroadcastConfigChangeObserver>>::operator[](
                      (__int64 *)v41,
                      (const wchar_t *)v51) )
    {
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<unsigned long>>>>(
        v54,
        *v57,
        v57);
      std::_Tree<std::_Tset_traits<enum SMS_BROADCAST_TYPES,std::less<enum SMS_BROADCAST_TYPES>,std::allocator<enum SMS_BROADCAST_TYPES>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<enum SMS_BROADCAST_TYPES>>>>(
        v55,
        *v58,
        v58);
      v35 = (const wchar_t *)v51;
      if ( v51[3] > (char *)7 )
        v35 = (const wchar_t *)v51[0];
      LogSmsRouterInfo(
        "CBroadcastConfigManager::NotifyBroadcastConfigChangeCallback",
        0xD1u,
        "BroadcastConfigChange for SmsDevice %S",
        v35);
      if ( *(_QWORD *)std::map<std::wstring,ATL::CComPtr<IBroadcastConfigChangeObserver>>::operator[](
                        (__int64 *)v41,
                        (const wchar_t *)v51) )
      {
        v36 = (_QWORD *)std::map<std::wstring,ATL::CComPtr<IBroadcastConfigChangeObserver>>::operator[](
                          (__int64 *)v41,
                          (const wchar_t *)v51);
        (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v36 + 24LL))(*v36, v52);
      }
    }
    SmsRouterBroadcastConfig::~SmsRouterBroadcastConfig((SmsRouterBroadcastConfig *)v52);
    std::wstring::~wstring(v51);
    v37 = (__int64 **)v32[2];
    if ( *((_BYTE *)v37 + 25) )
    {
      for ( ii = (__int64 *)v32[1]; !*((_BYTE *)ii + 25) && v32 == (__int64 *)ii[2]; ii = (__int64 *)ii[1] )
        v32 = ii;
      v32 = ii;
    }
    else
    {
      v32 = (__int64 *)v32[2];
      for ( jj = *v37; !*((_BYTE *)jj + 25); jj = (__int64 *)*jj )
        v32 = jj;
    }
  }
LABEL_106:
  std::_Tree<std::_Tmap_traits<std::wstring,SmsRouterBroadcastConfig,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,SmsRouterBroadcastConfig>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,SmsRouterBroadcastConfig,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,SmsRouterBroadcastConfig>>,0>>(v42);
  SmsRouterBroadcastConfig::~SmsRouterBroadcastConfig((SmsRouterBroadcastConfig *)v56);
  std::_Tree<std::_Tmap_traits<std::wstring,ATL::CComPtr<IBroadcastConfigChangeObserver>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CComPtr<IBroadcastConfigChangeObserver>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ATL::CComPtr<IBroadcastConfigChangeObserver>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ATL::CComPtr<IBroadcastConfigChangeObserver>>>,0>>(v41);
  return 0;
}

```

## disassembly

```asm
0x1800640e0  push    rbp
0x1800640e2  push    rbx
0x1800640e3  push    rsi
0x1800640e4  push    rdi
0x1800640e5  push    r12
0x1800640e7  push    r13
0x1800640e9  push    r14
0x1800640eb  push    r15
0x1800640ed  lea     rbp, [rsp-68h]
0x1800640f2  sub     rsp, 168h
0x1800640f9  mov     rax, cs:__security_cookie
0x180064100  xor     rax, rsp
0x180064103  mov     [rbp+0A0h+var_50], rax
0x180064107  mov     r14, rcx
0x18006410a  xor     r12d, r12d
0x18006410d  mov     [rsp+1A0h+var_180], r12
0x180064112  mov     [rsp+1A0h+var_178], r12
0x180064117  lea     ecx, [r12+48h]; Size
0x18006411c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064121  mov     [rax], rax
0x180064124  mov     [rax+8], rax
0x180064128  mov     [rax+10h], rax
0x18006412c  mov     word ptr [rax+18h], 101h
0x180064132  mov     [rsp+1A0h+var_180], rax
0x180064137  lea     rcx, [rbp+0A0h+var_90]; this
0x18006413b  call    ??0SmsRouterBroadcastConfig@@QEAA@XZ; SmsRouterBroadcastConfig::SmsRouterBroadcastConfig(void)
0x180064140  nop
0x180064141  mov     [rsp+1A0h+var_170], r12
0x180064146  mov     [rsp+1A0h+var_168], r12
0x18006414b  mov     ecx, 80h; Size
0x180064150  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064155  mov     [rax], rax
0x180064158  mov     [rax+8], rax
0x18006415c  mov     [rax+10h], rax
0x180064160  mov     word ptr [rax+18h], 101h
0x180064166  mov     [rsp+1A0h+var_170], rax
0x18006416b  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180064172  mov     [rsp+1A0h+var_148], rax
0x180064177  lea     r15, [r14+28h]
0x18006417b  mov     [rsp+1A0h+var_140], r15
0x180064180  mov     rax, [r15]
0x180064183  mov     rcx, r15
0x180064186  mov     rax, [rax]
0x180064189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006418e  nop
0x18006418f  cmp     [r14+8], r12d
0x180064193  jz      loc_18006474C
0x180064199  cmp     [r14+20h], r12d
0x18006419d  jnz     short loc_1800641A9
0x18006419f  cmp     [r14+70h], r12
0x1800641a3  jz      loc_18006474C
0x1800641a9  mov     rbx, [r14+58h]
0x1800641ad  mov     rbx, [rbx]
0x1800641b0  cmp     [rbx+19h], r12b
0x1800641b4  jnz     loc_18006431C
0x1800641ba  lea     rdx, [rbx+20h]
0x1800641be  lea     rcx, [rsp+1A0h+var_130]
0x1800641c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800641c8  mov     rdi, [rbx+40h]
0x1800641cc  mov     [rbp+0A0h+var_110], rdi
0x1800641d0  test    rdi, rdi
0x1800641d3  jz      short loc_1800641E8
0x1800641d5  mov     rax, [rdi]
0x1800641d8  mov     rcx, rdi
0x1800641db  mov     rax, [rax+8]
0x1800641df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800641e4  mov     rdi, [rbp+0A0h+var_110]
0x1800641e8  cmp     [r14+20h], r12d
0x1800641ec  jnz     short loc_180064248
0x1800641ee  mov     r15, [r14+68h]
0x1800641f2  mov     rsi, [r15+8]
0x1800641f6  xor     eax, eax
0x1800641f8  mov     [rsp+1A0h+var_154], eax
0x1800641fc  cmp     [rsi+19h], r12b
0x180064200  jnz     short loc_18006422A
0x180064202  lea     rcx, [rsi+20h]
0x180064206  lea     rdx, [rsp+1A0h+var_130]
0x18006420b  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180064210  test    al, al
0x180064212  jz      short loc_18006421A
0x180064214  mov     rsi, [rsi+10h]
0x180064218  jmp     short loc_180064220
0x18006421a  mov     r15, rsi
0x18006421d  mov     rsi, [rsi]
0x180064220  cmp     [rsi+19h], r12b
0x180064224  jz      short loc_180064202
0x180064226  mov     rdi, [rbp+0A0h+var_110]
0x18006422a  cmp     [r15+19h], r12b
0x18006422e  jnz     short loc_1800642AE
0x180064230  lea     rdx, [r15+20h]
0x180064234  lea     rcx, [rsp+1A0h+var_130]
0x180064239  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18006423e  test    al, al
0x180064240  jnz     short loc_1800642AA
0x180064242  cmp     r15, [r14+68h]
0x180064246  jz      short loc_1800642AA
0x180064248  lea     rdx, [rsp+1A0h+var_130]
0x18006424d  lea     rcx, [rsp+1A0h+var_170]
0x180064252  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USmsRouterBroadcastConfig@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USmsRouterBroadcastConfig@@@std@@@2@@std@@QEAAAEAUSmsRouterBroadcastConfig@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,SmsRouterBroadcastConfig>::operator[](std::wstring const &)
0x180064257  mov     rcx, rax
0x18006425a  lea     rdx, [rsp+1A0h+var_130]
0x18006425f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180064264  lea     rdx, [rsp+1A0h+var_130]
0x180064269  lea     rcx, [rsp+1A0h+var_180]
0x18006426e  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CComPtr@VIBroadcastConfigChangeObserver@@@ATL@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$CComPtr@VIBroadcastConfigChangeObserver@@@ATL@@@std@@@2@@std@@QEAAAEAV?$CComPtr@VIBroadcastConfigChangeObserver@@@ATL@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ATL::CComPtr<IBroadcastConfigChangeObserver>>::operator[](std::wstring const &)
0x180064273  mov     rsi, rax
0x180064276  mov     rdi, [rbp+0A0h+var_110]
0x18006427a  cmp     [rax], rdi
0x18006427d  jz      short loc_1800642AE
0x18006427f  test    rdi, rdi
0x180064282  jz      short loc_180064293
0x180064284  mov     rcx, [rdi]
0x180064287  mov     rax, [rcx+8]
0x18006428b  mov     rcx, rdi
0x18006428e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064293  mov     rcx, [rsi]
0x180064296  test    rcx, rcx
0x180064299  jz      short loc_1800642A7
0x18006429b  mov     rax, [rcx]
0x18006429e  mov     rax, [rax+10h]
0x1800642a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642a7  mov     [rsi], rdi
0x1800642aa  mov     rdi, [rbp+0A0h+var_110]
0x1800642ae  test    rdi, rdi
0x1800642b1  jz      short loc_1800642C3
0x1800642b3  mov     rax, [rdi]
0x1800642b6  mov     rcx, rdi
0x1800642b9  mov     rax, [rax+10h]
0x1800642bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642c2  nop
0x1800642c3  lea     rcx, [rsp+1A0h+var_130]; void *
0x1800642c8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800642cd  mov     rcx, [rbx+10h]
0x1800642d1  cmp     [rcx+19h], r12b
0x1800642d5  jz      short loc_1800642F8
0x1800642d7  mov     rax, [rbx+8]
0x1800642db  jmp     short loc_1800642EA
0x1800642dd  cmp     rbx, [rax+10h]
0x1800642e1  jnz     short loc_1800642F0
0x1800642e3  mov     rbx, rax
0x1800642e6  mov     rax, [rax+8]
0x1800642ea  cmp     [rax+19h], r12b
0x1800642ee  jz      short loc_1800642DD
0x1800642f0  mov     rbx, rax
0x1800642f3  jmp     loc_1800641B0
0x1800642f8  mov     rbx, rcx
0x1800642fb  mov     rcx, [rcx]
0x1800642fe  cmp     [rcx+19h], r12b
0x180064302  jnz     loc_1800641B0
0x180064308  mov     rbx, rcx
0x18006430b  mov     rax, [rcx]
0x18006430e  mov     rcx, rax
0x180064311  cmp     [rax+19h], r12b
0x180064315  jz      short loc_180064308
0x180064317  jmp     loc_1800641B0
0x18006431c  mov     rbx, [r14+78h]
0x180064320  mov     rbx, [rbx]
0x180064323  cmp     [rbx+19h], r12b
0x180064327  jnz     loc_18006456B
0x18006432d  lea     rdx, [rbx+20h]
0x180064331  lea     rcx, [rsp+1A0h+var_130]
0x180064336  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006433b  nop
0x18006433c  xorps   xmm0, xmm0
0x18006433f  movdqu  xmmword ptr [rbp+0A0h+var_110], xmm0
0x180064344  mov     [rbp+0A0h+var_100], r12
0x180064348  mov     rsi, [rbx+48h]
0x18006434c  sub     rsi, [rbx+40h]
0x180064350  sar     rsi, 6
0x180064354  test    rsi, rsi
0x180064357  jz      loc_180064417
0x18006435d  mov     rax, 3FFFFFFFFFFFFFFh
0x180064367  cmp     rsi, rax
0x18006436a  ja      loc_1800647B6
0x180064370  shl     rsi, 6
0x180064374  test    rsi, rsi
0x180064377  jnz     short loc_18006437E
0x180064379  mov     rdi, r12
0x18006437c  jmp     short loc_1800643BB
0x18006437e  cmp     rsi, 1000h
0x180064385  jb      short loc_1800643B0
0x180064387  lea     rcx, [rsi+27h]; Size
0x18006438b  cmp     rcx, rsi
0x18006438e  jbe     loc_1800647BC
0x180064394  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064399  test    rax, rax
0x18006439c  jz      loc_180064564
0x1800643a2  lea     rdi, [rax+27h]
0x1800643a6  and     rdi, 0FFFFFFFFFFFFFFE0h
0x1800643aa  mov     [rdi-8], rax
0x1800643ae  jmp     short loc_1800643BB
0x1800643b0  mov     rcx, rsi; Size
0x1800643b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800643b8  mov     rdi, rax
0x1800643bb  mov     [rbp+0A0h+var_110], rdi
0x1800643bf  mov     [rbp+0A0h+var_110+8], rdi
0x1800643c3  lea     rcx, [rdi+rsi]
0x1800643c7  mov     [rbp+0A0h+var_100], rcx
0x1800643cb  lea     rax, [rbp+0A0h+var_110]
0x1800643cf  mov     [rsp+1A0h+var_138], rax
0x1800643d4  mov     r12, [rbx+48h]
0x1800643d8  mov     rsi, [rbx+40h]
0x1800643dc  mov     [rsp+1A0h+var_160], rdi
0x1800643e1  mov     [rsp+48h], rdi
0x1800643e6  lea     rax, [rbp+0A0h+var_110]
0x1800643ea  mov     [rsp+1A0h+var_150], rax
0x1800643ef  jmp     short loc_180064409
0x1800643f1  mov     rdx, rsi; struct SmsRouterBroadcastConfig *
0x1800643f4  mov     rcx, rdi; this
0x1800643f7  call    ??0SmsRouterBroadcastConfig@@QEAA@AEBU0@@Z; SmsRouterBroadcastConfig::SmsRouterBroadcastConfig(SmsRouterBroadcastConfig const &)
0x1800643fc  add     rdi, 40h ; '@'
0x180064400  mov     [rsp+48h], rdi
0x180064405  add     rsi, 40h ; '@'
0x180064409  cmp     rsi, r12
0x18006440c  jnz     short loc_1800643F1
0x18006440e  mov     [rbp+0A0h+var_110+8], rdi
0x180064412  xor     r12d, r12d
0x180064415  jmp     short loc_18006441B
0x180064417  mov     rdi, [rbp+0A0h+var_110+8]
0x18006441b  mov     r15, [rbp+0A0h+var_110]
0x18006441f  jmp     loc_1800644F9
0x180064424  mov     rdx, r15; struct SmsRouterBroadcastConfig *
0x180064427  lea     rcx, [rbp+0A0h+var_F0]; this
0x18006442b  call    ??0SmsRouterBroadcastConfig@@QEAA@AEBU0@@Z; SmsRouterBroadcastConfig::SmsRouterBroadcastConfig(SmsRouterBroadcastConfig const &)
0x180064430  nop
0x180064431  cmp     [rbp+0A0h+var_E0], r12
0x180064435  jnz     short loc_180064453
0x180064437  mov     rdx, [rbp+0A0h+var_D0]
0x18006443b  mov     r8, rdx
0x18006443e  mov     rdx, [rdx]
0x180064441  lea     rcx, [rbp+0A0h+var_70]
0x180064445  call    ??$insert@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAAXV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@1@0@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ulong>>>>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ulong>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ulong>>>)
0x18006444a  lea     rcx, [rbp+0A0h+var_60]
0x18006444e  jmp     loc_1800644DC
0x180064453  cmp     [r14+20h], r12d
0x180064457  jnz     short loc_1800644A9
0x180064459  mov     r13, [r14+68h]
0x18006445d  mov     rsi, [r13+8]
0x180064461  xor     eax, eax
0x180064463  mov     [rsp+1A0h+var_154], eax
0x180064467  jmp     short loc_180064486
0x180064469  lea     rcx, [rsi+20h]
0x18006446d  lea     rdx, [rbp+0A0h+var_F0]
0x180064471  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180064476  test    al, al
0x180064478  jz      short loc_180064480
0x18006447a  mov     rsi, [rsi+10h]
0x18006447e  jmp     short loc_180064486
0x180064480  mov     r13, rsi
0x180064483  mov     rsi, [rsi]
0x180064486  cmp     [rsi+19h], r12b
0x18006448a  jz      short loc_180064469
0x18006448c  cmp     [r13+19h], r12b
0x180064490  jnz     short loc_1800644EC
0x180064492  lea     rdx, [r13+20h]
0x180064496  lea     rcx, [rbp+0A0h+var_F0]
0x18006449a  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18006449f  test    al, al
0x1800644a1  jnz     short loc_1800644EC
0x1800644a3  cmp     r13, [r14+68h]
0x1800644a7  jz      short loc_1800644EC
0x1800644a9  lea     rdx, [rbp+0A0h+var_F0]
0x1800644ad  lea     rcx, [rsp+1A0h+var_170]
0x1800644b2  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USmsRouterBroadcastConfig@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USmsRouterBroadcastConfig@@@std@@@2@@std@@QEAAAEAUSmsRouterBroadcastConfig@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,SmsRouterBroadcastConfig>::operator[](std::wstring const &)
0x1800644b7  lea     rcx, [rax+20h]
0x1800644bb  mov     rdx, [rbp+0A0h+var_D0]
0x1800644bf  mov     r8, rdx
0x1800644c2  mov     rdx, [rdx]
0x1800644c5  call    ??$insert@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAAXV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@1@0@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ulong>>>>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ulong>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ulong>>>)
0x1800644ca  lea     rdx, [rbp+0A0h+var_F0]
0x1800644ce  lea     rcx, [rsp+1A0h+var_170]
0x1800644d3  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USmsRouterBroadcastConfig@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USmsRouterBroadcastConfig@@@std@@@2@@std@@QEAAAEAUSmsRouterBroadcastConfig@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,SmsRouterBroadcastConfig>::operator[](std::wstring const &)
0x1800644d8  lea     rcx, [rax+30h]
0x1800644dc  mov     rdx, [rbp+0A0h+var_C0]
0x1800644e0  mov     r8, rdx
0x1800644e3  mov     rdx, [rdx]
0x1800644e6  call    ??$insert@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@W4SMS_BROADCAST_TYPES@@@std@@@std@@@std@@@?$_Tree@V?$_Tset_traits@W4SMS_BROADCAST_TYPES@@U?$less@W4SMS_BROADCAST_TYPES@@@std@@V?$allocator@W4SMS_BROADCAST_TYPES@@@3@$0A@@std@@@std@@QEAAXV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@W4SMS_BROADCAST_TYPES@@@std@@@std@@@1@0@Z; std::_Tree<std::_Tset_traits<SMS_BROADCAST_TYPES,std::less<SMS_BROADCAST_TYPES>,std::allocator<SMS_BROADCAST_TYPES>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<SMS_BROADCAST_TYPES>>>>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<SMS_BROADCAST_TYPES>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<SMS_BROADCAST_TYPES>>>)
0x1800644eb  nop
0x1800644ec  lea     rcx, [rbp+0A0h+var_F0]; this
0x1800644f0  call    ??1SmsRouterBroadcastConfig@@QEAA@XZ; SmsRouterBroadcastConfig::~SmsRouterBroadcastConfig(void)
0x1800644f5  add     r15, 40h ; '@'
0x1800644f9  cmp     r15, rdi
0x1800644fc  jnz     loc_180064424
0x180064502  lea     rcx, [rbp+0A0h+var_110]
0x180064506  call    ?_Tidy@?$vector@USmsRouterBroadcastConfig@@V?$allocator@USmsRouterBroadcastConfig@@@std@@@std@@AEAAXXZ; std::vector<SmsRouterBroadcastConfig>::_Tidy(void)
0x18006450b  lea     rcx, [rsp+1A0h+var_130]; void *
0x180064510  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180064515  mov     rcx, [rbx+10h]
0x180064519  cmp     [rcx+19h], r12b
0x18006451d  jz      short loc_180064540
0x18006451f  mov     rax, [rbx+8]
0x180064523  jmp     short loc_180064532
0x180064525  cmp     rbx, [rax+10h]
0x180064529  jnz     short loc_180064538
0x18006452b  mov     rbx, rax
0x18006452e  mov     rax, [rax+8]
0x180064532  cmp     [rax+19h], r12b
0x180064536  jz      short loc_180064525
0x180064538  mov     rbx, rax
0x18006453b  jmp     loc_180064323
  ... truncated ...
```
