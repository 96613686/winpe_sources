# DrvUtilsAppendUpdateInfoCallback(ushort const *,__int64)

- ea: `0x18003cd90`
- end: `0x18003d158`
- name: `?DrvUtilsAppendUpdateInfoCallback@@YAHPEBG_J@Z`
- size: `968`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x18003de08`
- `0x18003e41c`

## callees

- `0x180007720`
- `0x18001af70`
- `0x18001ba48`
- `0x18003cd90`
- `0x18003d160`
- `0x18003d288`
- `0x18003d3dc`
- `0x18003db68`
- `0x18003dbe0`
- `0x18003e094`
- `0x18003f734`
- `0x18003f80c`
- `0x180040220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ceaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ceaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cff1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003ce1e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003ce1e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003ce05`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003ce05`
- `drvstore!DriverPackageClose` at `0x18003d116`
- `drvstore!DriverPackageClose` at `0x18003d116`
- `drvstore!DriverStoreFindW` at `0x18003cea5`
- `drvstore!DriverStoreFindW` at `0x18003cea5`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x18003d0a0`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x18003d0a0`

## pseudocode

```c
_BOOL8 __fastcall DrvUtilsAppendUpdateInfoCallback(WCHAR *FileTitle, _QWORD *a2)
{
  DWORD LastError; // ebx
  _QWORD *v5; // rdi
  __int64 v6; // r8
  int v7; // eax
  unsigned __int16 *v8; // r12
  struct HDRIVERPACKAGE__ *v9; // rax
  __int64 v10; // r8
  struct HDRIVERPACKAGE__ *v11; // r15
  unsigned int v12; // r14d
  __int64 v13; // r8
  _QWORD *v14; // rcx
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rdx
  char v17; // al
  __int64 v18; // r8
  _QWORD *v19; // r9
  _BYTE v21[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v22; // [rsp+54h] [rbp-ACh] BYREF
  int v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+5Ch] [rbp-A4h] BYREF
  _BYTE v25[172]; // [rsp+60h] [rbp-A0h] BYREF
  char v26; // [rsp+10Ch] [rbp+Ch] BYREF
  unsigned __int16 v27[264]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR Buffer[264]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v29[264]; // [rsp+740h] [rbp+640h] BYREF

  v23 = 0;
  v24 = 0;
  v21[0] = 0;
  v22 = 0;
  memset_0(v25, 0, 0x2B8u);
  if ( GetFullPathNameW(FileTitle, 0x104u, Buffer, 0) )
  {
    if ( GetFileAttributesW(Buffer) == -1 && GetLastError() - 2 <= 1 )
    {
      v5 = a2 + 1;
      if ( *(_DWORD *)(a2[1] + 68LL) == 1 )
      {
        LastError = 2;
        goto LABEL_65;
      }
      v6 = *v5;
      v7 = 1;
    }
    else
    {
      v5 = a2 + 1;
      v6 = a2[1];
      if ( *(_DWORD *)(v6 + 68) == 1 )
      {
        v8 = FileTitle;
        goto LABEL_21;
      }
      FileTitle = Buffer;
      v7 = 0;
    }
    if ( !(unsigned int)DriverStoreFindW(*a2, FileTitle, *(unsigned __int16 *)(v6 + 72), 0, v7, v27, 260, v25) )
    {
LABEL_12:
      LastError = GetLastError();
      goto LABEL_65;
    }
    if ( *(_DWORD *)(*v5 + 68LL) == 3 )
    {
      FileTitle = v27;
    }
    else if ( *(_DWORD *)(*v5 + 68LL) == 4 )
    {
      if ( (int)StringCchCopyW(v29, 0x104u, v27) < 0 || !(unsigned int)pSetupTrimFileTitle(v29) )
        goto LABEL_64;
      FileTitle = (WCHAR *)pSetupGetFileTitle(v29);
    }
    else
    {
      FileTitle = (WCHAR *)&v26;
    }
    v8 = v27;
LABEL_21:
    if ( FileTitle && *FileTitle )
    {
      v9 = DrvUtilsDriverPackageOpen(v8, *(_WORD *)(*v5 + 72LL));
      v10 = *v5;
      v11 = v9;
      if ( v9 )
      {
        LastError = DrvUtilsGetDriverPackageInfo(v9, v8, *(unsigned __int16 *)(v10 + 72), 0, &v22);
        if ( LastError )
          goto LABEL_63;
      }
      else
      {
        if ( (*(_BYTE *)(v10 + 4) & 1) == 0 || *(_DWORD *)(v10 + 68) == 1 )
          goto LABEL_12;
        LastError = DrvUtilsGetDriverPackageInfoFromCache(
                      (struct HDRIVERSTORE__ *)*a2,
                      v8,
                      (enum _DRVUTILS_DRIVER_TYPE_FLAG *)&v22);
        if ( LastError )
          goto LABEL_65;
      }
      v12 = v22;
      if ( !v22 )
      {
        LastError = 15632;
        goto LABEL_56;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2>::GetImpl'::`2'::impl)
        && !pDrvUtilsDriverPackageAppliesToMachine((struct HDRIVERSTORE__ *)*a2, v11) )
      {
        v12 = 0x80000000;
      }
      if ( !(unsigned int)DrvUtilsInitializeUpdateTables(*v5, v12) )
      {
        LastError = GetLastError();
        goto LABEL_56;
      }
      v14 = (_QWORD *)*v5;
      if ( v12 == 0x80000000 )
      {
        v15 = v14[7];
      }
      else
      {
        if ( v12 != 1 )
        {
          v16 = FileTitle;
          if ( v12 == 2 )
          {
            v15 = v14[3];
          }
          else if ( v12 == 4 )
          {
            v15 = v14[5];
          }
          else
          {
            v15 = v14[6];
          }
LABEL_39:
          if ( (unsigned int)pSetupStringTableAddStringEx(v15, v16, v13, a2 + 2) == -1 )
          {
            LastError = 14;
          }
          else
          {
            if ( *(_DWORD *)(*v5 + 68LL) == 1
              || (unsigned int)DriverStoreGetObjectPropertyW(
                                 *a2,
                                 2,
                                 v27,
                                 DEVPKEY_DriverPackage_PendingDriverUpdate,
                                 &v23,
                                 v21,
                                 1,
                                 &v24,
                                 0)
              && v23 == 17
              && v24 == 1 )
            {
              v17 = v21[0];
            }
            else
            {
              v17 = 0;
              v21[0] = 0;
            }
            if ( !v17 || (*(_BYTE *)(*v5 + 4LL) & 2) != 0 )
            {
              if ( !v11 )
                goto LABEL_65;
              if ( v12 - 1 <= 1 )
              {
                v18 = *v5;
                v19 = (_QWORD *)(*v5 + 32LL);
                if ( v12 != 2 )
                  v19 = (_QWORD *)(v18 + 16);
                LastError = DrvUtilsGetDriverPackageInfo(v11, v8, *(unsigned __int16 *)(v18 + 72), *v19, 0);
              }
              goto LABEL_63;
            }
          }
LABEL_56:
          if ( !v11 )
            goto LABEL_65;
LABEL_63:
          DriverPackageClose(v11);
          goto LABEL_65;
        }
        v15 = v14[1];
      }
      v16 = FileTitle;
      goto LABEL_39;
    }
