# SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting::GetValue(HSTRING__ *,IInspectable * *)

- ea: `0x180019900`
- end: `0x180019bac`
- name: `?GetValue@CPointInTimeRestoreMaxDiskUsageSetting@PointInTimeRestore@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `684`
- prototype: `int(SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000b784`
- `0x180019900`
- `0x180021a30`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019942`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800199fc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019a90`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019b06`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019942`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800199fc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019a90`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019b06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019920`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800199de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019a72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019ae8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019920`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800199de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019a72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019ae8`

## string_xrefs

- `0x1800199ad`: `Failed to create UInt32 for Value`
- `0x180019a41`: `Failed to create UInt32 for MaxValue`
- `0x180019ad2`: `Failed to create UInt32 for MinValue`
- `0x180019b47`: `Failed to create UInt32 for DefaultValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting::GetValue(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting *this,
        HSTRING a2,
        struct IInspectable **a3)
{
  const WCHAR *StringRawBuffer; // rax
  unsigned int v7; // edi
  unsigned int v8; // eax
  int PVStatics; // esi
  const char *v10; // rax
  __int64 v11; // rdx
  const WCHAR *v13; // rax
  int v14; // edi
  const char *v15; // rax
  __int64 v16; // rdx
  const WCHAR *v17; // rax
  const WCHAR *v18; // rax
  int v19; // ebx
  const char *v20; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a3 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v7 = 2;
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"Value", -1, 0) == 2 )
  {
    v8 = (*(__int64 (__fastcall **)(SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting *))(*(_QWORD *)this + 264LL))(this);
    if ( v8 >= 2 )
    {
      v7 = v8;
      if ( v8 > 0x32 )
        v7 = 50;
    }
    PVStatics = SystemSettings::DataModel::PropValueHelper::_GetPVStatics();
    if ( PVStatics < 0
      || (PVStatics = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValueStatics *, _QWORD, struct IInspectable **))(*(_QWORD *)SystemSettings::DataModel::PropValueHelper::_pPVStatics + 88LL))(
                        SystemSettings::DataModel::PropValueHelper::_pPVStatics,
                        v7,
                        a3),
          PVStatics < 0) )
    {
      *a3 = 0;
    }
    if ( PVStatics < 0 )
    {
      v10 = "Failed to create UInt32 for Value";
      v11 = 1329;
LABEL_10:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v11,
        (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
        (const char *)(unsigned int)PVStatics,
        (int)v10,
        v20);
      return (unsigned int)PVStatics;
    }
    return 0;
  }
  v13 = WindowsGetStringRawBuffer(a2, 0);
  if ( CompareStringOrdinal(v13, -1, L"MaxValue", -1, 0) == 2 )
  {
    v14 = SystemSettings::DataModel::PropValueHelper::_GetPVStatics();
    if ( v14 < 0
      || (v14 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValueStatics *, __int64, struct IInspectable **))(*(_QWORD *)SystemSettings::DataModel::PropValueHelper::_pPVStatics + 88LL))(
                  SystemSettings::DataModel::PropValueHelper::_pPVStatics,
                  50,
                  a3),
          v14 < 0) )
    {
      *a3 = 0;
    }
    if ( v14 < 0 )
    {
      v15 = "Failed to create UInt32 for MaxValue";
      v16 = 1333;
LABEL_17:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v16,
        (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
        (const char *)(unsigned int)v14,
        (int)v15,
        v20);
      return (unsigned int)v14;
    }
  }
  else
  {
    v17 = WindowsGetStringRawBuffer(a2, 0);
    if ( CompareStringOrdinal(v17, -1, L"MinValue", -1, 0) == 2 )
    {
      PVStatics = SystemSettings::DataModel::PropValueHelper::_GetPVStatics();
      if ( PVStatics < 0
        || (PVStatics = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValueStatics *, __int64, struct IInspectable **))(*(_QWORD *)SystemSettings::DataModel::PropValueHelper::_pPVStatics + 88LL))(
                          SystemSettings::DataModel::PropValueHelper::_pPVStatics,
                          2,
                          a3),
            PVStatics < 0) )
      {
        *a3 = 0;
      }
      if ( PVStatics < 0 )
      {
        v10 = "Failed to create UInt32 for MinValue";
        v11 = 1337;
        goto LABEL_10;
      }
      return 0;
    }
    v18 = WindowsGetStringRawBuffer(a2, 0);
    if ( CompareStringOrdinal(v18, -1, L"DefaultValue", -1, 0) == 2 )
    {
      v14 = SystemSettings::DataModel::PropValueHelper::_GetPVStatics();
      if ( v14 < 0
        || (v14 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValueStatics *, __int64, struct IInspectable **))(*(_QWORD *)SystemSettings::DataModel::PropValueHelper::_pPVStatics + 88LL))(
                    SystemSettings::DataModel::PropValueHelper::_pPVStatics,
                    10,
                    a3),
            v14 < 0) )
      {
        *a3 = 0;
      }
      if ( v14 < 0 )
      {
        v15 = "Failed to create UInt32 for DefaultValue";
        v16 = 1341;
        goto LABEL_17;
      }
    }
    else
    {
      v19 = (*(__int64 (__fastcall **)(SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting *, HSTRING, struct IInspectable **))(*(_QWORD *)this + 240LL))(
              this,
              a2,
              a3);
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x541,
          (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
          (const char *)(unsigned int)v19,
          (int)"Failed to get named value",
          v20);
        return (unsigned int)v19;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180019900  push    rbx
0x180019902  push    rbp
0x180019903  push    rsi
0x180019904  push    rdi
0x180019905  push    r15
0x180019907  sub     rsp, 30h
0x18001990b  mov     rbx, r8
0x18001990e  mov     rbp, rdx
0x180019911  mov     rsi, rcx
0x180019914  mov     qword ptr [r8], 0
0x18001991b  xor     edx, edx; length
0x18001991d  mov     rcx, rbp; string
0x180019920  call    cs:__imp_WindowsGetStringRawBuffer
0x180019926  mov     rcx, rax; lpString1
0x180019929  mov     [rsp+58h+bIgnoreCase], 0; bIgnoreCase
0x180019931  or      r15d, 0FFFFFFFFh
0x180019935  mov     r9d, r15d; cchCount2
0x180019938  lea     r8, aValue; "Value"
0x18001993f  mov     edx, r15d; cchCount1
0x180019942  call    cs:__imp_CompareStringOrdinal
0x180019948  lea     edi, [r15+3]
0x18001994c  cmp     eax, edi
0x18001994e  jnz     loc_1800199D9
0x180019954  mov     rax, [rsi]
0x180019957  mov     rcx, rsi
0x18001995a  mov     rax, [rax+108h]
0x180019961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019966  cmp     eax, edi
0x180019968  jb      short loc_180019975
0x18001996a  mov     edi, eax
0x18001996c  lea     edx, [r15+33h]
0x180019970  cmp     eax, edx
0x180019972  cmova   edi, edx
0x180019975  call    ?_GetPVStatics@PropValueHelper@DataModel@SystemSettings@@CAJXZ; SystemSettings::DataModel::PropValueHelper::_GetPVStatics(void)
0x18001997a  mov     esi, eax
0x18001997c  test    eax, eax
0x18001997e  js      short loc_18001999E
0x180019980  mov     rcx, cs:?_pPVStatics@PropValueHelper@DataModel@SystemSettings@@0PEAUIPropertyValueStatics@Foundation@Windows@@EA; Windows::Foundation::IPropertyValueStatics * SystemSettings::DataModel::PropValueHelper::_pPVStatics
0x180019987  mov     rax, [rcx]
0x18001998a  mov     r8, rbx
0x18001998d  mov     edx, edi
0x18001998f  mov     rax, [rax+58h]
0x180019993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019998  mov     esi, eax
0x18001999a  test    eax, eax
0x18001999c  jns     short loc_1800199A5
0x18001999e  mov     qword ptr [rbx], 0
0x1800199a5  test    esi, esi
0x1800199a7  jns     loc_180019B9F
0x1800199ad  lea     rax, aFailedToCreate_3; "Failed to create UInt32 for Value"
0x1800199b4  mov     edx, 531h; void *
0x1800199b9  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x1800199c0  mov     r9d, esi; char *
0x1800199c3  mov     qword ptr [rsp+58h+bIgnoreCase], rax; int
0x1800199c8  mov     rcx, [rsp+58h]; this
0x1800199cd  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800199d2  mov     eax, esi
0x1800199d4  jmp     loc_180019BA1
0x1800199d9  xor     edx, edx; length
0x1800199db  mov     rcx, rbp; string
0x1800199de  call    cs:__imp_WindowsGetStringRawBuffer
0x1800199e4  mov     rcx, rax; lpString1
0x1800199e7  mov     [rsp+58h+bIgnoreCase], 0; bIgnoreCase
0x1800199ef  mov     r9d, r15d; cchCount2
0x1800199f2  lea     r8, aMaxvalue; "MaxValue"
0x1800199f9  mov     edx, r15d; cchCount1
0x1800199fc  call    cs:__imp_CompareStringOrdinal
0x180019a02  cmp     eax, edi
0x180019a04  jnz     short loc_180019A6D
0x180019a06  call    ?_GetPVStatics@PropValueHelper@DataModel@SystemSettings@@CAJXZ; SystemSettings::DataModel::PropValueHelper::_GetPVStatics(void)
0x180019a0b  mov     edi, eax
0x180019a0d  test    eax, eax
0x180019a0f  js      short loc_180019A32
0x180019a11  mov     rcx, cs:?_pPVStatics@PropValueHelper@DataModel@SystemSettings@@0PEAUIPropertyValueStatics@Foundation@Windows@@EA; Windows::Foundation::IPropertyValueStatics * SystemSettings::DataModel::PropValueHelper::_pPVStatics
0x180019a18  mov     rax, [rcx]
0x180019a1b  mov     r8, rbx
0x180019a1e  mov     edx, 32h ; '2'
0x180019a23  mov     rax, [rax+58h]
0x180019a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a2c  mov     edi, eax
0x180019a2e  test    eax, eax
0x180019a30  jns     short loc_180019A39
0x180019a32  mov     qword ptr [rbx], 0
0x180019a39  test    edi, edi
0x180019a3b  jns     loc_180019B9F
0x180019a41  lea     rax, aFailedToCreate_13; "Failed to create UInt32 for MaxValue"
0x180019a48  mov     edx, 535h; void *
0x180019a4d  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180019a54  mov     r9d, edi; char *
0x180019a57  mov     qword ptr [rsp+58h+bIgnoreCase], rax; int
0x180019a5c  mov     rcx, [rsp+58h]; this
0x180019a61  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180019a66  mov     eax, edi
0x180019a68  jmp     loc_180019BA1
0x180019a6d  xor     edx, edx; length
0x180019a6f  mov     rcx, rbp; string
0x180019a72  call    cs:__imp_WindowsGetStringRawBuffer
0x180019a78  mov     rcx, rax; lpString1
0x180019a7b  mov     [rsp+58h+bIgnoreCase], 0; bIgnoreCase
0x180019a83  mov     r9d, r15d; cchCount2
0x180019a86  lea     r8, aMinvalue; "MinValue"
0x180019a8d  mov     edx, r15d; cchCount1
0x180019a90  call    cs:__imp_CompareStringOrdinal
0x180019a96  cmp     eax, edi
0x180019a98  jnz     short loc_180019AE3
0x180019a9a  call    ?_GetPVStatics@PropValueHelper@DataModel@SystemSettings@@CAJXZ; SystemSettings::DataModel::PropValueHelper::_GetPVStatics(void)
0x180019a9f  mov     esi, eax
0x180019aa1  test    eax, eax
0x180019aa3  js      short loc_180019AC3
0x180019aa5  mov     rcx, cs:?_pPVStatics@PropValueHelper@DataModel@SystemSettings@@0PEAUIPropertyValueStatics@Foundation@Windows@@EA; Windows::Foundation::IPropertyValueStatics * SystemSettings::DataModel::PropValueHelper::_pPVStatics
0x180019aac  mov     rax, [rcx]
0x180019aaf  mov     r8, rbx
0x180019ab2  mov     edx, edi
0x180019ab4  mov     rax, [rax+58h]
0x180019ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019abd  mov     esi, eax
0x180019abf  test    eax, eax
0x180019ac1  jns     short loc_180019ACA
0x180019ac3  mov     qword ptr [rbx], 0
0x180019aca  test    esi, esi
0x180019acc  jns     loc_180019B9F
0x180019ad2  lea     rax, aFailedToCreate_12; "Failed to create UInt32 for MinValue"
0x180019ad9  mov     edx, 539h
0x180019ade  jmp     loc_1800199B9
0x180019ae3  xor     edx, edx; length
0x180019ae5  mov     rcx, rbp; string
0x180019ae8  call    cs:__imp_WindowsGetStringRawBuffer
0x180019aee  mov     rcx, rax; lpString1
0x180019af1  mov     [rsp+58h+bIgnoreCase], 0; bIgnoreCase
0x180019af9  mov     r9d, r15d; cchCount2
0x180019afc  lea     r8, aDefaultvalue; "DefaultValue"
0x180019b03  mov     edx, r15d; cchCount1
0x180019b06  call    cs:__imp_CompareStringOrdinal
0x180019b0c  cmp     eax, edi
0x180019b0e  jnz     short loc_180019B58
0x180019b10  call    ?_GetPVStatics@PropValueHelper@DataModel@SystemSettings@@CAJXZ; SystemSettings::DataModel::PropValueHelper::_GetPVStatics(void)
0x180019b15  mov     edi, eax
0x180019b17  test    eax, eax
0x180019b19  js      short loc_180019B3C
0x180019b1b  mov     rcx, cs:?_pPVStatics@PropValueHelper@DataModel@SystemSettings@@0PEAUIPropertyValueStatics@Foundation@Windows@@EA; Windows::Foundation::IPropertyValueStatics * SystemSettings::DataModel::PropValueHelper::_pPVStatics
0x180019b22  mov     rax, [rcx]
0x180019b25  mov     r8, rbx
0x180019b28  mov     edx, 0Ah
0x180019b2d  mov     rax, [rax+58h]
0x180019b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b36  mov     edi, eax
0x180019b38  test    eax, eax
0x180019b3a  jns     short loc_180019B43
0x180019b3c  mov     qword ptr [rbx], 0
0x180019b43  test    edi, edi
0x180019b45  jns     short loc_180019B9F
0x180019b47  lea     rax, aFailedToCreate_16; "Failed to create UInt32 for DefaultValu"...
0x180019b4e  mov     edx, 53Dh
0x180019b53  jmp     loc_180019A4D
0x180019b58  mov     rax, [rsi]
0x180019b5b  mov     r8, rbx
0x180019b5e  mov     rdx, rbp
0x180019b61  mov     rcx, rsi
0x180019b64  mov     rax, [rax+0F0h]
0x180019b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b70  mov     ebx, eax
0x180019b72  test    eax, eax
0x180019b74  jns     short loc_180019B9F
0x180019b76  mov     rcx, [rsp+58h]; this
0x180019b7b  lea     rax, aFailedToGetNam; "Failed to get named value"
0x180019b82  mov     qword ptr [rsp+58h+bIgnoreCase], rax; int
0x180019b87  mov     r9d, ebx; char *
0x180019b8a  lea     r8, aPcshellShellSy_6; "pcshell\\shell\\systemsettings\\recover"...
0x180019b91  mov     edx, 541h; void *
0x180019b96  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180019b9b  mov     eax, ebx
0x180019b9d  jmp     short loc_180019BA1
0x180019b9f  xor     eax, eax
0x180019ba1  add     rsp, 30h
0x180019ba5  pop     r15
0x180019ba7  pop     rdi
0x180019ba8  pop     rsi
0x180019ba9  pop     rbp
0x180019baa  pop     rbx
0x180019bab  retn
```
