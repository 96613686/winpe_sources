# StateRepoHelper::ForEachExtensionOnUser__lambda_a26f3ae5294048737c9c80dce769eb96___

- ea: `0x140047874`
- end: `0x140047a7a`
- name: `StateRepoHelper::ForEachExtensionOnUser__lambda_a26f3ae5294048737c9c80dce769eb96___`
- size: `518`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140043630`

## callees

- `0x140005240`
- `0x140028044`
- `0x140041500`
- `0x140047408`
- `0x140047874`
- `0x140047a80`
- `0x140047c3c`
- `0x140048208`
- `0x140070010`

## string_xrefs

- `0x1400478ef`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x140047952`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x140047a08`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x140047a2b`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x1400478a0`: `windows.searchProtocolHandler`
- `0x1400478c5`: `Windows.Internal.StateRepository.ApplicationExtension`

## pseudocode

```c
__int64 __fastcall StateRepoHelper::ForEachExtensionOnUser__lambda_a26f3ae5294048737c9c80dce769eb96___(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  unsigned int i; // esi
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, const wchar_t **); // rbx
  int v14; // eax
  int v15; // eax
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  int v19; // [rsp+20h] [rbp-39h]
  __int64 v20; // [rsp+30h] [rbp-29h] BYREF
  const wchar_t *v21; // [rsp+38h] [rbp-21h] BYREF
  unsigned int v22; // [rsp+40h] [rbp-19h] BYREF
  __int64 v23; // [rsp+48h] [rbp-11h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  __int64 v26; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v24[1] = -2;
  v21 = L"windows.searchProtocolHandler";
  v23 = 0;
  v26 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.ApplicationExtension",
    0x36u,
    0x35u);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>>(
         v26,
         &v23);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)v4,
      v19);
    goto LABEL_18;
  }
  v20 = 0;
  v6 = v23;
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v23 + 160LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v20);
  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v21);
  v9 = v7(v6, 0, *(_QWORD *)(v8 + 24), &v20);
  v5 = v9;
  if ( v9 < 0 )
  {
    v10 = 157;
    goto LABEL_5;
  }
  v22 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v20 + 56LL))(v20, &v22);
  v5 = v9;
  if ( v9 < 0 )
  {
    v10 = 160;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)v9,
      v19);
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v20);
    goto LABEL_18;
  }
  for ( i = 0; i < v22; ++i )
  {
    v21 = 0;
    v12 = v20;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t **))(*(_QWORD *)v20 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v21);
    v14 = v13(v12, i, &v21);
    v5 = v14;
    if ( v14 < 0 )
    {
      v16 = (unsigned int)v14;
      v17 = 166;
      goto LABEL_16;
    }
    v24[0] = *a3;
    v15 = StateRepoHelper::ForEachSearchProtocolHandler__lambda_3922738b78a3dc4c77f3f6a2e5a0db54___(v21, v24);
    v5 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
        (const char *)(unsigned int)v15,
        v19);
      v16 = v5;
      v17 = 169;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
        (const char *)v16,
        v19);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v21);
      goto LABEL_6;
    }
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v21);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v20);
  v5 = 0;
LABEL_18:
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(&v23);
  return v5;
}

