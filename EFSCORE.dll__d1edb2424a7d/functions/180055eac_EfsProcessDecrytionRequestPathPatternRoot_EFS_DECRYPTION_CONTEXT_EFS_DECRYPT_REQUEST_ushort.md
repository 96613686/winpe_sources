# EfsProcessDecrytionRequestPathPatternRoot(_EFS_DECRYPTION_CONTEXT *,_EFS_DECRYPT_REQUEST *,ushort *)

- ea: `0x180055eac`
- end: `0x180056779`
- name: `?EfsProcessDecrytionRequestPathPatternRoot@@YAXPEAU_EFS_DECRYPTION_CONTEXT@@PEAU_EFS_DECRYPT_REQUEST@@PEAG@Z`
- size: `2253`
- prototype: `void __fastcall(struct _EFS_DECRYPTION_CONTEXT *, struct _EFS_DECRYPT_REQUEST *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180054310`

## callees

- `0x180005045`
- `0x1800124d8`
- `0x1800226ec`
- `0x180022760`
- `0x1800554cc`
- `0x180055eac`
- `0x180056780`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800dddf0`

## import_xrefs

- `msvcrt!iswspace` at `0x180055f7a`
- `msvcrt!iswspace` at `0x180055fbc`
- `msvcrt!iswspace` at `0x180055f7a`
- `msvcrt!iswspace` at `0x180055fbc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800561d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800564f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800561d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800564f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056042`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005613d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800561c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800564e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800566ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056706`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056042`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005613d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800561c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800564e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800566ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056706`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056050`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005614b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800566fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056714`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056050`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005614b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800566fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005600e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005600e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056210`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x18005660e`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x18005660e`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180055fff`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180055fff`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x1800566e2`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x1800566e2`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180056291`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180056291`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180056075`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180056206`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180056075`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180056206`

## pseudocode

