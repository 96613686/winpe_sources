# Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_ExecuteActionThroughLaunch(unsigned __int64,Windows::ApplicationModel::Contacts::Internal::ActivationSource,HSTRING__ *,HWND__ *)

- ea: `0x1801da7e4`
- end: `0x1801da9b7`
- name: `?_ExecuteActionThroughLaunch@ContactActionControlItemBase@Internal@Contacts@ApplicationModel@Windows@@IEAAJ_KW4ActivationSource@2345@PEAUHSTRING__@@PEAUHWND__@@@Z`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1801d6d90`

## callees

- `0x180009dd0`
- `0x18001c710`
- `0x18006f0ec`
- `0x180142e10`
- `0x1801cc6d0`
- `0x1801d3c84`
- `0x1801da5a4`
- `0x1801da7e4`
- `0x1801da9c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da961`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da981`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da961`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da981`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da89e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da8b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da89e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da8b4`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_ExecuteActionThroughLaunch(
        _QWORD *a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  int ContactsProvider; // eax
  HSTRING v10; // r8
  HSTRING v11; // rbx
  int v12; // edi
  __int64 v13; // r8
  HSTRING v14; // rcx
  PCWSTR StringRawBuffer; // rax
  HSTRING v16; // rcx
  HSTRING string; // [rsp+50h] [rbp-41h] BYREF
  HSTRING v19; // [rsp+58h] [rbp-39h] BYREF
  HSTRING v20; // [rsp+60h] [rbp-31h] BYREF
  __int64 v21; // [rsp+68h] [rbp-29h] BYREF
  PCWSTR v22; // [rsp+70h] [rbp-21h] BYREF
  PCWSTR v23; // [rsp+78h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-11h] BYREF
  __int64 v25; // [rsp+98h] [rbp+7h]

  WindowsDeleteString(0);
  string = 0;
  WindowsDeleteString(0);
  v20 = 0;
  WindowsDeleteString(0);
  v19 = 0;
  ContactsProvider = InternalGetContactsProvider(&v19, &v20, &string);
  v11 = string;
  v12 = ContactsProvider;
  if ( ContactsProvider >= 0 )
  {
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                         (Microsoft::WRL::Wrappers::Details *)v19,
                         0,
                         v10) )
    {
      v14 = (HSTRING)a1[15];
      v21 = a1[8];
      string = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(v14, 0);
      v16 = (HSTRING)a1[12];
      v22 = StringRawBuffer;
      v23 = WindowsGetStringRawBuffer(v16, 0);
      v12 = Microsoft::WRL::Details::MakeAndInitialize<CContactCallActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,unsigned short const *,unsigned short const *,Windows::ApplicationModel::Contacts::IContact2 *>(
              &string,
              &v23,
              &v22,
              &v21);
      if ( v12 >= 0 )
      {
        v25 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Launch", 0xFu, 0xEu);
        v12 = Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_ExecuteActionThroughActivationFramework(
                a1,
                string,
                v25,
                3,
                a2,
                a3,
                a4,
                a5,
                v11);
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
    }
    else
    {
      Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_ExecuteActionThroughUriScheme(
        a1,
        L"ms-windows-store:PDP?PFN=%1",
        v13,
        a2,
        a3,
        a4,
        a5);
    }
  }
  WindowsDeleteString(v11);
  WindowsDeleteString(v20);
  WindowsDeleteString(v19);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1801da7e4  mov     [rsp-8+arg_10], rbx
0x1801da7e9  push    rbp
0x1801da7ea  push    rsi
0x1801da7eb  push    rdi
0x1801da7ec  push    r12
0x1801da7ee  push    r13
0x1801da7f0  push    r14
0x1801da7f2  push    r15
0x1801da7f4  lea     rbp, [rsp-1Fh]
0x1801da7f9  sub     rsp, 0B0h
0x1801da800  mov     rax, cs:__security_cookie
0x1801da807  xor     rax, rsp
0x1801da80a  mov     [rbp+4Fh+var_40], rax
0x1801da80e  mov     r13, [rbp+4Fh+arg_20]
0x1801da812  mov     rsi, rcx
0x1801da815  xor     ecx, ecx; string
0x1801da817  mov     r12, r9
0x1801da81a  mov     r14d, r8d
0x1801da81d  mov     r15, rdx
0x1801da820  call    cs:__imp_WindowsDeleteString
0x1801da827  nop     dword ptr [rax+rax+00h]
0x1801da82c  xor     ebx, ebx
0x1801da82e  xor     ecx, ecx; string
0x1801da830  mov     [rbp+4Fh+string], rbx
0x1801da834  call    cs:__imp_WindowsDeleteString
0x1801da83b  nop     dword ptr [rax+rax+00h]
0x1801da840  xor     ecx, ecx; string
0x1801da842  mov     [rbp+4Fh+var_80], rbx
0x1801da846  call    cs:__imp_WindowsDeleteString
0x1801da84d  nop     dword ptr [rax+rax+00h]
0x1801da852  lea     r8, [rbp+4Fh+string]; HSTRING *
0x1801da856  mov     [rbp+4Fh+var_88], rbx
0x1801da85a  lea     rdx, [rbp+4Fh+var_80]; HSTRING *
0x1801da85e  lea     rcx, [rbp+4Fh+var_88]; HSTRING *
0x1801da862  call    ?InternalGetContactsProvider@@YAJPEAPEAUHSTRING__@@00@Z; InternalGetContactsProvider(HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1801da867  mov     rbx, [rbp+4Fh+string]
0x1801da86b  mov     edi, eax
0x1801da86d  test    eax, eax
0x1801da86f  js      loc_1801DA95E
0x1801da875  mov     rcx, [rbp+4Fh+var_88]; this
0x1801da879  xor     edx, edx; HSTRING
0x1801da87b  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1801da880  test    eax, eax
0x1801da882  jz      loc_1801DA93D
0x1801da888  mov     rax, [rsi+40h]
0x1801da88c  xor     edx, edx; length
0x1801da88e  mov     rcx, [rsi+78h]; string
0x1801da892  mov     [rbp+4Fh+var_78], rax
0x1801da896  mov     [rbp+4Fh+string], 0
0x1801da89e  call    cs:__imp_WindowsGetStringRawBuffer
0x1801da8a5  nop     dword ptr [rax+rax+00h]
0x1801da8aa  mov     rcx, [rsi+60h]; string
0x1801da8ae  xor     edx, edx; length
0x1801da8b0  mov     [rbp+4Fh+var_70], rax
0x1801da8b4  call    cs:__imp_WindowsGetStringRawBuffer
0x1801da8bb  nop     dword ptr [rax+rax+00h]
0x1801da8c0  lea     r9, [rbp+4Fh+var_78]
0x1801da8c4  mov     [rbp+4Fh+var_68], rax
0x1801da8c8  lea     r8, [rbp+4Fh+var_70]
0x1801da8cc  lea     rdx, [rbp+4Fh+var_68]
0x1801da8d0  lea     rcx, [rbp+4Fh+string]
0x1801da8d4  call    ??$MakeAndInitialize@VCContactCallActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEBGPEBGPEAUIContact2@Contacts@45@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@012@$$QEAPEBG1$$QEAPEAUIContact2@Contacts@ApplicationModel@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CContactCallActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,ushort const *,ushort const *,Windows::ApplicationModel::Contacts::IContact2 *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>>,ushort const * &&,ushort const * &&,Windows::ApplicationModel::Contacts::IContact2 * &&)
0x1801da8d9  mov     edi, eax
0x1801da8db  test    eax, eax
0x1801da8dd  js      short loc_1801DA932
0x1801da8df  mov     r9d, 0Eh; unsigned int
0x1801da8e5  mov     [rbp+4Fh+var_48], 0
0x1801da8ed  lea     rdx, aWindowsLaunch; "Windows.Launch"
0x1801da8f4  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x1801da8f8  lea     r8d, [r9+1]; unsigned int
0x1801da8fc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801da901  mov     r8, [rbp+4Fh+var_48]
0x1801da905  mov     r9d, 3
0x1801da90b  mov     rdx, [rbp+4Fh+string]
0x1801da90f  mov     rcx, rsi
0x1801da912  mov     [rsp+0E0h+var_A0], rbx
0x1801da917  mov     [rsp+0E0h+var_A8], r13
0x1801da91c  mov     [rsp+0E0h+var_B0], r12
0x1801da921  mov     dword ptr [rsp+0E0h+var_B8], r14d
0x1801da926  mov     [rsp+0E0h+var_C0], r15
0x1801da92b  call    ?_ExecuteActionThroughActivationFramework@ContactActionControlItemBase@Internal@Contacts@ApplicationModel@Windows@@IEAAJPEAUIActivatedEventArgs@Activation@45@PEAUHSTRING__@@W4APPLICATION_VIEW_SIZE_PREFERENCE@@_KW4ActivationSource@2345@1PEAUHWND__@@1@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_ExecuteActionThroughActivationFramework(Windows::ApplicationModel::Activation::IActivatedEventArgs *,HSTRING__ *,APPLICATION_VIEW_SIZE_PREFERENCE,unsigned __int64,Windows::ApplicationModel::Contacts::Internal::ActivationSource,HSTRING__ *,HWND__ *,HSTRING__ *)
0x1801da930  mov     edi, eax
0x1801da932  lea     rcx, [rbp+4Fh+string]
0x1801da936  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801da93b  jmp     short loc_1801DA95E
0x1801da93d  mov     [rsp+0E0h+var_B0], r13
0x1801da942  lea     rdx, aMsWindowsStore_3; "ms-windows-store:PDP?PFN=%1"
0x1801da949  mov     [rsp+0E0h+var_B8], r12
0x1801da94e  mov     r9, r15
0x1801da951  mov     rcx, rsi
0x1801da954  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1801da959  call    ?_ExecuteActionThroughUriScheme@ContactActionControlItemBase@Internal@Contacts@ApplicationModel@Windows@@IEAAJPEBGW4APPLICATION_VIEW_SIZE_PREFERENCE@@_KW4ActivationSource@2345@PEAUHSTRING__@@PEAUHWND__@@@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_ExecuteActionThroughUriScheme(ushort const *,APPLICATION_VIEW_SIZE_PREFERENCE,unsigned __int64,Windows::ApplicationModel::Contacts::Internal::ActivationSource,HSTRING__ *,HWND__ *)
0x1801da95e  mov     rcx, rbx; string
0x1801da961  call    cs:__imp_WindowsDeleteString
0x1801da968  nop     dword ptr [rax+rax+00h]
0x1801da96d  mov     rcx, [rbp+4Fh+var_80]; string
0x1801da971  call    cs:__imp_WindowsDeleteString
0x1801da978  nop     dword ptr [rax+rax+00h]
0x1801da97d  mov     rcx, [rbp+4Fh+var_88]; string
0x1801da981  call    cs:__imp_WindowsDeleteString
0x1801da988  nop     dword ptr [rax+rax+00h]
0x1801da98d  mov     eax, edi
0x1801da98f  mov     rcx, [rbp+4Fh+var_40]
0x1801da993  xor     rcx, rsp; StackCookie
0x1801da996  call    __security_check_cookie
0x1801da99b  mov     rbx, [rsp+0E0h+arg_10]
0x1801da9a3  add     rsp, 0B0h
0x1801da9aa  pop     r15
0x1801da9ac  pop     r14
0x1801da9ae  pop     r13
0x1801da9b0  pop     r12
0x1801da9b2  pop     rdi
0x1801da9b3  pop     rsi
0x1801da9b4  pop     rbp
0x1801da9b5  retn
```
