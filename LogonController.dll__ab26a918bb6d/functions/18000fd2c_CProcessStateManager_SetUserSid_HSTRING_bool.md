# CProcessStateManager::_SetUserSid(HSTRING__ *,bool)

- ea: `0x18000fd2c`
- end: `0x18000ffe0`
- name: `?_SetUserSid@CProcessStateManager@@AEAAJPEAUHSTRING__@@_N@Z`
- size: `692`
- prototype: `int(CProcessStateManager *__hidden this, HSTRING, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001aad0`
- `0x18007f580`

## callees

- `0x18000f730`
- `0x18000fd2c`
- `0x18000fff0`
- `0x1800113b4`
- `0x180011ae0`
- `0x1800268e0`
- `0x1800315a0`
- `0x180033e90`
- `0x18005d488`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18000fded`
- `KERNEL32!CompareStringOrdinal` at `0x18000fded`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fe21`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fe7c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fe21`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fe7c`
- `KERNEL32!WaitForSingleObject` at `0x18000fd75`
- `KERNEL32!WaitForSingleObject` at `0x18000fd75`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fd85`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fe5a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fd85`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fe5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ff4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ff4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000fda2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000fda2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fdc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fdd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ff1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fdc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fdd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ff1d`

## string_xrefs

- `0x18000ff26`: `SelectedUserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CProcessStateManager::_SetUserSid(CProcessStateManager *this, HSTRING a2, char a3)
{
  int v6; // r13d
  char v7; // r15
  HSTRING v8; // rcx
  const WCHAR *v9; // rbx
  const WCHAR *v10; // rax
  char v11; // al
  int v12; // esi
  __int64 v13; // rbx
  volatile int *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r8
  const unsigned __int16 *StringRawBuffer; // rax
  int v19; // ebx
  __int64 v20; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-68h]
  _QWORD v22[11]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  int v24; // [rsp+90h] [rbp+8h]
  HSTRING v25; // [rsp+98h] [rbp+10h] BYREF
  char v26; // [rsp+A0h] [rbp+18h]
  char *v27; // [rsp+A8h] [rbp+20h] BYREF

  v25 = a2;
  v6 = *((_DWORD *)this + 111);
  v24 = *((_DWORD *)this + 112);
  v26 = *((_BYTE *)this + 452);
  WaitForSingleObject(*((HANDLE *)this + 21), 0xFFFFFFFF);
  AcquireSRWLockExclusive((PSRWLOCK)this + 52);
  v27 = (char *)this + 416;
  v7 = 0;
  if ( !a2 || WindowsIsStringEmpty(a2) )
  {
    WindowsDeleteString(*((HSTRING *)this + 53));
    *((_QWORD *)this + 53) = 0;
    v11 = 0;
  }
  else
  {
    v8 = (HSTRING)*((_QWORD *)this + 53);
    if ( v8
      && (v9 = WindowsGetStringRawBuffer(v8, 0),
          v10 = WindowsGetStringRawBuffer(a2, 0),
          CompareStringOrdinal(v10, -1, v9, -1, 1) == 2) )
    {
      v11 = 1;
    }
    else
    {
      v7 = 1;
      if ( (int)Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 53, &v25) >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 53), 0);
        SHRegSetString(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
          L"SelectedUserSID",
          StringRawBuffer);
      }
      v11 = 1;
    }
  }
  if ( a3 )
  {
    *((_BYTE *)this + 440) = v11;
    *((_BYTE *)this + 441) = 1;
  }
  if ( v7 )
    CProcessStateManager::_RefreshActiveUserSettings(this);
  if ( this != (CProcessStateManager *)-416LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 52);
  if ( v6 != *((_DWORD *)this + 111) )
  {
    v27 = 0;
    v25 = (HSTRING)this;
    v12 = 0;
    v13 = 0;
    AcquireSRWLockExclusive((PSRWLOCK)this + 38);
    v15 = *((_QWORD *)this + 37);
    if ( v15 )
    {
      Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v15 + 12), v14);
      v13 = v16;
    }
    if ( this != (CProcessStateManager *)-304LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 38);
    if ( v13 )
    {
      v22[0] = &v25;
      v22[1] = &v27;
      v12 = Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_e57e08407f09c4c5aa68ee8233b09626_,Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::IUserSettingManager *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>(
              v22,
              v13,
              (char *)this + 296);
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v13);
    }
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x874,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
        (const char *)(unsigned int)v12,
        bIgnoreCase);
      return (unsigned int)v12;
    }
  }
  if ( v24 != *((_DWORD *)this + 112) )
  {
    v19 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::IUserSettingManager *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<CProcessStateManager *,std::nullptr_t>(
            (char *)this + 320,
            this);
    if ( v19 < 0 )
    {
      v20 = 2169;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
        (const char *)(unsigned int)v19,
        bIgnoreCase);
      return (unsigned int)v19;
    }
  }
  if ( v26 != *((_BYTE *)this + 452) )
  {
    v19 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::IUserSettingManager *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<CProcessStateManager *,std::nullptr_t>(
            (char *)this + 344,
            this);
    if ( v19 < 0 )
    {
      v20 = 2174;
      goto LABEL_29;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000fd2c  mov     [rsp+arg_8], rdx
0x18000fd31  push    rbx
0x18000fd32  push    rbp
0x18000fd33  push    rsi
0x18000fd34  push    rdi
0x18000fd35  push    r12
0x18000fd37  push    r13
0x18000fd39  push    r14
0x18000fd3b  push    r15
0x18000fd3d  sub     rsp, 48h
0x18000fd41  mov     r12b, r8b
0x18000fd44  mov     rbp, rdx
0x18000fd47  mov     rdi, rcx
0x18000fd4a  mov     r13d, [rcx+1BCh]
0x18000fd51  mov     eax, [rcx+1C0h]
0x18000fd57  mov     [rsp+88h+arg_0], eax
0x18000fd5e  mov     al, [rcx+1C4h]
0x18000fd64  mov     [rsp+88h+arg_10], al
0x18000fd6b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000fd6e  mov     rcx, [rcx+0A8h]; hHandle
0x18000fd75  call    cs:__imp_WaitForSingleObject
0x18000fd7b  lea     rsi, [rdi+1A0h]
0x18000fd82  mov     rcx, rsi; SRWLock
0x18000fd85  call    cs:__imp_AcquireSRWLockExclusive
0x18000fd8b  mov     [rsp+88h+arg_18], rsi
0x18000fd93  xor     r15b, r15b
0x18000fd96  test    rbp, rbp
0x18000fd99  jz      loc_18000FF48
0x18000fd9f  mov     rcx, rbp; string
0x18000fda2  call    cs:__imp_WindowsIsStringEmpty
0x18000fda8  test    eax, eax
0x18000fdaa  jnz     loc_18000FF48
0x18000fdb0  lea     r14, [rdi+1A8h]
0x18000fdb7  mov     rcx, [r14]; string
0x18000fdba  test    rcx, rcx
0x18000fdbd  jz      loc_18000FF01
0x18000fdc3  xor     edx, edx; length
0x18000fdc5  call    cs:__imp_WindowsGetStringRawBuffer
0x18000fdcb  mov     rbx, rax
0x18000fdce  xor     edx, edx; length
0x18000fdd0  mov     rcx, rbp; string
0x18000fdd3  call    cs:__imp_WindowsGetStringRawBuffer
0x18000fdd9  mov     [rsp+88h+bIgnoreCase], 1; int
0x18000fde1  or      edx, 0FFFFFFFFh; cchCount1
0x18000fde4  mov     r9d, edx; cchCount2
0x18000fde7  mov     r8, rbx; lpString2
0x18000fdea  mov     rcx, rax; lpString1
0x18000fded  call    cs:__imp_CompareStringOrdinal
0x18000fdf3  cmp     eax, 2
0x18000fdf6  jnz     loc_18000FF01
0x18000fdfc  mov     al, 1
0x18000fdfe  test    r12b, r12b
0x18000fe01  jz      short loc_18000FE10
0x18000fe03  mov     [rdi+1B8h], al
0x18000fe09  mov     byte ptr [rdi+1B9h], 1
0x18000fe10  test    r15b, r15b
0x18000fe13  jnz     loc_18000FEF4
0x18000fe19  test    rsi, rsi
0x18000fe1c  jz      short loc_18000FE27
0x18000fe1e  mov     rcx, rsi; SRWLock
0x18000fe21  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fe27  cmp     r13d, [rdi+1BCh]
0x18000fe2e  jz      loc_18000FF67
0x18000fe34  lea     r14, [rdi+128h]
0x18000fe3b  mov     [rsp+88h+arg_18], 0
0x18000fe47  mov     [rsp+88h+arg_8], rdi
0x18000fe4f  xor     esi, esi
0x18000fe51  xor     ebx, ebx
0x18000fe53  lea     rbp, [r14+8]
0x18000fe57  mov     rcx, rbp; SRWLock
0x18000fe5a  call    cs:__imp_AcquireSRWLockExclusive
0x18000fe60  mov     r8, [r14]
0x18000fe63  test    r8, r8
0x18000fe66  jz      short loc_18000FE74
0x18000fe68  lea     rcx, [r8+0Ch]; this
0x18000fe6c  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18000fe71  mov     rbx, r8
0x18000fe74  test    rbp, rbp
0x18000fe77  jz      short loc_18000FE82
0x18000fe79  mov     rcx, rbp; SRWLock
0x18000fe7c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fe82  test    rbx, rbx
0x18000fe85  jnz     short loc_18000FEBE
0x18000fe87  test    esi, esi
0x18000fe89  jns     loc_18000FF67
0x18000fe8f  mov     rcx, [rsp+88h]; this
0x18000fe97  mov     r9d, esi; char *
0x18000fe9a  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x18000fea1  mov     edx, 874h; void *
0x18000fea6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000feab  mov     eax, esi
0x18000fead  add     rsp, 48h
0x18000feb1  pop     r15
0x18000feb3  pop     r14
0x18000feb5  pop     r13
0x18000feb7  pop     r12
0x18000feb9  pop     rdi
0x18000feba  pop     rsi
0x18000febb  pop     rbp
0x18000febc  pop     rbx
0x18000febd  retn
0x18000febe  lea     rax, [rsp+88h+arg_8]
0x18000fec6  mov     [rsp+88h+var_58], rax
0x18000fecb  lea     rax, [rsp+88h+arg_18]
0x18000fed3  mov     [rsp+88h+var_50], rax
0x18000fed8  mov     r8, r14
0x18000fedb  mov     rdx, rbx
0x18000fede  lea     rcx, [rsp+88h+var_58]
0x18000fee3  call    ??$InvokeDelegates@V_lambda_e57e08407f09c4c5aa68ee8233b09626_@@U?$ITypedEventHandler@PEAUIUserSettingManager@Controller@Logon@UI@Internal@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_e57e08407f09c4c5aa68ee8233b09626_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAUIUserSettingManager@Controller@Logon@UI@Internal@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_e57e08407f09c4c5aa68ee8233b09626_,Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::IUserSettingManager *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_e57e08407f09c4c5aa68ee8233b09626_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::IUserSettingManager *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x18000fee8  mov     esi, eax
0x18000feea  mov     rcx, rbx
0x18000feed  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000fef2  jmp     short loc_18000FE87
0x18000fef4  mov     rcx, rdi; this
0x18000fef7  call    ?_RefreshActiveUserSettings@CProcessStateManager@@AEAAXXZ; CProcessStateManager::_RefreshActiveUserSettings(void)
0x18000fefc  jmp     loc_18000FE19
0x18000ff01  mov     r15b, 1
0x18000ff04  lea     rdx, [rsp+88h+arg_8]; HSTRING *
0x18000ff0c  mov     rcx, r14; newString
0x18000ff0f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18000ff14  test    eax, eax
0x18000ff16  js      short loc_18000FF40
0x18000ff18  xor     edx, edx; length
0x18000ff1a  mov     rcx, [r14]; string
0x18000ff1d  call    cs:__imp_WindowsGetStringRawBuffer
0x18000ff23  mov     r9, rax; unsigned __int16 *
0x18000ff26  lea     r8, aSelectedusersi; "SelectedUserSID"
0x18000ff2d  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000ff34  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ff3b  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18000ff40  mov     al, r15b
0x18000ff43  jmp     loc_18000FDFE
0x18000ff48  mov     rcx, [rdi+1A8h]; string
0x18000ff4f  call    cs:__imp_WindowsDeleteString
0x18000ff55  mov     qword ptr [rdi+1A8h], 0
0x18000ff60  xor     al, al
0x18000ff62  jmp     loc_18000FDFE
0x18000ff67  mov     eax, [rsp+88h+arg_0]
0x18000ff6e  cmp     eax, [rdi+1C0h]
0x18000ff74  jz      short loc_18000FFB5
0x18000ff76  lea     rcx, [rdi+140h]
0x18000ff7d  mov     rdx, rdi
0x18000ff80  call    ??$InvokeAll@PEAVCProcessStateManager@@$$T@?$EventSource@U?$ITypedEventHandler@PEAUIUserSettingManager@Controller@Logon@UI@Internal@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAVCProcessStateManager@@$$T@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::IUserSettingManager *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<CProcessStateManager *,std::nullptr_t>(CProcessStateManager *,std::nullptr_t)
0x18000ff85  mov     ebx, eax
0x18000ff87  test    eax, eax
0x18000ff89  jns     short loc_18000FFB5
0x18000ff8b  mov     edx, 879h
0x18000ff90  jmp     short loc_18000FF97
0x18000ff92  mov     edx, 87Eh; void *
0x18000ff97  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x18000ff9e  mov     r9d, ebx; char *
0x18000ffa1  mov     rcx, [rsp+88h]; this
0x18000ffa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ffae  mov     eax, ebx
0x18000ffb0  jmp     loc_18000FEAD
0x18000ffb5  mov     al, [rsp+88h+arg_10]
0x18000ffbc  cmp     al, [rdi+1C4h]
0x18000ffc2  jz      short loc_18000FFD9
0x18000ffc4  lea     rcx, [rdi+158h]
0x18000ffcb  mov     rdx, rdi
0x18000ffce  call    ??$InvokeAll@PEAVCProcessStateManager@@$$T@?$EventSource@U?$ITypedEventHandler@PEAUIUserSettingManager@Controller@Logon@UI@Internal@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAVCProcessStateManager@@$$T@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::IUserSettingManager *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<CProcessStateManager *,std::nullptr_t>(CProcessStateManager *,std::nullptr_t)
0x18000ffd3  mov     ebx, eax
0x18000ffd5  test    eax, eax
0x18000ffd7  js      short loc_18000FF92
0x18000ffd9  xor     eax, eax
0x18000ffdb  jmp     loc_18000FEAD
```
