# CCloudFileSystemApplier::CompareFileContent(IFspFile *,IFspFile *,int *)

- ea: `0x18008db80`
- end: `0x18008e650`
- name: `?CompareFileContent@CCloudFileSystemApplier@@UEAAJPEAUIFspFile@@0PEAH@Z`
- size: `2768`
- prototype: `__int64 __fastcall(CCloudFileSystemApplier *__hidden this, struct IFspFile *, struct IFspFile *, int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180002ae0`
- `0x1800035f8`
- `0x180003f10`
- `0x18000430d`
- `0x180007b9c`
- `0x180007e10`
- `0x180009188`
- `0x180011314`
- `0x18001133c`
- `0x180022688`
- `0x180047d10`
- `0x18008b634`
- `0x18008c218`
- `0x18008db80`
- `0x180090ac0`
- `0x180092d2c`
- `0x18013e010`

## import_xrefs

- `KERNEL32!CancelIo` at `0x18008e577`
- `KERNEL32!CancelIo` at `0x18008e577`
- `KERNEL32!GetOverlappedResult` at `0x18008e2ea`
- `KERNEL32!GetOverlappedResult` at `0x18008e2ea`
- `KERNEL32!ReadFile` at `0x18008e22b`
- `KERNEL32!ReadFile` at `0x18008e22b`
- `KERNEL32!WaitForSingleObject` at `0x18008e5a0`
- `KERNEL32!WaitForSingleObject` at `0x18008e5b1`
- `KERNEL32!WaitForSingleObject` at `0x18008e5a0`
- `KERNEL32!WaitForSingleObject` at `0x18008e5b1`
- `KERNEL32!CloseHandle` at `0x18008e5c8`
- `KERNEL32!CloseHandle` at `0x18008e5df`
- `KERNEL32!CloseHandle` at `0x18008e5c8`
- `KERNEL32!CloseHandle` at `0x18008e5df`
- `KERNEL32!GetLastError` at `0x18008e235`
- `KERNEL32!GetLastError` at `0x18008e235`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008e00b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008e045`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008e00b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008e045`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18008e296`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18008e296`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008e180`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008e180`
- `ntdll!NtClose` at `0x18008e582`
- `ntdll!NtClose` at `0x18008e582`

## string_xrefs

