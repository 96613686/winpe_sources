# SystemSettings::BatterySaverOneCoreDataModel::CBatteryIcon::Initialize(void)

- ea: `0x180042750`
- end: `0x180042870`
- name: `?Initialize@CBatteryIcon@BatterySaverOneCoreDataModel@SystemSettings@@QEAAJXZ`
- size: `288`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatteryIcon *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180042fa0`

## callees

- `0x18000b508`
- `0x1800144c4`
- `0x180034768`
- `0x180034844`
- `0x18003eb80`
- `0x18003ff8c`
- `0x180040ae0`
- `0x180040b40`
- `0x180040bf4`
- `0x180042750`
- `0x1800457ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800427cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800427cb`

## string_xrefs

- `0x180042771`: `[CBatteryIcon] Already initialized\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatteryIcon::Initialize(RTL_SRWLOCK *this)
{
  unsigned int v2; // esi
  __int64 v4; // rax
  __int64 v5; // rax
  wil *v6; // rcx
  int v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF
  void *v9; // [rsp+50h] [rbp+18h] BYREF
  RTL_SRWLOCK *v10; // [rsp+58h] [rbp+20h] BYREF

  SystemSettings::DataModel::PowerAndBatteryHelper::DebugTrace(L"[CBatteryIcon]::Initialize\n");
  v2 = 0;
  if ( LOBYTE(this[5].Ptr) )
  {
    SystemSettings::DataModel::PowerAndBatteryHelper::DebugTrace(L"[CBatteryIcon] Already initialized\n");
    return 0;
  }
  else
  {
    try
    {
      winrt::Windows::Internal::UI::PowerUX::BatteryIcon::BatteryIcon((winrt::Windows::Internal::UI::PowerUX::BatteryIcon *)&v7);
      winrt::Windows::Internal::UI::PowerUX::BatteryIconEventHandler::BatteryIconEventHandler__lambda_52965d05d5963d2edf54d943d0b40294___(
        &v8,
        this);
      winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIcon<winrt::Windows::Internal::UI::PowerUX::IBatteryIcon>::BatteryIconChangedEvent(
        &v7,
        &v9,
        &v8);
      if ( v8 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v8);
      AcquireSRWLockExclusive(this + 3);
      v10 = this + 3;
      v4 = winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphOutline(
             &v7,
             &v8);
      winrt::Windows::Internal::UI::PowerUX::BatteryIconData::operator=(&this[1], v4);
      winrt::Windows::Foundation::IInspectable::~IInspectable((winrt::Windows::Foundation::IInspectable *)&v8);
      v5 = winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphFill(
             &v7,
             &v8);
      winrt::Windows::Internal::UI::PowerUX::BatteryIconData::operator=(&this[2], v5);
      winrt::Windows::Foundation::IInspectable::~IInspectable((winrt::Windows::Foundation::IInspectable *)&v8);
      winrt::Windows::Internal::UI::PowerUX::BatteryIconData::operator=(this, &v7);
      this[4].Ptr = v9;
      LOBYTE(this[5].Ptr) = 1;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
      SystemSettings::DataModel::PowerAndBatteryHelper::DebugTrace(L"[CBatteryIcon]::Initialize succeeded\n");
      winrt::Windows::Foundation::IInspectable::~IInspectable((winrt::Windows::Foundation::IInspectable *)&v7);
    }
    catch ( ... )
    {
      SystemSettings::DataModel::PowerAndBatteryHelper::DebugTrace(L"[CBatteryIcon]::Initialize FAILED with exception\n");
      return (unsigned int)wil::ResultFromCaughtException(v6);
    }
    return v2;
  }
}

