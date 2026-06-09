# CommonUtil::MpUtilMicrosoftCatalogCertCheck

- ea: `0x1400104e4`
- end: `0x140010885`
- name: `CommonUtil::MpUtilMicrosoftCatalogCertCheck`
- size: `929`
- prototype: `__int64 __fastcall(void **, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001088c`

## callees

- `0x1400015d0`
- `0x14000202c`
- `0x140003640`
- `0x140007718`
- `0x14000e990`
- `0x140010458`
- `0x1400104e4`
- `0x140010b20`
- `0x140010bc4`
- `0x140011234`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140010857`
- `KERNEL32!CloseHandle` at `0x140010857`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x140010688`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x140010688`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x14001083a`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x14001083a`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1400105ec`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1400105ec`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x14001062f`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x14001062f`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x140010828`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x140010828`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x1400106d7`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x1400106d7`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpUtilMicrosoftCatalogCertCheck(void **a1, unsigned int a2)
{
  void *v4; // rdi
  const unsigned __int16 *v5; // r8
  unsigned int v6; // r9d
  LONG File; // ebx
  HANDLE v8; // rsi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  HCATINFO v11; // rax
  int v12; // eax
  __int64 v13; // r8
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  unsigned int phPrevCatInfo; // [rsp+20h] [rbp-E0h]
  unsigned int v18; // [rsp+30h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES *v19; // [rsp+38h] [rbp-C8h]
  void *pcbHash; // [rsp+40h] [rbp-C0h] BYREF
  HCATADMIN phCatAdmin; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile[2]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v23[6]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h]
  int v25; // [rsp+80h] [rbp-80h]
  int *v26; // [rsp+88h] [rbp-78h]
  int v27; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+98h] [rbp-68h]
  int v29; // [rsp+A8h] [rbp-58h]
  int v30; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR *wszCatalogFile; // [rsp+C8h] [rbp-38h]
  __int64 v32; // [rsp+D0h] [rbp-30h]
  void **v33; // [rsp+D8h] [rbp-28h]
  HANDLE v34; // [rsp+E0h] [rbp-20h]
  BYTE *v35; // [rsp+E8h] [rbp-18h]
  int v36; // [rsp+F0h] [rbp-10h]
  GUID v37; // [rsp+110h] [rbp+10h] BYREF
  CATALOG_INFO psCatInfo; // [rsp+120h] [rbp+20h] BYREF
  BYTE pbHash[64]; // [rsp+330h] [rbp+230h] BYREF

  v37.Data1 = 11191659;
  *(_DWORD *)&v37.Data2 = 298896708;
  *(_DWORD *)v37.Data4 = -1073692020;
  *(_DWORD *)&v37.Data4[4] = -292175281;
  memset_0(v23, 0, 0x58u);
  memset_0(&v30, 0, 0x48u);
  memset_0(&psCatInfo, 0, sizeof(psCatInfo));
  phCatAdmin = 0;
  v4 = 0;
  LODWORD(pcbHash) = 64;
  hFile[0] = (HANDLE)-1LL;
  File = CommonUtil::UtilCreateFile((CommonUtil *)hFile, a1, v5, v6, phPrevCatInfo, 0x8000000u, v18, v19, pcbHash);
  v8 = hFile[0];
  if ( File < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 22;
LABEL_5:
      WPP_SF_d(v9[2], v10, &WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids, (unsigned int)File);
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  if ( !CryptCATAdminCalcHashFromFileHandle(hFile[0], (DWORD *)&pcbHash, pbHash, 0) )
  {
    File = HrGetLastFailure();
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 23;
      goto LABEL_5;
    }
    goto LABEL_38;
  }
  if ( !CryptCATAdminAcquireContext(&phCatAdmin, 0, 0) )
  {
    File = HrGetLastFailure();
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 24;
      goto LABEL_5;
    }
    goto LABEL_38;
  }
  v11 = CryptCATAdminEnumCatalogFromHash(phCatAdmin, pbHash, (DWORD)pcbHash, 0, 0);
  v4 = v11;
  if ( !v11 )
  {
    File = HrGetLastFailure();
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 25;
      goto LABEL_5;
    }
    goto LABEL_38;
  }
  psCatInfo.cbStruct = 524;
  if ( !CryptCATCatalogInfoFromContext(v11, &psCatInfo, 0) )
  {
    File = HrGetLastFailure();
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 26;
      goto LABEL_5;
    }
    goto LABEL_38;
  }
  v30 = 72;
  wszCatalogFile = psCatInfo.wszCatalogFile;
  v33 = a1;
  v34 = v8;
  v35 = pbHash;
  v36 = (int)pcbHash;
  v32 = 0;
  v23[0] = 88;
  v25 = 2;
  v26 = &v30;
  v24 = 2;
  v12 = 0;
  v27 = 1;
  if ( (a2 & 8) == 0 )
    v12 = 16;
  v29 = v12;
  if ( (a2 & 0x10) == 0 )
    v29 = v12 | 0x1000;
  File = CommonUtil::HrWinVerifyTrust(HWND_MESSAGE|0x2LL, &v37, (__int64)v23);
  if ( File < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_38;
    v15 = 27;
LABEL_30:
    WPP_SF_D(v14[2], v15, v13, (unsigned int)File);
    goto LABEL_38;
  }
  if ( !v28 )
  {
    File = -2147418113;
LABEL_41:
    CryptCATAdminReleaseCatalogContext(phCatAdmin, v4, 0);
    goto LABEL_42;
  }
  File = CommonUtil::UtilMicrosoftCertChainCheck(v28, a2);
  if ( File >= 0 )
  {
    File = 0;
    goto LABEL_38;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v15 = 28;
    goto LABEL_30;
  }
LABEL_38:
  if ( v28 )
    CommonUtil::UtilCloseWinVerifyTrust(v23);
  if ( v4 )
    goto LABEL_41;
LABEL_42:
  if ( phCatAdmin )
    CryptCATAdminReleaseContext(phCatAdmin, 0);
  if ( File == -2147023728 )
    File = -2146762496;
  if ( v8 != (HANDLE)-1LL )
    CloseHandle(v8);
  return (unsigned int)File;
}

```

