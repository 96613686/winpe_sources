# SqliteDatabase::AddNewNotification(IWpnNotification *,IWpnNotification * *,int *)

- ea: `0x180009980`
- end: `0x180009ec7`
- name: `?AddNewNotification@SqliteDatabase@@UEAAJPEAUIWpnNotification@@PEAPEAU2@PEAH@Z`
- size: `1351`
- prototype: `int(SqliteDatabase *__hidden this, struct IWpnNotification *, struct IWpnNotification **, int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004e38`
- `0x1800094b8`
- `0x180009980`
- `0x18000abb0`
- `0x18000b674`
- `0x18000e090`
- `0x18000e5f4`
- `0x180016510`
- `0x180018380`
- `0x18002ac00`
- `0x18002b07c`
- `0x180049644`
- `0x180085bd4`
- `0x1800a0b2c`
- `0x1800f08f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800099c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800099c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c93`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009d25`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009d25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009aed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009bd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009aed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009bd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall SqliteDatabase::AddNewNotification(
        SqliteDatabase *this,
        struct IWpnNotification *a2,
        struct IWpnNotification **a3,
        int *a4)
{
  _QWORD *v8; // rax
  bool v9; // zf
  char v10; // al
  int v11; // eax
  struct IWpnNotification *Replacement; // rax
  struct IWpnNotification *v13; // rbx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  int (__fastcall *v17)(struct IWpnNotification *, struct IWpnNotificationData **); // rsi
  struct IWpnNotification *v18; // rax
  struct IWpnNotificationData *v19; // rcx
  int v21; // eax
  __int64 v22; // rdx
  const WCHAR *v23; // rcx
  SqliteDatabase *v24; // rcx
  int v25; // eax
  int v26; // eax
  __int64 v27; // r9
  __int64 (__fastcall *v28)(struct IWpnNotification *, LPVOID *); // rsi
  int v29; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-B8h]
  LPVOID pv; // [rsp+58h] [rbp-80h] BYREF
  __int64 v32; // [rsp+60h] [rbp-78h]
  __int64 v33; // [rsp+68h] [rbp-70h]
  LPVOID v34; // [rsp+70h] [rbp-68h] BYREF
  __int64 v35; // [rsp+78h] [rbp-60h]
  __int64 v36; // [rsp+80h] [rbp-58h]
  unsigned __int16 *v37[10]; // [rsp+88h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  unsigned int v39; // [rsp+E8h] [rbp+10h] BYREF
  struct IWpnNotificationData *v40; // [rsp+F0h] [rbp+18h] BYREF
  struct IWpnNotification *v41; // [rsp+F8h] [rbp+20h]

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0, a3);
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 3);
  v8 = (_QWORD *)*((_QWORD *)this + 2);
  if ( !v8 || (v9 = *v8 == 0, v10 = 0, v9) )
    v10 = 1;
  if ( v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)0x8007139FLL,
      bIgnoreCase);
  if ( *((_BYTE *)this + 180) )
  {
    if ( this != (SqliteDatabase *)-120LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 3);
    return 0;
  }
  else
  {
    v37[0] = 0;
    v37[1] = (unsigned __int16 *)-1LL;
    v37[2] = (unsigned __int16 *)-1LL;
    v11 = (*(__int64 (__fastcall **)(struct IWpnNotification *, unsigned __int16 **))(*(_QWORD *)a2 + 32LL))(a2, v37);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x235,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v11,
        bIgnoreCase);
    Database::BeginTransaction(*((_QWORD *)this + 2));
    SqliteDatabase::ProcessExpiry((SqliteDatabase *)((char *)this - 32));
    v41 = 0;
    Replacement = SqliteDatabase::FindReplacement((SqliteDatabase *)((char *)this - 32), a2);
    v13 = Replacement;
    v41 = Replacement;
    if ( Replacement )
    {
      if ( a4 )
        *a4 = 1;
      v39 = 0;
      v26 = (*(__int64 (__fastcall **)(struct IWpnNotification *, unsigned int *))(*(_QWORD *)Replacement + 24LL))(
              Replacement,
              &v39);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x245,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
          (const char *)(unsigned int)v26,
          bIgnoreCase);
      LOBYTE(v27) = 1;
      (*(void (__fastcall **)(char *, unsigned __int16 *, _QWORD, __int64))(*((_QWORD *)this - 4) + 80LL))(
        (char *)this - 32,
        v37[0],
        v39,
        v27);
      pv = 0;
      v32 = 0;
      v33 = 0;
      v28 = *(__int64 (__fastcall **)(struct IWpnNotification *, LPVOID *))(*(_QWORD *)v13 + 40LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
      v32 = -1;
      v33 = -1;
      v29 = v28(v13, &pv);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x249,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
          (const char *)(unsigned int)v29,
          5);
      LODWORD(v22) = v32;
      if ( v32 == -1 )
      {
        if ( pv )
        {
          v22 = -1;
          do
            ++v22;
          while ( *((_WORD *)pv + v22) );
        }
        else
        {
          LODWORD(v22) = 0;
        }
      }
      v23 = &word_180124798;
      if ( pv )
        v23 = (const WCHAR *)pv;
      if ( CompareStringOrdinal(v23, v22, L"tile", -1, 0) == 2 )
      {
        v25 = SqliteDatabase::FillReplacementExplicitId(v24, v13, a2);
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x24E,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
            (const char *)(unsigned int)v25,
            bIgnoreCase);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    }
    else
    {
      pv = 0;
      v32 = -1;
      v33 = -1;
      v14 = (*(__int64 (__fastcall **)(struct IWpnNotification *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &pv);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x255,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
          (const char *)(unsigned int)v14,
          bIgnoreCase);
      v13 = SqliteDatabase::ProcessRollover((SqliteDatabase *)((char *)this - 32), v37[0], (const unsigned __int16 *)pv);
      v41 = v13;
      if ( pv )
        CoTaskMemFree(pv);
    }
    SqliteDatabase::InsertNotification((SqliteDatabase *)((char *)this - 32), a2);
    v34 = 0;
    v35 = -1;
    v36 = -1;
    v15 = (*(__int64 (__fastcall **)(struct IWpnNotification *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &v34);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v15,
        bIgnoreCase);
    LOBYTE(v16) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_40049089>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_40049089>::GetImpl'::`2'::impl,
      v16);
    v40 = 0;
    v17 = *(int (__fastcall **)(struct IWpnNotification *, struct IWpnNotificationData **))(*(_QWORD *)a2 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    if ( v17(a2, &v40) >= 0 && v40 )
    {
      v39 = 0;
      v21 = (*(__int64 (__fastcall **)(struct IWpnNotification *, unsigned int *))(*(_QWORD *)a2 + 24LL))(a2, &v39);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x273,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
          (const char *)(unsigned int)v21,
          bIgnoreCase);
      SqliteDatabase::InsertNotificationData((SqliteDatabase *)((char *)this - 32), v39, v40);
    }
    if ( a3 )
    {
      v18 = v13;
      v13 = 0;
      v41 = 0;
      *a3 = v18;
    }
    Database::Commit(*((Database **)this + 2));
    v19 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(struct IWpnNotificationData *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    if ( v34 )
    {
      CoTaskMemFree(v34);
      v34 = 0;
    }
    v35 = 0;
    v36 = 0;
    if ( v13 )
      (*(void (__fastcall **)(struct IWpnNotification *))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v37[0] )
      CoTaskMemFree(v37[0]);
    if ( this != (SqliteDatabase *)-120LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 3);
    return 0;
  }
}

