# CRegistry::GetValue(wchar_t const *,CLMString &)

- ea: `0x18017a460`
- end: `0x18017a66e`
- name: `?GetValue@CRegistry@@QEAAHPEB_WAEAVCLMString@@@Z`
- size: `526`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, struct CLMString *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801f9280`

## callees

- `0x180038f08`
- `0x1800f3e64`
- `0x180108e88`
- `0x18017a460`
- `0x18017a674`
- `0x180188d90`
- `0x18019b924`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017a48c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017a4ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017a48c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017a4ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18017a4e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18017a5c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18017a4e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18017a5c0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18017a54d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18017a54d`

## string_xrefs

- `0x18017a522`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x18017a578`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x18017a5db`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x18017a617`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`
- `0x18017a4da`: `InstallDirectory`
- `0x18017a5b2`: `InstallDirectory`

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
  DWORD Type[3]; // [rsp+34h] [rbp-234h] BYREF
  wchar_t Data[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  SetLastError(0);
  Type[0] = 0;
  v5 = (HKEY)*((_QWORD *)this + 22);
  if ( !v5 )
  {
    v6 = 6;
LABEL_3:
    SetLastError(v6);
    return 0;
  }
  cbData = 520;
  v7 = RegQueryValueExW(v5, L"InstallDirectory", 0, Type, (LPBYTE)Data, &cbData);
  v8 = v7;
  if ( v7 && v7 != 234 || Type[0] - 1 > 1 && Type[0] != 7 )
  {
    v6 = v7;
    goto LABEL_3;
  }
  try
  {
    if ( Type[0] == 2 )
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
        v8 = RegQueryValueExW(*((HKEY *)this + 22), L"InstallDirectory", 0, Type, v12, &cbData);
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
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      770,
      "onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx");
  }
  cbData = v11 >> 1;
  CLMString::Truncate(a3, v11 >> 1 != 0 ? (v11 >> 1) - 1 : 0);
  return 1;
}

