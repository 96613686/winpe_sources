# CommonUtil::MpUtilMicrosoftCatalogCertCheck

- ea: `0x14000ee14`
- end: `0x14000f1b4`
- name: `CommonUtil::MpUtilMicrosoftCatalogCertCheck`
- size: `928`
- prototype: `__int64 __fastcall(const WCHAR *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140005fdc`

## callees

- `0x1400015f0`
- `0x1400022ec`
- `0x140003040`
- `0x14000d89c`
- `0x14000ed88`
- `0x14000ee14`
- `0x14000f3e4`
- `0x14000f488`
- `0x14000f7c8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000f186`
- `KERNEL32!CloseHandle` at `0x14000f186`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x14000f169`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x14000f169`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x14000ef57`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x14000ef57`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x14000ef14`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x14000ef14`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x14000efff`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x14000efff`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x14000f157`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x14000f157`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x14000efb0`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x14000efb0`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpUtilMicrosoftCatalogCertCheck(const WCHAR *a1, unsigned int a2)
{
  void *v4; // rdi
  const unsigned __int16 *v5; // r8
  int File; // ebx
  HANDLE v7; // rsi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  HCATINFO v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // eax
  DWORD pcbHash; // [rsp+40h] [rbp-C0h] BYREF
  HCATADMIN phCatAdmin; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile[2]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v28[6]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+80h] [rbp-80h]
  int *v31; // [rsp+88h] [rbp-78h]
  int v32; // [rsp+90h] [rbp-70h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  int v34; // [rsp+A8h] [rbp-58h]
  int v35; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR *wszCatalogFile; // [rsp+C8h] [rbp-38h]
  __int64 v37; // [rsp+D0h] [rbp-30h]
  const WCHAR *v38; // [rsp+D8h] [rbp-28h]
  HANDLE v39; // [rsp+E0h] [rbp-20h]
  BYTE *v40; // [rsp+E8h] [rbp-18h]
  DWORD v41; // [rsp+F0h] [rbp-10h]
  GUID v42; // [rsp+110h] [rbp+10h] BYREF
  CATALOG_INFO psCatInfo; // [rsp+120h] [rbp+20h] BYREF
  BYTE pbHash[64]; // [rsp+330h] [rbp+230h] BYREF

  v42.Data1 = 11191659;
  *(_DWORD *)&v42.Data2 = 298896708;
  *(_DWORD *)v42.Data4 = -1073692020;
  *(_DWORD *)&v42.Data4[4] = -292175281;
  memset_0(v28, 0, 0x58u);
  memset_0(&v35, 0, 0x48u);
  memset_0(&psCatInfo, 0, sizeof(psCatInfo));
  phCatAdmin = 0;
  v4 = 0;
  pcbHash = 64;
  hFile[0] = (HANDLE)-1LL;
  File = CommonUtil::UtilCreateFile((CommonUtil *)hFile, a1, v5);
  v7 = hFile[0];
  if ( File >= 0 )
  {
    if ( CryptCATAdminCalcHashFromFileHandle(hFile[0], &pcbHash, pbHash, 0) )
    {
      if ( CryptCATAdminAcquireContext(&phCatAdmin, 0, 0) )
      {
        v16 = CryptCATAdminEnumCatalogFromHash(phCatAdmin, pbHash, pcbHash, 0, 0);
        v4 = v16;
        if ( v16 )
        {
          psCatInfo.cbStruct = 524;
          if ( CryptCATCatalogInfoFromContext(v16, &psCatInfo, 0) )
          {
            v35 = 72;
            wszCatalogFile = psCatInfo.wszCatalogFile;
            v38 = a1;
            v39 = v7;
            v40 = pbHash;
            v41 = pcbHash;
            v37 = 0;
            v28[0] = 88;
            v30 = 2;
            v31 = &v35;
            v29 = 2;
            v23 = 0;
            v32 = 1;
            if ( (a2 & 8) == 0 )
              v23 = 16;
            v34 = v23;
            if ( (a2 & 0x10) == 0 )
              v34 = v23 | 0x1000;
            File = CommonUtil::HrWinVerifyTrust(HWND_MESSAGE|0x2LL, &v42, (__int64)v28);
            if ( File >= 0 )
            {
              if ( !v33 )
              {
                File = -2147418113;
LABEL_40:
                CryptCATAdminReleaseCatalogContext(phCatAdmin, v4, 0);
                goto LABEL_41;
              }
              File = CommonUtil::UtilMicrosoftCertChainCheck(v33, a2);
              if ( File >= 0 )
              {
                File = 0;
              }
              else
              {
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v9 = 28;
                  goto LABEL_29;
                }
              }
            }
            else
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v9 = 27;
                goto LABEL_29;
              }
            }
          }
          else
          {
            File = HrGetLastFailure(v21, v20, v22);
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v9 = 26;
              goto LABEL_29;
            }
          }
        }
        else
        {
          File = HrGetLastFailure(v18, v17, v19);
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v9 = 25;
            goto LABEL_29;
          }
        }
      }
      else
      {
        File = HrGetLastFailure(v14, v13, v15);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 24;
          goto LABEL_29;
        }
      }
    }
    else
    {
      File = HrGetLastFailure(v11, v10, v12);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 23;
        goto LABEL_29;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 22;
LABEL_29:
      WPP_SF_d(v8[2], v9, &WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids, (unsigned int)File);
    }
  }
  if ( v33 )
    CommonUtil::UtilCloseWinVerifyTrust(v28);
  if ( v4 )
    goto LABEL_40;
