# SystemSettings::StorageSenseHandlers::AIComponentsList::AddAIComponentToSettingsList(SystemSettings::StorageSenseHandlers::AIComponent *)

- ea: `0x180094b54`
- end: `0x180094ee0`
- name: `?AddAIComponentToSettingsList@AIComponentsList@StorageSenseHandlers@SystemSettings@@AEAAJPEAVAIComponent@23@@Z`
- size: `908`
- prototype: `int(SystemSettings::StorageSenseHandlers::AIComponentsList *__hidden this, struct SystemSettings::StorageSenseHandlers::AIComponent *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180095e1c`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x18000e6cc`
- `0x180019eb4`
- `0x180019fa8`
- `0x18001a530`
- `0x18001f230`
- `0x18001f53c`
- `0x1800225e0`
- `0x1800248c0`
- `0x18003d36c`
- `0x180094b54`
- `0x1800c81a0`
- `0x1800c8240`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180094c1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180094c1a`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180094d53`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180094d53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094bcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094c05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094cae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094ce0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094d69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094d77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094df6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094e04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094ea0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094eb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094bcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094c05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094cae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094ce0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094d69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094d77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094df6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094e04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094ea0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094eb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094d27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094d18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094d27`

## string_xrefs

- `0x180094bb0`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\aicomponentslist.cpp`
- `0x180094bef`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\aicomponentslist.cpp`
- `0x180094c45`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\aicomponentslist.cpp`
- `0x180094dc0`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\aicomponentslist.cpp`
- `0x180094e20`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\aicomponentslist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemSettings::StorageSenseHandlers::AIComponentsList::AddAIComponentToSettingsList(
        SystemSettings::StorageSenseHandlers::AIComponentsList *this,
        struct SystemSettings::StorageSenseHandlers::AIComponent *a2)
{
  int Id; // eax
  unsigned int v5; // ebx
  int Description; // eax
  int Size; // eax
  unsigned int v8; // esi
  unsigned int v9; // r14d
  __int64 v10; // rbx
  int v11; // eax
  _QWORD *v12; // rdi
  int (__fastcall *v13)(_QWORD *, HSTRING *); // rbx
  _QWORD *v14; // rdi
  int (__fastcall *v15)(_QWORD *, HSTRING *); // rbx
  HSTRING v16; // r8
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v18; // rax
  int v19; // eax
  struct IInspectable *v20; // rbx
  int lpString2; // [rsp+20h] [rbp-69h]
  HSTRING string; // [rsp+50h] [rbp-39h] BYREF
  HSTRING v24; // [rsp+58h] [rbp-31h] BYREF
  struct IInspectable *v25; // [rsp+60h] [rbp-29h] BYREF
  HSTRING v26; // [rsp+68h] [rbp-21h] BYREF
  _QWORD *v27; // [rsp+70h] [rbp-19h] BYREF
  char *v28; // [rsp+78h] [rbp-11h] BYREF
  HSTRING v29; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-1h] BYREF
  __int64 v31; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  WindowsDeleteString(0);
  v29 = 0;
  Id = SystemSettings::StorageSenseHandlers::AIComponent::get_Id(a2, &v29);
  v5 = Id;
  if ( Id >= 0 )
  {
    WindowsDeleteString(0);
    string = 0;
    Description = SystemSettings::StorageSenseHandlers::AIComponent::get_Description(a2, &string);
    v5 = Description;
    if ( Description >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
      v28 = (char *)this + 272;
      LODWORD(v25) = 0;
      Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
               *((_QWORD *)this + 26),
               &v25);
      v5 = Size;
      if ( Size >= 0 )
      {
        v8 = (unsigned int)v25;
        v9 = 0;
        if ( (_DWORD)v25 )
        {
          while ( 1 )
          {
            v27 = 0;
            v10 = *((_QWORD *)this + 26);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
            v11 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
                    v10,
                    v9,
                    &v27);
            v5 = v11;
            if ( v11 < 0 )
              break;
            v24 = 0;
            v12 = v27;
            v13 = *(int (__fastcall **)(_QWORD *, HSTRING *))(*v27 + 48LL);
            WindowsDeleteString(0);
            v24 = 0;
            if ( v13(v12, &v24) >= 0 )
            {
              v26 = 0;
              v14 = v27;
              v15 = *(int (__fastcall **)(_QWORD *, HSTRING *))(*v27 + 88LL);
              WindowsDeleteString(0);
              v26 = 0;
              if ( v15(v14, &v26) >= 0 )
              {
                if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                      (Microsoft::WRL::Wrappers::Details *)v24,
                                      v29,
                                      v16) )
                {
                  v27[34] += *((_QWORD *)a2 + 34);
                  WindowsDeleteString(v26);
                  v26 = 0;
                  WindowsDeleteString(v24);
                  v24 = 0;
                  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
                  goto LABEL_24;
                }
                StringRawBuffer = WindowsGetStringRawBuffer(v26, 0);
                v18 = WindowsGetStringRawBuffer(string, 0);
                if ( CompareStringEx(0, 0x10u, v18, -1, StringRawBuffer, -1, 0, 0, 0) == 1 && v8 > v9 )
                  v8 = v9;
              }
              WindowsDeleteString(v26);
              v26 = 0;
            }
            WindowsDeleteString(v24);
            v24 = 0;
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
            if ( ++v9 >= (unsigned int)v25 )
              goto LABEL_19;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x220,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\aicomponentslist.cpp",
            (const char *)(unsigned int)v11,
            lpString2);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
        }
        else
        {
LABEL_19:
          v25 = 0;
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v25);
          v19 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(1u, &v25);
          v5 = v19;
          if ( v19 >= 0 )
          {
            v20 = v25;
            v31 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsApplicable", 0xDu, 0xCu);
            SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::SetValue(
              a2,
              v31,
              v20);
            Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
              *((_QWORD *)this + 26),
              v8,
              a2,
              0);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v25);
