# OSIntegration::DEH::Internal::MMGAHelper::RemoveChanges(void)

- ea: `0x180069670`
- end: `0x180069c0e`
- name: `?RemoveChanges@MMGAHelper@Internal@DEH@OSIntegration@@UEAAJXZ`
- size: `1438`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::MMGAHelper *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18001adb4`
- `0x180021e80`
- `0x18004eac0`
- `0x180064900`
- `0x180066780`
- `0x180069670`
- `0x180069eb4`
- `0x180088cb0`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800dcb24`
- `0x1800eb908`
- `0x1800ebc60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180069a97`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180069a97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006980d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006991a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069b17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006980d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006991a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069b17`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006987c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180069b71`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006987c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180069b71`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800699a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800699a8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180069727`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800697df`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180069727`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800697df`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall OSIntegration::DEH::Internal::MMGAHelper::RemoveChanges(
        OSIntegration::DEH::Internal::MMGAHelper *this)
{
  __int64 v3; // rsi
  struct Common::StringBuffer *v4; // r8
  int MapiClsidRegistryPath; // eax
  unsigned int v6; // edi
  const struct std::nothrow_t *v7; // rdx
  void *v8; // rbx
  const WCHAR *v9; // rdx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  const struct std::nothrow_t *v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  const struct std::nothrow_t *v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  const struct std::nothrow_t *v18; // rdx
  unsigned int InfoKeyW; // eax
  unsigned int v20; // ebx
  const struct std::nothrow_t *v21; // rdx
  bool v22; // bl
  const struct std::nothrow_t *v23; // rdx
  LSTATUS ValueW; // eax
  bool v25; // sf
  unsigned __int16 *v26; // rax
  int v27; // r10d
  int v28; // r9d
  unsigned int v29; // eax
  unsigned int v30; // ebx
  const struct std::nothrow_t *v31; // rdx
  unsigned int v32; // eax
  unsigned int v33; // ebx
  const struct std::nothrow_t *v34; // rdx
  int phkResult; // [rsp+20h] [rbp-148h]
  unsigned int phkResulta; // [rsp+20h] [rbp-148h]
  unsigned int phkResultb; // [rsp+20h] [rbp-148h]
  unsigned int phkResultc; // [rsp+20h] [rbp-148h]
  unsigned int phkResultd; // [rsp+20h] [rbp-148h]
  HKEY hKey; // [rsp+60h] [rbp-108h] BYREF
  HKEY v41; // [rsp+68h] [rbp-100h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+70h] [rbp-F8h] BYREF
  int v43; // [rsp+80h] [rbp-E8h]
  _DWORD v44[6]; // [rsp+88h] [rbp-E0h] BYREF
  __int16 v45; // [rsp+A0h] [rbp-C8h]
  LPCWSTR v46[4]; // [rsp+A8h] [rbp-C0h] BYREF
  _BYTE Src[32]; // [rsp+C8h] [rbp-A0h] BYREF
  _BYTE v48[32]; // [rsp+E8h] [rbp-80h] BYREF
  _BYTE pvData[56]; // [rsp+108h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  if ( !*((_BYTE *)this + 232) )
    return 0;
  v3 = std::optional<OSIntegration::DEH::Internal::MailProvider>::value((char *)this + 64);
  *(_OWORD *)lpSubKey = 0;
  v43 = 0;
  MapiClsidRegistryPath = OSIntegration::DEH::Internal::GetMapiClsidRegistryPath(
                            *(OSIntegration::DEH::Internal **)(*((_QWORD *)this + 3) + 224LL),
                            (unsigned __int16 *const)lpSubKey,
                            v4);
  v6 = MapiClsidRegistryPath;
  if ( MapiClsidRegistryPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18A,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\mmga\\mmgahelper.cpp",
      (const char *)(unsigned int)MapiClsidRegistryPath,
      phkResult);
    if ( lpSubKey[1] )
      operator delete((void *)lpSubKey[1], v7);
    return v6;
  }
  RegDeleteTreeW(HKEY_LOCAL_MACHINE, lpSubKey[1]);
  if ( *(_BYTE *)(v3 + 32) && *(_BYTE *)(v3 + 33) && *(_BYTE *)(*((_QWORD *)this + 3) + 405LL) )
  {
    v8 = (void *)std::wstring::wstring(v48, L"SOFTWARE\\Clients\\Mail");
    std::wstring::push_back(v8, 92);
    std::wstring::wstring(Src, v8);
    std::operator+<unsigned short>(v46, Src);
    std::wstring::_Tidy_deallocate(Src);
    std::wstring::_Tidy_deallocate(v48);
    v9 = (const WCHAR *)v46;
    if ( v46[3] > (LPCWSTR)7 )
      v9 = v46[0];
    RegDeleteTreeW(HKEY_LOCAL_MACHINE, v9);
    hKey = 0;
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Clients\\Mail", 0, 2u, &hKey);
    if ( v10 - 2 > 1 && v10 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x19B,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\mmga\\mmgahelper.cpp",
              (const char *)v10,
              phkResulta);
      Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
      std::wstring::_Tidy_deallocate(v46);
      if ( lpSubKey[1] )
        operator delete((void *)lpSubKey[1], v12);
      return v11;
    }
    v13 = RegDeleteValueW(hKey, 0);
    if ( v13 != 2 && v13 )
    {
      v14 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1A1,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\mmga\\mmgahelper.cpp",
              (const char *)v13,
              phkResulta);
      Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
      std::wstring::_Tidy_deallocate(v46);
      if ( lpSubKey[1] )
        operator delete((void *)lpSubKey[1], v15);
      return v14;
    }
    Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
    std::wstring::_Tidy_deallocate(v46);
  }
  v41 = 0;
  v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Clients\\Mail\\PackagedMail", 0, 1u, &v41);
  if ( v16 )
  {
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1AA,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\mmga\\mmgahelper.cpp",
            (const char *)v16,
            phkResultb);
    Common::AutoHandleCloseHKEY<HKEY__ *>(v41);
    if ( lpSubKey[1] )
      operator delete((void *)lpSubKey[1], v18);
    return v17;
  }
  LODWORD(hKey) = 0;
  InfoKeyW = RegQueryInfoKeyW(v41, 0, 0, 0, (LPDWORD)&hKey, 0, 0, 0, 0, 0, 0, 0);
  if ( InfoKeyW )
  {
    v20 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1B9,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\mmga\\mmgahelper.cpp",
            (const char *)InfoKeyW,
            phkResultc);
    Common::AutoHandleCloseHKEY<HKEY__ *>(v41);
    if ( lpSubKey[1] )
      operator delete((void *)lpSubKey[1], v21);
    return v20;
  }
  v22 = (_DWORD)hKey != 0;
  Common::AutoHandleCloseHKEY<HKEY__ *>(v41);
  if ( !v22 )
  {
    v44[0] = 6357072;
    v44[1] = 7012451;
    v44[2] = 6750305;
    v44[3] = 6553701;
    v44[4] = 6357069;
    v44[5] = 7077993;
    v45 = 0;
    LODWORD(hKey) = 26;
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Clients\\Mail", 0, 2u, 0, pvData, (LPDWORD)&hKey);
    v25 = ValueW < 0;
    if ( ValueW > 0 )
      v25 = 1;
    if ( !v25 && (_DWORD)hKey == 26 )
    {
      v26 = (unsigned __int16 *)v44;
      do
      {
        v27 = *(unsigned __int16 *)((char *)v26 + pvData - (_BYTE *)v44);
        v28 = *v26 - v27;
        if ( v28 )
          break;
        ++v26;
      }
      while ( v27 );
      if ( !v28 )
      {
        v41 = 0;
        v29 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Clients\\Mail", 0, 2u, &v41);
        if ( v29 - 2 > 1 && v29 )
        {
          v30 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x1DB,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\mmga\\mmgahelper.cpp",
                  (const char *)v29,
                  phkResultd);
          Common::AutoHandleCloseHKEY<HKEY__ *>(v41);
          if ( lpSubKey[1] )
            operator delete((void *)lpSubKey[1], v31);
          return v30;
        }
        v32 = RegDeleteValueW(v41, 0);
        if ( v32 != 2 && v32 )
        {
          v33 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x1E1,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\mmga\\mmgahelper.cpp",
                  (const char *)v32,
                  phkResultd);
          Common::AutoHandleCloseHKEY<HKEY__ *>(v41);
          if ( lpSubKey[1] )
            operator delete((void *)lpSubKey[1], v34);
          return v33;
        }
        Common::AutoHandleCloseHKEY<HKEY__ *>(v41);
      }
    }
  }
  if ( lpSubKey[1] )
    operator delete((void *)lpSubKey[1], v23);
  return 0;
}

```

