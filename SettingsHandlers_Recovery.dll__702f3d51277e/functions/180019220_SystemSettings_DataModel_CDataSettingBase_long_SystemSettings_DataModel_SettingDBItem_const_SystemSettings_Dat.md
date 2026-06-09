# SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetValue(HSTRING__ *,IInspectable * *)

- ea: `0x180019220`
- end: `0x1800192ec`
- name: `?GetValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008c24`
- `0x180019220`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001925b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001925b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001923d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001923d`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetValue(
        __int64 *a1,
        HSTRING a2,
        __int64 a3)
{
  const WCHAR *StringRawBuffer; // rax
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // eax
  unsigned int v11; // r8d
  const char *v12; // r9
  unsigned int v13; // ebx
  __int64 result; // rax
  int v15; // eax
  unsigned int v16; // ebx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v7 = CompareStringOrdinal(StringRawBuffer, -1, L"Value", -1, 0);
  try
  {
    v9 = *a1;
    if ( v7 == 2 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64))(v9 + 208))(a1, a3, v8, v9);
      v13 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x898,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v10,
          bIgnoreCase);
        return v13;
      }
    }
    else
    {
      v15 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64))(v9 + 240))(a1, a2, a3);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x89C,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v15,
          bIgnoreCase);
        return v16;
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x8A1, v11, v12);
  }
  return result;
}

```

## disassembly

```asm
0x180019220  mov     [rsp+arg_0], rbx
0x180019225  mov     [rsp+arg_8], rsi
0x18001922a  push    rdi
0x18001922b  sub     rsp, 30h
0x18001922f  mov     rdi, r8
0x180019232  mov     rsi, rdx
0x180019235  mov     rbx, rcx
0x180019238  xor     edx, edx; length
0x18001923a  mov     rcx, rsi; string
0x18001923d  call    cs:__imp_WindowsGetStringRawBuffer
0x180019243  mov     rcx, rax; lpString1
0x180019246  mov     [rsp+38h+bIgnoreCase], 0; int
0x18001924e  or      edx, 0FFFFFFFFh; cchCount1
0x180019251  mov     r9d, edx; cchCount2
0x180019254  lea     r8, aValue; "Value"
0x18001925b  call    cs:__imp_CompareStringOrdinal
0x180019261  mov     r9, [rbx]
0x180019264  mov     rcx, rbx
0x180019267  cmp     eax, 2
0x18001926a  jnz     short loc_18001929E
0x18001926c  mov     rdx, rdi
0x18001926f  mov     rax, [r9+0D0h]
0x180019276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001927b  mov     ebx, eax
0x18001927d  test    eax, eax
0x18001927f  jns     short loc_1800192D3
0x180019281  mov     rcx, [rsp+38h]; this
0x180019286  mov     r9d, eax; char *
0x180019289  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180019290  mov     edx, 898h; void *
0x180019295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001929a  mov     eax, ebx
0x18001929c  jmp     short loc_1800192DB
0x18001929e  mov     r8, rdi
0x1800192a1  mov     rdx, rsi
0x1800192a4  mov     rax, [r9+0F0h]
0x1800192ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192b0  mov     ebx, eax
0x1800192b2  test    eax, eax
0x1800192b4  jns     short loc_1800192D3
0x1800192b6  mov     rcx, [rsp+38h]; this
0x1800192bb  mov     r9d, eax; char *
0x1800192be  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800192c5  mov     edx, 89Ch; void *
0x1800192ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800192cf  mov     eax, ebx
0x1800192d1  jmp     short loc_1800192DB
0x1800192d3  xor     eax, eax
0x1800192d5  jmp     short loc_1800192DB
0x1800192d7  mov     eax, [rsp+38h+arg_18]
0x1800192db  mov     rbx, [rsp+38h+arg_0]
0x1800192e0  mov     rsi, [rsp+38h+arg_8]
0x1800192e5  add     rsp, 30h
0x1800192e9  pop     rdi
0x1800192ea  retn
```
