# GetTestSubstituteFileName

- ea: `0x14003afa8`
- end: `0x14003b29a`
- name: `GetTestSubstituteFileName`
- size: `754`
- prototype: `__int64 __fastcall(const WCHAR *, _DWORD *, wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14003b7b8`

## callees

- `0x140003de4`
- `0x140008de4`
- `0x14000e074`
- `0x14000e4d0`
- `0x1400179f4`
- `0x14003afa8`
- `0x140045dc0`
- `0x140045de4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14003b1ae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14003b1ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003b057`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003b1f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003b057`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003b1f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003b081`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003b081`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14003b188`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14003b188`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003b104`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003b104`

## string_xrefs

- `0x14003b073`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test\Security\HashSubstitution`

## pseudocode

```c
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
  int phkResultb; // [rsp+20h] [rbp-49h]
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
  if ( (unsigned int)AreTestKeysAllowed() )
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
0x14003afa8  mov     [rsp-8+arg_18], rbx
0x14003afad  push    rbp
0x14003afae  push    rsi
0x14003afaf  push    rdi
0x14003afb0  push    r12
0x14003afb2  push    r13
0x14003afb4  push    r14
0x14003afb6  push    r15
0x14003afb8  lea     rbp, [rsp-27h]
0x14003afbd  sub     rsp, 90h
0x14003afc4  mov     rax, cs:__security_cookie
0x14003afcb  xor     rax, rsp
0x14003afce  mov     [rbp+57h+var_38], rax
0x14003afd2  mov     r12, r8
0x14003afd5  mov     r14, rdx
0x14003afd8  mov     r13, rcx
0x14003afdb  xor     esi, esi
0x14003afdd  mov     [rbp+57h+hKey], rsi
0x14003afe1  mov     [rbp+57h+cValues], esi
0x14003afe4  mov     [rbp+57h+cbMaxValueNameLen], esi
0x14003afe7  mov     [rbp+57h+cchValueName], esi
0x14003afea  mov     edi, esi
0x14003afec  mov     [rbp+57h+lpValueName], rsi
0x14003aff0  mov     ebx, esi
0x14003aff2  mov     [rbp+57h+var_58], rbx
0x14003aff6  test    rdx, rdx
0x14003aff9  jz      short loc_14003AFFD
0x14003affb  mov     [rdx], esi
0x14003affd  test    r13, r13
0x14003b000  jnz     short loc_14003B009
0x14003b002  mov     edx, 97h
0x14003b007  jmp     short loc_14003B01F
0x14003b009  test    r14, r14
0x14003b00c  jnz     short loc_14003B015
0x14003b00e  mov     edx, 98h
0x14003b013  jmp     short loc_14003B01F
0x14003b015  test    r12, r12
0x14003b018  jnz     short loc_14003B03C
0x14003b01a  mov     edx, 99h; void *
0x14003b01f  mov     rcx, [rbp+5Fh]; this
0x14003b023  mov     esi, 80004003h
0x14003b028  mov     r9d, esi; char *
0x14003b02b  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003b032  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b037  jmp     loc_14003B1CD
0x14003b03c  mov     [rdx], esi
0x14003b03e  mov     [r8], rsi
0x14003b041  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x14003b046  test    eax, eax
0x14003b048  jz      loc_14003B1CD
0x14003b04e  mov     rcx, [rbp+57h+hKey]; hKey
0x14003b052  test    rcx, rcx
0x14003b055  jz      short loc_14003B061
0x14003b057  call    cs:__imp_RegCloseKey
0x14003b05d  mov     [rbp+57h+hKey], rsi
0x14003b061  lea     rax, [rbp+57h+hKey]
0x14003b065  mov     [rsp+0C0h+phkResult], rax; int
0x14003b06a  mov     r9d, 1; samDesired
0x14003b070  xor     r8d, r8d; ulOptions
0x14003b073  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14003b07a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003b081  call    cs:__imp_RegOpenKeyExW
0x14003b087  movzx   r15d, ax
0x14003b08b  or      r15d, 80070000h
0x14003b092  test    eax, eax
0x14003b094  cmovle  r15d, eax
0x14003b098  test    r15d, r15d
0x14003b09b  jns     short loc_14003B0C8
0x14003b09d  mov     esi, 80070002h
0x14003b0a2  cmp     r15d, esi
0x14003b0a5  jz      loc_14003B1CD
0x14003b0ab  mov     rcx, [rbp+5Fh]; this
0x14003b0af  mov     r9d, r15d; char *
0x14003b0b2  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003b0b9  mov     edx, 0A7h; void *
0x14003b0be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b0c3  jmp     loc_14003B1CA
0x14003b0c8  mov     [rsp+0C0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x14003b0cd  mov     [rsp+0C0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x14003b0d2  mov     [rsp+0C0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x14003b0d7  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x14003b0db  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x14003b0e0  lea     rax, [rbp+57h+cValues]
0x14003b0e4  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x14003b0e9  mov     [rsp+0C0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x14003b0ee  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x14003b0f3  mov     [rsp+0C0h+phkResult], rsi; int
0x14003b0f8  xor     r9d, r9d; lpReserved
0x14003b0fb  xor     r8d, r8d; lpcchClass
0x14003b0fe  xor     edx, edx; lpClass
0x14003b100  mov     rcx, [rbp+57h+hKey]; hKey
0x14003b104  call    cs:__imp_RegQueryInfoKeyW
0x14003b10a  test    eax, eax
0x14003b10c  jz      short loc_14003B118
0x14003b10e  mov     edx, 0B4h
0x14003b113  jmp     loc_14003B27F
0x14003b118  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x14003b11b  inc     eax
0x14003b11d  mov     [rbp+57h+cchValueName], eax
0x14003b120  mov     edx, eax
0x14003b122  lea     rcx, [rbp+57h+lpValueName]
0x14003b126  call    ?ReleaseAndAllocArray@?$XPtrBaseWithArrayAllocation@_WU?$STArrayZeroAllocPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJ_K@Z; WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::STArrayZeroAllocPolicy<wchar_t>>::ReleaseAndAllocArray(unsigned __int64)
0x14003b12b  mov     esi, eax
0x14003b12d  xor     r15d, r15d
0x14003b130  test    eax, eax
0x14003b132  jns     short loc_14003B152
0x14003b134  mov     rcx, [rbp+5Fh]; this
0x14003b138  mov     r9d, eax; char *
0x14003b13b  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003b142  mov     edx, 0B8h; void *
0x14003b147  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b14c  mov     rdi, [rbp+57h+lpValueName]
0x14003b150  jmp     short loc_14003B1CD
0x14003b152  mov     esi, r15d
0x14003b155  mov     rdi, [rbp+57h+lpValueName]
0x14003b159  cmp     [rbp+57h+cValues], r15d
0x14003b15d  jbe     short loc_14003B1C0
0x14003b15f  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x14003b162  inc     eax
0x14003b164  mov     [rbp+57h+cchValueName], eax
0x14003b167  mov     [rsp+0C0h+lpcValues], r15; lpcbData
0x14003b16c  mov     [rsp+0C0h+lpcbMaxClassLen], r15; lpData
0x14003b171  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r15; lpType
0x14003b176  mov     [rsp+0C0h+phkResult], r15; unsigned int
0x14003b17b  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x14003b17f  mov     r8, rdi; lpValueName
0x14003b182  mov     edx, esi; dwIndex
0x14003b184  mov     rcx, [rbp+57h+hKey]; hKey
0x14003b188  call    cs:__imp_RegEnumValueW
0x14003b18e  test    eax, eax
0x14003b190  jnz     loc_14003B27A
0x14003b196  or      eax, 0FFFFFFFFh
0x14003b199  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], eax; cchCount2
0x14003b19d  mov     [rsp+0C0h+phkResult], r13; int
0x14003b1a2  mov     r9d, eax; cchCount1
0x14003b1a5  mov     r8, rdi; lpString1
0x14003b1a8  lea     edx, [rax+2]; dwCmpFlags
0x14003b1ab  lea     ecx, [rdx+7Eh]; Locale
0x14003b1ae  call    cs:__imp_CompareStringW
0x14003b1b4  cmp     eax, 2
0x14003b1b7  jz      short loc_14003B221
0x14003b1b9  inc     esi
0x14003b1bb  cmp     esi, [rbp+57h+cValues]
0x14003b1be  jb      short loc_14003B15F
0x14003b1c0  mov     rax, rbx
0x14003b1c3  mov     rbx, r15
0x14003b1c6  mov     [r12], rax
0x14003b1ca  mov     esi, r15d
0x14003b1cd  test    rbx, rbx
0x14003b1d0  jz      short loc_14003B1DB
0x14003b1d2  mov     rcx, rbx; void *
0x14003b1d5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003b1da  nop
0x14003b1db  test    rdi, rdi
0x14003b1de  jz      short loc_14003B1E9
0x14003b1e0  mov     rcx, rdi; void *
0x14003b1e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003b1e8  nop
0x14003b1e9  mov     rcx, [rbp+57h+hKey]; hKey
0x14003b1ed  test    rcx, rcx
0x14003b1f0  jz      short loc_14003B1F8
0x14003b1f2  call    cs:__imp_RegCloseKey
0x14003b1f8  mov     eax, esi
0x14003b1fa  mov     rcx, [rbp+57h+var_38]
0x14003b1fe  xor     rcx, rsp; StackCookie
0x14003b201  call    __security_check_cookie
0x14003b206  mov     rbx, [rsp+0C0h+arg_18]
0x14003b20e  add     rsp, 90h
0x14003b215  pop     r15
0x14003b217  pop     r14
0x14003b219  pop     r13
0x14003b21b  pop     r12
0x14003b21d  pop     rdi
0x14003b21e  pop     rsi
0x14003b21f  pop     rbp
0x14003b220  retn
0x14003b221  mov     edx, 104h
0x14003b226  lea     rcx, [rbp+57h+var_58]
0x14003b22a  call    ?ReleaseAndAllocArray@?$XPtrBaseWithArrayAllocation@_WU?$STArrayZeroAllocPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJ_K@Z; WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::STArrayZeroAllocPolicy<wchar_t>>::ReleaseAndAllocArray(unsigned __int64)
0x14003b22f  mov     esi, eax
0x14003b231  test    eax, eax
0x14003b233  jns     short loc_14003B256
0x14003b235  mov     rcx, [rbp+5Fh]; this
0x14003b239  mov     r9d, eax; char *
0x14003b23c  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003b243  mov     edx, 0C4h; void *
0x14003b248  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b24d  mov     rbx, [rbp+57h+var_58]
0x14003b251  jmp     loc_14003B1CD
0x14003b256  mov     [rsp+0C0h+phkResult], r13; wchar_t *
0x14003b25b  mov     rbx, [rbp+57h+var_58]
0x14003b25f  mov     r8, rbx; wchar_t *
0x14003b262  mov     rdx, rdi; wchar_t *
0x14003b265  mov     rcx, [rbp+57h+hKey]; HKEY
0x14003b269  call    ?RegQueryStringValueWithDefault@@YAXPEAUHKEY__@@PEB_WPEA_WK1@Z; RegQueryStringValueWithDefault(HKEY__ *,wchar_t const *,wchar_t *,ulong,wchar_t const *)
0x14003b26e  mov     dword ptr [r14], 1
0x14003b275  jmp     loc_14003B1C0
0x14003b27a  mov     edx, 0BFh; void *
0x14003b27f  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003b286  mov     r9d, eax; char *
0x14003b289  mov     rcx, [rbp+5Fh]; this
0x14003b28d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14003b292  mov     esi, eax
0x14003b294  jmp     loc_14003B1CD
```
