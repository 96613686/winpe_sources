# CComponentInfo::HrReadDerivedRegistryInfo(RegKey *)

- ea: `0x18008fe60`
- end: `0x18008ff85`
- name: `?HrReadDerivedRegistryInfo@CComponentInfo@@MEAAJPEAVRegKey@@@Z`
- size: `293`
- prototype: `int(CComponentInfo *__hidden this, struct RegKey *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008f440`
- `0x1800ced40`
- `0x1800dc0e0`
- `0x1800dfb70`

## callees

- `0x180040b90`
- `0x18008fddc`
- `0x18008fe60`
- `0x18008ff8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ff6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ff6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008ff1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008ff1c`

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
0x18008fe60  mov     [rsp+arg_10], rbx
0x18008fe65  push    rbp
0x18008fe66  push    rsi
0x18008fe67  push    rdi
0x18008fe68  sub     rsp, 30h
0x18008fe6c  lea     rax, [rcx+58h]
0x18008fe70  mov     rdi, rdx
0x18008fe73  lea     r9, [rcx+50h]; unsigned __int16 **
0x18008fe77  mov     [rsp+48h+phkResult], rax; unsigned int *
0x18008fe7c  lea     r8, aAuthor; "Author"
0x18008fe83  mov     rsi, rcx
0x18008fe86  call    ?SafeReadStringValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAPEAGPEAI@Z; CRegistryInfo::SafeReadStringValue(RegKey *,ushort const *,ushort * *,uint *)
0x18008fe8b  lea     rax, [rsi+88h]
0x18008fe92  mov     rdx, rdi; struct RegKey *
0x18008fe95  lea     r9, [rsi+80h]; unsigned __int16 **
0x18008fe9c  mov     [rsp+48h+phkResult], rax; unsigned int *
0x18008fea1  lea     r8, aFriendlyname; "FriendlyName"
0x18008fea8  call    ?SafeReadStringValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAPEAGPEAI@Z; CRegistryInfo::SafeReadStringValue(RegKey *,ushort const *,ushort * *,uint *)
0x18008fead  lea     rax, [rsi+68h]
0x18008feb1  mov     rdx, rdi; struct RegKey *
0x18008feb4  lea     r9, [rsi+60h]; unsigned __int16 **
0x18008feb8  mov     [rsp+48h+phkResult], rax; unsigned int *
0x18008febd  lea     r8, aVersion; "Version"
0x18008fec4  call    ?SafeReadStringValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAPEAGPEAI@Z; CRegistryInfo::SafeReadStringValue(RegKey *,ushort const *,ushort * *,uint *)
0x18008fec9  lea     rax, [rsi+78h]
0x18008fecd  mov     rdx, rdi; struct RegKey *
0x18008fed0  lea     r9, [rsi+70h]; unsigned __int16 **
0x18008fed4  mov     [rsp+48h+phkResult], rax; unsigned int *
0x18008fed9  lea     r8, aSpecversion; "SpecVersion"
0x18008fee0  call    ?SafeReadStringValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAPEAGPEAI@Z; CRegistryInfo::SafeReadStringValue(RegKey *,ushort const *,ushort * *,uint *)
0x18008fee5  lea     r9, [rsi+3Ch]; struct _GUID *
0x18008fee9  mov     rdx, rdi; struct RegKey *
0x18008feec  lea     r8, aVendor; "Vendor"
0x18008fef3  call    ?SafeReadClsidValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAU_GUID@@@Z; CRegistryInfo::SafeReadClsidValue(RegKey *,ushort const *,_GUID *)
0x18008fef8  mov     rcx, [rdi]; hKey
0x18008fefb  lea     rax, [rsp+48h+hKey]
0x18008ff00  xor     ebx, ebx
0x18008ff02  mov     [rsp+48h+phkResult], rax; phkResult
0x18008ff07  mov     r9d, 20019h; samDesired
0x18008ff0d  mov     [rsp+48h+hKey], rbx
0x18008ff12  xor     r8d, r8d; ulOptions
0x18008ff15  lea     rdx, SubKey; "InProcServer32"
0x18008ff1c  call    cs:__imp_RegOpenKeyExW
0x18008ff22  test    eax, eax
0x18008ff24  jnz     short loc_18008FF7F
0x18008ff26  mov     rbx, [rsp+48h+hKey]
0x18008ff2b  lea     rax, [rsp+48h+hKey]
0x18008ff30  lea     r9, [rsi+90h]; unsigned __int16 **
0x18008ff37  mov     [rsp+48h+arg_8], rbx
0x18008ff3c  xor     r8d, r8d; unsigned __int16 *
0x18008ff3f  mov     [rsp+48h+phkResult], rax; unsigned int *
0x18008ff44  lea     rdx, [rsp+48h+arg_8]; struct RegKey *
0x18008ff49  mov     rbp, rbx
0x18008ff4c  call    ?SafeReadStringValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAPEAGPEAI@Z; CRegistryInfo::SafeReadStringValue(RegKey *,ushort const *,ushort * *,uint *)
0x18008ff51  mov     edi, eax
0x18008ff53  lea     rcx, [rsi+10h]; struct _GUID *
0x18008ff57  call    ?IsCLSIDDisabled@CCodecFactory@@SAHAEBU_GUID@@@Z; CCodecFactory::IsCLSIDDisabled(_GUID const &)
0x18008ff5c  mov     [rsi+8Ch], eax
0x18008ff62  test    rbp, rbp
0x18008ff65  jz      short loc_18008FF70
0x18008ff67  mov     rcx, rbx; hKey
0x18008ff6a  call    cs:__imp_RegCloseKey
0x18008ff70  mov     rbx, [rsp+48h+arg_10]
0x18008ff75  mov     eax, edi
0x18008ff77  add     rsp, 30h
0x18008ff7b  pop     rdi
0x18008ff7c  pop     rsi
0x18008ff7d  pop     rbp
0x18008ff7e  retn
0x18008ff7f  xor     edi, edi
0x18008ff81  xor     ebp, ebp
0x18008ff83  jmp     short loc_18008FF53
```
