# CProvisioningSingleton::OnSingletonDeinit(void)

- ea: `0x180023ff0`
- end: `0x1800240ed`
- name: `?OnSingletonDeinit@CProvisioningSingleton@@MEAAXXZ`
- size: `253`
- prototype: `void __fastcall(CProvisioningSingleton *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800067fc`
- `0x1800136cc`
- `0x180019c10`
- `0x18001f74c`
- `0x180022594`
- `0x180023ff0`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024016`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024016`

## string_xrefs

- `0x180024093`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CProvisioningSingleton::OnSingletonDeinit(CProvisioningSingleton *this)
{
  char *v2; // rbx
  int v3; // eax
  int v4[2]; // [rsp+20h] [rbp-48h] BYREF
  char *v5; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  __int64 v7; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = (char *)this + 248;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  v5 = v2;
  if ( *((_BYTE *)this + 392) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 29) + 8LL))(*((_QWORD *)this + 29));
    *((_BYTE *)this + 392) = 0;
  }
  if ( *((_QWORD *)this + 30) )
  {
    *(_QWORD *)v4 = 0;
    v7 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.ApplicationModel.Core.CoreApplication",
      0x2Eu,
      0x2Du);
    v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplication>>(
           v7,
           v4);
    if ( v3 >= 0 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v4 + 80LL))(*(_QWORD *)v4, *((_QWORD *)this + 30));
    else
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
        (const char *)(unsigned int)v3,
        v4[0]);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease((__int64 *)v4);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v5);
}

```

## disassembly

```asm
0x180023ff0  mov     [rsp+arg_8], rbx
0x180023ff5  push    rdi
0x180023ff6  sub     rsp, 60h
0x180023ffa  mov     rax, cs:__security_cookie
0x180024001  xor     rax, rsp
0x180024004  mov     [rsp+68h+var_18], rax
0x180024009  mov     rdi, rcx
0x18002400c  lea     rbx, [rcx+0F8h]
0x180024013  mov     rcx, rbx; lpCriticalSection
0x180024016  call    cs:__imp_EnterCriticalSection
0x18002401d  nop     dword ptr [rax+rax+00h]
0x180024022  mov     [rsp+68h+var_40], rbx
0x180024027  xor     ebx, ebx
0x180024029  cmp     [rdi+188h], bl
0x18002402f  jz      short loc_18002404A
0x180024031  mov     rcx, [rdi+0E8h]
0x180024038  mov     rax, [rcx]
0x18002403b  mov     rax, [rax+8]
0x18002403f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024044  mov     [rdi+188h], bl
0x18002404a  cmp     [rdi+0F0h], rbx
0x180024051  jz      short loc_1800240CA
0x180024053  mov     qword ptr [rsp+68h+var_48], rbx; int
0x180024058  mov     [rsp+68h+var_20], rbx
0x18002405d  mov     r9d, 2Dh ; '-'; unsigned int
0x180024063  lea     r8d, [r9+1]; unsigned int
0x180024067  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; "Windows.ApplicationModel.Core.CoreAppli"...
0x18002406e  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x180024073  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180024078  lea     rdx, [rsp+68h+var_48]
0x18002407d  mov     rcx, [rsp+68h+var_20]
0x180024082  call    ??$GetActivationFactory@V?$ComPtr@UICoreApplication@Core@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICoreApplication@Core@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplication>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplication>>)
0x180024087  mov     rcx, [rsp+68h]; this
0x18002408c  test    eax, eax
0x18002408e  jns     short loc_1800240A6
0x180024090  mov     r9d, eax; char *
0x180024093  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x18002409a  mov     edx, 48h ; 'H'; void *
0x18002409f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800240a4  jmp     short loc_1800240BF
0x1800240a6  mov     rcx, qword ptr [rsp+68h+var_48]
0x1800240ab  mov     rax, [rcx]
0x1800240ae  mov     rdx, [rdi+0F0h]
0x1800240b5  mov     rax, [rax+50h]
0x1800240b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240be  nop
0x1800240bf  lea     rcx, [rsp+68h+var_48]
0x1800240c4  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800240c9  nop
0x1800240ca  lea     rcx, [rsp+68h+var_40]; this
0x1800240cf  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800240d4  mov     rcx, [rsp+68h+var_18]
0x1800240d9  xor     rcx, rsp; StackCookie
0x1800240dc  call    __security_check_cookie
0x1800240e1  mov     rbx, [rsp+68h+arg_8]
0x1800240e6  add     rsp, 60h
0x1800240ea  pop     rdi
0x1800240eb  retn
```
