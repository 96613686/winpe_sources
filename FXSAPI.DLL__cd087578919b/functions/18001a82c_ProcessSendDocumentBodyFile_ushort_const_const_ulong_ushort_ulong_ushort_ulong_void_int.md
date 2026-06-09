# ProcessSendDocumentBodyFile(ushort const * * const,ulong,ushort *,ulong,ushort *,ulong,void *,int *)

- ea: `0x18001a82c`
- end: `0x18001ad21`
- name: `?ProcessSendDocumentBodyFile@@YAKQEAPEBGKPEAGK1KPEAXPEAH@Z`
- size: `1269`
- prototype: `__int64 __fastcall(const unsigned __int16 **const, unsigned int, unsigned __int16 *, __int64, unsigned __int16 *, unsigned int, void *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180019d54`

## callees

- `0x180008438`
- `0x18000abe4`
- `0x18000ac14`
- `0x180016124`
- `0x180016964`
- `0x180016de4`
- `0x18001a7a0`
- `0x18001a82c`
- `0x180021530`
- `0x18002bb58`
- `0x180031098`
- `0x180036b20`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18001aa4f`
- `KERNEL32!DeleteFileW` at `0x18001ace8`
- `KERNEL32!DeleteFileW` at `0x18001aa4f`
- `KERNEL32!DeleteFileW` at `0x18001ace8`
- `KERNEL32!CloseHandle` at `0x18001abed`
- `KERNEL32!CloseHandle` at `0x18001ac09`
- `KERNEL32!CloseHandle` at `0x18001abed`
- `KERNEL32!CloseHandle` at `0x18001ac09`
- `KERNEL32!GetLastError` at `0x18001a93a`
- `KERNEL32!GetLastError` at `0x18001a9cf`
- `KERNEL32!GetLastError` at `0x18001aa7c`
- `KERNEL32!GetLastError` at `0x18001ab27`
- `KERNEL32!GetLastError` at `0x18001ab9e`
- `KERNEL32!GetLastError` at `0x18001a93a`
- `KERNEL32!GetLastError` at `0x18001a9cf`
- `KERNEL32!GetLastError` at `0x18001aa7c`
- `KERNEL32!GetLastError` at `0x18001ab27`
- `KERNEL32!GetLastError` at `0x18001ab9e`

## pseudocode

```c
__int64 __fastcall ProcessSendDocumentBodyFile(
        const unsigned __int16 **const a1,
        unsigned int a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned int a6,
        void *a7,
        int *a8)
{
  unsigned int v10; // r8d
  _QWORD *v11; // rcx
  unsigned int v13; // r8d
  int v14; // esi
  DWORD LastError; // edi
  _QWORD *v16; // rcx
  const unsigned __int16 *v17; // r9
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  const unsigned __int16 *v20; // rax
  char *v21; // r9
  int v22; // edx
  WCHAR *FaxPrinterName; // rbx
  void *File; // r14
  void *v25; // r11
  const unsigned __int16 *v26; // rax
  int v27; // edx
  int v28; // ecx
  void *v29; // [rsp+20h] [rbp-E0h]
  DWORD v30; // [rsp+20h] [rbp-E0h]
  WCHAR v33[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR FileName[264]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(v33, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x1000) != 0 && *((_BYTE *)v11 + 25) >= 2u )
      WPP_SF_(v11[2], 131, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
    return 87;
  }
  if ( !CreateFinalTiffFile(*a1, v33, v10, a7) )
  {
    v14 = 0;
    LastError = GetLastError();
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = *a1;
      v18 = 132;
      goto LABEL_16;
    }
    goto LABEL_53;
  }
  LastError = 0;
  v14 = 1;
  if ( a2 > 1 )
  {
    while ( 1 )
    {
      if ( !CreateFinalTiffFile(a1[v14], FileName, v13, a7) )
      {
        LastError = GetLastError();
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = a1[v14];
          v18 = 133;
LABEL_16:
          WPP_SF_S(v16[2], v18, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v17);
        }
LABEL_53:
        if ( LastError )
        {
LABEL_64:
          if ( a8 )
          {
            if ( v14 == a2 )
              v14 = -1;
            *a8 = v14;
          }
          v26 = *a1;
          do
          {
            v27 = *(const unsigned __int16 *)((char *)v26 + (char *)v33 - (char *)*a1);
            v28 = *v26 - v27;
            if ( v28 )
              break;
            ++v26;
          }
          while ( v27 );
          if ( v28 )
            DeleteFileW(v33);
        }
        return LastError;
      }
      if ( !(unsigned int)MergeTiffFiles(v33, FileName) )
      {
        LastError = GetLastError();
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_25;
        }
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, a1[v14]);
      }
      v19 = WPP_GLOBAL_Control;
