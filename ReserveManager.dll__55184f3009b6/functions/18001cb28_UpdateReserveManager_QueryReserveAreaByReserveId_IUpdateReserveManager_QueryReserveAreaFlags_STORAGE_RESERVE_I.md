# UpdateReserveManager::QueryReserveAreaByReserveId(IUpdateReserveManager::QueryReserveAreaFlags,_STORAGE_RESERVE_ID,IUpdateReserveManager::RESERVE_AREA_INFORMATION *)

- ea: `0x18001cb28`
- end: `0x18001ce6e`
- name: `?QueryReserveAreaByReserveId@UpdateReserveManager@@AEAAJW4QueryReserveAreaFlags@IUpdateReserveManager@@W4_STORAGE_RESERVE_ID@@PEAURESERVE_AREA_INFORMATION@3@@Z`
- size: `838`
- prototype: `__int64 __fastcall(WCHAR *, char, unsigned int, _QWORD *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x1800133f8`
- `0x18001c9e0`
- `0x1800204d0`

## callees

- `0x180003870`
- `0x180003c84`
- `0x180008140`
- `0x18000fafc`
- `0x180015ad0`
- `0x18001cb28`
- `0x18001ce74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce57`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18001cc30`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18001cc30`

## string_xrefs

- `0x18001cca0`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001ccca`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001ccf4`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001cd1e`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001cd45`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001cd6c`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001cd93`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001cdf9`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001ccab`: `UpdateReserveManager::QueryReserveAreaByReserveId`
- `0x18001ccd5`: `UpdateReserveManager::QueryReserveAreaByReserveId`
- `0x18001ccff`: `UpdateReserveManager::QueryReserveAreaByReserveId`
- `0x18001cd29`: `UpdateReserveManager::QueryReserveAreaByReserveId`
- `0x18001cd50`: `UpdateReserveManager::QueryReserveAreaByReserveId`
- `0x18001cd77`: `UpdateReserveManager::QueryReserveAreaByReserveId`
- `0x18001cd9e`: `UpdateReserveManager::QueryReserveAreaByReserveId`
- `0x18001ce04`: `UpdateReserveManager::QueryReserveAreaByReserveId`
- `0x18001ce17`: `EnsureBOOL(::GetDiskFreeSpaceExW(m_WindowsDirPath, nullptr, nullptr, &UserSpaceFreeBytesOnDisk))`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::QueryReserveAreaByReserveId(WCHAR *a1, char a2, unsigned int a3, _QWORD *a4)
{
  __int64 result; // rax
  int ReserveAreaInternal; // ebx
  ULONGLONG v10; // rdi
  ULONGLONG v11; // rsi
  unsigned __int64 v12; // r14
  void *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rcx
  ULONGLONG v17; // r9
  __int64 v18; // rax
  const char *v19; // rax
  DWORD LastError; // edi
  const char *v21; // [rsp+20h] [rbp-40h] BYREF
  const char *v22; // [rsp+28h] [rbp-38h]
  __int64 v23; // [rsp+30h] [rbp-30h]
  const char *v24; // [rsp+38h] [rbp-28h]
  void *v25[2]; // [rsp+40h] [rbp-20h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+50h] [rbp-10h] BYREF

  v25[1] = (void *)-2LL;
  result = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)a1);
  if ( (int)result < 0 )
    return result;
  v25[0] = 0;
  ReserveAreaInternal = UpdateReserveManager::QueryReserveAreaInternal(a1, a3, v25);
  if ( ReserveAreaInternal < 0 )
  {
    if ( v25[0] )
      operator delete(v25[0]);
    return (unsigned int)ReserveAreaInternal;
  }
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = v25[0];
  v14 = 0;
  if ( *((_DWORD *)v25[0] + 1) )
  {
    while ( 1 )
    {
      v15 = *((_QWORD *)v25[0] + 3 * v14 + 2);
      if ( v15 < 0 )
        break;
      v16 = *((_QWORD *)v25[0] + 3 * v14 + 3);
      if ( v16 < 0 )
      {
        v21 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v22 = "UpdateReserveManager::QueryReserveAreaByReserveId";
        v23 = 3998;
        v19 = "::LongLongToULongLong(pQueryOutput->AreaInfo[i].SpaceUsed, &SpaceUsed)";
        goto LABEL_31;
      }
      v17 = v15 + v10;
      if ( v15 + v10 < v10 )
      {
        v21 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v22 = "UpdateReserveManager::QueryReserveAreaByReserveId";
        v23 = 4000;
        v19 = "::ULongLongAdd(TotalAreaInBytes, SpaceGuarantee, &TotalAreaInBytes)";
        goto LABEL_31;
      }
      if ( v16 + v12 < v12 )
      {
        v21 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v22 = "UpdateReserveManager::QueryReserveAreaByReserveId";
        v23 = 4001;
        v19 = "::ULongLongAdd(ReclaimableAreaInBytes, SpaceUsed, &ReclaimableAreaInBytes)";
        goto LABEL_31;
      }
      if ( v16 < (unsigned __int64)v15 )
      {
        v18 = v15 - v16;
        if ( v18 + v11 < v11 )
        {
          v21 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v22 = "UpdateReserveManager::QueryReserveAreaByReserveId";
          v23 = 4007;
          v19 = "::ULongLongAdd(FreeAreaInBytes, FreeSpaceInArea, &FreeAreaInBytes)";
          goto LABEL_31;
        }
        v11 += v18;
      }
      v10 = v17;
      v12 += v16;
      v14 = (unsigned int)(v14 + 1);
      if ( (unsigned int)v14 >= *((_DWORD *)v25[0] + 1) )
        goto LABEL_15;
    }
    v21 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v22 = "UpdateReserveManager::QueryReserveAreaByReserveId";
    v23 = 3995;
    v19 = "::LongLongToULongLong(pQueryOutput->AreaInfo[i].SpaceGuarantee, &SpaceGuarantee)";
    goto LABEL_31;
  }
