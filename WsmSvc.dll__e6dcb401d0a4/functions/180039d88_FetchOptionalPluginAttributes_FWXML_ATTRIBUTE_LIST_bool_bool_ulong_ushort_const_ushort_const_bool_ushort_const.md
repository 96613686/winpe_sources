# FetchOptionalPluginAttributes(FWXML_ATTRIBUTE_LIST *,bool *,bool *,ulong *,ushort const * *,ushort const * *,bool *,ushort const * *)

- ea: `0x180039d88`
- end: `0x18003a38d`
- name: `?FetchOptionalPluginAttributes@@YAHPEAUFWXML_ATTRIBUTE_LIST@@PEA_N1PEAKPEAPEBG313@Z`
- size: `1541`
- prototype: `__int64 __fastcall(struct FWXML_ATTRIBUTE_LIST *, bool *, bool *, unsigned int *, const unsigned __int16 **, const unsigned __int16 **, bool *, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180037950`
- `0x180194ec8`
- `0x18019752c`

## callees

- `0x180005d10`
- `0x180035ee0`
- `0x180039d88`
- `0x18003a610`
- `0x18003c640`
- `0x180112380`

## import_xrefs

- `msvcrt!_wtoi` at `0x180039f9e`
- `msvcrt!_wtoi` at `0x180039f9e`
- `msvcrt!_wcsnicmp` at `0x180039e74`
- `msvcrt!_wcsnicmp` at `0x180039f82`
- `msvcrt!_wcsnicmp` at `0x180039fe1`
- `msvcrt!_wcsnicmp` at `0x18003a03a`
- `msvcrt!_wcsnicmp` at `0x18003a093`
- `msvcrt!_wcsnicmp` at `0x18003a116`
- `msvcrt!_wcsnicmp` at `0x18003a15e`
- `msvcrt!_wcsnicmp` at `0x180039e74`
- `msvcrt!_wcsnicmp` at `0x180039f82`
- `msvcrt!_wcsnicmp` at `0x180039fe1`
- `msvcrt!_wcsnicmp` at `0x18003a03a`
- `msvcrt!_wcsnicmp` at `0x18003a093`
- `msvcrt!_wcsnicmp` at `0x18003a116`
- `msvcrt!_wcsnicmp` at `0x18003a15e`
- `msvcrt!_wcsicmp` at `0x18003a0be`
- `msvcrt!_wcsicmp` at `0x18003a0be`

## string_xrefs