## disassembly

```asm
0x180069670  mov     [rsp+arg_8], rbx
0x180069675  mov     [rsp+arg_10], rsi
0x18006967a  push    rdi
0x18006967b  push    r14
0x18006967d  push    r15
0x18006967f  sub     rsp, 150h
0x180069686  mov     rax, cs:__security_cookie
0x18006968d  xor     rax, rsp
0x180069690  mov     [rsp+168h+var_28], rax
0x180069698  mov     rbx, rcx
0x18006969b  xor     r14d, r14d
0x18006969e  cmp     [rcx+0E8h], r14b
0x1800696a5  jnz     short loc_1800696AE
0x1800696a7  xor     eax, eax
0x1800696a9  jmp     loc_180069BE4
0x1800696ae  add     rcx, 40h ; '@'
0x1800696b2  call    ?value@?$optional@UMailProvider@Internal@DEH@OSIntegration@@@std@@QEGAAAEAUMailProvider@Internal@DEH@OSIntegration@@XZ; std::optional<OSIntegration::DEH::Internal::MailProvider>::value(void)
0x1800696b7  mov     rsi, rax
0x1800696ba  xorps   xmm0, xmm0
0x1800696bd  movups  xmmword ptr [rsp+168h+lpSubKey], xmm0
0x1800696c2  mov     [rsp+168h+var_E8], r14d
0x1800696ca  mov     rcx, [rbx+18h]
0x1800696ce  lea     rdx, [rsp+168h+lpSubKey]; unsigned __int16 *
0x1800696d3  mov     rcx, [rcx+0E0h]; this
0x1800696da  call    ?GetMapiClsidRegistryPath@Internal@DEH@OSIntegration@@YAJQEAGAEAVStringBuffer@Common@@@Z; OSIntegration::DEH::Internal::GetMapiClsidRegistryPath(ushort * const,Common::StringBuffer &)
0x1800696df  mov     edi, eax
0x1800696e1  test    eax, eax
0x1800696e3  jns     short loc_180069718
0x1800696e5  mov     rcx, [rsp+168h]; this
0x1800696ed  mov     r9d, eax; char *
0x1800696f0  lea     r8, aOnecoreAdminAp_37; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800696f7  mov     edx, 18Ah; void *
0x1800696fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180069701  nop
0x180069702  mov     rcx, [rsp+168h+lpSubKey+8]; void *
0x180069707  test    rcx, rcx
0x18006970a  jz      short loc_180069711
0x18006970c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180069711  mov     eax, edi
0x180069713  jmp     loc_180069BE4
0x180069718  mov     rdx, [rsp+168h+lpSubKey+8]; lpSubKey
0x18006971d  mov     r15, 0FFFFFFFF80000002h
0x180069724  mov     rcx, r15; hKey
0x180069727  call    cs:__imp_RegDeleteTreeW
0x18006972e  nop     dword ptr [rax+rax+00h]
0x180069733  cmp     [rsi+20h], r14b
0x180069737  jz      loc_1800698F6
0x18006973d  cmp     [rsi+21h], r14b
0x180069741  jz      loc_1800698F6
0x180069747  mov     rax, [rbx+18h]
0x18006974b  cmp     [rax+195h], r14b
0x180069752  jz      loc_1800698F6
0x180069758  lea     rdx, aSoftwareClient_0; "SOFTWARE\\Clients\\Mail"
0x18006975f  lea     rcx, [rsp+168h+var_80]
0x180069767  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006976c  mov     rbx, rax
0x18006976f  mov     edx, 5Ch ; '\'
0x180069774  mov     rcx, rax
0x180069777  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x18006977c  mov     rdx, rbx; void *
0x18006977f  lea     rcx, [rsp+168h+Src]; void *
0x180069787  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18006978c  nop
0x18006978d  lea     r8, [rsi+28h]
0x180069791  lea     rdx, [rsp+168h+Src]; Src
0x180069799  lea     rcx, [rsp+168h+var_C0]; void *
0x1800697a1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800697a6  nop
0x1800697a7  lea     rcx, [rsp+168h+Src]
0x1800697af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800697b4  nop
0x1800697b5  lea     rcx, [rsp+168h+var_80]
0x1800697bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800697c2  lea     rdx, [rsp+168h+var_C0]
0x1800697ca  cmp     [rsp+168h+var_A8], 7
0x1800697d3  cmova   rdx, [rsp+168h+var_C0]; lpSubKey
0x1800697dc  mov     rcx, r15; hKey
0x1800697df  call    cs:__imp_RegDeleteTreeW
0x1800697e6  nop     dword ptr [rax+rax+00h]
0x1800697eb  mov     [rsp+168h+hKey], r14
0x1800697f0  lea     rax, [rsp+168h+hKey]
0x1800697f5  mov     [rsp+168h+phkResult], rax; unsigned int
0x1800697fa  mov     r9d, 2; samDesired
0x180069800  xor     r8d, r8d; ulOptions
0x180069803  lea     rdx, aSoftwareClient_0; "SOFTWARE\\Clients\\Mail"
0x18006980a  mov     rcx, r15; hKey
0x18006980d  call    cs:__imp_RegOpenKeyExW
0x180069814  nop     dword ptr [rax+rax+00h]
0x180069819  lea     ecx, [rax-2]
0x18006981c  mov     edi, 1
0x180069821  cmp     ecx, edi
0x180069823  jbe     short loc_180069875
0x180069825  test    eax, eax
0x180069827  jz      short loc_180069875
0x180069829  mov     rcx, [rsp+168h]; this
0x180069831  mov     r9d, eax; char *
0x180069834  lea     r8, aOnecoreAdminAp_37; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006983b  mov     edx, 19Bh; void *
0x180069840  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180069845  mov     ebx, eax
0x180069847  mov     rcx, [rsp+168h+hKey]
0x18006984c  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180069851  lea     rcx, [rsp+168h+var_C0]
0x180069859  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006985e  nop
0x18006985f  mov     rcx, [rsp+168h+lpSubKey+8]; void *
0x180069864  test    rcx, rcx
0x180069867  jz      short loc_18006986E
0x180069869  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006986e  mov     eax, ebx
0x180069870  jmp     loc_180069BE4
0x180069875  xor     edx, edx; lpValueName
0x180069877  mov     rcx, [rsp+168h+hKey]; hKey
0x18006987c  call    cs:__imp_RegDeleteValueW
0x180069883  nop     dword ptr [rax+rax+00h]
0x180069888  cmp     eax, 2
0x18006988b  jz      short loc_1800698DD
0x18006988d  test    eax, eax
0x18006988f  jz      short loc_1800698DD
0x180069891  mov     rcx, [rsp+168h]; this
0x180069899  mov     r9d, eax; char *
0x18006989c  lea     r8, aOnecoreAdminAp_37; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800698a3  mov     edx, 1A1h; void *
0x1800698a8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800698ad  mov     ebx, eax
0x1800698af  mov     rcx, [rsp+168h+hKey]
0x1800698b4  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800698b9  lea     rcx, [rsp+168h+var_C0]
0x1800698c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800698c6  nop
0x1800698c7  mov     rcx, [rsp+168h+lpSubKey+8]; void *
0x1800698cc  test    rcx, rcx
0x1800698cf  jz      short loc_1800698D6
0x1800698d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800698d6  mov     eax, ebx
0x1800698d8  jmp     loc_180069BE4
0x1800698dd  mov     rcx, [rsp+168h+hKey]
0x1800698e2  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800698e7  lea     rcx, [rsp+168h+var_C0]
0x1800698ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800698f4  jmp     short loc_1800698FB
0x1800698f6  mov     edi, 1
0x1800698fb  mov     [rsp+168h+var_100], r14
0x180069900  lea     rax, [rsp+168h+var_100]
0x180069905  mov     [rsp+168h+phkResult], rax; unsigned int
0x18006990a  mov     r9d, edi; samDesired
0x18006990d  xor     r8d, r8d; ulOptions
0x180069910  lea     rdx, aSoftwareClient; "SOFTWARE\\Clients\\Mail\\PackagedMail"
0x180069917  mov     rcx, r15; hKey
0x18006991a  call    cs:__imp_RegOpenKeyExW
0x180069921  nop     dword ptr [rax+rax+00h]
0x180069926  test    eax, eax
0x180069928  jz      short loc_180069969
0x18006992a  mov     rcx, [rsp+168h]; this
0x180069932  mov     r9d, eax; char *
0x180069935  lea     r8, aOnecoreAdminAp_37; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006993c  mov     edx, 1AAh; void *
0x180069941  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180069946  mov     ebx, eax
0x180069948  mov     rcx, [rsp+168h+var_100]
0x18006994d  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180069952  nop
0x180069953  mov     rcx, [rsp+168h+lpSubKey+8]; void *
0x180069958  test    rcx, rcx
0x18006995b  jz      short loc_180069962
0x18006995d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180069962  mov     eax, ebx
0x180069964  jmp     loc_180069BE4
0x180069969  mov     dword ptr [rsp+168h+hKey], r14d
0x18006996e  mov     [rsp+168h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180069973  mov     [rsp+168h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180069978  mov     [rsp+168h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18006997d  mov     [rsp+168h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180069982  mov     [rsp+168h+lpcValues], r14; lpcValues
0x180069987  mov     [rsp+168h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18006998c  mov     [rsp+168h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x180069991  lea     rax, [rsp+168h+hKey]
0x180069996  mov     [rsp+168h+phkResult], rax; unsigned int
0x18006999b  xor     r9d, r9d; lpReserved
0x18006999e  xor     r8d, r8d; lpcchClass
0x1800699a1  xor     edx, edx; lpClass
0x1800699a3  mov     rcx, [rsp+168h+var_100]; hKey
0x1800699a8  call    cs:__imp_RegQueryInfoKeyW
0x1800699af  nop     dword ptr [rax+rax+00h]
0x1800699b4  test    eax, eax
0x1800699b6  jz      short loc_1800699F7
0x1800699b8  mov     rcx, [rsp+168h]; this
0x1800699c0  mov     r9d, eax; char *
0x1800699c3  lea     r8, aOnecoreAdminAp_37; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800699ca  mov     edx, 1B9h; void *
0x1800699cf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800699d4  mov     ebx, eax
0x1800699d6  mov     rcx, [rsp+168h+var_100]
0x1800699db  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800699e0  nop
0x1800699e1  mov     rcx, [rsp+168h+lpSubKey+8]; void *
0x1800699e6  test    rcx, rcx
0x1800699e9  jz      short loc_1800699F0
0x1800699eb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800699f0  mov     eax, ebx
0x1800699f2  jmp     loc_180069BE4
0x1800699f7  movzx   ebx, r14b
0x1800699fb  cmp     dword ptr [rsp+168h+hKey], r14d
0x180069a00  cmova   ebx, edi
0x180069a03  mov     rcx, [rsp+168h+var_100]
0x180069a08  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180069a0d  test    bl, bl
0x180069a0f  jnz     loc_180069BCD
0x180069a15  mov     [rsp+168h+var_E0], 610050h
0x180069a20  mov     [rsp+168h+var_DC], 6B0063h
0x180069a2b  mov     [rsp+168h+var_D8], 670061h
0x180069a36  mov     [rsp+168h+var_D4], 640065h
0x180069a41  mov     [rsp+168h+var_D0], 61004Dh
0x180069a4c  mov     [rsp+168h+var_CC], 6C0069h
0x180069a57  mov     [rsp+168h+var_C8], r14w
0x180069a60  mov     dword ptr [rsp+168h+hKey], 1Ah
0x180069a68  lea     rax, [rsp+168h+hKey]
0x180069a6d  mov     [rsp+168h+lpcbMaxClassLen], rax; pcbData
0x180069a72  lea     rax, [rsp+168h+pvData]
0x180069a7a  mov     [rsp+168h+lpcbMaxSubKeyLen], rax; pvData
0x180069a7f  mov     [rsp+168h+phkResult], r14; pdwType
0x180069a84  mov     r9d, 2; dwFlags
0x180069a8a  xor     r8d, r8d; lpValue
0x180069a8d  lea     rdx, aSoftwareClient_0; "SOFTWARE\\Clients\\Mail"
0x180069a94  mov     rcx, r15; hkey
0x180069a97  call    cs:__imp_RegGetValueW
0x180069a9e  nop     dword ptr [rax+rax+00h]
0x180069aa3  test    eax, eax
0x180069aa5  jle     short loc_180069AB1
0x180069aa7  movzx   eax, ax
0x180069aaa  or      eax, 80070000h
0x180069aaf  test    eax, eax
0x180069ab1  js      loc_180069BCD
0x180069ab7  cmp     dword ptr [rsp+168h+hKey], 1Ah
0x180069abc  jnz     loc_180069BCD
0x180069ac2  lea     rax, [rsp+168h+var_E0]
0x180069aca  lea     r8, [rsp+168h+pvData]
0x180069ad2  sub     r8, rax
0x180069ad5  movzx   r9d, word ptr [rax]
0x180069ad9  movzx   r10d, word ptr [rax+r8]
0x180069ade  sub     r9d, r10d
0x180069ae1  jnz     short loc_180069AEC
0x180069ae3  add     rax, 2
0x180069ae7  test    r10d, r10d
0x180069aea  jnz     short loc_180069AD5
0x180069aec  test    r9d, r9d
0x180069aef  jnz     loc_180069BCD
0x180069af5  mov     [rsp+168h+var_100], r14
0x180069afa  lea     rax, [rsp+168h+var_100]
0x180069aff  mov     [rsp+168h+phkResult], rax; unsigned int
0x180069b04  mov     r9d, 2; samDesired
0x180069b0a  xor     r8d, r8d; ulOptions
0x180069b0d  lea     rdx, aSoftwareClient_0; "SOFTWARE\\Clients\\Mail"
0x180069b14  mov     rcx, r15; hKey
0x180069b17  call    cs:__imp_RegOpenKeyExW
0x180069b1e  nop     dword ptr [rax+rax+00h]
0x180069b23  lea     ecx, [rax-2]
0x180069b26  cmp     ecx, edi
0x180069b28  jbe     short loc_180069B6A
0x180069b2a  test    eax, eax
0x180069b2c  jz      short loc_180069B6A
0x180069b2e  mov     rcx, [rsp+168h]; this
0x180069b36  mov     r9d, eax; char *
0x180069b39  lea     r8, aOnecoreAdminAp_37; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180069b40  mov     edx, 1DBh; void *
0x180069b45  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180069b4a  mov     ebx, eax
0x180069b4c  mov     rcx, [rsp+168h+var_100]
0x180069b51  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180069b56  nop
0x180069b57  mov     rcx, [rsp+168h+lpSubKey+8]; void *
0x180069b5c  test    rcx, rcx
0x180069b5f  jz      short loc_180069B66
0x180069b61  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180069b66  mov     eax, ebx
0x180069b68  jmp     short loc_180069BE4
0x180069b6a  xor     edx, edx; lpValueName
0x180069b6c  mov     rcx, [rsp+168h+var_100]; hKey
0x180069b71  call    cs:__imp_RegDeleteValueW
0x180069b78  nop     dword ptr [rax+rax+00h]
0x180069b7d  cmp     eax, 2
0x180069b80  jz      short loc_180069BC2
0x180069b82  test    eax, eax
0x180069b84  jz      short loc_180069BC2
0x180069b86  mov     rcx, [rsp+168h]; this
0x180069b8e  mov     r9d, eax; char *
0x180069b91  lea     r8, aOnecoreAdminAp_37; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180069b98  mov     edx, 1E1h; void *
0x180069b9d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180069ba2  mov     ebx, eax
0x180069ba4  mov     rcx, [rsp+168h+var_100]
0x180069ba9  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180069bae  nop
0x180069baf  mov     rcx, [rsp+168h+lpSubKey+8]; void *
0x180069bb4  test    rcx, rcx
0x180069bb7  jz      short loc_180069BBE
0x180069bb9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180069bbe  mov     eax, ebx
0x180069bc0  jmp     short loc_180069BE4
0x180069bc2  mov     rcx, [rsp+168h+var_100]
  ... truncated ...
```
