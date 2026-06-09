# wpc::AppLimits::AppInventory::AppInventoryManager::impl::RefreshAppInventoryLocalCache(void)

- ea: `0x180017ee0`
- end: `0x18001835c`
- name: `?RefreshAppInventoryLocalCache@impl@AppInventoryManager@AppInventory@AppLimits@wpc@@QEAAXXZ`
- size: `1148`
- prototype: `void __fastcall(wpc::AppLimits::AppInventory::AppInventoryManager::impl *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800171f0`

## callees

- `0x1800032a0`
- `0x1800036e4`
- `0x180004bb0`
- `0x180005950`
- `0x180005a04`
- `0x180005f9c`
- `0x18000dc7c`
- `0x18000f100`
- `0x180014d98`
- `0x1800151a0`
- `0x1800153f8`
- `0x180015a54`
- `0x1800162f8`
- `0x180016bfc`
- `0x180017178`
- `0x180017ee0`
- `0x1800192d0`
- `0x18001bae4`
- `0x18001c724`
- `0x18001ca8c`
- `0x18002c010`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x180017fb8`
- `KERNEL32!CompareFileTime` at `0x180017fb8`

## pseudocode

```c
void __fastcall wpc::AppLimits::AppInventory::AppInventoryManager::impl::RefreshAppInventoryLocalCache(
        wpc::AppLimits::AppInventory::AppInventoryManager::impl *this)
{
  __int64 *v2; // rdi
  __int64 **v3; // r15
  __int64 *v4; // rbx
  _QWORD *v5; // rdx
  const FILETIME *v6; // rax
  __int64 **v7; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  const wchar_t *v10; // r13
  struct Sid *v11; // rcx
  char *v12; // rsi
  appids::AnyRuntimeApp *v13; // rdi
  Private::Format *v14; // rbx
  const wchar_t *v15; // r12
  Private::Format *v16; // rbx
  _QWORD *v17; // rax
  __int64 *v18; // rbx
  const wchar_t *v19; // rsi
  __int64 *v20; // r14
  __int64 *v21; // rsi
  const wchar_t *k; // rsi
  __int64 *v23; // rsi
  _BYTE *v24; // rbx
  _BYTE *v25; // r14
  void *v26; // rcx
  __int64 **v27; // rcx
  __int64 *ii; // rax
  __int64 *v29; // rdx
  __int64 **v30; // rcx
  __int64 *m; // rax
  __int64 *n; // rcx
  __int64 *jj; // rcx
  int v34; // [rsp+20h] [rbp-E0h]
  __int64 *v35; // [rsp+28h] [rbp-D8h]
  appids::AnyRuntimeApp *v36[2]; // [rsp+30h] [rbp-D0h] BYREF
  appids::AnyRuntimeApp *v37; // [rsp+40h] [rbp-C0h]
  struct Sid *v38; // [rsp+48h] [rbp-B8h]
  __int64 **v39; // [rsp+58h] [rbp-A8h]
  _QWORD v40[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v41; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h]
  __int64 v43; // [rsp+88h] [rbp-78h]
  _BYTE v44[16]; // [rsp+90h] [rbp-70h] BYREF
  FILETIME FileTime2; // [rsp+A0h] [rbp-60h] BYREF
  char v46[16]; // [rsp+B0h] [rbp-50h] BYREF
  char *v47[4]; // [rsp+C0h] [rbp-40h] BYREF
  char *v48[4]; // [rsp+E0h] [rbp-20h] BYREF
  char *v49[5]; // [rsp+100h] [rbp+0h] BYREF

  v34 = 0;
  DateTime::GetCurrent((__int64)&FileTime2);
  (*(void (__fastcall **)(wpc::AppLimits::AppInventory::AppInventoryManager::impl *, _QWORD *))(*(_QWORD *)this + 48LL))(
    this,
    v40);
  v2 = **(__int64 ***)v40[1];
  v35 = v2;
  while ( !*((_BYTE *)v2 + 25) )
  {
    v38 = (struct Sid *)(v2 + 4);
    v3 = (__int64 **)(v2 + 17);
    v39 = (__int64 **)(v2 + 17);
    *(_OWORD *)v36 = 0;
    v37 = 0;
    v4 = *(__int64 **)v2[17];
    while ( !*((_BYTE *)v4 + 25) )
    {
      if ( *((_BYTE *)v4 + 296) )
      {
        v5 = v4 + 33;
        if ( (unsigned __int64)v4[36] > 7 )
          v5 = (_QWORD *)*v5;
        DateTime::Deserialize((__int64)v44, v5);
        v6 = (const FILETIME *)DateTime::operator+(v44, v46, &qword_18004A3B0);
        if ( CompareFileTime(v6, &FileTime2) < 0 )
        {
          if ( v36[1] == v37 )
          {
            std::vector<appids::AnyRuntimeApp>::_Emplace_reallocate<appids::AnyRuntimeApp const &>(v36, v36[1], v4 + 4);
          }
          else
          {
            appids::AnyRuntimeApp::AnyRuntimeApp(v36[1], (const struct appids::AnyRuntimeApp *)(v4 + 4));
            v36[1] = (appids::AnyRuntimeApp *)((char *)v36[1] + 80);
          }
        }
      }
      v7 = (__int64 **)v4[2];
      if ( *((_BYTE *)v7 + 25) )
      {
        for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v4 = i;
        v4 = i;
      }
      else
      {
        v4 = (__int64 *)v4[2];
        for ( j = *v7; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v4 = j;
      }
    }
    v10 = (const wchar_t *)v36[0];
    if ( v36[0] != v36[1] )
    {
      v11 = v38;
      v12 = (char *)v38 + 72;
      v13 = v36[1];
      do
      {
        wpc::AppLimits::AppInventory::AppInventoryStorage::DeleteAppForUser(
          v11,
          (const struct appids::AnyRuntimeApp *)v10);
        v41 = 0;
        v42 = 0;
        v43 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v41, L"App {0} expires for user {1}", 0x1Cu);
        v14 = (Private::Format *)StringAlgo::FormatString(v49, &v41);
        v15 = v10 + 24;
        std::wstring::wstring((__int64)v48, (__int64)(v10 + 24));
        v16 = (Private::Format *)Private::Format::operator%<std::wstring>(v14);
        std::wstring::wstring((__int64)v47, (__int64)v12);
        v17 = (_QWORD *)Private::Format::operator%<std::wstring>(v16);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          if ( v17[3] > 7u )
            v17 = (_QWORD *)*v17;
          WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_e79369f3d8d632091aecb665c0941012_Traceguids, v17);
        }
        std::wstring::~wstring(v47);
        std::wstring::~wstring(v48);
        std::wstring::~wstring(v49);
        v18 = *v3;
        v19 = (const wchar_t *)(*v3)[1];
        v20 = *v3;
        if ( *((_BYTE *)v19 + 25) )
        {
          v21 = *v3;
        }
        else
        {
          do
          {
            if ( (unsigned __int8)std::operator<<unsigned short>(v19 + 40, v10 + 24) )
            {
              v19 = (const wchar_t *)*((_QWORD *)v19 + 2);
            }
            else
            {
              if ( *((_BYTE *)v20 + 25) && (unsigned __int8)std::operator<<unsigned short>(v10 + 24, v19 + 40) )
                v20 = (__int64 *)v19;
              v18 = (__int64 *)v19;
              v19 = *(const wchar_t **)v19;
            }
          }
          while ( !*((_BYTE *)v19 + 25) );
          v3 = v39;
          v21 = *v39;
          v15 = v10 + 24;
        }
        if ( *((_BYTE *)v20 + 25) )
          k = (const wchar_t *)(v21 + 1);
        else
          k = (const wchar_t *)v20;
LABEL_41:
        for ( k = *(const wchar_t **)k; !*((_BYTE *)k + 25); k = (const wchar_t *)*((_QWORD *)k + 2) )
        {
          if ( (unsigned __int8)std::operator<<unsigned short>(v15, k + 40) )
          {
            v20 = (__int64 *)k;
            goto LABEL_41;
          }
        }
        v23 = *v3;
        if ( v18 == (__int64 *)**v3 && *((_BYTE *)v20 + 25) )
        {
          v24 = (_BYTE *)v23[1];
          if ( !v24[25] )
          {
            do
            {
              std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *>>>(
                v3,
                v3,
                *((_QWORD *)v24 + 2));
              v25 = *(_BYTE **)v24;
              wpc::AppLimits::AppInventory::AppInfo::~AppInfo((char **)v24 + 14);
              std::wstring::~wstring((char **)v24 + 10);
              if ( (char)v24[72] != -1 )
                std::wstring::~wstring((char **)v24 + 5);
              v26 = v24;
              v24 = v25;
              operator delete(v26);
            }
            while ( !v25[25] );
          }
          v23[1] = (__int64)v23;
          *v23 = (__int64)v23;
          v23[2] = (__int64)v23;
          v3[1] = 0;
        }
        else
        {
          while ( v18 != v20 )
          {
            v29 = v18;
            v30 = (__int64 **)v18[2];
            if ( *((_BYTE *)v30 + 25) )
            {
              for ( m = (__int64 *)v18[1]; !*((_BYTE *)m + 25) && v18 == (__int64 *)m[2]; m = (__int64 *)m[1] )
                v18 = m;
              v18 = m;
            }
            else
            {
              v18 = (__int64 *)v18[2];
              for ( n = *v30; !*((_BYTE *)n + 25); n = (__int64 *)*n )
                v18 = n;
            }
            std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::_Erase_unchecked(
              v3,
              v29);
          }
        }
        v34 |= 3u;
        v10 += 40;
        v11 = v38;
        v12 = (char *)v38 + 72;
      }
      while ( v10 != (const wchar_t *)v13 );
      v2 = v35;
    }
    std::vector<appids::AnyRuntimeApp>::~vector<appids::AnyRuntimeApp>(v36);
    v27 = (__int64 **)v2[2];
    if ( *((_BYTE *)v27 + 25) )
    {
      for ( ii = (__int64 *)v2[1]; !*((_BYTE *)ii + 25) && v2 == (__int64 *)ii[2]; ii = (__int64 *)ii[1] )
        v2 = ii;
      v2 = ii;
      v35 = ii;
    }
    else
    {
      v2 = (__int64 *)v2[2];
      v35 = (__int64 *)v27;
      for ( jj = *v27; !*((_BYTE *)jj + 25); jj = (__int64 *)*jj )
      {
        v2 = jj;
        v35 = jj;
      }
    }
  }
  if ( v40[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40[0] + 24LL))(v40[0]);
}