```c
void __fastcall EfsProcessDecrytionRequestPathPatternRoot(
        struct _EFS_DECRYPTION_CONTEXT *a1,
        struct _EFS_DECRYPT_REQUEST *a2,
        unsigned __int16 *a3)
{
  struct _EFS_DECRYPTION_CONTEXT *v5; // r12
  int v6; // ecx
  unsigned int v7; // ebx
  wint_t v8; // ax
  unsigned __int16 *v9; // rdi
  _WORD *v10; // rdi
  void *v11; // r15
  DWORD v12; // r14d
  int v13; // ecx
  char *FirstVolumeW; // r13
  bool i; // zf
  signed int LastError; // eax
  int ShouldProcessDecryptionRequests; // eax
  HANDLE ProcessHeap; // rax
  int v19; // ecx
  int v20; // ecx
  signed int v21; // ebx
  int v22; // eax
  HANDLE v23; // rax
  HANDLE v24; // rax
  signed int v25; // eax
  int v26; // ecx
  unsigned int v27; // ebx
  int v28; // eax
  int v29; // ecx
  unsigned __int64 v30; // rcx
  int v31; // ecx
  unsigned __int64 v32; // rcx
  int v33; // ecx
  unsigned int v34; // r14d
  int v35; // ecx
  unsigned int v36; // r12d
  int v37; // ecx
  HANDLE v38; // rax
  unsigned int v39; // r14d
  int v40; // ecx
  int v41; // ecx
  HANDLE v42; // rax
  HANDLE v43; // rax
  char v44; // [rsp+20h] [rbp-E0h]
  DWORD cchReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v46; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR v47; // [rsp+48h] [rbp-B8h] BYREF
  SIZE_T dwBytes; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD v49; // [rsp+54h] [rbp-ACh]
  struct _EFS_DECRYPT_REQUEST *v50; // [rsp+58h] [rbp-A8h]
  struct _EFS_DECRYPTION_CONTEXT *v51; // [rsp+60h] [rbp-A0h]
  WCHAR szVolumeName[264]; // [rsp+70h] [rbp-90h] BYREF

  v50 = a2;
  v51 = a1;
  v5 = a1;
  memset_0(szVolumeName, 0, 0x208u);
  v47 = 0;
  cchReturnLength = 0;
  dwBytes = 0;
  fnEfsLogTrace1Strings(v6, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 45, 249);
  if ( a3 )
  {
    v8 = *a3;
    v7 = 0;
    v9 = a3;
    while ( v8 && iswspace(v8) )
      v8 = *++v9;
    if ( *v9 )
    {
      if ( *v9 == 92 || *v9 == 42 )
      {
        while ( *a3 )
        {
          if ( !iswspace(*a3) && *a3 != 92 )
          {
            if ( *a3 )
            {
              v49 = 0;
              v10 = 0;
              v11 = 0;
              v12 = 0;
              FirstVolumeW = (char *)FindFirstVolumeW(szVolumeName, 0x104u);
              for ( i = FirstVolumeW + 1 == 0; ; i = !FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) )
              {
                if ( i )
                {
                  LastError = GetLastError();
                  v7 = LastError;
                  if ( LastError > 0 )
                    v7 = (unsigned __int16)LastError | 0x80070000;
                }
                if ( v7 )
                  break;
                ShouldProcessDecryptionRequests = EfsShouldProcessDecryptionRequests(v5);
                v13 = 0;
                if ( !ShouldProcessDecryptionRequests )
                  goto LABEL_66;
                if ( v11 )
                {
                  ProcessHeap = GetProcessHeap();
                  HeapFree(ProcessHeap, 0, v11);
                  v11 = 0;
                }
                v46 = 0;
                cchReturnLength = 0;
                v7 = 0;
                if ( GetVolumePathNamesForVolumeNameW(szVolumeName, &v47, 0, &cchReturnLength) )
                  goto LABEL_31;
                v21 = GetLastError();
                if ( v21 > 0 )
                  v21 = (unsigned __int16)v21 | 0x80070000;
                if ( v21 == -2147024662 )
                {
                  v21 = 0;
                  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 45, 56);
                }
                fnEfsLogTrace1Strings(v20, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 59);
                v22 = fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&sourceString,
                        v21,
                        45,
                        59);
                v7 = 0;
                if ( v22 >= 0 )
                {
LABEL_31:
                  if ( cchReturnLength > v12 )
                  {
                    if ( v10 )
                    {
                      v23 = GetProcessHeap();
                      HeapFree(v23, 0, v10);
                      v10 = 0;
                    }
                    fnEfsLogTrace1Strings(v19, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 68);
                    v7 = ULongLongToULong(2LL * cchReturnLength, (unsigned int *)&dwBytes);
                    if ( (int)fnEfsLogTrace1String1Dword(
                                g_hPublisher,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                (unsigned int)&sourceString,
                                v7,
                                45,
                                68) < 0 )
                      goto LABEL_67;
                    v24 = GetProcessHeap();
                    v10 = HeapAlloc(v24, 8u, (unsigned int)dwBytes);
                    if ( !v10 )
                    {
                      v44 = 71;
LABEL_62:
                      v7 = -2147024882;
                      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024882, 45, v44);
                      goto LABEL_67;
                    }
                    v12 = cchReturnLength;
                    v7 = 0;
                    v49 = cchReturnLength;
                  }
                  if ( GetVolumePathNamesForVolumeNameW(szVolumeName, v10, v12, &cchReturnLength) )
                    goto LABEL_42;
                  v25 = GetLastError();
                  v27 = v25;
                  if ( v25 > 0 )
                    v27 = (unsigned __int16)v25 | 0x80070000;
                  fnEfsLogTrace1Strings(v26, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 83);
                  v28 = fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&sourceString,
                          v27,
                          45,
                          83);
                  v7 = 0;
                  if ( v28 >= 0 )
                  {
LABEL_42:
                    if ( *v10 && GetDriveTypeW(v10) == 3 )
                    {
                      fnEfsLogTrace1Strings(
                        v29,
                        (unsigned int)EFS_TRACE_START_EVENT,
                        (unsigned int)&sourceString,
                        45,
                        101);
                      v30 = -1;
                      do
                        ++v30;
                      while ( v10[v30] );
                      v7 = ULongLongToULong(v30, &v46);
                      if ( (int)fnEfsLogTrace1String1Dword(
                                  g_hPublisher,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                  (unsigned int)&sourceString,
                                  v7,
                                  45,
                                  101) < 0 )
                        goto LABEL_67;
                      fnEfsLogTrace1Strings(
                        v31,
                        (unsigned int)EFS_TRACE_START_EVENT,
                        (unsigned int)&sourceString,
                        45,
                        102);
                      v32 = -1;
                      do
                        ++v32;
                      while ( a3[v32] );
                      v7 = ULongLongToULong(v32, (unsigned int *)&dwBytes + 1);
                      if ( (int)fnEfsLogTrace1String1Dword(
                                  g_hPublisher,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                  (unsigned int)&sourceString,
                                  v7,
                                  45,
                                  102) < 0 )
                        goto LABEL_67;
                      fnEfsLogTrace1Strings(
                        v33,
                        (unsigned int)EFS_TRACE_START_EVENT,
                        (unsigned int)&sourceString,
                        45,
                        103);
                      v34 = -1;
                      if ( v46 + HIDWORD(dwBytes) >= v46 )
                        v34 = v46 + HIDWORD(dwBytes);
                      v7 = v46 + HIDWORD(dwBytes) < v46 ? 0x80070216 : 0;
                      if ( (int)fnEfsLogTrace1String1Dword(
                                  g_hPublisher,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                  (unsigned int)&sourceString,
                                  v7,
                                  45,
                                  103) < 0 )
                        goto LABEL_67;
                      fnEfsLogTrace1Strings(
                        v35,
                        (unsigned int)EFS_TRACE_START_EVENT,
                        (unsigned int)&sourceString,
                        45,
                        104);
                      v36 = -1;
                      if ( v34 + 1 >= v34 )
                        v36 = v34 + 1;
                      v46 = v36;
                      v7 = v34 + 1 < v34 ? 0x80070216 : 0;
                      if ( (int)fnEfsLogTrace1String1Dword(
                                  g_hPublisher,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                  (unsigned int)&sourceString,
                                  v7,
                                  45,
                                  104) < 0 )
                        goto LABEL_67;
                      fnEfsLogTrace1Strings(
                        v37,
                        (unsigned int)EFS_TRACE_START_EVENT,
                        (unsigned int)&sourceString,
                        45,
                        105);
                      v7 = ULongLongToULong(2LL * v36, &v46);
                      if ( (int)fnEfsLogTrace1String1Dword(
                                  g_hPublisher,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                  (unsigned int)&sourceString,
                                  v7,
                                  45,
                                  105) < 0 )
                        goto LABEL_67;
                      v38 = GetProcessHeap();
                      v39 = v46;
                      v11 = HeapAlloc(v38, 8u, v46);
                      if ( !v11 )
                      {
                        v44 = 108;
                        goto LABEL_62;
                      }
                      fnEfsLogTrace1Strings(
                        v40,
                        (unsigned int)EFS_TRACE_START_EVENT,
                        (unsigned int)&sourceString,
                        45,
                        114);
                      v7 = StringCbCopyW((unsigned __int16 *)v11, v39, v10);
                      if ( (int)fnEfsLogTrace1String1Dword(
                                  g_hPublisher,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                  (unsigned int)&sourceString,
                                  v7,
                                  45,
                                  114) < 0 )
                        goto LABEL_67;
                      fnEfsLogTrace1Strings(
                        v41,
                        (unsigned int)EFS_TRACE_START_EVENT,
                        (unsigned int)&sourceString,
                        45,
                        115);
                      v7 = StringCbCatW((unsigned __int16 *)v11, v39, a3);
                      if ( (int)fnEfsLogTrace1String1Dword(
                                  g_hPublisher,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                  (unsigned int)&sourceString,
                                  v7,
                                  45,
                                  115) < 0 )
                        goto LABEL_67;
                      v5 = v51;
                      EfsProcessDecrytionRequestPathPattern(v51, v50, (unsigned __int16 *)v11);
                      v12 = v49;
                      v7 = 0;
                    }
                  }
                }
              }
              if ( v7 == -2147024878 )
              {
                v7 = 0;
                fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 45, 133);
              }
LABEL_66:
              fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 136);
              fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v7,
                45,
                136);
LABEL_67:
              if ( FirstVolumeW != (char *)-1LL )
                FindVolumeClose(FirstVolumeW);
              if ( v10 )
              {
                v42 = GetProcessHeap();
                HeapFree(v42, 0, v10);
              }
              if ( v11 )
              {
                v43 = GetProcessHeap();
                HeapFree(v43, 0, v11);
              }
            }
            break;
          }
          ++a3;
        }
      }
      else
      {
        EfsProcessDecrytionRequestPathPattern(v5, a2, v9);
      }
    }
  }
  else
  {
    v7 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 45, 251);
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v7,
    45,
    148);
}

```

