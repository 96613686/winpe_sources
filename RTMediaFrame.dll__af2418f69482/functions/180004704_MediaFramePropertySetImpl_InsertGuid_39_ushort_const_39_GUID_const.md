# MediaFramePropertySetImpl::InsertGuid<39>(ushort const (&)[39],_GUID const &)

- ea: `0x180004704`
- end: `0x180004809`
- name: `??$InsertGuid@$0CH@@MediaFramePropertySetImpl@@AEAAXAEAY0CH@$$CBGAEBU_GUID@@@Z`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b090`

## callees

- `0x1800019c0`
- `0x180004704`
- `0x180005cd0`
- `0x18000c340`
- `0x180026920`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004802`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004802`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180004793`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180004793`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall MediaFramePropertySetImpl::InsertGuid<39>(__int64 a1, const WCHAR *a2, _OWORD *a3)
{
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING_HEADER *, void **); // rbx
  unsigned int v8; // eax
  int v9; // edx
  __int64 v10; // rbx
  void *v11; // rdi
  HRESULT v12; // eax
  unsigned int v13; // eax
  int v14; // edx
  void *v15; // rcx
  char v16[8]; // [rsp+20h] [rbp-40h] BYREF
  void *v17; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF

  v17 = 0;
  v6 = *(_QWORD *)(a1 + 112);
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING_HEADER *, void **))(*(_QWORD *)v6 + 160LL);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v17);
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *a3;
  v8 = v7(v6, &hstringHeader, &v17);
  MF::ThrowIfFailed((MF *)v8, v9);
  v16[0] = 0;
  v10 = *(_QWORD *)(a1 + 104);
  v11 = v17;
  string = 0;
  v12 = WindowsCreateStringReference(a2, 0x26u, &hstringHeader, &string);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x180004808LL);
  }
  v13 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
          v10,
          string,
          v11,
          v16);
  MF::ThrowIfFailed((MF *)v13, v14);
  v15 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
  }
}

```

## disassembly

```asm
0x180004704  mov     [rsp-28h+arg_18], rbx
0x180004709  push    rbp
0x18000470a  push    rsi
0x18000470b  push    rdi
0x18000470c  push    r14
0x18000470e  push    r15
0x180004710  mov     rbp, rsp
0x180004713  sub     rsp, 60h
0x180004717  mov     rax, cs:__security_cookie
0x18000471e  xor     rax, rsp
0x180004721  mov     [rbp+var_10], rax
0x180004725  mov     rsi, r8
0x180004728  mov     r15, rdx
0x18000472b  mov     r14, rcx
0x18000472e  mov     [rbp+var_38], 0
0x180004736  mov     rdi, [rcx+70h]
0x18000473a  mov     rax, [rdi]
0x18000473d  mov     rbx, [rax+0A0h]
0x180004744  lea     rcx, [rbp+var_38]
0x180004748  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000474d  movups  xmm0, xmmword ptr [rsi]
0x180004750  movdqu  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x180004755  lea     r8, [rbp+var_38]
0x180004759  lea     rdx, [rbp+hstringHeader]
0x18000475d  mov     rcx, rdi
0x180004760  mov     rax, rbx
0x180004763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004768  mov     ecx, eax; this
0x18000476a  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000476f  mov     [rbp+var_40], 0
0x180004773  mov     rbx, [r14+68h]
0x180004777  mov     rdi, [rbp+var_38]
0x18000477b  mov     [rbp+string], 0
0x180004783  lea     r9, [rbp+string]; string
0x180004787  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000478b  mov     edx, 26h ; '&'; length
0x180004790  mov     rcx, r15; sourceString
0x180004793  call    cs:__imp_WindowsCreateStringReference
0x180004799  test    eax, eax
0x18000479b  js      short loc_1800047F6
0x18000479d  lea     r9, [rbp+var_40]
0x1800047a1  mov     r8, rdi
0x1800047a4  mov     rdx, [rbp+string]
0x1800047a8  mov     rcx, rbx
0x1800047ab  call    ?Insert@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,IInspectable *,uchar *)
0x1800047b0  mov     ecx, eax; this
0x1800047b2  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800047b7  nop
0x1800047b8  mov     rcx, [rbp+var_38]
0x1800047bc  test    rcx, rcx
0x1800047bf  jz      short loc_1800047D6
0x1800047c1  mov     [rbp+var_38], 0
0x1800047c9  mov     rax, [rcx]
0x1800047cc  mov     rax, [rax+10h]
0x1800047d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047d5  nop
0x1800047d6  mov     rcx, [rbp+var_10]
0x1800047da  xor     rcx, rsp; StackCookie
0x1800047dd  call    __security_check_cookie
0x1800047e2  mov     rbx, [rsp+60h+arg_18]
0x1800047ea  add     rsp, 60h
0x1800047ee  pop     r15
0x1800047f0  pop     r14
0x1800047f2  pop     rdi
0x1800047f3  pop     rsi
0x1800047f4  pop     rbp
0x1800047f5  retn
0x1800047f6  xor     r9d, r9d; lpArguments
0x1800047f9  xor     r8d, r8d; nNumberOfArguments
0x1800047fc  lea     edx, [r9+1]; dwExceptionFlags
0x180004800  mov     ecx, eax; dwExceptionCode
0x180004802  call    cs:__imp_RaiseException
```
