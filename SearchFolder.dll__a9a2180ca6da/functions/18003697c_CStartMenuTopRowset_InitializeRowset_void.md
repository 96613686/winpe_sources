# CStartMenuTopRowset::_InitializeRowset(void)

- ea: `0x18003697c`
- end: `0x180036ae4`
- name: `?_InitializeRowset@CStartMenuTopRowset@@AEAAJXZ`
- size: `360`
- prototype: `__int64 __fastcall(CStartMenuTopRowset *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003974c`

## callees

- `0x18003697c`
- `0x18003a384`
- `0x18003a3b0`
- `0x18003ab9c`
- `0x18004a320`
- `0x180051010`

## import_xrefs

- `SHCORE!__imp_SHWindowsPolicy` at `0x180036a77`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180036a77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036a9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036a9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800369fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800369fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CStartMenuTopRowset::_InitializeRowset(CStartMenuTopRowset *this)
{
  HDPA v2; // rax
  __int64 v3; // rcx
  unsigned int v4; // esi
  int v5; // edi
  int v6; // r9d
  int ShouldQuery; // eax
  HKEY v8; // rcx
  int v9; // r9d
  int v10; // eax
  HKEY v11; // rcx
  int QueryCommSetting; // eax
  HKEY v13; // rcx
  int v14; // r9d
  HKEY v15; // rcx
  int QueryFilesSetting; // eax
  HKEY v17; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v2 = g_pfn_DPA_Create(8);
  *((_QWORD *)this + 23) = v2;
  if ( v2 )
  {
    v3 = *((_QWORD *)this + 9);
    v4 = 0;
    if ( v3 )
      (*(void (__fastcall **)(__int64, GUID *, char *))(*(_QWORD *)v3 + 24LL))(
        v3,
        &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
        (char *)this + 112);
  }
  else
  {
    v4 = -2147024882;
  }
  hKey = 0;
  v5 = 1;
  if ( RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
         0,
         1u,
         &hKey) )
  {
    *((_DWORD *)this + 54) = 1;
    *((_DWORD *)this + 55) = 1;
    *((_DWORD *)this + 57) = CStartMenuTopRowset::s_GetQueryCommSetting(0);
    *((_DWORD *)this + 56) = 1;
    *((_DWORD *)this + 52) = CStartMenuTopRowset::s_GetQueryFilesSetting(0);
  }
  else
  {
    ShouldQuery = CStartMenuTopRowset::s_ShouldQuery(
                    hKey,
                    L"Start_SearchPrograms",
                    &POLID_NoSearchProgramsInStartMenu,
                    v6);
    v8 = hKey;
    *((_DWORD *)this + 54) = ShouldQuery;
    v10 = CStartMenuTopRowset::s_ShouldQuery(v8, L"Start_SearchInternet", &POLID_NoSearchInternetInStartMenu, v9);
    v11 = hKey;
    *((_DWORD *)this + 55) = v10;
    QueryCommSetting = CStartMenuTopRowset::s_GetQueryCommSetting(v11);
    v13 = hKey;
    *((_DWORD *)this + 57) = QueryCommSetting;
    if ( !(unsigned int)CStartMenuTopRowset::s_ShouldQuery(v13, L"Start_SearchControlPanel", &POLID_NULL, v14)
      || (unsigned int)SHWindowsPolicy(POLID_NoControlPanel) )
    {
      v5 = 0;
    }
    v15 = hKey;
    *((_DWORD *)this + 56) = v5;
    QueryFilesSetting = CStartMenuTopRowset::s_GetQueryFilesSetting(v15);
    v17 = hKey;
    *((_DWORD *)this + 52) = QueryFilesSetting;
    RegCloseKey(v17);
  }
  return v4;
}

