# SystemSettings::BatterySaverOneCoreDataModel::CBatteryIcon::GetBatteryIconData(SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE_SNAPSHOT *)

- ea: `0x1800412f4`
- end: `0x180041616`
- name: `?GetBatteryIconData@CBatteryIcon@BatterySaverOneCoreDataModel@SystemSettings@@QEAAEPEAU_BATTERY_STATE_SNAPSHOT@23@@Z`
- size: `802`
- prototype: `unsigned __int8 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatteryIcon *__hidden this, struct SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE_SNAPSHOT *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040d74`

## callees

- `0x18000b508`
- `0x1800140d8`
- `0x1800144c4`
- `0x180034768`
- `0x180034844`
- `0x180037b94`
- `0x180040704`
- `0x180040748`
- `0x18004097c`
- `0x180040ae0`
- `0x180040b40`
- `0x180040ba0`
- `0x180040c50`
- `0x1800412f4`
- `0x180042d00`
- `0x1800457ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041322`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041322`

## string_xrefs

- `0x180041467`: `[CBatteryIcon] GetBatteryIconData: refreshed icon cache on demand\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatteryIcon::GetBatteryIconData(
        RTL_SRWLOCK *this,
        struct SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE_SNAPSHOT *a2)
{
  struct SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE_SNAPSHOT *v2; // r12
  RTL_SRWLOCK *v3; // r15
  char v4; // di
  int v5; // esi
  RTL_SRWLOCK *v6; // rbx
  RTL_SRWLOCK *v7; // r14
  __int64 v8; // rbx
  char v9; // r13
  _QWORD *v10; // rax
  int v11; // esi
  char v12; // bl
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 *v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rax
  __int64 v20; // rdx
  RTL_SRWLOCK *v21; // r15
  __int64 *v22; // rax
  __int64 v23; // rdx
  __int64 *v24; // rax
  __int64 v25; // rdx
  _BYTE v27[8]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v28[8]; // [rsp+28h] [rbp-50h] BYREF
  RTL_SRWLOCK *v29; // [rsp+30h] [rbp-48h] BYREF
  RTL_SRWLOCK *v30; // [rsp+80h] [rbp+8h] BYREF
  struct SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE_SNAPSHOT *v31; // [rsp+88h] [rbp+10h]
  __int64 v32; // [rsp+90h] [rbp+18h] BYREF
  RTL_SRWLOCK *v33; // [rsp+98h] [rbp+20h]

  v31 = a2;
  v30 = this;
  v2 = a2;
  v3 = this;
  v4 = 0;
  v5 = 0;
  LODWORD(v32) = 0;
  v6 = this + 3;
  AcquireSRWLockExclusive(this + 3);
  v29 = v6;
  v7 = v3 + 1;
  if ( !LOBYTE(v3[5].Ptr) )
  {
    v8 = v32;
    goto LABEL_5;
  }
  v8 = 0;
  v32 = 0;
  v5 = 1;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v3[1], &v32) )
  {
LABEL_5:
    v9 = 1;
    goto LABEL_6;
  }
  v9 = 0;
