# CComponentInfo::HrReadDerivedRegistryInfo(RegKey *)

- ea: `0x180064680`
- end: `0x1800647b2`
- name: `?HrReadDerivedRegistryInfo@CComponentInfo@@MEAAJPEAVRegKey@@@Z`
- size: `306`
- prototype: `int(CComponentInfo *__hidden this, struct RegKey *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180063b30`
- `0x1800d1590`
- `0x1800ded50`
- `0x1800e2950`

## callees

- `0x18005f4a4`
- `0x1800645ec`
- `0x180064680`
- `0x1800647b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064790`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064790`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006473c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006473c`

## pseudocode

```c
__int64 __fastcall CComponentInfo::HrReadDerivedRegistryInfo(CComponentInfo *this, struct RegKey *a2)
{
  CRegistryInfo *v4; // rcx
  CRegistryInfo *v5; // rcx
  CRegistryInfo *v6; // rcx
  CRegistryInfo *v7; // rcx
  HKEY v8; // rcx
  HKEY v9; // rbx
  CRegistryInfo *v10; // rcx
  HKEY v11; // rbp
  unsigned int StringValue; // edi
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  HKEY v15; // [rsp+58h] [rbp+10h] BYREF

  CRegistryInfo::SafeReadStringValue(this, a2, L"Author", (unsigned __int16 **)this + 10, (unsigned int *)this + 22);
  CRegistryInfo::SafeReadStringValue(v4, a2, L"FriendlyName", (unsigned __int16 **)this + 16, (unsigned int *)this + 34);
  CRegistryInfo::SafeReadStringValue(v5, a2, L"Version", (unsigned __int16 **)this + 12, (unsigned int *)this + 26);
  CRegistryInfo::SafeReadStringValue(v6, a2, L"SpecVersion", (unsigned __int16 **)this + 14, (unsigned int *)this + 30);
  CRegistryInfo::SafeReadClsidValue(v7, a2, L"Vendor", (struct _GUID *)((char *)this + 60));
  v8 = *(HKEY *)a2;
  v9 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(v8, L"InProcServer32", 0, 0x20019u, &hKey) )
  {
    StringValue = 0;
    v11 = 0;
  }
  else
  {
    v9 = hKey;
    v15 = hKey;
    v11 = hKey;
    StringValue = CRegistryInfo::SafeReadStringValue(
                    v10,
                    (struct RegKey *)&v15,
                    0,
                    (unsigned __int16 **)this + 18,
                    (unsigned int *)&hKey);
  }
  *((_DWORD *)this + 35) = CCodecFactory::IsCLSIDDisabled((const struct _GUID *)this + 1);
  if ( v11 )
    RegCloseKey(v9);
  return StringValue;
}

```

## disassembly

