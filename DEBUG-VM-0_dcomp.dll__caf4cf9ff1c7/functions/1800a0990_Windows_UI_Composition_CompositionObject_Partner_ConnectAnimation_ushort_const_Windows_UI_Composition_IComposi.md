# Windows::UI::Composition::CompositionObject::Partner::ConnectAnimation(ushort const *,Windows::UI::Composition::ICompositionAnimation *,Windows::UI::Composition::ICompositionAnimatorPartner * *)

- ea: `0x1800a0990`
- end: `0x1800a0c75`
- name: `?ConnectAnimation@Partner@CompositionObject@Composition@UI@Windows@@UEAAJPEBGPEAUICompositionAnimation@345@PEAPEAUICompositionAnimatorPartner@345@@Z`
- size: `741`
- prototype: `int(Windows::UI::Composition::CompositionObject::Partner *__hidden this, const unsigned __int16 *, struct Windows::UI::Composition::ICompositionAnimation *, struct Windows::UI::Composition::ICompositionAnimatorPartner **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800093f4`
- `0x18000bc00`
- `0x18000f810`
- `0x18000f850`
- `0x180012da0`
- `0x180013528`
- `0x1800171b0`
- `0x180036f90`
- `0x1800a0990`
- `0x1800e77ac`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a0a3f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a0a55`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a0a3f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a0a55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a0a25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a0a25`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800a0a6c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800a0c20`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800a0a6c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800a0c20`

## string_xrefs

- `0x1800a0a61`: `The given object has already been closed / disposed and may no longer be used.`
- `0x1800a0c12`: `The given object has already been closed / disposed and may no longer be used.`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionObject::Partner::ConnectAnimation(
        Windows::UI::Composition::CompositionObject::Partner *this,
        const unsigned __int16 *a2,
        struct Windows::UI::Composition::ICompositionAnimation *a3,
        struct Windows::UI::Composition::ICompositionAnimatorPartner **a4)
{
  char *v4; // r12
  Microsoft::WRL2::ContextSession *v7; // r15
  struct Windows::UI::Composition::ICompositionAnimatorPartner *v8; // rbx
  unsigned __int64 v9; // rdi
  unsigned int v10; // eax
  UINT32 v11; // edx
  HRESULT v12; // eax
  unsigned int v13; // edi
  Microsoft::WRL2::NestableRuntimeClass *v14; // rcx
  HSTRING v16; // r13
  struct Windows::UI::Composition::ICompositionAnimation *v17; // r14
  __int64 (__fastcall **v18)(struct Windows::UI::Composition::ICompositionAnimation *, GUID *, struct Windows::UI::Composition::ICompositionAnimation **); // rax
  int v19; // eax
  __int64 v20; // rdx
  void **i; // rax
  __int64 v22; // rax
  __int64 (__fastcall *v23)(char *, HSTRING, struct Windows::UI::Composition::ICompositionAnimation *, _QWORD, Microsoft::WRL2::NestableRuntimeClass **); // rdi
  int v24; // eax
  Microsoft::WRL2::NestableRuntimeClass *v25; // rsi
  struct Windows::UI::Composition::ICompositionAnimation *v26; // rcx
  __int64 (__fastcall **v27)(struct Windows::UI::Composition::ICompositionAnimation *, GUID *, struct Windows::UI::Composition::ICompositionAnimation **); // rax
  const wchar_t *v28; // r8
  struct Windows::UI::Composition::ICompositionAnimation *v29; // [rsp+30h] [rbp-39h] BYREF
  Microsoft::WRL2::NestableRuntimeClass *v30; // [rsp+38h] [rbp-31h] BYREF
  __int64 v31; // [rsp+40h] [rbp-29h] BYREF
  struct Windows::UI::Composition::ICompositionAnimatorPartner **v32; // [rsp+48h] [rbp-21h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-19h] BYREF
  HSTRING string; // [rsp+68h] [rbp-1h] BYREF

