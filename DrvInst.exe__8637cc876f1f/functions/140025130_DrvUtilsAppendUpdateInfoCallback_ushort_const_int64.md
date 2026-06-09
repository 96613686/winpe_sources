# DrvUtilsAppendUpdateInfoCallback(ushort const *,__int64)

- ea: `0x140025130`
- end: `0x14002550c`
- name: `?DrvUtilsAppendUpdateInfoCallback@@YAHPEBG_J@Z`
- size: `988`
- prototype: `_BOOL8 __fastcall(WCHAR *FileTitle, _QWORD *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x140024e0c`
- `0x1400266c8`

## callees

- `0x1400070bc`
- `0x14000bcbc`
- `0x14000c354`
- `0x140010918`
- `0x140025130`
- `0x140025514`
- `0x1400256d4`
- `0x140025828`
- `0x140026424`
- `0x14002649c`
- `0x140026994`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400251ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400251ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025393`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400251be`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400251be`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1400251a5`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1400251a5`
- `drvstore!DriverPackageClose` at `0x1400254c9`
- `drvstore!DriverPackageClose` at `0x1400254c9`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140025453`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140025453`
- `drvstore!DriverStoreFindW` at `0x140025247`
- `drvstore!DriverStoreFindW` at `0x140025247`

## pseudocode

```c
_BOOL8 __fastcall DrvUtilsAppendUpdateInfoCallback(WCHAR *FileTitle, _QWORD *a2)
{
  DWORD LastError; // ebx
  _QWORD *v5; // rdi
  __int64 v6; // r8
  int v7; // eax
  unsigned __int16 *v8; // r13
  struct HDRIVERPACKAGE__ *v9; // rax
  __int64 v10; // r8
  struct HDRIVERPACKAGE__ *v11; // r15
  unsigned int v12; // r14d
  _QWORD *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // r8
  _QWORD *v16; // r9
  size_t v18; // [rsp+20h] [rbp-E0h]
  _DWORD v19[3]; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v20[172]; // [rsp+60h] [rbp-A0h] BYREF
  char v21; // [rsp+10Ch] [rbp+Ch] BYREF
  unsigned __int16 v22[264]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR Buffer[264]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v24[264]; // [rsp+740h] [rbp+640h] BYREF

  v19[1] = 0;
  v19[2] = 0;
  v19[0] = 0;
  memset_0(v20, 0, 0x2B8u);
  if ( !GetFullPathNameW(FileTitle, 0x104u, Buffer, 0) )
  {
    LastError = 87;
    goto LABEL_60;
  }
  if ( GetFileAttributesW(Buffer) == -1 && GetLastError() - 2 <= 1 )
  {
    v5 = a2 + 1;
    if ( *(_DWORD *)(a2[1] + 68LL) == 1 )
    {
      LastError = 2;
      goto LABEL_60;
    }
    v6 = *v5;
    v7 = 1;
    goto LABEL_11;
  }
  v5 = a2 + 1;
  v6 = a2[1];
  if ( *(_DWORD *)(v6 + 68) != 1 )
  {
    FileTitle = Buffer;
    v7 = 0;
LABEL_11:
    if ( !(unsigned int)DriverStoreFindW(*a2, FileTitle, *(unsigned __int16 *)(v6 + 72), 0, v7, v22, 260, v20) )
    {
LABEL_12:
      LastError = GetLastError();
      goto LABEL_60;
    }
    if ( *(_DWORD *)(*v5 + 68LL) == 3 )
    {
      FileTitle = v22;
    }
    else if ( *(_DWORD *)(*v5 + 68LL) == 4 )
    {
      if ( StringCchCopyW(v24, 0x104u, v22) < 0 || !(unsigned int)pSetupTrimFileTitle(v24) )
        goto LABEL_59;
      FileTitle = (WCHAR *)pSetupGetFileTitle(v24);
    }
    else
    {
      FileTitle = (WCHAR *)&v21;
    }
    v8 = v22;
    goto LABEL_21;
  }
  v8 = FileTitle;
LABEL_21:
  if ( !FileTitle || !*FileTitle )
  {
LABEL_59:
    LastError = 13;
    goto LABEL_60;
  }
  v9 = DrvUtilsDriverPackageOpen(v8, *(_WORD *)(*v5 + 72LL));
  v10 = *v5;
  v11 = v9;
  if ( v9 )
  {
    LastError = DrvUtilsGetDriverPackageInfo(v9, v8, *(unsigned __int16 *)(v10 + 72), 0, v19);
    if ( LastError )
      goto LABEL_58;
  }
  else
  {
    if ( (*(_BYTE *)(v10 + 4) & 1) == 0 || *(_DWORD *)(v10 + 68) == 1 )
      goto LABEL_12;
    LastError = DrvUtilsGetDriverPackageInfoFromCache(
                  (struct HDRIVERSTORE__ *)*a2,
                  v8,
                  (enum _DRVUTILS_DRIVER_TYPE_FLAG *)v19);
    if ( LastError )
      goto LABEL_60;
  }
  v12 = v19[0];
  if ( !v19[0] )
  {
    LastError = 15632;
    goto LABEL_51;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2>::GetImpl'::`2'::impl)
    && !pDrvUtilsDriverPackageAppliesToMachine((struct HDRIVERSTORE__ *)*a2, v11) )
  {
    v12 = 0x80000000;
  }
  if ( !(unsigned int)DrvUtilsInitializeUpdateTables(*v5, v12) )
  {
    LastError = GetLastError();
    goto LABEL_51;
  }
  v13 = (_QWORD *)*v5;
  switch ( v12 )
  {
    case 0x80000000:
      v14 = v13[7];
LABEL_38:
      LODWORD(v18) = 4;
      goto LABEL_39;
    case 1u:
      v14 = v13[1];
      goto LABEL_38;
    case 2u:
      v14 = v13[3];
      goto LABEL_38;
  }
  LODWORD(v18) = 4;
  if ( v12 == 4 )
    v14 = v13[5];
  else
    v14 = v13[6];
