# FwEnumGlobalOpenPorts(HKEY__ *,ushort const *,ulong *,_tag_FW_RULE * *,ulong,int,ulong)

- ea: `0x180032050`
- end: `0x180032710`
- name: `?FwEnumGlobalOpenPorts@@YAJPEAUHKEY__@@PEBGPEAKPEAPEAU_tag_FW_RULE@@KHK@Z`
- size: `1728`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned int *, struct _tag_FW_RULE **, unsigned int, int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ba5c`

## callees

- `0x1800042c4`
- `0x180006f50`
- `0x18000cff0`
- `0x18001e9ac`
- `0x18001f650`
- `0x18001ffd4`
- `0x1800230c0`
- `0x180031008`
- `0x180032050`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800323bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800323bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326bb`
- `fwbase!FwAlloc` at `0x180032201`
- `fwbase!FwAlloc` at `0x180032275`
- `fwbase!FwAlloc` at `0x180032201`
- `fwbase!FwAlloc` at `0x180032275`
- `fwbase!FwArrayCopy` at `0x18003233a`
- `fwbase!FwArrayCopy` at `0x18003233a`
- `fwbase!FwStringCopy` at `0x1800322bd`
- `fwbase!FwStringCopy` at `0x1800323a9`
- `fwbase!FwStringCopy` at `0x18003247e`
- `fwbase!FwStringCopy` at `0x1800324aa`
- `fwbase!FwStringCopy` at `0x1800322bd`
- `fwbase!FwStringCopy` at `0x1800323a9`
- `fwbase!FwStringCopy` at `0x18003247e`
- `fwbase!FwStringCopy` at `0x1800324aa`
- `fwbase!FwStringBuild` at `0x18003243a`
- `fwbase!FwStringBuild` at `0x18003243a`
- `fwbase!FwArrayDestroy` at `0x1800326de`
- `fwbase!FwArrayDestroy` at `0x1800326de`
- `fwbase!FwRegOpenKey` at `0x1800320f4`
- `fwbase!FwRegOpenKey` at `0x1800320f4`
- `fwbase!FwRegCloseKey` at `0x1800326e8`
- `fwbase!FwRegCloseKey` at `0x1800326e8`
- `fwbase!FwArrayCreateFromRegistry` at `0x18003216b`
- `fwbase!FwArrayCreateFromRegistry` at `0x18003216b`

## string_xrefs

- `0x180032467`: `@FirewallAPI.dll,-28752`
- `0x18003249c`: `@FirewallAPI.dll,-28502`
- `0x180032477`: `@FirewallAPI.dll,-23006`
- `0x180032493`: `@FirewallAPI.dll,-23006`

## pseudocode

