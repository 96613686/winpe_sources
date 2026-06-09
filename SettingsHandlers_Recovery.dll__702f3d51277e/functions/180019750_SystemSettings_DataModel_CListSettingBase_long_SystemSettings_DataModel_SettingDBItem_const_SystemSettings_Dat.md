# SystemSettings::DataModel::CListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetValue(HSTRING__ *,IInspectable * *)

- ea: `0x180019750`
- end: `0x1800198f6`
- name: `?GetValue@?$CListSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `422`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008c24`
- `0x180019750`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019791`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800197fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001986b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180019791`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800197fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001986b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001976f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800197e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001984d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001976f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800197e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001984d`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetValue(
        __int64 *a1,
        HSTRING a2,
        _QWORD *a3)
{
  const WCHAR *StringRawBuffer; // rax
  int v7; // eax
  int v8; // eax
  unsigned int v9; // r8d
  const char *v10; // r9
  unsigned int v11; // ebx
  __int64 result; // rax
  const WCHAR *v13; // rax
  int v14; // eax
  unsigned int v15; // ebx
  const WCHAR *v16; // rax
  int v17; // eax
  __int64 v18; // r9
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // eax
  unsigned int v22; // ebx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-38h]
  BOOL bIgnoreCaseb; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a3 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v7 = CompareStringOrdinal(StringRawBuffer, -1, L"Value", -1, 0);
  try
  {
    if ( v7 == 2 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(*a1 + 208))(a1, a3);
      v11 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB08,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v8,
          bIgnoreCase);
        return v11;
      }
    }
    else
    {
      v13 = WindowsGetStringRawBuffer(a2, 0);
      if ( CompareStringOrdinal(v13, -1, L"PossibleValues", -1, 0) == 2 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(*a1 + 264))(a1, a3);
        v15 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB0C,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
            (const char *)(unsigned int)v14,
            bIgnoreCasea);
          return v15;
        }
      }
      else
      {
        v16 = WindowsGetStringRawBuffer(a2, 0);
        v17 = CompareStringOrdinal(v16, -1, L"Restriction", -1, 0);
        v18 = *a1;
        if ( v17 == 2 )
        {
          v19 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(v18 + 272))(a1, a3);
          v20 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB10,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
              (const char *)(unsigned int)v19,
              bIgnoreCaseb);
            return v20;
          }
        }
        else
        {
          v21 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD *))(v18 + 240))(a1, a2, a3);
          v22 = v21;
          if ( v21 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB14,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
              (const char *)(unsigned int)v21,
              bIgnoreCaseb);
            return v22;
          }
        }
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0xB19, v9, v10);
  }
  return result;
}

```

## disassembly

