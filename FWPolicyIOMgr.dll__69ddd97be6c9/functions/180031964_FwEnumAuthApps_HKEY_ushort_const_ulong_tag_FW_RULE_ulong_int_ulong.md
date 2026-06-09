# FwEnumAuthApps(HKEY__ *,ushort const *,ulong *,_tag_FW_RULE * *,ulong,int,ulong)

- ea: `0x180031964`
- end: `0x180032047`
- name: `?FwEnumAuthApps@@YAJPEAUHKEY__@@PEBGPEAKPEAPEAU_tag_FW_RULE@@KHK@Z`
- size: `1763`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned int *, struct _tag_FW_RULE **, unsigned int, int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ba5c`

## callees

- `0x1800042c4`
- `0x180006230`
- `0x180006f50`
- `0x18000cff0`
- `0x18001f650`
- `0x18001ffd4`
- `0x1800230c0`
- `0x180031008`
- `0x180031964`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031ff2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031ff2`
- `fwbase!FwFree` at `0x180031d5f`
- `fwbase!FwFree` at `0x180031d5f`
- `fwbase!FwAlloc` at `0x180031ae8`
- `fwbase!FwAlloc` at `0x180031ae8`
- `fwbase!FwArrayCopy` at `0x180031be1`
- `fwbase!FwArrayCopy` at `0x180031be1`
- `fwbase!FwStringCopy` at `0x180031b3e`
- `fwbase!FwStringCopy` at `0x180031b5e`
- `fwbase!FwStringCopy` at `0x180031c50`
- `fwbase!FwStringCopy` at `0x180031d26`
- `fwbase!FwStringCopy` at `0x180031b3e`
- `fwbase!FwStringCopy` at `0x180031b5e`
- `fwbase!FwStringCopy` at `0x180031c50`
- `fwbase!FwStringCopy` at `0x180031d26`
- `fwbase!FwStringBuild` at `0x180031ced`
- `fwbase!FwStringBuild` at `0x180031d93`
- `fwbase!FwStringBuild` at `0x180031ced`
- `fwbase!FwStringBuild` at `0x180031d93`
- `fwbase!FwArrayDestroy` at `0x180032015`
- `fwbase!FwArrayDestroy` at `0x180032015`
- `fwbase!FwRegOpenKey` at `0x1800319e0`
- `fwbase!FwRegOpenKey` at `0x1800319e0`
- `fwbase!FwRegCloseKey` at `0x18003201f`
- `fwbase!FwRegCloseKey` at `0x18003201f`
- `fwbase!FwArrayCreateFromRegistry` at `0x180031a54`
- `fwbase!FwArrayCreateFromRegistry` at `0x180031a54`
- `fwbase!FwWcsICmp` at `0x180031d0e`
- `fwbase!FwWcsICmp` at `0x180031d0e`

## string_xrefs

- `0x180031d1f`: `@FirewallAPI.dll,-33002`
- `0x180031d07`: `@xpsp2res.dll,-22019`

## pseudocode

