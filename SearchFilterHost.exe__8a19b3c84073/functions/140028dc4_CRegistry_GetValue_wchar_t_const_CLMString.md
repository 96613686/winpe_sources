# CRegistry::GetValue(wchar_t const *,CLMString &)

- ea: `0x140028dc4`
- end: `0x140028fdc`
- name: `?GetValue@CRegistry@@QEAAHPEB_WAEAVCLMString@@@Z`
- size: `536`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, struct CLMString *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140027f4c`

## callees

- `0x1400030a0`
- `0x1400198c4`
- `0x140024808`
- `0x140028310`
- `0x1400284e8`
- `0x140028508`
- `0x140028dc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028dfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028e19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028dfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028e19`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140028e4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140028f2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140028e4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140028f2e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140028ebb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140028ebb`

## string_xrefs

- `0x140028e48`: `InstallDirectory`
- `0x140028f20`: `InstallDirectory`
- `0x140028e90`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x140028ee6`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x140028f49`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x140028f85`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`

## pseudocode

```c
__int64 __fastcall CRegistry::GetValue(CRegistry *this, const wchar_t *a2, struct CLMString *a3)
{
  HKEY v5; // rcx
  DWORD v6; // ecx
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  WCHAR *Buffer; // rax
  DWORD v10; // eax
  unsigned int v11; // eax
  BYTE *v12; // rax
  DWORD v13; // esi
  wchar_t *v14; // rax
  int v15; // eax
  unsigned int lpData; // [rsp+20h] [rbp-248h]
  DWORD cbData; // [rsp+30h] [rbp-238h] BYREF
  DWORD Type; // [rsp+34h] [rbp-234h] BYREF
  __int64 v20; // [rsp+38h] [rbp-230h]
  wchar_t Data[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v20 = -2;
  SetLastError(0);
  Type = 0;
  v5 = (HKEY)*((_QWORD *)this + 22);
  if ( !v5 )
  {
    v6 = 6;
LABEL_3:
    SetLastError(v6);
    return 0;
  }
  cbData = 520;
  v7 = RegQueryValueExW(v5, L"InstallDirectory", 0, &Type, (LPBYTE)Data, &cbData);
  v8 = v7;
  if ( v7 && v7 != 234 || Type - 1 > 1 && Type != 7 )
  {
    v6 = v7;
    goto LABEL_3;
  }
  try
  {
    if ( Type == 2 )
    {
      if ( v7 == 234 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2E3,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
          (const char *)0xCE,
          lpData);
      Buffer = CLMString::GetBuffer(a3, 260);
      v10 = ExpandEnvironmentStringsW(Data, Buffer, 0x104u);
      cbData = v10;
      if ( v10 - 1 > 0x102 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2E9,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
          (const char *)0xCE,
          lpData);
      v11 = 2 * v10;
      cbData = v11;
    }
    else
    {
      if ( v7 == 234 )
      {
        v12 = (BYTE *)CLMString::GetBuffer(a3, cbData >> 1);
        v8 = RegQueryValueExW(*((HKEY *)this + 22), L"InstallDirectory", 0, &Type, v12, &cbData);
      }
      else
      {
        v13 = cbData;
        v14 = CLMString::GetBuffer(a3, cbData >> 1);
        v15 = StringCbCopyW(v14, v13, Data);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2F8,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
            (const char *)(unsigned int)v15,
            lpData);
      }
      v11 = cbData;
    }
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2FD,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
        (const char *)v8,
        lpData);
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>();
  }
  cbData = v11 >> 1;
  CLMString::Truncate(a3, v11 >> 1 != 0 ? (v11 >> 1) - 1 : 0);
  return 1;
}

```

## disassembly