LABEL_15:
  if ( (a2 & 1) == 0 )
  {
LABEL_20:
    *a4 = v10;
    a4[1] = v11;
    a4[2] = v12;
    if ( v13 )
      operator delete(v13);
    return 0;
  }
  TotalNumberOfFreeBytes.QuadPart = 0;
  if ( GetDiskFreeSpaceExW(a1 + 68, 0, 0, &TotalNumberOfFreeBytes) )
  {
    if ( TotalNumberOfFreeBytes.QuadPart + v10 < v10 )
    {
      v21 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v22 = "UpdateReserveManager::QueryReserveAreaByReserveId";
      v23 = 4016;
      v19 = "::ULongLongAdd(TotalAreaInBytes, UserSpaceFreeBytesOnDisk.QuadPart, &TotalAreaInBytes)";
    }
    else
    {
      if ( TotalNumberOfFreeBytes.QuadPart + v11 >= v11 )
      {
        v10 += TotalNumberOfFreeBytes.QuadPart;
        v11 += TotalNumberOfFreeBytes.QuadPart;
        goto LABEL_20;
      }
      v21 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v22 = "UpdateReserveManager::QueryReserveAreaByReserveId";
      v23 = 4017;
      v19 = "::ULongLongAdd(FreeAreaInBytes, UserSpaceFreeBytesOnDisk.QuadPart, &FreeAreaInBytes)";
    }
LABEL_31:
    v24 = v19;
    RtlReportErrorOrigination(&v21, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942934LL);
    if ( v13 )
      operator delete(v13);
    return 2147942934LL;
  }
  if ( GetLastError() )
  {
    LastError = GetLastError();
    if ( !LastError )
      INTERNAL_ERROR_ACTION(-1073741595);
  }
  else
  {
    LastError = 14077;
  }
  v21 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
  v22 = "UpdateReserveManager::QueryReserveAreaByReserveId";
  v23 = 4014;
  v24 = "EnsureBOOL(::GetDiskFreeSpaceExW(m_WindowsDirPath, nullptr, nullptr, &UserSpaceFreeBytesOnDisk))";
  if ( (int)LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  RtlReportErrorOrigination(&v21, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, LastError);
  if ( v13 )
    operator delete(v13);
  return LastError;
}

