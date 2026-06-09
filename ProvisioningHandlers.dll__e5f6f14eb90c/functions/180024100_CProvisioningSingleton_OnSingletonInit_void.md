# CProvisioningSingleton::OnSingletonInit(void)

- ea: `0x180024100`
- end: `0x1800242f2`
- name: `?OnSingletonInit@CProvisioningSingleton@@MEAAJXZ`
- size: `498`
- prototype: `__int64 __fastcall(CProvisioningSingleton *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800034b8`
- `0x1800067fc`
- `0x1800087ec`
- `0x1800136cc`
- `0x180019c10`
- `0x180022524`
- `0x180022594`
- `0x180022864`
- `0x180024100`
- `0x180024408`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024130`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024130`

## string_xrefs

- `0x18002421e`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CProvisioningSingleton::OnSingletonInit(CProvisioningSingleton *this)
{
  char *v2; // rbx
  int v3; // eax
  int v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  void **v7; // rdi
  CProvisioningSingleton *v8; // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, CProvisioningSingleton *, char *); // rbx
  __int64 v11; // rax
  CProvisioningSingleton *v12; // r14
  CProvisioningSingleton *v14; // [rsp+20h] [rbp-50h] BYREF
  __int64 v15; // [rsp+28h] [rbp-48h] BYREF
  __int64 (__fastcall *v16)(CProvisioningSingleton *__hidden, struct IInspectable *, struct IInspectable *); // [rsp+30h] [rbp-40h] BYREF
  char *v17; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v2 = (char *)this + 248;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  v17 = v2;
  v15 = 0;
  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.Core.CoreApplication",
    0x2Eu,
    0x2Du);
  v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplication>>(
         v19,
         &v15);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v7 = (void **)((char *)this + 232);
    v8 = (CProvisioningSingleton *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
    v14 = v8;
    if ( v8 )
    {
      *(_QWORD *)v8 = &PluginEngine::`vftable';
      *((_QWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 3) = 0;
      *((_QWORD *)v8 + 4) = 0;
      *((_QWORD *)v8 + 5) = 0;
      *((_QWORD *)v8 + 6) = 0;
      *((_DWORD *)v8 + 14) = 0;
    }
    else
    {
      v8 = 0;
    }
    if ( v8 == *v7 )
    {
      v8 = (CProvisioningSingleton *)*v7;
    }
    else
    {
      std::unique_ptr<PluginEngine>::_Delete((char *)this + 232);
      *v7 = v8;
    }
    if ( v8 )
    {
      (*(void (__fastcall **)(CProvisioningSingleton *, __int64))(*(_QWORD *)v8 + 72LL))(v8, 1);
      v9 = v15;
      v10 = *(__int64 (__fastcall **)(__int64, CProvisioningSingleton *, char *))(*(_QWORD *)v15 + 72LL);
      v16 = CProvisioningSingleton::OnResuming;
      v14 = this;
      v11 = _lambda_4885db004e1493983883bfbd4778eeeb_::_lambda_4885db004e1493983883bfbd4778eeeb_(
              &hstringHeader,
              &v14,
              &v16);
      Microsoft::WRL::Callback<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_4885db004e1493983883bfbd4778eeeb_>(
        &v14,
        v11);
      v12 = v14;
      v4 = v10(v9, v14, (char *)this + 240);
      if ( v12 )
        (*(void (__fastcall **)(CProvisioningSingleton *))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v4 >= 0 )
      {
        v4 = 0;
        goto LABEL_18;
      }
      v6 = 56;
    }
    else
    {
      v4 = -2147024882;
      v6 = 50;
    }
    v5 = (unsigned int)v4;
  }
  else
  {
    v5 = (unsigned int)v3;
    v6 = 47;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
    (const char *)v5,
    (int)v14);
LABEL_18:
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v15);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v17);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180024100  mov     [rsp-18h+arg_8], rbx
0x180024105  mov     [rsp-18h+arg_10], rsi
0x18002410a  push    rbp
0x18002410b  push    rdi
0x18002410c  push    r14
0x18002410e  mov     rbp, rsp
0x180024111  sub     rsp, 70h
0x180024115  mov     rax, cs:__security_cookie
0x18002411c  xor     rax, rsp
0x18002411f  mov     [rbp+var_10], rax
0x180024123  mov     rsi, rcx
0x180024126  lea     rbx, [rcx+0F8h]
0x18002412d  mov     rcx, rbx; lpCriticalSection
0x180024130  call    cs:__imp_EnterCriticalSection
0x180024137  nop     dword ptr [rax+rax+00h]
0x18002413c  mov     [rbp+var_38], rbx
0x180024140  mov     [rbp+var_48], 0
0x180024148  mov     [rbp+var_18], 0
0x180024150  mov     r9d, 2Dh ; '-'; unsigned int
0x180024156  lea     r8d, [r9+1]; unsigned int
0x18002415a  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; "Windows.ApplicationModel.Core.CoreAppli"...
0x180024161  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180024165  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002416a  lea     rdx, [rbp+var_48]
0x18002416e  mov     rcx, [rbp+var_18]
0x180024172  call    ??$GetActivationFactory@V?$ComPtr@UICoreApplication@Core@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICoreApplication@Core@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplication>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplication>>)
0x180024177  mov     ebx, eax
0x180024179  test    eax, eax
0x18002417b  jns     short loc_18002418A
0x18002417d  mov     r9d, eax
0x180024180  mov     edx, 2Fh ; '/'
0x180024185  jmp     loc_18002421A
0x18002418a  lea     rdi, [rsi+0E8h]
0x180024191  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024198  mov     ecx, 40h ; '@'; unsigned __int64
0x18002419d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800241a2  mov     rbx, rax
0x1800241a5  mov     [rbp+var_50], rax
0x1800241a9  test    rax, rax
0x1800241ac  jz      short loc_1800241F1
0x1800241ae  lea     rax, ??_7PluginEngine@@6B@; const PluginEngine::`vftable'
0x1800241b5  mov     [rbx], rax
0x1800241b8  mov     qword ptr [rbx+8], 0
0x1800241c0  mov     qword ptr [rbx+10h], 0
0x1800241c8  mov     qword ptr [rbx+18h], 0
0x1800241d0  mov     qword ptr [rbx+20h], 0
0x1800241d8  mov     qword ptr [rbx+28h], 0
0x1800241e0  mov     qword ptr [rbx+30h], 0
0x1800241e8  mov     dword ptr [rbx+38h], 0
0x1800241ef  jmp     short loc_1800241F3
0x1800241f1  xor     ebx, ebx
0x1800241f3  cmp     rbx, [rdi]
0x1800241f6  jz      short loc_180024205
0x1800241f8  mov     rcx, rdi
0x1800241fb  call    ?_Delete@?$unique_ptr@VPluginEngine@@U?$default_delete@VPluginEngine@@@std@@@std@@AEAAXXZ; std::unique_ptr<PluginEngine>::_Delete(void)
0x180024200  mov     [rdi], rbx
0x180024203  jmp     short loc_180024208
0x180024205  mov     rbx, [rdi]
0x180024208  test    rbx, rbx
0x18002420b  jnz     short loc_18002422F
0x18002420d  mov     ebx, 8007000Eh
0x180024212  mov     edx, 32h ; '2'; void *
0x180024217  mov     r9d, ebx; char *
0x18002421a  mov     rcx, [rbp+18h]; this
0x18002421e  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x180024225  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002422a  jmp     loc_1800242BB
0x18002422f  mov     rax, [rbx]
0x180024232  mov     edx, 1
0x180024237  mov     rcx, rbx
0x18002423a  mov     rax, [rax+48h]
0x18002423e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024243  mov     rdi, [rbp+var_48]
0x180024247  mov     rax, [rdi]
0x18002424a  mov     rbx, [rax+48h]
0x18002424e  lea     rax, ?OnResuming@CProvisioningSingleton@@QEAAJPEAUIInspectable@@0@Z; CProvisioningSingleton::OnResuming(IInspectable *,IInspectable *)
0x180024255  mov     [rbp+var_40], rax
0x180024259  mov     [rbp+var_50], rsi
0x18002425d  lea     r8, [rbp+var_40]
0x180024261  lea     rdx, [rbp+var_50]
0x180024265  lea     rcx, [rbp+hstringHeader]
0x180024269  call    ??0_lambda_4885db004e1493983883bfbd4778eeeb_@@QEAA@AEBQEAVCProvisioningSingleton@@AEBQ81@EAAJPEAUIInspectable@@1@Z@Z; _lambda_4885db004e1493983883bfbd4778eeeb_::_lambda_4885db004e1493983883bfbd4778eeeb_(CProvisioningSingleton * const &,long (CProvisioningSingleton::*const &)(IInspectable *,IInspectable *))
0x18002426e  mov     rdx, rax
0x180024271  lea     rcx, [rbp+var_50]
0x180024275  call    ??$Callback@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@V_lambda_4885db004e1493983883bfbd4778eeeb_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@@01@$$QEAV_lambda_4885db004e1493983883bfbd4778eeeb_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::IEventHandler<IInspectable *>,_lambda_4885db004e1493983883bfbd4778eeeb_>(_lambda_4885db004e1493983883bfbd4778eeeb_ &&)
0x18002427a  nop
0x18002427b  mov     r14, [rbp+var_50]
0x18002427f  lea     r8, [rsi+0F0h]
0x180024286  mov     rdx, r14
0x180024289  mov     rcx, rdi
0x18002428c  mov     rax, rbx
0x18002428f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024294  mov     ebx, eax
0x180024296  test    r14, r14
0x180024299  jz      short loc_1800242AB
0x18002429b  mov     rdx, [r14]
0x18002429e  mov     rcx, r14
0x1800242a1  mov     rax, [rdx+10h]
0x1800242a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242aa  nop
0x1800242ab  test    ebx, ebx
0x1800242ad  jns     short loc_1800242B9
0x1800242af  mov     edx, 38h ; '8'
0x1800242b4  jmp     loc_180024217
0x1800242b9  xor     ebx, ebx
0x1800242bb  lea     rcx, [rbp+var_48]
0x1800242bf  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800242c4  nop
0x1800242c5  lea     rcx, [rbp+var_38]; this
0x1800242c9  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800242ce  mov     eax, ebx
0x1800242d0  mov     rcx, [rbp+var_10]
0x1800242d4  xor     rcx, rsp; StackCookie
0x1800242d7  call    __security_check_cookie
0x1800242dc  lea     r11, [rsp+70h+var_s0]
0x1800242e1  mov     rbx, [r11+28h]
0x1800242e5  mov     rsi, [r11+30h]
0x1800242e9  mov     rsp, r11
0x1800242ec  pop     r14
0x1800242ee  pop     rdi
0x1800242ef  pop     rbp
0x1800242f0  retn
```
