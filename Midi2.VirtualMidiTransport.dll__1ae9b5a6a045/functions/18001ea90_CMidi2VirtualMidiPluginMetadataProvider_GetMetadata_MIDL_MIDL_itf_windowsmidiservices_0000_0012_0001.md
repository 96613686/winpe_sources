# CMidi2VirtualMidiPluginMetadataProvider::GetMetadata(__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 *)

- ea: `0x18001ea90`
- end: `0x18001ec45`
- name: `?GetMetadata@CMidi2VirtualMidiPluginMetadataProvider@@UEAAJPEAU__MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(CMidi2VirtualMidiPluginMetadataProvider *__hidden this, struct __MIDL___MIDL_itf_windowsmidiservices_0000_0012_0001 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800038f0`
- `0x180009784`
- `0x18000bf6c`
- `0x18001e528`
- `0x18001e714`
- `0x18001e8cc`
- `0x18001ea90`
- `0x18001ec4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ebf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ebf1`

## string_xrefs

- `0x18001eabe`: `avcore\midi2\transport\virtualmiditransport\midi2.virtualmidipluginmetadataprovider.cpp`

## pseudocode

```c
__int64 __fastcall CMidi2VirtualMidiPluginMetadataProvider::GetMetadata(
        CMidi2VirtualMidiPluginMetadataProvider *this,
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
    v5 = 27;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidipluginmetadataprovider.cpp",
      (const char *)v4,
      (int)pv);
    return v4;
  }
  v7 = 0;
  *(GUID *)a2 = GUID_8feaad91_70e1_4a19_997a_377720a719c1;
  cotaskmem_string_nothrow = (char *)wil::make_cotaskmem_string_nothrow((wil *)&pv, L"APP", a3);
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
    v5 = 33;
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
    v5 = 41;
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
    v5 = 47;
    goto LABEL_3;
  }
  *((_QWORD *)a2 + 7) = v15;
  result = 0;
  *((_QWORD *)a2 + 6) = 0;
  *((_DWORD *)a2 + 16) = 1;
  return result;
}

```

## disassembly

