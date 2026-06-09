# VideoFrameImpl::CopyPropertiesFrom(Windows::Media::IMediaFrame *)

- ea: `0x18000e740`
- end: `0x18000ea61`
- name: `?CopyPropertiesFrom@VideoFrameImpl@@AEAAXPEAUIMediaFrame@Media@Windows@@@Z`
- size: `801`
- prototype: `void __fastcall(VideoFrameImpl *__hidden this, struct Windows::Media::IMediaFrame *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001e07c`

## callees

- `0x1800019c0`
- `0x180005cd0`
- `0x18000e740`
- `0x18000ee0c`
- `0x18000ee80`
- `0x1800223ac`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e8f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e98a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e8f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e98a`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall VideoFrameImpl::CopyPropertiesFrom(VideoFrameImpl *this, struct Windows::Media::IMediaFrame *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Media::IMediaFrame *, char *); // rdi
  unsigned int v5; // eax
  int v6; // edx
  __int64 (__fastcall *v7)(struct Windows::Media::IMediaFrame *, char *); // rdi
  unsigned int v8; // eax
  int v9; // edx
  __int64 (__fastcall *v10)(struct Windows::Media::IMediaFrame *, char *); // rdi
  unsigned int v11; // eax
  int v12; // edx
  unsigned int v13; // eax
  int v14; // edx
  __int64 (__fastcall *v15)(struct Windows::Media::IMediaFrame *, __int64 *); // rbx
  unsigned int v16; // eax
  int v17; // edx
  unsigned int v18; // eax
  int v19; // edx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  unsigned int v22; // eax
  int v23; // edx
  unsigned int v24; // eax
  int v25; // edx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64 *); // rbx
  unsigned int v28; // eax
  int v29; // edx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, HSTRING *); // rbx
  unsigned int v32; // eax
  int v33; // edx
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int64 *); // rbx
  unsigned int v36; // eax
  int v37; // edx
  unsigned int v38; // eax
  int v39; // edx
  unsigned int v40; // eax
  int v41; // edx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  HSTRING string; // [rsp+30h] [rbp-48h] BYREF
  __int64 v50; // [rsp+38h] [rbp-40h] BYREF
  __int64 v51; // [rsp+40h] [rbp-38h] BYREF
  __int64 v52; // [rsp+48h] [rbp-30h] BYREF
  __int64 v53; // [rsp+50h] [rbp-28h] BYREF
  __int64 v54; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v55[3]; // [rsp+60h] [rbp-18h] BYREF
  char v56; // [rsp+B0h] [rbp+38h] BYREF
  char v57; // [rsp+B8h] [rbp+40h] BYREF
  char v58; // [rsp+C0h] [rbp+48h] BYREF
  __int64 v59; // [rsp+C8h] [rbp+50h] BYREF

  v4 = *(__int64 (__fastcall **)(struct Windows::Media::IMediaFrame *, char *))(*(_QWORD *)a2 + 72LL);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease((char *)this + 56);
  v5 = v4(a2, (char *)this + 56);
  MF::ThrowIfFailed((MF *)v5, v6);
  v7 = *(__int64 (__fastcall **)(struct Windows::Media::IMediaFrame *, char *))(*(_QWORD *)a2 + 88LL);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease((char *)this + 64);
  v8 = v7(a2, (char *)this + 64);
  MF::ThrowIfFailed((MF *)v8, v9);
  v10 = *(__int64 (__fastcall **)(struct Windows::Media::IMediaFrame *, char *))(*(_QWORD *)a2 + 104LL);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease((char *)this + 72);
  v11 = v10(a2, (char *)this + 72);
  MF::ThrowIfFailed((MF *)v11, v12);
  v57 = 0;
  v13 = (*(__int64 (__fastcall **)(struct Windows::Media::IMediaFrame *, char *))(*(_QWORD *)a2 + 120LL))(a2, &v57);
  MF::ThrowIfFailed((MF *)v13, v14);
  *((_BYTE *)this + 50) = v57 != 0;
  v52 = 0;
  v15 = *(__int64 (__fastcall **)(struct Windows::Media::IMediaFrame *, __int64 *))(*(_QWORD *)a2 + 128LL);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v52);
  v16 = v15(a2, &v52);
  MF::ThrowIfFailed((MF *)v16, v17);
  MF::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet>(
    v55,
    &v52);
  MF::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,MediaFramePropertySetImpl>(
    &v53,
    (char *)this + 80);
  v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v53 + 96LL))(v53);
  MF::ThrowIfFailed((MF *)v18, v19);
  MF::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
    &v54,
    v55);
  v59 = 0;
  v20 = v54;
  v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 48LL);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v59);
  v22 = v21(v20, &v59);
  MF::ThrowIfFailed((MF *)v22, v23);
  v56 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v59 + 56LL))(v59, &v56);
  MF::ThrowIfFailed((MF *)v24, v25);
  while ( v56 )
  {
    v50 = 0;
    v51 = 0;
    string = 0;
    v26 = v59;
    v27 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 48LL);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v50);
    v28 = v27(v26, &v50);
    MF::ThrowIfFailed((MF *)v28, v29);
    v30 = v50;
    v31 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v50 + 48LL);
    WindowsDeleteString(string);
    string = 0;
    v32 = v31(v30, &string);
    MF::ThrowIfFailed((MF *)v32, v33);
    v34 = v50;
    v35 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 56LL);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v51);
    v36 = v35(v34, &v51);
    MF::ThrowIfFailed((MF *)v36, v37);
    v58 = 0;
    v38 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, char *))(*(_QWORD *)v53 + 80LL))(v53, string, v51, &v58);
    MF::ThrowIfFailed((MF *)v38, v39);
    v40 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v59 + 64LL))(v59, &v56);
    MF::ThrowIfFailed((MF *)v40, v41);
    WindowsDeleteString(string);
    string = 0;
    v42 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v43 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
  }
  v44 = v59;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v47 = v55[0];
  if ( v55[0] )
  {
    v55[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v48 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
}

```