  v4 = (char *)this - 112;
  v32 = a4;
  *a4 = 0;
  v7 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)this - 11);
  Microsoft::WRL2::ContextSession::BeginApiEntry(v7);
  if ( (v4[48] & 2) != 0 )
  {
    v8 = 0;
    v29 = 0;
    v31 = 0;
    v9 = -1;
    v30 = 0;
    string = 0;
    do
      ++v9;
    while ( a2[v9] );
    if ( v9 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v10 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v9);
    v11 = v10 - 1;
    if ( (unsigned int)v9 < v10 )
      v11 = v9;
    v12 = WindowsCreateStringReference(a2, v11, &hstringHeader, &string);
    if ( v12 < 0 )
    {
      RaiseException(v12, 1u, 0, 0);
      __debugbreak();
    }
    v16 = string;
    string = 0;
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v29);
    v17 = 0;
    if ( a3 )
    {
      v18 = *(__int64 (__fastcall ***)(struct Windows::UI::Composition::ICompositionAnimation *, GUID *, struct Windows::UI::Composition::ICompositionAnimation **))a3;
      v29 = 0;
      v19 = (*v18)(a3, &GUID_7d099463_1e1d_4495_828a_d36bd8ebeeb7, &v29);
      v20 = 0;
      v13 = v19;
      if ( v19 < 0 )
      {
        v26 = v29;
        if ( !v29 )
        {
LABEL_33:
          DoStackCaptureDirect(v13, 0x4D0u);
          v14 = v30;
          if ( !v30 )
            goto LABEL_16;
          v30 = 0;
          goto LABEL_15;
        }
        v29 = 0;
        v27 = *(__int64 (__fastcall ***)(struct Windows::UI::Composition::ICompositionAnimation *, GUID *, struct Windows::UI::Composition::ICompositionAnimation **))v26;
      }
      else
      {
        a3 = v29;
        for ( i = (void **)*((_QWORD *)v29 + 1); ; i = (void **)*i )
        {
          if ( !i )
          {
            if ( v29 )
            {
              v29 = 0;
              (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionAnimation *))(*(_QWORD *)a3 + 16LL))(a3);
            }
            v13 = -2147467262;
            goto LABEL_33;
          }
          if ( &Windows::UI::Composition::CompositionAnimation::s_InterfaceType == (_UNKNOWN *)i )
            break;
        }
        v29 = 0;
        if ( (*((_BYTE *)a3 + 48) & 2) != 0 )
        {
          if ( !*((_QWORD *)a3 + 3) )
            Microsoft::WRL2::FailFast::Unexpected("No session");
          if ( *((Microsoft::WRL2::ContextSession **)a3 + 3) == v7 )
          {
            v17 = a3;
            goto LABEL_27;
          }
          v28 = L"The caller is not allowed to perform this operation on this object.";
          v13 = -2147024891;
        }
        else
        {
          v28 = L"The given object has already been closed / disposed and may no longer be used.";
          v13 = -2147483629;
        }
        RoOriginateErrorW(v13, 0, v28);
        v27 = *(__int64 (__fastcall ***)(struct Windows::UI::Composition::ICompositionAnimation *, GUID *, struct Windows::UI::Composition::ICompositionAnimation **))a3;
        v26 = a3;
      }
      ((void (__fastcall *)(struct Windows::UI::Composition::ICompositionAnimation *, __int64))v27[2])(v26, v20);
      goto LABEL_33;
    }
