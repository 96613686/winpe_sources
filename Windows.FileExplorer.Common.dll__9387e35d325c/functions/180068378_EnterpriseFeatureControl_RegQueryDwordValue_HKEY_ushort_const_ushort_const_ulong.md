# EnterpriseFeatureControl::RegQueryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x180068378`
- end: `0x1800684c9`
- name: `?RegQueryDwordValue@EnterpriseFeatureControl@@CAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `337`
- prototype: `static int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180068140`

## callees

- `0x180004d6c`
- `0x1800077c8`
- `0x18002037c`
- `0x18002edcc`
- `0x180068378`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006840c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006840c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006845f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006845f`

## string_xrefs

- `0x180068453`: `TemporaryEnterpriseFeatureControlState`

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
  LSTATUS v8; // eax
  unsigned int v9; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-20h]
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  int v15; // [rsp+64h] [rbp+24h]
  unsigned int Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  int v18; // [rsp+74h] [rbp+34h]

  v18 = HIDWORD(a3);
  v15 = HIDWORD(a1);
  hKey[0] = 0;
  Type = 4;
  cbData = 4;
  Data = 0;
  if ( a2 )
  {
    if ( a4 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        hKey,
        0);
      v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, hKey);
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      if ( (v6 & 0x80000000) == 0 )
      {
        v9 = RegQueryValueExW(hKey[0], L"TemporaryEnterpriseFeatureControlState", 0, &Type, (LPBYTE)&Data, &cbData);
        if ( v9 )
        {
          v6 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x83,
                 (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
                 (const char *)v9,
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
0x180068378  mov     qword ptr [rsp-18h+Type], r8
0x18006837d  mov     qword ptr [rsp-18h+cbData], rcx
0x180068382  push    rbp
0x180068383  push    rbx
0x180068384  push    rdi
0x180068385  mov     rbp, rsp
0x180068388  sub     rsp, 40h
0x18006838c  mov     [rbp+hKey], 0
0x180068394  mov     rdi, r9
0x180068397  mov     [rbp+Type], 4
0x18006839e  mov     rbx, rdx
0x1800683a1  mov     [rbp+cbData], 4
0x1800683a8  mov     [rbp+Data], 0
0x1800683af  test    rdx, rdx
0x1800683b2  jnz     short loc_1800683C0
0x1800683b4  mov     ebx, 80070057h
0x1800683b9  mov     edx, 76h ; 'v'
0x1800683be  jmp     short loc_1800683CD
0x1800683c0  test    rdi, rdi
0x1800683c3  jnz     short loc_1800683E5
0x1800683c5  mov     ebx, 80004003h
0x1800683ca  lea     edx, [rdi+78h]; void *
0x1800683cd  mov     rcx, [rbp+18h]; this
0x1800683d1  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800683d8  mov     r9d, ebx; char *
0x1800683db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800683e0  jmp     loc_1800684B6
0x1800683e5  xor     edx, edx
0x1800683e7  lea     rcx, [rbp+hKey]
0x1800683eb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800683f0  lea     rax, [rbp+hKey]
0x1800683f4  mov     r9d, 1; samDesired
0x1800683fa  xor     r8d, r8d; ulOptions
0x1800683fd  mov     [rsp+40h+phkResult], rax; phkResult
0x180068402  mov     rdx, rbx; lpSubKey
0x180068405  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006840c  call    cs:__imp_RegOpenKeyExW
0x180068412  mov     ebx, eax
0x180068414  test    eax, eax
0x180068416  jle     short loc_180068421
0x180068418  movzx   ebx, ax
0x18006841b  or      ebx, 80070000h
0x180068421  test    ebx, ebx
0x180068423  jns     short loc_18006843B
0x180068425  lea     eax, [rbx+7FF8FFFEh]
0x18006842b  cmp     eax, 1
0x18006842e  jbe     loc_1800684B6
0x180068434  mov     edx, 7Ch ; '|'
0x180068439  jmp     short loc_1800683CD
0x18006843b  mov     rcx, [rbp+hKey]; hKey
0x18006843f  lea     rax, [rbp+cbData]
0x180068443  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180068448  lea     r9, [rbp+Type]; lpType
0x18006844c  lea     rax, [rbp+Data]
0x180068450  xor     r8d, r8d; lpReserved
0x180068453  lea     rdx, aTemporaryenter; "TemporaryEnterpriseFeatureControlState"
0x18006845a  mov     [rsp+40h+phkResult], rax; unsigned int
0x18006845f  call    cs:__imp_RegQueryValueExW
0x180068465  test    eax, eax
0x180068467  jz      short loc_180068485
0x180068469  mov     rcx, [rbp+18h]; this
0x18006846d  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180068474  mov     r9d, eax; char *
0x180068477  mov     edx, 83h; void *
0x18006847c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180068481  mov     ebx, eax
0x180068483  jmp     short loc_1800684B6
0x180068485  cmp     [rbp+Type], 4
0x180068489  jz      short loc_18006849A
0x18006848b  mov     ebx, 8000FFFFh
0x180068490  mov     edx, 86h
0x180068495  jmp     loc_1800683CD
0x18006849a  cmp     [rbp+cbData], 4
0x18006849e  jz      short loc_1800684AF
0x1800684a0  mov     ebx, 8000FFFFh
0x1800684a5  mov     edx, 87h
0x1800684aa  jmp     loc_1800683CD
0x1800684af  mov     eax, [rbp+Data]
0x1800684b2  xor     ebx, ebx
0x1800684b4  mov     [rdi], eax
0x1800684b6  lea     rcx, [rbp+hKey]
0x1800684ba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800684bf  mov     eax, ebx
0x1800684c1  add     rsp, 40h
0x1800684c5  pop     rdi
0x1800684c6  pop     rbx
0x1800684c7  pop     rbp
0x1800684c8  retn
```
