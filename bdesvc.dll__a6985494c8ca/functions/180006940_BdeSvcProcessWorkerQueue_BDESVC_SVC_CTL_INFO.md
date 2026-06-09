# BdeSvcProcessWorkerQueue(_BDESVC_SVC_CTL_INFO *)

- ea: `0x180006940`
- end: `0x1800073a3`
- name: `?BdeSvcProcessWorkerQueue@@YAXPEAU_BDESVC_SVC_CTL_INFO@@@Z`
- size: `2659`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x180007d90`

## callees

- `0x180006260`
- `0x180006940`
- `0x1800073b0`
- `0x180009f30`
- `0x180009f60`
- `0x18002a04c`
- `0x18002a62c`
- `0x18002a718`
- `0x18002aad4`
- `0x18002ae7c`
- `0x18002f65c`
- `0x180034070`
- `0x180034d28`
- `0x18003a99c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800069f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006b25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006da4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800069f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006b25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006da4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006be6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007307`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006be6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007307`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000736a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000736a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006989`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000719b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000719b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072f7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006c88`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007167`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006c88`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007167`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180006d3e`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180007218`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180006d3e`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180007218`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180006c03`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180006ec1`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180007320`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180006c03`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180006ec1`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180007320`

## pseudocode

```c
void __fastcall BdeSvcProcessWorkerQueue(LPCRITICAL_SECTION lpCriticalSection)
{
  LPCRITICAL_SECTION v1; // r14
  LPCRITICAL_SECTION v2; // r12
  WCHAR *v3; // rdi
  __int64 ***OwningThread; // r8
  __int64 **v5; // r9
  __int64 *v6; // rcx
  __int64 v7; // rdx
  PVOID *v8; // rcx
  __int64 v9; // rdx
  WCHAR ***v10; // rax
  WCHAR **v11; // r9
  WCHAR *v12; // rbx
  __int64 v13; // r10
  _QWORD *v14; // r9
  __int64 v15; // rbx
  volatile signed __int32 *FileW; // r15
  DWORD LastError; // eax
  volatile signed __int32 *v18; // r12
  LONG *p_LockCount; // r15
  unsigned int v20; // eax
  LPCRITICAL_SECTION v21; // r13
  __int64 v22; // r13
  __int64 v23; // rcx
  LPCRITICAL_SECTION v24; // rax
  unsigned int **v25; // r13
  unsigned int *v26; // rbx
  __int64 v27; // rcx
  const wchar_t *v28; // rax
  const wchar_t *v29; // rdx
  size_t v30; // rcx
  size_t v31; // r8
  int v32; // eax
  char v33; // dl
  unsigned int *v34; // rcx
  unsigned int *v35; // rax
  size_t v36; // rax
  const wchar_t *v37; // rdx
  const wchar_t *v38; // rcx
  size_t v39; // r8
  int v40; // eax
  PVOID *v41; // rcx
  wchar_t **v42; // r9
  wchar_t **v43; // r9
  const WCHAR *v44; // rcx
  volatile signed __int32 *v45; // rbx
  DWORD v46; // eax
  unsigned int v47; // eax
  __int64 v48; // r13
  LPCRITICAL_SECTION v49; // [rsp+40h] [rbp-2B8h]
  WCHAR *v50; // [rsp+48h] [rbp-2B0h] BYREF
  size_t v51; // [rsp+50h] [rbp-2A8h]
  unsigned int *v52; // [rsp+58h] [rbp-2A0h]
  volatile signed __int32 *v53; // [rsp+60h] [rbp-298h]
  LPCRITICAL_SECTION v54; // [rsp+68h] [rbp-290h]
  volatile signed __int32 *v55; // [rsp+70h] [rbp-288h]
  LPCRITICAL_SECTION v56; // [rsp+78h] [rbp-280h]
  LPCRITICAL_SECTION v57; // [rsp+80h] [rbp-278h]
  HANDLE hHeap; // [rsp+90h] [rbp-268h]
  _QWORD v59[2]; // [rsp+98h] [rbp-260h] BYREF
  __int64 v60; // [rsp+A8h] [rbp-250h] BYREF
  char v61; // [rsp+B0h] [rbp-248h]
  char v62[8]; // [rsp+B8h] [rbp-240h] BYREF
  LPCRITICAL_SECTION v63; // [rsp+C0h] [rbp-238h]
  char v64[28]; // [rsp+C8h] [rbp-230h] BYREF
  int i; // [rsp+E4h] [rbp-214h]
  _QWORD v66[2]; // [rsp+F0h] [rbp-208h] BYREF
  int v67; // [rsp+100h] [rbp-1F8h] BYREF
  int v68; // [rsp+108h] [rbp-1F0h]
  volatile signed __int32 *v69; // [rsp+110h] [rbp-1E8h]
  wchar_t *S2[2]; // [rsp+2A0h] [rbp-58h] BYREF
  size_t N; // [rsp+2B0h] [rbp-48h]
  unsigned __int64 v72; // [rsp+2B8h] [rbp-40h]

  v49 = lpCriticalSection;
  v57 = lpCriticalSection;
  v1 = lpCriticalSection;
  v56 = lpCriticalSection;
  v2 = lpCriticalSection;
  v54 = lpCriticalSection;
  hHeap = GetProcessHeap();
  memset_0(&v67, 0, 0x1A0u);
  while ( 1 )
  {
    v66[0] = 0;
    v3 = 0;
    v50 = 0;
    *(_OWORD *)S2 = 0;
    N = 0;
    v72 = 0;
    std::wstring::_Construct_empty(S2);
    EnterCriticalSection(v1);
    OwningThread = (__int64 ***)v1[1].OwningThread;
    v5 = OwningThread[1];
    if ( v5 )
    {
      v6 = **OwningThread;
      v3 = (WCHAR *)v6[2];
      v50 = v3;
      v7 = *v6;
      OwningThread[1] = (__int64 **)((char *)v5 - 1);
      *(_QWORD *)v6[1] = v7;
      *(_QWORD *)(v7 + 8) = v6[1];
      std::_Deallocate<16>(v6, (struct std::nothrow_t *)24);
    }
    LeaveCriticalSection(v1);
    if ( !v3 )
      break;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        134,
        &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
        *(unsigned int *)v3);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *(_DWORD *)v3 == 1 )
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
        WPP_SF_S(v8[2], 135, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v3 + 8);
      v15 = (__int64)(v3 + 8);
      v52 = (unsigned int *)(v3 + 8);
      FileW = (volatile signed __int32 *)CreateFileW(v3 + 8, 0, 3u, 0, 3u, 0x80u, 0);
      v55 = FileW;
      if ( FileW == (volatile signed __int32 *)-1LL )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            136,
            &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
            LastError);
        }
        v18 = (volatile signed __int32 *)&v2[1];
        p_LockCount = &v56[1].LockCount;
      }
      else
      {
        memset_0(&v67, 0, 0x1A0u);
        v67 = 416;
        v68 = 1;
        v69 = FileW;
        v20 = CM_Register_Notification(&v67, v1, BdeSvcDeviceEventCallback, v66);
        if ( v20 )
        {
          v66[0] = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v20);
          v18 = (volatile signed __int32 *)&v2[1];
          v21 = v56;
        }
        else
        {
          v18 = (volatile signed __int32 *)&v1[1];
          v53 = (volatile signed __int32 *)&v1[1];
          _InterlockedIncrement((volatile signed __int32 *)&v1[1]);
          v51 = (size_t)v1;
          EnterCriticalSection(v1);
          if ( __eh34_try(-1, 0) )
          {
            __eh34_scope_strut(0);
            v59[0] = v3 + 8;
            v59[1] = v66[0];
            std::_Tree<std::_Tmap_traits<std::wstring,HCMNOTIFICATION__ *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,HCMNOTIFICATION__ *>>,0>>::_Emplace<std::pair<unsigned short const *,HCMNOTIFICATION__ *>>(
              *(_QWORD *)&v1[1].LockCount,
              &v60,
              v59);
            if ( v61 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
              v23 = 0;
            }
            else
            {
              v22 = v60;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  138,
                  &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
                  v3 + 8);
              v23 = *(_QWORD *)(v22 + 64);
              *(_QWORD *)(v22 + 64) = v66[0];
            }
            v66[0] = v23;
            LeaveCriticalSection(v1);
            v24 = v49;
          }
          if ( __eh34_catch(0) )
          {
            if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
              FileW = v55;
              v3 = v50;
              v24 = v57;
              v49 = v57;
              v1 = v57;
              v15 = (__int64)v52;
              v18 = v53;
              __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180006E87);
            }
          }
          if ( v66[0] )
          {
            ((void (*)(void))CM_Unregister_Notification)();
            _InterlockedDecrement(v18);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
            v21 = v49;
          }
          else
          {
            v21 = v24;
          }
        }
        CloseHandle((HANDLE)FileW);
        p_LockCount = &v21[1].LockCount;
      }
      v55 = v18;
      v66[0] = 0;
      if ( !(unsigned int)((__int64 (__fastcall *)(__int64))BdeSvcDiskDevicePnpPathFromVolumePath)(v15) )
      {
        v63 = v1;
        EnterCriticalSection(v1);
        v25 = *(unsigned int ***)p_LockCount;
        v26 = **(unsigned int ***)p_LockCount;
        v27 = *((_QWORD *)v26 + 1);
        v52 = (unsigned int *)v27;
        for ( i = 0; !*(_BYTE *)(v27 + 25); v52 = (unsigned int *)v27 )
        {
          v28 = (const wchar_t *)(v27 + 32);
          v51 = N;
          v29 = (const wchar_t *)S2;
          if ( v72 > 7 )
            v29 = S2[0];
          v30 = *(_QWORD *)(v27 + 48);
          v53 = (volatile signed __int32 *)v30;
          if ( *((_QWORD *)v28 + 3) > 7u )
            v28 = *(const wchar_t **)v28;
          v31 = N;
          if ( N >= v30 )
            v31 = v30;
          v32 = wmemcmp(v28, v29, v31);
          if ( v32 )
          {
            if ( v32 < 0 )
            {
LABEL_92:
              v33 = 1;
              v34 = v52;
              goto LABEL_78;
            }
          }
          else if ( (unsigned __int64)v53 < v51 )
          {
            goto LABEL_92;
          }
          v33 = 0;
          v34 = v52;
          v26 = v52;
LABEL_78:
          v35 = v34 + 4;
          if ( !v33 )
            v35 = v34;
          v27 = *(_QWORD *)v35;
        }
        if ( *((_BYTE *)v26 + 25) )
        {
LABEL_94:
          v26 = *v25;
        }
        else
        {
          v36 = *((_QWORD *)v26 + 6);
          v53 = (volatile signed __int32 *)v36;
          v37 = (const wchar_t *)(v26 + 8);
          if ( *((_QWORD *)v26 + 7) > 7u )
            v37 = *(const wchar_t **)v37;
          v51 = N;
          v38 = (const wchar_t *)S2;
          if ( v72 > 7 )
            v38 = S2[0];
          v39 = v36;
          if ( v36 >= N )
            v39 = N;
          v40 = wmemcmp(v38, v37, v39);
          if ( v40 )
          {
            if ( v40 < 0 )
              goto LABEL_94;
          }
          else if ( v51 < (unsigned __int64)v53 )
          {
            goto LABEL_94;
          }
        }
        v41 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v42 = S2;
          if ( v72 > 7 )
            v42 = (wchar_t **)S2[0];
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v42);
          v41 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v26 == **(unsigned int ***)p_LockCount )
        {
          v44 = (const WCHAR *)S2;
          if ( v72 > 7 )
            v44 = S2[0];
          v45 = (volatile signed __int32 *)CreateFileW(v44, 0x20000u, 3u, 0, 3u, 0x80u, 0);
          v51 = (size_t)v45;
          if ( v45 == (volatile signed __int32 *)-1LL )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v46 = GetLastError();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v46);
            }
          }
          else
          {
            memset_0(&v67, 0, 0x1A0u);
            v67 = 416;
            v68 = 1;
            v69 = v45;
            v47 = CM_Register_Notification(&v67, v1, BdeSvcDeviceEventCallback, v66);
            if ( v47 )
            {
              v66[0] = 0;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  145,
                  &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
                  v47);
            }
            else
            {
              if ( __eh34_try(-1, 2) )
              {
                __eh34_scope_strut(2);
                _InterlockedIncrement(v18);
                v48 = v66[0];
                *(_QWORD *)(*(_QWORD *)std::map<std::wstring,HCMNOTIFICATION__ *>::_Try_emplace<std::wstring const &,>(
                                         *(_QWORD *)p_LockCount,
                                         v64,
                                         S2)
                          + 64LL) = v48;
                v66[0] = 0;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
              }
              if ( __eh34_catch(2) )
              {
                if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
                  v3 = v50;
                  v45 = (volatile signed __int32 *)v51;
                  v49 = v57;
                  v18 = v55;
                  v1 = v57;
                  __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_1800072CC);
                }
              }
            }
            CloseHandle((HANDLE)v45);
          }
        }
        else if ( v41 != &WPP_GLOBAL_Control && (*((_BYTE *)v41 + 28) & 2) != 0 )
        {
          v43 = S2;
          if ( v72 > 7 )
            v43 = (wchar_t **)S2[0];
          WPP_SF_S(v41[2], 143, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v43);
        }
        LeaveCriticalSection(v1);
      }
      if ( v66[0] )
      {
        ((void (*)(void))CM_Unregister_Notification)();
        _InterlockedDecrement(v18);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
      }
      v2 = v54;
      goto LABEL_127;
    }
    if ( *(_DWORD *)v3 != 2 )
    {
      if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 2) == 0 )
        goto LABEL_127;
      v9 = 152;
      goto LABEL_16;
    }
    v66[0] = *((_QWORD *)v3 + 2);
    EnterCriticalSection(v1);
    v10 = *(WCHAR ****)&v1[1].LockCount;
    v11 = *v10;
    v12 = **v10;
    v50 = v12;
    v13 = v66[0];
    while ( 1 )
    {
      if ( v12 == (WCHAR *)v11 )
        goto LABEL_22;
      if ( *((_QWORD *)v12 + 8) == v13 )
        break;
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HCMNOTIFICATION__ *>>>,std::_Iterator_base0>::operator++((__int64 *)&v50);
      v12 = v50;
    }
    if ( v12 == (WCHAR *)v11 )
    {
LABEL_22:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
      v66[0] = 0;
      goto LABEL_32;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v14 = v12 + 16;
      if ( *((_QWORD *)v12 + 7) > 7u )
        v14 = (_QWORD *)*v14;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v14);
    }
    std::_Tree<std::_Tmap_traits<std::wstring,HCMNOTIFICATION__ *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,HCMNOTIFICATION__ *>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HCMNOTIFICATION__ *>>>>,0>(
      *(_QWORD *)&v1[1].LockCount,
      v62,
      v12);
