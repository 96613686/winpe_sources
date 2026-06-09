# SystemSettings::DataModel::CLabeledStringSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetValue(HSTRING__ *,IInspectable * *)

- ea: `0x1800195d0`
- end: `0x18001973d`
- name: `?GetValue@?$CLabeledStringSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `365`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008c24`
- `0x1800195d0`
- `0x180021a30`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001960d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001960d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800195ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800195ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001962a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800196db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800196ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001962a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800196db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800196ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::DataModel::CLabeledStringSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetValue(
        __int64 *a1,
        HSTRING a2,
        _QWORD *a3)
{
  const WCHAR *StringRawBuffer; // rax
  int v7; // eax
  __int64 v8; // r14
  int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // r8d
  const char *v12; // r9
  __int64 result; // rax
  HSTRING v14; // rsi
  int PVStatics; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HSTRING string; // [rsp+70h] [rbp+18h] BYREF

  *a3 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v7 = CompareStringOrdinal(StringRawBuffer, -1, L"Value", -1, 0);
  try
  {
    v8 = *a1;
    if ( v7 == 2 )
    {
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      v9 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v8 + 264))(a1, &string);
      v10 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC22,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v9,
          bIgnoreCase);
        WindowsDeleteString(string);
        return v10;
      }
      v14 = string;
      PVStatics = SystemSettings::DataModel::PropValueHelper::_GetPVStatics();
      if ( PVStatics < 0
        || (PVStatics = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValueStatics *, HSTRING, _QWORD *))(*(_QWORD *)SystemSettings::DataModel::PropValueHelper::_pPVStatics + 144LL))(
                          SystemSettings::DataModel::PropValueHelper::_pPVStatics,
                          v14,
                          a3),
            PVStatics < 0) )
      {
        *a3 = 0;
      }
      if ( PVStatics < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC23,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)PVStatics,
          bIgnoreCase);
        WindowsDeleteString(string);
        return (unsigned int)PVStatics;
      }
      WindowsDeleteString(string);
    }
    else
    {
      v16 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD *))(v8 + 240))(a1, a2, a3);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC27,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v16,
          bIgnoreCase);
        return v17;
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0xC2C, v11, v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800195d0  push    rbx
0x1800195d2  push    rsi
0x1800195d3  push    rdi
0x1800195d4  push    r14
0x1800195d6  sub     rsp, 38h
0x1800195da  mov     rdi, r8
0x1800195dd  mov     rsi, rdx
0x1800195e0  mov     rbx, rcx
0x1800195e3  mov     qword ptr [r8], 0
0x1800195ea  xor     edx, edx; length
0x1800195ec  mov     rcx, rsi; string
0x1800195ef  call    cs:__imp_WindowsGetStringRawBuffer
0x1800195f5  mov     rcx, rax; lpString1
0x1800195f8  mov     [rsp+58h+bIgnoreCase], 0; int
0x180019600  or      edx, 0FFFFFFFFh; cchCount1
0x180019603  mov     r9d, edx; cchCount2
0x180019606  lea     r8, aValue; "Value"
0x18001960d  call    cs:__imp_CompareStringOrdinal
0x180019613  mov     r14, [rbx]
0x180019616  cmp     eax, 2
0x180019619  jnz     loc_1800196F2
0x18001961f  mov     [rsp+58h+string], 0
0x180019628  xor     ecx, ecx; string
0x18001962a  call    cs:__imp_WindowsDeleteString
0x180019630  mov     [rsp+58h+string], 0
0x180019639  lea     rdx, [rsp+58h+string]
0x18001963e  mov     rcx, rbx
0x180019641  mov     rax, [r14+108h]
0x180019648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001964d  mov     ebx, eax
0x18001964f  test    eax, eax
0x180019651  jns     short loc_18001967F
0x180019653  mov     rcx, [rsp+58h]; this
0x180019658  mov     r9d, eax; char *
0x18001965b  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180019662  mov     edx, 0C22h; void *
0x180019667  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001966c  nop
0x18001966d  mov     rcx, [rsp+58h+string]; string
0x180019672  call    cs:__imp_WindowsDeleteString
0x180019678  mov     eax, ebx
0x18001967a  jmp     loc_180019732
0x18001967f  mov     rsi, [rsp+58h+string]
0x180019684  call    ?_GetPVStatics@PropValueHelper@DataModel@SystemSettings@@CAJXZ; SystemSettings::DataModel::PropValueHelper::_GetPVStatics(void)
0x180019689  mov     ebx, eax
0x18001968b  test    eax, eax
0x18001968d  js      short loc_1800196B1
0x18001968f  mov     rcx, cs:?_pPVStatics@PropValueHelper@DataModel@SystemSettings@@0PEAUIPropertyValueStatics@Foundation@Windows@@EA; Windows::Foundation::IPropertyValueStatics * SystemSettings::DataModel::PropValueHelper::_pPVStatics
0x180019696  mov     rax, [rcx]
0x180019699  mov     r8, rdi
0x18001969c  mov     rdx, rsi
0x18001969f  mov     rax, [rax+90h]
0x1800196a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196ab  mov     ebx, eax
0x1800196ad  test    eax, eax
0x1800196af  jns     short loc_1800196B8
0x1800196b1  mov     qword ptr [rdi], 0
0x1800196b8  test    ebx, ebx
0x1800196ba  jns     short loc_1800196E5
0x1800196bc  mov     rcx, [rsp+58h]; this
0x1800196c1  mov     r9d, ebx; char *
0x1800196c4  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800196cb  mov     edx, 0C23h; void *
0x1800196d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800196d5  nop
0x1800196d6  mov     rcx, [rsp+58h+string]; string
0x1800196db  call    cs:__imp_WindowsDeleteString
0x1800196e1  mov     eax, ebx
0x1800196e3  jmp     short loc_180019732
0x1800196e5  mov     rcx, [rsp+58h+string]; string
0x1800196ea  call    cs:__imp_WindowsDeleteString
0x1800196f0  jmp     short loc_18001972A
0x1800196f2  mov     r8, rdi
0x1800196f5  mov     rdx, rsi
0x1800196f8  mov     rcx, rbx
0x1800196fb  mov     rax, [r14+0F0h]
0x180019702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019707  mov     ebx, eax
0x180019709  test    eax, eax
0x18001970b  jns     short loc_18001972A
0x18001970d  mov     rcx, [rsp+58h]; this
0x180019712  mov     r9d, eax; char *
0x180019715  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001971c  mov     edx, 0C27h; void *
0x180019721  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019726  mov     eax, ebx
0x180019728  jmp     short loc_180019732
0x18001972a  xor     eax, eax
0x18001972c  jmp     short loc_180019732
0x18001972e  mov     eax, dword ptr [rsp+58h+string]
0x180019732  add     rsp, 38h
0x180019736  pop     r14
0x180019738  pop     rdi
0x180019739  pop     rsi
0x18001973a  pop     rbx
0x18001973b  retn
```