## disassembly

```asm
0x18000e740  push    rbp
0x18000e742  push    rbx
0x18000e743  push    rsi
0x18000e744  push    rdi
0x18000e745  push    r14
0x18000e747  push    r15
0x18000e749  mov     rbp, rsp
0x18000e74c  sub     rsp, 78h
0x18000e750  mov     rsi, rdx
0x18000e753  mov     r14, rcx
0x18000e756  xor     r15d, r15d
0x18000e759  mov     rax, [rdx]
0x18000e75c  mov     rdi, [rax+48h]
0x18000e760  add     rcx, 38h ; '8'
0x18000e764  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000e769  lea     rdx, [r14+38h]
0x18000e76d  mov     rcx, rsi
0x18000e770  mov     rax, rdi
0x18000e773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e778  mov     ecx, eax; this
0x18000e77a  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e77f  mov     rax, [rsi]
0x18000e782  mov     rdi, [rax+58h]
0x18000e786  lea     rcx, [r14+40h]
0x18000e78a  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000e78f  lea     rdx, [r14+40h]
0x18000e793  mov     rcx, rsi
0x18000e796  mov     rax, rdi
0x18000e799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e79e  mov     ecx, eax; this
0x18000e7a0  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e7a5  mov     rax, [rsi]
0x18000e7a8  mov     rdi, [rax+68h]
0x18000e7ac  lea     rcx, [r14+48h]
0x18000e7b0  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000e7b5  lea     rdx, [r14+48h]
0x18000e7b9  mov     rcx, rsi
0x18000e7bc  mov     rax, rdi
0x18000e7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7c4  mov     ecx, eax; this
0x18000e7c6  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e7cb  mov     [rbp+arg_8], r15b
0x18000e7cf  mov     rax, [rsi]
0x18000e7d2  lea     rdx, [rbp+arg_8]
0x18000e7d6  mov     rcx, rsi
0x18000e7d9  mov     rax, [rax+78h]
0x18000e7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7e2  mov     ecx, eax; this
0x18000e7e4  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e7e9  cmp     [rbp+arg_8], r15b
0x18000e7ed  setnz   al
0x18000e7f0  mov     [r14+32h], al
0x18000e7f4  mov     [rbp+var_30], r15
0x18000e7f8  mov     rax, [rsi]
0x18000e7fb  mov     rbx, [rax+80h]
0x18000e802  lea     rcx, [rbp+var_30]
0x18000e806  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000e80b  lea     rdx, [rbp+var_30]
0x18000e80f  mov     rcx, rsi
0x18000e812  mov     rax, rbx
0x18000e815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e81a  mov     ecx, eax; this
0x18000e81c  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e821  lea     rdx, [rbp+var_30]
0x18000e825  lea     rcx, [rbp+var_18]
0x18000e829  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@UIPropertySet@234@@MF@@YA?AV?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@23@@Z; MF::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet>(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> const &)
0x18000e82e  nop
0x18000e82f  lea     rdx, [r14+50h]
0x18000e833  lea     rcx, [rbp+var_28]
0x18000e837  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@VMediaFramePropertySetImpl@@@MF@@YA?AV?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@VMediaFramePropertySetImpl@@@23@@Z; MF::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,MediaFramePropertySetImpl>(Microsoft::WRL::ComPtr<MediaFramePropertySetImpl> const &)
0x18000e83c  nop
0x18000e83d  mov     rcx, [rbp+var_28]
0x18000e841  mov     rax, [rcx]
0x18000e844  mov     rax, [rax+60h]
0x18000e848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e84d  mov     ecx, eax; this
0x18000e84f  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e854  lea     rdx, [rbp+var_18]
0x18000e858  lea     rcx, [rbp+var_20]
0x18000e85c  call    ??$As@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@234@@MF@@YA?AV?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@23@@Z; MF::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>> const &)
0x18000e861  nop
0x18000e862  mov     [rbp+arg_18], r15
0x18000e866  mov     rdi, [rbp+var_20]
0x18000e86a  mov     rax, [rdi]
0x18000e86d  mov     rbx, [rax+30h]
0x18000e871  lea     rcx, [rbp+arg_18]
0x18000e875  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000e87a  lea     rdx, [rbp+arg_18]
0x18000e87e  mov     rcx, rdi
0x18000e881  mov     rax, rbx
0x18000e884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e889  mov     ecx, eax; this
0x18000e88b  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e890  mov     [rbp+arg_0], r15b
0x18000e894  mov     rcx, [rbp+arg_18]
0x18000e898  mov     rax, [rcx]
0x18000e89b  lea     rdx, [rbp+arg_0]
0x18000e89f  mov     rax, [rax+38h]
0x18000e8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8a8  mov     ecx, eax; this
0x18000e8aa  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e8af  jmp     loc_18000E9C8
0x18000e8b4  mov     [rbp+var_40], r15
0x18000e8b8  mov     [rbp+var_38], r15
0x18000e8bc  mov     [rbp+string], r15
0x18000e8c0  mov     rdi, [rbp+arg_18]
0x18000e8c4  mov     rax, [rdi]
0x18000e8c7  mov     rbx, [rax+30h]
0x18000e8cb  lea     rcx, [rbp+var_40]
0x18000e8cf  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000e8d4  lea     rdx, [rbp+var_40]
0x18000e8d8  mov     rcx, rdi
0x18000e8db  mov     rax, rbx
0x18000e8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8e3  mov     ecx, eax; this
0x18000e8e5  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e8ea  mov     rdi, [rbp+var_40]
0x18000e8ee  mov     rax, [rdi]
0x18000e8f1  mov     rbx, [rax+30h]
0x18000e8f5  mov     rcx, [rbp+string]; string
0x18000e8f9  call    cs:__imp_WindowsDeleteString
0x18000e8ff  mov     [rbp+string], r15
0x18000e903  lea     rdx, [rbp+string]
0x18000e907  mov     rcx, rdi
0x18000e90a  mov     rax, rbx
0x18000e90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e912  mov     ecx, eax; this
0x18000e914  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e919  mov     rdi, [rbp+var_40]
0x18000e91d  mov     rax, [rdi]
0x18000e920  mov     rbx, [rax+38h]
0x18000e924  lea     rcx, [rbp+var_38]
0x18000e928  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000e92d  lea     rdx, [rbp+var_38]
0x18000e931  mov     rcx, rdi
0x18000e934  mov     rax, rbx
0x18000e937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e93c  mov     ecx, eax; this
0x18000e93e  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e943  mov     [rbp+arg_10], r15b
0x18000e947  mov     rcx, [rbp+var_28]
0x18000e94b  mov     rax, [rcx]
0x18000e94e  lea     r9, [rbp+arg_10]
0x18000e952  mov     r8, [rbp+var_38]
0x18000e956  mov     rdx, [rbp+string]
0x18000e95a  mov     rax, [rax+50h]
0x18000e95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e963  mov     ecx, eax; this
0x18000e965  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e96a  mov     rcx, [rbp+arg_18]
0x18000e96e  mov     rax, [rcx]
0x18000e971  lea     rdx, [rbp+arg_0]
0x18000e975  mov     rax, [rax+40h]
0x18000e979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e97e  mov     ecx, eax; this
0x18000e980  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000e985  nop
0x18000e986  mov     rcx, [rbp+string]; string
0x18000e98a  call    cs:__imp_WindowsDeleteString
0x18000e990  mov     [rbp+string], r15
0x18000e994  mov     rcx, [rbp+var_38]
0x18000e998  test    rcx, rcx
0x18000e99b  jz      short loc_18000E9AE
0x18000e99d  mov     [rbp+var_38], r15
0x18000e9a1  mov     rax, [rcx]
0x18000e9a4  mov     rax, [rax+10h]
0x18000e9a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9ad  nop
0x18000e9ae  mov     rcx, [rbp+var_40]
0x18000e9b2  test    rcx, rcx
0x18000e9b5  jz      short loc_18000E9C8
0x18000e9b7  mov     [rbp+var_40], r15
0x18000e9bb  mov     rax, [rcx]
0x18000e9be  mov     rax, [rax+10h]
0x18000e9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9c7  nop
0x18000e9c8  cmp     [rbp+arg_0], r15b
0x18000e9cc  jnz     loc_18000E8B4
0x18000e9d2  mov     rcx, [rbp+arg_18]
0x18000e9d6  test    rcx, rcx
0x18000e9d9  jz      short loc_18000E9EC
0x18000e9db  mov     [rbp+arg_18], r15
0x18000e9df  mov     rax, [rcx]
0x18000e9e2  mov     rax, [rax+10h]
0x18000e9e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9eb  nop
0x18000e9ec  mov     rcx, [rbp+var_20]
0x18000e9f0  test    rcx, rcx
0x18000e9f3  jz      short loc_18000EA06
0x18000e9f5  mov     [rbp+var_20], r15
0x18000e9f9  mov     rax, [rcx]
0x18000e9fc  mov     rax, [rax+10h]
0x18000ea00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea05  nop
0x18000ea06  mov     rcx, [rbp+var_28]
0x18000ea0a  test    rcx, rcx
0x18000ea0d  jz      short loc_18000EA20
0x18000ea0f  mov     [rbp+var_28], r15
0x18000ea13  mov     rax, [rcx]
0x18000ea16  mov     rax, [rax+10h]
0x18000ea1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea1f  nop
0x18000ea20  mov     rcx, [rbp+var_18]
0x18000ea24  test    rcx, rcx
0x18000ea27  jz      short loc_18000EA3A
0x18000ea29  mov     [rbp+var_18], r15
0x18000ea2d  mov     rax, [rcx]
0x18000ea30  mov     rax, [rax+10h]
0x18000ea34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea39  nop
0x18000ea3a  mov     rcx, [rbp+var_30]
0x18000ea3e  test    rcx, rcx
0x18000ea41  jz      short loc_18000EA54
0x18000ea43  mov     [rbp+var_30], r15
0x18000ea47  mov     rax, [rcx]
0x18000ea4a  mov     rax, [rax+10h]
0x18000ea4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea53  nop
0x18000ea54  add     rsp, 78h
0x18000ea58  pop     r15
0x18000ea5a  pop     r14
0x18000ea5c  pop     rdi
0x18000ea5d  pop     rsi
0x18000ea5e  pop     rbx
0x18000ea5f  pop     rbp
0x18000ea60  retn
```
