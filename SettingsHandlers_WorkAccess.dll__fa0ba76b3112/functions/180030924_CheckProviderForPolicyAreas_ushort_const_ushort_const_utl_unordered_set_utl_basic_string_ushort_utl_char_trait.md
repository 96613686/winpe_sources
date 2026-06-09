# CheckProviderForPolicyAreas(ushort const *,ushort const *,utl::unordered_set<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> *)

- ea: `0x180030924`
- end: `0x180030bd1`
- name: `?CheckProviderForPolicyAreas@@YAJPEBG0PEAV?$unordered_set@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z`
- size: `685`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180031d60`
- `0x180032040`

## callees

- `0x1800096ec`
- `0x18002cff8`
- `0x18002e67c`
- `0x18002f768`
- `0x180030924`

## import_xrefs

- `policymanager!EnterprisePolicyManagerStore_GetAllProviderContextSidAreas` at `0x1800309ce`
- `policymanager!EnterprisePolicyManagerStore_GetAllProviderContextSidAreas` at `0x180030aa6`
- `policymanager!EnterprisePolicyManagerStore_GetAllProviderContextSidAreas` at `0x1800309ce`
- `policymanager!EnterprisePolicyManagerStore_GetAllProviderContextSidAreas` at `0x180030aa6`
- `OLEAUT32!__imp_SysAllocString` at `0x180030954`
- `OLEAUT32!__imp_SysAllocString` at `0x180030991`
- `OLEAUT32!__imp_SysAllocString` at `0x180030a11`
- `OLEAUT32!__imp_SysAllocString` at `0x180030954`
- `OLEAUT32!__imp_SysAllocString` at `0x180030991`
- `OLEAUT32!__imp_SysAllocString` at `0x180030a11`
- `OLEAUT32!__imp_SysFreeString` at `0x1800309fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180030a61`
- `OLEAUT32!__imp_SysFreeString` at `0x180030b2a`
- `OLEAUT32!__imp_SysFreeString` at `0x180030b78`
- `OLEAUT32!__imp_SysFreeString` at `0x1800309fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180030a61`
- `OLEAUT32!__imp_SysFreeString` at `0x180030b2a`
- `OLEAUT32!__imp_SysFreeString` at `0x180030b78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030a82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030b4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030a82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030b4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030b99`

## string_xrefs

- `0x180030976`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180030a32`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckProviderForPolicyAreas(OLECHAR *psz, OLECHAR *a2, __int64 a3)
{
  __int64 v6; // rdx
  unsigned int v7; // edi
  BSTR *v8; // rcx
  unsigned int m; // esi
  unsigned int i; // ebx
  BSTR *v11; // rcx
  unsigned int v12; // eax
  unsigned int j; // ebx
  unsigned int v14; // edi
  unsigned int k; // edi
  LPVOID pv; // [rsp+20h] [rbp-99h] BYREF
  unsigned int v18; // [rsp+28h] [rbp-91h] BYREF
  LPVOID v19; // [rsp+30h] [rbp-89h] BYREF
  _QWORD v20[2]; // [rsp+38h] [rbp-81h] BYREF
  char v21; // [rsp+48h] [rbp-71h]
  _BYTE v22[8]; // [rsp+50h] [rbp-69h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-39h]
  const wchar_t *v25; // [rsp+90h] [rbp-29h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  unsigned int v27; // [rsp+138h] [rbp+7Fh] BYREF

  PolicyManagerScopeData::PolicyManagerScopeData((PolicyManagerScopeData *)v22);
  if ( !SysAllocString(a2) )
  {
    v6 = 540;
LABEL_3:
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)0x8007000ELL,
      (int)pv);
    goto LABEL_26;
  }
  bstrString = SysAllocString(psz);
  if ( !bstrString )
  {
    v6 = 543;
    goto LABEL_3;
  }
  v25 = L"Default";
  v27 = 0;
  pv = 0;
  EnterprisePolicyManagerStore_GetAllProviderContextSidAreas(
    (struct PolicyManagerScopeData *)v22,
    &v27,
    (unsigned __int16 ***)&pv);
  v20[0] = &pv;
  v20[1] = &v27;
  v21 = 1;
  v18 = 0;
  v19 = 0;
  SysFreeString(bstrString);
  bstrString = SysAllocString(L"Device");
  if ( bstrString )
  {
    EnterprisePolicyManagerStore_GetAllProviderContextSidAreas(
      (struct PolicyManagerScopeData *)v22,
      &v18,
      (unsigned __int16 ***)&v19);
    if ( pv )
    {
      for ( i = 0; i < v27; ++i )
        utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,0>::emplace<unsigned short * &,0>(
          a3,
          v20,
          (char *)pv + 8 * i);
    }
    v11 = (BSTR *)v19;
    v12 = v18;
    if ( v19 )
    {
      for ( j = 0; j < v18; v11 = (BSTR *)v19 )
      {
        utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,0>::emplace<unsigned short * &,0>(
          a3,
          v20,
          &v11[j++]);
        v12 = v18;
      }
      if ( v11 )
      {
        v14 = 0;
        if ( v12 )
        {
          do
          {
            SysFreeString(v11[v14]);
            *((_QWORD *)v19 + v14++) = 0;
            v11 = (BSTR *)v19;
          }
          while ( v14 < v18 );
        }
        CoTaskMemFree(v11);
        v19 = 0;
      }
    }
    if ( pv )
    {
      for ( k = 0; k < v27; ++k )
      {
        SysFreeString(*((BSTR *)pv + k));
        *((_QWORD *)pv + k) = 0;
      }
      CoTaskMemFree(pv);
      pv = 0;
    }
    v7 = 0;
  }
  else
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23C,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)0x8007000ELL,
      (int)pv);
    v8 = (BSTR *)pv;
    if ( pv )
    {
      for ( m = 0; m < v27; v8 = (BSTR *)pv )
      {
        SysFreeString(v8[m]);
        *((_QWORD *)pv + m++) = 0;
      }
      CoTaskMemFree(v8);
      pv = 0;
    }
  }
