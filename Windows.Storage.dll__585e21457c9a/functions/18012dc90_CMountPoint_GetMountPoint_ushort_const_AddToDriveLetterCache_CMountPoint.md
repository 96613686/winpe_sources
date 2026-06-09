# CMountPoint::GetMountPoint(ushort const *,AddToDriveLetterCache,CMountPoint * *)

- ea: `0x18012dc90`
- end: `0x18012e3b8`
- name: `?GetMountPoint@CMountPoint@@SAJPEBGW4AddToDriveLetterCache@@PEAPEAV1@@Z`
- size: `1832`
- prototype: ``
- caller_count: `16`
- callee_count: `12`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180090dc0`
- `0x1800b69d0`
- `0x180146a60`
- `0x18014c6c0`
- `0x1802389e0`
- `0x18027c750`
- `0x1802adfcc`
- `0x1802e91a8`
- `0x1802f07b8`
- `0x18031a800`
- `0x18032af54`
- `0x180357f40`
- `0x180360698`
- `0x1805bcde0`
- `0x1805cea8c`
- `0x180601130`

## callees

- `0x1800451f0`
- `0x18009d164`
- `0x1800a743c`
- `0x18012c990`
- `0x18012d080`
- `0x18012dbb0`
- `0x18012dc90`
- `0x18012e3c0`
- `0x1802ac0a0`
- `0x1803460c8`
- `0x1803a4cb0`
- `0x1803a57e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012dd33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012dd33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012dedb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012dedb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012e071`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012e1fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012e071`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012e1fe`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18012e110`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18012e110`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18012e328`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18012e328`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18012dd26`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18012dd26`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18012df47`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18012df47`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18012dfc3`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18012e1cd`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18012dfc3`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18012e1cd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18012dcf8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18012dcf8`

## pseudocode

```c
__int64 __fastcall CMountPoint::GetMountPoint(unsigned __int64 a1, int a2, struct CMtPtLocal *a3)
{
  int v3; // ebx
  struct CMtPtLocal *v4; // rsi
  volatile signed __int32 *v6; // rdi
  int v7; // r14d
  WCHAR v8; // ax
  WCHAR *v9; // rcx
  WCHAR v10; // dx
  WCHAR v11; // ax
  int Error; // r15d
  int v13; // r13d
  __int64 v14; // rbx
  WCHAR *v15; // r14
  WCHAR *v16; // r8
  unsigned __int64 v17; // rsi
  unsigned __int64 v18; // rdi
  struct CMtPtLocal *v19; // rdi
  __int64 v20; // r8
  unsigned int v21; // ebx
  int v23; // edx
  _WORD *v24; // rax
  unsigned __int64 i; // rcx
  WCHAR *v26; // r8
  unsigned __int64 v27; // rsi
  unsigned __int64 v28; // rdi
  __int64 v29; // rcx
  _WORD *v30; // rdx
  __int64 v31; // r8
  _WORD *v32; // rcx
  int v33; // edx
  _WORD *v34; // rax
  unsigned __int64 j; // rcx
  __int64 v36; // rcx
  WCHAR *p_pszPath; // rdx
  __int64 v38; // r8
  WCHAR *v39; // rcx
  volatile signed __int32 *v40; // [rsp+38h] [rbp-D0h]
  int DriveNumberW; // [rsp+44h] [rbp-C4h]
  WCHAR sz[4]; // [rsp+48h] [rbp-C0h] BYREF
  struct CMountPoint *v44; // [rsp+50h] [rbp-B8h] BYREF
  struct CMtPtLocal *v45[2]; // [rsp+60h] [rbp-A8h] BYREF
  WCHAR pszPath; // [rsp+78h] [rbp-90h] BYREF
  char v47[526]; // [rsp+7Ah] [rbp-8Eh] BYREF
  WCHAR v48[264]; // [rsp+288h] [rbp+180h] BYREF
  WCHAR v49[264]; // [rsp+498h] [rbp+390h] BYREF

  v3 = a2;
  v4 = a3;
  v45[0] = a3;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Shell32_MountPoint_GetMountPoint_Start,
      a3,
      1,
      &v44);
  v6 = 0;
  *(_QWORD *)v4 = 0;
  v40 = 0;
  v44 = 0;
  DriveNumberW = PathGetDriveNumberW((LPCWSTR)a1);
  v7 = DriveNumberW;
  if ( DriveNumberW != -1 )
  {
    InitOnceExecuteOnce(
      &stru_180803DC0,
      _lambda_c12b5e827bbdb1597ce6a3af58750a50_::_lambda_invoker_cdecl_,
      &Parameter,
      0);
    EnterCriticalSection(&Parameter);
    if ( HIDWORD(qword_1808041C0) )
      goto LABEL_34;
    if ( !a1 )
      goto LABEL_13;
    v8 = *(_WORD *)a1;
    v9 = (WCHAR *)a1;
    if ( *(_WORD *)a1 == 92 )
    {
      if ( *(_WORD *)(a1 + 2) != 92 || *(_WORD *)(a1 + 4) != 63 || *(_WORD *)(a1 + 6) != 92 )
        goto LABEL_8;
      v8 = *(_WORD *)(a1 + 8);
      v9 = (WCHAR *)(a1 + 8);
    }
    if ( v8 >= 0x61u )
    {
      v10 = *v9;
      if ( *v9 <= 0x7Au )
        goto LABEL_9;
    }
LABEL_8:
    v10 = *v9;
    if ( (unsigned __int16)(*v9 - 65) <= 0x19u )
    {
LABEL_9:
      if ( v9[1] == 58 )
      {
        v11 = v9[2];
        if ( !v11 || v11 == 92 && !v9[3] )
        {
          sz[0] = v10;
          CharLowerBuffW(sz, 1u);
          if ( sz[0] )
            goto LABEL_115;
        }
      }
    }
LABEL_13:
    if ( (unsigned int)CMountPoint::_IsNetDriveLazyLoadNetDLLs(DriveNumberW) )
    {
LABEL_115:
      CMountPoint::_GetMountPointForDriveLetter(DriveNumberW, &v44);
      v19 = v44;
      goto LABEL_35;
    }
    memset_0(v47, 0, 0x206u);
    Error = 1;
    pszPath = 0;
    if ( qword_1808041A8 )
    {
      v13 = 0;
      *(_DWORD *)sz = *(_DWORD *)qword_1808041A8;
      if ( *(int *)sz > 0 )
      {
        while ( 1 )
        {
          if ( v6 )
          {
LABEL_32:
            v3 = a2;
            v4 = v45[0];
            v7 = DriveNumberW;
            if ( pszPath )
              goto LABEL_33;
            break;
          }
          if ( qword_1808041A8 && v13 >= 0 && v13 < *(_DWORD *)qword_1808041A8 )
            v14 = *(_QWORD *)(*(_QWORD *)(qword_1808041A8 + 8) + 8LL * v13);
          else
            v14 = 0;
          v15 = (WCHAR *)(v14 + 520);
          if ( (unsigned __int64)(v14 + 520) < 0x10000 )
          {
            if ( SHGetFolderPathW(0, (unsigned int)v15 | 0x4000, 0, 0, v48) < 0 )
              goto LABEL_31;
            v16 = v48;
          }
          else
          {
            v16 = (WCHAR *)(v14 + 520);
          }
          v17 = -1;
          do
            ++v17;
          while ( v16[v17] );
          if ( v17 && v16[v17 - 1] == 92 )
            --v17;
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)(a1 + 2 * v18) );
          if ( v18 && *(_WORD *)(a1 + 2 * v18 - 2) == 92 )
            --v18;
          if ( v17 <= v18 )
          {
            if ( *(_WORD *)(a1 + 2 * v17) == 92 )
            {
              v23 = v17;
            }
            else
            {
              if ( v18 != v17 )
                goto LABEL_30;
              v23 = v18;
            }
            if ( CompareStringOrdinal((LPCWCH)a1, v23, v16, v17, 1) == 2 )
            {
              if ( v17 < v18 )
              {
                v24 = (_WORD *)(a1 + 2 + 2 * v17);
                for ( i = a1 + 2 * v18; (unsigned __int64)v24 < i; ++v24 )
                {
                  if ( *v24 == 92 )
                    break;
                }
              }
              if ( a1 < 0x10000 )
              {
                if ( SHGetFolderPathW(0, a1 | 0x4000, 0, 0, v49) >= 0 )
                {
                  v26 = v49;
                  goto LABEL_65;
                }
              }
              else
              {
                v26 = (WCHAR *)a1;
LABEL_65:
                v27 = -1;
                do
                  ++v27;
                while ( v26[v27] );
                if ( v27 && v26[v27 - 1] == 92 )
                  --v27;
                v28 = -1;
                do
                  ++v28;
                while ( *(_WORD *)(v14 + 2 * v28) );
                if ( v28 && *(_WORD *)(v14 + 2 * v28 - 2) == 92 )
                  --v28;
                if ( v27 <= v28 )
                {
                  if ( *(_WORD *)(v14 + 2 * v27) == 92 )
                  {
                    v33 = v27;
                  }
                  else
                  {
                    if ( v28 != v27 )
                      goto LABEL_72;
                    v33 = v28;
                  }
                  if ( CompareStringOrdinal((LPCWCH)v14, v33, v26, v27, 1) == 2 )
                  {
                    if ( v27 < v28 )
                    {
                      v34 = (_WORD *)(v14 + 2 * (v27 + 1));
                      for ( j = v14 + 2 * v28; (unsigned __int64)v34 < j; ++v34 )
                      {
                        if ( *v34 == 92 )
                          break;
                      }
                    }
                    v6 = *(volatile signed __int32 **)(v14 + 1040);
                    v40 = v6;
                    v44 = (struct CMountPoint *)v6;
                    _InterlockedIncrement(v6 + 12);
                    v36 = 2147483646;
                    p_pszPath = &pszPath;
                    v38 = 260;
                    do
                    {
                      if ( !v36 )
                        break;
                      if ( !*v15 )
                        break;
                      *p_pszPath++ = *v15++;
                      --v36;
                      --v38;
                    }
                    while ( v38 );
                    v39 = p_pszPath - 1;
                    if ( v38 )
                      v39 = p_pszPath;
                    *v39 = 0;
                    ++*(_DWORD *)(v14 + 1048);
                    Error = 0;
                    goto LABEL_31;
                  }
                }
              }
LABEL_72:
              if ( (pszPath || GetVolumePathNameW((LPCWSTR)a1, &pszPath, 0x104u) || (int)ResultFromKnownLastError() >= 0)
                && !StrCmpIW(&pszPath, (PCWSTR)(v14 + 520)) )
              {
                v6 = *(volatile signed __int32 **)(v14 + 1040);
                v40 = v6;
                v44 = (struct CMountPoint *)v6;
                _InterlockedIncrement(v6 + 12);
                if ( a2 == 1 )
                {
                  v29 = 2147483646;
                  v30 = (_WORD *)a1;
                  v31 = 260;
                  do
                  {
                    if ( !v29 )
                      break;
                    if ( !*v30 )
                      break;
                    *(_WORD *)v14 = *v30++;
                    v14 += 2;
                    --v29;
                    --v31;
                  }
                  while ( v31 );
                  v32 = (_WORD *)(v14 - 2);
                  if ( v31 )
                    v32 = (_WORD *)v14;
                  *v32 = 0;
                }
                Error = 0;
                goto LABEL_31;
              }
            }
          }
LABEL_30:
          v6 = v40;
LABEL_31:
          if ( ++v13 >= *(int *)sz )
            goto LABEL_32;
        }
      }
    }
    if ( !GetVolumePathNameW((LPCWSTR)a1, &pszPath, 0x104u) )
      Error = ResultFromKnownLastError();
