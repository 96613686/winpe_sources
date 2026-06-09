# winreOpenRecoveryWim(ushort const *,void * *,void * *,ushort *,ulong)

- ea: `0x18001f850`
- end: `0x18001fbb7`
- name: `?winreOpenRecoveryWim@@YAHPEBGPEAPEAX1PEAGK@Z`
- size: `871`
- prototype: `int(const unsigned __int16 *, void **, void **, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x180029f9c`

## callees

- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x18001de7c`
- `0x18001f850`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001f911`
- `KERNEL32!GetLastError` at `0x18001f938`
- `KERNEL32!GetLastError` at `0x18001fa83`
- `KERNEL32!GetLastError` at `0x18001faae`
- `KERNEL32!GetLastError` at `0x18001faec`
- `KERNEL32!GetLastError` at `0x18001fb4a`
- `KERNEL32!GetLastError` at `0x18001f911`
- `KERNEL32!GetLastError` at `0x18001f938`
- `KERNEL32!GetLastError` at `0x18001fa83`
- `KERNEL32!GetLastError` at `0x18001faae`
- `KERNEL32!GetLastError` at `0x18001faec`
- `KERNEL32!GetLastError` at `0x18001fb4a`
- `KERNEL32!RemoveDirectoryW` at `0x18001fb6f`
- `KERNEL32!RemoveDirectoryW` at `0x18001fb6f`
- `KERNEL32!SetLastError` at `0x18001fb8f`
- `KERNEL32!SetLastError` at `0x18001fb8f`
- `KERNEL32!CreateDirectoryW` at `0x18001fa79`
- `KERNEL32!CreateDirectoryW` at `0x18001fa79`
- `WIMGAPI!WIMGetAttributes` at `0x18001fae2`
- `WIMGAPI!WIMGetAttributes` at `0x18001fae2`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18001faa4`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18001faa4`
- `WIMGAPI!WIMCreateFile` at `0x18001f903`
- `WIMGAPI!WIMCreateFile` at `0x18001f903`
- `WIMGAPI!WIMLoadImage` at `0x18001fb3c`
- `WIMGAPI!WIMLoadImage` at `0x18001fb3c`

## string_xrefs

- `0x18001f956`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18001fa3e`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18001fa55`: `failed to append path`
- `0x18001f917`: `Failed to open winre.wim: %d`
- `0x18001f93e`: `failed to get temp path`
- `0x18001f94f`: `winreOpenRecoveryWim %s (0x%x) in file %S line %d`
- `0x18001fa61`: `winreOpenRecoveryWim %s (0x%x) in file %S line %d`
- `0x18001fac8`: `Failed to create mount dir: 0x%x`
- `0x18001fab4`: `failed to set temporary path for wimgapi`

## pseudocode

