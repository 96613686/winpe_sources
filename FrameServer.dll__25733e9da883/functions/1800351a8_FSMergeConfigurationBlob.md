# FSMergeConfigurationBlob

- ea: `0x1800351a8`
- end: `0x18003569b`
- name: `FSMergeConfigurationBlob`
- size: `1267`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007e94c`

## callees

- `0x180008cf0`
- `0x180009608`
- `0x180009cc0`
- `0x18000a460`
- `0x18000ad10`
- `0x18001c84c`
- `0x18002da54`
- `0x18002dbc4`
- `0x18002dbf8`
- `0x1800351a8`
- `0x1800367b0`
- `0x180039968`
- `0x1800e924c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800354f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800355e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800354f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800355e2`

## pseudocode

```c
__int64 __fastcall FSMergeConfigurationBlob(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        unsigned int *a6)
{
  char *v6; // r14
  __int64 v8; // rax
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  unsigned int *v14; // r13
  unsigned int v15; // edi
  int v16; // eax
  __int64 v17; // rax
  unsigned int v18; // esi
  int v19; // eax
  __int64 v20; // rdx
  __int64 unique_cotaskmem; // rax
  __int64 v22; // r8
  void *v23; // rcx
  unsigned int v24; // r12d
  unsigned int v25; // esi
  __int64 v26; // r15
  unsigned int v27; // ecx
  __int64 v28; // rdx
  _QWORD *v29; // rcx
  char *v30; // rax
  struct IFSConfigurationEntry *v32; // [rsp+40h] [rbp-30h] BYREF
  void *Src; // [rsp+48h] [rbp-28h] BYREF
  __int64 v34; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v35; // [rsp+58h] [rbp-18h]
  __int64 v36; // [rsp+5Ch] [rbp-14h]
  LPVOID pv; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v38; // [rsp+C0h] [rbp+50h]

  v38 = a3;
  v6 = 0;
  v34 = 0;
  Src = 0;
  v8 = a3;
  v36 = 0;
  v35 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    WPP_SF_qDqd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      363,
      &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
      a1,
      a2,
      a3,
      a4);
    v8 = v38;
  }
  if ( !a1 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( g_wppLevels )
    {
      v13 = 364;
      goto LABEL_74;
    }
    goto LABEL_75;
  }
  if ( !a2 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( g_wppLevels )
    {
      v13 = 365;
      goto LABEL_74;
    }
    goto LABEL_75;
  }
  if ( !v8 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( g_wppLevels )
    {
      v13 = 366;
      goto LABEL_74;
    }
    goto LABEL_75;
  }
  if ( !a4 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( g_wppLevels )
    {
      v13 = 367;
      goto LABEL_74;
    }
    goto LABEL_75;
  }
  if ( !a5 )
  {
    v11 = -2147467261;
    v12 = -2147467261;
    if ( g_wppLevels )
    {
      v13 = 368;
      goto LABEL_74;
    }
    goto LABEL_75;
  }
  v14 = a6;
  *a5 = 0;
  if ( !v14 )
  {
    v11 = -2147467261;
    v12 = -2147467261;
    if ( g_wppLevels )
    {
      v13 = 369;
      goto LABEL_74;
    }
    goto LABEL_75;
  }
  v15 = 0;
  *v14 = 0;
  do
  {
    LODWORD(pv) = 0;
    v32 = 0;
    v16 = FSConfigurationEntry::CreateInstance((unsigned __int8 *)(a1 + v15), a2 - v15, (unsigned int *)&pv, &v32);
    v12 = v16;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_38;
      v20 = 370;
      goto LABEL_37;
    }
    if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add(&v34, v32) )
    {
      v16 = -2147024882;
      v12 = -2147024882;
      if ( g_wppLevels )
      {
        v20 = 371;
        goto LABEL_37;
      }
LABEL_38:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v32);
      goto LABEL_75;
    }
    if ( v15 + (unsigned int)pv < v15 )
    {
      v16 = -2147024362;
      v12 = -2147024362;
      if ( g_wppLevels )
      {
        v20 = 372;
LABEL_37:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v16);
        goto LABEL_38;
      }
      goto LABEL_38;
    }
    v15 += (unsigned int)pv;
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v32);
  }
  while ( v15 < a2 );
  v17 = v38;
  v18 = 0;
  while ( 1 )
  {
    LODWORD(pv) = 0;
    v32 = 0;
    v16 = FSConfigurationEntry::CreateInstance((unsigned __int8 *)(v17 + v18), a4 - v18, (unsigned int *)&pv, &v32);
    v12 = v16;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_38;
      v20 = 373;
      goto LABEL_37;
    }
    if ( (unsigned int)FSFindConfigurationEntryInArrayInternal(&v34, v32) == -1 )
    {
      if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add(&v34, v32) )
      {
        v16 = -2147024882;
        v12 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_38;
        v20 = 374;
        goto LABEL_37;
      }
      v19 = (int)pv;
      if ( (unsigned int)pv + v15 < v15 )
      {
        v16 = -2147024362;
        v12 = -2147024362;
        if ( !g_wppLevels )
          goto LABEL_38;
        v20 = 375;
        goto LABEL_37;
      }
      v15 += (unsigned int)pv;
    }
    else
    {
      v19 = (int)pv;
    }
    if ( v19 + v18 < v18 )
    {
      v16 = -2147024362;
      v12 = -2147024362;
      if ( !g_wppLevels )
        goto LABEL_38;
      v20 = 376;
      goto LABEL_37;
    }
    v18 += v19;
    v12 = 0;
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v32);
    if ( v18 >= a4 )
      break;
    v17 = v38;
  }
  unique_cotaskmem = wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(&pv, v15);
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    &Src,
    unique_cotaskmem);
  v23 = pv;
  pv = 0;
  if ( v23 )
    CoTaskMemFree(v23);
  v6 = (char *)Src;
  if ( Src )
  {
    v24 = v35;
    v25 = 0;
    v26 = 0;
    if ( !v35 )
    {
LABEL_63:
      v29 = a5;
      v30 = v6;
      v6 = 0;
      *v14 = v15;
      *v29 = v30;
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_Ddq(*((_QWORD *)WPP_GLOBAL_Control + 27), 382, v22, 0, v15, v30);
      goto LABEL_65;
    }
    while ( 1 )
    {
      Src = 0;
      LODWORD(pv) = 0;
      v11 = (*(__int64 (__fastcall **)(_QWORD, void **, LPVOID *))(**(_QWORD **)(v34 + 8 * v26) + 48LL))(
              *(_QWORD *)(v34 + 8 * v26),
              &Src,
              &pv);
      v12 = v11;
      if ( v11 < 0 )
        break;
      v27 = (_DWORD)pv + v25;
      if ( (unsigned int)pv + v25 < (unsigned int)pv )
      {
        v11 = -2147024362;
        v12 = -2147024362;
        if ( !g_wppLevels )
          goto LABEL_75;
        v13 = 379;
        goto LABEL_74;
      }
      v28 = v25;
      v25 += (unsigned int)pv;
      if ( v27 > v15 )
      {
        v12 = -1072860816;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            380,
            &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
            0,
            -1072860816);
        goto LABEL_75;
      }
      v12 = 0;
      memcpy_0(&v6[v28], Src, (unsigned int)pv);
      v26 = (unsigned int)(v26 + 1);
      if ( (unsigned int)v26 >= v24 )
        goto LABEL_63;
    }
    if ( !g_wppLevels )
      goto LABEL_75;
    v13 = 378;
  }
  else
  {
    v11 = -2147024882;
    v12 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_75;
    v13 = 377;
  }
