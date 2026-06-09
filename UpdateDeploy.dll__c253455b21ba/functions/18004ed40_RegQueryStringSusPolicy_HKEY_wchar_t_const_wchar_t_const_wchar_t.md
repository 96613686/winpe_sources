# RegQueryStringSusPolicy(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x18004ed40`
- end: `0x18004ef40`
- name: `?RegQueryStringSusPolicy@@YAJPEAUHKEY__@@PEB_W1PEAPEA_W@Z`
- size: `512`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004e830`

## callees

- `0x180003180`
- `0x18000dce4`
- `0x18000dd60`
- `0x18004c26c`
- `0x18004ed40`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004edbf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004edbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004eebf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ef18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004eebf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ef18`

## string_xrefs

- `0x18004ed70`: `C:\__w\1\s\src\Client\lib\PolicyCommon\PolicyCommon.cpp`
- `0x18004edea`: `C:\__w\1\s\src\Client\lib\PolicyCommon\PolicyCommon.cpp`
- `0x18004ee95`: `C:\__w\1\s\src\Client\lib\PolicyCommon\PolicyCommon.cpp`
- `0x18004eec9`: `C:\__w\1\s\src\Client\lib\PolicyCommon\PolicyCommon.cpp`

## pseudocode

```c
__int64 __fastcall RegQueryStringSusPolicy(HKEY a1, const wchar_t *a2, const wchar_t *a3, wchar_t **a4)
{
  LSTATUS v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // edi
  __int64 v10; // rdx
  unsigned int ValueCchHelper; // eax
  int v12; // eax
  HKEY v13; // rcx
  int phkResult; // [rsp+20h] [rbp-40h]
  int phkResulta; // [rsp+20h] [rbp-40h]
  int phkResultb; // [rsp+20h] [rbp-40h]
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\PolicyCommon\\PolicyCommon.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return 2147500035LL;
  }
  *a4 = 0;
  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, &hKey);
  v9 = (unsigned __int16)v7 | 0x80070000;
  if ( v7 <= 0 )
    v9 = v7;
  if ( v9 == -2147024894 )
  {
    v10 = 63;
LABEL_7:
    v9 = -2145124326;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\PolicyCommon\\PolicyCommon.cpp",
      (const char *)v9,
      phkResulta);
LABEL_18:
    if ( hKey )
      RegCloseKey(hKey);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\PolicyCommon\\PolicyCommon.cpp",
      (const char *)v9,
      phkResultb);
    return v9;
  }
  if ( (v9 & 0x80000000) != 0 )
  {
    v10 = 64;
    goto LABEL_8;
  }
  phkResulta = 0;
  ValueCchHelper = SafeRegQueryValueCchHelper(v8, hKey, a3, 0);
  v9 = ValueCchHelper;
  if ( ValueCchHelper == -2147024894 )
  {
    v10 = 67;
    goto LABEL_7;
  }
  if ( (int)(ValueCchHelper + 0x80000000) >= 0 && ValueCchHelper != -2147024662 )
  {
    v10 = 68;
    goto LABEL_8;
  }
  v12 = SafeRegQueryValueCchHelper(0, hKey, a3, 0);
  v9 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\PolicyCommon\\PolicyCommon.cpp",
      (const char *)(unsigned int)v12,
      0);
    goto LABEL_18;
  }
  v13 = hKey;
  *a4 = 0;
  if ( v13 )
    RegCloseKey(v13);
  return 0;
}

```

## disassembly