```

## disassembly

```asm
0x18001cb28  mov     rax, rsp
0x18001cb2b  push    rbp
0x18001cb2c  push    rsi
0x18001cb2d  push    rdi
0x18001cb2e  push    r12
0x18001cb30  push    r13
0x18001cb32  push    r14
0x18001cb34  push    r15
0x18001cb36  mov     rbp, rsp
0x18001cb39  sub     rsp, 60h
0x18001cb3d  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x18001cb45  mov     [rax+10h], rbx
0x18001cb49  mov     rax, cs:__security_cookie
0x18001cb50  xor     rax, rsp
0x18001cb53  mov     [rbp+var_8], rax
0x18001cb57  mov     r15, r9
0x18001cb5a  mov     ebx, r8d
0x18001cb5d  mov     r12d, edx
0x18001cb60  mov     r13, rcx
0x18001cb63  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001cb68  test    eax, eax
0x18001cb6a  js      loc_18001CC7C
0x18001cb70  mov     [rbp+var_20], 0
0x18001cb78  lea     r8, [rbp+var_20]
0x18001cb7c  mov     edx, ebx
0x18001cb7e  mov     rcx, r13
0x18001cb81  call    ?QueryReserveAreaInternal@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@PEAV?$AutoNewArrayPtr@E@Windows@@@Z; UpdateReserveManager::QueryReserveAreaInternal(_STORAGE_RESERVE_ID,Windows::AutoNewArrayPtr<uchar> *)
0x18001cb86  mov     ebx, eax
0x18001cb88  test    eax, eax
0x18001cb8a  jns     short loc_18001CBA1
0x18001cb8c  mov     rcx, [rbp+var_20]; void *
0x18001cb90  test    rcx, rcx
0x18001cb93  jz      short loc_18001CB9A
0x18001cb95  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cb9a  mov     eax, ebx
0x18001cb9c  jmp     loc_18001CC7C
0x18001cba1  xor     edi, edi
0x18001cba3  xor     esi, esi
0x18001cba5  xor     r14d, r14d
0x18001cba8  mov     rbx, [rbp+var_20]
0x18001cbac  xor     edx, edx
0x18001cbae  cmp     [rbx+4], edx
0x18001cbb1  jbe     short loc_18001CC12
0x18001cbb3  lea     rcx, [rdx+rdx*2]
0x18001cbb7  mov     rax, [rbx+rcx*8+10h]
0x18001cbbc  test    rax, rax
0x18001cbbf  js      loc_18001CD45
0x18001cbc5  mov     rcx, [rbx+rcx*8+18h]
0x18001cbca  test    rcx, rcx
0x18001cbcd  js      loc_18001CD1E
0x18001cbd3  lea     r9, [rax+rdi]
0x18001cbd7  cmp     r9, rdi
0x18001cbda  jb      loc_18001CCF4
0x18001cbe0  lea     r8, [rcx+r14]
0x18001cbe4  cmp     r8, r14
0x18001cbe7  jb      loc_18001CCCA
0x18001cbed  cmp     rcx, rax
0x18001cbf0  jnb     short loc_18001CC05
0x18001cbf2  sub     rax, rcx
0x18001cbf5  lea     rcx, [rax+rsi]
0x18001cbf9  cmp     rcx, rsi
0x18001cbfc  jb      loc_18001CCA0
0x18001cc02  mov     rsi, rcx
0x18001cc05  mov     rdi, r9
0x18001cc08  mov     r14, r8
0x18001cc0b  inc     edx
0x18001cc0d  cmp     edx, [rbx+4]
0x18001cc10  jb      short loc_18001CBB3
0x18001cc12  test    r12b, 1
0x18001cc16  jz      short loc_18001CC62
0x18001cc18  mov     qword ptr [rbp+TotalNumberOfFreeBytes], 0
0x18001cc20  lea     rcx, [r13+88h]; lpDirectoryName
0x18001cc27  lea     r9, [rbp+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x18001cc2b  xor     r8d, r8d; lpTotalNumberOfBytes
0x18001cc2e  xor     edx, edx; lpFreeBytesAvailableToCaller
0x18001cc30  call    cs:__imp_GetDiskFreeSpaceExW
0x18001cc36  test    eax, eax
0x18001cc38  jz      loc_18001CDEA
0x18001cc3e  mov     rax, qword ptr [rbp+TotalNumberOfFreeBytes]
0x18001cc42  lea     rdx, [rax+rdi]; unsigned __int64
0x18001cc46  cmp     rdx, rdi
0x18001cc49  jb      loc_18001CD93
0x18001cc4f  lea     rcx, [rax+rsi]
0x18001cc53  cmp     rcx, rsi
0x18001cc56  jb      loc_18001CD6C
0x18001cc5c  mov     rdi, rdx
0x18001cc5f  mov     rsi, rcx
0x18001cc62  mov     [r15], rdi
0x18001cc65  mov     [r15+8], rsi
0x18001cc69  mov     [r15+10h], r14
0x18001cc6d  test    rbx, rbx
0x18001cc70  jz      short loc_18001CC7A
0x18001cc72  mov     rcx, rbx; void *
0x18001cc75  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cc7a  xor     eax, eax
0x18001cc7c  mov     rcx, [rbp+var_8]
0x18001cc80  xor     rcx, rsp; StackCookie
0x18001cc83  call    __security_check_cookie
0x18001cc88  mov     rbx, [rsp+60h+arg_8]
0x18001cc90  add     rsp, 60h
0x18001cc94  pop     r15
0x18001cc96  pop     r14
0x18001cc98  pop     r13
0x18001cc9a  pop     r12
0x18001cc9c  pop     rdi
0x18001cc9d  pop     rsi
0x18001cc9e  pop     rbp
0x18001cc9f  retn
0x18001cca0  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001cca7  mov     [rbp+var_40], rax
0x18001ccab  lea     rax, aUpdatereservem_33; "UpdateReserveManager::QueryReserveAreaB"...
0x18001ccb2  mov     [rbp+var_38], rax
0x18001ccb6  mov     [rbp+var_30], 0FA7h
0x18001ccbe  lea     rax, aUlonglongaddFr_1; "::ULongLongAdd(FreeAreaInBytes, FreeSpa"...
0x18001ccc5  jmp     loc_18001CDB8
0x18001ccca  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001ccd1  mov     [rbp+var_40], rax
0x18001ccd5  lea     rax, aUpdatereservem_33; "UpdateReserveManager::QueryReserveAreaB"...
0x18001ccdc  mov     [rbp+var_38], rax
0x18001cce0  mov     [rbp+var_30], 0FA1h
0x18001cce8  lea     rax, aUlonglongaddRe; "::ULongLongAdd(ReclaimableAreaInBytes, "...
0x18001ccef  jmp     loc_18001CDB8
0x18001ccf4  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001ccfb  mov     [rbp+var_40], rax
0x18001ccff  lea     rax, aUpdatereservem_33; "UpdateReserveManager::QueryReserveAreaB"...
0x18001cd06  mov     [rbp+var_38], rax
0x18001cd0a  mov     [rbp+var_30], 0FA0h
0x18001cd12  lea     rax, aUlonglongaddTo_0; "::ULongLongAdd(TotalAreaInBytes, SpaceG"...
0x18001cd19  jmp     loc_18001CDB8
0x18001cd1e  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001cd25  mov     [rbp+var_40], rax
0x18001cd29  lea     rax, aUpdatereservem_33; "UpdateReserveManager::QueryReserveAreaB"...
0x18001cd30  mov     [rbp+var_38], rax
0x18001cd34  mov     [rbp+var_30], 0F9Eh
0x18001cd3c  lea     rax, aLonglongtoulon; "::LongLongToULongLong(pQueryOutput->Are"...
0x18001cd43  jmp     short loc_18001CDB8
0x18001cd45  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001cd4c  mov     [rbp+var_40], rax
0x18001cd50  lea     rax, aUpdatereservem_33; "UpdateReserveManager::QueryReserveAreaB"...
0x18001cd57  mov     [rbp+var_38], rax
0x18001cd5b  mov     [rbp+var_30], 0F9Bh
0x18001cd63  lea     rax, aLonglongtoulon_0; "::LongLongToULongLong(pQueryOutput->Are"...
0x18001cd6a  jmp     short loc_18001CDB8
0x18001cd6c  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001cd73  mov     [rbp+var_40], rax
0x18001cd77  lea     rax, aUpdatereservem_33; "UpdateReserveManager::QueryReserveAreaB"...
0x18001cd7e  mov     [rbp+var_38], rax
0x18001cd82  mov     [rbp+var_30], 0FB1h
0x18001cd8a  lea     rax, aUlonglongaddFr_2; "::ULongLongAdd(FreeAreaInBytes, UserSpa"...
0x18001cd91  jmp     short loc_18001CDB8
0x18001cd93  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001cd9a  mov     [rbp+var_40], rax
0x18001cd9e  lea     rax, aUpdatereservem_33; "UpdateReserveManager::QueryReserveAreaB"...
0x18001cda5  mov     [rbp+var_38], rax
0x18001cda9  mov     [rbp+var_30], 0FB0h
0x18001cdb1  lea     rax, aUlonglongaddTo; "::ULongLongAdd(TotalAreaInBytes, UserSp"...
0x18001cdb8  mov     [rbp+var_28], rax
0x18001cdbc  mov     r8d, 80070216h
0x18001cdc2  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001cdc9  lea     rcx, [rbp+var_40]
0x18001cdcd  call    RtlReportErrorOrigination
0x18001cdd2  nop
0x18001cdd3  test    rbx, rbx
0x18001cdd6  jz      short loc_18001CDE0
0x18001cdd8  mov     rcx, rbx; void *
0x18001cddb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cde0  mov     eax, 80070216h
0x18001cde5  jmp     loc_18001CC7C
0x18001cdea  call    cs:__imp_GetLastError
0x18001cdf0  test    eax, eax
0x18001cdf2  jnz     short loc_18001CE57
0x18001cdf4  mov     edi, 36FDh
0x18001cdf9  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001ce00  mov     [rbp+var_40], rax
0x18001ce04  lea     rax, aUpdatereservem_33; "UpdateReserveManager::QueryReserveAreaB"...
0x18001ce0b  mov     [rbp+var_38], rax
0x18001ce0f  mov     [rbp+var_30], 0FAEh
0x18001ce17  lea     rax, aEnsureboolGetd_0; "EnsureBOOL(::GetDiskFreeSpaceExW(m_Wind"...
0x18001ce1e  mov     [rbp+var_28], rax
0x18001ce22  test    edi, edi
0x18001ce24  jle     short loc_18001CE2F
0x18001ce26  movzx   edi, di
0x18001ce29  or      edi, 80070000h
0x18001ce2f  mov     r8d, edi
0x18001ce32  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001ce39  lea     rcx, [rbp+var_40]
0x18001ce3d  call    RtlReportErrorOrigination
0x18001ce42  nop
0x18001ce43  test    rbx, rbx
0x18001ce46  jz      short loc_18001CE50
0x18001ce48  mov     rcx, rbx; void *
0x18001ce4b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ce50  mov     eax, edi
0x18001ce52  jmp     loc_18001CC7C
0x18001ce57  call    cs:__imp_GetLastError
0x18001ce5d  mov     edi, eax
0x18001ce5f  test    eax, eax
0x18001ce61  jnz     short loc_18001CDF9
0x18001ce63  mov     ecx, 0C00000E5h; int
0x18001ce68  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