## disassembly

```asm
0x180055eac  mov     [rsp-8+arg_18], rbx
0x180055eb1  push    rbp
0x180055eb2  push    rsi
0x180055eb3  push    rdi
0x180055eb4  push    r12
0x180055eb6  push    r13
0x180055eb8  push    r14
0x180055eba  push    r15
0x180055ebc  lea     rbp, [rsp-190h]
0x180055ec4  sub     rsp, 290h
0x180055ecb  mov     rax, cs:__security_cookie
0x180055ed2  xor     rax, rsp
0x180055ed5  mov     [rbp+1C0h+var_40], rax
0x180055edc  mov     rsi, r8
0x180055edf  mov     [rsp+2C0h+var_268], rdx
0x180055ee4  mov     r14, rdx
0x180055ee7  mov     [rsp+2C0h+var_260], rcx
0x180055eec  mov     r12, rcx
0x180055eef  xor     edx, edx; Val
0x180055ef1  mov     r8d, 208h; Size
0x180055ef7  lea     rcx, [rsp+2C0h+szVolumeName]; void *
0x180055efc  call    memset_0
0x180055f01  xor     r13d, r13d
0x180055f04  mov     dword ptr [rsp+2C0h+var_2A0], 8F9h
0x180055f0c  lea     r8, sourceString
0x180055f13  mov     word ptr [rsp+2C0h+var_27C+4], r13w
0x180055f19  lea     rdx, EFS_TRACE_ENTER_EVENT
0x180055f20  mov     dword ptr [rsp+2C0h+dwBytes+4], r13d
0x180055f25  mov     [rsp+2C0h+cchReturnLength], r13d
0x180055f2a  lea     r9d, [r13+2Dh]
0x180055f2e  mov     dword ptr [rsp+2C0h+dwBytes], r13d
0x180055f33  call    fnEfsLogTrace1Strings
0x180055f38  test    rsi, rsi
0x180055f3b  jnz     short loc_180055F6C
0x180055f3d  mov     rcx, cs:g_hPublisher
0x180055f44  lea     r9d, [r13+2Dh]
0x180055f48  mov     r8d, 80070057h
0x180055f4e  mov     dword ptr [rsp+2C0h+var_2A0], 8FBh
0x180055f56  lea     rdx, EFS_TRACE_ERROR
0x180055f5d  mov     ebx, 80070057h
0x180055f62  call    fnEfsLogTrace1
0x180055f67  jmp     loc_18005671A
0x180055f6c  movzx   eax, word ptr [rsi]
0x180055f6f  mov     ebx, r13d
0x180055f72  mov     rdi, rsi
0x180055f75  jmp     short loc_180055F8B
0x180055f77  movzx   ecx, ax; C
0x180055f7a  call    cs:__imp_iswspace
0x180055f80  test    eax, eax
0x180055f82  jz      short loc_180055F90
0x180055f84  add     rdi, 2
0x180055f88  movzx   eax, word ptr [rdi]
0x180055f8b  test    ax, ax
0x180055f8e  jnz     short loc_180055F77
0x180055f90  cmp     [rdi], r13w
0x180055f94  jz      loc_18005671A
0x180055f9a  cmp     word ptr [rdi], 5Ch ; '\'
0x180055f9e  jz      short loc_180055FD0
0x180055fa0  cmp     word ptr [rdi], 2Ah ; '*'
0x180055fa4  jz      short loc_180055FD0
0x180055fa6  mov     r8, rdi; unsigned __int16 *
0x180055fa9  mov     rdx, r14; struct _EFS_DECRYPT_REQUEST *
0x180055fac  mov     rcx, r12; struct _EFS_DECRYPTION_CONTEXT *
0x180055faf  call    ?EfsProcessDecrytionRequestPathPattern@@YAXPEAU_EFS_DECRYPTION_CONTEXT@@PEAU_EFS_DECRYPT_REQUEST@@PEAG@Z; EfsProcessDecrytionRequestPathPattern(_EFS_DECRYPTION_CONTEXT *,_EFS_DECRYPT_REQUEST *,ushort *)
0x180055fb4  jmp     loc_18005671A
0x180055fb9  movzx   ecx, ax; C
0x180055fbc  call    cs:__imp_iswspace
0x180055fc2  test    eax, eax
0x180055fc4  jnz     short loc_180055FCC
0x180055fc6  cmp     word ptr [rsi], 5Ch ; '\'
0x180055fca  jnz     short loc_180055FDD
0x180055fcc  add     rsi, 2
0x180055fd0  movzx   eax, word ptr [rsi]
0x180055fd3  test    ax, ax
0x180055fd6  jnz     short loc_180055FB9
0x180055fd8  jmp     loc_18005671A
0x180055fdd  cmp     [rsi], r13w
0x180055fe1  jz      loc_18005671A
0x180055fe7  mov     edx, 104h; cchBufferLength
0x180055fec  mov     [rsp+2C0h+var_26C], r13d
0x180055ff1  lea     rcx, [rsp+2C0h+szVolumeName]; lpszVolumeName
0x180055ff6  mov     rdi, r13
0x180055ff9  mov     r15, r13
0x180055ffc  mov     r14d, r13d
0x180055fff  call    cs:__imp_FindFirstVolumeW
0x180056005  mov     r13, rax
0x180056008  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005600c  jnz     short loc_180056023
0x18005600e  call    cs:__imp_GetLastError
0x180056014  mov     ebx, eax
0x180056016  test    eax, eax
0x180056018  jle     short loc_180056023
0x18005601a  movzx   ebx, ax
0x18005601d  or      ebx, 80070000h
0x180056023  test    ebx, ebx
0x180056025  jnz     loc_180056656
0x18005602b  mov     rcx, r12; struct _EFS_DECRYPTION_CONTEXT *
0x18005602e  call    ?EfsShouldProcessDecryptionRequests@@YAHPEAU_EFS_DECRYPTION_CONTEXT@@@Z; EfsShouldProcessDecryptionRequests(_EFS_DECRYPTION_CONTEXT *)
0x180056033  xor     ecx, ecx
0x180056035  test    eax, eax
0x180056037  jz      loc_180056686
0x18005603d  test    r15, r15
0x180056040  jz      short loc_18005605B
0x180056042  call    cs:__imp_GetProcessHeap
0x180056048  mov     r8, r15; lpMem
0x18005604b  xor     edx, edx; dwFlags
0x18005604d  mov     rcx, rax; hHeap
0x180056050  call    cs:__imp_HeapFree
0x180056056  xor     ecx, ecx
0x180056058  mov     r15d, ecx
0x18005605b  mov     dword ptr [rsp+2C0h+var_27C], ecx
0x18005605f  lea     r9, [rsp+2C0h+cchReturnLength]; lpcchReturnLength
0x180056064  mov     [rsp+2C0h+cchReturnLength], ecx
0x180056068  lea     rdx, [rsp+2C0h+var_27C+4]; lpszVolumePathNames
0x18005606d  lea     rcx, [rsp+2C0h+szVolumeName]; lpszVolumeName
0x180056072  xor     r8d, r8d; cchBufferLength
0x180056075  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18005607b  xor     ebx, ebx
0x18005607d  test    eax, eax
0x18005607f  jnz     loc_18005612A
0x180056085  call    cs:__imp_GetLastError
0x18005608b  mov     ebx, eax
0x18005608d  xor     eax, eax
0x18005608f  test    ebx, ebx
0x180056091  jle     short loc_18005609C
0x180056093  movzx   ebx, bx
0x180056096  or      ebx, 80070000h
0x18005609c  cmp     ebx, 800700EAh
0x1800560a2  jnz     short loc_1800560CA
0x1800560a4  mov     rcx, cs:g_hPublisher
0x1800560ab  lea     rdx, EFS_TRACE_STATUS
0x1800560b2  mov     r9d, 2Dh ; '-'
0x1800560b8  mov     dword ptr [rsp+2C0h+var_2A0], 938h
0x1800560c0  xor     r8d, r8d
0x1800560c3  mov     ebx, eax
0x1800560c5  call    fnEfsLogTrace1
0x1800560ca  mov     r9d, 2Dh ; '-'
0x1800560d0  mov     dword ptr [rsp+2C0h+var_2A0], 93Bh
0x1800560d8  lea     r8, sourceString
0x1800560df  lea     rdx, EFS_TRACE_START_EVENT
0x1800560e6  call    fnEfsLogTrace1Strings
0x1800560eb  mov     rcx, cs:g_hPublisher
0x1800560f2  lea     r9, sourceString
0x1800560f9  mov     [rsp+2C0h+var_290], 93Bh
0x180056101  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180056108  mov     [rsp+2C0h+var_298], 2Dh ; '-'
0x180056110  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180056117  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x18005611b  call    fnEfsLogTrace1String1Dword
0x180056120  xor     ebx, ebx
0x180056122  test    eax, eax
0x180056124  js      loc_180056600
0x18005612a  cmp     [rsp+2C0h+cchReturnLength], r14d
0x18005612f  jbe     loc_1800561F6
0x180056135  xor     r14d, r14d
0x180056138  test    rdi, rdi
0x18005613b  jz      short loc_180056154
0x18005613d  call    cs:__imp_GetProcessHeap
0x180056143  mov     r8, rdi; lpMem
0x180056146  xor     edx, edx; dwFlags
0x180056148  mov     rcx, rax; hHeap
0x18005614b  call    cs:__imp_HeapFree
0x180056151  mov     edi, r14d
0x180056154  mov     r9d, 2Dh ; '-'
0x18005615a  mov     dword ptr [rsp+2C0h+var_2A0], 944h
0x180056162  lea     r8, sourceString
0x180056169  lea     rdx, EFS_TRACE_START_EVENT
0x180056170  call    fnEfsLogTrace1Strings
0x180056175  mov     ecx, [rsp+2C0h+cchReturnLength]
0x180056179  lea     rdx, [rsp+2C0h+dwBytes]; unsigned int *
0x18005617e  add     rcx, rcx; unsigned __int64
0x180056181  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180056186  mov     rcx, cs:g_hPublisher
0x18005618d  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180056194  mov     [rsp+2C0h+var_290], 944h
0x18005619c  lea     r9, sourceString
0x1800561a3  mov     [rsp+2C0h+var_298], 2Dh ; '-'
0x1800561ab  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800561b2  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x1800561b6  mov     ebx, eax
0x1800561b8  call    fnEfsLogTrace1String1Dword
0x1800561bd  test    eax, eax
0x1800561bf  js      loc_1800566D9
0x1800561c5  call    cs:__imp_GetProcessHeap
0x1800561cb  mov     r8d, dword ptr [rsp+2C0h+dwBytes]; dwBytes
0x1800561d0  mov     edx, 8; dwFlags
0x1800561d5  mov     rcx, rax; hHeap
0x1800561d8  call    cs:__imp_HeapAlloc
0x1800561de  mov     rdi, rax
0x1800561e1  test    rax, rax
0x1800561e4  jz      loc_18005661B
0x1800561ea  mov     r14d, [rsp+2C0h+cchReturnLength]
0x1800561ef  xor     ebx, ebx
0x1800561f1  mov     [rsp+2C0h+var_26C], r14d
0x1800561f6  lea     r9, [rsp+2C0h+cchReturnLength]; lpcchReturnLength
0x1800561fb  mov     r8d, r14d; cchBufferLength
0x1800561fe  mov     rdx, rdi; lpszVolumePathNames
0x180056201  lea     rcx, [rsp+2C0h+szVolumeName]; lpszVolumeName
0x180056206  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18005620c  test    eax, eax
0x18005620e  jnz     short loc_180056285
0x180056210  call    cs:__imp_GetLastError
0x180056216  mov     ebx, eax
0x180056218  test    eax, eax
0x18005621a  jle     short loc_180056225
0x18005621c  movzx   ebx, ax
0x18005621f  or      ebx, 80070000h
0x180056225  mov     r9d, 2Dh ; '-'
0x18005622b  mov     dword ptr [rsp+2C0h+var_2A0], 953h
0x180056233  lea     r8, sourceString
0x18005623a  lea     rdx, EFS_TRACE_START_EVENT
0x180056241  call    fnEfsLogTrace1Strings
0x180056246  mov     rcx, cs:g_hPublisher
0x18005624d  lea     r9, sourceString
0x180056254  mov     [rsp+2C0h+var_290], 953h
0x18005625c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180056263  mov     [rsp+2C0h+var_298], 2Dh ; '-'
0x18005626b  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180056272  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x180056276  call    fnEfsLogTrace1String1Dword
0x18005627b  xor     ebx, ebx
0x18005627d  test    eax, eax
0x18005627f  js      loc_180056600
0x180056285  cmp     [rdi], bx
0x180056288  jz      loc_180056600
0x18005628e  mov     rcx, rdi; lpRootPathName
0x180056291  call    cs:__imp_GetDriveTypeW
0x180056297  cmp     eax, 3
0x18005629a  jnz     loc_180056600
0x1800562a0  lea     r12, sourceString
0x1800562a7  mov     dword ptr [rsp+2C0h+var_2A0], 965h
0x1800562af  mov     r8, r12
0x1800562b2  lea     r9d, [rax+2Ah]
0x1800562b6  lea     rdx, EFS_TRACE_START_EVENT
0x1800562bd  call    fnEfsLogTrace1Strings
0x1800562c2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800562c6  xor     r14d, r14d
0x1800562c9  inc     rcx; unsigned __int64
0x1800562cc  cmp     [rdi+rcx*2], r14w
0x1800562d1  jnz     short loc_1800562C9
0x1800562d3  lea     rdx, [rsp+2C0h+var_27C]; unsigned int *
0x1800562d8  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800562dd  mov     rcx, cs:g_hPublisher
0x1800562e4  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800562eb  mov     [rsp+2C0h+var_290], 965h
0x1800562f3  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800562fa  mov     [rsp+2C0h+var_298], 2Dh ; '-'
0x180056302  mov     r9, r12
0x180056305  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x180056309  mov     ebx, eax
0x18005630b  call    fnEfsLogTrace1String1Dword
0x180056310  test    eax, eax
0x180056312  js      loc_1800566D9
0x180056318  mov     r9d, 2Dh ; '-'
0x18005631e  mov     dword ptr [rsp+2C0h+var_2A0], 966h
0x180056326  mov     r8, r12
0x180056329  lea     rdx, EFS_TRACE_START_EVENT
0x180056330  call    fnEfsLogTrace1Strings
0x180056335  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180056339  inc     rcx; unsigned __int64
0x18005633c  cmp     [rsi+rcx*2], r14w
0x180056341  jnz     short loc_180056339
0x180056343  lea     rdx, [rsp+2C0h+dwBytes+4]; unsigned int *
0x180056348  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18005634d  mov     rcx, cs:g_hPublisher
0x180056354  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18005635b  mov     [rsp+2C0h+var_290], 966h
0x180056363  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18005636a  mov     [rsp+2C0h+var_298], 2Dh ; '-'
0x180056372  mov     r9, r12
0x180056375  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x180056379  mov     ebx, eax
0x18005637b  call    fnEfsLogTrace1String1Dword
0x180056380  test    eax, eax
0x180056382  js      loc_1800566D9
0x180056388  mov     r9d, 2Dh ; '-'
0x18005638e  mov     dword ptr [rsp+2C0h+var_2A0], 967h
0x180056396  mov     r8, r12
0x180056399  lea     rdx, EFS_TRACE_START_EVENT
0x1800563a0  call    fnEfsLogTrace1Strings
0x1800563a5  mov     ecx, dword ptr [rsp+2C0h+dwBytes+4]
0x1800563a9  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800563b0  add     ecx, dword ptr [rsp+2C0h+var_27C]
0x1800563b4  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800563bb  or      r14d, 0FFFFFFFFh
0x1800563bf  mov     [rsp+2C0h+var_290], 967h
0x1800563c7  cmp     ecx, dword ptr [rsp+2C0h+var_27C]
0x1800563cb  mov     r9, r12
0x1800563ce  mov     [rsp+2C0h+var_298], 2Dh ; '-'
0x1800563d6  cmovnb  r14d, ecx
0x1800563da  mov     rcx, cs:g_hPublisher
0x1800563e1  sbb     ebx, ebx
0x1800563e3  and     ebx, 80070216h
0x1800563e9  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x1800563ed  call    fnEfsLogTrace1String1Dword
0x1800563f2  test    eax, eax
0x1800563f4  js      loc_1800566D9
0x1800563fa  mov     r9d, 2Dh ; '-'
0x180056400  mov     dword ptr [rsp+2C0h+var_2A0], 968h
0x180056408  mov     r8, r12
  ... truncated ...
```
