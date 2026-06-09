# ApplicationActivationImpl::IsAppForeground(ushort *,bool *)

- ea: `0x1800788a4`
- end: `0x180078bf9`
- name: `?IsAppForeground@ApplicationActivationImpl@@AEAAJPEAGPEA_N@Z`
- size: `853`
- prototype: `__int64 __fastcall(ApplicationActivationImpl *__hidden this, unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007a7e8`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x180027c60`
- `0x180031540`
- `0x180038c70`
- `0x1800439dc`
- `0x18005ae90`
- `0x1800788a4`
- `0x18007ac88`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180078ba9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180078ba9`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800788e2`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800788e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078a55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078a91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078af8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078a55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078a91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078af8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078acf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078acf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007892d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007892d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180078b38`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180078b38`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ApplicationActivationImpl::IsAppForeground(ApplicationActivationImpl *this, char *a2, bool *a3)
{
  __int64 v5; // rbx
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, GUID *, __int64 *); // rdi
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64 *); // rdi
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  signed __int64 v21; // rax
  int v22; // edx
  int v23; // ecx
  CallerIdentity *ForegroundWindow; // rbx
  unsigned __int16 **v25; // r8
  int ImmersiveAppIdFromWindow; // eax
  struct HWND__ v27[2]; // [rsp+20h] [rbp-60h] BYREF
  __int64 v28; // [rsp+28h] [rbp-58h] BYREF
  __int64 v29; // [rsp+30h] [rbp-50h] BYREF
  int v30; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  __int64 v32; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v34; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a3 = 1;
  v30 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v30, 0);
  if ( v30 == 5 )
  {
    *(_QWORD *)&v27[0].unused = 0;
    v34 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.ApplicationModel.WindowManagement.Window",
      0x3Au,
      0x39u);
    v5 = v34;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v27);
    ActivationFactory = RoGetActivationFactory(v5, &GUID_5e75aba7_c424_4076_9d47_409a1eda087f, v27);
    v7 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36A,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v27[0].unused);
LABEL_15:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v27);
      return v7;
    }
    v29 = 0;
    v8 = *(_QWORD *)&v27[0].unused;
    v9 = ***(__int64 (__fastcall ****)(__int64, GUID *, __int64 *))&v27[0].unused;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
    v10 = v9(v8, &GUID_75fe1ae9_48db_43ed_a383_c199142860a9, &v29);
    if ( v10 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x36D,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v10,
        v27[0].unused);
    v28 = 0;
    v11 = v29;
    v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
    v13 = v12(v11, &v28);
    v7 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x370,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v13,
        v27[0].unused);
LABEL_14:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
      goto LABEL_15;
    }
    v14 = v28;
    if ( !v28 )
    {
      *a3 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
      v7 = 0;
      goto LABEL_15;
    }
    v32 = 0;
    v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
    v16 = v15(v14, &v32);
    v7 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x378,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v16,
        v27[0].unused);
LABEL_13:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
      goto LABEL_14;
    }
    string = 0;
    v17 = v32;
    v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v19 = v18(v17, &string);
    v7 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37B,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v19,
        v27[0].unused);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_13;
    }
    v21 = (char *)WindowsGetStringRawBuffer(string, 0) - a2;
    do
    {
      v22 = *(unsigned __int16 *)&a2[v21];
      v23 = *(unsigned __int16 *)a2 - v22;
      if ( v23 )
        break;
      a2 += 2;
    }
    while ( v22 );
    if ( v23 )
      *a3 = 0;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v27);
  }
  else if ( v30 == 3 )
  {
    ForegroundWindow = (CallerIdentity *)GetForegroundWindow();
    if ( ForegroundWindow )
    {
      *(_QWORD *)&v27[0].unused = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v27,
        0);
      ImmersiveAppIdFromWindow = CallerIdentity::GetImmersiveAppIdFromWindow(ForegroundWindow, v27, v25);
      v7 = ImmersiveAppIdFromWindow;
      if ( ImmersiveAppIdFromWindow == -2147023728 )
      {
        *a3 = 0;
        v7 = 0;
      }
      else
      {
        if ( ImmersiveAppIdFromWindow >= 0 )
        {
          if ( (unsigned int)_o__wcsicmp(a2, *(_QWORD *)&v27[0].unused) )
            *a3 = 0;
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v27);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x393,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
          (const char *)(unsigned int)ImmersiveAppIdFromWindow,
          v27[0].unused);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v27);
      return v7;
    }
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800788a4  mov     [rsp-28h+arg_0], rbx
0x1800788a9  push    rbp
0x1800788aa  push    rsi
0x1800788ab  push    rdi
0x1800788ac  push    r14
0x1800788ae  push    r15
0x1800788b0  mov     rbp, rsp
0x1800788b3  sub     rsp, 80h
0x1800788ba  mov     rax, cs:__security_cookie
0x1800788c1  xor     rax, rsp
0x1800788c4  mov     [rbp+var_10], rax
0x1800788c8  mov     rsi, r8
0x1800788cb  mov     r14, rdx
0x1800788ce  mov     byte ptr [r8], 1
0x1800788d2  xor     r15d, r15d
0x1800788d5  mov     [rbp+var_48], r15d
0x1800788d9  xor     r8d, r8d
0x1800788dc  lea     rdx, [rbp+var_48]
0x1800788e0  xor     ecx, ecx
0x1800788e2  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800788e8  cmp     [rbp+var_48], 5
0x1800788ec  jnz     loc_180078B2E
0x1800788f2  mov     qword ptr [rbp+var_60.unused], r15
0x1800788f6  mov     [rbp+var_18], r15
0x1800788fa  lea     r9d, [r15+39h]; unsigned int
0x1800788fe  lea     r8d, [r15+3Ah]; unsigned int
0x180078902  lea     rdx, ?RuntimeClass_Windows_Internal_ApplicationModel_WindowManagement_Window@@3QBGB; "Windows.Internal.ApplicationModel.Windo"...
0x180078909  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18007890d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180078912  mov     rbx, [rbp+var_18]
0x180078916  lea     rcx, [rbp+var_60]
0x18007891a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007891f  lea     r8, [rbp+var_60]
0x180078923  lea     rdx, _GUID_5e75aba7_c424_4076_9d47_409a1eda087f
0x18007892a  mov     rcx, rbx
0x18007892d  call    cs:__imp_RoGetActivationFactory
0x180078933  mov     ebx, eax
0x180078935  test    eax, eax
0x180078937  jns     short loc_180078956
0x180078939  mov     rcx, [rbp+28h]; this
0x18007893d  mov     r9d, eax; char *
0x180078940  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180078947  mov     edx, 36Ah; void *
0x18007894c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078951  jmp     loc_180078AB9
0x180078956  mov     [rbp+var_50], r15
0x18007895a  mov     rbx, qword ptr [rbp+var_60.unused]
0x18007895e  mov     rax, [rbx]
0x180078961  mov     rdi, [rax]
0x180078964  lea     rcx, [rbp+var_50]
0x180078968  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007896d  lea     r8, [rbp+var_50]
0x180078971  lea     rdx, _GUID_75fe1ae9_48db_43ed_a383_c199142860a9
0x180078978  mov     rcx, rbx
0x18007897b  mov     rax, rdi
0x18007897e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078983  nop
0x180078984  mov     rcx, [rbp+28h]; this
0x180078988  test    eax, eax
0x18007898a  js      loc_180078BE4
0x180078990  mov     [rbp+var_58], r15
0x180078994  mov     rdi, [rbp+var_50]
0x180078998  mov     rax, [rdi]
0x18007899b  mov     rbx, [rax+30h]
0x18007899f  lea     rcx, [rbp+var_58]
0x1800789a3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800789a8  lea     rdx, [rbp+var_58]
0x1800789ac  mov     rcx, rdi
0x1800789af  mov     rax, rbx
0x1800789b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800789b7  mov     ebx, eax
0x1800789b9  test    eax, eax
0x1800789bb  jns     short loc_1800789DA
0x1800789bd  mov     rcx, [rbp+28h]; this
0x1800789c1  mov     r9d, eax; char *
0x1800789c4  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800789cb  mov     edx, 370h; void *
0x1800789d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800789d5  jmp     loc_180078AA5
0x1800789da  mov     rbx, [rbp+var_58]
0x1800789de  test    rbx, rbx
0x1800789e1  jnz     short loc_180078A01
0x1800789e3  mov     [rsi], r15b
0x1800789e6  lea     rcx, [rbp+var_58]
0x1800789ea  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800789ef  nop
0x1800789f0  lea     rcx, [rbp+var_50]
0x1800789f4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800789f9  mov     ebx, r15d
0x1800789fc  jmp     loc_180078AB9
0x180078a01  mov     [rbp+var_38], r15
0x180078a05  mov     rax, [rbx]
0x180078a08  mov     rdi, [rax+30h]
0x180078a0c  lea     rcx, [rbp+var_38]
0x180078a10  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180078a15  lea     rdx, [rbp+var_38]
0x180078a19  mov     rcx, rbx
0x180078a1c  mov     rax, rdi
0x180078a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a24  mov     ebx, eax
0x180078a26  test    eax, eax
0x180078a28  jns     short loc_180078A44
0x180078a2a  mov     rcx, [rbp+28h]; this
0x180078a2e  mov     r9d, eax; char *
0x180078a31  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180078a38  mov     edx, 378h; void *
0x180078a3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078a42  jmp     short loc_180078A9B
0x180078a44  mov     [rbp+string], r15
0x180078a48  mov     rdi, [rbp+var_38]
0x180078a4c  mov     rax, [rdi]
0x180078a4f  mov     rbx, [rax+30h]
0x180078a53  xor     ecx, ecx; string
0x180078a55  call    cs:__imp_WindowsDeleteString
0x180078a5b  mov     [rbp+string], r15
0x180078a5f  lea     rdx, [rbp+string]
0x180078a63  mov     rcx, rdi
0x180078a66  mov     rax, rbx
0x180078a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a6e  mov     ebx, eax
0x180078a70  test    eax, eax
0x180078a72  jns     short loc_180078AC9
0x180078a74  mov     rcx, [rbp+28h]; this
0x180078a78  mov     r9d, eax; char *
0x180078a7b  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180078a82  mov     edx, 37Bh; void *
0x180078a87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078a8c  nop
0x180078a8d  mov     rcx, [rbp+string]; string
0x180078a91  call    cs:__imp_WindowsDeleteString
0x180078a97  mov     [rbp+string], r15
0x180078a9b  lea     rcx, [rbp+var_38]
0x180078a9f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180078aa4  nop
0x180078aa5  lea     rcx, [rbp+var_58]
0x180078aa9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180078aae  nop
0x180078aaf  lea     rcx, [rbp+var_50]
0x180078ab3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180078ab8  nop
0x180078ab9  lea     rcx, [rbp+var_60]
0x180078abd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180078ac2  mov     eax, ebx
0x180078ac4  jmp     loc_180078BC1
0x180078ac9  xor     edx, edx; length
0x180078acb  mov     rcx, [rbp+string]; string
0x180078acf  call    cs:__imp_WindowsGetStringRawBuffer
0x180078ad5  sub     rax, r14
0x180078ad8  movzx   ecx, word ptr [r14]
0x180078adc  movzx   edx, word ptr [r14+rax]
0x180078ae1  sub     ecx, edx
0x180078ae3  jnz     short loc_180078AED
0x180078ae5  add     r14, 2
0x180078ae9  test    edx, edx
0x180078aeb  jnz     short loc_180078AD8
0x180078aed  test    ecx, ecx
0x180078aef  jz      short loc_180078AF4
0x180078af1  mov     [rsi], r15b
0x180078af4  mov     rcx, [rbp+string]; string
0x180078af8  call    cs:__imp_WindowsDeleteString
0x180078afe  mov     [rbp+string], r15
0x180078b02  lea     rcx, [rbp+var_38]
0x180078b06  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180078b0b  nop
0x180078b0c  lea     rcx, [rbp+var_58]
0x180078b10  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180078b15  nop
0x180078b16  lea     rcx, [rbp+var_50]
0x180078b1a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180078b1f  nop
0x180078b20  lea     rcx, [rbp+var_60]
0x180078b24  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180078b29  jmp     loc_180078BBF
0x180078b2e  cmp     [rbp+var_48], 3
0x180078b32  jnz     loc_180078BBF
0x180078b38  call    cs:__imp_GetForegroundWindow
0x180078b3e  mov     rbx, rax
0x180078b41  test    rax, rax
0x180078b44  jnz     short loc_180078B4B
0x180078b46  mov     [rsi], r15b
0x180078b49  jmp     short loc_180078BBF
0x180078b4b  mov     qword ptr [rbp+var_60.unused], r15
0x180078b4f  xor     edx, edx
0x180078b51  lea     rcx, [rbp+var_60]
0x180078b55  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180078b5a  lea     rdx, [rbp+var_60]; HWND
0x180078b5e  mov     rcx, rbx; this
0x180078b61  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x180078b66  mov     ebx, eax
0x180078b68  cmp     eax, 80070490h
0x180078b6d  jnz     short loc_180078B77
0x180078b6f  mov     [rsi], r15b
0x180078b72  mov     ebx, r15d
0x180078b75  jmp     short loc_180078B94
0x180078b77  test    eax, eax
0x180078b79  jns     short loc_180078BA2
0x180078b7b  mov     rcx, [rbp+28h]; this
0x180078b7f  mov     r9d, eax; char *
0x180078b82  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180078b89  mov     edx, 393h; void *
0x180078b8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078b93  nop
0x180078b94  lea     rcx, [rbp+var_60]
0x180078b98  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180078b9d  jmp     loc_180078AC2
0x180078ba2  mov     rdx, qword ptr [rbp+var_60.unused]
0x180078ba6  mov     rcx, r14
0x180078ba9  call    cs:__imp__o__wcsicmp
0x180078baf  test    eax, eax
0x180078bb1  jz      short loc_180078BB6
0x180078bb3  mov     [rsi], r15b
0x180078bb6  lea     rcx, [rbp+var_60]
0x180078bba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180078bbf  xor     eax, eax
0x180078bc1  mov     rcx, [rbp+var_10]
0x180078bc5  xor     rcx, rsp; StackCookie
0x180078bc8  call    __security_check_cookie
0x180078bcd  mov     rbx, [rsp+80h+arg_0]
0x180078bd5  add     rsp, 80h
0x180078bdc  pop     r15
0x180078bde  pop     r14
0x180078be0  pop     rdi
0x180078be1  pop     rsi
0x180078be2  pop     rbp
0x180078be3  retn
0x180078be4  mov     r9d, eax; char *
0x180078be7  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180078bee  mov     edx, 36Dh; void *
0x180078bf3  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
