# FwAdvPolicyLoadSet(_tag_FW_SET_MANIPULATOR *,HKEY__ *,ushort const *,_tag_FW_BLOB_RULE * *,ulong *,ulong,ushort const *)

- ea: `0x180016f9c`
- end: `0x180017773`
- name: `?FwAdvPolicyLoadSet@@YAJPEAU_tag_FW_SET_MANIPULATOR@@PEAUHKEY__@@PEBGPEAPEAU_tag_FW_BLOB_RULE@@PEAKK2@Z`
- size: `2007`
- prototype: `__int64 __fastcall(struct _tag_FW_SET_MANIPULATOR *, HKEY, const unsigned __int16 *, struct _tag_FW_BLOB_RULE **, unsigned int *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001629c`

## callees

- `0x1800041d0`
- `0x1800042c4`
- `0x18000f280`
- `0x180016e14`
- `0x180016f9c`
- `0x18001777c`
- `0x180018218`
- `0x18001a56c`
- `0x18001f650`
- `0x1800371bc`
- `0x18003b010`

## import_xrefs

- `fwbase!FwFree` at `0x18001721e`
- `fwbase!FwFree` at `0x1800172fc`
- `fwbase!FwFree` at `0x180017508`
- `fwbase!FwFree` at `0x18001751a`
- `fwbase!FwFree` at `0x18001771d`
- `fwbase!FwFree` at `0x18001772f`
- `fwbase!FwFree` at `0x180017739`
- `fwbase!FwFree` at `0x180017741`
- `fwbase!FwFree` at `0x18001721e`
- `fwbase!FwFree` at `0x1800172fc`
- `fwbase!FwFree` at `0x180017508`
- `fwbase!FwFree` at `0x18001751a`
- `fwbase!FwFree` at `0x18001771d`
- `fwbase!FwFree` at `0x18001772f`
- `fwbase!FwFree` at `0x180017739`
- `fwbase!FwFree` at `0x180017741`
- `fwbase!FwStringCopy` at `0x1800170dc`
- `fwbase!FwStringCopy` at `0x1800170dc`
- `fwbase!FwRegOpenKey` at `0x18001701e`
- `fwbase!FwRegOpenKey` at `0x18001701e`
- `fwbase!FwRegQueryString` at `0x18001719f`
- `fwbase!FwRegQueryString` at `0x180017274`
- `fwbase!FwRegQueryString` at `0x18001719f`
- `fwbase!FwRegQueryString` at `0x180017274`
- `fwbase!FwRegCloseKey` at `0x18001774b`
- `fwbase!FwRegCloseKey` at `0x18001774b`
- `fwbase!FwRegQueryNumValues` at `0x180017158`
- `fwbase!FwRegQueryNumValues` at `0x180017158`
- `fwbase!FwRegEnumValueNameAndValueData` at `0x180017491`
- `fwbase!FwRegEnumValueNameAndValueData` at `0x180017491`

## pseudocode