```c
__int64 __fastcall winreOpenRecoveryWim(const unsigned __int16 *a1, void **a2, void **a3, unsigned __int16 *a4)
{
  int v8; // r12d
  void *v9; // rax
  DWORD LastError; // eax
  const wchar_t *v11; // rdx
  DWORD v12; // eax
  const wchar_t *v13; // r8
  signed int v14; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  const unsigned __int16 *v17; // r8
  DWORD v18; // eax
  void *v19; // rax
  __int64 v21; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v23[548]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v24; // [rsp+264h] [rbp+164h]
  __int16 v25; // [rsp+26Eh] [rbp+16Eh]
  unsigned __int16 v26; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v27[606]; // [rsp+272h] [rbp+172h] BYREF

  v26 = 0;
  memset_0(v27, 0, 0x25Au);
  memset_0(v23, 0, 0x230u);
  if ( a1 && a2 && a3 && a4 )
  {
    v8 = 0;
    *a4 = 0;
    *a2 = 0;
    *a3 = 0;
    v9 = (void *)WIMCreateFile(a1, 0x80000000LL, 3, 0x20000000, 0, 0);
    *a2 = v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      v11 = L"Failed to open winre.wim: %d";
      goto LABEL_37;
    }
    if ( !(unsigned int)SecureGetTempPathW(0x12Eu, &v26) )
    {
      v12 = GetLastError();
      v13 = L"failed to get temp path";
      LODWORD(v21) = 3021;
      goto LABEL_9;
    }
    v22 = 0;
    v14 = StringCchLengthW(&v26, 0x7FFFFFFFu, &v22);
    if ( v14 >= 0 )
    {
      if ( !v22 || (v17 = L"%s\\%s", *(&v25 + v22) == 92) )
        v17 = L"%s%s";
      v14 = StringCchPrintfW(a4, 0x12Eu, v17, &v26, L"winre");
      if ( v14 >= 0 )
      {
        v14 = 0;
        goto LABEL_25;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v16 = 15;
        goto LABEL_21;
      }
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v16 = 14;
LABEL_21:
        WPP_SF_d(v15[2], v16, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v14);
      }
    }
    v14 = (unsigned __int16)v14;
    if ( (_WORD)v14 )
    {
      LODWORD(v21) = 3026;
      UnattendLogW(
        2,
        L"winreOpenRecoveryWim %s (0x%x) in file %S line %d",
        L"failed to append path",
        (unsigned __int16)v14,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        v21);
LABEL_43:
      *a4 = 0;
      goto LABEL_44;
    }
LABEL_25:
    if ( !CreateDirectoryW(a4, 0) )
    {
      v18 = GetLastError();
      v14 = v18;
      if ( v18 != 183 )
      {
        UnattendLogW(0, L"Failed to create mount dir: 0x%x", v18);
        goto LABEL_38;
      }
      v14 = 0;
    }
    v8 = 1;
    if ( (unsigned int)WIMSetTemporaryPath(*a2, &v26) )
    {
      if ( (unsigned int)WIMGetAttributes(*a2, v23, 560) )
      {
        if ( !v24 )
        {
          v14 = 1168;
          UnattendLogW(0, L"Could not find a bootable index in the wim file.");
LABEL_40:
          RemoveDirectoryW(a4);
          goto LABEL_43;
        }
        UnattendLogW(0, L"Loading boot index %d");
        v19 = (void *)WIMLoadImage(*a2, v24);
        *a3 = v19;
        if ( v19 )
        {
LABEL_38:
          if ( !v14 )
            return 1;
          if ( !v8 )
            goto LABEL_43;
          goto LABEL_40;
        }
        LastError = GetLastError();
        v11 = L"Failed to load winre.wim: 0x%x";
LABEL_37:
        v14 = LastError;
        UnattendLogW(0, v11, LastError);
        goto LABEL_38;
      }
      v12 = GetLastError();
      v13 = L"failed to get wim attributes";
      LODWORD(v21) = 3056;
    }
    else
    {
      v12 = GetLastError();
      v13 = L"failed to set temporary path for wimgapi";
      LODWORD(v21) = 3047;
    }
LABEL_9:
    v14 = v12;
    UnattendLogW(
      2,
      L"winreOpenRecoveryWim %s (0x%x) in file %S line %d",
      v13,
      v12,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      v21);
    goto LABEL_38;
  }
  v14 = 87;
  if ( a4 )
    goto LABEL_43;
LABEL_44:
  SetLastError(v14);
  return 0;
}

```

## disassembly