```asm
0x180064680  mov     [rsp+arg_10], rbx
0x180064685  push    rbp
0x180064686  push    rsi
0x180064687  push    rdi
0x180064688  sub     rsp, 30h
0x18006468c  lea     rax, [rcx+58h]
0x180064690  mov     rdi, rdx
0x180064693  lea     r9, [rcx+50h]; unsigned __int16 **
0x180064697  mov     [rsp+48h+phkResult], rax; unsigned int *
0x18006469c  lea     r8, aAuthor; "Author"
0x1800646a3  mov     rsi, rcx
0x1800646a6  call    ?SafeReadStringValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAPEAGPEAI@Z; CRegistryInfo::SafeReadStringValue(RegKey *,ushort const *,ushort * *,uint *)
0x1800646ab  lea     rax, [rsi+88h]
0x1800646b2  mov     rdx, rdi; struct RegKey *
0x1800646b5  lea     r9, [rsi+80h]; unsigned __int16 **
0x1800646bc  mov     [rsp+48h+phkResult], rax; unsigned int *
0x1800646c1  lea     r8, aFriendlyname; "FriendlyName"
0x1800646c8  call    ?SafeReadStringValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAPEAGPEAI@Z; CRegistryInfo::SafeReadStringValue(RegKey *,ushort const *,ushort * *,uint *)
0x1800646cd  lea     rax, [rsi+68h]
0x1800646d1  mov     rdx, rdi; struct RegKey *
0x1800646d4  lea     r9, [rsi+60h]; unsigned __int16 **
0x1800646d8  mov     [rsp+48h+phkResult], rax; unsigned int *
0x1800646dd  lea     r8, aVersion; "Version"
0x1800646e4  call    ?SafeReadStringValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAPEAGPEAI@Z; CRegistryInfo::SafeReadStringValue(RegKey *,ushort const *,ushort * *,uint *)
0x1800646e9  lea     rax, [rsi+78h]
0x1800646ed  mov     rdx, rdi; struct RegKey *
0x1800646f0  lea     r9, [rsi+70h]; unsigned __int16 **
0x1800646f4  mov     [rsp+48h+phkResult], rax; unsigned int *
0x1800646f9  lea     r8, aSpecversion; "SpecVersion"
0x180064700  call    ?SafeReadStringValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAPEAGPEAI@Z; CRegistryInfo::SafeReadStringValue(RegKey *,ushort const *,ushort * *,uint *)
0x180064705  lea     r9, [rsi+3Ch]; struct _GUID *
0x180064709  mov     rdx, rdi; struct RegKey *
0x18006470c  lea     r8, aVendor; "Vendor"
0x180064713  call    ?SafeReadClsidValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAU_GUID@@@Z; CRegistryInfo::SafeReadClsidValue(RegKey *,ushort const *,_GUID *)
0x180064718  mov     rcx, [rdi]; hKey
0x18006471b  lea     rax, [rsp+48h+hKey]
0x180064720  xor     ebx, ebx
0x180064722  mov     [rsp+48h+phkResult], rax; phkResult
0x180064727  mov     r9d, 20019h; samDesired
0x18006472d  mov     [rsp+48h+hKey], rbx
0x180064732  xor     r8d, r8d; ulOptions
0x180064735  lea     rdx, SubKey; "InProcServer32"
0x18006473c  call    cs:__imp_RegOpenKeyExW
0x180064743  nop     dword ptr [rax+rax+00h]
0x180064748  test    eax, eax
0x18006474a  jnz     short loc_1800647AC
0x18006474c  mov     rbx, [rsp+48h+hKey]
0x180064751  lea     rax, [rsp+48h+hKey]
0x180064756  lea     r9, [rsi+90h]; unsigned __int16 **
0x18006475d  mov     [rsp+48h+arg_8], rbx
0x180064762  xor     r8d, r8d; unsigned __int16 *
0x180064765  mov     [rsp+48h+phkResult], rax; unsigned int *
0x18006476a  lea     rdx, [rsp+48h+arg_8]; struct RegKey *
0x18006476f  mov     rbp, rbx
0x180064772  call    ?SafeReadStringValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAPEAGPEAI@Z; CRegistryInfo::SafeReadStringValue(RegKey *,ushort const *,ushort * *,uint *)
0x180064777  mov     edi, eax
0x180064779  lea     rcx, [rsi+10h]; struct _GUID *
0x18006477d  call    ?IsCLSIDDisabled@CCodecFactory@@SAHAEBU_GUID@@@Z; CCodecFactory::IsCLSIDDisabled(_GUID const &)
0x180064782  mov     [rsi+8Ch], eax
0x180064788  test    rbp, rbp
0x18006478b  jz      short loc_18006479C
0x18006478d  mov     rcx, rbx; hKey
0x180064790  call    cs:__imp_RegCloseKey
0x180064797  nop     dword ptr [rax+rax+00h]
0x18006479c  mov     rbx, [rsp+48h+arg_10]
0x1800647a1  mov     eax, edi
0x1800647a3  add     rsp, 30h
0x1800647a7  pop     rdi
0x1800647a8  pop     rsi
0x1800647a9  pop     rbp
0x1800647aa  retn
0x1800647ac  xor     edi, edi
0x1800647ae  xor     ebp, ebp
0x1800647b0  jmp     short loc_180064779
```
