# Windows::Networking::UX::Internal::CategoryBase::Initialize(_GUID const &,ushort const *)

- ea: `0x180004980`
- end: `0x180004c0b`
- name: `?Initialize@CategoryBase@Internal@UX@Networking@Windows@@IEAAJAEBU_GUID@@PEBG@Z`
- size: `651`
- prototype: `int(Windows::Networking::UX::Internal::CategoryBase *__hidden this, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800069f8`

## callees

- `0x180002150`
- `0x180004980`
- `0x1800050c0`
- `0x180005be0`
- `0x180005c80`
- `0x180005fc0`
- `0x180020988`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800049fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004a76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800049fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004a76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180004a0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180004a87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180004a0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180004a87`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::CategoryBase::Initialize(
        Windows::Networking::UX::Internal::CategoryBase *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3)
{
  HSTRING *v6; // r14
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rbx
  HRESULT String; // eax
  unsigned int v10; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  HSTRING *v13; // rbx
  HRESULT v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v18)(_QWORD, GUID *, char *); // rdi
  int v19; // eax
  __int64 (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rdx
  __int64 (__fastcall ***v22)(_QWORD, GUID *, char *); // [rsp+80h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_426275660baf32778194b91bb4cd93ce_Traceguids);
  *(struct _GUID *)((char *)this + 24) = *a2;
  v6 = (HSTRING *)((char *)this + 40);
  v7 = -1;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    if ( v8 > 0xFFFFFFFF )
    {
      v10 = -2147024362;
      goto LABEL_12;
    }
    WindowsDeleteString(*v6);
    *v6 = 0;
    String = WindowsCreateString(a3, v8, (HSTRING *)this + 5);
  }
  else
  {
    String = Microsoft::WRL::Wrappers::HString::Set(
               (Windows::Networking::UX::Internal::CategoryBase *)((char *)this + 40),
               &sourceString,
               0);
  }
  v10 = String;
LABEL_12:
  if ( (v10 & 0x80000000) == 0 )
  {
    v13 = (HSTRING *)((char *)this + 48);
    if ( a3 )
    {
      do
        ++v7;
      while ( a3[v7] );
      if ( v7 > 0xFFFFFFFF )
      {
        v10 = -2147024362;
        goto LABEL_23;
      }
      WindowsDeleteString(*v13);
      *v13 = 0;
      v14 = WindowsCreateString(a3, v7, (HSTRING *)this + 6);
    }
    else
    {
      v14 = Microsoft::WRL::Wrappers::HString::Set(
              (Windows::Networking::UX::Internal::CategoryBase *)((char *)this + 48),
              &sourceString,
              0);
    }
    v10 = v14;
LABEL_23:
    if ( (v10 & 0x80000000) != 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v10;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_40;
      v12 = 12;
      goto LABEL_27;
    }
    v22 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    v16 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IAvailableNetwork,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IAvailableNetwork *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IAvailableNetwork *>>>(
            v15,
            &v22);
    if ( v16 < 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_426275660baf32778194b91bb4cd93ce_Traceguids,
          (unsigned int)v16,
          v16);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      v10 = -2147024882;
      goto LABEL_38;
    }
    v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
    v18 = **v22;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 96);
    v19 = v18(v17, &GUID_0a0f6e0b_65ae_5f3f_941b_3597508526e9, (char *)this + 96);
    v10 = v19;
    if ( v19 < 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_38:
        v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
        if ( v22 )
        {
          v22 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v20)[2])(v20);
          v11 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_40;
      }
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_426275660baf32778194b91bb4cd93ce_Traceguids,
        (unsigned int)v19,
        v19);
    }
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_38;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v12 = 11;
LABEL_27:
    WPP_SF_dd(v11[2], v12, &WPP_426275660baf32778194b91bb4cd93ce_Traceguids, v10, v10);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_40:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 )
    WPP_SF_d(v11[2], 15, &WPP_426275660baf32778194b91bb4cd93ce_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180004980  push    rbx
0x180004982  push    rbp
0x180004983  push    rsi
0x180004984  push    rdi
0x180004985  push    r12
0x180004987  push    r13
0x180004989  push    r14
0x18000498b  push    r15
0x18000498d  sub     rsp, 38h
0x180004991  mov     rsi, r8
0x180004994  mov     rbx, rdx
0x180004997  mov     rbp, rcx
0x18000499a  lea     r12, WPP_GLOBAL_Control
0x1800049a1  lea     r13, WPP_426275660baf32778194b91bb4cd93ce_Traceguids
0x1800049a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049af  cmp     rcx, r12
0x1800049b2  jz      short loc_1800049CB
0x1800049b4  test    byte ptr [rcx+1Ch], 40h
0x1800049b8  jz      short loc_1800049CB
0x1800049ba  mov     edx, 0Ah
0x1800049bf  mov     r8, r13
0x1800049c2  mov     rcx, [rcx+10h]
0x1800049c6  call    WPP_SF_
0x1800049cb  movups  xmm0, xmmword ptr [rbx]
0x1800049ce  movdqu  xmmword ptr [rbp+18h], xmm0
0x1800049d3  lea     r14, [rbp+28h]
0x1800049d7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800049db  mov     eax, 0FFFFFFFFh
0x1800049e0  xor     r15d, r15d
0x1800049e3  test    rsi, rsi
0x1800049e6  jz      short loc_180004A1D
0x1800049e8  mov     rbx, rdi
0x1800049eb  inc     rbx
0x1800049ee  cmp     [rsi+rbx*2], r15w
0x1800049f3  jnz     short loc_1800049EB
0x1800049f5  cmp     rbx, rax
0x1800049f8  ja      short loc_180004A16
0x1800049fa  mov     rcx, [r14]; string
0x1800049fd  call    cs:__imp_WindowsDeleteString
0x180004a03  mov     [r14], r15
0x180004a06  mov     edx, ebx; length
0x180004a08  mov     r8, r14; string
0x180004a0b  mov     rcx, rsi; sourceString
0x180004a0e  call    cs:__imp_WindowsCreateString
0x180004a14  jmp     short loc_180004A2F
0x180004a16  mov     ebx, 80070216h
0x180004a1b  jmp     short loc_180004A36
0x180004a1d  xor     r8d, r8d; unsigned int
0x180004a20  lea     rdx, sourceString; unsigned __int16 *
0x180004a27  mov     rcx, r14; this
0x180004a2a  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180004a2f  mov     ebx, eax
0x180004a31  mov     eax, 0FFFFFFFFh
0x180004a36  test    ebx, ebx
0x180004a38  jns     short loc_180004A5B
0x180004a3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a41  cmp     rcx, r12
0x180004a44  jz      loc_180004BF8
0x180004a4a  test    byte ptr [rcx+1Ch], 2
0x180004a4e  jz      loc_180004BD9
0x180004a54  mov     edx, 0Bh
0x180004a59  jmp     short loc_180004ACD
0x180004a5b  lea     rbx, [rbp+30h]
0x180004a5f  test    rsi, rsi
0x180004a62  jz      short loc_180004A96
0x180004a64  inc     rdi
0x180004a67  cmp     [rsi+rdi*2], r15w
0x180004a6c  jnz     short loc_180004A64
0x180004a6e  cmp     rdi, rax
0x180004a71  ja      short loc_180004A8F
0x180004a73  mov     rcx, [rbx]; string
0x180004a76  call    cs:__imp_WindowsDeleteString
0x180004a7c  mov     [rbx], r15
0x180004a7f  mov     edx, edi; length
0x180004a81  mov     r8, rbx; string
0x180004a84  mov     rcx, rsi; sourceString
0x180004a87  call    cs:__imp_WindowsCreateString
0x180004a8d  jmp     short loc_180004AA8
0x180004a8f  mov     ebx, 80070216h
0x180004a94  jmp     short loc_180004AAA
0x180004a96  xor     r8d, r8d; unsigned int
0x180004a99  lea     rdx, sourceString; unsigned __int16 *
0x180004aa0  mov     rcx, rbx; this
0x180004aa3  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180004aa8  mov     ebx, eax
0x180004aaa  test    ebx, ebx
0x180004aac  jns     short loc_180004AEC
0x180004aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ab5  cmp     rcx, r12
0x180004ab8  jz      loc_180004BF8
0x180004abe  test    byte ptr [rcx+1Ch], 2
0x180004ac2  jz      loc_180004BD9
0x180004ac8  mov     edx, 0Ch
0x180004acd  mov     [rsp+78h+var_58], ebx
0x180004ad1  mov     r9d, ebx
0x180004ad4  mov     r8, r13
0x180004ad7  mov     rcx, [rcx+10h]
0x180004adb  call    WPP_SF_dd
0x180004ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ae7  jmp     loc_180004BD9
0x180004aec  mov     [rsp+78h+arg_0], r15
0x180004af4  lea     rcx, [rsp+78h+arg_0]
0x180004afc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180004b01  lea     rdx, [rsp+78h+arg_0]
0x180004b09  call    ??$CreateExternalObjectVector@UIAvailableNetwork@UX@Networking@Windows@@V?$Vector@PEAUIAvailableNetwork@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIAvailableNetwork@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIAvailableNetwork@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@PEAUIAvailableNetwork@UX@Networking@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIAvailableNetwork@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIAvailableNetwork@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIAvailableNetwork@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@PEAUIAvailableNetwork@UX@Networking@Windows@@@6784@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IAvailableNetwork,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IAvailableNetwork *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IAvailableNetwork *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IAvailableNetwork *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IAvailableNetwork *>> * *)
0x180004b0e  test    eax, eax
0x180004b10  jns     short loc_180004B4A
0x180004b12  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b19  cmp     rcx, r12
0x180004b1c  jz      short loc_180004B43
0x180004b1e  test    byte ptr [rcx+1Ch], 2
0x180004b22  jz      short loc_180004B43
0x180004b24  mov     edx, 0Dh
0x180004b29  mov     [rsp+78h+var_58], eax
0x180004b2d  mov     r9d, eax
0x180004b30  mov     r8, r13
0x180004b33  mov     rcx, [rcx+10h]
0x180004b37  call    WPP_SF_dd
0x180004b3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b43  mov     ebx, 8007000Eh
0x180004b48  jmp     short loc_180004BAE
0x180004b4a  mov     rbx, [rsp+78h+arg_0]
0x180004b52  mov     rax, [rbx]
0x180004b55  mov     rdi, [rax]
0x180004b58  lea     rcx, [rbp+60h]
0x180004b5c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180004b61  lea     r8, [rbp+60h]
0x180004b65  lea     rdx, _GUID_0a0f6e0b_65ae_5f3f_941b_3597508526e9
0x180004b6c  mov     rcx, rbx
0x180004b6f  mov     rax, rdi
0x180004b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b77  mov     ebx, eax
0x180004b79  test    eax, eax
0x180004b7b  jns     short loc_180004BA7
0x180004b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b84  cmp     rcx, r12
0x180004b87  jz      short loc_180004BAE
0x180004b89  test    byte ptr [rcx+1Ch], 2
0x180004b8d  jz      short loc_180004BAE
0x180004b8f  mov     edx, 0Eh
0x180004b94  mov     [rsp+78h+var_58], eax
0x180004b98  mov     r9d, eax
0x180004b9b  mov     r8, r13
0x180004b9e  mov     rcx, [rcx+10h]
0x180004ba2  call    WPP_SF_dd
0x180004ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bae  mov     rdx, [rsp+78h+arg_0]
0x180004bb6  test    rdx, rdx
0x180004bb9  jz      short loc_180004BD9
0x180004bbb  mov     [rsp+78h+arg_0], r15
0x180004bc3  mov     rax, [rdx]
0x180004bc6  mov     rcx, rdx
0x180004bc9  mov     rax, [rax+10h]
0x180004bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bd9  cmp     rcx, r12
0x180004bdc  jz      short loc_180004BF8
0x180004bde  test    byte ptr [rcx+1Ch], 40h
0x180004be2  jz      short loc_180004BF8
0x180004be4  mov     edx, 0Fh
0x180004be9  mov     r9d, ebx
0x180004bec  mov     r8, r13
0x180004bef  mov     rcx, [rcx+10h]
0x180004bf3  call    WPP_SF_d
0x180004bf8  mov     eax, ebx
0x180004bfa  add     rsp, 38h
0x180004bfe  pop     r15
0x180004c00  pop     r14
0x180004c02  pop     r13
0x180004c04  pop     r12
0x180004c06  pop     rdi
0x180004c07  pop     rsi
0x180004c08  pop     rbp
0x180004c09  pop     rbx
0x180004c0a  retn
```
