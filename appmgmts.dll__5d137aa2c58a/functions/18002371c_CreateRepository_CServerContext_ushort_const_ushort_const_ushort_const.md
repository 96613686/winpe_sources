# CreateRepository(CServerContext *,ushort const *,ushort const *,ushort const *)

- ea: `0x18002371c`
- end: `0x180023bb8`
- name: `?CreateRepository@@YAJPEAVCServerContext@@PEBG11@Z`
- size: `1180`
- prototype: `int __fastcall(struct CServerContext *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18001b9d0`

## callees

- `0x1800016d0`
- `0x18001d130`
- `0x18001e754`
- `0x18002350c`
- `0x18002366c`
- `0x18002371c`
- `0x180023bc0`
- `0x180023cdc`
- `0x180024260`
- `0x18002435c`
- `0x180024458`
- `0x180026f3c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023aef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023af9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023b03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023b0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023b81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023aef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023af9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023b03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023b0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023b81`
- `adsldpc!ADSIGetObjectAttributes` at `0x18002380b`
- `adsldpc!ADSIGetObjectAttributes` at `0x180023941`
- `adsldpc!ADSIGetObjectAttributes` at `0x18002380b`
- `adsldpc!ADSIGetObjectAttributes` at `0x180023941`
- `adsldpc!BuildADsPathFromParent` at `0x1800238c6`
- `adsldpc!BuildADsPathFromParent` at `0x1800239d1`
- `adsldpc!BuildADsPathFromParent` at `0x1800238c6`
- `adsldpc!BuildADsPathFromParent` at `0x1800239d1`
- `adsldpc!ADSICloseDSObject` at `0x18002385d`
- `adsldpc!ADSICloseDSObject` at `0x180023974`
- `adsldpc!ADSICloseDSObject` at `0x180023b18`
- `adsldpc!ADSICloseDSObject` at `0x180023b23`
- `adsldpc!ADSICloseDSObject` at `0x180023b40`
- `adsldpc!ADSICloseDSObject` at `0x180023b63`
- `adsldpc!ADSICloseDSObject` at `0x18002385d`
- `adsldpc!ADSICloseDSObject` at `0x180023974`
- `adsldpc!ADSICloseDSObject` at `0x180023b18`
- `adsldpc!ADSICloseDSObject` at `0x180023b23`
- `adsldpc!ADSICloseDSObject` at `0x180023b40`
- `adsldpc!ADSICloseDSObject` at `0x180023b63`
- `adsldpc!ADSISetObjectAttributes` at `0x180023ae3`
- `adsldpc!ADSISetObjectAttributes` at `0x180023ae3`
- `adsldpc!ADSIDeleteDSObject` at `0x180023b53`
- `adsldpc!ADSIDeleteDSObject` at `0x180023b53`
- `adsldpc!FreeADsMem` at `0x18002384d`
- `adsldpc!FreeADsMem` at `0x180023905`
- `adsldpc!FreeADsMem` at `0x180023969`
- `adsldpc!FreeADsMem` at `0x180023b2e`
- `adsldpc!FreeADsMem` at `0x180023b73`
- `adsldpc!FreeADsMem` at `0x18002384d`
- `adsldpc!FreeADsMem` at `0x180023905`
- `adsldpc!FreeADsMem` at `0x180023969`
- `adsldpc!FreeADsMem` at `0x180023b2e`
- `adsldpc!FreeADsMem` at `0x180023b73`

## string_xrefs

- `0x180023a52`: `lastUpdateSequence`
- `0x180023a9b`: `extensionName`

## pseudocode

