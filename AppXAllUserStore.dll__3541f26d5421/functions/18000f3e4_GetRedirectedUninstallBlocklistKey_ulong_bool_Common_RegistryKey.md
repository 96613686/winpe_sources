# GetRedirectedUninstallBlocklistKey(ulong,bool,Common::RegistryKey *)

- ea: `0x18000f3e4`
- end: `0x18000f534`
- name: `?GetRedirectedUninstallBlocklistKey@@YAJK_NPEAVRegistryKey@Common@@@Z`
- size: `336`
- prototype: `int(unsigned int, bool, struct Common::RegistryKey *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b324`

## callees

- `0x180004940`
- `0x180004968`
- `0x180007860`
- `0x180007a10`
- `0x18000f3e4`
- `0x18000f53c`
- `0x180018248`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f468`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f4cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f468`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f4cc`

## string_xrefs

- `0x18000f41b`: `onecore\base\appmodel\common\appxuninstallblocklist.cpp`
- `0x18000f48a`: `onecore\base\appmodel\common\appxuninstallblocklist.cpp`
- `0x18000f4b0`: `EnterpriseUninstallBlockList`

## pseudocode

```c
__int64 __fastcall GetRedirectedUninstallBlocklistKey(__int64 a1, __int64 a2, HKEY *a3)
{
  int PersistedRegKeyPath; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  __int64 v7; // rdx
  HKEY v8; // rcx
  LSTATUS v9; // eax
  int phkResult; // [rsp+20h] [rbp-20h]
  int phkResulta; // [rsp+20h] [rbp-20h]
  LPCWSTR lpSubKey[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  HKEY hKey; // [rsp+68h] [rbp+28h] BYREF

  lpSubKey[0] = 0;
  PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(
                          (Common **)&Common::StateSeparation::AppxPolicies,
                          (unsigned __int16 **)lpSubKey);
  v5 = PersistedRegKeyPath;
  if ( PersistedRegKeyPath >= 0 )
  {
    hKey = 0;
    Common::AutoHandleCloseHKEY<HKEY__ *>(0);
    hKey = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 >= 0 )
    {
      Common::AutoHandleCloseHKEY<HKEY__ *>(*a3);
      v8 = hKey;
      *a3 = 0;
      v9 = RegOpenKeyExW(v8, L"EnterpriseUninstallBlockList", 0, 0x20019u, a3);
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      if ( v5 >= 0 )
      {
        Common::RegistryKey::~RegistryKey(&hKey);
        v5 = 0;
        goto LABEL_15;
      }
      if ( v5 == -2147024894 )
      {
        Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
        Common::GlobalHeap::Free((void *)lpSubKey[0]);
        return 2147942402LL;
      }
      v7 = 258;
    }
    else
    {
      v7 = 250;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\common\\appxuninstallblocklist.cpp",
      (const char *)(unsigned int)v5,
      phkResulta);
    Common::RegistryKey::~RegistryKey(&hKey);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF7,
      (unsigned int)"onecore\\base\\appmodel\\common\\appxuninstallblocklist.cpp",
      (const char *)(unsigned int)PersistedRegKeyPath,
      phkResult);
  }
LABEL_15:
  Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>((PVOID *)lpSubKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f3e4  mov     [rsp-8+arg_0], rbx
0x18000f3e9  mov     [rsp-8+arg_8], rdi
0x18000f3ee  push    rbp
0x18000f3ef  mov     rbp, rsp
0x18000f3f2  sub     rsp, 40h
0x18000f3f6  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x18000f3fa  mov     [rbp+lpSubKey], 0
0x18000f402  lea     rcx, ?AppxPolicies@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; struct Common::StateSeparationRedirectionMapping *
0x18000f409  mov     rdi, r8
0x18000f40c  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)
0x18000f411  mov     ebx, eax
0x18000f413  test    eax, eax
0x18000f415  jns     short loc_18000F434
0x18000f417  mov     rcx, [rbp+8]; this
0x18000f41b  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\appxun"...
0x18000f422  mov     r9d, eax; char *
0x18000f425  mov     edx, 0F7h; void *
0x18000f42a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f42f  jmp     loc_18000F519
0x18000f434  xor     ecx, ecx
0x18000f436  mov     [rbp+hKey], 0
0x18000f43e  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000f443  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18000f447  lea     rax, [rbp+hKey]
0x18000f44b  mov     r9d, 20019h; samDesired
0x18000f451  mov     qword ptr [rsp+40h+phkResult], rax; int
0x18000f456  xor     r8d, r8d; ulOptions
0x18000f459  mov     [rbp+hKey], 0
0x18000f461  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f468  call    cs:__imp_RegOpenKeyExW
0x18000f46e  mov     ebx, eax
0x18000f470  test    eax, eax
0x18000f472  jle     short loc_18000F47D
0x18000f474  movzx   ebx, ax
0x18000f477  or      ebx, 80070000h
0x18000f47d  test    ebx, ebx
0x18000f47f  jns     short loc_18000F4A4
0x18000f481  mov     edx, 0FAh; void *
0x18000f486  mov     rcx, [rbp+8]; this
0x18000f48a  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\appxun"...
0x18000f491  mov     r9d, ebx; char *
0x18000f494  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f499  lea     rcx, [rbp+hKey]; this
0x18000f49d  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18000f4a2  jmp     short loc_18000F519
0x18000f4a4  mov     rcx, [rdi]
0x18000f4a7  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000f4ac  mov     rcx, [rbp+hKey]; hKey
0x18000f4b0  lea     rdx, aEnterpriseunin; "EnterpriseUninstallBlockList"
0x18000f4b7  mov     r9d, 20019h; samDesired
0x18000f4bd  mov     qword ptr [rdi], 0
0x18000f4c4  xor     r8d, r8d; ulOptions
0x18000f4c7  mov     qword ptr [rsp+40h+phkResult], rdi; phkResult
0x18000f4cc  call    cs:__imp_RegOpenKeyExW
0x18000f4d2  mov     ebx, eax
0x18000f4d4  test    eax, eax
0x18000f4d6  jle     short loc_18000F4E1
0x18000f4d8  movzx   ebx, ax
0x18000f4db  or      ebx, 80070000h
0x18000f4e1  test    ebx, ebx
0x18000f4e3  jns     short loc_18000F50E
0x18000f4e5  mov     edi, 80070002h
0x18000f4ea  cmp     ebx, edi
0x18000f4ec  jnz     short loc_18000F504
0x18000f4ee  mov     rcx, [rbp+hKey]
0x18000f4f2  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000f4f7  mov     rcx, [rbp+lpSubKey]; void *
0x18000f4fb  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000f500  mov     eax, edi
0x18000f502  jmp     short loc_18000F524
0x18000f504  mov     edx, 102h
0x18000f509  jmp     loc_18000F486
0x18000f50e  lea     rcx, [rbp+hKey]; this
0x18000f512  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18000f517  xor     ebx, ebx
0x18000f519  lea     rcx, [rbp+lpSubKey]
0x18000f51d  call    ??1?$AutoArray@U_MainPackageInfo@AppxAllUserStore@@$1??$AutoArrayDeallocate@U_MainPackageInfo@AppxAllUserStore@@@Common@@YAXPEAU12@@Z@Common@@QEAA@XZ; Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(void)
0x18000f522  mov     eax, ebx
0x18000f524  mov     rbx, [rsp+40h+arg_0]
0x18000f529  mov     rdi, [rsp+40h+arg_8]
0x18000f52e  add     rsp, 40h
0x18000f532  pop     rbp
0x18000f533  retn
```