- `0x18008dc21`: `CCloudFileSystemApplier::CompareFileContent`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall CCloudFileSystemApplier::CompareFileContent(
        CCloudFileSystemApplier *this,
        struct IFspFile *a2,
        struct IFspFile *a3,
        int *a4)
{
  _DWORD *v8; // rax
  __int64 v9; // r12
  char v10; // cl
  __int16 v11; // ax
  int v12; // eax
  __int16 v13; // cx
  int v14; // eax
  __int64 v15; // r9
  PVOID *v16; // rcx
  BOOL v17; // edi
  CCloudFileSystemApplier *v18; // rcx
  CCloudFileSystemApplier *v19; // rcx
  BOOL v20; // eax
  int i; // ebx
  HANDLE EventW; // rax
  HANDLE v23; // rax
  struct IFspFile *v24; // rdx
  unsigned __int64 v25; // r14
  __int128 v26; // xmm6
  DWORD v27; // esi
  __int64 j; // rdx
  __int64 v29; // rcx
  int k; // ebx
  __int64 v31; // rcx
  signed int LastError; // eax
  int m; // edi
  DWORD v34; // eax
  size_t v35; // rbx
  __int64 n; // rbx
  HANDLE v37; // rcx
  HANDLE v38; // rdi
  HANDLE v39; // rcx
  unsigned int v40; // ebx
  int HaveDataStream; // [rsp+38h] [rbp-D0h] BYREF
  int v43; // [rsp+3Ch] [rbp-CCh]
  __int64 v44; // [rsp+40h] [rbp-C8h]
  const char *v45; // [rsp+48h] [rbp-C0h]
  __int64 v46; // [rsp+50h] [rbp-B8h]
  struct IFspStagedFile *v47; // [rsp+58h] [rbp-B0h] BYREF
  struct IFspStagedFile *v48; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int Size; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int Size_4; // [rsp+6Ch] [rbp-9Ch]
  _BOOL8 v51; // [rsp+70h] [rbp-98h] BYREF
  __int64 v52; // [rsp+78h] [rbp-90h]
  unsigned __int64 v53; // [rsp+80h] [rbp-88h] BYREF
  HANDLE hFile[2]; // [rsp+88h] [rbp-80h] BYREF
  HANDLE hHandle[2]; // [rsp+98h] [rbp-70h]
  __int64 v56; // [rsp+A8h] [rbp-60h] BYREF
  HANDLE hObject[2]; // [rsp+B0h] [rbp-58h]
  LPVOID lpBuffer[3]; // [rsp+C0h] [rbp-48h] BYREF
  _OWORD v59[4]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v60; // [rsp+118h] [rbp+10h] BYREF
  __int128 v61; // [rsp+120h] [rbp+18h]
  _OWORD v62[2]; // [rsp+130h] [rbp+28h] BYREF
  __int64 v63; // [rsp+150h] [rbp+48h]
  HANDLE Handles[2]; // [rsp+158h] [rbp+50h] BYREF
  HANDLE v65; // [rsp+168h] [rbp+60h]
  _DWORD v66[18]; // [rsp+170h] [rbp+68h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 100, &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = 0;
  if ( (v8[17] & 0x100) == 0 || (v10 = 1, *((_BYTE *)v8 + 65) < 6u) )
    v10 = 0;
  HaveDataStream = 0;
  v43 = 4351;
  LOBYTE(v44) = v10;
  v45 = "CCloudFileSystemApplier::CompareFileContent";
  v46 = 0;
  `eh vector constructor iterator'(
    lpBuffer,
    8u,
    2u,
    CEcsMemPtr<unsigned char,0>::CEcsMemPtr<unsigned char,0>,
    CEcsMemPtr<unsigned char,0>::~CEcsMemPtr<unsigned char,0>);
  *(_OWORD *)hFile = 0;
  *(_OWORD *)hHandle = 0;
  v52 = 0;
  memset_0(v59, 0, sizeof(v59));
  v60 = 0;
  v61 = 0;
  memset(v62, 0, sizeof(v62));
  v63 = 0;
  *(_OWORD *)hObject = 0;
  if ( a4 )
    *a4 = 0;
  v11 = 4368;
  if ( !a2 )
    goto LABEL_115;
  LOWORD(v43) = 4368;
  HaveDataStream = 0;
  v11 = 4369;
  if ( !a3 )
    goto LABEL_115;
  LOWORD(v43) = 4369;
  HaveDataStream = 0;
  v11 = 4370;
  if ( !a4 )
    goto LABEL_115;
  HaveDataStream = 0;
  LOWORD(v43) = 4370;
  Size = 0;
  v12 = (*(__int64 (__fastcall **)(struct IFspFile *, unsigned int *))(*(_QWORD *)a2 + 40LL))(a2, &Size);
  HaveDataStream = v12;
  v13 = 4376;
  if ( v12 < 0 )
  {
LABEL_14:
    HIWORD(v43) = v13;
    goto LABEL_117;
  }
  LOWORD(v43) = 4376;
  HaveDataStream = v12;
  v11 = 4377;
  if ( (Size & 0x10) != 0 )
    goto LABEL_115;
  HaveDataStream = 0;
  LOWORD(v43) = 4377;
  v14 = (*(__int64 (__fastcall **)(struct IFspFile *, unsigned int *))(*(_QWORD *)a3 + 40LL))(a3, &Size);
  HaveDataStream = v14;
  v13 = 4378;
  if ( v14 < 0 )
    goto LABEL_14;
  LOWORD(v43) = 4378;
  HaveDataStream = v14;
  v11 = 4379;
  if ( (Size & 0x10) != 0 )
  {
LABEL_115:
    HaveDataStream = -2147024809;
LABEL_116:
    HIWORD(v43) = v11;
    goto LABEL_117;
  }
  HaveDataStream = 0;
  LOWORD(v43) = 4379;
  v53 = 0;
  v56 = 0;
  HaveDataStream = (*(__int64 (__fastcall **)(struct IFspFile *, unsigned __int64 *))(*(_QWORD *)a2 + 64LL))(a2, &v53);
  v11 = 4385;
  if ( HaveDataStream < 0 )
    goto LABEL_116;
  LOWORD(v43) = 4385;
  HaveDataStream = (*(__int64 (__fastcall **)(struct IFspFile *, __int64 *))(*(_QWORD *)a3 + 64LL))(a3, &v56);
  v11 = 4386;
  if ( HaveDataStream < 0 )
    goto LABEL_116;
  LOWORD(v43) = 4386;
  if ( v53 == v56 )
  {
    if ( !v53 && !v56 )
    {
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          (unsigned int)(v53 + 102),
          &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids);
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
      v17 = 1;
      goto LABEL_105;
    }
    v51 = 0;
    Size = 0;
    ATL::CComQIPtr<IFspStagedFile,&__s_GUID const _GUID_c7d62de8_fe8c_4d03_940d_7726c6c5e3e9>::CComQIPtr<IFspStagedFile,&__s_GUID const _GUID_c7d62de8_fe8c_4d03_940d_7726c6c5e3e9>(
      &v48,
      (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))a2);
    ATL::CComQIPtr<IFspStagedFile,&__s_GUID const _GUID_c7d62de8_fe8c_4d03_940d_7726c6c5e3e9>::CComQIPtr<IFspStagedFile,&__s_GUID const _GUID_c7d62de8_fe8c_4d03_940d_7726c6c5e3e9>(
      &v47,
      (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))a3);
    if ( v48 )
    {
      HaveDataStream = CCloudFileSystemApplier::DoesHaveDataStream(v18, v48, (int *)&Size);
      if ( HaveDataStream < 0 )
      {
        HIWORD(v43) = 4408;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
        goto LABEL_39;
      }
      LOWORD(v43) = 4408;
      HIDWORD(v51) = Size == 0;
    }
    else
    {
      HaveDataStream = (*(__int64 (__fastcall **)(CCloudFileSystemApplier *, struct IFspFile *, char *))(*(_QWORD *)this + 112LL))(
                         this,
                         a2,
                         (char *)&v51 + 4);
      if ( HaveDataStream < 0 )
      {
        HIWORD(v43) = 4414;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
        goto LABEL_39;
      }
      LOWORD(v43) = 4414;
    }
    if ( v47 )
    {
      HaveDataStream = CCloudFileSystemApplier::DoesHaveDataStream(v19, v47, (int *)&Size);
      if ( HaveDataStream < 0 )
      {
        HIWORD(v43) = 4418;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
        goto LABEL_39;
      }
      LOWORD(v43) = 4418;
      v20 = Size == 0;
      LODWORD(v51) = v20;
    }
    else
    {
      HaveDataStream = (*(__int64 (__fastcall **)(CCloudFileSystemApplier *, struct IFspFile *, _BOOL8 *))(*(_QWORD *)this + 112LL))(
                         this,
                         a3,
                         &v51);
      if ( HaveDataStream < 0 )
      {
        HIWORD(v43) = 4424;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
        goto LABEL_39;
      }
      LOWORD(v43) = 4424;
      v20 = v51;
    }
    if ( !HIDWORD(v51) && !v20 )
    {
      for ( i = 0; i < 2; ++i )
      {
        EventW = CreateEventW(0, 1, 0, 0);
        hHandle[i] = EventW;
        if ( !EventW )
        {
          HaveDataStream = EcsGetLastFailureAsHRESULT();
          HIWORD(v43) = 4437;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
          goto LABEL_39;
        }
        HaveDataStream = 0;
        LOWORD(v43) = 4437;
        v23 = CreateEventW(0, 1, 0, 0);
        hObject[i] = v23;
        if ( !v23 )
        {
          HaveDataStream = EcsGetLastFailureAsHRESULT();
          HIWORD(v43) = 4440;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
          goto LABEL_39;
        }
        HaveDataStream = 0;
        LOWORD(v43) = 4440;
        *(_QWORD *)&v62[2 * i] = v23;
        v24 = a2;
        if ( i )
          v24 = a3;
        HaveDataStream = CCloudFileSystemApplier::OpenFileForCompare(
                           this,
                           v24,
                           (struct _OVERLAPPED *)&v60 + i,
                           (struct _REQUEST_OPLOCK_INPUT_BUFFER *)&v66[3 * i],
                           (struct _REQUEST_OPLOCK_OUTPUT_BUFFER *)&v66[6 * i + 6],
                           &hFile[i]);
        if ( HaveDataStream < 0 )
        {
          HIWORD(v43) = 4448;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
          goto LABEL_39;
        }
        LOWORD(v43) = 4448;
        HaveDataStream = CEcsMemPtr<unsigned short,0>::AllocBytes(&lpBuffer[i], 0x100000u);
        if ( HaveDataStream < 0 )
        {
          HIWORD(v43) = 4450;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
          goto LABEL_39;
        }
        LOWORD(v43) = 4450;
      }
      if ( CCloudFileSystemApplier::m_dwCompareFileDelayMs )
        Sleep(CCloudFileSystemApplier::m_dwCompareFileDelayMs);
      v17 = 1;
      v25 = v53;
      v26 = *(_OWORD *)hObject;
      while ( v17 && v25 )
      {
        v65 = 0;
        v27 = 0x100000;
        if ( v25 < 0x100000 )
          v27 = v25;
        *(_OWORD *)Handles = v26;
        for ( j = 0; j != 2; ++j )
        {
          v29 = 2 * j;
          v59[v29] = 0;
          v59[v29 + 1] = 0;
          *((_QWORD *)&v59[v29 + 1] + 1) = hHandle[j];
        }
        for ( k = 0; k < 2; ++k )
        {
          v31 = 2LL * k;
          LODWORD(v59[v31 + 1]) = v9;
          DWORD1(v59[v31 + 1]) = HIDWORD(v9);
          if ( !ReadFile(hFile[k], lpBuffer[k], v27, 0, (LPOVERLAPPED)&v59[v31]) )
          {
            LastError = GetLastError();
            if ( LastError != 997 )
            {
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              HaveDataStream = LastError;
              HIWORD(v43) = 4504;
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
              goto LABEL_39;
            }
            HaveDataStream = 0;
            LOWORD(v43) = 4504;
            *((_DWORD *)&v52 + k) = 1;
          }
        }
        for ( m = 0; m < 2; ++m )
        {
          v65 = hHandle[m];
          v34 = WaitForMultipleObjects(3u, Handles, 0, 0xFFFFFFFF);
          if ( v34 == -1 )
          {
            HaveDataStream = EcsGetLastFailureAsHRESULT();
            HIWORD(v43) = 4517;
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
            goto LABEL_39;
          }
          HaveDataStream = 0;
          LOWORD(v43) = 4517;
          if ( v34 != 2 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 104, &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids, v34);
            }
            *(&Size + m) = 0;
            HaveDataStream = -2134376425;
            HIWORD(v43) = 4532;
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
            goto LABEL_39;
          }
          *((_DWORD *)&v52 + m) = 0;
          HaveDataStream = 0;
          if ( !GetOverlappedResult(hFile[m], (LPOVERLAPPED)&v59[2 * m], &Size + m, 0) )
          {
            HaveDataStream = EcsGetLastFailureAsHRESULT();
            HIWORD(v43) = 4525;
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
            goto LABEL_39;
          }
          HaveDataStream = 0;
          LOWORD(v43) = 4525;
        }
        v35 = Size_4;
        if ( Size < Size_4 )
          v35 = Size;
        if ( !(_DWORD)v35 )
        {
          HaveDataStream = -2147418113;
          HIWORD(v43) = 4539;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
          goto LABEL_39;
        }
        HaveDataStream = 0;
        LOWORD(v43) = 4539;
        if ( (_DWORD)v35 != v27
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_lll(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            105,
            &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids,
            v27,
            Size,
            Size_4);
        }
        v17 = memcmp_0(lpBuffer[0], lpBuffer[1], v35) == 0;
        v25 -= v35;
        v9 += v35;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
      v16 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_105;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 103, &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids);
    }
    HaveDataStream = -2147467263;
    HIWORD(v43) = 4430;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
LABEL_39:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    goto LABEL_117;
  }
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 101, &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids);
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  v17 = 0;
LABEL_105:
  if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 17) & 0x100) != 0 && *((_BYTE *)v16 + 65) >= 4u )
  {
    LOBYTE(v15) = v17 ? 89 : 78;
    WPP_SF_c(v16[7], 106, &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids, v15);
  }
  *a4 = v17;
LABEL_117:
  for ( n = 0; n != 2; ++n )
  {
    v37 = hFile[n];
    if ( v37 )
    {
      CancelIo(v37);
      NtClose(hFile[n]);
      hFile[n] = 0;
      if ( *((_DWORD *)&v52 + n) )
        WaitForSingleObject(hHandle[n], 0xFFFFFFFF);
      v38 = hObject[n];
      WaitForSingleObject(v38, 0xFFFFFFFF);
    }
    else
    {
      v38 = hObject[n];
    }
    v39 = hHandle[n];
    if ( v39 )
    {
      CloseHandle(v39);
      hHandle[n] = 0;
    }
    if ( v38 )
    {
      CloseHandle(v38);
      hObject[n] = 0;
    }
  }
  v40 = HaveDataStream;
  `eh vector destructor iterator'(lpBuffer, 8u, 2u, CEcsMemPtr<unsigned char,0>::~CEcsMemPtr<unsigned char,0>);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&HaveDataStream);
  return v40;
}

