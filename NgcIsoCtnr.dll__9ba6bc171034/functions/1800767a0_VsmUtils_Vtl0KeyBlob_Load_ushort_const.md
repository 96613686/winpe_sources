# VsmUtils::Vtl0KeyBlob::Load(ushort const *)

- ea: `0x1800767a0`
- end: `0x18007688b`
- name: `?Load@Vtl0KeyBlob@VsmUtils@@QEAAJPEBG@Z`
- size: `235`
- prototype: `int(VsmUtils::Vtl0KeyBlob *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024820`

## callees

- `0x18000d62c`
- `0x1800108e4`
- `0x180011174`
- `0x18002bfec`
- `0x1800767a0`
- `0x180076894`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x18007681f`
- `ncrypt!NCryptOpenKey` at `0x18007681f`

## string_xrefs

- `0x1800767c4`: `onecore\ds\security\trustlet\utils\vtl0\lib\vtl0tpmcommands.cpp`
- `0x18007684a`: `onecore\ds\security\trustlet\utils\vtl0\lib\vtl0tpmcommands.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VsmUtils::Vtl0KeyBlob::Load(BYTE *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  NCRYPT_PROV_HANDLE v6; // rsi
  SECURITY_STATUS v7; // eax
  __int64 v8; // rdx
  DWORD dwFlags; // [rsp+20h] [rbp-18h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  NCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    v6 = *(_QWORD *)VsmUtils::Vtl0Tpm::Instance();
    if ( !v6 )
    {
      v4 = -2146893786;
      v5 = 48;
      goto LABEL_3;
    }
    phKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &phKey,
      0);
    v7 = NCryptOpenKey(v6, &phKey, a2, 0, 0);
    v4 = v7;
    if ( v7 >= 0 )
    {
      v7 = VsmUtils::Vtl0KeyBlob::Load(this, phKey);
      v4 = v7;
      if ( v7 >= 0 )
      {
        this[72] = 1;
        phKey = 0;
        v4 = 0;
        goto LABEL_12;
      }
      v8 = 60;
    }
    else
    {
      v8 = 57;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\vtl0tpmcommands.cpp",
      (const char *)(unsigned int)v7,
      dwFlagsa);
LABEL_12:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    return v4;
  }
  v4 = -2147467261;
  v5 = 43;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\vtl0tpmcommands.cpp",
    (const char *)v4,
    dwFlags);
  return v4;
}

```

## disassembly

```asm
0x1800767a0  mov     [rsp+arg_0], rbx
0x1800767a5  mov     [rsp+arg_10], rsi
0x1800767aa  push    rdi
0x1800767ab  sub     rsp, 30h
0x1800767af  mov     rbx, rdx
0x1800767b2  mov     rdi, rcx
0x1800767b5  test    rdx, rdx
0x1800767b8  jnz     short loc_1800767DD
0x1800767ba  mov     ebx, 80004003h
0x1800767bf  mov     edx, 2Bh ; '+'; void *
0x1800767c4  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\trustlet\\utils"...
0x1800767cb  mov     r9d, ebx; char *
0x1800767ce  mov     rcx, [rsp+38h]; this
0x1800767d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800767d8  jmp     loc_180076879
0x1800767dd  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x1800767e2  mov     rsi, [rax]
0x1800767e5  test    rsi, rsi
0x1800767e8  jnz     short loc_1800767F4
0x1800767ea  mov     ebx, 80090026h
0x1800767ef  lea     edx, [rsi+30h]
0x1800767f2  jmp     short loc_1800767C4
0x1800767f4  mov     [rsp+38h+phKey], 0
0x1800767fd  xor     edx, edx
0x1800767ff  lea     rcx, [rsp+38h+phKey]
0x180076804  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180076809  mov     [rsp+38h+dwFlags], 0; int
0x180076811  xor     r9d, r9d; dwLegacyKeySpec
0x180076814  mov     r8, rbx; pszKeyName
0x180076817  lea     rdx, [rsp+38h+phKey]; phKey
0x18007681c  mov     rcx, rsi; hProvider
0x18007681f  call    cs:__imp_NCryptOpenKey
0x180076825  mov     ebx, eax
0x180076827  test    eax, eax
0x180076829  jns     short loc_180076832
0x18007682b  mov     edx, 39h ; '9'
0x180076830  jmp     short loc_18007684A
0x180076832  mov     rdx, [rsp+38h+phKey]; hObject
0x180076837  mov     rcx, rdi; pbOutput
0x18007683a  call    ?Load@Vtl0KeyBlob@VsmUtils@@QEAAJ_K@Z; VsmUtils::Vtl0KeyBlob::Load(unsigned __int64)
0x18007683f  mov     ebx, eax
0x180076841  test    eax, eax
0x180076843  jns     short loc_180076860
0x180076845  mov     edx, 3Ch ; '<'; void *
0x18007684a  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\trustlet\\utils"...
0x180076851  mov     r9d, eax; char *
0x180076854  mov     rcx, [rsp+38h]; this
0x180076859  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007685e  jmp     short loc_18007686F
0x180076860  mov     byte ptr [rdi+48h], 1
0x180076864  mov     [rsp+38h+phKey], 0
0x18007686d  xor     ebx, ebx
0x18007686f  lea     rcx, [rsp+38h+phKey]
0x180076874  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180076879  mov     eax, ebx
0x18007687b  mov     rbx, [rsp+38h+arg_0]
0x180076880  mov     rsi, [rsp+38h+arg_10]
0x180076885  add     rsp, 30h
0x180076889  pop     rdi
0x18007688a  retn
```
