# CDsmDeviceScan::OnDeviceArrival(CDevObject *)

- ea: `0x180004580`
- end: `0x18000491c`
- name: `?OnDeviceArrival@CDsmDeviceScan@@UEAAXPEAVCDevObject@@@Z`
- size: `924`
- prototype: `void __fastcall(CDsmDeviceScan *__hidden this, struct CDevObject *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180004580`
- `0x180004924`
- `0x180004b40`
- `0x180004e94`
- `0x1800112a4`
- `0x18001af70`
- `0x18001b98a`
- `0x18001ba48`
- `0x180020aa4`
- `0x180021790`
- `0x180022070`
- `0x180025074`
- `0x180027ba8`
- `0x18002f240`
- `0x1800419a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000465b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000465b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x180004688`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x180004688`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800046e6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800046e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004871`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004871`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000483f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000483f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004885`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004885`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004617`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004617`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800048ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800048ec`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180004749`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180004749`

## string_xrefs

- `0x1800045d0`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDsmDeviceScan::OnDeviceArrival(
        CDsmDeviceScan *this,
        struct CDevObject *a2,
        __int64 a3,
        const char *a4)
{
  unsigned __int16 *v6; // rbx
  _BYTE *v7; // r15
  __int64 v8; // rcx
  char *v9; // rax
  size_t v10; // rdi
  size_t v11; // r14
  unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rsi
  const unsigned __int16 *v14; // rcx
  int v15; // ecx
  int v16; // ecx
  HRESULT v17; // edi
  __int64 v18; // rax
  const struct _DEVPROPERTY *v19; // rdx
  CDevObject *v20; // rcx
  unsigned int v21; // r8d
  __int64 v22; // rax
  bool v23; // r12
  const wchar_t *v24; // r9
  RTL_SRWLOCK *v25; // r15
  int v26; // [rsp+20h] [rbp-88h]
  struct tagPROPVARIANT pvar; // [rsp+40h] [rbp-68h] BYREF
  HRESULT *v28; // [rsp+58h] [rbp-50h] BYREF
  GUID pclsid; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v6 = 0;
  v7 = *(_BYTE **)(*((_QWORD *)a2 + 2) + 8LL);
  if ( !v7 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  v8 = 0x7FFFFFFF;
  v9 = *(char **)(*((_QWORD *)a2 + 2) + 8LL);
  do
  {
    if ( !*(_WORD *)v9 )
      break;
    v9 += 2;
    --v8;
  }
  while ( v8 );
  v10 = 2 * ((v9 - v7) >> 1);
  v11 = v10 + 2;
  v12 = (unsigned __int16 *)CoTaskMemAlloc(v10 + 2);
  v13 = v12;
  if ( !v12 )
  {
    v17 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\base\\Devices\\Setup\\Dsm\\inc\\DevObjectQuery.h",
      (const char *)0x8007000ELL,
      v26);
    goto LABEL_47;
  }
  if ( v10 )
  {
    if ( v11 >= v10 )
    {
      memcpy_0(v12, v7, v10);
      v14 = &v13[v10 / 2];
      v13[v10 / 2] = 0;
      goto LABEL_12;
    }
    memset_0(v12, 0, v11);
    *(_DWORD *)_o__errno() = 34;
    invalid_parameter_noinfo();
  }
  v14 = &v13[v10 / 2];
  v13[v10 / 2] = 0;
LABEL_12:
  *v14 = 0;
  _o__wcsupr(v13);
  v6 = (unsigned __int16 *)v13;
  v15 = *((_DWORD *)this + 40);
  if ( v15 == 3 )
  {
    memset(&pvar, 0, sizeof(pvar));
    v17 = -2147467259;
    v18 = *((_QWORD *)a2 + 2);
    v19 = *(const struct _DEVPROPERTY **)(v18 + 24);
    v20 = 0;
    v21 = *(_DWORD *)(v18 + 16);
    while ( (unsigned int)v20 < v21 )
    {
      v22 = *(_QWORD *)&v19->CompKey.Key.fmtid.Data1 - *(_QWORD *)&DEVPKEY_Device_IsPresent.fmtid.Data1;
      if ( *(_QWORD *)&v19->CompKey.Key.fmtid.Data1 == *(_QWORD *)&DEVPKEY_Device_IsPresent.fmtid.Data1 )
        v22 = *(_QWORD *)v19->CompKey.Key.fmtid.Data4 - *(_QWORD *)DEVPKEY_Device_IsPresent.fmtid.Data4;
      if ( !v22 && v19->CompKey.Key.pid == 5 )
      {
        v17 = CDevObject::_ConvertToPPV(v20, v19, &pvar);
        break;
      }
      ++v19;
      v20 = (CDevObject *)(unsigned int)((_DWORD)v20 + 1);
    }
    if ( v17 >= 0 )
    {
      v23 = pvar.vt == 11 && pvar.iVal == -1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v24 = L"IsPresent";
        if ( !v23 )
          v24 = L"NOT Present";
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_43d4499022663c6448c6fdf63854fbee_Traceguids,
          (_DWORD)v24,
          (__int64)v13);
      }
      v25 = (RTL_SRWLOCK *)((char *)this + 32);
      *(_QWORD *)&pclsid.Data1 = (char *)this + 32;
      AcquireSRWLockExclusive((PSRWLOCK)this + 4);
      try
      {
        ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<bool>>::SetAt(
          (char *)this + 88,
          v13,
          v23);
      }
      catch ( ATL::CAtlException *v28 )
      {
        v6 = (unsigned __int16 *)v13;
        v17 = *v28;
        v25 = *(RTL_SRWLOCK **)&pclsid.Data1;
      }
      ReleaseSRWLockExclusive(v25);
    }
    PropVariantClear((PROPVARIANT *)&pvar);