LABEL_24:
            Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v28);
            WindowsDeleteString(string);
            v5 = 0;
            goto LABEL_25;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x243,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\aicomponentslist.cpp",
            (const char *)(unsigned int)v19,
            lpString2);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v25);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21A,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\aicomponentslist.cpp",
          (const char *)(unsigned int)Size,
          lpString2);
      }
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v28);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x215,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\aicomponentslist.cpp",
        (const char *)(unsigned int)Description,
        lpString2);
    }
    WindowsDeleteString(string);
LABEL_25:
    string = 0;
    goto LABEL_26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x213,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\aicomponentslist.cpp",
    (const char *)(unsigned int)Id,
    lpString2);
LABEL_26:
  WindowsDeleteString(v29);
  return v5;
}

```

## disassembly

```asm
0x180094b54  mov     [rsp-8+arg_10], rbx
0x180094b59  push    rbp
0x180094b5a  push    rsi
0x180094b5b  push    rdi
0x180094b5c  push    r12
0x180094b5e  push    r13
0x180094b60  push    r14
0x180094b62  push    r15
0x180094b64  lea     rbp, [rsp-27h]
0x180094b69  sub     rsp, 0B0h
0x180094b70  mov     rax, cs:__security_cookie
0x180094b77  xor     rax, rsp
0x180094b7a  mov     [rbp+57h+var_38], rax
0x180094b7e  mov     r15, rdx
0x180094b81  mov     r13, rcx
0x180094b84  xor     r12d, r12d
0x180094b87  mov     [rbp+57h+var_60], r12
0x180094b8b  xor     ecx, ecx; string
0x180094b8d  call    cs:__imp_WindowsDeleteString
0x180094b93  mov     [rbp+57h+var_60], r12
0x180094b97  lea     rdx, [rbp+57h+var_60]; HSTRING *
0x180094b9b  mov     rcx, r15; this
0x180094b9e  call    ?get_Id@AIComponent@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::AIComponent::get_Id(HSTRING__ * *)
0x180094ba3  mov     ebx, eax
0x180094ba5  test    eax, eax
0x180094ba7  jns     short loc_180094BC6
0x180094ba9  mov     rcx, [rbp+5Fh]; this
0x180094bad  mov     r9d, eax; char *
0x180094bb0  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\coresettinghandlers"...
0x180094bb7  mov     edx, 213h; void *
0x180094bbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094bc1  jmp     loc_180094EAD
0x180094bc6  mov     [rbp+57h+string], r12
0x180094bca  xor     ecx, ecx; string
0x180094bcc  call    cs:__imp_WindowsDeleteString
0x180094bd2  mov     [rbp+57h+string], r12
0x180094bd6  lea     rdx, [rbp+57h+string]; HSTRING *
0x180094bda  mov     rcx, r15; this
0x180094bdd  call    ?get_Description@AIComponent@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::AIComponent::get_Description(HSTRING__ * *)
0x180094be2  mov     ebx, eax
0x180094be4  test    eax, eax
0x180094be6  jns     short loc_180094C10
0x180094be8  mov     rcx, [rbp+5Fh]; this
0x180094bec  mov     r9d, eax; char *
0x180094bef  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\coresettinghandlers"...
0x180094bf6  mov     edx, 215h; void *
0x180094bfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094c00  nop
0x180094c01  mov     rcx, [rbp+57h+string]; string
0x180094c05  call    cs:__imp_WindowsDeleteString
0x180094c0b  jmp     loc_180094EA9
0x180094c10  lea     rbx, [r13+110h]
0x180094c17  mov     rcx, rbx; lpCriticalSection
0x180094c1a  call    cs:__imp_EnterCriticalSection
0x180094c20  mov     [rbp+57h+var_68], rbx
0x180094c24  mov     dword ptr [rbp+57h+var_80], r12d
0x180094c28  lea     rdx, [rbp+57h+var_80]
0x180094c2c  mov     rcx, [r13+0D0h]
0x180094c33  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x180094c38  mov     ebx, eax
0x180094c3a  test    eax, eax
0x180094c3c  jns     short loc_180094C62
0x180094c3e  mov     rcx, [rbp+5Fh]; this
0x180094c42  mov     r9d, eax; char *
0x180094c45  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\coresettinghandlers"...
0x180094c4c  mov     edx, 21Ah; void *
0x180094c51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094c56  nop
0x180094c57  lea     rcx, [rbp+57h+var_68]; this
0x180094c5b  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180094c60  jmp     short loc_180094C01
0x180094c62  mov     esi, dword ptr [rbp+57h+var_80]
0x180094c65  mov     r14d, r12d
0x180094c68  test    esi, esi
0x180094c6a  jz      loc_180094D97
0x180094c70  mov     [rbp+57h+var_70], r12
0x180094c74  mov     rbx, [r13+0D0h]
0x180094c7b  lea     rcx, [rbp+57h+var_70]
0x180094c7f  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180094c84  lea     r8, [rbp+57h+var_70]
0x180094c88  mov     edx, r14d
0x180094c8b  mov     rcx, rbx
0x180094c8e  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x180094c93  mov     ebx, eax
0x180094c95  test    eax, eax
0x180094c97  js      loc_180094E19
0x180094c9d  mov     [rbp+57h+var_88], r12
0x180094ca1  mov     rdi, [rbp+57h+var_70]
0x180094ca5  mov     rax, [rdi]
0x180094ca8  mov     rbx, [rax+30h]
0x180094cac  xor     ecx, ecx; string
0x180094cae  call    cs:__imp_WindowsDeleteString
0x180094cb4  mov     [rbp+57h+var_88], r12
0x180094cb8  lea     rdx, [rbp+57h+var_88]
0x180094cbc  mov     rcx, rdi
0x180094cbf  mov     rax, rbx
0x180094cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094cc7  test    eax, eax
0x180094cc9  js      loc_180094D73
0x180094ccf  mov     [rbp+57h+var_78], r12
0x180094cd3  mov     rdi, [rbp+57h+var_70]
0x180094cd7  mov     rax, [rdi]
0x180094cda  mov     rbx, [rax+58h]
0x180094cde  xor     ecx, ecx; string
0x180094ce0  call    cs:__imp_WindowsDeleteString
0x180094ce6  mov     [rbp+57h+var_78], r12
0x180094cea  lea     rdx, [rbp+57h+var_78]
0x180094cee  mov     rcx, rdi
0x180094cf1  mov     rax, rbx
0x180094cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094cf9  test    eax, eax
0x180094cfb  js      short loc_180094D65
0x180094cfd  mov     rdx, [rbp+57h+var_60]; HSTRING
0x180094d01  mov     rcx, [rbp+57h+var_88]; this
0x180094d05  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180094d0a  test    eax, eax
0x180094d0c  jz      loc_180094DE0
0x180094d12  xor     edx, edx; length
0x180094d14  mov     rcx, [rbp+57h+var_78]; string
0x180094d18  call    cs:__imp_WindowsGetStringRawBuffer
0x180094d1e  mov     rbx, rax
0x180094d21  xor     edx, edx; length
0x180094d23  mov     rcx, [rbp+57h+string]; string
0x180094d27  call    cs:__imp_WindowsGetStringRawBuffer
0x180094d2d  mov     [rsp+0E0h+lParam], r12; lParam
0x180094d32  mov     [rsp+0E0h+lpReserved], r12; lpReserved
0x180094d37  mov     [rsp+0E0h+lpVersionInformation], r12; lpVersionInformation
0x180094d3c  or      edi, 0FFFFFFFFh
0x180094d3f  mov     [rsp+0E0h+cchCount2], edi; cchCount2
0x180094d43  mov     [rsp+0E0h+lpString2], rbx; int
0x180094d48  mov     r9d, edi; cchCount1
0x180094d4b  mov     r8, rax; lpString1
0x180094d4e  lea     edx, [rdi+11h]; dwCmpFlags
0x180094d51  xor     ecx, ecx; lpLocaleName
0x180094d53  call    cs:__imp_CompareStringEx
0x180094d59  cmp     eax, 1
0x180094d5c  jnz     short loc_180094D65
0x180094d5e  cmp     esi, r14d
0x180094d61  cmova   esi, r14d
0x180094d65  mov     rcx, [rbp+57h+var_78]; string
0x180094d69  call    cs:__imp_WindowsDeleteString
0x180094d6f  mov     [rbp+57h+var_78], r12
0x180094d73  mov     rcx, [rbp+57h+var_88]; string
0x180094d77  call    cs:__imp_WindowsDeleteString
0x180094d7d  mov     [rbp+57h+var_88], r12
0x180094d81  lea     rcx, [rbp+57h+var_70]
0x180094d85  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180094d8a  inc     r14d
0x180094d8d  cmp     r14d, dword ptr [rbp+57h+var_80]
0x180094d91  jb      loc_180094C70
0x180094d97  mov     [rbp+57h+var_80], r12
0x180094d9b  lea     rcx, [rbp+57h+var_80]
0x180094d9f  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180094da4  lea     rdx, [rbp+57h+var_80]; struct IInspectable **
0x180094da8  mov     cl, 1; unsigned __int8
0x180094daa  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x180094daf  mov     ebx, eax
0x180094db1  test    eax, eax
0x180094db3  jns     loc_180094E40
0x180094db9  mov     rcx, [rbp+5Fh]; this
0x180094dbd  mov     r9d, eax; char *
0x180094dc0  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\coresettinghandlers"...
0x180094dc7  mov     edx, 243h; void *
0x180094dcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094dd1  nop
0x180094dd2  lea     rcx, [rbp+57h+var_80]
0x180094dd6  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180094ddb  jmp     loc_180094C57
0x180094de0  mov     rcx, [rbp+57h+var_70]
0x180094de4  mov     rax, [r15+110h]
0x180094deb  add     [rcx+110h], rax
0x180094df2  mov     rcx, [rbp+57h+var_78]; string
0x180094df6  call    cs:__imp_WindowsDeleteString
0x180094dfc  mov     [rbp+57h+var_78], r12
0x180094e00  mov     rcx, [rbp+57h+var_88]; string
0x180094e04  call    cs:__imp_WindowsDeleteString
0x180094e0a  mov     [rbp+57h+var_88], r12
0x180094e0e  lea     rcx, [rbp+57h+var_70]
0x180094e12  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180094e17  jmp     short loc_180094E92
0x180094e19  mov     rcx, [rbp+5Fh]; this
0x180094e1d  mov     r9d, eax; char *
0x180094e20  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\coresettinghandlers"...
0x180094e27  mov     edx, 220h; void *
0x180094e2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094e31  nop
0x180094e32  lea     rcx, [rbp+57h+var_70]
0x180094e36  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180094e3b  jmp     loc_180094C57
0x180094e40  mov     rbx, [rbp+57h+var_80]
0x180094e44  mov     [rbp+57h+var_40], r12
0x180094e48  mov     r9d, 0Ch; unsigned int
0x180094e4e  lea     r8d, [r9+1]; unsigned int
0x180094e52  lea     rdx, aIsapplicable; "IsApplicable"
0x180094e59  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180094e5d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180094e62  nop
0x180094e63  mov     r8, rbx
0x180094e66  mov     rdx, [rbp+57h+var_40]
0x180094e6a  mov     rcx, r15
0x180094e6d  call    ?SetValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z; SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::SetValue(HSTRING__ *,IInspectable *)
0x180094e72  nop
0x180094e73  xor     r9d, r9d
0x180094e76  mov     r8, r15
0x180094e79  mov     edx, esi
0x180094e7b  mov     rcx, [r13+0D0h]
0x180094e82  call    ?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)
0x180094e87  nop
0x180094e88  lea     rcx, [rbp+57h+var_80]
0x180094e8c  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180094e91  nop
0x180094e92  lea     rcx, [rbp+57h+var_68]; this
0x180094e96  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180094e9b  nop
0x180094e9c  mov     rcx, [rbp+57h+string]; string
0x180094ea0  call    cs:__imp_WindowsDeleteString
0x180094ea6  mov     ebx, r12d
0x180094ea9  mov     [rbp+57h+string], r12
0x180094ead  mov     rcx, [rbp+57h+var_60]; string
0x180094eb1  call    cs:__imp_WindowsDeleteString
0x180094eb7  mov     eax, ebx
0x180094eb9  mov     rcx, [rbp+57h+var_38]
0x180094ebd  xor     rcx, rsp; StackCookie
0x180094ec0  call    __security_check_cookie
0x180094ec5  mov     rbx, [rsp+0E0h+arg_10]
0x180094ecd  add     rsp, 0B0h
0x180094ed4  pop     r15
0x180094ed6  pop     r14
0x180094ed8  pop     r13
0x180094eda  pop     r12
0x180094edc  pop     rdi
0x180094edd  pop     rsi
0x180094ede  pop     rbp
0x180094edf  retn
```
