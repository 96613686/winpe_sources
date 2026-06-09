# CIdentityProfileHandler::_MigrateRegKey(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180014de4`
- end: `0x18001517b`
- name: `?_MigrateRegKey@CIdentityProfileHandler@@AEAAJPEAUHKEY__@@PEBG11@Z`
- size: `919`
- prototype: `__int64 __fastcall(CIdentityProfileHandler *this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800147a0`

## callees

- `0x180002030`
- `0x180003560`
- `0x18000acb0`
- `0x18001448c`
- `0x1800144b4`
- `0x1800145a0`
- `0x180014974`
- `0x180014de4`
- `0x180015374`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180015069`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180015069`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001511c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001512f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001511c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001512f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014fa1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014fa1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014f16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014f16`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180015018`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180015018`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001514a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001515b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001514a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001515b`

## pseudocode

```c
__int64 __fastcall CIdentityProfileHandler::_MigrateRegKey(
        CIdentityProfileHandler *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  WCHAR *v6; // rbx
  CIdentityProfileHandler *v8; // rcx
  __int64 v9; // rdx
  CIdentityProfileHandler *v10; // rcx
  __int64 v11; // r8
  int v12; // esi
  const unsigned __int16 *v13; // r14
  CIdentityProfileHandler *v14; // rcx
  CIdentityProfileHandler *v15; // rcx
  __int64 v16; // rdx
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-30h] BYREF
  LPCWSTR v19; // [rsp+58h] [rbp-28h] BYREF
  HKEY hKeyDest; // [rsp+60h] [rbp-20h] BYREF
  HKEY hKeySrc; // [rsp+68h] [rbp-18h] BYREF
  _BYTE v22[16]; // [rsp+70h] [rbp-10h] BYREF
  CIdentityProfileHandler *dwDisposition; // [rsp+B0h] [rbp+30h] BYREF
  int PathKey; // [rsp+B8h] [rbp+38h] BYREF
  int v25; // [rsp+BCh] [rbp+3Ch]

  v25 = HIDWORD(a2);
  dwDisposition = this;
  lpSubKey = 0;
  v6 = 0;
  v19 = 0;
  PathKey = 0;
  CLogBlock::CLogBlock((CLogBlock *)v22, "CIdentityProfileHandler::_MigrateRegKey", &PathKey);
  LODWORD(dwDisposition) = 0;
  hKeySrc = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  hKeyDest = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  PathKey = CIdentityProfileHandler::_CreatePathKey(v8, a3, a4, (void **)&lpSubKey);
  v12 = PathKey;
  if ( PathKey < 0 )
  {
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v11, (_DWORD)a3, (__int64)a4, PathKey);
LABEL_5:
      v12 = PathKey;
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  v13 = a5;
  PathKey = CIdentityProfileHandler::_CreatePathKey(v10, a3, a5, (void **)&v19);
  v12 = PathKey;
  if ( PathKey >= 0 )
  {
    v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKeySrc);
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)WPP_0955e053d70b3b28b837838791dca877_Traceguids,
          (_DWORD)lpSubKey,
          v12);
      }
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v6 = (WCHAR *)v19;
      goto LABEL_43;
    }
    v6 = (WCHAR *)v19;
    v12 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0, 0, 0xF003Fu, 0, &hKeyDest, (LPDWORD)&dwDisposition);
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)WPP_0955e053d70b3b28b837838791dca877_Traceguids,
          (_DWORD)v6,
          v12);
      }
      goto LABEL_41;
    }
    if ( (_DWORD)dwDisposition != 1 )
    {
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_0955e053d70b3b28b837838791dca877_Traceguids);
      }
      v12 = -2146893052;
      goto LABEL_43;
    }
    PathKey = CIdentityProfileHandler::_AdjustRegSidKeyForUser(v14, hKeyDest, v13);
    v12 = PathKey;
    if ( PathKey < 0 )
    {
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_0955e053d70b3b28b837838791dca877_Traceguids,
          (unsigned int)PathKey);
        goto LABEL_5;
      }
      goto LABEL_44;
    }
    v12 = RegCopyTreeW(hKeySrc, 0, hKeyDest);
    if ( v12 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v16 = 32;
LABEL_28:
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_0955e053d70b3b28b837838791dca877_Traceguids, (unsigned int)v12);
      }
    }
    else
    {
      v12 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, lpSubKey);
      if ( !v12 )
      {
        v12 = 0;
LABEL_43:
        PathKey = v12;
        goto LABEL_44;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v16 = 33;
        goto LABEL_28;
      }
    }
LABEL_41:
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v11, (_DWORD)a3, (__int64)v13, PathKey);
    v6 = (WCHAR *)v19;
    goto LABEL_5;
  }
  v6 = (WCHAR *)v19;
LABEL_44:
  if ( hKeyDest != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(hKeyDest);
    hKeyDest = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( hKeySrc != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(hKeySrc);
    hKeySrc = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  CLogBlock::~CLogBlock((CLogBlock *)v22, v9, v11);
  if ( v6 )
    LocalFree(v6);
  if ( lpSubKey )
    LocalFree((HLOCAL)lpSubKey);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180014de4  mov     [rsp-28h+arg_10], rbx
0x180014de9  mov     qword ptr [rsp-28h+arg_8], rdx
0x180014dee  mov     [rsp-28h+dwDisposition], rcx
0x180014df3  push    rbp
0x180014df4  push    rsi
0x180014df5  push    r13
0x180014df7  push    r14
0x180014df9  push    r15
0x180014dfb  mov     rbp, rsp
0x180014dfe  sub     rsp, 80h
0x180014e05  mov     r15, r8
0x180014e08  mov     [rbp+lpSubKey], 0
0x180014e10  xor     ebx, ebx
0x180014e12  lea     r8, [rbp+arg_8]; int *
0x180014e16  lea     rdx, aCidentityprofi_2; "CIdentityProfileHandler::_MigrateRegKey"
0x180014e1d  mov     [rbp+var_28], rbx
0x180014e21  lea     rcx, [rbp+var_10]; this
0x180014e25  mov     [rbp+arg_8], ebx
0x180014e28  mov     r14, r9
0x180014e2b  call    ??0CLogBlock@@QEAA@PEBDPEAJ@Z; CLogBlock::CLogBlock(char const *,long *)
0x180014e30  or      r13, 0FFFFFFFFFFFFFFFFh
0x180014e34  mov     dword ptr [rbp+dwDisposition], ebx
0x180014e37  lea     r9, [rbp+lpSubKey]; void **
0x180014e3b  mov     [rbp+hKeySrc], r13
0x180014e3f  mov     r8, r14; unsigned __int16 *
0x180014e42  mov     [rbp+hKeyDest], r13
0x180014e46  mov     rdx, r15; unsigned __int16 *
0x180014e49  call    ?_CreatePathKey@CIdentityProfileHandler@@AEAAJPEBG0PEAPEAX@Z; CIdentityProfileHandler::_CreatePathKey(ushort const *,ushort const *,void * *)
0x180014e4e  mov     [rbp+arg_8], eax
0x180014e51  mov     esi, eax
0x180014e53  test    eax, eax
0x180014e55  jns     short loc_180014E98
0x180014e57  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e5e  lea     rax, WPP_GLOBAL_Control
0x180014e65  cmp     rcx, rax
0x180014e68  jz      loc_180015113
0x180014e6e  test    byte ptr [rcx+1Ch], 4
0x180014e72  jz      loc_180015113
0x180014e78  mov     rcx, [rcx+10h]
0x180014e7c  lea     edx, [rbx+1Ah]
0x180014e7f  mov     [rsp+80h+samDesired], esi
0x180014e83  mov     r9, r15
0x180014e86  mov     [rsp+80h+phkResult], r14
0x180014e8b  call    WPP_SF_SSd
0x180014e90  mov     esi, [rbp+arg_8]
0x180014e93  jmp     loc_180015113
0x180014e98  mov     r14, [rbp+arg_20]
0x180014e9c  lea     r9, [rbp+var_28]; void **
0x180014ea0  mov     r8, r14; unsigned __int16 *
0x180014ea3  mov     rdx, r15; unsigned __int16 *
0x180014ea6  call    ?_CreatePathKey@CIdentityProfileHandler@@AEAAJPEBG0PEAPEAX@Z; CIdentityProfileHandler::_CreatePathKey(ushort const *,ushort const *,void * *)
0x180014eab  mov     [rbp+arg_8], eax
0x180014eae  mov     esi, eax
0x180014eb0  test    eax, eax
0x180014eb2  jns     short loc_180014EF6
0x180014eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ebb  lea     rax, WPP_GLOBAL_Control
0x180014ec2  cmp     rcx, rax
0x180014ec5  jz      short loc_180014EED
0x180014ec7  test    byte ptr [rcx+1Ch], 4
0x180014ecb  jz      short loc_180014EED
0x180014ecd  mov     rcx, [rcx+10h]
0x180014ed1  mov     edx, 1Bh
0x180014ed6  mov     [rsp+80h+samDesired], esi
0x180014eda  mov     r9, r15
0x180014edd  mov     [rsp+80h+phkResult], r14
0x180014ee2  call    WPP_SF_SSd
0x180014ee7  mov     rbx, [rbp+var_28]
0x180014eeb  jmp     short loc_180014E90
0x180014eed  mov     rbx, [rbp+var_28]
0x180014ef1  jmp     loc_180015113
0x180014ef6  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180014efa  lea     rax, [rbp+hKeySrc]
0x180014efe  mov     r15, 0FFFFFFFF80000002h
0x180014f05  mov     [rsp+80h+phkResult], rax; phkResult
0x180014f0a  mov     rcx, r15; hKey
0x180014f0d  mov     r9d, 20019h; samDesired
0x180014f13  xor     r8d, r8d; ulOptions
0x180014f16  call    cs:__imp_RegOpenKeyExW
0x180014f1c  mov     esi, eax
0x180014f1e  test    eax, eax
0x180014f20  jz      short loc_180014F6E
0x180014f22  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f29  lea     rax, WPP_GLOBAL_Control
0x180014f30  cmp     rcx, rax
0x180014f33  jz      short loc_180014F58
0x180014f35  test    byte ptr [rcx+1Ch], 4
0x180014f39  jz      short loc_180014F58
0x180014f3b  mov     r9, [rbp+lpSubKey]
0x180014f3f  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x180014f46  mov     rcx, [rcx+10h]
0x180014f4a  mov     edx, 1Ch
0x180014f4f  mov     dword ptr [rsp+80h+phkResult], esi
0x180014f53  call    WPP_SF_Sd
0x180014f58  test    esi, esi
0x180014f5a  jle     short loc_180014F65
0x180014f5c  movzx   esi, si
0x180014f5f  or      esi, 80070000h
0x180014f65  mov     rbx, [rbp+var_28]
0x180014f69  jmp     loc_180015110
0x180014f6e  lea     rax, [rbp+dwDisposition]
0x180014f72  xor     r9d, r9d; lpClass
0x180014f75  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x180014f7a  xor     r8d, r8d; Reserved
0x180014f7d  lea     rax, [rbp+hKeyDest]
0x180014f81  mov     rcx, r15; hKey
0x180014f84  mov     [rsp+80h+var_48], rax; phkResult
0x180014f89  mov     [rsp+80h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180014f8e  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x180014f96  mov     dword ptr [rsp+80h+phkResult], ebx; dwOptions
0x180014f9a  mov     rbx, [rbp+var_28]
0x180014f9e  mov     rdx, rbx; lpSubKey
0x180014fa1  call    cs:__imp_RegCreateKeyExW
0x180014fa7  mov     esi, eax
0x180014fa9  test    eax, eax
0x180014fab  jnz     loc_1800150CE
0x180014fb1  cmp     dword ptr [rbp+dwDisposition], 1
0x180014fb5  jnz     loc_180015099
0x180014fbb  mov     rdx, [rbp+hKeyDest]; HKEY
0x180014fbf  mov     r8, r14; unsigned __int16 *
0x180014fc2  call    ?_AdjustRegSidKeyForUser@CIdentityProfileHandler@@AEAAJPEAUHKEY__@@PEBG@Z; CIdentityProfileHandler::_AdjustRegSidKeyForUser(HKEY__ *,ushort const *)
0x180014fc7  mov     [rbp+arg_8], eax
0x180014fca  mov     esi, eax
0x180014fcc  test    eax, eax
0x180014fce  jns     short loc_18001500E
0x180014fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fd7  lea     rax, WPP_GLOBAL_Control
0x180014fde  cmp     rcx, rax
0x180014fe1  jz      loc_180015113
0x180014fe7  test    byte ptr [rcx+1Ch], 4
0x180014feb  jz      loc_180015113
0x180014ff1  mov     rcx, [rcx+10h]
0x180014ff5  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x180014ffc  mov     edx, 1Dh
0x180015001  mov     r9d, esi
0x180015004  call    WPP_SF_d
0x180015009  jmp     loc_180014E90
0x18001500e  mov     r8, [rbp+hKeyDest]; hKeyDest
0x180015012  xor     edx, edx; lpSubKey
0x180015014  mov     rcx, [rbp+hKeySrc]; hKeySrc
0x180015018  call    cs:__imp_RegCopyTreeW
0x18001501e  mov     esi, eax
0x180015020  test    eax, eax
0x180015022  jz      short loc_180015062
0x180015024  mov     rcx, cs:WPP_GLOBAL_Control
0x18001502b  lea     rax, WPP_GLOBAL_Control
0x180015032  cmp     rcx, rax
0x180015035  jz      loc_180015103
0x18001503b  test    byte ptr [rcx+1Ch], 4
0x18001503f  jz      loc_180015103
0x180015045  mov     edx, 20h ; ' '
0x18001504a  mov     rcx, [rcx+10h]
0x18001504e  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x180015055  mov     r9d, esi
0x180015058  call    WPP_SF_d
0x18001505d  jmp     loc_180015103
0x180015062  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180015066  mov     rcx, r15; hKey
0x180015069  call    cs:__imp_RegDeleteTreeW
0x18001506f  mov     esi, eax
0x180015071  test    eax, eax
0x180015073  jz      short loc_180015095
0x180015075  mov     rcx, cs:WPP_GLOBAL_Control
0x18001507c  lea     rax, WPP_GLOBAL_Control
0x180015083  cmp     rcx, rax
0x180015086  jz      short loc_180015103
0x180015088  test    byte ptr [rcx+1Ch], 4
0x18001508c  jz      short loc_180015103
0x18001508e  mov     edx, 21h ; '!'
0x180015093  jmp     short loc_18001504A
0x180015095  xor     esi, esi
0x180015097  jmp     short loc_180015110
0x180015099  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150a0  lea     rax, WPP_GLOBAL_Control
0x1800150a7  cmp     rcx, rax
0x1800150aa  jz      short loc_1800150C7
0x1800150ac  test    byte ptr [rcx+1Ch], 4
0x1800150b0  jz      short loc_1800150C7
0x1800150b2  mov     rcx, [rcx+10h]
0x1800150b6  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x1800150bd  mov     edx, 1Eh
0x1800150c2  call    WPP_SF_
0x1800150c7  mov     esi, 80090304h
0x1800150cc  jmp     short loc_180015110
0x1800150ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150d5  lea     rax, WPP_GLOBAL_Control
0x1800150dc  cmp     rcx, rax
0x1800150df  jz      short loc_180015103
0x1800150e1  test    byte ptr [rcx+1Ch], 4
0x1800150e5  jz      short loc_180015103
0x1800150e7  mov     rcx, [rcx+10h]
0x1800150eb  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x1800150f2  mov     edx, 1Fh
0x1800150f7  mov     dword ptr [rsp+80h+phkResult], esi
0x1800150fb  mov     r9, rbx
0x1800150fe  call    WPP_SF_Sd
0x180015103  test    esi, esi
0x180015105  jle     short loc_180015110
0x180015107  movzx   esi, si
0x18001510a  or      esi, 80070000h
0x180015110  mov     [rbp+arg_8], esi
0x180015113  mov     rcx, [rbp+hKeyDest]; hKey
0x180015117  cmp     rcx, r13
0x18001511a  jz      short loc_180015126
0x18001511c  call    cs:__imp_RegCloseKey
0x180015122  mov     [rbp+hKeyDest], r13
0x180015126  mov     rcx, [rbp+hKeySrc]; hKey
0x18001512a  cmp     rcx, r13
0x18001512d  jz      short loc_180015139
0x18001512f  call    cs:__imp_RegCloseKey
0x180015135  mov     [rbp+hKeySrc], r13
0x180015139  lea     rcx, [rbp+var_10]; this
0x18001513d  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180015142  test    rbx, rbx
0x180015145  jz      short loc_180015150
0x180015147  mov     rcx, rbx; hMem
0x18001514a  call    cs:__imp_LocalFree
0x180015150  cmp     [rbp+lpSubKey], 0
0x180015155  jz      short loc_180015161
0x180015157  mov     rcx, [rbp+lpSubKey]; hMem
0x18001515b  call    cs:__imp_LocalFree
0x180015161  mov     rbx, [rsp+80h+arg_10]
0x180015169  mov     eax, esi
0x18001516b  add     rsp, 80h
0x180015172  pop     r15
0x180015174  pop     r14
0x180015176  pop     r13
0x180015178  pop     rsi
0x180015179  pop     rbp
0x18001517a  retn
```
