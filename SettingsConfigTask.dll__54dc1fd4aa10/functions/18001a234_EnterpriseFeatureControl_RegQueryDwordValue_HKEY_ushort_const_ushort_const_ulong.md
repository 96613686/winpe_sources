# EnterpriseFeatureControl::RegQueryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x18001a234`
- end: `0x18001a37f`
- name: `?RegQueryDwordValue@EnterpriseFeatureControl@@CAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `331`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180019ffc`

## callees

- `0x18000972c`
- `0x18001297c`
- `0x18001a234`
- `0x18001b968`
- `0x18001fb74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a2c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a2c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a315`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a315`

## string_xrefs

- `0x18001a309`: `TemporaryEnterpriseFeatureControlState`

## pseudocode

```c
__int64 __fastcall EnterpriseFeatureControl::RegQueryDwordValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HKEY *v8; // rax
  LSTATUS v9; // eax
  unsigned int v10; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-20h]
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  int v16; // [rsp+64h] [rbp+24h]
  unsigned int Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  int v19; // [rsp+74h] [rbp+34h]

  v19 = HIDWORD(a3);
  v16 = HIDWORD(a1);
  hKey[0] = 0;
  Type = 4;
  cbData = 4;
  Data = 0;
  if ( a2 )
  {
    if ( a4 )
    {
      v8 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                     hKey,
                     a2,
                     a3);
      v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, v8);
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( (v6 & 0x80000000) == 0 )
      {
        v10 = RegQueryValueExW(hKey[0], L"TemporaryEnterpriseFeatureControlState", 0, &Type, (LPBYTE)&Data, &cbData);
        if ( v10 )
        {
          v6 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x83,
                 (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
                 (const char *)v10,
                 phkResult);
          goto LABEL_18;
        }
        if ( Type == 4 )
        {
          if ( cbData == 4 )
          {
            v6 = 0;
            *a4 = Data;
            goto LABEL_18;
          }
          v6 = -2147418113;
          v7 = 135;
        }
        else
        {
          v6 = -2147418113;
          v7 = 134;
        }
      }
      else
      {
        if ( v6 + 2147024894 <= 1 )
          goto LABEL_18;
        v7 = 124;
      }
    }
    else
    {
      v6 = -2147467261;
      v7 = 120;
    }
  }
  else
  {
    v6 = -2147024809;
    v7 = 118;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
    (const char *)v6,
    phkResult);
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return v6;
}

```

## disassembly

```asm
0x18001a234  mov     qword ptr [rsp-18h+Type], r8
0x18001a239  mov     qword ptr [rsp-18h+cbData], rcx
0x18001a23e  push    rbp
0x18001a23f  push    rbx
0x18001a240  push    rdi
0x18001a241  mov     rbp, rsp
0x18001a244  sub     rsp, 40h
0x18001a248  mov     [rbp+hKey], 0
0x18001a250  mov     rdi, r9
0x18001a253  mov     [rbp+Type], 4
0x18001a25a  mov     rbx, rdx
0x18001a25d  mov     [rbp+cbData], 4
0x18001a264  mov     [rbp+Data], 0
0x18001a26b  test    rdx, rdx
0x18001a26e  jnz     short loc_18001A27C
0x18001a270  mov     ebx, 80070057h
0x18001a275  mov     edx, 76h ; 'v'
0x18001a27a  jmp     short loc_18001A289
0x18001a27c  test    rdi, rdi
0x18001a27f  jnz     short loc_18001A2A1
0x18001a281  mov     ebx, 80004003h
0x18001a286  lea     edx, [rdi+78h]; void *
0x18001a289  mov     rcx, [rbp+18h]; this
0x18001a28d  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18001a294  mov     r9d, ebx; char *
0x18001a297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a29c  jmp     loc_18001A36C
0x18001a2a1  lea     rcx, [rbp+hKey]
0x18001a2a5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001a2aa  mov     r9d, 1; samDesired
0x18001a2b0  mov     [rsp+40h+phkResult], rax; phkResult
0x18001a2b5  xor     r8d, r8d; ulOptions
0x18001a2b8  mov     rdx, rbx; lpSubKey
0x18001a2bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a2c2  call    cs:__imp_RegOpenKeyExW
0x18001a2c8  mov     ebx, eax
0x18001a2ca  test    eax, eax
0x18001a2cc  jle     short loc_18001A2D7
0x18001a2ce  movzx   ebx, ax
0x18001a2d1  or      ebx, 80070000h
0x18001a2d7  test    ebx, ebx
0x18001a2d9  jns     short loc_18001A2F1
0x18001a2db  lea     eax, [rbx+7FF8FFFEh]
0x18001a2e1  cmp     eax, 1
0x18001a2e4  jbe     loc_18001A36C
0x18001a2ea  mov     edx, 7Ch ; '|'
0x18001a2ef  jmp     short loc_18001A289
0x18001a2f1  mov     rcx, [rbp+hKey]; hKey
0x18001a2f5  lea     rax, [rbp+cbData]
0x18001a2f9  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001a2fe  lea     r9, [rbp+Type]; lpType
0x18001a302  lea     rax, [rbp+Data]
0x18001a306  xor     r8d, r8d; lpReserved
0x18001a309  lea     rdx, aTemporaryenter; "TemporaryEnterpriseFeatureControlState"
0x18001a310  mov     [rsp+40h+phkResult], rax; unsigned int
0x18001a315  call    cs:__imp_RegQueryValueExW
0x18001a31b  test    eax, eax
0x18001a31d  jz      short loc_18001A33B
0x18001a31f  mov     rcx, [rbp+18h]; this
0x18001a323  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18001a32a  mov     r9d, eax; char *
0x18001a32d  mov     edx, 83h; void *
0x18001a332  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001a337  mov     ebx, eax
0x18001a339  jmp     short loc_18001A36C
0x18001a33b  cmp     [rbp+Type], 4
0x18001a33f  jz      short loc_18001A350
0x18001a341  mov     ebx, 8000FFFFh
0x18001a346  mov     edx, 86h
0x18001a34b  jmp     loc_18001A289
0x18001a350  cmp     [rbp+cbData], 4
0x18001a354  jz      short loc_18001A365
0x18001a356  mov     ebx, 8000FFFFh
0x18001a35b  mov     edx, 87h
0x18001a360  jmp     loc_18001A289
0x18001a365  mov     eax, [rbp+Data]
0x18001a368  xor     ebx, ebx
0x18001a36a  mov     [rdi], eax
0x18001a36c  lea     rcx, [rbp+hKey]
0x18001a370  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001a375  mov     eax, ebx
0x18001a377  add     rsp, 40h
0x18001a37b  pop     rdi
0x18001a37c  pop     rbx
0x18001a37d  pop     rbp
0x18001a37e  retn
```
