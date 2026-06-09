# GetTestSubstituteFileName

- ea: `0x18005ab98`
- end: `0x18005ae8a`
- name: `GetTestSubstituteFileName`
- size: `754`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005b3a8`

## callees

- `0x180003180`
- `0x180009438`
- `0x18000e864`
- `0x180011fa0`
- `0x18001a930`
- `0x18005ab98`
- `0x180061960`
- `0x180061d54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ac71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ac71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ac47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ade2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ac47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ade2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005acf4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005acf4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18005ad78`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18005ad78`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ad9e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ad9e`

## string_xrefs

- `0x18005ac63`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test\Security\HashSubstitution`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetTestSubstituteFileName(const WCHAR *a1, _DWORD *a2, wchar_t **a3)
{
  unsigned int v6; // esi
  WCHAR *v7; // rdi
  wchar_t *v8; // rbx
  __int64 v9; // rdx
  const struct std::nothrow_t *v10; // rdx
  LSTATUS v11; // eax
  signed int v12; // r15d
  unsigned int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  DWORD v16; // esi
  wchar_t *v17; // rax
  int v19; // eax
  unsigned int v20; // r9d
  int phkResult; // [rsp+20h] [rbp-49h]
  int phkResulta; // [rsp+20h] [rbp-49h]
  unsigned int phkResultb; // [rsp+20h] [rbp-49h]
  int phkResultc; // [rsp+20h] [rbp-49h]
  LPWSTR lpValueName; // [rsp+60h] [rbp-9h] BYREF
  wchar_t *v26; // [rsp+68h] [rbp-1h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+70h] [rbp+7h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp+Bh] BYREF
  DWORD cValues; // [rsp+78h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v6 = 0;
  hKey = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  v7 = 0;
  lpValueName = 0;
  v8 = 0;
  v26 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v9 = 151;
LABEL_9:
    v6 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
      (const char *)0x80004003LL,
      phkResult);
    goto LABEL_28;
  }
  if ( !a2 )
  {
    v9 = 152;
    goto LABEL_9;
  }
  if ( !a3 )
  {
    v9 = 153;
    goto LABEL_9;
  }
  *a2 = 0;
  *a3 = 0;
  if ( (unsigned int)AreTestKeysAllowed((bool)a1) )
  {
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v11 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test\\Security\\HashSubstitution",
            0,
            1u,
            &hKey);
    v12 = (unsigned __int16)v11 | 0x80070000;
    if ( v11 <= 0 )
      v12 = v11;
    if ( v12 < 0 )
    {
      v6 = -2147024894;
      if ( v12 == -2147024894 )
        goto LABEL_28;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
        (const char *)(unsigned int)v12,
        phkResulta);
LABEL_27:
      v6 = v12;
      goto LABEL_28;
    }
    v13 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    if ( !v13 )
    {
      cchValueName = cbMaxValueNameLen + 1;
      v15 = WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::STArrayZeroAllocPolicy<wchar_t>>::ReleaseAndAllocArray(
              &lpValueName,
              cbMaxValueNameLen + 1);
      v6 = v15;
      v12 = 0;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB8,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
          (const char *)(unsigned int)v15,
          phkResultb);
        v7 = lpValueName;
        goto LABEL_28;
      }
      v16 = 0;
      v7 = lpValueName;
      if ( cValues )
      {
        while ( 1 )
        {
          cchValueName = cbMaxValueNameLen + 1;
          v13 = RegEnumValueW(hKey, v16, v7, &cchValueName, 0, 0, 0, 0);
          if ( v13 )
          {
            v14 = 191;
            goto LABEL_39;
          }
          if ( CompareStringW(0x7Fu, 1u, v7, -1, a1, -1) == 2 )
            break;
          if ( ++v16 >= cValues )
            goto LABEL_26;
        }
        v19 = WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::STArrayZeroAllocPolicy<wchar_t>>::ReleaseAndAllocArray(
                &v26,
                260);
        v6 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC4,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
            (const char *)(unsigned int)v19,
            phkResultc);
          v8 = v26;
          goto LABEL_28;
        }
        v8 = v26;
        RegQueryStringValueWithDefault(hKey, v7, v26, v20, a1);
        *a2 = 1;
      }
