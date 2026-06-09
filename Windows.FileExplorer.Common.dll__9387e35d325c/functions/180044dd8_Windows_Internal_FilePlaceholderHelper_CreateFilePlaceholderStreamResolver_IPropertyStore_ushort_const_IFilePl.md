# Windows::Internal::FilePlaceholderHelper::CreateFilePlaceholderStreamResolver(IPropertyStore *,ushort const *,IFilePlaceholderStreamResolver * *)

- ea: `0x180044dd8`
- end: `0x180044f5e`
- name: `?CreateFilePlaceholderStreamResolver@FilePlaceholderHelper@Internal@Windows@@YAJPEAUIPropertyStore@@PEBGPEAPEAUIFilePlaceholderStreamResolver@@@Z`
- size: `390`
- prototype: `int(Windows::Internal::FilePlaceholderHelper *__hidden this, struct IPropertyStore *, const unsigned __int16 *, struct IFilePlaceholderStreamResolver **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003d634`

## callees

- `0x180004a54`
- `0x180037780`
- `0x180044718`
- `0x180044da8`
- `0x180044dd8`
- `0x180046bf8`
- `0x180089010`

## import_xrefs

- `Windows.Storage!__imp_SHExtCoCreateInstanceCheckCategory` at `0x180044ef2`
- `Windows.Storage!__imp_SHExtCoCreateInstanceCheckCategory` at `0x180044ef2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044e97`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044e97`
- `PROPSYS!PropVariantToGUID` at `0x180044e8b`
- `PROPSYS!PropVariantToGUID` at `0x180044e8b`

## string_xrefs

- `0x180044e53`: `PlaceholderResolverCLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::FilePlaceholderHelper::CreateFilePlaceholderStreamResolver(
        __int64 (__fastcall ***this)(Windows::Internal::FilePlaceholderHelper *, GUID *, __int64 *),
        const WCHAR *a2,
        unsigned __int16 *a3,
        struct IFilePlaceholderStreamResolver **a4)
{
  __int64 (__fastcall *v7)(Windows::Internal::FilePlaceholderHelper *, GUID *, __int64 *); // rbx
  __int64 v8; // rdx
  int FailIf; // ebx
  const unsigned __int16 *v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v14; // [rsp+40h] [rbp-40h] BYREF
  __int64 v15; // [rsp+48h] [rbp-38h] BYREF
  PROPVARIANT propvar[3]; // [rsp+50h] [rbp-30h] BYREF
  GUID pguid; // [rsp+68h] [rbp-18h] BYREF

  *(_QWORD *)a3 = 0;
  v15 = 0;
  v7 = **this;
  CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore(&v15, a2, a3, a4);
  FailIf = v7((Windows::Internal::FilePlaceholderHelper *)this, &GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &v15);
  if ( FailIf >= 0 )
  {
    pguid = GUID_NULL;
    LOWORD(propvar[0]) = 0;
    FailIf = CPropertyStoreHelperBase<INamedPropertyStore>::GetFailIfEmpty<unsigned short const *>(
               &v15,
               L"PlaceholderResolverCLSID",
               propvar);
    if ( FailIf >= 0 )
    {
      pguid = GUID_NULL;
      if ( LOWORD(propvar[0]) )
        FailIf = PropVariantToGUID(propvar, &pguid);
      else
        FailIf = -2147023728;
    }
    PropVariantClear(propvar);
    if ( FailIf >= 0 )
    {
      FailIf = Windows::Internal::FilePlaceholderHelper::_VerifyFilePlaceholderLocation(
                 (Windows::Internal::FilePlaceholderHelper *)&pguid,
                 a2,
                 v10);
      if ( FailIf >= 0 )
      {
        v14 = 0;
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v14);
        FailIf = SHExtCoCreateInstanceCheckCategory(
                   &pguid,
                   CATID_FilePlaceholderStreamResolver,
                   0,
                   1029,
                   0,
                   &GUID_cedcbd91_e5ac_4a58_8bec_f6049ef73c41,
                   &v14);
        if ( FailIf >= 0 )
        {
          FailIf = (*(__int64 (__fastcall **)(__int64, Windows::Internal::FilePlaceholderHelper *, const WCHAR *))(*(_QWORD *)v14 + 24LL))(
                     v14,
                     (Windows::Internal::FilePlaceholderHelper *)this,
                     a2);
          if ( FailIf >= 0 )
          {
            v12 = v14;
            v14 = 0;
            *(_QWORD *)a3 = v12;
          }
        }
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v14);
      }
    }
  }
  CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore(&v15, v8, v10, v11);
  return (unsigned int)FailIf;
}

