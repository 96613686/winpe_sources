# CMidi2DiagnosticsPluginMetadataProvider::GetMetadata(__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 *)

- ea: `0x1800119a0`
- end: `0x180011b55`
- name: `?GetMetadata@CMidi2DiagnosticsPluginMetadataProvider@@UEAAJPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(CMidi2DiagnosticsPluginMetadataProvider *__hidden this, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800033d0`
- `0x180008f64`
- `0x18000b7fc`
- `0x180011630`
- `0x1800117e8`
- `0x1800119a0`
- `0x180011b5c`
- `0x180011d2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011b01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011a98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011b01`

## string_xrefs

- `0x1800119ce`: `avcore\midi2\transport\diagnosticstransport\midi2.diagnosticspluginmetadataprovider.cpp`

## pseudocode

```c
__int64 __fastcall CMidi2DiagnosticsPluginMetadataProvider::GetMetadata(
        CMidi2DiagnosticsPluginMetadataProvider *this,
        struct __MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 *a2,
        unsigned __int64 a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 result; // rax
  __int64 v7; // rbx
  char *cotaskmem_string_nothrow; // rax
  unsigned __int16 **v9; // r8
  unsigned __int16 **v10; // r8
  __int64 v11; // rbx
  __int64 CurrentModuleVersionCompanyName; // rax
  unsigned __int64 v13; // r8
  char *v14; // rax
  __int64 v15; // rbx
  __int64 CurrentModuleVersion; // rax
  unsigned __int64 v17; // r8
  char *v18; // rax
  LPVOID pv; // [rsp+20h] [rbp-58h] BYREF
  char v20; // [rsp+28h] [rbp-50h] BYREF
  char v21; // [rsp+30h] [rbp-48h] BYREF
  char v22; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v23[32]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 26;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.diagnosticspluginmetadataprovider.cpp",
      (const char *)v4,
      (int)pv);
    return v4;
  }
  v7 = 0;
  *(GUID *)a2 = GUID_ac9b5417_3fe0_4e62_960f_034ee4235a1a;
  cotaskmem_string_nothrow = (char *)wil::make_cotaskmem_string_nothrow((wil *)&pv, L"DIAG", a3);
  if ( &v20 != cotaskmem_string_nothrow )
  {
    v7 = *(_QWORD *)cotaskmem_string_nothrow;
    *(_QWORD *)cotaskmem_string_nothrow = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( !v7 )
  {
    v4 = -2147024882;
    v5 = 32;
    goto LABEL_3;
  }
  *((_QWORD *)a2 + 2) = v7;
  WindowsMidiServicesInternal::ResourceCopyToCoString((WindowsMidiServicesInternal *)0x1F5, (_DWORD)a2 + 24, v9);
  WindowsMidiServicesInternal::ResourceCopyToCoString((WindowsMidiServicesInternal *)0x1F6, (_DWORD)a2 + 32, v10);
  v11 = 0;
  CurrentModuleVersionCompanyName = WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName(v23);
  if ( *(_QWORD *)(CurrentModuleVersionCompanyName + 24) > 7u )
    CurrentModuleVersionCompanyName = *(_QWORD *)CurrentModuleVersionCompanyName;
  v14 = (char *)wil::make_cotaskmem_string_nothrow(
                  (wil *)&pv,
                  (const unsigned __int16 *)CurrentModuleVersionCompanyName,
                  v13);
  if ( &v21 != v14 )
  {
    v11 = *(_QWORD *)v14;
    *(_QWORD *)v14 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  std::wstring::~wstring(v23);
  if ( !v11 )
  {
    v4 = -2147024882;
    v5 = 40;
    goto LABEL_3;
  }
  *((_QWORD *)a2 + 5) = v11;
  v15 = 0;
  CurrentModuleVersion = WindowsMidiServicesInternal::GetCurrentModuleVersion(v23);
  if ( *(_QWORD *)(CurrentModuleVersion + 24) > 7u )
    CurrentModuleVersion = *(_QWORD *)CurrentModuleVersion;
  v18 = (char *)wil::make_cotaskmem_string_nothrow((wil *)&pv, (const unsigned __int16 *)CurrentModuleVersion, v17);
  if ( &v22 != v18 )
  {
    v15 = *(_QWORD *)v18;
    *(_QWORD *)v18 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  std::wstring::~wstring(v23);
  if ( !v15 )
  {
    v4 = -2147024882;
    v5 = 45;
    goto LABEL_3;
  }
  *((_QWORD *)a2 + 7) = v15;
  result = 0;
  *((_QWORD *)a2 + 6) = 0;
  *((_DWORD *)a2 + 16) = 4;
  return result;
}

```

## disassembly

