# Windows::ApplicationModel::Resources::Core::_GetApplicationLanguageHandle(HKEY__ * *)

- ea: `0x180076bfc`
- end: `0x180076cd5`
- name: `?_GetApplicationLanguageHandle@Core@Resources@ApplicationModel@Windows@@YAJPEAPEAUHKEY__@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Resources::Core *__hidden this, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800810c0`

## callees

- `0x180076bfc`
- `0x1800862f0`

## import_xrefs

- `KERNELBASE!GetCurrentPackageFamilyName` at `0x180076c2c`
- `KERNELBASE!GetCurrentPackageFamilyName` at `0x180076c2c`
- `profapi!__imp_GetAppContainerRegistryHandleFromName` at `0x180076c6c`
- `profapi!__imp_GetAppContainerRegistryHandleFromName` at `0x180076c95`
- `profapi!__imp_GetAppContainerRegistryHandleFromName` at `0x180076c6c`
- `profapi!__imp_GetAppContainerRegistryHandleFromName` at `0x180076c95`

## string_xrefs

- `0x180076c5e`: `ResourcesConfig`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Resources::Core::_GetApplicationLanguageHandle(
        Windows::ApplicationModel::Resources::Core *this,
        HKEY *a2)
{
  LONG CurrentPackageFamilyName; // eax
  unsigned int v4; // edx
  int AppContainerRegistryHandleFromName; // eax
  int v6; // eax
  UINT32 packageFamilyNameLength; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v9; // [rsp+38h] [rbp-B0h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+40h] [rbp-A8h] BYREF

  packageFamilyNameLength = 65;
  CurrentPackageFamilyName = GetCurrentPackageFamilyName(&packageFamilyNameLength, packageFamilyName);
  v4 = CurrentPackageFamilyName;
  if ( CurrentPackageFamilyName > 0 )
    v4 = (unsigned __int16)CurrentPackageFamilyName | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
  {
    v9 = 0;
    AppContainerRegistryHandleFromName = GetAppContainerRegistryHandleFromName(
                                           packageFamilyName,
                                           0,
                                           L"ResourcesConfig",
                                           131097,
                                           &v9);
    v4 = AppContainerRegistryHandleFromName;
    if ( AppContainerRegistryHandleFromName == -2147024894 )
    {
      v6 = GetAppContainerRegistryHandleFromName(packageFamilyName, 0, 0, 131103, &v9);
      v4 = v6;
      if ( v6 < 0 )
      {
        if ( v6 != -2147024891 )
          return v4;
        v4 = 0;
      }
    }
    else if ( AppContainerRegistryHandleFromName < 0 )
    {
      return v4;
    }
    *(_QWORD *)this = v9;
  }
  return v4;
}

```

## disassembly

```asm
0x180076bfc  push    rbx
0x180076bfe  sub     rsp, 0E0h
0x180076c05  mov     rax, cs:__security_cookie
0x180076c0c  xor     rax, rsp
0x180076c0f  mov     [rsp+0E8h+var_18], rax
0x180076c17  mov     rbx, rcx
0x180076c1a  mov     [rsp+0E8h+packageFamilyNameLength], 41h ; 'A'
0x180076c22  lea     rcx, [rsp+0E8h+packageFamilyNameLength]; packageFamilyNameLength
0x180076c27  lea     rdx, [rsp+0E8h+packageFamilyName]; packageFamilyName
0x180076c2c  call    cs:__imp_GetCurrentPackageFamilyName
0x180076c32  mov     edx, eax
0x180076c34  test    eax, eax
0x180076c36  jle     short loc_180076C41
0x180076c38  movzx   edx, ax
0x180076c3b  or      edx, 80070000h
0x180076c41  test    edx, edx
0x180076c43  js      short loc_180076CA9
0x180076c45  lea     rax, [rsp+0E8h+var_B0]
0x180076c4a  mov     [rsp+0E8h+var_B0], 0
0x180076c53  mov     r9d, 20019h
0x180076c59  mov     [rsp+0E8h+var_C8], rax
0x180076c5e  lea     r8, aResourcesconfi; "ResourcesConfig"
0x180076c65  xor     edx, edx
0x180076c67  lea     rcx, [rsp+0E8h+packageFamilyName]
0x180076c6c  call    cs:__imp_GetAppContainerRegistryHandleFromName
0x180076c72  mov     edx, eax
0x180076c74  cmp     eax, 80070002h
0x180076c79  jnz     short loc_180076CCF
0x180076c7b  lea     rax, [rsp+0E8h+var_B0]
0x180076c80  mov     r9d, 2001Fh
0x180076c86  xor     r8d, r8d
0x180076c89  mov     [rsp+0E8h+var_C8], rax
0x180076c8e  xor     edx, edx
0x180076c90  lea     rcx, [rsp+0E8h+packageFamilyName]
0x180076c95  call    cs:__imp_GetAppContainerRegistryHandleFromName
0x180076c9b  mov     edx, eax
0x180076c9d  test    eax, eax
0x180076c9f  js      short loc_180076CC4
0x180076ca1  mov     rax, [rsp+0E8h+var_B0]
0x180076ca6  mov     [rbx], rax
0x180076ca9  mov     eax, edx
0x180076cab  mov     rcx, [rsp+0E8h+var_18]
0x180076cb3  xor     rcx, rsp; StackCookie
0x180076cb6  call    __security_check_cookie
0x180076cbb  add     rsp, 0E0h
0x180076cc2  pop     rbx
0x180076cc3  retn
0x180076cc4  cmp     eax, 80070005h
0x180076cc9  jnz     short loc_180076CA9
0x180076ccb  xor     edx, edx
0x180076ccd  jmp     short loc_180076CA1
0x180076ccf  test    eax, eax
0x180076cd1  js      short loc_180076CA9
0x180076cd3  jmp     short loc_180076CA1
```