```

## disassembly

```asm
0x180009980  mov     [rsp+arg_0], rcx
0x180009985  push    rbx
0x180009986  push    rsi
0x180009987  push    rdi
0x180009988  push    r12
0x18000998a  push    r13
0x18000998c  push    r14
0x18000998e  push    r15
0x180009990  sub     rsp, 0A0h
0x180009997  mov     rsi, r9
0x18000999a  mov     r12, r8
0x18000999d  mov     r14, rdx
0x1800099a0  mov     r13, rcx
0x1800099a3  xor     ebx, ebx
0x1800099a5  test    rdx, rdx
0x1800099a8  jz      loc_180009E8A
0x1800099ae  test    r12, r12
0x1800099b1  jnz     loc_180009E94
0x1800099b7  test    rsi, rsi
0x1800099ba  jnz     loc_180009CF6
0x1800099c0  lea     rdi, [r13+78h]
0x1800099c4  mov     rcx, rdi; lpCriticalSection
0x1800099c7  call    cs:__imp_EnterCriticalSection
0x1800099cd  mov     [rsp+0D8h+var_98], rdi
0x1800099d2  lea     r15, [r13-20h]
0x1800099d6  mov     rax, [r15+30h]
0x1800099da  test    rax, rax
0x1800099dd  jz      short loc_1800099E6
0x1800099df  cmp     [rax], rbx
0x1800099e2  mov     al, bl
0x1800099e4  jnz     short loc_1800099E8
0x1800099e6  mov     al, 1
0x1800099e8  mov     rcx, [rsp+0D8h]; this
0x1800099f0  test    al, al
0x1800099f2  jnz     loc_180009C34
0x1800099f8  cmp     [r13+0B4h], bl
0x1800099ff  jnz     loc_180009C8B
0x180009a05  mov     [rsp+0D8h+var_90], r15
0x180009a0a  mov     [rsp+0D8h+var_88], 1
0x180009a0f  mov     [rsp+0D8h+var_50], rbx
0x180009a17  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009a1b  mov     [rsp+0D8h+var_48], rax
0x180009a23  mov     [rsp+0D8h+var_40], rax
0x180009a2b  mov     rax, [r14]
0x180009a2e  lea     rdx, [rsp+0D8h+var_50]
0x180009a36  mov     rcx, r14
0x180009a39  mov     rax, [rax+20h]
0x180009a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a42  mov     rcx, [rsp+0D8h]; this
0x180009a4a  test    eax, eax
0x180009a4c  js      loc_180009C4C
0x180009a52  mov     rcx, [r13+10h]
0x180009a56  call    ?BeginTransaction@Database@@QEAAXW4BeginTransactionLock@1@@Z; Database::BeginTransaction(Database::BeginTransactionLock)
0x180009a5b  mov     rcx, r15; this
0x180009a5e  call    ?ProcessExpiry@SqliteDatabase@@AEAAXXZ; SqliteDatabase::ProcessExpiry(void)
0x180009a63  mov     [rsp+0D8h+arg_18], rbx
0x180009a6b  mov     rdx, r14; struct IWpnNotification *
0x180009a6e  mov     rcx, r15; this
0x180009a71  call    ?FindReplacement@SqliteDatabase@@AEAAPEAUIWpnNotification@@PEAU2@@Z; SqliteDatabase::FindReplacement(IWpnNotification *)
0x180009a76  mov     rbx, rax
0x180009a79  mov     [rsp+0D8h+arg_18], rax
0x180009a81  test    rax, rax
0x180009a84  jnz     loc_180009E9D
0x180009a8a  xor     esi, esi
0x180009a8c  mov     [rsp+0D8h+pv], rsi
0x180009a91  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009a95  mov     [rsp+0D8h+var_78], rax
0x180009a9a  mov     [rsp+0D8h+var_70], rax
0x180009a9f  mov     rax, [r14]
0x180009aa2  lea     rdx, [rsp+0D8h+pv]
0x180009aa7  mov     rcx, r14
0x180009aaa  mov     rax, [rax+28h]
0x180009aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ab3  mov     rcx, [rsp+0D8h]; this
0x180009abb  test    eax, eax
0x180009abd  js      loc_180009C61
0x180009ac3  mov     r8, [rsp+0D8h+pv]; unsigned __int16 *
0x180009ac8  mov     rdx, [rsp+0D8h+var_50]; unsigned __int16 *
0x180009ad0  mov     rcx, r15; this
0x180009ad3  call    ?ProcessRollover@SqliteDatabase@@AEAAPEAUIWpnNotification@@PEBG0@Z; SqliteDatabase::ProcessRollover(ushort const *,ushort const *)
0x180009ad8  mov     rbx, rax
0x180009adb  mov     [rsp+0D8h+arg_18], rax
0x180009ae3  mov     rcx, [rsp+0D8h+pv]; pv
0x180009ae8  test    rcx, rcx
0x180009aeb  jz      short loc_180009AF3
0x180009aed  call    cs:__imp_CoTaskMemFree
0x180009af3  mov     rdx, r14; struct IWpnNotification *
0x180009af6  mov     rcx, r15; this
0x180009af9  call    ?InsertNotification@SqliteDatabase@@AEAAXPEAUIWpnNotification@@@Z; SqliteDatabase::InsertNotification(IWpnNotification *)
0x180009afe  mov     [rsp+0D8h+var_68], rsi
0x180009b03  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009b07  mov     [rsp+0D8h+var_60], rax
0x180009b0c  mov     [rsp+0D8h+var_58], rax
0x180009b14  mov     rax, [r14]
0x180009b17  lea     rdx, [rsp+0D8h+var_68]
0x180009b1c  mov     rcx, r14
0x180009b1f  mov     rax, [rax+28h]
0x180009b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b28  mov     rcx, [rsp+0D8h]; this
0x180009b30  test    eax, eax
0x180009b32  js      loc_180009C76
0x180009b38  mov     dl, 1
0x180009b3a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_40049089@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_40049089@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40049089> `wil::Feature<__WilFeatureTraits_Feature_40049089>::GetImpl(void)'::`2'::impl
0x180009b41  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_40049089@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40049089>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180009b46  mov     [rsp+0D8h+arg_10], rsi
0x180009b4e  mov     rax, [r14]
0x180009b51  mov     rsi, [rax+60h]
0x180009b55  lea     rcx, [rsp+0D8h+arg_10]
0x180009b5d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009b62  lea     rdx, [rsp+0D8h+arg_10]
0x180009b6a  mov     rcx, r14
0x180009b6d  mov     rax, rsi
0x180009b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b75  xor     esi, esi
0x180009b77  test    eax, eax
0x180009b79  jns     loc_180009CA5
0x180009b7f  test    r12, r12
0x180009b82  jz      short loc_180009B96
0x180009b84  mov     rax, rbx
0x180009b87  mov     rbx, rsi
0x180009b8a  mov     [rsp+0D8h+arg_18], rbx
0x180009b92  mov     [r12], rax
0x180009b96  mov     rcx, [r13+10h]; this
0x180009b9a  call    ?Commit@Database@@QEAAXXZ; Database::Commit(void)
0x180009b9f  mov     [rsp+0D8h+var_88], sil
0x180009ba4  mov     rcx, [rsp+0D8h+arg_10]
0x180009bac  test    rcx, rcx
0x180009baf  jz      short loc_180009BC6
0x180009bb1  mov     [rsp+0D8h+arg_10], rsi
0x180009bb9  mov     rax, [rcx]
0x180009bbc  mov     rax, [rax+10h]
0x180009bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bc5  nop
0x180009bc6  mov     rcx, [rsp+0D8h+var_68]; pv
0x180009bcb  test    rcx, rcx
0x180009bce  jz      short loc_180009BDB
0x180009bd0  call    cs:__imp_CoTaskMemFree
0x180009bd6  mov     [rsp+0D8h+var_68], rsi
0x180009bdb  mov     [rsp+0D8h+var_60], rsi
0x180009be0  mov     [rsp+0D8h+var_58], rsi
0x180009be8  test    rbx, rbx
0x180009beb  jz      short loc_180009BFD
0x180009bed  mov     rax, [rbx]
0x180009bf0  mov     rcx, rbx
0x180009bf3  mov     rax, [rax+10h]
0x180009bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bfc  nop
0x180009bfd  mov     rcx, [rsp+0D8h+var_50]; pv
0x180009c05  test    rcx, rcx
0x180009c08  jz      short loc_180009C11
0x180009c0a  call    cs:__imp_CoTaskMemFree
0x180009c10  nop
0x180009c11  test    rdi, rdi
0x180009c14  jz      short loc_180009C1F
0x180009c16  mov     rcx, rdi; lpCriticalSection
0x180009c19  call    cs:__imp_LeaveCriticalSection
0x180009c1f  xor     eax, eax
0x180009c21  add     rsp, 0A0h
0x180009c28  pop     r15
0x180009c2a  pop     r14
0x180009c2c  pop     r13
0x180009c2e  pop     r12
0x180009c30  pop     rdi
0x180009c31  pop     rsi
0x180009c32  pop     rbx
0x180009c33  retn
0x180009c34  mov     r9d, 8007139Fh; char *
0x180009c3a  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009c41  mov     edx, 22Fh; void *
0x180009c46  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009c4c  mov     r9d, eax; char *
0x180009c4f  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009c56  mov     edx, 235h; void *
0x180009c5b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009c61  mov     r9d, eax; char *
0x180009c64  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009c6b  mov     edx, 255h; void *
0x180009c70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009c76  mov     r9d, eax; char *
0x180009c79  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009c80  mov     edx, 25Ch; void *
0x180009c85  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009c8b  test    rdi, rdi
0x180009c8e  jz      short loc_180009C9E
0x180009c90  mov     rcx, rdi; lpCriticalSection
0x180009c93  call    cs:__imp_LeaveCriticalSection
0x180009c99  mov     [rsp+0D8h+var_98], rbx
0x180009c9e  xor     eax, eax
0x180009ca0  jmp     loc_180009C21
0x180009ca5  cmp     [rsp+0D8h+arg_10], rsi
0x180009cad  jz      loc_180009B7F
0x180009cb3  mov     [rsp+0D8h+arg_8], esi
0x180009cba  mov     rax, [r14]
0x180009cbd  lea     rdx, [rsp+0D8h+arg_8]
0x180009cc5  mov     rcx, r14
0x180009cc8  mov     rax, [rax+18h]
0x180009ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cd1  mov     rcx, [rsp+0D8h]; this
0x180009cd9  test    eax, eax
0x180009cdb  jns     loc_180009E6E
0x180009ce1  mov     r9d, eax; char *
0x180009ce4  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009ceb  mov     edx, 273h; void *
0x180009cf0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009cf6  mov     [rsi], ebx
0x180009cf8  jmp     loc_1800099C0
0x180009cfd  mov     rdx, r8
0x180009d00  inc     rdx; cchCount1
0x180009d03  cmp     [rax+rdx*2], si
0x180009d07  jnz     short loc_180009D00
0x180009d09  lea     rcx, word_180124798
0x180009d10  test    rax, rax
0x180009d13  cmovnz  rcx, rax; lpString1
0x180009d17  mov     [rsp+0D8h+bIgnoreCase], esi; int
0x180009d1b  mov     r9d, r8d; cchCount2
0x180009d1e  lea     r8, aTile; "tile"
0x180009d25  call    cs:__imp_CompareStringOrdinal
0x180009d2b  cmp     eax, 2
0x180009d2e  jnz     loc_180009E5F
0x180009d34  mov     r8, r14; struct IWpnNotification *
0x180009d37  mov     rdx, rbx; struct IWpnNotification *
0x180009d3a  call    ?FillReplacementExplicitId@SqliteDatabase@@AEAAJPEAUIWpnNotification@@0@Z; SqliteDatabase::FillReplacementExplicitId(IWpnNotification *,IWpnNotification *)
0x180009d3f  mov     rcx, [rsp+0D8h]; this
0x180009d47  test    eax, eax
0x180009d49  jns     loc_180009E5F
0x180009d4f  mov     r9d, eax; char *
0x180009d52  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009d59  mov     edx, 24Eh; void *
0x180009d5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009d64  xor     esi, esi
0x180009d66  mov     [rsp+0D8h+arg_8], esi
0x180009d6d  mov     rax, [rax]
0x180009d70  lea     rdx, [rsp+0D8h+arg_8]
0x180009d78  mov     rcx, rbx
0x180009d7b  mov     rax, [rax+18h]
0x180009d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d84  mov     rcx, [rsp+0D8h]; this
0x180009d8c  test    eax, eax
0x180009d8e  js      loc_180009E35
0x180009d94  mov     rax, [r15]
0x180009d97  mov     [rsp+0D8h+var_B0], esi
0x180009d9b  mov     [rsp+0D8h+bIgnoreCase], 5; int
0x180009da3  mov     r9b, 1
0x180009da6  mov     r8d, [rsp+0D8h+arg_8]
0x180009dae  mov     rdx, [rsp+0D8h+var_50]
0x180009db6  mov     rcx, r15
0x180009db9  mov     rax, [rax+50h]
0x180009dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dc2  mov     [rsp+0D8h+pv], rsi
0x180009dc7  mov     [rsp+0D8h+var_78], rsi
0x180009dcc  mov     [rsp+0D8h+var_70], rsi
0x180009dd1  mov     rax, [rbx]
0x180009dd4  mov     rsi, [rax+28h]
0x180009dd8  lea     rcx, [rsp+0D8h+pv]
0x180009ddd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009de2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009de6  mov     [rsp+0D8h+var_78], rax
0x180009deb  mov     [rsp+0D8h+var_70], rax
0x180009df0  lea     rdx, [rsp+0D8h+pv]
0x180009df5  mov     rcx, rbx
0x180009df8  mov     rax, rsi
0x180009dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e00  mov     rcx, [rsp+0D8h]; this
0x180009e08  xor     esi, esi
0x180009e0a  test    eax, eax
0x180009e0c  js      short loc_180009E4A
0x180009e0e  mov     rdx, [rsp+0D8h+var_78]
0x180009e13  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009e17  mov     rax, [rsp+0D8h+pv]
0x180009e1c  cmp     rdx, r8
0x180009e1f  jnz     loc_180009D09
0x180009e25  test    rax, rax
0x180009e28  jnz     loc_180009CFD
0x180009e2e  mov     edx, esi
0x180009e30  jmp     loc_180009D09
0x180009e35  mov     r9d, eax; char *
0x180009e38  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009e3f  mov     edx, 245h; void *
0x180009e44  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009e4a  mov     r9d, eax; char *
0x180009e4d  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009e54  mov     edx, 249h; void *
0x180009e59  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009e5f  lea     rcx, [rsp+0D8h+pv]
0x180009e64  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009e69  jmp     loc_180009AF3
0x180009e6e  mov     r8, [rsp+0D8h+arg_10]; struct IWpnNotificationData *
0x180009e76  mov     edx, [rsp+0D8h+arg_8]; unsigned int
0x180009e7d  mov     rcx, r15; this
0x180009e80  call    ?InsertNotificationData@SqliteDatabase@@AEAAXKPEAUIWpnNotificationData@@@Z; SqliteDatabase::InsertNotificationData(ulong,IWpnNotificationData *)
0x180009e85  jmp     loc_180009B7F
0x180009e8a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "newNotification != nullptr")
0x180009e8f  jmp     loc_1800099AE
0x180009e94  mov     [r12], rbx
0x180009e98  jmp     loc_1800099B7
0x180009e9d  test    rsi, rsi
0x180009ea0  jz      loc_180009D64
0x180009ea6  mov     dword ptr [rsi], 1
0x180009eac  jmp     loc_180009D64
0x180009eb1  lea     rcx, [rsp+0D8h+var_98]; this
  ... truncated ...
```