```

## disassembly

```asm
0x180017ee0  push    rbp
0x180017ee2  push    rbx
0x180017ee3  push    rsi
0x180017ee4  push    rdi
0x180017ee5  push    r12
0x180017ee7  push    r13
0x180017ee9  push    r14
0x180017eeb  push    r15
0x180017eed  lea     rbp, [rsp-38h]
0x180017ef2  sub     rsp, 138h
0x180017ef9  mov     rax, cs:__security_cookie
0x180017f00  xor     rax, rsp
0x180017f03  mov     [rbp+70h+var_48], rax
0x180017f07  mov     rbx, rcx
0x180017f0a  xor     r12d, r12d
0x180017f0d  mov     [rsp+170h+var_150], r12d
0x180017f12  lea     rcx, [rbp+70h+FileTime2]
0x180017f16  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x180017f1b  mov     rax, [rbx]
0x180017f1e  lea     rdx, [rsp+170h+var_110]
0x180017f23  mov     rcx, rbx
0x180017f26  mov     rax, [rax+30h]
0x180017f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f2f  nop
0x180017f30  mov     rax, [rsp+170h+var_108]
0x180017f35  mov     rdi, [rax]
0x180017f38  mov     rdi, [rdi]
0x180017f3b  mov     [rsp+170h+var_148], rdi
0x180017f40  cmp     [rdi+19h], r12b
0x180017f44  jnz     loc_180018325
0x180017f4a  lea     rcx, [rdi+20h]
0x180017f4e  mov     [rsp+170h+var_128], rcx
0x180017f53  lea     r15, [rcx+68h]
0x180017f57  mov     [rsp+170h+var_118], r15
0x180017f5c  xorps   xmm0, xmm0
0x180017f5f  movdqu  xmmword ptr [rsp+170h+var_140], xmm0
0x180017f65  mov     [rsp+170h+var_130], r12
0x180017f6a  mov     rbx, [r15]
0x180017f6d  mov     rbx, [rbx]
0x180017f70  cmp     [rbx+19h], r12b
0x180017f74  jnz     loc_180018045
0x180017f7a  cmp     [rbx+128h], r12b
0x180017f81  jz      short loc_180017FF6
0x180017f83  lea     rdx, [rbx+108h]
0x180017f8a  cmp     qword ptr [rdx+18h], 7
0x180017f8f  jbe     short loc_180017F94
0x180017f91  mov     rdx, [rdx]
0x180017f94  lea     rcx, [rbp+70h+var_E0]
0x180017f98  call    ?Deserialize@DateTime@@SA?AV1@QEBG@Z; DateTime::Deserialize(ushort const * const)
0x180017f9d  lea     r8, qword_18004A3B0
0x180017fa4  lea     rdx, [rbp+70h+var_C0]
0x180017fa8  lea     rcx, [rbp+70h+var_E0]
0x180017fac  call    ??HDateTime@@QEBA?AV0@AEBVTimeSpan@@@Z; DateTime::operator+(TimeSpan const &)
0x180017fb1  lea     rdx, [rbp+70h+FileTime2]; lpFileTime2
0x180017fb5  mov     rcx, rax; lpFileTime1
0x180017fb8  call    cs:__imp_CompareFileTime
0x180017fbe  shr     eax, 1Fh
0x180017fc1  test    al, al
0x180017fc3  jz      short loc_180017FF6
0x180017fc5  mov     rax, [rsp+170h+var_140+8]
0x180017fca  cmp     rax, [rsp+170h+var_130]
0x180017fcf  jz      short loc_180017FE5
0x180017fd1  lea     rdx, [rbx+20h]; struct appids::AnyRuntimeApp *
0x180017fd5  mov     rcx, rax; this
0x180017fd8  call    ??0AnyRuntimeApp@appids@@QEAA@AEBV01@@Z; appids::AnyRuntimeApp::AnyRuntimeApp(appids::AnyRuntimeApp const &)
0x180017fdd  add     [rsp+170h+var_140+8], 50h ; 'P'
0x180017fe3  jmp     short loc_180017FF6
0x180017fe5  lea     r8, [rbx+20h]
0x180017fe9  mov     rdx, rax
0x180017fec  lea     rcx, [rsp+170h+var_140]
0x180017ff1  call    ??$_Emplace_reallocate@AEBVAnyRuntimeApp@appids@@@?$vector@VAnyRuntimeApp@appids@@V?$allocator@VAnyRuntimeApp@appids@@@std@@@std@@AEAAPEAVAnyRuntimeApp@appids@@QEAV23@AEBV23@@Z; std::vector<appids::AnyRuntimeApp>::_Emplace_reallocate<appids::AnyRuntimeApp const &>(appids::AnyRuntimeApp * const,appids::AnyRuntimeApp const &)
0x180017ff6  mov     rcx, [rbx+10h]
0x180017ffa  cmp     [rcx+19h], r12b
0x180017ffe  jz      short loc_180018021
0x180018000  mov     rax, [rbx+8]
0x180018004  jmp     short loc_180018013
0x180018006  cmp     rbx, [rax+10h]
0x18001800a  jnz     short loc_180018019
0x18001800c  mov     rbx, rax
0x18001800f  mov     rax, [rax+8]
0x180018013  cmp     [rax+19h], r12b
0x180018017  jz      short loc_180018006
0x180018019  mov     rbx, rax
0x18001801c  jmp     loc_180017F70
0x180018021  mov     rbx, rcx
0x180018024  mov     rcx, [rcx]
0x180018027  cmp     [rcx+19h], r12b
0x18001802b  jnz     loc_180017F70
0x180018031  mov     rbx, rcx
0x180018034  mov     rax, [rcx]
0x180018037  mov     rcx, rax
0x18001803a  cmp     [rax+19h], r12b
0x18001803e  jz      short loc_180018031
0x180018040  jmp     loc_180017F70
0x180018045  mov     r13, [rsp+170h+var_140]
0x18001804a  mov     rax, [rsp+170h+var_140+8]
0x18001804f  cmp     r13, rax
0x180018052  jz      loc_180018268
0x180018058  mov     rcx, [rsp+170h+var_128]; struct Sid *
0x18001805d  lea     rsi, [rcx+48h]
0x180018061  mov     rdi, rax
0x180018064  mov     rdx, r13; struct appids::AnyRuntimeApp *
0x180018067  call    ?DeleteAppForUser@AppInventoryStorage@AppInventory@AppLimits@wpc@@SAXAEBVSid@@AEBVAnyRuntimeApp@appids@@@Z; wpc::AppLimits::AppInventory::AppInventoryStorage::DeleteAppForUser(Sid const &,appids::AnyRuntimeApp const &)
0x18001806c  xorps   xmm0, xmm0
0x18001806f  movups  [rsp+170h+var_100], xmm0
0x180018074  mov     [rbp+70h+var_F0], r12
0x180018078  mov     [rbp+70h+var_E8], r12
0x18001807c  mov     r8d, 1Ch
0x180018082  lea     rdx, aApp0ExpiresFor; "App {0} expires for user {1}"
0x180018089  lea     rcx, [rsp+170h+var_100]
0x18001808e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018093  lea     rdx, [rsp+170h+var_100]
0x180018098  lea     rcx, [rbp+70h+var_70]
0x18001809c  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x1800180a1  mov     rbx, rax
0x1800180a4  lea     r12, [r13+30h]
0x1800180a8  mov     rdx, r12
0x1800180ab  lea     rcx, [rbp+70h+var_90]
0x1800180af  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800180b4  nop
0x1800180b5  lea     rdx, [rbp+70h+var_90]
0x1800180b9  mov     rcx, rbx; this
0x1800180bc  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x1800180c1  mov     rbx, rax
0x1800180c4  mov     rdx, rsi
0x1800180c7  lea     rcx, [rbp+70h+var_B0]
0x1800180cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800180d0  nop
0x1800180d1  lea     rdx, [rbp+70h+var_B0]
0x1800180d5  mov     rcx, rbx; this
0x1800180d8  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x1800180dd  lea     rdx, WPP_GLOBAL_Control
0x1800180e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180eb  cmp     rcx, rdx
0x1800180ee  jz      short loc_180018119
0x1800180f0  test    byte ptr [rcx+1Ch], 4
0x1800180f4  jz      short loc_180018119
0x1800180f6  cmp     qword ptr [rax+18h], 7
0x1800180fb  jbe     short loc_180018100
0x1800180fd  mov     rax, [rax]
0x180018100  mov     edx, 0Dh
0x180018105  mov     r9, rax
0x180018108  lea     r8, WPP_e79369f3d8d632091aecb665c0941012_Traceguids
0x18001810f  mov     rcx, [rcx+10h]
0x180018113  call    WPP_SF_S
0x180018118  nop
0x180018119  lea     rcx, [rbp+70h+var_B0]
0x18001811d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018122  nop
0x180018123  lea     rcx, [rbp+70h+var_90]
0x180018127  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001812c  nop
0x18001812d  lea     rcx, [rbp+70h+var_70]
0x180018131  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018136  mov     rbx, [r15]
0x180018139  mov     rsi, [rbx+8]
0x18001813d  mov     r14, rbx
0x180018140  cmp     byte ptr [rsi+19h], 0
0x180018144  jnz     short loc_180018191
0x180018146  lea     rdx, [r13+30h]
0x18001814a  lea     rcx, [rsi+50h]
0x18001814e  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180018153  test    al, al
0x180018155  jz      short loc_18001815D
0x180018157  mov     rsi, [rsi+10h]
0x18001815b  jmp     short loc_18001817D
0x18001815d  cmp     byte ptr [r14+19h], 0
0x180018162  jz      short loc_180018177
0x180018164  lea     rdx, [rsi+50h]
0x180018168  lea     rcx, [r13+30h]
0x18001816c  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180018171  test    al, al
0x180018173  cmovnz  r14, rsi
0x180018177  mov     rbx, rsi
0x18001817a  mov     rsi, [rsi]
0x18001817d  cmp     byte ptr [rsi+19h], 0
0x180018181  jz      short loc_180018146
0x180018183  mov     r15, [rsp+170h+var_118]
0x180018188  mov     rsi, [r15]
0x18001818b  lea     r12, [r13+30h]
0x18001818f  jmp     short loc_180018194
0x180018191  mov     rsi, rbx
0x180018194  cmp     byte ptr [r14+19h], 0
0x180018199  jz      short loc_1800181A1
0x18001819b  add     rsi, 8
0x18001819f  jmp     short loc_1800181A4
0x1800181a1  mov     rsi, r14
0x1800181a4  mov     rsi, [rsi]
0x1800181a7  jmp     short loc_1800181C2
0x1800181a9  lea     rdx, [rsi+50h]
0x1800181ad  mov     rcx, r12
0x1800181b0  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x1800181b5  test    al, al
0x1800181b7  jz      short loc_1800181BE
0x1800181b9  mov     r14, rsi
0x1800181bc  jmp     short loc_1800181A4
0x1800181be  mov     rsi, [rsi+10h]
0x1800181c2  cmp     byte ptr [rsi+19h], 0
0x1800181c6  jz      short loc_1800181A9
0x1800181c8  mov     rsi, [r15]
0x1800181cb  xor     r12d, r12d
0x1800181ce  cmp     rbx, [rsi]
0x1800181d1  jnz     loc_180018282
0x1800181d7  cmp     [r14+19h], r12b
0x1800181db  jz      loc_180018282
0x1800181e1  mov     rbx, [rsi+8]
0x1800181e5  cmp     [rbx+19h], r12b
0x1800181e9  jnz     short loc_180018239
0x1800181eb  mov     r8, [rbx+10h]
0x1800181ef  mov     rdx, r15
0x1800181f2  mov     rcx, r15
0x1800181f5  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *>>>(std::allocator<std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *>> &,std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *> *)
0x1800181fa  mov     r14, [rbx]
0x1800181fd  lea     rcx, [rbx+70h]; this
0x180018201  call    ??1AppInfo@AppInventory@AppLimits@wpc@@QEAA@XZ; wpc::AppLimits::AppInventory::AppInfo::~AppInfo(void)
0x180018206  lea     rcx, [rbx+50h]
0x18001820a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001820f  lea     rcx, [rbx+28h]
0x180018213  movsx   rax, byte ptr [rcx+20h]
0x180018218  add     rax, 1
0x18001821c  jz      short loc_180018223
0x18001821e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018223  mov     rcx, rbx; Block
0x180018226  mov     rbx, r14
0x180018229  mov     edx, 158h
0x18001822e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018233  cmp     [r14+19h], r12b
0x180018237  jz      short loc_1800181EB
0x180018239  mov     [rsi+8], rsi
0x18001823d  mov     [rsi], rsi
0x180018240  mov     [rsi+10h], rsi
0x180018244  mov     [r15+8], r12
0x180018248  or      [rsp+170h+var_150], 3
0x18001824d  add     r13, 50h ; 'P'
0x180018251  cmp     r13, rdi
0x180018254  mov     rcx, [rsp+170h+var_128]
0x180018259  lea     rsi, [rcx+48h]
0x18001825d  jnz     loc_180018064
0x180018263  mov     rdi, [rsp+170h+var_148]
0x180018268  lea     rcx, [rsp+170h+var_140]
0x18001826d  call    ??1?$vector@VAnyRuntimeApp@appids@@V?$allocator@VAnyRuntimeApp@appids@@@std@@@std@@QEAA@XZ; std::vector<appids::AnyRuntimeApp>::~vector<appids::AnyRuntimeApp>(void)
0x180018272  mov     rcx, [rdi+10h]
0x180018276  cmp     [rcx+19h], r12b
0x18001827a  jz      short loc_1800182F7
0x18001827c  mov     rax, [rdi+8]
0x180018280  jmp     short loc_1800182E4
0x180018282  cmp     rbx, r14
0x180018285  jz      short loc_180018248
0x180018287  mov     rdx, rbx
0x18001828a  mov     rcx, [rbx+10h]
0x18001828e  cmp     [rcx+19h], r12b
0x180018292  jz      short loc_1800182B2
0x180018294  mov     rax, [rbx+8]
0x180018298  jmp     short loc_1800182A7
0x18001829a  cmp     rbx, [rax+10h]
0x18001829e  jnz     short loc_1800182AD
0x1800182a0  mov     rbx, rax
0x1800182a3  mov     rax, [rax+8]
0x1800182a7  cmp     [rax+19h], r12b
0x1800182ab  jz      short loc_18001829A
0x1800182ad  mov     rbx, rax
0x1800182b0  jmp     short loc_1800182CD
0x1800182b2  mov     rbx, rcx
0x1800182b5  mov     rcx, [rcx]
0x1800182b8  cmp     [rcx+19h], r12b
0x1800182bc  jnz     short loc_1800182CD
0x1800182be  mov     rbx, rcx
0x1800182c1  mov     rax, [rcx]
0x1800182c4  mov     rcx, rax
0x1800182c7  cmp     [rax+19h], r12b
0x1800182cb  jz      short loc_1800182BE
0x1800182cd  mov     rcx, r15
0x1800182d0  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>,std::_Iterator_base0>)
0x1800182d5  jmp     short loc_180018282
0x1800182d7  cmp     rdi, [rax+10h]
0x1800182db  jnz     short loc_1800182EA
0x1800182dd  mov     rdi, rax
0x1800182e0  mov     rax, [rax+8]
0x1800182e4  cmp     [rax+19h], r12b
0x1800182e8  jz      short loc_1800182D7
0x1800182ea  mov     rdi, rax
0x1800182ed  mov     [rsp+170h+var_148], rax
0x1800182f2  jmp     loc_180017F40
0x1800182f7  mov     rdi, rcx
0x1800182fa  mov     [rsp+170h+var_148], rcx
0x1800182ff  mov     rcx, [rcx]
0x180018302  cmp     [rcx+19h], r12b
0x180018306  jnz     loc_180017F40
0x18001830c  mov     rdi, rcx
0x18001830f  mov     [rsp+170h+var_148], rcx
0x180018314  mov     rax, [rcx]
0x180018317  mov     rcx, rax
0x18001831a  cmp     [rax+19h], r12b
0x18001831e  jz      short loc_18001830C
0x180018320  jmp     loc_180017F40
0x180018325  mov     rcx, [rsp+170h+var_110]
0x18001832a  test    rcx, rcx
0x18001832d  jz      short loc_18001833C
0x18001832f  mov     rax, [rcx]
0x180018332  mov     rax, [rax+18h]
  ... truncated ...
```
