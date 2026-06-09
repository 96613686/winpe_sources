# Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180016040`
- end: `0x180016290`
- name: `?MarshalObjectToPropertySet@PhoneCallActivatedEventArgsImpl@Activation@ApplicationModel@Windows@@UEAAJPEAUIPropertySet@Collections@Foundation@4@@Z`
- size: `592`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000e284`
- `0x180016004`
- `0x180016040`
- `0x180016798`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800160c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800161ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800160c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800161ed`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800160ff`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800160ff`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl::MarshalObjectToPropertySet(
        Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl *this,
        __int64 (__fastcall ***a2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64))
{
  __int64 result; // rax
  __int64 (__fastcall **v5)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64); // rax
  __int64 (__fastcall *v6)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64); // rbx
  __int64 v7; // rax
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  _QWORD *v11; // rcx
  HSTRING v12; // rbx
  __int128 v13; // xmm0
  __int64 v14; // rax
  int v15; // ebx
  unsigned int v16; // r8d
  __int64 v17; // rcx
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  _QWORD *v20; // rbx
  unsigned __int64 v21; // rdx
  __int64 v22; // rsi
  __int64 v23; // rdi
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  int v27; // eax
  _QWORD *v28; // rcx
  _QWORD *v29; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-50h] BYREF
  HSTRING string; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v32[8]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD *v33; // [rsp+58h] [rbp-28h] BYREF
  __int64 v34; // [rsp+60h] [rbp-20h] BYREF
  _QWORD *v35; // [rsp+68h] [rbp-18h] BYREF

  result = CActivatedEventArgsBase::MarshalObjectToPropertySet((RTL_SRWLOCK *)this - 21, a2);
  if ( (int)result < 0 )
    return result;
  v5 = *a2;
  v35 = 0;
  v6 = *v5;
  v7 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>(&v35);
  v6((struct Windows::Foundation::Collections::IPropertySet *)a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, v7);
  v33 = 0;
  string = 0;
  v8 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    __debugbreak();
  }
  v11 = v33;
  v12 = string;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
  }
  RoGetActivationFactory(v12, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v33);
  v13 = *(_OWORD *)((char *)this + 56);
  v34 = 0;
  v14 = *v33;
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = v13;
  v15 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING_HEADER *, __int64 *))(v14 + 160))(v33, &hstringHeader, &v34);
  if ( v15 < 0 )
  {
    v17 = v34;
LABEL_7:
    if ( v17 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
    }
    v19 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
    }
    return (unsigned int)v15;
  }
  v20 = v35;
  v21 = -1;
  v32[0] = 0;
  v22 = *v35;
  string = 0;
  do
    ++v21;
  while ( aLineid[v21] );
  if ( v21 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v21, v16);
    __debugbreak();
  }
  if ( (int)v21 + 1 < (unsigned int)v21 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v21, v16);
    JUMPOUT(0x18001628FLL);
  }
  v23 = v34;
  v24 = WindowsCreateStringReference(L"LineId", v21, &hstringHeader, &string);
  if ( v24 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
    __debugbreak();
  }
  v27 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v22 + 80))(v20, string, v23, v32);
  v17 = v34;
  v15 = v27;
  if ( v27 < 0 )
    goto LABEL_7;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v28 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
  }
  v29 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
  }
  return 0;
}

