# SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetBGCapability(HSTRING__ *,SystemSettings::BatteryUsageHandlers::BackgroundCapability *)

- ea: `0x1800485c8`
- end: `0x180048763`
- name: `?GetBGCapability@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAUHSTRING__@@PEAW4BackgroundCapability@23@@Z`
- size: `411`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *__hidden this, HSTRING, enum SystemSettings::BatteryUsageHandlers::BackgroundCapability *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004834c`
- `0x180048520`

## callees

- `0x18000a13c`
- `0x18000fa10`
- `0x18002e2b0`
- `0x1800485c8`
- `0x18004896c`
- `0x1800489f4`
- `0x180049164`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004868a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004868a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048720`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048730`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048720`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048730`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800486bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800486bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetBGCapability(
        SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *this,
        HSTRING a2,
        enum SystemSettings::BatteryUsageHandlers::BackgroundCapability *a3)
{
  int InitResult; // eax
  int v6; // ebx
  SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton *v8; // rcx
  int CurrentUserSidString; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, unsigned __int16 *, PCWSTR, int *); // rbx
  PCWSTR StringRawBuffer; // rax
  int v13; // [rsp+20h] [rbp-30h]
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-18h] BYREF
  __int64 v16; // [rsp+40h] [rbp-10h]
  __int64 v17; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v19; // [rsp+70h] [rbp+20h] BYREF
  int v20; // [rsp+74h] [rbp+24h]
  HSTRING v21; // [rsp+78h] [rbp+28h] BYREF
  HSTRING string; // [rsp+88h] [rbp+38h] BYREF

  v21 = a2;
  v20 = HIDWORD(this);
  v19 = 0;
  InitResult = SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BackgroundCapability>::GetInitResult();
  v6 = InitResult;
  if ( InitResult >= 0 )
  {
    if ( !a2 )
    {
      *(_DWORD *)a3 = 0;
      return 2147500037LL;
    }
    v15 = 0;
    v16 = 0;
    v17 = 0;
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&v15);
    v16 = -1;
    v17 = -1;
    CurrentUserSidString = SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSidString(
                             v8,
                             &v15);
    v6 = CurrentUserSidString;
    if ( CurrentUserSidString >= 0 )
    {
      EnterCriticalSection(&stru_18007A0B0);
      v14 = &stru_18007A0B0;
      string = 0;
      Microsoft::WRL::Wrappers::HString::Set(&string, &v21);
      v10 = *((_QWORD *)&xmmword_18007A0A0 + 1);
      v11 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, PCWSTR, int *))(**((_QWORD **)&xmmword_18007A0A0 + 1)
                                                                                 + 40LL);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v6 = v11(v10, v15, StringRawBuffer, &v19);
      if ( v6 >= 0 )
      {
        Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v14);
        if ( (v19 & 0x20) != 0 )
        {
          *(_DWORD *)a3 = 1;
        }
        else if ( (v19 & 2) != 0 )
        {
          *(_DWORD *)a3 = 3;
        }
        else if ( (v19 & 0x10) != 0 )
        {
          *(_DWORD *)a3 = 4;
        }
        else
        {
          *(_DWORD *)a3 = (v19 & 0x32) == 0 ? 2 : 0;
        }
      }
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v14);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x255,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\backgroundcapabilitysingleton.cpp",
        (const char *)(unsigned int)CurrentUserSidString,
        v13);
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&v15);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\backgroundcapabilitysingleton.cpp",
      (const char *)(unsigned int)InitResult,
      v13);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800485c8  mov     [rsp-18h+arg_10], rbx
0x1800485cd  mov     [rsp-18h+arg_8], rdx
0x1800485d2  mov     [rsp-18h+arg_0], rcx
0x1800485d7  push    rbp
0x1800485d8  push    rsi
0x1800485d9  push    rdi
0x1800485da  mov     rbp, rsp
0x1800485dd  sub     rsp, 50h
0x1800485e1  mov     rsi, r8
0x1800485e4  mov     rdi, rdx
0x1800485e7  mov     dword ptr [rbp+arg_0], 0
0x1800485ee  call    ?GetInitResult@?$CSingletonHelper@W4BackgroundCapability@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAJXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BackgroundCapability>::GetInitResult(void)
0x1800485f3  mov     ebx, eax
0x1800485f5  test    eax, eax
0x1800485f7  jns     short loc_180048616
0x1800485f9  mov     rcx, [rbp+18h]; this
0x1800485fd  mov     r9d, eax; char *
0x180048600  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\coresettinghandlers"...
0x180048607  mov     edx, 248h; void *
0x18004860c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048611  jmp     loc_180048751
0x180048616  test    rdi, rdi
0x180048619  jnz     short loc_180048627
0x18004861b  mov     [rsi], edi
0x18004861d  mov     eax, 80004005h
0x180048622  jmp     loc_180048753
0x180048627  mov     [rbp+var_18], 0
0x18004862f  mov     [rbp+var_10], 0
0x180048637  mov     [rbp+var_8], 0
0x18004863f  lea     rcx, [rbp+var_18]
0x180048643  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180048648  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004864c  mov     [rbp+var_10], rax
0x180048650  mov     [rbp+var_8], rax
0x180048654  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x180048658  call    ?GetCurrentUserSidString@BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAPEAG@Z; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton::GetCurrentUserSidString(ushort * *)
0x18004865d  mov     ebx, eax
0x18004865f  test    eax, eax
0x180048661  jns     short loc_180048680
0x180048663  mov     rcx, [rbp+18h]; this
0x180048667  mov     r9d, eax; char *
0x18004866a  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\coresettinghandlers"...
0x180048671  mov     edx, 255h; void *
0x180048676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004867b  jmp     loc_180048748
0x180048680  lea     rbx, stru_18007A0B0
0x180048687  mov     rcx, rbx; lpCriticalSection
0x18004868a  call    cs:__imp_EnterCriticalSection
0x180048690  mov     [rbp+var_20], rbx
0x180048694  mov     [rbp+string], 0
0x18004869c  lea     rdx, [rbp+arg_8]; HSTRING *
0x1800486a0  lea     rcx, [rbp+string]; newString
0x1800486a4  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800486a9  mov     rdi, qword ptr cs:xmmword_18007A0A0+8
0x1800486b0  mov     rax, [rdi]
0x1800486b3  mov     rbx, [rax+28h]
0x1800486b7  xor     edx, edx; length
0x1800486b9  mov     rcx, [rbp+string]; string
0x1800486bd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800486c3  lea     r9, [rbp+arg_0]
0x1800486c7  mov     r8, rax
0x1800486ca  mov     rdx, [rbp+var_18]
0x1800486ce  mov     rcx, rdi
0x1800486d1  mov     rax, rbx
0x1800486d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486d9  mov     ebx, eax
0x1800486db  test    eax, eax
0x1800486dd  js      short loc_18004871C
0x1800486df  lea     rcx, [rbp+var_20]; this
0x1800486e3  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800486e8  mov     eax, dword ptr [rbp+arg_0]
0x1800486eb  test    al, 20h
0x1800486ed  jz      short loc_1800486F7
0x1800486ef  mov     dword ptr [rsi], 1
0x1800486f5  jmp     short loc_18004871C
0x1800486f7  test    al, 2
0x1800486f9  jz      short loc_180048703
0x1800486fb  mov     dword ptr [rsi], 3
0x180048701  jmp     short loc_18004871C
0x180048703  test    al, 10h
0x180048705  jz      short loc_18004870F
0x180048707  mov     dword ptr [rsi], 4
0x18004870d  jmp     short loc_18004871C
0x18004870f  and     al, 32h
0x180048711  neg     al
0x180048713  sbb     eax, eax
0x180048715  not     eax
0x180048717  and     eax, 2
0x18004871a  mov     [rsi], eax
0x18004871c  mov     rcx, [rbp+string]; string
0x180048720  call    cs:__imp_WindowsDeleteString
0x180048726  mov     [rbp+string], 0
0x18004872e  xor     ecx, ecx; string
0x180048730  call    cs:__imp_WindowsDeleteString
0x180048736  mov     [rbp+string], 0
0x18004873e  lea     rcx, [rbp+var_20]; this
0x180048742  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180048747  nop
0x180048748  lea     rcx, [rbp+var_18]
0x18004874c  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180048751  mov     eax, ebx
0x180048753  mov     rbx, [rsp+50h+arg_10]
0x18004875b  add     rsp, 50h
0x18004875f  pop     rdi
0x180048760  pop     rsi
0x180048761  pop     rbp
0x180048762  retn
```
