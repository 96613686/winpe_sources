# CProvisioningSingleton::GetInstalledPackageDetails(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::Management::Provisioning::IPackage * *)

- ea: `0x1800230d8`
- end: `0x1800232d2`
- name: `?GetInstalledPackageDetails@CProvisioningSingleton@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIPackage@Provisioning@Management@Windows@@@Z`
- size: `506`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001314c`
- `0x180013ca0`
- `0x180014230`
- `0x180016a60`

## callees

- `0x1800067fc`
- `0x1800087ec`
- `0x180019c10`
- `0x18001e560`
- `0x180022424`
- `0x18002247c`
- `0x1800230d8`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002310a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002310a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800231bd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800231bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800231da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800231da`

## string_xrefs

- `0x180023150`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`
- `0x180023222`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CProvisioningSingleton::GetInstalledPackageDetails(__int64 a1, __int64 *a2, _QWORD *a3)
{
  const unsigned __int16 (*v5)[50]; // rdx
  int v6; // eax
  unsigned int v7; // edi
  __int64 result; // rax
  unsigned __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING, __int64 *); // rbx
  int v12; // eax
  unsigned int v13; // ebx
  const char *v14; // r9
  __int64 v15; // rax
  UINT32 length; // [rsp+20h] [rbp-88h] BYREF
  __int64 v17; // [rsp+28h] [rbp-80h] BYREF
  __int64 v18; // [rsp+30h] [rbp-78h] BYREF
  struct _RTL_CRITICAL_SECTION *v19; // [rsp+38h] [rbp-70h] BYREF
  HSTRING string; // [rsp+40h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-60h] BYREF
  HSTRING v22; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  EnterCriticalSection(&stru_18003EF28);
  v19 = &stru_18003EF28;
  *a3 = 0;
  v18 = 0;
  Windows::Internal::StringReference::StringReference(&v22, v5);
  v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageCollection>>(
         v22,
         &v18);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v17 = 0;
    if ( (unsigned __int64)a2[3] >= 8 )
      a2 = (__int64 *)*a2;
    length = 0;
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)a2 + v9) );
    if ( (int)ULongLongToUInt(v9, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference((PCWSTR)a2, length, &hstringHeader, &string);
    v10 = v18;
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v18 + 56LL);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v17);
    try
    {
      v12 = v11(v10, string, &v17);
      v13 = v12;
      if ( v12 >= 0 )
      {
        v15 = v17;
        v17 = 0;
        *a3 = v15;
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v17);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v18);
        Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v19);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x135,
          (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
          (const char *)(unsigned int)v12,
          length);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v17);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v18);
        Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v19);
        result = v13;
      }
    }
    catch ( ... )
    {
      length = wil::details::in1diag3::Return_CaughtException(
                 retaddr,
                 (void *)0x137,
                 (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
                 v14);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v17);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v18);
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v19);
      return length;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12F,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
      (const char *)(unsigned int)v6,
      length);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v18);
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v19);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x1800230d8  mov     [rsp+arg_0], rbx
0x1800230dd  push    rsi
0x1800230de  push    rdi
0x1800230df  push    r14
0x1800230e1  sub     rsp, 90h
0x1800230e8  mov     rax, cs:__security_cookie
0x1800230ef  xor     rax, rsp
0x1800230f2  mov     [rsp+0A8h+var_28], rax
0x1800230fa  mov     rsi, r8
0x1800230fd  mov     rbx, rdx
0x180023100  lea     rdi, stru_18003EF28
0x180023107  mov     rcx, rdi; lpCriticalSection
0x18002310a  call    cs:__imp_EnterCriticalSection
0x180023111  nop     dword ptr [rax+rax+00h]
0x180023116  mov     [rsp+0A8h+var_70], rdi
0x18002311b  xor     r14d, r14d
0x18002311e  mov     [rsi], r14
0x180023121  mov     [rsp+0A8h+var_78], r14
0x180023126  lea     rcx, [rsp+0A8h+var_48]; string
0x18002312b  call    ??$?0$0DC@@StringReference@Internal@Windows@@QEAA@AEAY0DC@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[50])
0x180023130  lea     rdx, [rsp+0A8h+var_78]
0x180023135  mov     rcx, [rsp+0A8h+var_48]
0x18002313a  call    ??$ActivateInstance@V?$ComPtr@UIPackageCollection@Provisioning@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageCollection@Provisioning@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageCollection>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageCollection>>)
0x18002313f  mov     edi, eax
0x180023141  test    eax, eax
0x180023143  jns     short loc_18002317E
0x180023145  mov     rcx, [rsp+0A8h]; this
0x18002314d  mov     r9d, eax; char *
0x180023150  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x180023157  mov     edx, 12Fh; void *
0x18002315c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023161  nop
0x180023162  lea     rcx, [rsp+0A8h+var_78]
0x180023167  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18002316c  nop
0x18002316d  lea     rcx, [rsp+0A8h+var_70]; this
0x180023172  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180023177  mov     eax, edi
0x180023179  jmp     loc_1800232AD
0x18002317e  mov     [rsp+0A8h+var_80], r14
0x180023183  cmp     qword ptr [rbx+18h], 8
0x180023188  jb      short loc_18002318D
0x18002318a  mov     rbx, [rbx]
0x18002318d  mov     [rsp+0A8h+length], r14d; int
0x180023192  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180023196  inc     rcx; unsigned __int64
0x180023199  cmp     [rbx+rcx*2], r14w
0x18002319e  jnz     short loc_180023196
0x1800231a0  lea     rdx, [rsp+0A8h+length]; unsigned int *
0x1800231a5  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800231aa  test    eax, eax
0x1800231ac  jns     short loc_1800231C9
0x1800231ae  xor     r9d, r9d; lpArguments
0x1800231b1  xor     r8d, r8d; nNumberOfArguments
0x1800231b4  lea     edx, [r9+1]; dwExceptionFlags
0x1800231b8  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800231bd  call    cs:__imp_RaiseException
0x1800231c4  nop     dword ptr [rax+rax+00h]
0x1800231c9  lea     r9, [rsp+0A8h+string]; string
0x1800231ce  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x1800231d3  mov     edx, [rsp+0A8h+length]; length
0x1800231d7  mov     rcx, rbx; sourceString
0x1800231da  call    cs:__imp_WindowsCreateStringReference
0x1800231e1  nop     dword ptr [rax+rax+00h]
0x1800231e6  mov     rdi, [rsp+0A8h+var_78]
0x1800231eb  mov     rax, [rdi]
0x1800231ee  mov     rbx, [rax+38h]
0x1800231f2  lea     rcx, [rsp+0A8h+var_80]
0x1800231f7  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800231fc  lea     r8, [rsp+0A8h+var_80]
0x180023201  mov     rdx, [rsp+0A8h+string]
0x180023206  mov     rcx, rdi
0x180023209  mov     rax, rbx
0x18002320c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023211  mov     ebx, eax
0x180023213  test    eax, eax
0x180023215  jns     short loc_180023258
0x180023217  mov     rcx, [rsp+0A8h]; this
0x18002321f  mov     r9d, eax; char *
0x180023222  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x180023229  mov     edx, 135h; void *
0x18002322e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023233  nop
0x180023234  lea     rcx, [rsp+0A8h+var_80]
0x180023239  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18002323e  nop
0x18002323f  lea     rcx, [rsp+0A8h+var_78]
0x180023244  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023249  nop
0x18002324a  lea     rcx, [rsp+0A8h+var_70]; this
0x18002324f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180023254  mov     eax, ebx
0x180023256  jmp     short loc_1800232AD
0x180023258  mov     rax, [rsp+0A8h+var_80]
0x18002325d  mov     [rsp+0A8h+var_80], r14
0x180023262  mov     [rsi], rax
0x180023265  lea     rcx, [rsp+0A8h+var_80]
0x18002326a  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18002326f  nop
0x180023270  lea     rcx, [rsp+0A8h+var_78]
0x180023275  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18002327a  nop
0x18002327b  lea     rcx, [rsp+0A8h+var_70]; this
0x180023280  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180023285  xor     eax, eax
0x180023287  jmp     short loc_1800232AD
0x180023289  lea     rcx, [rsp+0A8h+var_80]
0x18002328e  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023293  nop
0x180023294  lea     rcx, [rsp+0A8h+var_78]
0x180023299  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18002329e  nop
0x18002329f  lea     rcx, [rsp+0A8h+var_70]; this
0x1800232a4  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800232a9  mov     eax, [rsp+0A8h+length]
0x1800232ad  mov     rcx, [rsp+0A8h+var_28]
0x1800232b5  xor     rcx, rsp; StackCookie
0x1800232b8  call    __security_check_cookie
0x1800232bd  mov     rbx, [rsp+0A8h+arg_0]
0x1800232c5  add     rsp, 90h
0x1800232cc  pop     r14
0x1800232ce  pop     rdi
0x1800232cf  pop     rsi
0x1800232d0  retn
```
