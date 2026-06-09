# ValidateFaxSendDocumentParams(void *,ushort const * * const,ulong,_FAX_COVERPAGE_INFO_EXW const *,_FAX_PERSONAL_PROFILEW const *,_FAX_JOB_PARAM_EXW const *,ulong,int *)

- ea: `0x18001ba58`
- end: `0x18001c19c`
- name: `?ValidateFaxSendDocumentParams@@YAHPEAXQEAPEBGKPEBU_FAX_COVERPAGE_INFO_EXW@@PEBU_FAX_PERSONAL_PROFILEW@@PEBU_FAX_JOB_PARAM_EXW@@KPEAH@Z`
- size: `1860`
- prototype: `_BOOL8 __fastcall(_DWORD *, const unsigned __int16 **const, __int64, const struct _FAX_COVERPAGE_INFO_EXW *, const struct _FAX_PERSONAL_PROFILEW *, const struct _FAX_JOB_PARAM_EXW *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180019d54`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000f220`
- `0x180014314`
- `0x18001a7a0`
- `0x18001ba58`
- `0x180021438`
- `0x180021530`
- `0x18002bb58`
- `0x180031098`
- `0x18003d510`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x18001bd36`
- `KERNEL32!GetFullPathNameW` at `0x18001bd36`
- `KERNEL32!GetFileAttributesW` at `0x18001bd56`
- `KERNEL32!GetFileAttributesW` at `0x18001bd56`
- `KERNEL32!GetFileSize` at `0x18001bd9d`
- `KERNEL32!GetFileSize` at `0x18001bd9d`
- `KERNEL32!CloseHandle` at `0x18001bdb7`
- `KERNEL32!CloseHandle` at `0x18001bed9`
- `KERNEL32!CloseHandle` at `0x18001bdb7`
- `KERNEL32!CloseHandle` at `0x18001bed9`
- `KERNEL32!SetLastError` at `0x18001c15d`
- `KERNEL32!SetLastError` at `0x18001c15d`
- `KERNEL32!GetLastError` at `0x18001be52`
- `KERNEL32!GetLastError` at `0x18001be8e`
- `KERNEL32!GetLastError` at `0x18001beea`
- `KERNEL32!GetLastError` at `0x18001bf77`
- `KERNEL32!GetLastError` at `0x18001bfcf`
- `KERNEL32!GetLastError` at `0x18001c006`
- `KERNEL32!GetLastError` at `0x18001be52`
- `KERNEL32!GetLastError` at `0x18001be8e`
- `KERNEL32!GetLastError` at `0x18001beea`
- `KERNEL32!GetLastError` at `0x18001bf77`
- `KERNEL32!GetLastError` at `0x18001bfcf`
- `KERNEL32!GetLastError` at `0x18001c006`

## pseudocode