```c
__int64 __fastcall FwEnumAuthApps(
        HKEY a1,
        const unsigned __int16 *a2,
        unsigned int *a3,
        struct _tag_FW_RULE **a4,
        unsigned int a5,
        int a6,
        unsigned int a7)
{
  const wchar_t *v7; // rax
  _QWORD *v8; // rsi
  int v9; // eax
  int v10; // ebx
  LPCOLESTR v11; // rcx
  __int64 v12; // rdx
  __int64 v14; // r15
  unsigned int v15; // r12d
  __int64 v16; // r14
  unsigned int v17; // eax
  unsigned int v18; // r13d
  _QWORD *v19; // rax
  unsigned int v20; // eax
  int v21; // eax
  int v22; // ecx
  int v23; // edx
  int v24; // r8d
  int v25; // eax
  unsigned int v26; // ecx
  int v27; // eax
  int v28; // eax
  unsigned int v29; // edx
  int v30; // eax
  int v31; // edx
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r9
  __int64 v35; // [rsp+30h] [rbp-81h]
  unsigned int i; // [rsp+40h] [rbp-71h]
  const wchar_t *v37; // [rsp+48h] [rbp-69h]
  __int64 v40; // [rsp+60h] [rbp-51h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-49h] BYREF
  __int128 v42; // [rsp+70h] [rbp-41h] BYREF
  __int64 v43; // [rsp+80h] [rbp-31h] BYREF
  int v44; // [rsp+88h] [rbp-29h] BYREF
  wchar_t pszDest[8]; // [rsp+90h] [rbp-21h] BYREF
  int v46; // [rsp+A0h] [rbp-11h]

  v46 = 0;
  v43 = 0;
  v44 = 0;
  v7 = L"-Domain";
  hMem = 0;
  if ( a7 != 1 )
    v7 = L"-Standard";
  v8 = 0;
  v37 = v7;
  *(_OWORD *)pszDest = 0;
  v42 = 0;
  v9 = FwRegOpenKey(a1, a2, 1, &v43, &v44);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v12 = 26;
LABEL_13:
        WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_10622196d762368449fa8f46c322a63a_Traceguids, (unsigned int)v9);
        v11 = WPP_GLOBAL_Control;
        goto LABEL_80;
      }
      goto LABEL_80;
    }
    goto LABEL_86;
  }
  if ( !v44 )
    return 0;
  v9 = FwArrayCreateFromRegistry(v43, L"List", 88, FwInitWFICFAppInfoFromReg, FwInitWFICFAppInfoDestroy, &a6, &v42);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v12 = 27;
        goto LABEL_13;
      }
LABEL_80:
      if ( v11 != (LPCOLESTR)&WPP_GLOBAL_Control && (v11[14] & 1) != 0 )
        WPP_SF_Sd(*((_QWORD *)v11 + 2), 38, (unsigned int)WPP_10622196d762368449fa8f46c322a63a_Traceguids, 0, v10);
    }
LABEL_86:
    FwFreeWFRule(v8);
    if ( hMem )
      LocalFree(hMem);
    hMem = 0;
    goto LABEL_89;
  }
  v14 = 0;
  v15 = 0;
LABEL_15:
  if ( v15 < (unsigned int)v42 )
  {
    v16 = 88LL * v15;
    v17 = *(_DWORD *)(v16 + *((_QWORD *)&v42 + 1) + 48);
    if ( !v17 )
      v17 = 1;
    v18 = 0;
    for ( i = v17; ; v17 = i )
    {
      if ( v18 >= v17 )
      {
        ++v15;
        goto LABEL_15;
      }
      v19 = (_QWORD *)FwAlloc(504);
      v8 = v19;
      if ( !v19 )
        break;
      memset_0(v19, 0, 0x1F8u);
      v20 = a7;
      *((_WORD *)v8 + 146) |= 1u;
      *((_DWORD *)v8 + 11) = 1;
      *((_WORD *)v8 + 4) = 256;
      *((_DWORD *)v8 + 10) = v20;
      v14 = *(_QWORD *)(v16 + *((_QWORD *)&v42 + 1));
      if ( !v14 )
        v14 = *(_QWORD *)(v16 + *((_QWORD *)&v42 + 1) + 72);
      v21 = FwStringCopy(v14, v8 + 3);
      v10 = v21;
      if ( v21 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v33 = 29;
LABEL_71:
          v34 = (unsigned int)v21;
LABEL_75:
          WPP_SF_d(*((_QWORD *)v11 + 2), v33, WPP_10622196d762368449fa8f46c322a63a_Traceguids, v34);
          goto LABEL_78;
        }
        goto LABEL_79;
      }
      v21 = FwStringCopy(*(_QWORD *)(v16 + *((_QWORD *)&v42 + 1) + 8), v8 + 34);
      v10 = v21;
      if ( v21 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v33 = 30;
          goto LABEL_71;
        }
        goto LABEL_79;
      }
      v22 = *((_DWORD *)v8 + 44);
      v23 = *((_DWORD *)v8 + 45);
      *((_WORD *)v8 + 24) = 6;
      v24 = *(_DWORD *)(v16 + *((_QWORD *)&v42 + 1) + 24);
      v25 = v22;
      v26 = v22 & 0xFFFFFFFE;
      v27 = v25 | 1;
      if ( v24 )
        v26 = v27;
      v28 = v23;
      v29 = v23 & 0xFFFFFFFE;
      *((_DWORD *)v8 + 44) = v26;
      v30 = v28 | 1;
      if ( v24 )
        v29 = v30;
      *((_DWORD *)v8 + 45) = v29;
      v21 = FwArrayCopy(
              8,
              FwCopyIPv4SubNet,
              wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
              v16 + *((_QWORD *)&v42 + 1) + 32LL,
              v8 + 23);
      v10 = v21;
      if ( v21 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v33 = 31;
          goto LABEL_71;
        }
        goto LABEL_79;
      }
      v31 = *(_DWORD *)(v16 + *((_QWORD *)&v42 + 1) + 64);
      *((_DWORD *)v8 + 72) = (v31 != 0) + 2;
      v32 = *((_QWORD *)&v42 + 1);
      if ( *(_DWORD *)(v16 + *((_QWORD *)&v42 + 1) + 48) && v31 )
      {
        v21 = FwMigrateLegacyAuthenticatedBypassSddl(
                *(_QWORD *)(*(_QWORD *)(v16 + *((_QWORD *)&v42 + 1) + 56) + 16LL * v18),
                &hMem);
        v10 = v21;
        if ( v21 < 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v33 = 32;
            goto LABEL_71;
          }
          goto LABEL_79;
        }
        v21 = FwStringCopy(hMem, v8 + 37);
        v10 = v21;
        if ( v21 < 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v33 = 33;
            goto LABEL_71;
          }
          goto LABEL_79;
        }
        LocalFree(hMem);
        hMem = 0;
        *((_WORD *)v8 + 146) |= 2u;
        LODWORD(v35) = v18;
        v21 = StringCchPrintfExW(pszDest, 0xAu, 0, 0, 0x800u, L"-%d", v35);
        v10 = v21;
        if ( v21 < 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v33 = 34;
            goto LABEL_71;
          }
          goto LABEL_79;
        }
        v32 = *((_QWORD *)&v42 + 1);
      }
      *((_DWORD *)v8 + 84) = *(_DWORD *)(v16 + v32 + 80);
      v21 = FwStringBuild(v8 + 2, *(_QWORD *)(v16 + *((_QWORD *)&v42 + 1) + 72), L"-TCP", v37);
      v10 = v21;
      if ( v21 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v33 = 35;
          goto LABEL_71;
        }
        goto LABEL_79;
      }
      if ( a6 && !(unsigned int)FwWcsICmp(L"@xpsp2res.dll,-22019", v8[3]) )
        FwStringCopy(L"@FirewallAPI.dll,-33002", v8 + 39);
      *v8 = *a4;
      *a4 = (struct _tag_FW_RULE *)v8;
      v40 = 0;
      v21 = FwCopyRule(v8, &v40);
      v10 = v21;
      if ( v21 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v33 = 36;
          goto LABEL_71;
        }
        goto LABEL_79;
      }
      FwFree(*(_QWORD *)(v40 + 16));
      v21 = FwStringBuild(v40 + 16, *(_QWORD *)(v16 + *((_QWORD *)&v42 + 1) + 72), L"-UDP", v37);
      v10 = v21;
      if ( v21 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v33 = 37;
          goto LABEL_71;
        }
        goto LABEL_79;
      }
      ++v18;
      *(_WORD *)(v40 + 48) = 17;
      *(_QWORD *)v40 = *a4;
      *a4 = (struct _tag_FW_RULE *)v40;
    }
    v10 = -2147024882;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v33 = 28;
      v34 = 2147942414LL;
      goto LABEL_75;
    }
LABEL_79:
    if ( v14 )
    {
      if ( v11 != (LPCOLESTR)&WPP_GLOBAL_Control && (v11[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)v11 + 2), 39, WPP_10622196d762368449fa8f46c322a63a_Traceguids, (unsigned int)v10);
      goto LABEL_86;
    }
    goto LABEL_80;
  }
  *a3 = 2 * v42;
  if ( v10 < 0 )
  {
    v8 = 0;
LABEL_78:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_79;
  }
LABEL_89:
  FwArrayDestroy(88, FwInitWFICFAppInfoDestroy, &v42);
  FwRegCloseKey(v43);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180031964  push    rbp
0x180031966  push    rbx
0x180031967  push    rsi
0x180031968  push    rdi
0x180031969  push    r12
0x18003196b  push    r13
0x18003196d  push    r14
0x18003196f  push    r15
0x180031971  lea     rbp, [rsp-7]
0x180031976  sub     rsp, 0B8h
0x18003197d  mov     rax, cs:__security_cookie
0x180031984  xor     rax, rsp
0x180031987  mov     [rbp+3Fh+var_48], rax
0x18003198b  xor     edi, edi
0x18003198d  mov     [rbp+3Fh+var_98], r8
0x180031991  xor     eax, eax
0x180031993  mov     [rbp+3Fh+var_A0], r9
0x180031997  mov     [rbp+3Fh+var_50], eax
0x18003199a  lea     r8, aStandard; "-Standard"
0x1800319a1  xorps   xmm0, xmm0
0x1800319a4  mov     [rbp+3Fh+var_70], rdi
0x1800319a8  lea     r13d, [rdi+1]
0x1800319ac  mov     [rbp+3Fh+var_68], edi
0x1800319af  cmp     [rbp+3Fh+arg_30], r13d
0x1800319b3  lea     rax, aDomain_0; "-Domain"
0x1800319ba  lea     r9, [rbp+3Fh+var_70]
0x1800319be  mov     [rbp+3Fh+hMem], rdi
0x1800319c2  cmovnz  rax, r8
0x1800319c6  mov     esi, edi
0x1800319c8  mov     [rbp+3Fh+var_A8], rax
0x1800319cc  mov     r8d, r13d
0x1800319cf  lea     rax, [rbp+3Fh+var_68]
0x1800319d3  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800319d8  movups  xmmword ptr [rbp+3Fh+pszDest], xmm0
0x1800319dc  movups  [rbp+3Fh+var_80], xmm0
0x1800319e0  call    cs:__imp_FwRegOpenKey
0x1800319e6  lea     r14, ?FwInitWFICFAppInfoDestroy@@YAXPEAU_tag_WF_ICF_APP_INFO@@@Z; FwInitWFICFAppInfoDestroy(_tag_WF_ICF_APP_INFO *)
0x1800319ed  mov     ebx, eax
0x1800319ef  test    eax, eax
0x1800319f1  jns     short loc_180031A19
0x1800319f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319fa  lea     rdi, WPP_GLOBAL_Control
0x180031a01  cmp     rcx, rdi
0x180031a04  jz      loc_180031FE1
0x180031a0a  test    [rcx+1Ch], r13b
0x180031a0e  jz      loc_180031F8E
0x180031a14  lea     edx, [rsi+1Ah]
0x180031a17  jmp     short loc_180031A86
0x180031a19  cmp     [rbp+3Fh+var_68], edi
0x180031a1c  jnz     short loc_180031A25
0x180031a1e  xor     eax, eax
0x180031a20  jmp     loc_180032027
0x180031a25  mov     rcx, [rbp+3Fh+var_70]
0x180031a29  lea     rax, [rbp+3Fh+var_80]
0x180031a2d  mov     [rsp+0F0h+var_C0], rax
0x180031a32  lea     r9, ?FwInitWFICFAppInfoFromReg@@YAJPEAXPEAUHKEY__@@PEBGPEAU_tag_WF_ICF_APP_INFO@@PEAH@Z; FwInitWFICFAppInfoFromReg(void *,HKEY__ *,ushort const *,_tag_WF_ICF_APP_INFO *,int *)
0x180031a39  lea     rax, [rbp+3Fh+arg_28]
0x180031a3d  mov     r8d, 58h ; 'X'
0x180031a43  mov     [rsp+0F0h+var_C8], rax
0x180031a48  lea     rdx, aList; "List"
0x180031a4f  mov     qword ptr [rsp+0F0h+var_D0], r14
0x180031a54  call    cs:__imp_FwArrayCreateFromRegistry
0x180031a5a  mov     ebx, eax
0x180031a5c  test    eax, eax
0x180031a5e  jns     short loc_180031AA5
0x180031a60  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a67  lea     rdi, WPP_GLOBAL_Control
0x180031a6e  cmp     rcx, rdi
0x180031a71  jz      loc_180031FE1
0x180031a77  test    [rcx+1Ch], r13b
0x180031a7b  jz      loc_180031F8E
0x180031a81  mov     edx, 1Bh
0x180031a86  mov     rcx, [rcx+10h]
0x180031a8a  lea     r8, WPP_10622196d762368449fa8f46c322a63a_Traceguids
0x180031a91  mov     r9d, eax
0x180031a94  call    WPP_SF_d
0x180031a99  mov     rcx, cs:WPP_GLOBAL_Control
0x180031aa0  jmp     loc_180031F8E
0x180031aa5  mov     r15, rdi
0x180031aa8  mov     r12d, edi
0x180031aab  mov     eax, dword ptr [rbp+3Fh+var_80]
0x180031aae  lea     rdi, WPP_GLOBAL_Control
0x180031ab5  cmp     r12d, eax
0x180031ab8  jnb     loc_180031F69
0x180031abe  mov     eax, r12d
0x180031ac1  imul    r14, rax, 58h ; 'X'
0x180031ac5  mov     rax, qword ptr [rbp+3Fh+var_80+8]
0x180031ac9  mov     eax, [r14+rax+30h]
0x180031ace  test    eax, eax
0x180031ad0  cmovz   eax, r13d
0x180031ad4  xor     r13d, r13d
0x180031ad7  mov     [rbp+3Fh+var_B0], eax
0x180031ada  cmp     r13d, eax
0x180031add  jnb     loc_180031DCD
0x180031ae3  mov     ecx, 1F8h
0x180031ae8  call    cs:__imp_FwAlloc
0x180031aee  mov     rsi, rax
0x180031af1  test    rax, rax
0x180031af4  jz      loc_180031F33
0x180031afa  xor     edx, edx; Val
0x180031afc  mov     r8d, 1F8h; Size
0x180031b02  mov     rcx, rax; void *
0x180031b05  call    memset_0
0x180031b0a  mov     eax, [rbp+3Fh+arg_30]
0x180031b0d  mov     ecx, 1
0x180031b12  or      [rsi+124h], cx
0x180031b19  mov     [rsi+2Ch], ecx
0x180031b1c  mov     word ptr [rsi+8], 100h
0x180031b22  mov     [rsi+28h], eax
0x180031b25  mov     rax, qword ptr [rbp+3Fh+var_80+8]
0x180031b29  mov     r15, [r14+rax]
0x180031b2d  test    r15, r15
0x180031b30  jnz     short loc_180031B37
0x180031b32  mov     r15, [r14+rax+48h]
0x180031b37  lea     rdx, [rsi+18h]
0x180031b3b  mov     rcx, r15
0x180031b3e  call    cs:__imp_FwStringCopy
0x180031b44  mov     ebx, eax
0x180031b46  test    eax, eax
0x180031b48  js      loc_180031F12
0x180031b4e  mov     rcx, qword ptr [rbp+3Fh+var_80+8]
0x180031b52  lea     rdx, [rsi+110h]
0x180031b59  mov     rcx, [r14+rcx+8]
0x180031b5e  call    cs:__imp_FwStringCopy
0x180031b64  mov     ebx, eax
0x180031b66  test    eax, eax
0x180031b68  js      loc_180031EF4
0x180031b6e  mov     ecx, [rsi+0B0h]
0x180031b74  mov     r9d, 0FFFFFFFEh
0x180031b7a  mov     edx, [rsi+0B4h]
0x180031b80  mov     word ptr [rsi+30h], 6
0x180031b86  mov     rax, qword ptr [rbp+3Fh+var_80+8]
0x180031b8a  mov     r8d, [r14+rax+18h]
0x180031b8f  mov     eax, ecx
0x180031b91  and     ecx, r9d
0x180031b94  or      eax, 1
0x180031b97  test    r8d, r8d
0x180031b9a  cmovnz  ecx, eax
0x180031b9d  mov     eax, edx
0x180031b9f  and     edx, r9d
0x180031ba2  mov     [rsi+0B0h], ecx
0x180031ba8  or      eax, 1
0x180031bab  lea     rcx, [rsi+0B8h]
0x180031bb2  test    r8d, r8d
0x180031bb5  mov     qword ptr [rsp+0F0h+var_D0], rcx
0x180031bba  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180031bc1  mov     ecx, 8
0x180031bc6  cmovnz  edx, eax
0x180031bc9  mov     [rsi+0B4h], edx
0x180031bcf  lea     rdx, FwCopyIPv4SubNet
0x180031bd6  mov     r9, qword ptr [rbp+3Fh+var_80+8]
0x180031bda  add     r9, 20h ; ' '
0x180031bde  add     r9, r14
0x180031be1  call    cs:__imp_FwArrayCopy
0x180031be7  mov     ebx, eax
0x180031be9  test    eax, eax
0x180031beb  js      loc_180031ECE
0x180031bf1  mov     rax, qword ptr [rbp+3Fh+var_80+8]
0x180031bf5  mov     edx, [r14+rax+40h]
0x180031bfa  mov     eax, edx
0x180031bfc  neg     eax
0x180031bfe  sbb     ecx, ecx
0x180031c00  neg     ecx
0x180031c02  add     ecx, 2
0x180031c05  mov     [rsi+120h], ecx
0x180031c0b  mov     rcx, qword ptr [rbp+3Fh+var_80+8]
0x180031c0f  cmp     dword ptr [r14+rcx+30h], 0
0x180031c15  jz      loc_180031CB8
0x180031c1b  test    edx, edx
0x180031c1d  jz      loc_180031CB8
0x180031c23  mov     rcx, [r14+rcx+38h]
0x180031c28  lea     rdx, [rbp+3Fh+hMem]
0x180031c2c  mov     eax, r13d
0x180031c2f  add     rax, rax
0x180031c32  mov     rcx, [rcx+rax*8]
0x180031c36  call    FwMigrateLegacyAuthenticatedBypassSddl
0x180031c3b  mov     ebx, eax
0x180031c3d  test    eax, eax
0x180031c3f  js      loc_180031E2D
0x180031c45  mov     rcx, [rbp+3Fh+hMem]
0x180031c49  lea     rdx, [rsi+128h]
0x180031c50  call    cs:__imp_FwStringCopy
0x180031c56  mov     ebx, eax
0x180031c58  test    eax, eax
0x180031c5a  js      loc_180031E04
0x180031c60  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180031c64  call    cs:__imp_LocalFree
0x180031c6a  mov     eax, 2
0x180031c6f  mov     [rbp+3Fh+hMem], 0
0x180031c77  or      [rsi+124h], ax
0x180031c7e  lea     rcx, [rbp+3Fh+pszDest]; pszDest
0x180031c82  xor     r9d, r9d; unsigned __int64 *
0x180031c85  mov     dword ptr [rsp+0F0h+var_C0], r13d
0x180031c8a  lea     rax, aD_1; "-%d"
0x180031c91  xor     r8d, r8d; unsigned __int16 **
0x180031c94  mov     [rsp+0F0h+var_C8], rax; unsigned __int16 *
0x180031c99  mov     [rsp+0F0h+var_D0], 800h; unsigned int
0x180031ca1  lea     edx, [r9+0Ah]; unsigned __int64
0x180031ca5  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180031caa  mov     ebx, eax
0x180031cac  test    eax, eax
0x180031cae  js      loc_180031DDB
0x180031cb4  mov     rcx, qword ptr [rbp+3Fh+var_80+8]
0x180031cb8  mov     eax, [r14+rcx+50h]
0x180031cbd  lea     r8, aTcp; "-TCP"
0x180031cc4  mov     r9, [rbp+3Fh+var_A8]
0x180031cc8  lea     rcx, [rsi+10h]
0x180031ccc  mov     [rsi+150h], eax
0x180031cd2  lea     rax, [rbp+3Fh+pszDest]
0x180031cd6  mov     rdx, qword ptr [rbp+3Fh+var_80+8]
0x180031cda  mov     [rsp+0F0h+var_C8], 0
0x180031ce3  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180031ce8  mov     rdx, [r14+rdx+48h]
0x180031ced  call    cs:__imp_FwStringBuild
0x180031cf3  mov     ebx, eax
0x180031cf5  test    eax, eax
0x180031cf7  js      loc_180031EA8
0x180031cfd  cmp     [rbp+3Fh+arg_28], 0
0x180031d01  jz      short loc_180031D2C
0x180031d03  mov     rdx, [rsi+18h]
0x180031d07  lea     rcx, aXpsp2resDll220; "@xpsp2res.dll,-22019"
0x180031d0e  call    cs:__imp_FwWcsICmp
0x180031d14  test    eax, eax
0x180031d16  jnz     short loc_180031D2C
0x180031d18  lea     rdx, [rsi+138h]
0x180031d1f  lea     rcx, aFirewallapiDll; "@FirewallAPI.dll,-33002"
0x180031d26  call    cs:__imp_FwStringCopy
0x180031d2c  mov     rcx, [rbp+3Fh+var_A0]
0x180031d30  lea     rdx, [rbp+3Fh+var_90]
0x180031d34  mov     rax, [rcx]
0x180031d37  mov     [rsi], rax
0x180031d3a  mov     [rcx], rsi
0x180031d3d  mov     rcx, rsi
0x180031d40  mov     [rbp+3Fh+var_90], 0
0x180031d48  call    FwCopyRule
0x180031d4d  mov     ebx, eax
0x180031d4f  test    eax, eax
0x180031d51  js      loc_180031E7F
0x180031d57  mov     rcx, [rbp+3Fh+var_90]
0x180031d5b  mov     rcx, [rcx+10h]
0x180031d5f  call    cs:__imp_FwFree
0x180031d65  mov     rdx, qword ptr [rbp+3Fh+var_80+8]
0x180031d69  lea     rax, [rbp+3Fh+pszDest]
0x180031d6d  mov     rcx, [rbp+3Fh+var_90]
0x180031d71  lea     r8, aUdp; "-UDP"
0x180031d78  mov     r9, [rbp+3Fh+var_A8]
0x180031d7c  add     rcx, 10h
0x180031d80  mov     [rsp+0F0h+var_C8], 0
0x180031d89  mov     rdx, [r14+rdx+48h]
0x180031d8e  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180031d93  call    cs:__imp_FwStringBuild
0x180031d99  mov     ebx, eax
0x180031d9b  test    eax, eax
0x180031d9d  js      loc_180031E56
0x180031da3  mov     rax, [rbp+3Fh+var_90]
0x180031da7  inc     r13d
0x180031daa  mov     rdx, [rbp+3Fh+var_A0]
0x180031dae  mov     word ptr [rax+30h], 11h
0x180031db4  mov     rax, [rbp+3Fh+var_90]
0x180031db8  mov     rcx, [rdx]
0x180031dbb  mov     [rax], rcx
0x180031dbe  mov     rax, [rbp+3Fh+var_90]
0x180031dc2  mov     [rdx], rax
0x180031dc5  mov     eax, [rbp+3Fh+var_B0]
0x180031dc8  jmp     loc_180031ADA
0x180031dcd  mov     r13d, 1
0x180031dd3  add     r12d, r13d
0x180031dd6  jmp     loc_180031AAB
0x180031ddb  mov     rcx, cs:WPP_GLOBAL_Control
0x180031de2  mov     r13d, 1
0x180031de8  cmp     rcx, rdi
0x180031deb  jz      loc_180031F82
0x180031df1  test    [rcx+1Ch], r13b
0x180031df5  jz      loc_180031F82
0x180031dfb  lea     edx, [r13+21h]
0x180031dff  jmp     loc_180031F2E
0x180031e04  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e0b  mov     r13d, 1
0x180031e11  cmp     rcx, rdi
0x180031e14  jz      loc_180031F82
0x180031e1a  test    [rcx+1Ch], r13b
0x180031e1e  jz      loc_180031F82
0x180031e24  lea     edx, [r13+20h]
0x180031e28  jmp     loc_180031F2E
0x180031e2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e34  mov     r13d, 1
0x180031e3a  cmp     rcx, rdi
0x180031e3d  jz      loc_180031F82
0x180031e43  test    [rcx+1Ch], r13b
0x180031e47  jz      loc_180031F82
0x180031e4d  lea     edx, [r13+1Fh]
0x180031e51  jmp     loc_180031F2E
0x180031e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e5d  mov     r13d, 1
0x180031e63  cmp     rcx, rdi
0x180031e66  jz      loc_180031F82
0x180031e6c  test    [rcx+1Ch], r13b
0x180031e70  jz      loc_180031F82
0x180031e76  lea     edx, [r13+24h]
0x180031e7a  jmp     loc_180031F2E
  ... truncated ...
```