```

## disassembly

```asm
0x180044dd8  mov     [rsp-28h+arg_18], rbx
0x180044ddd  push    rbp
0x180044dde  push    rsi
0x180044ddf  push    rdi
0x180044de0  push    r14
0x180044de2  push    r15
0x180044de4  mov     rbp, rsp
0x180044de7  sub     rsp, 80h
0x180044dee  mov     rax, cs:__security_cookie
0x180044df5  xor     rax, rsp
0x180044df8  mov     [rbp+var_8], rax
0x180044dfc  mov     rsi, r8
0x180044dff  mov     rdi, rdx
0x180044e02  mov     r14, rcx
0x180044e05  xor     r15d, r15d
0x180044e08  mov     [r8], r15
0x180044e0b  mov     [rbp+var_38], r15
0x180044e0f  mov     rax, [rcx]
0x180044e12  mov     rbx, [rax]
0x180044e15  lea     rcx, [rbp+var_38]
0x180044e19  call    ?ClearPropertyStore@?$CPropertyStoreHelperBase@UINamedPropertyStore@@@@QEAAXXZ; CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore(void)
0x180044e1e  lea     r8, [rbp+var_38]
0x180044e22  lea     rdx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x180044e29  mov     rcx, r14
0x180044e2c  mov     rax, rbx
0x180044e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e34  mov     ebx, eax
0x180044e36  test    eax, eax
0x180044e38  js      loc_180044F2F
0x180044e3e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180044e45  movdqu  xmmword ptr [rbp+pguid.Data1], xmm0
0x180044e4a  mov     word ptr [rbp+propvar], r15w
0x180044e4f  lea     r8, [rbp+propvar]
0x180044e53  lea     rdx, aPlaceholderres; "PlaceholderResolverCLSID"
0x180044e5a  lea     rcx, [rbp+var_38]
0x180044e5e  call    ??$GetFailIfEmpty@PEBG@?$CPropertyStoreHelperBase@UINamedPropertyStore@@@@QEBAJPEBGPEAUtagPROPVARIANT@@@Z; CPropertyStoreHelperBase<INamedPropertyStore>::GetFailIfEmpty<ushort const *>(ushort const *,tagPROPVARIANT *)
0x180044e63  mov     ebx, eax
0x180044e65  test    eax, eax
0x180044e67  js      short loc_180044E93
0x180044e69  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180044e70  movdqu  xmmword ptr [rbp+pguid.Data1], xmm0
0x180044e75  cmp     word ptr [rbp+propvar], r15w
0x180044e7a  jnz     short loc_180044E83
0x180044e7c  mov     ebx, 80070490h
0x180044e81  jmp     short loc_180044E93
0x180044e83  lea     rdx, [rbp+pguid]; pguid
0x180044e87  lea     rcx, [rbp+propvar]; propvar
0x180044e8b  call    cs:__imp_PropVariantToGUID
0x180044e91  mov     ebx, eax
0x180044e93  lea     rcx, [rbp+propvar]; pvar
0x180044e97  call    cs:__imp_PropVariantClear
0x180044e9d  test    ebx, ebx
0x180044e9f  js      loc_180044F2F
0x180044ea5  mov     rdx, rdi; struct _GUID *
0x180044ea8  lea     rcx, [rbp+pguid]; this
0x180044eac  call    ?_VerifyFilePlaceholderLocation@FilePlaceholderHelper@Internal@Windows@@YAJAEBU_GUID@@PEBG@Z; Windows::Internal::FilePlaceholderHelper::_VerifyFilePlaceholderLocation(_GUID const &,ushort const *)
0x180044eb1  mov     ebx, eax
0x180044eb3  test    eax, eax
0x180044eb5  js      short loc_180044F2F
0x180044eb7  mov     [rbp+var_40], r15
0x180044ebb  lea     rcx, [rbp+var_40]
0x180044ebf  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180044ec4  lea     rax, [rbp+var_40]
0x180044ec8  mov     [rsp+80h+var_50], rax
0x180044ecd  lea     rax, _GUID_cedcbd91_e5ac_4a58_8bec_f6049ef73c41
0x180044ed4  mov     [rsp+80h+var_58], rax
0x180044ed9  mov     [rsp+80h+var_60], r15d
0x180044ede  mov     r9d, 405h
0x180044ee4  xor     r8d, r8d
0x180044ee7  lea     rdx, CATID_FilePlaceholderStreamResolver
0x180044eee  lea     rcx, [rbp+pguid]
0x180044ef2  call    cs:__imp_SHExtCoCreateInstanceCheckCategory
0x180044ef8  mov     ebx, eax
0x180044efa  test    eax, eax
0x180044efc  js      short loc_180044F25
0x180044efe  mov     rcx, [rbp+var_40]
0x180044f02  mov     rax, [rcx]
0x180044f05  mov     r8, rdi
0x180044f08  mov     rdx, r14
0x180044f0b  mov     rax, [rax+18h]
0x180044f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f14  mov     ebx, eax
0x180044f16  test    eax, eax
0x180044f18  js      short loc_180044F25
0x180044f1a  mov     rax, [rbp+var_40]
0x180044f1e  mov     [rbp+var_40], r15
0x180044f22  mov     [rsi], rax
0x180044f25  lea     rcx, [rbp+var_40]
0x180044f29  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180044f2e  nop
0x180044f2f  lea     rcx, [rbp+var_38]
0x180044f33  call    ?ClearPropertyStore@?$CPropertyStoreHelperBase@UINamedPropertyStore@@@@QEAAXXZ; CPropertyStoreHelperBase<INamedPropertyStore>::ClearPropertyStore(void)
0x180044f38  nop
0x180044f39  mov     eax, ebx
0x180044f3b  mov     rcx, [rbp+var_8]
0x180044f3f  xor     rcx, rsp; StackCookie
0x180044f42  call    __security_check_cookie
0x180044f47  mov     rbx, [rsp+80h+arg_18]
0x180044f4f  add     rsp, 80h
0x180044f56  pop     r15
0x180044f58  pop     r14
0x180044f5a  pop     rdi
0x180044f5b  pop     rsi
0x180044f5c  pop     rbp
0x180044f5d  retn
```