LABEL_39:
  if ( (unsigned int)pSetupStringTableAddStringEx(v14, v18) == -1 )
  {
    LastError = 14;
LABEL_51:
    if ( !v11 )
      goto LABEL_60;
LABEL_58:
    DriverPackageClose(v11);
    goto LABEL_60;
  }
  if ( *(_DWORD *)(*v5 + 68LL) != 1 )
    DriverStoreGetObjectPropertyW(*a2, 2, v22, DEVPKEY_DriverPackage_PendingDriverUpdate);
  if ( v11 )
  {
    if ( v12 - 1 <= 1 )
    {
      v15 = *v5;
      v16 = (_QWORD *)(*v5 + 32LL);
      if ( v12 != 2 )
        v16 = (_QWORD *)(v15 + 16);
      LastError = DrvUtilsGetDriverPackageInfo(v11, v8, *(unsigned __int16 *)(v15 + 72), *v16, 0);
    }
    goto LABEL_58;
  }
LABEL_60:
  *((_DWORD *)a2 + 5) = LastError;
  return LastError == 0;
}

```

## disassembly

```asm
0x140025130  mov     [rsp-8+arg_10], rbx
0x140025135  push    rbp
0x140025136  push    rsi
0x140025137  push    rdi
0x140025138  push    r12
0x14002513a  push    r13
0x14002513c  push    r14
0x14002513e  push    r15
0x140025140  lea     rbp, [rsp-860h]
0x140025148  sub     rsp, 960h
0x14002514f  mov     rax, cs:__security_cookie
0x140025156  xor     rax, rsp
0x140025159  mov     [rbp+890h+var_40], rax
0x140025160  xor     r14d, r14d
0x140025163  mov     r12, rdx
0x140025166  mov     rsi, rcx
0x140025169  mov     [rsp+990h+var_938], r14d
0x14002516e  xor     edx, edx; Val
0x140025170  mov     [rsp+990h+var_934], r14d
0x140025175  lea     rcx, [rsp+990h+var_930]; void *
0x14002517a  mov     [rsp+990h+var_940], r14b
0x14002517f  mov     r8d, 2B8h; Size
0x140025185  mov     [rsp+990h+var_93C], r14d
0x14002518a  call    memset_0
0x14002518f  mov     r15d, 104h
0x140025195  lea     r8, [rbp+890h+Buffer]; lpBuffer
0x14002519c  mov     edx, r15d; nBufferLength
0x14002519f  xor     r9d, r9d; lpFilePart
0x1400251a2  mov     rcx, rsi; lpFileName
0x1400251a5  call    cs:__imp_GetFullPathNameW
0x1400251ab  test    eax, eax
0x1400251ad  jnz     short loc_1400251B7
0x1400251af  lea     ebx, [rax+57h]
0x1400251b2  jmp     loc_1400254D6
0x1400251b7  lea     rcx, [rbp+890h+Buffer]; lpFileName
0x1400251be  call    cs:__imp_GetFileAttributesW
0x1400251c4  mov     ebx, 1
0x1400251c9  cmp     eax, 0FFFFFFFFh
0x1400251cc  jnz     short loc_1400251F9
0x1400251ce  call    cs:__imp_GetLastError
0x1400251d4  add     eax, 0FFFFFFFEh
0x1400251d7  cmp     eax, ebx
0x1400251d9  ja      short loc_1400251F9
0x1400251db  lea     rdi, [r12+8]
0x1400251e0  mov     rax, [rdi]
0x1400251e3  cmp     [rax+44h], ebx
0x1400251e6  jz      short loc_1400251EF
0x1400251e8  mov     r8, [rdi]
0x1400251eb  mov     eax, ebx
0x1400251ed  jmp     short loc_140025219
0x1400251ef  mov     ebx, 2
0x1400251f4  jmp     loc_1400254D6
0x1400251f9  lea     rdi, [r12+8]
0x1400251fe  mov     r8, [rdi]
0x140025201  cmp     [r8+44h], ebx
0x140025205  jnz     short loc_14002520F
0x140025207  mov     r13, rsi
0x14002520a  jmp     loc_1400252C4
0x14002520f  lea     rsi, [rbp+890h+Buffer]
0x140025216  mov     eax, r14d
0x140025219  movzx   r8d, word ptr [r8+48h]
0x14002521e  lea     rcx, [rsp+990h+var_930]
0x140025223  mov     [rsp+990h+var_958], rcx
0x140025228  xor     r9d, r9d
0x14002522b  lea     rcx, [rbp+890h+var_670]
0x140025232  mov     [rsp+990h+var_960], r15d
0x140025237  mov     [rsp+990h+var_968], rcx
0x14002523c  mov     rdx, rsi
0x14002523f  mov     rcx, [r12]
0x140025243  mov     dword ptr [rsp+990h+var_970], eax
0x140025247  call    cs:__imp_DriverStoreFindW
0x14002524d  test    eax, eax
0x14002524f  jnz     short loc_14002525E
0x140025251  call    cs:__imp_GetLastError
0x140025257  mov     ebx, eax
0x140025259  jmp     loc_1400254D6
0x14002525e  mov     rax, [rdi]
0x140025261  cmp     dword ptr [rax+44h], 3
0x140025265  jnz     short loc_140025270
0x140025267  lea     rsi, [rbp+890h+var_670]
0x14002526e  jmp     short loc_1400252BD
0x140025270  cmp     dword ptr [rax+44h], 4
0x140025274  jnz     short loc_1400252B9
0x140025276  lea     r8, [rbp+890h+var_670]; unsigned __int16 *
0x14002527d  mov     rdx, r15; unsigned __int64
0x140025280  lea     rcx, [rbp+890h+var_250]; unsigned __int16 *
0x140025287  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002528c  test    eax, eax
0x14002528e  js      loc_1400254D1
0x140025294  lea     rcx, [rbp+890h+var_250]
0x14002529b  call    pSetupTrimFileTitle
0x1400252a0  test    eax, eax
0x1400252a2  jz      loc_1400254D1
0x1400252a8  lea     rcx, [rbp+890h+var_250]
0x1400252af  call    pSetupGetFileTitle
0x1400252b4  mov     rsi, rax
0x1400252b7  jmp     short loc_1400252BD
0x1400252b9  lea     rsi, [rbp+890h+var_884]
0x1400252bd  lea     r13, [rbp+890h+var_670]
0x1400252c4  test    rsi, rsi
0x1400252c7  jz      loc_1400254D1
0x1400252cd  cmp     [rsi], r14w
0x1400252d1  jz      loc_1400254D1
0x1400252d7  mov     rdx, [rdi]
0x1400252da  mov     rcx, r13; unsigned __int16 *
0x1400252dd  movzx   edx, word ptr [rdx+48h]; unsigned __int16
0x1400252e1  call    ?DrvUtilsDriverPackageOpen@@YAPEAUHDRIVERPACKAGE__@@PEBGG@Z; DrvUtilsDriverPackageOpen(ushort const *,ushort)
0x1400252e6  mov     r8, [rdi]
0x1400252e9  mov     r15, rax
0x1400252ec  test    rax, rax
0x1400252ef  jnz     short loc_140025322
0x1400252f1  test    [r8+4], bl
0x1400252f5  jz      loc_140025251
0x1400252fb  cmp     [r8+44h], ebx
0x1400252ff  jz      loc_140025251
0x140025305  mov     rcx, [r12]; struct HDRIVERSTORE__ *
0x140025309  lea     r8, [rsp+990h+var_93C]; enum _DRVUTILS_DRIVER_TYPE_FLAG *
0x14002530e  mov     rdx, r13; unsigned __int16 *
0x140025311  call    ?DrvUtilsGetDriverPackageInfoFromCache@@YAKPEAUHDRIVERSTORE__@@PEBGPEAW4_DRVUTILS_DRIVER_TYPE_FLAG@@@Z; DrvUtilsGetDriverPackageInfoFromCache(HDRIVERSTORE__ *,ushort const *,_DRVUTILS_DRIVER_TYPE_FLAG *)
0x140025316  mov     ebx, eax
0x140025318  test    eax, eax
0x14002531a  jnz     loc_1400254D6
0x140025320  jmp     short loc_140025349
0x140025322  movzx   r8d, word ptr [r8+48h]
0x140025327  lea     rax, [rsp+990h+var_93C]
0x14002532c  xor     r9d, r9d
0x14002532f  mov     [rsp+990h+var_970], rax
0x140025334  mov     rdx, r13
0x140025337  mov     rcx, r15
0x14002533a  call    DrvUtilsGetDriverPackageInfo
0x14002533f  mov     ebx, eax
0x140025341  test    eax, eax
0x140025343  jnz     loc_1400254C6
0x140025349  mov     r14d, [rsp+990h+var_93C]
0x14002534e  test    r14d, r14d
0x140025351  jnz     short loc_14002535D
0x140025353  mov     ebx, 3D10h
0x140025358  jmp     loc_140025483
0x14002535d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2> `wil::Feature<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2>::GetImpl(void)'::`2'::impl
0x140025364  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2>::__private_IsEnabled(void)
0x140025369  test    al, al
0x14002536b  jz      short loc_140025384
0x14002536d  mov     rcx, [r12]; struct HDRIVERSTORE__ *
0x140025371  mov     rdx, r15; struct HDRIVERPACKAGE__ *
0x140025374  call    ?pDrvUtilsDriverPackageAppliesToMachine@@YAHPEAUHDRIVERSTORE__@@PEAUHDRIVERPACKAGE__@@@Z; pDrvUtilsDriverPackageAppliesToMachine(HDRIVERSTORE__ *,HDRIVERPACKAGE__ *)
0x140025379  test    eax, eax
0x14002537b  mov     eax, 80000000h
0x140025380  cmovz   r14d, eax
0x140025384  mov     rcx, [rdi]
0x140025387  mov     edx, r14d
0x14002538a  call    ?DrvUtilsInitializeUpdateTables@@YAHPEAU_DRVUTILS_UPDATE_INFO@@W4_DRVUTILS_DRIVER_TYPE_FLAG@@@Z; DrvUtilsInitializeUpdateTables(_DRVUTILS_UPDATE_INFO *,_DRVUTILS_DRIVER_TYPE_FLAG)
0x14002538f  test    eax, eax
0x140025391  jnz     short loc_1400253A0
0x140025393  call    cs:__imp_GetLastError
0x140025399  mov     ebx, eax
0x14002539b  jmp     loc_140025483
0x1400253a0  mov     rcx, [rdi]
0x1400253a3  lea     r9, [r12+10h]
0x1400253a8  cmp     r14d, 80000000h
0x1400253af  jnz     short loc_1400253D2
0x1400253b1  mov     rcx, [rcx+38h]; int
0x1400253b5  mov     rdx, rsi
0x1400253b8  mov     dword ptr [rsp+990h+var_970], 4; size_t
0x1400253c0  call    pSetupStringTableAddStringEx
0x1400253c5  cmp     eax, 0FFFFFFFFh
0x1400253c8  jnz     short loc_140025407
0x1400253ca  lea     ebx, [rax+0Fh]
0x1400253cd  jmp     loc_140025483
0x1400253d2  cmp     r14d, 1
0x1400253d6  jnz     short loc_1400253DE
0x1400253d8  mov     rcx, [rcx+8]
0x1400253dc  jmp     short loc_1400253B5
0x1400253de  mov     rdx, rsi
0x1400253e1  cmp     r14d, 2
0x1400253e5  jnz     short loc_1400253ED
0x1400253e7  mov     rcx, [rcx+18h]
0x1400253eb  jmp     short loc_1400253B8
0x1400253ed  mov     eax, 4
0x1400253f2  mov     dword ptr [rsp+990h+var_970], eax
0x1400253f6  cmp     r14d, eax
0x1400253f9  jnz     short loc_140025401
0x1400253fb  mov     rcx, [rcx+28h]
0x1400253ff  jmp     short loc_1400253C0
0x140025401  mov     rcx, [rcx+30h]
0x140025405  jmp     short loc_1400253C0
0x140025407  mov     rax, [rdi]
0x14002540a  mov     esi, 1
0x14002540f  cmp     [rax+44h], esi
0x140025412  jz      short loc_140025472
0x140025414  mov     rcx, [r12]
0x140025418  lea     rax, [rsp+990h+var_934]
0x14002541d  mov     [rsp+990h+var_950], 0
0x140025425  lea     r9, DEVPKEY_DriverPackage_PendingDriverUpdate
0x14002542c  mov     [rsp+990h+var_958], rax
0x140025431  lea     r8, [rbp+890h+var_670]
0x140025438  lea     rax, [rsp+990h+var_940]
0x14002543d  mov     [rsp+990h+var_960], esi
0x140025441  mov     [rsp+990h+var_968], rax
0x140025446  lea     edx, [rsi+1]
0x140025449  lea     rax, [rsp+990h+var_938]
0x14002544e  mov     [rsp+990h+var_970], rax
0x140025453  call    cs:__imp_DriverStoreGetObjectPropertyW
0x140025459  test    eax, eax
0x14002545b  jz      short loc_14002546A
0x14002545d  cmp     [rsp+990h+var_938], 11h
0x140025462  jnz     short loc_14002546A
0x140025464  cmp     [rsp+990h+var_934], esi
0x140025468  jz      short loc_140025472
0x14002546a  xor     al, al
0x14002546c  mov     [rsp+990h+var_940], al
0x140025470  jmp     short loc_140025476
0x140025472  mov     al, [rsp+990h+var_940]
0x140025476  test    al, al
0x140025478  jz      short loc_14002548A
0x14002547a  mov     rax, [rdi]
0x14002547d  test    byte ptr [rax+4], 2
0x140025481  jnz     short loc_14002548A
0x140025483  test    r15, r15
0x140025486  jz      short loc_1400254D6
0x140025488  jmp     short loc_1400254C6
0x14002548a  test    r15, r15
0x14002548d  jz      short loc_1400254D6
0x14002548f  lea     eax, [r14-1]
0x140025493  cmp     eax, esi
0x140025495  ja      short loc_1400254C6
0x140025497  mov     r8, [rdi]
0x14002549a  lea     r9, [r8+20h]
0x14002549e  cmp     r14d, 2
0x1400254a2  jz      short loc_1400254A8
0x1400254a4  lea     r9, [r8+10h]
0x1400254a8  mov     r9, [r9]
0x1400254ab  mov     rdx, r13
0x1400254ae  movzx   r8d, word ptr [r8+48h]
0x1400254b3  mov     rcx, r15
0x1400254b6  mov     [rsp+990h+var_970], 0
0x1400254bf  call    DrvUtilsGetDriverPackageInfo
0x1400254c4  mov     ebx, eax
0x1400254c6  mov     rcx, r15
0x1400254c9  call    cs:__imp_DriverPackageClose
0x1400254cf  jmp     short loc_1400254D6
0x1400254d1  mov     ebx, 0Dh
0x1400254d6  xor     eax, eax
0x1400254d8  mov     [r12+14h], ebx
0x1400254dd  test    ebx, ebx
0x1400254df  setz    al
0x1400254e2  mov     rcx, [rbp+890h+var_40]
0x1400254e9  xor     rcx, rsp; StackCookie
0x1400254ec  call    __security_check_cookie
0x1400254f1  mov     rbx, [rsp+990h+arg_10]
0x1400254f9  add     rsp, 960h
0x140025500  pop     r15
0x140025502  pop     r14
0x140025504  pop     r13
0x140025506  pop     r12
0x140025508  pop     rdi
0x140025509  pop     rsi
0x14002550a  pop     rbp
0x14002550b  retn
```