LABEL_74:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v11);
LABEL_75:
  if ( byte_18010EC4D )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 381, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, v12);
LABEL_65:
  if ( v6 )
    CoTaskMemFree(v6);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(&v34);
  return v12;
}

```

## disassembly

```asm
0x1800351a8  mov     r11, rsp
0x1800351ab  mov     [r11+10h], rbx
0x1800351af  mov     [r11+18h], r8
0x1800351b3  push    rbp
0x1800351b4  push    rsi
0x1800351b5  push    rdi
0x1800351b6  push    r12
0x1800351b8  push    r13
0x1800351ba  push    r14
0x1800351bc  push    r15
0x1800351be  mov     rbp, rsp
0x1800351c1  sub     rsp, 70h
0x1800351c5  xor     r14d, r14d
0x1800351c8  mov     [rbp+var_20], 0
0x1800351d0  mov     [rbp+Src], r14
0x1800351d4  mov     r15d, r9d
0x1800351d7  mov     rax, r8
0x1800351da  mov     [rbp+var_14], 0
0x1800351e2  mov     esi, edx
0x1800351e4  mov     [rbp+var_18], 0
0x1800351eb  mov     r12, rcx
0x1800351ee  cmp     cs:byte_18010EC4D, 8
0x1800351f5  jb      short loc_180035229
0x1800351f7  mov     [r11-78h], r9d
0x1800351fb  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180035202  mov     r9, rcx
0x180035205  mov     [r11-80h], rax
0x180035209  mov     rcx, cs:WPP_GLOBAL_Control
0x180035210  mov     edx, 16Bh
0x180035215  mov     [rsp+70h+var_50], esi
0x180035219  mov     rcx, [rcx+0D8h]
0x180035220  call    WPP_SF_qDqd
0x180035225  mov     rax, [rbp+arg_10]
0x180035229  test    r12, r12
0x18003522c  jnz     short loc_18003524C
0x18003522e  mov     eax, 80070057h
0x180035233  mov     ebx, eax
0x180035235  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003523c  jb      loc_180035667
0x180035242  mov     edx, 16Ch
0x180035247  jmp     loc_180035649
0x18003524c  test    esi, esi
0x18003524e  jnz     short loc_18003526E
0x180035250  mov     eax, 80070057h
0x180035255  mov     ebx, eax
0x180035257  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003525e  jb      loc_180035667
0x180035264  mov     edx, 16Dh
0x180035269  jmp     loc_180035649
0x18003526e  test    rax, rax
0x180035271  jnz     short loc_180035291
0x180035273  mov     eax, 80070057h
0x180035278  mov     ebx, eax
0x18003527a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180035281  jb      loc_180035667
0x180035287  mov     edx, 16Eh
0x18003528c  jmp     loc_180035649
0x180035291  test    r15d, r15d
0x180035294  jnz     short loc_1800352B4
0x180035296  mov     eax, 80070057h
0x18003529b  mov     ebx, eax
0x18003529d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800352a4  jb      loc_180035667
0x1800352aa  mov     edx, 16Fh
0x1800352af  jmp     loc_180035649
0x1800352b4  mov     rcx, [rbp+arg_20]
0x1800352b8  test    rcx, rcx
0x1800352bb  jnz     short loc_1800352DB
0x1800352bd  mov     eax, 80004003h
0x1800352c2  mov     ebx, eax
0x1800352c4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800352cb  jb      loc_180035667
0x1800352d1  mov     edx, 170h
0x1800352d6  jmp     loc_180035649
0x1800352db  mov     r13, [rbp+arg_28]
0x1800352df  mov     [rcx], r14
0x1800352e2  test    r13, r13
0x1800352e5  jnz     short loc_180035305
0x1800352e7  mov     eax, 80004003h
0x1800352ec  mov     ebx, eax
0x1800352ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800352f5  jb      loc_180035667
0x1800352fb  mov     edx, 171h
0x180035300  jmp     loc_180035649
0x180035305  xor     ebx, ebx
0x180035307  xor     edi, edi
0x180035309  mov     [r13+0], ebx
0x18003530d  test    esi, esi
0x18003530f  jz      short loc_180035370
0x180035311  mov     edx, esi
0x180035313  mov     ecx, edi
0x180035315  sub     edx, edi; unsigned int
0x180035317  mov     dword ptr [rbp+pv], r14d
0x18003531b  add     rcx, r12; unsigned __int8 *
0x18003531e  mov     [rbp+var_30], r14
0x180035322  lea     r9, [rbp+var_30]; struct IFSConfigurationEntry **
0x180035326  lea     r8, [rbp+pv]; unsigned int *
0x18003532a  call    ?CreateInstance@FSConfigurationEntry@@SAJPEAEKPEAKPEAPEAUIFSConfigurationEntry@@@Z; FSConfigurationEntry::CreateInstance(uchar *,ulong,ulong *,IFSConfigurationEntry * *)
0x18003532f  mov     ebx, eax
0x180035331  test    eax, eax
0x180035333  js      loc_180035439
0x180035339  mov     rdx, [rbp+var_30]
0x18003533d  lea     rcx, [rbp+var_20]
0x180035341  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x180035346  test    eax, eax
0x180035348  jz      loc_1800353F8
0x18003534e  mov     ecx, dword ptr [rbp+pv]
0x180035351  add     ecx, edi
0x180035353  cmp     ecx, edi
0x180035355  jb      loc_1800353E1
0x18003535b  mov     edi, ecx
0x18003535d  xor     ebx, ebx
0x18003535f  lea     rcx, [rbp+var_30]; void *
0x180035363  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180035368  cmp     edi, esi
0x18003536a  jb      short loc_180035311
0x18003536c  mov     rax, [rbp+arg_10]
0x180035370  xor     esi, esi
0x180035372  test    r15d, r15d
0x180035375  jz      loc_1800354D4
0x18003537b  mov     edx, r15d
0x18003537e  mov     ecx, esi
0x180035380  sub     edx, esi; unsigned int
0x180035382  mov     dword ptr [rbp+pv], r14d
0x180035386  add     rcx, rax; unsigned __int8 *
0x180035389  mov     [rbp+var_30], r14
0x18003538d  lea     r9, [rbp+var_30]; struct IFSConfigurationEntry **
0x180035391  lea     r8, [rbp+pv]; unsigned int *
0x180035395  call    ?CreateInstance@FSConfigurationEntry@@SAJPEAEKPEAKPEAPEAUIFSConfigurationEntry@@@Z; FSConfigurationEntry::CreateInstance(uchar *,ulong,ulong *,IFSConfigurationEntry * *)
0x18003539a  mov     ebx, eax
0x18003539c  test    eax, eax
0x18003539e  js      loc_1800354BD
0x1800353a4  mov     rdx, [rbp+var_30]
0x1800353a8  lea     rcx, [rbp+var_20]
0x1800353ac  call    ?FSFindConfigurationEntryInArrayInternal@@YAKAEAV?$CTUnkArray@UIFSConfigurationEntry@@@@PEAUIFSConfigurationEntry@@@Z; FSFindConfigurationEntryInArrayInternal(CTUnkArray<IFSConfigurationEntry> &,IFSConfigurationEntry *)
0x1800353b1  cmp     eax, 0FFFFFFFFh
0x1800353b4  jnz     loc_180035449
0x1800353ba  mov     rdx, [rbp+var_30]
0x1800353be  lea     rcx, [rbp+var_20]
0x1800353c2  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x1800353c7  test    eax, eax
0x1800353c9  jz      loc_180035485
0x1800353cf  mov     eax, dword ptr [rbp+pv]
0x1800353d2  lea     ecx, [rax+rdi]
0x1800353d5  cmp     ecx, edi
0x1800353d7  jb      loc_18003546E
0x1800353dd  mov     edi, ecx
0x1800353df  jmp     short loc_18003544C
0x1800353e1  mov     eax, 80070216h
0x1800353e6  mov     ebx, eax
0x1800353e8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800353ef  jb      short loc_18003542B
0x1800353f1  mov     edx, 174h
0x1800353f6  jmp     short loc_18003540D
0x1800353f8  mov     eax, 8007000Eh
0x1800353fd  mov     ebx, eax
0x1800353ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180035406  jb      short loc_18003542B
0x180035408  mov     edx, 173h
0x18003540d  mov     rcx, cs:WPP_GLOBAL_Control
0x180035414  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003541b  xor     r9d, r9d
0x18003541e  mov     [rsp+70h+var_50], eax
0x180035422  mov     rcx, [rcx+10h]
0x180035426  call    WPP_SF_qD
0x18003542b  lea     rcx, [rbp+var_30]; void *
0x18003542f  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180035434  jmp     loc_180035667
0x180035439  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180035440  jb      short loc_18003542B
0x180035442  mov     edx, 172h
0x180035447  jmp     short loc_18003540D
0x180035449  mov     eax, dword ptr [rbp+pv]
0x18003544c  lea     ecx, [rax+rsi]
0x18003544f  cmp     ecx, esi
0x180035451  jb      short loc_18003549F
0x180035453  mov     esi, ecx
0x180035455  xor     ebx, ebx
0x180035457  lea     rcx, [rbp+var_30]; void *
0x18003545b  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180035460  cmp     esi, r15d
0x180035463  jnb     short loc_1800354D4
0x180035465  mov     rax, [rbp+arg_10]
0x180035469  jmp     loc_18003537B
0x18003546e  mov     eax, 80070216h
0x180035473  mov     ebx, eax
0x180035475  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003547c  jb      short loc_18003542B
0x18003547e  mov     edx, 177h
0x180035483  jmp     short loc_18003540D
0x180035485  mov     eax, 8007000Eh
0x18003548a  mov     ebx, eax
0x18003548c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180035493  jb      short loc_18003542B
0x180035495  mov     edx, 176h
0x18003549a  jmp     loc_18003540D
0x18003549f  mov     eax, 80070216h
0x1800354a4  mov     ebx, eax
0x1800354a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800354ad  jb      loc_18003542B
0x1800354b3  mov     edx, 178h
0x1800354b8  jmp     loc_18003540D
0x1800354bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800354c4  jb      loc_18003542B
0x1800354ca  mov     edx, 175h
0x1800354cf  jmp     loc_18003540D
0x1800354d4  mov     edx, edi
0x1800354d6  lea     rcx, [rbp+pv]
0x1800354da  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x1800354df  mov     rdx, rax
0x1800354e2  lea     rcx, [rbp+Src]
0x1800354e6  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x1800354eb  mov     rcx, [rbp+pv]; pv
0x1800354ef  mov     [rbp+pv], r14
0x1800354f3  test    rcx, rcx
0x1800354f6  jz      short loc_1800354FE
0x1800354f8  call    cs:__imp_CoTaskMemFree
0x1800354fe  mov     r14, [rbp+Src]
0x180035502  test    r14, r14
0x180035505  jnz     short loc_180035525
0x180035507  mov     eax, 8007000Eh
0x18003550c  mov     ebx, eax
0x18003550e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180035515  jb      loc_180035667
0x18003551b  mov     edx, 179h
0x180035520  jmp     loc_180035649
0x180035525  mov     r12d, [rbp+var_18]
0x180035529  xor     esi, esi
0x18003552b  xor     r15d, r15d
0x18003552e  test    r12d, r12d
0x180035531  jz      short loc_18003559C
0x180035533  mov     rax, [rbp+var_20]
0x180035537  lea     r8, [rbp+pv]
0x18003553b  mov     [rbp+Src], 0
0x180035543  lea     rdx, [rbp+Src]
0x180035547  mov     dword ptr [rbp+pv], 0
0x18003554e  mov     rcx, [rax+r15*8]
0x180035552  mov     rax, [rcx]
0x180035555  mov     rax, [rax+30h]
0x180035559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003555e  mov     ebx, eax
0x180035560  test    eax, eax
0x180035562  js      loc_18003563B
0x180035568  mov     eax, dword ptr [rbp+pv]
0x18003556b  lea     ecx, [rax+rsi]
0x18003556e  cmp     ecx, eax
0x180035570  jb      loc_180035624
0x180035576  mov     edx, esi
0x180035578  mov     esi, ecx
0x18003557a  cmp     ecx, edi
0x18003557c  ja      loc_18003560B
0x180035582  lea     rcx, [r14+rdx]; void *
0x180035586  mov     r8d, eax; Size
0x180035589  mov     rdx, [rbp+Src]; Src
0x18003558d  xor     ebx, ebx
0x18003558f  call    memcpy_0
0x180035594  inc     r15d
0x180035597  cmp     r15d, r12d
0x18003559a  jb      short loc_180035533
0x18003559c  mov     rcx, [rbp+arg_20]
0x1800355a0  mov     rax, r14
0x1800355a3  xor     r14d, r14d
0x1800355a6  mov     [r13+0], edi
0x1800355aa  mov     [rcx], rax
0x1800355ad  cmp     cs:byte_18010EC4D, 8
0x1800355b4  jb      short loc_1800355DA
0x1800355b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800355bd  mov     edx, 17Eh
0x1800355c2  mov     [rsp+70h+var_48], rax
0x1800355c7  mov     r9d, ebx
0x1800355ca  mov     [rsp+70h+var_50], edi
0x1800355ce  mov     rcx, [rcx+0D8h]
0x1800355d5  call    WPP_SF_Ddq
0x1800355da  test    r14, r14
0x1800355dd  jz      short loc_1800355E8
0x1800355df  mov     rcx, r14; pv
0x1800355e2  call    cs:__imp_CoTaskMemFree
0x1800355e8  lea     rcx, [rbp+var_20]; void *
0x1800355ec  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800355f1  mov     eax, ebx
0x1800355f3  mov     rbx, [rsp+70h+arg_8]
0x1800355fb  add     rsp, 70h
0x1800355ff  pop     r15
0x180035601  pop     r14
0x180035603  pop     r13
0x180035605  pop     r12
0x180035607  pop     rdi
0x180035608  pop     rsi
0x180035609  pop     rbp
0x18003560a  retn
0x18003560b  mov     ebx, 0C00D7170h
0x180035610  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180035617  jb      short loc_180035667
0x180035619  mov     edx, 17Ch
0x18003561e  mov     [rsp+70h+var_50], ebx
0x180035622  jmp     short loc_18003564D
0x180035624  mov     eax, 80070216h
0x180035629  mov     ebx, eax
0x18003562b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180035632  jb      short loc_180035667
  ... truncated ...
```
