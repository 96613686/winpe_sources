# AuthHostWebInstance::CreateHostedWindow(IUnknown *)

- ea: `0x140007080`
- end: `0x1400076f9`
- name: `?CreateHostedWindow@AuthHostWebInstance@@AEAAJPEAUIUnknown@@@Z`
- size: `1657`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140004ac0`

## callees

- `0x140002c98`
- `0x140003a8c`
- `0x140006c44`
- `0x140006c94`
- `0x140006d04`
- `0x140006d74`
- `0x140006de4`
- `0x140006e54`
- `0x140007080`
- `0x140012f60`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140007177`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140007177`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000715e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000715e`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall AuthHostWebInstance::CreateHostedWindow(AuthHostWebInstance *this, struct IUnknown *a2)
{
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v5; // edi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, HSTRING, _QWORD); // rdi
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v16; // rax
  AuthHostWebInstance *v17; // r14
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v20; // rax
  AuthHostWebInstance *v21; // r14
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v23)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v24; // rax
  AuthHostWebInstance *v25; // r14
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, AuthHostWebInstance *, char *); // rbx
  __int64 v28; // rax
  AuthHostWebInstance *v29; // r14
  __int64 v30; // rbx
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 v32; // rdx
  AuthHostWebInstance *v34; // [rsp+20h] [rbp-29h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-21h] BYREF
  __int64 (__fastcall *v36)(AuthHostWebInstance *__hidden, struct Windows::UI::Core::ICoreDispatcher *, struct Windows::UI::Core::IAcceleratorKeyEventArgs *); // [rsp+30h] [rbp-19h] BYREF
  int v37; // [rsp+38h] [rbp-11h]
  __int64 v38; // [rsp+40h] [rbp-9h] BYREF
  __int64 v39; // [rsp+48h] [rbp-1h] BYREF
  __int64 v40; // [rsp+50h] [rbp+7h] BYREF
  __int64 v41; // [rsp+58h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+60h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+1Fh] BYREF

  v40 = 0;
  v35 = 0;
  v39 = 0;
  v38 = 0;
  v41 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_cd292360_2763_4085_8a9f_74b224a29175,
         &v40);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v7 = 10;