```c
__int64 __fastcall FwEnumGlobalOpenPorts(
        HKEY a1,
        const unsigned __int16 *a2,
        unsigned int *a3,
        struct _tag_FW_RULE **a4,
        unsigned int a5,
        int a6,
        unsigned int a7)
{
  __int64 v7; // r15
  _DWORD *v10; // rdi
  unsigned int v11; // r13d
  const wchar_t *v12; // rax
  int v13; // eax
  int v14; // ebx
  LPCOLESTR v15; // rcx
  __int64 v16; // rdx
  unsigned int v18; // edx
  unsigned int v19; // ecx
  __int64 v20; // r14
  unsigned int v21; // eax
  unsigned int v22; // r12d
  _DWORD *v23; // rax
  __int64 v24; // rax
  int v25; // eax
  int v26; // r8d
  int v27; // eax
  unsigned int v28; // ecx
  int v29; // eax
  int v30; // eax
  unsigned int v31; // edx
  int v32; // eax
  int v33; // edx
  __int64 v34; // rcx
  int v35; // edx
  int v36; // edx
  const wchar_t *v37; // rcx
  char *v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // r9
  __int64 v41; // [rsp+30h] [rbp-81h]
  int v42; // [rsp+40h] [rbp-71h]
  unsigned int v43; // [rsp+44h] [rbp-6Dh]
  unsigned int v44; // [rsp+48h] [rbp-69h]
  const wchar_t *v45; // [rsp+50h] [rbp-61h]
  __int128 v48; // [rsp+68h] [rbp-49h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-39h] BYREF
  __int64 v50; // [rsp+80h] [rbp-31h] BYREF
  int v51; // [rsp+88h] [rbp-29h] BYREF
  wchar_t pszDest[8]; // [rsp+90h] [rbp-21h] BYREF
  int v53; // [rsp+A0h] [rbp-11h]

  v7 = 0;
  v50 = 0;
  v51 = 0;
  v53 = 0;
  hMem = 0;
  v10 = 0;
  v48 = 0;
  *(_OWORD *)pszDest = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v11 = a7;
  v12 = L"-Domain";
  if ( a7 != 1 )
    v12 = L"-Standard";
  v45 = v12;
  v48 = 0;
  v13 = FwRegOpenKey(a1, a2, 1, &v50, &v51);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
      goto LABEL_93;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_87;
    v16 = 14;
    goto LABEL_15;
  }
  if ( !v51 )
    return 0;
  v13 = FwArrayCreateFromRegistry(v50, L"List", 88, FwInitWFICFPortInfoFromReg, FwInitWFICFPortInfoDestroy, &a6, &v48);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
      goto LABEL_93;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_87;
    v16 = 15;
LABEL_15:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_10622196d762368449fa8f46c322a63a_Traceguids, (unsigned int)v13);
    v15 = WPP_GLOBAL_Control;
    goto LABEL_87;
  }
  v18 = 0;
  v42 = 0;
  v19 = 0;
LABEL_17:
  v43 = v19;
  if ( v19 >= (unsigned int)v48 )
  {
    *a3 = v18;
    if ( v14 < 0 )
    {
      v10 = 0;
LABEL_85:
      v15 = WPP_GLOBAL_Control;
      goto LABEL_86;
    }
    goto LABEL_96;
  }
  v20 = 88LL * v19;
  v21 = *(_DWORD *)(*((_QWORD *)&v48 + 1) + v20 + 40);
  if ( !v21 )
    v21 = 1;
  v22 = 0;
  v44 = v21;
  while ( 1 )
  {
    if ( v22 >= v21 )
    {
      v19 = v43 + 1;
      goto LABEL_17;
    }
    v23 = (_DWORD *)FwAlloc(504);
    v10 = v23;
    if ( !v23 )
    {
      v40 = 2147942414LL;
      v14 = -2147024882;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v39 = 16;
        goto LABEL_82;
      }
      goto LABEL_86;
    }
    memset_0(v23, 0, 0x1F8u);
    v10[10] = v11;
    *((_WORD *)v10 + 146) |= 1u;
    v10[11] = 1;
    *((_WORD *)v10 + 4) = 256;
    if ( *(_DWORD *)(v20 + *((_QWORD *)&v48 + 1) + 12) == 6 )
    {
      *((_WORD *)v10 + 24) = 6;
    }
    else if ( *(_DWORD *)(v20 + *((_QWORD *)&v48 + 1) + 12) == 17 )
    {
      *((_WORD *)v10 + 24) = 17;
    }
    if ( *((_WORD *)v10 + 24) == 6 || *((_WORD *)v10 + 24) == 17 )
      break;
LABEL_31:
    v7 = *(_QWORD *)(v20 + *((_QWORD *)&v48 + 1));
    if ( !v7 )
      v7 = *(_QWORD *)(v20 + *((_QWORD *)&v48 + 1) + 72);
    v25 = FwStringCopy(v7, v10 + 6);
    v14 = v25;
    if ( v25 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v39 = 18;
LABEL_75:
        v40 = (unsigned int)v25;
LABEL_82:
        WPP_SF_d(*((_QWORD *)v15 + 2), v39, WPP_10622196d762368449fa8f46c322a63a_Traceguids, v40);
        goto LABEL_85;
      }
      goto LABEL_86;
    }
    v26 = *(_DWORD *)(v20 + *((_QWORD *)&v48 + 1) + 16);
    v27 = v10[44];
    v28 = v27 & 0xFFFFFFFE;
    v29 = v27 | 1;
    if ( v26 )
      v28 = v29;
    v30 = v10[45];
    v31 = v30 & 0xFFFFFFFE;
    v10[44] = v28;
    v32 = v30 | 1;
    if ( v26 )
      v31 = v32;
    v10[45] = v31;
    v25 = FwArrayCopy(
            8,
            FwCopyIPv4SubNet,
            wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
            v20 + *((_QWORD *)&v48 + 1) + 24LL,
            v10 + 46);
    v14 = v25;
    if ( v25 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v39 = 19;
        goto LABEL_75;
      }
      goto LABEL_86;
    }
    v33 = *(_DWORD *)(v20 + *((_QWORD *)&v48 + 1) + 56);
    v10[72] = (v33 != 0) + 2;
    v34 = *((_QWORD *)&v48 + 1);
    if ( *(_DWORD *)(v20 + *((_QWORD *)&v48 + 1) + 40) && v33 )
    {
      v25 = FwMigrateLegacyAuthenticatedBypassSddl(
              *(_QWORD *)(*(_QWORD *)(v20 + *((_QWORD *)&v48 + 1) + 48) + 16LL * v22),
              &hMem);
      v14 = v25;
      if ( v25 < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v39 = 20;
          goto LABEL_75;
        }
        goto LABEL_86;
      }
      v25 = FwStringCopy(hMem, v10 + 74);
      v14 = v25;
      if ( v25 < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v39 = 21;
          goto LABEL_75;
        }
        goto LABEL_86;
      }
      LocalFree(hMem);
      hMem = 0;
      *((_WORD *)v10 + 146) |= 2u;
      LODWORD(v41) = v22;
      v25 = StringCchPrintfExW(pszDest, 0xAu, 0, 0, 0x800u, L"-%d", v41);
      v14 = v25;
      if ( v25 < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v39 = 22;
          goto LABEL_75;
        }
        goto LABEL_86;
      }
      v34 = *((_QWORD *)&v48 + 1);
    }
    v10[84] = *(_DWORD *)(v20 + v34 + 80);
    v25 = FwStringBuild(v10 + 4, *(_QWORD *)(v20 + *((_QWORD *)&v48 + 1) + 72), v45, pszDest);
    v14 = v25;
    if ( v25 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v39 = 23;
        goto LABEL_75;
      }
      goto LABEL_86;
    }
    if ( a6 )
    {
      v35 = *(_DWORD *)(v20 + *((_QWORD *)&v48 + 1) + 60);
      if ( v35 )
      {
        v36 = v35 - 1;
        if ( v36 )
        {
          if ( v36 != 1 )
            goto LABEL_55;
          v37 = L"@FirewallAPI.dll,-28752";
LABEL_53:
          v38 = (char *)(v10 + 78);
        }
        else
        {
          FwStringCopy(L"@FirewallAPI.dll,-23006", v10 + 78);
          v38 = (char *)(v10 + 6);
          *(_QWORD *)(v20 + *((_QWORD *)&v48 + 1)) = *((_QWORD *)v10 + 3);
          v37 = L"@FirewallAPI.dll,-23006";
        }
        FwStringCopy(v37, v38);
        goto LABEL_55;
      }
      v37 = L"@FirewallAPI.dll,-28502";
      goto LABEL_53;
    }
LABEL_55:
    v18 = ++v42;
    ++v22;
    *(_QWORD *)v10 = *a4;
    v21 = v44;
    *a4 = (struct _tag_FW_RULE *)v10;
    v11 = a7;
  }
  v10[16] = 1;
  v24 = FwAlloc(4);
  *((_QWORD *)v10 + 9) = v24;
  if ( v24 )
  {
    *(_WORD *)(v24 + 2) = *(_WORD *)(v20 + *((_QWORD *)&v48 + 1) + 8);
    **((_WORD **)v10 + 9) = *(_WORD *)(*((_QWORD *)v10 + 9) + 2LL);
    goto LABEL_31;
  }
  v40 = 2147942414LL;
  v14 = -2147024882;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v39 = 17;
    goto LABEL_82;
  }
LABEL_86:
  if ( v7 )
  {
    if ( v15 != (LPCOLESTR)&WPP_GLOBAL_Control && (v15[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v15 + 2), 25, WPP_10622196d762368449fa8f46c322a63a_Traceguids, (unsigned int)v14);
  }
  else
  {
LABEL_87:
    if ( v15 != (LPCOLESTR)&WPP_GLOBAL_Control && (v15[14] & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)v15 + 2), 24, (unsigned int)WPP_10622196d762368449fa8f46c322a63a_Traceguids, 0, v14);
  }
LABEL_93:
  FwFreeWFRule(v10);
  if ( hMem )
    LocalFree(hMem);
  hMem = 0;
LABEL_96:
  FwArrayDestroy(88, FwInitWFICFPortInfoDestroy, &v48);
  FwRegCloseKey(v50);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180032050  push    rbp
0x180032052  push    rbx
0x180032053  push    rsi
0x180032054  push    rdi
0x180032055  push    r12
0x180032057  push    r13
0x180032059  push    r14
0x18003205b  push    r15
0x18003205d  lea     rbp, [rsp-7]
0x180032062  sub     rsp, 0B8h
0x180032069  mov     rax, cs:__security_cookie
0x180032070  xor     rax, rsp
0x180032073  mov     [rbp+3Fh+var_48], rax
0x180032077  xor     r15d, r15d
0x18003207a  mov     [rbp+3Fh+var_98], r9
0x18003207e  xor     eax, eax
0x180032080  mov     [rbp+3Fh+var_90], r8
0x180032084  mov     [rbp+3Fh+var_70], r15
0x180032088  xorps   xmm0, xmm0
0x18003208b  mov     [rbp+3Fh+var_68], r15d
0x18003208f  xorps   xmm1, xmm1
0x180032092  mov     [rbp+3Fh+var_50], eax
0x180032095  mov     rsi, rdx
0x180032098  mov     [rbp+3Fh+hMem], r15
0x18003209c  mov     rbx, rcx
0x18003209f  mov     edi, r15d
0x1800320a2  movups  [rbp+3Fh+var_88], xmm0
0x1800320a6  movups  xmmword ptr [rbp+3Fh+pszDest], xmm1
0x1800320aa  test    rcx, rcx
0x1800320ad  jnz     short loc_1800320B4
0x1800320af  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800320b4  mov     r13d, [rbp+3Fh+arg_30]
0x1800320b8  lea     rcx, aStandard; "-Standard"
0x1800320bf  mov     r12d, 1
0x1800320c5  lea     rax, aDomain_0; "-Domain"
0x1800320cc  xorps   xmm0, xmm0
0x1800320cf  lea     r9, [rbp+3Fh+var_70]
0x1800320d3  cmp     r13d, r12d
0x1800320d6  mov     r8d, r12d
0x1800320d9  mov     rdx, rsi
0x1800320dc  cmovnz  rax, rcx
0x1800320e0  mov     rcx, rbx
0x1800320e3  mov     [rbp+3Fh+var_A0], rax
0x1800320e7  lea     rax, [rbp+3Fh+var_68]
0x1800320eb  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800320f0  movups  [rbp+3Fh+var_88], xmm0
0x1800320f4  call    cs:__imp_FwRegOpenKey
0x1800320fa  lea     r14, ?FwInitWFICFPortInfoDestroy@@YAXPEAU_tag_WF_ICF_PORT_INFO@@@Z; FwInitWFICFPortInfoDestroy(_tag_WF_ICF_PORT_INFO *)
0x180032101  mov     ebx, eax
0x180032103  test    eax, eax
0x180032105  jns     short loc_18003212F
0x180032107  mov     rcx, cs:WPP_GLOBAL_Control
0x18003210e  lea     rsi, WPP_GLOBAL_Control
0x180032115  cmp     rcx, rsi
0x180032118  jz      loc_1800326AA
0x18003211e  test    [rcx+1Ch], r12b
0x180032122  jz      loc_180032657
0x180032128  lea     edx, [r12+0Dh]
0x18003212d  jmp     short loc_18003219D
0x18003212f  cmp     [rbp+3Fh+var_68], r15d
0x180032133  jnz     short loc_18003213C
0x180032135  xor     eax, eax
0x180032137  jmp     loc_1800326F0
0x18003213c  mov     rcx, [rbp+3Fh+var_70]
0x180032140  lea     rax, [rbp+3Fh+var_88]
0x180032144  mov     [rsp+0F0h+var_C0], rax
0x180032149  lea     r9, ?FwInitWFICFPortInfoFromReg@@YAJPEAXPEAUHKEY__@@PEBGPEAU_tag_WF_ICF_PORT_INFO@@PEAH@Z; FwInitWFICFPortInfoFromReg(void *,HKEY__ *,ushort const *,_tag_WF_ICF_PORT_INFO *,int *)
0x180032150  lea     rax, [rbp+3Fh+arg_28]
0x180032154  mov     r8d, 58h ; 'X'
0x18003215a  mov     [rsp+0F0h+var_C8], rax
0x18003215f  lea     rdx, aList; "List"
0x180032166  mov     qword ptr [rsp+0F0h+var_D0], r14
0x18003216b  call    cs:__imp_FwArrayCreateFromRegistry
0x180032171  mov     ebx, eax
0x180032173  test    eax, eax
0x180032175  jns     short loc_1800321BC
0x180032177  mov     rcx, cs:WPP_GLOBAL_Control
0x18003217e  lea     rsi, WPP_GLOBAL_Control
0x180032185  cmp     rcx, rsi
0x180032188  jz      loc_1800326AA
0x18003218e  test    [rcx+1Ch], r12b
0x180032192  jz      loc_180032657
0x180032198  mov     edx, 0Fh
0x18003219d  mov     rcx, [rcx+10h]
0x1800321a1  lea     r8, WPP_10622196d762368449fa8f46c322a63a_Traceguids
0x1800321a8  mov     r9d, eax
0x1800321ab  call    WPP_SF_d
0x1800321b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800321b7  jmp     loc_180032657
0x1800321bc  xor     edx, edx
0x1800321be  mov     [rbp+3Fh+var_B0], edx
0x1800321c1  xor     ecx, ecx
0x1800321c3  lea     rsi, WPP_GLOBAL_Control
0x1800321ca  mov     [rbp+3Fh+var_AC], ecx
0x1800321cd  mov     eax, ebx
0x1800321cf  cmp     ecx, dword ptr [rbp+3Fh+var_88]
0x1800321d2  jnb     loc_180032634
0x1800321d8  mov     eax, ecx
0x1800321da  imul    r14, rax, 58h ; 'X'
0x1800321de  mov     rax, qword ptr [rbp+3Fh+var_88+8]
0x1800321e2  mov     eax, [rax+r14+28h]
0x1800321e7  test    eax, eax
0x1800321e9  cmovz   eax, r12d
0x1800321ed  xor     r12d, r12d
0x1800321f0  mov     [rbp+3Fh+var_A8], eax
0x1800321f3  cmp     r12d, eax
0x1800321f6  jnb     loc_1800324D6
0x1800321fc  mov     ecx, 1F8h
0x180032201  call    cs:__imp_FwAlloc
0x180032207  mov     rdi, rax
0x18003220a  test    rax, rax
0x18003220d  jz      loc_1800325FC
0x180032213  xor     edx, edx; Val
0x180032215  mov     r8d, 1F8h; Size
0x18003221b  mov     rcx, rax; void *
0x18003221e  call    memset_0
0x180032223  mov     ecx, 1
0x180032228  mov     [rdi+28h], r13d
0x18003222c  or      [rdi+124h], cx
0x180032233  mov     [rdi+2Ch], ecx
0x180032236  mov     word ptr [rdi+8], 100h
0x18003223c  mov     rax, qword ptr [rbp+3Fh+var_88+8]
0x180032240  lea     edx, [rcx+5]
0x180032243  lea     r13d, [rcx+10h]
0x180032247  cmp     [r14+rax+0Ch], edx
0x18003224c  jnz     short loc_180032254
0x18003224e  mov     [rdi+30h], dx
0x180032252  jmp     short loc_180032260
0x180032254  cmp     [r14+rax+0Ch], r13d
0x180032259  jnz     short loc_180032260
0x18003225b  mov     [rdi+30h], r13w
0x180032260  cmp     [rdi+30h], dx
0x180032264  jz      short loc_18003226D
0x180032266  cmp     [rdi+30h], r13w
0x18003226b  jnz     short loc_1800322A1
0x18003226d  mov     [rdi+40h], ecx
0x180032270  mov     ecx, 4
0x180032275  call    cs:__imp_FwAlloc
0x18003227b  mov     [rdi+48h], rax
0x18003227f  test    rax, rax
0x180032282  jz      loc_1800325D6
0x180032288  mov     rcx, qword ptr [rbp+3Fh+var_88+8]
0x18003228c  movzx   edx, word ptr [r14+rcx+8]
0x180032292  mov     [rax+2], dx
0x180032296  mov     rcx, [rdi+48h]
0x18003229a  movzx   eax, word ptr [rcx+2]
0x18003229e  mov     [rcx], ax
0x1800322a1  mov     rax, qword ptr [rbp+3Fh+var_88+8]
0x1800322a5  mov     r15, [r14+rax]
0x1800322a9  test    r15, r15
0x1800322ac  jnz     short loc_1800322B3
0x1800322ae  mov     r15, [r14+rax+48h]
0x1800322b3  lea     r13, [rdi+18h]
0x1800322b7  mov     rcx, r15
0x1800322ba  mov     rdx, r13
0x1800322bd  call    cs:__imp_FwStringCopy
0x1800322c3  mov     ebx, eax
0x1800322c5  test    eax, eax
0x1800322c7  js      loc_1800325B0
0x1800322cd  mov     ecx, [rdi+0B0h]
0x1800322d3  mov     r9d, 0FFFFFFFEh
0x1800322d9  mov     edx, [rdi+0B4h]
0x1800322df  mov     rax, qword ptr [rbp+3Fh+var_88+8]
0x1800322e3  mov     r8d, [r14+rax+10h]
0x1800322e8  mov     eax, ecx
0x1800322ea  and     ecx, r9d
0x1800322ed  or      eax, 1
0x1800322f0  test    r8d, r8d
0x1800322f3  cmovnz  ecx, eax
0x1800322f6  mov     eax, edx
0x1800322f8  and     edx, r9d
0x1800322fb  mov     [rdi+0B0h], ecx
0x180032301  or      eax, 1
0x180032304  lea     rcx, [rdi+0B8h]
0x18003230b  test    r8d, r8d
0x18003230e  mov     qword ptr [rsp+0F0h+var_D0], rcx
0x180032313  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18003231a  mov     ecx, 8
0x18003231f  cmovnz  edx, eax
0x180032322  mov     [rdi+0B4h], edx
0x180032328  lea     rdx, FwCopyIPv4SubNet
0x18003232f  mov     r9, qword ptr [rbp+3Fh+var_88+8]
0x180032333  add     r9, 18h
0x180032337  add     r9, r14
0x18003233a  call    cs:__imp_FwArrayCopy
0x180032340  mov     ebx, eax
0x180032342  test    eax, eax
0x180032344  js      loc_180032589
0x18003234a  mov     rax, qword ptr [rbp+3Fh+var_88+8]
0x18003234e  mov     edx, [r14+rax+38h]
0x180032353  mov     eax, edx
0x180032355  neg     eax
0x180032357  sbb     ecx, ecx
0x180032359  neg     ecx
0x18003235b  add     ecx, 2
0x18003235e  mov     [rdi+120h], ecx
0x180032364  mov     rcx, qword ptr [rbp+3Fh+var_88+8]
0x180032368  cmp     dword ptr [r14+rcx+28h], 0
0x18003236e  jz      loc_180032411
0x180032374  test    edx, edx
0x180032376  jz      loc_180032411
0x18003237c  mov     rcx, [r14+rcx+30h]
0x180032381  lea     rdx, [rbp+3Fh+hMem]
0x180032385  mov     eax, r12d
0x180032388  add     rax, rax
0x18003238b  mov     rcx, [rcx+rax*8]
0x18003238f  call    FwMigrateLegacyAuthenticatedBypassSddl
0x180032394  mov     ebx, eax
0x180032396  test    eax, eax
0x180032398  js      loc_18003253B
0x18003239e  mov     rcx, [rbp+3Fh+hMem]
0x1800323a2  lea     rdx, [rdi+128h]
0x1800323a9  call    cs:__imp_FwStringCopy
0x1800323af  mov     ebx, eax
0x1800323b1  test    eax, eax
0x1800323b3  js      loc_180032511
0x1800323b9  mov     rcx, [rbp+3Fh+hMem]; hMem
0x1800323bd  call    cs:__imp_LocalFree
0x1800323c3  mov     eax, 2
0x1800323c8  mov     [rbp+3Fh+hMem], 0
0x1800323d0  or      [rdi+124h], ax
0x1800323d7  lea     rcx, [rbp+3Fh+pszDest]; pszDest
0x1800323db  xor     r9d, r9d; unsigned __int64 *
0x1800323de  mov     dword ptr [rsp+0F0h+var_C0], r12d
0x1800323e3  lea     rax, aD_1; "-%d"
0x1800323ea  xor     r8d, r8d; unsigned __int16 **
0x1800323ed  mov     [rsp+0F0h+var_C8], rax; unsigned __int16 *
0x1800323f2  mov     [rsp+0F0h+var_D0], 800h; unsigned int
0x1800323fa  lea     edx, [r9+0Ah]; unsigned __int64
0x1800323fe  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180032403  mov     ebx, eax
0x180032405  test    eax, eax
0x180032407  js      loc_1800324E7
0x18003240d  mov     rcx, qword ptr [rbp+3Fh+var_88+8]
0x180032411  mov     eax, [r14+rcx+50h]
0x180032416  lea     r9, [rbp+3Fh+pszDest]
0x18003241a  mov     r8, [rbp+3Fh+var_A0]
0x18003241e  lea     rcx, [rdi+10h]
0x180032422  mov     [rdi+150h], eax
0x180032428  mov     rdx, qword ptr [rbp+3Fh+var_88+8]
0x18003242c  mov     qword ptr [rsp+0F0h+var_D0], 0
0x180032435  mov     rdx, [r14+rdx+48h]
0x18003243a  call    cs:__imp_FwStringBuild
0x180032440  mov     ebx, eax
0x180032442  test    eax, eax
0x180032444  js      loc_180032562
0x18003244a  cmp     [rbp+3Fh+arg_28], 0
0x18003244e  jz      short loc_1800324B0
0x180032450  mov     rcx, qword ptr [rbp+3Fh+var_88+8]
0x180032454  mov     edx, [r14+rcx+3Ch]
0x180032459  test    edx, edx
0x18003245b  jz      short loc_18003249C
0x18003245d  sub     edx, 1
0x180032460  jz      short loc_180032470
0x180032462  cmp     edx, 1
0x180032465  jnz     short loc_1800324B0
0x180032467  lea     rcx, aFirewallapiDll_2; "@FirewallAPI.dll,-28752"
0x18003246e  jmp     short loc_1800324A3
0x180032470  lea     rdx, [rdi+138h]
0x180032477  lea     rcx, aFirewallapiDll_0; "@FirewallAPI.dll,-23006"
0x18003247e  call    cs:__imp_FwStringCopy
0x180032484  mov     rcx, [r13+0]
0x180032488  mov     rdx, r13
0x18003248b  mov     rax, qword ptr [rbp+3Fh+var_88+8]
0x18003248f  mov     [r14+rax], rcx
0x180032493  lea     rcx, aFirewallapiDll_0; "@FirewallAPI.dll,-23006"
0x18003249a  jmp     short loc_1800324AA
0x18003249c  lea     rcx, aFirewallapiDll_4; "@FirewallAPI.dll,-28502"
0x1800324a3  lea     rdx, [rdi+138h]
0x1800324aa  call    cs:__imp_FwStringCopy
0x1800324b0  mov     r13, [rbp+3Fh+var_98]
0x1800324b4  mov     edx, [rbp+3Fh+var_B0]
0x1800324b7  inc     edx
0x1800324b9  mov     [rbp+3Fh+var_B0], edx
0x1800324bc  inc     r12d
0x1800324bf  mov     rax, [r13+0]
0x1800324c3  mov     [rdi], rax
0x1800324c6  mov     eax, [rbp+3Fh+var_A8]
0x1800324c9  mov     [r13+0], rdi
0x1800324cd  mov     r13d, [rbp+3Fh+arg_30]
0x1800324d1  jmp     loc_1800321F3
0x1800324d6  mov     ecx, [rbp+3Fh+var_AC]
0x1800324d9  mov     r12d, 1
0x1800324df  add     ecx, r12d
0x1800324e2  jmp     loc_1800321C3
0x1800324e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800324ee  mov     r12d, 1
0x1800324f4  cmp     rcx, rsi
0x1800324f7  jz      loc_18003264B
0x1800324fd  test    [rcx+1Ch], r12b
0x180032501  jz      loc_18003264B
0x180032507  lea     edx, [r12+15h]
0x18003250c  jmp     loc_1800325D1
0x180032511  mov     rcx, cs:WPP_GLOBAL_Control
0x180032518  mov     r12d, 1
0x18003251e  cmp     rcx, rsi
0x180032521  jz      loc_18003264B
0x180032527  test    [rcx+1Ch], r12b
0x18003252b  jz      loc_18003264B
0x180032531  lea     edx, [r12+14h]
  ... truncated ...
```