```c
int __fastcall CreateRepository(
        struct CServerContext *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int v4; // r13d
  unsigned __int16 *v7; // rsi
  unsigned __int16 *v9; // r12
  int result; // eax
  unsigned int v11; // edi
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int128 v14; // xmm1
  unsigned int v15; // eax
  int Container; // eax
  const unsigned __int16 *v17; // rdx
  int v18; // ebx
  int v19; // eax
  int v20; // ebx
  int v21; // ebx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  int v25; // [rsp+30h] [rbp-D0h] BYREF
  void *v26; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v27; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v28; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pMem; // [rsp+50h] [rbp-B0h] BYREF
  void *v30; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+68h] [rbp-98h] BYREF
  void *v33; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v34; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v35[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _ads_attr_info v36; // [rsp+A0h] [rbp-60h] BYREF
  struct _ads_attr_info v37; // [rsp+C0h] [rbp-40h] BYREF
  struct _ads_attr_info v38; // [rsp+E0h] [rbp-20h] BYREF
  struct _ads_attr_info v39; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v40[32]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v41[264]; // [rsp+160h] [rbp+60h] BYREF

  v4 = 0;
  v30 = 0;
  v31 = a4;
  v26 = 0;
  v7 = a2;
  v33 = 0;
  v28 = 0;
  v9 = 0;
  v27 = 0;
  v25 = 0;
  v32 = 0;
  v34 = L"displayName";
  pMem = 0;
  if ( !a2 )
  {
    result = GetRootPath(a1, v41, (unsigned int)a3);
    if ( result < 0 )
      return result;
    v7 = v41;
  }
  v11 = 101;
  if ( a4 )
  {
    if ( (gCsOptions & 1) != 0 )
      v12 = GetADsOpenObjectFlags() | 0x21;
    else
      v12 = 101;
    result = DSServerOpenDSObject(a1, a4, v12, &v33);
    if ( result < 0 )
      return result;
    if ( (int)ADSIGetObjectAttributes(v33, &v34, 1, &pMem, &v25) >= 0 && v25 )
    {
      v14 = *((_OWORD *)pMem + 1);
      v35[0] = *(_OWORD *)pMem;
      v35[1] = v14;
      UnpackStrAllocFrom<_ads_attr_info>((__int64)v35, (HLOCAL *)&v28);
      v9 = v28;
    }
    if ( pMem )
      FreeADsMem(pMem);
    pMem = 0;
    ADSICloseDSObject(v33, v13);
  }
  if ( (gCsOptions & 1) != 0 )
    v15 = GetADsOpenObjectFlags() | 0x21;
  else
    v15 = 101;
  result = DSServerOpenDSObject(a1, v7, v15, &v30);
  if ( result >= 0 )
  {
    Container = CreateContainer(v30, a3, L"Application Store");
    v18 = Container;
    if ( Container != -2147024713 && Container != -2147019886 )
      goto LABEL_36;
    if ( (int)BuildADsPathFromParent(v7, a3, &v27) >= 0 )
    {
      v19 = (gCsOptions & 1) != 0 ? GetADsOpenObjectFlags() | 0x21 : 101;
      v20 = DSServerOpenDSObject(a1, v27, v19, &v26);
      FreeADsMem(v27);
      if ( v20 >= 0 )
      {
        v34 = L"appSchemaVersion";
        v21 = 0;
        if ( (int)ADSIGetObjectAttributes(v26, &v34, 1, &pMem, &v25) >= 0 && v25 && *((_DWORD *)pMem + 6) )
          v21 = *(_DWORD *)(*((_QWORD *)pMem + 2) + 8LL);
        if ( pMem )
          FreeADsMem(pMem);
        ADSICloseDSObject(v26, v22);
        if ( v21 != 1740 )
        {
          if ( v21 )
            return -2147221138;
          DeleteRepository(a1, v7, a3);
          v18 = CreateContainer(v30, a3, L"Application Store");
LABEL_36:
          if ( v18 < 0 )
            goto LABEL_43;
          v4 = 1;
          v18 = BuildADsPathFromParent(v7, a3, &v27);
          if ( v18 < 0 )
            goto LABEL_43;
          if ( (gCsOptions & 1) != 0 )
            v11 = GetADsOpenObjectFlags() | 0x21;
          v18 = DSServerOpenDSObject(a1, v27, v11, &v26);
          if ( v18 < 0 || (v18 = CreateContainer(v26, L"CN=Packages", L"Application Packages"), v18 < 0) )
          {
LABEL_43:
            if ( v26 )
              ADSICloseDSObject(v26, v17);
            if ( v4 )
              ADSIDeleteDSObject(v30, a3);
            if ( v30 )
              ADSICloseDSObject(v30, v17);
            if ( v27 )
              FreeADsMem(v27);
            if ( !v9 )
              return RemapErrorCode(v18, v17);
          }
          else
          {
            GetCurrentUsn(v40);
            v28 = v40;
            PackStrArrToAttr(&v36, L"lastUpdateSequence", &v28, 1u);
            PackStrArrToAttr(&v37, L"displayName", &v31, v31 != 0);
            v31 = v9;
            PackStrArrToAttr(&v38, L"extensionName", &v31, v9 != 0);
            LODWORD(v28) = 1740;
            PackDWArrToAttr(&v39, L"appSchemaVersion", (unsigned int *)&v28, 1u);
            v18 = ADSISetObjectAttributes(v26, &v36, 4, &v32);
            LocalFree(v36.pADsValues);
            LocalFree(v37.pADsValues);
            LocalFree(v38.pADsValues);
            LocalFree(v39.pADsValues);
            ADSICloseDSObject(v26, v23);
            ADSICloseDSObject(v30, v24);
            FreeADsMem(v27);
          }
          LocalFree(v9);
          return RemapErrorCode(v18, v17);
        }
      }
    }
    return -2147221142;
  }
  return result;
}

```

