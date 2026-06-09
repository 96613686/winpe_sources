# StateRepoHelper::ForEachSearchProtocolHandler__lambda_3922738b78a3dc4c77f3f6a2e5a0db54___

- ea: `0x140047a80`
- end: `0x140047c34`
- name: `StateRepoHelper::ForEachSearchProtocolHandler__lambda_3922738b78a3dc4c77f3f6a2e5a0db54___`
- size: `436`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140047874`

## callees

- `0x140028044`
- `0x140041500`
- `0x140047468`
- `0x1400474c4`
- `0x140047a80`
- `0x140047df4`
- `0x140048250`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140047aff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140047c1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140047aff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140047c1c`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x140047b24`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x140047b24`

## string_xrefs

- `0x140047ae2`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x140047b37`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x140047b72`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x140047bb4`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall StateRepoHelper::ForEachSearchProtocolHandler__lambda_3922738b78a3dc4c77f3f6a2e5a0db54___(
        __int64 *a1,
        __int64 a2)
{
  __int64 v3; // rax
  int ChildElement; // ebx
  void *v5; // rcx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdx
  void *v12; // rcx
  __int64 v13; // [rsp+20h] [rbp-40h] BYREF
  __int64 v14; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v15[2]; // [rsp+30h] [rbp-30h] BYREF
  LPVOID *p_pv; // [rsp+40h] [rbp-20h] BYREF
  __int64 v17; // [rsp+48h] [rbp-18h] BYREF
  char v18; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  unsigned int v20; // [rsp+80h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+30h] BYREF
  __int64 v22; // [rsp+98h] [rbp+38h] BYREF

  v15[1] = -2;
  v20 = 0;
  pv = 0;
  v3 = *a1;
  p_pv = &pv;
  v17 = 0;
  v18 = 1;
  ChildElement = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, __int64 *))(v3 + 512))(a1, &v20, &v17);
  wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( ChildElement < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)ChildElement,
      v13);
LABEL_3:
    v5 = pv;
    pv = 0;
    if ( v5 )
      CoTaskMemFree(v5);
    return (unsigned int)ChildElement;
  }
  v22 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v22);
  v7 = SRDictionaryToPropertySet(v20, pv, &v22);
  ChildElement = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)v7,
      v13);
LABEL_8:
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v22);
    goto LABEL_3;
  }
  v14 = 0;
  v8 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
         &v22,
         &v14);
  ChildElement = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)v8,
      v13);
LABEL_11:
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v14);
    goto LABEL_8;
  }
  v13 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v13);
  ChildElement = StateRepoHelper::GetChildElement(v9, v14, &v13);
  if ( ChildElement < 0 )
  {
    v11 = 125;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)ChildElement,
      v13);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v13);
    goto LABEL_11;
  }
  v15[0] = a2;
  ChildElement = StateRepoHelper::ForEachChildElement__lambda_094ae5f9b4fc1013eabe3ab3e7d83e48___(v10, v13, v15);
  if ( ChildElement < 0 )
  {
    v11 = 142;
    goto LABEL_14;
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v14);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v22);
  v12 = pv;
  pv = 0;
  if ( v12 )
    CoTaskMemFree(v12);
  return 0;
}

```

## disassembly