```asm
0x1800119a0  mov     [rsp+arg_0], rbx
0x1800119a5  push    rdi
0x1800119a6  sub     rsp, 70h
0x1800119aa  mov     rax, cs:__security_cookie
0x1800119b1  xor     rax, rsp
0x1800119b4  mov     [rsp+78h+var_18], rax
0x1800119b9  mov     rdi, rdx
0x1800119bc  test    rdx, rdx
0x1800119bf  jnz     short loc_1800119E4
0x1800119c1  mov     ebx, 80070057h
0x1800119c6  lea     edx, [rdi+1Ah]; void *
0x1800119c9  mov     rcx, [rsp+78h]; this
0x1800119ce  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transport\\diagnosticstr"...
0x1800119d5  mov     r9d, ebx; char *
0x1800119d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800119dd  mov     eax, ebx
0x1800119df  jmp     loc_180011B3A
0x1800119e4  movups  xmm0, xmmword ptr cs:_GUID_ac9b5417_3fe0_4e62_960f_034ee4235a1a.Data1
0x1800119eb  lea     rcx, [rsp+78h+pv]; this
0x1800119f0  xor     ebx, ebx
0x1800119f2  movdqu  xmmword ptr [rdx], xmm0
0x1800119f6  lea     rdx, aDiag; "DIAG"
0x1800119fd  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180011a02  lea     rcx, [rsp+78h+var_50]
0x180011a07  cmp     rcx, rax
0x180011a0a  jz      short loc_180011A16
0x180011a0c  mov     rbx, [rax]
0x180011a0f  mov     qword ptr [rax], 0
0x180011a16  mov     rcx, [rsp+78h+pv]; pv
0x180011a1b  test    rcx, rcx
0x180011a1e  jz      short loc_180011A26
0x180011a20  call    cs:__imp_CoTaskMemFree
0x180011a26  test    rbx, rbx
0x180011a29  jnz     short loc_180011A37
0x180011a2b  mov     ebx, 8007000Eh
0x180011a30  mov     edx, 20h ; ' '
0x180011a35  jmp     short loc_1800119C9
0x180011a37  lea     rdx, [rdi+18h]; unsigned int
0x180011a3b  mov     [rdi+10h], rbx
0x180011a3f  mov     ecx, 1F5h; this
0x180011a44  call    ?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z; WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)
0x180011a49  lea     rdx, [rdi+20h]; unsigned int
0x180011a4d  mov     ecx, 1F6h; this
0x180011a52  call    ?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z; WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)
0x180011a57  lea     rcx, [rsp+78h+var_38]
0x180011a5c  xor     ebx, ebx
0x180011a5e  call    ?GetCurrentModuleVersionCompanyName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName(void)
0x180011a63  cmp     qword ptr [rax+18h], 7
0x180011a68  jbe     short loc_180011A6D
0x180011a6a  mov     rax, [rax]
0x180011a6d  mov     rdx, rax; unsigned __int16 *
0x180011a70  lea     rcx, [rsp+78h+pv]; this
0x180011a75  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180011a7a  lea     rcx, [rsp+78h+var_48]
0x180011a7f  cmp     rcx, rax
0x180011a82  jz      short loc_180011A8E
0x180011a84  mov     rbx, [rax]
0x180011a87  mov     qword ptr [rax], 0
0x180011a8e  mov     rcx, [rsp+78h+pv]; pv
0x180011a93  test    rcx, rcx
0x180011a96  jz      short loc_180011A9E
0x180011a98  call    cs:__imp_CoTaskMemFree
0x180011a9e  lea     rcx, [rsp+78h+var_38]
0x180011aa3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011aa8  test    rbx, rbx
0x180011aab  jnz     short loc_180011ABC
0x180011aad  mov     ebx, 8007000Eh
0x180011ab2  mov     edx, 28h ; '('
0x180011ab7  jmp     loc_1800119C9
0x180011abc  mov     [rdi+28h], rbx
0x180011ac0  lea     rcx, [rsp+78h+var_38]
0x180011ac5  xor     ebx, ebx
0x180011ac7  call    ?GetCurrentModuleVersion@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WindowsMidiServicesInternal::GetCurrentModuleVersion(void)
0x180011acc  cmp     qword ptr [rax+18h], 7
0x180011ad1  jbe     short loc_180011AD6
0x180011ad3  mov     rax, [rax]
0x180011ad6  mov     rdx, rax; unsigned __int16 *
0x180011ad9  lea     rcx, [rsp+78h+pv]; this
0x180011ade  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180011ae3  lea     rcx, [rsp+78h+var_40]
0x180011ae8  cmp     rcx, rax
0x180011aeb  jz      short loc_180011AF7
0x180011aed  mov     rbx, [rax]
0x180011af0  mov     qword ptr [rax], 0
0x180011af7  mov     rcx, [rsp+78h+pv]; pv
0x180011afc  test    rcx, rcx
0x180011aff  jz      short loc_180011B07
0x180011b01  call    cs:__imp_CoTaskMemFree
0x180011b07  lea     rcx, [rsp+78h+var_38]
0x180011b0c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011b11  test    rbx, rbx
0x180011b14  jnz     short loc_180011B25
0x180011b16  mov     ebx, 8007000Eh
0x180011b1b  mov     edx, 2Dh ; '-'
0x180011b20  jmp     loc_1800119C9
0x180011b25  mov     [rdi+38h], rbx
0x180011b29  xor     eax, eax
0x180011b2b  mov     qword ptr [rdi+30h], 0
0x180011b33  mov     dword ptr [rdi+40h], 4
0x180011b3a  mov     rcx, [rsp+78h+var_18]
0x180011b3f  xor     rcx, rsp; StackCookie
0x180011b42  call    __security_check_cookie
0x180011b47  mov     rbx, [rsp+78h+arg_0]
0x180011b4f  add     rsp, 70h
0x180011b53  pop     rdi
0x180011b54  retn
```
