# CClassContainer::SetPriorityByFileExt(ushort const *,ushort const *,uint)

- ea: `0x180023050`
- end: `0x180023320`
- name: `?SetPriorityByFileExt@CClassContainer@@UEAAJPEBG0I@Z`
- size: `720`
- prototype: `__int64 __fastcall(CClassContainer *this, const unsigned __int16 *, wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x1800016d0`
- `0x180008f58`
- `0x18001d130`
- `0x18001e82c`
- `0x180023050`
- `0x180023448`
- `0x18002350c`
- `0x18002435c`
- `0x180024458`
- `0x180026f3c`
- `0x18002ad84`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023253`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023263`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002327b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023253`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023263`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002327b`
- `adsldpc!ADSIGetObjectAttributes` at `0x180023170`
- `adsldpc!ADSIGetObjectAttributes` at `0x180023170`
- `adsldpc!ADSICloseDSObject` at `0x18002329d`
- `adsldpc!ADSICloseDSObject` at `0x18002329d`
- `adsldpc!ADSISetObjectAttributes` at `0x1800232fb`
- `adsldpc!ADSISetObjectAttributes` at `0x1800232fb`
- `adsldpc!FreeADsMem` at `0x180023292`
- `adsldpc!FreeADsMem` at `0x180023292`

## string_xrefs

- `0x180023141`: `lastUpdateSequence`

## pseudocode

```c
__int64 __fastcall CClassContainer::SetPriorityByFileExt(
        CClassContainer *this,
        const unsigned __int16 *a2,
        wchar_t *a3,
        unsigned int a4)
{
  DWORD v4; // esi
  wchar_t *v5; // r12
  const unsigned __int16 *v6; // rax
  unsigned __int16 **v8; // r15
  unsigned int v9; // r14d
  __int64 (__fastcall *v10)(CClassContainer *, const unsigned __int16 *, HLOCAL *); // rax
  DWORD v11; // edi
  int v12; // eax
  int v13; // ebx
  unsigned int v15; // eax
  __int128 v16; // xmm1
  __int64 v17; // rbx
  wchar_t *v18; // r12
  __int64 v19; // rcx
  bool v20; // zf
  __int64 v21; // rdx
  unsigned int i; // edi
  const unsigned __int16 *v23; // rdx
  __int64 v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v26; // [rsp+34h] [rbp-CCh] BYREF
  void *v27; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v28; // [rsp+40h] [rbp-C0h]
  int v29; // [rsp+44h] [rbp-BCh] BYREF
  wchar_t *String2; // [rsp+48h] [rbp-B8h]
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pMem; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 **v33; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v34; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v35; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v36[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _ads_attr_info v37; // [rsp+A0h] [rbp-60h] BYREF
  struct _ads_attr_info v38; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v39[20]; // [rsp+120h] [rbp+20h] BYREF

  v4 = 0;
  String2 = a3;
  v28 = a4;
  v35 = L"fileExtPriority";
  v5 = a3;
  v6 = *(const unsigned __int16 **)this;
  v27 = 0;
  hMem = 0;
  v8 = 0;
  v33 = 0;
  v9 = 0;
  v10 = (__int64 (__fastcall *)(CClassContainer *, const unsigned __int16 *, HLOCAL *))*((_QWORD *)v6 + 19);
  v11 = 0;
  pMem = 0;
  v25 = 0;
  v29 = 0;
  v26 = 0;
  v12 = v10(this, a2, &hMem);
  v13 = v12;
  if ( v12 >= 0 )
  {
    if ( v12 )
      return 2147746153LL;
    if ( (gCsOptions & 1) != 0 )
      v15 = GetADsOpenObjectFlags() | 0x21;
    else
      v15 = 101;
    v13 = DSServerOpenDSObject((const unsigned __int16 **)this + 74, (const unsigned __int16 *)hMem, v15, &v27);
    if ( v13 >= 0 )
    {
      GetCurrentUsn(v39);
      v34 = v39;
      PackStrArrToAttr(&v37, (WCHAR *)L"lastUpdateSequence", &v34, 1u);
      v9 = 1;
      if ( (int)ADSIGetObjectAttributes(v27, &v35, 1, &pMem, &v25) >= 0 && v25 )
      {
        v16 = *((_OWORD *)pMem + 1);
        v36[0] = *(_OWORD *)pMem;
        v36[1] = v16;
        UnpackStrArrFrom<_ads_attr_info>((__int64)v36, &v33, &v26);
        v8 = v33;
        v11 = v26;
      }
      if ( !v11 )
        goto LABEL_21;
      while ( 1 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v5[v17] );
        v18 = v8[v4];
        if ( !wcsncmp_0(v18, String2, (unsigned int)v17) )
        {
          v19 = -1;
          do
            ++v19;
          while ( v18[v19] );
          if ( v19 == v17 + 3 )
            break;
        }
        v20 = ++v4 == v11;
        if ( v4 >= v11 )
          goto LABEL_22;
        v5 = String2;
      }
      LODWORD(v24) = v28 % 0x64;
      v13 = StringCchPrintfW(v18, v19 + 1, L"%s:%2d", String2, v24);
      if ( v13 >= 0 )
      {
LABEL_21:
        v20 = v4 == v11;
LABEL_22:
        if ( v20 )
        {
          v13 = -2147221143;
        }
        else
        {
          if ( v11 )
          {
            PackStrArrToAttr(&v38, (WCHAR *)L"fileExtPriority", v8, v11);
            v9 = 2;
          }
          v13 = ADSISetObjectAttributes(v27, &v37, v9, &v29);
          if ( v13 >= 0 )
            UpdateStoreUsn(*((void **)this + 69), v39);
        }
      }
    }
  }
  LocalFree(v8);
  if ( hMem )
    LocalFree(hMem);
  for ( i = 0; i < v9; ++i )
    LocalFree(*((HLOCAL *)&v37.pADsValues + 4 * i));
  if ( pMem )
    FreeADsMem(pMem);
  ADSICloseDSObject(v27, v21);
  return RemapErrorCode(v13, v23);
}