## disassembly

```asm
0x1400104e4  mov     [rsp-8+arg_10], rbx
0x1400104e9  push    rbp
0x1400104ea  push    rsi
0x1400104eb  push    rdi
0x1400104ec  push    r14
0x1400104ee  push    r15
0x1400104f0  lea     rbp, [rsp-280h]
0x1400104f8  sub     rsp, 380h
0x1400104ff  mov     rax, cs:__security_cookie
0x140010506  xor     rax, rsp
0x140010509  mov     [rbp+2A0h+var_30], rax
0x140010510  mov     r14d, edx
0x140010513  mov     r15, rcx
0x140010516  mov     [rbp+2A0h+var_290], 0AAC56Bh
0x14001051d  mov     [rbp+2A0h+var_28C], 11D0CD44h
0x140010524  mov     [rbp+2A0h+var_288], 0C000C28Ch
0x14001052b  mov     [rbp+2A0h+var_284], 0EE95C24Fh
0x140010532  xor     edx, edx; Val
0x140010534  lea     r8d, [rdx+58h]; Size
0x140010538  lea     rcx, [rsp+3A0h+var_340]; void *
0x14001053d  call    memset_0
0x140010542  xor     edx, edx; Val
0x140010544  lea     r8d, [rdx+48h]; Size
0x140010548  lea     rcx, [rbp+2A0h+var_2E0]; void *
0x14001054c  call    memset_0
0x140010551  xor     edx, edx; Val
0x140010553  mov     r8d, 20Ch; Size
0x140010559  lea     rcx, [rbp+2A0h+psCatInfo]; void *
0x14001055d  call    memset_0
0x140010562  mov     [rsp+3A0h+phCatAdmin], 0
0x14001056b  xor     edi, edi
0x14001056d  mov     dword ptr [rsp+3A0h+pcbHash], 40h ; '@'; void *
0x140010575  mov     [rsp+3A0h+hFile], 0FFFFFFFFFFFFFFFFh
0x14001057e  mov     [rsp+3A0h+var_378], 8000000h; unsigned int
0x140010586  mov     rdx, r15; void **
0x140010589  lea     rcx, [rsp+3A0h+hFile]; this
0x14001058e  call    ?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEBGKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z; CommonUtil::UtilCreateFile(void * *,ushort const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)
0x140010593  mov     ebx, eax
0x140010595  mov     rsi, [rsp+3A0h+hFile]
0x14001059a  test    eax, eax
0x14001059c  jns     short loc_1400105DA
0x14001059e  lea     rax, WPP_GLOBAL_Control
0x1400105a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400105ac  cmp     rcx, rax
0x1400105af  jz      loc_140010807
0x1400105b5  test    byte ptr [rcx+1Ch], 1
0x1400105b9  jz      loc_140010807
0x1400105bf  lea     edx, [rdi+16h]
0x1400105c2  mov     r9d, ebx
0x1400105c5  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x1400105cc  mov     rcx, [rcx+10h]
0x1400105d0  call    WPP_SF_d
0x1400105d5  jmp     loc_140010807
0x1400105da  xor     r9d, r9d; dwFlags
0x1400105dd  lea     r8, [rbp+2A0h+pbHash]; pbHash
0x1400105e4  lea     rdx, [rsp+3A0h+pcbHash]; pcbHash
0x1400105e9  mov     rcx, rsi; hFile
0x1400105ec  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x1400105f2  test    eax, eax
0x1400105f4  jnz     short loc_140010625
0x1400105f6  call    HrGetLastFailure
0x1400105fb  mov     ebx, eax
0x1400105fd  lea     rax, WPP_GLOBAL_Control
0x140010604  mov     rcx, cs:WPP_GLOBAL_Control
0x14001060b  cmp     rcx, rax
0x14001060e  jz      loc_140010807
0x140010614  test    byte ptr [rcx+1Ch], 1
0x140010618  jz      loc_140010807
0x14001061e  mov     edx, 17h
0x140010623  jmp     short loc_1400105C2
0x140010625  xor     r8d, r8d; dwFlags
0x140010628  xor     edx, edx; pgSubsystem
0x14001062a  lea     rcx, [rsp+3A0h+phCatAdmin]; phCatAdmin
0x14001062f  call    cs:__imp_CryptCATAdminAcquireContext
0x140010635  test    eax, eax
0x140010637  jnz     short loc_14001066B
0x140010639  call    HrGetLastFailure
0x14001063e  mov     ebx, eax
0x140010640  lea     rax, WPP_GLOBAL_Control
0x140010647  mov     rcx, cs:WPP_GLOBAL_Control
0x14001064e  cmp     rcx, rax
0x140010651  jz      loc_140010807
0x140010657  test    byte ptr [rcx+1Ch], 1
0x14001065b  jz      loc_140010807
0x140010661  mov     edx, 18h
0x140010666  jmp     loc_1400105C2
0x14001066b  mov     [rsp+3A0h+phPrevCatInfo], 0; phPrevCatInfo
0x140010674  xor     r9d, r9d; dwFlags
0x140010677  mov     r8d, dword ptr [rsp+3A0h+pcbHash]; cbHash
0x14001067c  lea     rdx, [rbp+2A0h+pbHash]; pbHash
0x140010683  mov     rcx, [rsp+3A0h+phCatAdmin]; hCatAdmin
0x140010688  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x14001068e  mov     rdi, rax
0x140010691  test    rax, rax
0x140010694  jnz     short loc_1400106C6
0x140010696  call    HrGetLastFailure
0x14001069b  mov     ebx, eax
0x14001069d  lea     rax, WPP_GLOBAL_Control
0x1400106a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400106ab  cmp     rcx, rax
0x1400106ae  jz      loc_140010807
0x1400106b4  test    byte ptr [rcx+1Ch], 1
0x1400106b8  jz      loc_140010807
0x1400106be  lea     edx, [rdi+19h]
0x1400106c1  jmp     loc_1400105C2
0x1400106c6  mov     [rbp+2A0h+psCatInfo.cbStruct], 20Ch
0x1400106cd  xor     r8d, r8d; dwFlags
0x1400106d0  lea     rdx, [rbp+2A0h+psCatInfo]; psCatInfo
0x1400106d4  mov     rcx, rax; hCatInfo
0x1400106d7  call    cs:__imp_CryptCATCatalogInfoFromContext
0x1400106dd  test    eax, eax
0x1400106df  jnz     short loc_140010713
0x1400106e1  call    HrGetLastFailure
0x1400106e6  mov     ebx, eax
0x1400106e8  lea     rax, WPP_GLOBAL_Control
0x1400106ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400106f6  cmp     rcx, rax
0x1400106f9  jz      loc_140010807
0x1400106ff  test    byte ptr [rcx+1Ch], 1
0x140010703  jz      loc_140010807
0x140010709  mov     edx, 1Ah
0x14001070e  jmp     loc_1400105C2
0x140010713  mov     [rbp+2A0h+var_2E0], 48h ; 'H'
0x14001071a  lea     rax, [rbp+2A0h+psCatInfo.wszCatalogFile]
0x14001071e  mov     [rbp+2A0h+var_2D8], rax
0x140010722  mov     [rbp+2A0h+var_2C8], r15
0x140010726  mov     [rbp+2A0h+var_2C0], rsi
0x14001072a  lea     rax, [rbp+2A0h+pbHash]
0x140010731  mov     [rbp+2A0h+var_2B8], rax
0x140010735  mov     eax, dword ptr [rsp+3A0h+pcbHash]
0x140010739  mov     [rbp+2A0h+var_2B0], eax
0x14001073c  mov     [rbp+2A0h+var_2D0], 0
0x140010744  mov     [rsp+3A0h+var_340], 58h ; 'X'
0x14001074c  mov     ecx, 2
0x140010751  mov     [rbp+2A0h+var_320], ecx
0x140010754  lea     rax, [rbp+2A0h+var_2E0]
0x140010758  mov     [rbp+2A0h+var_318], rax
0x14001075c  mov     [rsp+3A0h+var_328], rcx
0x140010761  xor     eax, eax
0x140010763  mov     [rbp+2A0h+var_310], 1
0x14001076a  test    r14b, 8
0x14001076e  lea     ecx, [rax+10h]
0x140010771  cmovz   eax, ecx
0x140010774  mov     [rbp+2A0h+var_2F8], eax
0x140010777  test    cl, r14b
0x14001077a  jnz     short loc_140010783
0x14001077c  bts     eax, 0Ch
0x140010780  mov     [rbp+2A0h+var_2F8], eax
0x140010783  lea     r8, [rsp+3A0h+var_340]
0x140010788  lea     rdx, [rbp+2A0h+var_290]
0x14001078c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140010790  call    CommonUtil__HrWinVerifyTrust
0x140010795  mov     ebx, eax
0x140010797  test    eax, eax
0x140010799  jns     short loc_1400107C7
0x14001079b  lea     rax, WPP_GLOBAL_Control
0x1400107a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400107a9  cmp     rcx, rax
0x1400107ac  jz      short loc_140010807
0x1400107ae  test    byte ptr [rcx+1Ch], 1
0x1400107b2  jz      short loc_140010807
0x1400107b4  mov     edx, 1Bh
0x1400107b9  mov     r9d, ebx
0x1400107bc  mov     rcx, [rcx+10h]
0x1400107c0  call    WPP_SF_D
0x1400107c5  jmp     short loc_140010807
0x1400107c7  mov     rcx, [rbp+2A0h+var_308]
0x1400107cb  test    rcx, rcx
0x1400107ce  jnz     short loc_1400107D7
0x1400107d0  mov     ebx, 8000FFFFh
0x1400107d5  jmp     short loc_14001081D
0x1400107d7  mov     edx, r14d
0x1400107da  call    CommonUtil__UtilMicrosoftCertChainCheck
0x1400107df  mov     ebx, eax
0x1400107e1  test    eax, eax
0x1400107e3  jns     short loc_140010805
0x1400107e5  lea     rax, WPP_GLOBAL_Control
0x1400107ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400107f3  cmp     rcx, rax
0x1400107f6  jz      short loc_140010807
0x1400107f8  test    byte ptr [rcx+1Ch], 1
0x1400107fc  jz      short loc_140010807
0x1400107fe  mov     edx, 1Ch
0x140010803  jmp     short loc_1400107B9
0x140010805  xor     ebx, ebx
0x140010807  cmp     [rbp+2A0h+var_308], 0
0x14001080c  jz      short loc_140010818
0x14001080e  lea     rcx, [rsp+3A0h+var_340]
0x140010813  call    CommonUtil__UtilCloseWinVerifyTrust
0x140010818  test    rdi, rdi
0x14001081b  jz      short loc_14001082E
0x14001081d  xor     r8d, r8d; dwFlags
0x140010820  mov     rdx, rdi; hCatInfo
0x140010823  mov     rcx, [rsp+3A0h+phCatAdmin]; hCatAdmin
0x140010828  call    cs:__imp_CryptCATAdminReleaseCatalogContext
0x14001082e  mov     rcx, [rsp+3A0h+phCatAdmin]; hCatAdmin
0x140010833  test    rcx, rcx
0x140010836  jz      short loc_140010840
0x140010838  xor     edx, edx; dwFlags
0x14001083a  call    cs:__imp_CryptCATAdminReleaseContext
0x140010840  mov     eax, 800B0100h
0x140010845  cmp     ebx, 80070490h
0x14001084b  cmovz   ebx, eax
0x14001084e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140010852  jz      short loc_14001085D
0x140010854  mov     rcx, rsi; hObject
0x140010857  call    cs:__imp_CloseHandle
0x14001085d  mov     eax, ebx
0x14001085f  mov     rcx, [rbp+2A0h+var_30]
0x140010866  xor     rcx, rsp; StackCookie
0x140010869  call    __security_check_cookie
0x14001086e  mov     rbx, [rsp+3A0h+arg_10]
0x140010876  add     rsp, 380h
0x14001087d  pop     r15
0x14001087f  pop     r14
0x140010881  pop     rdi
0x140010882  pop     rsi
0x140010883  pop     rbp
0x140010884  retn
```