LABEL_32:
    LeaveCriticalSection(v1);
    if ( v66[0] )
    {
      ((void (*)(void))CM_Unregister_Notification)();
      _InterlockedDecrement((volatile signed __int32 *)&v1[1]);
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v9 = 151;
LABEL_16:
        WPP_SF_(v8[2], v9, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
      }
    }
LABEL_127:
    HeapFree(hHeap, 0, v3);
    if ( v72 > 7 )
      std::_Deallocate<16>(S2[0], (struct std::nothrow_t *)(2 * v72 + 2));
  }
  if ( v72 > 7 )
    std::_Deallocate<16>(S2[0], (struct std::nothrow_t *)(2 * v72 + 2));
}

```

## disassembly

```asm
0x180006940  mov     [rsp+arg_8], rbx
0x180006945  mov     [rsp+arg_10], rsi
0x18000694a  push    rdi
0x18000694b  push    r12
0x18000694d  push    r13
0x18000694f  push    r14
0x180006951  push    r15
0x180006953  sub     rsp, 2D0h
0x18000695a  mov     rax, cs:__security_cookie
0x180006961  xor     rax, rsp
0x180006964  mov     [rsp+2F8h+var_38], rax
0x18000696c  mov     [rsp+2F8h+var_2B8], rcx
0x180006971  mov     [rsp+2F8h+var_278], rcx
0x180006979  mov     r14, rcx
0x18000697c  mov     [rsp+2F8h+var_280], rcx
0x180006981  mov     r12, rcx
0x180006984  mov     [rsp+2F8h+var_290], rcx
0x180006989  call    cs:__imp_GetProcessHeap
0x180006990  nop     dword ptr [rax+rax+00h]
0x180006995  mov     [rsp+2F8h+hHeap], rax
0x18000699d  xor     edx, edx; Val
0x18000699f  mov     r8d, 1A0h; Size
0x1800069a5  lea     rcx, [rsp+2F8h+var_1F8]; void *
0x1800069ad  call    memset_0
0x1800069b2  xor     esi, esi
0x1800069b4  lea     r13, WPP_GLOBAL_Control
0x1800069bb  mov     [rsp+2F8h+var_208], rsi
0x1800069c3  mov     rdi, rsi
0x1800069c6  mov     [rsp+2F8h+var_2B0], rsi
0x1800069cb  xorps   xmm0, xmm0
0x1800069ce  movups  xmmword ptr [rsp+2F8h+S2], xmm0
0x1800069d6  mov     [rsp+2F8h+N], rsi
0x1800069de  mov     [rsp+2F8h+var_40], rsi
0x1800069e6  lea     rcx, [rsp+2F8h+S2]
0x1800069ee  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800069f3  nop
0x1800069f4  mov     rcx, r14; lpCriticalSection
0x1800069f7  call    cs:__imp_EnterCriticalSection
0x1800069fe  nop     dword ptr [rax+rax+00h]
0x180006a03  mov     r8, [r14+38h]
0x180006a07  mov     r9, [r8+8]
0x180006a0b  test    r9, r9
0x180006a0e  jz      short loc_180006A43
0x180006a10  mov     rax, [r8]
0x180006a13  mov     rcx, [rax]
0x180006a16  mov     rdi, [rcx+10h]
0x180006a1a  mov     [rsp+2F8h+var_2B0], rdi
0x180006a1f  mov     rdx, [rcx]
0x180006a22  lea     rax, [r9-1]
0x180006a26  mov     [r8+8], rax
0x180006a2a  mov     rax, [rcx+8]
0x180006a2e  mov     [rax], rdx
0x180006a31  mov     rax, [rcx+8]
0x180006a35  mov     [rdx+8], rax
0x180006a39  mov     edx, 18h
0x180006a3e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006a43  mov     rcx, r14; lpCriticalSection
0x180006a46  call    cs:__imp_LeaveCriticalSection
0x180006a4d  nop     dword ptr [rax+rax+00h]
0x180006a52  test    rdi, rdi
0x180006a55  jnz     short loc_180006AA8
0x180006a57  mov     rdx, [rsp+2F8h+var_40]
0x180006a5f  cmp     rdx, 7
0x180006a63  jbe     short loc_180006A7A
0x180006a65  lea     rdx, ds:2[rdx*2]
0x180006a6d  mov     rcx, [rsp+2F8h+S2]
0x180006a75  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006a7a  mov     rcx, [rsp+2F8h+var_38]
0x180006a82  xor     rcx, rsp; StackCookie
0x180006a85  call    __security_check_cookie
0x180006a8a  lea     r11, [rsp+2F8h+var_28]
0x180006a92  mov     rbx, [r11+38h]
0x180006a96  mov     rsi, [r11+40h]
0x180006a9a  mov     rsp, r11
0x180006a9d  pop     r15
0x180006a9f  pop     r14
0x180006aa1  pop     r13
0x180006aa3  pop     r12
0x180006aa5  pop     rdi
0x180006aa6  retn
0x180006aa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006aaf  cmp     rcx, r13
0x180006ab2  jz      short loc_180006AD9
0x180006ab4  test    byte ptr [rcx+1Ch], 8
0x180006ab8  jz      short loc_180006AD9
0x180006aba  mov     edx, 86h
0x180006abf  mov     r9d, [rdi]
0x180006ac2  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180006ac9  mov     rcx, [rcx+10h]
0x180006acd  call    WPP_SF_d
0x180006ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ad9  mov     edx, [rdi]
0x180006adb  sub     edx, 1
0x180006ade  jz      loc_180006C38
0x180006ae4  cmp     edx, 1
0x180006ae7  jz      short loc_180006B16
0x180006ae9  cmp     rcx, r13
0x180006aec  jz      loc_18000735D
0x180006af2  test    byte ptr [rcx+1Ch], 2
0x180006af6  jz      loc_18000735D
0x180006afc  mov     edx, 98h
0x180006b01  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180006b08  mov     rcx, [rcx+10h]
0x180006b0c  call    WPP_SF_
0x180006b11  jmp     loc_18000735D
0x180006b16  mov     rax, [rdi+10h]
0x180006b1a  mov     [rsp+2F8h+var_208], rax
0x180006b22  mov     rcx, r14; lpCriticalSection
0x180006b25  call    cs:__imp_EnterCriticalSection
0x180006b2c  nop     dword ptr [rax+rax+00h]
0x180006b31  mov     rax, [r14+30h]
0x180006b35  mov     r9, [rax]
0x180006b38  mov     rbx, [r9]
0x180006b3b  mov     [rsp+2F8h+var_2B0], rbx
0x180006b40  mov     r10, [rsp+2F8h+var_208]
0x180006b48  cmp     rbx, r9
0x180006b4b  jz      short loc_180006B69
0x180006b4d  cmp     [rbx+40h], r10
0x180006b51  jz      short loc_180006B64
0x180006b53  lea     rcx, [rsp+2F8h+var_2B0]
0x180006b58  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHCMNOTIFICATION__@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HCMNOTIFICATION__ *>>>,std::_Iterator_base0>::operator++(void)
0x180006b5d  mov     rbx, [rsp+2F8h+var_2B0]
0x180006b62  jmp     short loc_180006B48
0x180006b64  cmp     rbx, r9
0x180006b67  jnz     short loc_180006B9A
0x180006b69  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b70  cmp     rcx, r13
0x180006b73  jz      short loc_180006B90
0x180006b75  test    byte ptr [rcx+1Ch], 2
0x180006b79  jz      short loc_180006B90
0x180006b7b  mov     edx, 95h
0x180006b80  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180006b87  mov     rcx, [rcx+10h]
0x180006b8b  call    WPP_SF_
0x180006b90  mov     [rsp+2F8h+var_208], rsi
0x180006b98  jmp     short loc_180006BE3
0x180006b9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ba1  cmp     rcx, r13
0x180006ba4  jz      short loc_180006BCF
0x180006ba6  test    byte ptr [rcx+1Ch], 8
0x180006baa  jz      short loc_180006BCF
0x180006bac  lea     r9, [rbx+20h]
0x180006bb0  cmp     qword ptr [r9+18h], 7
0x180006bb5  jbe     short loc_180006BBA
0x180006bb7  mov     r9, [r9]
0x180006bba  mov     edx, 96h
0x180006bbf  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180006bc6  mov     rcx, [rcx+10h]
0x180006bca  call    WPP_SF_S
0x180006bcf  mov     r8, rbx
0x180006bd2  lea     rdx, [rsp+2F8h+var_240]
0x180006bda  mov     rcx, [r14+30h]
0x180006bde  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHCMNOTIFICATION__@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHCMNOTIFICATION__@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHCMNOTIFICATION__@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHCMNOTIFICATION__@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::wstring,HCMNOTIFICATION__ *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,HCMNOTIFICATION__ *>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HCMNOTIFICATION__ *>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HCMNOTIFICATION__ *>>>>)
0x180006be3  mov     rcx, r14; lpCriticalSection
0x180006be6  call    cs:__imp_LeaveCriticalSection
0x180006bed  nop     dword ptr [rax+rax+00h]
0x180006bf2  mov     rcx, [rsp+2F8h+var_208]
0x180006bfa  test    rcx, rcx
0x180006bfd  jz      loc_18000735D
0x180006c03  call    cs:__imp_CM_Unregister_Notification
0x180006c0a  nop     dword ptr [rax+rax+00h]
0x180006c0f  lock dec dword ptr [r14+28h]
0x180006c14  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c1b  cmp     rcx, r13
0x180006c1e  jz      loc_18000735D
0x180006c24  test    byte ptr [rcx+1Ch], 8
0x180006c28  jz      loc_18000735D
0x180006c2e  mov     edx, 97h
0x180006c33  jmp     loc_180006B01
0x180006c38  cmp     rcx, r13
0x180006c3b  jz      short loc_180006C5C
0x180006c3d  test    byte ptr [rcx+1Ch], 8
0x180006c41  jz      short loc_180006C5C
0x180006c43  lea     r9, [rdi+10h]
0x180006c47  mov     edx, 87h
0x180006c4c  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180006c53  mov     rcx, [rcx+10h]
0x180006c57  call    WPP_SF_S
0x180006c5c  lea     rbx, [rdi+10h]
0x180006c60  mov     [rsp+2F8h+var_2A0], rbx
0x180006c65  mov     [rsp+2F8h+hTemplateFile], rsi; hTemplateFile
0x180006c6a  mov     [rsp+2F8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180006c72  mov     [rsp+2F8h+dwCreationDisposition], 3; dwCreationDisposition
0x180006c7a  xor     r9d, r9d; lpSecurityAttributes
0x180006c7d  xor     edx, edx; dwDesiredAccess
0x180006c7f  mov     r8d, 3; dwShareMode
0x180006c85  mov     rcx, rbx; lpFileName
0x180006c88  call    cs:__imp_CreateFileW
0x180006c8f  nop     dword ptr [rax+rax+00h]
0x180006c94  mov     r15, rax
0x180006c97  mov     [rsp+2F8h+var_288], rax
0x180006c9c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006ca0  jnz     short loc_180006CF1
0x180006ca2  mov     rax, cs:WPP_GLOBAL_Control
0x180006ca9  cmp     rax, r13
0x180006cac  jz      short loc_180006CDF
0x180006cae  test    byte ptr [rax+1Ch], 2
0x180006cb2  jz      short loc_180006CDF
0x180006cb4  call    cs:__imp_GetLastError
0x180006cbb  nop     dword ptr [rax+rax+00h]
0x180006cc0  mov     edx, 88h
0x180006cc5  mov     r9d, eax
0x180006cc8  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180006ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cd6  mov     rcx, [rcx+10h]
0x180006cda  call    WPP_SF_d
0x180006cdf  add     r12, 28h ; '('
0x180006ce3  mov     r15, [rsp+2F8h+var_280]
0x180006ce8  add     r15, 30h ; '0'
0x180006cec  jmp     loc_180006F22
0x180006cf1  xor     edx, edx; Val
0x180006cf3  mov     r8d, 1A0h; Size
0x180006cf9  lea     rcx, [rsp+2F8h+var_1F8]; void *
0x180006d01  call    memset_0
0x180006d06  mov     [rsp+2F8h+var_1F8], 1A0h
0x180006d11  mov     [rsp+2F8h+var_1F0], 1
0x180006d1c  mov     [rsp+2F8h+var_1E8], r15
0x180006d24  lea     r9, [rsp+2F8h+var_208]
0x180006d2c  lea     r8, ?BdeSvcDeviceEventCallback@@YAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; BdeSvcDeviceEventCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180006d33  mov     rdx, r14
0x180006d36  lea     rcx, [rsp+2F8h+var_1F8]
0x180006d3e  call    cs:__imp_CM_Register_Notification
0x180006d45  nop     dword ptr [rax+rax+00h]
0x180006d4a  test    eax, eax
0x180006d4c  jz      short loc_180006D8E
0x180006d4e  mov     [rsp+2F8h+var_208], rsi
0x180006d56  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d5d  cmp     rcx, r13
0x180006d60  jz      short loc_180006D80
0x180006d62  test    byte ptr [rcx+1Ch], 2
0x180006d66  jz      short loc_180006D80
0x180006d68  mov     edx, 89h
0x180006d6d  mov     r9d, eax
0x180006d70  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180006d77  mov     rcx, [rcx+10h]
0x180006d7b  call    WPP_SF_d
0x180006d80  add     r12, 28h ; '('
0x180006d84  mov     r13, [rsp+2F8h+var_280]
0x180006d89  jmp     loc_180006F03
0x180006d8e  lea     r12, [r14+28h]
0x180006d92  mov     [rsp+2F8h+var_298], r12
0x180006d97  lock inc dword ptr [r12]
0x180006d9c  mov     [rsp+2F8h+var_2A8], r14
0x180006da1  mov     rcx, r14; lpCriticalSection
0x180006da4  call    cs:__imp_EnterCriticalSection
0x180006dab  nop     dword ptr [rax+rax+00h]
0x180006db0  nop
0x180006db1  mov     [rsp+2F8h+var_260], rbx
0x180006db9  mov     rax, [rsp+2F8h+var_208]
0x180006dc1  mov     [rsp+2F8h+var_258], rax
0x180006dc9  lea     r8, [rsp+2F8h+var_260]
0x180006dd1  lea     rdx, [rsp+2F8h+var_250]
0x180006dd9  mov     rcx, [r14+30h]
0x180006ddd  call    ??$_Emplace@U?$pair@PEBGPEAUHCMNOTIFICATION__@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHCMNOTIFICATION__@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHCMNOTIFICATION__@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHCMNOTIFICATION__@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@PEBGPEAUHCMNOTIFICATION__@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,HCMNOTIFICATION__ *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,HCMNOTIFICATION__ *>>,0>>::_Emplace<std::pair<ushort const *,HCMNOTIFICATION__ *>>(std::pair<ushort const *,HCMNOTIFICATION__ *> &&)
0x180006de2  cmp     [rsp+2F8h+var_248], 0
0x180006dea  jnz     short loc_180006E3E
0x180006dec  mov     r13, [rsp+2F8h+var_250]
0x180006df4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dfb  lea     rax, WPP_GLOBAL_Control
0x180006e02  cmp     rcx, rax
0x180006e05  jz      short loc_180006E25
0x180006e07  test    byte ptr [rcx+1Ch], 8
0x180006e0b  jz      short loc_180006E25
0x180006e0d  mov     edx, 8Ah
0x180006e12  mov     r9, rbx
0x180006e15  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180006e1c  mov     rcx, [rcx+10h]
0x180006e20  call    WPP_SF_S
0x180006e25  mov     rcx, [r13+40h]
0x180006e29  mov     rax, [rsp+2F8h+var_208]
0x180006e31  mov     [r13+40h], rax
0x180006e35  lea     r13, WPP_GLOBAL_Control
0x180006e3c  jmp     short loc_180006E68
0x180006e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e45  cmp     rcx, r13
0x180006e48  jz      short loc_180006E65
0x180006e4a  test    byte ptr [rcx+1Ch], 8
0x180006e4e  jz      short loc_180006E65
0x180006e50  mov     edx, 8Bh
0x180006e55  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180006e5c  mov     rcx, [rcx+10h]
0x180006e60  call    WPP_SF_
0x180006e65  mov     rcx, rsi
0x180006e68  mov     [rsp+2F8h+var_208], rcx
0x180006e70  mov     rcx, r14; lpCriticalSection
0x180006e73  call    cs:__imp_LeaveCriticalSection
0x180006e7a  nop     dword ptr [rax+rax+00h]
0x180006e7f  nop
0x180006e80  mov     rax, [rsp+2F8h+var_2B8]
0x180006e85  jmp     short loc_180006EB4
0x180006e87  xor     esi, esi
0x180006e89  lea     r13, WPP_GLOBAL_Control
0x180006e90  mov     r15, [rsp+2F8h+var_288]
0x180006e95  mov     rdi, [rsp+2F8h+var_2B0]
0x180006e9a  mov     rax, [rsp+2F8h+var_278]
0x180006ea2  mov     [rsp+2F8h+var_2B8], rax
0x180006ea7  mov     r14, rax
0x180006eaa  mov     rbx, [rsp+2F8h+var_2A0]
0x180006eaf  mov     r12, [rsp+2F8h+var_298]
0x180006eb4  mov     rcx, [rsp+2F8h+var_208]
  ... truncated ...
```
