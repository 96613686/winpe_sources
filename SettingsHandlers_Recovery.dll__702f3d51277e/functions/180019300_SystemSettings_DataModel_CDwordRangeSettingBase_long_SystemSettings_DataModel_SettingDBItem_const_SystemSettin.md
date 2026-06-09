# SystemSettings::DataModel::CDwordRangeSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetValue(HSTRING__ *,IInspectable * *)

- ea: `0x180019300`
- end: `0x1800195c1`
- name: `?GetValue@?$CDwordRangeSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `705`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008c24`
- `0x180019300`
- `0x180021a30`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019341`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800193f6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019483`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019510`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019341`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800193f6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019483`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019510`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001931f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800193d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800194f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001931f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800193d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800194f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CDwordRangeSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetValue(
        _QWORD *a1,
        HSTRING a2,
        _QWORD *a3)
{
  const WCHAR *StringRawBuffer; // rax
  int v7; // eax
  unsigned int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // r8d
  unsigned int v11; // esi
  int PVStatics; // edi
  unsigned int v13; // r8d
  const char *v14; // r9
  __int64 result; // rax
  const WCHAR *v16; // rax
  unsigned int v17; // esi
  int v18; // edi
  const WCHAR *v19; // rax
  unsigned int v20; // esi
  int v21; // edi
  const WCHAR *v22; // rax
  unsigned int v23; // esi
  int v24; // edi
  int v25; // eax
  unsigned int v26; // ebx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-38h]
  BOOL bIgnoreCaseb; // [rsp+20h] [rbp-38h]
  BOOL bIgnoreCasec; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a3 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v7 = CompareStringOrdinal(StringRawBuffer, -1, L"Value", -1, 0);
  try
  {
    if ( v7 == 2 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 264LL))(a1);
      v9 = a1[11];
      v10 = *(_DWORD *)(v9 + 28);
      if ( v8 >= v10 )
        v10 = v8;
      v11 = *(_DWORD *)(v9 + 24);
      if ( v10 <= v11 )
        v11 = v10;
      PVStatics = SystemSettings::DataModel::PropValueHelper::_GetPVStatics();
      if ( PVStatics < 0
        || (PVStatics = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValueStatics *, _QWORD, _QWORD *))(*(_QWORD *)SystemSettings::DataModel::PropValueHelper::_pPVStatics + 88LL))(
                          SystemSettings::DataModel::PropValueHelper::_pPVStatics,
                          v11,
                          a3),
            PVStatics < 0) )
      {
        *a3 = 0;
      }
      if ( PVStatics < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA84,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)PVStatics,
          bIgnoreCase);
        return (unsigned int)PVStatics;
      }
    }
    else
    {
      v16 = WindowsGetStringRawBuffer(a2, 0);
      if ( CompareStringOrdinal(v16, -1, L"MaxValue", -1, 0) == 2 )
      {
        v17 = *(_DWORD *)(a1[11] + 24LL);
        v18 = SystemSettings::DataModel::PropValueHelper::_GetPVStatics();
        if ( v18 < 0
          || (v18 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValueStatics *, _QWORD, _QWORD *))(*(_QWORD *)SystemSettings::DataModel::PropValueHelper::_pPVStatics + 88LL))(
                      SystemSettings::DataModel::PropValueHelper::_pPVStatics,
                      v17,
                      a3),
              v18 < 0) )
        {
          *a3 = 0;
        }
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA88,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
            (const char *)(unsigned int)v18,
            bIgnoreCasea);
          return (unsigned int)v18;
        }
      }
      else
      {
        v19 = WindowsGetStringRawBuffer(a2, 0);
        if ( CompareStringOrdinal(v19, -1, L"MinValue", -1, 0) == 2 )
        {
          v20 = *(_DWORD *)(a1[11] + 28LL);
          v21 = SystemSettings::DataModel::PropValueHelper::_GetPVStatics();
          if ( v21 < 0
            || (v21 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValueStatics *, _QWORD, _QWORD *))(*(_QWORD *)SystemSettings::DataModel::PropValueHelper::_pPVStatics + 88LL))(
                        SystemSettings::DataModel::PropValueHelper::_pPVStatics,
                        v20,
                        a3),
                v21 < 0) )
          {
            *a3 = 0;
          }
          if ( v21 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA8C,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
              (const char *)(unsigned int)v21,
              bIgnoreCaseb);
            return (unsigned int)v21;
          }
        }
        else
        {
          v22 = WindowsGetStringRawBuffer(a2, 0);
          if ( CompareStringOrdinal(v22, -1, L"DefaultValue", -1, 0) == 2 )
          {
            v23 = *(_DWORD *)(a1[11] + 32LL);
            v24 = SystemSettings::DataModel::PropValueHelper::_GetPVStatics();
            if ( v24 < 0
              || (v24 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValueStatics *, _QWORD, _QWORD *))(*(_QWORD *)SystemSettings::DataModel::PropValueHelper::_pPVStatics + 88LL))(
                          SystemSettings::DataModel::PropValueHelper::_pPVStatics,
                          v23,
                          a3),
                  v24 < 0) )
            {
              *a3 = 0;
            }
            if ( v24 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xA90,
                (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
                (const char *)(unsigned int)v24,
                bIgnoreCasec);
              return (unsigned int)v24;
            }
          }
          else
          {
            v25 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _QWORD *))(*a1 + 240LL))(a1, a2, a3);
            v26 = v25;
            if ( v25 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xA94,
                (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
                (const char *)(unsigned int)v25,
                bIgnoreCasec);
              return v26;
            }
          }
        }
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0xA99, v13, v14);
  }
  return result;
}

