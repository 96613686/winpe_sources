# Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl::RuntimeClassInitialize(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180016298`
- end: `0x1800164ac`
- name: `?RuntimeClassInitialize@PhoneCallActivatedEventArgsImpl@Activation@ApplicationModel@Windows@@QEAAJPEAUIPropertySet@Collections@Foundation@4@@Z`
- size: `532`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000fb00`

## callees

- `0x180001dc0`
- `0x18000e284`
- `0x180016004`
- `0x180016298`
- `0x180017108`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001633e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001633e`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl::RuntimeClassInitialize(
        Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl *this,
        __int64 (__fastcall ***a2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64))
{
  __int64 result; // rax
  __int64 (__fastcall **v5)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64); // rax
  __int64 (__fastcall *v6)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64); // rbx
  __int64 v7; // rax
  unsigned int v8; // r8d
  _QWORD *v9; // rbx
  unsigned __int64 v10; // rdx
  __int64 v11; // rdi
  HRESULT v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  int v15; // eax
  void (__fastcall ***v16)(_QWORD, GUID *, _QWORD *); // rcx
  unsigned int v17; // ebx
  void (*v18)(void); // rax
  _QWORD *v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  void (__fastcall ***v22)(_QWORD, GUID *, _QWORD *); // rcx
  void (__fastcall ***v23)(_QWORD, GUID *, _QWORD *); // rcx
  _QWORD *v24; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  void (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-30h] BYREF
  _QWORD *v28; // [rsp+48h] [rbp-28h] BYREF
  __int64 v29; // [rsp+50h] [rbp-20h] BYREF
  GUID v30; // [rsp+58h] [rbp-18h] BYREF

  result = CActivatedEventArgsBase::RuntimeClassInitialize(this, a2);
  if ( (int)result < 0 )
    return result;
  v5 = *a2;
  v28 = 0;
  v6 = *v5;
  v7 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>(&v28);
  v6((struct Windows::Foundation::Collections::IPropertySet *)a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, v7);
  v9 = v28;
  v10 = -1;
  v27 = 0;
  v11 = *v28;
  string = 0;
  do
    ++v10;
  while ( aLineid[v10] );
  if ( v10 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v10, v8);
    __debugbreak();
  }
  if ( (int)v10 + 1 < (unsigned int)v10 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v10, v8);
    JUMPOUT(0x1800164ABLL);
  }
  v12 = WindowsCreateStringReference(L"LineId", v10, &hstringHeader, &string);
  if ( v12 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
    __debugbreak();
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _QWORD))(v11 + 48))(v9, string, &v27);
  v16 = v27;
  v17 = v15;
  if ( v15 < 0 )
  {
    if ( !v27 )
    {
LABEL_11:
      v19 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
      }
      return v17;
    }
    v27 = 0;
    v18 = (void (*)(void))(*v16)[2];
LABEL_10:
    v18();
    goto LABEL_11;
  }
  v29 = 0;
  (**v27)(v27, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v29);
  v30 = GUID_NULL;
  v20 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v29 + 160LL))(v29, &v30);
  v21 = v29;
  v17 = v20;
  if ( v20 < 0 )
  {
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v27;
    if ( !v27 )
      goto LABEL_11;
    v27 = 0;
    v18 = (void (*)(void))(*v22)[2];
    goto LABEL_10;
  }
  *((GUID *)this + 14) = v30;
  if ( v21 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v23 = v27;
  if ( v27 )
  {
    v27 = 0;
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v23)[2])(v23);
  }
  v24 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
  }
  return 0;
}

