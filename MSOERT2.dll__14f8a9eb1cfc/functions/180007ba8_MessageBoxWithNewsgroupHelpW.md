# MessageBoxWithNewsgroupHelpW

- ea: `0x180007ba8`
- end: `0x180007f6b`
- name: `MessageBoxWithNewsgroupHelpW`
- size: `963`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007840`
- `0x18000c570`

## callees

- `0x1800010f0`
- `0x180001c80`
- `0x180004640`
- `0x18000470c`
- `0x180006ac0`
- `0x180007768`
- `0x180007ba8`
- `0x180012d6c`
- `0x180012f8e`
- `0x180012fc0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180007e70`
- `KERNEL32!LocalFree` at `0x180007e80`
- `KERNEL32!LocalFree` at `0x180007f3a`
- `KERNEL32!LocalFree` at `0x180007e70`
- `KERNEL32!LocalFree` at `0x180007e80`
- `KERNEL32!LocalFree` at `0x180007f3a`
- `KERNEL32!LocalAlloc` at `0x180007d2b`
- `KERNEL32!LocalAlloc` at `0x180007d2b`
- `KERNEL32!DeactivateActCtx` at `0x180007f28`
- `KERNEL32!DeactivateActCtx` at `0x180007f28`
- `KERNEL32!ReleaseActCtx` at `0x180007f31`
- `KERNEL32!ReleaseActCtx` at `0x180007f31`
- `SHLWAPI!SHRegGetBoolUSValueA` at `0x180007c70`
- `SHLWAPI!SHRegGetBoolUSValueA` at `0x180007c70`
- `USER32!LoadStringW` at `0x180007cb3`
- `USER32!LoadStringW` at `0x180007cd4`
- `USER32!LoadStringW` at `0x180007cb3`
- `USER32!LoadStringW` at `0x180007cd4`
- `USER32!DialogBoxParamW` at `0x180007f09`
- `USER32!DialogBoxParamW` at `0x180007f09`

## pseudocode

```c
__int64 __fastcall MessageBoxWithNewsgroupHelpW(
        HINSTANCE a1,
        HWND a2,
        LPARAM a3,
        LPARAM a4,
        unsigned int a5,
        unsigned __int16 *a6,
        const unsigned __int16 *a7,
        __int64 a8,
        const WCHAR *a9,
        const WCHAR *a10,
        const WCHAR *a11,
        const TASKDIALOG_BUTTON *a12,
        UINT a13)
{
  const unsigned __int16 *v14; // r8
  int v15; // r14d
  void *v19; // rsi
  __int64 v20; // rdi
  int StringW; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  unsigned __int16 *v24; // rax
  WCHAR *v25; // rdi
  int v26; // eax
  int v27; // eax
  const WCHAR *pszVerificationText; // rcx
  BOOL *v29; // r9
  __int64 v30; // rcx
  char *v33; // rbx
  unsigned int v34; // edi
  int pnButton[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v36; // [rsp+38h] [rbp-C8h] BYREF
  ULONG_PTR ulCookie; // [rsp+40h] [rbp-C0h] BYREF
  const WCHAR *v38; // [rsp+48h] [rbp-B8h]
  const WCHAR *v39; // [rsp+50h] [rbp-B0h]
  const WCHAR *v40; // [rsp+58h] [rbp-A8h]
  const WCHAR *v41; // [rsp+60h] [rbp-A0h]
  LPCWCH lpSrcStr; // [rsp+68h] [rbp-98h]
  LPARAM dwInitParam[6]; // [rsp+70h] [rbp-90h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v45[512]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR v46[512]; // [rsp+540h] [rbp+440h] BYREF
  WCHAR Buffer[512]; // [rsp+940h] [rbp+840h] BYREF

  v14 = a7;
  v15 = 0;
  lpSrcStr = a9;
  v39 = a10;
  if ( !a7 )
    v14 = (const unsigned __int16 *)a3;
  v41 = a11;
  v38 = (const WCHAR *)a4;
  v40 = (const WCHAR *)a3;
  v36 = 0;
  *(_QWORD *)pnButton = 0;
  GetNewsgroupHelpUrl(a6, 1, v14, 0, (unsigned __int16 **)pnButton);
  v19 = *(void **)pnButton;
  if ( !*(_QWORD *)pnButton )
    return -1;
  if ( SHRegGetBoolUSValueA("Software\\Microsoft\\Windows Mail", "Downlevel MessageBox", 0, 0) )
  {
    dwInitParam[0] = a5;
    dwInitParam[5] = (LPARAM)dwInitParam;
    dwInitParam[4] = (LPARAM)MessageBoxWithNewsgroupHelpDlgProc;
    dwInitParam[1] = a3;
    dwInitParam[2] = a4;
    dwInitParam[3] = (LPARAM)v19;
    ulCookie = 0;
    v33 = (char *)CreateAndActivateContext(&ulCookie);
    v34 = DialogBoxParamW(g_hInst, (LPCWSTR)0x65, a2, MessageBoxWithNewsgroupHelpExDlgProc, (LPARAM)dwInitParam);
    if ( (unsigned __int64)(v33 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( ulCookie )
        DeactivateActCtx(0, ulCookie);
      ReleaseActCtx(v33);
    }
    LocalFree(v19);
    return v34;
  }
  else
  {
    v20 = -1;
    Buffer[0] = 0;
    pnButton[0] = -1;
    v46[0] = 0;
    v45[0] = 0;
    StringW = LoadStringW(g_hInst, 0x7D3u, Buffer, 512);
    v22 = LoadStringW(g_hInst, 0x7D1u, v46, 512);
    if ( StringW <= 0 || v22 <= 0 || (int)StringCchPrintfW(v45, 0x200u, Buffer, v46) < 0 )
    {
      HrGetLastError();
    }
    else
    {
      do
        ++v20;
      while ( v45[v20] );
      v23 = v20 + 1;
      v24 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (unsigned int)(v20 + 1));
      v25 = v24;
      if ( v24 )
      {
        if ( (int)StringCchCopyW(v24, v23, v45) >= 0 )
        {
          memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
          pTaskConfig.hwndParent = a2;
          pTaskConfig.cbSize = 160;
          pTaskConfig.hInstance = a1;
          pTaskConfig.dwFlags = 1;
          if ( a13 )
          {
            pTaskConfig.cButtons = a13;
            pTaskConfig.pButtons = a12;
          }
          else
          {
            v26 = a5 & 0xF;
            if ( v26 == 1 )
            {
              pTaskConfig.dwCommonButtons = 9;
              pTaskConfig.nDefaultButton = ((a5 & 0xF00) == 256) + 1;
            }
            else if ( v26 == 4 )
            {
              pTaskConfig.dwCommonButtons = 6;
              pTaskConfig.nDefaultButton = 7 - ((a5 & 0xF00) != 256);
            }
            else
            {
              pTaskConfig.dwCommonButtons = 1;
            }
          }
          pTaskConfig.pszWindowTitle = v38;
          pTaskConfig.pszMainInstruction = v39;
          pTaskConfig.pszContent = v40;
          pTaskConfig.pszExpandedInformation = v41;
          v27 = FIsEmptyW(lpSrcStr);
          pszVerificationText = pTaskConfig.pszVerificationText;
          v29 = &v36;
          pTaskConfig.pszFooter = v25;
          pTaskConfig.lpCallbackData = (LONG_PTR)v19;
          if ( !v27 )
            pszVerificationText = lpSrcStr;
          LOBYTE(v15) = v27 == 0;
          pTaskConfig.pszVerificationText = pszVerificationText;
          v30 = 0xFFFF;
          if ( (a5 & 0xF0) == 0x40 )
            v30 = 65533;
          pTaskConfig.hMainIcon = (HICON)v30;
          if ( v27 )
            v29 = 0;
          pTaskConfig.pfCallback = (PFTASKDIALOGCALLBACK)TaskDialogWithNewsgroupHelpDlgProc;
          TaskDialogIndirect(&pTaskConfig, pnButton, 0, v29);
        }
        LocalFree(v25);
      }
    }
    LocalFree(v19);
    if ( v15 )
      return (unsigned int)((unsigned __int16)v36 | (LOWORD(pnButton[0]) << 16));
    else
      return (unsigned int)pnButton[0];
  }
}

```

## disassembly

```asm
0x180007ba8  push    rbp
0x180007baa  push    rbx
0x180007bab  push    rsi
0x180007bac  push    rdi
0x180007bad  push    r12
0x180007baf  push    r13
0x180007bb1  push    r14
0x180007bb3  push    r15
0x180007bb5  lea     rbp, [rsp-0C58h]
0x180007bbd  sub     rsp, 0D58h
0x180007bc4  mov     rax, cs:__security_cookie
0x180007bcb  xor     rax, rsp
0x180007bce  mov     [rbp+0C90h+var_50], rax
0x180007bd5  mov     rax, [rbp+0C90h+arg_40]
0x180007bdc  mov     rbx, r8
0x180007bdf  mov     r8, [rbp+0C90h+arg_30]
0x180007be6  xor     r14d, r14d
0x180007be9  mov     r12, [rbp+0C90h+arg_58]
0x180007bf0  test    r8, r8
0x180007bf3  mov     [rsp+0D90h+lpSrcStr], rax
0x180007bf8  mov     rdi, r9
0x180007bfb  mov     rax, [rbp+0C90h+arg_48]
0x180007c02  mov     r15, rdx
0x180007c05  mov     [rsp+0D90h+var_D40], rax
0x180007c0a  lea     edx, [r14+1]; unsigned int
0x180007c0e  mov     rax, [rbp+0C90h+arg_50]
0x180007c15  mov     r13, rcx
0x180007c18  mov     rcx, [rbp+0C90h+arg_28]; unsigned __int16 *
0x180007c1f  cmovz   r8, rbx; unsigned __int16 *
0x180007c23  mov     [rsp+0D90h+var_D30], rax
0x180007c28  lea     rax, [rsp+0D90h+pnButton]
0x180007c2d  mov     [rsp+0D90h+var_D48], r9
0x180007c32  xor     r9d, r9d; unsigned __int16 *
0x180007c35  mov     [rsp+0D90h+dwInitParam], rax; unsigned __int16 **
0x180007c3a  mov     [rsp+0D90h+var_D38], rbx
0x180007c3f  mov     [rsp+0D90h+var_D58], r14d
0x180007c44  mov     qword ptr [rsp+0D90h+pnButton], r14
0x180007c49  call    ?GetNewsgroupHelpUrl@@YAJPEBGK0PEAGPEAPEAG@Z; GetNewsgroupHelpUrl(ushort const *,ulong,ushort const *,ushort *,ushort * *)
0x180007c4e  mov     rsi, qword ptr [rsp+0D90h+pnButton]
0x180007c53  test    rsi, rsi
0x180007c56  jz      loc_180007F44
0x180007c5c  xor     r9d, r9d; fDefault
0x180007c5f  lea     rdx, c_szRegDownlevelMessageBox; "Downlevel MessageBox"
0x180007c66  xor     r8d, r8d; fIgnoreHKCU
0x180007c69  lea     rcx, c_szRegFlat; "Software\\Microsoft\\Windows Mail"
0x180007c70  call    cs:__imp_SHRegGetBoolUSValueA
0x180007c76  test    eax, eax
0x180007c78  jnz     loc_180007EA7
0x180007c7e  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x180007c85  lea     r8, [rbp+0C90h+Buffer]; lpBuffer
0x180007c8c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180007c90  mov     [rbp+0C90h+Buffer], r14w
0x180007c98  mov     r9d, 200h; cchBufferMax
0x180007c9e  mov     [rsp+0D90h+pnButton], edi
0x180007ca2  mov     edx, 7D3h; uID
0x180007ca7  mov     [rbp+0C90h+var_850], r14w
0x180007caf  mov     [rbp+0C90h+var_C50], ax
0x180007cb3  call    cs:__imp_LoadStringW
0x180007cb9  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x180007cc0  lea     r8, [rbp+0C90h+var_850]; lpBuffer
0x180007cc7  mov     r9d, 200h; cchBufferMax
0x180007ccd  mov     edx, 7D1h; uID
0x180007cd2  mov     ebx, eax
0x180007cd4  call    cs:__imp_LoadStringW
0x180007cda  test    ebx, ebx
0x180007cdc  jle     loc_180007E78
0x180007ce2  xor     ebx, ebx
0x180007ce4  test    eax, eax
0x180007ce6  jle     loc_180007E78
0x180007cec  lea     r9, [rbp+0C90h+var_850]
0x180007cf3  mov     edx, 200h; unsigned __int64
0x180007cf8  lea     r8, [rbp+0C90h+Buffer]; unsigned __int16 *
0x180007cff  lea     rcx, [rbp+0C90h+var_C50]; unsigned __int16 *
0x180007d03  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007d08  test    eax, eax
0x180007d0a  js      loc_180007E78
0x180007d10  lea     rax, [rbp+0C90h+var_C50]
0x180007d14  inc     rdi
0x180007d17  cmp     [rax+rdi*2], bx
0x180007d1b  jnz     short loc_180007D14
0x180007d1d  lea     eax, [rdi+1]
0x180007d20  mov     ecx, 40h ; '@'; uFlags
0x180007d25  lea     rdx, [rax+rax]; uBytes
0x180007d29  mov     ebx, eax
0x180007d2b  call    cs:__imp_LocalAlloc
0x180007d31  mov     rdi, rax
0x180007d34  test    rax, rax
0x180007d37  jz      loc_180007E7D
0x180007d3d  lea     r8, [rbp+0C90h+var_C50]; unsigned __int16 *
0x180007d41  mov     edx, ebx; unsigned __int64
0x180007d43  mov     rcx, rax; unsigned __int16 *
0x180007d46  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007d4b  test    eax, eax
0x180007d4d  js      loc_180007E6D
0x180007d53  mov     ebx, 0A0h
0x180007d58  lea     rcx, [rbp+0C90h+pTaskConfig]; void *
0x180007d5c  mov     r8d, ebx; Size
0x180007d5f  xor     edx, edx; Val
0x180007d61  call    memset_0
0x180007d66  mov     eax, [rbp+0C90h+arg_60]
0x180007d6c  mov     edx, 1
0x180007d71  mov     [rbp+0C90h+pTaskConfig.hwndParent], r15
0x180007d75  xor     r15d, r15d
0x180007d78  mov     [rbp+0C90h+pTaskConfig.cbSize], ebx
0x180007d7b  mov     ebx, [rbp+0C90h+arg_20]
0x180007d81  mov     [rbp+0C90h+pTaskConfig.hInstance], r13
0x180007d85  mov     [rbp+0C90h+pTaskConfig.dwFlags], edx
0x180007d88  test    eax, eax
0x180007d8a  jz      short loc_180007D95
0x180007d8c  mov     [rbp+0C90h+pTaskConfig.cButtons], eax
0x180007d8f  mov     [rbp+0C90h+pTaskConfig.pButtons], r12
0x180007d93  jmp     short loc_180007DE5
0x180007d95  mov     eax, ebx
0x180007d97  and     eax, 0Fh
0x180007d9a  cmp     eax, edx
0x180007d9c  jnz     short loc_180007DBE
0x180007d9e  mov     ecx, r15d
0x180007da1  mov     [rbp+0C90h+pTaskConfig.dwCommonButtons], 9
0x180007da8  mov     eax, ebx
0x180007daa  and     eax, 0F00h
0x180007daf  cmp     eax, 100h
0x180007db4  setz    cl
0x180007db7  add     ecx, edx
0x180007db9  mov     [rbp+0C90h+pTaskConfig.nDefaultButton], ecx
0x180007dbc  jmp     short loc_180007DE5
0x180007dbe  cmp     eax, 4
0x180007dc1  jnz     short loc_180007DE2
0x180007dc3  mov     eax, ebx
0x180007dc5  mov     [rbp+0C90h+pTaskConfig.dwCommonButtons], 6
0x180007dcc  and     eax, 0F00h
0x180007dd1  sub     eax, 100h
0x180007dd6  neg     eax
0x180007dd8  sbb     eax, eax
0x180007dda  add     eax, 7
0x180007ddd  mov     [rbp+0C90h+pTaskConfig.nDefaultButton], eax
0x180007de0  jmp     short loc_180007DE5
0x180007de2  mov     [rbp+0C90h+pTaskConfig.dwCommonButtons], edx
0x180007de5  mov     rax, [rsp+0D90h+var_D48]
0x180007dea  mov     rcx, [rsp+0D90h+lpSrcStr]; lpSrcStr
0x180007def  mov     [rbp+0C90h+pTaskConfig.pszWindowTitle], rax
0x180007df3  mov     rax, [rsp+0D90h+var_D40]
0x180007df8  mov     [rbp+0C90h+pTaskConfig.pszMainInstruction], rax
0x180007dfc  mov     rax, [rsp+0D90h+var_D38]
0x180007e01  mov     [rbp+0C90h+pTaskConfig.pszContent], rax
0x180007e05  mov     rax, [rsp+0D90h+var_D30]
0x180007e0a  mov     [rbp+0C90h+pTaskConfig.pszExpandedInformation], rax
0x180007e0e  call    FIsEmptyW
0x180007e13  mov     rcx, [rbp+0C90h+pTaskConfig.pszVerificationText]
0x180007e17  lea     r9, [rsp+0D90h+var_D58]
0x180007e1c  test    eax, eax
0x180007e1e  mov     [rbp+0C90h+pTaskConfig.pszFooter], rdi
0x180007e22  mov     edx, eax
0x180007e24  mov     [rbp+0C90h+pTaskConfig.lpCallbackData], rsi
0x180007e28  cmovz   rcx, [rsp+0D90h+lpSrcStr]
0x180007e2e  setz    r14b
0x180007e32  mov     [rbp+0C90h+pTaskConfig.pszVerificationText], rcx
0x180007e36  and     bl, 0F0h
0x180007e39  cmp     bl, 40h ; '@'
0x180007e3c  mov     ecx, 0FFFFh
0x180007e41  lea     eax, [rcx-2]
0x180007e44  cmovz   ecx, eax
0x180007e47  test    edx, edx
0x180007e49  mov     qword ptr [rbp+0C90h+pTaskConfig.24h], rcx
0x180007e4d  lea     rax, ?TaskDialogWithNewsgroupHelpDlgProc@@YAJPEAUHWND__@@I_K_J2@Z; TaskDialogWithNewsgroupHelpDlgProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x180007e54  cmovnz  r9, r15; pfVerificationFlagChecked
0x180007e58  mov     [rbp+0C90h+pTaskConfig.pfCallback], rax
0x180007e5c  xor     r8d, r8d; pnRadioButton
0x180007e5f  lea     rdx, [rsp+0D90h+pnButton]; pnButton
0x180007e64  lea     rcx, [rbp+0C90h+pTaskConfig]; pTaskConfig
0x180007e68  call    TaskDialogIndirect
0x180007e6d  mov     rcx, rdi; hMem
0x180007e70  call    cs:__imp_LocalFree
0x180007e76  jmp     short loc_180007E7D
0x180007e78  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180007e7d  mov     rcx, rsi; hMem
0x180007e80  call    cs:__imp_LocalFree
0x180007e86  test    r14d, r14d
0x180007e89  jz      short loc_180007E9C
0x180007e8b  movzx   ecx, word ptr [rsp+0D90h+pnButton]
0x180007e90  movzx   eax, word ptr [rsp+0D90h+var_D58]
0x180007e95  shl     ecx, 10h
0x180007e98  or      ecx, eax
0x180007e9a  jmp     short loc_180007EA0
0x180007e9c  mov     ecx, [rsp+0D90h+pnButton]
0x180007ea0  mov     eax, ecx
0x180007ea2  jmp     loc_180007F48
0x180007ea7  mov     eax, [rbp+0C90h+arg_20]
0x180007ead  lea     rcx, [rsp+0D90h+ulCookie]; lpCookie
0x180007eb2  mov     dword ptr [rsp+0D90h+var_D20], eax
0x180007eb6  lea     rax, [rsp+0D90h+var_D20]
0x180007ebb  mov     [rbp+0C90h+var_CF8], rax
0x180007ebf  lea     rax, ?MessageBoxWithNewsgroupHelpDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; MessageBoxWithNewsgroupHelpDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180007ec6  mov     [rbp+0C90h+var_D00], rax
0x180007eca  mov     dword ptr [rsp+0D90h+var_D20+4], r14d
0x180007ecf  mov     [rsp+0D90h+var_D18], rbx
0x180007ed4  mov     [rbp+0C90h+var_D10], rdi
0x180007ed8  mov     [rbp+0C90h+var_D08], rsi
0x180007edc  mov     [rsp+0D90h+ulCookie], r14
0x180007ee1  call    CreateAndActivateContext
0x180007ee6  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x180007eed  lea     r9, ?MessageBoxWithNewsgroupHelpExDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180007ef4  mov     rbx, rax
0x180007ef7  mov     r8, r15; hWndParent
0x180007efa  lea     rax, [rsp+0D90h+var_D20]
0x180007eff  mov     edx, 65h ; 'e'; lpTemplateName
0x180007f04  mov     [rsp+0D90h+dwInitParam], rax; dwInitParam
0x180007f09  call    cs:__imp_DialogBoxParamW
0x180007f0f  lea     rcx, [rbx-1]
0x180007f13  mov     rdi, rax
0x180007f16  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180007f1a  ja      short loc_180007F37
0x180007f1c  mov     rdx, [rsp+0D90h+ulCookie]; ulCookie
0x180007f21  test    rdx, rdx
0x180007f24  jz      short loc_180007F2E
0x180007f26  xor     ecx, ecx; dwFlags
0x180007f28  call    cs:__imp_DeactivateActCtx
0x180007f2e  mov     rcx, rbx; hActCtx
0x180007f31  call    cs:__imp_ReleaseActCtx
0x180007f37  mov     rcx, rsi; hMem
0x180007f3a  call    cs:__imp_LocalFree
0x180007f40  mov     eax, edi
0x180007f42  jmp     short loc_180007F48
0x180007f44  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007f48  mov     rcx, [rbp+0C90h+var_50]
0x180007f4f  xor     rcx, rsp; StackCookie
0x180007f52  call    __security_check_cookie
0x180007f57  add     rsp, 0D58h
0x180007f5e  pop     r15
0x180007f60  pop     r14
0x180007f62  pop     r13
0x180007f64  pop     r12
0x180007f66  pop     rdi
0x180007f67  pop     rsi
0x180007f68  pop     rbx
0x180007f69  pop     rbp
0x180007f6a  retn
```
