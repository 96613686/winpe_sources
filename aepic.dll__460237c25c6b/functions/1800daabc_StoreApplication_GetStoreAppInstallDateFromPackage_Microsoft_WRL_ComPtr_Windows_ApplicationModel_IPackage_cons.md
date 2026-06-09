# StoreApplication::GetStoreAppInstallDateFromPackage(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)

- ea: `0x1800daabc`
- end: `0x1800dac85`
- name: `?GetStoreAppInstallDateFromPackage@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@@Z`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800dc88c`

## callees

- `0x180005890`
- `0x18000faf0`
- `0x18001b434`
- `0x1800295dc`
- `0x1800daabc`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800dabd3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800dabd3`

## string_xrefs

- `0x1800dab77`: `IPackage3::get_InstalledDate() failed`
- `0x1800dab1d`: `StoreApplication::GetStoreAppInstallDateFromPackage`
- `0x1800dab84`: `StoreApplication::GetStoreAppInstallDateFromPackage`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
FILETIME __fastcall StoreApplication::GetStoreAppInstallDateFromPackage(FILETIME a1, _QWORD *a2)
{
  __int64 v3; // rcx
  void (*v4)(void); // rax
  __int64 v5; // rcx
  int wMonth; // [rsp+30h] [rbp-39h]
  int wDay; // [rsp+38h] [rbp-31h]
  int wYear; // [rsp+40h] [rbp-29h]
  int wHour; // [rsp+48h] [rbp-21h]
  int wMinute; // [rsp+50h] [rbp-19h]
  int wSecond; // [rsp+58h] [rbp-11h]
  __int64 v13; // [rsp+60h] [rbp-9h] BYREF
  FILETIME v14; // [rsp+68h] [rbp-1h] BYREF
  FILETIME FileTime; // [rsp+70h] [rbp+7h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp+17h] BYREF
  unsigned __int16 v17[8]; // [rsp+90h] [rbp+27h] BYREF
  __int128 v18; // [rsp+A0h] [rbp+37h]
  __int64 v19; // [rsp+B0h] [rbp+47h]

  FileTime = a1;
  v14 = 0;
  v13 = 0;
  if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*a2)(*a2, &GUID_5f738b61_f86a_4917_93d1_f1ee9d3b35d9, &v13) < 0 )
  {
    AslLogCallPrintf(3, "StoreApplication::GetStoreAppInstallDateFromPackage", 848, "QueryInterface(IPackage3) failed");
    ((void (__fastcall *)(_QWORD, _QWORD))std::wstring::wstring)(a1, &pszFormat);
    goto LABEL_3;
  }
  if ( (*(int (__fastcall **)(__int64, FILETIME *))(*(_QWORD *)v13 + 56LL))(v13, &v14) < 0 )
  {
    AslLogCallPrintf(
      3,
      "StoreApplication::GetStoreAppInstallDateFromPackage",
      855,
      "IPackage3::get_InstalledDate() failed");
    ((void (__fastcall *)(_QWORD, _QWORD))std::wstring::wstring)(a1, &pszFormat);
LABEL_3:
    v3 = v13;
    if ( v13 )
    {
      v13 = 0;
      v4 = *(void (**)(void))(*(_QWORD *)v3 + 16LL);
LABEL_11:
      v4();
      return a1;
    }
    return a1;
  }
  FileTime = v14;
  SystemTime = 0;
  *(_OWORD *)v17 = 0;
  v18 = 0;
  v19 = 0;
  if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
  {
    wSecond = SystemTime.wSecond;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    wYear = SystemTime.wYear;
    wDay = SystemTime.wDay;
    wMonth = SystemTime.wMonth;
    StringCchPrintfExW(
      v17,
      0x14u,
      0,
      0,
      0x800u,
      L"%02hd/%02hd/%04hd %02hd:%02hd:%02hd",
      wMonth,
      wDay,
      wYear,
      wHour,
      wMinute,
      wSecond);
  }
  ((void (__fastcall *)(_QWORD, _QWORD))std::wstring::wstring)(a1, v17);
  v5 = v13;
  if ( v13 )
  {
    v13 = 0;
    v4 = *(void (**)(void))(*(_QWORD *)v5 + 16LL);
    goto LABEL_11;
  }
  return a1;
}