LABEL_26:
  PolicyManagerScopeData::~PolicyManagerScopeData((PolicyManagerScopeData *)v22);
  return v7;
}

```

## disassembly

```asm
0x180030924  mov     [rsp-8+arg_0], rbx
0x180030929  mov     [rsp-8+arg_8], rsi
0x18003092e  push    rbp
0x18003092f  push    rdi
0x180030930  push    r14
0x180030932  lea     rbp, [rsp-47h]
0x180030937  sub     rsp, 100h
0x18003093e  mov     rsi, r8
0x180030941  mov     rbx, rdx
0x180030944  mov     rdi, rcx
0x180030947  lea     rcx, [rbp+57h+var_C0]; this
0x18003094b  call    ??0PolicyManagerScopeData@@QEAA@XZ; PolicyManagerScopeData::PolicyManagerScopeData(void)
0x180030950  nop
0x180030951  mov     rcx, rbx; psz
0x180030954  call    cs:__imp_SysAllocString
0x18003095b  nop     dword ptr [rax+rax+00h]
0x180030960  mov     [rbp+57h+var_B8], rax
0x180030964  xor     r14d, r14d
0x180030967  test    rax, rax
0x18003096a  jnz     short loc_18003098E
0x18003096c  mov     edx, 21Ch; void *
0x180030971  mov     edi, 8007000Eh
0x180030976  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x18003097d  mov     r9d, edi; char *
0x180030980  mov     rcx, [rbp+5Fh]; this
0x180030984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030989  jmp     loc_180030BAD
0x18003098e  mov     rcx, rdi; psz
0x180030991  call    cs:__imp_SysAllocString
0x180030998  nop     dword ptr [rax+rax+00h]
0x18003099d  mov     [rbp+57h+bstrString], rax
0x1800309a1  test    rax, rax
0x1800309a4  jnz     short loc_1800309AD
0x1800309a6  mov     edx, 21Fh
0x1800309ab  jmp     short loc_180030971
0x1800309ad  lea     rax, aDefault_1; "Default"
0x1800309b4  mov     [rbp+57h+var_80], rax
0x1800309b8  mov     [rbp+57h+arg_18], r14d
0x1800309bc  mov     [rsp+110h+pv], r14; int
0x1800309c1  lea     r8, [rsp+110h+pv]
0x1800309c6  lea     rdx, [rbp+57h+arg_18]
0x1800309ca  lea     rcx, [rbp+57h+var_C0]
0x1800309ce  call    cs:__imp_?EnterprisePolicyManagerStore_GetAllProviderContextSidAreas@@YAJPEAUPolicyManagerScopeData@@PEAKPEAPEAPEAG@Z; EnterprisePolicyManagerStore_GetAllProviderContextSidAreas(PolicyManagerScopeData *,ulong *,ushort * * *)
0x1800309d5  nop     dword ptr [rax+rax+00h]
0x1800309da  lea     rax, [rsp+110h+pv]
0x1800309df  mov     [rsp+110h+var_D8], rax
0x1800309e4  lea     rax, [rbp+57h+arg_18]
0x1800309e8  mov     [rbp+57h+var_D0], rax
0x1800309ec  mov     [rbp+57h+var_C8], 1
0x1800309f0  mov     [rsp+110h+var_E8], r14d
0x1800309f5  mov     [rsp+110h+var_E0], r14
0x1800309fa  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800309fe  call    cs:__imp_SysFreeString
0x180030a05  nop     dword ptr [rax+rax+00h]
0x180030a0a  lea     rcx, aDevice; "Device"
0x180030a11  call    cs:__imp_SysAllocString
0x180030a18  nop     dword ptr [rax+rax+00h]
0x180030a1d  mov     [rbp+57h+bstrString], rax
0x180030a21  test    rax, rax
0x180030a24  jnz     short loc_180030A98
0x180030a26  mov     rcx, [rbp+5Fh]; this
0x180030a2a  mov     edi, 8007000Eh
0x180030a2f  mov     r9d, edi; char *
0x180030a32  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180030a39  mov     edx, 23Ch; void *
0x180030a3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030a43  nop
0x180030a44  mov     rcx, [rsp+110h+pv]
0x180030a49  test    rcx, rcx
0x180030a4c  jz      loc_180030BAD
0x180030a52  mov     esi, r14d
0x180030a55  cmp     [rbp+57h+arg_18], r14d
0x180030a59  jbe     short loc_180030A82
0x180030a5b  mov     ebx, esi
0x180030a5d  mov     rcx, [rcx+rbx*8]; bstrString
0x180030a61  call    cs:__imp_SysFreeString
0x180030a68  nop     dword ptr [rax+rax+00h]
0x180030a6d  mov     rax, [rsp+110h+pv]
0x180030a72  mov     [rax+rbx*8], r14
0x180030a76  inc     esi
0x180030a78  mov     rcx, [rsp+110h+pv]; pv
0x180030a7d  cmp     esi, [rbp+57h+arg_18]
0x180030a80  jb      short loc_180030A5B
0x180030a82  call    cs:__imp_CoTaskMemFree
0x180030a89  nop     dword ptr [rax+rax+00h]
0x180030a8e  mov     [rsp+110h+pv], r14
0x180030a93  jmp     loc_180030BAD
0x180030a98  lea     r8, [rsp+110h+var_E0]
0x180030a9d  lea     rdx, [rsp+110h+var_E8]
0x180030aa2  lea     rcx, [rbp+57h+var_C0]
0x180030aa6  call    cs:__imp_?EnterprisePolicyManagerStore_GetAllProviderContextSidAreas@@YAJPEAUPolicyManagerScopeData@@PEAKPEAPEAPEAG@Z; EnterprisePolicyManagerStore_GetAllProviderContextSidAreas(PolicyManagerScopeData *,ulong *,ushort * * *)
0x180030aad  nop     dword ptr [rax+rax+00h]
0x180030ab2  cmp     [rsp+110h+pv], r14
0x180030ab7  jz      short loc_180030AE1
0x180030ab9  mov     ebx, r14d
0x180030abc  cmp     [rbp+57h+arg_18], r14d
0x180030ac0  jbe     short loc_180030AE1
0x180030ac2  mov     ecx, ebx
0x180030ac4  mov     rax, [rsp+110h+pv]
0x180030ac9  lea     r8, [rax+rcx*8]
0x180030acd  lea     rdx, [rsp+110h+var_D8]
0x180030ad2  mov     rcx, rsi
0x180030ad5  call    ??$emplace@AEAPEAG$0A@@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_DlistConstIt@U?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@utl@@_N@1@AEAPEAG@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,0>::emplace<ushort * &,0>(ushort * &)
0x180030ada  inc     ebx
0x180030adc  cmp     ebx, [rbp+57h+arg_18]
0x180030adf  jb      short loc_180030AC2
0x180030ae1  mov     rcx, [rsp+110h+var_E0]
0x180030ae6  mov     eax, [rsp+110h+var_E8]
0x180030aea  test    rcx, rcx
0x180030aed  jz      short loc_180030B5D
0x180030aef  mov     ebx, r14d
0x180030af2  test    eax, eax
0x180030af4  jz      short loc_180030B18
0x180030af6  mov     eax, ebx
0x180030af8  lea     r8, [rcx+rax*8]
0x180030afc  lea     rdx, [rsp+110h+var_D8]
0x180030b01  mov     rcx, rsi
0x180030b04  call    ??$emplace@AEAPEAG$0A@@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_DlistConstIt@U?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@utl@@_N@1@AEAPEAG@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,0>::emplace<ushort * &,0>(ushort * &)
0x180030b09  inc     ebx
0x180030b0b  mov     eax, [rsp+110h+var_E8]
0x180030b0f  mov     rcx, [rsp+110h+var_E0]
0x180030b14  cmp     ebx, eax
0x180030b16  jb      short loc_180030AF6
0x180030b18  test    rcx, rcx
0x180030b1b  jz      short loc_180030B5D
0x180030b1d  mov     edi, r14d
0x180030b20  test    eax, eax
0x180030b22  jz      short loc_180030B4C
0x180030b24  mov     ebx, edi
0x180030b26  mov     rcx, [rcx+rbx*8]; bstrString
0x180030b2a  call    cs:__imp_SysFreeString
0x180030b31  nop     dword ptr [rax+rax+00h]
0x180030b36  mov     rax, [rsp+110h+var_E0]
0x180030b3b  mov     [rax+rbx*8], r14
0x180030b3f  inc     edi
0x180030b41  mov     rcx, [rsp+110h+var_E0]; pv
0x180030b46  cmp     edi, [rsp+110h+var_E8]
0x180030b4a  jb      short loc_180030B24
0x180030b4c  call    cs:__imp_CoTaskMemFree
0x180030b53  nop     dword ptr [rax+rax+00h]
0x180030b58  mov     [rsp+110h+var_E0], r14
0x180030b5d  cmp     [rsp+110h+pv], r14
0x180030b62  jz      short loc_180030BAA
0x180030b64  mov     edi, r14d
0x180030b67  cmp     [rbp+57h+arg_18], r14d
0x180030b6b  jbe     short loc_180030B94
0x180030b6d  mov     ebx, edi
0x180030b6f  mov     rcx, [rsp+110h+pv]
0x180030b74  mov     rcx, [rcx+rbx*8]; bstrString
0x180030b78  call    cs:__imp_SysFreeString
0x180030b7f  nop     dword ptr [rax+rax+00h]
0x180030b84  mov     rax, [rsp+110h+pv]
0x180030b89  mov     [rax+rbx*8], r14
0x180030b8d  inc     edi
0x180030b8f  cmp     edi, [rbp+57h+arg_18]
0x180030b92  jb      short loc_180030B6D
0x180030b94  mov     rcx, [rsp+110h+pv]; pv
0x180030b99  call    cs:__imp_CoTaskMemFree
0x180030ba0  nop     dword ptr [rax+rax+00h]
0x180030ba5  mov     [rsp+110h+pv], r14
0x180030baa  mov     edi, r14d
0x180030bad  lea     rcx, [rbp+57h+var_C0]; this
0x180030bb1  call    ??1PolicyManagerScopeData@@QEAA@XZ; PolicyManagerScopeData::~PolicyManagerScopeData(void)
0x180030bb6  mov     eax, edi
0x180030bb8  lea     r11, [rsp+110h+var_10]
0x180030bc0  mov     rbx, [r11+20h]
0x180030bc4  mov     rsi, [r11+28h]
0x180030bc8  mov     rsp, r11
0x180030bcb  pop     r14
0x180030bcd  pop     rdi
0x180030bce  pop     rbp
0x180030bcf  retn
```