LABEL_26:
      v17 = v8;
      v8 = 0;
      *a3 = v17;
      goto LABEL_27;
    }
    v14 = 180;
LABEL_39:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v14,
           (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
           (const char *)v13,
           phkResultb);
  }
LABEL_28:
  if ( v8 )
    operator delete(v8, v10);
  if ( v7 )
    operator delete(v7, v10);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18005ab98  mov     [rsp-8+arg_18], rbx
0x18005ab9d  push    rbp
0x18005ab9e  push    rsi
0x18005ab9f  push    rdi
0x18005aba0  push    r12
0x18005aba2  push    r13
0x18005aba4  push    r14
0x18005aba6  push    r15
0x18005aba8  lea     rbp, [rsp-27h]
0x18005abad  sub     rsp, 90h
0x18005abb4  mov     rax, cs:__security_cookie
0x18005abbb  xor     rax, rsp
0x18005abbe  mov     [rbp+57h+var_38], rax
0x18005abc2  mov     r12, r8
0x18005abc5  mov     r14, rdx
0x18005abc8  mov     r13, rcx
0x18005abcb  xor     esi, esi
0x18005abcd  mov     [rbp+57h+hKey], rsi
0x18005abd1  mov     [rbp+57h+cValues], esi
0x18005abd4  mov     [rbp+57h+cbMaxValueNameLen], esi
0x18005abd7  mov     [rbp+57h+cchValueName], esi
0x18005abda  mov     edi, esi
0x18005abdc  mov     [rbp+57h+lpValueName], rsi
0x18005abe0  mov     ebx, esi
0x18005abe2  mov     [rbp+57h+var_58], rbx
0x18005abe6  test    rdx, rdx
0x18005abe9  jz      short loc_18005ABED
0x18005abeb  mov     [rdx], esi
0x18005abed  test    r13, r13
0x18005abf0  jnz     short loc_18005ABF9
0x18005abf2  mov     edx, 97h
0x18005abf7  jmp     short loc_18005AC0F
0x18005abf9  test    r14, r14
0x18005abfc  jnz     short loc_18005AC05
0x18005abfe  mov     edx, 98h
0x18005ac03  jmp     short loc_18005AC0F
0x18005ac05  test    r12, r12
0x18005ac08  jnz     short loc_18005AC2C
0x18005ac0a  mov     edx, 99h; void *
0x18005ac0f  mov     rcx, [rbp+5Fh]; this
0x18005ac13  mov     esi, 80004003h
0x18005ac18  mov     r9d, esi; char *
0x18005ac1b  lea     r8, aCW1SSrcClientL_22; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005ac22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ac27  jmp     loc_18005ADBD
0x18005ac2c  mov     [rdx], esi
0x18005ac2e  mov     [r8], rsi
0x18005ac31  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x18005ac36  test    eax, eax
0x18005ac38  jz      loc_18005ADBD
0x18005ac3e  mov     rcx, [rbp+57h+hKey]; hKey
0x18005ac42  test    rcx, rcx
0x18005ac45  jz      short loc_18005AC51
0x18005ac47  call    cs:__imp_RegCloseKey
0x18005ac4d  mov     [rbp+57h+hKey], rsi
0x18005ac51  lea     rax, [rbp+57h+hKey]
0x18005ac55  mov     [rsp+0C0h+phkResult], rax; int
0x18005ac5a  mov     r9d, 1; samDesired
0x18005ac60  xor     r8d, r8d; ulOptions
0x18005ac63  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005ac6a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005ac71  call    cs:__imp_RegOpenKeyExW
0x18005ac77  movzx   r15d, ax
0x18005ac7b  or      r15d, 80070000h
0x18005ac82  test    eax, eax
0x18005ac84  cmovle  r15d, eax
0x18005ac88  test    r15d, r15d
0x18005ac8b  jns     short loc_18005ACB8
0x18005ac8d  mov     esi, 80070002h
0x18005ac92  cmp     r15d, esi
0x18005ac95  jz      loc_18005ADBD
0x18005ac9b  mov     rcx, [rbp+5Fh]; this
0x18005ac9f  mov     r9d, r15d; char *
0x18005aca2  lea     r8, aCW1SSrcClientL_22; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005aca9  mov     edx, 0A7h; void *
0x18005acae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005acb3  jmp     loc_18005ADBA
0x18005acb8  mov     [rsp+0C0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18005acbd  mov     [rsp+0C0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18005acc2  mov     [rsp+0C0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18005acc7  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18005accb  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18005acd0  lea     rax, [rbp+57h+cValues]
0x18005acd4  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x18005acd9  mov     [rsp+0C0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18005acde  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x18005ace3  mov     [rsp+0C0h+phkResult], rsi; int
0x18005ace8  xor     r9d, r9d; lpReserved
0x18005aceb  xor     r8d, r8d; lpcchClass
0x18005acee  xor     edx, edx; lpClass
0x18005acf0  mov     rcx, [rbp+57h+hKey]; hKey
0x18005acf4  call    cs:__imp_RegQueryInfoKeyW
0x18005acfa  test    eax, eax
0x18005acfc  jz      short loc_18005AD08
0x18005acfe  mov     edx, 0B4h
0x18005ad03  jmp     loc_18005AE6F
0x18005ad08  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18005ad0b  inc     eax
0x18005ad0d  mov     [rbp+57h+cchValueName], eax
0x18005ad10  mov     edx, eax
0x18005ad12  lea     rcx, [rbp+57h+lpValueName]
0x18005ad16  call    ?ReleaseAndAllocArray@?$XPtrBaseWithArrayAllocation@_WU?$STArrayZeroAllocPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJ_K@Z; WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::STArrayZeroAllocPolicy<wchar_t>>::ReleaseAndAllocArray(unsigned __int64)
0x18005ad1b  mov     esi, eax
0x18005ad1d  xor     r15d, r15d
0x18005ad20  test    eax, eax
0x18005ad22  jns     short loc_18005AD42
0x18005ad24  mov     rcx, [rbp+5Fh]; this
0x18005ad28  mov     r9d, eax; char *
0x18005ad2b  lea     r8, aCW1SSrcClientL_22; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005ad32  mov     edx, 0B8h; void *
0x18005ad37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ad3c  mov     rdi, [rbp+57h+lpValueName]
0x18005ad40  jmp     short loc_18005ADBD
0x18005ad42  mov     esi, r15d
0x18005ad45  mov     rdi, [rbp+57h+lpValueName]
0x18005ad49  cmp     [rbp+57h+cValues], r15d
0x18005ad4d  jbe     short loc_18005ADB0
0x18005ad4f  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18005ad52  inc     eax
0x18005ad54  mov     [rbp+57h+cchValueName], eax
0x18005ad57  mov     [rsp+0C0h+lpcValues], r15; lpcbData
0x18005ad5c  mov     [rsp+0C0h+lpcbMaxClassLen], r15; lpData
0x18005ad61  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r15; lpType
0x18005ad66  mov     [rsp+0C0h+phkResult], r15; unsigned int
0x18005ad6b  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18005ad6f  mov     r8, rdi; lpValueName
0x18005ad72  mov     edx, esi; dwIndex
0x18005ad74  mov     rcx, [rbp+57h+hKey]; hKey
0x18005ad78  call    cs:__imp_RegEnumValueW
0x18005ad7e  test    eax, eax
0x18005ad80  jnz     loc_18005AE6A
0x18005ad86  or      eax, 0FFFFFFFFh
0x18005ad89  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], eax; cchCount2
0x18005ad8d  mov     [rsp+0C0h+phkResult], r13; int
0x18005ad92  mov     r9d, eax; cchCount1
0x18005ad95  mov     r8, rdi; lpString1
0x18005ad98  lea     edx, [rax+2]; dwCmpFlags
0x18005ad9b  lea     ecx, [rdx+7Eh]; Locale
0x18005ad9e  call    cs:__imp_CompareStringW
0x18005ada4  cmp     eax, 2
0x18005ada7  jz      short loc_18005AE11
0x18005ada9  inc     esi
0x18005adab  cmp     esi, [rbp+57h+cValues]
0x18005adae  jb      short loc_18005AD4F
0x18005adb0  mov     rax, rbx
0x18005adb3  mov     rbx, r15
0x18005adb6  mov     [r12], rax
0x18005adba  mov     esi, r15d
0x18005adbd  test    rbx, rbx
0x18005adc0  jz      short loc_18005ADCB
0x18005adc2  mov     rcx, rbx; void *
0x18005adc5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005adca  nop
0x18005adcb  test    rdi, rdi
0x18005adce  jz      short loc_18005ADD9
0x18005add0  mov     rcx, rdi; void *
0x18005add3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005add8  nop
0x18005add9  mov     rcx, [rbp+57h+hKey]; hKey
0x18005addd  test    rcx, rcx
0x18005ade0  jz      short loc_18005ADE8
0x18005ade2  call    cs:__imp_RegCloseKey
0x18005ade8  mov     eax, esi
0x18005adea  mov     rcx, [rbp+57h+var_38]
0x18005adee  xor     rcx, rsp; StackCookie
0x18005adf1  call    __security_check_cookie
0x18005adf6  mov     rbx, [rsp+0C0h+arg_18]
0x18005adfe  add     rsp, 90h
0x18005ae05  pop     r15
0x18005ae07  pop     r14
0x18005ae09  pop     r13
0x18005ae0b  pop     r12
0x18005ae0d  pop     rdi
0x18005ae0e  pop     rsi
0x18005ae0f  pop     rbp
0x18005ae10  retn
0x18005ae11  mov     edx, 104h
0x18005ae16  lea     rcx, [rbp+57h+var_58]
0x18005ae1a  call    ?ReleaseAndAllocArray@?$XPtrBaseWithArrayAllocation@_WU?$STArrayZeroAllocPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJ_K@Z; WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::STArrayZeroAllocPolicy<wchar_t>>::ReleaseAndAllocArray(unsigned __int64)
0x18005ae1f  mov     esi, eax
0x18005ae21  test    eax, eax
0x18005ae23  jns     short loc_18005AE46
0x18005ae25  mov     rcx, [rbp+5Fh]; this
0x18005ae29  mov     r9d, eax; char *
0x18005ae2c  lea     r8, aCW1SSrcClientL_22; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005ae33  mov     edx, 0C4h; void *
0x18005ae38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ae3d  mov     rbx, [rbp+57h+var_58]
0x18005ae41  jmp     loc_18005ADBD
0x18005ae46  mov     [rsp+0C0h+phkResult], r13; wchar_t *
0x18005ae4b  mov     rbx, [rbp+57h+var_58]
0x18005ae4f  mov     r8, rbx; wchar_t *
0x18005ae52  mov     rdx, rdi; wchar_t *
0x18005ae55  mov     rcx, [rbp+57h+hKey]; HKEY
0x18005ae59  call    ?RegQueryStringValueWithDefault@@YAXPEAUHKEY__@@PEB_WPEA_WK1@Z; RegQueryStringValueWithDefault(HKEY__ *,wchar_t const *,wchar_t *,ulong,wchar_t const *)
0x18005ae5e  mov     dword ptr [r14], 1
0x18005ae65  jmp     loc_18005ADB0
0x18005ae6a  mov     edx, 0BFh; void *
0x18005ae6f  lea     r8, aCW1SSrcClientL_22; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005ae76  mov     r9d, eax; char *
0x18005ae79  mov     rcx, [rbp+5Fh]; this
0x18005ae7d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005ae82  mov     esi, eax
0x18005ae84  jmp     loc_18005ADBD
```