```asm
0x18004ed40  mov     [rsp-28h+arg_0], rbx
0x18004ed45  push    rbp
0x18004ed46  push    rsi
0x18004ed47  push    rdi
0x18004ed48  push    r14
0x18004ed4a  push    r15
0x18004ed4c  mov     rbp, rsp
0x18004ed4f  sub     rsp, 60h
0x18004ed53  mov     rax, cs:__security_cookie
0x18004ed5a  xor     rax, rsp
0x18004ed5d  mov     [rbp+var_10], rax
0x18004ed61  mov     r14, r9
0x18004ed64  mov     r15, r8
0x18004ed67  test    r9, r9
0x18004ed6a  jnz     short loc_18004ED90
0x18004ed6c  mov     rcx, [rbp+28h]; this
0x18004ed70  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\Policy"...
0x18004ed77  mov     ebx, 80004003h
0x18004ed7c  mov     edx, 96h; void *
0x18004ed81  mov     r9d, ebx; char *
0x18004ed84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ed89  mov     eax, ebx
0x18004ed8b  jmp     loc_18004EF20
0x18004ed90  mov     qword ptr [r9], 0
0x18004ed97  lea     rax, [rbp+hKey]
0x18004ed9b  mov     r9d, 1; samDesired
0x18004eda1  mov     [rsp+60h+phkResult], rax; int
0x18004eda6  xor     r8d, r8d; ulOptions
0x18004eda9  mov     [rbp+hKey], 0
0x18004edb1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004edb8  mov     [rbp+var_20], 0
0x18004edbf  call    cs:__imp_RegOpenKeyExW
0x18004edc5  movzx   edi, ax
0x18004edc8  mov     ebx, 80070002h
0x18004edcd  or      edi, 80070000h
0x18004edd3  test    eax, eax
0x18004edd5  cmovle  edi, eax
0x18004edd8  cmp     edi, ebx
0x18004edda  jnz     short loc_18004EDFE
0x18004eddc  mov     edx, 3Fh ; '?'; void *
0x18004ede1  mov     edi, 8024001Ah
0x18004ede6  mov     rcx, [rbp+28h]; this
0x18004edea  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\Policy"...
0x18004edf1  mov     r9d, edi; char *
0x18004edf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004edf9  jmp     loc_18004EEB6
0x18004edfe  test    edi, edi
0x18004ee00  jns     short loc_18004EE09
0x18004ee02  mov     edx, 40h ; '@'
0x18004ee07  jmp     short loc_18004EDE6
0x18004ee09  mov     rdx, [rbp+hKey]
0x18004ee0d  lea     rax, [rbp+var_20]
0x18004ee11  mov     [rsp+60h+var_30], 0
0x18004ee1a  xor     r9d, r9d
0x18004ee1d  mov     [rsp+60h+var_38], rax
0x18004ee22  mov     r8, r15
0x18004ee25  mov     dword ptr [rsp+60h+phkResult], 0
0x18004ee2d  call    SafeRegQueryValueCchHelper
0x18004ee32  mov     edi, eax
0x18004ee34  cmp     eax, ebx
0x18004ee36  jnz     short loc_18004EE3F
0x18004ee38  mov     edx, 43h ; 'C'
0x18004ee3d  jmp     short loc_18004EDE1
0x18004ee3f  mov     ecx, 80000000h
0x18004ee44  add     eax, ecx
0x18004ee46  test    ecx, eax
0x18004ee48  jnz     short loc_18004EE59
0x18004ee4a  cmp     edi, 800700EAh
0x18004ee50  jz      short loc_18004EE59
0x18004ee52  mov     edx, 44h ; 'D'
0x18004ee57  jmp     short loc_18004EDE6
0x18004ee59  movsxd  rsi, [rbp+var_20]
0x18004ee5d  mov     rcx, rsi; unsigned __int64
0x18004ee60  test    esi, esi
0x18004ee62  jnz     short loc_18004EEE1
0x18004ee64  xor     ebx, ebx
0x18004ee66  mov     rdx, [rbp+hKey]
0x18004ee6a  lea     rax, [rbp+var_20]
0x18004ee6e  mov     [rsp+60h+var_30], 0
0x18004ee77  mov     r9, rbx
0x18004ee7a  mov     [rsp+60h+var_38], rax
0x18004ee7f  mov     r8, r15
0x18004ee82  mov     dword ptr [rsp+60h+phkResult], esi; int
0x18004ee86  call    SafeRegQueryValueCchHelper
0x18004ee8b  mov     edi, eax
0x18004ee8d  test    eax, eax
0x18004ee8f  jns     short loc_18004EF0C
0x18004ee91  mov     rcx, [rbp+28h]; this
0x18004ee95  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\Policy"...
0x18004ee9c  mov     r9d, eax; char *
0x18004ee9f  mov     edx, 50h ; 'P'; void *
0x18004eea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eea9  test    rbx, rbx
0x18004eeac  jz      short loc_18004EEB6
0x18004eeae  mov     rcx, rbx; lpMem
0x18004eeb1  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18004eeb6  mov     rcx, [rbp+hKey]; hKey
0x18004eeba  test    rcx, rcx
0x18004eebd  jz      short loc_18004EEC5
0x18004eebf  call    cs:__imp_RegCloseKey
0x18004eec5  mov     rcx, [rbp+28h]; this
0x18004eec9  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\Policy"...
0x18004eed0  mov     r9d, edi; char *
0x18004eed3  mov     edx, 98h; void *
0x18004eed8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eedd  mov     eax, edi
0x18004eedf  jmp     short loc_18004EF20
0x18004eee1  mov     edx, 2; unsigned __int64
0x18004eee6  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18004eeeb  mov     rbx, rax
0x18004eeee  neg     rax
0x18004eef1  sbb     edi, edi
0x18004eef3  not     edi
0x18004eef5  and     edi, 8007000Eh
0x18004eefb  test    rbx, rbx
0x18004eefe  jnz     loc_18004EE66
0x18004ef04  lea     edx, [rbx+4Eh]
0x18004ef07  jmp     loc_18004EDE6
0x18004ef0c  mov     rcx, [rbp+hKey]; hKey
0x18004ef10  mov     [r14], rbx
0x18004ef13  test    rcx, rcx
0x18004ef16  jz      short loc_18004EF1E
0x18004ef18  call    cs:__imp_RegCloseKey
0x18004ef1e  xor     eax, eax
0x18004ef20  mov     rcx, [rbp+var_10]
0x18004ef24  xor     rcx, rsp; StackCookie
0x18004ef27  call    __security_check_cookie
0x18004ef2c  mov     rbx, [rsp+60h+arg_0]
0x18004ef34  add     rsp, 60h
0x18004ef38  pop     r15
0x18004ef3a  pop     r14
0x18004ef3c  pop     rdi
0x18004ef3d  pop     rsi
0x18004ef3e  pop     rbp
0x18004ef3f  retn
```
