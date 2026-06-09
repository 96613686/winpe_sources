# MediaFramePropertySetImpl::InsertString<39>(ushort const (&)[39],ushort const *)

- ea: `0x18001cadc`
- end: `0x18001cc31`
- name: `??$InsertString@$0CH@@MediaFramePropertySetImpl@@AEAAXAEAY0CH@$$CBGPEBG@Z`
- size: `341`
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
- `0x18001cadc`
- `0x180026920`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cb68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cbc4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cc2a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cb68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cbc4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cc2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001cb52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001cbae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001cb52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001cbae`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall MediaFramePropertySetImpl::InsertString<39>(__int64 a1, const WCHAR *a2, const WCHAR *a3)
{
  __int64 *v6; // rsi
  __int64 v7; // r15
  unsigned __int64 v8; // rdx
  HRESULT v9; // eax
  unsigned int v10; // eax
  int v11; // edx
  __int64 v12; // rbx
  __int64 v13; // rdi
  HRESULT v14; // eax
  unsigned int v15; // eax
  int v16; // edx
  __int64 v17; // rcx
  _BYTE v18[8]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v19; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF

  v19 = 0;
  v6 = *(__int64 **)(a1 + 112);
  v7 = *v6;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v19);
  string = 0;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( v8 > 0xFFFFFFFF || (int)v8 + 1 < (unsigned int)v8 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x18001CC30LL);
  }
  v9 = WindowsCreateStringReference(a3, v8, &hstringHeader, &string);
  if ( v9 < 0 )
    RaiseException(v9, 1u, 0, 0);
  v10 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v7 + 144))(v6, string, &v19);
  MF::ThrowIfFailed((MF *)v10, v11);
  v18[0] = 0;
  v12 = *(_QWORD *)(a1 + 104);
  v13 = v19;
  string = 0;
  v14 = WindowsCreateStringReference(a2, 0x26u, &hstringHeader, &string);
  if ( v14 < 0 )
    RaiseException(v14, 1u, 0, 0);
  v15 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
          v12,
          string,
          v13,
          v18);
  MF::ThrowIfFailed((MF *)v15, v16);
  v17 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
}

```

## disassembly

```asm
0x18001cadc  push    rbp
0x18001cade  push    rbx
0x18001cadf  push    rsi
0x18001cae0  push    rdi
0x18001cae1  push    r12
0x18001cae3  push    r14
0x18001cae5  push    r15
0x18001cae7  mov     rbp, rsp
0x18001caea  sub     rsp, 60h
0x18001caee  mov     rax, cs:__security_cookie
0x18001caf5  xor     rax, rsp
0x18001caf8  mov     [rbp+var_10], rax
0x18001cafc  mov     rbx, r8
0x18001caff  mov     r14, rdx
0x18001cb02  mov     rdi, rcx
0x18001cb05  xor     r12d, r12d
0x18001cb08  mov     [rbp+var_38], r12
0x18001cb0c  mov     rsi, [rcx+70h]
0x18001cb10  mov     r15, [rsi]
0x18001cb13  lea     rcx, [rbp+var_38]
0x18001cb17  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18001cb1c  mov     [rbp+string], r12
0x18001cb20  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001cb24  inc     rdx; length
0x18001cb27  cmp     [rbx+rdx*2], r12w
0x18001cb2c  jnz     short loc_18001CB24
0x18001cb2e  mov     eax, 0FFFFFFFFh
0x18001cb33  cmp     rdx, rax
0x18001cb36  ja      loc_18001CC1B
0x18001cb3c  lea     eax, [rdx+1]
0x18001cb3f  cmp     eax, edx
0x18001cb41  jb      loc_18001CC1B
0x18001cb47  lea     r9, [rbp+string]; string
0x18001cb4b  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001cb4f  mov     rcx, rbx; sourceString
0x18001cb52  call    cs:__imp_WindowsCreateStringReference
0x18001cb58  test    eax, eax
0x18001cb5a  jns     short loc_18001CB6F
0x18001cb5c  xor     r9d, r9d; lpArguments
0x18001cb5f  xor     r8d, r8d; nNumberOfArguments
0x18001cb62  lea     edx, [r9+1]; dwExceptionFlags
0x18001cb66  mov     ecx, eax; dwExceptionCode
0x18001cb68  call    cs:__imp_RaiseException
0x18001cb6e  nop
0x18001cb6f  lea     r8, [rbp+var_38]
0x18001cb73  mov     rdx, [rbp+string]
0x18001cb77  mov     rcx, rsi
0x18001cb7a  mov     rax, [r15+90h]
0x18001cb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb86  mov     ecx, eax; this
0x18001cb88  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18001cb8d  nop
0x18001cb8e  mov     [rbp+var_40], r12b
0x18001cb92  mov     rbx, [rdi+68h]
0x18001cb96  mov     rdi, [rbp+var_38]
0x18001cb9a  mov     [rbp+string], r12
0x18001cb9e  lea     r9, [rbp+string]; string
0x18001cba2  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001cba6  mov     edx, 26h ; '&'; length
0x18001cbab  mov     rcx, r14; sourceString
0x18001cbae  call    cs:__imp_WindowsCreateStringReference
0x18001cbb4  test    eax, eax
0x18001cbb6  jns     short loc_18001CBCB
0x18001cbb8  xor     r9d, r9d; lpArguments
0x18001cbbb  xor     r8d, r8d; nNumberOfArguments
0x18001cbbe  lea     edx, [r9+1]; dwExceptionFlags
0x18001cbc2  mov     ecx, eax; dwExceptionCode
0x18001cbc4  call    cs:__imp_RaiseException
0x18001cbca  nop
0x18001cbcb  lea     r9, [rbp+var_40]
0x18001cbcf  mov     r8, rdi
0x18001cbd2  mov     rdx, [rbp+string]
0x18001cbd6  mov     rcx, rbx
0x18001cbd9  call    ?Insert@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,IInspectable *,uchar *)
0x18001cbde  mov     ecx, eax; this
0x18001cbe0  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18001cbe5  nop
0x18001cbe6  mov     rcx, [rbp+var_38]
0x18001cbea  test    rcx, rcx
0x18001cbed  jz      short loc_18001CC00
0x18001cbef  mov     [rbp+var_38], r12
0x18001cbf3  mov     rax, [rcx]
0x18001cbf6  mov     rax, [rax+10h]
0x18001cbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbff  nop
0x18001cc00  mov     rcx, [rbp+var_10]
0x18001cc04  xor     rcx, rsp; StackCookie
0x18001cc07  call    __security_check_cookie
0x18001cc0c  add     rsp, 60h
0x18001cc10  pop     r15
0x18001cc12  pop     r14
0x18001cc14  pop     r12
0x18001cc16  pop     rdi
0x18001cc17  pop     rsi
0x18001cc18  pop     rbx
0x18001cc19  pop     rbp
0x18001cc1a  retn
0x18001cc1b  xor     r9d, r9d; lpArguments
0x18001cc1e  xor     r8d, r8d; nNumberOfArguments
0x18001cc21  lea     edx, [r9+1]; dwExceptionFlags
0x18001cc25  mov     ecx, 80070216h; dwExceptionCode
0x18001cc2a  call    cs:__imp_RaiseException
```