## disassembly

```asm
0x18002371c  push    rbp
0x18002371e  push    rbx
0x18002371f  push    rsi
0x180023720  push    rdi
0x180023721  push    r12
0x180023723  push    r13
0x180023725  push    r14
0x180023727  push    r15
0x180023729  lea     rbp, [rsp-288h]
0x180023731  sub     rsp, 388h
0x180023738  mov     rax, cs:__security_cookie
0x18002373f  xor     rax, rsp
0x180023742  mov     [rbp+2C0h+var_50], rax
0x180023749  xor     r13d, r13d
0x18002374c  lea     rax, aDisplayname; "displayName"
0x180023753  mov     [rsp+3C0h+var_368], r13
0x180023758  mov     rbx, r9
0x18002375b  mov     [rsp+3C0h+var_360], rbx
0x180023760  mov     r15, r8
0x180023763  mov     [rsp+3C0h+var_388], r13
0x180023768  mov     rsi, rdx
0x18002376b  mov     [rsp+3C0h+var_350], r13
0x180023770  mov     r14, rcx
0x180023773  mov     [rsp+3C0h+var_378], r13
0x180023778  mov     r12d, r13d
0x18002377b  mov     [rsp+3C0h+var_380], r13
0x180023780  mov     [rsp+3C0h+var_390], r13d
0x180023785  mov     [rsp+3C0h+var_358], r13d
0x18002378a  mov     [rsp+3C0h+var_348], rax
0x18002378f  mov     [rsp+3C0h+pMem], r13
0x180023794  test    rdx, rdx
0x180023797  jnz     short loc_1800237AE
0x180023799  lea     rdx, [rbp+2C0h+var_260]; unsigned __int16 *
0x18002379d  call    ?GetRootPath@@YAJPEAVCServerContext@@PEAGK@Z; GetRootPath(CServerContext *,ushort *,ulong)
0x1800237a2  test    eax, eax
0x1800237a4  js      loc_180023B95
0x1800237aa  lea     rsi, [rbp+2C0h+var_260]
0x1800237ae  mov     edi, 65h ; 'e'
0x1800237b3  test    rbx, rbx
0x1800237b6  jz      loc_180023863
0x1800237bc  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x1800237c3  jz      short loc_1800237CF
0x1800237c5  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x1800237ca  or      eax, 21h
0x1800237cd  jmp     short loc_1800237D1
0x1800237cf  mov     eax, edi
0x1800237d1  lea     r9, [rsp+3C0h+var_350]; void **
0x1800237d6  mov     r8d, eax; int
0x1800237d9  mov     rdx, rbx; unsigned __int16 *
0x1800237dc  mov     rcx, r14; struct CServerContext *
0x1800237df  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x1800237e4  test    eax, eax
0x1800237e6  js      loc_180023B95
0x1800237ec  mov     rcx, [rsp+3C0h+var_350]
0x1800237f1  lea     rax, [rsp+3C0h+var_390]
0x1800237f6  lea     r9, [rsp+3C0h+pMem]
0x1800237fb  mov     [rsp+3C0h+var_3A0], rax
0x180023800  mov     r8d, 1
0x180023806  lea     rdx, [rsp+3C0h+var_348]
0x18002380b  call    cs:__imp_ADSIGetObjectAttributes
0x180023811  test    eax, eax
0x180023813  js      short loc_180023843
0x180023815  cmp     [rsp+3C0h+var_390], r13d
0x18002381a  jz      short loc_180023843
0x18002381c  mov     rax, [rsp+3C0h+pMem]
0x180023821  lea     rdx, [rsp+3C0h+var_378]
0x180023826  lea     rcx, [rbp+2C0h+var_340]
0x18002382a  movups  xmm0, xmmword ptr [rax]
0x18002382d  movups  xmm1, xmmword ptr [rax+10h]
0x180023831  movaps  [rbp+2C0h+var_340], xmm0
0x180023835  movaps  [rbp+2C0h+var_330], xmm1
0x180023839  call    ??$UnpackStrAllocFrom@U_ads_attr_info@@@@YAJU_ads_attr_info@@PEAPEAG@Z; UnpackStrAllocFrom<_ads_attr_info>(_ads_attr_info,ushort * *)
0x18002383e  mov     r12, [rsp+3C0h+var_378]
0x180023843  mov     rcx, [rsp+3C0h+pMem]; pMem
0x180023848  test    rcx, rcx
0x18002384b  jz      short loc_180023853
0x18002384d  call    cs:__imp_FreeADsMem
0x180023853  mov     rcx, [rsp+3C0h+var_350]
0x180023858  mov     [rsp+3C0h+pMem], r13
0x18002385d  call    cs:__imp_ADSICloseDSObject
0x180023863  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x18002386a  jz      short loc_180023876
0x18002386c  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x180023871  or      eax, 21h
0x180023874  jmp     short loc_180023878
0x180023876  mov     eax, edi
0x180023878  lea     r9, [rsp+3C0h+var_368]; void **
0x18002387d  mov     r8d, eax; int
0x180023880  mov     rdx, rsi; unsigned __int16 *
0x180023883  mov     rcx, r14; struct CServerContext *
0x180023886  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x18002388b  test    eax, eax
0x18002388d  js      loc_180023B95
0x180023893  mov     rcx, [rsp+3C0h+var_368]; void *
0x180023898  lea     r8, aApplicationSto; "Application Store"
0x18002389f  mov     rdx, r15; unsigned __int16 *
0x1800238a2  call    ?CreateContainer@@YAJPEAXPEBG1@Z; CreateContainer(void *,ushort const *,ushort const *)
0x1800238a7  mov     ebx, eax
0x1800238a9  cmp     eax, 800700B7h
0x1800238ae  jz      short loc_1800238BB
0x1800238b0  cmp     eax, 80071392h
0x1800238b5  jnz     loc_1800239B8
0x1800238bb  lea     r8, [rsp+3C0h+var_380]
0x1800238c0  mov     rdx, r15
0x1800238c3  mov     rcx, rsi
0x1800238c6  call    cs:__imp_?BuildADsPathFromParent@@YAJPEAG0PEAPEAG@Z; BuildADsPathFromParent(ushort *,ushort *,ushort * *)
0x1800238cc  test    eax, eax
0x1800238ce  js      loc_180023B90
0x1800238d4  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x1800238db  jz      short loc_1800238E7
0x1800238dd  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x1800238e2  or      eax, 21h
0x1800238e5  jmp     short loc_1800238E9
0x1800238e7  mov     eax, edi
0x1800238e9  mov     rdx, [rsp+3C0h+var_380]; unsigned __int16 *
0x1800238ee  lea     r9, [rsp+3C0h+var_388]; void **
0x1800238f3  mov     r8d, eax; int
0x1800238f6  mov     rcx, r14; struct CServerContext *
0x1800238f9  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x1800238fe  mov     rcx, [rsp+3C0h+var_380]; pMem
0x180023903  mov     ebx, eax
0x180023905  call    cs:__imp_FreeADsMem
0x18002390b  test    ebx, ebx
0x18002390d  js      loc_180023B90
0x180023913  mov     rcx, [rsp+3C0h+var_388]
0x180023918  lea     rax, aAppschemaversi; "appSchemaVersion"
0x18002391f  mov     [rsp+3C0h+var_348], rax
0x180023924  lea     r9, [rsp+3C0h+pMem]
0x180023929  lea     rax, [rsp+3C0h+var_390]
0x18002392e  mov     r8d, 1
0x180023934  lea     rdx, [rsp+3C0h+var_348]
0x180023939  mov     [rsp+3C0h+var_3A0], rax
0x18002393e  mov     ebx, r13d
0x180023941  call    cs:__imp_ADSIGetObjectAttributes
0x180023947  mov     rcx, [rsp+3C0h+pMem]; pMem
0x18002394c  test    eax, eax
0x18002394e  js      short loc_180023964
0x180023950  cmp     [rsp+3C0h+var_390], r13d
0x180023955  jz      short loc_180023964
0x180023957  cmp     [rcx+18h], r13d
0x18002395b  jz      short loc_180023964
0x18002395d  mov     rax, [rcx+10h]
0x180023961  mov     ebx, [rax+8]
0x180023964  test    rcx, rcx
0x180023967  jz      short loc_18002396F
0x180023969  call    cs:__imp_FreeADsMem
0x18002396f  mov     rcx, [rsp+3C0h+var_388]
0x180023974  call    cs:__imp_ADSICloseDSObject
0x18002397a  cmp     ebx, 6CCh
0x180023980  jz      loc_180023B90
0x180023986  test    ebx, ebx
0x180023988  jz      short loc_180023994
0x18002398a  mov     eax, 8004016Eh
0x18002398f  jmp     loc_180023B95
0x180023994  mov     r8, r15; unsigned __int16 *
0x180023997  mov     rdx, rsi; unsigned __int16 *
0x18002399a  mov     rcx, r14; struct CServerContext *
0x18002399d  call    ?DeleteRepository@@YAJPEAVCServerContext@@PEBG1@Z; DeleteRepository(CServerContext *,ushort const *,ushort const *)
0x1800239a2  mov     rcx, [rsp+3C0h+var_368]; void *
0x1800239a7  lea     r8, aApplicationSto; "Application Store"
0x1800239ae  mov     rdx, r15; unsigned __int16 *
0x1800239b1  call    ?CreateContainer@@YAJPEAXPEBG1@Z; CreateContainer(void *,ushort const *,ushort const *)
0x1800239b6  mov     ebx, eax
0x1800239b8  test    ebx, ebx
0x1800239ba  js      loc_180023B36
0x1800239c0  lea     r8, [rsp+3C0h+var_380]
0x1800239c5  mov     rdx, r15
0x1800239c8  mov     rcx, rsi
0x1800239cb  mov     r13d, 1
0x1800239d1  call    cs:__imp_?BuildADsPathFromParent@@YAJPEAG0PEAPEAG@Z; BuildADsPathFromParent(ushort *,ushort *,ushort * *)
0x1800239d7  mov     ebx, eax
0x1800239d9  test    eax, eax
0x1800239db  js      loc_180023B36
0x1800239e1  mov     esi, r13d
0x1800239e4  test    byte ptr cs:?gCsOptions@@3KA, sil; ulong gCsOptions
0x1800239eb  jz      short loc_1800239F7
0x1800239ed  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x1800239f2  mov     edi, eax
0x1800239f4  or      edi, 21h
0x1800239f7  mov     rdx, [rsp+3C0h+var_380]; unsigned __int16 *
0x1800239fc  lea     r9, [rsp+3C0h+var_388]; void **
0x180023a01  mov     r8d, edi; int
0x180023a04  mov     rcx, r14; struct CServerContext *
0x180023a07  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x180023a0c  mov     ebx, eax
0x180023a0e  test    eax, eax
0x180023a10  js      loc_180023B36
0x180023a16  mov     rcx, [rsp+3C0h+var_388]; void *
0x180023a1b  lea     r8, aApplicationPac; "Application Packages"
0x180023a22  lea     rdx, aCnPackages; "CN=Packages"
0x180023a29  call    ?CreateContainer@@YAJPEAXPEBG1@Z; CreateContainer(void *,ushort const *,ushort const *)
0x180023a2e  mov     ebx, eax
0x180023a30  test    eax, eax
0x180023a32  js      loc_180023B36
0x180023a38  lea     rcx, [rbp+2C0h+var_2A0]; unsigned __int16 *
0x180023a3c  call    ?GetCurrentUsn@@YAXPEAG@Z; GetCurrentUsn(ushort *)
0x180023a41  lea     rax, [rbp+2C0h+var_2A0]
0x180023a45  mov     r9d, esi; unsigned int
0x180023a48  lea     r8, [rsp+3C0h+var_378]; unsigned __int16 **
0x180023a4d  mov     [rsp+3C0h+var_378], rax
0x180023a52  lea     rdx, aLastupdatesequ; "lastUpdateSequence"
0x180023a59  lea     rcx, [rbp+2C0h+var_320]; struct _ads_attr_info *
0x180023a5d  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x180023a62  mov     rax, [rsp+3C0h+var_360]
0x180023a67  lea     r8, [rsp+3C0h+var_360]; unsigned __int16 **
0x180023a6c  xor     r9d, r9d
0x180023a6f  mov     [rsp+3C0h+var_360], rax
0x180023a74  test    rax, rax
0x180023a77  lea     rdx, aDisplayname; "displayName"
0x180023a7e  lea     rcx, [rbp+2C0h+var_300]; struct _ads_attr_info *
0x180023a82  setnz   r9b; unsigned int
0x180023a86  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x180023a8b  xor     r9d, r9d
0x180023a8e  mov     [rsp+3C0h+var_360], r12
0x180023a93  test    r12, r12
0x180023a96  lea     r8, [rsp+3C0h+var_360]; unsigned __int16 **
0x180023a9b  lea     rdx, aExtensionname; "extensionName"
0x180023aa2  setnz   r9b; unsigned int
0x180023aa6  lea     rcx, [rbp+2C0h+var_2E0]; struct _ads_attr_info *
0x180023aaa  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x180023aaf  mov     r9d, esi; unsigned int
0x180023ab2  mov     dword ptr [rsp+3C0h+var_378], 6CCh
0x180023aba  lea     r8, [rsp+3C0h+var_378]; unsigned int *
0x180023abf  lea     rdx, aAppschemaversi; "appSchemaVersion"
0x180023ac6  lea     rcx, [rbp+2C0h+var_2C0]; struct _ads_attr_info *
0x180023aca  call    ?PackDWArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAKK@Z; PackDWArrToAttr(_ads_attr_info *,ushort const *,ulong *,ulong)
0x180023acf  mov     rcx, [rsp+3C0h+var_388]
0x180023ad4  lea     r9, [rsp+3C0h+var_358]
0x180023ad9  mov     r8d, 4
0x180023adf  lea     rdx, [rbp+2C0h+var_320]
0x180023ae3  call    cs:__imp_ADSISetObjectAttributes
0x180023ae9  mov     rcx, [rbp+2C0h+var_320.pADsValues]; hMem
0x180023aed  mov     ebx, eax
0x180023aef  call    cs:__imp_LocalFree
0x180023af5  mov     rcx, [rbp+2C0h+var_300.pADsValues]; hMem
0x180023af9  call    cs:__imp_LocalFree
0x180023aff  mov     rcx, [rbp+2C0h+var_2E0.pADsValues]; hMem
0x180023b03  call    cs:__imp_LocalFree
0x180023b09  mov     rcx, [rbp+2C0h+var_2C0.pADsValues]; hMem
0x180023b0d  call    cs:__imp_LocalFree
0x180023b13  mov     rcx, [rsp+3C0h+var_388]
0x180023b18  call    cs:__imp_ADSICloseDSObject
0x180023b1e  mov     rcx, [rsp+3C0h+var_368]
0x180023b23  call    cs:__imp_ADSICloseDSObject
0x180023b29  mov     rcx, [rsp+3C0h+var_380]; pMem
0x180023b2e  call    cs:__imp_FreeADsMem
0x180023b34  jmp     short loc_180023B7E
0x180023b36  mov     rcx, [rsp+3C0h+var_388]
0x180023b3b  test    rcx, rcx
0x180023b3e  jz      short loc_180023B46
0x180023b40  call    cs:__imp_ADSICloseDSObject
0x180023b46  test    r13d, r13d
0x180023b49  jz      short loc_180023B59
0x180023b4b  mov     rcx, [rsp+3C0h+var_368]
0x180023b50  mov     rdx, r15
0x180023b53  call    cs:__imp_ADSIDeleteDSObject
0x180023b59  mov     rcx, [rsp+3C0h+var_368]
0x180023b5e  test    rcx, rcx
0x180023b61  jz      short loc_180023B69
0x180023b63  call    cs:__imp_ADSICloseDSObject
0x180023b69  mov     rcx, [rsp+3C0h+var_380]; pMem
0x180023b6e  test    rcx, rcx
0x180023b71  jz      short loc_180023B79
0x180023b73  call    cs:__imp_FreeADsMem
0x180023b79  test    r12, r12
0x180023b7c  jz      short loc_180023B87
0x180023b7e  mov     rcx, r12; hMem
0x180023b81  call    cs:__imp_LocalFree
0x180023b87  mov     ecx, ebx; int
0x180023b89  call    ?RemapErrorCode@@YAJJPEBG@Z; RemapErrorCode(long,ushort const *)
0x180023b8e  jmp     short loc_180023B95
0x180023b90  mov     eax, 8004016Ah
0x180023b95  mov     rcx, [rbp+2C0h+var_50]
0x180023b9c  xor     rcx, rsp; StackCookie
0x180023b9f  call    __security_check_cookie
0x180023ba4  add     rsp, 388h
0x180023bab  pop     r15
0x180023bad  pop     r14
0x180023baf  pop     r13
0x180023bb1  pop     r12
0x180023bb3  pop     rdi
0x180023bb4  pop     rsi
0x180023bb5  pop     rbx
0x180023bb6  pop     rbp
0x180023bb7  retn
```
