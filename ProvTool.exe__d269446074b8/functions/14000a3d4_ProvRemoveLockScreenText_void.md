# ProvRemoveLockScreenText(void)

- ea: `0x14000a3d4`
- end: `0x14000a777`
- name: `?ProvRemoveLockScreenText@@YAJXZ`
- size: `931`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400059ac`

## callees

- `0x140001130`
- `0x140008820`
- `0x14000a3d4`
- `0x14000a780`
- `0x14000ded0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14000a643`
- `msvcrt!_wcsicmp` at `0x14000a643`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000a5b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000a715`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000a724`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000a5b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000a715`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000a724`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a6a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a68d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a68d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a423`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a474`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a4c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a423`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a474`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a4c5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14000a6e7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14000a6e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a437`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a488`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a4d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a4ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a53a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a54b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a5c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a5d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a698`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a735`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a746`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a437`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a488`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a4d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a4ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a53a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a54b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a5c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a5d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a698`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a735`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a746`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000a526`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000a5a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000a62f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000a526`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000a5a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000a62f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14000a6b5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14000a6b5`

## pseudocode

```c
__int64 ProvRemoveLockScreenText(void)
{
  const WCHAR *v1; // rdx
  PVOID v2; // rdi
  wchar_t *v3; // rsi
  HKEY v4; // r14
  DWORD LastError; // ebx
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  DWORD pcbData; // [rsp+40h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-90h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-80h] BYREF
  PVOID pvData[2]; // [rsp+60h] [rbp-78h] BYREF
  __int64 v13; // [rsp+70h] [rbp-68h]
  PVOID v14[2]; // [rsp+78h] [rbp-60h] BYREF
  __int64 v15; // [rsp+88h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\LostMode",
         0,
         0x20019u,
         &hKey) )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    hkey = 0;
    if ( !`ProvIsStateSeparationEnabled'::`2'::s_HasRun )
    {
      phkResult = 0;
      `ProvIsStateSeparationEnabled'::`2'::s_Redirection = RegOpenKeyExW(
                                                             HKEY_LOCAL_MACHINE,
                                                             L"Software\\Microsoft\\Provisioning\\StateSeparationMode",
                                                             0,
                                                             0x20119u,
                                                             &phkResult) == 0;
      RegCloseKey(phkResult);
      `ProvIsStateSeparationEnabled'::`2'::s_HasRun = 1;
    }
    v1 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\";
    if ( !`ProvIsStateSeparationEnabled'::`2'::s_Redirection )
      v1 = L"SOFTWARE\\Microsoft\\Provisioning\\";
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0x2001Fu, &hkey) )
    {
      if ( hkey )
        RegCloseKey(hkey);
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
    else
    {
      pcbData = 0;
      if ( RegGetValueW(hkey, 0, L"LostModeMessage", 2u, 0, 0, &pcbData) )
      {
        if ( hkey )
          RegCloseKey(hkey);
        if ( hKey )
          RegCloseKey(hKey);
        return 0;
      }
      else
      {
        *(_OWORD *)pvData = 0;
        v13 = 0;
        std::vector<unsigned short>::resize(pvData, (unsigned __int64)pcbData >> 1);
        v2 = pvData[0];
        if ( RegGetValueW(hkey, 0, L"LostModeMessage", 2u, 0, pvData[0], &pcbData) )
        {
          if ( v2 )
            operator delete(v2);
          if ( hkey )
            RegCloseKey(hkey);
          if ( hKey )
            RegCloseKey(hKey);
          return 0;
        }
        else
        {
          *(_OWORD *)v14 = 0;
          v15 = 0;
          std::vector<unsigned short>::resize(v14, (unsigned __int64)pcbData >> 1);
          v3 = (wchar_t *)v14[0];
          if ( !RegGetValueW(hKey, 0, L"LostModeMessage", 2u, 0, v14[0], &pcbData) && !_wcsicmp((const wchar_t *)v2, v3) )
          {
            if ( (unsigned int)dword_140017048 > 4 )
              tlgWriteTransfer_EventWriteTransfer(&dword_140017048, &dword_140013434, 0, 0);
            v4 = hKey;
            if ( hKey )
            {
              LastError = GetLastError();
              RegCloseKey(v4);
              SetLastError(LastError);
            }
            hKey = 0;
            v6 = RegDeleteKeyW(
                   HKEY_LOCAL_MACHINE,
                   L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\LostMode");
            if ( v6 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x6C,
                (__int64)"onecoreuap\\admin\\prov\\lib\\lockscreenstatus.cpp",
                (const char *)(unsigned int)v6);
            v7 = RegDeleteValueW(hkey, L"LostModeMessage");
            if ( v7 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x6D,
                (__int64)"onecoreuap\\admin\\prov\\lib\\lockscreenstatus.cpp",
                (const char *)(unsigned int)v7);
          }
          if ( v3 )
            operator delete(v3);
          if ( v2 )
            operator delete(v2);
          if ( hkey )
            RegCloseKey(hkey);
          if ( hKey )
            RegCloseKey(hKey);
          return 0;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14000a3d4  push    rbx
0x14000a3d6  push    rsi
0x14000a3d7  push    rdi
0x14000a3d8  push    r12
0x14000a3da  push    r14
0x14000a3dc  push    r15
0x14000a3de  sub     rsp, 0A8h
0x14000a3e5  mov     rax, cs:__security_cookie
0x14000a3ec  xor     rax, rsp
0x14000a3ef  mov     [rsp+0D8h+var_40], rax
0x14000a3f7  xor     r15d, r15d
0x14000a3fa  mov     [rsp+0D8h+hKey], r15
0x14000a3ff  lea     rax, [rsp+0D8h+hKey]
0x14000a404  mov     [rsp+0D8h+phkResult], rax; phkResult
0x14000a409  mov     r9d, 20019h; samDesired
0x14000a40f  xor     r8d, r8d; ulOptions
0x14000a412  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000a419  mov     r12, 0FFFFFFFF80000002h
0x14000a420  mov     rcx, r12; hKey
0x14000a423  call    cs:__imp_RegOpenKeyExW
0x14000a429  test    eax, eax
0x14000a42b  jz      short loc_14000A444
0x14000a42d  mov     rcx, [rsp+0D8h+hKey]; hKey
0x14000a432  test    rcx, rcx
0x14000a435  jz      short loc_14000A43D
0x14000a437  call    cs:__imp_RegCloseKey
0x14000a43d  xor     eax, eax
0x14000a43f  jmp     loc_14000A755
0x14000a444  mov     [rsp+0D8h+hkey], r15
0x14000a449  cmp     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, r15b; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x14000a450  jnz     short loc_14000A495
0x14000a452  mov     [rsp+0D8h+var_80], r15
0x14000a457  lea     rax, [rsp+0D8h+var_80]
0x14000a45c  mov     [rsp+0D8h+phkResult], rax; phkResult
0x14000a461  mov     r9d, 20119h; samDesired
0x14000a467  xor     r8d, r8d; ulOptions
0x14000a46a  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Provisioning\\Stat"...
0x14000a471  mov     rcx, r12; hKey
0x14000a474  call    cs:__imp_RegOpenKeyExW
0x14000a47a  test    eax, eax
0x14000a47c  setz    cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x14000a483  mov     rcx, [rsp+0D8h+var_80]; hKey
0x14000a488  call    cs:__imp_RegCloseKey
0x14000a48e  mov     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x14000a495  mov     al, cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x14000a49b  lea     rcx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Provisioning\\"
0x14000a4a2  lea     rdx, aOsdataSoftware; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x14000a4a9  test    al, al
0x14000a4ab  cmovz   rdx, rcx; lpSubKey
0x14000a4af  lea     rax, [rsp+0D8h+hkey]
0x14000a4b4  mov     [rsp+0D8h+phkResult], rax; phkResult
0x14000a4b9  mov     r9d, 2001Fh; samDesired
0x14000a4bf  xor     r8d, r8d; ulOptions
0x14000a4c2  mov     rcx, r12; hKey
0x14000a4c5  call    cs:__imp_RegOpenKeyExW
0x14000a4cb  test    eax, eax
0x14000a4cd  jz      short loc_14000A4F7
0x14000a4cf  mov     rcx, [rsp+0D8h+hkey]; hKey
0x14000a4d4  test    rcx, rcx
0x14000a4d7  jz      short loc_14000A4E0
0x14000a4d9  call    cs:__imp_RegCloseKey
0x14000a4df  nop
0x14000a4e0  mov     rcx, [rsp+0D8h+hKey]; hKey
0x14000a4e5  test    rcx, rcx
0x14000a4e8  jz      short loc_14000A4F0
0x14000a4ea  call    cs:__imp_RegCloseKey
0x14000a4f0  xor     eax, eax
0x14000a4f2  jmp     loc_14000A755
0x14000a4f7  mov     [rsp+0D8h+var_98], r15d
0x14000a4fc  lea     rax, [rsp+0D8h+var_98]
0x14000a501  mov     [rsp+0D8h+pcbData], rax; pcbData
0x14000a506  mov     [rsp+0D8h+pvData], r15; pvData
0x14000a50b  mov     [rsp+0D8h+phkResult], r15; pdwType
0x14000a510  mov     ebx, 2
0x14000a515  mov     r9d, ebx; dwFlags
0x14000a518  lea     r8, ValueName; "LostModeMessage"
0x14000a51f  xor     edx, edx; lpSubKey
0x14000a521  mov     rcx, [rsp+0D8h+hkey]; hkey
0x14000a526  call    cs:__imp_RegGetValueW
0x14000a52c  test    eax, eax
0x14000a52e  jz      short loc_14000A558
0x14000a530  mov     rcx, [rsp+0D8h+hkey]; hKey
0x14000a535  test    rcx, rcx
0x14000a538  jz      short loc_14000A541
0x14000a53a  call    cs:__imp_RegCloseKey
0x14000a540  nop
0x14000a541  mov     rcx, [rsp+0D8h+hKey]; hKey
0x14000a546  test    rcx, rcx
0x14000a549  jz      short loc_14000A551
0x14000a54b  call    cs:__imp_RegCloseKey
0x14000a551  xor     eax, eax
0x14000a553  jmp     loc_14000A755
0x14000a558  xorps   xmm0, xmm0
0x14000a55b  movdqu  xmmword ptr [rsp+0D8h+var_78], xmm0
0x14000a561  mov     [rsp+0D8h+var_68], r15
0x14000a566  mov     edx, [rsp+0D8h+var_98]
0x14000a56a  shr     rdx, 1
0x14000a56d  lea     rcx, [rsp+0D8h+var_78]
0x14000a572  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x14000a577  nop
0x14000a578  lea     rax, [rsp+0D8h+var_98]
0x14000a57d  mov     [rsp+0D8h+pcbData], rax; pcbData
0x14000a582  mov     rdi, [rsp+0D8h+var_78]
0x14000a587  mov     [rsp+0D8h+pvData], rdi; pvData
0x14000a58c  mov     [rsp+0D8h+phkResult], r15; pdwType
0x14000a591  mov     r9d, ebx; dwFlags
0x14000a594  lea     r8, ValueName; "LostModeMessage"
0x14000a59b  xor     edx, edx; lpSubKey
0x14000a59d  mov     rcx, [rsp+0D8h+hkey]; hkey
0x14000a5a2  call    cs:__imp_RegGetValueW
0x14000a5a8  test    eax, eax
0x14000a5aa  jz      short loc_14000A5E3
0x14000a5ac  test    rdi, rdi
0x14000a5af  jz      short loc_14000A5BB
0x14000a5b1  mov     rcx, rdi
0x14000a5b4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000a5ba  nop
0x14000a5bb  mov     rcx, [rsp+0D8h+hkey]; hKey
0x14000a5c0  test    rcx, rcx
0x14000a5c3  jz      short loc_14000A5CC
0x14000a5c5  call    cs:__imp_RegCloseKey
0x14000a5cb  nop
0x14000a5cc  mov     rcx, [rsp+0D8h+hKey]; hKey
0x14000a5d1  test    rcx, rcx
0x14000a5d4  jz      short loc_14000A5DC
0x14000a5d6  call    cs:__imp_RegCloseKey
0x14000a5dc  xor     eax, eax
0x14000a5de  jmp     loc_14000A755
0x14000a5e3  xorps   xmm0, xmm0
0x14000a5e6  movdqu  xmmword ptr [rsp+0D8h+var_60], xmm0
0x14000a5ec  mov     [rsp+0D8h+var_50], r15
0x14000a5f4  mov     edx, [rsp+0D8h+var_98]
0x14000a5f8  shr     rdx, 1
0x14000a5fb  lea     rcx, [rsp+0D8h+var_60]
0x14000a600  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x14000a605  lea     rax, [rsp+0D8h+var_98]
0x14000a60a  mov     [rsp+0D8h+pcbData], rax; pcbData
0x14000a60f  mov     rsi, [rsp+0D8h+var_60]
0x14000a614  mov     [rsp+0D8h+pvData], rsi; pvData
0x14000a619  mov     [rsp+0D8h+phkResult], r15; pdwType
0x14000a61e  mov     r9d, ebx; dwFlags
0x14000a621  lea     r8, ValueName; "LostModeMessage"
0x14000a628  xor     edx, edx; lpSubKey
0x14000a62a  mov     rcx, [rsp+0D8h+hKey]; hkey
0x14000a62f  call    cs:__imp_RegGetValueW
0x14000a635  test    eax, eax
0x14000a637  jnz     loc_14000A70D
0x14000a63d  mov     rdx, rsi; String2
0x14000a640  mov     rcx, rdi; String1
0x14000a643  call    cs:__imp__wcsicmp
0x14000a649  test    eax, eax
0x14000a64b  jnz     loc_14000A70D
0x14000a651  mov     eax, cs:dword_140017048
0x14000a657  cmp     eax, 4
0x14000a65a  jbe     short loc_14000A683
0x14000a65c  lea     rax, [rsp+0D8h+var_60]
0x14000a661  mov     [rsp+0D8h+pvData], rax
0x14000a666  mov     dword ptr [rsp+0D8h+phkResult], ebx; int
0x14000a66a  xor     r9d, r9d
0x14000a66d  xor     r8d, r8d
0x14000a670  lea     rdx, dword_140013434
0x14000a677  lea     rcx, dword_140017048
0x14000a67e  call    _tlgWriteTransfer_EventWriteTransfer
0x14000a683  mov     r14, [rsp+0D8h+hKey]
0x14000a688  test    r14, r14
0x14000a68b  jz      short loc_14000A6A6
0x14000a68d  call    cs:__imp_GetLastError
0x14000a693  mov     ebx, eax
0x14000a695  mov     rcx, r14; hKey
0x14000a698  call    cs:__imp_RegCloseKey
0x14000a69e  mov     ecx, ebx; dwErrCode
0x14000a6a0  call    cs:__imp_SetLastError
0x14000a6a6  mov     [rsp+0D8h+hKey], r15
0x14000a6ab  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000a6b2  mov     rcx, r12; hKey
0x14000a6b5  call    cs:__imp_RegDeleteKeyW
0x14000a6bb  mov     rcx, [rsp+0D8h]; this
0x14000a6c3  test    eax, eax
0x14000a6c5  jns     short loc_14000A6DB
0x14000a6c7  mov     r9d, eax; char *
0x14000a6ca  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\lockscree"...
0x14000a6d1  mov     edx, 6Ch ; 'l'; void *
0x14000a6d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000a6db  lea     rdx, ValueName; "LostModeMessage"
0x14000a6e2  mov     rcx, [rsp+0D8h+hkey]; hKey
0x14000a6e7  call    cs:__imp_RegDeleteValueW
0x14000a6ed  mov     rcx, [rsp+0D8h]; this
0x14000a6f5  test    eax, eax
0x14000a6f7  jns     short loc_14000A70D
0x14000a6f9  mov     r9d, eax; char *
0x14000a6fc  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\lockscree"...
0x14000a703  mov     edx, 6Dh ; 'm'; void *
0x14000a708  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000a70d  test    rsi, rsi
0x14000a710  jz      short loc_14000A71C
0x14000a712  mov     rcx, rsi
0x14000a715  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000a71b  nop
0x14000a71c  test    rdi, rdi
0x14000a71f  jz      short loc_14000A72B
0x14000a721  mov     rcx, rdi
0x14000a724  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000a72a  nop
0x14000a72b  mov     rcx, [rsp+0D8h+hkey]; hKey
0x14000a730  test    rcx, rcx
0x14000a733  jz      short loc_14000A73C
0x14000a735  call    cs:__imp_RegCloseKey
0x14000a73b  nop
0x14000a73c  mov     rcx, [rsp+0D8h+hKey]; hKey
0x14000a741  test    rcx, rcx
0x14000a744  jz      short loc_14000A74D
0x14000a746  call    cs:__imp_RegCloseKey
0x14000a74c  nop
0x14000a74d  xor     eax, eax
0x14000a74f  jmp     short loc_14000A755
0x14000a751  mov     eax, [rsp+0D8h+var_98]
0x14000a755  mov     rcx, [rsp+0D8h+var_40]
0x14000a75d  xor     rcx, rsp; StackCookie
0x14000a760  call    __security_check_cookie
0x14000a765  add     rsp, 0A8h
0x14000a76c  pop     r15
0x14000a76e  pop     r14
0x14000a770  pop     r12
0x14000a772  pop     rdi
0x14000a773  pop     rsi
0x14000a774  pop     rbx
0x14000a775  retn
```
