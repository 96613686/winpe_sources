# SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetNamedValue(HSTRING__ *,IInspectable * *)

- ea: `0x180016b20`
- end: `0x180016bbf`
- name: `?GetNamedValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@MEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008c24`
- `0x180016b20`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016b54`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016b83`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016b54`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016b83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016b35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016b64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016b35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016b64`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetNamedValue(
        __int64 a1,
        HSTRING a2,
        _QWORD *a3)
{
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v5; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a3 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"Icon", -1, 0) == 2 )
    return 0;
  v5 = WindowsGetStringRawBuffer(a2, 0);
  if ( CompareStringOrdinal(v5, -1, L"AdditionalDescription", -1, 0) == 2 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8F2,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
    (const char *)0x80070057LL,
    bIgnoreCase);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180016b20  push    rbx
0x180016b22  sub     rsp, 30h
0x180016b26  mov     rbx, rdx
0x180016b29  mov     qword ptr [r8], 0
0x180016b30  xor     edx, edx; length
0x180016b32  mov     rcx, rbx; string
0x180016b35  call    cs:__imp_WindowsGetStringRawBuffer
0x180016b3b  mov     rcx, rax; lpString1
0x180016b3e  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x180016b46  or      r9d, 0FFFFFFFFh; cchCount2
0x180016b4a  lea     r8, String2; "Icon"
0x180016b51  or      edx, r9d; cchCount1
0x180016b54  call    cs:__imp_CompareStringOrdinal
0x180016b5a  cmp     eax, 2
0x180016b5d  jz      short loc_180016BB0
0x180016b5f  xor     edx, edx; length
0x180016b61  mov     rcx, rbx; string
0x180016b64  call    cs:__imp_WindowsGetStringRawBuffer
0x180016b6a  mov     rcx, rax; lpString1
0x180016b6d  mov     [rsp+38h+bIgnoreCase], 0; int
0x180016b75  or      r9d, 0FFFFFFFFh; cchCount2
0x180016b79  lea     r8, aAdditionaldesc; "AdditionalDescription"
0x180016b80  or      edx, r9d; cchCount1
0x180016b83  call    cs:__imp_CompareStringOrdinal
0x180016b89  cmp     eax, 2
0x180016b8c  jz      short loc_180016BB0
0x180016b8e  mov     rcx, [rsp+38h]; this
0x180016b93  mov     ebx, 80070057h
0x180016b98  mov     r9d, ebx; char *
0x180016b9b  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180016ba2  mov     edx, 8F2h; void *
0x180016ba7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016bac  mov     eax, ebx
0x180016bae  jmp     short loc_180016BB8
0x180016bb0  xor     eax, eax
0x180016bb2  jmp     short loc_180016BB8
0x180016bb4  mov     eax, [rsp+38h+arg_10]
0x180016bb8  add     rsp, 30h
0x180016bbc  pop     rbx
0x180016bbd  retn
```