LABEL_47:
    if ( v17 >= 0 )
      goto LABEL_51;
    goto LABEL_48;
  }
  v16 = v15 - 1;
  if ( v16 )
  {
    if ( v16 == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_43d4499022663c6448c6fdf63854fbee_Traceguids);
      ResetEvent(*((HANDLE *)this + 3));
    }
    goto LABEL_51;
  }
  if ( !IsContainerRefreshDateExpired(v13, *((const unsigned __int16 **)this + 21)) )
    goto LABEL_51;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_43d4499022663c6448c6fdf63854fbee_Traceguids, v13);
  pclsid = 0;
  v17 = CLSIDFromString(v13, &pclsid);
  if ( v17 >= 0 )
  {
    v17 = CDsmDeviceScan::_AddDeviceToList(this, &pclsid);
    goto LABEL_47;
  }
LABEL_48:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      &WPP_43d4499022663c6448c6fdf63854fbee_Traceguids,
      (unsigned int)v17);
LABEL_51:
  if ( v6 )
    CoTaskMemFree(v6);
}

```

## disassembly

```asm
0x180004580  mov     [rsp+arg_10], rbx
0x180004585  mov     [rsp+arg_18], rsi
0x18000458a  push    rdi
0x18000458b  push    r12
0x18000458d  push    r13
0x18000458f  push    r14
0x180004591  push    r15
0x180004593  sub     rsp, 80h
0x18000459a  mov     rax, cs:__security_cookie
0x1800045a1  xor     rax, rsp
0x1800045a4  mov     [rsp+0A8h+var_38], rax
0x1800045a9  mov     r12, rdx
0x1800045ac  mov     r13, rcx
0x1800045af  xor     ebx, ebx
0x1800045b1  mov     rax, [rdx+10h]
0x1800045b5  mov     r15, [rax+8]
0x1800045b9  test    r15, r15
0x1800045bc  jnz     short loc_1800045C2
0x1800045be  mov     al, 1
0x1800045c0  jmp     short loc_1800045C4
0x1800045c2  xor     al, al
0x1800045c4  mov     rcx, [rsp+0A8h]; this
0x1800045cc  test    al, al
0x1800045ce  jz      short loc_1800045E2
0x1800045d0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800045d7  mov     edx, 0F89h; void *
0x1800045dc  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800045e2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800045e9  test    r15, r15
0x1800045ec  jz      short loc_18000460C
0x1800045ee  mov     ecx, 7FFFFFFFh
0x1800045f3  mov     rax, r15
0x1800045f6  cmp     word ptr [rax], 0
0x1800045fa  jz      short loc_180004606
0x1800045fc  add     rax, 2
0x180004600  sub     rcx, 1
0x180004604  jnz     short loc_1800045F6
0x180004606  sub     rax, r15
0x180004609  sar     rax, 1
0x18000460c  lea     rdi, [rax+rax]
0x180004610  lea     r14, [rdi+2]
0x180004614  mov     rcx, r14; cb
0x180004617  call    cs:__imp_CoTaskMemAlloc
0x18000461d  mov     rsi, rax
0x180004620  test    rax, rax
0x180004623  jz      loc_18000488D
0x180004629  test    r15, r15
0x18000462c  jz      short loc_180004677
0x18000462e  test    rdi, rdi
0x180004631  jz      short loc_18000466C
0x180004633  mov     rcx, rax; void *
0x180004636  cmp     r14, rdi
0x180004639  jb      short loc_180004651
0x18000463b  mov     r8, rdi; Size
0x18000463e  mov     rdx, r15; Src
0x180004641  call    memcpy_0
0x180004646  lea     rcx, [rdi+rsi]
0x18000464a  xor     eax, eax
0x18000464c  mov     [rcx], ax
0x18000464f  jmp     short loc_180004680
0x180004651  mov     r8, r14; Size
0x180004654  xor     edx, edx; Val
0x180004656  call    memset_0
0x18000465b  call    cs:__imp__o__errno
0x180004661  mov     dword ptr [rax], 22h ; '"'
0x180004667  call    _invalid_parameter_noinfo
0x18000466c  lea     rcx, [rdi+rsi]
0x180004670  xor     eax, eax
0x180004672  mov     [rcx], ax
0x180004675  jmp     short loc_180004680
0x180004677  xor     eax, eax
0x180004679  mov     [rsi], ax
0x18000467c  lea     rcx, [rdi+rsi]
0x180004680  xor     eax, eax
0x180004682  mov     [rcx], ax
0x180004685  mov     rcx, rsi
0x180004688  call    cs:__imp__o__wcsupr
0x18000468e  mov     rbx, rsi
0x180004691  mov     [rsp+0A8h+var_70], rbx
0x180004696  mov     ecx, [r13+0A0h]
0x18000469d  cmp     ecx, 3
0x1800046a0  jz      loc_18000476D
0x1800046a6  sub     ecx, 1
0x1800046a9  jz      short loc_1800046F1
0x1800046ab  cmp     ecx, 1
0x1800046ae  jnz     loc_1800048E4
0x1800046b4  lea     r14, WPP_GLOBAL_Control
0x1800046bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046c2  cmp     rcx, r14
0x1800046c5  jz      short loc_1800046E2
0x1800046c7  test    byte ptr [rcx+1Ch], 1
0x1800046cb  jz      short loc_1800046E2
0x1800046cd  mov     edx, 1Eh
0x1800046d2  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x1800046d9  mov     rcx, [rcx+10h]
0x1800046dd  call    WPP_SF_
0x1800046e2  mov     rcx, [r13+18h]; hEvent
0x1800046e6  call    cs:__imp_ResetEvent
0x1800046ec  jmp     loc_1800048E4
0x1800046f1  mov     rdx, [r13+0A8h]; unsigned __int16 *
0x1800046f8  mov     rcx, rsi; unsigned __int16 *
0x1800046fb  call    ?IsContainerRefreshDateExpired@@YA_NPEBG0@Z; IsContainerRefreshDateExpired(ushort const *,ushort const *)
0x180004700  test    al, al
0x180004702  jz      loc_1800048E4
0x180004708  lea     r14, WPP_GLOBAL_Control
0x18000470f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004716  cmp     rcx, r14
0x180004719  jz      short loc_180004739
0x18000471b  test    byte ptr [rcx+1Ch], 1
0x18000471f  jz      short loc_180004739
0x180004721  mov     edx, 1Dh
0x180004726  mov     r9, rsi
0x180004729  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x180004730  mov     rcx, [rcx+10h]
0x180004734  call    WPP_SF_S
0x180004739  xorps   xmm0, xmm0
0x18000473c  movups  xmmword ptr [rsp+0A8h+pclsid.Data1], xmm0
0x180004741  lea     rdx, [rsp+0A8h+pclsid]; pclsid
0x180004746  mov     rcx, rsi; lpsz
0x180004749  call    cs:__imp_CLSIDFromString
0x18000474f  mov     edi, eax
0x180004751  test    eax, eax
0x180004753  js      loc_1800048B9
0x180004759  lea     rdx, [rsp+0A8h+pclsid]; struct _GUID *
0x18000475e  mov     rcx, r13; this
0x180004761  call    ?_AddDeviceToList@CDsmDeviceScan@@AEAAJAEBU_GUID@@@Z; CDsmDeviceScan::_AddDeviceToList(_GUID const &)
0x180004766  mov     edi, eax
0x180004768  jmp     loc_1800048B5
0x18000476d  xorps   xmm0, xmm0
0x180004770  xor     eax, eax
0x180004772  movups  xmmword ptr [rsp+0A8h+pvar], xmm0
0x180004777  mov     [rsp+0A8h+var_58], rax
0x18000477c  mov     edi, 80004005h
0x180004781  mov     rax, [r12+10h]
0x180004786  mov     rdx, [rax+18h]; struct _DEVPROPERTY *
0x18000478a  xor     ecx, ecx; this
0x18000478c  mov     r8d, [rax+10h]
0x180004790  cmp     ecx, r8d
0x180004793  jnb     short loc_1800047CB
0x180004795  mov     rax, [rdx]
0x180004798  sub     rax, qword ptr cs:DEVPKEY_Device_IsPresent.fmtid.Data1
0x18000479f  jnz     short loc_1800047AC
0x1800047a1  mov     rax, [rdx+8]
0x1800047a5  sub     rax, qword ptr cs:DEVPKEY_Device_IsPresent.fmtid.Data4
0x1800047ac  test    rax, rax
0x1800047af  jnz     short loc_1800047B7
0x1800047b1  cmp     dword ptr [rdx+10h], 5
0x1800047b5  jz      short loc_1800047BF
0x1800047b7  add     rdx, 30h ; '0'
0x1800047bb  inc     ecx
0x1800047bd  jmp     short loc_180004790
0x1800047bf  lea     r8, [rsp+0A8h+pvar]; struct tagPROPVARIANT *
0x1800047c4  call    ?_ConvertToPPV@CDevObject@@AEAAJPEBU_DEVPROPERTY@@PEAUtagPROPVARIANT@@@Z; CDevObject::_ConvertToPPV(_DEVPROPERTY const *,tagPROPVARIANT *)
0x1800047c9  mov     edi, eax
0x1800047cb  test    edi, edi
0x1800047cd  js      loc_180004879
0x1800047d3  cmp     word ptr [rsp+0A8h+pvar], 0Bh
0x1800047d9  jnz     short loc_1800047E8
0x1800047db  cmp     word ptr [rsp+0A8h+pvar+8], 0FFFFh
0x1800047e1  jnz     short loc_1800047E8
0x1800047e3  mov     r12b, 1
0x1800047e6  jmp     short loc_1800047EB
0x1800047e8  xor     r12b, r12b
0x1800047eb  lea     r14, WPP_GLOBAL_Control
0x1800047f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047f9  cmp     rcx, r14
0x1800047fc  jz      short loc_180004833
0x1800047fe  test    byte ptr [rcx+1Ch], 1
0x180004802  jz      short loc_180004833
0x180004804  lea     rax, aNotPresent; "NOT Present"
0x18000480b  lea     r9, aIspresent; "IsPresent"
0x180004812  test    r12b, r12b
0x180004815  cmovz   r9, rax
0x180004819  mov     edx, 1Fh
0x18000481e  mov     qword ptr [rsp+0A8h+var_88], rsi
0x180004823  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x18000482a  mov     rcx, [rcx+10h]
0x18000482e  call    WPP_SF_SS
0x180004833  lea     r15, [r13+20h]
0x180004837  mov     qword ptr [rsp+0A8h+pclsid.Data1], r15
0x18000483c  mov     rcx, r15; SRWLock
0x18000483f  call    cs:__imp_AcquireSRWLockExclusive
0x180004845  nop
0x180004846  lea     rcx, [r13+58h]
0x18000484a  movzx   r8d, r12b
0x18000484e  mov     rdx, rsi
0x180004851  call    ?SetAt@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_NV?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@_N@2@@ATL@@QEAAPEAU__POSITION@@PEBG_N@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,bool,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<bool>>::SetAt(ushort const *,bool)
0x180004856  nop
0x180004857  jmp     short loc_18000486E
0x180004859  lea     r14, WPP_GLOBAL_Control
0x180004860  mov     rbx, [rsp+0A8h+var_70]
0x180004865  mov     edi, [rsp+0A8h+var_78]
0x180004869  mov     r15, qword ptr [rsp+0A8h+pclsid.Data1]
0x18000486e  mov     rcx, r15; SRWLock
0x180004871  call    cs:__imp_ReleaseSRWLockExclusive
0x180004877  jmp     short loc_180004880
0x180004879  lea     r14, WPP_GLOBAL_Control
0x180004880  lea     rcx, [rsp+0A8h+pvar]; pvar
0x180004885  call    cs:__imp_PropVariantClear
0x18000488b  jmp     short loc_1800048B5
0x18000488d  mov     rcx, [rsp+0A8h]; this
0x180004895  mov     edi, 8007000Eh
0x18000489a  mov     r9d, edi; char *
0x18000489d  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\Devices\\Setup\\Dsm\\"...
0x1800048a4  mov     edx, 18h; void *
0x1800048a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048ae  lea     r14, WPP_GLOBAL_Control
0x1800048b5  test    edi, edi
0x1800048b7  jns     short loc_1800048E4
0x1800048b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048c0  cmp     rcx, r14
0x1800048c3  jz      short loc_1800048E4
0x1800048c5  test    byte ptr [rcx+1Ch], 4
0x1800048c9  jz      short loc_1800048E4
0x1800048cb  mov     edx, 20h ; ' '
0x1800048d0  mov     r9d, edi
0x1800048d3  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x1800048da  mov     rcx, [rcx+10h]
0x1800048de  call    WPP_SF_d
0x1800048e3  nop
0x1800048e4  test    rbx, rbx
0x1800048e7  jz      short loc_1800048F2
0x1800048e9  mov     rcx, rbx; pv
0x1800048ec  call    cs:__imp_CoTaskMemFree
0x1800048f2  mov     rcx, [rsp+0A8h+var_38]
0x1800048f7  xor     rcx, rsp; StackCookie
0x1800048fa  call    __security_check_cookie
0x1800048ff  lea     r11, [rsp+0A8h+var_28]
0x180004907  mov     rbx, [r11+40h]
0x18000490b  mov     rsi, [r11+48h]
0x18000490f  mov     rsp, r11
0x180004912  pop     r15
0x180004914  pop     r14
0x180004916  pop     r13
0x180004918  pop     r12
0x18000491a  pop     rdi
0x18000491b  retn
```