```c
_BOOL8 __fastcall ValidateFaxSendDocumentParams(
        _DWORD *a1,
        const unsigned __int16 **const a2,
        __int64 a3,
        const struct _FAX_COVERPAGE_INFO_EXW *a4,
        const struct _FAX_PERSONAL_PROFILEW *a5,
        const struct _FAX_JOB_PARAM_EXW *a6,
        unsigned int a7,
        int *a8)
{
  int v11; // r14d
  _DWORD *v12; // rcx
  __int64 v13; // rdx
  DWORD v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // r9
  __int64 v18; // rdx
  DWORD FullPathNameW; // ebx
  WCHAR *FaxPrinterName; // rbx
  void *File; // rbp
  DWORD FileSize; // ebx
  DWORD v23; // eax
  DWORD v24; // eax
  char LastError; // al
  DWORD v26; // eax
  void *v28; // [rsp+20h] [rbp-298h]
  int v29; // [rsp+40h] [rbp-278h] BYREF
  LPWSTR FilePart; // [rsp+48h] [rbp-270h] BYREF
  int *v31; // [rsp+50h] [rbp-268h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-258h] BYREF

  v31 = a8;
  v11 = -1;
  v29 = a3;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
    v12 = WPP_GLOBAL_Control;
    a3 = (unsigned int)v29;
  }
  if ( a1 && *a1 && !a1[4] )
  {
    if ( a2 )
    {
      if ( !a4 )
        goto LABEL_36;
    }
    else if ( !a4 || *((_DWORD *)a4 + 1) == 2 )
    {
      if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x1000) == 0 || *((_BYTE *)v12 + 25) < 2u )
        goto LABEL_16;
      v13 = 152;
      goto LABEL_15;
    }
    if ( *(_DWORD *)a4 != 40 )
    {
      if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x1000) == 0 || *((_BYTE *)v12 + 25) < 2u )
        goto LABEL_16;
      v15 = 153;
      goto LABEL_23;
    }
    v16 = *((unsigned int *)a4 + 1);
    if ( (_DWORD)v16 != 1 )
    {
      if ( (_DWORD)v16 != 2 )
      {
        if ( v12 != (_DWORD *)&WPP_GLOBAL_Control && (v12[7] & 0x1000) != 0 && *((_BYTE *)v12 + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)v12 + 2), 154, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v16);
        goto LABEL_16;
      }
LABEL_36:
      if ( a5 )
      {
        if ( *(_DWORD *)a5 != 136 )
        {
          if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x1000) == 0 || *((_BYTE *)v12 + 25) < 2u )
            goto LABEL_16;
          v15 = 156;
          goto LABEL_23;
        }
        if ( a6 )
        {
          if ( *(_DWORD *)a6 != 96 )
          {
            if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x1000) == 0 || *((_BYTE *)v12 + 25) < 2u )
              goto LABEL_16;
            v15 = 158;
LABEL_23:
            WPP_SF_dd(*((_QWORD *)v12 + 2), v15, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
            goto LABEL_16;
          }
          v17 = *((unsigned int *)a6 + 1);
          if ( (unsigned int)v17 >= 3 )
          {
            if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x1000) == 0 || *((_BYTE *)v12 + 25) < 2u )
              goto LABEL_16;
            v18 = 159;
            goto LABEL_53;
          }
          v17 = *((unsigned int *)a6 + 6);
          if ( (v17 & 0xFFFFFFE2) != 0 )
          {
            if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x1000) == 0 || *((_BYTE *)v12 + 25) < 2u )
              goto LABEL_16;
            v18 = 160;
            goto LABEL_53;
          }
          if ( (v17 & 0xFFFFFFE7) == 5 )
          {
            if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x1000) == 0 || *((_BYTE *)v12 + 25) < 2u )
              goto LABEL_16;
            v18 = 161;
LABEL_53:
            WPP_SF_d(*((_QWORD *)v12 + 2), v18, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v17);
            goto LABEL_16;
          }
          if ( a2 )
          {
            FilePart = 0;
            v11 = 0;
            if ( (int)a3 > 0 )
            {
              while ( 1 )
              {
                FullPathNameW = GetFullPathNameW(a2[v11], 0x104u, Buffer, &FilePart);
                if ( FullPathNameW - 1 > 0x103 )
                  break;
                if ( GetFileAttributesW(Buffer) == -1 )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    LastError = GetLastError();
                    WPP_SF_Sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      164,
                      (unsigned int)&WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids,
                      (unsigned int)Buffer,
                      LastError);
                  }
                  goto LABEL_35;
                }
                FaxPrinterName = GetFaxPrinterName(a1);
                File = (void *)SafePrinterNotifyWaitCreateFile(FaxPrinterName, Buffer, v28);
                pMemFree(FaxPrinterName);
                if ( File == (void *)-1LL )
                {
                  v24 = GetLastError();
                  v14 = v24;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_Sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      165,
                      (unsigned int)&WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids,
                      (unsigned int)Buffer,
                      v24);
                  }
                  goto LABEL_130;
                }
                FileSize = GetFileSize(File, 0);
                if ( FileSize == -1 )
                {
                  v23 = GetLastError();
                  v14 = v23;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      166,
                      &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids,
                      v23);
                  }
                  CloseHandle(File);
                  goto LABEL_130;
                }
                CloseHandle(File);
                if ( !FileSize )
                {
                  v14 = 13;
                  goto LABEL_130;
                }
                if ( ++v11 >= v29 )
                {
                  v12 = WPP_GLOBAL_Control;
                  goto LABEL_69;
                }
              }
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v26 = GetLastError();
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  163,
                  &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids,
                  v26);
              }
              if ( FullPathNameW <= 0x104 )
              {
                v14 = GetLastError();
                goto LABEL_130;
              }
              goto LABEL_16;
            }
          }
LABEL_69:
          if ( a4 && *((_DWORD *)a4 + 1) == 1 && !*((_DWORD *)a4 + 4) )
          {
            v29 = 1;
            if ( !(unsigned int)FaxGetPersonalCoverPagesOption(a1, &v29) )
            {
              v14 = 0;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v14 = GetLastError();
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  167,
                  &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids,
                  v14);
              }
LABEL_107:
              v11 = -1;
              goto LABEL_130;
            }
            if ( !v29 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
              }
              v14 = 1920;
              goto LABEL_107;
            }
            v12 = WPP_GLOBAL_Control;
          }
          if ( *((_DWORD *)a6 + 11) || *((_QWORD *)a6 + 6) == 4294906420LL )
          {
            if ( v12 != (_DWORD *)&WPP_GLOBAL_Control && (v12[7] & 0x1000) != 0 && *((_BYTE *)v12 + 25) >= 2u )
              WPP_SF_(*((_QWORD *)v12 + 2), 169, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
            v14 = 50;
          }
          else
          {
            v14 = 0;
          }
          goto LABEL_107;
        }
        if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x1000) == 0 || *((_BYTE *)v12 + 25) < 2u )
          goto LABEL_16;
        v13 = 162;
      }
      else
      {
        if ( v12 == (_DWORD *)&WPP_GLOBAL_Control || (v12[7] & 0x1000) == 0 || *((_BYTE *)v12 + 25) < 2u )
          goto LABEL_16;
        v13 = 157;
      }
LABEL_15:
      WPP_SF_(*((_QWORD *)v12 + 2), v13, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
LABEL_16:
      v14 = 87;
      goto LABEL_130;
    }
    if ( *((_QWORD *)a4 + 1) )
      goto LABEL_36;
    if ( v12 != (_DWORD *)&WPP_GLOBAL_Control && (v12[7] & 0x1000) != 0 && *((_BYTE *)v12 + 25) >= 2u )
      WPP_SF_(*((_QWORD *)v12 + 2), 155, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
LABEL_35:
    v14 = 2;
  }
  else
  {
    if ( v12 != (_DWORD *)&WPP_GLOBAL_Control && (v12[7] & 0x1000) != 0 && *((_BYTE *)v12 + 25) >= 2u )
      WPP_SF_P(*((_QWORD *)v12 + 2), 150, a3, a1);
    v14 = 6;
  }
LABEL_130:
  if ( v31 )
    *v31 = v11;
  SetLastError(v14);
  return v14 == 0;
}

```

