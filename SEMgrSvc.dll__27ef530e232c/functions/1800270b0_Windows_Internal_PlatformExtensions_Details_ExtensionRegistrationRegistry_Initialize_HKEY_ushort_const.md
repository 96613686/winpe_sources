# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)

- ea: `0x1800270b0`
- end: `0x1800272cc`
- name: `?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `540`
- prototype: `int(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180025720`

## callees

- `0x18000c964`
- `0x180014898`
- `0x1800270b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027119`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002712c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002712c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027124`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027124`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002718d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027212`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002727e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002718d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027212`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002727e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800270fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800270fa`

## string_xrefs

- `0x180027140`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180027196`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180027171`: `ExtensionClass`

## pseudocode

```c
int __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(
        Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  HKEY *v3; // r12
  unsigned int v5; // r14d
  HKEY v6; // r15
  HKEY v7; // rsi
  DWORD LastError; // ebx
  unsigned int ValueW; // eax
  const char *v11; // r9
  int v12; // edi
  __int64 v13; // rdx
  HKEY v14; // rcx
  unsigned int v15; // eax
  const char *v16; // r9
  HKEY v17; // rcx
  unsigned int v18; // eax
  const char *v19; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-40h]
  unsigned int phkResulta; // [rsp+20h] [rbp-40h]
  int phkResultb; // [rsp+20h] [rbp-40h]
  unsigned int phkResultc; // [rsp+20h] [rbp-40h]
  unsigned int phkResultd; // [rsp+20h] [rbp-40h]
  HKEY *v25; // [rsp+40h] [rbp-20h]
  HKEY v26; // [rsp+48h] [rbp-18h] BYREF
  char v27; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  DWORD pcbData; // [rsp+A0h] [rbp+40h] BYREF
  int pvData; // [rsp+B8h] [rbp+58h] BYREF

  v3 = (HKEY *)((char *)this + 8);
  v27 = 1;
  v25 = (HKEY *)((char *)this + 8);
  v26 = 0;
  v5 = RegOpenKeyExW(a2, a3, 0, 0x20019u, &v26);
  if ( v27 )
  {
    v6 = v26;
    v7 = *v25;
    if ( *v25 )
    {
      LastError = GetLastError();
      RegCloseKey(v7);
      SetLastError(LastError);
    }
    *v25 = v6;
  }
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xE0,
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
             (const char *)v5,
             phkResult);
  pcbData = 256;
  ValueW = RegGetValueW(*v3, 0, L"ExtensionClass", 2u, 0, (char *)this + 24, &pcbData);
  v11 = 0;
  if ( ValueW != 2 )
    v11 = (const char *)ValueW;
  if ( (_DWORD)v11 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x118,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
            v11,
            phkResulta);
    if ( v12 < 0 )
    {
      v13 = 227;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)v12,
        phkResultb);
      return v12;
    }
  }
  v14 = *v3;
  pvData = 0;
  pcbData = 4;
  v15 = RegGetValueW(v14, 0, L"Test", 0x10u, 0, &pvData, &pcbData);
  v16 = 0;
  if ( v15 != 2 )
    v16 = (const char *)v15;
  if ( (_DWORD)v16 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x118,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
            v16,
            phkResultc);
    if ( v12 < 0 )
    {
      v13 = 231;
      goto LABEL_12;
    }
  }
  v17 = *v3;
  *((_BYTE *)this + 16) = pvData != 0;
  pcbData = 4;
  v18 = RegGetValueW(v17, 0, L"VelocityFeatureId", 0x10u, 0, (char *)this + 20, &pcbData);
  v19 = 0;
  if ( v18 != 2 )
    v19 = (const char *)v18;
  if ( (_DWORD)v19 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x118,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
            v19,
            phkResultd);
    if ( v12 < 0 )
    {
      v13 = 235;
      goto LABEL_12;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800270b0  mov     [rsp-38h+arg_8], rbx
0x1800270b5  push    rbp
0x1800270b6  push    rsi
0x1800270b7  push    rdi
0x1800270b8  push    r12
0x1800270ba  push    r13
0x1800270bc  push    r14
0x1800270be  push    r15
0x1800270c0  mov     rbp, rsp
0x1800270c3  sub     rsp, 60h
0x1800270c7  lea     r12, [rcx+8]
0x1800270cb  mov     [rbp+var_10], 1
0x1800270cf  mov     r13, rcx
0x1800270d2  mov     [rbp+var_20], r12
0x1800270d6  mov     rax, r8
0x1800270d9  lea     rcx, [rbp+var_18]
0x1800270dd  mov     r10, rdx
0x1800270e0  mov     [rsp+60h+phkResult], rcx; unsigned int
0x1800270e5  xor     esi, esi
0x1800270e7  mov     rcx, r10; hKey
0x1800270ea  mov     r9d, 20019h; samDesired
0x1800270f0  mov     [rbp+var_18], rsi
0x1800270f4  xor     r8d, r8d; ulOptions
0x1800270f7  mov     rdx, rax; lpSubKey
0x1800270fa  call    cs:__imp_RegOpenKeyExW
0x180027100  mov     r14d, eax
0x180027103  cmp     [rbp+var_10], sil
0x180027107  jz      short loc_180027137
0x180027109  mov     rdi, [rbp+var_20]
0x18002710d  mov     r15, [rbp+var_18]
0x180027111  mov     rsi, [rdi]
0x180027114  test    rsi, rsi
0x180027117  jz      short loc_180027132
0x180027119  call    cs:__imp_GetLastError
0x18002711f  mov     rcx, rsi; hKey
0x180027122  mov     ebx, eax
0x180027124  call    cs:__imp_RegCloseKey
0x18002712a  mov     ecx, ebx; dwErrCode
0x18002712c  call    cs:__imp_SetLastError
0x180027132  mov     [rdi], r15
0x180027135  xor     esi, esi
0x180027137  test    r14d, r14d
0x18002713a  jz      short loc_180027159
0x18002713c  mov     rcx, [rbp+38h]; this
0x180027140  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180027147  mov     r9d, r14d; char *
0x18002714a  mov     edx, 0E0h; void *
0x18002714f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180027154  jmp     loc_1800272B4
0x180027159  lea     rcx, [rbp+arg_0]
0x18002715d  mov     [rbp+arg_0], 100h
0x180027164  mov     [rsp+60h+pcbData], rcx; pcbData
0x180027169  lea     rax, [r13+18h]
0x18002716d  mov     rcx, [r12]; hkey
0x180027171  lea     r8, aExtensionclass; "ExtensionClass"
0x180027178  mov     [rsp+60h+pvData], rax; pvData
0x18002717d  mov     r15d, 2
0x180027183  mov     r9d, r15d; dwFlags
0x180027186  mov     [rsp+60h+phkResult], rsi; int
0x18002718b  xor     edx, edx; lpSubKey
0x18002718d  call    cs:__imp_RegGetValueW
0x180027193  mov     r9d, esi
0x180027196  lea     rbx, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18002719d  cmp     eax, r15d
0x1800271a0  mov     r14d, 118h
0x1800271a6  cmovnz  r9d, eax; char *
0x1800271aa  test    r9d, r9d
0x1800271ad  jz      short loc_1800271DE
0x1800271af  mov     rcx, [rbp+38h]; this
0x1800271b3  mov     r8, rbx; unsigned int
0x1800271b6  mov     edx, r14d; void *
0x1800271b9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800271be  mov     edi, eax
0x1800271c0  test    eax, eax
0x1800271c2  jns     short loc_1800271DE
0x1800271c4  lea     edx, [r14-35h]; void *
0x1800271c8  mov     rcx, [rbp+38h]; this
0x1800271cc  mov     r9d, edi; char *
0x1800271cf  mov     r8, rbx; unsigned int
0x1800271d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800271d7  mov     eax, edi
0x1800271d9  jmp     loc_1800272B4
0x1800271de  mov     rcx, [r12]; hkey
0x1800271e2  lea     rax, [rbp+arg_0]
0x1800271e6  mov     [rsp+60h+pcbData], rax; pcbData
0x1800271eb  lea     r8, aTest; "Test"
0x1800271f2  lea     rax, [rbp+arg_18]
0x1800271f6  mov     [rbp+arg_18], esi
0x1800271f9  mov     [rsp+60h+pvData], rax; pvData
0x1800271fe  mov     r9d, 10h; dwFlags
0x180027204  xor     edx, edx; lpSubKey
0x180027206  mov     [rsp+60h+phkResult], rsi; unsigned int
0x18002720b  mov     [rbp+arg_0], 4
0x180027212  call    cs:__imp_RegGetValueW
0x180027218  cmp     eax, r15d
0x18002721b  mov     r9d, esi
0x18002721e  cmovnz  r9d, eax; char *
0x180027222  test    r9d, r9d
0x180027225  jz      short loc_180027243
0x180027227  mov     rcx, [rbp+38h]; this
0x18002722b  mov     r8, rbx; unsigned int
0x18002722e  mov     edx, r14d; void *
0x180027231  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180027236  mov     edi, eax
0x180027238  test    eax, eax
0x18002723a  jns     short loc_180027243
0x18002723c  mov     edx, 0E7h
0x180027241  jmp     short loc_1800271C8
0x180027243  cmp     [rbp+arg_18], esi
0x180027246  lea     rcx, [rbp+arg_0]
0x18002724a  mov     [rsp+60h+pcbData], rcx; pcbData
0x18002724f  lea     r8, aVelocityfeatur; "VelocityFeatureId"
0x180027256  mov     rcx, [r12]; hkey
0x18002725a  setnz   al
0x18002725d  mov     [r13+10h], al
0x180027261  mov     r9d, 10h; dwFlags
0x180027267  lea     rax, [r13+14h]
0x18002726b  mov     [rbp+arg_0], 4
0x180027272  mov     [rsp+60h+pvData], rax; pvData
0x180027277  xor     edx, edx; lpSubKey
0x180027279  mov     [rsp+60h+phkResult], rsi; unsigned int
0x18002727e  call    cs:__imp_RegGetValueW
0x180027284  cmp     eax, r15d
0x180027287  mov     r9d, esi
0x18002728a  cmovnz  r9d, eax; char *
0x18002728e  test    r9d, r9d
0x180027291  jz      short loc_1800272B2
0x180027293  mov     rcx, [rbp+38h]; this
0x180027297  mov     r8, rbx; unsigned int
0x18002729a  mov     edx, r14d; void *
0x18002729d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800272a2  mov     edi, eax
0x1800272a4  test    eax, eax
0x1800272a6  jns     short loc_1800272B2
0x1800272a8  mov     edx, 0EBh
0x1800272ad  jmp     loc_1800271C8
0x1800272b2  xor     eax, eax
0x1800272b4  mov     rbx, [rsp+60h+arg_8]
0x1800272bc  add     rsp, 60h
0x1800272c0  pop     r15
0x1800272c2  pop     r14
0x1800272c4  pop     r13
0x1800272c6  pop     r12
0x1800272c8  pop     rdi
0x1800272c9  pop     rsi
0x1800272ca  pop     rbp
0x1800272cb  retn
```