LABEL_64:
    LastError = 13;
    goto LABEL_65;
  }
  LastError = 87;
LABEL_65:
  *((_DWORD *)a2 + 5) = LastError;
  return LastError == 0;
}

```

## disassembly

```asm
0x18003cd90  mov     [rsp-8+arg_10], rbx
0x18003cd95  push    rbp
0x18003cd96  push    rsi
0x18003cd97  push    rdi
0x18003cd98  push    r12
0x18003cd9a  push    r13
0x18003cd9c  push    r14
0x18003cd9e  push    r15
0x18003cda0  lea     rbp, [rsp-860h]
0x18003cda8  sub     rsp, 960h
0x18003cdaf  mov     rax, cs:__security_cookie
0x18003cdb6  xor     rax, rsp
0x18003cdb9  mov     [rbp+890h+var_40], rax
0x18003cdc0  xor     r14d, r14d
0x18003cdc3  mov     r13, rdx
0x18003cdc6  mov     rsi, rcx
0x18003cdc9  mov     [rsp+990h+var_938], r14d
0x18003cdce  xor     edx, edx; Val
0x18003cdd0  mov     [rsp+990h+var_934], r14d
0x18003cdd5  lea     rcx, [rsp+990h+var_930]; void *
0x18003cdda  mov     [rsp+990h+var_940], r14b
0x18003cddf  mov     r8d, 2B8h; Size
0x18003cde5  mov     [rsp+990h+var_93C], r14d
0x18003cdea  call    memset_0
0x18003cdef  mov     r15d, 104h
0x18003cdf5  lea     r8, [rbp+890h+Buffer]; lpBuffer
0x18003cdfc  mov     edx, r15d; nBufferLength
0x18003cdff  xor     r9d, r9d; lpFilePart
0x18003ce02  mov     rcx, rsi; lpFileName
0x18003ce05  call    cs:__imp_GetFullPathNameW
0x18003ce0b  test    eax, eax
0x18003ce0d  jnz     short loc_18003CE17
0x18003ce0f  lea     ebx, [rax+57h]
0x18003ce12  jmp     loc_18003D123
0x18003ce17  lea     rcx, [rbp+890h+Buffer]; lpFileName
0x18003ce1e  call    cs:__imp_GetFileAttributesW
0x18003ce24  mov     ebx, 1
0x18003ce29  cmp     eax, 0FFFFFFFFh
0x18003ce2c  jnz     short loc_18003CE58
0x18003ce2e  call    cs:__imp_GetLastError
0x18003ce34  add     eax, 0FFFFFFFEh
0x18003ce37  cmp     eax, ebx
0x18003ce39  ja      short loc_18003CE58
0x18003ce3b  lea     rdi, [r13+8]
0x18003ce3f  mov     rax, [rdi]
0x18003ce42  cmp     [rax+44h], ebx
0x18003ce45  jz      short loc_18003CE4E
0x18003ce47  mov     r8, [rdi]
0x18003ce4a  mov     eax, ebx
0x18003ce4c  jmp     short loc_18003CE77
0x18003ce4e  mov     ebx, 2
0x18003ce53  jmp     loc_18003D123
0x18003ce58  lea     rdi, [r13+8]
0x18003ce5c  mov     r8, [rdi]
0x18003ce5f  cmp     [r8+44h], ebx
0x18003ce63  jnz     short loc_18003CE6D
0x18003ce65  mov     r12, rsi
0x18003ce68  jmp     loc_18003CF22
0x18003ce6d  lea     rsi, [rbp+890h+Buffer]
0x18003ce74  mov     eax, r14d
0x18003ce77  movzx   r8d, word ptr [r8+48h]
0x18003ce7c  lea     rcx, [rsp+990h+var_930]
0x18003ce81  mov     [rsp+990h+var_958], rcx
0x18003ce86  xor     r9d, r9d
0x18003ce89  lea     rcx, [rbp+890h+var_670]
0x18003ce90  mov     [rsp+990h+var_960], r15d
0x18003ce95  mov     [rsp+990h+var_968], rcx
0x18003ce9a  mov     rdx, rsi
0x18003ce9d  mov     rcx, [r13+0]
0x18003cea1  mov     dword ptr [rsp+990h+var_970], eax
0x18003cea5  call    cs:__imp_DriverStoreFindW
0x18003ceab  test    eax, eax
0x18003cead  jnz     short loc_18003CEBC
0x18003ceaf  call    cs:__imp_GetLastError
0x18003ceb5  mov     ebx, eax
0x18003ceb7  jmp     loc_18003D123
0x18003cebc  mov     rax, [rdi]
0x18003cebf  cmp     dword ptr [rax+44h], 3
0x18003cec3  jnz     short loc_18003CECE
0x18003cec5  lea     rsi, [rbp+890h+var_670]
0x18003cecc  jmp     short loc_18003CF1B
0x18003cece  cmp     dword ptr [rax+44h], 4
0x18003ced2  jnz     short loc_18003CF17
0x18003ced4  lea     r8, [rbp+890h+var_670]; unsigned __int16 *
0x18003cedb  mov     rdx, r15; unsigned __int64
0x18003cede  lea     rcx, [rbp+890h+var_250]; unsigned __int16 *
0x18003cee5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003ceea  test    eax, eax
0x18003ceec  js      loc_18003D11E
0x18003cef2  lea     rcx, [rbp+890h+var_250]
0x18003cef9  call    pSetupTrimFileTitle
0x18003cefe  test    eax, eax
0x18003cf00  jz      loc_18003D11E
0x18003cf06  lea     rcx, [rbp+890h+var_250]
0x18003cf0d  call    pSetupGetFileTitle
0x18003cf12  mov     rsi, rax
0x18003cf15  jmp     short loc_18003CF1B
0x18003cf17  lea     rsi, [rbp+890h+var_884]
0x18003cf1b  lea     r12, [rbp+890h+var_670]
0x18003cf22  test    rsi, rsi
0x18003cf25  jz      loc_18003D11E
0x18003cf2b  cmp     [rsi], r14w
0x18003cf2f  jz      loc_18003D11E
0x18003cf35  mov     rdx, [rdi]
0x18003cf38  mov     rcx, r12; unsigned __int16 *
0x18003cf3b  movzx   edx, word ptr [rdx+48h]; unsigned __int16
0x18003cf3f  call    ?DrvUtilsDriverPackageOpen@@YAPEAUHDRIVERPACKAGE__@@PEBGG@Z; DrvUtilsDriverPackageOpen(ushort const *,ushort)
0x18003cf44  mov     r8, [rdi]
0x18003cf47  mov     r15, rax
0x18003cf4a  test    rax, rax
0x18003cf4d  jnz     short loc_18003CF80
0x18003cf4f  test    [r8+4], bl
0x18003cf53  jz      loc_18003CEAF
0x18003cf59  cmp     [r8+44h], ebx
0x18003cf5d  jz      loc_18003CEAF
0x18003cf63  mov     rcx, [r13+0]; struct HDRIVERSTORE__ *
0x18003cf67  lea     r8, [rsp+990h+var_93C]; enum _DRVUTILS_DRIVER_TYPE_FLAG *
0x18003cf6c  mov     rdx, r12; unsigned __int16 *
0x18003cf6f  call    ?DrvUtilsGetDriverPackageInfoFromCache@@YAKPEAUHDRIVERSTORE__@@PEBGPEAW4_DRVUTILS_DRIVER_TYPE_FLAG@@@Z; DrvUtilsGetDriverPackageInfoFromCache(HDRIVERSTORE__ *,ushort const *,_DRVUTILS_DRIVER_TYPE_FLAG *)
0x18003cf74  mov     ebx, eax
0x18003cf76  test    eax, eax
0x18003cf78  jnz     loc_18003D123
0x18003cf7e  jmp     short loc_18003CFA7
0x18003cf80  movzx   r8d, word ptr [r8+48h]
0x18003cf85  lea     rax, [rsp+990h+var_93C]
0x18003cf8a  xor     r9d, r9d
0x18003cf8d  mov     [rsp+990h+var_970], rax
0x18003cf92  mov     rdx, r12
0x18003cf95  mov     rcx, r15
0x18003cf98  call    DrvUtilsGetDriverPackageInfo
0x18003cf9d  mov     ebx, eax
0x18003cf9f  test    eax, eax
0x18003cfa1  jnz     loc_18003D113
0x18003cfa7  mov     r14d, [rsp+990h+var_93C]
0x18003cfac  test    r14d, r14d
0x18003cfaf  jnz     short loc_18003CFBB
0x18003cfb1  mov     ebx, 3D10h
0x18003cfb6  jmp     loc_18003D0D0
0x18003cfbb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2> `wil::Feature<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2>::GetImpl(void)'::`2'::impl
0x18003cfc2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2>::__private_IsEnabled(void)
0x18003cfc7  test    al, al
0x18003cfc9  jz      short loc_18003CFE2
0x18003cfcb  mov     rcx, [r13+0]; struct HDRIVERSTORE__ *
0x18003cfcf  mov     rdx, r15; struct HDRIVERPACKAGE__ *
0x18003cfd2  call    ?pDrvUtilsDriverPackageAppliesToMachine@@YAHPEAUHDRIVERSTORE__@@PEAUHDRIVERPACKAGE__@@@Z; pDrvUtilsDriverPackageAppliesToMachine(HDRIVERSTORE__ *,HDRIVERPACKAGE__ *)
0x18003cfd7  test    eax, eax
0x18003cfd9  mov     eax, 80000000h
0x18003cfde  cmovz   r14d, eax
0x18003cfe2  mov     rcx, [rdi]
0x18003cfe5  mov     edx, r14d
0x18003cfe8  call    ?DrvUtilsInitializeUpdateTables@@YAHPEAU_DRVUTILS_UPDATE_INFO@@W4_DRVUTILS_DRIVER_TYPE_FLAG@@@Z; DrvUtilsInitializeUpdateTables(_DRVUTILS_UPDATE_INFO *,_DRVUTILS_DRIVER_TYPE_FLAG)
0x18003cfed  test    eax, eax
0x18003cfef  jnz     short loc_18003CFFE
0x18003cff1  call    cs:__imp_GetLastError
0x18003cff7  mov     ebx, eax
0x18003cff9  jmp     loc_18003D0D0
0x18003cffe  mov     rcx, [rdi]
0x18003d001  lea     r9, [r13+10h]
0x18003d005  cmp     r14d, 80000000h
0x18003d00c  jnz     short loc_18003D027
0x18003d00e  mov     rcx, [rcx+38h]
0x18003d012  mov     rdx, rsi
0x18003d015  call    pSetupStringTableAddStringEx
0x18003d01a  cmp     eax, 0FFFFFFFFh
0x18003d01d  jnz     short loc_18003D054
0x18003d01f  lea     ebx, [rax+0Fh]
0x18003d022  jmp     loc_18003D0D0
0x18003d027  cmp     r14d, 1
0x18003d02b  jnz     short loc_18003D033
0x18003d02d  mov     rcx, [rcx+8]
0x18003d031  jmp     short loc_18003D012
0x18003d033  mov     rdx, rsi
0x18003d036  cmp     r14d, 2
0x18003d03a  jnz     short loc_18003D042
0x18003d03c  mov     rcx, [rcx+18h]
0x18003d040  jmp     short loc_18003D015
0x18003d042  cmp     r14d, 4
0x18003d046  jnz     short loc_18003D04E
0x18003d048  mov     rcx, [rcx+28h]
0x18003d04c  jmp     short loc_18003D015
0x18003d04e  mov     rcx, [rcx+30h]
0x18003d052  jmp     short loc_18003D015
0x18003d054  mov     rax, [rdi]
0x18003d057  mov     esi, 1
0x18003d05c  cmp     [rax+44h], esi
0x18003d05f  jz      short loc_18003D0BF
0x18003d061  mov     rcx, [r13+0]
0x18003d065  lea     rax, [rsp+990h+var_934]
0x18003d06a  mov     [rsp+990h+var_950], 0
0x18003d072  lea     r9, DEVPKEY_DriverPackage_PendingDriverUpdate
0x18003d079  mov     [rsp+990h+var_958], rax
0x18003d07e  lea     r8, [rbp+890h+var_670]
0x18003d085  lea     rax, [rsp+990h+var_940]
0x18003d08a  mov     [rsp+990h+var_960], esi
0x18003d08e  mov     [rsp+990h+var_968], rax
0x18003d093  lea     edx, [rsi+1]
0x18003d096  lea     rax, [rsp+990h+var_938]
0x18003d09b  mov     [rsp+990h+var_970], rax
0x18003d0a0  call    cs:__imp_DriverStoreGetObjectPropertyW
0x18003d0a6  test    eax, eax
0x18003d0a8  jz      short loc_18003D0B7
0x18003d0aa  cmp     [rsp+990h+var_938], 11h
0x18003d0af  jnz     short loc_18003D0B7
0x18003d0b1  cmp     [rsp+990h+var_934], esi
0x18003d0b5  jz      short loc_18003D0BF
0x18003d0b7  xor     al, al
0x18003d0b9  mov     [rsp+990h+var_940], al
0x18003d0bd  jmp     short loc_18003D0C3
0x18003d0bf  mov     al, [rsp+990h+var_940]
0x18003d0c3  test    al, al
0x18003d0c5  jz      short loc_18003D0D7
0x18003d0c7  mov     rax, [rdi]
0x18003d0ca  test    byte ptr [rax+4], 2
0x18003d0ce  jnz     short loc_18003D0D7
0x18003d0d0  test    r15, r15
0x18003d0d3  jz      short loc_18003D123
0x18003d0d5  jmp     short loc_18003D113
0x18003d0d7  test    r15, r15
0x18003d0da  jz      short loc_18003D123
0x18003d0dc  lea     eax, [r14-1]
0x18003d0e0  cmp     eax, esi
0x18003d0e2  ja      short loc_18003D113
0x18003d0e4  mov     r8, [rdi]
0x18003d0e7  lea     r9, [r8+20h]
0x18003d0eb  cmp     r14d, 2
0x18003d0ef  jz      short loc_18003D0F5
0x18003d0f1  lea     r9, [r8+10h]
0x18003d0f5  mov     r9, [r9]
0x18003d0f8  mov     rdx, r12
0x18003d0fb  movzx   r8d, word ptr [r8+48h]
0x18003d100  mov     rcx, r15
0x18003d103  mov     [rsp+990h+var_970], 0
0x18003d10c  call    DrvUtilsGetDriverPackageInfo
0x18003d111  mov     ebx, eax
0x18003d113  mov     rcx, r15
0x18003d116  call    cs:__imp_DriverPackageClose
0x18003d11c  jmp     short loc_18003D123
0x18003d11e  mov     ebx, 0Dh
0x18003d123  xor     eax, eax
0x18003d125  mov     [r13+14h], ebx
0x18003d129  test    ebx, ebx
0x18003d12b  setz    al
0x18003d12e  mov     rcx, [rbp+890h+var_40]
0x18003d135  xor     rcx, rsp; StackCookie
0x18003d138  call    __security_check_cookie
0x18003d13d  mov     rbx, [rsp+990h+arg_10]
0x18003d145  add     rsp, 960h
0x18003d14c  pop     r15
0x18003d14e  pop     r14
0x18003d150  pop     r13
0x18003d152  pop     r12
0x18003d154  pop     rdi
0x18003d155  pop     rsi
0x18003d156  pop     rbp
0x18003d157  retn
```