LABEL_27:
    v22 = *(_QWORD *)v4;
    v29 = a3;
    v23 = *(__int64 (__fastcall **)(char *, HSTRING, struct Windows::UI::Composition::ICompositionAnimation *, _QWORD, Microsoft::WRL2::NestableRuntimeClass **))(v22 + 120);
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v30);
    v24 = v23(v4, v16, v17, 0, &v30);
    v13 = v24;
    if ( v24 < 0 )
    {
      DoStackCaptureDirect(v24, 0x4D2u);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v31);
      Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v30);
      Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v29);
      goto LABEL_16;
    }
    v25 = v30;
    if ( v30 )
    {
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v31);
      v8 = (Microsoft::WRL2::NestableRuntimeClass *)((char *)v25 + 152);
      Microsoft::WRL2::NestableRuntimeClass::InternalAddRef(v25);
      v25 = v30;
    }
    v13 = 0;
    *v32 = v8;
    if ( v25 )
    {
      v30 = 0;
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v25);
    }
    if ( v17 )
    {
      v14 = v17;
LABEL_15:
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v14);
    }
  }
  else
  {
    v13 = -2147483629;
    RoOriginateErrorW(
      2147483667LL,
      0,
      L"The given object has already been closed / disposed and may no longer be used.");
  }
LABEL_16:
  Microsoft::WRL2::ContextSession::EndApiEntry(v7);
  return v13;
}

