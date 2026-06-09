# WillEulaPageBeShown(void)

- ea: `0x18000ccf8`
- end: `0x18000cddf`
- name: `?WillEulaPageBeShown@@YA_NXZ`
- size: `231`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e654`

## callees

- `0x18000ccf8`
- `0x18001b1a0`
- `0x180034a30`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cd5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cd9d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cd5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cd9d`

## string_xrefs

- `0x18000cdcd`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
bool WillEulaPageBeShown(void)
{
  int v0; // ebx
  LSTATUS ValueW; // eax
  unsigned __int64 v2; // r9
  bool v3; // zf
  int pdwType; // [rsp+20h] [rbp-40h]
  int pvData; // [rsp+40h] [rbp-20h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD v8; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v0 = 0;
  pcbData = 4;
  pvData = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::GetImpl'::`2'::impl) )
  {
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
               L"SetupDisplayedEula",
               0x10u,
               0,
               &pvData,
               &pcbData);
    v2 = (unsigned __int16)ValueW | 0x80070000;
    if ( ValueW <= 0 )
      v2 = (unsigned int)ValueW;
    if ( (v2 & 0x80000000) == 0LL )
    {
      v0 = pvData;
    }
    else if ( (unsigned int)(v2 + 2147024894) > 1 )
    {
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1C96,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)v2,
        pdwType);
    }
    v3 = v0 == 1;
  }
  else
  {
    v8 = 0;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
           L"SetupDisplayedEula",
           0x10u,
           &v8,
           &pvData,
           &pcbData) )
    {
      return 1;
    }
    v3 = pvData == 1;
  }
  return !v3;
}

```

## disassembly

```asm
0x18000ccf8  mov     [rsp-8+arg_0], rbx
0x18000ccfd  push    rbp
0x18000ccfe  mov     rbp, rsp
0x18000cd01  sub     rsp, 60h
0x18000cd05  mov     rax, cs:__security_cookie
0x18000cd0c  xor     rax, rsp
0x18000cd0f  mov     [rbp+var_10], rax
0x18000cd13  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::GetImpl(void)'::`2'::impl
0x18000cd1a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::__private_IsEnabled(void)
0x18000cd1f  xor     ebx, ebx
0x18000cd21  mov     [rbp+var_1C], 4
0x18000cd28  test    al, al
0x18000cd2a  mov     [rbp+var_20], ebx
0x18000cd2d  lea     rax, [rbp+var_1C]
0x18000cd31  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000cd38  mov     [rsp+60h+pcbData], rax; pcbData
0x18000cd3d  lea     r8, Value; "SetupDisplayedEula"
0x18000cd44  lea     rax, [rbp+var_20]
0x18000cd48  mov     [rsp+60h+pvData], rax; pvData
0x18000cd4d  lea     r9d, [rbx+10h]; dwFlags
0x18000cd51  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000cd58  jz      short loc_18000CD91
0x18000cd5a  mov     [rsp+60h+pdwType], rbx; int
0x18000cd5f  call    cs:__imp_RegGetValueW
0x18000cd65  movzx   r9d, ax
0x18000cd69  or      r9d, 80070000h
0x18000cd70  test    eax, eax
0x18000cd72  cmovle  r9d, eax; char *
0x18000cd76  test    r9d, r9d
0x18000cd79  jns     short loc_18000CD89
0x18000cd7b  lea     eax, [r9+7FF8FFFEh]
0x18000cd82  cmp     eax, 1
0x18000cd85  ja      short loc_18000CDC9
0x18000cd87  jmp     short loc_18000CD8C
0x18000cd89  mov     ebx, [rbp+var_20]
0x18000cd8c  cmp     ebx, 1
0x18000cd8f  jmp     short loc_18000CDAF
0x18000cd91  lea     rax, [rbp+var_18]
0x18000cd95  mov     [rbp+var_18], ebx
0x18000cd98  mov     [rsp+60h+pdwType], rax; pdwType
0x18000cd9d  call    cs:__imp_RegGetValueW
0x18000cda3  test    eax, eax
0x18000cda5  jz      short loc_18000CDAB
0x18000cda7  mov     al, 1
0x18000cda9  jmp     short loc_18000CDB2
0x18000cdab  cmp     [rbp+var_20], 1
0x18000cdaf  setnz   al
0x18000cdb2  mov     rcx, [rbp+var_10]
0x18000cdb6  xor     rcx, rsp; StackCookie
0x18000cdb9  call    __security_check_cookie
0x18000cdbe  mov     rbx, [rsp+60h+arg_0]
0x18000cdc3  add     rsp, 60h
0x18000cdc7  pop     rbp
0x18000cdc8  retn
0x18000cdc9  mov     rcx, [rbp+8]; this
0x18000cdcd  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000cdd4  mov     edx, 1C96h; void *
0x18000cdd9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
