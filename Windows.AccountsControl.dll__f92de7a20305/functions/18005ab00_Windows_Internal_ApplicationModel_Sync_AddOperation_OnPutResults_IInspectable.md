# Windows::Internal::ApplicationModel::Sync::AddOperation::OnPutResults(IInspectable *)

- ea: `0x18005ab00`
- end: `0x18005ac30`
- name: `?OnPutResults@AddOperation@Sync@ApplicationModel@Internal@Windows@@UEAAJPEAUIInspectable@@@Z`
- size: `304`
- prototype: `int(Windows::Internal::ApplicationModel::Sync::AddOperation *__hidden this, struct IInspectable *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006eac`
- `0x18000c14c`
- `0x180011ffc`
- `0x18005923c`
- `0x18005ab00`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005ab70`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005ab70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ab9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005abe4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ab9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005abe4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::AddOperation::OnPutResults(
        RTL_SRWLOCK *this,
        struct IInspectable *a2)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  RTL_SRWLOCK *v7; // rsi
  HSTRING Ptr; // rcx
  struct Windows::Foundation::IPropertyValue *v9; // rdi
  __int64 (__fastcall *v10)(struct Windows::Foundation::IPropertyValue *, RTL_SRWLOCK *); // rbx
  int FormattedUserDataAccountId; // eax
  __int64 v12; // rdx
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct Windows::Foundation::IPropertyValue *v16; // [rsp+48h] [rbp+10h] BYREF
  RTL_SRWLOCK *v17; // [rsp+50h] [rbp+18h] BYREF

  v16 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  v5 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, struct Windows::Foundation::IPropertyValue **))QueryInterface)(
         a2,
         &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
         &v16);
  v6 = v5;
  if ( v5 >= 0 )
  {
    AcquireSRWLockExclusive(this + 81);
    v17 = this + 81;
    v7 = this + 79;
    Ptr = (HSTRING)this[79].Ptr;
    if ( LOBYTE(this[80].Ptr) )
    {
      v9 = v16;
      v10 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, RTL_SRWLOCK *))(*(_QWORD *)v16
                                                                                                  + 152LL);
      WindowsDeleteString(Ptr);
      v7->Ptr = 0;
      FormattedUserDataAccountId = v10(v9, this + 79);
      v6 = FormattedUserDataAccountId;
      if ( FormattedUserDataAccountId < 0 )
      {
        v12 = 289;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)FormattedUserDataAccountId,
          v14);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
        goto LABEL_10;
      }
    }
    else
    {
      WindowsDeleteString(Ptr);
      v7->Ptr = 0;
      FormattedUserDataAccountId = GetFormattedUserDataAccountId(v16, (HSTRING *)&this[79]);
      v6 = FormattedUserDataAccountId;
      if ( FormattedUserDataAccountId < 0 )
      {
        v12 = 293;
        goto LABEL_6;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
    v6 = 0;
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11C,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
    (const char *)(unsigned int)v5,
    v14);
LABEL_10:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  return v6;
}

```

## disassembly

```asm
0x18005ab00  mov     [rsp+arg_0], rbx
0x18005ab05  push    rbp
0x18005ab06  push    rsi
0x18005ab07  push    rdi; int
0x18005ab08  sub     rsp, 20h
0x18005ab0c  mov     rdi, rdx
0x18005ab0f  mov     rbp, rcx
0x18005ab12  mov     [rsp+38h+arg_8], 0
0x18005ab1b  mov     rax, [rdx]
0x18005ab1e  mov     rbx, [rax]
0x18005ab21  lea     rcx, [rsp+38h+arg_8]
0x18005ab26  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005ab2b  lea     r8, [rsp+38h+arg_8]
0x18005ab30  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18005ab37  mov     rcx, rdi
0x18005ab3a  mov     rax, rbx
0x18005ab3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab42  mov     ebx, eax
0x18005ab44  test    eax, eax
0x18005ab46  jns     short loc_18005AB66
0x18005ab48  mov     rcx, [rsp+38h]; this
0x18005ab4d  mov     r9d, eax; char *
0x18005ab50  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005ab57  mov     edx, 11Ch; void *
0x18005ab5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ab61  jmp     loc_18005AC17
0x18005ab66  lea     rbx, [rbp+288h]
0x18005ab6d  mov     rcx, rbx; SRWLock
0x18005ab70  call    cs:__imp_AcquireSRWLockExclusive
0x18005ab76  mov     [rsp+38h+arg_10], rbx
0x18005ab7b  lea     rsi, [rbp+278h]
0x18005ab82  mov     rcx, [rsi]; string
0x18005ab85  cmp     byte ptr [rbp+280h], 0
0x18005ab8c  jz      short loc_18005ABE4
0x18005ab8e  mov     rdi, [rsp+38h+arg_8]
0x18005ab93  mov     rax, [rdi]
0x18005ab96  mov     rbx, [rax+98h]
0x18005ab9d  call    cs:__imp_WindowsDeleteString
0x18005aba3  mov     qword ptr [rsi], 0
0x18005abaa  mov     rdx, rsi
0x18005abad  mov     rcx, rdi
0x18005abb0  mov     rax, rbx
0x18005abb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005abb8  mov     ebx, eax
0x18005abba  test    eax, eax
0x18005abbc  jns     short loc_18005AC0B
0x18005abbe  mov     edx, 121h; void *
0x18005abc3  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005abca  mov     r9d, eax; char *
0x18005abcd  mov     rcx, [rsp+38h]; this
0x18005abd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005abd7  nop
0x18005abd8  lea     rcx, [rsp+38h+arg_10]
0x18005abdd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005abe2  jmp     short loc_18005AC17
0x18005abe4  call    cs:__imp_WindowsDeleteString
0x18005abea  mov     qword ptr [rsi], 0
0x18005abf1  mov     rdx, rsi; HSTRING *
0x18005abf4  mov     rcx, [rsp+38h+arg_8]; struct Windows::Foundation::IPropertyValue *
0x18005abf9  call    ?GetFormattedUserDataAccountId@@YAJPEAUIPropertyValue@Foundation@Windows@@PEAPEAUHSTRING__@@@Z; GetFormattedUserDataAccountId(Windows::Foundation::IPropertyValue *,HSTRING__ * *)
0x18005abfe  mov     ebx, eax
0x18005ac00  test    eax, eax
0x18005ac02  jns     short loc_18005AC0B
0x18005ac04  mov     edx, 125h
0x18005ac09  jmp     short loc_18005ABC3
0x18005ac0b  lea     rcx, [rsp+38h+arg_10]
0x18005ac10  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005ac15  xor     ebx, ebx
0x18005ac17  lea     rcx, [rsp+38h+arg_8]
0x18005ac1c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005ac21  mov     eax, ebx
0x18005ac23  mov     rbx, [rsp+38h+arg_0]
0x18005ac28  add     rsp, 20h
0x18005ac2c  pop     rdi
0x18005ac2d  pop     rsi
0x18005ac2e  pop     rbp
0x18005ac2f  retn
```
