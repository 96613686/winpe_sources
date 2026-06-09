# Windows::Storage::ApplicationDataFactoryServer::GetApplicationDataInstance(HSTRING__ *,Windows::Storage::IApplicationData * *)

- ea: `0x180017250`
- end: `0x1800173e6`
- name: `?GetApplicationDataInstance@ApplicationDataFactoryServer@Storage@Windows@@CAJPEAUHSTRING__@@PEAPEAUIApplicationData@23@@Z`
- size: `406`
- prototype: `HRESULT __fastcall(HSTRING__ *userSid, Windows::Storage::IApplicationData **value)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001e9b4`
- `0x18003f264`

## callees

- `0x180003820`
- `0x180009778`
- `0x180017250`
- `0x1800173ec`
- `0x18001e6c0`
- `0x180021efc`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800173a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800173a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800172c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001733b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800172c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001733b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017373`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataFactoryServer::GetApplicationDataInstance(
        HSTRING userSid,
        Windows::Storage::IApplicationData **value)
{
  int v2; // eax
  unsigned int v3; // ebx
  Windows::Storage::IApplicationData *v4; // rcx
  Windows::Storage::IApplicationData *ptr; // rcx
  Windows::Storage::IApplicationData *v7; // rcx
  PCWSTR StringRawBuffer; // rax
  _QWORD v9[5]; // [rsp+30h] [rbp-28h] BYREF
  void *retaddr; // [rsp+68h] [rbp+10h]
  HSTRING string; // [rsp+70h] [rbp+18h] BYREF
  Windows::Storage::IApplicationData **v12; // [rsp+78h] [rbp+20h] BYREF
  Microsoft::WRL::ComPtr<Windows::Storage::IApplicationData> appData; // [rsp+80h] [rbp+28h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > propertyKeyHString; // [rsp+88h] [rbp+30h] BYREF

  v12 = value;
  string = userSid;
  appData.ptr_ = 0;
  propertyKeyHString.m_ptr = 0;
  if ( !userSid )
  {
    v3 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0xBCu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
      -2147024809);
    if ( propertyKeyHString.m_ptr )
      WindowsDeleteString(propertyKeyHString.m_ptr);
    ptr = appData.ptr_;
    if ( appData.ptr_ )
    {
      appData.ptr_ = 0;
      ptr->Release(ptr);
    }
    return v3;
  }
  if ( !value )
  {
    v3 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0xBDu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
      -2147024809);
LABEL_22:
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&propertyKeyHString);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&appData);
    return v3;
  }
  v9[0] = &string;
  v9[1] = &propertyKeyHString;
  v9[2] = &appData;
  v9[3] = &v12;
  v2 = lambda_c53faa248f43030dfa3ac1ff7f3091df_::operator()((__int64)v9);
  v3 = v2;
  if ( v2 != -2147483637 )
  {
    if ( v2 >= 0 )
    {
      if ( propertyKeyHString.m_ptr )
        WindowsDeleteString(propertyKeyHString.m_ptr);
      v4 = appData.ptr_;
      if ( appData.ptr_ )
      {
        appData.ptr_ = 0;
        v4->Release(v4);
      }
      return 0;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0xECu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
      v3,
      "User %ws",
      StringRawBuffer);
    goto LABEL_22;
  }
  if ( propertyKeyHString.m_ptr )
    WindowsDeleteString(propertyKeyHString.m_ptr);
  v7 = appData.ptr_;
  if ( appData.ptr_ )
  {
    appData.ptr_ = 0;
    v7->Release(v7);
  }
  return 2147483659LL;
}

```

## disassembly