```

## disassembly

```asm
0x180019300  push    rbx
0x180019302  push    rsi
0x180019303  push    rdi
0x180019304  push    r15
0x180019306  sub     rsp, 38h
0x18001930a  mov     rbx, r8
0x18001930d  mov     rsi, rdx
0x180019310  mov     rdi, rcx
0x180019313  mov     qword ptr [r8], 0
0x18001931a  xor     edx, edx; length
0x18001931c  mov     rcx, rsi; string
0x18001931f  call    cs:__imp_WindowsGetStringRawBuffer
0x180019325  mov     rcx, rax; lpString1
0x180019328  mov     [rsp+58h+bIgnoreCase], 0; int
0x180019330  or      r15d, 0FFFFFFFFh
0x180019334  mov     r9d, r15d; cchCount2
0x180019337  lea     r8, aValue; "Value"
0x18001933e  mov     edx, r15d; cchCount1
0x180019341  call    cs:__imp_CompareStringOrdinal
0x180019347  cmp     eax, 2
0x18001934a  jnz     loc_1800193D3
0x180019350  mov     rax, [rdi]
0x180019353  mov     rcx, rdi
0x180019356  mov     rax, [rax+108h]
0x18001935d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019362  mov     rcx, [rdi+58h]
0x180019366  mov     r8d, [rcx+1Ch]
0x18001936a  cmp     eax, r8d
0x18001936d  cmovnb  r8d, eax
0x180019371  mov     esi, [rcx+18h]
0x180019374  cmp     r8d, esi
0x180019377  cmovbe  esi, r8d
0x18001937b  call    ?_GetPVStatics@PropValueHelper@DataModel@SystemSettings@@CAJXZ; SystemSettings::DataModel::PropValueHelper::_GetPVStatics(void)
0x180019380  mov     edi, eax
0x180019382  test    eax, eax
0x180019384  js      short loc_1800193A4
0x180019386  mov     rcx, cs:?_pPVStatics@PropValueHelper@DataModel@SystemSettings@@0PEAUIPropertyValueStatics@Foundation@Windows@@EA; Windows::Foundation::IPropertyValueStatics * SystemSettings::DataModel::PropValueHelper::_pPVStatics
0x18001938d  mov     rax, [rcx]
0x180019390  mov     r8, rbx
0x180019393  mov     edx, esi
0x180019395  mov     rax, [rax+58h]
0x180019399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001939e  mov     edi, eax
0x1800193a0  test    eax, eax
0x1800193a2  jns     short loc_1800193AB
0x1800193a4  mov     qword ptr [rbx], 0
0x1800193ab  test    edi, edi
0x1800193ad  jns     loc_1800195AE
0x1800193b3  mov     rcx, [rsp+58h]; this
0x1800193b8  mov     r9d, edi; char *
0x1800193bb  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800193c2  mov     edx, 0A84h; void *
0x1800193c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800193cc  mov     eax, edi
0x1800193ce  jmp     loc_1800195B6
0x1800193d3  xor     edx, edx; length
0x1800193d5  mov     rcx, rsi; string
0x1800193d8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800193de  mov     rcx, rax; lpString1
0x1800193e1  mov     [rsp+58h+bIgnoreCase], 0; int
0x1800193e9  mov     r9d, r15d; cchCount2
0x1800193ec  lea     r8, aMaxvalue; "MaxValue"
0x1800193f3  mov     edx, r15d; cchCount1
0x1800193f6  call    cs:__imp_CompareStringOrdinal
0x1800193fc  cmp     eax, 2
0x1800193ff  jnz     short loc_180019460
0x180019401  mov     rax, [rdi+58h]
0x180019405  mov     esi, [rax+18h]
0x180019408  call    ?_GetPVStatics@PropValueHelper@DataModel@SystemSettings@@CAJXZ; SystemSettings::DataModel::PropValueHelper::_GetPVStatics(void)
0x18001940d  mov     edi, eax
0x18001940f  test    eax, eax
0x180019411  js      short loc_180019431
0x180019413  mov     rcx, cs:?_pPVStatics@PropValueHelper@DataModel@SystemSettings@@0PEAUIPropertyValueStatics@Foundation@Windows@@EA; Windows::Foundation::IPropertyValueStatics * SystemSettings::DataModel::PropValueHelper::_pPVStatics
0x18001941a  mov     rax, [rcx]
0x18001941d  mov     r8, rbx
0x180019420  mov     edx, esi
0x180019422  mov     rax, [rax+58h]
0x180019426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001942b  mov     edi, eax
0x18001942d  test    eax, eax
0x18001942f  jns     short loc_180019438
0x180019431  mov     qword ptr [rbx], 0
0x180019438  test    edi, edi
0x18001943a  jns     loc_1800195AE
0x180019440  mov     rcx, [rsp+58h]; this
0x180019445  mov     r9d, edi; char *
0x180019448  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001944f  mov     edx, 0A88h; void *
0x180019454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019459  mov     eax, edi
0x18001945b  jmp     loc_1800195B6
0x180019460  xor     edx, edx; length
0x180019462  mov     rcx, rsi; string
0x180019465  call    cs:__imp_WindowsGetStringRawBuffer
0x18001946b  mov     rcx, rax; lpString1
0x18001946e  mov     [rsp+58h+bIgnoreCase], 0; int
0x180019476  mov     r9d, r15d; cchCount2
0x180019479  lea     r8, aMinvalue; "MinValue"
0x180019480  mov     edx, r15d; cchCount1
0x180019483  call    cs:__imp_CompareStringOrdinal
0x180019489  cmp     eax, 2
0x18001948c  jnz     short loc_1800194ED
0x18001948e  mov     rax, [rdi+58h]
0x180019492  mov     esi, [rax+1Ch]
0x180019495  call    ?_GetPVStatics@PropValueHelper@DataModel@SystemSettings@@CAJXZ; SystemSettings::DataModel::PropValueHelper::_GetPVStatics(void)
0x18001949a  mov     edi, eax
0x18001949c  test    eax, eax
0x18001949e  js      short loc_1800194BE
0x1800194a0  mov     rcx, cs:?_pPVStatics@PropValueHelper@DataModel@SystemSettings@@0PEAUIPropertyValueStatics@Foundation@Windows@@EA; Windows::Foundation::IPropertyValueStatics * SystemSettings::DataModel::PropValueHelper::_pPVStatics
0x1800194a7  mov     rax, [rcx]
0x1800194aa  mov     r8, rbx
0x1800194ad  mov     edx, esi
0x1800194af  mov     rax, [rax+58h]
0x1800194b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194b8  mov     edi, eax
0x1800194ba  test    eax, eax
0x1800194bc  jns     short loc_1800194C5
0x1800194be  mov     qword ptr [rbx], 0
0x1800194c5  test    edi, edi
0x1800194c7  jns     loc_1800195AE
0x1800194cd  mov     rcx, [rsp+58h]; this
0x1800194d2  mov     r9d, edi; char *
0x1800194d5  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800194dc  mov     edx, 0A8Ch; void *
0x1800194e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800194e6  mov     eax, edi
0x1800194e8  jmp     loc_1800195B6
0x1800194ed  xor     edx, edx; length
0x1800194ef  mov     rcx, rsi; string
0x1800194f2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800194f8  mov     rcx, rax; lpString1
0x1800194fb  mov     [rsp+58h+bIgnoreCase], 0; int
0x180019503  mov     r9d, r15d; cchCount2
0x180019506  lea     r8, aDefaultvalue; "DefaultValue"
0x18001950d  mov     edx, r15d; cchCount1
0x180019510  call    cs:__imp_CompareStringOrdinal
0x180019516  cmp     eax, 2
0x180019519  jnz     short loc_180019573
0x18001951b  mov     rax, [rdi+58h]
0x18001951f  mov     esi, [rax+20h]
0x180019522  call    ?_GetPVStatics@PropValueHelper@DataModel@SystemSettings@@CAJXZ; SystemSettings::DataModel::PropValueHelper::_GetPVStatics(void)
0x180019527  mov     edi, eax
0x180019529  test    eax, eax
0x18001952b  js      short loc_18001954B
0x18001952d  mov     rcx, cs:?_pPVStatics@PropValueHelper@DataModel@SystemSettings@@0PEAUIPropertyValueStatics@Foundation@Windows@@EA; Windows::Foundation::IPropertyValueStatics * SystemSettings::DataModel::PropValueHelper::_pPVStatics
0x180019534  mov     rax, [rcx]
0x180019537  mov     r8, rbx
0x18001953a  mov     edx, esi
0x18001953c  mov     rax, [rax+58h]
0x180019540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019545  mov     edi, eax
0x180019547  test    eax, eax
0x180019549  jns     short loc_180019552
0x18001954b  mov     qword ptr [rbx], 0
0x180019552  test    edi, edi
0x180019554  jns     short loc_1800195AE
0x180019556  mov     rcx, [rsp+58h]; this
0x18001955b  mov     r9d, edi; char *
0x18001955e  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180019565  mov     edx, 0A90h; void *
0x18001956a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001956f  mov     eax, edi
0x180019571  jmp     short loc_1800195B6
0x180019573  mov     rax, [rdi]
0x180019576  mov     r8, rbx
0x180019579  mov     rdx, rsi
0x18001957c  mov     rcx, rdi
0x18001957f  mov     rax, [rax+0F0h]
0x180019586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001958b  mov     ebx, eax
0x18001958d  test    eax, eax
0x18001958f  jns     short loc_1800195AE
0x180019591  mov     rcx, [rsp+58h]; this
0x180019596  mov     r9d, eax; char *
0x180019599  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800195a0  mov     edx, 0A94h; void *
0x1800195a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800195aa  mov     eax, ebx
0x1800195ac  jmp     short loc_1800195B6
0x1800195ae  xor     eax, eax
0x1800195b0  jmp     short loc_1800195B6
0x1800195b2  mov     eax, [rsp+58h+arg_10]
0x1800195b6  add     rsp, 38h
0x1800195ba  pop     r15
0x1800195bc  pop     rdi
0x1800195bd  pop     rsi
0x1800195be  pop     rbx
0x1800195bf  retn
```