```

## disassembly

```asm
0x18003697c  mov     [rsp+arg_8], rbx
0x180036981  mov     [rsp+arg_10], rsi
0x180036986  push    rdi
0x180036987  sub     rsp, 30h
0x18003698b  mov     rbx, rcx
0x18003698e  mov     ecx, 8; cItemGrow
0x180036993  call    cs:g_pfn_DPA_Create
0x180036999  mov     [rbx+0B8h], rax
0x1800369a0  test    rax, rax
0x1800369a3  jz      short loc_1800369C9
0x1800369a5  mov     rcx, [rbx+48h]
0x1800369a9  xor     esi, esi
0x1800369ab  test    rcx, rcx
0x1800369ae  jz      short loc_1800369CE
0x1800369b0  mov     rax, [rcx]
0x1800369b3  lea     r8, [rbx+70h]
0x1800369b7  lea     rdx, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x1800369be  mov     rax, [rax+18h]
0x1800369c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369c7  jmp     short loc_1800369CE
0x1800369c9  mov     esi, 8007000Eh
0x1800369ce  lea     rax, [rsp+38h+hKey]
0x1800369d3  mov     [rsp+38h+hKey], 0
0x1800369dc  mov     edi, 1
0x1800369e1  mov     [rsp+38h+phkResult], rax; phkResult
0x1800369e6  mov     r9d, edi; samDesired
0x1800369e9  lea     rdx, pwszKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800369f0  xor     r8d, r8d; ulOptions
0x1800369f3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800369fa  call    cs:__imp_RegOpenKeyExW
0x180036a00  test    eax, eax
0x180036a02  jnz     loc_180036AA6
0x180036a08  mov     rcx, [rsp+38h+hKey]; hkey
0x180036a0d  lea     r8, POLID_NoSearchProgramsInStartMenu; struct _GUID *
0x180036a14  lea     rdx, aStartSearchpro; "Start_SearchPrograms"
0x180036a1b  call    ?s_ShouldQuery@CStartMenuTopRowset@@CAHPEAUHKEY__@@PEBGAEBU_GUID@@H@Z; CStartMenuTopRowset::s_ShouldQuery(HKEY__ *,ushort const *,_GUID const &,int)
0x180036a20  mov     rcx, [rsp+38h+hKey]; hkey
0x180036a25  lea     r8, POLID_NoSearchInternetInStartMenu; struct _GUID *
0x180036a2c  lea     rdx, aStartSearchint; "Start_SearchInternet"
0x180036a33  mov     [rbx+0D8h], eax
0x180036a39  call    ?s_ShouldQuery@CStartMenuTopRowset@@CAHPEAUHKEY__@@PEBGAEBU_GUID@@H@Z; CStartMenuTopRowset::s_ShouldQuery(HKEY__ *,ushort const *,_GUID const &,int)
0x180036a3e  mov     rcx, [rsp+38h+hKey]; HKEY
0x180036a43  mov     [rbx+0DCh], eax
0x180036a49  call    ?s_GetQueryCommSetting@CStartMenuTopRowset@@SAHPEAUHKEY__@@@Z; CStartMenuTopRowset::s_GetQueryCommSetting(HKEY__ *)
0x180036a4e  mov     rcx, [rsp+38h+hKey]; hkey
0x180036a53  lea     r8, POLID_NULL; struct _GUID *
0x180036a5a  lea     rdx, aStartSearchcon; "Start_SearchControlPanel"
0x180036a61  mov     [rbx+0E4h], eax
0x180036a67  call    ?s_ShouldQuery@CStartMenuTopRowset@@CAHPEAUHKEY__@@PEBGAEBU_GUID@@H@Z; CStartMenuTopRowset::s_ShouldQuery(HKEY__ *,ushort const *,_GUID const &,int)
0x180036a6c  test    eax, eax
0x180036a6e  jz      short loc_180036A81
0x180036a70  lea     rcx, POLID_NoControlPanel
0x180036a77  call    cs:__imp_SHWindowsPolicy
0x180036a7d  test    eax, eax
0x180036a7f  jz      short loc_180036A83
0x180036a81  xor     edi, edi
0x180036a83  mov     rcx, [rsp+38h+hKey]
0x180036a88  mov     [rbx+0E0h], edi
0x180036a8e  call    ?s_GetQueryFilesSetting@CStartMenuTopRowset@@SA?AW4_QUERY_FILES@@PEAUHKEY__@@@Z; CStartMenuTopRowset::s_GetQueryFilesSetting(HKEY__ *)
0x180036a93  mov     rcx, [rsp+38h+hKey]; hKey
0x180036a98  mov     [rbx+0D0h], eax
0x180036a9e  call    cs:__imp_RegCloseKey
0x180036aa4  jmp     short loc_180036AD2
0x180036aa6  xor     ecx, ecx; HKEY
0x180036aa8  mov     [rbx+0D8h], edi
0x180036aae  mov     [rbx+0DCh], edi
0x180036ab4  call    ?s_GetQueryCommSetting@CStartMenuTopRowset@@SAHPEAUHKEY__@@@Z; CStartMenuTopRowset::s_GetQueryCommSetting(HKEY__ *)
0x180036ab9  xor     ecx, ecx
0x180036abb  mov     [rbx+0E4h], eax
0x180036ac1  mov     [rbx+0E0h], edi
0x180036ac7  call    ?s_GetQueryFilesSetting@CStartMenuTopRowset@@SA?AW4_QUERY_FILES@@PEAUHKEY__@@@Z; CStartMenuTopRowset::s_GetQueryFilesSetting(HKEY__ *)
0x180036acc  mov     [rbx+0D0h], eax
0x180036ad2  mov     rbx, [rsp+38h+arg_8]
0x180036ad7  mov     eax, esi
0x180036ad9  mov     rsi, [rsp+38h+arg_10]
0x180036ade  add     rsp, 30h
0x180036ae2  pop     rdi
0x180036ae3  retn
```
