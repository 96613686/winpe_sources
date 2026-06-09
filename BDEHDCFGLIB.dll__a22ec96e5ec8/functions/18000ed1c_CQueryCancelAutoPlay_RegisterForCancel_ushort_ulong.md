# CQueryCancelAutoPlay::RegisterForCancel(ushort,ulong *)

- ea: `0x18000ed1c`
- end: `0x18000f01e`
- name: `?RegisterForCancel@CQueryCancelAutoPlay@@SAJGPEAK@Z`
- size: `770`
- prototype: `__int64 __fastcall(unsigned __int16, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800101a0`

## callees

- `0x1800015c4`
- `0x180006c30`
- `0x18000ed1c`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000ee4d`
- `ADVAPI32!RegCloseKey` at `0x18000eeda`
- `ADVAPI32!RegCloseKey` at `0x18000eee5`
- `ADVAPI32!RegCloseKey` at `0x18000ee4d`
- `ADVAPI32!RegCloseKey` at `0x18000eeda`
- `ADVAPI32!RegCloseKey` at `0x18000eee5`
- `ADVAPI32!RegSetValueExW` at `0x18000ee42`
- `ADVAPI32!RegSetValueExW` at `0x18000eecf`
- `ADVAPI32!RegSetValueExW` at `0x18000ee42`
- `ADVAPI32!RegSetValueExW` at `0x18000eecf`
- `ADVAPI32!RegCreateKeyExW` at `0x18000ee12`
- `ADVAPI32!RegCreateKeyExW` at `0x18000eea6`
- `ADVAPI32!RegCreateKeyExW` at `0x18000ee12`
- `ADVAPI32!RegCreateKeyExW` at `0x18000eea6`
- `ADVAPI32!RegSetKeyValueW` at `0x18000edab`
- `ADVAPI32!RegSetKeyValueW` at `0x18000edab`
- `ADVAPI32!RegOpenKeyExW` at `0x18000edce`
- `ADVAPI32!RegOpenKeyExW` at `0x18000edce`
- `KERNEL32!GetCurrentProcess` at `0x18000ee53`
- `KERNEL32!GetCurrentProcess` at `0x18000ee53`
- `KERNEL32!K32GetModuleBaseNameW` at `0x18000ee6c`
- `KERNEL32!K32GetModuleBaseNameW` at `0x18000ee6c`
- `ole32!CreateClassMoniker` at `0x18000eef7`
- `ole32!CreateClassMoniker` at `0x18000eef7`
- `ole32!GetRunningObjectTable` at `0x18000ef0e`
- `ole32!GetRunningObjectTable` at `0x18000ef0e`

## string_xrefs

- `0x18000ed9a`: `Software\Microsoft\Windows\CurrentVersion\explorer\AutoplayHandlers\CancelAutoplay\CLSID`

## pseudocode

```c
__int64 __fastcall CQueryCancelAutoPlay::RegisterForCancel(unsigned __int16 a1, unsigned int *a2)
{
  unsigned int v3; // esi
  unsigned __int16 *v4; // rbx
  HANDLE CurrentProcess; // rax
  HRESULT RunningObjectTable; // edi
  LPRUNNINGOBJECTTABLE pprot; // [rsp+50h] [rbp-278h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-270h] BYREF
  LPMONIKER ppmk; // [rsp+60h] [rbp-268h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-260h] BYREF
  HKEY v12; // [rsp+70h] [rbp-258h] BYREF
  unsigned __int16 *v13; // [rsp+78h] [rbp-250h]
  WCHAR BaseName[264]; // [rsp+80h] [rbp-248h] BYREF

  v3 = a1;
  v4 = 0;
  v13 = 0;
  ppmk = 0;
  pprot = 0;
  phkResult = 0;
  hKey = 0;
  v12 = 0;
  memset_0(BaseName, 0, 0x208u);
  RegSetKeyValueW(
    HKEY_LOCAL_MACHINE,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\explorer\\AutoplayHandlers\\CancelAutoplay\\CLSID",
    L"c87f39e0-fd44-41bc-8a81-38b2dab691ff",
    1u,
    0,
    0);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\AppID", 0, 0x20006u, &phkResult) )
  {
    if ( !RegCreateKeyExW(phkResult, L"{d056ebce-e7e9-4994-a5e6-de59430306c1}", 0, 0, 1u, 2u, 0, &hKey, 0) )
    {
      RegSetValueExW(hKey, L"RunAs", 0, 1u, L"Interactive User", 0x22u);
      RegCloseKey(hKey);
    }
    CurrentProcess = GetCurrentProcess();
    K32GetModuleBaseNameW(CurrentProcess, 0, BaseName, 0x104u);
    if ( !RegCreateKeyExW(phkResult, BaseName, 0, 0, 1u, 2u, 0, &v12, 0) )
    {
      RegSetValueExW(v12, L"AppId", 0, 1u, (const BYTE *)L"{d056ebce-e7e9-4994-a5e6-de59430306c1}", 0x4Eu);
      RegCloseKey(v12);
    }
    RegCloseKey(phkResult);
  }
  RunningObjectTable = CreateClassMoniker(&CQueryCancelAutoPlay::_clsid, &ppmk);
  if ( RunningObjectTable >= 0 )
  {
    RunningObjectTable = GetRunningObjectTable(0, &pprot);
    if ( RunningObjectTable >= 0 )
    {
      v4 = (unsigned __int16 *)operator new(0x218u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v4 )
      {
        *(_QWORD *)v4 = &CQueryCancelAutoPlay::`vftable';
        *((_DWORD *)v4 + 2) = 1;
        memset_0(v4 + 6, 0, 0x208u);
      }
      else
      {
        v4 = 0;
      }
      v13 = v4;
      if ( v4 )
      {
        RunningObjectTable = StringCchPrintfW(v4 + 6, 0x104u, L"%c:\\", v3);
        if ( RunningObjectTable >= 0 )
          RunningObjectTable = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, __int64, unsigned __int16 *, LPMONIKER, unsigned int *))pprot->lpVtbl->Register)(
                                 pprot,
                                 3,
                                 v4,
                                 ppmk,
                                 a2);
      }
      else
      {
        RunningObjectTable = -2147024882;
      }
    }
  }
  if ( v4 )
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( pprot )
  {
    ((void (__fastcall *)(LPRUNNINGOBJECTTABLE))pprot->lpVtbl->Release)(pprot);
    pprot = 0;
  }
  if ( ppmk )
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
  return (unsigned int)RunningObjectTable;
}

```

## disassembly

```asm
0x18000ed1c  mov     [rsp+arg_10], rbx
0x18000ed21  push    rsi
0x18000ed22  push    rdi
0x18000ed23  push    r12
0x18000ed25  push    r14
0x18000ed27  push    r15
0x18000ed29  sub     rsp, 2A0h
0x18000ed30  mov     rax, cs:__security_cookie
0x18000ed37  xor     rax, rsp
0x18000ed3a  mov     [rsp+2C8h+var_38], rax
0x18000ed42  mov     r14, rdx
0x18000ed45  movzx   esi, cx
0x18000ed48  xor     r15d, r15d
0x18000ed4b  mov     ebx, r15d
0x18000ed4e  mov     [rsp+2C8h+var_250], rbx
0x18000ed53  mov     [rsp+2C8h+ppmk], r15
0x18000ed58  mov     [rsp+2C8h+pprot], r15
0x18000ed5d  mov     [rsp+2C8h+phkResult], r15
0x18000ed62  mov     [rsp+2C8h+hKey], r15
0x18000ed67  mov     [rsp+2C8h+var_258], r15
0x18000ed6c  xor     edx, edx; Val
0x18000ed6e  mov     r8d, 208h; Size
0x18000ed74  lea     rcx, [rsp+2C8h+BaseName]; void *
0x18000ed7c  call    memset_0
0x18000ed81  nop
0x18000ed82  mov     [rsp+2C8h+cbData], r15d; cbData
0x18000ed87  mov     [rsp+2C8h+lpData], r15; lpData
0x18000ed8c  lea     r12d, [r15+1]
0x18000ed90  mov     r9d, r12d; dwType
0x18000ed93  lea     r8, ValueName; "c87f39e0-fd44-41bc-8a81-38b2dab691ff"
0x18000ed9a  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000eda1  mov     rdi, 0FFFFFFFF80000002h
0x18000eda8  mov     rcx, rdi; hKey
0x18000edab  call    cs:__imp_RegSetKeyValueW
0x18000edb1  lea     rax, [rsp+2C8h+phkResult]
0x18000edb6  mov     [rsp+2C8h+lpData], rax; phkResult
0x18000edbb  mov     r9d, 20006h; samDesired
0x18000edc1  xor     r8d, r8d; ulOptions
0x18000edc4  lea     rdx, aSoftwareClasse; "Software\\Classes\\AppID"
0x18000edcb  mov     rcx, rdi; hKey
0x18000edce  call    cs:__imp_RegOpenKeyExW
0x18000edd4  test    eax, eax
0x18000edd6  jnz     loc_18000EEEB
0x18000eddc  mov     [rsp+2C8h+lpdwDisposition], r15; lpdwDisposition
0x18000ede1  lea     rax, [rsp+2C8h+hKey]
0x18000ede6  mov     [rsp+2C8h+var_290], rax; phkResult
0x18000edeb  mov     [rsp+2C8h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000edf0  mov     [rsp+2C8h+cbData], 2; samDesired
0x18000edf8  mov     dword ptr [rsp+2C8h+lpData], r12d; dwOptions
0x18000edfd  xor     r9d, r9d; lpClass
0x18000ee00  xor     r8d, r8d; Reserved
0x18000ee03  lea     rdi, aD056ebceE7e949; "{d056ebce-e7e9-4994-a5e6-de59430306c1}"
0x18000ee0a  mov     rdx, rdi; lpSubKey
0x18000ee0d  mov     rcx, [rsp+2C8h+phkResult]; hKey
0x18000ee12  call    cs:__imp_RegCreateKeyExW
0x18000ee18  test    eax, eax
0x18000ee1a  jnz     short loc_18000EE53
0x18000ee1c  mov     [rsp+2C8h+cbData], 22h ; '"'; cbData
0x18000ee24  lea     rax, Data; "Interactive User"
0x18000ee2b  mov     [rsp+2C8h+lpData], rax; lpData
0x18000ee30  mov     r9d, r12d; dwType
0x18000ee33  xor     r8d, r8d; Reserved
0x18000ee36  lea     rdx, aRunas; "RunAs"
0x18000ee3d  mov     rcx, [rsp+2C8h+hKey]; hKey
0x18000ee42  call    cs:__imp_RegSetValueExW
0x18000ee48  mov     rcx, [rsp+2C8h+hKey]; hKey
0x18000ee4d  call    cs:__imp_RegCloseKey
0x18000ee53  call    cs:__imp_GetCurrentProcess
0x18000ee59  mov     rcx, rax; hProcess
0x18000ee5c  mov     r9d, 104h; nSize
0x18000ee62  lea     r8, [rsp+2C8h+BaseName]; lpBaseName
0x18000ee6a  xor     edx, edx; hModule
0x18000ee6c  call    cs:__imp_K32GetModuleBaseNameW
0x18000ee72  mov     [rsp+2C8h+lpdwDisposition], r15; lpdwDisposition
0x18000ee77  lea     rax, [rsp+2C8h+var_258]
0x18000ee7c  mov     [rsp+2C8h+var_290], rax; phkResult
0x18000ee81  mov     [rsp+2C8h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000ee86  mov     [rsp+2C8h+cbData], 2; samDesired
0x18000ee8e  mov     dword ptr [rsp+2C8h+lpData], r12d; dwOptions
0x18000ee93  xor     r9d, r9d; lpClass
0x18000ee96  xor     r8d, r8d; Reserved
0x18000ee99  lea     rdx, [rsp+2C8h+BaseName]; lpSubKey
0x18000eea1  mov     rcx, [rsp+2C8h+phkResult]; hKey
0x18000eea6  call    cs:__imp_RegCreateKeyExW
0x18000eeac  test    eax, eax
0x18000eeae  jnz     short loc_18000EEE0
0x18000eeb0  mov     [rsp+2C8h+cbData], 4Eh ; 'N'; cbData
0x18000eeb8  mov     [rsp+2C8h+lpData], rdi; lpData
0x18000eebd  mov     r9d, r12d; dwType
0x18000eec0  xor     r8d, r8d; Reserved
0x18000eec3  lea     rdx, aAppid; "AppId"
0x18000eeca  mov     rcx, [rsp+2C8h+var_258]; hKey
0x18000eecf  call    cs:__imp_RegSetValueExW
0x18000eed5  mov     rcx, [rsp+2C8h+var_258]; hKey
0x18000eeda  call    cs:__imp_RegCloseKey
0x18000eee0  mov     rcx, [rsp+2C8h+phkResult]; hKey
0x18000eee5  call    cs:__imp_RegCloseKey
0x18000eeeb  lea     rdx, [rsp+2C8h+ppmk]; ppmk
0x18000eef0  lea     rcx, ?_clsid@CQueryCancelAutoPlay@@0U_GUID@@B; rclsid
0x18000eef7  call    cs:__imp_CreateClassMoniker
0x18000eefd  mov     edi, eax
0x18000eeff  test    eax, eax
0x18000ef01  js      loc_18000EFAF
0x18000ef07  lea     rdx, [rsp+2C8h+pprot]; pprot
0x18000ef0c  xor     ecx, ecx; reserved
0x18000ef0e  call    cs:__imp_GetRunningObjectTable
0x18000ef14  mov     edi, eax
0x18000ef16  test    eax, eax
0x18000ef18  js      loc_18000EFAF
0x18000ef1e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ef25  mov     ecx, 218h; unsigned __int64
0x18000ef2a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ef2f  mov     rbx, rax
0x18000ef32  test    rax, rax
0x18000ef35  jz      short loc_18000EF58
0x18000ef37  lea     rax, ??_7CQueryCancelAutoPlay@@6B@; const CQueryCancelAutoPlay::`vftable'
0x18000ef3e  mov     [rbx], rax
0x18000ef41  mov     [rbx+8], r12d
0x18000ef45  lea     rcx, [rbx+0Ch]; void *
0x18000ef49  xor     edx, edx; Val
0x18000ef4b  mov     r8d, 208h; Size
0x18000ef51  call    memset_0
0x18000ef56  jmp     short loc_18000EF5B
0x18000ef58  mov     rbx, r15
0x18000ef5b  mov     [rsp+2C8h+var_250], rbx
0x18000ef60  test    rbx, rbx
0x18000ef63  jnz     short loc_18000EF6C
0x18000ef65  mov     edi, 8007000Eh
0x18000ef6a  jmp     short loc_18000EFAF
0x18000ef6c  mov     r9d, esi
0x18000ef6f  lea     rcx, [rbx+0Ch]; unsigned __int16 *
0x18000ef73  lea     r8, aC; "%c:\\"
0x18000ef7a  mov     edx, 104h; unsigned __int64
0x18000ef7f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ef84  mov     edi, eax
0x18000ef86  test    eax, eax
0x18000ef88  js      short loc_18000EFAF
0x18000ef8a  mov     rcx, [rsp+2C8h+pprot]
0x18000ef8f  mov     rax, [rcx]
0x18000ef92  mov     [rsp+2C8h+lpData], r14
0x18000ef97  mov     r9, [rsp+2C8h+ppmk]
0x18000ef9c  mov     r8, rbx
0x18000ef9f  mov     edx, 3
0x18000efa4  mov     rax, [rax+18h]
0x18000efa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efad  mov     edi, eax
0x18000efaf  test    rbx, rbx
0x18000efb2  jz      short loc_18000EFC3
0x18000efb4  mov     rax, [rbx]
0x18000efb7  mov     rcx, rbx
0x18000efba  mov     rax, [rax+10h]
0x18000efbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efc3  mov     rcx, [rsp+2C8h+pprot]
0x18000efc8  test    rcx, rcx
0x18000efcb  jz      short loc_18000EFDE
0x18000efcd  mov     rax, [rcx]
0x18000efd0  mov     rax, [rax+10h]
0x18000efd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efd9  mov     [rsp+2C8h+pprot], r15
0x18000efde  mov     rcx, [rsp+2C8h+ppmk]
0x18000efe3  test    rcx, rcx
0x18000efe6  jz      short loc_18000EFF4
0x18000efe8  mov     rax, [rcx]
0x18000efeb  mov     rax, [rax+10h]
0x18000efef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eff4  mov     eax, edi
0x18000eff6  mov     rcx, [rsp+2C8h+var_38]
0x18000effe  xor     rcx, rsp; StackCookie
0x18000f001  call    __security_check_cookie
0x18000f006  mov     rbx, [rsp+2C8h+arg_10]
0x18000f00e  add     rsp, 2A0h
0x18000f015  pop     r15
0x18000f017  pop     r14
0x18000f019  pop     r12
0x18000f01b  pop     rdi
0x18000f01c  pop     rsi
0x18000f01d  retn
0x180014342  push    rbp
0x180014344  sub     rsp, 50h
0x180014348  mov     rbp, rdx
0x18001434b  mov     rcx, [rbp+78h]
0x18001434f  test    rcx, rcx
0x180014352  jz      short loc_180014368
0x180014354  mov     rax, [rcx]
0x180014357  mov     rax, [rax+10h]
0x18001435b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014360  mov     qword ptr [rbp+78h], 0
0x180014368  mov     rcx, [rbp+50h]
0x18001436c  test    rcx, rcx
0x18001436f  jz      short loc_180014385
0x180014371  mov     rax, [rcx]
0x180014374  mov     rax, [rax+10h]
0x180014378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001437d  mov     qword ptr [rbp+50h], 0
0x180014385  mov     rcx, [rbp+60h]
0x180014389  test    rcx, rcx
0x18001438c  jz      short loc_18001439B
0x18001438e  mov     rax, [rcx]
0x180014391  mov     rax, [rax+10h]
0x180014395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001439a  nop
0x18001439b  add     rsp, 50h
0x18001439f  pop     rbp
0x1800143a0  retn
```