LABEL_41:
  if ( phCatAdmin )
    CryptCATAdminReleaseContext(phCatAdmin, 0);
  if ( File == -2147023728 )
    File = -2146762496;
  if ( v7 != (HANDLE)-1LL )
    CloseHandle(v7);
  return (unsigned int)File;
}

```

## disassembly

```asm
0x14000ee14  mov     [rsp-8+arg_10], rbx
0x14000ee19  push    rbp
0x14000ee1a  push    rsi
0x14000ee1b  push    rdi
0x14000ee1c  push    r14
0x14000ee1e  push    r15
0x14000ee20  lea     rbp, [rsp-280h]
0x14000ee28  sub     rsp, 380h
0x14000ee2f  mov     rax, cs:__security_cookie
0x14000ee36  xor     rax, rsp
0x14000ee39  mov     [rbp+2A0h+var_30], rax
0x14000ee40  mov     r14d, edx
0x14000ee43  mov     r15, rcx
0x14000ee46  mov     [rbp+2A0h+var_290], 0AAC56Bh
0x14000ee4d  mov     [rbp+2A0h+var_28C], 11D0CD44h
0x14000ee54  mov     [rbp+2A0h+var_288], 0C000C28Ch
0x14000ee5b  mov     [rbp+2A0h+var_284], 0EE95C24Fh
0x14000ee62  xor     edx, edx; Val
0x14000ee64  lea     r8d, [rdx+58h]; Size
0x14000ee68  lea     rcx, [rsp+3A0h+var_340]; void *
0x14000ee6d  call    memset_0
0x14000ee72  xor     edx, edx; Val
0x14000ee74  lea     r8d, [rdx+48h]; Size
0x14000ee78  lea     rcx, [rbp+2A0h+var_2E0]; void *
0x14000ee7c  call    memset_0
0x14000ee81  xor     edx, edx; Val
0x14000ee83  mov     r8d, 20Ch; Size
0x14000ee89  lea     rcx, [rbp+2A0h+psCatInfo]; void *
0x14000ee8d  call    memset_0
0x14000ee92  mov     [rsp+3A0h+phCatAdmin], 0
0x14000ee9b  xor     edi, edi
0x14000ee9d  mov     [rsp+3A0h+pcbHash], 40h ; '@'; void *
0x14000eea5  mov     [rsp+3A0h+hFile], 0FFFFFFFFFFFFFFFFh
0x14000eeae  mov     rdx, r15; void **
0x14000eeb1  lea     rcx, [rsp+3A0h+hFile]; this
0x14000eeb6  call    ?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEBGKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z; CommonUtil::UtilCreateFile(void * *,ushort const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)
0x14000eebb  mov     ebx, eax
0x14000eebd  mov     rsi, [rsp+3A0h+hFile]
0x14000eec2  test    eax, eax
0x14000eec4  jns     short loc_14000EF02
0x14000eec6  lea     rax, WPP_GLOBAL_Control
0x14000eecd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eed4  cmp     rcx, rax
0x14000eed7  jz      loc_14000F136
0x14000eedd  test    byte ptr [rcx+1Ch], 1
0x14000eee1  jz      loc_14000F136
0x14000eee7  lea     edx, [rdi+16h]
0x14000eeea  mov     r9d, ebx
0x14000eeed  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x14000eef4  mov     rcx, [rcx+10h]
0x14000eef8  call    WPP_SF_d
0x14000eefd  jmp     loc_14000F136
0x14000ef02  xor     r9d, r9d; dwFlags
0x14000ef05  lea     r8, [rbp+2A0h+pbHash]; pbHash
0x14000ef0c  lea     rdx, [rsp+3A0h+pcbHash]; pcbHash
0x14000ef11  mov     rcx, rsi; hFile
0x14000ef14  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x14000ef1a  test    eax, eax
0x14000ef1c  jnz     short loc_14000EF4D
0x14000ef1e  call    HrGetLastFailure
0x14000ef23  mov     ebx, eax
0x14000ef25  lea     rax, WPP_GLOBAL_Control
0x14000ef2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef33  cmp     rcx, rax
0x14000ef36  jz      loc_14000F136
0x14000ef3c  test    byte ptr [rcx+1Ch], 1
0x14000ef40  jz      loc_14000F136
0x14000ef46  mov     edx, 17h
0x14000ef4b  jmp     short loc_14000EEEA
0x14000ef4d  xor     r8d, r8d; dwFlags
0x14000ef50  xor     edx, edx; pgSubsystem
0x14000ef52  lea     rcx, [rsp+3A0h+phCatAdmin]; phCatAdmin
0x14000ef57  call    cs:__imp_CryptCATAdminAcquireContext
0x14000ef5d  test    eax, eax
0x14000ef5f  jnz     short loc_14000EF93
0x14000ef61  call    HrGetLastFailure
0x14000ef66  mov     ebx, eax
0x14000ef68  lea     rax, WPP_GLOBAL_Control
0x14000ef6f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef76  cmp     rcx, rax
0x14000ef79  jz      loc_14000F136
0x14000ef7f  test    byte ptr [rcx+1Ch], 1
0x14000ef83  jz      loc_14000F136
0x14000ef89  mov     edx, 18h
0x14000ef8e  jmp     loc_14000EEEA
0x14000ef93  mov     [rsp+3A0h+phPrevCatInfo], 0; phPrevCatInfo
0x14000ef9c  xor     r9d, r9d; dwFlags
0x14000ef9f  mov     r8d, [rsp+3A0h+pcbHash]; cbHash
0x14000efa4  lea     rdx, [rbp+2A0h+pbHash]; pbHash
0x14000efab  mov     rcx, [rsp+3A0h+phCatAdmin]; hCatAdmin
0x14000efb0  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x14000efb6  mov     rdi, rax
0x14000efb9  test    rax, rax
0x14000efbc  jnz     short loc_14000EFEE
0x14000efbe  call    HrGetLastFailure
0x14000efc3  mov     ebx, eax
0x14000efc5  lea     rax, WPP_GLOBAL_Control
0x14000efcc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000efd3  cmp     rcx, rax
0x14000efd6  jz      loc_14000F136
0x14000efdc  test    byte ptr [rcx+1Ch], 1
0x14000efe0  jz      loc_14000F136
0x14000efe6  lea     edx, [rdi+19h]
0x14000efe9  jmp     loc_14000EEEA
0x14000efee  mov     [rbp+2A0h+psCatInfo.cbStruct], 20Ch
0x14000eff5  xor     r8d, r8d; dwFlags
0x14000eff8  lea     rdx, [rbp+2A0h+psCatInfo]; psCatInfo
0x14000effc  mov     rcx, rax; hCatInfo
0x14000efff  call    cs:__imp_CryptCATCatalogInfoFromContext
0x14000f005  test    eax, eax
0x14000f007  jnz     short loc_14000F03B
0x14000f009  call    HrGetLastFailure
0x14000f00e  mov     ebx, eax
0x14000f010  lea     rax, WPP_GLOBAL_Control
0x14000f017  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f01e  cmp     rcx, rax
0x14000f021  jz      loc_14000F136
0x14000f027  test    byte ptr [rcx+1Ch], 1
0x14000f02b  jz      loc_14000F136
0x14000f031  mov     edx, 1Ah
0x14000f036  jmp     loc_14000EEEA
0x14000f03b  mov     [rbp+2A0h+var_2E0], 48h ; 'H'
0x14000f042  lea     rax, [rbp+2A0h+psCatInfo.wszCatalogFile]
0x14000f046  mov     [rbp+2A0h+var_2D8], rax
0x14000f04a  mov     [rbp+2A0h+var_2C8], r15
0x14000f04e  mov     [rbp+2A0h+var_2C0], rsi
0x14000f052  lea     rax, [rbp+2A0h+pbHash]
0x14000f059  mov     [rbp+2A0h+var_2B8], rax
0x14000f05d  mov     eax, [rsp+3A0h+pcbHash]
0x14000f061  mov     [rbp+2A0h+var_2B0], eax
0x14000f064  mov     [rbp+2A0h+var_2D0], 0
0x14000f06c  mov     [rsp+3A0h+var_340], 58h ; 'X'
0x14000f074  mov     ecx, 2
0x14000f079  mov     [rbp+2A0h+var_320], ecx
0x14000f07c  lea     rax, [rbp+2A0h+var_2E0]
0x14000f080  mov     [rbp+2A0h+var_318], rax
0x14000f084  mov     [rsp+3A0h+var_328], rcx
0x14000f089  xor     eax, eax
0x14000f08b  mov     [rbp+2A0h+var_310], 1
0x14000f092  test    r14b, 8
0x14000f096  lea     ecx, [rax+10h]
0x14000f099  cmovz   eax, ecx
0x14000f09c  mov     [rbp+2A0h+var_2F8], eax
0x14000f09f  test    cl, r14b
0x14000f0a2  jnz     short loc_14000F0AB
0x14000f0a4  bts     eax, 0Ch
0x14000f0a8  mov     [rbp+2A0h+var_2F8], eax
0x14000f0ab  lea     r8, [rsp+3A0h+var_340]
0x14000f0b0  lea     rdx, [rbp+2A0h+var_290]
0x14000f0b4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000f0b8  call    CommonUtil__HrWinVerifyTrust
0x14000f0bd  mov     ebx, eax
0x14000f0bf  test    eax, eax
0x14000f0c1  jns     short loc_14000F0F6
0x14000f0c3  lea     rax, WPP_GLOBAL_Control
0x14000f0ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f0d1  cmp     rcx, rax
0x14000f0d4  jz      short loc_14000F136
0x14000f0d6  test    byte ptr [rcx+1Ch], 1
0x14000f0da  jz      short loc_14000F136
0x14000f0dc  mov     edx, 1Bh
0x14000f0e1  mov     r9d, ebx
0x14000f0e4  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x14000f0eb  mov     rcx, [rcx+10h]
0x14000f0ef  call    WPP_SF_d
0x14000f0f4  jmp     short loc_14000F136
0x14000f0f6  mov     rcx, [rbp+2A0h+var_308]
0x14000f0fa  test    rcx, rcx
0x14000f0fd  jnz     short loc_14000F106
0x14000f0ff  mov     ebx, 8000FFFFh
0x14000f104  jmp     short loc_14000F14C
0x14000f106  mov     edx, r14d
0x14000f109  call    CommonUtil__UtilMicrosoftCertChainCheck
0x14000f10e  mov     ebx, eax
0x14000f110  test    eax, eax
0x14000f112  jns     short loc_14000F134
0x14000f114  lea     rax, WPP_GLOBAL_Control
0x14000f11b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f122  cmp     rcx, rax
0x14000f125  jz      short loc_14000F136
0x14000f127  test    byte ptr [rcx+1Ch], 1
0x14000f12b  jz      short loc_14000F136
0x14000f12d  mov     edx, 1Ch
0x14000f132  jmp     short loc_14000F0E1
0x14000f134  xor     ebx, ebx
0x14000f136  cmp     [rbp+2A0h+var_308], 0
0x14000f13b  jz      short loc_14000F147
0x14000f13d  lea     rcx, [rsp+3A0h+var_340]
0x14000f142  call    CommonUtil__UtilCloseWinVerifyTrust
0x14000f147  test    rdi, rdi
0x14000f14a  jz      short loc_14000F15D
0x14000f14c  xor     r8d, r8d; dwFlags
0x14000f14f  mov     rdx, rdi; hCatInfo
0x14000f152  mov     rcx, [rsp+3A0h+phCatAdmin]; hCatAdmin
0x14000f157  call    cs:__imp_CryptCATAdminReleaseCatalogContext
0x14000f15d  mov     rcx, [rsp+3A0h+phCatAdmin]; hCatAdmin
0x14000f162  test    rcx, rcx
0x14000f165  jz      short loc_14000F16F
0x14000f167  xor     edx, edx; dwFlags
0x14000f169  call    cs:__imp_CryptCATAdminReleaseContext
0x14000f16f  mov     eax, 800B0100h
0x14000f174  cmp     ebx, 80070490h
0x14000f17a  cmovz   ebx, eax
0x14000f17d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000f181  jz      short loc_14000F18C
0x14000f183  mov     rcx, rsi; hObject
0x14000f186  call    cs:__imp_CloseHandle
0x14000f18c  mov     eax, ebx
0x14000f18e  mov     rcx, [rbp+2A0h+var_30]
0x14000f195  xor     rcx, rsp; StackCookie
0x14000f198  call    __security_check_cookie
0x14000f19d  mov     rbx, [rsp+3A0h+arg_10]
0x14000f1a5  add     rsp, 380h
0x14000f1ac  pop     r15
0x14000f1ae  pop     r14
0x14000f1b0  pop     rdi
0x14000f1b1  pop     rsi
0x14000f1b2  pop     rbp
0x14000f1b3  retn
```
