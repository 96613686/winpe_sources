# COAServer::ErrSaveKeys(HKEY__ *)

- ea: `0x180062920`
- end: `0x1800630cd`
- name: `?ErrSaveKeys@COAServer@@QEAAIPEAUHKEY__@@@Z`
- size: `1965`
- prototype: `unsigned int __fastcall(COAServer *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180063450`

## callees

- `0x180016790`
- `0x180046978`
- `0x18004c520`
- `0x180059120`
- `0x18005b0d4`
- `0x180062920`
- `0x1800646cc`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `USER32!wsprintfA` at `0x1800629d6`
- `USER32!wsprintfA` at `0x1800629ec`
- `USER32!wsprintfA` at `0x180062a6b`
- `USER32!wsprintfA` at `0x180062b62`
- `USER32!wsprintfA` at `0x180062be3`
- `USER32!wsprintfA` at `0x180062cad`
- `USER32!wsprintfA` at `0x180062d2e`
- `USER32!wsprintfA` at `0x180062e35`
- `USER32!wsprintfA` at `0x180062eb6`
- `USER32!wsprintfA` at `0x180062f67`
- `USER32!wsprintfA` at `0x180062fc3`
- `USER32!wsprintfA` at `0x180063000`
- `USER32!wsprintfA` at `0x1800629d6`
- `USER32!wsprintfA` at `0x1800629ec`
- `USER32!wsprintfA` at `0x180062a6b`
- `USER32!wsprintfA` at `0x180062b62`
- `USER32!wsprintfA` at `0x180062be3`
- `USER32!wsprintfA` at `0x180062cad`
- `USER32!wsprintfA` at `0x180062d2e`
- `USER32!wsprintfA` at `0x180062e35`
- `USER32!wsprintfA` at `0x180062eb6`
- `USER32!wsprintfA` at `0x180062f67`
- `USER32!wsprintfA` at `0x180062fc3`
- `USER32!wsprintfA` at `0x180063000`
- `ADVAPI32!RegOpenKeyA` at `0x180062a47`
- `ADVAPI32!RegOpenKeyA` at `0x180062b06`
- `ADVAPI32!RegOpenKeyA` at `0x180062bbf`
- `ADVAPI32!RegOpenKeyA` at `0x180062d0a`
- `ADVAPI32!RegOpenKeyA` at `0x180062df3`
- `ADVAPI32!RegOpenKeyA` at `0x180062e92`
- `ADVAPI32!RegOpenKeyA` at `0x180062fdd`
- `ADVAPI32!RegOpenKeyA` at `0x180062a47`
- `ADVAPI32!RegOpenKeyA` at `0x180062b06`
- `ADVAPI32!RegOpenKeyA` at `0x180062bbf`
- `ADVAPI32!RegOpenKeyA` at `0x180062d0a`
- `ADVAPI32!RegOpenKeyA` at `0x180062df3`
- `ADVAPI32!RegOpenKeyA` at `0x180062e92`
- `ADVAPI32!RegOpenKeyA` at `0x180062fdd`
- `ADVAPI32!RegCloseKey` at `0x180062a20`
- `ADVAPI32!RegCloseKey` at `0x180062ab8`
- `ADVAPI32!RegCloseKey` at `0x180062ad2`
- `ADVAPI32!RegCloseKey` at `0x180062b96`
- `ADVAPI32!RegCloseKey` at `0x180062c30`
- `ADVAPI32!RegCloseKey` at `0x180062c4a`
- `ADVAPI32!RegCloseKey` at `0x180062ce1`
- `ADVAPI32!RegCloseKey` at `0x180062d7b`
- `ADVAPI32!RegCloseKey` at `0x180062d95`
- `ADVAPI32!RegCloseKey` at `0x180062dbf`
- `ADVAPI32!RegCloseKey` at `0x180062e69`
- `ADVAPI32!RegCloseKey` at `0x180062f03`
- `ADVAPI32!RegCloseKey` at `0x180062f1d`
- `ADVAPI32!RegCloseKey` at `0x180062f37`
- `ADVAPI32!RegCloseKey` at `0x180062f9b`
- `ADVAPI32!RegCloseKey` at `0x180063045`
- `ADVAPI32!RegCloseKey` at `0x18006305b`
- `ADVAPI32!RegCloseKey` at `0x18006307b`
- `ADVAPI32!RegCloseKey` at `0x18006308b`
- `ADVAPI32!RegCloseKey` at `0x18006309b`
- `ADVAPI32!RegCloseKey` at `0x180062a20`
- `ADVAPI32!RegCloseKey` at `0x180062ab8`
- `ADVAPI32!RegCloseKey` at `0x180062ad2`
- `ADVAPI32!RegCloseKey` at `0x180062b96`
- `ADVAPI32!RegCloseKey` at `0x180062c30`
- `ADVAPI32!RegCloseKey` at `0x180062c4a`
- `ADVAPI32!RegCloseKey` at `0x180062ce1`
- `ADVAPI32!RegCloseKey` at `0x180062d7b`
- `ADVAPI32!RegCloseKey` at `0x180062d95`
- `ADVAPI32!RegCloseKey` at `0x180062dbf`
- `ADVAPI32!RegCloseKey` at `0x180062e69`
- `ADVAPI32!RegCloseKey` at `0x180062f03`
- `ADVAPI32!RegCloseKey` at `0x180062f1d`
- `ADVAPI32!RegCloseKey` at `0x180062f37`
- `ADVAPI32!RegCloseKey` at `0x180062f9b`
- `ADVAPI32!RegCloseKey` at `0x180063045`
- `ADVAPI32!RegCloseKey` at `0x18006305b`
- `ADVAPI32!RegCloseKey` at `0x18006307b`
- `ADVAPI32!RegCloseKey` at `0x18006308b`
- `ADVAPI32!RegCloseKey` at `0x18006309b`

