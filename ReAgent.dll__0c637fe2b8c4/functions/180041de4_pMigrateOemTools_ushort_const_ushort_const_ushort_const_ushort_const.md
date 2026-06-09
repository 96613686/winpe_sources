# pMigrateOemTools(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180041de4`
- end: `0x18004231d`
- name: `?pMigrateOemTools@@YAHPEBG000@Z`
- size: `1337`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18002f4c0`
- `0x180042b6c`

## callees

- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x1800109f8`
- `0x18001de7c`
- `0x180025a60`
- `0x180026158`
- `0x18003e150`
- `0x18003e1dc`
- `0x180041de4`
- `0x18004d52c`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005cff0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180041f5e`
- `KERNEL32!GetLastError` at `0x180042079`
- `KERNEL32!GetLastError` at `0x1800420bb`
- `KERNEL32!GetLastError` at `0x1800420e1`
- `KERNEL32!GetLastError` at `0x18004212b`
- `KERNEL32!GetLastError` at `0x180042155`
- `KERNEL32!GetLastError` at `0x180042189`
- `KERNEL32!GetLastError` at `0x1800421f7`
- `KERNEL32!GetLastError` at `0x18004225b`
- `KERNEL32!GetLastError` at `0x1800422c8`
- `KERNEL32!GetLastError` at `0x180041f5e`
- `KERNEL32!GetLastError` at `0x180042079`
- `KERNEL32!GetLastError` at `0x1800420bb`
- `KERNEL32!GetLastError` at `0x1800420e1`
- `KERNEL32!GetLastError` at `0x18004212b`
- `KERNEL32!GetLastError` at `0x180042155`
- `KERNEL32!GetLastError` at `0x180042189`
- `KERNEL32!GetLastError` at `0x1800421f7`
- `KERNEL32!GetLastError` at `0x18004225b`
- `KERNEL32!GetLastError` at `0x1800422c8`
- `WIMGAPI!WIMCloseHandle` at `0x1800422a9`
- `WIMGAPI!WIMCloseHandle` at `0x1800422e5`
- `WIMGAPI!WIMCloseHandle` at `0x1800422a9`
- `WIMGAPI!WIMCloseHandle` at `0x1800422e5`
- `WIMGAPI!WIMSetTemporaryPath` at `0x1800420d7`
- `WIMGAPI!WIMSetTemporaryPath` at `0x1800420d7`
- `WIMGAPI!WIMRegisterMessageCallback` at `0x18004214b`
- `WIMGAPI!WIMRegisterMessageCallback` at `0x18004214b`
- `WIMGAPI!WIMApplyImage` at `0x18004217f`
- `WIMGAPI!WIMApplyImage` at `0x18004217f`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x1800422be`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x1800422be`
- `WIMGAPI!WIMCreateFile` at `0x1800420ad`
- `WIMGAPI!WIMCreateFile` at `0x1800420ad`
- `WIMGAPI!WIMLoadImage` at `0x18004211d`
- `WIMGAPI!WIMLoadImage` at `0x18004211d`
- `ole32!CoTaskMemFree` at `0x18004229b`
- `ole32!CoTaskMemFree` at `0x18004229b`

## string_xrefs

- `0x180041f64`: `pMigrateOemTools AppendPath failed. Error: 0x%x`
- `0x180041fac`: `pMigrateOemTools Downlevel WinRE image path: %s`
- `0x18004207f`: `pMigrateOemTools SecureGetTempPathW failed. Error: 0x%x`
- `0x1800420c1`: `pMigrateOemTools WIMCreateFile failed. Error: 0x%x`
- `0x1800420e7`: `pMigrateOemTools WIMSetTemporaryPath failed. Error: 0x%x`
- `0x18004218f`: `pMigrateOemTools WIMExtractImageDirectory failed. Error: 0x%x`
- `0x1800421fd`: `pMigrateOemTools failed to set WinRE config. Error: 0x%x`
- `0x18004222d`: `pMigrateOemToolsfailed to get recovery file path`
- `0x180042211`: `ReCustomization.xml`

## pseudocode

```c
__int64 __fastcall pMigrateOemTools(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  void *v7; // r15
  int v8; // eax
  __int16 v9; // bx
  const unsigned __int16 *v10; // rsi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  const unsigned __int16 *v13; // r8
  DWORD LastError; // eax
  const wchar_t *v15; // rdx
  __int64 v16; // rbx
  int v17; // eax
  __int16 v18; // bx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rsi
  DWORD v23; // eax
  const wchar_t *v24; // rdx
  __int64 v25; // r14
  DWORD v26; // eax
  const wchar_t *v27; // rdx
  __int64 v28; // r12
  DWORD v29; // eax
  unsigned int v31; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v32; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v34; // [rsp+48h] [rbp-B8h]
  __int128 v35; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v36[227]; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+77Ch] [rbp+67Ch]
  int v38; // [rsp+780h] [rbp+680h]
  int v39; // [rsp+790h] [rbp+690h]
  unsigned __int16 v40; // [rsp+9F0h] [rbp+8F0h] BYREF
  _BYTE v41[606]; // [rsp+9F2h] [rbp+8F2h] BYREF
  unsigned __int16 v42; // [rsp+C50h] [rbp+B50h] BYREF
  _BYTE v43[606]; // [rsp+C52h] [rbp+B52h] BYREF
  unsigned __int16 v44; // [rsp+EB0h] [rbp+DB0h] BYREF
  _BYTE v45[606]; // [rsp+EB2h] [rbp+DB2h] BYREF

  v34 = a3;
  v31 = 0;
  v40 = 0;
  memset_0(v41, 0, 0x25Au);
  v44 = 0;
  memset_0(v45, 0, 0x25Au);
  v42 = 0;
  memset_0(v43, 0, 0x25Au);
  v7 = 0;
  pv = 0;
  v35 = 0;
  AsmMigrateOemToolsStart(a2);
  if ( !a1 || !a2 )
  {
    v22 = 0;
    v25 = 0;
    UnattendLogW(1, L"pMigrateOemTools Invalid arguments specified.");
    LODWORD(v16) = 87;
    goto LABEL_59;
  }
  v32 = 0;
  v8 = StringCchLengthW(a2, 0x7FFFFFFFu, &v32);
  v9 = v8;
  v10 = L"%s\\%s";
  if ( v8 >= 0 )
  {
    if ( !v32 || (v13 = L"%s\\%s", a2[v32 - 1] == 92) )
      v13 = L"%s%s";
    v8 = StringCchPrintfW(&v40, 0x12Eu, v13, a2, L"Winre.wim");
    v9 = v8;
    if ( v8 >= 0 )
      goto LABEL_18;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 15;
      goto LABEL_14;
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 14;
LABEL_14:
      WPP_SF_d(v11[2], v12, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v8);
    }
  }
  if ( v9 )
  {
LABEL_16:
    LastError = GetLastError();
    v15 = L"pMigrateOemTools AppendPath failed. Error: 0x%x";
LABEL_17:
    LODWORD(v16) = LastError;
    UnattendLogW(1, v15, LastError);
    goto LABEL_67;
  }