LABEL_6:
  v33 = v3 + 1;
  if ( (v5 & 1) != 0 )
  {
    v5 &= ~1u;
    if ( v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v32);
  }
  if ( !v9 )
  {
    v10 = (_QWORD *)winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphFill(
                      &v3[1],
                      v28);
    v11 = v5 | 2;
    LODWORD(v32) = v11;
    if ( !*v10
      || (LOBYTE(v11) = v11 | 4,
          v12 = 0,
          !*(_QWORD *)winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphOutline(
                        &v3[1],
                        v27)) )
    {
      v12 = 1;
    }
    if ( (v11 & 4) != 0 )
    {
      LOBYTE(v11) = v11 & 0xFB;
      winrt::handle_type<winrt::impl::hstring_traits>::close(v27);
    }
    if ( (v11 & 2) != 0 )
      winrt::handle_type<winrt::impl::hstring_traits>::close(v28);
    if ( v12 )
    {
      v32 = 0;
      if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(v3, &v32) )
      {
        try
        {
          v13 = winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphOutline(
                  v3,
                  &v32);
          winrt::Windows::Internal::UI::PowerUX::BatteryIconData::operator=(&v3[1], v13);
          winrt::Windows::Foundation::IInspectable::~IInspectable((winrt::Windows::Foundation::IInspectable *)&v32);
          v14 = winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphFill(
                  v3,
                  &v32);
          winrt::Windows::Internal::UI::PowerUX::BatteryIconData::operator=(&v3[2], v14);
          winrt::Windows::Foundation::IInspectable::~IInspectable((winrt::Windows::Foundation::IInspectable *)&v32);
          SystemSettings::DataModel::PowerAndBatteryHelper::DebugTrace(L"[CBatteryIcon] GetBatteryIconData: refreshed icon cache on demand\n");
        }
        catch ( ... )
        {
          SystemSettings::DataModel::PowerAndBatteryHelper::DebugTrace(L"[CBatteryIcon] GetBatteryIconData: on-demand refresh failed\n");
          v3 = v30;
          v2 = v31;
          v7 = v33;
        }
      }
    }
    *(_DWORD *)v2 = winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BatteryPercentage(v7);
    v15 = (__int64 *)winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::AltText(
                       &v3[1],
                       &v30);
    if ( (__int64 *)((char *)v2 + 8) != v15 )
    {
      v16 = *v15;
      *v15 = 0;
      winrt::handle_type<winrt::impl::hstring_traits>::attach((char *)v2 + 8, v16);
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v30);
    *((_BYTE *)v2 + 52) = winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::IsBatteryPresent(v7);
    v17 = (__int64 *)winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphFill(
                       &v3[1],
                       &v30);
    if ( (__int64 *)((char *)v2 + 16) != v17 )
    {
      v18 = *v17;
      *v17 = 0;
      winrt::handle_type<winrt::impl::hstring_traits>::attach((char *)v2 + 16, v18);
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v30);
    v19 = (__int64 *)winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphOutline(
                       &v3[1],
                       &v30);
    if ( (__int64 *)((char *)v2 + 24) != v19 )
    {
      v20 = *v19;
      *v19 = 0;
      winrt::handle_type<winrt::impl::hstring_traits>::attach((char *)v2 + 24, v20);
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v30);
    *((_DWORD *)v2 + 12) = winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BatteryFillColor(v7);
    v30 = 0;
    v21 = v3 + 2;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(v21, &v30) )
    {
      winrt::hstring::operator=((char *)v2 + 32, (char *)v2 + 16);
      winrt::hstring::operator=((char *)v2 + 40, (char *)v2 + 24);
    }
    else
    {
      v22 = (__int64 *)winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphFill(
                         v21,
                         &v30);
      if ( (__int64 *)((char *)v2 + 32) != v22 )
      {
        v23 = *v22;
        *v22 = 0;
        winrt::handle_type<winrt::impl::hstring_traits>::attach((char *)v2 + 32, v23);
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v30);
      v24 = (__int64 *)winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphOutline(
                         v21,
                         &v30);
      if ( (__int64 *)((char *)v2 + 40) != v24 )
      {
        v25 = *v24;
        *v24 = 0;
        winrt::handle_type<winrt::impl::hstring_traits>::attach((char *)v2 + 40, v25);
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v30);
    }
    v4 = 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v29);
  return v4;
}