## string_xrefs

- `0x1800629e1`: `DeletePI\%s`
- `0x180062a60`: `Replace\%s`
- `0x180062ff5`: `Replace\%s`
- `0x180062b57`: `DeleteIF\%s`
- `0x180062ca2`: `DeleteIF\%s`
- `0x180062bd8`: `Replace\Interface\%s`
- `0x180062d23`: `Replace\Interface\%s`
- `0x180062e2a`: `DeleteCL\%s`
- `0x180062eab`: `Replace\CLSID\%s`
- `0x180062f5c`: `DeleteAP\%s`
- `0x180062de9`: `Clsid`

## pseudocode

```c
__int64 __fastcall COAServer::ErrSaveKeys(COAServer *this, HKEY a2)
{
  __int64 v3; // rcx
  HKEY v5; // rbx
  LSTATUS v6; // eax
  HKEY v7; // rcx
  LSTATUS v8; // edi
  LSTATUS v9; // eax
  HKEY v10; // rbx
  HKEY v11; // rbx
  LSTATUS v12; // eax
  HKEY v13; // rdx
  unsigned int v14; // ebx
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  HKEY v17; // rbx
  HKEY v18; // rax
  int v19; // r14d
  HKEY v20; // rbx
  LSTATUS v21; // eax
  HKEY v22; // rcx
  LSTATUS v23; // eax
  HKEY v24; // rbx
  HKEY v25; // rbx
  LSTATUS v26; // eax
  HKEY v27; // rdx
  LSTATUS v28; // eax
  LSTATUS v29; // eax
  int v30; // r14d
  HKEY v31; // rbx
  LSTATUS v32; // eax
  HKEY v33; // rcx
  LSTATUS v34; // eax
  HKEY v35; // rbx
  HKEY v36; // rbx
  LSTATUS v37; // eax
  HKEY v38; // rdx
  LSTATUS v39; // eax
  LSTATUS v40; // eax
  __int64 v41; // rbx
  HKEY v42; // rax
  HKEY v43; // rbx
  LSTATUS v44; // eax
  HKEY v45; // rcx
  LSTATUS v46; // eax
  HKEY v47; // rbx
  HKEY v48; // rbx
  LSTATUS v49; // eax
  HKEY v50; // rdx
  LSTATUS v51; // eax
  LSTATUS v52; // eax
  LSTATUS v53; // eax
  HKEY v54; // rbx
  LSTATUS v55; // eax
  HKEY v56; // rcx
  LSTATUS v57; // eax
  HKEY v58; // rbx
  HKEY v59; // rbx
  LSTATUS v60; // eax
  HKEY v61; // rdx
  LSTATUS v62; // eax
  LSTATUS v63; // eax
  HKEY hKey; // [rsp+20h] [rbp-E0h] BYREF
  HKEY phkResult; // [rsp+28h] [rbp-D8h] BYREF
  HKEY v67; // [rsp+30h] [rbp-D0h] BYREF
  CHAR v68[40]; // [rsp+38h] [rbp-C8h] BYREF
  CHAR SubKey[48]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR v70[256]; // [rsp+90h] [rbp-70h] BYREF
  CHAR v71[256]; // [rsp+190h] [rbp+90h] BYREF
  char v72[2048]; // [rsp+290h] [rbp+190h] BYREF
  char v73[2048]; // [rsp+A90h] [rbp+990h] BYREF

  v3 = *((_QWORD *)this + 17);
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v67 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Project::GetProjectName(*(Project **)(v3 + 40), v73, 0x7FCu);
  Projitem::GetModName(*((Projitem **)this + 17), v72, 0x7FCu);
  if ( (*((_WORD *)this + 38) & 0x1200) == 0 )
    goto LABEL_48;
  wsprintfA(SubKey, "%s.%s", v73, v72);
  wsprintfA(v70, "DeletePI\\%s", SubKey);
  v5 = hKey;
  v6 = FastRegCreateKey(a2, v70, &hKey);
  v7 = hKey;
  v8 = v6;
  if ( v6 )
    v7 = v5;
  hKey = v7;
  if ( v6 )
    goto LABEL_78;
  v9 = RegCloseKey(v7);
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v8 = v9;
  if ( v9 )
    goto LABEL_78;
  v10 = phkResult;
  if ( RegOpenKeyA(HKEY_CLASSES_ROOT, SubKey, &phkResult) )
  {
    phkResult = v10;
  }
  else
  {
    wsprintfA(v70, "Replace\\%s", SubKey);
    v11 = hKey;
    v12 = FastRegCreateKey(a2, v70, &hKey);
    v13 = hKey;
    v8 = v12;
    if ( v12 )
      v13 = v11;
    hKey = v13;
    if ( v12 )
      goto LABEL_78;
    v14 = _ErrRegCopyTree(phkResult, v13);
    if ( v14 )
      goto LABEL_79;
    v15 = RegCloseKey(phkResult);
    phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    v8 = v15;
    if ( v15 )
      goto LABEL_78;
    v16 = RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    v8 = v16;
    if ( v16 )
      goto LABEL_78;
  }
  if ( (*((_WORD *)this + 38) & 0x1200) == 0 )
  {
LABEL_48:
    v41 = (__int64)v67;
LABEL_49:
    v8 = RegOpenKeyA(HKEY_CLASSES_ROOT, szCLSID, &v67);
    v42 = v67;
    if ( v8 )
      v42 = (HKEY)v41;
    v67 = v42;
    if ( !v8 )
    {
      StringFromGUID2Ansi((const struct _GUID *)((char *)this + 44), v68, 39);
      wsprintfA(v70, "DeleteCL\\%s", v68);
      v43 = hKey;
      v44 = FastRegCreateKey(a2, v70, &hKey);
      v45 = hKey;
      v8 = v44;
      if ( v44 )
        v45 = v43;
      hKey = v45;
      if ( !v44 )
      {
        v46 = RegCloseKey(v45);
        hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
        v8 = v46;
        if ( !v46 )
        {
          v47 = phkResult;
          if ( RegOpenKeyA(v67, v68, &phkResult) )
          {
            phkResult = v47;
          }
          else
          {
            wsprintfA(v70, "Replace\\CLSID\\%s", v68);
            v48 = hKey;
            v49 = FastRegCreateKey(a2, v70, &hKey);
            v50 = hKey;
            v8 = v49;
            if ( v49 )
              v50 = v48;
            hKey = v50;
            if ( v49 )
              goto LABEL_78;
            v14 = _ErrRegCopyTree(phkResult, v50);
            if ( v14 )
              goto LABEL_79;
            v51 = RegCloseKey(phkResult);
            phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
            v8 = v51;
            if ( v51 )
              goto LABEL_78;
            v52 = RegCloseKey(hKey);
            hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
            v8 = v52;
            if ( v52 )
              goto LABEL_78;
          }
          v53 = RegCloseKey(v67);
          v67 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
          v8 = v53;
          if ( !v53 && (*((_WORD *)this + 38) & 0x1200) != 0 )
          {
            wsprintfA(v70, "DeleteAP\\%s", v68);
            v54 = hKey;
            v55 = FastRegCreateKey(a2, v70, &hKey);
            v56 = hKey;
            v8 = v55;
            if ( v55 )
              v56 = v54;
            hKey = v56;
            if ( !v55 )
            {
              v57 = RegCloseKey(v56);
              hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
              v8 = v57;
              if ( !v57 )
              {
                wsprintfA(v71, "AppID\\%s", v68);
                v58 = phkResult;
                if ( RegOpenKeyA(HKEY_CLASSES_ROOT, v71, &phkResult) )
                {
                  phkResult = v58;
                }
                else
                {
                  wsprintfA(v70, "Replace\\%s", v71);
                  v59 = hKey;
                  v60 = FastRegCreateKey(a2, v70, &hKey);
                  v61 = hKey;
                  v8 = v60;
                  if ( v60 )
                    v61 = v59;
                  hKey = v61;
                  if ( !v60 )
                  {
                    v14 = _ErrRegCopyTree(phkResult, v61);
                    if ( v14 )
                      goto LABEL_79;
                    v62 = RegCloseKey(phkResult);
                    phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
                    v8 = v62;
                    if ( !v62 )
                    {
                      v63 = RegCloseKey(hKey);
                      hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
                      v8 = v63;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    goto LABEL_78;
  }
  v17 = v67;
  v8 = RegOpenKeyA(HKEY_CLASSES_ROOT, szInterface, &v67);
  v18 = v67;
  if ( v8 )
    v18 = v17;
  v67 = v18;
  if ( !v8 )
  {
    v19 = 0;
    if ( *((int *)this + 38) > 0 )
    {
      do
      {
        StringFromGUID2Ansi((const struct _GUID *)(*((_QWORD *)this + 18) + 16LL * v19), v68, 39);
        wsprintfA(v70, "DeleteIF\\%s", v68);
        v20 = hKey;
        v21 = FastRegCreateKey(a2, v70, &hKey);
        v22 = hKey;
        v8 = v21;
        if ( v21 )
          v22 = v20;
        hKey = v22;
        if ( v21 )
          goto LABEL_78;
        v23 = RegCloseKey(v22);
        hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
        v8 = v23;
        if ( v23 )
          goto LABEL_78;
        v24 = phkResult;
        if ( RegOpenKeyA(v67, v68, &phkResult) )
        {
          phkResult = v24;
        }
        else
        {
          wsprintfA(v70, "Replace\\Interface\\%s", v68);
          v25 = hKey;
          v26 = FastRegCreateKey(a2, v70, &hKey);
          v27 = hKey;
          v8 = v26;
          if ( v26 )
            v27 = v25;
          hKey = v27;
          if ( v26 )
            goto LABEL_78;
          v14 = _ErrRegCopyTree(phkResult, v27);
          if ( v14 )
            goto LABEL_79;
          v28 = RegCloseKey(phkResult);
          phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
          v8 = v28;
          if ( v28 )
            goto LABEL_78;
          v29 = RegCloseKey(hKey);
          hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
          v8 = v29;
          if ( v29 )
            goto LABEL_78;
        }
      }
      while ( ++v19 < *((_DWORD *)this + 38) );
    }
    v30 = 0;
    if ( *((int *)this + 42) > 0 )
    {
      do
      {
        StringFromGUID2Ansi((const struct _GUID *)(*((_QWORD *)this + 20) + 16LL * v30), v68, 39);
        wsprintfA(v70, "DeleteIF\\%s", v68);
        v31 = hKey;
        v32 = FastRegCreateKey(a2, v70, &hKey);
        v33 = hKey;
        v8 = v32;
        if ( v32 )
          v33 = v31;
        hKey = v33;
        if ( v32 )
          goto LABEL_78;
        v34 = RegCloseKey(v33);
        hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
        v8 = v34;
        if ( v34 )
          goto LABEL_78;
        v35 = phkResult;
        if ( RegOpenKeyA(v67, v68, &phkResult) )
        {
          phkResult = v35;
        }
        else
        {
          wsprintfA(v70, "Replace\\Interface\\%s", v68);
          v36 = hKey;
          v37 = FastRegCreateKey(a2, v70, &hKey);
          v38 = hKey;
          v8 = v37;
          if ( v37 )
            v38 = v36;
          hKey = v38;
          if ( v37 )
            goto LABEL_78;
          v14 = _ErrRegCopyTree(phkResult, v38);
          if ( v14 )
            goto LABEL_79;
          v39 = RegCloseKey(phkResult);
          phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
          v8 = v39;
          if ( v39 )
            goto LABEL_78;
          v40 = RegCloseKey(hKey);
          hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
          v8 = v40;
          if ( v40 )
            goto LABEL_78;
        }
      }
      while ( ++v30 < *((_DWORD *)this + 42) );
    }
    v41 = -1;
    v8 = RegCloseKey(v67);
    v67 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    if ( !v8 )
      goto LABEL_49;
  }
LABEL_78:
  v14 = ErrFromRegError(v8);
LABEL_79:
  if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(phkResult);
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  if ( v67 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(v67);
  return v14;
}

```