```asm
0x180019750  push    rbx
0x180019752  push    rsi
0x180019753  push    rdi
0x180019754  push    r15
0x180019756  sub     rsp, 38h
0x18001975a  mov     rdi, r8
0x18001975d  mov     rsi, rdx
0x180019760  mov     rbx, rcx
0x180019763  mov     qword ptr [r8], 0
0x18001976a  xor     edx, edx; length
0x18001976c  mov     rcx, rsi; string
0x18001976f  call    cs:__imp_WindowsGetStringRawBuffer
0x180019775  mov     rcx, rax; lpString1
0x180019778  mov     [rsp+58h+bIgnoreCase], 0; int
0x180019780  or      r15d, 0FFFFFFFFh
0x180019784  mov     r9d, r15d; cchCount2
0x180019787  lea     r8, aValue; "Value"
0x18001978e  mov     edx, r15d; cchCount1
0x180019791  call    cs:__imp_CompareStringOrdinal
0x180019797  cmp     eax, 2
0x18001979a  jnz     short loc_1800197DB
0x18001979c  mov     rax, [rbx]
0x18001979f  mov     rdx, rdi
0x1800197a2  mov     rcx, rbx
0x1800197a5  mov     rax, [rax+0D0h]
0x1800197ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197b1  mov     ebx, eax
0x1800197b3  test    eax, eax
0x1800197b5  jns     loc_1800198E3
0x1800197bb  mov     rcx, [rsp+58h]; this
0x1800197c0  mov     r9d, eax; char *
0x1800197c3  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800197ca  mov     edx, 0B08h; void *
0x1800197cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800197d4  mov     eax, ebx
0x1800197d6  jmp     loc_1800198EB
0x1800197db  xor     edx, edx; length
0x1800197dd  mov     rcx, rsi; string
0x1800197e0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800197e6  mov     rcx, rax; lpString1
0x1800197e9  mov     [rsp+58h+bIgnoreCase], 0; int
0x1800197f1  mov     r9d, r15d; cchCount2
0x1800197f4  lea     r8, aPossiblevalues; "PossibleValues"
0x1800197fb  mov     edx, r15d; cchCount1
0x1800197fe  call    cs:__imp_CompareStringOrdinal
0x180019804  cmp     eax, 2
0x180019807  jnz     short loc_180019848
0x180019809  mov     rax, [rbx]
0x18001980c  mov     rdx, rdi
0x18001980f  mov     rcx, rbx
0x180019812  mov     rax, [rax+108h]
0x180019819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001981e  mov     ebx, eax
0x180019820  test    eax, eax
0x180019822  jns     loc_1800198E3
0x180019828  mov     rcx, [rsp+58h]; this
0x18001982d  mov     r9d, eax; char *
0x180019830  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180019837  mov     edx, 0B0Ch; void *
0x18001983c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019841  mov     eax, ebx
0x180019843  jmp     loc_1800198EB
0x180019848  xor     edx, edx; length
0x18001984a  mov     rcx, rsi; string
0x18001984d  call    cs:__imp_WindowsGetStringRawBuffer
0x180019853  mov     rcx, rax; lpString1
0x180019856  mov     [rsp+58h+bIgnoreCase], 0; int
0x18001985e  mov     r9d, r15d; cchCount2
0x180019861  lea     r8, aRestriction; "Restriction"
0x180019868  mov     edx, r15d; cchCount1
0x18001986b  call    cs:__imp_CompareStringOrdinal
0x180019871  mov     r9, [rbx]
0x180019874  mov     rcx, rbx
0x180019877  cmp     eax, 2
0x18001987a  jnz     short loc_1800198AE
0x18001987c  mov     rdx, rdi
0x18001987f  mov     rax, [r9+110h]
0x180019886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001988b  mov     ebx, eax
0x18001988d  test    eax, eax
0x18001988f  jns     short loc_1800198E3
0x180019891  mov     rcx, [rsp+58h]; this
0x180019896  mov     r9d, eax; char *
0x180019899  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800198a0  mov     edx, 0B10h; void *
0x1800198a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198aa  mov     eax, ebx
0x1800198ac  jmp     short loc_1800198EB
0x1800198ae  mov     r8, rdi
0x1800198b1  mov     rdx, rsi
0x1800198b4  mov     rax, [r9+0F0h]
0x1800198bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198c0  mov     ebx, eax
0x1800198c2  test    eax, eax
0x1800198c4  jns     short loc_1800198E3
0x1800198c6  mov     rcx, [rsp+58h]; this
0x1800198cb  mov     r9d, eax; char *
0x1800198ce  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800198d5  mov     edx, 0B14h; void *
0x1800198da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800198df  mov     eax, ebx
0x1800198e1  jmp     short loc_1800198EB
0x1800198e3  xor     eax, eax
0x1800198e5  jmp     short loc_1800198EB
0x1800198e7  mov     eax, [rsp+58h+arg_10]
0x1800198eb  add     rsp, 38h
0x1800198ef  pop     r15
0x1800198f1  pop     rdi
0x1800198f2  pop     rsi
0x1800198f3  pop     rbx
0x1800198f4  retn
```
