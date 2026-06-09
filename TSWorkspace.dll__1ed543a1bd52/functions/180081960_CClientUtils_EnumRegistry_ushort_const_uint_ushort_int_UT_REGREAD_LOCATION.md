# CClientUtils::EnumRegistry(ushort const *,uint,ushort *,int *,UT_REGREAD_LOCATION)

- ea: `0x180081960`
- end: `0x180081d56`
- name: `?EnumRegistry@CClientUtils@@UEAAHPEBGIPEAGPEAHW4UT_REGREAD_LOCATION@@@Z`
- size: `1014`
- prototype: `int __high(const unsigned __int16 *, unsigned int, unsigned __int16 *, int *, enum UT_REGREAD_LOCATION)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ece0`
- `0x180020bf0`
- `0x18004f09c`
- `0x180081960`
- `0x1800824b4`
- `0x180084634`
- `0x180087938`
- `0x180087b50`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180081cda`
- `ADVAPI32!RegCloseKey` at `0x180081d2d`
- `ADVAPI32!RegCloseKey` at `0x180081cda`
- `ADVAPI32!RegCloseKey` at `0x180081d2d`
- `ADVAPI32!RegEnumKeyExW` at `0x180081b5e`
- `ADVAPI32!RegEnumKeyExW` at `0x180081b5e`
- `ADVAPI32!RegOpenKeyExW` at `0x180081a64`
- `ADVAPI32!RegOpenKeyExW` at `0x180081adf`
- `ADVAPI32!RegOpenKeyExW` at `0x180081bd7`
- `ADVAPI32!RegOpenKeyExW` at `0x180081a64`
- `ADVAPI32!RegOpenKeyExW` at `0x180081adf`
- `ADVAPI32!RegOpenKeyExW` at `0x180081bd7`

## string_xrefs

- `0x180081a16`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::EnumRegistry(
        __int64 a1,
        const unsigned __int16 *a2,
        DWORD a3,
        WCHAR *a4,
        DWORD *lpcchName,
        int a6)
{
  unsigned int v8; // esi
  int AppContainerRegistryLocation; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v12; // ebx
  unsigned int v13; // eax
  char v14; // bl
  unsigned int v15; // eax
  LSTATUS v16; // ebx
  unsigned int v17; // eax
  LSTATUS v18; // ebx
  PVOID *v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // r8
  LSTATUS v24; // ebx
  unsigned int v25; // eax
  __int64 v26; // r8
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[272]; // [rsp+50h] [rbp-B0h] BYREF

  v8 = 0;
  ftLastWriteTime = 0;
  hKey = 0;
  CClientUtils::MakeSubKey(SubKey, (unsigned int)a2, a2);
  if ( a3 )
    goto LABEL_18;
  if ( !a6 )
  {
    if ( !(unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
      goto LABEL_14;
    AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
    if ( AppContainerRegistryLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Unable to get AppContainer registry location.",
          AppContainerRegistryLocation);
      }
      goto LABEL_43;
    }
    v12 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, (PHKEY)(a1 + 56));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
        v13,
        (__int64)SubKey,
        v12);
    }
    if ( v12 )
    {
LABEL_14:
      v14 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, (PHKEY)(a1 + 56));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          v15,
          (__int64)SubKey,
          v14);
      }
    }
    goto LABEL_18;
  }
  v18 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, (PHKEY)(a1 + 56));
  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
      v20,
      (__int64)SubKey,
      v18);
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v18 )
  {
LABEL_18:
    v16 = RegEnumKeyExW(*(HKEY *)(a1 + 56), a3, a4, lpcchName, 0, 0, 0, &ftLastWriteTime);
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v23, v22, v16);
      }
      v24 = RegCloseKey(*(HKEY *)(a1 + 56));
      if ( v24
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v26, v25, v24);
      }
      *(_QWORD *)(a1 + 56) = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids, v17);
      }
      v8 = 1;
    }
    goto LABEL_43;
  }
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 3u )
  {
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
      v21,
      (__int64)SubKey);
  }
LABEL_43:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x180081960  push    rbp
0x180081962  push    rbx
0x180081963  push    rsi
0x180081964  push    rdi
0x180081965  push    r12
0x180081967  push    r14
0x180081969  push    r15
0x18008196b  lea     rbp, [rsp-180h]
0x180081973  sub     rsp, 280h
0x18008197a  mov     rax, cs:__security_cookie
0x180081981  xor     rax, rsp
0x180081984  mov     [rbp+1B0h+var_40], rax
0x18008198b  mov     r12, [rbp+1B0h+lpcchName]
0x180081992  mov     r14d, r8d
0x180081995  mov     rdi, rcx
0x180081998  xor     esi, esi
0x18008199a  mov     r8, rdx; unsigned __int16 *
0x18008199d  mov     qword ptr [rsp+2B0h+ftLastWriteTime.dwLowDateTime], rsi
0x1800819a2  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x1800819a7  mov     [rsp+2B0h+hKey], rsi
0x1800819ac  mov     r15, r9
0x1800819af  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1800819b4  test    r14d, r14d
0x1800819b7  jnz     loc_180081B38
0x1800819bd  cmp     [rbp+1B0h+arg_28], esi
0x1800819c3  jnz     loc_180081BB9
0x1800819c9  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1800819ce  test    eax, eax
0x1800819d0  jz      loc_180081AC1
0x1800819d6  lea     rcx, [rsp+2B0h+hKey]; HKEY *
0x1800819db  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1800819e0  mov     ebx, eax
0x1800819e2  test    eax, eax
0x1800819e4  jns     short loc_180081A48
0x1800819e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800819ed  lea     rdx, WPP_GLOBAL_Control
0x1800819f4  cmp     rcx, rdx
0x1800819f7  jz      loc_180081D23
0x1800819fd  test    byte ptr [rcx+1Ch], 8
0x180081a01  jz      loc_180081D23
0x180081a07  cmp     byte ptr [rcx+19h], 2
0x180081a0b  jb      loc_180081D23
0x180081a11  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081a16  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x180081a1d  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x180081a21  mov     [rsp+2B0h+phkResult], rcx
0x180081a26  lea     edx, [rsi+1Bh]
0x180081a29  mov     rcx, cs:WPP_GLOBAL_Control
0x180081a30  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180081a37  mov     r9d, eax
0x180081a3a  mov     rcx, [rcx+10h]
0x180081a3e  call    WPP_SF_DsD
0x180081a43  jmp     loc_180081D23
0x180081a48  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180081a4d  lea     rax, [rdi+38h]
0x180081a51  mov     r9d, 20019h; samDesired
0x180081a57  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180081a5c  xor     r8d, r8d; ulOptions
0x180081a5f  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x180081a64  call    cs:__imp_RegOpenKeyExW
0x180081a6a  mov     ebx, eax
0x180081a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180081a73  lea     rax, WPP_GLOBAL_Control
0x180081a7a  cmp     rcx, rax
0x180081a7d  jz      short loc_180081ABD
0x180081a7f  test    byte ptr [rcx+1Ch], 1
0x180081a83  jz      short loc_180081ABD
0x180081a85  cmp     byte ptr [rcx+19h], 4
0x180081a89  jb      short loc_180081ABD
0x180081a8b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081a90  lea     rcx, [rsp+2B0h+SubKey]
0x180081a95  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x180081a99  mov     [rsp+2B0h+phkResult], rcx
0x180081a9e  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180081aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180081aac  mov     edx, 1Ch
0x180081ab1  mov     r9d, eax
0x180081ab4  mov     rcx, [rcx+10h]
0x180081ab8  call    WPP_SF_DSD
0x180081abd  test    ebx, ebx
0x180081abf  jz      short loc_180081B38
0x180081ac1  lea     rax, [rdi+38h]
0x180081ac5  mov     r9d, 20019h; samDesired
0x180081acb  xor     r8d, r8d; ulOptions
0x180081ace  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180081ad3  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x180081ad8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180081adf  call    cs:__imp_RegOpenKeyExW
0x180081ae5  mov     ebx, eax
0x180081ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x180081aee  lea     rax, WPP_GLOBAL_Control
0x180081af5  cmp     rcx, rax
0x180081af8  jz      short loc_180081B38
0x180081afa  test    byte ptr [rcx+1Ch], 1
0x180081afe  jz      short loc_180081B38
0x180081b00  cmp     byte ptr [rcx+19h], 4
0x180081b04  jb      short loc_180081B38
0x180081b06  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081b0b  lea     rcx, [rsp+2B0h+SubKey]
0x180081b10  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x180081b14  mov     [rsp+2B0h+phkResult], rcx
0x180081b19  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180081b20  mov     rcx, cs:WPP_GLOBAL_Control
0x180081b27  mov     edx, 1Dh
0x180081b2c  mov     r9d, eax
0x180081b2f  mov     rcx, [rcx+10h]
0x180081b33  call    WPP_SF_DSD
0x180081b38  mov     rcx, [rdi+38h]; hKey
0x180081b3c  lea     rax, [rsp+2B0h+ftLastWriteTime]
0x180081b41  mov     [rsp+2B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180081b46  mov     r9, r12; lpcchName
0x180081b49  mov     [rsp+2B0h+lpcchClass], rsi; lpcchClass
0x180081b4e  mov     r8, r15; lpName
0x180081b51  mov     [rsp+2B0h+lpClass], rsi; lpClass
0x180081b56  mov     edx, r14d; dwIndex
0x180081b59  mov     [rsp+2B0h+phkResult], rsi; lpReserved
0x180081b5e  call    cs:__imp_RegEnumKeyExW
0x180081b64  mov     ebx, eax
0x180081b66  test    eax, eax
0x180081b68  jnz     loc_180081C96
0x180081b6e  mov     rax, cs:WPP_GLOBAL_Control
0x180081b75  lea     rdx, WPP_GLOBAL_Control
0x180081b7c  cmp     rax, rdx
0x180081b7f  jz      short loc_180081BAF
0x180081b81  test    byte ptr [rax+1Ch], 1
0x180081b85  jz      short loc_180081BAF
0x180081b87  cmp     byte ptr [rax+19h], 4
0x180081b8b  jb      short loc_180081BAF
0x180081b8d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081b92  mov     rcx, cs:WPP_GLOBAL_Control
0x180081b99  lea     edx, [rbx+20h]
0x180081b9c  mov     r9d, eax
0x180081b9f  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180081ba6  mov     rcx, [rcx+10h]
0x180081baa  call    WPP_SF_D
0x180081baf  mov     esi, 1
0x180081bb4  jmp     loc_180081D23
0x180081bb9  lea     rax, [rdi+38h]
0x180081bbd  mov     r9d, 20019h; samDesired
0x180081bc3  xor     r8d, r8d; ulOptions
0x180081bc6  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180081bcb  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x180081bd0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081bd7  call    cs:__imp_RegOpenKeyExW
0x180081bdd  mov     ebx, eax
0x180081bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180081be6  lea     rax, WPP_GLOBAL_Control
0x180081bed  cmp     rcx, rax
0x180081bf0  jz      short loc_180081C3E
0x180081bf2  test    byte ptr [rcx+1Ch], 1
0x180081bf6  jz      short loc_180081C3E
0x180081bf8  cmp     byte ptr [rcx+19h], 4
0x180081bfc  jb      short loc_180081C3E
0x180081bfe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081c03  lea     rcx, [rsp+2B0h+SubKey]
0x180081c08  mov     dword ptr [rsp+2B0h+lpClass], ebx
0x180081c0c  mov     [rsp+2B0h+phkResult], rcx
0x180081c11  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180081c18  mov     rcx, cs:WPP_GLOBAL_Control
0x180081c1f  mov     edx, 1Eh
0x180081c24  mov     r9d, eax
0x180081c27  mov     rcx, [rcx+10h]
0x180081c2b  call    WPP_SF_DSD
0x180081c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180081c37  lea     rax, WPP_GLOBAL_Control
0x180081c3e  test    ebx, ebx
0x180081c40  jz      loc_180081B38
0x180081c46  cmp     rcx, rax
0x180081c49  jz      loc_180081D23
0x180081c4f  test    byte ptr [rcx+1Ch], 1
0x180081c53  jz      loc_180081D23
0x180081c59  cmp     byte ptr [rcx+19h], 3
0x180081c5d  jb      loc_180081D23
0x180081c63  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081c68  lea     rcx, [rsp+2B0h+SubKey]
0x180081c6d  mov     edx, 1Fh
0x180081c72  mov     [rsp+2B0h+phkResult], rcx
0x180081c77  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180081c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180081c85  mov     r9d, eax
0x180081c88  mov     rcx, [rcx+10h]
0x180081c8c  call    WPP_SF_DS
0x180081c91  jmp     loc_180081D23
0x180081c96  mov     rax, cs:WPP_GLOBAL_Control
0x180081c9d  lea     r14, WPP_GLOBAL_Control
0x180081ca4  cmp     rax, r14
0x180081ca7  jz      short loc_180081CD6
0x180081ca9  test    byte ptr [rax+1Ch], 1
0x180081cad  jz      short loc_180081CD6
0x180081caf  cmp     byte ptr [rax+19h], 4
0x180081cb3  jb      short loc_180081CD6
0x180081cb5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180081cc1  mov     edx, 21h ; '!'
0x180081cc6  mov     r9d, eax
0x180081cc9  mov     dword ptr [rsp+2B0h+phkResult], ebx
0x180081ccd  mov     rcx, [rcx+10h]
0x180081cd1  call    WPP_SF_Dl
0x180081cd6  mov     rcx, [rdi+38h]; hKey
0x180081cda  call    cs:__imp_RegCloseKey
0x180081ce0  mov     ebx, eax
0x180081ce2  test    eax, eax
0x180081ce4  jz      short loc_180081D1F
0x180081ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x180081ced  cmp     rcx, r14
0x180081cf0  jz      short loc_180081D1F
0x180081cf2  test    byte ptr [rcx+1Ch], 1
0x180081cf6  jz      short loc_180081D1F
0x180081cf8  cmp     byte ptr [rcx+19h], 2
0x180081cfc  jb      short loc_180081D1F
0x180081cfe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081d03  mov     rcx, cs:WPP_GLOBAL_Control
0x180081d0a  mov     edx, 22h ; '"'
0x180081d0f  mov     r9d, eax
0x180081d12  mov     dword ptr [rsp+2B0h+phkResult], ebx
0x180081d16  mov     rcx, [rcx+10h]
0x180081d1a  call    WPP_SF_Dl
0x180081d1f  mov     [rdi+38h], rsi
0x180081d23  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180081d28  test    rcx, rcx
0x180081d2b  jz      short loc_180081D33
0x180081d2d  call    cs:__imp_RegCloseKey
0x180081d33  mov     eax, esi
0x180081d35  mov     rcx, [rbp+1B0h+var_40]
0x180081d3c  xor     rcx, rsp; StackCookie
0x180081d3f  call    __security_check_cookie
0x180081d44  add     rsp, 280h
0x180081d4b  pop     r15
0x180081d4d  pop     r14
0x180081d4f  pop     r12
0x180081d51  pop     rdi
0x180081d52  pop     rsi
0x180081d53  pop     rbx
0x180081d54  pop     rbp
0x180081d55  retn
```
