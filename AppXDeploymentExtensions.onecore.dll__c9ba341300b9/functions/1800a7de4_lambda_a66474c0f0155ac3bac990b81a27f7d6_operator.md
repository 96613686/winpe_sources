# _lambda_a66474c0f0155ac3bac990b81a27f7d6_::operator()

- ea: `0x1800a7de4`
- end: `0x1800a813e`
- name: `_lambda_a66474c0f0155ac3bac990b81a27f7d6_::operator()`
- size: `858`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801f7c60`

## callees

- `0x1800a7de4`
- `0x1800a8f80`
- `0x1800a8fc8`
- `0x1800f0260`
- `0x1801f6ec0`
- `0x1801f7124`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a7f72`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a7f9c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a7f72`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a7f9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7ea4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7f09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8005`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a808e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a80a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a80dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7ea4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7f09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8005`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a808e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a80a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a80dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7e46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7e46`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a7f46`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a7f46`

## string_xrefs

- `0x1800a7e73`: `Path %ls`
- `0x1800a7ed9`: `Path %ls`
- `0x1800a8060`: `Path %ls`
- `0x1800a8119`: `Path %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_a66474c0f0155ac3bac990b81a27f7d6_::operator()(__int64 a1)
{
  unsigned int v2; // eax
  StateCreation *v3; // rcx
  unsigned int v4; // ebx
  int v6; // eax
  unsigned int v7; // edi
  DWORD v8; // esi
  DWORD i; // edx
  unsigned int v10; // eax
  int v11; // eax
  LPDWORD lpcchClass; // [rsp+30h] [rbp-D0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( **(_BYTE **)a1 )
  {
    hKey = 0;
    v2 = RegOpenKeyExW(
           *(HKEY *)(*(_QWORD *)(a1 + 8) + 264LL),
           *(LPCWSTR *)(*(_QWORD *)(a1 + 8) + 280LL),
           0,
           0xF003Fu,
           &hKey);
    v3 = (StateCreation *)(v2 - 2);
    if ( (unsigned int)v3 <= 1 )
    {
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(hKey);
    }
    else
    {
      if ( v2 )
      {
        v4 = wil::details::in1diag3::Return_Win32Msg(
               retaddr,
               (void *)0xC5E,
               (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
               (const char *)v2,
               (unsigned int)"Path %ls",
               *(const char **)(*(_QWORD *)(a1 + 8) + 280LL));
        if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          RegCloseKey(hKey);
        return v4;
      }
      v6 = StateCreation::RemoveRegistryValuesFromKey(v3, hKey);
      v7 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xC61,
          (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
          (const char *)(unsigned int)v6,
          (int)"Path %ls",
          *(const char **)(*(_QWORD *)(a1 + 8) + 280LL));
        if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          RegCloseKey(hKey);
        return v7;
      }
      v8 = 0;
      for ( i = 0; ; i = v8 )
      {
        cchName = 260;
        v10 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        if ( v10 )
          break;
        if ( CompareStringOrdinal(Name, -1, L"Schemas", -1, 1) == 2
          || CompareStringOrdinal(Name, -1, L"AcquisitionInfo", -1, 1) == 2 )
        {
          ++v8;
        }
        else
        {
          v7 = StateCreation::RemoveRegistryKey(*(StateCreation **)(a1 + 8), hKey, Name);
          if ( (v7 & 0x80000000) != 0 )
          {
            LODWORD(lpcchClass) = v8;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0xC6B,
              (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
              (const char *)v7,
              (int)"Key %ls index %u",
              (const char *)Name,
              lpcchClass);
            if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
              RegCloseKey(hKey);
            return v7;
          }
        }
      }
      if ( ((v10 - 3) & 0xFFFFFEFF) != 0 )
      {
        v4 = wil::details::in1diag3::Return_Win32Msg(
               retaddr,
               (void *)0xC79,
               (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
               (const char *)v10,
               (unsigned int)"Path %ls",
               *(const char **)(*(_QWORD *)(a1 + 8) + 280LL));
        if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          RegCloseKey(hKey);
        return v4;
      }
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(hKey);
    }
  }
  else
  {
    v11 = StateCreation::RemoveRegistryKey(
            *(StateCreation **)(a1 + 8),
            *(HKEY *)(*(_QWORD *)(a1 + 8) + 264LL),
            *(const unsigned __int16 **)(*(_QWORD *)(a1 + 8) + 280LL));
    v7 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xC7F,
        (unsigned int)"onecore\\admin\\appmodel\\statecreation\\lib\\statecreation.cpp",
        (const char *)(unsigned int)v11,
        (int)"Path %ls",
        *(const char **)(*(_QWORD *)(a1 + 8) + 280LL));
      return v7;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800a7de4  push    rbp
0x1800a7de6  push    rbx
0x1800a7de7  push    rsi
0x1800a7de8  push    rdi
0x1800a7de9  lea     rbp, [rsp-178h]
0x1800a7df1  sub     rsp, 278h
0x1800a7df8  mov     rax, cs:__security_cookie
0x1800a7dff  xor     rax, rsp
0x1800a7e02  mov     [rbp+190h+var_30], rax
0x1800a7e09  mov     rbx, rcx
0x1800a7e0c  mov     rax, [rcx]
0x1800a7e0f  cmp     byte ptr [rax], 0
0x1800a7e12  jz      loc_1800A80E5
0x1800a7e18  mov     [rsp+290h+hKey], 0
0x1800a7e21  mov     rcx, [rcx+8]
0x1800a7e25  lea     rax, [rsp+290h+hKey]
0x1800a7e2a  mov     [rsp+290h+phkResult], rax; phkResult
0x1800a7e2f  mov     r9d, 0F003Fh; samDesired
0x1800a7e35  xor     r8d, r8d; ulOptions
0x1800a7e38  mov     rdx, [rcx+118h]; lpSubKey
0x1800a7e3f  mov     rcx, [rcx+108h]; hKey
0x1800a7e46  call    cs:__imp_RegOpenKeyExW
0x1800a7e4c  lea     ecx, [rax-2]; this
0x1800a7e4f  cmp     ecx, 1
0x1800a7e52  jbe     loc_1800A80CD
0x1800a7e58  test    eax, eax
0x1800a7e5a  jz      short loc_1800A7EB2
0x1800a7e5c  mov     rdx, [rbx+8]
0x1800a7e60  mov     rcx, [rbp+198h]; this
0x1800a7e67  mov     rdx, [rdx+118h]
0x1800a7e6e  mov     [rsp+290h+lpClass], rdx; char *
0x1800a7e73  lea     rdx, aPathLs; "Path %ls"
0x1800a7e7a  mov     [rsp+290h+phkResult], rdx; unsigned int
0x1800a7e7f  mov     r9d, eax; char *
0x1800a7e82  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1800a7e89  mov     edx, 0C5Eh; void *
0x1800a7e8e  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800a7e93  mov     ebx, eax
0x1800a7e95  mov     rcx, [rsp+290h+hKey]; hKey
0x1800a7e9a  lea     rdx, [rcx-1]
0x1800a7e9e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800a7ea2  ja      short loc_1800A7EAB
0x1800a7ea4  call    cs:__imp_RegCloseKey
0x1800a7eaa  nop
0x1800a7eab  mov     eax, ebx
0x1800a7ead  jmp     loc_1800A80B2
0x1800a7eb2  mov     rdx, [rsp+290h+hKey]; HKEY
0x1800a7eb7  call    ?RemoveRegistryValuesFromKey@StateCreation@@AEAAJPEAUHKEY__@@@Z; StateCreation::RemoveRegistryValuesFromKey(HKEY__ *)
0x1800a7ebc  mov     edi, eax
0x1800a7ebe  test    eax, eax
0x1800a7ec0  jns     short loc_1800A7F17
0x1800a7ec2  mov     rdx, [rbx+8]
0x1800a7ec6  mov     rcx, [rbp+198h]; this
0x1800a7ecd  mov     rdx, [rdx+118h]
0x1800a7ed4  mov     [rsp+290h+lpClass], rdx; char *
0x1800a7ed9  lea     rdx, aPathLs; "Path %ls"
0x1800a7ee0  mov     [rsp+290h+phkResult], rdx; int
0x1800a7ee5  mov     r9d, eax; char *
0x1800a7ee8  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1800a7eef  mov     edx, 0C61h; void *
0x1800a7ef4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a7ef9  nop
0x1800a7efa  mov     rcx, [rsp+290h+hKey]; hKey
0x1800a7eff  lea     rax, [rcx-1]
0x1800a7f03  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a7f07  ja      short loc_1800A7F10
0x1800a7f09  call    cs:__imp_RegCloseKey
0x1800a7f0f  nop
0x1800a7f10  mov     eax, edi
0x1800a7f12  jmp     loc_1800A80B2
0x1800a7f17  xor     esi, esi
0x1800a7f19  mov     [rsp+290h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800a7f1e  mov     [rsp+290h+lpcchClass], rsi; lpcchClass
0x1800a7f23  mov     [rsp+290h+lpClass], rsi; lpClass
0x1800a7f28  mov     [rsp+290h+phkResult], rsi; lpReserved
0x1800a7f2d  xor     edx, edx; dwIndex
0x1800a7f2f  mov     [rsp+290h+cchName], 104h
0x1800a7f37  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800a7f3c  lea     r8, [rsp+290h+Name]; lpName
0x1800a7f41  mov     rcx, [rsp+290h+hKey]; hKey
0x1800a7f46  call    cs:__imp_RegEnumKeyExW
0x1800a7f4c  mov     r9d, eax; char *
0x1800a7f4f  test    eax, eax
0x1800a7f51  jnz     loc_1800A803E
0x1800a7f57  mov     dword ptr [rsp+290h+phkResult], 1; bIgnoreCase
0x1800a7f5f  or      r9d, 0FFFFFFFFh; cchCount2
0x1800a7f63  lea     r8, aSchemas; "Schemas"
0x1800a7f6a  or      edx, r9d; cchCount1
0x1800a7f6d  lea     rcx, [rsp+290h+Name]; lpString1
0x1800a7f72  call    cs:__imp_CompareStringOrdinal
0x1800a7f78  cmp     eax, 2
0x1800a7f7b  jz      loc_1800A8011
0x1800a7f81  mov     dword ptr [rsp+290h+phkResult], 1; bIgnoreCase
0x1800a7f89  or      r9d, 0FFFFFFFFh; cchCount2
0x1800a7f8d  lea     r8, aAcquisitioninf; "AcquisitionInfo"
0x1800a7f94  or      edx, r9d; cchCount1
0x1800a7f97  lea     rcx, [rsp+290h+Name]; lpString1
0x1800a7f9c  call    cs:__imp_CompareStringOrdinal
0x1800a7fa2  cmp     eax, 2
0x1800a7fa5  jz      short loc_1800A8011
0x1800a7fa7  lea     r8, [rsp+290h+Name]; unsigned __int16 *
0x1800a7fac  mov     rdx, [rsp+290h+hKey]; HKEY
0x1800a7fb1  mov     rcx, [rbx+8]; this
0x1800a7fb5  call    ?RemoveRegistryKey@StateCreation@@AEAAJPEAUHKEY__@@PEBG@Z; StateCreation::RemoveRegistryKey(HKEY__ *,ushort const *)
0x1800a7fba  mov     edi, eax
0x1800a7fbc  test    eax, eax
0x1800a7fbe  jns     short loc_1800A8013
0x1800a7fc0  mov     rcx, [rbp+198h]; this
0x1800a7fc7  mov     dword ptr [rsp+290h+lpcchClass], esi
0x1800a7fcb  lea     rax, [rsp+290h+Name]
0x1800a7fd0  mov     [rsp+290h+lpClass], rax; char *
0x1800a7fd5  lea     rax, aKeyLsIndexU; "Key %ls index %u"
0x1800a7fdc  mov     [rsp+290h+phkResult], rax; int
0x1800a7fe1  mov     r9d, edi; char *
0x1800a7fe4  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1800a7feb  mov     edx, 0C6Bh; void *
0x1800a7ff0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a7ff5  nop
0x1800a7ff6  mov     rcx, [rsp+290h+hKey]; hKey
0x1800a7ffb  lea     rax, [rcx-1]
0x1800a7fff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a8003  ja      short loc_1800A800C
0x1800a8005  call    cs:__imp_RegCloseKey
0x1800a800b  nop
0x1800a800c  jmp     loc_1800A7F10
0x1800a8011  inc     esi
0x1800a8013  mov     [rsp+290h+lpftLastWriteTime], 0
0x1800a801c  mov     [rsp+290h+lpcchClass], 0
0x1800a8025  mov     [rsp+290h+lpClass], 0
0x1800a802e  mov     [rsp+290h+phkResult], 0
0x1800a8037  mov     edx, esi
0x1800a8039  jmp     loc_1800A7F2F
0x1800a803e  lea     eax, [r9-3]
0x1800a8042  test    eax, 0FFFFFEFFh
0x1800a8047  jz      short loc_1800A809A
0x1800a8049  mov     rax, [rbx+8]
0x1800a804d  mov     rcx, [rbp+198h]; this
0x1800a8054  mov     rax, [rax+118h]
0x1800a805b  mov     [rsp+290h+lpClass], rax; char *
0x1800a8060  lea     rdx, aPathLs; "Path %ls"
0x1800a8067  mov     [rsp+290h+phkResult], rdx; unsigned int
0x1800a806c  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1800a8073  mov     edx, 0C79h; void *
0x1800a8078  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800a807d  mov     ebx, eax
0x1800a807f  mov     rcx, [rsp+290h+hKey]; hKey
0x1800a8084  lea     rdx, [rcx-1]
0x1800a8088  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800a808c  ja      short loc_1800A8095
0x1800a808e  call    cs:__imp_RegCloseKey
0x1800a8094  nop
0x1800a8095  jmp     loc_1800A7EAB
0x1800a809a  mov     rcx, [rsp+290h+hKey]; hKey
0x1800a809f  lea     rax, [rcx-1]
0x1800a80a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a80a7  ja      short loc_1800A80B0
0x1800a80a9  call    cs:__imp_RegCloseKey
0x1800a80af  nop
0x1800a80b0  xor     eax, eax
0x1800a80b2  mov     rcx, [rbp+190h+var_30]
0x1800a80b9  xor     rcx, rsp; StackCookie
0x1800a80bc  call    __security_check_cookie
0x1800a80c1  add     rsp, 278h
0x1800a80c8  pop     rdi
0x1800a80c9  pop     rsi
0x1800a80ca  pop     rbx
0x1800a80cb  pop     rbp
0x1800a80cc  retn
0x1800a80cd  mov     rcx, [rsp+290h+hKey]; hKey
0x1800a80d2  lea     rax, [rcx-1]
0x1800a80d6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a80da  ja      short loc_1800A80E3
0x1800a80dc  call    cs:__imp_RegCloseKey
0x1800a80e2  nop
0x1800a80e3  jmp     short loc_1800A80B0
0x1800a80e5  mov     rcx, [rcx+8]; this
0x1800a80e9  mov     r8, [rcx+118h]; unsigned __int16 *
0x1800a80f0  mov     rdx, [rcx+108h]; HKEY
0x1800a80f7  call    ?RemoveRegistryKey@StateCreation@@AEAAJPEAUHKEY__@@PEBG@Z; StateCreation::RemoveRegistryKey(HKEY__ *,ushort const *)
0x1800a80fc  mov     edi, eax
0x1800a80fe  test    eax, eax
0x1800a8100  jns     short loc_1800A80B0
0x1800a8102  mov     rdx, [rbx+8]
0x1800a8106  mov     rcx, [rbp+198h]; this
0x1800a810d  mov     rdx, [rdx+118h]
0x1800a8114  mov     [rsp+290h+lpClass], rdx; char *
0x1800a8119  lea     rdx, aPathLs; "Path %ls"
0x1800a8120  mov     [rsp+290h+phkResult], rdx; int
0x1800a8125  mov     r9d, eax; char *
0x1800a8128  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\statecreation"...
0x1800a812f  mov     edx, 0C7Fh; void *
0x1800a8134  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a8139  jmp     loc_1800A7F10
```