```

## disassembly

```asm
0x180016298  mov     [rsp-18h+arg_10], rbx
0x18001629d  mov     [rsp-18h+arg_18], rsi
0x1800162a2  push    rbp
0x1800162a3  push    rdi
0x1800162a4  push    r14
0x1800162a6  mov     rbp, rsp
0x1800162a9  sub     rsp, 70h
0x1800162ad  mov     rax, cs:__security_cookie
0x1800162b4  xor     rax, rsp
0x1800162b7  mov     [rbp+var_8], rax
0x1800162bb  mov     rdi, rdx
0x1800162be  mov     rsi, rcx
0x1800162c1  call    ?RuntimeClassInitialize@CActivatedEventArgsBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsBase::RuntimeClassInitialize(Windows::Foundation::Collections::IPropertySet *)
0x1800162c6  xor     r14d, r14d
0x1800162c9  test    eax, eax
0x1800162cb  js      loc_18001639A
0x1800162d1  mov     rax, [rdi]
0x1800162d4  lea     rcx, [rbp+var_28]
0x1800162d8  mov     [rbp+var_28], r14
0x1800162dc  mov     rbx, [rax]
0x1800162df  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800162e4  mov     r8, rax
0x1800162e7  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800162ee  mov     rax, rbx
0x1800162f1  mov     rcx, rdi
0x1800162f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162f9  mov     rbx, [rbp+var_28]
0x1800162fd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180016301  mov     rcx, cs:off_18001B9F8; sourceString
0x180016308  mov     [rbp+var_30], r14
0x18001630c  mov     rdi, [rbx]
0x18001630f  mov     [rbp+string], r14
0x180016313  inc     rdx; int
0x180016316  cmp     [rcx+rdx*2], r14w
0x18001631b  jnz     short loc_180016313
0x18001631d  mov     eax, 0FFFFFFFFh
0x180016322  cmp     rdx, rax
0x180016325  ja      loc_180016496
0x18001632b  lea     eax, [rdx+1]
0x18001632e  cmp     eax, edx
0x180016330  jb      loc_1800164A1
0x180016336  lea     r9, [rbp+string]; string
0x18001633a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001633e  call    cs:__imp_WindowsCreateStringReference
0x180016344  test    eax, eax
0x180016346  js      loc_18001648E
0x18001634c  mov     rdx, [rbp+string]
0x180016350  lea     r8, [rbp+var_30]
0x180016354  mov     rax, [rdi+30h]
0x180016358  mov     rcx, rbx
0x18001635b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016360  mov     rcx, [rbp+var_30]
0x180016364  mov     ebx, eax
0x180016366  test    eax, eax
0x180016368  jns     short loc_1800163BB
0x18001636a  test    rcx, rcx
0x18001636d  jz      short loc_18001637F
0x18001636f  mov     [rbp+var_30], r14
0x180016373  mov     rdx, [rcx]
0x180016376  mov     rax, [rdx+10h]
0x18001637a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001637f  mov     rcx, [rbp+var_28]
0x180016383  test    rcx, rcx
0x180016386  jz      short loc_180016398
0x180016388  mov     [rbp+var_28], r14
0x18001638c  mov     rax, [rcx]
0x18001638f  mov     rax, [rax+10h]
0x180016393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016398  mov     eax, ebx
0x18001639a  mov     rcx, [rbp+var_8]
0x18001639e  xor     rcx, rsp; StackCookie
0x1800163a1  call    __security_check_cookie
0x1800163a6  lea     r11, [rsp+70h+var_s0]
0x1800163ab  mov     rbx, [r11+30h]
0x1800163af  mov     rsi, [r11+38h]
0x1800163b3  mov     rsp, r11
0x1800163b6  pop     r14
0x1800163b8  pop     rdi
0x1800163b9  pop     rbp
0x1800163ba  retn
0x1800163bb  mov     [rbp+var_20], r14
0x1800163bf  lea     r8, [rbp+var_20]
0x1800163c3  mov     rax, [rcx]
0x1800163c6  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1800163cd  mov     rax, [rax]
0x1800163d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163d5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800163dc  mov     rcx, [rbp+var_20]
0x1800163e0  lea     rdx, [rbp+var_18]
0x1800163e4  movdqu  [rbp+var_18], xmm0
0x1800163e9  mov     rax, [rcx]
0x1800163ec  mov     rax, [rax+0A0h]
0x1800163f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163f8  mov     rcx, [rbp+var_20]
0x1800163fc  mov     ebx, eax
0x1800163fe  test    eax, eax
0x180016400  jns     short loc_180016434
0x180016402  test    rcx, rcx
0x180016405  jz      short loc_180016417
0x180016407  mov     [rbp+var_20], r14
0x18001640b  mov     rdx, [rcx]
0x18001640e  mov     rax, [rdx+10h]
0x180016412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016417  mov     rcx, [rbp+var_30]
0x18001641b  test    rcx, rcx
0x18001641e  jz      loc_18001637F
0x180016424  mov     [rbp+var_30], r14
0x180016428  mov     rax, [rcx]
0x18001642b  mov     rax, [rax+10h]
0x18001642f  jmp     loc_18001637A
0x180016434  movups  xmm0, [rbp+var_18]
0x180016438  movdqu  xmmword ptr [rsi+0E0h], xmm0
0x180016440  test    rcx, rcx
0x180016443  jz      short loc_180016455
0x180016445  mov     [rbp+var_20], r14
0x180016449  mov     rax, [rcx]
0x18001644c  mov     rax, [rax+10h]
0x180016450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016455  mov     rcx, [rbp+var_30]
0x180016459  test    rcx, rcx
0x18001645c  jz      short loc_18001646E
0x18001645e  mov     [rbp+var_30], r14
0x180016462  mov     rax, [rcx]
0x180016465  mov     rax, [rax+10h]
0x180016469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001646e  mov     rcx, [rbp+var_28]
0x180016472  test    rcx, rcx
0x180016475  jz      short loc_180016487
0x180016477  mov     [rbp+var_28], r14
0x18001647b  mov     rax, [rcx]
0x18001647e  mov     rax, [rax+10h]
0x180016482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016487  xor     eax, eax
0x180016489  jmp     loc_18001639A
0x18001648e  mov     ecx, eax; this
0x180016490  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180016495  int     3; Trap to Debugger
0x180016496  mov     ecx, 80070216h; this
0x18001649b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800164a0  int     3; Trap to Debugger
0x1800164a1  mov     ecx, 80070216h; this
0x1800164a6  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