LABEL_61:
      WPP_SF_d(v6[7], v7, WPP_bfa95fea1b46398427ec08da96c2d59a_Traceguids, (unsigned int)v5);
      goto LABEL_62;
    }
    goto LABEL_62;
  }
  v8 = v40;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v40 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  if ( WindowsCreateStringReference(L"HostWindow", 0xAu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5 = v9(v8, string, &v35);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v7 = 11;
      goto LABEL_61;
    }
LABEL_62:
    if ( v35 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v35)[19])(v35);
    goto LABEL_73;
  }
  v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
  v11 = **v35;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  v5 = v11(v10, &GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f, &v39);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v7 = 12;
      goto LABEL_61;
    }
    goto LABEL_62;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v39 + 24LL))(v39, (char *)this + 64);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v7 = 13;
      goto LABEL_61;
    }
    goto LABEL_62;
  }
  v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
  v13 = (*v35)[9];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v13)(v12, &v38);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v7 = 14;
      goto LABEL_61;
    }
    goto LABEL_62;
  }
  v5 = Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreDispatcher>::As<Windows::UI::Core::ICoreAcceleratorKeys>(
         &v38,
         &v41);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v7 = 15;
      goto LABEL_61;
    }
    goto LABEL_62;
  }
  v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
  v15 = (*v35)[54];
  v36 = AuthHostWebInstance::HandleSizedEvent;
  v37 = 0;
  v34 = this;
  v16 = _lambda_8d72cac82bd4635b5765a6b3ebc66f5e_::_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_(&string, &v34, &v36);
  Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>,_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_>(
    &v34,
    v16);
  v17 = v34;
  v5 = v15(v14, (GUID *)v34, (__int64 *)this + 18);
  if ( v17 )
    (*(void (__fastcall **)(AuthHostWebInstance *))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v7 = 16;
      goto LABEL_61;
    }
    goto LABEL_62;
  }
  v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
  v19 = (*v35)[24];
  v36 = AuthHostWebInstance::HandleWindowActivatedEvent;
  v37 = 0;
  v34 = this;
  v20 = _lambda_8d72cac82bd4635b5765a6b3ebc66f5e_::_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_(&string, &v34, &v36);
  Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowActivatedEventArgs *>,_lambda_6412db1a0a1618af10ca0c7de7541180_>(
    &v34,
    v20);
  v21 = v34;
  v5 = v19(v18, (GUID *)v34, (__int64 *)this + 19);
  if ( v21 )
    (*(void (__fastcall **)(AuthHostWebInstance *))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v7 = 17;
      goto LABEL_61;
    }
    goto LABEL_62;
  }
  v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
  v23 = (*v35)[30];
  v36 = AuthHostWebInstance::HandleWindowClosedEvent;
  v37 = 0;
  v34 = this;
  v24 = _lambda_8d72cac82bd4635b5765a6b3ebc66f5e_::_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_(&string, &v34, &v36);
  Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::CoreWindowEventArgs *>,_lambda_9917ab12da543e53efc8a56210ff7d5d_>(
    &v34,
    v24);
  v25 = v34;
  v5 = v23(v22, (GUID *)v34, (__int64 *)this + 20);
  if ( v25 )
    (*(void (__fastcall **)(AuthHostWebInstance *))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v7 = 18;
      goto LABEL_61;
    }
    goto LABEL_62;
  }
  v26 = v41;
  v27 = *(__int64 (__fastcall **)(__int64, AuthHostWebInstance *, char *))(*(_QWORD *)v41 + 48LL);
  v36 = AuthHostWebInstance::HandleAcceleratorKeyEvent;
  v37 = 0;
  v34 = this;
  v28 = _lambda_8d72cac82bd4635b5765a6b3ebc66f5e_::_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_(&string, &v34, &v36);
  Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_>(
    &v34,
    v28);
  v29 = v34;
  v5 = v27(v26, v34, (char *)this + 168);
  if ( v29 )
    (*(void (__fastcall **)(AuthHostWebInstance *))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v7 = 19;
      goto LABEL_61;
    }
    goto LABEL_62;
  }
  v30 = v38;
  if ( *((_QWORD *)this + 88) != v38 )
  {
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
    v34 = (AuthHostWebInstance *)*((_QWORD *)this + 88);
    *((_QWORD *)this + 88) = v30;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  }
  v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
  if ( *((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 9) != v35 )
  {
    if ( v35 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v35)[1])(v35);
    v34 = (AuthHostWebInstance *)*((_QWORD *)this + 9);
    *((_QWORD *)this + 9) = v31;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
  }
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v31)[18])(v31);
  LOBYTE(v32) = 1;
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*v35)[13])(v35, v32);
LABEL_73:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140007080  mov     [rsp-8+arg_10], rbx
0x140007085  mov     [rsp-8+arg_18], rsi
0x14000708a  push    rbp
0x14000708b  push    rdi
0x14000708c  push    r14
0x14000708e  lea     rbp, [rsp-47h]
0x140007093  sub     rsp, 90h
0x14000709a  mov     rax, cs:__security_cookie
0x1400070a1  xor     rax, rsp
0x1400070a4  mov     [rbp+57h+var_20], rax
0x1400070a8  mov     rdi, rdx
0x1400070ab  mov     rsi, rcx
0x1400070ae  mov     [rbp+57h+var_50], 0
0x1400070b6  mov     [rbp+57h+var_78], 0
0x1400070be  mov     [rbp+57h+var_58], 0
0x1400070c6  mov     [rbp+57h+var_60], 0
0x1400070ce  mov     [rbp+57h+var_48], 0
0x1400070d6  mov     rax, [rdx]
0x1400070d9  mov     rbx, [rax]
0x1400070dc  lea     rcx, [rbp+57h+var_50]
0x1400070e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400070e5  lea     r8, [rbp+57h+var_50]
0x1400070e9  lea     rdx, _GUID_cd292360_2763_4085_8a9f_74b224a29175
0x1400070f0  mov     rcx, rdi
0x1400070f3  mov     rax, rbx
0x1400070f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070fb  mov     edi, eax
0x1400070fd  test    eax, eax
0x1400070ff  jns     short loc_140007136
0x140007101  lea     rax, WPP_GLOBAL_Control
0x140007108  mov     rcx, cs:WPP_GLOBAL_Control
0x14000710f  cmp     rcx, rax
0x140007112  jz      loc_1400075E7
0x140007118  test    byte ptr [rcx+44h], 2
0x14000711c  jz      loc_1400075E7
0x140007122  cmp     byte ptr [rcx+41h], 2
0x140007126  jb      loc_1400075E7
0x14000712c  mov     edx, 0Ah
0x140007131  jmp     loc_1400075D4
0x140007136  mov     rbx, [rbp+57h+var_50]
0x14000713a  mov     rax, [rbx]
0x14000713d  mov     rdi, [rax+30h]
0x140007141  lea     rcx, [rbp+57h+var_78]
0x140007145  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000714a  lea     r9, [rbp+57h+string]; string
0x14000714e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140007152  mov     edx, 0Ah; length
0x140007157  lea     rcx, sourceString; "HostWindow"
0x14000715e  call    cs:__imp_WindowsCreateStringReference
0x140007164  test    eax, eax
0x140007166  jns     short loc_14000717D
0x140007168  xor     r9d, r9d; lpArguments
0x14000716b  xor     r8d, r8d; nNumberOfArguments
0x14000716e  lea     edx, [r9+1]; dwExceptionFlags
0x140007172  mov     ecx, 0C000000Dh; dwExceptionCode
0x140007177  call    cs:__imp_RaiseException
0x14000717d  lea     r8, [rbp+57h+var_78]
0x140007181  mov     rdx, [rbp+57h+string]
0x140007185  mov     rcx, rbx
0x140007188  mov     rax, rdi
0x14000718b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007190  mov     edi, eax
0x140007192  test    eax, eax
0x140007194  jns     short loc_1400071CB
0x140007196  lea     rax, WPP_GLOBAL_Control
0x14000719d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400071a4  cmp     rcx, rax
0x1400071a7  jz      loc_1400075E7
0x1400071ad  test    byte ptr [rcx+44h], 2
0x1400071b1  jz      loc_1400075E7
0x1400071b7  cmp     byte ptr [rcx+41h], 2
0x1400071bb  jb      loc_1400075E7
0x1400071c1  mov     edx, 0Bh
0x1400071c6  jmp     loc_1400075D4
0x1400071cb  mov     rbx, [rbp+57h+var_78]
0x1400071cf  mov     rax, [rbx]
0x1400071d2  mov     rdi, [rax]
0x1400071d5  lea     rcx, [rbp+57h+var_58]
0x1400071d9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400071de  lea     r8, [rbp+57h+var_58]
0x1400071e2  lea     rdx, _GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f
0x1400071e9  mov     rcx, rbx
0x1400071ec  mov     rax, rdi
0x1400071ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071f4  mov     edi, eax
0x1400071f6  test    eax, eax
0x1400071f8  jns     short loc_14000722F
0x1400071fa  lea     rax, WPP_GLOBAL_Control
0x140007201  mov     rcx, cs:WPP_GLOBAL_Control
0x140007208  cmp     rcx, rax
0x14000720b  jz      loc_1400075E7
0x140007211  test    byte ptr [rcx+44h], 2
0x140007215  jz      loc_1400075E7
0x14000721b  cmp     byte ptr [rcx+41h], 2
0x14000721f  jb      loc_1400075E7
0x140007225  mov     edx, 0Ch
0x14000722a  jmp     loc_1400075D4
0x14000722f  mov     rcx, [rbp+57h+var_58]
0x140007233  mov     rax, [rcx]
0x140007236  lea     rdx, [rsi+40h]
0x14000723a  mov     rax, [rax+18h]
0x14000723e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007243  mov     edi, eax
0x140007245  test    eax, eax
0x140007247  jns     short loc_14000727E
0x140007249  lea     rax, WPP_GLOBAL_Control
0x140007250  mov     rcx, cs:WPP_GLOBAL_Control
0x140007257  cmp     rcx, rax
0x14000725a  jz      loc_1400075E7
0x140007260  test    byte ptr [rcx+44h], 2
0x140007264  jz      loc_1400075E7
0x14000726a  cmp     byte ptr [rcx+41h], 2
0x14000726e  jb      loc_1400075E7
0x140007274  mov     edx, 0Dh
0x140007279  jmp     loc_1400075D4
0x14000727e  mov     rdi, [rbp+57h+var_78]
0x140007282  mov     rax, [rdi]
0x140007285  mov     rbx, [rax+48h]
0x140007289  lea     rcx, [rbp+57h+var_60]
0x14000728d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140007292  lea     rdx, [rbp+57h+var_60]
0x140007296  mov     rcx, rdi
0x140007299  mov     rax, rbx
0x14000729c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400072a1  mov     edi, eax
0x1400072a3  test    eax, eax
0x1400072a5  jns     short loc_1400072DC
0x1400072a7  lea     rax, WPP_GLOBAL_Control
0x1400072ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400072b5  cmp     rcx, rax
0x1400072b8  jz      loc_1400075E7
0x1400072be  test    byte ptr [rcx+44h], 2
0x1400072c2  jz      loc_1400075E7
0x1400072c8  cmp     byte ptr [rcx+41h], 2
0x1400072cc  jb      loc_1400075E7
0x1400072d2  mov     edx, 0Eh
0x1400072d7  jmp     loc_1400075D4
0x1400072dc  lea     rdx, [rbp+57h+var_48]
0x1400072e0  lea     rcx, [rbp+57h+var_60]
0x1400072e4  call    ??$As@UICoreAcceleratorKeys@Core@UI@Windows@@@?$ComPtr@UICoreDispatcher@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICoreAcceleratorKeys@Core@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreDispatcher>::As<Windows::UI::Core::ICoreAcceleratorKeys>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreAcceleratorKeys>>)
0x1400072e9  mov     edi, eax
0x1400072eb  test    eax, eax
0x1400072ed  jns     short loc_140007324
0x1400072ef  lea     rax, WPP_GLOBAL_Control
0x1400072f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400072fd  cmp     rcx, rax
0x140007300  jz      loc_1400075E7
0x140007306  test    byte ptr [rcx+44h], 2
0x14000730a  jz      loc_1400075E7
0x140007310  cmp     byte ptr [rcx+41h], 2
0x140007314  jb      loc_1400075E7
0x14000731a  mov     edx, 0Fh
0x14000731f  jmp     loc_1400075D4
0x140007324  mov     rdi, [rbp+57h+var_78]
0x140007328  mov     rax, [rdi]
0x14000732b  mov     rbx, [rax+1B0h]
0x140007332  lea     rax, ?HandleSizedEvent@AuthHostWebInstance@@AEAAJPEAUICoreWindow@Core@UI@Windows@@PEAUIWindowSizeChangedEventArgs@345@@Z; AuthHostWebInstance::HandleSizedEvent(Windows::UI::Core::ICoreWindow *,Windows::UI::Core::IWindowSizeChangedEventArgs *)
0x140007339  mov     [rbp+57h+var_70], rax
0x14000733d  mov     [rbp+57h+var_68], 0
0x140007344  mov     eax, [rbp+57h+var_64]
0x140007347  mov     [rbp+57h+var_64], eax
0x14000734a  mov     [rbp+57h+var_80], rsi
0x14000734e  lea     r8, [rbp+57h+var_70]
0x140007352  lea     rdx, [rbp+57h+var_80]
0x140007356  lea     rcx, [rbp+57h+string]
0x14000735a  call    ??0_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_@@QEAA@AEBQEAVAuthHostWebInstance@@AEBQ81@EAAJPEAUICoreWindow@Core@UI@Windows@@PEAUIWindowSizeChangedEventArgs@345@@Z@Z; _lambda_8d72cac82bd4635b5765a6b3ebc66f5e_::_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_(AuthHostWebInstance * const &,long (AuthHostWebInstance::*const &)(Windows::UI::Core::ICoreWindow *,Windows::UI::Core::IWindowSizeChangedEventArgs *))
0x14000735f  mov     rdx, rax
0x140007362  lea     rcx, [rbp+57h+var_80]
0x140007366  call    ??$Callback@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowSizeChangedEventArgs@234@@Foundation@Windows@@V_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowSizeChangedEventArgs@234@@Foundation@Windows@@@01@$$QEAV_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowSizeChangedEventArgs *>,_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_>(_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_ &&)
0x14000736b  nop
0x14000736c  mov     r14, [rbp+57h+var_80]
0x140007370  lea     r8, [rsi+90h]
0x140007377  mov     rdx, r14
0x14000737a  mov     rcx, rdi
0x14000737d  mov     rax, rbx
0x140007380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007385  mov     edi, eax
0x140007387  test    r14, r14
0x14000738a  jz      short loc_14000739C
0x14000738c  mov     rax, [r14]
0x14000738f  mov     rcx, r14
0x140007392  mov     rax, [rax+10h]
0x140007396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000739b  nop
0x14000739c  test    edi, edi
0x14000739e  jns     short loc_1400073D5
0x1400073a0  lea     rax, WPP_GLOBAL_Control
0x1400073a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073ae  cmp     rcx, rax
0x1400073b1  jz      loc_1400075E7
0x1400073b7  test    byte ptr [rcx+44h], 2
0x1400073bb  jz      loc_1400075E7
0x1400073c1  cmp     byte ptr [rcx+41h], 2
0x1400073c5  jb      loc_1400075E7
0x1400073cb  mov     edx, 10h
0x1400073d0  jmp     loc_1400075D4
0x1400073d5  mov     rdi, [rbp+57h+var_78]
0x1400073d9  mov     rax, [rdi]
0x1400073dc  mov     rbx, [rax+0C0h]
0x1400073e3  lea     rax, ?HandleWindowActivatedEvent@AuthHostWebInstance@@AEAAJPEAUICoreWindow@Core@UI@Windows@@PEAUIWindowActivatedEventArgs@345@@Z; AuthHostWebInstance::HandleWindowActivatedEvent(Windows::UI::Core::ICoreWindow *,Windows::UI::Core::IWindowActivatedEventArgs *)
0x1400073ea  mov     [rbp+57h+var_70], rax
0x1400073ee  mov     [rbp+57h+var_68], 0
0x1400073f5  mov     eax, [rbp+57h+var_64]
0x1400073f8  mov     [rbp+57h+var_64], eax
0x1400073fb  mov     [rbp+57h+var_80], rsi
0x1400073ff  lea     r8, [rbp+57h+var_70]
0x140007403  lea     rdx, [rbp+57h+var_80]
0x140007407  lea     rcx, [rbp+57h+string]
0x14000740b  call    ??0_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_@@QEAA@AEBQEAVAuthHostWebInstance@@AEBQ81@EAAJPEAUICoreWindow@Core@UI@Windows@@PEAUIWindowSizeChangedEventArgs@345@@Z@Z; _lambda_8d72cac82bd4635b5765a6b3ebc66f5e_::_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_(AuthHostWebInstance * const &,long (AuthHostWebInstance::*const &)(Windows::UI::Core::ICoreWindow *,Windows::UI::Core::IWindowSizeChangedEventArgs *))
0x140007410  mov     rdx, rax
0x140007413  lea     rcx, [rbp+57h+var_80]
0x140007417  call    ??$Callback@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowActivatedEventArgs@234@@Foundation@Windows@@V_lambda_6412db1a0a1618af10ca0c7de7541180_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowActivatedEventArgs@234@@Foundation@Windows@@@01@$$QEAV_lambda_6412db1a0a1618af10ca0c7de7541180_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowActivatedEventArgs *>,_lambda_6412db1a0a1618af10ca0c7de7541180_>(_lambda_6412db1a0a1618af10ca0c7de7541180_ &&)
0x14000741c  nop
0x14000741d  mov     r14, [rbp+57h+var_80]
0x140007421  lea     r8, [rsi+98h]
0x140007428  mov     rdx, r14
0x14000742b  mov     rcx, rdi
0x14000742e  mov     rax, rbx
0x140007431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007436  mov     edi, eax
0x140007438  test    r14, r14
0x14000743b  jz      short loc_14000744D
0x14000743d  mov     rax, [r14]
0x140007440  mov     rcx, r14
0x140007443  mov     rax, [rax+10h]
0x140007447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000744c  nop
0x14000744d  test    edi, edi
0x14000744f  jns     short loc_140007486
0x140007451  lea     rax, WPP_GLOBAL_Control
0x140007458  mov     rcx, cs:WPP_GLOBAL_Control
0x14000745f  cmp     rcx, rax
0x140007462  jz      loc_1400075E7
0x140007468  test    byte ptr [rcx+44h], 2
0x14000746c  jz      loc_1400075E7
0x140007472  cmp     byte ptr [rcx+41h], 2
0x140007476  jb      loc_1400075E7
0x14000747c  mov     edx, 11h
0x140007481  jmp     loc_1400075D4
0x140007486  mov     rdi, [rbp+57h+var_78]
0x14000748a  mov     rax, [rdi]
0x14000748d  mov     rbx, [rax+0F0h]
0x140007494  lea     rax, ?HandleWindowClosedEvent@AuthHostWebInstance@@AEAAJPEAUICoreWindow@Core@UI@Windows@@PEAUICoreWindowEventArgs@345@@Z; AuthHostWebInstance::HandleWindowClosedEvent(Windows::UI::Core::ICoreWindow *,Windows::UI::Core::ICoreWindowEventArgs *)
0x14000749b  mov     [rbp+57h+var_70], rax
0x14000749f  mov     [rbp+57h+var_68], 0
0x1400074a6  mov     eax, [rbp+57h+var_64]
0x1400074a9  mov     [rbp+57h+var_64], eax
0x1400074ac  mov     [rbp+57h+var_80], rsi
0x1400074b0  lea     r8, [rbp+57h+var_70]
0x1400074b4  lea     rdx, [rbp+57h+var_80]
0x1400074b8  lea     rcx, [rbp+57h+string]
0x1400074bc  call    ??0_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_@@QEAA@AEBQEAVAuthHostWebInstance@@AEBQ81@EAAJPEAUICoreWindow@Core@UI@Windows@@PEAUIWindowSizeChangedEventArgs@345@@Z@Z; _lambda_8d72cac82bd4635b5765a6b3ebc66f5e_::_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_(AuthHostWebInstance * const &,long (AuthHostWebInstance::*const &)(Windows::UI::Core::ICoreWindow *,Windows::UI::Core::IWindowSizeChangedEventArgs *))
0x1400074c1  mov     rdx, rax
0x1400074c4  lea     rcx, [rbp+57h+var_80]
0x1400074c8  call    ??$Callback@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVCoreWindowEventArgs@234@@Foundation@Windows@@V_lambda_9917ab12da543e53efc8a56210ff7d5d_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVCoreWindowEventArgs@234@@Foundation@Windows@@@01@$$QEAV_lambda_9917ab12da543e53efc8a56210ff7d5d_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::CoreWindowEventArgs *>,_lambda_9917ab12da543e53efc8a56210ff7d5d_>(_lambda_9917ab12da543e53efc8a56210ff7d5d_ &&)
0x1400074cd  nop
0x1400074ce  mov     r14, [rbp+57h+var_80]
0x1400074d2  lea     r8, [rsi+0A0h]
0x1400074d9  mov     rdx, r14
0x1400074dc  mov     rcx, rdi
0x1400074df  mov     rax, rbx
0x1400074e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074e7  mov     edi, eax
0x1400074e9  test    r14, r14
0x1400074ec  jz      short loc_1400074FE
0x1400074ee  mov     rax, [r14]
0x1400074f1  mov     rcx, r14
0x1400074f4  mov     rax, [rax+10h]
0x1400074f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074fd  nop
0x1400074fe  test    edi, edi
0x140007500  jns     short loc_140007537
0x140007502  lea     rax, WPP_GLOBAL_Control
0x140007509  mov     rcx, cs:WPP_GLOBAL_Control
0x140007510  cmp     rcx, rax
0x140007513  jz      loc_1400075E7
0x140007519  test    byte ptr [rcx+44h], 2
0x14000751d  jz      loc_1400075E7
0x140007523  cmp     byte ptr [rcx+41h], 2
0x140007527  jb      loc_1400075E7
0x14000752d  mov     edx, 12h
0x140007532  jmp     loc_1400075D4
0x140007537  mov     rdi, [rbp+57h+var_48]
0x14000753b  mov     rax, [rdi]
0x14000753e  mov     rbx, [rax+30h]
0x140007542  lea     rax, ?HandleAcceleratorKeyEvent@AuthHostWebInstance@@AEAAJPEAUICoreDispatcher@Core@UI@Windows@@PEAUIAcceleratorKeyEventArgs@345@@Z; AuthHostWebInstance::HandleAcceleratorKeyEvent(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)
0x140007549  mov     [rbp+57h+var_70], rax
0x14000754d  mov     [rbp+57h+var_68], 0
0x140007554  mov     eax, [rbp+57h+var_64]
0x140007557  mov     [rbp+57h+var_64], eax
0x14000755a  mov     [rbp+57h+var_80], rsi
0x14000755e  lea     r8, [rbp+57h+var_70]
0x140007562  lea     rdx, [rbp+57h+var_80]
0x140007566  lea     rcx, [rbp+57h+string]
0x14000756a  call    ??0_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_@@QEAA@AEBQEAVAuthHostWebInstance@@AEBQ81@EAAJPEAUICoreWindow@Core@UI@Windows@@PEAUIWindowSizeChangedEventArgs@345@@Z@Z; _lambda_8d72cac82bd4635b5765a6b3ebc66f5e_::_lambda_8d72cac82bd4635b5765a6b3ebc66f5e_(AuthHostWebInstance * const &,long (AuthHostWebInstance::*const &)(Windows::UI::Core::ICoreWindow *,Windows::UI::Core::IWindowSizeChangedEventArgs *))
0x14000756f  mov     rdx, rax
0x140007572  lea     rcx, [rbp+57h+var_80]
0x140007576  call    ??$Callback@U?$ITypedEventHandler@PEAVCoreDispatcher@Core@UI@Windows@@PEAVAcceleratorKeyEventArgs@234@@Foundation@Windows@@V_lambda_766ca67daaea39a1a461b0c067384f4a_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCoreDispatcher@Core@UI@Windows@@PEAVAcceleratorKeyEventArgs@234@@Foundation@Windows@@@01@$$QEAV_lambda_766ca67daaea39a1a461b0c067384f4a_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_>(_lambda_766ca67daaea39a1a461b0c067384f4a_ &&)
0x14000757b  nop
0x14000757c  mov     r14, [rbp+57h+var_80]
  ... truncated ...
```
