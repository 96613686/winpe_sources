# CAccountsSettingsPane::CompleteRequestSettings(Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs *)

- ea: `0x1800263b8`
- end: `0x1800264bc`
- name: `?CompleteRequestSettings@CAccountsSettingsPane@@QEAAJPEAUIAccountsSettingsPaneCommandsRequestedEventArgs@ApplicationSettings@UI@Windows@@@Z`
- size: `260`
- prototype: `__int64 __fastcall(CAccountsSettingsPane *__hidden this, struct Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036c88`

## callees

- `0x180006eac`
- `0x18000c14c`
- `0x1800263b8`
- `0x18003073c`
- `0x1800308a4`
- `0x180030a0c`
- `0x180030b74`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800263ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800263ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800263e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800263e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAccountsSettingsPane::CompleteRequestSettings(
        CAccountsSettingsPane *this,
        struct Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs *a2)
{
  char *v4; // rbx
  __int64 (__fastcall *v5)(struct Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs *, char *); // rdi
  int v6; // eax
  int v7; // ebx
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char *v12; // [rsp+50h] [rbp+8h] BYREF

  v4 = (char *)this + 48;
  AcquireSRWLockExclusive((PSRWLOCK)this + 6);
  v12 = v4;
  v5 = *(__int64 (__fastcall **)(struct Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs *, char *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  v6 = v5(a2, (char *)this + 56);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x497,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
      (const char *)(unsigned int)v6,
      v10);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
    return (unsigned int)v7;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  v7 = CAccountsSettingsPane::_TransferWebAccountProviders(this, a2);
  if ( v7 < 0 )
  {
    v9 = 1177;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
      (const char *)(unsigned int)v7,
      v10);
    return (unsigned int)v7;
  }
  v7 = CAccountsSettingsPane::_TransferWebAccounts(this, a2);
  if ( v7 < 0 )
  {
    v9 = 1178;
    goto LABEL_6;
  }
  v7 = CAccountsSettingsPane::_TransferCredentials(this, a2);
  if ( v7 < 0 )
  {
    v9 = 1179;
    goto LABEL_6;
  }
  v7 = CAccountsSettingsPane::_TransferSettingCommands(this, a2);
  if ( v7 < 0 )
  {
    v9 = 1180;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x1800263b8  push    rbx
0x1800263ba  push    rbp
0x1800263bb  push    rsi
0x1800263bc  push    rdi
0x1800263bd  sub     rsp, 28h
0x1800263c1  mov     rsi, rdx
0x1800263c4  mov     rbp, rcx
0x1800263c7  lea     rbx, [rcx+30h]
0x1800263cb  mov     rcx, rbx; SRWLock
0x1800263ce  call    cs:__imp_AcquireSRWLockExclusive
0x1800263d4  mov     [rsp+48h+arg_0], rbx
0x1800263d9  mov     rax, [rsi]
0x1800263dc  mov     rdi, [rax+50h]
0x1800263e0  lea     rbx, [rbp+38h]
0x1800263e4  mov     rcx, [rbx]; string
0x1800263e7  call    cs:__imp_WindowsDeleteString
0x1800263ed  mov     qword ptr [rbx], 0
0x1800263f4  mov     rdx, rbx
0x1800263f7  mov     rcx, rsi
0x1800263fa  mov     rax, rdi
0x1800263fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026402  mov     ebx, eax
0x180026404  test    eax, eax
0x180026406  jns     short loc_180026433
0x180026408  mov     rcx, [rsp+48h]; this
0x18002640d  mov     r9d, eax; char *
0x180026410  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x180026417  mov     edx, 497h; void *
0x18002641c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026421  nop
0x180026422  lea     rcx, [rsp+48h+arg_0]
0x180026427  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002642c  mov     eax, ebx
0x18002642e  jmp     loc_1800264B3
0x180026433  lea     rcx, [rsp+48h+arg_0]
0x180026438  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002643d  mov     rdx, rsi; struct Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs *
0x180026440  mov     rcx, rbp; this
0x180026443  call    ?_TransferWebAccountProviders@CAccountsSettingsPane@@AEAAJPEAUIAccountsSettingsPaneCommandsRequestedEventArgs@ApplicationSettings@UI@Windows@@@Z; CAccountsSettingsPane::_TransferWebAccountProviders(Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs *)
0x180026448  mov     ebx, eax
0x18002644a  test    eax, eax
0x18002644c  jns     short loc_180026469
0x18002644e  mov     edx, 499h; void *
0x180026453  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x18002645a  mov     r9d, ebx; char *
0x18002645d  mov     rcx, [rsp+48h]; this
0x180026462  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026467  jmp     short loc_18002642C
0x180026469  mov     rdx, rsi; struct Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs *
0x18002646c  mov     rcx, rbp; this
0x18002646f  call    ?_TransferWebAccounts@CAccountsSettingsPane@@AEAAJPEAUIAccountsSettingsPaneCommandsRequestedEventArgs@ApplicationSettings@UI@Windows@@@Z; CAccountsSettingsPane::_TransferWebAccounts(Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs *)
0x180026474  mov     ebx, eax
0x180026476  test    eax, eax
0x180026478  jns     short loc_180026481
0x18002647a  mov     edx, 49Ah
0x18002647f  jmp     short loc_180026453
0x180026481  mov     rdx, rsi; struct Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs *
0x180026484  mov     rcx, rbp; this
0x180026487  call    ?_TransferCredentials@CAccountsSettingsPane@@AEAAJPEAUIAccountsSettingsPaneCommandsRequestedEventArgs@ApplicationSettings@UI@Windows@@@Z; CAccountsSettingsPane::_TransferCredentials(Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs *)
0x18002648c  mov     ebx, eax
0x18002648e  test    eax, eax
0x180026490  jns     short loc_180026499
0x180026492  mov     edx, 49Bh
0x180026497  jmp     short loc_180026453
0x180026499  mov     rdx, rsi; struct Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs *
0x18002649c  mov     rcx, rbp; this
0x18002649f  call    ?_TransferSettingCommands@CAccountsSettingsPane@@AEAAJPEAUIAccountsSettingsPaneCommandsRequestedEventArgs@ApplicationSettings@UI@Windows@@@Z; CAccountsSettingsPane::_TransferSettingCommands(Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs *)
0x1800264a4  mov     ebx, eax
0x1800264a6  test    eax, eax
0x1800264a8  jns     short loc_1800264B1
0x1800264aa  mov     edx, 49Ch
0x1800264af  jmp     short loc_180026453
0x1800264b1  xor     eax, eax
0x1800264b3  add     rsp, 28h
0x1800264b7  pop     rdi
0x1800264b8  pop     rsi
0x1800264b9  pop     rbp
0x1800264ba  pop     rbx
0x1800264bb  retn
```