LABEL_18:
  if ( Utils::DoesPathExist(&v40) )
  {
    LODWORD(v16) = 3;
    UnattendLogW(0, L"pMigrateOemTools Downlevel WinRE.wim not found. There's nothing to migrate.");
    goto LABEL_67;
  }
  UnattendLogW(0, L"pMigrateOemTools Downlevel WinRE image path: %s", &v40);
  v32 = 0;
  v17 = StringCchLengthW(a1, 0x7FFFFFFFu, &v32);
  v18 = v17;
  if ( v17 >= 0 )
  {
    if ( !v32 || a1[v32 - 1] == 92 )
      v10 = L"%s%s";
    v17 = StringCchPrintfW(&v44, 0x12Eu, v10, a1, L"Sources\\Recovery\\Tools");
    v18 = v17;
    if ( v17 >= 0 )
      goto LABEL_33;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v20 = 15;
      goto LABEL_31;
    }
  }
  else
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v20 = 14;
LABEL_31:
      WPP_SF_d(v19[2], v20, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v17);
    }
  }
  if ( v18 )
    goto LABEL_16;
LABEL_33:
  if ( !(unsigned int)SecureGetTempPathW(0x12Eu, &v42) )
  {
    LastError = GetLastError();
    v15 = L"pMigrateOemTools SecureGetTempPathW failed. Error: 0x%x";
    goto LABEL_17;
  }
  v21 = WIMCreateFile(&v40, 0x80000000LL, 3, 0x20000000, 0, 0);
  v22 = v21;
  if ( !v21 )
  {
    LastError = GetLastError();
    v15 = L"pMigrateOemTools WIMCreateFile failed. Error: 0x%x";
    goto LABEL_17;
  }
  if ( (unsigned int)WIMSetTemporaryPath(v21, &v42) )
  {
    *((_QWORD *)&v35 + 1) = 0;
    *(_QWORD *)&v35 = &v44;
    v25 = WIMLoadImage(v22, 1);
    if ( !v25 )
    {
      v23 = GetLastError();
      v24 = L"pMigrateOemTools WIMLoadImage failed. Error: 0x%x";
      goto LABEL_39;
    }
    if ( (unsigned int)WIMRegisterMessageCallback(v22, ApplyOemToolsCallback, &v35) )
    {
      v26 = GetLastError();
      v27 = L"pMigrateOemTools WIMRegisterMessageCallback failed. Error: 0x%x";
LABEL_44:
      LODWORD(v16) = v26;
      UnattendLogW(1, v27, v26);
      goto LABEL_62;
    }
    if ( !(unsigned int)WIMApplyImage(v25, a1, 128) )
    {
      v26 = GetLastError();
      v27 = L"pMigrateOemTools WIMExtractImageDirectory failed. Error: 0x%x";
      goto LABEL_44;
    }
    LODWORD(v16) = 0;
    if ( !DWORD2(v35) )
      goto LABEL_57;
    if ( !a4 )
      goto LABEL_57;
    v28 = (__int64)v34;
    if ( !v34 )
      goto LABEL_57;
    memset_0(v36, 0, 0x990u);
    v36[0] = 2448;
    v37 = 1;
    v38 = 1;
    v39 = 1;
    if ( !WinReSetConfigInternal((__int64)v36, a4) )
    {
      v26 = GetLastError();
      v27 = L"pMigrateOemTools failed to set WinRE config. Error: 0x%x";
      goto LABEL_44;
    }
    LODWORD(v16) = winreGetRecoveryFilePath(v28, 1, 1, L"ReCustomization.xml", (unsigned __int16 **)&pv);
    if ( (_DWORD)v16 )
    {
      UnattendLogW(1, L"pMigrateOemToolsfailed to get recovery file path");
      v7 = pv;
      goto LABEL_59;
    }
    v7 = pv;
    if ( pv && !WinReSetCustomizationInternal((__int64)a4, (unsigned __int16 *)pv) )
    {
      v16 = GetLastError();
      UnattendLogW(1, L"pMigrateOemTools failed to set WinRE customization. Error: 0x%x", v16);
    }
    else
    {
LABEL_57:
      v31 = 1;
    }
LABEL_59:
    if ( v7 )
      CoTaskMemFree(v7);
    if ( !v25 )
    {
LABEL_63:
      if ( !v22 )
        goto LABEL_67;
      goto LABEL_64;
    }
LABEL_62:
    WIMCloseHandle(v25);
    goto LABEL_63;
  }
  v23 = GetLastError();
  v24 = L"pMigrateOemTools WIMSetTemporaryPath failed. Error: 0x%x";
