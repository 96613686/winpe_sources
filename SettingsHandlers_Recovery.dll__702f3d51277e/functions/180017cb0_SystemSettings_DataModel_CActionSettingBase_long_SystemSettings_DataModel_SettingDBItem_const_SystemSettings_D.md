# SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x180017cb0`
- end: `0x180017dcc`
- name: `?GetProperty@?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `284`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008c24`
- `0x180017cb0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180017cf1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180017d5e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180017d8c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180017cf1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180017d5e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180017d8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017ccf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017d40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017d6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017ccf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017d40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017d6e`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetProperty(
        __int64 a1,
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
  const WCHAR *v14; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a3 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v7 = CompareStringOrdinal(StringRawBuffer, -1, L"ActionDescription", -1, 0);
  try
  {
    if ( v7 == 2 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 216LL))(a1, a3);
      v11 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x804,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v8,
          bIgnoreCase);
        return v11;
      }
    }
    else
    {
      v13 = WindowsGetStringRawBuffer(a2, 0);
      if ( CompareStringOrdinal(v13, -1, L"Icon", -1, 0) != 2 )
      {
        v14 = WindowsGetStringRawBuffer(a2, 0);
        if ( CompareStringOrdinal(v14, -1, L"AdditionalDescription", -1, 0) != 2 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x810,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
            (const char *)0x80070057LL,
            bIgnoreCasea);
          return 2147942487LL;
        }
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x815, v9, v10);
  }
  return result;
}

```

## disassembly

```asm
0x180017cb0  push    rbx
0x180017cb2  push    rsi
0x180017cb3  push    rdi
0x180017cb4  push    r15
0x180017cb6  sub     rsp, 38h
0x180017cba  mov     rsi, r8
0x180017cbd  mov     rbx, rdx
0x180017cc0  mov     rdi, rcx
0x180017cc3  mov     qword ptr [r8], 0
0x180017cca  xor     edx, edx; length
0x180017ccc  mov     rcx, rbx; string
0x180017ccf  call    cs:__imp_WindowsGetStringRawBuffer
0x180017cd5  mov     rcx, rax; lpString1
0x180017cd8  mov     [rsp+58h+bIgnoreCase], 0; int
0x180017ce0  or      r15d, 0FFFFFFFFh
0x180017ce4  mov     r9d, r15d; cchCount2
0x180017ce7  lea     r8, aActiondescript; "ActionDescription"
0x180017cee  mov     edx, r15d; cchCount1
0x180017cf1  call    cs:__imp_CompareStringOrdinal
0x180017cf7  cmp     eax, 2
0x180017cfa  jnz     short loc_180017D3B
0x180017cfc  mov     rax, [rdi]
0x180017cff  mov     rdx, rsi
0x180017d02  mov     rcx, rdi
0x180017d05  mov     rax, [rax+0D8h]
0x180017d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d11  mov     ebx, eax
0x180017d13  test    eax, eax
0x180017d15  jns     loc_180017DB9
0x180017d1b  mov     rcx, [rsp+58h]; this
0x180017d20  mov     r9d, eax; char *
0x180017d23  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180017d2a  mov     edx, 804h; void *
0x180017d2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d34  mov     eax, ebx
0x180017d36  jmp     loc_180017DC1
0x180017d3b  xor     edx, edx; length
0x180017d3d  mov     rcx, rbx; string
0x180017d40  call    cs:__imp_WindowsGetStringRawBuffer
0x180017d46  mov     rcx, rax; lpString1
0x180017d49  mov     [rsp+58h+bIgnoreCase], 0; bIgnoreCase
0x180017d51  mov     r9d, r15d; cchCount2
0x180017d54  lea     r8, String2; "Icon"
0x180017d5b  mov     edx, r15d; cchCount1
0x180017d5e  call    cs:__imp_CompareStringOrdinal
0x180017d64  cmp     eax, 2
0x180017d67  jz      short loc_180017DB9
0x180017d69  xor     edx, edx; length
0x180017d6b  mov     rcx, rbx; string
0x180017d6e  call    cs:__imp_WindowsGetStringRawBuffer
0x180017d74  mov     rcx, rax; lpString1
0x180017d77  mov     [rsp+58h+bIgnoreCase], 0; int
0x180017d7f  mov     r9d, r15d; cchCount2
0x180017d82  lea     r8, aAdditionaldesc; "AdditionalDescription"
0x180017d89  mov     edx, r15d; cchCount1
0x180017d8c  call    cs:__imp_CompareStringOrdinal
0x180017d92  cmp     eax, 2
0x180017d95  jz      short loc_180017DB9
0x180017d97  mov     rcx, [rsp+58h]; this
0x180017d9c  mov     ebx, 80070057h
0x180017da1  mov     r9d, ebx; char *
0x180017da4  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180017dab  mov     edx, 810h; void *
0x180017db0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017db5  mov     eax, ebx
0x180017db7  jmp     short loc_180017DC1
0x180017db9  xor     eax, eax
0x180017dbb  jmp     short loc_180017DC1
0x180017dbd  mov     eax, [rsp+58h+arg_10]
0x180017dc1  add     rsp, 38h
0x180017dc5  pop     r15
0x180017dc7  pop     rdi
0x180017dc8  pop     rsi
0x180017dc9  pop     rbx
0x180017dca  retn
```