```

## disassembly

```asm
0x1800412f4  mov     rax, rsp
0x1800412f7  mov     [rax+10h], rdx
0x1800412fb  mov     [rax+8], rcx
0x1800412ff  push    rbx
0x180041300  push    rsi
0x180041301  push    rdi
0x180041302  push    r12
0x180041304  push    r13
0x180041306  push    r14
0x180041308  push    r15
0x18004130a  sub     rsp, 40h
0x18004130e  mov     r12, rdx
0x180041311  mov     r15, rcx
0x180041314  xor     edi, edi
0x180041316  mov     esi, edi
0x180041318  mov     [rax+18h], edi
0x18004131b  lea     rbx, [rcx+18h]
0x18004131f  mov     rcx, rbx; SRWLock
0x180041322  call    cs:__imp_AcquireSRWLockExclusive
0x180041328  mov     [rsp+78h+var_48], rbx
0x18004132d  mov     al, [r15+28h]
0x180041331  nop
0x180041332  lea     r14, [r15+8]
0x180041336  test    al, al
0x180041338  jz      short loc_180041360
0x18004133a  mov     ebx, edi
0x18004133c  mov     [rsp+78h+arg_10], rbx
0x180041344  lea     esi, [rdi+1]
0x180041347  lea     rdx, [rsp+78h+arg_10]
0x18004134f  mov     rcx, r14
0x180041352  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180041357  test    al, al
0x180041359  jnz     short loc_180041368
0x18004135b  mov     r13b, dil
0x18004135e  jmp     short loc_18004136B
0x180041360  mov     rbx, [rsp+78h+arg_10]
0x180041368  mov     r13b, 1
0x18004136b  mov     [rsp+78h+arg_18], r14
0x180041373  test    sil, 1
0x180041377  jz      short loc_18004138E
0x180041379  and     esi, 0FFFFFFFEh
0x18004137c  test    rbx, rbx
0x18004137f  jz      short loc_18004138E
0x180041381  lea     rcx, [rsp+78h+arg_10]
0x180041389  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18004138e  test    r13b, r13b
0x180041391  jnz     loc_1800415F9
0x180041397  lea     rdx, [rsp+78h+var_50]
0x18004139c  mov     rcx, r14
0x18004139f  call    ?BaseGlyphFill@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphFill(void)
0x1800413a4  nop
0x1800413a5  or      esi, 2
0x1800413a8  mov     dword ptr [rsp+78h+arg_10], esi
0x1800413af  cmp     [rax], rdi
0x1800413b2  jz      short loc_1800413CC
0x1800413b4  lea     rdx, [rsp+78h+var_58]
0x1800413b9  mov     rcx, r14
0x1800413bc  call    ?BaseGlyphOutline@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphOutline(void)
0x1800413c1  or      esi, 4
0x1800413c4  cmp     [rax], rdi
0x1800413c7  mov     bl, dil
0x1800413ca  jnz     short loc_1800413CE
0x1800413cc  mov     bl, 1
0x1800413ce  test    sil, 4
0x1800413d2  jz      short loc_1800413E2
0x1800413d4  and     esi, 0FFFFFFFBh
0x1800413d7  lea     rcx, [rsp+78h+var_58]
0x1800413dc  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800413e1  nop
0x1800413e2  test    sil, 2
0x1800413e6  jz      short loc_1800413F2
0x1800413e8  lea     rcx, [rsp+78h+var_50]
0x1800413ed  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800413f2  test    bl, bl
0x1800413f4  jz      loc_180041490
0x1800413fa  mov     [rsp+78h+arg_10], rdi
0x180041402  lea     rdx, [rsp+78h+arg_10]
0x18004140a  mov     rcx, r15
0x18004140d  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180041412  test    al, al
0x180041414  jnz     short loc_180041490
0x180041416  lea     rdx, [rsp+78h+arg_10]
0x18004141e  mov     rcx, r15
0x180041421  call    ?BaseGlyphOutline@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphOutline(void)
0x180041426  mov     rdx, rax
0x180041429  mov     rcx, r14
0x18004142c  call    ??4BatteryIconData@PowerUX@UI@Internal@Windows@winrt@@QEAAAEAU012345@$$QEAU012345@@Z; winrt::Windows::Internal::UI::PowerUX::BatteryIconData::operator=(winrt::Windows::Internal::UI::PowerUX::BatteryIconData &&)
0x180041431  lea     rcx, [rsp+78h+arg_10]; this
0x180041439  call    ??1IInspectable@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IInspectable::~IInspectable(void)
0x18004143e  lea     rdx, [rsp+78h+arg_10]
0x180041446  mov     rcx, r15
0x180041449  call    ?BaseGlyphFill@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphFill(void)
0x18004144e  lea     rcx, [r15+10h]
0x180041452  mov     rdx, rax
0x180041455  call    ??4BatteryIconData@PowerUX@UI@Internal@Windows@winrt@@QEAAAEAU012345@$$QEAU012345@@Z; winrt::Windows::Internal::UI::PowerUX::BatteryIconData::operator=(winrt::Windows::Internal::UI::PowerUX::BatteryIconData &&)
0x18004145a  lea     rcx, [rsp+78h+arg_10]; this
0x180041462  call    ??1IInspectable@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IInspectable::~IInspectable(void)
0x180041467  lea     rcx, aCbatteryiconGe; "[CBatteryIcon] GetBatteryIconData: refr"...
0x18004146e  call    ?DebugTrace@PowerAndBatteryHelper@DataModel@SystemSettings@@SAXPEBGZZ; SystemSettings::DataModel::PowerAndBatteryHelper::DebugTrace(ushort const *,...)
0x180041473  nop
0x180041474  jmp     short loc_180041490
0x180041476  xor     edi, edi
0x180041478  mov     r15, [rsp+78h+arg_0]
0x180041480  mov     r12, [rsp+78h+arg_8]
0x180041488  mov     r14, [rsp+78h+arg_18]
0x180041490  mov     rcx, r14
0x180041493  call    ?BatteryPercentage@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BatteryPercentage(void)
0x180041498  mov     [r12], eax
0x18004149c  lea     rcx, [r15+8]
0x1800414a0  lea     rdx, [rsp+78h+arg_0]
0x1800414a8  call    ?AltText@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::AltText(void)
0x1800414ad  lea     rcx, [r12+8]
0x1800414b2  cmp     rcx, rax
0x1800414b5  jz      short loc_1800414C2
0x1800414b7  mov     rdx, [rax]
0x1800414ba  mov     [rax], rdi
0x1800414bd  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x1800414c2  lea     rcx, [rsp+78h+arg_0]
0x1800414ca  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800414cf  mov     rcx, r14
0x1800414d2  call    ?IsBatteryPresent@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::IsBatteryPresent(void)
0x1800414d7  mov     [r12+34h], al
0x1800414dc  lea     rcx, [r15+8]
0x1800414e0  lea     rdx, [rsp+78h+arg_0]
0x1800414e8  call    ?BaseGlyphFill@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphFill(void)
0x1800414ed  lea     r13, [r12+10h]
0x1800414f2  cmp     r13, rax
0x1800414f5  jz      short loc_180041505
0x1800414f7  mov     rdx, [rax]
0x1800414fa  mov     [rax], rdi
0x1800414fd  mov     rcx, r13
0x180041500  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x180041505  lea     rcx, [rsp+78h+arg_0]
0x18004150d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180041512  lea     rcx, [r15+8]
0x180041516  lea     rdx, [rsp+78h+arg_0]
0x18004151e  call    ?BaseGlyphOutline@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphOutline(void)
0x180041523  lea     rsi, [r12+18h]
0x180041528  cmp     rsi, rax
0x18004152b  jz      short loc_18004153B
0x18004152d  mov     rdx, [rax]
0x180041530  mov     [rax], rdi
0x180041533  mov     rcx, rsi
0x180041536  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18004153b  lea     rcx, [rsp+78h+arg_0]
0x180041543  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180041548  mov     rcx, r14
0x18004154b  call    ?BatteryFillColor@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BatteryFillColor(void)
0x180041550  mov     [r12+30h], eax
0x180041555  mov     [rsp+78h+arg_0], rdi
0x18004155d  add     r15, 10h
0x180041561  lea     rbx, [r12+20h]
0x180041566  lea     rdx, [rsp+78h+arg_0]
0x18004156e  mov     rcx, r15
0x180041571  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180041576  test    al, al
0x180041578  jnz     short loc_1800415DE
0x18004157a  lea     rdx, [rsp+78h+arg_0]
0x180041582  mov     rcx, r15
0x180041585  call    ?BaseGlyphFill@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphFill(void)
0x18004158a  cmp     rbx, rax
0x18004158d  jz      short loc_18004159D
0x18004158f  mov     rdx, [rax]
0x180041592  mov     [rax], rdi
0x180041595  mov     rcx, rbx
0x180041598  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18004159d  lea     rcx, [rsp+78h+arg_0]
0x1800415a5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800415aa  lea     rdx, [rsp+78h+arg_0]
0x1800415b2  mov     rcx, r15
0x1800415b5  call    ?BaseGlyphOutline@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphOutline(void)
0x1800415ba  lea     rcx, [r12+28h]
0x1800415bf  cmp     rcx, rax
0x1800415c2  jz      short loc_1800415CF
0x1800415c4  mov     rdx, [rax]
0x1800415c7  mov     [rax], rdi
0x1800415ca  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x1800415cf  lea     rcx, [rsp+78h+arg_0]
0x1800415d7  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800415dc  jmp     short loc_1800415F6
0x1800415de  mov     rdx, r13
0x1800415e1  mov     rcx, rbx
0x1800415e4  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x1800415e9  lea     rcx, [r12+28h]
0x1800415ee  mov     rdx, rsi
0x1800415f1  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x1800415f6  mov     dil, 1
0x1800415f9  lea     rcx, [rsp+78h+var_48]
0x1800415fe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180041603  mov     al, dil
0x180041606  add     rsp, 40h
0x18004160a  pop     r15
0x18004160c  pop     r14
0x18004160e  pop     r13
0x180041610  pop     r12
0x180041612  pop     rdi
0x180041613  pop     rsi
0x180041614  pop     rbx
0x180041615  retn
```