LABEL_25:
      v20 = a1[v14];
      v21 = (char *)((char *)FileName - (char *)v20);
      do
      {
        v22 = *(unsigned __int16 *)&v21[(_QWORD)v20];
        v13 = *v20 - v22;
        if ( v13 )
          break;
        ++v20;
      }
      while ( v22 );
      if ( v13 )
      {
        DeleteFileW(FileName);
        v19 = WPP_GLOBAL_Control;
      }
      if ( LastError )
        goto LABEL_64;
      if ( ++v14 >= a2 )
        goto LABEL_38;
    }
  }
  v19 = WPP_GLOBAL_Control;
LABEL_38:
  if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x1000) != 0 && *((_BYTE *)v19 + 25) >= 5u )
    WPP_SF_S(v19[2], 135, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v33);
  FaxPrinterName = GetFaxPrinterName(a7);
  File = (void *)SafePrinterNotifyWaitCreateFile(FaxPrinterName, v33, v29);
  pMemFree(FaxPrinterName);
  if ( File == (void *)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        136,
        (unsigned int)&WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids,
        (unsigned int)FileName,
        LastError);
    }
    goto LABEL_53;
  }
  if ( !(unsigned int)CopyFileToServerQueueW((int)a7, (int)File, (int)L"tif", (int)a5, v30) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, FileName);
    }
    CloseHandle(File);
    goto LABEL_53;
  }
  CloseHandle(File);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, a5);
  }
  if ( (int)StringCchCopyW(a3, 0x104u, v33) < 0 )
  {
    LastError = 8;
    if ( WPP_GLOBAL_Control != v25
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, 8);
    }
    goto LABEL_64;
  }
  return LastError;
}