```asm
0x140028dc4  mov     rax, rsp
0x140028dc7  push    rdi
0x140028dc8  sub     rsp, 260h
0x140028dcf  mov     [rsp+268h+var_230], 0FFFFFFFFFFFFFFFEh
0x140028dd8  mov     [rax+10h], rbx
0x140028ddc  mov     [rax+20h], rsi
0x140028de0  mov     rax, cs:__security_cookie
0x140028de7  xor     rax, rsp
0x140028dea  mov     [rsp+268h+var_18], rax
0x140028df2  mov     rdi, r8
0x140028df5  mov     rsi, rcx
0x140028df8  xor     ecx, ecx; dwErrCode
0x140028dfa  call    cs:__imp_SetLastError
0x140028e00  mov     [rsp+268h+Type], 0
0x140028e08  mov     rcx, [rsi+0B0h]; hKey
0x140028e0f  test    rcx, rcx
0x140028e12  jnz     short loc_140028E24
0x140028e14  mov     ecx, 6; dwErrCode
0x140028e19  call    cs:__imp_SetLastError
0x140028e1f  jmp     loc_140028FB5
0x140028e24  mov     [rsp+268h+cbData], 208h
0x140028e2c  lea     rax, [rsp+268h+cbData]
0x140028e31  mov     [rsp+268h+lpcbData], rax; lpcbData
0x140028e36  lea     rax, [rsp+268h+Data]
0x140028e3b  mov     [rsp+268h+lpData], rax; int
0x140028e40  lea     r9, [rsp+268h+Type]; lpType
0x140028e45  xor     r8d, r8d; lpReserved
0x140028e48  lea     rdx, ValueName; "InstallDirectory"
0x140028e4f  call    cs:__imp_RegQueryValueExW
0x140028e55  mov     ebx, eax
0x140028e57  mov     ecx, 0EAh
0x140028e5c  test    eax, eax
0x140028e5e  jz      short loc_140028E64
0x140028e60  cmp     eax, ecx
0x140028e62  jnz     short loc_140028E75
0x140028e64  mov     edx, [rsp+268h+Type]
0x140028e68  lea     eax, [rdx-1]
0x140028e6b  cmp     eax, 1
0x140028e6e  jbe     short loc_140028E79
0x140028e70  cmp     edx, 7
0x140028e73  jz      short loc_140028E79
0x140028e75  mov     ecx, ebx
0x140028e77  jmp     short loc_140028E19
0x140028e79  cmp     edx, 2
0x140028e7c  jnz     short loc_140028EF7
0x140028e7e  cmp     ebx, ecx
0x140028e80  jnz     short loc_140028EA1
0x140028e82  mov     rcx, [rsp+268h]; this
0x140028e8a  mov     r9d, 0CEh; char *
0x140028e90  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\search\\com"...
0x140028e97  mov     edx, 2E3h; void *
0x140028e9c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140028ea1  mov     esi, 104h
0x140028ea6  mov     edx, esi; int
0x140028ea8  mov     rcx, rdi; this
0x140028eab  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x140028eb0  mov     r8d, esi; nSize
0x140028eb3  mov     rdx, rax; lpDst
0x140028eb6  lea     rcx, [rsp+268h+Data]; lpSrc
0x140028ebb  call    cs:__imp_ExpandEnvironmentStringsW
0x140028ec1  mov     [rsp+268h+cbData], eax
0x140028ec5  lea     ecx, [rax-1]
0x140028ec8  cmp     ecx, 102h
0x140028ece  ja      short loc_140028ED8
0x140028ed0  add     eax, eax
0x140028ed2  mov     [rsp+268h+cbData], eax
0x140028ed6  jmp     short loc_140028F3A
0x140028ed8  mov     rcx, [rsp+268h]; this
0x140028ee0  mov     r9d, 0CEh; char *
0x140028ee6  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\search\\com"...
0x140028eed  mov     edx, 2E9h; void *
0x140028ef2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140028ef7  cmp     ebx, ecx
0x140028ef9  mov     rcx, rdi; this
0x140028efc  jnz     short loc_140028F5A
0x140028efe  mov     edx, [rsp+268h+cbData]
0x140028f02  shr     edx, 1; int
0x140028f04  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x140028f09  lea     rcx, [rsp+268h+cbData]
0x140028f0e  mov     [rsp+268h+lpcbData], rcx; lpcbData
0x140028f13  mov     [rsp+268h+lpData], rax; unsigned int
0x140028f18  lea     r9, [rsp+268h+Type]; lpType
0x140028f1d  xor     r8d, r8d; lpReserved
0x140028f20  lea     rdx, ValueName; "InstallDirectory"
0x140028f27  mov     rcx, [rsi+0B0h]; hKey
0x140028f2e  call    cs:__imp_RegQueryValueExW
0x140028f34  mov     ebx, eax
0x140028f36  mov     eax, [rsp+268h+cbData]
0x140028f3a  test    ebx, ebx
0x140028f3c  jz      short loc_140028F97
0x140028f3e  mov     rcx, [rsp+268h]; this
0x140028f46  mov     r9d, ebx; char *
0x140028f49  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\search\\com"...
0x140028f50  mov     edx, 2FDh; void *
0x140028f55  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140028f5a  mov     edx, [rsp+268h+cbData]
0x140028f5e  mov     esi, edx
0x140028f60  shr     edx, 1; int
0x140028f62  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x140028f67  lea     r8, [rsp+268h+Data]; wchar_t *
0x140028f6c  mov     edx, esi; unsigned __int64
0x140028f6e  mov     rcx, rax; wchar_t *
0x140028f71  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140028f76  mov     rcx, [rsp+268h]; this
0x140028f7e  test    eax, eax
0x140028f80  jns     short loc_140028F36
0x140028f82  mov     r9d, eax; char *
0x140028f85  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\search\\com"...
0x140028f8c  mov     edx, 2F8h; void *
0x140028f91  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140028f97  shr     eax, 1
0x140028f99  mov     [rsp+268h+cbData], eax
0x140028f9d  lea     ecx, [rax-1]
0x140028fa0  neg     eax
0x140028fa2  sbb     edx, edx
0x140028fa4  and     edx, ecx; unsigned int
0x140028fa6  mov     rcx, rdi; this
0x140028fa9  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x140028fae  mov     eax, 1
0x140028fb3  jmp     short loc_140028FB7
0x140028fb5  xor     eax, eax
0x140028fb7  mov     rcx, [rsp+268h+var_18]
0x140028fbf  xor     rcx, rsp; StackCookie
0x140028fc2  call    __security_check_cookie
0x140028fc7  lea     r11, [rsp+268h+var_8]
0x140028fcf  mov     rbx, [r11+18h]
0x140028fd3  mov     rsi, [r11+28h]
0x140028fd7  mov     rsp, r11
0x140028fda  pop     rdi
0x140028fdb  retn
```