```

## disassembly

```asm
0x18017a460  mov     [rsp+arg_8], rbx
0x18017a465  mov     [rsp+arg_18], rsi
0x18017a46a  push    rdi
0x18017a46b  sub     rsp, 260h
0x18017a472  mov     rax, cs:__security_cookie
0x18017a479  xor     rax, rsp
0x18017a47c  mov     [rsp+268h+var_18], rax
0x18017a484  mov     rdi, r8
0x18017a487  mov     rsi, rcx
0x18017a48a  xor     ecx, ecx; dwErrCode
0x18017a48c  call    cs:__imp_SetLastError
0x18017a492  mov     [rsp+268h+Type], 0
0x18017a49a  mov     rcx, [rsi+0B0h]; hKey
0x18017a4a1  test    rcx, rcx
0x18017a4a4  jnz     short loc_18017A4B6
0x18017a4a6  mov     ecx, 6; dwErrCode
0x18017a4ab  call    cs:__imp_SetLastError
0x18017a4b1  jmp     loc_18017A647
0x18017a4b6  mov     [rsp+268h+cbData], 208h
0x18017a4be  lea     rax, [rsp+268h+cbData]
0x18017a4c3  mov     [rsp+268h+lpcbData], rax; lpcbData
0x18017a4c8  lea     rax, [rsp+268h+Data]
0x18017a4cd  mov     [rsp+268h+lpData], rax; int
0x18017a4d2  lea     r9, [rsp+268h+Type]; lpType
0x18017a4d7  xor     r8d, r8d; lpReserved
0x18017a4da  lea     rdx, aInstalldirecto; "InstallDirectory"
0x18017a4e1  call    cs:__imp_RegQueryValueExW
0x18017a4e7  mov     ebx, eax
0x18017a4e9  mov     ecx, 0EAh
0x18017a4ee  test    eax, eax
0x18017a4f0  jz      short loc_18017A4F6
0x18017a4f2  cmp     eax, ecx
0x18017a4f4  jnz     short loc_18017A507
0x18017a4f6  mov     edx, [rsp+268h+Type]
0x18017a4fa  lea     eax, [rdx-1]
0x18017a4fd  cmp     eax, 1
0x18017a500  jbe     short loc_18017A50B
0x18017a502  cmp     edx, 7
0x18017a505  jz      short loc_18017A50B
0x18017a507  mov     ecx, ebx
0x18017a509  jmp     short loc_18017A4AB
0x18017a50b  cmp     edx, 2
0x18017a50e  jnz     short loc_18017A589
0x18017a510  cmp     ebx, ecx
0x18017a512  jnz     short loc_18017A533
0x18017a514  mov     rcx, [rsp+268h]; this
0x18017a51c  mov     r9d, 0CEh; char *
0x18017a522  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x18017a529  mov     edx, 2E3h; void *
0x18017a52e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18017a533  mov     esi, 104h
0x18017a538  mov     edx, esi; int
0x18017a53a  mov     rcx, rdi; this
0x18017a53d  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x18017a542  mov     r8d, esi; nSize
0x18017a545  mov     rdx, rax; lpDst
0x18017a548  lea     rcx, [rsp+268h+Data]; lpSrc
0x18017a54d  call    cs:__imp_ExpandEnvironmentStringsW
0x18017a553  mov     [rsp+268h+cbData], eax
0x18017a557  lea     ecx, [rax-1]
0x18017a55a  cmp     ecx, 102h
0x18017a560  ja      short loc_18017A56A
0x18017a562  add     eax, eax
0x18017a564  mov     [rsp+268h+cbData], eax
0x18017a568  jmp     short loc_18017A5CC
0x18017a56a  mov     rcx, [rsp+268h]; this
0x18017a572  mov     r9d, 0CEh; char *
0x18017a578  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x18017a57f  mov     edx, 2E9h; void *
0x18017a584  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18017a589  cmp     ebx, ecx
0x18017a58b  mov     rcx, rdi; this
0x18017a58e  jnz     short loc_18017A5EC
0x18017a590  mov     edx, [rsp+268h+cbData]
0x18017a594  shr     edx, 1; int
0x18017a596  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x18017a59b  lea     rcx, [rsp+268h+cbData]
0x18017a5a0  mov     [rsp+268h+lpcbData], rcx; lpcbData
0x18017a5a5  mov     [rsp+268h+lpData], rax; unsigned int
0x18017a5aa  lea     r9, [rsp+268h+Type]; lpType
0x18017a5af  xor     r8d, r8d; lpReserved
0x18017a5b2  lea     rdx, aInstalldirecto; "InstallDirectory"
0x18017a5b9  mov     rcx, [rsi+0B0h]; hKey
0x18017a5c0  call    cs:__imp_RegQueryValueExW
0x18017a5c6  mov     ebx, eax
0x18017a5c8  mov     eax, [rsp+268h+cbData]
0x18017a5cc  test    ebx, ebx
0x18017a5ce  jz      short loc_18017A629
0x18017a5d0  mov     rcx, [rsp+268h]; this
0x18017a5d8  mov     r9d, ebx; char *
0x18017a5db  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x18017a5e2  mov     edx, 2FDh; void *
0x18017a5e7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18017a5ec  mov     edx, [rsp+268h+cbData]
0x18017a5f0  mov     esi, edx
0x18017a5f2  shr     edx, 1; int
0x18017a5f4  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x18017a5f9  lea     r8, [rsp+268h+Data]; wchar_t *
0x18017a5fe  mov     edx, esi; unsigned __int64
0x18017a600  mov     rcx, rax; wchar_t *
0x18017a603  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18017a608  mov     rcx, [rsp+268h]; this
0x18017a610  test    eax, eax
0x18017a612  jns     short loc_18017A5C8
0x18017a614  mov     r9d, eax; char *
0x18017a617  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\search\\com"...
0x18017a61e  mov     edx, 2F8h; void *
0x18017a623  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017a629  shr     eax, 1
0x18017a62b  mov     [rsp+268h+cbData], eax
0x18017a62f  lea     ecx, [rax-1]
0x18017a632  neg     eax
0x18017a634  sbb     edx, edx
0x18017a636  and     edx, ecx; unsigned int
0x18017a638  mov     rcx, rdi; this
0x18017a63b  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x18017a640  mov     eax, 1
0x18017a645  jmp     short loc_18017A649
0x18017a647  xor     eax, eax
0x18017a649  mov     rcx, [rsp+268h+var_18]
0x18017a651  xor     rcx, rsp; StackCookie
0x18017a654  call    __security_check_cookie
0x18017a659  lea     r11, [rsp+268h+var_8]
0x18017a661  mov     rbx, [r11+18h]
0x18017a665  mov     rsi, [r11+28h]
0x18017a669  mov     rsp, r11
0x18017a66c  pop     rdi
0x18017a66d  retn
```
