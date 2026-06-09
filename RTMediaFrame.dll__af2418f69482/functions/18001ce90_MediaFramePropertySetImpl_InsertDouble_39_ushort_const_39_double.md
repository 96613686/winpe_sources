# MediaFramePropertySetImpl::InsertDouble<39>(ushort const (&)[39],double)

- ea: `0x18001ce90`
- end: `0x18001cf85`
- name: `??$InsertDouble@$0CH@@MediaFramePropertySetImpl@@AEAAXAEAY0CH@$$CBGN@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b090`

## callees

- `0x1800019c0`
- `0x180005cd0`
- `0x18000c340`
- `0x18001ce90`
- `0x180026920`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cf29`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cf29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001cf13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001cf13`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall MediaFramePropertySetImpl::InsertDouble<39>(__int64 a1, const WCHAR *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, void **); // rbx
  __int64 v6; // rdx
  unsigned int v7; // eax
  int v8; // edx
  __int64 v9; // rbx
  void *v10; // rdi
  HRESULT v11; // eax
  unsigned int v12; // eax
  int v13; // edx
  void *v14; // rcx
  char v15[8]; // [rsp+20h] [rbp-50h] BYREF
  void *v16; // [rsp+28h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+48h] [rbp-28h] BYREF

  v16 = 0;
  v4 = *(_QWORD *)(a1 + 112);
  v5 = *(__int64 (__fastcall **)(__int64, __int64, void **))(*(_QWORD *)v4 + 120LL);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v16);
  v7 = v5(v4, v6, &v16);
  MF::ThrowIfFailed((MF *)v7, v8);
  v15[0] = 0;
  v9 = *(_QWORD *)(a1 + 104);
  v10 = v16;
  string = 0;
  v11 = WindowsCreateStringReference(a2, 0x26u, &hstringHeader, &string);
  if ( v11 < 0 )
    RaiseException(v11, 1u, 0, 0);
  v12 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
          v9,
          string,
          v10,
          v15);
  MF::ThrowIfFailed((MF *)v12, v13);
  v14 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
  }
}

```

## disassembly

```asm
0x18001ce90  push    rbp
0x18001ce92  push    rbx
0x18001ce93  push    rsi
0x18001ce94  push    rdi
0x18001ce95  push    r14
0x18001ce97  mov     rbp, rsp
0x18001ce9a  sub     rsp, 70h
0x18001ce9e  movaps  [rsp+70h+var_10], xmm6
0x18001cea3  mov     rax, cs:__security_cookie
0x18001ceaa  xor     rax, rsp
0x18001cead  mov     [rbp+var_20], rax
0x18001ceb1  movaps  xmm6, xmm2
0x18001ceb4  mov     r14, rdx
0x18001ceb7  mov     rsi, rcx
0x18001ceba  mov     [rbp+var_48], 0
0x18001cec2  mov     rdi, [rcx+70h]
0x18001cec6  mov     rax, [rdi]
0x18001cec9  mov     rbx, [rax+78h]
0x18001cecd  lea     rcx, [rbp+var_48]
0x18001ced1  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18001ced6  lea     r8, [rbp+var_48]
0x18001ceda  movaps  xmm1, xmm6
0x18001cedd  mov     rcx, rdi
0x18001cee0  mov     rax, rbx
0x18001cee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cee8  mov     ecx, eax; this
0x18001ceea  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18001ceef  mov     [rbp+var_50], 0
0x18001cef3  mov     rbx, [rsi+68h]
0x18001cef7  mov     rdi, [rbp+var_48]
0x18001cefb  mov     [rbp+string], 0
0x18001cf03  lea     r9, [rbp+string]; string
0x18001cf07  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001cf0b  mov     edx, 26h ; '&'; length
0x18001cf10  mov     rcx, r14; sourceString
0x18001cf13  call    cs:__imp_WindowsCreateStringReference
0x18001cf19  test    eax, eax
0x18001cf1b  jns     short loc_18001CF30
0x18001cf1d  xor     r9d, r9d; lpArguments
0x18001cf20  xor     r8d, r8d; nNumberOfArguments
0x18001cf23  lea     edx, [r9+1]; dwExceptionFlags
0x18001cf27  mov     ecx, eax; dwExceptionCode
0x18001cf29  call    cs:__imp_RaiseException
0x18001cf2f  nop
0x18001cf30  lea     r9, [rbp+var_50]
0x18001cf34  mov     r8, rdi
0x18001cf37  mov     rdx, [rbp+string]
0x18001cf3b  mov     rcx, rbx
0x18001cf3e  call    ?Insert@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,IInspectable *,uchar *)
0x18001cf43  mov     ecx, eax; this
0x18001cf45  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18001cf4a  nop
0x18001cf4b  mov     rcx, [rbp+var_48]
0x18001cf4f  test    rcx, rcx
0x18001cf52  jz      short loc_18001CF69
0x18001cf54  mov     [rbp+var_48], 0
0x18001cf5c  mov     rax, [rcx]
0x18001cf5f  mov     rax, [rax+10h]
0x18001cf63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf68  nop
0x18001cf69  mov     rcx, [rbp+var_20]
0x18001cf6d  xor     rcx, rsp; StackCookie
0x18001cf70  call    __security_check_cookie
0x18001cf75  movaps  xmm6, [rsp+70h+var_10]
0x18001cf7a  add     rsp, 70h
0x18001cf7e  pop     r14
0x18001cf80  pop     rdi
0x18001cf81  pop     rsi
0x18001cf82  pop     rbx
0x18001cf83  pop     rbp
0x18001cf84  retn
```