- `0x18003a214`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003a240`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003a26c`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003a298`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003a2c4`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003a329`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003a355`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180039f75`: `ProcessIdleTimeoutSec`
- `0x180039f13`: `onecore\admin\wmi\wmx\config\configxmladditionalvalidation.cpp`

## pseudocode

```c
__int64 __fastcall FetchOptionalPluginAttributes(
        struct FWXML_ATTRIBUTE_LIST *a1,
        bool *a2,
        bool *a3,
        unsigned int *a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6,
        bool *a7,
        const unsigned __int16 **a8)
{
  int v11; // esi
  _QWORD *v12; // rdi
  __int64 v13; // r15
  __int64 v14; // rcx
  const wchar_t *v15; // rax
  wchar_t *AttributeValue; // rax
  int i; // esi
  __int64 v18; // r14
  __int64 v19; // rcx
  const unsigned __int16 *v20; // r8
  unsigned int v21; // edx
  const wchar_t *v23; // rax
  const wchar_t *v24; // rax
  int j; // esi
  __int64 v26; // r14
  __int64 v27; // rcx
  const wchar_t *v28; // rax
  int k; // esi
  __int64 v30; // r14
  __int64 v31; // rcx
  const wchar_t *v32; // rax
  int m; // esi
  __int64 v34; // r14
  __int64 v35; // rcx
  const wchar_t *v36; // rax
  const wchar_t *v37; // rsi
  int ii; // esi
  __int64 v39; // r14
  __int64 v40; // rcx
  const wchar_t *v41; // rax
  int n; // esi
  __int64 v43; // r15
  __int64 v44; // rcx
  const wchar_t *v45; // rax
  wchar_t *v46; // rax
  bool *v47; // [rsp+70h] [rbp+18h]

  v47 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
    a3 = v47;
  }
  if ( !a1 )
  {
    v20 = L"912";
    v21 = 912;
LABEL_25:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmladditionalvalidation.cpp", v21, v20, 0x54Fu, 0);
    return 0;
  }
  if ( !a2 )
  {
    v20 = L"913";
    v21 = 913;
    goto LABEL_25;
  }
  if ( !a3 )
  {
    v20 = L"914";
    v21 = 914;
    goto LABEL_25;
  }
  if ( !a4 )
  {
    v20 = L"915";
    v21 = 915;
    goto LABEL_25;
  }
  if ( !a5 )
  {
    v20 = L"916";
    v21 = 916;
    goto LABEL_25;
  }
  if ( !a6 )
  {
    v20 = L"917";
    v21 = 917;
    goto LABEL_25;
  }
  if ( !a8 )
  {
    v20 = L"918";
    v21 = 918;
    goto LABEL_25;
  }
  *a2 = 0;
  v11 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  while ( 1 )
  {
    v12 = (_QWORD *)((char *)a1 + 8);
    if ( v11 == *(_DWORD *)a1 )
      break;
    v13 = 104LL * v11;
    v14 = v13 + *v12;
    if ( v14 )
    {
      if ( *(_DWORD *)(v14 + 16) == 16 )
      {
        v15 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v14);
        if ( !_wcsnicmp(v15, L"UseSharedProcess", 0x10u) )
        {
          AttributeValue = (wchar_t *)FwXmlGetAttributeValue(v13 + *v12);
          if ( (unsigned int)StringCchEqualsCI(AttributeValue, (wchar_t *)L"true") )
            *a2 = 1;
          break;
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    }
    ++v11;
  }
  for ( i = 0; i != *(_DWORD *)a1; ++i )
  {
    v18 = 104LL * i;
    v19 = v18 + *v12;
    if ( v19 )
    {
      if ( *(_DWORD *)(v19 + 16) == 21 )
      {
        v23 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v19);
        if ( !_wcsnicmp(v23, L"ProcessIdleTimeoutSec", 0x15u) )
        {
          v24 = (const wchar_t *)FwXmlGetAttributeValue(v18 + *v12);
          *a4 = _wtoi(v24);
          break;
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    }
  }
  for ( j = 0; j != *(_DWORD *)a1; ++j )
  {
    v26 = 104LL * j;
    v27 = v26 + *v12;
    if ( v27 )
    {
      if ( *(_DWORD *)(v27 + 16) == 13 )
      {
        v28 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v27);
        if ( !_wcsnicmp(v28, L"RunAsPassword", 0xDu) )
        {
          *a6 = (const unsigned __int16 *)FwXmlGetAttributeValue(v26 + *v12);
          break;
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    }
  }
  for ( k = 0; k != *(_DWORD *)a1; ++k )
  {
    v30 = 104LL * k;
    v31 = v30 + *v12;
    if ( v31 )
    {
      if ( *(_DWORD *)(v31 + 16) == 9 )
      {
        v32 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v31);
        if ( !_wcsnicmp(v32, L"RunAsUser", 9u) )
        {
          *a5 = (const unsigned __int16 *)FwXmlGetAttributeValue(v30 + *v12);
          break;
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    }
  }
  for ( m = 0; m != *(_DWORD *)a1; ++m )
  {
    v34 = 104LL * m;
    v35 = v34 + *v12;
    if ( v35 )
    {
      if ( *(_DWORD *)(v35 + 16) == 11 )
      {
        v36 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v35);
        if ( !_wcsnicmp(v36, L"AutoRestart", 0xBu) )
        {
          v37 = (const wchar_t *)FwXmlGetAttributeValue(v34 + *v12);
          if ( !v37 )
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x8Bu, L"139", 0x54Fu, 0);
          if ( !_wcsicmp(v37, L"true") )
            *v47 = 1;
          break;
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    }
  }
  if ( a7 )
  {
    for ( n = 0; n != *(_DWORD *)a1; ++n )
    {
      v43 = 104LL * n;
      v44 = v43 + *v12;
      if ( v44 )
      {
        if ( *(_DWORD *)(v44 + 16) == 19 )
        {
          v45 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v44);
          if ( !_wcsnicmp(v45, L"RunAsVirtualAccount", 0x13u) )
          {
            v46 = (wchar_t *)FwXmlGetAttributeValue(v43 + *v12);
            if ( (unsigned int)StringCchEqualsCI(v46, (wchar_t *)L"true") )
              *a7 = 1;
            break;
          }
        }
      }
      else
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
      }
    }
  }
  for ( ii = 0; ii != *(_DWORD *)a1; ++ii )
  {
    v39 = 104LL * ii;
    v40 = v39 + *v12;
    if ( v40 )
    {
      if ( *(_DWORD *)(v40 + 16) == 25 )
      {
        v41 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v40);
        if ( !_wcsnicmp(v41, L"RunAsVirtualAccountGroups", 0x19u) )
        {
          *a8 = (const unsigned __int16 *)FwXmlGetAttributeValue(v39 + *v12);
          break;
        }
      }
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
  return 1;
}

```

## disassembly

```asm
0x180039d88  mov     [rsp+arg_0], rbp
0x180039d8d  mov     [rsp+arg_8], rsi
0x180039d92  mov     [rsp+arg_10], r8
0x180039d97  push    rdi
0x180039d98  push    r12
0x180039d9a  push    r13
0x180039d9c  push    r14
0x180039d9e  push    r15
0x180039da0  sub     rsp, 30h
0x180039da4  mov     r13, r9
0x180039da7  mov     r14, rdx
0x180039daa  mov     rbp, rcx
0x180039dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180039db4  lea     rax, WPP_GLOBAL_Control
0x180039dbb  cmp     rcx, rax
0x180039dbe  jnz     loc_180039ECC
0x180039dc4  test    rbp, rbp
0x180039dc7  jz      loc_180039EF8
0x180039dcd  test    r14, r14
0x180039dd0  jz      loc_18003A193
0x180039dd6  test    r8, r8
0x180039dd9  jz      loc_18003A1A4
0x180039ddf  test    r13, r13
0x180039de2  jz      loc_18003A1B5
0x180039de8  mov     rax, [rsp+58h+arg_20]
0x180039df0  test    rax, rax
0x180039df3  jz      loc_18003A1C6
0x180039df9  mov     r15, [rsp+58h+arg_28]
0x180039e01  test    r15, r15
0x180039e04  jz      loc_18003A1D7
0x180039e0a  cmp     [rsp+58h+arg_38], 0
0x180039e13  jz      loc_18003A1E8
0x180039e19  mov     byte ptr [r14], 0
0x180039e1d  xor     esi, esi
0x180039e1f  mov     byte ptr [r8], 0
0x180039e23  mov     dword ptr [r13+0], 0
0x180039e2b  mov     qword ptr [rax], 0
0x180039e32  mov     qword ptr [r15], 0
0x180039e39  lea     rdi, [rbp+8]
0x180039e3d  cmp     esi, [rbp+0]
0x180039e40  jz      short loc_180039EA0
0x180039e42  mov     rcx, [rdi]
0x180039e45  movsxd  rax, esi
0x180039e48  imul    r15, rax, 68h ; 'h'
0x180039e4c  add     rcx, r15
0x180039e4f  jz      loc_18003A1F9
0x180039e55  cmp     dword ptr [rcx+10h], 10h
0x180039e59  jz      short loc_180039E5F
0x180039e5b  inc     esi
0x180039e5d  jmp     short loc_180039E39
0x180039e5f  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180039e64  mov     rcx, rax; String1
0x180039e67  lea     rdx, aUsesharedproce; "UseSharedProcess"
0x180039e6e  mov     r8d, 10h; MaxCount
0x180039e74  call    cs:__imp__wcsnicmp
0x180039e7a  test    eax, eax
0x180039e7c  jnz     short loc_180039E5B
0x180039e7e  mov     rcx, [rdi]
0x180039e81  add     rcx, r15
0x180039e84  call    FwXmlGetAttributeValue
0x180039e89  lea     rdx, aTrue; "true"
0x180039e90  mov     rcx, rax; String1
0x180039e93  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x180039e98  test    eax, eax
0x180039e9a  jz      short loc_180039EA0
0x180039e9c  mov     byte ptr [r14], 1
0x180039ea0  xor     esi, esi
0x180039ea2  cmp     esi, [rbp+0]
0x180039ea5  jz      loc_180039FA8
0x180039eab  mov     rcx, [rdi]
0x180039eae  movsxd  rax, esi
0x180039eb1  imul    r14, rax, 68h ; 'h'
0x180039eb5  add     rcx, r14
0x180039eb8  jz      loc_18003A225
0x180039ebe  cmp     dword ptr [rcx+10h], 15h
0x180039ec2  jz      loc_180039F6D
0x180039ec8  inc     esi
0x180039eca  jmp     short loc_180039EA2
0x180039ecc  test    dword ptr [rcx+1Ch], 200000h
0x180039ed3  jz      loc_180039DC4
0x180039ed9  mov     rcx, [rcx+10h]
0x180039edd  lea     r8, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids
0x180039ee4  mov     edx, 3Bh ; ';'
0x180039ee9  call    WPP_SF_
0x180039eee  mov     r8, [rsp+58h+arg_10]
0x180039ef3  jmp     loc_180039DC4
0x180039ef8  lea     r8, a912; "912"
0x180039eff  mov     edx, 390h; unsigned int
0x180039f04  mov     r9d, 54Fh; unsigned int
0x180039f0a  mov     [rsp+58h+var_38], 0; struct IRequestContext *
0x180039f13  lea     rcx, aOnecoreAdminWm_160; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x180039f1a  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180039f1f  xor     eax, eax
0x180039f21  jmp     short loc_180039F55
0x180039f23  mov     rcx, [rdi]
0x180039f26  add     rcx, r14
0x180039f29  call    FwXmlGetAttributeValue
0x180039f2e  mov     rcx, [rsp+58h+arg_38]
0x180039f36  mov     [rcx], rax
0x180039f39  mov     rcx, cs:WPP_GLOBAL_Control
0x180039f40  lea     rax, WPP_GLOBAL_Control
0x180039f47  cmp     rcx, rax
0x180039f4a  jnz     loc_18003A366
0x180039f50  mov     eax, 1
0x180039f55  mov     rbp, [rsp+58h+arg_0]
0x180039f5a  mov     rsi, [rsp+58h+arg_8]
0x180039f5f  add     rsp, 30h
0x180039f63  pop     r15
0x180039f65  pop     r14
0x180039f67  pop     r13
0x180039f69  pop     r12
0x180039f6b  pop     rdi
0x180039f6c  retn
0x180039f6d  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180039f72  mov     rcx, rax; String1
0x180039f75  lea     rdx, aProcessidletim; "ProcessIdleTimeoutSec"
0x180039f7c  mov     r8d, 15h; MaxCount
0x180039f82  call    cs:__imp__wcsnicmp
0x180039f88  test    eax, eax
0x180039f8a  jnz     loc_180039EC8
0x180039f90  mov     rcx, [rdi]
0x180039f93  add     rcx, r14
0x180039f96  call    FwXmlGetAttributeValue
0x180039f9b  mov     rcx, rax; String
0x180039f9e  call    cs:__imp__wtoi
0x180039fa4  mov     [r13+0], eax
0x180039fa8  xor     esi, esi
0x180039faa  cmp     esi, [rbp+0]
0x180039fad  jz      short loc_18003A001
0x180039faf  mov     rcx, [rdi]
0x180039fb2  movsxd  rax, esi
0x180039fb5  imul    r14, rax, 68h ; 'h'
0x180039fb9  add     rcx, r14
0x180039fbc  jz      loc_18003A251
0x180039fc2  cmp     dword ptr [rcx+10h], 0Dh
0x180039fc6  jz      short loc_180039FCC
0x180039fc8  inc     esi
0x180039fca  jmp     short loc_180039FAA
0x180039fcc  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180039fd1  mov     rcx, rax; String1
0x180039fd4  lea     rdx, aRunaspassword; "RunAsPassword"
0x180039fdb  mov     r8d, 0Dh; MaxCount
0x180039fe1  call    cs:__imp__wcsnicmp
0x180039fe7  test    eax, eax
0x180039fe9  jnz     short loc_180039FC8
0x180039feb  mov     rcx, [rdi]
0x180039fee  add     rcx, r14
0x180039ff1  call    FwXmlGetAttributeValue
0x180039ff6  mov     rcx, [rsp+58h+arg_28]
0x180039ffe  mov     [rcx], rax
0x18003a001  xor     esi, esi
0x18003a003  cmp     esi, [rbp+0]
0x18003a006  jz      short loc_18003A05A
0x18003a008  mov     rcx, [rdi]
0x18003a00b  movsxd  rax, esi
0x18003a00e  imul    r14, rax, 68h ; 'h'
0x18003a012  add     rcx, r14
0x18003a015  jz      loc_18003A27D
0x18003a01b  cmp     dword ptr [rcx+10h], 9
0x18003a01f  jz      short loc_18003A025
0x18003a021  inc     esi
0x18003a023  jmp     short loc_18003A003
0x18003a025  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18003a02a  mov     rcx, rax; String1
0x18003a02d  lea     rdx, aRunasuser; "RunAsUser"
0x18003a034  mov     r8d, 9; MaxCount
0x18003a03a  call    cs:__imp__wcsnicmp
0x18003a040  test    eax, eax
0x18003a042  jnz     short loc_18003A021
0x18003a044  mov     rcx, [rdi]
0x18003a047  add     rcx, r14
0x18003a04a  call    FwXmlGetAttributeValue
0x18003a04f  mov     rcx, [rsp+58h+arg_20]
0x18003a057  mov     [rcx], rax
0x18003a05a  xor     esi, esi
0x18003a05c  cmp     esi, [rbp+0]
0x18003a05f  jz      short loc_18003A0CC
0x18003a061  mov     rcx, [rdi]
0x18003a064  movsxd  rax, esi
0x18003a067  imul    r14, rax, 68h ; 'h'
0x18003a06b  add     rcx, r14
0x18003a06e  jz      loc_18003A2A9
0x18003a074  cmp     dword ptr [rcx+10h], 0Bh
0x18003a078  jz      short loc_18003A07E
0x18003a07a  inc     esi
0x18003a07c  jmp     short loc_18003A05C
0x18003a07e  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18003a083  mov     rcx, rax; String1
0x18003a086  lea     rdx, aAutorestart; "AutoRestart"
0x18003a08d  mov     r8d, 0Bh; MaxCount
0x18003a093  call    cs:__imp__wcsnicmp
0x18003a099  test    eax, eax
0x18003a09b  jnz     short loc_18003A07A
0x18003a09d  mov     rcx, [rdi]
0x18003a0a0  add     rcx, r14
0x18003a0a3  call    FwXmlGetAttributeValue
0x18003a0a8  mov     rsi, rax
0x18003a0ab  test    rax, rax
0x18003a0ae  jz      loc_18003A2D5
0x18003a0b4  lea     rdx, aTrue; "true"
0x18003a0bb  mov     rcx, rsi; String1
0x18003a0be  call    cs:__imp__wcsicmp
0x18003a0c4  test    eax, eax
0x18003a0c6  jz      loc_18003A301
0x18003a0cc  mov     r14, [rsp+58h+arg_30]
0x18003a0d4  test    r14, r14
0x18003a0d7  jnz     short loc_18003A125
0x18003a0d9  xor     esi, esi
0x18003a0db  cmp     esi, [rbp+0]
0x18003a0de  jz      loc_180039F39
0x18003a0e4  mov     rcx, [rdi]
0x18003a0e7  movsxd  rax, esi
0x18003a0ea  imul    r14, rax, 68h ; 'h'
0x18003a0ee  add     rcx, r14
0x18003a0f1  jz      loc_18003A33A
0x18003a0f7  cmp     dword ptr [rcx+10h], 19h
0x18003a0fb  jz      short loc_18003A101
0x18003a0fd  inc     esi
0x18003a0ff  jmp     short loc_18003A0DB
0x18003a101  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18003a106  mov     rcx, rax; String1
0x18003a109  lea     rdx, aRunasvirtualac_0; "RunAsVirtualAccountGroups"
0x18003a110  mov     r8d, 19h; MaxCount
0x18003a116  call    cs:__imp__wcsnicmp
0x18003a11c  test    eax, eax
0x18003a11e  jnz     short loc_18003A0FD
0x18003a120  jmp     loc_180039F23
0x18003a125  xor     esi, esi
0x18003a127  cmp     esi, [rbp+0]
0x18003a12a  jz      short loc_18003A0D9
0x18003a12c  mov     rcx, [rdi]
0x18003a12f  movsxd  rax, esi
0x18003a132  imul    r15, rax, 68h ; 'h'
0x18003a136  add     rcx, r15
0x18003a139  jz      loc_18003A30E
0x18003a13f  cmp     dword ptr [rcx+10h], 13h
0x18003a143  jz      short loc_18003A149
0x18003a145  inc     esi
0x18003a147  jmp     short loc_18003A127
0x18003a149  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18003a14e  mov     rcx, rax; String1
0x18003a151  lea     rdx, aRunasvirtualac; "RunAsVirtualAccount"
0x18003a158  mov     r8d, 13h; MaxCount
0x18003a15e  call    cs:__imp__wcsnicmp
0x18003a164  test    eax, eax
0x18003a166  jnz     short loc_18003A145
0x18003a168  mov     rcx, [rdi]
0x18003a16b  add     rcx, r15
0x18003a16e  call    FwXmlGetAttributeValue
0x18003a173  lea     rdx, aTrue; "true"
0x18003a17a  mov     rcx, rax; String1
0x18003a17d  call    ?StringCchEqualsCI@@YAHPEBG0@Z; StringCchEqualsCI(ushort const *,ushort const *)
0x18003a182  test    eax, eax
0x18003a184  jz      loc_18003A0D9
0x18003a18a  mov     byte ptr [r14], 1
0x18003a18e  jmp     loc_18003A0D9
0x18003a193  lea     r8, a913; "913"
0x18003a19a  mov     edx, 391h
0x18003a19f  jmp     loc_180039F04
0x18003a1a4  lea     r8, a914; "914"
0x18003a1ab  mov     edx, 392h
0x18003a1b0  jmp     loc_180039F04
0x18003a1b5  lea     r8, a915; "915"
0x18003a1bc  mov     edx, 393h
0x18003a1c1  jmp     loc_180039F04
0x18003a1c6  lea     r8, a916; "916"
0x18003a1cd  mov     edx, 394h
0x18003a1d2  jmp     loc_180039F04
0x18003a1d7  lea     r8, a917; "917"
0x18003a1de  mov     edx, 395h
0x18003a1e3  jmp     loc_180039F04
0x18003a1e8  lea     r8, a918; "918"
0x18003a1ef  mov     edx, 396h
0x18003a1f4  jmp     loc_180039F04
0x18003a1f9  mov     r9d, 54Fh; unsigned int
0x18003a1ff  mov     [rsp+58h+var_38], 0; struct IRequestContext *
0x18003a208  lea     r8, a522; "522"
0x18003a20f  mov     edx, 20Ah; unsigned int
0x18003a214  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x18003a21b  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18003a220  jmp     loc_180039E5B
0x18003a225  mov     r9d, 54Fh; unsigned int
0x18003a22b  mov     [rsp+58h+var_38], 0; struct IRequestContext *
0x18003a234  lea     r8, a522; "522"
0x18003a23b  mov     edx, 20Ah; unsigned int
0x18003a240  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x18003a247  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18003a24c  jmp     loc_180039EC8
0x18003a251  mov     r9d, 54Fh; unsigned int
0x18003a257  mov     [rsp+58h+var_38], 0; struct IRequestContext *
0x18003a260  lea     r8, a522; "522"
0x18003a267  mov     edx, 20Ah; unsigned int
0x18003a26c  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x18003a273  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18003a278  jmp     loc_180039FC8
0x18003a27d  mov     r9d, 54Fh; unsigned int
0x18003a283  mov     [rsp+58h+var_38], 0; struct IRequestContext *
0x18003a28c  lea     r8, a522; "522"
0x18003a293  mov     edx, 20Ah; unsigned int
0x18003a298  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
  ... truncated ...
```