LABEL_39:
  LODWORD(v16) = v23;
  UnattendLogW(1, v24, v23);
LABEL_64:
  if ( !(unsigned int)WIMUnregisterMessageCallback(v22, ApplyOemToolsCallback) )
  {
    v29 = GetLastError();
    UnattendLogW(2, L"pMigrateOemTools WIMUnregisterMessageCallback failed. Error: 0x%x", v29);
  }
  WIMCloseHandle(v22);
LABEL_67:
  AsmMigrateOemToolsEnd(v31, v16);
  return v31;
}

```

## disassembly

```asm
0x180041de4  push    rbp
0x180041de6  push    rbx
0x180041de7  push    rsi
0x180041de8  push    rdi
0x180041de9  push    r12
0x180041deb  push    r13
0x180041ded  push    r14
0x180041def  push    r15
0x180041df1  lea     rbp, [rsp-1028h]
0x180041df9  mov     eax, 1128h
0x180041dfe  call    _alloca_probe
0x180041e03  sub     rsp, rax
0x180041e06  mov     rax, cs:__security_cookie
0x180041e0d  xor     rax, rsp
0x180041e10  mov     [rbp+1060h+var_50], rax
0x180041e17  mov     [rsp+1160h+var_1118], r8
0x180041e1c  mov     rdi, rdx
0x180041e1f  mov     r12, rcx
0x180041e22  mov     [rsp+1160h+var_1130], 0
0x180041e2a  xor     eax, eax
0x180041e2c  lea     rcx, [rbp+1060h+var_76E]; void *
0x180041e33  mov     ebx, 25Ah
0x180041e38  mov     [rbp+1060h+var_770], ax
0x180041e3f  mov     r8d, ebx; Size
0x180041e42  xor     edx, edx; Val
0x180041e44  mov     r13, r9
0x180041e47  call    memset_0
0x180041e4c  xor     eax, eax
0x180041e4e  lea     rcx, [rbp+1060h+var_2AE]; void *
0x180041e55  mov     r8d, ebx; Size
0x180041e58  mov     [rbp+1060h+var_2B0], ax
0x180041e5f  xor     edx, edx; Val
0x180041e61  call    memset_0
0x180041e66  xor     eax, eax
0x180041e68  lea     rcx, [rbp+1060h+var_50E]; void *
0x180041e6f  mov     r8d, ebx; Size
0x180041e72  mov     [rbp+1060h+var_510], ax
0x180041e79  xor     edx, edx; Val
0x180041e7b  call    memset_0
0x180041e80  xorps   xmm0, xmm0
0x180041e83  xor     r15d, r15d
0x180041e86  mov     rcx, rdi; unsigned __int16 *
0x180041e89  mov     [rsp+1160h+pv], r15
0x180041e8e  movups  [rsp+1160h+var_1110], xmm0
0x180041e93  call    ?AsmMigrateOemToolsStart@@YAXPEBG@Z; AsmMigrateOemToolsStart(ushort const *)
0x180041e98  test    r12, r12
0x180041e9b  jz      loc_18004227C
0x180041ea1  test    rdi, rdi
0x180041ea4  jz      loc_18004227C
0x180041eaa  lea     r8, [rsp+1160h+var_1128]; unsigned __int64 *
0x180041eaf  mov     [rsp+1160h+var_1128], r15
0x180041eb4  mov     edx, 7FFFFFFFh; unsigned __int64
0x180041eb9  mov     rcx, rdi; unsigned __int16 *
0x180041ebc  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180041ec1  lea     r14, WPP_GLOBAL_Control
0x180041ec8  mov     ebx, eax
0x180041eca  lea     rsi, aSS_1; "%s\\%s"
0x180041ed1  test    eax, eax
0x180041ed3  jns     short loc_180041EED
0x180041ed5  mov     rcx, cs:WPP_GLOBAL_Control
0x180041edc  cmp     rcx, r14
0x180041edf  jz      short loc_180041F59
0x180041ee1  test    byte ptr [rcx+1Ch], 2
0x180041ee5  jz      short loc_180041F59
0x180041ee7  lea     edx, [r15+0Eh]
0x180041eeb  jmp     short loc_180041F46
0x180041eed  mov     rax, [rsp+1160h+var_1128]
0x180041ef2  test    rax, rax
0x180041ef5  jz      short loc_180041F02
0x180041ef7  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180041efd  mov     r8, rsi
0x180041f00  jnz     short loc_180041F09
0x180041f02  lea     r8, aSS_2; "%s%s"
0x180041f09  lea     rax, aWinreWim; "Winre.wim"
0x180041f10  mov     r9, rdi
0x180041f13  mov     edx, 12Eh; unsigned __int64
0x180041f18  mov     [rsp+1160h+var_1140], rax
0x180041f1d  lea     rcx, [rbp+1060h+var_770]; unsigned __int16 *
0x180041f24  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041f29  mov     ebx, eax
0x180041f2b  test    eax, eax
0x180041f2d  jns     short loc_180041F7F
0x180041f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f36  cmp     rcx, r14
0x180041f39  jz      short loc_180041F59
0x180041f3b  test    byte ptr [rcx+1Ch], 2
0x180041f3f  jz      short loc_180041F59
0x180041f41  mov     edx, 0Fh
0x180041f46  mov     rcx, [rcx+10h]
0x180041f4a  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180041f51  mov     r9d, eax
0x180041f54  call    WPP_SF_d
0x180041f59  test    bx, bx
0x180041f5c  jz      short loc_180041F7F
0x180041f5e  call    cs:__imp_GetLastError
0x180041f64  lea     rdx, aPmigrateoemtoo_9; "pMigrateOemTools AppendPath failed. Err"...
0x180041f6b  mov     r8d, eax
0x180041f6e  mov     ecx, 1
0x180041f73  mov     ebx, eax
0x180041f75  call    UnattendLogW
0x180041f7a  jmp     loc_1800422EB
0x180041f7f  lea     rcx, [rbp+1060h+var_770]; unsigned __int16 *
0x180041f86  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x180041f8b  xor     ecx, ecx
0x180041f8d  test    eax, eax
0x180041f8f  jz      short loc_180041FA5
0x180041f91  lea     rdx, aPmigrateoemtoo_3; "pMigrateOemTools Downlevel WinRE.wim no"...
0x180041f98  lea     ebx, [rcx+3]
0x180041f9b  call    UnattendLogW
0x180041fa0  jmp     loc_1800422EB
0x180041fa5  lea     r8, [rbp+1060h+var_770]
0x180041fac  lea     rdx, aPmigrateoemtoo_10; "pMigrateOemTools Downlevel WinRE image "...
0x180041fb3  call    UnattendLogW
0x180041fb8  lea     r8, [rsp+1160h+var_1128]; unsigned __int64 *
0x180041fbd  mov     [rsp+1160h+var_1128], r15
0x180041fc2  mov     edx, 7FFFFFFFh; unsigned __int64
0x180041fc7  mov     rcx, r12; unsigned __int16 *
0x180041fca  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180041fcf  mov     ebx, eax
0x180041fd1  test    eax, eax
0x180041fd3  jns     short loc_180041FEE
0x180041fd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180041fdc  cmp     rcx, r14
0x180041fdf  jz      short loc_18004205B
0x180041fe1  test    byte ptr [rcx+1Ch], 2
0x180041fe5  jz      short loc_18004205B
0x180041fe7  mov     edx, 0Eh
0x180041fec  jmp     short loc_180042048
0x180041fee  mov     rax, [rsp+1160h+var_1128]
0x180041ff3  test    rax, rax
0x180041ff6  jz      short loc_180042001
0x180041ff8  cmp     word ptr [r12+rax*2-2], 5Ch ; '\'
0x180041fff  jnz     short loc_180042008
0x180042001  lea     rsi, aSS_2; "%s%s"
0x180042008  lea     rax, aSourcesRecover; "Sources\\Recovery\\Tools"
0x18004200f  mov     r9, r12
0x180042012  mov     r8, rsi; unsigned __int16 *
0x180042015  mov     [rsp+1160h+var_1140], rax
0x18004201a  mov     edx, 12Eh; unsigned __int64
0x18004201f  lea     rcx, [rbp+1060h+var_2B0]; unsigned __int16 *
0x180042026  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004202b  mov     ebx, eax
0x18004202d  test    eax, eax
0x18004202f  jns     short loc_180042064
0x180042031  mov     rcx, cs:WPP_GLOBAL_Control
0x180042038  cmp     rcx, r14
0x18004203b  jz      short loc_18004205B
0x18004203d  test    byte ptr [rcx+1Ch], 2
0x180042041  jz      short loc_18004205B
0x180042043  mov     edx, 0Fh
0x180042048  mov     rcx, [rcx+10h]
0x18004204c  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180042053  mov     r9d, eax
0x180042056  call    WPP_SF_d
0x18004205b  test    bx, bx
0x18004205e  jnz     loc_180041F5E
0x180042064  lea     rdx, [rbp+1060h+var_510]; unsigned __int16 *
0x18004206b  mov     ecx, 12Eh; unsigned int
0x180042070  call    ?SecureGetTempPathW@@YAKKPEAG@Z; SecureGetTempPathW(ulong,ushort *)
0x180042075  test    eax, eax
0x180042077  jnz     short loc_18004208B
0x180042079  call    cs:__imp_GetLastError
0x18004207f  lea     rdx, aPmigrateoemtoo_0; "pMigrateOemTools SecureGetTempPathW fai"...
0x180042086  jmp     loc_180041F6B
0x18004208b  mov     [rsp+1160h+var_1138], r15
0x180042090  lea     rcx, [rbp+1060h+var_770]
0x180042097  mov     edx, 80000000h
0x18004209c  mov     dword ptr [rsp+1160h+var_1140], r15d
0x1800420a1  mov     r9d, 20000000h
0x1800420a7  mov     r8d, 3
0x1800420ad  call    cs:__imp_WIMCreateFile
0x1800420b3  mov     rsi, rax
0x1800420b6  test    rax, rax
0x1800420b9  jnz     short loc_1800420CD
0x1800420bb  call    cs:__imp_GetLastError
0x1800420c1  lea     rdx, aPmigrateoemtoo_4; "pMigrateOemTools WIMCreateFile failed. "...
0x1800420c8  jmp     loc_180041F6B
0x1800420cd  lea     rdx, [rbp+1060h+var_510]
0x1800420d4  mov     rcx, rsi
0x1800420d7  call    cs:__imp_WIMSetTemporaryPath
0x1800420dd  test    eax, eax
0x1800420df  jnz     short loc_180042102
0x1800420e1  call    cs:__imp_GetLastError
0x1800420e7  lea     rdx, aPmigrateoemtoo_1; "pMigrateOemTools WIMSetTemporaryPath fa"...
0x1800420ee  mov     ecx, 1
0x1800420f3  mov     r8d, eax
0x1800420f6  mov     ebx, eax
0x1800420f8  call    UnattendLogW
0x1800420fd  jmp     loc_1800422B4
0x180042102  lea     rax, [rbp+1060h+var_2B0]
0x180042109  mov     qword ptr [rsp+1160h+var_1110+8], r15
0x18004210e  mov     edi, 1
0x180042113  mov     qword ptr [rsp+1160h+var_1110], rax
0x180042118  mov     edx, edi
0x18004211a  mov     rcx, rsi
0x18004211d  call    cs:__imp_WIMLoadImage
0x180042123  mov     r14, rax
0x180042126  test    rax, rax
0x180042129  jnz     short loc_18004213C
0x18004212b  call    cs:__imp_GetLastError
0x180042131  lea     rdx, aPmigrateoemtoo_5; "pMigrateOemTools WIMLoadImage failed. E"...
0x180042138  mov     ecx, edi
0x18004213a  jmp     short loc_1800420F3
0x18004213c  lea     r8, [rsp+1160h+var_1110]
0x180042141  mov     rcx, rsi
0x180042144  lea     rdx, ?ApplyOemToolsCallback@@YAKK_K_JPEAX@Z; ApplyOemToolsCallback(ulong,unsigned __int64,__int64,void *)
0x18004214b  call    cs:__imp_WIMRegisterMessageCallback
0x180042151  test    eax, eax
0x180042153  jz      short loc_180042173
0x180042155  call    cs:__imp_GetLastError
0x18004215b  lea     rdx, aPmigrateoemtoo_6; "pMigrateOemTools WIMRegisterMessageCall"...
0x180042162  mov     r8d, eax
0x180042165  mov     ecx, edi
0x180042167  mov     ebx, eax
0x180042169  call    UnattendLogW
0x18004216e  jmp     loc_1800422A6
0x180042173  mov     r8d, 80h
0x180042179  mov     rdx, r12
0x18004217c  mov     rcx, r14
0x18004217f  call    cs:__imp_WIMApplyImage
0x180042185  test    eax, eax
0x180042187  jnz     short loc_180042198
0x180042189  call    cs:__imp_GetLastError
0x18004218f  lea     rdx, aPmigrateoemtoo_2; "pMigrateOemTools WIMExtractImageDirecto"...
0x180042196  jmp     short loc_180042162
0x180042198  xor     ebx, ebx
0x18004219a  cmp     dword ptr [rsp+1160h+var_1110+8], ebx
0x18004219e  jz      loc_180042276
0x1800421a4  test    r13, r13
0x1800421a7  jz      loc_180042276
0x1800421ad  mov     r12, [rsp+1160h+var_1118]
0x1800421b2  test    r12, r12
0x1800421b5  jz      loc_180042276
0x1800421bb  mov     ebx, 990h
0x1800421c0  lea     rcx, [rsp+1160h+var_1100]; void *
0x1800421c5  mov     r8d, ebx; Size
0x1800421c8  xor     edx, edx; Val
0x1800421ca  call    memset_0
0x1800421cf  mov     rdx, r13
0x1800421d2  mov     [rsp+1160h+var_1100], rbx
0x1800421d7  lea     rcx, [rsp+1160h+var_1100]
0x1800421dc  mov     [rbp+1060h+var_9E4], edi
0x1800421e2  mov     [rbp+1060h+var_9E0], edi
0x1800421e8  mov     [rbp+1060h+var_9D0], edi
0x1800421ee  call    WinReSetConfigInternal
0x1800421f3  test    eax, eax
0x1800421f5  jnz     short loc_180042209
0x1800421f7  call    cs:__imp_GetLastError
0x1800421fd  lea     rdx, aPmigrateoemtoo_7; "pMigrateOemTools failed to set WinRE co"...
0x180042204  jmp     loc_180042162
0x180042209  lea     rax, [rsp+1160h+pv]
0x18004220e  mov     r8d, edi
0x180042211  lea     r9, aRecustomizatio_2; "ReCustomization.xml"
0x180042218  mov     [rsp+1160h+var_1140], rax
0x18004221d  mov     edx, edi
0x18004221f  mov     rcx, r12
0x180042222  call    winreGetRecoveryFilePath
0x180042227  mov     ebx, eax
0x180042229  test    eax, eax
0x18004222b  jz      short loc_180042242
0x18004222d  lea     rdx, aPmigrateoemtoo_12; "pMigrateOemToolsfailed to get recovery "...
0x180042234  mov     ecx, edi
0x180042236  call    UnattendLogW
0x18004223b  mov     r15, [rsp+1160h+pv]
0x180042240  jmp     short loc_180042293
0x180042242  mov     r15, [rsp+1160h+pv]
0x180042247  test    r15, r15
0x18004224a  jz      short loc_180042276
0x18004224c  mov     rdx, r15
0x18004224f  mov     rcx, r13
0x180042252  call    WinReSetCustomizationInternal
0x180042257  test    eax, eax
0x180042259  jnz     short loc_180042276
0x18004225b  call    cs:__imp_GetLastError
0x180042261  lea     rdx, aPmigrateoemtoo_11; "pMigrateOemTools failed to set WinRE cu"...
0x180042268  mov     ecx, edi
0x18004226a  mov     r8d, eax
0x18004226d  mov     ebx, eax
0x18004226f  call    UnattendLogW
0x180042274  jmp     short loc_180042293
0x180042276  mov     [rsp+1160h+var_1130], edi
0x18004227a  jmp     short loc_180042293
0x18004227c  xor     esi, esi
0x18004227e  lea     rdx, aPmigrateoemtoo_8; "pMigrateOemTools Invalid arguments spec"...
0x180042285  xor     r14d, r14d
0x180042288  lea     ecx, [rsi+1]
0x18004228b  call    UnattendLogW
0x180042290  lea     ebx, [rsi+57h]
0x180042293  test    r15, r15
0x180042296  jz      short loc_1800422A1
0x180042298  mov     rcx, r15; pv
0x18004229b  call    cs:__imp_CoTaskMemFree
0x1800422a1  test    r14, r14
0x1800422a4  jz      short loc_1800422AF
0x1800422a6  mov     rcx, r14
0x1800422a9  call    cs:__imp_WIMCloseHandle
0x1800422af  test    rsi, rsi
0x1800422b2  jz      short loc_1800422EB
0x1800422b4  lea     rdx, ?ApplyOemToolsCallback@@YAKK_K_JPEAX@Z; ApplyOemToolsCallback(ulong,unsigned __int64,__int64,void *)
0x1800422bb  mov     rcx, rsi
  ... truncated ...
```
