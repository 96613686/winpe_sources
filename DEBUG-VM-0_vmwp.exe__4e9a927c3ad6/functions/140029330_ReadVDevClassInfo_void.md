# ReadVDevClassInfo(void)

- ea: `0x140029330`
- end: `0x1400295d4`
- name: `?ReadVDevClassInfo@@YA?AV?$map@U_GUID@@UVDevClassInfo@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UVDevClassInfo@@@std@@@std@@@std@@XZ`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400dbf60`

## callees

- `0x140023f74`
- `0x140029330`
- `0x1400295dc`
- `0x140029724`
- `0x140029b80`
- `0x140029d08`
- `0x14009d7ac`
- `0x1400d5d30`
- `0x140132940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400293a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140029403`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400294bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400293a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140029403`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400294bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002951b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002957c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002959e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002951b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002957c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002959e`

## string_xrefs

- `0x1400293c6`: `onecore\vm\common\vml\VmRegistry.h`
- `0x140029421`: `onecore\vm\common\vml\VmRegistry.h`
- `0x1400294d9`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_OWORD *__fastcall ReadVDevClassInfo(_OWORD *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // edi
  __m128i si128; // xmm6
  const unsigned __int16 *v6; // rdx
  const WCHAR *v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rax
  wil *v11; // rcx
  unsigned int v12; // eax
  LPCWSTR *v13; // r8
  unsigned int phkResult; // [rsp+20h] [rbp-98h]
  unsigned int phkResulta; // [rsp+20h] [rbp-98h]
  unsigned int phkResultb; // [rsp+20h] [rbp-98h]
  _BYTE v17[16]; // [rsp+40h] [rbp-78h] BYREF
  HKEY v18; // [rsp+50h] [rbp-68h] BYREF
  HKEY v19; // [rsp+58h] [rbp-60h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp-58h] BYREF
  __m128i v21; // [rsp+70h] [rbp-48h]
  HKEY hKey; // [rsp+80h] [rbp-38h] BYREF
  _BYTE v23[16]; // [rsp+88h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  *a1 = 0;
  std::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>();
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
         0,
         0x20019u,
         &hKey);
  if ( (v2 & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
      (const char *)v2,
      phkResult);
  v18 = 0;
  v3 = RegOpenKeyExW(hKey, L"VirtualDevices", 0, 0x20019u, &v18);
  if ( (v3 & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
      (const char *)v3,
      phkResulta);
  v4 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    *(_OWORD *)lpSubKey = 0;
    v21 = si128;
    LOWORD(lpSubKey[0]) = 0;
    if ( !(unsigned int)Vml::VmRegistryKey::EnumKey(&v18, v4, lpSubKey) )
      break;
    v6 = (const unsigned __int16 *)lpSubKey;
    if ( v21.m128i_i64[1] > 7uLL )
      v6 = lpSubKey[0];
    try
    {
      Vml::VmGuid::Assign((Vml::VmGuid *)v23, v6);
      v19 = 0;
      v7 = (const WCHAR *)lpSubKey;
      if ( v21.m128i_i64[1] > 7uLL )
        v7 = lpSubKey[0];
      v8 = RegOpenKeyExW(v18, v7, 0, 0x20019u, &v19);
      if ( (v8 & 0xFFFFFFFD) != 0 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1F9,
          (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
          (const char *)v8,
          phkResultb);
      v9 = std::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>::_Try_emplace<_GUID const &,>(
             a1,
             v17,
             v23);
      ReadSingleVDevClassInfo((struct Vml::VmRegistryKey *)&v19, (struct VDevClassInfo *)(*(_QWORD *)v9 + 48LL));
      if ( v19 )
      {
        RegCloseKey(v19);
        v19 = 0;
      }
      if ( v21.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(lpSubKey[0], 2 * v21.m128i_i64[1] + 2);
      ++v4;
    }
    catch ( ... )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
      {
        v12 = wil::ResultFromCaughtException(v11);
        v13 = lpSubKey;
        if ( v21.m128i_i64[1] > 7uLL )
          v13 = (LPCWSTR *)lpSubKey[0];
        VmlDebugTrace(0x4000, L"VDevRegistrar: Invalid registration data for device %s (error: 0x%08x)", v13, v12);
      }
      throw;
    }
  }
  if ( v21.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(lpSubKey[0], 2 * v21.m128i_i64[1] + 2);
  if ( v18 )
  {
    RegCloseKey(v18);
    v18 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x140029330  mov     rax, rsp
0x140029333  mov     [rax+10h], rbx
0x140029337  push    rdi
0x140029338  sub     rsp, 0B0h
0x14002933f  movaps  xmmword ptr [rax-18h], xmm6
0x140029343  mov     rax, cs:__security_cookie
0x14002934a  xor     rax, rsp
0x14002934d  mov     [rsp+0B8h+var_20], rax
0x140029355  mov     rbx, rcx
0x140029358  mov     [rsp+0B8h+var_80], rcx
0x14002935d  mov     [rsp+0B8h+var_88], 0
0x140029365  xorps   xmm0, xmm0
0x140029368  movups  xmmword ptr [rcx], xmm0
0x14002936b  call    ??0?$map@U_GUID@@UVDevClassInfo@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UVDevClassInfo@@@std@@@std@@@std@@QEAA@XZ; std::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>(void)
0x140029370  mov     [rsp+0B8h+var_88], 1
0x140029378  mov     [rsp+0B8h+hKey], 0
0x140029384  lea     rax, [rsp+0B8h+hKey]
0x14002938c  mov     qword ptr [rsp+0B8h+phkResult], rax; unsigned int
0x140029391  mov     r9d, 20019h; samDesired
0x140029397  xor     r8d, r8d; ulOptions
0x14002939a  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400293a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400293a8  call    cs:__imp_RegOpenKeyExW
0x1400293af  nop     dword ptr [rax+rax+00h]
0x1400293b4  test    eax, 0FFFFFFFDh
0x1400293b9  jz      short loc_1400293D8
0x1400293bb  mov     rcx, [rsp+0B8h]; this
0x1400293c3  mov     r9d, eax; char *
0x1400293c6  lea     r8, aOnecoreVmCommo_108; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x1400293cd  mov     edx, 1F9h; void *
0x1400293d2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400293d8  mov     [rsp+0B8h+var_68], 0
0x1400293e1  lea     rax, [rsp+0B8h+var_68]
0x1400293e6  mov     qword ptr [rsp+0B8h+phkResult], rax; unsigned int
0x1400293eb  mov     r9d, 20019h; samDesired
0x1400293f1  xor     r8d, r8d; ulOptions
0x1400293f4  lea     rdx, SubKey; "VirtualDevices"
0x1400293fb  mov     rcx, [rsp+0B8h+hKey]; hKey
0x140029403  call    cs:__imp_RegOpenKeyExW
0x14002940a  nop     dword ptr [rax+rax+00h]
0x14002940f  test    eax, 0FFFFFFFDh
0x140029414  jz      short loc_140029433
0x140029416  mov     rcx, [rsp+0B8h]; this
0x14002941e  mov     r9d, eax; char *
0x140029421  lea     r8, aOnecoreVmCommo_108; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x140029428  mov     edx, 1F9h; void *
0x14002942d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140029433  xor     edi, edi
0x140029435  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14002943d  xorps   xmm0, xmm0
0x140029440  movups  xmmword ptr [rsp+0B8h+lpSubKey], xmm0
0x140029445  movdqu  [rsp+0B8h+var_48], xmm6
0x14002944b  xor     eax, eax
0x14002944d  mov     word ptr [rsp+0B8h+lpSubKey], ax
0x140029452  lea     r8, [rsp+0B8h+lpSubKey]
0x140029457  mov     edx, edi
0x140029459  lea     rcx, [rsp+0B8h+var_68]
0x14002945e  call    ?EnumKey@VmRegistryKey@Vml@@QEBAHKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Vml::VmRegistryKey::EnumKey(ulong,std::wstring &)
0x140029463  test    eax, eax
0x140029465  jz      loc_140029554
0x14002946b  lea     rdx, [rsp+0B8h+lpSubKey]
0x140029470  cmp     qword ptr [rsp+0B8h+var_48+8], 7
0x140029476  cmova   rdx, [rsp+0B8h+lpSubKey]; unsigned __int16 *
0x14002947c  lea     rcx, [rsp+0B8h+var_30]; this
0x140029484  call    ?Assign@VmGuid@Vml@@QEAAXQEBG@Z; Vml::VmGuid::Assign(ushort const * const)
0x140029489  mov     [rsp+0B8h+var_60], 0
0x140029492  lea     rdx, [rsp+0B8h+lpSubKey]
0x140029497  cmp     qword ptr [rsp+0B8h+var_48+8], 7
0x14002949d  cmova   rdx, [rsp+0B8h+lpSubKey]; lpSubKey
0x1400294a3  lea     rax, [rsp+0B8h+var_60]
0x1400294a8  mov     qword ptr [rsp+0B8h+phkResult], rax; unsigned int
0x1400294ad  mov     r9d, 20019h; samDesired
0x1400294b3  xor     r8d, r8d; ulOptions
0x1400294b6  mov     rcx, [rsp+0B8h+var_68]; hKey
0x1400294bb  call    cs:__imp_RegOpenKeyExW
0x1400294c2  nop     dword ptr [rax+rax+00h]
0x1400294c7  test    eax, 0FFFFFFFDh
0x1400294cc  jz      short loc_1400294EA
0x1400294ce  mov     rcx, [rsp+0B8h]; this
0x1400294d6  mov     r9d, eax; char *
0x1400294d9  lea     r8, aOnecoreVmCommo_108; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x1400294e0  mov     edx, 1F9h; void *
0x1400294e5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400294ea  lea     r8, [rsp+0B8h+var_30]
0x1400294f2  lea     rdx, [rsp+0B8h+var_78]
0x1400294f7  mov     rcx, rbx
0x1400294fa  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@UVDevClassInfo@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UVDevClassInfo@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UVDevClassInfo@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x1400294ff  mov     rdx, [rax]
0x140029502  add     rdx, 30h ; '0'; struct VDevClassInfo *
0x140029506  lea     rcx, [rsp+0B8h+var_60]; struct Vml::VmRegistryKey *
0x14002950b  call    ?ReadSingleVDevClassInfo@@YAXAEAVVmRegistryKey@Vml@@PEAUVDevClassInfo@@@Z; ReadSingleVDevClassInfo(Vml::VmRegistryKey &,VDevClassInfo *)
0x140029510  nop
0x140029511  mov     rcx, [rsp+0B8h+var_60]; hKey
0x140029516  test    rcx, rcx
0x140029519  jz      short loc_140029530
0x14002951b  call    cs:__imp_RegCloseKey
0x140029522  nop     dword ptr [rax+rax+00h]
0x140029527  mov     [rsp+0B8h+var_60], 0
0x140029530  mov     rdx, qword ptr [rsp+0B8h+var_48+8]
0x140029535  cmp     rdx, 7
0x140029539  jbe     short loc_14002954D
0x14002953b  lea     rdx, ds:2[rdx*2]
0x140029543  mov     rcx, [rsp+0B8h+lpSubKey]
0x140029548  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14002954d  inc     edi
0x14002954f  jmp     loc_14002943D
0x140029554  mov     rdx, qword ptr [rsp+0B8h+var_48+8]
0x140029559  cmp     rdx, 7
0x14002955d  jbe     short loc_140029572
0x14002955f  lea     rdx, ds:2[rdx*2]
0x140029567  mov     rcx, [rsp+0B8h+lpSubKey]
0x14002956c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140029571  nop
0x140029572  mov     rcx, [rsp+0B8h+var_68]; hKey
0x140029577  test    rcx, rcx
0x14002957a  jz      short loc_140029591
0x14002957c  call    cs:__imp_RegCloseKey
0x140029583  nop     dword ptr [rax+rax+00h]
0x140029588  mov     [rsp+0B8h+var_68], 0
0x140029591  mov     rcx, [rsp+0B8h+hKey]; hKey
0x140029599  test    rcx, rcx
0x14002959c  jz      short loc_1400295AA
0x14002959e  call    cs:__imp_RegCloseKey
0x1400295a5  nop     dword ptr [rax+rax+00h]
0x1400295aa  mov     rax, rbx
0x1400295ad  mov     rcx, [rsp+0B8h+var_20]
0x1400295b5  xor     rcx, rsp; StackCookie
0x1400295b8  call    __security_check_cookie
0x1400295bd  lea     r11, [rsp+0B8h+var_8]
0x1400295c5  mov     rbx, [r11+18h]
0x1400295c9  movaps  xmm6, xmmword ptr [r11-10h]
0x1400295ce  mov     rsp, r11
0x1400295d1  pop     rdi
0x1400295d2  retn
```
