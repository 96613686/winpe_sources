# XpsToTiffConverter::XpsToTiffConverter::StartDocW(uint,IStream *,uint,IXpsRasterizationFactory2 *,IXpsRasterizerNotificationCallback *,char const *,char const *,_CRYPT_INFO *,_DOC_SETTINGS,IFilePoolTemp *)

- ea: `0x18000a870`
- end: `0x18000ab94`
- name: `?StartDocW@XpsToTiffConverter@1@UEAAJIPEAUIStream@@IPEAUIXpsRasterizationFactory2@@PEAUIXpsRasterizerNotificationCallback@@PEBD3PEAU_CRYPT_INFO@@U_DOC_SETTINGS@@PEAUIFilePoolTemp@@@Z`
- size: `804`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800016a0`
- `0x1800021ad`
- `0x18000a870`
- `0x18000b0ac`
- `0x18000b3ac`
- `0x18000b62c`
- `0x18000e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XpsToTiffConverter::XpsToTiffConverter::StartDocW(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  _QWORD *v13; // r14
  _QWORD *v14; // r14
  _QWORD *v15; // rbx
  HRESULT v16; // eax
  LPVOID v17; // rsi
  __int64 *v18; // rbx
  __int64 (__fastcall *v19)(__int64, __int64); // rsi
  int v20; // eax
  __int64 v21; // r15
  __int64 (__fastcall *v22)(__int64, __int64); // r12
  _QWORD *v23; // rsi
  int v24; // eax
  int v25; // eax
  __int64 v26; // rbx
  __int64 (__fastcall *v27)(__int64, GUID *, _QWORD, __int64); // r14
  int v28; // eax
  int v29; // eax
  const char *v30; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-88h]
  int ppva; // [rsp+20h] [rbp-88h]
  LPVOID v34; // [rsp+30h] [rbp-78h] BYREF
  LPVOID v35; // [rsp+38h] [rbp-70h] BYREF
  int v36; // [rsp+40h] [rbp-68h] BYREF
  __int128 v37; // [rsp+48h] [rbp-60h]
  IID rclsid; // [rsp+58h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  try
  {
    if ( !a11 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)0x80070057LL,
        ppv);
    *(_DWORD *)(a1 + 24) = a4;
    v13 = (_QWORD *)(a1 + 32);
    if ( *(_QWORD *)(a1 + 32) != a5 )
    {
      if ( *v13 )
        winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(a1 + 32);
      *v13 = a5;
      if ( a5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 8LL))(a5);
    }
    v14 = (_QWORD *)(a1 + 40);
    if ( *(_QWORD *)(a1 + 40) != a6 )
    {
      if ( *v14 )
        winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(a1 + 40);
      *v14 = a6;
      if ( a6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 8LL))(a6);
    }
    v15 = (_QWORD *)(a1 + 72);
    if ( *(_QWORD *)(a1 + 72) != a3 )
    {
      if ( *v15 )
        winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(a1 + 72);
      *v15 = a3;
      if ( a3 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
    }
    rclsid.Data1 = 830277352;
    *(_DWORD *)&rclsid.Data2 = 1128095524;
    *(_DWORD *)rclsid.Data4 = -830867523;
    *(_DWORD *)&rclsid.Data4[4] = -1028925336;
    v34 = 0;
    v36 = 0;
    v37 = 0;
    v16 = CoCreateInstance_0(&rclsid, 0, 1u, &winrt::impl::guid_v<IWICImagingFactory>, &v34);
    if ( v16 < 0 )
      winrt::throw_hresult((unsigned int)v16, &v36);
    v17 = v34;
    v35 = v34;
    v18 = (__int64 *)(a1 + 64);
    if ( (LPVOID *)(a1 + 64) == &v35 )
    {
      if ( v34 )
        winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(&v35);
    }
    else
    {
      if ( *v18 )
        winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(a1 + 64);
      *v18 = (__int64)v17;
    }
    v19 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a11 + 24LL);
    if ( *(_QWORD *)(a1 + 80) )
      winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(a1 + 80);
    v20 = v19(a11, a1 + 80);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x19,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)v20,
        ppva);
    v21 = *v18;
    v22 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)*v18 + 112LL);
    v23 = (_QWORD *)(a1 + 48);
    if ( *(_QWORD *)(a1 + 48) )
      winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(a1 + 48);
    v24 = v22(v21, a1 + 48);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1A,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)v24,
        ppva);
    v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v23 + 112LL))(*v23, *(_QWORD *)(a1 + 80));
    if ( v25 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)v25,
        ppva);
    v26 = *v18;
    v27 = *(__int64 (__fastcall **)(__int64, GUID *, _QWORD, __int64))(*(_QWORD *)v26 + 64LL);
    if ( *(_QWORD *)(a1 + 56) )
      winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(a1 + 56);
    v28 = v27(v26, &GUID_ContainerFormatTiff, 0, a1 + 56);
    if ( v28 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)v28,
        ppva);
    v29 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 56) + 24LL))(
            *(_QWORD *)(a1 + 56),
            *v23,
            2);
    if ( v29 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1E,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)v29,
        ppva);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x21,
                           (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpsto"
                                         "tiffconverter.cpp",
                           v30);
  }
  return result;
}

