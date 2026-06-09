# Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::LoadAccountTypes(Windows::Foundation::Collections::IVector<Windows::Internal::ApplicationModel::Sync::IKnownAccountType *> * *)

- ea: `0x18006245c`
- end: `0x18006256c`
- name: `?LoadAccountTypes@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@QEAAJPEAPEAU?$IVector@PEAUIKnownAccountType@Sync@ApplicationModel@Internal@Windows@@@Collections@Foundation@5@@Z`
- size: `272`
- prototype: `__int64 __fastcall(Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c5f8`
- `0x18005e3d4`

## callees

- `0x180006eac`
- `0x180011ffc`
- `0x18005fda4`
- `0x1800613c0`
- `0x18006245c`
- `0x1800633d8`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800624bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800624fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800624bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800624fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062544`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::LoadAccountTypes(
        Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile *this,
        _QWORD *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  int AvailableXmlPath; // eax
  __int64 v8; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+48h] [rbp+28h] BYREF
  __int64 (__fastcall ***v13)(_QWORD, GUID *, _QWORD *); // [rsp+50h] [rbp+30h] BYREF

  *a2 = 0;
  v13 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
  v5 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ApplicationModel::Sync::IKnownAccountType,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::ApplicationModel::Sync::IKnownAccountType *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ApplicationModel::Sync::IKnownAccountType *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ApplicationModel::Sync::IKnownAccountType *>,0>>(
         v4,
         &v13);
  v6 = v5;
  if ( v5 >= 0 )
  {
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    AvailableXmlPath = Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::GetAvailableXmlPath(
                         this,
                         &string);
    v6 = AvailableXmlPath;
    if ( AvailableXmlPath >= 0 )
    {
      if ( string )
        Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::ParseXmlFile(this, string);
      AvailableXmlPath = (**v13)(v13, &GUID_ad2b376e_b876_5958_af36_da9d84fd7189, a2);
      v6 = AvailableXmlPath;
      if ( AvailableXmlPath >= 0 )
      {
        WindowsDeleteString(string);
        v6 = 0;
        goto LABEL_11;
      }
      v8 = 64;
    }
    else
    {
      v8 = 58;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\knownaccounttypesfile.cpp",
      (const char *)(unsigned int)AvailableXmlPath,
      savedregs);
    WindowsDeleteString(string);
LABEL_11:
    string = 0;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x37,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\knownaccounttypesfile.cpp",
    (const char *)(unsigned int)v5,
    savedregs);
LABEL_12:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
  return v6;
}

```

## disassembly

```asm
0x18006245c  mov     [rsp-18h+arg_0], rbx
0x180062461  push    rbp
0x180062462  push    rsi
0x180062463  push    rdi; int
0x180062464  mov     rbp, rsp
0x180062467  sub     rsp, 20h
0x18006246b  mov     rsi, rdx
0x18006246e  mov     rdi, rcx
0x180062471  mov     qword ptr [rdx], 0
0x180062478  mov     [rbp+arg_10], 0
0x180062480  lea     rcx, [rbp+arg_10]
0x180062484  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062489  lea     rdx, [rbp+arg_10]
0x18006248d  call    ??$CreateExternalObjectVector@UIKnownAccountType@Sync@ApplicationModel@Internal@Windows@@V?$AgileVector@PEAUIKnownAccountType@Sync@ApplicationModel@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIKnownAccountType@Sync@ApplicationModel@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIKnownAccountType@Sync@ApplicationModel@Internal@Windows@@@4785@$0A@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIKnownAccountType@Sync@ApplicationModel@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIKnownAccountType@Sync@ApplicationModel@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIKnownAccountType@Sync@ApplicationModel@Internal@Windows@@@4785@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ApplicationModel::Sync::IKnownAccountType,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::ApplicationModel::Sync::IKnownAccountType *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ApplicationModel::Sync::IKnownAccountType *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ApplicationModel::Sync::IKnownAccountType *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::ApplicationModel::Sync::IKnownAccountType *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ApplicationModel::Sync::IKnownAccountType *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ApplicationModel::Sync::IKnownAccountType *>,0> * *)
0x180062492  mov     ebx, eax
0x180062494  test    eax, eax
0x180062496  jns     short loc_1800624B5
0x180062498  mov     rcx, [rbp+18h]; this
0x18006249c  mov     r9d, eax; char *
0x18006249f  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800624a6  mov     edx, 37h ; '7'; void *
0x1800624ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800624b0  jmp     loc_180062554
0x1800624b5  mov     [rbp+string], 0
0x1800624bd  xor     ecx, ecx; string
0x1800624bf  call    cs:__imp_WindowsDeleteString
0x1800624c5  mov     [rbp+string], 0
0x1800624cd  lea     rdx, [rbp+string]; newString
0x1800624d1  mov     rcx, rdi; this
0x1800624d4  call    ?GetAvailableXmlPath@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@AEAAJPEAPEAUHSTRING__@@@Z; Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::GetAvailableXmlPath(HSTRING__ * *)
0x1800624d9  mov     ebx, eax
0x1800624db  test    eax, eax
0x1800624dd  jns     short loc_180062504
0x1800624df  mov     edx, 3Ah ; ':'; void *
0x1800624e4  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800624eb  mov     r9d, eax; char *
0x1800624ee  mov     rcx, [rbp+18h]; this
0x1800624f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800624f7  nop
0x1800624f8  mov     rcx, [rbp+string]; string
0x1800624fc  call    cs:__imp_WindowsDeleteString
0x180062502  jmp     short loc_18006254C
0x180062504  mov     rdx, [rbp+string]; HSTRING
0x180062508  test    rdx, rdx
0x18006250b  jz      short loc_18006251A
0x18006250d  mov     r8, [rbp+arg_10]
0x180062511  mov     rcx, rdi; this
0x180062514  call    ?ParseXmlFile@KnownAccountTypesFile@Sync@ApplicationModel@Internal@Windows@@AEAAJPEAUHSTRING__@@PEAU?$IVector@PEAUIKnownAccountType@Sync@ApplicationModel@Internal@Windows@@@Collections@Foundation@5@@Z; Windows::Internal::ApplicationModel::Sync::KnownAccountTypesFile::ParseXmlFile(HSTRING__ *,Windows::Foundation::Collections::IVector<Windows::Internal::ApplicationModel::Sync::IKnownAccountType *> *)
0x180062519  nop
0x18006251a  mov     rcx, [rbp+arg_10]
0x18006251e  mov     rax, [rcx]
0x180062521  mov     r8, rsi
0x180062524  lea     rdx, _GUID_ad2b376e_b876_5958_af36_da9d84fd7189
0x18006252b  mov     rax, [rax]
0x18006252e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062533  mov     ebx, eax
0x180062535  test    eax, eax
0x180062537  jns     short loc_180062540
0x180062539  mov     edx, 40h ; '@'
0x18006253e  jmp     short loc_1800624E4
0x180062540  mov     rcx, [rbp+string]; string
0x180062544  call    cs:__imp_WindowsDeleteString
0x18006254a  xor     ebx, ebx
0x18006254c  mov     [rbp+string], 0
0x180062554  lea     rcx, [rbp+arg_10]
0x180062558  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006255d  mov     eax, ebx
0x18006255f  mov     rbx, [rsp+20h+arg_0]
0x180062564  add     rsp, 20h
0x180062568  pop     rdi
0x180062569  pop     rsi
0x18006256a  pop     rbp
0x18006256b  retn
```