```asm
0x18001ea90  mov     [rsp+arg_0], rbx
0x18001ea95  push    rdi
0x18001ea96  sub     rsp, 70h
0x18001ea9a  mov     rax, cs:__security_cookie
0x18001eaa1  xor     rax, rsp
0x18001eaa4  mov     [rsp+78h+var_18], rax
0x18001eaa9  mov     rdi, rdx
0x18001eaac  test    rdx, rdx
0x18001eaaf  jnz     short loc_18001EAD4
0x18001eab1  mov     ebx, 80070057h
0x18001eab6  lea     edx, [rdi+1Bh]; void *
0x18001eab9  mov     rcx, [rsp+78h]; this
0x18001eabe  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transport\\virtualmiditr"...
0x18001eac5  mov     r9d, ebx; char *
0x18001eac8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eacd  mov     eax, ebx
0x18001eacf  jmp     loc_18001EC2A
0x18001ead4  movups  xmm0, xmmword ptr cs:_GUID_8feaad91_70e1_4a19_997a_377720a719c1.Data1
0x18001eadb  lea     rcx, [rsp+78h+pv]; this
0x18001eae0  xor     ebx, ebx
0x18001eae2  movdqu  xmmword ptr [rdx], xmm0
0x18001eae6  lea     rdx, aApp; "APP"
0x18001eaed  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18001eaf2  lea     rcx, [rsp+78h+var_50]
0x18001eaf7  cmp     rcx, rax
0x18001eafa  jz      short loc_18001EB06
0x18001eafc  mov     rbx, [rax]
0x18001eaff  mov     qword ptr [rax], 0
0x18001eb06  mov     rcx, [rsp+78h+pv]; pv
0x18001eb0b  test    rcx, rcx
0x18001eb0e  jz      short loc_18001EB16
0x18001eb10  call    cs:__imp_CoTaskMemFree
0x18001eb16  test    rbx, rbx
0x18001eb19  jnz     short loc_18001EB27
0x18001eb1b  mov     ebx, 8007000Eh
0x18001eb20  mov     edx, 21h ; '!'
0x18001eb25  jmp     short loc_18001EAB9
0x18001eb27  lea     rdx, [rdi+18h]; unsigned int
0x18001eb2b  mov     [rdi+10h], rbx
0x18001eb2f  mov     ecx, 1F5h; this
0x18001eb34  call    ?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z; WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)
0x18001eb39  lea     rdx, [rdi+20h]; unsigned int
0x18001eb3d  mov     ecx, 1F6h; this
0x18001eb42  call    ?ResourceCopyToCoString@WindowsMidiServicesInternal@@YAJIPEAPEAG@Z; WindowsMidiServicesInternal::ResourceCopyToCoString(uint,ushort * *)
0x18001eb47  lea     rcx, [rsp+78h+var_38]
0x18001eb4c  xor     ebx, ebx
0x18001eb4e  call    ?GetCurrentModuleVersionCompanyName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName(void)
0x18001eb53  cmp     qword ptr [rax+18h], 7
0x18001eb58  jbe     short loc_18001EB5D
0x18001eb5a  mov     rax, [rax]
0x18001eb5d  mov     rdx, rax; unsigned __int16 *
0x18001eb60  lea     rcx, [rsp+78h+pv]; this
0x18001eb65  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18001eb6a  lea     rcx, [rsp+78h+var_48]
0x18001eb6f  cmp     rcx, rax
0x18001eb72  jz      short loc_18001EB7E
0x18001eb74  mov     rbx, [rax]
0x18001eb77  mov     qword ptr [rax], 0
0x18001eb7e  mov     rcx, [rsp+78h+pv]; pv
0x18001eb83  test    rcx, rcx
0x18001eb86  jz      short loc_18001EB8E
0x18001eb88  call    cs:__imp_CoTaskMemFree
0x18001eb8e  lea     rcx, [rsp+78h+var_38]
0x18001eb93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001eb98  test    rbx, rbx
0x18001eb9b  jnz     short loc_18001EBAC
0x18001eb9d  mov     ebx, 8007000Eh
0x18001eba2  mov     edx, 29h ; ')'
0x18001eba7  jmp     loc_18001EAB9
0x18001ebac  mov     [rdi+28h], rbx
0x18001ebb0  lea     rcx, [rsp+78h+var_38]
0x18001ebb5  xor     ebx, ebx
0x18001ebb7  call    ?GetCurrentModuleVersion@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WindowsMidiServicesInternal::GetCurrentModuleVersion(void)
0x18001ebbc  cmp     qword ptr [rax+18h], 7
0x18001ebc1  jbe     short loc_18001EBC6
0x18001ebc3  mov     rax, [rax]
0x18001ebc6  mov     rdx, rax; unsigned __int16 *
0x18001ebc9  lea     rcx, [rsp+78h+pv]; this
0x18001ebce  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18001ebd3  lea     rcx, [rsp+78h+var_40]
0x18001ebd8  cmp     rcx, rax
0x18001ebdb  jz      short loc_18001EBE7
0x18001ebdd  mov     rbx, [rax]
0x18001ebe0  mov     qword ptr [rax], 0
0x18001ebe7  mov     rcx, [rsp+78h+pv]; pv
0x18001ebec  test    rcx, rcx
0x18001ebef  jz      short loc_18001EBF7
0x18001ebf1  call    cs:__imp_CoTaskMemFree
0x18001ebf7  lea     rcx, [rsp+78h+var_38]
0x18001ebfc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ec01  test    rbx, rbx
0x18001ec04  jnz     short loc_18001EC15
0x18001ec06  mov     ebx, 8007000Eh
0x18001ec0b  mov     edx, 2Fh ; '/'
0x18001ec10  jmp     loc_18001EAB9
0x18001ec15  mov     [rdi+38h], rbx
0x18001ec19  xor     eax, eax
0x18001ec1b  mov     qword ptr [rdi+30h], 0
0x18001ec23  mov     dword ptr [rdi+40h], 1
0x18001ec2a  mov     rcx, [rsp+78h+var_18]
0x18001ec2f  xor     rcx, rsp; StackCookie
0x18001ec32  call    __security_check_cookie
0x18001ec37  mov     rbx, [rsp+78h+arg_0]
0x18001ec3f  add     rsp, 70h
0x18001ec43  pop     rdi
0x18001ec44  retn
```