```

## disassembly

```asm
0x1800daabc  mov     [rsp-8+arg_10], rbx
0x1800daac1  push    rbp
0x1800daac2  lea     rbp, [rsp-57h]
0x1800daac7  sub     rsp, 0C0h
0x1800daace  mov     rax, cs:__security_cookie
0x1800daad5  xor     rax, rsp
0x1800daad8  mov     [rbp+57h+var_8], rax
0x1800daadc  mov     rbx, rcx
0x1800daadf  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rcx
0x1800daae3  mov     [rbp+57h+var_58], 0
0x1800daaeb  mov     [rbp+57h+var_60], 0
0x1800daaf3  mov     rcx, [rdx]
0x1800daaf6  mov     rax, [rcx]
0x1800daaf9  lea     r8, [rbp+57h+var_60]
0x1800daafd  lea     rdx, _GUID_5f738b61_f86a_4917_93d1_f1ee9d3b35d9
0x1800dab04  mov     rax, [rax]
0x1800dab07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dab0c  test    eax, eax
0x1800dab0e  jns     short loc_1800DAB5F
0x1800dab10  lea     r9, aQueryinterface; "QueryInterface(IPackage3) failed"
0x1800dab17  mov     r8d, 350h
0x1800dab1d  lea     rdx, aStoreapplicati; "StoreApplication::GetStoreAppInstallDat"...
0x1800dab24  mov     ecx, 3
0x1800dab29  call    AslLogCallPrintf
0x1800dab2e  lea     rdx, pszFormat
0x1800dab35  mov     rcx, rbx
0x1800dab38  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dab3d  nop
0x1800dab3e  mov     rcx, [rbp+57h+var_60]
0x1800dab42  test    rcx, rcx
0x1800dab45  jz      loc_1800DAC65
0x1800dab4b  mov     [rbp+57h+var_60], 0
0x1800dab53  mov     rax, [rcx]
0x1800dab56  mov     rax, [rax+10h]
0x1800dab5a  jmp     loc_1800DAC5F
0x1800dab5f  mov     rcx, [rbp+57h+var_60]
0x1800dab63  mov     rax, [rcx]
0x1800dab66  lea     rdx, [rbp+57h+var_58]
0x1800dab6a  mov     rax, [rax+38h]
0x1800dab6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dab73  test    eax, eax
0x1800dab75  jns     short loc_1800DABA7
0x1800dab77  lea     r9, aIpackage3GetIn; "IPackage3::get_InstalledDate() failed"
0x1800dab7e  mov     r8d, 357h
0x1800dab84  lea     rdx, aStoreapplicati; "StoreApplication::GetStoreAppInstallDat"...
0x1800dab8b  mov     ecx, 3
0x1800dab90  call    AslLogCallPrintf
0x1800dab95  lea     rdx, pszFormat
0x1800dab9c  mov     rcx, rbx
0x1800dab9f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800daba4  nop
0x1800daba5  jmp     short loc_1800DAB3E
0x1800daba7  mov     eax, dword ptr [rbp+57h+var_58]
0x1800dabaa  mov     ecx, dword ptr [rbp+57h+var_58+4]
0x1800dabad  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x1800dabb0  mov     [rbp+57h+FileTime.dwHighDateTime], ecx
0x1800dabb3  xorps   xmm0, xmm0
0x1800dabb6  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800dabba  xorps   xmm1, xmm1
0x1800dabbd  xor     eax, eax
0x1800dabbf  movups  xmmword ptr [rbp+57h+var_30], xmm1
0x1800dabc3  movups  [rbp+57h+var_20], xmm1
0x1800dabc7  mov     [rbp+57h+var_10], rax
0x1800dabcb  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x1800dabcf  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x1800dabd3  call    cs:__imp_FileTimeToSystemTime
0x1800dabd9  test    eax, eax
0x1800dabdb  jz      short loc_1800DAC3A
0x1800dabdd  movzx   eax, [rbp+57h+SystemTime.wSecond]
0x1800dabe1  movzx   ecx, [rbp+57h+SystemTime.wMinute]
0x1800dabe5  movzx   edx, [rbp+57h+SystemTime.wHour]
0x1800dabe9  movzx   r8d, [rbp+57h+SystemTime.wYear]
0x1800dabee  movzx   r9d, [rbp+57h+SystemTime.wDay]
0x1800dabf3  movzx   r10d, [rbp+57h+SystemTime.wMonth]
0x1800dabf8  mov     [rsp+0C0h+var_68], eax
0x1800dabfc  mov     [rsp+0C0h+var_70], ecx
0x1800dac00  mov     [rsp+0C0h+var_78], edx
0x1800dac04  mov     [rsp+0C0h+var_80], r8d
0x1800dac09  mov     [rsp+0C0h+var_88], r9d
0x1800dac0e  mov     [rsp+0C0h+var_90], r10d
0x1800dac13  lea     rax, a02hd02hd04hd02; "%02hd/%02hd/%04hd %02hd:%02hd:%02hd"
0x1800dac1a  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x1800dac1f  mov     [rsp+0C0h+dwFlags], 800h; dwFlags
0x1800dac27  xor     r9d, r9d; unsigned __int64 *
0x1800dac2a  xor     r8d, r8d; unsigned __int16 **
0x1800dac2d  lea     edx, [r9+14h]; unsigned __int64
0x1800dac31  lea     rcx, [rbp+57h+var_30]; unsigned __int16 *
0x1800dac35  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800dac3a  lea     rdx, [rbp+57h+var_30]
0x1800dac3e  mov     rcx, rbx
0x1800dac41  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dac46  nop
0x1800dac47  mov     rcx, [rbp+57h+var_60]
0x1800dac4b  test    rcx, rcx
0x1800dac4e  jz      short loc_1800DAC65
0x1800dac50  mov     [rbp+57h+var_60], 0
0x1800dac58  mov     rdx, [rcx]
0x1800dac5b  mov     rax, [rdx+10h]
0x1800dac5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dac64  nop
0x1800dac65  mov     rax, rbx
0x1800dac68  mov     rcx, [rbp+57h+var_8]
0x1800dac6c  xor     rcx, rsp; StackCookie
0x1800dac6f  call    __security_check_cookie
0x1800dac74  mov     rbx, [rsp+0C0h+arg_10]
0x1800dac7c  add     rsp, 0C0h
0x1800dac83  pop     rbp
0x1800dac84  retn
```