```

## disassembly

```asm
0x1800a0990  push    rbp
0x1800a0992  push    rbx
0x1800a0993  push    rsi
0x1800a0994  push    rdi
0x1800a0995  push    r12
0x1800a0997  push    r13
0x1800a0999  push    r14
0x1800a099b  push    r15
0x1800a099d  lea     rbp, [rsp-1Fh]
0x1800a09a2  sub     rsp, 88h
0x1800a09a9  mov     rax, cs:__security_cookie
0x1800a09b0  xor     rax, rsp
0x1800a09b3  mov     [rbp+57h+var_50], rax
0x1800a09b7  lea     r12, [rcx-70h]
0x1800a09bb  mov     [rbp+57h+var_78], r9
0x1800a09bf  xor     r13d, r13d
0x1800a09c2  mov     rsi, r8
0x1800a09c5  mov     [r9], r13
0x1800a09c8  mov     r14, rdx
0x1800a09cb  mov     r15, [r12+18h]
0x1800a09d0  mov     rcx, r15; this
0x1800a09d3  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x1800a09d8  test    byte ptr [r12+30h], 2
0x1800a09de  jz      short loc_1800A0A5C
0x1800a09e0  mov     ebx, r13d
0x1800a09e3  mov     [rbp+57h+var_90], r13
0x1800a09e7  mov     [rbp+57h+var_80], rbx
0x1800a09eb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a09ef  mov     [rbp+57h+var_88], r13
0x1800a09f3  mov     [rbp+57h+string], r13
0x1800a09f7  inc     rdi
0x1800a09fa  cmp     [r14+rdi*2], r13w
0x1800a09ff  jnz     short loc_1800A09F7
0x1800a0a01  mov     eax, 0FFFFFFFFh
0x1800a0a06  cmp     rdi, rax
0x1800a0a09  ja      short loc_1800A0A46
0x1800a0a0b  mov     ecx, edi; unsigned int
0x1800a0a0d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800a0a12  cmp     edi, eax
0x1800a0a14  lea     r9, [rbp+57h+string]; string
0x1800a0a18  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800a0a1c  mov     rcx, r14; sourceString
0x1800a0a1f  lea     edx, [rax-1]
0x1800a0a22  cmovb   edx, edi; length
0x1800a0a25  call    cs:__imp_WindowsCreateStringReference
0x1800a0a2b  test    eax, eax
0x1800a0a2d  jns     loc_1800A0AC5
0x1800a0a33  xor     r9d, r9d; lpArguments
0x1800a0a36  xor     r8d, r8d; nNumberOfArguments
0x1800a0a39  mov     ecx, eax; dwExceptionCode
0x1800a0a3b  lea     edx, [r9+1]; dwExceptionFlags
0x1800a0a3f  call    cs:__imp_RaiseException
0x1800a0a45  int     3; Trap to Debugger
0x1800a0a46  xor     r9d, r9d; lpArguments
0x1800a0a49  xor     r8d, r8d; nNumberOfArguments
0x1800a0a4c  mov     ecx, 80070216h; dwExceptionCode
0x1800a0a51  lea     edx, [r9+1]; dwExceptionFlags
0x1800a0a55  call    cs:__imp_RaiseException
0x1800a0a5b  int     3; Trap to Debugger
0x1800a0a5c  mov     edi, 80000013h
0x1800a0a61  lea     r8, aTheGivenObject; "The given object has already been close"...
0x1800a0a68  mov     ecx, edi
0x1800a0a6a  xor     edx, edx
0x1800a0a6c  call    cs:__imp_RoOriginateErrorW
0x1800a0a72  jmp     short loc_1800A0A9B
0x1800a0a74  mov     rax, [rbp+57h+var_78]
0x1800a0a78  xor     edi, edi
0x1800a0a7a  mov     [rax], rbx
0x1800a0a7d  test    rsi, rsi
0x1800a0a80  jz      short loc_1800A0A8E
0x1800a0a82  mov     rcx, rsi; this
0x1800a0a85  mov     [rbp+57h+var_88], rdi
0x1800a0a89  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x1800a0a8e  test    r14, r14
0x1800a0a91  jz      short loc_1800A0A9B
0x1800a0a93  mov     rcx, r14; this
0x1800a0a96  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x1800a0a9b  mov     rcx, r15; this
0x1800a0a9e  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x1800a0aa3  mov     eax, edi
0x1800a0aa5  mov     rcx, [rbp+57h+var_50]
0x1800a0aa9  xor     rcx, rsp; StackCookie
0x1800a0aac  call    __security_check_cookie
0x1800a0ab1  add     rsp, 88h
0x1800a0ab8  pop     r15
0x1800a0aba  pop     r14
0x1800a0abc  pop     r13
0x1800a0abe  pop     r12
0x1800a0ac0  pop     rdi
0x1800a0ac1  pop     rsi
0x1800a0ac2  pop     rbx
0x1800a0ac3  pop     rbp
0x1800a0ac4  retn
0x1800a0ac5  mov     r13, [rbp+57h+string]
0x1800a0ac9  lea     rcx, [rbp+57h+var_90]; void *
0x1800a0acd  mov     [rbp+57h+string], rbx
0x1800a0ad1  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x1800a0ad6  xor     r14d, r14d
0x1800a0ad9  test    rsi, rsi
0x1800a0adc  jz      short loc_1800A0B4E
0x1800a0ade  mov     rax, [rsi]
0x1800a0ae1  lea     r8, [rbp+57h+var_90]
0x1800a0ae5  lea     rdx, _GUID_7d099463_1e1d_4495_828a_d36bd8ebeeb7
0x1800a0aec  mov     [rbp+57h+var_90], rbx
0x1800a0af0  mov     rcx, rsi
0x1800a0af3  mov     rax, [rax]
0x1800a0af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0afb  xor     edx, edx
0x1800a0afd  mov     edi, eax
0x1800a0aff  test    eax, eax
0x1800a0b01  js      loc_1800A0BF7
0x1800a0b07  mov     rsi, [rbp+57h+var_90]
0x1800a0b0b  mov     rax, [rsi+8]
0x1800a0b0f  test    rax, rax
0x1800a0b12  jz      loc_1800A0BB8
0x1800a0b18  lea     rcx, ?s_InterfaceType@CompositionAnimation@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; Microsoft::WRL2::NestableRuntimeClass::InterfaceType const Windows::UI::Composition::CompositionAnimation::s_InterfaceType
0x1800a0b1f  cmp     rcx, rax
0x1800a0b22  jz      short loc_1800A0B29
0x1800a0b24  mov     rax, [rax]
0x1800a0b27  jmp     short loc_1800A0B0F
0x1800a0b29  mov     [rbp+57h+var_90], rdx
0x1800a0b2d  test    byte ptr [rsi+30h], 2
0x1800a0b31  jz      loc_1800A0C12
0x1800a0b37  cmp     [rsi+18h], rdx
0x1800a0b3b  jz      loc_1800A0C3C
0x1800a0b41  cmp     [rsi+18h], r15
0x1800a0b45  jnz     loc_1800A0C2E
0x1800a0b4b  mov     r14, rsi
0x1800a0b4e  mov     rax, [r12]
0x1800a0b52  lea     rcx, [rbp+57h+var_88]; void *
0x1800a0b56  mov     [rbp+57h+var_90], rsi
0x1800a0b5a  mov     rdi, [rax+78h]
0x1800a0b5e  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x1800a0b63  lea     rax, [rbp+57h+var_88]
0x1800a0b67  xor     r9d, r9d
0x1800a0b6a  mov     [rsp+0C0h+var_A0], rax
0x1800a0b6f  mov     r8, r14
0x1800a0b72  mov     rax, rdi
0x1800a0b75  mov     rdx, r13
0x1800a0b78  mov     rcx, r12
0x1800a0b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0b80  mov     edi, eax
0x1800a0b82  test    eax, eax
0x1800a0b84  js      loc_1800A0C49
0x1800a0b8a  mov     rsi, [rbp+57h+var_88]
0x1800a0b8e  test    rsi, rsi
0x1800a0b91  jz      loc_1800A0A74
0x1800a0b97  lea     rcx, [rbp+57h+var_80]
0x1800a0b9b  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1800a0ba0  mov     rcx, rsi; this
0x1800a0ba3  lea     rbx, [rsi+98h]
0x1800a0baa  call    ?InternalAddRef@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalAddRef(void)
0x1800a0baf  mov     rsi, [rbp+57h+var_88]
0x1800a0bb3  jmp     loc_1800A0A74
0x1800a0bb8  test    rsi, rsi
0x1800a0bbb  jz      short loc_1800A0BD0
0x1800a0bbd  mov     [rbp+57h+var_90], rdx
0x1800a0bc1  mov     rcx, rsi
0x1800a0bc4  mov     rax, [rsi]
0x1800a0bc7  mov     rax, [rax+10h]
0x1800a0bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0bd0  mov     edi, 80004002h
0x1800a0bd5  mov     edx, 4D0h; unsigned int
0x1800a0bda  mov     ecx, edi; int
0x1800a0bdc  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x1800a0be1  mov     rcx, [rbp+57h+var_88]
0x1800a0be5  test    rcx, rcx
0x1800a0be8  jz      loc_1800A0A9B
0x1800a0bee  mov     [rbp+57h+var_88], rbx
0x1800a0bf2  jmp     loc_1800A0A96
0x1800a0bf7  mov     rcx, [rbp+57h+var_90]
0x1800a0bfb  test    rcx, rcx
0x1800a0bfe  jz      short loc_1800A0BD5
0x1800a0c00  mov     [rbp+57h+var_90], rdx
0x1800a0c04  mov     rax, [rcx]
0x1800a0c07  mov     rax, [rax+10h]
0x1800a0c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0c10  jmp     short loc_1800A0BD5
0x1800a0c12  lea     r8, aTheGivenObject; "The given object has already been close"...
0x1800a0c19  mov     edi, 80000013h
0x1800a0c1e  mov     ecx, edi
0x1800a0c20  call    cs:__imp_RoOriginateErrorW
0x1800a0c26  mov     rax, [rsi]
0x1800a0c29  mov     rcx, rsi
0x1800a0c2c  jmp     short loc_1800A0C07
0x1800a0c2e  lea     r8, aTheCallerIsNot; "The caller is not allowed to perform th"...
0x1800a0c35  mov     edi, 80070005h
0x1800a0c3a  jmp     short loc_1800A0C1E
0x1800a0c3c  lea     rcx, aNoSession; "No session"
0x1800a0c43  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x1800a0c49  mov     edx, 4D2h; unsigned int
0x1800a0c4e  mov     ecx, eax; int
0x1800a0c50  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x1800a0c55  lea     rcx, [rbp+57h+var_80]
0x1800a0c59  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1800a0c5e  lea     rcx, [rbp+57h+var_88]; void *
0x1800a0c62  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x1800a0c67  lea     rcx, [rbp+57h+var_90]; void *
0x1800a0c6b  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x1800a0c70  jmp     loc_1800A0A9B
```