## disassembly

```asm
0x180062920  mov     [rsp-8+arg_10], rbx
0x180062925  push    rbp
0x180062926  push    rsi
0x180062927  push    rdi
0x180062928  push    r12
0x18006292a  push    r13
0x18006292c  push    r14
0x18006292e  push    r15
0x180062930  lea     rbp, [rsp-11A0h]
0x180062938  mov     eax, 12A0h
0x18006293d  call    _alloca_probe
0x180062942  sub     rsp, rax
0x180062945  mov     rax, cs:__security_cookie
0x18006294c  xor     rax, rsp
0x18006294f  mov     [rbp+11D0h+var_40], rax
0x180062956  mov     rsi, rcx
0x180062959  mov     rcx, [rcx+88h]
0x180062960  or      r12, 0FFFFFFFFFFFFFFFFh
0x180062964  mov     [rsp+12D0h+phkResult], r12
0x180062969  mov     [rsp+12D0h+hKey], r12
0x18006296e  mov     [rsp+12D0h+var_12A0], r12
0x180062973  mov     rcx, [rcx+28h]; this
0x180062977  mov     r15, rdx
0x18006297a  mov     ebx, 7FCh
0x18006297f  lea     rdx, [rbp+11D0h+var_840]; char *
0x180062986  mov     r8d, ebx; unsigned int
0x180062989  call    ?GetProjectName@Project@@QEAAHPEADI@Z; Project::GetProjectName(char *,uint)
0x18006298e  mov     rcx, [rsi+88h]; this
0x180062995  lea     rdx, [rbp+11D0h+var_1040]; char *
0x18006299c  mov     r8d, ebx; unsigned int
0x18006299f  call    ?GetModName@Projitem@@QEAAHPEADI@Z; Projitem::GetModName(char *,uint)
0x1800629a4  mov     r14d, 1200h
0x1800629aa  mov     r13, 0FFFFFFFF80000000h
0x1800629b1  test    [rsi+4Ch], r14w
0x1800629b6  jz      loc_180062DDF
0x1800629bc  lea     r9, [rbp+11D0h+var_1040]
0x1800629c3  lea     r8, [rbp+11D0h+var_840]
0x1800629ca  lea     rdx, aSS_6; "%s.%s"
0x1800629d1  lea     rcx, [rsp+12D0h+SubKey]; LPSTR
0x1800629d6  call    cs:__imp_wsprintfA
0x1800629dc  lea     r8, [rsp+12D0h+SubKey]
0x1800629e1  lea     rdx, aDeletepiS; "DeletePI\\%s"
0x1800629e8  lea     rcx, [rbp+11D0h+var_1240]; LPSTR
0x1800629ec  call    cs:__imp_wsprintfA
0x1800629f2  mov     rbx, [rsp+12D0h+hKey]
0x1800629f7  lea     r8, [rsp+12D0h+hKey]; HKEY *
0x1800629fc  lea     rdx, [rbp+11D0h+var_1240]; char *
0x180062a00  mov     rcx, r15; HKEY
0x180062a03  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180062a08  mov     rcx, [rsp+12D0h+hKey]
0x180062a0d  test    eax, eax
0x180062a0f  mov     edi, eax
0x180062a11  cmovnz  rcx, rbx; hKey
0x180062a15  mov     [rsp+12D0h+hKey], rcx
0x180062a1a  jnz     loc_180063068
0x180062a20  call    cs:__imp_RegCloseKey
0x180062a26  mov     [rsp+12D0h+hKey], r12
0x180062a2b  mov     edi, eax
0x180062a2d  test    eax, eax
0x180062a2f  jnz     loc_180063068
0x180062a35  mov     rbx, [rsp+12D0h+phkResult]
0x180062a3a  lea     r8, [rsp+12D0h+phkResult]; phkResult
0x180062a3f  lea     rdx, [rsp+12D0h+SubKey]; lpSubKey
0x180062a44  mov     rcx, r13; hKey
0x180062a47  call    cs:__imp_RegOpenKeyA
0x180062a4d  test    eax, eax
0x180062a4f  jz      short loc_180062A5B
0x180062a51  mov     [rsp+12D0h+phkResult], rbx
0x180062a56  jmp     loc_180062AE7
0x180062a5b  lea     r8, [rsp+12D0h+SubKey]
0x180062a60  lea     rdx, aReplaceS; "Replace\\%s"
0x180062a67  lea     rcx, [rbp+11D0h+var_1240]; LPSTR
0x180062a6b  call    cs:__imp_wsprintfA
0x180062a71  mov     rbx, [rsp+12D0h+hKey]
0x180062a76  lea     r8, [rsp+12D0h+hKey]; HKEY *
0x180062a7b  lea     rdx, [rbp+11D0h+var_1240]; char *
0x180062a7f  mov     rcx, r15; HKEY
0x180062a82  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180062a87  mov     rdx, [rsp+12D0h+hKey]
0x180062a8c  test    eax, eax
0x180062a8e  mov     edi, eax
0x180062a90  cmovnz  rdx, rbx; HKEY
0x180062a94  mov     [rsp+12D0h+hKey], rdx
0x180062a99  jnz     loc_180063068
0x180062a9f  mov     rcx, [rsp+12D0h+phkResult]; HKEY
0x180062aa4  call    ?_ErrRegCopyTree@@YAIPEAUHKEY__@@0@Z; _ErrRegCopyTree(HKEY__ *,HKEY__ *)
0x180062aa9  mov     ebx, eax
0x180062aab  test    eax, eax
0x180062aad  jnz     loc_180063071
0x180062ab3  mov     rcx, [rsp+12D0h+phkResult]; hKey
0x180062ab8  call    cs:__imp_RegCloseKey
0x180062abe  mov     [rsp+12D0h+phkResult], r12
0x180062ac3  mov     edi, eax
0x180062ac5  test    eax, eax
0x180062ac7  jnz     loc_180063068
0x180062acd  mov     rcx, [rsp+12D0h+hKey]; hKey
0x180062ad2  call    cs:__imp_RegCloseKey
0x180062ad8  mov     [rsp+12D0h+hKey], r12
0x180062add  mov     edi, eax
0x180062adf  test    eax, eax
0x180062ae1  jnz     loc_180063068
0x180062ae7  test    [rsi+4Ch], r14w
0x180062aec  jz      loc_180062DDF
0x180062af2  mov     rbx, [rsp+12D0h+var_12A0]
0x180062af7  lea     r8, [rsp+12D0h+var_12A0]; phkResult
0x180062afc  lea     rdx, ?szInterface@@3PADA; "Interface"
0x180062b03  mov     rcx, r13; hKey
0x180062b06  call    cs:__imp_RegOpenKeyA
0x180062b0c  mov     edi, eax
0x180062b0e  mov     rax, [rsp+12D0h+var_12A0]
0x180062b13  test    edi, edi
0x180062b15  cmovnz  rax, rbx
0x180062b19  mov     [rsp+12D0h+var_12A0], rax
0x180062b1e  jnz     loc_180063068
0x180062b24  xor     r14d, r14d
0x180062b27  cmp     [rsi+98h], r14d
0x180062b2e  jle     loc_180062C6F
0x180062b34  movsxd  rcx, r14d
0x180062b37  lea     rdx, [rsp+12D0h+var_1298]; char *
0x180062b3c  mov     r8d, 27h ; '''; int
0x180062b42  shl     rcx, 4
0x180062b46  add     rcx, [rsi+90h]; struct _GUID *
0x180062b4d  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x180062b52  lea     r8, [rsp+12D0h+var_1298]
0x180062b57  lea     rdx, aDeleteifS; "DeleteIF\\%s"
0x180062b5e  lea     rcx, [rbp+11D0h+var_1240]; LPSTR
0x180062b62  call    cs:__imp_wsprintfA
0x180062b68  mov     rbx, [rsp+12D0h+hKey]
0x180062b6d  lea     r8, [rsp+12D0h+hKey]; HKEY *
0x180062b72  lea     rdx, [rbp+11D0h+var_1240]; char *
0x180062b76  mov     rcx, r15; HKEY
0x180062b79  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180062b7e  mov     rcx, [rsp+12D0h+hKey]
0x180062b83  test    eax, eax
0x180062b85  mov     edi, eax
0x180062b87  cmovnz  rcx, rbx; hKey
0x180062b8b  mov     [rsp+12D0h+hKey], rcx
0x180062b90  jnz     loc_180063068
0x180062b96  call    cs:__imp_RegCloseKey
0x180062b9c  mov     [rsp+12D0h+hKey], r12
0x180062ba1  mov     edi, eax
0x180062ba3  test    eax, eax
0x180062ba5  jnz     loc_180063068
0x180062bab  mov     rcx, [rsp+12D0h+var_12A0]; hKey
0x180062bb0  mov     rbx, [rsp+12D0h+phkResult]
0x180062bb5  lea     r8, [rsp+12D0h+phkResult]; phkResult
0x180062bba  lea     rdx, [rsp+12D0h+var_1298]; lpSubKey
0x180062bbf  call    cs:__imp_RegOpenKeyA
0x180062bc5  test    eax, eax
0x180062bc7  jz      short loc_180062BD3
0x180062bc9  mov     [rsp+12D0h+phkResult], rbx
0x180062bce  jmp     loc_180062C5F
0x180062bd3  lea     r8, [rsp+12D0h+var_1298]
0x180062bd8  lea     rdx, aReplaceInterfa; "Replace\\Interface\\%s"
0x180062bdf  lea     rcx, [rbp+11D0h+var_1240]; LPSTR
0x180062be3  call    cs:__imp_wsprintfA
0x180062be9  mov     rbx, [rsp+12D0h+hKey]
0x180062bee  lea     r8, [rsp+12D0h+hKey]; HKEY *
0x180062bf3  lea     rdx, [rbp+11D0h+var_1240]; char *
0x180062bf7  mov     rcx, r15; HKEY
0x180062bfa  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180062bff  mov     rdx, [rsp+12D0h+hKey]
0x180062c04  test    eax, eax
0x180062c06  mov     edi, eax
0x180062c08  cmovnz  rdx, rbx; HKEY
0x180062c0c  mov     [rsp+12D0h+hKey], rdx
0x180062c11  jnz     loc_180063068
0x180062c17  mov     rcx, [rsp+12D0h+phkResult]; HKEY
0x180062c1c  call    ?_ErrRegCopyTree@@YAIPEAUHKEY__@@0@Z; _ErrRegCopyTree(HKEY__ *,HKEY__ *)
0x180062c21  mov     ebx, eax
0x180062c23  test    eax, eax
0x180062c25  jnz     loc_180063071
0x180062c2b  mov     rcx, [rsp+12D0h+phkResult]; hKey
0x180062c30  call    cs:__imp_RegCloseKey
0x180062c36  mov     [rsp+12D0h+phkResult], r12
0x180062c3b  mov     edi, eax
0x180062c3d  test    eax, eax
0x180062c3f  jnz     loc_180063068
0x180062c45  mov     rcx, [rsp+12D0h+hKey]; hKey
0x180062c4a  call    cs:__imp_RegCloseKey
0x180062c50  mov     [rsp+12D0h+hKey], r12
0x180062c55  mov     edi, eax
0x180062c57  test    eax, eax
0x180062c59  jnz     loc_180063068
0x180062c5f  inc     r14d
0x180062c62  cmp     r14d, [rsi+98h]
0x180062c69  jl      loc_180062B34
0x180062c6f  xor     r14d, r14d
0x180062c72  cmp     [rsi+0A8h], r14d
0x180062c79  jle     loc_180062DBA
0x180062c7f  movsxd  rcx, r14d
0x180062c82  lea     rdx, [rsp+12D0h+var_1298]; char *
0x180062c87  mov     r8d, 27h ; '''; int
0x180062c8d  shl     rcx, 4
0x180062c91  add     rcx, [rsi+0A0h]; struct _GUID *
0x180062c98  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x180062c9d  lea     r8, [rsp+12D0h+var_1298]
0x180062ca2  lea     rdx, aDeleteifS; "DeleteIF\\%s"
0x180062ca9  lea     rcx, [rbp+11D0h+var_1240]; LPSTR
0x180062cad  call    cs:__imp_wsprintfA
0x180062cb3  mov     rbx, [rsp+12D0h+hKey]
0x180062cb8  lea     r8, [rsp+12D0h+hKey]; HKEY *
0x180062cbd  lea     rdx, [rbp+11D0h+var_1240]; char *
0x180062cc1  mov     rcx, r15; HKEY
0x180062cc4  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180062cc9  mov     rcx, [rsp+12D0h+hKey]
0x180062cce  test    eax, eax
0x180062cd0  mov     edi, eax
0x180062cd2  cmovnz  rcx, rbx; hKey
0x180062cd6  mov     [rsp+12D0h+hKey], rcx
0x180062cdb  jnz     loc_180063068
0x180062ce1  call    cs:__imp_RegCloseKey
0x180062ce7  mov     [rsp+12D0h+hKey], r12
0x180062cec  mov     edi, eax
0x180062cee  test    eax, eax
0x180062cf0  jnz     loc_180063068
0x180062cf6  mov     rcx, [rsp+12D0h+var_12A0]; hKey
0x180062cfb  mov     rbx, [rsp+12D0h+phkResult]
0x180062d00  lea     r8, [rsp+12D0h+phkResult]; phkResult
0x180062d05  lea     rdx, [rsp+12D0h+var_1298]; lpSubKey
0x180062d0a  call    cs:__imp_RegOpenKeyA
0x180062d10  test    eax, eax
0x180062d12  jz      short loc_180062D1E
0x180062d14  mov     [rsp+12D0h+phkResult], rbx
0x180062d19  jmp     loc_180062DAA
0x180062d1e  lea     r8, [rsp+12D0h+var_1298]
0x180062d23  lea     rdx, aReplaceInterfa; "Replace\\Interface\\%s"
0x180062d2a  lea     rcx, [rbp+11D0h+var_1240]; LPSTR
0x180062d2e  call    cs:__imp_wsprintfA
0x180062d34  mov     rbx, [rsp+12D0h+hKey]
0x180062d39  lea     r8, [rsp+12D0h+hKey]; HKEY *
0x180062d3e  lea     rdx, [rbp+11D0h+var_1240]; char *
0x180062d42  mov     rcx, r15; HKEY
0x180062d45  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180062d4a  mov     rdx, [rsp+12D0h+hKey]
0x180062d4f  test    eax, eax
0x180062d51  mov     edi, eax
0x180062d53  cmovnz  rdx, rbx; HKEY
0x180062d57  mov     [rsp+12D0h+hKey], rdx
0x180062d5c  jnz     loc_180063068
0x180062d62  mov     rcx, [rsp+12D0h+phkResult]; HKEY
0x180062d67  call    ?_ErrRegCopyTree@@YAIPEAUHKEY__@@0@Z; _ErrRegCopyTree(HKEY__ *,HKEY__ *)
0x180062d6c  mov     ebx, eax
0x180062d6e  test    eax, eax
0x180062d70  jnz     loc_180063071
0x180062d76  mov     rcx, [rsp+12D0h+phkResult]; hKey
0x180062d7b  call    cs:__imp_RegCloseKey
0x180062d81  mov     [rsp+12D0h+phkResult], r12
0x180062d86  mov     edi, eax
0x180062d88  test    eax, eax
0x180062d8a  jnz     loc_180063068
0x180062d90  mov     rcx, [rsp+12D0h+hKey]; hKey
0x180062d95  call    cs:__imp_RegCloseKey
0x180062d9b  mov     [rsp+12D0h+hKey], r12
0x180062da0  mov     edi, eax
0x180062da2  test    eax, eax
0x180062da4  jnz     loc_180063068
0x180062daa  inc     r14d
0x180062dad  cmp     r14d, [rsi+0A8h]
0x180062db4  jl      loc_180062C7F
0x180062dba  mov     rcx, [rsp+12D0h+var_12A0]; hKey
0x180062dbf  call    cs:__imp_RegCloseKey
0x180062dc5  mov     rbx, r12
0x180062dc8  mov     edi, eax
0x180062dca  mov     [rsp+12D0h+var_12A0], rbx
0x180062dcf  test    eax, eax
0x180062dd1  jnz     loc_180063068
0x180062dd7  mov     r14d, 1200h
0x180062ddd  jmp     short loc_180062DE4
0x180062ddf  mov     rbx, [rsp+12D0h+var_12A0]
0x180062de4  lea     r8, [rsp+12D0h+var_12A0]; phkResult
0x180062de9  lea     rdx, ?szCLSID@@3PADA; "Clsid"
0x180062df0  mov     rcx, r13; hKey
0x180062df3  call    cs:__imp_RegOpenKeyA
0x180062df9  mov     edi, eax
0x180062dfb  mov     rax, [rsp+12D0h+var_12A0]
0x180062e00  test    edi, edi
0x180062e02  cmovnz  rax, rbx
0x180062e06  mov     [rsp+12D0h+var_12A0], rax
0x180062e0b  jnz     loc_180063068
0x180062e11  lea     rcx, [rsi+2Ch]; struct _GUID *
0x180062e15  lea     rdx, [rsp+12D0h+var_1298]; char *
0x180062e1a  mov     r8d, 27h ; '''; int
0x180062e20  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x180062e25  lea     r8, [rsp+12D0h+var_1298]
0x180062e2a  lea     rdx, aDeleteclS; "DeleteCL\\%s"
0x180062e31  lea     rcx, [rbp+11D0h+var_1240]; LPSTR
0x180062e35  call    cs:__imp_wsprintfA
0x180062e3b  mov     rbx, [rsp+12D0h+hKey]
0x180062e40  lea     r8, [rsp+12D0h+hKey]; HKEY *
0x180062e45  lea     rdx, [rbp+11D0h+var_1240]; char *
0x180062e49  mov     rcx, r15; HKEY
0x180062e4c  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBDPEAPEAU1@@Z; FastRegCreateKey(HKEY__ *,char const *,HKEY__ * *)
0x180062e51  mov     rcx, [rsp+12D0h+hKey]
0x180062e56  test    eax, eax
0x180062e58  mov     edi, eax
0x180062e5a  cmovnz  rcx, rbx; hKey
0x180062e5e  mov     [rsp+12D0h+hKey], rcx
0x180062e63  jnz     loc_180063068
0x180062e69  call    cs:__imp_RegCloseKey
  ... truncated ...
```