```c
__int64 __fastcall FwAdvPolicyLoadSet(
        struct _tag_FW_SET_MANIPULATOR *a1,
        HKEY a2,
        const unsigned __int16 *a3,
        struct _tag_FW_BLOB_RULE **a4,
        unsigned int *a5,
        unsigned int a6,
        const unsigned __int16 *a7)
{
  struct _tag_FW_SET_MANIPULATOR *v7; // r13
  int v9; // eax
  signed int v10; // esi
  struct _tag_FW_BLOB_RULE *v11; // r14
  LPCOLESTR v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rax
  __int64 (__fastcall **v16)(struct _tag_FW_BLOB_RULE *); // rdi
  _DWORD *v17; // rax
  const unsigned __int16 *v18; // rcx
  int v19; // eax
  LPCOLESTR v20; // rcx
  int v21; // ebx
  __int64 v22; // rdx
  __int64 v23; // rbx
  _QWORD *v24; // rax
  unsigned __int16 v25; // r13
  unsigned int v26; // r12d
  struct _tag_FW_SET_MANIPULATOR *v27; // rsi
  struct _tag_FW_RULE_PARSER *SmallestCompatibleParserForSchemaVersion; // rax
  struct _tag_FW_RULE_PARSER **v29; // r8
  unsigned int v30; // edx
  unsigned __int16 v31; // cx
  struct _tag_FW_RULE_PARSER *v32; // rax
  int v33; // r11d
  struct _tag_FW_SET_MANIPULATOR *v34; // rsi
  unsigned int v35; // r12d
  __int64 (__fastcall *v36)(struct _tag_FW_BLOB_RULE *); // rax
  __int64 v37; // r9
  int v38; // edx
  int v39; // r8d
  struct _tag_FW_SET_MANIPULATOR *v40; // r13
  int v41; // r12d
  struct _tag_FW_BLOB_RULE **v42; // rcx
  LPCWSTR v43; // rcx
  unsigned int v45; // [rsp+40h] [rbp-71h] BYREF
  unsigned int v46; // [rsp+44h] [rbp-6Dh] BYREF
  struct _tag_FW_SET_MANIPULATOR *v47; // [rsp+48h] [rbp-69h]
  struct _tag_FW_RULE_PARSER *v48[2]; // [rsp+50h] [rbp-61h] BYREF
  struct _tag_FW_BLOB_RULE **v49; // [rsp+60h] [rbp-51h]
  unsigned int *v50; // [rsp+68h] [rbp-49h]
  wchar_t *String; // [rsp+70h] [rbp-41h] BYREF
  LPCWSTR lpString2; // [rsp+78h] [rbp-39h] BYREF
  HKEY v53; // [rsp+80h] [rbp-31h] BYREF
  unsigned __int16 *v54; // [rsp+88h] [rbp-29h] BYREF
  __int64 v55; // [rsp+90h] [rbp-21h] BYREF
  unsigned int v56; // [rsp+98h] [rbp-19h] BYREF
  int v57; // [rsp+9Ch] [rbp-15h] BYREF

  v7 = a1;
  v47 = a1;
  v50 = a5;
  v49 = a4;
  v53 = 0;
  v57 = 0;
  v56 = 0;
  lpString2 = 0;
  String = 0;
  v54 = 0;
  v55 = 0;
  *(_OWORD *)v48 = 0;
  v9 = FwRegOpenKey(a2, a3, 9, &v53, &v57);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 0;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_95;
    v13 = 23;
    v14 = (unsigned int)v9;
    goto LABEL_9;
  }
  v15 = (*(__int64 (**)(void))v7)();
  v11 = (struct _tag_FW_BLOB_RULE *)v15;
  if ( !v15 )
  {
    v10 = -2147024882;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_95;
    v13 = 24;
    v14 = 2147942414LL;
LABEL_9:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids, v14);
LABEL_95:
    (*((void (__fastcall **)(struct _tag_FW_BLOB_RULE *))v7 + 9))(v11);
    FwFree(v11);
    v21 = 0;
    goto LABEL_96;
  }
  (*((void (__fastcall **)(__int64))v7 + 13))(v15);
  v16 = (__int64 (__fastcall **)(struct _tag_FW_BLOB_RULE *))((char *)v7 + 40);
  v17 = (_DWORD *)(*((__int64 (__fastcall **)(struct _tag_FW_BLOB_RULE *))v7 + 5))(v11);
  v18 = a3;
  if ( a7 )
    v18 = a7;
  *v17 = 3670016;
  v19 = FwStringCopy(v18, &v55);
  v10 = v19;
  if ( v19 >= 0 )
  {
    v23 = v55;
    v24 = (_QWORD *)(*((__int64 (__fastcall **)(struct _tag_FW_BLOB_RULE *))v7 + 6))(v11);
    v25 = 0;
    *v24 = v23;
    v21 = 1;
    v55 = 0;
    v56 = 0;
    if ( !v57 )
      goto LABEL_87;
    v45 = 0;
    v46 = 0;
    v19 = FwRegQueryNumValues(v53, &v56);
    v10 = v19;
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_88;
      v22 = 26;
      goto LABEL_70;
    }
    v19 = FwRegQueryString(v53, 0, L"SkipVersion", &String, &v57);
    v10 = v19;
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_88;
      v22 = 27;
      goto LABEL_70;
    }
    if ( v57 )
    {
      v54 = String;
      v19 = FwAdvPolicyDecodeVersion(String, &v45, &v46, (const unsigned __int16 **)&v54);
      v10 = v19;
      if ( v19 < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_88;
        v22 = 28;
        goto LABEL_70;
      }
      FwFree(String);
      String = 0;
      v54 = 0;
      if ( (unsigned __int16)((unsigned __int8)v46 | ((unsigned __int8)v45 << 8)) >= 0x221u )
      {
        *(_DWORD *)(*v16)(v11) = 0x40000;
        v56 = 0;
      }
    }
    v19 = FwRegQueryString(v53, 0, L"Version", &String, &v57);
    v10 = v19;
    if ( v19 < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_88;
      v22 = 29;
      goto LABEL_70;
    }
    if ( String && v57 )
    {
      v54 = String;
      v19 = FwAdvPolicyDecodeVersion(String, &v45, &v46, (const unsigned __int16 **)&v54);
      v10 = v19;
      if ( v19 < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_88;
        v22 = 30;
LABEL_70:
        v37 = (unsigned int)v19;
LABEL_71:
        WPP_SF_d(*((_QWORD *)v20 + 2), v22, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids, v37);
        goto LABEL_88;
      }
      FwFree(String);
      v26 = v45;
      String = 0;
      v54 = 0;
      v25 = (unsigned __int8)v46 | ((unsigned __int8)v45 << 8);
      *(_DWORD *)(*v16)(v11) = 0x10000;
      if ( v25 >= 0x300u )
      {
        *(_DWORD *)(*v16)(v11) = 0x40000;
        v56 = 0;
      }
      v27 = v47;
      SmallestCompatibleParserForSchemaVersion = FwFindSmallestCompatibleParserForSchemaVersion(
                                                   v25,
                                                   *((_DWORD *)v47 + 30),
                                                   *((struct _tag_FW_RULE_PARSER ***)v47 + 16));
      v29 = (struct _tag_FW_RULE_PARSER **)*((_QWORD *)v27 + 18);
      v30 = *((_DWORD *)v27 + 34);
      v48[0] = SmallestCompatibleParserForSchemaVersion;
      v32 = FwFindSmallestCompatibleParserForSchemaVersion(v31, v30, v29);
      v48[1] = v32;
      v10 = v26 < 2 ? 0x80070057 : 0;
      if ( v26 >= 2 && v48[0] && v32 )
        goto LABEL_54;
      *(_DWORD *)(*v16)(v11) = 3670016;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x10) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids, v26, v46);
    }
    else
    {
      *(_DWORD *)(*v16)(v11) = 3670016;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x10) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids, a3);
    }
    v33 = 0;
    v56 = 0;
LABEL_54:
    if ( v33 )
    {
      v34 = v47;
      v35 = 0;
      (*((void (__fastcall **)(struct _tag_FW_BLOB_RULE *))v47 + 8))(v11);
      *(_WORD *)(*((__int64 (__fastcall **)(struct _tag_FW_BLOB_RULE *))v34 + 7))(v11) = v25;
      while ( v35 < v56 )
      {
        v19 = FwRegEnumValueNameAndValueData(v53, v35, &lpString2, &String, &v57, 0, 0);
        v10 = v19;
        if ( v19 < 0 )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v22 = 33;
            goto LABEL_70;
          }
          goto LABEL_88;
        }
        if ( !v57 )
          break;
        v45 = 0;
        v10 = FwAdvPolicySetParseField(lpString2, String, v11, &v45, v48[0], v25);
        if ( v10 == -2147467263 )
        {
          v36 = *v16;
          if ( v25 <= 0x221u )
          {
            *(_DWORD *)v36(v11) = 3670016;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x10) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                34,
                WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids,
                lpString2);
              v20 = WPP_GLOBAL_Control;
            }
            v19 = -2147024809;
            v10 = -2147024809;
            if ( v20 != (LPCOLESTR)&WPP_GLOBAL_Control && (v20[14] & 1) != 0 )
            {
              v22 = 35;
              goto LABEL_70;
            }
            goto LABEL_88;
          }
          *(_DWORD *)v36(v11) = 0x20000;
        }
        else if ( v10 < 0 )
        {
          *(_DWORD *)(*v16)(v11) = 3670016;
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
          {
            if ( (WPP_GLOBAL_Control[14] & 0x10) != 0 )
            {
              WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), v38, v39, v10, (__int64)lpString2);
              v20 = WPP_GLOBAL_Control;
            }
            if ( v20 != (LPCOLESTR)&WPP_GLOBAL_Control && (v20[14] & 1) != 0 )
            {
              v22 = 37;
              v37 = (unsigned int)v10;
              goto LABEL_71;
            }
          }
          goto LABEL_88;
        }
        FwFree(lpString2);
        lpString2 = 0;
        FwFree(String);
        ++v35;
        String = 0;
      }
      v40 = v47;
      v19 = FwEnumAdvPolicySuites(v47, v53, v11, v48);
      v10 = v19;
      if ( v19 >= 0 )
      {
        v41 = *(_DWORD *)(*v16)(v11);
        v10 = (*((__int64 (__fastcall **)(struct _tag_FW_BLOB_RULE *))v40 + 12))(v11);
        if ( *(_DWORD *)(*v16)(v11) < v41 )
          *(_DWORD *)(*v16)(v11) = v41;
        goto LABEL_87;
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v22 = 38;
        goto LABEL_70;
      }
      goto LABEL_88;
    }
LABEL_87:
    if ( v10 >= 0 )
      goto LABEL_92;
    goto LABEL_88;
  }
  v20 = WPP_GLOBAL_Control;
  v21 = 1;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v22 = 25;
    goto LABEL_70;
  }
LABEL_88:
  if ( *(_DWORD *)(*v16)(v11) == 0x10000 )
  {
    *(_DWORD *)(*v16)(v11) = 3670016;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids,
        (unsigned int)v10);
  }
LABEL_92:
  if ( (a6 & *(_DWORD *)(*v16)(v11)) == 0 )
  {
    v7 = v47;
    goto LABEL_95;
  }
  v42 = v49;
  *(_QWORD *)v11 = *v49;
  *v42 = v11;
LABEL_96:
  v43 = lpString2;
  *v50 += v21;
  FwFree(v43);
  FwFree(String);
  FwFree(0);
  FwRegCloseKey(v53);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180016f9c  push    rbp
0x180016f9e  push    rbx
0x180016f9f  push    rsi
0x180016fa0  push    rdi
0x180016fa1  push    r12
0x180016fa3  push    r13
0x180016fa5  push    r14
0x180016fa7  push    r15
0x180016fa9  lea     rbp, [rsp-7]
0x180016fae  sub     rsp, 0B8h
0x180016fb5  mov     rax, cs:__security_cookie
0x180016fbc  xor     rax, rsp
0x180016fbf  mov     [rbp+3Fh+var_50], rax
0x180016fc3  mov     rbx, [rbp+3Fh+arg_30]
0x180016fc7  xor     r15d, r15d
0x180016fca  mov     r13, rcx
0x180016fcd  mov     [rbp+3Fh+var_A8], rcx
0x180016fd1  mov     rcx, [rbp+3Fh+arg_20]
0x180016fd5  mov     r12, r8
0x180016fd8  mov     [rbp+3Fh+var_88], rcx
0x180016fdc  mov     rax, rdx
0x180016fdf  lea     rcx, [rbp+3Fh+var_54]
0x180016fe3  mov     [rbp+3Fh+var_90], r9
0x180016fe7  mov     [rsp+0F0h+var_D0], rcx
0x180016fec  lea     r9, [rbp+3Fh+var_70]
0x180016ff0  xorps   xmm0, xmm0
0x180016ff3  mov     [rbp+3Fh+var_70], r15
0x180016ff7  mov     rcx, rax
0x180016ffa  mov     [rbp+3Fh+var_54], r15d
0x180016ffe  lea     r8d, [r15+9]
0x180017002  mov     [rbp+3Fh+var_58], r15d
0x180017006  mov     rdx, r12
0x180017009  mov     [rbp+3Fh+lpString2], r15
0x18001700d  mov     [rbp+3Fh+String], r15
0x180017011  mov     [rbp+3Fh+var_68], r15
0x180017015  mov     [rbp+3Fh+var_60], r15
0x180017019  movdqu  xmmword ptr [rbp+3Fh+var_A0], xmm0
0x18001701e  call    cs:__imp_FwRegOpenKey
0x180017024  mov     esi, eax
0x180017026  test    eax, eax
0x180017028  jns     short loc_180017059
0x18001702a  mov     r14d, r15d
0x18001702d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017034  lea     r15, WPP_GLOBAL_Control
0x18001703b  cmp     rcx, r15
0x18001703e  jz      loc_18001770E
0x180017044  lea     ebx, [r14+1]
0x180017048  test    [rcx+1Ch], bl
0x18001704b  jz      loc_18001770E
0x180017051  lea     edx, [rbx+16h]
0x180017054  mov     r9d, eax
0x180017057  jmp     short loc_180017098
0x180017059  mov     rax, [r13+0]
0x18001705d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017062  mov     r14, rax
0x180017065  test    rax, rax
0x180017068  jnz     short loc_1800170AD
0x18001706a  mov     esi, 8007000Eh
0x18001706f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017076  lea     r15, WPP_GLOBAL_Control
0x18001707d  cmp     rcx, r15
0x180017080  jz      loc_18001770E
0x180017086  lea     ebx, [rax+1]
0x180017089  test    [rcx+1Ch], bl
0x18001708c  jz      loc_18001770E
0x180017092  lea     edx, [rax+18h]
0x180017095  mov     r9d, esi
0x180017098  mov     rcx, [rcx+10h]
0x18001709c  lea     r8, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids
0x1800170a3  call    WPP_SF_d
0x1800170a8  jmp     loc_18001770E
0x1800170ad  mov     rax, [r13+68h]
0x1800170b1  mov     rcx, r14
0x1800170b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170b9  lea     rdi, [r13+28h]
0x1800170bd  mov     rcx, r14
0x1800170c0  mov     rax, [rdi]
0x1800170c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170c8  test    rbx, rbx
0x1800170cb  lea     rdx, [rbp+3Fh+var_60]
0x1800170cf  mov     rcx, r12
0x1800170d2  cmovnz  rcx, rbx
0x1800170d6  mov     dword ptr [rax], 380000h
0x1800170dc  call    cs:__imp_FwStringCopy
0x1800170e2  mov     esi, eax
0x1800170e4  test    eax, eax
0x1800170e6  jns     short loc_180017115
0x1800170e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170ef  lea     r15, WPP_GLOBAL_Control
0x1800170f6  mov     ebx, 1
0x1800170fb  cmp     rcx, r15
0x1800170fe  jz      loc_18001769B
0x180017104  test    [rcx+1Ch], bl
0x180017107  jz      loc_18001769B
0x18001710d  lea     edx, [rbx+18h]
0x180017110  jmp     loc_18001758B
0x180017115  mov     rax, [r13+30h]
0x180017119  mov     rcx, r14
0x18001711c  mov     rbx, [rbp+3Fh+var_60]
0x180017120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017125  xor     r13d, r13d
0x180017128  lea     r15, WPP_GLOBAL_Control
0x18001712f  mov     [rax], rbx
0x180017132  lea     ebx, [r13+1]
0x180017136  mov     [rbp+3Fh+var_60], r13
0x18001713a  mov     [rbp+3Fh+var_58], r13d
0x18001713e  cmp     [rbp+3Fh+var_54], r13d
0x180017142  jz      loc_180017697
0x180017148  mov     rcx, [rbp+3Fh+var_70]
0x18001714c  lea     rdx, [rbp+3Fh+var_58]
0x180017150  mov     [rbp+3Fh+var_B0], r13d
0x180017154  mov     [rbp+3Fh+var_AC], r13d
0x180017158  call    cs:__imp_FwRegQueryNumValues
0x18001715e  mov     esi, eax
0x180017160  test    eax, eax
0x180017162  jns     short loc_180017185
0x180017164  mov     rcx, cs:WPP_GLOBAL_Control
0x18001716b  cmp     rcx, r15
0x18001716e  jz      loc_18001769B
0x180017174  test    [rcx+1Ch], bl
0x180017177  jz      loc_18001769B
0x18001717d  lea     edx, [rbx+19h]
0x180017180  jmp     loc_18001758B
0x180017185  mov     rcx, [rbp+3Fh+var_70]
0x180017189  lea     rax, [rbp+3Fh+var_54]
0x18001718d  lea     r9, [rbp+3Fh+String]
0x180017191  mov     [rsp+0F0h+var_D0], rax
0x180017196  lea     r8, aSkipversion; "SkipVersion"
0x18001719d  xor     edx, edx
0x18001719f  call    cs:__imp_FwRegQueryString
0x1800171a5  mov     esi, eax
0x1800171a7  test    eax, eax
0x1800171a9  jns     short loc_1800171CE
0x1800171ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171b2  cmp     rcx, r15
0x1800171b5  jz      loc_18001769B
0x1800171bb  test    [rcx+1Ch], bl
0x1800171be  jz      loc_18001769B
0x1800171c4  mov     edx, 1Bh
0x1800171c9  jmp     loc_18001758B
0x1800171ce  cmp     [rbp+3Fh+var_54], r13d
0x1800171d2  jz      loc_18001725A
0x1800171d8  mov     rcx, [rbp+3Fh+String]; String
0x1800171dc  lea     r9, [rbp+3Fh+var_68]; unsigned __int16 **
0x1800171e0  lea     r8, [rbp+3Fh+var_AC]; unsigned int *
0x1800171e4  mov     [rbp+3Fh+var_68], rcx
0x1800171e8  lea     rdx, [rbp+3Fh+var_B0]; unsigned int *
0x1800171ec  call    ?FwAdvPolicyDecodeVersion@@YAJPEBGPEAK1PEAPEBG@Z; FwAdvPolicyDecodeVersion(ushort const *,ulong *,ulong *,ushort const * *)
0x1800171f1  mov     esi, eax
0x1800171f3  test    eax, eax
0x1800171f5  jns     short loc_18001721A
0x1800171f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171fe  cmp     rcx, r15
0x180017201  jz      loc_18001769B
0x180017207  test    [rcx+1Ch], bl
0x18001720a  jz      loc_18001769B
0x180017210  mov     edx, 1Ch
0x180017215  jmp     loc_18001758B
0x18001721a  mov     rcx, [rbp+3Fh+String]
0x18001721e  call    cs:__imp_FwFree
0x180017224  movzx   eax, byte ptr [rbp+3Fh+var_AC]
0x180017228  movzx   ecx, byte ptr [rbp+3Fh+var_B0]
0x18001722c  shl     cx, 8
0x180017230  or      cx, ax
0x180017233  mov     [rbp+3Fh+String], r13
0x180017237  mov     eax, 221h
0x18001723c  mov     [rbp+3Fh+var_68], r13
0x180017240  cmp     ax, cx
0x180017243  ja      short loc_18001725A
0x180017245  mov     rax, [rdi]
0x180017248  mov     rcx, r14
0x18001724b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017250  mov     dword ptr [rax], 40000h
0x180017256  mov     [rbp+3Fh+var_58], r13d
0x18001725a  mov     rcx, [rbp+3Fh+var_70]
0x18001725e  lea     rax, [rbp+3Fh+var_54]
0x180017262  lea     r9, [rbp+3Fh+String]
0x180017266  mov     [rsp+0F0h+var_D0], rax
0x18001726b  lea     r8, aVersion; "Version"
0x180017272  xor     edx, edx
0x180017274  call    cs:__imp_FwRegQueryString
0x18001727a  mov     esi, eax
0x18001727c  test    eax, eax
0x18001727e  jns     short loc_1800172A3
0x180017280  mov     rcx, cs:WPP_GLOBAL_Control
0x180017287  cmp     rcx, r15
0x18001728a  jz      loc_18001769B
0x180017290  test    [rcx+1Ch], bl
0x180017293  jz      loc_18001769B
0x180017299  mov     edx, 1Dh
0x18001729e  jmp     loc_18001758B
0x1800172a3  mov     rcx, [rbp+3Fh+String]; String
0x1800172a7  test    rcx, rcx
0x1800172aa  jz      loc_1800173F0
0x1800172b0  cmp     [rbp+3Fh+var_54], r13d
0x1800172b4  jz      loc_1800173F0
0x1800172ba  lea     r9, [rbp+3Fh+var_68]; unsigned __int16 **
0x1800172be  mov     [rbp+3Fh+var_68], rcx
0x1800172c2  lea     r8, [rbp+3Fh+var_AC]; unsigned int *
0x1800172c6  lea     rdx, [rbp+3Fh+var_B0]; unsigned int *
0x1800172ca  call    ?FwAdvPolicyDecodeVersion@@YAJPEBGPEAK1PEAPEBG@Z; FwAdvPolicyDecodeVersion(ushort const *,ulong *,ulong *,ushort const * *)
0x1800172cf  mov     esi, eax
0x1800172d1  test    eax, eax
0x1800172d3  jns     short loc_1800172F8
0x1800172d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800172dc  cmp     rcx, r15
0x1800172df  jz      loc_18001769B
0x1800172e5  test    [rcx+1Ch], bl
0x1800172e8  jz      loc_18001769B
0x1800172ee  mov     edx, 1Eh
0x1800172f3  jmp     loc_18001758B
0x1800172f8  mov     rcx, [rbp+3Fh+String]
0x1800172fc  call    cs:__imp_FwFree
0x180017302  movzx   eax, byte ptr [rbp+3Fh+var_AC]
0x180017306  mov     rcx, r14
0x180017309  mov     r12d, [rbp+3Fh+var_B0]
0x18001730d  mov     [rbp+3Fh+String], r13
0x180017311  mov     [rbp+3Fh+var_68], r13
0x180017315  movzx   r13d, r12b
0x180017319  shl     r13w, 8
0x18001731e  or      r13w, ax
0x180017322  mov     rax, [rdi]
0x180017325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001732a  mov     dword ptr [rax], 10000h
0x180017330  mov     eax, 300h
0x180017335  cmp     r13w, ax
0x180017339  jb      short loc_180017355
0x18001733b  mov     rax, [rdi]
0x18001733e  mov     rcx, r14
0x180017341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017346  xor     r11d, r11d
0x180017349  mov     dword ptr [rax], 40000h
0x18001734f  mov     [rbp+3Fh+var_58], r11d
0x180017353  jmp     short loc_180017359
0x180017355  mov     r11d, [rbp+3Fh+var_58]
0x180017359  mov     rsi, [rbp+3Fh+var_A8]
0x18001735d  movzx   ecx, r13w; unsigned __int16
0x180017361  mov     r8, [rsi+80h]; struct _tag_FW_RULE_PARSER **
0x180017368  mov     edx, [rsi+78h]; unsigned int
0x18001736b  call    ?FwFindSmallestCompatibleParserForSchemaVersion@@YAPEAU_tag_FW_RULE_PARSER@@GKPEAPEAU1@@Z; FwFindSmallestCompatibleParserForSchemaVersion(ushort,ulong,_tag_FW_RULE_PARSER * *)
0x180017370  mov     r8, [rsi+90h]; struct _tag_FW_RULE_PARSER **
0x180017377  mov     edx, [rsi+88h]; unsigned int
0x18001737d  mov     [rbp+3Fh+var_A0], rax
0x180017381  call    ?FwFindSmallestCompatibleParserForSchemaVersion@@YAPEAU_tag_FW_RULE_PARSER@@GKPEAPEAU1@@Z; FwFindSmallestCompatibleParserForSchemaVersion(ushort,ulong,_tag_FW_RULE_PARSER * *)
0x180017386  cmp     r12d, 2
0x18001738a  mov     [rbp+3Fh+var_A0+8], rax
0x18001738e  sbb     esi, esi
0x180017390  and     esi, 80070057h
0x180017396  cmp     r12d, 2
0x18001739a  jb      short loc_1800173AC
0x18001739c  cmp     [rbp+3Fh+var_A0], 0
0x1800173a1  jz      short loc_1800173AC
0x1800173a3  test    rax, rax
0x1800173a6  jnz     loc_180017432
0x1800173ac  mov     rax, [rdi]
0x1800173af  mov     rcx, r14
0x1800173b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173b7  mov     dword ptr [rax], 380000h
0x1800173bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173c4  cmp     rcx, r15
0x1800173c7  jz      short loc_18001742B
0x1800173c9  test    byte ptr [rcx+1Ch], 10h
0x1800173cd  jz      short loc_18001742B
0x1800173cf  mov     eax, [rbp+3Fh+var_AC]
0x1800173d2  lea     r8, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids
0x1800173d9  mov     rcx, [rcx+10h]
0x1800173dd  mov     edx, 1Fh
0x1800173e2  mov     r9d, r12d
0x1800173e5  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1800173e9  call    WPP_SF_dd
0x1800173ee  jmp     short loc_18001742B
0x1800173f0  mov     rax, [rdi]
0x1800173f3  mov     rcx, r14
0x1800173f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173fb  mov     dword ptr [rax], 380000h
0x180017401  mov     rcx, cs:WPP_GLOBAL_Control
0x180017408  cmp     rcx, r15
0x18001740b  jz      short loc_18001742B
0x18001740d  test    byte ptr [rcx+1Ch], 10h
0x180017411  jz      short loc_18001742B
0x180017413  mov     rcx, [rcx+10h]
0x180017417  lea     r8, WPP_2a379e3342163711788e2aec1e7ce8d2_Traceguids
0x18001741e  mov     edx, 20h ; ' '
0x180017423  mov     r9, r12
0x180017426  call    WPP_SF_S
0x18001742b  xor     r11d, r11d
0x18001742e  mov     [rbp+3Fh+var_58], r11d
0x180017432  test    r11d, r11d
0x180017435  jz      loc_180017697
0x18001743b  mov     rsi, [rbp+3Fh+var_A8]
0x18001743f  mov     rcx, r14
0x180017442  xor     r12d, r12d
0x180017445  mov     rax, [rsi+40h]
0x180017449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001744e  mov     rax, [rsi+38h]
0x180017452  mov     rcx, r14
0x180017455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001745a  mov     [rax], r13w
0x18001745e  cmp     r12d, [rbp+3Fh+var_58]
0x180017462  jnb     loc_180017625
  ... truncated ...
```