```asm
0x180017250  mov     [rsp-10h+arg_8], value
0x180017255  mov     [rsp-10h+string], userSid
0x18001725a  push    rbp
0x18001725b  push    rbx
0x18001725c  mov     rbp, rsp
0x18001725f  sub     rsp, 58h
0x180017263  mov     [rbp+appData.ptr_], 0
0x18001726b  mov     [rbp+propertyKeyHString.m_ptr], 0
0x180017273  test    userSid, userSid
0x180017276  jz      short loc_1800172F4
0x180017278  test    value, value
0x18001727b  jz      loc_18001737B
0x180017281  lea     rax, [rbp+string]
0x180017285  mov     [rbp+var_28], rax
0x180017289  lea     userSid, [rbp+var_28]
0x18001728d  lea     rax, [rbp+propertyKeyHString]
0x180017291  mov     [rbp+var_20], rax
0x180017295  lea     rax, [rbp+appData]
0x180017299  mov     [rbp+var_18], rax
0x18001729d  lea     rax, [rbp+arg_8]
0x1800172a1  mov     [rbp+var_10], rax
0x1800172a5  call    _lambda_c53faa248f43030dfa3ac1ff7f3091df___operator__
0x1800172aa  mov     ebx, eax
0x1800172ac  cmp     eax, 8000000Bh
0x1800172b1  jz      loc_180017343
0x1800172b7  test    eax, eax
0x1800172b9  js      loc_18001739A
0x1800172bf  mov     userSid, [rbp+propertyKeyHString.m_ptr]; string
0x1800172c3  test    userSid, userSid
0x1800172c6  jz      short loc_1800172CE
0x1800172c8  call    cs:__imp_WindowsDeleteString
0x1800172ce  mov     userSid, [rbp+appData.ptr_]
0x1800172d2  test    userSid, userSid
0x1800172d5  jz      short loc_1800172EB
0x1800172d7  mov     [rbp+appData.ptr_], 0
0x1800172df  mov     rax, [userSid]
0x1800172e2  mov     rax, [rax+10h]
0x1800172e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172eb  xor     eax, eax
0x1800172ed  add     rsp, 58h
0x1800172f1  pop     rbx
0x1800172f2  pop     rbp
0x1800172f3  retn
0x1800172f4  mov     userSid, [rbp+10h]; callerReturnAddress
0x1800172f8  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800172ff  mov     ebx, 80070057h
0x180017304  mov     edx, 0BCh; lineNumber
0x180017309  mov     r9d, ebx; hr
0x18001730c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017311  mov     userSid, [rbp+propertyKeyHString.m_ptr]; string
0x180017315  test    userSid, userSid
0x180017318  jnz     short loc_18001733B
0x18001731a  mov     userSid, [rbp+appData.ptr_]
0x18001731e  test    userSid, userSid
0x180017321  jz      short loc_180017337
0x180017323  mov     [rbp+appData.ptr_], 0
0x18001732b  mov     rax, [userSid]
0x18001732e  mov     rax, [rax+10h]
0x180017332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017337  mov     eax, ebx
0x180017339  jmp     short loc_1800172ED
0x18001733b  call    cs:__imp_WindowsDeleteString
0x180017341  jmp     short loc_18001731A
0x180017343  mov     userSid, [rbp+propertyKeyHString.m_ptr]; string
0x180017347  test    userSid, userSid
0x18001734a  jnz     short loc_180017373
0x18001734c  mov     userSid, [rbp+appData.ptr_]
0x180017350  test    userSid, userSid
0x180017353  jz      short loc_180017369
0x180017355  mov     [rbp+appData.ptr_], 0
0x18001735d  mov     value, [userSid]
0x180017360  mov     rax, [value+10h]
0x180017364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017369  mov     eax, 8000000Bh
0x18001736e  jmp     loc_1800172ED
0x180017373  call    cs:__imp_WindowsDeleteString
0x180017379  jmp     short loc_18001734C
0x18001737b  mov     userSid, [rbp+10h]; callerReturnAddress
0x18001737f  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\statemanage"...
0x180017386  mov     ebx, 80070057h
0x18001738b  mov     edx, 0BDh; lineNumber
0x180017390  mov     r9d, ebx; hr
0x180017393  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017398  jmp     short loc_1800173CF
0x18001739a  mov     userSid, [rbp+string]; string
0x18001739e  xor     edx, edx; length
0x1800173a0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800173a6  mov     userSid, [rbp+10h]; callerReturnAddress
0x1800173aa  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800173b1  mov     [rsp+58h+var_30], rax
0x1800173b6  mov     r9d, ebx; hr
0x1800173b9  lea     rax, aUserWs; "User %ws"
0x1800173c0  mov     edx, 0ECh; lineNumber
0x1800173c5  mov     [rsp+58h+formatString], rax; formatString
0x1800173ca  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800173cf  lea     userSid, [rbp+propertyKeyHString]; this
0x1800173d3  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800173d8  lea     userSid, [rbp+appData]; this
0x1800173dc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800173e1  jmp     loc_180017337
```