## disassembly

```asm
0x18001ba58  mov     [rsp+arg_10], rbx
0x18001ba5d  push    rbp
0x18001ba5e  push    rsi
0x18001ba5f  push    rdi
0x18001ba60  push    r12
0x18001ba62  push    r13
0x18001ba64  push    r14
0x18001ba66  push    r15
0x18001ba68  sub     rsp, 280h
0x18001ba6f  mov     rax, cs:__security_cookie
0x18001ba76  xor     rax, rsp
0x18001ba79  mov     [rsp+2B8h+var_48], rax
0x18001ba81  mov     rax, [rsp+2B8h+arg_38]
0x18001ba89  mov     rsi, r9
0x18001ba8c  mov     r15, [rsp+2B8h+arg_28]
0x18001ba94  mov     r13, rdx
0x18001ba97  mov     rbx, [rsp+2B8h+arg_20]
0x18001ba9f  mov     r12, rcx
0x18001baa2  mov     [rsp+2B8h+var_268], rax
0x18001baa7  or      r14d, 0FFFFFFFFh
0x18001baab  mov     [rsp+2B8h+var_278], r8d
0x18001bab0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bab7  lea     rdx, WPP_GLOBAL_Control
0x18001babe  lea     r11, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001bac5  mov     ebp, 1000h
0x18001baca  cmp     rcx, rdx
0x18001bacd  jz      short loc_18001BB05
0x18001bacf  test    [rcx+1Ch], ebp
0x18001bad2  jz      short loc_18001BB05
0x18001bad4  cmp     byte ptr [rcx+19h], 5
0x18001bad8  jb      short loc_18001BB05
0x18001bada  mov     rcx, [rcx+10h]
0x18001bade  mov     edx, 95h
0x18001bae3  mov     r8, r11
0x18001bae6  call    WPP_SF_
0x18001baeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001baf2  lea     rdx, WPP_GLOBAL_Control
0x18001baf9  mov     r8d, [rsp+2B8h+var_278]
0x18001bafe  lea     r11, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001bb05  xor     r10d, r10d
0x18001bb08  test    r12, r12
0x18001bb0b  jz      loc_18001C123
0x18001bb11  cmp     [r12], r10d
0x18001bb15  jz      loc_18001C123
0x18001bb1b  cmp     [r12+10h], r10d
0x18001bb20  jnz     loc_18001C123
0x18001bb26  lea     edi, [r10+2]
0x18001bb2a  test    r13, r13
0x18001bb2d  jnz     short loc_18001BB64
0x18001bb2f  test    rsi, rsi
0x18001bb32  jz      short loc_18001BB39
0x18001bb34  cmp     [rsi+4], edi
0x18001bb37  jnz     short loc_18001BB6D
0x18001bb39  cmp     rcx, rdx
0x18001bb3c  jz      short loc_18001BB5A
0x18001bb3e  test    [rcx+1Ch], ebp
0x18001bb41  jz      short loc_18001BB5A
0x18001bb43  cmp     [rcx+19h], dil
0x18001bb47  jb      short loc_18001BB5A
0x18001bb49  mov     edx, 98h
0x18001bb4e  mov     rcx, [rcx+10h]
0x18001bb52  mov     r8, r11
0x18001bb55  call    WPP_SF_
0x18001bb5a  mov     ebx, 57h ; 'W'
0x18001bb5f  jmp     loc_18001C14E
0x18001bb64  test    rsi, rsi
0x18001bb67  jz      loc_18001BC01
0x18001bb6d  mov     r9d, [rsi]
0x18001bb70  cmp     r9d, 28h ; '('
0x18001bb74  jz      short loc_18001BBA1
0x18001bb76  cmp     rcx, rdx
0x18001bb79  jz      short loc_18001BB5A
0x18001bb7b  test    [rcx+1Ch], ebp
0x18001bb7e  jz      short loc_18001BB5A
0x18001bb80  cmp     [rcx+19h], dil
0x18001bb84  jb      short loc_18001BB5A
0x18001bb86  mov     edx, 99h
0x18001bb8b  mov     [rsp+2B8h+var_298], 28h ; '('
0x18001bb93  mov     rcx, [rcx+10h]
0x18001bb97  mov     r8, r11
0x18001bb9a  call    WPP_SF_dd
0x18001bb9f  jmp     short loc_18001BB5A
0x18001bba1  mov     r9d, [rsi+4]
0x18001bba5  cmp     r9d, 1
0x18001bba9  jz      short loc_18001BBD3
0x18001bbab  cmp     r9d, edi
0x18001bbae  jz      short loc_18001BC01
0x18001bbb0  cmp     rcx, rdx
0x18001bbb3  jz      short loc_18001BB5A
0x18001bbb5  test    [rcx+1Ch], ebp
0x18001bbb8  jz      short loc_18001BB5A
0x18001bbba  cmp     [rcx+19h], dil
0x18001bbbe  jb      short loc_18001BB5A
0x18001bbc0  mov     rcx, [rcx+10h]
0x18001bbc4  mov     edx, 9Ah
0x18001bbc9  mov     r8, r11
0x18001bbcc  call    WPP_SF_d
0x18001bbd1  jmp     short loc_18001BB5A
0x18001bbd3  cmp     [rsi+8], r10
0x18001bbd7  jnz     short loc_18001BC01
0x18001bbd9  cmp     rcx, rdx
0x18001bbdc  jz      short loc_18001BBFA
0x18001bbde  test    [rcx+1Ch], ebp
0x18001bbe1  jz      short loc_18001BBFA
0x18001bbe3  cmp     [rcx+19h], dil
0x18001bbe7  jb      short loc_18001BBFA
0x18001bbe9  mov     rcx, [rcx+10h]
0x18001bbed  mov     edx, 9Bh
0x18001bbf2  mov     r8, r11
0x18001bbf5  call    WPP_SF_
0x18001bbfa  mov     ebx, edi
0x18001bbfc  jmp     loc_18001C14E
0x18001bc01  test    rbx, rbx
0x18001bc04  jz      loc_18001C0FD
0x18001bc0a  mov     r9d, 88h
0x18001bc10  cmp     [rbx], r9d
0x18001bc13  jz      short loc_18001BC42
0x18001bc15  cmp     rcx, rdx
0x18001bc18  jz      loc_18001BB5A
0x18001bc1e  test    [rcx+1Ch], ebp
0x18001bc21  jz      loc_18001BB5A
0x18001bc27  cmp     [rcx+19h], dil
0x18001bc2b  jb      loc_18001BB5A
0x18001bc31  lea     edx, [r9+14h]
0x18001bc35  mov     [rsp+2B8h+var_298], r9d
0x18001bc3a  mov     r9d, [rbx]
0x18001bc3d  jmp     loc_18001BB93
0x18001bc42  test    r15, r15
0x18001bc45  jz      loc_18001C0D7
0x18001bc4b  cmp     dword ptr [r15], 60h ; '`'
0x18001bc4f  jz      short loc_18001BC7F
0x18001bc51  cmp     rcx, rdx
0x18001bc54  jz      loc_18001BB5A
0x18001bc5a  test    [rcx+1Ch], ebp
0x18001bc5d  jz      loc_18001BB5A
0x18001bc63  cmp     [rcx+19h], dil
0x18001bc67  jb      loc_18001BB5A
0x18001bc6d  mov     edx, 9Eh
0x18001bc72  mov     [rsp+2B8h+var_298], 60h ; '`'
0x18001bc7a  jmp     loc_18001BB93
0x18001bc7f  mov     r9d, [r15+4]
0x18001bc83  cmp     r9d, 3
0x18001bc87  jb      short loc_18001BCBB
0x18001bc89  cmp     rcx, rdx
0x18001bc8c  jz      loc_18001BB5A
0x18001bc92  test    [rcx+1Ch], ebp
0x18001bc95  jz      loc_18001BB5A
0x18001bc9b  cmp     [rcx+19h], dil
0x18001bc9f  jb      loc_18001BB5A
0x18001bca5  mov     edx, 9Fh
0x18001bcaa  mov     rcx, [rcx+10h]
0x18001bcae  mov     r8, r11
0x18001bcb1  call    WPP_SF_d
0x18001bcb6  jmp     loc_18001BB5A
0x18001bcbb  mov     r9d, [r15+18h]
0x18001bcbf  test    r9d, 0FFFFFFE2h
0x18001bcc6  jz      short loc_18001BCEB
0x18001bcc8  cmp     rcx, rdx
0x18001bccb  jz      loc_18001BB5A
0x18001bcd1  test    [rcx+1Ch], ebp
0x18001bcd4  jz      loc_18001BB5A
0x18001bcda  cmp     [rcx+19h], dil
0x18001bcde  jb      loc_18001BB5A
0x18001bce4  mov     edx, 0A0h
0x18001bce9  jmp     short loc_18001BCAA
0x18001bceb  mov     eax, r9d
0x18001bcee  and     eax, 0FFFFFFE7h
0x18001bcf1  test    eax, 0FFFFFFFAh
0x18001bcf6  jnz     loc_18001C0B1
0x18001bcfc  cmp     eax, 5
0x18001bcff  jz      loc_18001C0B1
0x18001bd05  test    r13, r13
0x18001bd08  jz      loc_18001BDE8
0x18001bd0e  mov     [rsp+2B8h+FilePart], r10
0x18001bd13  mov     r14d, r10d
0x18001bd16  test    r8d, r8d
0x18001bd19  jle     loc_18001BDE8
0x18001bd1f  mov     ecx, r14d
0x18001bd22  lea     r9, [rsp+2B8h+FilePart]; lpFilePart
0x18001bd27  lea     r8, [rsp+2B8h+Buffer]; lpBuffer
0x18001bd2c  mov     edx, 104h; nBufferLength
0x18001bd31  mov     rcx, [r13+rcx*8+0]; lpFileName
0x18001bd36  call    cs:__imp_GetFullPathNameW
0x18001bd3d  nop     dword ptr [rax+rax+00h]
0x18001bd42  mov     ebx, eax
0x18001bd44  dec     eax
0x18001bd46  cmp     eax, 103h
0x18001bd4b  ja      loc_18001BFAD
0x18001bd51  lea     rcx, [rsp+2B8h+Buffer]; lpFileName
0x18001bd56  call    cs:__imp_GetFileAttributesW
0x18001bd5d  nop     dword ptr [rax+rax+00h]
0x18001bd62  cmp     eax, 0FFFFFFFFh
0x18001bd65  jz      loc_18001BF49
0x18001bd6b  mov     rcx, r12; void *
0x18001bd6e  call    ?GetFaxPrinterName@@YAPEAGPEAX@Z; GetFaxPrinterName(void *)
0x18001bd73  lea     rdx, [rsp+2B8h+Buffer]; lpFileName
0x18001bd78  mov     rcx, rax; pPrinterName
0x18001bd7b  mov     rbx, rax
0x18001bd7e  call    SafePrinterNotifyWaitCreateFile
0x18001bd83  mov     rcx, rbx; lpMem
0x18001bd86  mov     rbp, rax
0x18001bd89  call    pMemFree
0x18001bd8e  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18001bd92  jz      loc_18001BEEA
0x18001bd98  xor     edx, edx; lpFileSizeHigh
0x18001bd9a  mov     rcx, rbp; hFile
0x18001bd9d  call    cs:__imp_GetFileSize
0x18001bda4  nop     dword ptr [rax+rax+00h]
0x18001bda9  mov     ebx, eax
0x18001bdab  cmp     eax, 0FFFFFFFFh
0x18001bdae  jz      loc_18001BE8E
0x18001bdb4  mov     rcx, rbp; hObject
0x18001bdb7  call    cs:__imp_CloseHandle
0x18001bdbe  nop     dword ptr [rax+rax+00h]
0x18001bdc3  xor     r10d, r10d
0x18001bdc6  test    ebx, ebx
0x18001bdc8  jz      loc_18001BE84
0x18001bdce  inc     r14d
0x18001bdd1  cmp     r14d, [rsp+2B8h+var_278]
0x18001bdd6  jl      loc_18001BD1F
0x18001bddc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bde3  mov     ebp, 1000h
0x18001bde8  test    rsi, rsi
0x18001bdeb  jz      loc_18001C061
0x18001bdf1  cmp     dword ptr [rsi+4], 1
0x18001bdf5  jnz     loc_18001C061
0x18001bdfb  cmp     [rsi+10h], r10d
0x18001bdff  jnz     loc_18001C061
0x18001be05  lea     rdx, [rsp+2B8h+var_278]
0x18001be0a  mov     [rsp+2B8h+var_278], 1
0x18001be12  mov     rcx, r12
0x18001be15  call    FaxGetPersonalCoverPagesOption
0x18001be1a  xor     r10d, r10d
0x18001be1d  test    eax, eax
0x18001be1f  jnz     loc_18001C019
0x18001be25  mov     ebx, r10d
0x18001be28  mov     rax, cs:WPP_GLOBAL_Control
0x18001be2f  lea     rdx, WPP_GLOBAL_Control
0x18001be36  cmp     rax, rdx
0x18001be39  jz      loc_18001C075
0x18001be3f  test    [rax+1Ch], ebp
0x18001be42  jz      loc_18001C075
0x18001be48  cmp     [rax+19h], dil
0x18001be4c  jb      loc_18001C075
0x18001be52  call    cs:__imp_GetLastError
0x18001be59  nop     dword ptr [rax+rax+00h]
0x18001be5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be65  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001be6c  mov     edx, 0A7h
0x18001be71  mov     r9d, eax
0x18001be74  mov     ebx, eax
0x18001be76  mov     rcx, [rcx+10h]
0x18001be7a  call    WPP_SF_d
0x18001be7f  jmp     loc_18001C075
0x18001be84  mov     ebx, 0Dh
0x18001be89  jmp     loc_18001C14E
0x18001be8e  call    cs:__imp_GetLastError
0x18001be95  nop     dword ptr [rax+rax+00h]
0x18001be9a  mov     ebx, eax
0x18001be9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bea3  lea     rdx, WPP_GLOBAL_Control
0x18001beaa  cmp     rcx, rdx
0x18001bead  jz      short loc_18001BED6
0x18001beaf  test    dword ptr [rcx+1Ch], 1000h
0x18001beb6  jz      short loc_18001BED6
0x18001beb8  cmp     [rcx+19h], dil
0x18001bebc  jb      short loc_18001BED6
0x18001bebe  mov     rcx, [rcx+10h]
0x18001bec2  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001bec9  mov     edx, 0A6h
0x18001bece  mov     r9d, eax
0x18001bed1  call    WPP_SF_d
0x18001bed6  mov     rcx, rbp; hObject
0x18001bed9  call    cs:__imp_CloseHandle
0x18001bee0  nop     dword ptr [rax+rax+00h]
0x18001bee5  jmp     loc_18001C14E
0x18001beea  call    cs:__imp_GetLastError
0x18001bef1  nop     dword ptr [rax+rax+00h]
0x18001bef6  mov     ebx, eax
0x18001bef8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001beff  lea     rdx, WPP_GLOBAL_Control
0x18001bf06  cmp     rcx, rdx
0x18001bf09  jz      loc_18001C14E
0x18001bf0f  test    dword ptr [rcx+1Ch], 1000h
0x18001bf16  jz      loc_18001C14E
0x18001bf1c  cmp     [rcx+19h], dil
0x18001bf20  jb      loc_18001C14E
0x18001bf26  mov     rcx, [rcx+10h]
0x18001bf2a  lea     r9, [rsp+2B8h+Buffer]
0x18001bf2f  mov     edx, 0A5h
0x18001bf34  mov     [rsp+2B8h+var_298], eax
0x18001bf38  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001bf3f  call    WPP_SF_Sd
0x18001bf44  jmp     loc_18001C14E
0x18001bf49  mov     rax, cs:WPP_GLOBAL_Control
0x18001bf50  lea     rdx, WPP_GLOBAL_Control
0x18001bf57  cmp     rax, rdx
0x18001bf5a  jz      loc_18001BBFA
0x18001bf60  test    dword ptr [rax+1Ch], 1000h
0x18001bf67  jz      loc_18001BBFA
  ... truncated ...
```