```asm
0x18001f850  push    rbp
0x18001f852  push    rbx
0x18001f853  push    rdi
0x18001f854  push    r12
0x18001f856  push    r14
0x18001f858  push    r15
0x18001f85a  lea     rbp, [rsp-3E8h]
0x18001f862  sub     rsp, 4E8h
0x18001f869  mov     rax, cs:__security_cookie
0x18001f870  xor     rax, rsp
0x18001f873  mov     [rbp+410h+var_40], rax
0x18001f87a  mov     r15, r8
0x18001f87d  mov     r14, rdx
0x18001f880  mov     rbx, rcx
0x18001f883  xor     eax, eax
0x18001f885  xor     edx, edx; Val
0x18001f887  mov     [rbp+410h+var_2A0], ax
0x18001f88e  mov     r8d, 25Ah; Size
0x18001f894  lea     rcx, [rbp+410h+var_29E]; void *
0x18001f89b  mov     rdi, r9
0x18001f89e  call    memset_0
0x18001f8a3  xor     edx, edx; Val
0x18001f8a5  lea     rcx, [rsp+510h+var_4D0]; void *
0x18001f8aa  mov     r8d, 230h; Size
0x18001f8b0  call    memset_0
0x18001f8b5  test    rbx, rbx
0x18001f8b8  jz      loc_18001FB7E
0x18001f8be  test    r14, r14
0x18001f8c1  jz      loc_18001FB7E
0x18001f8c7  test    r15, r15
0x18001f8ca  jz      loc_18001FB7E
0x18001f8d0  test    rdi, rdi
0x18001f8d3  jz      loc_18001FB7E
0x18001f8d9  xor     eax, eax
0x18001f8db  xor     r12d, r12d
0x18001f8de  mov     [rdi], ax
0x18001f8e1  mov     edx, 80000000h
0x18001f8e6  mov     [r14], rax
0x18001f8e9  mov     r9d, 20000000h
0x18001f8ef  mov     [rsp+510h+var_4E8], rax
0x18001f8f4  mov     rcx, rbx
0x18001f8f7  lea     r8d, [r12+3]
0x18001f8fc  mov     [r15], rax
0x18001f8ff  mov     dword ptr [rsp+510h+var_4F0], eax
0x18001f903  call    cs:__imp_WIMCreateFile
0x18001f909  mov     [r14], rax
0x18001f90c  test    rax, rax
0x18001f90f  jnz     short loc_18001F923
0x18001f911  call    cs:__imp_GetLastError
0x18001f917  lea     rdx, aFailedToOpenWi_1; "Failed to open winre.wim: %d"
0x18001f91e  jmp     loc_18001FB57
0x18001f923  lea     rdx, [rbp+410h+var_2A0]; unsigned __int16 *
0x18001f92a  mov     ecx, 12Eh; unsigned int
0x18001f92f  call    ?SecureGetTempPathW@@YAKKPEAG@Z; SecureGetTempPathW(ulong,ushort *)
0x18001f934  test    eax, eax
0x18001f936  jnz     short loc_18001F974
0x18001f938  call    cs:__imp_GetLastError
0x18001f93e  lea     r8, aFailedToGetTem; "failed to get temp path"
0x18001f945  mov     dword ptr [rsp+510h+var_4E8], 0BCDh
0x18001f94d  mov     ebx, eax
0x18001f94f  lea     rdx, aWinreopenrecov; "winreOpenRecoveryWim %s (0x%x) in file "...
0x18001f956  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18001f95d  mov     r9d, ebx
0x18001f960  mov     ecx, 2
0x18001f965  mov     [rsp+510h+var_4F0], rax
0x18001f96a  call    UnattendLogW
0x18001f96f  jmp     loc_18001FB63
0x18001f974  lea     r8, [rsp+510h+var_4E0]; unsigned __int64 *
0x18001f979  mov     [rsp+510h+var_4E0], r12
0x18001f97e  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001f983  lea     rcx, [rbp+410h+var_2A0]; unsigned __int16 *
0x18001f98a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001f98f  mov     ebx, eax
0x18001f991  test    eax, eax
0x18001f993  jns     short loc_18001F9BD
0x18001f995  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f99c  lea     rax, WPP_GLOBAL_Control
0x18001f9a3  cmp     rcx, rax
0x18001f9a6  jz      loc_18001FA37
0x18001f9ac  test    byte ptr [rcx+1Ch], 2
0x18001f9b0  jz      loc_18001FA37
0x18001f9b6  mov     edx, 0Eh
0x18001f9bb  jmp     short loc_18001FA24
0x18001f9bd  mov     rax, [rsp+510h+var_4E0]
0x18001f9c2  test    rax, rax
0x18001f9c5  jz      short loc_18001F9D9
0x18001f9c7  cmp     [rbp+rax*2+410h+var_2A2], 5Ch ; '\'
0x18001f9d0  lea     r8, aSS_1; "%s\\%s"
0x18001f9d7  jnz     short loc_18001F9E0
0x18001f9d9  lea     r8, aSS_2; "%s%s"
0x18001f9e0  lea     rax, aWinre; "winre"
0x18001f9e7  mov     edx, 12Eh; unsigned __int64
0x18001f9ec  lea     r9, [rbp+410h+var_2A0]
0x18001f9f3  mov     [rsp+510h+var_4F0], rax
0x18001f9f8  mov     rcx, rdi; unsigned __int16 *
0x18001f9fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fa00  mov     ebx, eax
0x18001fa02  test    eax, eax
0x18001fa04  jns     short loc_18001FA72
0x18001fa06  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa0d  lea     rax, WPP_GLOBAL_Control
0x18001fa14  cmp     rcx, rax
0x18001fa17  jz      short loc_18001FA37
0x18001fa19  test    byte ptr [rcx+1Ch], 2
0x18001fa1d  jz      short loc_18001FA37
0x18001fa1f  mov     edx, 0Fh
0x18001fa24  mov     rcx, [rcx+10h]
0x18001fa28  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18001fa2f  mov     r9d, ebx
0x18001fa32  call    WPP_SF_d
0x18001fa37  movzx   ebx, bx
0x18001fa3a  test    ebx, ebx
0x18001fa3c  jz      short loc_18001FA74
0x18001fa3e  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18001fa45  mov     dword ptr [rsp+510h+var_4E8], 0BD2h
0x18001fa4d  mov     r9d, ebx
0x18001fa50  mov     [rsp+510h+var_4F0], rax
0x18001fa55  lea     r8, aFailedToAppend_7; "failed to append path"
0x18001fa5c  mov     ecx, 2
0x18001fa61  lea     rdx, aWinreopenrecov; "winreOpenRecoveryWim %s (0x%x) in file "...
0x18001fa68  call    UnattendLogW
0x18001fa6d  jmp     loc_18001FB88
0x18001fa72  xor     ebx, ebx
0x18001fa74  xor     edx, edx; lpSecurityAttributes
0x18001fa76  mov     rcx, rdi; lpPathName
0x18001fa79  call    cs:__imp_CreateDirectoryW
0x18001fa7f  test    eax, eax
0x18001fa81  jnz     short loc_18001FA94
0x18001fa83  call    cs:__imp_GetLastError
0x18001fa89  mov     ebx, eax
0x18001fa8b  cmp     eax, 0B7h
0x18001fa90  jnz     short loc_18001FAC8
0x18001fa92  xor     ebx, ebx
0x18001fa94  mov     rcx, [r14]
0x18001fa97  lea     rdx, [rbp+410h+var_2A0]
0x18001fa9e  mov     r12d, 1
0x18001faa4  call    cs:__imp_WIMSetTemporaryPath
0x18001faaa  test    eax, eax
0x18001faac  jnz     short loc_18001FAD4
0x18001faae  call    cs:__imp_GetLastError
0x18001fab4  lea     r8, aFailedToSetTem; "failed to set temporary path for wimgap"...
0x18001fabb  mov     dword ptr [rsp+510h+var_4E8], 0BE7h
0x18001fac3  jmp     loc_18001F94D
0x18001fac8  lea     rdx, aFailedToCreate_28; "Failed to create mount dir: 0x%x"
0x18001facf  jmp     loc_18001FB59
0x18001fad4  mov     rcx, [r14]
0x18001fad7  lea     rdx, [rsp+510h+var_4D0]
0x18001fadc  mov     r8d, 230h
0x18001fae2  call    cs:__imp_WIMGetAttributes
0x18001fae8  test    eax, eax
0x18001faea  jnz     short loc_18001FB06
0x18001faec  call    cs:__imp_GetLastError
0x18001faf2  lea     r8, aFailedToGetWim_0; "failed to get wim attributes"
0x18001faf9  mov     dword ptr [rsp+510h+var_4E8], 0BF0h
0x18001fb01  jmp     loc_18001F94D
0x18001fb06  mov     r8d, [rbp+410h+var_2AC]
0x18001fb0d  xor     ecx, ecx
0x18001fb0f  test    r8d, r8d
0x18001fb12  jnz     short loc_18001FB27
0x18001fb14  lea     rdx, aCouldNotFindAB; "Could not find a bootable index in the "...
0x18001fb1b  mov     ebx, 490h
0x18001fb20  call    UnattendLogW
0x18001fb25  jmp     short loc_18001FB6C
0x18001fb27  lea     rdx, aLoadingBootInd; "Loading boot index %d"
0x18001fb2e  call    UnattendLogW
0x18001fb33  mov     edx, [rbp+410h+var_2AC]
0x18001fb39  mov     rcx, [r14]
0x18001fb3c  call    cs:__imp_WIMLoadImage
0x18001fb42  mov     [r15], rax
0x18001fb45  test    rax, rax
0x18001fb48  jnz     short loc_18001FB63
0x18001fb4a  call    cs:__imp_GetLastError
0x18001fb50  lea     rdx, aFailedToLoadWi; "Failed to load winre.wim: 0x%x"
0x18001fb57  mov     ebx, eax
0x18001fb59  mov     r8d, eax
0x18001fb5c  xor     ecx, ecx
0x18001fb5e  call    UnattendLogW
0x18001fb63  test    ebx, ebx
0x18001fb65  jz      short loc_18001FB77
0x18001fb67  test    r12d, r12d
0x18001fb6a  jz      short loc_18001FB88
0x18001fb6c  mov     rcx, rdi; lpPathName
0x18001fb6f  call    cs:__imp_RemoveDirectoryW
0x18001fb75  jmp     short loc_18001FB88
0x18001fb77  mov     eax, 1
0x18001fb7c  jmp     short loc_18001FB97
0x18001fb7e  mov     ebx, 57h ; 'W'
0x18001fb83  test    rdi, rdi
0x18001fb86  jz      short loc_18001FB8D
0x18001fb88  xor     eax, eax
0x18001fb8a  mov     [rdi], ax
0x18001fb8d  mov     ecx, ebx; dwErrCode
0x18001fb8f  call    cs:__imp_SetLastError
0x18001fb95  xor     eax, eax
0x18001fb97  mov     rcx, [rbp+410h+var_40]
0x18001fb9e  xor     rcx, rsp; StackCookie
0x18001fba1  call    __security_check_cookie
0x18001fba6  add     rsp, 4E8h
0x18001fbad  pop     r15
0x18001fbaf  pop     r14
0x18001fbb1  pop     r12
0x18001fbb3  pop     rdi
0x18001fbb4  pop     rbx
0x18001fbb5  pop     rbp
0x18001fbb6  retn
```