```asm
0x140047a80  mov     rax, rsp
0x140047a83  push    rbp
0x140047a84  push    rsi
0x140047a85  push    rdi
0x140047a86  mov     rbp, rsp
0x140047a89  sub     rsp, 60h
0x140047a8d  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x140047a95  mov     [rax+10h], rbx
0x140047a99  mov     rdi, rdx
0x140047a9c  xor     esi, esi
0x140047a9e  mov     [rbp+arg_0], esi
0x140047aa1  mov     [rbp+pv], rsi
0x140047aa5  mov     rax, [rcx]
0x140047aa8  lea     rdx, [rbp+pv]
0x140047aac  mov     [rbp+var_20], rdx
0x140047ab0  mov     [rbp+var_18], rsi
0x140047ab4  mov     [rbp+var_10], 1
0x140047ab8  lea     r8, [rbp+var_18]
0x140047abc  lea     rdx, [rbp+arg_0]
0x140047ac0  mov     rax, [rax+200h]
0x140047ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047acc  mov     ebx, eax
0x140047ace  lea     rcx, [rbp+var_20]
0x140047ad2  call    ??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x140047ad7  test    ebx, ebx
0x140047ad9  jns     short loc_140047B0C
0x140047adb  mov     rcx, [rbp+18h]; this
0x140047adf  mov     r9d, ebx; char *
0x140047ae2  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x140047ae9  lea     edx, [rsi+74h]; void *
0x140047aec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047af1  nop
0x140047af2  mov     rcx, [rbp+pv]; pv
0x140047af6  mov     [rbp+pv], rsi
0x140047afa  test    rcx, rcx
0x140047afd  jz      short loc_140047B05
0x140047aff  call    cs:__imp_CoTaskMemFree
0x140047b05  mov     eax, ebx
0x140047b07  jmp     loc_140047C24
0x140047b0c  mov     [rbp+arg_18], rsi
0x140047b10  lea     rcx, [rbp+arg_18]
0x140047b14  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047b19  lea     r8, [rbp+arg_18]
0x140047b1d  mov     rdx, [rbp+pv]
0x140047b21  mov     ecx, [rbp+arg_0]
0x140047b24  call    cs:__imp_SRDictionaryToPropertySet
0x140047b2a  mov     ebx, eax
0x140047b2c  test    eax, eax
0x140047b2e  jns     short loc_140047B54
0x140047b30  mov     rcx, [rbp+18h]; this
0x140047b34  mov     r9d, eax; char *
0x140047b37  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x140047b3e  mov     edx, 76h ; 'v'; void *
0x140047b43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047b48  nop
0x140047b49  lea     rcx, [rbp+arg_18]
0x140047b4d  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047b52  jmp     short loc_140047AF2
0x140047b54  mov     [rbp+var_38], rsi
0x140047b58  lea     rdx, [rbp+var_38]
0x140047b5c  lea     rcx, [rbp+arg_18]
0x140047b60  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x140047b65  mov     ebx, eax
0x140047b67  test    eax, eax
0x140047b69  jns     short loc_140047B8F
0x140047b6b  mov     rcx, [rbp+18h]; this
0x140047b6f  mov     r9d, eax; char *
0x140047b72  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x140047b79  mov     edx, 79h ; 'y'; void *
0x140047b7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047b83  nop
0x140047b84  lea     rcx, [rbp+var_38]
0x140047b88  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047b8d  jmp     short loc_140047B49
0x140047b8f  mov     [rbp+var_40], rsi
0x140047b93  lea     rcx, [rbp+var_40]
0x140047b97  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047b9c  lea     r8, [rbp+var_40]
0x140047ba0  mov     rdx, [rbp+var_38]
0x140047ba4  call    ?GetChildElement@StateRepoHelper@@YAJPEB_WPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAPEAU2345@@Z; StateRepoHelper::GetChildElement(wchar_t const *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x140047ba9  mov     ebx, eax
0x140047bab  test    eax, eax
0x140047bad  jns     short loc_140047BD3
0x140047baf  mov     edx, 7Dh ; '}'; void *
0x140047bb4  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x140047bbb  mov     r9d, ebx; char *
0x140047bbe  mov     rcx, [rbp+18h]; this
0x140047bc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047bc7  nop
0x140047bc8  lea     rcx, [rbp+var_40]
0x140047bcc  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047bd1  jmp     short loc_140047B84
0x140047bd3  mov     [rbp+var_30], rdi
0x140047bd7  lea     r8, [rbp+var_30]
0x140047bdb  mov     rdx, [rbp+var_40]
0x140047bdf  call    StateRepoHelper__ForEachChildElement__lambda_094ae5f9b4fc1013eabe3ab3e7d83e48___
0x140047be4  mov     ebx, eax
0x140047be6  test    eax, eax
0x140047be8  jns     short loc_140047BF1
0x140047bea  mov     edx, 8Eh
0x140047bef  jmp     short loc_140047BB4
0x140047bf1  lea     rcx, [rbp+var_40]
0x140047bf5  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047bfa  nop
0x140047bfb  lea     rcx, [rbp+var_38]
0x140047bff  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047c04  nop
0x140047c05  lea     rcx, [rbp+arg_18]
0x140047c09  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047c0e  nop
0x140047c0f  mov     rcx, [rbp+pv]; pv
0x140047c13  mov     [rbp+pv], rsi
0x140047c17  test    rcx, rcx
0x140047c1a  jz      short loc_140047C22
0x140047c1c  call    cs:__imp_CoTaskMemFree
0x140047c22  xor     eax, eax
0x140047c24  mov     rbx, [rsp+60h+arg_8]
0x140047c2c  add     rsp, 60h
0x140047c30  pop     rdi
0x140047c31  pop     rsi
0x140047c32  pop     rbp
0x140047c33  retn
```