LABEL_33:
    if ( Error >= 0 && !v6 )
    {
      PathCchAddBackslash(&pszPath, 0x104u);
      if ( CMountPoint::_ExtractDriveLetter(&pszPath) )
      {
        CMountPoint::_GetMountPointForDriveLetter(v7, &v44);
        v19 = v44;
      }
      else
      {
        v45[0] = 0;
        CMountPoint::_GetMountPointForFolder(&pszPath, v45);
        v19 = v45[0];
      }
      if ( v19 && v3 == 1 )
        CDriveLetterCache::AddPathLookupEntry(
          (CDriveLetterCache *)&qword_180803E68,
          (const unsigned __int16 *)a1,
          &pszPath,
          v19);
      goto LABEL_35;
    }
LABEL_34:
    v19 = (struct CMtPtLocal *)v40;
LABEL_35:
    LeaveCriticalSection(&Parameter);
    goto LABEL_36;
  }
  CMountPoint::GetSimulatedMountPointFromVolumeGuid((STRSAFE_PCNZWCH)a1, &v44);
  v19 = v44;
LABEL_36:
  v21 = -2147467259;
  if ( v19 )
  {
    *(_QWORD *)v4 = v19;
    v21 = 0;
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Shell32_MountPoint_GetMountPoint_Stop,
      v20,
      1,
      v45);
  return v21;
}