```

## disassembly

```asm
0x180016040  mov     [rsp-18h+arg_10], rbx
0x180016045  mov     [rsp-18h+arg_18], rsi
0x18001604a  push    rbp
0x18001604b  push    rdi
0x18001604c  push    r14
0x18001604e  mov     rbp, rsp
0x180016051  sub     rsp, 80h
0x180016058  mov     rax, cs:__security_cookie
0x18001605f  xor     rax, rsp
0x180016062  mov     [rbp+var_10], rax
0x180016066  mov     rsi, rcx
0x180016069  mov     rdi, rdx
0x18001606c  add     rcx, 0FFFFFFFFFFFFFF58h; this
0x180016073  call    ?MarshalObjectToPropertySet@CActivatedEventArgsBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x180016078  xor     r14d, r14d
0x18001607b  test    eax, eax
0x18001607d  js      loc_180016180
0x180016083  mov     rax, [rdi]
0x180016086  lea     rcx, [rbp+var_18]
0x18001608a  mov     [rbp+var_18], r14
0x18001608e  mov     rbx, [rax]
0x180016091  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180016096  mov     r8, rax
0x180016099  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800160a0  mov     rax, rbx
0x1800160a3  mov     rcx, rdi
0x1800160a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160ab  lea     r9, [rbp+string]; string
0x1800160af  mov     [rbp+var_28], r14
0x1800160b3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800160b7  mov     [rbp+string], r14
0x1800160bb  lea     edx, [r14+20h]; length
0x1800160bf  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1800160c6  call    cs:__imp_WindowsCreateStringReference
0x1800160cc  test    eax, eax
0x1800160ce  js      loc_18001627D
0x1800160d4  mov     rcx, [rbp+var_28]
0x1800160d8  mov     rbx, [rbp+string]
0x1800160dc  test    rcx, rcx
0x1800160df  jz      short loc_1800160F1
0x1800160e1  mov     [rbp+var_28], r14
0x1800160e5  mov     rax, [rcx]
0x1800160e8  mov     rax, [rax+10h]
0x1800160ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160f1  lea     r8, [rbp+var_28]
0x1800160f5  mov     rcx, rbx
0x1800160f8  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x1800160ff  call    cs:__imp_RoGetActivationFactory
0x180016105  mov     rcx, [rbp+var_28]
0x180016109  lea     r8, [rbp+var_20]
0x18001610d  movups  xmm0, xmmword ptr [rsi+38h]
0x180016111  mov     [rbp+var_20], r14
0x180016115  lea     rdx, [rbp+hstringHeader]
0x180016119  mov     rax, [rcx]
0x18001611c  movdqu  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x180016121  mov     rax, [rax+0A0h]
0x180016128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001612d  mov     ebx, eax
0x18001612f  test    eax, eax
0x180016131  jns     short loc_1800161A4
0x180016133  mov     rcx, [rbp+var_20]
0x180016137  test    rcx, rcx
0x18001613a  jz      short loc_18001614C
0x18001613c  mov     [rbp+var_20], r14
0x180016140  mov     rdx, [rcx]
0x180016143  mov     rax, [rdx+10h]
0x180016147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001614c  mov     rcx, [rbp+var_28]
0x180016150  test    rcx, rcx
0x180016153  jz      short loc_180016165
0x180016155  mov     [rbp+var_28], r14
0x180016159  mov     rax, [rcx]
0x18001615c  mov     rax, [rax+10h]
0x180016160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016165  mov     rcx, [rbp+var_18]
0x180016169  test    rcx, rcx
0x18001616c  jz      short loc_18001617E
0x18001616e  mov     [rbp+var_18], r14
0x180016172  mov     rax, [rcx]
0x180016175  mov     rax, [rax+10h]
0x180016179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001617e  mov     eax, ebx
0x180016180  mov     rcx, [rbp+var_10]
0x180016184  xor     rcx, rsp; StackCookie
0x180016187  call    __security_check_cookie
0x18001618c  lea     r11, [rsp+80h+var_s0]
0x180016194  mov     rbx, [r11+30h]
0x180016198  mov     rsi, [r11+38h]
0x18001619c  mov     rsp, r11
0x18001619f  pop     r14
0x1800161a1  pop     rdi
0x1800161a2  pop     rbp
0x1800161a3  retn
0x1800161a4  mov     rbx, [rbp+var_18]
0x1800161a8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800161ac  mov     rcx, cs:off_18001B9F8; sourceString
0x1800161b3  mov     [rbp+var_30], r14b
0x1800161b7  mov     rsi, [rbx]
0x1800161ba  mov     [rbp+string], r14
0x1800161be  inc     rdx; int
0x1800161c1  cmp     [rcx+rdx*2], r14w
0x1800161c6  jnz     short loc_1800161BE
0x1800161c8  mov     eax, 0FFFFFFFFh
0x1800161cd  cmp     rdx, rax
0x1800161d0  ja      loc_180016272
0x1800161d6  lea     eax, [rdx+1]
0x1800161d9  cmp     eax, edx
0x1800161db  jb      loc_180016285
0x1800161e1  mov     rdi, [rbp+var_20]
0x1800161e5  lea     r9, [rbp+string]; string
0x1800161e9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800161ed  call    cs:__imp_WindowsCreateStringReference
0x1800161f3  test    eax, eax
0x1800161f5  js      short loc_18001626A
0x1800161f7  mov     rdx, [rbp+string]
0x1800161fb  lea     r9, [rbp+var_30]
0x1800161ff  mov     rax, [rsi+50h]
0x180016203  mov     r8, rdi
0x180016206  mov     rcx, rbx
0x180016209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001620e  mov     rcx, [rbp+var_20]
0x180016212  mov     ebx, eax
0x180016214  test    eax, eax
0x180016216  js      loc_180016137
0x18001621c  test    rcx, rcx
0x18001621f  jz      short loc_180016231
0x180016221  mov     [rbp+var_20], r14
0x180016225  mov     rax, [rcx]
0x180016228  mov     rax, [rax+10h]
0x18001622c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016231  mov     rcx, [rbp+var_28]
0x180016235  test    rcx, rcx
0x180016238  jz      short loc_18001624A
0x18001623a  mov     [rbp+var_28], r14
0x18001623e  mov     rax, [rcx]
0x180016241  mov     rax, [rax+10h]
0x180016245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001624a  mov     rcx, [rbp+var_18]
0x18001624e  test    rcx, rcx
0x180016251  jz      short loc_180016263
0x180016253  mov     [rbp+var_18], r14
0x180016257  mov     rax, [rcx]
0x18001625a  mov     rax, [rax+10h]
0x18001625e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016263  xor     eax, eax
0x180016265  jmp     loc_180016180
0x18001626a  mov     ecx, eax; this
0x18001626c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180016271  int     3; Trap to Debugger
0x180016272  mov     ecx, 80070216h; this
0x180016277  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001627c  int     3; Trap to Debugger
0x18001627d  mov     ecx, eax; this
0x18001627f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180016284  int     3; Trap to Debugger
0x180016285  mov     ecx, 80070216h; this
0x18001628a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