```

## disassembly

```asm
0x180042750  push    rbx
0x180042752  push    rsi
0x180042753  push    rdi
0x180042754  sub     rsp, 20h
0x180042758  mov     rdi, rcx
0x18004275b  lea     rcx, aCbatteryiconIn; "[CBatteryIcon]::Initialize\n"
0x180042762  call    ?DebugTrace@PowerAndBatteryHelper@DataModel@SystemSettings@@SAXPEBGZZ; SystemSettings::DataModel::PowerAndBatteryHelper::DebugTrace(ushort const *,...)
0x180042767  xor     esi, esi
0x180042769  mov     al, [rdi+28h]
0x18004276c  nop
0x18004276d  test    al, al
0x18004276f  jz      short loc_180042784
0x180042771  lea     rcx, aCbatteryiconAl; "[CBatteryIcon] Already initialized\n"
0x180042778  call    ?DebugTrace@PowerAndBatteryHelper@DataModel@SystemSettings@@SAXPEBGZZ; SystemSettings::DataModel::PowerAndBatteryHelper::DebugTrace(ushort const *,...)
0x18004277d  xor     eax, eax
0x18004277f  jmp     loc_180042868
0x180042784  lea     rcx, [rsp+38h+arg_0]; this
0x180042789  call    ??0BatteryIcon@PowerUX@UI@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::UI::PowerUX::BatteryIcon::BatteryIcon(void)
0x18004278e  nop
0x18004278f  mov     rdx, rdi
0x180042792  lea     rcx, [rsp+38h+arg_8]
0x180042797  call    winrt__Windows__Internal__UI__PowerUX__BatteryIconEventHandler__BatteryIconEventHandler__lambda_52965d05d5963d2edf54d943d0b40294___
0x18004279c  nop
0x18004279d  lea     r8, [rsp+38h+arg_8]
0x1800427a2  lea     rdx, [rsp+38h+arg_10]
0x1800427a7  lea     rcx, [rsp+38h+arg_0]
0x1800427ac  call    ?BatteryIconChangedEvent@?$consume_Windows_Internal_UI_PowerUX_IBatteryIcon@UIBatteryIcon@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUBatteryIconEventHandler@PowerUX@UI@Internal@Windows@3@@Z; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIcon<winrt::Windows::Internal::UI::PowerUX::IBatteryIcon>::BatteryIconChangedEvent(winrt::Windows::Internal::UI::PowerUX::BatteryIconEventHandler const &)
0x1800427b1  nop
0x1800427b2  cmp     [rsp+38h+arg_8], 0
0x1800427b8  jz      short loc_1800427C4
0x1800427ba  lea     rcx, [rsp+38h+arg_8]
0x1800427bf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800427c4  lea     rbx, [rdi+18h]
0x1800427c8  mov     rcx, rbx; SRWLock
0x1800427cb  call    cs:__imp_AcquireSRWLockExclusive
0x1800427d1  mov     [rsp+38h+arg_18], rbx
0x1800427d6  lea     rdx, [rsp+38h+arg_8]
0x1800427db  lea     rcx, [rsp+38h+arg_0]
0x1800427e0  call    ?BaseGlyphOutline@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphOutline(void)
0x1800427e5  lea     rcx, [rdi+8]
0x1800427e9  mov     rdx, rax
0x1800427ec  call    ??4BatteryIconData@PowerUX@UI@Internal@Windows@winrt@@QEAAAEAU012345@$$QEAU012345@@Z; winrt::Windows::Internal::UI::PowerUX::BatteryIconData::operator=(winrt::Windows::Internal::UI::PowerUX::BatteryIconData &&)
0x1800427f1  lea     rcx, [rsp+38h+arg_8]; this
0x1800427f6  call    ??1IInspectable@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IInspectable::~IInspectable(void)
0x1800427fb  lea     rdx, [rsp+38h+arg_8]
0x180042800  lea     rcx, [rsp+38h+arg_0]
0x180042805  call    ?BaseGlyphFill@?$consume_Windows_Internal_UI_PowerUX_IBatteryIconData@UIBatteryIconData@PowerUX@UI@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UI_PowerUX_IBatteryIconData<winrt::Windows::Internal::UI::PowerUX::IBatteryIconData>::BaseGlyphFill(void)
0x18004280a  lea     rcx, [rdi+10h]
0x18004280e  mov     rdx, rax
0x180042811  call    ??4BatteryIconData@PowerUX@UI@Internal@Windows@winrt@@QEAAAEAU012345@$$QEAU012345@@Z; winrt::Windows::Internal::UI::PowerUX::BatteryIconData::operator=(winrt::Windows::Internal::UI::PowerUX::BatteryIconData &&)
0x180042816  lea     rcx, [rsp+38h+arg_8]; this
0x18004281b  call    ??1IInspectable@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IInspectable::~IInspectable(void)
0x180042820  lea     rdx, [rsp+38h+arg_0]
0x180042825  mov     rcx, rdi
0x180042828  call    ??4BatteryIconData@PowerUX@UI@Internal@Windows@winrt@@QEAAAEAU012345@$$QEAU012345@@Z; winrt::Windows::Internal::UI::PowerUX::BatteryIconData::operator=(winrt::Windows::Internal::UI::PowerUX::BatteryIconData &&)
0x18004282d  mov     rax, [rsp+38h+arg_10]
0x180042832  mov     [rdi+20h], rax
0x180042836  mov     eax, 1
0x18004283b  xchg    al, [rdi+28h]
0x18004283e  lea     rcx, [rsp+38h+arg_18]
0x180042843  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180042848  lea     rcx, aCbatteryiconIn_0; "[CBatteryIcon]::Initialize succeeded\n"
0x18004284f  call    ?DebugTrace@PowerAndBatteryHelper@DataModel@SystemSettings@@SAXPEBGZZ; SystemSettings::DataModel::PowerAndBatteryHelper::DebugTrace(ushort const *,...)
0x180042854  nop
0x180042855  lea     rcx, [rsp+38h+arg_0]; this
0x18004285a  call    ??1IInspectable@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IInspectable::~IInspectable(void)
0x18004285f  nop
0x180042860  jmp     short loc_180042866
0x180042862  mov     esi, [rsp+38h+arg_0]
0x180042866  mov     eax, esi
0x180042868  add     rsp, 20h
0x18004286c  pop     rdi
0x18004286d  pop     rsi
0x18004286e  pop     rbx
0x18004286f  retn
```