```

## disassembly

```asm
0x18012dc90  mov     r11, rsp
0x18012dc93  push    rbp
0x18012dc94  push    rbx
0x18012dc95  lea     rbp, [r11-5E8h]
0x18012dc9c  sub     rsp, 6D8h
0x18012dca3  mov     rax, cs:__security_cookie
0x18012dcaa  xor     rax, rsp
0x18012dcad  mov     [rbp+5E0h+var_40], rax
0x18012dcb4  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18012dcbb  mov     ebx, edx
0x18012dcbd  mov     [r11+10h], rsi
0x18012dcc1  mov     rsi, r8
0x18012dcc4  mov     [r11-18h], rdi
0x18012dcc8  mov     [r11-20h], r12
0x18012dccc  mov     r12, rcx
0x18012dccf  mov     [r11-30h], r14
0x18012dcd3  mov     [rsp+6E0h+var_688], r8
0x18012dcd8  mov     [rsp+6E0h+var_6A8], edx
0x18012dcdc  jnz     loc_18012E038
0x18012dce2  xor     edi, edi
0x18012dce4  mov     qword ptr [rsi], 0
0x18012dceb  mov     rcx, r12; pszPath
0x18012dcee  mov     qword ptr [rsp+6E0h+var_6B0], rdi
0x18012dcf3  mov     [rsp+6E0h+var_698], rdi
0x18012dcf8  call    cs:__imp_PathGetDriveNumberW
0x18012dcfe  mov     [rsp+3Ch], eax
0x18012dd02  mov     r14d, eax
0x18012dd05  cmp     eax, 0FFFFFFFFh
0x18012dd08  jz      loc_18012E2CE
0x18012dd0e  xor     r9d, r9d; Context
0x18012dd11  lea     r8, Parameter; Parameter
0x18012dd18  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c12b5e827bbdb1597ce6a3af58750a50_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18012dd1f  lea     rcx, stru_180803DC0; InitOnce
0x18012dd26  call    cs:__imp_InitOnceExecuteOnce
0x18012dd2c  lea     rcx, Parameter; lpCriticalSection
0x18012dd33  call    cs:__imp_EnterCriticalSection
0x18012dd39  cmp     dword ptr cs:qword_1808041C0+4, edi
0x18012dd3f  jnz     loc_18012DECF
0x18012dd45  test    r12, r12
0x18012dd48  jz      short loc_18012DD96
0x18012dd4a  movzx   eax, word ptr [r12]
0x18012dd4f  mov     rcx, r12
0x18012dd52  cmp     ax, 5Ch ; '\'
0x18012dd56  jz      loc_18012E297
0x18012dd5c  cmp     ax, 61h ; 'a'
0x18012dd60  jnb     loc_18012E307
0x18012dd66  movzx   edx, word ptr [rcx]
0x18012dd69  lea     eax, [rdx-41h]
0x18012dd6c  cmp     ax, 19h
0x18012dd70  ja      short loc_18012DD96
0x18012dd72  cmp     word ptr [rcx+2], 3Ah ; ':'
0x18012dd77  jnz     short loc_18012DD96
0x18012dd79  movzx   eax, word ptr [rcx+4]
0x18012dd7d  test    ax, ax
0x18012dd80  jz      loc_18012E319
0x18012dd86  cmp     ax, 5Ch ; '\'
0x18012dd8a  jnz     short loc_18012DD96
0x18012dd8c  cmp     [rcx+6], di
0x18012dd90  jz      loc_18012E319
0x18012dd96  mov     ecx, r14d; int
0x18012dd99  call    ?_IsNetDriveLazyLoadNetDLLs@CMountPoint@@CAHH@Z; CMountPoint::_IsNetDriveLazyLoadNetDLLs(int)
0x18012dd9e  test    eax, eax
0x18012dda0  jnz     loc_18012E339
0x18012dda6  mov     [rsp+6E0h+var_30], r15
0x18012ddae  lea     rcx, [rsp+6E0h+var_66E]; void *
0x18012ddb3  xor     edx, edx; Val
0x18012ddb5  mov     [rsp+6E0h+var_20], r13
0x18012ddbd  mov     r8d, 206h; Size
0x18012ddc3  call    memset_0
0x18012ddc8  xor     eax, eax
0x18012ddca  mov     r15d, 1
0x18012ddd0  mov     [rsp+6E0h+pszPath], ax
0x18012ddd5  mov     rax, cs:qword_1808041A8
0x18012dddc  test    rax, rax
0x18012dddf  jz      loc_18012DFB5
0x18012dde5  mov     eax, [rax]
0x18012dde7  xor     r13d, r13d
0x18012ddea  mov     dword ptr [rsp+6E0h+sz], eax
0x18012ddee  test    eax, eax
0x18012ddf0  jle     loc_18012DFB5
0x18012ddf6  test    rdi, rdi
0x18012ddf9  jnz     loc_18012DEA0
0x18012ddff  mov     rax, cs:qword_1808041A8
0x18012de06  test    rax, rax
0x18012de09  jz      loc_18012DFF3
0x18012de0f  test    r13d, r13d
0x18012de12  js      loc_18012DFF3
0x18012de18  cmp     r13d, [rax]
0x18012de1b  jge     loc_18012DFF3
0x18012de21  mov     rax, [rax+8]
0x18012de25  movsxd  rcx, r13d
0x18012de28  mov     rbx, [rax+rcx*8]
0x18012de2c  lea     r14, [rbx+208h]
0x18012de33  cmp     r14, 10000h
0x18012de3a  jb      loc_18012E350
0x18012de40  mov     r8, r14; lpString2
0x18012de43  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18012de4a  nop     word ptr [rax+rax+00h]
0x18012de50  inc     rsi
0x18012de53  cmp     word ptr [r8+rsi*2], 0
0x18012de59  jnz     short loc_18012DE50
0x18012de5b  test    rsi, rsi
0x18012de5e  jnz     loc_18012DFDE
0x18012de64  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18012de6b  nop     dword ptr [rax+rax+00h]
0x18012de70  inc     rdi
0x18012de73  cmp     word ptr [r12+rdi*2], 0
0x18012de79  jnz     short loc_18012DE70
0x18012de7b  test    rdi, rdi
0x18012de7e  jnz     loc_18012DFA0
0x18012de84  cmp     rsi, rdi
0x18012de87  jbe     loc_18012DFFA
0x18012de8d  mov     rdi, qword ptr [rsp+6E0h+var_6B0]
0x18012de92  inc     r13d
0x18012de95  cmp     r13d, dword ptr [rsp+6E0h+sz]
0x18012de9a  jl      loc_18012DDF6
0x18012dea0  cmp     [rsp+6E0h+pszPath], 0
0x18012dea6  mov     ebx, [rsp+6E0h+var_6A8]
0x18012deaa  mov     rsi, [rsp+6E0h+var_688]
0x18012deaf  mov     r14d, [rsp+3Ch]
0x18012deb4  jz      loc_18012DFB5
0x18012deba  mov     r13, [rsp+6E0h+var_20]
0x18012dec2  test    r15d, r15d
0x18012dec5  mov     r15, [rsp+6E0h+var_30]
0x18012decd  jns     short loc_18012DF38
0x18012decf  mov     rdi, qword ptr [rsp+6E0h+var_6B0]
0x18012ded4  lea     rcx, Parameter; lpCriticalSection
0x18012dedb  call    cs:__imp_LeaveCriticalSection
0x18012dee1  mov     r14, [rsp+6E0h+var_28]
0x18012dee9  mov     ebx, 80004005h
0x18012deee  mov     r12, [rsp+6E0h+var_18]
0x18012def6  test    rdi, rdi
0x18012def9  jz      short loc_18012DF00
0x18012defb  mov     [rsi], rdi
0x18012defe  xor     ebx, ebx
0x18012df00  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18012df07  mov     rdi, [rsp+6D0h]
0x18012df0f  mov     rsi, [rsp+6E0h+arg_8]
0x18012df17  jnz     loc_18012E010
0x18012df1d  mov     eax, ebx
0x18012df1f  mov     rcx, [rbp+5E0h+var_40]
0x18012df26  xor     rcx, rsp; StackCookie
0x18012df29  call    __security_check_cookie
0x18012df2e  add     rsp, 6D8h
0x18012df35  pop     rbx
0x18012df36  pop     rbp
0x18012df37  retn
0x18012df38  test    rdi, rdi
0x18012df3b  jnz     short loc_18012DECF
0x18012df3d  mov     edx, 104h; cchPath
0x18012df42  lea     rcx, [rsp+6E0h+pszPath]; pszPath
0x18012df47  call    cs:__imp_PathCchAddBackslash
0x18012df4d  lea     rcx, [rsp+6E0h+pszPath]; unsigned __int16 *
0x18012df52  call    ?_ExtractDriveLetter@CMountPoint@@CAGPEBG@Z; CMountPoint::_ExtractDriveLetter(ushort const *)
0x18012df57  test    ax, ax
0x18012df5a  jz      loc_18012E2E5
0x18012df60  lea     rdx, [rsp+6E0h+var_698]; struct CMountPoint **
0x18012df65  mov     ecx, r14d; int
0x18012df68  call    ?_GetMountPointForDriveLetter@CMountPoint@@CAJHPEAPEAV1@@Z; CMountPoint::_GetMountPointForDriveLetter(int,CMountPoint * *)
0x18012df6d  mov     rdi, [rsp+6E0h+var_698]
0x18012df72  test    rdi, rdi
0x18012df75  jz      loc_18012DED4
0x18012df7b  cmp     ebx, 1
0x18012df7e  jnz     loc_18012DED4
0x18012df84  mov     r9, rdi; struct CMountPoint *
0x18012df87  lea     r8, [rsp+6E0h+pszPath]; unsigned __int16 *
0x18012df8c  mov     rdx, r12; unsigned __int16 *
0x18012df8f  lea     rcx, qword_180803E68; this
0x18012df96  call    ?AddPathLookupEntry@CDriveLetterCache@@QEAAJPEBG0PEAVCMountPoint@@@Z; CDriveLetterCache::AddPathLookupEntry(ushort const *,ushort const *,CMountPoint *)
0x18012df9b  jmp     loc_18012DED4
0x18012dfa0  cmp     word ptr [r12+rdi*2-2], 5Ch ; '\'
0x18012dfa7  jnz     loc_18012DE84
0x18012dfad  dec     rdi
0x18012dfb0  jmp     loc_18012DE84
0x18012dfb5  mov     r8d, 104h; cchBufferLength
0x18012dfbb  lea     rdx, [rsp+6E0h+pszPath]; lpszVolumePathName
0x18012dfc0  mov     rcx, r12; lpszFileName
0x18012dfc3  call    cs:__imp_GetVolumePathNameW
0x18012dfc9  test    eax, eax
0x18012dfcb  jnz     loc_18012DEBA
0x18012dfd1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18012dfd6  mov     r15d, eax
0x18012dfd9  jmp     loc_18012DEBA
0x18012dfde  cmp     word ptr [r8+rsi*2-2], 5Ch ; '\'
0x18012dfe5  jnz     loc_18012DE64
0x18012dfeb  dec     rsi
0x18012dfee  jmp     loc_18012DE64
0x18012dff3  xor     ebx, ebx
0x18012dff5  jmp     loc_18012DE2C
0x18012dffa  cmp     word ptr [r12+rsi*2], 5Ch ; '\'
0x18012e000  jz      short loc_18012E060
0x18012e002  cmp     rdi, rsi
0x18012e005  jnz     loc_18012DE8D
0x18012e00b  mov     rdx, rdi
0x18012e00e  jmp     short loc_18012E063
0x18012e010  lea     rax, [rsp+6E0h+var_688]
0x18012e015  mov     r9d, 1
0x18012e01b  lea     rdx, Shell32_MountPoint_GetMountPoint_Stop
0x18012e022  mov     [rsp+20h], rax
0x18012e027  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x18012e02e  call    McGenEventWrite_EventWriteTransfer
0x18012e033  jmp     loc_18012DF1D
0x18012e038  lea     rax, [rsp+6E0h+var_698]
0x18012e03d  mov     r9d, 1
0x18012e043  lea     rdx, Shell32_MountPoint_GetMountPoint_Start
0x18012e04a  mov     [rsp+20h], rax
0x18012e04f  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x18012e056  call    McGenEventWrite_EventWriteTransfer
0x18012e05b  jmp     loc_18012DCE2
0x18012e060  mov     rdx, rsi; cchCount1
0x18012e063  mov     r9d, esi; cchCount2
0x18012e066  mov     dword ptr [rsp+20h], 1; bIgnoreCase
0x18012e06e  mov     rcx, r12; lpString1
0x18012e071  call    cs:__imp_CompareStringOrdinal
0x18012e077  cmp     eax, 2
0x18012e07a  jnz     loc_18012DE8D
0x18012e080  cmp     rsi, rdi
0x18012e083  jnb     short loc_18012E0A6
0x18012e085  lea     rax, [r12+2]
0x18012e08a  lea     rax, [rax+rsi*2]
0x18012e08e  lea     rcx, [r12+rdi*2]
0x18012e092  cmp     rax, rcx
0x18012e095  jnb     short loc_18012E0A6
0x18012e097  cmp     word ptr [rax], 5Ch ; '\'
0x18012e09b  jz      short loc_18012E0A6
0x18012e09d  add     rax, 2
0x18012e0a1  cmp     rax, rcx
0x18012e0a4  jb      short loc_18012E097
0x18012e0a6  cmp     r12, 10000h
0x18012e0ad  jb      loc_18012E384
0x18012e0b3  mov     r8, r12; lpString2
0x18012e0b6  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18012e0bd  nop     dword ptr [rax]
0x18012e0c0  inc     rsi
0x18012e0c3  cmp     word ptr [r8+rsi*2], 0
0x18012e0c9  jnz     short loc_18012E0C0
0x18012e0cb  test    rsi, rsi
0x18012e0ce  jnz     loc_18012E195
0x18012e0d4  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18012e0db  nop     dword ptr [rax+rax+00h]
0x18012e0e0  inc     rdi
0x18012e0e3  cmp     word ptr [rbx+rdi*2], 0
0x18012e0e8  jnz     short loc_18012E0E0
0x18012e0ea  test    rdi, rdi
0x18012e0ed  jnz     loc_18012E181
0x18012e0f3  cmp     rsi, rdi
0x18012e0f6  jbe     loc_18012E1AA
0x18012e0fc  cmp     [rsp+6E0h+pszPath], 0
0x18012e102  jz      loc_18012E1BF
0x18012e108  mov     rdx, r14; psz2
0x18012e10b  lea     rcx, [rsp+6E0h+pszPath]; psz1
0x18012e110  call    cs:__imp_StrCmpIW
0x18012e116  test    eax, eax
0x18012e118  jnz     loc_18012DE8D
0x18012e11e  mov     rdi, [rbx+410h]
0x18012e125  mov     qword ptr [rsp+6E0h+var_6B0], rdi
0x18012e12a  mov     [rsp+6E0h+var_698], rdi
0x18012e12f  lock inc dword ptr [rdi+30h]
0x18012e133  cmp     [rsp+6E0h+var_6A8], 1
0x18012e138  jnz     short loc_18012E179
0x18012e13a  mov     ecx, 7FFFFFFEh
0x18012e13f  mov     rdx, r12
0x18012e142  mov     r8d, 104h
0x18012e148  test    rcx, rcx
0x18012e14b  jz      short loc_18012E169
0x18012e14d  movzx   eax, word ptr [rdx]
0x18012e150  test    ax, ax
0x18012e153  jz      short loc_18012E169
0x18012e155  mov     [rbx], ax
0x18012e158  add     rdx, 2
0x18012e15c  add     rbx, 2
0x18012e160  dec     rcx
0x18012e163  sub     r8, 1
0x18012e167  jnz     short loc_18012E148
0x18012e169  test    r8, r8
0x18012e16c  lea     rcx, [rbx-2]
0x18012e170  cmovnz  rcx, rbx
0x18012e174  xor     eax, eax
0x18012e176  mov     [rcx], ax
0x18012e179  xor     r15d, r15d
0x18012e17c  jmp     loc_18012DE92
0x18012e181  cmp     word ptr [rbx+rdi*2-2], 5Ch ; '\'
0x18012e187  jnz     loc_18012E0F3
0x18012e18d  dec     rdi
0x18012e190  jmp     loc_18012E0F3
0x18012e195  cmp     word ptr [r8+rsi*2-2], 5Ch ; '\'
0x18012e19c  jnz     loc_18012E0D4
0x18012e1a2  dec     rsi
0x18012e1a5  jmp     loc_18012E0D4
0x18012e1aa  cmp     word ptr [rbx+rsi*2], 5Ch ; '\'
0x18012e1af  jz      short loc_18012E1ED
0x18012e1b1  cmp     rdi, rsi
0x18012e1b4  jnz     loc_18012E0FC
0x18012e1ba  mov     rdx, rdi
0x18012e1bd  jmp     short loc_18012E1F0
0x18012e1bf  mov     r8d, 104h; cchBufferLength
0x18012e1c5  lea     rdx, [rsp+6E0h+pszPath]; lpszVolumePathName
0x18012e1ca  mov     rcx, r12; lpszFileName
0x18012e1cd  call    cs:__imp_GetVolumePathNameW
0x18012e1d3  test    eax, eax
  ... truncated ...
```
