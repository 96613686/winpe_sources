# SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetAppBackgroundCapable(HSTRING__ *,int *)

- ea: `0x1800483dc`
- end: `0x18004851a`
- name: `?GetAppBackgroundCapable@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@PEAH@Z`
- size: `318`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *__hidden this, HSTRING, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004b8fc`
- `0x18004e11c`
- `0x1800513a4`

## callees

- `0x18000a13c`
- `0x18002e2b0`
- `0x1800483dc`
- `0x18004896c`
- `0x1800489f4`
- `0x180049164`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800484df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800484ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800484df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800484ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800484b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800484b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetAppBackgroundCapable(
        SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *this,
        HSTRING a2,
        int *a3)
{
  int InitResult; // eax
  unsigned int v6; // ebx
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v8; // rcx
  int CurrentUserSidString; // eax
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, unsigned __int16 *, PCWSTR, SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton **); // rbx
  PCWSTR StringRawBuffer; // rax
  int v13; // [rsp+20h] [rbp-30h]
  unsigned __int16 *v14; // [rsp+30h] [rbp-20h] BYREF
  __int64 v15; // [rsp+38h] [rbp-18h]
  __int64 v16; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v18; // [rsp+70h] [rbp+20h] BYREF
  HSTRING v19; // [rsp+78h] [rbp+28h] BYREF
  HSTRING string; // [rsp+88h] [rbp+38h] BYREF

  v19 = a2;
  v18 = this;
  InitResult = SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BackgroundCapability>::GetInitResult();
  v6 = InitResult;
  if ( InitResult >= 0 )
  {
    if ( !a2 )
      return 2147500037LL;
    v14 = 0;
    v15 = 0;
    v16 = 0;
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&v14);
    v15 = -1;
    v16 = -1;
    CurrentUserSidString = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSidString(
                             v8,
                             &v14);
    v6 = CurrentUserSidString;
    if ( CurrentUserSidString >= 0 )
    {
      string = 0;
      Microsoft::WRL::Wrappers::HString::Set(&string, &v19);
      LODWORD(v18) = 0;
      v10 = *((_QWORD *)&xmmword_18007A0A0 + 1);
      v11 = *(int (__fastcall **)(__int64, unsigned __int16 *, PCWSTR, SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton **))(**((_QWORD **)&xmmword_18007A0A0 + 1) + 40LL);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      *a3 = v11(v10, v14, StringRawBuffer, &v18) >= 0;
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      v6 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18B,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\backgroundcapabilitysingleton.cpp",
        (const char *)(unsigned int)CurrentUserSidString,
        v13);
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&v14);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17E,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\backgroundcapabilitysingleton.cpp",
      (const char *)(unsigned int)InitResult,
      v13);
  }
  return v6;
}

```

## disassembly

```asm
0x1800483dc  mov     [rsp-18h+arg_10], rbx
0x1800483e1  mov     [rsp-18h+arg_8], rdx
0x1800483e6  mov     [rsp-18h+arg_0], rcx
0x1800483eb  push    rbp
0x1800483ec  push    rsi
0x1800483ed  push    rdi
0x1800483ee  mov     rbp, rsp
0x1800483f1  sub     rsp, 50h
0x1800483f5  mov     rsi, r8
0x1800483f8  mov     rdi, rdx
0x1800483fb  call    ?GetInitResult@?$CSingletonHelper@W4BackgroundCapability@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAJXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BackgroundCapability>::GetInitResult(void)
0x180048400  mov     ebx, eax
0x180048402  test    eax, eax
0x180048404  jns     short loc_180048423
0x180048406  mov     rcx, [rbp+18h]; this
0x18004840a  mov     r9d, eax; char *
0x18004840d  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\coresettinghandlers"...
0x180048414  mov     edx, 17Eh; void *
0x180048419  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004841e  jmp     loc_180048508
0x180048423  test    rdi, rdi
0x180048426  jnz     short loc_180048432
0x180048428  mov     eax, 80004005h
0x18004842d  jmp     loc_18004850A
0x180048432  mov     [rbp+var_20], 0
0x18004843a  mov     [rbp+var_18], 0
0x180048442  mov     [rbp+var_10], 0
0x18004844a  lea     rcx, [rbp+var_20]
0x18004844e  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180048453  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048457  mov     [rbp+var_18], rax
0x18004845b  mov     [rbp+var_10], rax
0x18004845f  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x180048463  call    ?GetCurrentUserSidString@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAPEAG@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSidString(ushort * *)
0x180048468  mov     ebx, eax
0x18004846a  test    eax, eax
0x18004846c  jns     short loc_180048488
0x18004846e  mov     rcx, [rbp+18h]; this
0x180048472  mov     r9d, eax; char *
0x180048475  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\coresettinghandlers"...
0x18004847c  mov     edx, 18Bh; void *
0x180048481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048486  jmp     short loc_1800484FF
0x180048488  mov     [rbp+string], 0
0x180048490  lea     rdx, [rbp+arg_8]; HSTRING *
0x180048494  lea     rcx, [rbp+string]; newString
0x180048498  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18004849d  mov     dword ptr [rbp+arg_0], 0
0x1800484a4  mov     rdi, qword ptr cs:xmmword_18007A0A0+8
0x1800484ab  mov     rax, [rdi]
0x1800484ae  mov     rbx, [rax+28h]
0x1800484b2  xor     edx, edx; length
0x1800484b4  mov     rcx, [rbp+string]; string
0x1800484b8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800484be  lea     r9, [rbp+arg_0]
0x1800484c2  mov     r8, rax
0x1800484c5  mov     rdx, [rbp+var_20]
0x1800484c9  mov     rcx, rdi
0x1800484cc  mov     rax, rbx
0x1800484cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484d4  not     eax
0x1800484d6  shr     eax, 1Fh
0x1800484d9  mov     [rsi], eax
0x1800484db  mov     rcx, [rbp+string]; string
0x1800484df  call    cs:__imp_WindowsDeleteString
0x1800484e5  mov     [rbp+string], 0
0x1800484ed  xor     ecx, ecx; string
0x1800484ef  call    cs:__imp_WindowsDeleteString
0x1800484f5  mov     [rbp+string], 0
0x1800484fd  xor     ebx, ebx
0x1800484ff  lea     rcx, [rbp+var_20]
0x180048503  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180048508  mov     eax, ebx
0x18004850a  mov     rbx, [rsp+50h+arg_10]
0x180048512  add     rsp, 50h
0x180048516  pop     rdi
0x180048517  pop     rsi
0x180048518  pop     rbp
0x180048519  retn
```
