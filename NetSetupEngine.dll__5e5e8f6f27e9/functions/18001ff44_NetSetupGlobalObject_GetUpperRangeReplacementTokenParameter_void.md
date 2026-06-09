# NetSetupGlobalObject::GetUpperRangeReplacementTokenParameter(void)

- ea: `0x18001ff44`
- end: `0x18002005a`
- name: `?GetUpperRangeReplacementTokenParameter@NetSetupGlobalObject@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `278`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18001f780`

## callees

- `0x180010200`
- `0x180012108`
- `0x18001f2c4`
- `0x18001ff44`
- `0x18002b260`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002000b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002000b`

## string_xrefs

- `0x180020016`: `UpperRangeReplacementToken`
- `0x180020036`: `UpperRangeReplacementToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY __fastcall NetSetupGlobalObject::GetUpperRangeReplacementTokenParameter(__int64 a1, HKEY a2)
{
  char v4; // al
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF

  hKey = a2;
  if ( !byte_1800D4E9F || byte_1800D4E9E )
  {
    RegistryKey::CreateSubKey(
      (HKEY *)(*(_QWORD *)(a1 + 24) + 24LL),
      (HKEY)&hKey,
      L"Control\\NetworkSetup2\\Parameters",
      1u,
      0,
      0);
    if ( byte_1800D4E9F )
    {
      v4 = byte_1800D4E9E;
    }
    else
    {
      v4 = RegistryKey::ValueExists((RegistryKey *)&hKey, L"UpperRangeReplacementToken");
      byte_1800D4E9E = v4;
      byte_1800D4E9F = 1;
    }
    if ( v4 )
    {
      RegistryKey::GetValueString(&hKey, a2, L"UpperRangeReplacementToken");
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    else
    {
      *((_QWORD *)a2 + 3) = 7;
      *((_QWORD *)a2 + 2) = 0;
      *(_WORD *)a2 = 0;
      if ( hKey )
        RegCloseKey(hKey);
    }
  }
  else
  {
    *((_QWORD *)a2 + 3) = 7;
    *((_QWORD *)a2 + 2) = 0;
    *(_WORD *)a2 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18001ff44  push    rbx
0x18001ff46  sub     rsp, 60h
0x18001ff4a  mov     [rsp+68h+var_20], 0FFFFFFFFFFFFFFFEh
0x18001ff53  mov     rax, cs:__security_cookie
0x18001ff5a  xor     rax, rsp
0x18001ff5d  mov     [rsp+68h+var_10], rax
0x18001ff62  mov     rbx, rdx
0x18001ff65  mov     [rsp+68h+hKey], rdx
0x18001ff6a  cmp     cs:byte_1800D4E9F, 0
0x18001ff71  jz      short loc_18001FFA7
0x18001ff73  cmp     cs:byte_1800D4E9E, 0
0x18001ff7a  jnz     short loc_18001FFA7
0x18001ff7c  mov     qword ptr [rdx+18h], 7
0x18001ff84  mov     qword ptr [rdx+10h], 0
0x18001ff8c  xor     ecx, ecx
0x18001ff8e  mov     [rdx], cx
0x18001ff91  mov     rax, rbx
0x18001ff94  mov     rcx, [rsp+68h+var_10]
0x18001ff99  xor     rcx, rsp; StackCookie
0x18001ff9c  call    __security_check_cookie
0x18001ffa1  add     rsp, 60h
0x18001ffa5  pop     rbx
0x18001ffa6  retn
0x18001ffa7  mov     rcx, [rcx+18h]
0x18001ffab  add     rcx, 18h
0x18001ffaf  mov     [rsp+68h+var_40], 0
0x18001ffb8  mov     [rsp+68h+var_48], 0
0x18001ffc1  mov     r9d, 1
0x18001ffc7  lea     r8, aControlNetwork_6; "Control\\NetworkSetup2\\Parameters"
0x18001ffce  lea     rdx, [rsp+68h+hKey]
0x18001ffd3  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x18001ffd8  nop
0x18001ffd9  cmp     cs:byte_1800D4E9F, 0
0x18001ffe0  jz      short loc_180020016
0x18001ffe2  mov     al, cs:byte_1800D4E9E
0x18001ffe8  test    al, al
0x18001ffea  jnz     short loc_180020036
0x18001ffec  mov     qword ptr [rbx+18h], 7
0x18001fff4  mov     qword ptr [rbx+10h], 0
0x18001fffc  xor     eax, eax
0x18001fffe  mov     [rbx], ax
0x180020001  mov     rcx, [rsp+68h+hKey]; hKey
0x180020006  test    rcx, rcx
0x180020009  jz      short loc_18001FF91
0x18002000b  call    cs:__imp_RegCloseKey
0x180020011  jmp     loc_18001FF91
0x180020016  lea     rdx, aUpperrangerepl; "UpperRangeReplacementToken"
0x18002001d  lea     rcx, [rsp+68h+hKey]; this
0x180020022  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x180020027  mov     cs:byte_1800D4E9E, al
0x18002002d  mov     cs:byte_1800D4E9F, 1
0x180020034  jmp     short loc_18001FFE8
0x180020036  lea     r8, aUpperrangerepl; "UpperRangeReplacementToken"
0x18002003d  mov     rdx, rbx
0x180020040  lea     rcx, [rsp+68h+hKey]
0x180020045  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18002004a  nop
0x18002004b  lea     rcx, [rsp+68h+hKey]
0x180020050  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020055  jmp     loc_18001FF91
```