```

## disassembly

```asm
0x18008db80  mov     rax, rsp
0x18008db83  push    rbp
0x18008db84  push    rbx
0x18008db85  push    rsi
0x18008db86  push    rdi
0x18008db87  push    r12
0x18008db89  push    r13
0x18008db8b  push    r14
0x18008db8d  push    r15
0x18008db8f  lea     rbp, [rax-118h]
0x18008db96  sub     rsp, 1D8h
0x18008db9d  movaps  xmmword ptr [rax-58h], xmm6
0x18008dba1  mov     rax, cs:__security_cookie
0x18008dba8  xor     rax, rsp
0x18008dbab  mov     [rbp+110h+var_60], rax
0x18008dbb2  mov     r13, r9
0x18008dbb5  mov     r14, r8
0x18008dbb8  mov     rsi, rdx
0x18008dbbb  mov     r15, rcx
0x18008dbbe  lea     rdi, WPP_GLOBAL_Control
0x18008dbc5  mov     ebx, 100h
0x18008dbca  mov     rax, cs:WPP_GLOBAL_Control
0x18008dbd1  cmp     rax, rdi
0x18008dbd4  jz      short loc_18008DBFD
0x18008dbd6  test    [rax+44h], ebx
0x18008dbd9  jz      short loc_18008DBFD
0x18008dbdb  cmp     byte ptr [rax+41h], 6
0x18008dbdf  jb      short loc_18008DBFD
0x18008dbe1  mov     edx, 64h ; 'd'
0x18008dbe6  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x18008dbed  mov     rcx, [rax+38h]
0x18008dbf1  call    WPP_SF_
0x18008dbf6  mov     rax, cs:WPP_GLOBAL_Control
0x18008dbfd  xor     r12d, r12d
0x18008dc00  test    [rax+44h], ebx
0x18008dc03  jz      short loc_18008DC0D
0x18008dc05  cmp     byte ptr [rax+41h], 6
0x18008dc09  mov     cl, 1
0x18008dc0b  jnb     short loc_18008DC10
0x18008dc0d  mov     cl, r12b
0x18008dc10  mov     [rsp+210h+var_1E0], r12d
0x18008dc15  mov     [rsp+210h+var_1DC], 10FFh
0x18008dc1d  mov     byte ptr [rsp+210h+var_1D8], cl
0x18008dc21  lea     rax, aCcloudfilesyst_15; "CCloudFileSystemApplier::CompareFileCon"...
0x18008dc28  mov     [rsp+210h+var_1D0], rax
0x18008dc2d  mov     [rsp+210h+var_1C8], r12
0x18008dc32  lea     rax, ??1?$CEcsMemPtr@E$0A@@@QEAA@XZ; CEcsMemPtr<uchar,0>::~CEcsMemPtr<uchar,0>(void)
0x18008dc39  mov     [rsp+210h+lpOverlapped], rax; void (*)(void *)
0x18008dc3e  lea     r9, ??0?$CEcsMemPtr@E$0A@@@QEAA@XZ; void (*)(void *)
0x18008dc45  mov     edx, 8; unsigned __int64
0x18008dc4a  lea     r8d, [rdx-6]; unsigned __int64
0x18008dc4e  lea     rcx, [rbp+110h+lpBuffer]; void *
0x18008dc52  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18008dc57  nop
0x18008dc58  xorps   xmm0, xmm0
0x18008dc5b  movups  xmmword ptr [rbp+110h+hFile], xmm0
0x18008dc5f  xorps   xmm1, xmm1
0x18008dc62  movups  xmmword ptr [rbp+110h+hHandle], xmm1
0x18008dc66  mov     [rsp+210h+var_1A0], r12
0x18008dc6b  xor     edx, edx; Val
0x18008dc6d  lea     r8d, [rdx+40h]; Size
0x18008dc71  lea     rcx, [rbp+110h+var_140]; void *
0x18008dc75  call    memset_0
0x18008dc7a  mov     [rbp+110h+var_100], r12
0x18008dc7e  xorps   xmm0, xmm0
0x18008dc81  xor     eax, eax
0x18008dc83  movups  [rbp+110h+var_F8], xmm0
0x18008dc87  movups  [rbp+110h+var_E8], xmm0
0x18008dc8b  movups  [rbp+110h+var_D8], xmm0
0x18008dc8f  mov     [rbp+110h+var_C8], rax
0x18008dc93  movups  xmmword ptr [rbp+110h+hObject], xmm0
0x18008dc97  test    r13, r13
0x18008dc9a  jz      short loc_18008DCA0
0x18008dc9c  mov     [r13+0], r12d
0x18008dca0  mov     eax, [rsp+210h+var_1E0]
0x18008dca4  mov     [rsp+210h+var_1E0], eax
0x18008dca8  mov     eax, 1110h
0x18008dcad  test    rsi, rsi
0x18008dcb0  jz      loc_18008E55E
0x18008dcb6  mov     [rsp+210h+var_1E0], r12d
0x18008dcbb  mov     word ptr [rsp+210h+var_1DC], ax
0x18008dcc0  mov     [rsp+210h+var_1E0], r12d
0x18008dcc5  mov     eax, 1111h
0x18008dcca  test    r14, r14
0x18008dccd  jz      loc_18008E55E
0x18008dcd3  mov     [rsp+210h+var_1E0], r12d
0x18008dcd8  mov     word ptr [rsp+210h+var_1DC], ax
0x18008dcdd  mov     [rsp+210h+var_1E0], r12d
0x18008dce2  mov     eax, 1112h
0x18008dce7  test    r13, r13
0x18008dcea  jz      loc_18008E55E
0x18008dcf0  mov     [rsp+210h+var_1E0], r12d
0x18008dcf5  mov     word ptr [rsp+210h+var_1DC], ax
0x18008dcfa  mov     dword ptr [rsp+210h+Size], r12d
0x18008dcff  mov     rax, [rsi]
0x18008dd02  lea     rdx, [rsp+210h+Size]
0x18008dd07  mov     rcx, rsi
0x18008dd0a  mov     rax, [rax+28h]
0x18008dd0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dd13  mov     [rsp+210h+var_1E0], eax
0x18008dd17  mov     [rsp+210h+var_1E0], eax
0x18008dd1b  mov     ecx, 1118h
0x18008dd20  test    eax, eax
0x18008dd22  jns     short loc_18008DD2E
0x18008dd24  mov     word ptr [rsp+210h+var_1DC+2], cx
0x18008dd29  jmp     loc_18008E56B
0x18008dd2e  mov     word ptr [rsp+210h+var_1DC], cx
0x18008dd33  mov     [rsp+210h+var_1E0], eax
0x18008dd37  mov     eax, 1119h
0x18008dd3c  test    byte ptr [rsp+210h+Size], 10h
0x18008dd41  jnz     loc_18008E55E
0x18008dd47  mov     [rsp+210h+var_1E0], r12d
0x18008dd4c  mov     word ptr [rsp+210h+var_1DC], ax
0x18008dd51  mov     rax, [r14]
0x18008dd54  lea     rdx, [rsp+210h+Size]
0x18008dd59  mov     rcx, r14
0x18008dd5c  mov     rax, [rax+28h]
0x18008dd60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dd65  mov     [rsp+210h+var_1E0], eax
0x18008dd69  mov     [rsp+210h+var_1E0], eax
0x18008dd6d  mov     ecx, 111Ah
0x18008dd72  test    eax, eax
0x18008dd74  js      short loc_18008DD24
0x18008dd76  mov     word ptr [rsp+210h+var_1DC], cx
0x18008dd7b  mov     [rsp+210h+var_1E0], eax
0x18008dd7f  lea     eax, [rcx+1]
0x18008dd82  test    byte ptr [rsp+210h+Size], 10h
0x18008dd87  jnz     loc_18008E55E
0x18008dd8d  mov     [rsp+210h+var_1E0], r12d
0x18008dd92  mov     word ptr [rsp+210h+var_1DC], ax
0x18008dd97  mov     [rsp+210h+var_198], r12
0x18008dd9c  mov     [rbp+110h+var_170], r12
0x18008dda0  mov     rax, [rsi]
0x18008dda3  lea     rdx, [rsp+210h+var_198]
0x18008dda8  mov     rcx, rsi
0x18008ddab  mov     rax, [rax+40h]
0x18008ddaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ddb4  mov     [rsp+210h+var_1E0], eax
0x18008ddb8  mov     [rsp+210h+var_1E0], eax
0x18008ddbc  test    eax, eax
0x18008ddbe  mov     eax, 1121h
0x18008ddc3  js      loc_18008E566
0x18008ddc9  mov     word ptr [rsp+210h+var_1DC], ax
0x18008ddce  mov     rax, [r14]
0x18008ddd1  lea     rdx, [rbp+110h+var_170]
0x18008ddd5  mov     rcx, r14
0x18008ddd8  mov     rax, [rax+40h]
0x18008dddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dde1  mov     [rsp+210h+var_1E0], eax
0x18008dde5  mov     [rsp+210h+var_1E0], eax
0x18008dde9  test    eax, eax
0x18008ddeb  mov     eax, 1122h
0x18008ddf0  js      loc_18008E566
0x18008ddf6  mov     word ptr [rsp+210h+var_1DC], ax
0x18008ddfb  mov     rax, [rsp+210h+var_198]
0x18008de00  mov     rcx, [rbp+110h+var_170]
0x18008de04  cmp     rax, rcx
0x18008de07  jz      short loc_18008DE44
0x18008de09  mov     rcx, cs:WPP_GLOBAL_Control
0x18008de10  cmp     rcx, rdi
0x18008de13  jz      short loc_18008DE3C
0x18008de15  test    [rcx+44h], ebx
0x18008de18  jz      short loc_18008DE3C
0x18008de1a  cmp     byte ptr [rcx+41h], 4
0x18008de1e  jb      short loc_18008DE3C
0x18008de20  mov     edx, 65h ; 'e'
0x18008de25  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x18008de2c  mov     rcx, [rcx+38h]
0x18008de30  call    WPP_SF_
0x18008de35  mov     rcx, cs:WPP_GLOBAL_Control
0x18008de3c  mov     edi, r12d
0x18008de3f  jmp     loc_18008E4CA
0x18008de44  test    rax, rax
0x18008de47  jnz     short loc_18008DE89
0x18008de49  test    rcx, rcx
0x18008de4c  jnz     short loc_18008DE89
0x18008de4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008de55  cmp     rcx, rdi
0x18008de58  jz      short loc_18008DE7F
0x18008de5a  test    [rcx+44h], ebx
0x18008de5d  jz      short loc_18008DE7F
0x18008de5f  cmp     byte ptr [rcx+41h], 4
0x18008de63  jb      short loc_18008DE7F
0x18008de65  lea     edx, [rax+66h]
0x18008de68  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x18008de6f  mov     rcx, [rcx+38h]
0x18008de73  call    WPP_SF_
0x18008de78  mov     rcx, cs:WPP_GLOBAL_Control
0x18008de7f  mov     edi, 1
0x18008de84  jmp     loc_18008E4CA
0x18008de89  mov     dword ptr [rsp+210h+var_1A8+4], r12d
0x18008de8e  mov     dword ptr [rsp+210h+var_1A8], r12d
0x18008de93  mov     dword ptr [rsp+210h+Size], r12d
0x18008de98  mov     rdx, rsi
0x18008de9b  lea     rcx, [rsp+210h+var_1B8]
0x18008dea0  call    ??0?$CComQIPtr@UIFspStagedFile@@$1?_GUID_c7d62de8_fe8c_4d03_940d_7726c6c5e3e9@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IFspStagedFile,&__s_GUID const _GUID_c7d62de8_fe8c_4d03_940d_7726c6c5e3e9>::CComQIPtr<IFspStagedFile,&__s_GUID const _GUID_c7d62de8_fe8c_4d03_940d_7726c6c5e3e9>(IUnknown *)
0x18008dea5  nop
0x18008dea6  mov     rdx, r14
0x18008dea9  lea     rcx, [rsp+210h+var_1C0]
0x18008deae  call    ??0?$CComQIPtr@UIFspStagedFile@@$1?_GUID_c7d62de8_fe8c_4d03_940d_7726c6c5e3e9@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IFspStagedFile,&__s_GUID const _GUID_c7d62de8_fe8c_4d03_940d_7726c6c5e3e9>::CComQIPtr<IFspStagedFile,&__s_GUID const _GUID_c7d62de8_fe8c_4d03_940d_7726c6c5e3e9>(IUnknown *)
0x18008deb3  nop
0x18008deb4  mov     rdx, [rsp+210h+var_1B8]; struct IFspStagedFile *
0x18008deb9  test    rdx, rdx
0x18008debc  jnz     short loc_18008DEFF
0x18008debe  mov     rax, [r15]
0x18008dec1  lea     r8, [rsp+210h+var_1A8+4]
0x18008dec6  mov     rdx, rsi
0x18008dec9  mov     rcx, r15
0x18008decc  mov     rax, [rax+70h]
0x18008ded0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ded5  mov     [rsp+210h+var_1E0], eax
0x18008ded9  mov     [rsp+210h+var_1E0], eax
0x18008dedd  test    eax, eax
0x18008dedf  mov     eax, 113Eh
0x18008dee4  jns     short loc_18008DEF8
0x18008dee6  mov     word ptr [rsp+210h+var_1DC+2], ax
0x18008deeb  lea     rcx, [rsp+210h+var_1C0]
0x18008def0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18008def5  nop
0x18008def6  jmp     short loc_18008DF2A
0x18008def8  mov     word ptr [rsp+210h+var_1DC], ax
0x18008defd  jmp     short loc_18008DF4D
0x18008deff  lea     r8, [rsp+210h+Size]; int *
0x18008df04  call    ?DoesHaveDataStream@CCloudFileSystemApplier@@AEAAJPEAUIFspStagedFile@@PEAH@Z; CCloudFileSystemApplier::DoesHaveDataStream(IFspStagedFile *,int *)
0x18008df09  mov     [rsp+210h+var_1E0], eax
0x18008df0d  mov     [rsp+210h+var_1E0], eax
0x18008df11  test    eax, eax
0x18008df13  mov     eax, 1138h
0x18008df18  jns     short loc_18008DF39
0x18008df1a  mov     word ptr [rsp+210h+var_1DC+2], ax
0x18008df1f  lea     rcx, [rsp+210h+var_1C0]
0x18008df24  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18008df29  nop
0x18008df2a  lea     rcx, [rsp+210h+var_1B8]
0x18008df2f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18008df34  jmp     loc_18008E56B
0x18008df39  mov     word ptr [rsp+210h+var_1DC], ax
0x18008df3e  mov     eax, r12d
0x18008df41  cmp     dword ptr [rsp+210h+Size], r12d
0x18008df46  setz    al
0x18008df49  mov     dword ptr [rsp+210h+var_1A8+4], eax
0x18008df4d  mov     rdx, [rsp+210h+var_1C0]; struct IFspStagedFile *
0x18008df52  test    rdx, rdx
0x18008df55  jnz     short loc_18008DF9C
0x18008df57  mov     rax, [r15]
0x18008df5a  lea     r8, [rsp+210h+var_1A8]
0x18008df5f  mov     rdx, r14
0x18008df62  mov     rcx, r15
0x18008df65  mov     rax, [rax+70h]
0x18008df69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008df6e  mov     [rsp+210h+var_1E0], eax
0x18008df72  mov     [rsp+210h+var_1E0], eax
0x18008df76  test    eax, eax
0x18008df78  mov     eax, 1148h
0x18008df7d  jns     short loc_18008DF91
0x18008df7f  mov     word ptr [rsp+210h+var_1DC+2], ax
0x18008df84  lea     rcx, [rsp+210h+var_1C0]
0x18008df89  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18008df8e  nop
0x18008df8f  jmp     short loc_18008DF2A
0x18008df91  mov     word ptr [rsp+210h+var_1DC], ax
0x18008df96  mov     eax, dword ptr [rsp+210h+var_1A8]
0x18008df9a  jmp     short loc_18008DFE0
0x18008df9c  lea     r8, [rsp+210h+Size]; int *
0x18008dfa1  call    ?DoesHaveDataStream@CCloudFileSystemApplier@@AEAAJPEAUIFspStagedFile@@PEAH@Z; CCloudFileSystemApplier::DoesHaveDataStream(IFspStagedFile *,int *)
0x18008dfa6  mov     [rsp+210h+var_1E0], eax
0x18008dfaa  mov     [rsp+210h+var_1E0], eax
0x18008dfae  test    eax, eax
0x18008dfb0  mov     eax, 1142h
0x18008dfb5  jns     short loc_18008DFCC
0x18008dfb7  mov     word ptr [rsp+210h+var_1DC+2], ax
0x18008dfbc  lea     rcx, [rsp+210h+var_1C0]
0x18008dfc1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18008dfc6  nop
0x18008dfc7  jmp     loc_18008DF2A
0x18008dfcc  mov     word ptr [rsp+210h+var_1DC], ax
0x18008dfd1  mov     eax, r12d
0x18008dfd4  cmp     dword ptr [rsp+210h+Size], r12d
0x18008dfd9  setz    al
0x18008dfdc  mov     dword ptr [rsp+210h+var_1A8], eax
0x18008dfe0  cmp     dword ptr [rsp+210h+var_1A8+4], r12d
0x18008dfe5  jnz     loc_18008E50B
0x18008dfeb  test    eax, eax
0x18008dfed  jnz     loc_18008E50B
0x18008dff3  mov     ebx, r12d
0x18008dff6  cmp     ebx, 2
0x18008dff9  jge     loc_18008E176
0x18008dfff  xor     r9d, r9d; lpName
0x18008e002  xor     r8d, r8d; bInitialState
0x18008e005  lea     edx, [r9+1]; bManualReset
0x18008e009  xor     ecx, ecx; lpEventAttributes
0x18008e00b  call    cs:__imp_CreateEventW
0x18008e011  movsxd  rdi, ebx
0x18008e014  mov     [rbp+rdi*8+110h+hHandle], rax
0x18008e019  mov     ecx, [rsp+210h+var_1E0]
0x18008e01d  mov     [rsp+210h+var_1E0], ecx
0x18008e021  test    rax, rax
0x18008e024  jz      loc_18008E153
0x18008e02a  mov     [rsp+210h+var_1E0], r12d
0x18008e02f  mov     eax, 1155h
  ... truncated ...
```
