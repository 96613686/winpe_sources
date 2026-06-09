# EnterpriseFeatureControl::RegQueryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x180036efc`
- end: `0x18003708a`
- name: `?RegQueryDwordValue@EnterpriseFeatureControl@@CAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `398`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180036ac8`

## callees

- `0x180007660`
- `0x1800183f4`
- `0x180036efc`
- `0x180037440`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036f9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036f9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036f67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003704b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036f67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003704b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037066`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036feb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036feb`

## string_xrefs

- `0x180036fdf`: `TemporaryEnterpriseFeatureControlState`

## pseudocode

```c
__int64 __fastcall EnterpriseFeatureControl::RegQueryDwordValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  LSTATUS v8; // eax
  unsigned int v9; // eax
  __int64 v10; // rdx
  HKEY v11; // rcx
  int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+38h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-14h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  hKey = 0;
  Type = 4;
  cbData = 4;
  *(_DWORD *)Data = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 118;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v5 = -2147467261;
    v6 = 120;
    goto LABEL_3;
  }
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, &hKey);
  v5 = v8;
  if ( v8 > 0 )
    v5 = (unsigned __int16)v8 | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( v5 + 2147024894 <= 1 )
      goto LABEL_4;
    v6 = 124;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)v5,
      phkResult);
LABEL_4:
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  v9 = RegQueryValueExW(hKey, L"TemporaryEnterpriseFeatureControlState", 0, &Type, Data, &cbData);
  if ( v9 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x83,
           (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
           (const char *)v9,
           phkResulta);
    goto LABEL_4;
  }
  if ( Type != 4 )
  {
    v10 = 134;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)0x8000FFFFLL,
      phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147549183LL;
  }
  if ( cbData != 4 )
  {
    v10 = 135;
    goto LABEL_20;
  }
  v11 = hKey;
  *a4 = *(_DWORD *)Data;
  if ( v11 )
    RegCloseKey(v11);
  return 0;
}

```

## disassembly

```asm
0x180036efc  mov     [rsp-8+arg_0], rbx
0x180036f01  mov     [rsp-8+arg_10], rdi
0x180036f06  push    rbp
0x180036f07  mov     rbp, rsp
0x180036f0a  sub     rsp, 50h
0x180036f0e  mov     rax, cs:__security_cookie
0x180036f15  xor     rax, rsp
0x180036f18  mov     [rbp+var_8], rax
0x180036f1c  mov     [rbp+hKey], 0
0x180036f24  mov     rdi, r9
0x180036f27  mov     [rbp+Type], 4
0x180036f2e  mov     [rbp+cbData], 4
0x180036f35  mov     dword ptr [rbp+Data], 0
0x180036f3c  test    rdx, rdx
0x180036f3f  jnz     short loc_180036F74
0x180036f41  mov     ebx, 80070057h
0x180036f46  mov     edx, 76h ; 'v'; void *
0x180036f4b  mov     rcx, [rbp+8]; this
0x180036f4f  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180036f56  mov     r9d, ebx; char *
0x180036f59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036f5e  mov     rcx, [rbp+hKey]; hKey
0x180036f62  test    rcx, rcx
0x180036f65  jz      short loc_180036F6D
0x180036f67  call    cs:__imp_RegCloseKey
0x180036f6d  mov     eax, ebx
0x180036f6f  jmp     loc_18003706E
0x180036f74  test    rdi, rdi
0x180036f77  jnz     short loc_180036F83
0x180036f79  mov     ebx, 80004003h
0x180036f7e  lea     edx, [rdi+78h]; lpSubKey
0x180036f81  jmp     short loc_180036F4B
0x180036f83  lea     rax, [rbp+hKey]
0x180036f87  mov     r9d, 1; samDesired
0x180036f8d  xor     r8d, r8d; ulOptions
0x180036f90  mov     [rsp+50h+phkResult], rax; phkResult
0x180036f95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180036f9c  call    cs:__imp_RegOpenKeyExW
0x180036fa2  mov     ebx, eax
0x180036fa4  test    eax, eax
0x180036fa6  jle     short loc_180036FB1
0x180036fa8  movzx   ebx, ax
0x180036fab  or      ebx, 80070000h
0x180036fb1  test    ebx, ebx
0x180036fb3  jns     short loc_180036FC7
0x180036fb5  lea     eax, [rbx+7FF8FFFEh]
0x180036fbb  cmp     eax, 1
0x180036fbe  jbe     short loc_180036F5E
0x180036fc0  mov     edx, 7Ch ; '|'
0x180036fc5  jmp     short loc_180036F4B
0x180036fc7  mov     rcx, [rbp+hKey]; hKey
0x180036fcb  lea     rax, [rbp+cbData]
0x180036fcf  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180036fd4  lea     r9, [rbp+Type]; lpType
0x180036fd8  lea     rax, [rbp+Data]
0x180036fdc  xor     r8d, r8d; lpReserved
0x180036fdf  lea     rdx, ValueName; "TemporaryEnterpriseFeatureControlState"
0x180036fe6  mov     [rsp+50h+phkResult], rax; int
0x180036feb  call    cs:__imp_RegQueryValueExW
0x180036ff1  test    eax, eax
0x180036ff3  jz      short loc_180037014
0x180036ff5  mov     rcx, [rbp+8]; this
0x180036ff9  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180037000  mov     r9d, eax; char *
0x180037003  mov     edx, 83h; void *
0x180037008  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003700d  mov     ebx, eax
0x18003700f  jmp     loc_180036F5E
0x180037014  cmp     [rbp+Type], 4
0x180037018  jz      short loc_180037021
0x18003701a  mov     edx, 86h
0x18003701f  jmp     short loc_18003702C
0x180037021  cmp     [rbp+cbData], 4
0x180037025  jz      short loc_180037058
0x180037027  mov     edx, 87h; void *
0x18003702c  mov     rcx, [rbp+8]; this
0x180037030  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180037037  mov     r9d, 8000FFFFh; char *
0x18003703d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037042  mov     rcx, [rbp+hKey]; hKey
0x180037046  test    rcx, rcx
0x180037049  jz      short loc_180037051
0x18003704b  call    cs:__imp_RegCloseKey
0x180037051  mov     eax, 8000FFFFh
0x180037056  jmp     short loc_18003706E
0x180037058  mov     rcx, [rbp+hKey]; hKey
0x18003705c  mov     eax, dword ptr [rbp+Data]
0x18003705f  mov     [rdi], eax
0x180037061  test    rcx, rcx
0x180037064  jz      short loc_18003706C
0x180037066  call    cs:__imp_RegCloseKey
0x18003706c  xor     eax, eax
0x18003706e  mov     rcx, [rbp+var_8]
0x180037072  xor     rcx, rsp; StackCookie
0x180037075  call    __security_check_cookie
0x18003707a  mov     rbx, [rsp+50h+arg_0]
0x18003707f  mov     rdi, [rsp+50h+arg_10]
0x180037084  add     rsp, 50h
0x180037088  pop     rbp
0x180037089  retn
```