```

## disassembly

```asm
0x180023050  push    rbp
0x180023052  push    rbx
0x180023053  push    rsi
0x180023054  push    rdi
0x180023055  push    r12
0x180023057  push    r13
0x180023059  push    r14
0x18002305b  push    r15
0x18002305d  lea     rbp, [rsp-58h]
0x180023062  sub     rsp, 158h
0x180023069  mov     rax, cs:__security_cookie
0x180023070  xor     rax, rsp
0x180023073  mov     [rbp+90h+var_48], rax
0x180023077  xor     esi, esi
0x180023079  mov     [rsp+190h+String2], r8
0x18002307e  lea     rax, aFileextpriorit; "fileExtPriority"
0x180023085  mov     [rsp+190h+var_150], r9d
0x18002308a  mov     [rsp+190h+var_120], rax
0x18002308f  mov     r12, r8
0x180023092  mov     rax, [rcx]
0x180023095  lea     r8, [rsp+190h+hMem]
0x18002309a  mov     r13, rcx
0x18002309d  mov     [rsp+190h+var_158], rsi
0x1800230a2  mov     [rsp+190h+hMem], rsi
0x1800230a7  mov     r15d, esi
0x1800230aa  mov     [rsp+190h+var_130], rsi
0x1800230af  mov     r14d, esi
0x1800230b2  mov     rax, [rax+98h]
0x1800230b9  mov     edi, esi
0x1800230bb  mov     [rsp+190h+pMem], rsi
0x1800230c0  mov     [rsp+190h+var_160], esi
0x1800230c4  mov     [rsp+190h+var_14C], esi
0x1800230c8  mov     [rsp+190h+var_15C], esi
0x1800230cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230d1  mov     ebx, eax
0x1800230d3  test    eax, eax
0x1800230d5  js      loc_180023250
0x1800230db  jz      short loc_1800230E7
0x1800230dd  mov     eax, 80040169h
0x1800230e2  jmp     loc_1800232AA
0x1800230e7  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x1800230ee  jz      short loc_1800230FA
0x1800230f0  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x1800230f5  or      eax, 21h
0x1800230f8  jmp     short loc_1800230FF
0x1800230fa  mov     eax, 65h ; 'e'
0x1800230ff  mov     rdx, [rsp+190h+hMem]; unsigned __int16 *
0x180023104  lea     rcx, [r13+250h]; struct CServerContext *
0x18002310b  lea     r9, [rsp+190h+var_158]; void **
0x180023110  mov     r8d, eax; int
0x180023113  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x180023118  mov     ebx, eax
0x18002311a  test    eax, eax
0x18002311c  js      loc_180023250
0x180023122  lea     rcx, [rbp+90h+var_70]; unsigned __int16 *
0x180023126  call    ?GetCurrentUsn@@YAXPEAG@Z; GetCurrentUsn(ushort *)
0x18002312b  lea     rax, [rbp+90h+var_70]
0x18002312f  mov     ebx, 1
0x180023134  mov     r9d, ebx; unsigned int
0x180023137  mov     [rsp+190h+var_128], rax
0x18002313c  lea     r8, [rsp+190h+var_128]; unsigned __int16 **
0x180023141  lea     rdx, aLastupdatesequ; "lastUpdateSequence"
0x180023148  lea     rcx, [rbp+90h+var_F0]; struct _ads_attr_info *
0x18002314c  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x180023151  mov     rcx, [rsp+190h+var_158]
0x180023156  lea     rax, [rsp+190h+var_160]
0x18002315b  lea     r9, [rsp+190h+pMem]
0x180023160  mov     [rsp+190h+var_170], rax
0x180023165  mov     r8d, ebx
0x180023168  lea     rdx, [rsp+190h+var_120]
0x18002316d  mov     r14d, ebx
0x180023170  call    cs:__imp_ADSIGetObjectAttributes
0x180023176  test    eax, eax
0x180023178  js      short loc_1800231B0
0x18002317a  cmp     [rsp+190h+var_160], esi
0x18002317e  jz      short loc_1800231B0
0x180023180  mov     rax, [rsp+190h+pMem]
0x180023185  lea     r8, [rsp+190h+var_15C]
0x18002318a  lea     rdx, [rsp+190h+var_130]
0x18002318f  lea     rcx, [rbp+90h+var_110]
0x180023193  movups  xmm0, xmmword ptr [rax]
0x180023196  movups  xmm1, xmmword ptr [rax+10h]
0x18002319a  movaps  [rbp+90h+var_110], xmm0
0x18002319e  movaps  [rbp+90h+var_100], xmm1
0x1800231a2  call    ??$UnpackStrArrFrom@U_ads_attr_info@@@@YAJU_ads_attr_info@@PEAPEAPEAGPEAK@Z; UnpackStrArrFrom<_ads_attr_info>(_ads_attr_info,ushort * * *,ulong *)
0x1800231a7  mov     r15, [rsp+190h+var_130]
0x1800231ac  mov     edi, [rsp+190h+var_15C]
0x1800231b0  xor     edx, edx
0x1800231b2  test    edi, edi
0x1800231b4  jz      loc_180023241
0x1800231ba  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800231be  inc     rbx
0x1800231c1  cmp     [r12+rbx*2], dx
0x1800231c6  jnz     short loc_1800231BE
0x1800231c8  mov     rdx, [rsp+190h+String2]; String2
0x1800231cd  mov     r8d, ebx; MaxCount
0x1800231d0  mov     eax, esi
0x1800231d2  mov     r12, [r15+rax*8]
0x1800231d6  mov     rcx, r12; String1
0x1800231d9  call    wcsncmp_0
0x1800231de  xor     edx, edx
0x1800231e0  test    eax, eax
0x1800231e2  jnz     short loc_1800231FB
0x1800231e4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800231e8  inc     rcx
0x1800231eb  cmp     [r12+rcx*2], dx
0x1800231f0  jnz     short loc_1800231E8
0x1800231f2  lea     rax, [rbx+3]
0x1800231f6  cmp     rcx, rax
0x1800231f9  jz      short loc_180023208
0x1800231fb  inc     esi
0x1800231fd  cmp     esi, edi
0x1800231ff  jnb     short loc_180023243
0x180023201  mov     r12, [rsp+190h+String2]
0x180023206  jmp     short loc_1800231BA
0x180023208  mov     r8d, [rsp+190h+var_150]
0x18002320d  mov     eax, 51EB851Fh
0x180023212  mov     r9, [rsp+190h+String2]
0x180023217  mul     r8d
0x18002321a  shr     edx, 5
0x18002321d  imul    eax, edx, 64h ; 'd'
0x180023220  lea     rdx, [rcx+1]; unsigned __int64
0x180023224  mov     rcx, r12; unsigned __int16 *
0x180023227  sub     r8d, eax
0x18002322a  mov     dword ptr [rsp+190h+var_170], r8d
0x18002322f  lea     r8, aS2d; "%s:%2d"
0x180023236  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002323b  mov     ebx, eax
0x18002323d  test    eax, eax
0x18002323f  js      short loc_18002324E
0x180023241  cmp     esi, edi
0x180023243  jnz     loc_1800232CA
0x180023249  mov     ebx, 80040169h
0x18002324e  xor     esi, esi
0x180023250  mov     rcx, r15; hMem
0x180023253  call    cs:__imp_LocalFree
0x180023259  mov     rcx, [rsp+190h+hMem]; hMem
0x18002325e  test    rcx, rcx
0x180023261  jz      short loc_180023269
0x180023263  call    cs:__imp_LocalFree
0x180023269  mov     edi, esi
0x18002326b  test    r14d, r14d
0x18002326e  jz      short loc_180023288
0x180023270  mov     ecx, edi
0x180023272  shl     rcx, 5
0x180023276  mov     rcx, [rbp+rcx+90h+var_F0.pADsValues]; hMem
0x18002327b  call    cs:__imp_LocalFree
0x180023281  inc     edi
0x180023283  cmp     edi, r14d
0x180023286  jb      short loc_180023270
0x180023288  mov     rcx, [rsp+190h+pMem]; pMem
0x18002328d  test    rcx, rcx
0x180023290  jz      short loc_180023298
0x180023292  call    cs:__imp_FreeADsMem
0x180023298  mov     rcx, [rsp+190h+var_158]
0x18002329d  call    cs:__imp_ADSICloseDSObject
0x1800232a3  mov     ecx, ebx; int
0x1800232a5  call    ?RemapErrorCode@@YAJJPEBG@Z; RemapErrorCode(long,ushort const *)
0x1800232aa  mov     rcx, [rbp+90h+var_48]
0x1800232ae  xor     rcx, rsp; StackCookie
0x1800232b1  call    __security_check_cookie
0x1800232b6  add     rsp, 158h
0x1800232bd  pop     r15
0x1800232bf  pop     r14
0x1800232c1  pop     r13
0x1800232c3  pop     r12
0x1800232c5  pop     rdi
0x1800232c6  pop     rsi
0x1800232c7  pop     rbx
0x1800232c8  pop     rbp
0x1800232c9  retn
0x1800232ca  xor     esi, esi
0x1800232cc  test    edi, edi
0x1800232ce  jz      short loc_1800232EA
0x1800232d0  mov     r9d, edi; unsigned int
0x1800232d3  lea     rdx, aFileextpriorit; "fileExtPriority"
0x1800232da  mov     r8, r15; unsigned __int16 **
0x1800232dd  lea     rcx, [rbp+90h+var_D0]; struct _ads_attr_info *
0x1800232e1  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x1800232e6  lea     r14d, [rsi+2]
0x1800232ea  mov     rcx, [rsp+190h+var_158]
0x1800232ef  lea     r9, [rsp+190h+var_14C]
0x1800232f4  mov     r8d, r14d
0x1800232f7  lea     rdx, [rbp+90h+var_F0]
0x1800232fb  call    cs:__imp_ADSISetObjectAttributes
0x180023301  mov     ebx, eax
0x180023303  test    eax, eax
0x180023305  js      loc_180023250
0x18002330b  mov     rcx, [r13+228h]; void *
0x180023312  lea     rdx, [rbp+90h+var_70]; unsigned __int16 *
0x180023316  call    ?UpdateStoreUsn@@YAJPEAXPEBG@Z; UpdateStoreUsn(void *,ushort const *)
0x18002331b  jmp     loc_180023250
```