```

## disassembly

```asm
0x140047874  push    rbp
0x140047876  push    rbx
0x140047877  push    rsi
0x140047878  push    rdi
0x140047879  push    r14
0x14004787b  lea     rbp, [rsp-37h]
0x140047880  sub     rsp, 90h
0x140047887  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x14004788f  mov     rax, cs:__security_cookie
0x140047896  xor     rax, rsp
0x140047899  mov     [rbp+57h+var_30], rax
0x14004789d  mov     r14, r8
0x1400478a0  lea     rax, aWindowsSearchp; "windows.searchProtocolHandler"
0x1400478a7  mov     [rbp+57h+var_78], rax
0x1400478ab  mov     [rbp+57h+var_68], 0
0x1400478b3  mov     [rbp+57h+var_38], 0
0x1400478bb  mov     r9d, 35h ; '5'; unsigned int
0x1400478c1  lea     r8d, [r9+1]; unsigned int
0x1400478c5  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationExtension@@3QB_WB; "Windows.Internal.StateRepository.Applic"...
0x1400478cc  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1400478d0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x1400478d5  lea     rdx, [rbp+57h+var_68]
0x1400478d9  mov     rcx, [rbp+57h+var_38]
0x1400478dd  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>>)
0x1400478e2  mov     ebx, eax
0x1400478e4  test    eax, eax
0x1400478e6  jns     short loc_140047905
0x1400478e8  mov     rcx, [rbp+5Fh]; this
0x1400478ec  mov     r9d, eax; char *
0x1400478ef  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400478f6  mov     edx, 99h; void *
0x1400478fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047900  jmp     loc_140047A55
0x140047905  mov     [rbp+57h+var_80], 0
0x14004790d  mov     rdi, [rbp+57h+var_68]
0x140047911  mov     rax, [rdi]
0x140047914  mov     rbx, [rax+0A0h]
0x14004791b  lea     rcx, [rbp+57h+var_80]
0x14004791f  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047924  lea     rdx, [rbp+57h+var_78]
0x140047928  lea     rcx, [rbp+57h+hstringHeader]
0x14004792c  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x140047931  nop
0x140047932  lea     r9, [rbp+57h+var_80]
0x140047936  mov     r8, [rax+18h]
0x14004793a  xor     edx, edx
0x14004793c  mov     rcx, rdi
0x14004793f  mov     rax, rbx
0x140047942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047947  mov     ebx, eax
0x140047949  test    eax, eax
0x14004794b  jns     short loc_140047974
0x14004794d  mov     edx, 9Dh; void *
0x140047952  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x140047959  mov     r9d, eax; char *
0x14004795c  mov     rcx, [rbp+5Fh]; this
0x140047960  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047965  nop
0x140047966  lea     rcx, [rbp+57h+var_80]
0x14004796a  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x14004796f  jmp     loc_140047A55
0x140047974  mov     [rbp+57h+var_70], 0
0x14004797b  mov     rcx, [rbp+57h+var_80]
0x14004797f  mov     rax, [rcx]
0x140047982  lea     rdx, [rbp+57h+var_70]
0x140047986  mov     rax, [rax+38h]
0x14004798a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004798f  mov     ebx, eax
0x140047991  test    eax, eax
0x140047993  jns     short loc_14004799C
0x140047995  mov     edx, 0A0h
0x14004799a  jmp     short loc_140047952
0x14004799c  xor     esi, esi
0x14004799e  cmp     esi, [rbp+57h+var_70]
0x1400479a1  jnb     loc_140047A4A
0x1400479a7  mov     [rbp+57h+var_78], 0
0x1400479af  mov     rdi, [rbp+57h+var_80]
0x1400479b3  mov     rax, [rdi]
0x1400479b6  mov     rbx, [rax+30h]
0x1400479ba  lea     rcx, [rbp+57h+var_78]
0x1400479be  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x1400479c3  lea     r8, [rbp+57h+var_78]
0x1400479c7  mov     edx, esi
0x1400479c9  mov     rcx, rdi
0x1400479cc  mov     rax, rbx
0x1400479cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400479d4  mov     ebx, eax
0x1400479d6  test    eax, eax
0x1400479d8  js      short loc_140047A23
0x1400479da  mov     rax, [r14]
0x1400479dd  mov     [rbp+57h+var_60], rax
0x1400479e1  lea     rdx, [rbp+57h+var_60]
0x1400479e5  mov     rcx, [rbp+57h+var_78]
0x1400479e9  call    StateRepoHelper__ForEachSearchProtocolHandler__lambda_3922738b78a3dc4c77f3f6a2e5a0db54___
0x1400479ee  mov     ebx, eax
0x1400479f0  test    eax, eax
0x1400479f2  js      short loc_140047A01
0x1400479f4  lea     rcx, [rbp+57h+var_78]
0x1400479f8  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x1400479fd  inc     esi
0x1400479ff  jmp     short loc_14004799E
0x140047a01  mov     rcx, [rbp+5Fh]; this
0x140047a05  mov     r9d, ebx; char *
0x140047a08  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x140047a0f  mov     edx, 0CFh; void *
0x140047a14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047a19  mov     r9d, ebx
0x140047a1c  mov     edx, 0A9h
0x140047a21  jmp     short loc_140047A2B
0x140047a23  mov     r9d, eax; char *
0x140047a26  mov     edx, 0A6h; void *
0x140047a2b  lea     r8, aOnecoreuapBase_55; "onecoreuap\\base\\appmodel\\search\\com"...
0x140047a32  mov     rcx, [rbp+5Fh]; this
0x140047a36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047a3b  nop
0x140047a3c  lea     rcx, [rbp+57h+var_78]
0x140047a40  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047a45  jmp     loc_140047966
0x140047a4a  lea     rcx, [rbp+57h+var_80]
0x140047a4e  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047a53  xor     ebx, ebx
0x140047a55  lea     rcx, [rbp+57h+var_68]
0x140047a59  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x140047a5e  mov     eax, ebx
0x140047a60  mov     rcx, [rbp+57h+var_30]
0x140047a64  xor     rcx, rsp; StackCookie
0x140047a67  call    __security_check_cookie
0x140047a6c  add     rsp, 90h
0x140047a73  pop     r14
0x140047a75  pop     rdi
0x140047a76  pop     rsi
0x140047a77  pop     rbx
0x140047a78  pop     rbp
0x140047a79  retn
```
