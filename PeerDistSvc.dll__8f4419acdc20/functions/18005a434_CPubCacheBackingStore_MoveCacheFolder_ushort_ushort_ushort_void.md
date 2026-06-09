# CPubCacheBackingStore::MoveCacheFolder(ushort *,ushort *,ushort *,void *)

- ea: `0x18005a434`
- end: `0x18005a7b2`
- name: `?MoveCacheFolder@CPubCacheBackingStore@@AEAAKPEAG00PEAX@Z`
- size: `894`
- prototype: `__int64 __fastcall(CPubCacheBackingStore *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, HANDLE hTransaction)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18005a7b8`
- `0x18005ab08`

## callees

- `0x18000cf48`
- `0x18000cfc0`
- `0x1800180e4`
- `0x1800183a0`
- `0x18001844c`
- `0x180018924`
- `0x18005a434`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a5b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a6eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a6ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a5b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a6eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a6ff`
- `KERNEL32!FindNextFileW` at `0x18005a6dd`
- `KERNEL32!FindNextFileW` at `0x18005a6dd`
- `KERNEL32!FindClose` at `0x18005a789`
- `KERNEL32!FindClose` at `0x18005a789`
- `api-ms-win-core-kernel32-legacy-l1-1-3!MoveFileTransactedW` at `0x18005a6cb`
- `api-ms-win-core-kernel32-legacy-l1-1-3!MoveFileTransactedW` at `0x18005a6cb`
- `api-ms-win-core-kernel32-legacy-l1-1-3!FindFirstFileTransactedW` at `0x18005a5a2`
- `api-ms-win-core-kernel32-legacy-l1-1-3!FindFirstFileTransactedW` at `0x18005a5a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPubCacheBackingStore::MoveCacheFolder(
        CPubCacheBackingStore *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        HANDLE hTransaction)
{
  int v8; // eax
  DWORD v9; // ebx
  CHostedCacheMsgEncoding *v10; // rcx
  int v11; // edx
  int v12; // eax
  HANDLE FirstFileTransactedW; // rsi
  DWORD LastError; // eax
  int v15; // eax
  DWORD v16; // eax
  DWORD v17; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR NewFileName[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_SSS(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      262,
      (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      (__int64)L"*");
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v8 = StringCchPrintfW(FileName, 0x104u, L"%s\\", a2);
  if ( v8 >= 0 )
  {
    v12 = StringCchCatW(FileName, 0x104u, L"*");
    if ( v12 >= 0 )
    {
      FirstFileTransactedW = FindFirstFileTransactedW(
                               FileName,
                               FindExInfoBasic,
                               &FindFileData,
                               FindExSearchNameMatch,
                               0,
                               0,
                               hTransaction);
      if ( FirstFileTransactedW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError - 2 <= 1 )
        {
          return 0;
        }
        else if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            265,
            (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
            (_DWORD)a2,
            LastError);
        }
      }
      else
      {
        while ( 1 )
        {
          if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
          {
            v15 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", a2, FindFileData.cFileName);
            if ( v15 < 0
              || (v15 = StringCchPrintfW(NewFileName, 0x104u, L"%s\\%s", a3, FindFileData.cFileName), v15 < 0) )
            {
              v9 = (unsigned __int16)v15;
              goto LABEL_44;
            }
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
            {
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                266,
                (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
                (unsigned int)FileName,
                (__int64)NewFileName);
            }
            if ( !MoveFileTransactedW(FileName, NewFileName, PubCacheMoveFolderCallback, this, 2u, hTransaction) )
              break;
          }
          if ( !FindNextFileW(FirstFileTransactedW, &FindFileData) )
          {
            v16 = GetLastError();
            v9 = v16;
            if ( v16 == 18 )
            {
              v9 = 0;
            }
            else if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                268,
                (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
                (_DWORD)a2,
                v16);
            }
            goto LABEL_44;
          }
        }
        v17 = GetLastError();
        v9 = v17;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            267,
            (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
            (unsigned int)FileName,
            (__int64)NewFileName,
            v17);
        }
LABEL_44:
        FindClose(FirstFileTransactedW);
      }
    }
    else
    {
      v9 = (unsigned __int16)v12;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v11 = 264;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v9 = (unsigned __int16)v8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v11 = 263;
LABEL_10:
      WPP_SF_Sd(
        *((_QWORD *)v10 + 12),
        v11,
        (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
        (_DWORD)a2,
        v9);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18005a434  push    rbp
0x18005a436  push    rbx
0x18005a437  push    rsi
0x18005a438  push    rdi
0x18005a439  push    r13
0x18005a43b  push    r14
0x18005a43d  push    r15
0x18005a43f  lea     rbp, [rsp-5C0h]
0x18005a447  sub     rsp, 6C0h
0x18005a44e  mov     rax, cs:__security_cookie
0x18005a455  xor     rax, rsp
0x18005a458  mov     [rbp+5F0h+var_40], rax
0x18005a45f  mov     r14, [rbp+5F0h+arg_20]
0x18005a466  mov     rbx, r8
0x18005a469  mov     rdi, rdx
0x18005a46c  mov     r15, rcx
0x18005a46f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a476  lea     r13, WPP_GLOBAL_Control
0x18005a47d  lea     rax, asc_180174A68; "*"
0x18005a484  lea     rsi, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005a48b  cmp     rcx, r13
0x18005a48e  jz      short loc_18005A4BA
0x18005a490  test    byte ptr [rcx+6Ch], 4
0x18005a494  jz      short loc_18005A4BA
0x18005a496  cmp     byte ptr [rcx+69h], 4
0x18005a49a  jb      short loc_18005A4BA
0x18005a49c  mov     rcx, [rcx+60h]
0x18005a4a0  mov     edx, 106h
0x18005a4a5  mov     qword ptr [rsp+6F0h+dwAdditionalFlags], rax
0x18005a4aa  mov     r9, rdi
0x18005a4ad  mov     r8, rsi
0x18005a4b0  mov     [rsp+6F0h+lpSearchFilter], rbx
0x18005a4b5  call    WPP_SF_SSS
0x18005a4ba  xor     edx, edx; Val
0x18005a4bc  lea     rcx, [rsp+6F0h+FindFileData]; void *
0x18005a4c1  mov     r8d, 250h; Size
0x18005a4c7  call    memset_0
0x18005a4cc  mov     r9, rdi
0x18005a4cf  lea     r8, aS_0; "%s\\"
0x18005a4d6  mov     edx, 104h; unsigned __int64
0x18005a4db  lea     rcx, [rbp+5F0h+FileName]; unsigned __int16 *
0x18005a4e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005a4e7  test    eax, eax
0x18005a4e9  jns     short loc_18005A52F
0x18005a4eb  movzx   ebx, ax
0x18005a4ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a4f5  cmp     rcx, r13
0x18005a4f8  jz      loc_18005A78F
0x18005a4fe  test    byte ptr [rcx+6Ch], 4
0x18005a502  jz      loc_18005A78F
0x18005a508  cmp     byte ptr [rcx+69h], 1
0x18005a50c  jb      loc_18005A78F
0x18005a512  mov     edx, 107h
0x18005a517  mov     dword ptr [rsp+6F0h+lpSearchFilter], ebx
0x18005a51b  mov     r8, rsi
0x18005a51e  mov     rcx, [rcx+60h]
0x18005a522  mov     r9, rdi
0x18005a525  call    WPP_SF_Sd
0x18005a52a  jmp     loc_18005A78F
0x18005a52f  lea     r8, asc_180174A68; "*"
0x18005a536  mov     edx, 104h; unsigned __int64
0x18005a53b  lea     rcx, [rbp+5F0h+FileName]; unsigned __int16 *
0x18005a542  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005a547  test    eax, eax
0x18005a549  jns     short loc_18005A579
0x18005a54b  movzx   ebx, ax
0x18005a54e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a555  cmp     rcx, r13
0x18005a558  jz      loc_18005A78F
0x18005a55e  test    byte ptr [rcx+6Ch], 4
0x18005a562  jz      loc_18005A78F
0x18005a568  cmp     byte ptr [rcx+69h], 1
0x18005a56c  jb      loc_18005A78F
0x18005a572  mov     edx, 108h
0x18005a577  jmp     short loc_18005A517
0x18005a579  xor     r9d, r9d; fSearchOp
0x18005a57c  mov     [rsp+6F0h+hTransaction], r14; hTransaction
0x18005a581  mov     [rsp+6F0h+dwAdditionalFlags], 0; dwAdditionalFlags
0x18005a589  lea     r8, [rsp+6F0h+FindFileData]; lpFindFileData
0x18005a58e  lea     rcx, [rbp+5F0h+FileName]; lpFileName
0x18005a595  mov     [rsp+6F0h+lpSearchFilter], 0; lpSearchFilter
0x18005a59e  lea     edx, [r9+1]; fInfoLevelId
0x18005a5a2  call    cs:__imp_FindFirstFileTransactedW
0x18005a5a8  mov     rsi, rax
0x18005a5ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005a5af  jnz     short loc_18005A601
0x18005a5b1  call    cs:__imp_GetLastError
0x18005a5b7  mov     ebx, eax
0x18005a5b9  lea     ecx, [rax-2]
0x18005a5bc  cmp     ecx, 1
0x18005a5bf  jbe     short loc_18005A5FA
0x18005a5c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a5c8  cmp     rcx, r13
0x18005a5cb  jz      loc_18005A78F
0x18005a5d1  test    byte ptr [rcx+6Ch], 4
0x18005a5d5  jz      loc_18005A78F
0x18005a5db  cmp     byte ptr [rcx+69h], 1
0x18005a5df  jb      loc_18005A78F
0x18005a5e5  mov     edx, 109h
0x18005a5ea  mov     dword ptr [rsp+6F0h+lpSearchFilter], eax
0x18005a5ee  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005a5f5  jmp     loc_18005A51E
0x18005a5fa  xor     ebx, ebx
0x18005a5fc  jmp     loc_18005A78F
0x18005a601  test    [rsp+6F0h+FindFileData], 10h
0x18005a606  jnz     loc_18005A6D5
0x18005a60c  lea     rax, [rsp+6F0h+var_684]
0x18005a611  mov     r9, rdi
0x18005a614  lea     r8, aSS; "%s\\%s"
0x18005a61b  mov     [rsp+6F0h+lpSearchFilter], rax
0x18005a620  mov     edx, 104h; unsigned __int64
0x18005a625  lea     rcx, [rbp+5F0h+FileName]; unsigned __int16 *
0x18005a62c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005a631  test    eax, eax
0x18005a633  js      loc_18005A74D
0x18005a639  lea     rax, [rsp+6F0h+var_684]
0x18005a63e  mov     r9, rbx
0x18005a641  lea     r8, aSS; "%s\\%s"
0x18005a648  mov     [rsp+6F0h+lpSearchFilter], rax
0x18005a64d  mov     edx, 104h; unsigned __int64
0x18005a652  lea     rcx, [rbp+5F0h+NewFileName]; unsigned __int16 *
0x18005a659  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005a65e  test    eax, eax
0x18005a660  js      loc_18005A74D
0x18005a666  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a66d  cmp     rcx, r13
0x18005a670  jz      short loc_18005A6A6
0x18005a672  test    byte ptr [rcx+6Ch], 4
0x18005a676  jz      short loc_18005A6A6
0x18005a678  cmp     byte ptr [rcx+69h], 4
0x18005a67c  jb      short loc_18005A6A6
0x18005a67e  mov     rcx, [rcx+60h]
0x18005a682  lea     rax, [rbp+5F0h+NewFileName]
0x18005a689  mov     edx, 10Ah
0x18005a68e  mov     [rsp+6F0h+lpSearchFilter], rax
0x18005a693  lea     r9, [rbp+5F0h+FileName]
0x18005a69a  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005a6a1  call    WPP_SF_SS
0x18005a6a6  mov     qword ptr [rsp+6F0h+dwAdditionalFlags], r14; hTransaction
0x18005a6ab  lea     r8, ?PubCacheMoveFolderCallback@@YAKT_LARGE_INTEGER@@000KKPEAX11@Z; lpProgressRoutine
0x18005a6b2  mov     r9, r15; lpData
0x18005a6b5  mov     dword ptr [rsp+6F0h+lpSearchFilter], 2; dwFlags
0x18005a6bd  lea     rdx, [rbp+5F0h+NewFileName]; lpNewFileName
0x18005a6c4  lea     rcx, [rbp+5F0h+FileName]; lpExistingFileName
0x18005a6cb  call    cs:__imp_MoveFileTransactedW
0x18005a6d1  test    eax, eax
0x18005a6d3  jz      short loc_18005A6FF
0x18005a6d5  lea     rdx, [rsp+6F0h+FindFileData]; lpFindFileData
0x18005a6da  mov     rcx, rsi; hFindFile
0x18005a6dd  call    cs:__imp_FindNextFileW
0x18005a6e3  test    eax, eax
0x18005a6e5  jnz     loc_18005A601
0x18005a6eb  call    cs:__imp_GetLastError
0x18005a6f1  mov     ebx, eax
0x18005a6f3  cmp     eax, 12h
0x18005a6f6  jnz     short loc_18005A752
0x18005a6f8  xor     ebx, ebx
0x18005a6fa  jmp     loc_18005A786
0x18005a6ff  call    cs:__imp_GetLastError
0x18005a705  mov     ebx, eax
0x18005a707  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a70e  cmp     rcx, r13
0x18005a711  jz      short loc_18005A786
0x18005a713  test    byte ptr [rcx+6Ch], 4
0x18005a717  jz      short loc_18005A786
0x18005a719  cmp     byte ptr [rcx+69h], 1
0x18005a71d  jb      short loc_18005A786
0x18005a71f  mov     rcx, [rcx+60h]
0x18005a723  lea     r9, [rbp+5F0h+FileName]
0x18005a72a  mov     [rsp+6F0h+dwAdditionalFlags], eax
0x18005a72e  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005a735  lea     rax, [rbp+5F0h+NewFileName]
0x18005a73c  mov     edx, 10Bh
0x18005a741  mov     [rsp+6F0h+lpSearchFilter], rax
0x18005a746  call    WPP_SF_SSD
0x18005a74b  jmp     short loc_18005A786
0x18005a74d  movzx   ebx, ax
0x18005a750  jmp     short loc_18005A786
0x18005a752  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a759  cmp     rcx, r13
0x18005a75c  jz      short loc_18005A786
0x18005a75e  test    byte ptr [rcx+6Ch], 4
0x18005a762  jz      short loc_18005A786
0x18005a764  cmp     byte ptr [rcx+69h], 1
0x18005a768  jb      short loc_18005A786
0x18005a76a  mov     rcx, [rcx+60h]
0x18005a76e  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005a775  mov     edx, 10Ch
0x18005a77a  mov     dword ptr [rsp+6F0h+lpSearchFilter], eax
0x18005a77e  mov     r9, rdi
0x18005a781  call    WPP_SF_Sd
0x18005a786  mov     rcx, rsi; hFindFile
0x18005a789  call    cs:__imp_FindClose
0x18005a78f  mov     eax, ebx
0x18005a791  mov     rcx, [rbp+5F0h+var_40]
0x18005a798  xor     rcx, rsp; StackCookie
0x18005a79b  call    __security_check_cookie
0x18005a7a0  add     rsp, 6C0h
0x18005a7a7  pop     r15
0x18005a7a9  pop     r14
0x18005a7ab  pop     r13
0x18005a7ad  pop     rdi
0x18005a7ae  pop     rsi
0x18005a7af  pop     rbx
0x18005a7b0  pop     rbp
0x18005a7b1  retn
```