```

## disassembly

```asm
0x18000a870  push    rbx
0x18000a872  push    rsi
0x18000a873  push    rdi
0x18000a874  push    r12
0x18000a876  push    r14
0x18000a878  push    r15
0x18000a87a  sub     rsp, 78h
0x18000a87e  mov     rax, cs:__security_cookie
0x18000a885  xor     rax, rsp
0x18000a888  mov     [rsp+0A8h+var_40], rax
0x18000a88d  mov     rsi, r8
0x18000a890  mov     rdi, rcx
0x18000a893  mov     r15, [rsp+0A8h+arg_50]
0x18000a89b  mov     rcx, [rsp+0A8h]; this
0x18000a8a3  test    r15, r15
0x18000a8a6  jz      loc_18000AB0C
0x18000a8ac  mov     [rdi+18h], r9d
0x18000a8b0  lea     r14, [rdi+20h]
0x18000a8b4  mov     rbx, [rsp+0A8h+arg_20]
0x18000a8bc  cmp     [r14], rbx
0x18000a8bf  jz      short loc_18000A8E7
0x18000a8c1  cmp     qword ptr [r14], 0
0x18000a8c5  jz      short loc_18000A8CF
0x18000a8c7  mov     rcx, r14
0x18000a8ca  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000a8cf  mov     [r14], rbx
0x18000a8d2  test    rbx, rbx
0x18000a8d5  jz      short loc_18000A8E7
0x18000a8d7  mov     rax, [rbx]
0x18000a8da  mov     rcx, rbx
0x18000a8dd  mov     rax, [rax+8]
0x18000a8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8e6  nop
0x18000a8e7  lea     r14, [rdi+28h]
0x18000a8eb  mov     rbx, [rsp+0A8h+arg_28]
0x18000a8f3  cmp     [r14], rbx
0x18000a8f6  jz      short loc_18000A91E
0x18000a8f8  cmp     qword ptr [r14], 0
0x18000a8fc  jz      short loc_18000A906
0x18000a8fe  mov     rcx, r14
0x18000a901  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000a906  mov     [r14], rbx
0x18000a909  test    rbx, rbx
0x18000a90c  jz      short loc_18000A91E
0x18000a90e  mov     rax, [rbx]
0x18000a911  mov     rcx, rbx
0x18000a914  mov     rax, [rax+8]
0x18000a918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a91d  nop
0x18000a91e  lea     rbx, [rdi+48h]
0x18000a922  cmp     [rbx], rsi
0x18000a925  jz      short loc_18000A94D
0x18000a927  cmp     qword ptr [rbx], 0
0x18000a92b  jz      short loc_18000A935
0x18000a92d  mov     rcx, rbx
0x18000a930  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000a935  mov     [rbx], rsi
0x18000a938  test    rsi, rsi
0x18000a93b  jz      short loc_18000A94D
0x18000a93d  mov     rax, [rsi]
0x18000a940  mov     rcx, rsi
0x18000a943  mov     rax, [rax+8]
0x18000a947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a94c  nop
0x18000a94d  mov     [rsp+0A8h+rclsid.Data1], 317D06E8h
0x18000a955  mov     dword ptr [rsp+0A8h+rclsid.Data2], 433D5F24h
0x18000a95d  mov     dword ptr [rsp+0A8h+rclsid.Data4], 0CE79F7BDh
0x18000a965  mov     dword ptr [rsp+0A8h+rclsid.Data4+4], 0C2ABD868h
0x18000a96d  mov     [rsp+0A8h+var_78], 0
0x18000a976  mov     [rsp+0A8h+var_68], 0
0x18000a97e  xorps   xmm0, xmm0
0x18000a981  movdqu  [rsp+0A8h+var_60], xmm0
0x18000a987  lea     rax, [rsp+0A8h+var_78]
0x18000a98c  mov     qword ptr [rsp+0A8h+ppv], rax; int
0x18000a991  lea     r9, ??$guid_v@UIWICImagingFactory@@@impl@winrt@@3Uguid@2@B; riid
0x18000a998  xor     edx, edx; pUnkOuter
0x18000a99a  lea     r8d, [rdx+1]; dwClsContext
0x18000a99e  lea     rcx, [rsp+0A8h+rclsid]; rclsid
0x18000a9a3  call    CoCreateInstance_0
0x18000a9a8  test    eax, eax
0x18000a9aa  js      loc_18000AB22
0x18000a9b0  mov     rsi, [rsp+0A8h+var_78]
0x18000a9b5  mov     [rsp+0A8h+var_70], rsi
0x18000a9ba  lea     rbx, [rdi+40h]
0x18000a9be  lea     rax, [rsp+0A8h+var_70]
0x18000a9c3  cmp     rbx, rax
0x18000a9c6  jz      short loc_18000A9DB
0x18000a9c8  cmp     qword ptr [rbx], 0
0x18000a9cc  jz      short loc_18000A9D6
0x18000a9ce  mov     rcx, rbx
0x18000a9d1  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000a9d6  mov     [rbx], rsi
0x18000a9d9  jmp     short loc_18000A9EA
0x18000a9db  test    rsi, rsi
0x18000a9de  jz      short loc_18000A9EA
0x18000a9e0  lea     rcx, [rsp+0A8h+var_70]
0x18000a9e5  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000a9ea  mov     rax, [r15]
0x18000a9ed  mov     rsi, [rax+18h]
0x18000a9f1  lea     r14, [rdi+50h]
0x18000a9f5  cmp     qword ptr [r14], 0
0x18000a9f9  jz      short loc_18000AA03
0x18000a9fb  mov     rcx, r14
0x18000a9fe  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000aa03  mov     rdx, r14
0x18000aa06  mov     rcx, r15
0x18000aa09  mov     rax, rsi
0x18000aa0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa11  mov     rcx, [rsp+0A8h]; this
0x18000aa19  test    eax, eax
0x18000aa1b  js      loc_18000AB2E
0x18000aa21  mov     r15, [rbx]
0x18000aa24  mov     rax, [r15]
0x18000aa27  mov     r12, [rax+70h]
0x18000aa2b  lea     rsi, [rdi+30h]
0x18000aa2f  cmp     qword ptr [rsi], 0
0x18000aa33  jz      short loc_18000AA3D
0x18000aa35  mov     rcx, rsi
0x18000aa38  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000aa3d  mov     rdx, rsi
0x18000aa40  mov     rcx, r15
0x18000aa43  mov     rax, r12
0x18000aa46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa4b  mov     rcx, [rsp+0A8h]; this
0x18000aa53  test    eax, eax
0x18000aa55  js      loc_18000AB42
0x18000aa5b  mov     rcx, [rsi]
0x18000aa5e  mov     rax, [rcx]
0x18000aa61  mov     rdx, [r14]
0x18000aa64  mov     rax, [rax+70h]
0x18000aa68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa6d  mov     rcx, [rsp+0A8h]; this
0x18000aa75  test    eax, eax
0x18000aa77  js      loc_18000AB56
0x18000aa7d  mov     rbx, [rbx]
0x18000aa80  mov     rax, [rbx]
0x18000aa83  mov     r14, [rax+40h]
0x18000aa87  cmp     qword ptr [rdi+38h], 0
0x18000aa8c  jz      short loc_18000AA97
0x18000aa8e  lea     rcx, [rdi+38h]
0x18000aa92  call    ?unconditional_release_ref@?$com_ptr@UIXpsRasterizerNotificationCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IXpsRasterizerNotificationCallback>::unconditional_release_ref(void)
0x18000aa97  lea     r9, [rdi+38h]
0x18000aa9b  xor     r8d, r8d
0x18000aa9e  lea     rdx, GUID_ContainerFormatTiff
0x18000aaa5  mov     rcx, rbx
0x18000aaa8  mov     rax, r14
0x18000aaab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aab0  mov     rcx, [rsp+0A8h]; this
0x18000aab8  test    eax, eax
0x18000aaba  js      loc_18000AB6A
0x18000aac0  mov     rcx, [rdi+38h]
0x18000aac4  mov     rax, [rcx]
0x18000aac7  mov     r8d, 2
0x18000aacd  mov     rdx, [rsi]
0x18000aad0  mov     rax, [rax+18h]
0x18000aad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aad9  mov     rcx, [rsp+0A8h]; this
0x18000aae1  test    eax, eax
0x18000aae3  js      loc_18000AB7E
0x18000aae9  xor     eax, eax
0x18000aaeb  jmp     short loc_18000AAF1
0x18000aaed  mov     eax, dword ptr [rsp+0A8h+var_78]
0x18000aaf1  mov     rcx, [rsp+0A8h+var_40]
0x18000aaf6  xor     rcx, rsp; StackCookie
0x18000aaf9  call    __security_check_cookie
0x18000aafe  add     rsp, 78h
0x18000ab02  pop     r15
0x18000ab04  pop     r14
0x18000ab06  pop     r12
0x18000ab08  pop     rdi
0x18000ab09  pop     rsi
0x18000ab0a  pop     rbx
0x18000ab0b  retn
0x18000ab0c  mov     r9d, 80070057h; char *
0x18000ab12  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000ab19  lea     edx, [r15+0Fh]; void *
0x18000ab1d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ab22  lea     rdx, [rsp+0A8h+var_68]
0x18000ab27  mov     ecx, eax
0x18000ab29  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000ab2e  mov     r9d, eax; char *
0x18000ab31  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000ab38  mov     edx, 19h; void *
0x18000ab3d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ab42  mov     r9d, eax; char *
0x18000ab45  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000ab4c  mov     edx, 1Ah; void *
0x18000ab51  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ab56  mov     r9d, eax; char *
0x18000ab59  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000ab60  mov     edx, 1Bh; void *
0x18000ab65  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ab6a  mov     r9d, eax; char *
0x18000ab6d  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000ab74  mov     edx, 1Dh; void *
0x18000ab79  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ab7e  mov     r9d, eax; char *
0x18000ab81  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000ab88  mov     edx, 1Eh; void *
0x18000ab8d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