```

## disassembly

```asm
0x18001a82c  mov     [rsp-8+arg_8], rbx
0x18001a831  push    rbp
0x18001a832  push    rsi
0x18001a833  push    rdi
0x18001a834  push    r12
0x18001a836  push    r13
0x18001a838  push    r14
0x18001a83a  push    r15
0x18001a83c  lea     rbp, [rsp-390h]
0x18001a844  sub     rsp, 490h
0x18001a84b  mov     rax, cs:__security_cookie
0x18001a852  xor     rax, rsp
0x18001a855  mov     [rbp+3C0h+var_40], rax
0x18001a85c  mov     rax, [rbp+3C0h+arg_38]
0x18001a863  mov     r14d, edx
0x18001a866  mov     r13, [rbp+3C0h+arg_20]
0x18001a86d  mov     r15, rcx
0x18001a870  mov     r12, [rbp+3C0h+arg_30]
0x18001a877  lea     rcx, [rsp+4C0h+var_460]; void *
0x18001a87c  mov     [rsp+4C0h+var_478], r8
0x18001a881  mov     ebx, 208h
0x18001a886  mov     [rsp+4C0h+var_480], edx
0x18001a88a  mov     r8d, ebx; Size
0x18001a88d  xor     edx, edx; Val
0x18001a88f  mov     [rsp+4C0h+var_470], rax
0x18001a894  call    memset_0
0x18001a899  mov     r8d, ebx; Size
0x18001a89c  lea     rcx, [rbp+3C0h+FileName]; void *
0x18001a8a3  xor     edx, edx; Val
0x18001a8a5  call    memset_0
0x18001a8aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8b1  lea     rax, WPP_GLOBAL_Control
0x18001a8b8  mov     ebx, 1000h
0x18001a8bd  cmp     rcx, rax
0x18001a8c0  jz      short loc_18001A8F0
0x18001a8c2  test    [rcx+1Ch], ebx
0x18001a8c5  jz      short loc_18001A8F0
0x18001a8c7  cmp     byte ptr [rcx+19h], 5
0x18001a8cb  jb      short loc_18001A8F0
0x18001a8cd  mov     rcx, [rcx+10h]
0x18001a8d1  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001a8d8  mov     edx, 82h
0x18001a8dd  call    WPP_SF_
0x18001a8e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8e9  lea     rax, WPP_GLOBAL_Control
0x18001a8f0  test    r15, r15
0x18001a8f3  jnz     short loc_18001A924
0x18001a8f5  cmp     rcx, rax
0x18001a8f8  jz      short loc_18001A91A
0x18001a8fa  test    [rcx+1Ch], ebx
0x18001a8fd  jz      short loc_18001A91A
0x18001a8ff  cmp     byte ptr [rcx+19h], 2
0x18001a903  jb      short loc_18001A91A
0x18001a905  mov     rcx, [rcx+10h]
0x18001a909  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001a910  mov     edx, 83h
0x18001a915  call    WPP_SF_
0x18001a91a  mov     eax, 57h ; 'W'
0x18001a91f  jmp     loc_18001ACF6
0x18001a924  mov     rcx, [r15]; unsigned __int16 *
0x18001a927  lea     rdx, [rsp+4C0h+var_460]; unsigned __int16 *
0x18001a92c  mov     r9, r12; void *
0x18001a92f  call    ?CreateFinalTiffFile@@YAHPEBGPEAGKPEAX@Z; CreateFinalTiffFile(ushort const *,ushort *,ulong,void *)
0x18001a934  test    eax, eax
0x18001a936  jnz     short loc_18001A98F
0x18001a938  xor     esi, esi
0x18001a93a  call    cs:__imp_GetLastError
0x18001a941  nop     dword ptr [rax+rax+00h]
0x18001a946  mov     edi, eax
0x18001a948  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a94f  lea     rax, WPP_GLOBAL_Control
0x18001a956  cmp     rcx, rax
0x18001a959  jz      loc_18001ABF9
0x18001a95f  test    [rcx+1Ch], ebx
0x18001a962  jz      loc_18001ABF9
0x18001a968  cmp     byte ptr [rcx+19h], 2
0x18001a96c  jb      loc_18001ABF9
0x18001a972  mov     r9, [r15]
0x18001a975  mov     edx, 84h
0x18001a97a  mov     rcx, [rcx+10h]
0x18001a97e  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001a985  call    WPP_SF_S
0x18001a98a  jmp     loc_18001ABF9
0x18001a98f  xor     edi, edi
0x18001a991  lea     esi, [rdi+1]
0x18001a994  cmp     r14d, esi
0x18001a997  jbe     loc_18001AAC6
0x18001a99d  mov     ebx, esi
0x18001a99f  lea     rdx, [rbp+3C0h+FileName]; unsigned __int16 *
0x18001a9a6  mov     r9, r12; void *
0x18001a9a9  mov     rcx, [r15+rbx*8]; unsigned __int16 *
0x18001a9ad  call    ?CreateFinalTiffFile@@YAHPEBGPEAGKPEAX@Z; CreateFinalTiffFile(ushort const *,ushort *,ulong,void *)
0x18001a9b2  test    eax, eax
0x18001a9b4  jz      loc_18001AA7C
0x18001a9ba  lea     rdx, [rbp+3C0h+FileName]; LPCWSTR
0x18001a9c1  lea     rcx, [rsp+4C0h+var_460]; lpFileName
0x18001a9c6  call    MergeTiffFiles
0x18001a9cb  test    eax, eax
0x18001a9cd  jnz     short loc_18001AA18
0x18001a9cf  call    cs:__imp_GetLastError
0x18001a9d6  nop     dword ptr [rax+rax+00h]
0x18001a9db  mov     edi, eax
0x18001a9dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9e4  lea     rax, WPP_GLOBAL_Control
0x18001a9eb  cmp     rcx, rax
0x18001a9ee  jz      short loc_18001AA1F
0x18001a9f0  test    dword ptr [rcx+1Ch], 1000h
0x18001a9f7  jz      short loc_18001AA1F
0x18001a9f9  cmp     byte ptr [rcx+19h], 2
0x18001a9fd  jb      short loc_18001AA1F
0x18001a9ff  mov     r9, [r15+rbx*8]
0x18001aa03  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001aa0a  mov     rcx, [rcx+10h]
0x18001aa0e  mov     edx, 86h
0x18001aa13  call    WPP_SF_S
0x18001aa18  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa1f  mov     rax, [r15+rbx*8]
0x18001aa23  lea     r9, [rbp+3C0h+FileName]
0x18001aa2a  sub     r9, rax
0x18001aa2d  movzx   r8d, word ptr [rax]
0x18001aa31  movzx   edx, word ptr [rax+r9]
0x18001aa36  sub     r8d, edx
0x18001aa39  jnz     short loc_18001AA43
0x18001aa3b  add     rax, 2
0x18001aa3f  test    edx, edx
0x18001aa41  jnz     short loc_18001AA2D
0x18001aa43  test    r8d, r8d
0x18001aa46  jz      short loc_18001AA62
0x18001aa48  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x18001aa4f  call    cs:__imp_DeleteFileW
0x18001aa56  nop     dword ptr [rax+rax+00h]
0x18001aa5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa62  test    edi, edi
0x18001aa64  jnz     loc_18001ACAA
0x18001aa6a  inc     esi
0x18001aa6c  cmp     esi, r14d
0x18001aa6f  jb      loc_18001A99D
0x18001aa75  mov     ebx, 1000h
0x18001aa7a  jmp     short loc_18001AACD
0x18001aa7c  call    cs:__imp_GetLastError
0x18001aa83  nop     dword ptr [rax+rax+00h]
0x18001aa88  mov     edi, eax
0x18001aa8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa91  lea     rax, WPP_GLOBAL_Control
0x18001aa98  cmp     rcx, rax
0x18001aa9b  jz      loc_18001ABF9
0x18001aaa1  test    dword ptr [rcx+1Ch], 1000h
0x18001aaa8  jz      loc_18001ABF9
0x18001aaae  cmp     byte ptr [rcx+19h], 2
0x18001aab2  jb      loc_18001ABF9
0x18001aab8  mov     r9, [r15+rbx*8]
0x18001aabc  mov     edx, 85h
0x18001aac1  jmp     loc_18001A97A
0x18001aac6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aacd  lea     rax, WPP_GLOBAL_Control
0x18001aad4  cmp     rcx, rax
0x18001aad7  jz      short loc_18001AAFE
0x18001aad9  test    [rcx+1Ch], ebx
0x18001aadc  jz      short loc_18001AAFE
0x18001aade  cmp     byte ptr [rcx+19h], 5
0x18001aae2  jb      short loc_18001AAFE
0x18001aae4  mov     rcx, [rcx+10h]
0x18001aae8  lea     r9, [rsp+4C0h+var_460]
0x18001aaed  mov     edx, 87h
0x18001aaf2  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001aaf9  call    WPP_SF_S
0x18001aafe  mov     rcx, r12; void *
0x18001ab01  call    ?GetFaxPrinterName@@YAPEAGPEAX@Z; GetFaxPrinterName(void *)
0x18001ab06  lea     rdx, [rsp+4C0h+var_460]; lpFileName
0x18001ab0b  mov     rcx, rax; pPrinterName
0x18001ab0e  mov     rbx, rax
0x18001ab11  call    SafePrinterNotifyWaitCreateFile
0x18001ab16  mov     rcx, rbx; lpMem
0x18001ab19  mov     r14, rax
0x18001ab1c  call    pMemFree
0x18001ab21  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18001ab25  jnz     short loc_18001AB85
0x18001ab27  call    cs:__imp_GetLastError
0x18001ab2e  nop     dword ptr [rax+rax+00h]
0x18001ab33  mov     edi, eax
0x18001ab35  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab3c  lea     rax, WPP_GLOBAL_Control
0x18001ab43  cmp     rcx, rax
0x18001ab46  jz      loc_18001ABF9
0x18001ab4c  test    dword ptr [rcx+1Ch], 1000h
0x18001ab53  jz      loc_18001ABF9
0x18001ab59  cmp     byte ptr [rcx+19h], 2
0x18001ab5d  jb      loc_18001ABF9
0x18001ab63  mov     rcx, [rcx+10h]
0x18001ab67  lea     r9, [rbp+3C0h+FileName]
0x18001ab6e  mov     edx, 88h
0x18001ab73  mov     [rsp+4C0h+var_4A0], edi
0x18001ab77  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001ab7e  call    WPP_SF_Sd
0x18001ab83  jmp     short loc_18001ABF9
0x18001ab85  mov     r9, r13; int
0x18001ab88  lea     r8, aTif; "tif"
0x18001ab8f  mov     rdx, r14; int
0x18001ab92  mov     rcx, r12; int
0x18001ab95  call    CopyFileToServerQueueW
0x18001ab9a  test    eax, eax
0x18001ab9c  jnz     short loc_18001AC06
0x18001ab9e  call    cs:__imp_GetLastError
0x18001aba5  nop     dword ptr [rax+rax+00h]
0x18001abaa  mov     edi, eax
0x18001abac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abb3  lea     rax, WPP_GLOBAL_Control
0x18001abba  cmp     rcx, rax
0x18001abbd  jz      short loc_18001ABEA
0x18001abbf  test    dword ptr [rcx+1Ch], 1000h
0x18001abc6  jz      short loc_18001ABEA
0x18001abc8  cmp     byte ptr [rcx+19h], 2
0x18001abcc  jb      short loc_18001ABEA
0x18001abce  mov     rcx, [rcx+10h]
0x18001abd2  lea     r9, [rbp+3C0h+FileName]
0x18001abd9  mov     edx, 89h
0x18001abde  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001abe5  call    WPP_SF_S
0x18001abea  mov     rcx, r14; hObject
0x18001abed  call    cs:__imp_CloseHandle
0x18001abf4  nop     dword ptr [rax+rax+00h]
0x18001abf9  test    edi, edi
0x18001abfb  jz      loc_18001ACF4
0x18001ac01  jmp     loc_18001ACAA
0x18001ac06  mov     rcx, r14; hObject
0x18001ac09  call    cs:__imp_CloseHandle
0x18001ac10  nop     dword ptr [rax+rax+00h]
0x18001ac15  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac1c  lea     r11, WPP_GLOBAL_Control
0x18001ac23  cmp     rcx, r11
0x18001ac26  jz      short loc_18001AC56
0x18001ac28  test    dword ptr [rcx+1Ch], 1000h
0x18001ac2f  jz      short loc_18001AC56
0x18001ac31  cmp     byte ptr [rcx+19h], 5
0x18001ac35  jb      short loc_18001AC56
0x18001ac37  mov     rcx, [rcx+10h]
0x18001ac3b  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001ac42  mov     edx, 8Ah
0x18001ac47  mov     r9, r13
0x18001ac4a  call    WPP_SF_S
0x18001ac4f  lea     r11, WPP_GLOBAL_Control
0x18001ac56  mov     rcx, [rsp+4C0h+var_478]; unsigned __int16 *
0x18001ac5b  lea     r8, [rsp+4C0h+var_460]; unsigned __int16 *
0x18001ac60  mov     edx, 104h; unsigned __int64
0x18001ac65  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ac6a  test    eax, eax
0x18001ac6c  jns     loc_18001ACF4
0x18001ac72  mov     edi, 8
0x18001ac77  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac7e  cmp     rcx, r11
0x18001ac81  jz      short loc_18001ACAA
0x18001ac83  test    dword ptr [rcx+1Ch], 1000h
0x18001ac8a  jz      short loc_18001ACAA
0x18001ac8c  cmp     byte ptr [rcx+19h], 2
0x18001ac90  jb      short loc_18001ACAA
0x18001ac92  mov     rcx, [rcx+10h]
0x18001ac96  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001ac9d  mov     edx, 8Bh
0x18001aca2  mov     r9d, edi
0x18001aca5  call    WPP_SF_d
0x18001acaa  mov     rax, [rsp+4C0h+var_470]
0x18001acaf  test    rax, rax
0x18001acb2  jz      short loc_18001ACC0
0x18001acb4  or      ecx, 0FFFFFFFFh
0x18001acb7  cmp     esi, [rsp+4C0h+var_480]
0x18001acbb  cmovz   esi, ecx
0x18001acbe  mov     [rax], esi
0x18001acc0  mov     rax, [r15]
0x18001acc3  lea     r8, [rsp+4C0h+var_460]
0x18001acc8  sub     r8, rax
0x18001accb  movzx   ecx, word ptr [rax]
0x18001acce  movzx   edx, word ptr [rax+r8]
0x18001acd3  sub     ecx, edx
0x18001acd5  jnz     short loc_18001ACDF
0x18001acd7  add     rax, 2
0x18001acdb  test    edx, edx
0x18001acdd  jnz     short loc_18001ACCB
0x18001acdf  test    ecx, ecx
0x18001ace1  jz      short loc_18001ACF4
0x18001ace3  lea     rcx, [rsp+4C0h+var_460]; lpFileName
0x18001ace8  call    cs:__imp_DeleteFileW
0x18001acef  nop     dword ptr [rax+rax+00h]
0x18001acf4  mov     eax, edi
0x18001acf6  mov     rcx, [rbp+3C0h+var_40]
0x18001acfd  xor     rcx, rsp; StackCookie
0x18001ad00  call    __security_check_cookie
0x18001ad05  mov     rbx, [rsp+4C0h+arg_8]
0x18001ad0d  add     rsp, 490h
0x18001ad14  pop     r15
0x18001ad16  pop     r14
0x18001ad18  pop     r13
0x18001ad1a  pop     r12
0x18001ad1c  pop     rdi
0x18001ad1d  pop     rsi
0x18001ad1e  pop     rbp
0x18001ad1f  retn
```
