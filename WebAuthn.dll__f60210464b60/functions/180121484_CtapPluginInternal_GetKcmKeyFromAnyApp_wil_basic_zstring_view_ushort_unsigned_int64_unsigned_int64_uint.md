# CtapPluginInternal::GetKcmKeyFromAnyApp(wil::basic_zstring_view<ushort>,unsigned __int64,unsigned __int64 *,uint &)

- ea: `0x180121484`
- end: `0x180121729`
- name: `?GetKcmKeyFromAnyApp@CtapPluginInternal@@YAJV?$basic_zstring_view@G@wil@@_KPEA_KAEAI@Z`
- size: `677`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021bac`

## callees

- `0x180017764`
- `0x180017a88`
- `0x180018cc0`
- `0x180020584`
- `0x180020614`
- `0x180021e34`
- `0x180036da4`
- `0x180121100`
- `0x180121484`

## import_xrefs

- `ncrypt!NCryptEnumKeys` at `0x18012150b`
- `ncrypt!NCryptEnumKeys` at `0x18012160d`
- `ncrypt!NCryptEnumKeys` at `0x18012150b`
- `ncrypt!NCryptEnumKeys` at `0x18012160d`
- `ncrypt!NCryptOpenKey` at `0x180121554`
- `ncrypt!NCryptOpenKey` at `0x180121554`
- `ncrypt!NCryptFreeBuffer` at `0x1801215e5`
- `ncrypt!NCryptFreeBuffer` at `0x18012168b`
- `ncrypt!NCryptFreeBuffer` at `0x1801216ce`
- `ncrypt!NCryptFreeBuffer` at `0x1801216fa`
- `ncrypt!NCryptFreeBuffer` at `0x1801215e5`
- `ncrypt!NCryptFreeBuffer` at `0x18012168b`
- `ncrypt!NCryptFreeBuffer` at `0x1801216ce`
- `ncrypt!NCryptFreeBuffer` at `0x1801216fa`

## string_xrefs

- `0x1801214bd`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180121634`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180121659`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CtapPluginInternal::GetKcmKeyFromAnyApp(_QWORD *a1, NCRYPT_PROV_HANDLE a2, _QWORD *a3, _DWORD *a4)
{
  SECURITY_STATUS v8; // ebx
  const WCHAR *v9; // rbx
  SECURITY_STATUS v10; // eax
  int PropertyValue; // eax
  unsigned __int16 *v12; // rax
  int v13; // r8d
  int v14; // edx
  NCRYPT_KEY_HANDLE v15; // rdx
  PVOID v16; // rcx
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  PVOID v19; // rcx
  __int64 v20; // rax
  PVOID v21; // rcx
  PVOID v22; // rcx
  DWORD dwFlags; // [rsp+20h] [rbp-50h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-50h]
  NCRYPT_KEY_HANDLE phKey; // [rsp+30h] [rbp-40h] BYREF
  __int64 v27; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int16 *v28; // [rsp+40h] [rbp-30h] BYREF
  PVOID ppEnumState; // [rsp+48h] [rbp-28h] BYREF
  PVOID *p_pvInput; // [rsp+50h] [rbp-20h] BYREF
  NCryptKeyName *ppKeyName; // [rsp+58h] [rbp-18h] BYREF
  char v32; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  PVOID pvInput; // [rsp+B0h] [rbp+40h] BYREF

  if ( a3 )
  {
    *a3 = 0;
    ppEnumState = 0;
    pvInput = 0;
    phKey = 0;
    v27 = 0;
    *a4 = 0;
    p_pvInput = &pvInput;
    ppKeyName = 0;
    v32 = 1;
    v8 = NCryptEnumKeys(a2, 0, &ppKeyName, &ppEnumState, 0);
    wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>(&p_pvInput);
    while ( v8 != -2146893782 )
    {
      if ( v8 < 0 )
      {
        v17 = (unsigned int)v8;
        v18 = 775;
        goto LABEL_19;
      }
      v9 = *(const WCHAR **)pvInput;
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
        &phKey,
        0);
      v10 = NCryptOpenKey(a2, &phKey, v9, 0, 0);
      v8 = v10;
      if ( v10 < 0 )
      {
        v17 = (unsigned int)v10;
        v18 = 777;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)v17,
          dwFlagsa);
LABEL_20:
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v27);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
        v19 = pvInput;
        pvInput = 0;
        if ( v19 )
          NCryptFreeBuffer(v19);
        goto LABEL_30;
      }
      v28 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v28,
        0);
      PropertyValue = GetPropertyValue(phKey, L"NgcAccountId", &v28);
      v8 = PropertyValue;
      if ( PropertyValue < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30C,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)(unsigned int)PropertyValue,
          dwFlagsa);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v28);
        goto LABEL_20;
      }
      v12 = v28;
      do
      {
        v13 = *(unsigned __int16 *)((char *)v12 + *a1 - (_QWORD)v28);
        v14 = *v12 - v13;
        if ( v14 )
          break;
        ++v12;
      }
      while ( v13 );
      if ( !v14 && ++*a4 == 1 )
      {
        v15 = phKey;
        phKey = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
          &v27,
          v15);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
        &phKey,
        0);
      v16 = pvInput;
      pvInput = 0;
      if ( v16 )
        NCryptFreeBuffer(v16);
      p_pvInput = &pvInput;
      ppKeyName = 0;
      v32 = 1;
      v8 = NCryptEnumKeys(a2, 0, &ppKeyName, &ppEnumState, 0);
      wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>(&p_pvInput);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v28);
    }
    if ( *a4 )
    {
      v20 = v27;
      v27 = 0;
      *a3 = v20;
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v27);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      v21 = pvInput;
      pvInput = 0;
      if ( v21 )
        NCryptFreeBuffer(v21);
      v8 = 0;
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v27);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      v22 = pvInput;
      pvInput = 0;
      if ( v22 )
        NCryptFreeBuffer(v22);
      v8 = -2146893811;
    }
LABEL_30:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NCryptFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NCryptFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppEnumState);
  }
  else
  {
    v8 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FB,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)0x80004003LL,
      dwFlags);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180121484  mov     [rsp-28h+arg_0], rbx
0x180121489  mov     [rsp-28h+arg_8], rsi
0x18012148e  push    rbp
0x18012148f  push    rdi
0x180121490  push    r12
0x180121492  push    r14
0x180121494  push    r15
0x180121496  mov     rbp, rsp
0x180121499  sub     rsp, 70h
0x18012149d  mov     rdi, r9
0x1801214a0  mov     rsi, r8
0x1801214a3  mov     r14, rdx
0x1801214a6  mov     r15, rcx
0x1801214a9  xor     r12d, r12d
0x1801214ac  test    r8, r8
0x1801214af  jnz     short loc_1801214D3
0x1801214b1  mov     rcx, [rbp+28h]; this
0x1801214b5  mov     ebx, 80004003h
0x1801214ba  mov     r9d, ebx; char *
0x1801214bd  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801214c4  mov     edx, 2FBh; void *
0x1801214c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801214ce  jmp     loc_18012170E
0x1801214d3  mov     [r8], r12
0x1801214d6  mov     [rbp+ppEnumState], r12
0x1801214da  mov     [rbp+pvInput], r12
0x1801214de  mov     [rbp+phKey], r12
0x1801214e2  mov     [rbp+var_38], r12
0x1801214e6  mov     [r9], r12d
0x1801214e9  lea     rax, [rbp+pvInput]
0x1801214ed  mov     [rbp+var_20], rax
0x1801214f1  mov     [rbp+ppKeyName], r12
0x1801214f5  mov     [rbp+var_10], 1
0x1801214f9  mov     [rsp+70h+dwFlags], r12d; dwFlags
0x1801214fe  lea     r9, [rbp+ppEnumState]; ppEnumState
0x180121502  lea     r8, [rbp+ppKeyName]; ppKeyName
0x180121506  xor     edx, edx; pszScope
0x180121508  mov     rcx, r14; hProvider
0x18012150b  call    cs:__imp_NCryptEnumKeys
0x180121511  mov     ebx, eax
0x180121513  lea     rcx, [rbp+var_20]
0x180121517  call    ??1?$out_param_t@V?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>(void)
0x18012151c  cmp     ebx, 8009002Ah
0x180121522  jz      loc_18012169D
0x180121528  test    ebx, ebx
0x18012152a  js      loc_180121693
0x180121530  mov     rax, [rbp+pvInput]
0x180121534  mov     rbx, [rax]
0x180121537  xor     edx, edx
0x180121539  lea     rcx, [rbp+phKey]
0x18012153d  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180121542  mov     [rsp+70h+dwFlags], r12d; int
0x180121547  xor     r9d, r9d; dwLegacyKeySpec
0x18012154a  mov     r8, rbx; pszKeyName
0x18012154d  lea     rdx, [rbp+phKey]; phKey
0x180121551  mov     rcx, r14; hProvider
0x180121554  call    cs:__imp_NCryptOpenKey
0x18012155a  mov     ebx, eax
0x18012155c  test    eax, eax
0x18012155e  js      loc_180121651
0x180121564  mov     [rbp+var_30], r12
0x180121568  xor     edx, edx
0x18012156a  lea     rcx, [rbp+var_30]
0x18012156e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180121573  lea     r8, [rbp+var_30]; unsigned __int16 **
0x180121577  lea     rdx, aNgcaccountid; "NgcAccountId"
0x18012157e  mov     rcx, [rbp+phKey]; hObject
0x180121582  call    ?GetPropertyValue@@YAJ_KPEBGPEAPEAG@Z; GetPropertyValue(unsigned __int64,ushort const *,ushort * *)
0x180121587  mov     ebx, eax
0x180121589  test    eax, eax
0x18012158b  js      loc_18012162D
0x180121591  mov     rax, [rbp+var_30]
0x180121595  mov     rcx, [r15]
0x180121598  sub     rcx, rax
0x18012159b  movzx   edx, word ptr [rax]
0x18012159e  movzx   r8d, word ptr [rax+rcx]
0x1801215a3  sub     edx, r8d
0x1801215a6  jnz     short loc_1801215B1
0x1801215a8  add     rax, 2
0x1801215ac  test    r8d, r8d
0x1801215af  jnz     short loc_18012159B
0x1801215b1  test    edx, edx
0x1801215b3  jnz     short loc_1801215CD
0x1801215b5  inc     dword ptr [rdi]
0x1801215b7  cmp     dword ptr [rdi], 1
0x1801215ba  jnz     short loc_1801215CD
0x1801215bc  mov     rdx, [rbp+phKey]
0x1801215c0  mov     [rbp+phKey], r12
0x1801215c4  lea     rcx, [rbp+var_38]
0x1801215c8  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1801215cd  xor     edx, edx
0x1801215cf  lea     rcx, [rbp+phKey]
0x1801215d3  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1801215d8  mov     rcx, [rbp+pvInput]; pvInput
0x1801215dc  mov     [rbp+pvInput], r12
0x1801215e0  test    rcx, rcx
0x1801215e3  jz      short loc_1801215EB
0x1801215e5  call    cs:__imp_NCryptFreeBuffer
0x1801215eb  lea     rax, [rbp+pvInput]
0x1801215ef  mov     [rbp+var_20], rax
0x1801215f3  mov     [rbp+ppKeyName], r12
0x1801215f7  mov     [rbp+var_10], 1
0x1801215fb  mov     [rsp+70h+dwFlags], r12d; dwFlags
0x180121600  lea     r9, [rbp+ppEnumState]; ppEnumState
0x180121604  lea     r8, [rbp+ppKeyName]; ppKeyName
0x180121608  xor     edx, edx; pszScope
0x18012160a  mov     rcx, r14; hProvider
0x18012160d  call    cs:__imp_NCryptEnumKeys
0x180121613  mov     ebx, eax
0x180121615  lea     rcx, [rbp+var_20]
0x180121619  call    ??1?$out_param_t@V?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>(void)
0x18012161e  nop
0x18012161f  lea     rcx, [rbp+var_30]
0x180121623  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180121628  jmp     loc_18012151C
0x18012162d  mov     rcx, [rbp+28h]; this
0x180121631  mov     r9d, eax; char *
0x180121634  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012163b  mov     edx, 30Ch; void *
0x180121640  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121645  nop
0x180121646  lea     rcx, [rbp+var_30]
0x18012164a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18012164f  jmp     short loc_18012166A
0x180121651  mov     r9d, eax; char *
0x180121654  mov     edx, 309h; void *
0x180121659  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180121660  mov     rcx, [rbp+28h]; this
0x180121664  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121669  nop
0x18012166a  lea     rcx, [rbp+var_38]
0x18012166e  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180121673  nop
0x180121674  lea     rcx, [rbp+phKey]
0x180121678  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18012167d  nop
0x18012167e  mov     rcx, [rbp+pvInput]; pvInput
0x180121682  mov     [rbp+pvInput], r12
0x180121686  test    rcx, rcx
0x180121689  jz      short loc_180121705
0x18012168b  call    cs:__imp_NCryptFreeBuffer
0x180121691  jmp     short loc_180121705
0x180121693  mov     r9d, ebx
0x180121696  mov     edx, 307h
0x18012169b  jmp     short loc_180121659
0x18012169d  cmp     dword ptr [rdi], 1
0x1801216a0  jb      short loc_1801216D9
0x1801216a2  mov     rax, [rbp+var_38]
0x1801216a6  mov     [rbp+var_38], r12
0x1801216aa  mov     [rsi], rax
0x1801216ad  lea     rcx, [rbp+var_38]
0x1801216b1  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1801216b6  nop
0x1801216b7  lea     rcx, [rbp+phKey]
0x1801216bb  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1801216c0  nop
0x1801216c1  mov     rcx, [rbp+pvInput]; pvInput
0x1801216c5  mov     [rbp+pvInput], r12
0x1801216c9  test    rcx, rcx
0x1801216cc  jz      short loc_1801216D4
0x1801216ce  call    cs:__imp_NCryptFreeBuffer
0x1801216d4  mov     ebx, r12d
0x1801216d7  jmp     short loc_180121705
0x1801216d9  lea     rcx, [rbp+var_38]
0x1801216dd  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1801216e2  nop
0x1801216e3  lea     rcx, [rbp+phKey]
0x1801216e7  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1801216ec  nop
0x1801216ed  mov     rcx, [rbp+pvInput]; pvInput
0x1801216f1  mov     [rbp+pvInput], r12
0x1801216f5  test    rcx, rcx
0x1801216f8  jz      short loc_180121700
0x1801216fa  call    cs:__imp_NCryptFreeBuffer
0x180121700  mov     ebx, 8009000Dh
0x180121705  lea     rcx, [rbp+ppEnumState]
0x180121709  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NCryptFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NCryptFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18012170e  mov     eax, ebx
0x180121710  lea     r11, [rsp+70h+var_s0]
0x180121715  mov     rbx, [r11+30h]
0x180121719  mov     rsi, [r11+38h]
0x18012171d  mov     rsp, r11
0x180121720  pop     r15
0x180121722  pop     r14
0x180121724  pop     r12
0x180121726  pop     rdi
0x180121727  pop     rbp
0x180121728  retn
```
