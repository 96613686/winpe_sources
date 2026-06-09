# UpdateReserveManager::UntagFilesInReserve(_STORAGE_RESERVE_ID)

- ea: `0x180020778`
- end: `0x180020c65`
- name: `?UntagFilesInReserve@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@@Z`
- size: `1261`
- prototype: `__int64 __fastcall(UpdateReserveManager *this, unsigned int)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update`

## callers

- `0x180014960`
- `0x1800192e0`
- `0x18001b8f0`

## callees

- `0x180003870`
- `0x180003c84`
- `0x1800044e0`
- `0x180008140`
- `0x18000fafc`
- `0x180010ea4`
- `0x180010fe0`
- `0x180015ad0`
- `0x18001ac20`
- `0x18001e6c8`
- `0x180020778`
- `0x180021e80`
- `0x1800248e0`
- `0x180033010`

## import_xrefs

- `ntdll!NtClose` at `0x180020a12`
- `ntdll!NtClose` at `0x180020b4c`
- `ntdll!NtClose` at `0x180020bea`
- `ntdll!NtClose` at `0x180020a12`
- `ntdll!NtClose` at `0x180020b4c`
- `ntdll!NtClose` at `0x180020bea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002097b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002097b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c3d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800208cf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800208cf`
- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x18002095f`
- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x1800209c1`
- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x18002095f`
- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x1800209c1`

## string_xrefs

- `0x180020a55`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180020b93`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180020a60`: `UpdateReserveManager::UntagFilesInReserve`
- `0x180020b9e`: `UpdateReserveManager::UntagFilesInReserve`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::UntagFilesInReserve(UpdateReserveManager *this, unsigned int a2)
{
  __int64 result; // rax
  NTSTATUS v5; // eax
  DWORD LastError; // edi
  signed int v7; // esi
  unsigned __int64 v8; // rdx
  _DWORD *v9; // r14
  unsigned int *lpOutBuffer; // rbx
  DWORD nOutBufferSize; // edi
  char v12; // al
  LARGE_INTEGER *v13; // r13
  unsigned int v14; // r12d
  char IsEnabled; // al
  void *v16; // rcx
  char *v17; // rdi
  signed int v18; // eax
  int v19; // eax
  int v20; // r12d
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  DWORD v26; // esi
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  unsigned int v29; // [rsp+48h] [rbp-89h]
  DWORD v30; // [rsp+4Ch] [rbp-85h]
  int v32; // [rsp+54h] [rbp-7Dh]
  _QWORD v33[2]; // [rsp+68h] [rbp-69h] BYREF
  _QWORD v34[5]; // [rsp+78h] [rbp-59h] BYREF
  DWORD BytesReturned; // [rsp+A0h] [rbp-31h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-29h] BYREF
  char v37; // [rsp+B0h] [rbp-21h]
  FILE_ID_DESCRIPTOR FileId; // [rsp+B8h] [rbp-19h] BYREF
  const char *v39; // [rsp+D0h] [rbp-1h]
  _DWORD v40[4]; // [rsp+D8h] [rbp+7h] BYREF

  v34[4] = -2;
  result = UpdateReserveManager::EnsureNotInSafeMode(this);
  if ( (int)result < 0 )
    return result;
  v40[0] = 28;
  v40[1] = 17;
  v40[2] = 18;
  v36 = 0;
  v37 = 0;
  v33[0] = v40;
  v33[1] = 3;
  v5 = RtlSystemUtil::PrivilegeAcquisition::Acquire(&v36, v33);
  if ( v5 < 0 )
  {
    LastError = ConvertNtStatusToHResult(v5);
    goto LABEL_47;
  }
  v7 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
    && a2 == 1 )
  {
    v7 = (*(__int64 (__fastcall **)(UpdateReserveManager *))(*(_QWORD *)this + 176LL))(this);
  }
  v32 = v7;
  v33[0] = 0;
  v9 = operator new[](0x14u);
  v33[0] = v9;
  v9[1] = 103;
  v9[2] = 3;
  *v9 = 1;
  v9[4] = a2;
  lpOutBuffer = 0;
  nOutBufferSize = 0x2000000;
LABEL_8:
  v12 = 1;
  v30 = nOutBufferSize;
  while ( 1 )
  {
    if ( v12 )
    {
      if ( lpOutBuffer )
        operator delete(lpOutBuffer, v8);
      lpOutBuffer = (unsigned int *)operator new[](nOutBufferSize);
    }
    BytesReturned = 0;
    if ( !DeviceIoControl(*((HANDLE *)this + 16), 0x90277u, v9, 0x14u, lpOutBuffer, nOutBufferSize, &BytesReturned, 0) )
    {
      LastError = GetLastError();
      if ( LastError != 122 )
      {
        if ( LastError == 38 )
        {
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
            || v7 >= 0 )
          {
            if ( lpOutBuffer )
              operator delete(lpOutBuffer, v22);
            operator delete(v9, v22);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v36);
            return 0;
          }
          CUpdateReserveManagerDiagnostics::ReportUntagFilesInReserveFailure((const char *)this + 1200, a2, v7, v32);
          if ( lpOutBuffer )
            operator delete(lpOutBuffer, v23);
          operator delete(v9, v23);
          LastError = v7;
        }
        else
        {
          if ( !LastError )
            INTERNAL_ERROR_ACTION(-1073741595);
          *(_QWORD *)&FileId.dwSize = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          FileId.FileId.QuadPart = (LONGLONG)"UpdateReserveManager::UntagFilesInReserve";
          *(_QWORD *)FileId.ObjectId.Data4 = 3000;
          v39 = "LastError";
          if ( (int)LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          RtlReportErrorOrigination(&FileId, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, LastError);
          if ( lpOutBuffer )
            operator delete(lpOutBuffer, v21);
          operator delete(v9, v21);
        }
LABEL_47:
        RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v36);
        return LastError;
      }
      nOutBufferSize = BytesReturned;
      goto LABEL_8;
    }
    v13 = (LARGE_INTEGER *)((char *)lpOutBuffer + lpOutBuffer[1]);
    v14 = 0;
    v29 = 0;
    if ( *lpOutBuffer )
      break;
LABEL_34:
    v12 = 0;
    v9[1] &= ~1u;
  }
  while ( 1 )
  {
    FileId.8 = 0;
    *(_QWORD *)&FileId.dwSize = 24;
    FileId.FileId = v13[2];
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl);
    v16 = (void *)*((_QWORD *)this + 16);
    if ( IsEnabled )
    {
      v17 = (char *)OpenFileById(v16, &FileId, 0x100u, 7u, 0, 0x2000000u);
      if ( ((unsigned __int64)(v17 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        goto LABEL_23;
      if ( v7 >= 0 )
      {
        v18 = GetLastError();
        v7 = v18;
        if ( v18 > 0 )
          v7 = (unsigned __int16)v18 | 0x80070000;
      }
      if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
LABEL_23:
        v19 = UpdateReserveManager::MoveFileBetweenReserveAreas(this, 6u, 0, v17);
        if ( v19 < 0 && v7 >= 0 )
          v7 = v19;
      }
      goto LABEL_29;
    }
    v17 = (char *)OpenFileById(v16, &FileId, 0x100u, 7u, 0, 0x2000000u);
    if ( (unsigned __int64)(v17 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      break;
    v20 = UpdateReserveManager::MoveFileBetweenReserveAreas(this, 6u, 0, v17);
    if ( v20 < 0 )
    {
      CUpdateReserveManagerDiagnostics::ReportUntagFilesInReserveFailure((const char *)this + 1200, a2, v20, 0);
      if ( NtClose(v17) < 0 )
        __fastfail(7u);
      operator delete(lpOutBuffer, v24);
      operator delete(v9, v25);
      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v36);
      return (unsigned int)v20;
    }
    v14 = v29;
LABEL_29:
    v13 = (LARGE_INTEGER *)((char *)v13 + (unsigned int)v13->HighPart);
    if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v17) < 0 )
      __fastfail(7u);
    v29 = ++v14;
    if ( v14 >= *lpOutBuffer )
    {
      nOutBufferSize = v30;
      goto LABEL_34;
    }
  }
  if ( GetLastError() )
  {
    v26 = GetLastError();
    if ( !v26 )
      INTERNAL_ERROR_ACTION(-1073741595);
  }
  else
  {
    v26 = 14077;
  }
  v34[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
  v34[1] = "UpdateReserveManager::UntagFilesInReserve";
  v34[2] = 3058;
  v34[3] = "FileHandle.IsValid()";
  if ( (int)v26 > 0 )
    v26 = (unsigned __int16)v26 | 0x80070000;
  RtlReportErrorOrigination(v34, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v26);
  if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v17) < 0 )
    __fastfail(7u);
  operator delete(lpOutBuffer, v27);
  operator delete(v9, v28);
  RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v36);
  return v26;
}

```

## disassembly

```asm
0x180020778  mov     rax, rsp
0x18002077b  push    rbp
0x18002077c  push    rsi
0x18002077d  push    rdi
0x18002077e  push    r12
0x180020780  push    r13
0x180020782  push    r14
0x180020784  push    r15
0x180020786  lea     rbp, [rax-5Fh]
0x18002078a  sub     rsp, 0F0h
0x180020791  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x180020799  mov     [rax+18h], rbx
0x18002079d  mov     rax, cs:__security_cookie
0x1800207a4  xor     rax, rsp
0x1800207a7  mov     [rbp+57h+var_40], rax
0x1800207ab  mov     r12d, edx
0x1800207ae  mov     [rsp+48h], edx
0x1800207b2  mov     r15, rcx
0x1800207b5  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x1800207ba  xor     r13d, r13d
0x1800207bd  test    eax, eax
0x1800207bf  js      loc_180020C16
0x1800207c5  mov     [rbp+57h+var_50], 1Ch
0x1800207cc  mov     [rbp+57h+var_4C], 11h
0x1800207d3  mov     [rbp+57h+var_48], 12h
0x1800207da  mov     [rbp+57h+var_80], r13
0x1800207de  mov     [rbp+57h+var_78], r13b
0x1800207e2  lea     rax, [rbp+57h+var_50]
0x1800207e6  mov     [rbp+57h+var_C0], rax
0x1800207ea  lea     ebx, [r13+3]
0x1800207ee  mov     [rbp+57h+var_B8], rbx
0x1800207f2  lea     rdx, [rbp+57h+var_C0]
0x1800207f6  lea     rcx, [rbp+57h+var_80]
0x1800207fa  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x1800207ff  test    eax, eax
0x180020801  jns     short loc_180020811
0x180020803  mov     ecx, eax; Status
0x180020805  call    ConvertNtStatusToHResult
0x18002080a  mov     edi, eax
0x18002080c  jmp     loc_180020AFB
0x180020811  mov     esi, r13d
0x180020814  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18002081b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180020820  test    al, al
0x180020822  jz      short loc_18002083E
0x180020824  cmp     r12d, 1
0x180020828  jnz     short loc_18002083E
0x18002082a  mov     rax, [r15]
0x18002082d  mov     rcx, r15
0x180020830  mov     rax, [rax+0B0h]
0x180020837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002083c  mov     esi, eax
0x18002083e  mov     [rbp+57h+var_D4], esi
0x180020841  mov     [rbp+57h+var_C0], r13
0x180020845  mov     ecx, 14h; unsigned __int64
0x18002084a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002084f  mov     r14, rax
0x180020852  mov     [rbp+57h+var_C0], rax
0x180020856  mov     dword ptr [rax+4], 67h ; 'g'
0x18002085d  mov     [rax+8], ebx
0x180020860  mov     dword ptr [rax], 1
0x180020866  mov     [rax+10h], r12d
0x18002086a  mov     rbx, r13
0x18002086d  mov     [rbp+57h+var_D0], rbx
0x180020871  mov     edi, 2000000h
0x180020876  mov     al, 1
0x180020878  mov     [rsp+44h], edi
0x18002087c  test    al, al
0x18002087e  jz      short loc_18002089F
0x180020880  test    rbx, rbx
0x180020883  jz      short loc_180020891
0x180020885  mov     rcx, rbx; void *
0x180020888  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002088d  mov     [rbp+57h+var_D0], r13
0x180020891  mov     ecx, edi; unsigned __int64
0x180020893  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180020898  mov     rbx, rax
0x18002089b  mov     [rbp+57h+var_D0], rax
0x18002089f  mov     [rbp+57h+BytesReturned], r13d
0x1800208a3  mov     [rsp+120h+lpOverlapped], r13; lpOverlapped
0x1800208a8  lea     rax, [rbp+57h+BytesReturned]
0x1800208ac  mov     [rsp+120h+lpBytesReturned], rax; lpBytesReturned
0x1800208b1  mov     [rsp+120h+nOutBufferSize], edi; nOutBufferSize
0x1800208b5  mov     [rsp+120h+lpOutBuffer], rbx; lpOutBuffer
0x1800208ba  mov     r9d, 14h; nInBufferSize
0x1800208c0  mov     r8, r14; lpInBuffer
0x1800208c3  mov     edx, 90277h; dwIoControlCode
0x1800208c8  mov     rcx, [r15+80h]; hDevice
0x1800208cf  call    cs:__imp_DeviceIoControl
0x1800208d5  test    eax, eax
0x1800208d7  jnz     short loc_1800208EF
0x1800208d9  call    cs:__imp_GetLastError
0x1800208df  mov     edi, eax
0x1800208e1  cmp     eax, 7Ah ; 'z'
0x1800208e4  jnz     loc_180020A48
0x1800208ea  mov     edi, [rbp+57h+BytesReturned]
0x1800208ed  jmp     short loc_180020876
0x1800208ef  mov     r13d, [rbx+4]
0x1800208f3  add     r13, rbx
0x1800208f6  xor     r12d, r12d
0x1800208f9  mov     [rsp+120h+var_E0], r12d
0x1800208fe  cmp     [rbx], r12d
0x180020901  jbe     loc_180020A38
0x180020907  xorps   xmm0, xmm0
0x18002090a  movdqu  xmmword ptr [rbp+57h+FileId.8], xmm0
0x18002090f  mov     qword ptr [rbp+57h+FileId.dwSize], 18h
0x180020917  mov     rax, [r13+10h]
0x18002091b  mov     qword ptr [rbp+57h+FileId.8], rax
0x18002091f  mov     [rbp+57h+var_C8], 0
0x180020927  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18002092e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180020933  mov     [rsp+120h+nOutBufferSize], 2000000h; dwFlagsAndAttributes
0x18002093b  mov     r8d, 100h; dwDesiredAccess
0x180020941  lea     rdx, [rbp+57h+FileId]; lpFileId
0x180020945  mov     rcx, [r15+80h]; hVolumeHint
0x18002094c  mov     [rsp+120h+lpOutBuffer], 0; lpSecurityAttributes
0x180020955  test    al, al
0x180020957  jz      short loc_1800209B8
0x180020959  mov     r9d, 7; dwShareMode
0x18002095f  call    cs:__imp_OpenFileById
0x180020965  mov     rdi, rax
0x180020968  mov     [rbp+57h+var_C8], rax
0x18002096c  inc     rax
0x18002096f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180020975  jnz     short loc_18002099A
0x180020977  test    esi, esi
0x180020979  js      short loc_180020990
0x18002097b  call    cs:__imp_GetLastError
0x180020981  mov     esi, eax
0x180020983  test    eax, eax
0x180020985  jle     short loc_180020990
0x180020987  movzx   esi, ax
0x18002098a  or      esi, 80070000h
0x180020990  lea     rax, [rdi-1]
0x180020994  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020998  ja      short loc_1800209FE
0x18002099a  mov     r9, rdi
0x18002099d  xor     r8d, r8d
0x1800209a0  lea     edx, [r8+6]
0x1800209a4  mov     rcx, r15
0x1800209a7  call    ?MoveFileBetweenReserveAreas@UpdateReserveManager@@UEAAJW4MoveFileBetweenReserveAreasFlags@IUpdateReserveManager@@W4ScenarioId@3@QEAX@Z; UpdateReserveManager::MoveFileBetweenReserveAreas(IUpdateReserveManager::MoveFileBetweenReserveAreasFlags,IUpdateReserveManager::ScenarioId,void * const)
0x1800209ac  test    eax, eax
0x1800209ae  jns     short loc_1800209FE
0x1800209b0  test    esi, esi
0x1800209b2  js      short loc_1800209FE
0x1800209b4  mov     esi, eax
0x1800209b6  jmp     short loc_1800209FE
0x1800209b8  mov     r12d, 7
0x1800209be  mov     r9d, r12d; dwShareMode
0x1800209c1  call    cs:__imp_OpenFileById
0x1800209c7  mov     rdi, rax
0x1800209ca  mov     [rbp+57h+var_C8], rax
0x1800209ce  dec     rax
0x1800209d1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800209d5  ja      loc_180020B80
0x1800209db  mov     r9, rdi
0x1800209de  xor     r8d, r8d
0x1800209e1  lea     edx, [r12-1]
0x1800209e6  mov     rcx, r15
0x1800209e9  call    ?MoveFileBetweenReserveAreas@UpdateReserveManager@@UEAAJW4MoveFileBetweenReserveAreasFlags@IUpdateReserveManager@@W4ScenarioId@3@QEAX@Z; UpdateReserveManager::MoveFileBetweenReserveAreas(IUpdateReserveManager::MoveFileBetweenReserveAreasFlags,IUpdateReserveManager::ScenarioId,void * const)
0x1800209ee  mov     r12d, eax
0x1800209f1  test    eax, eax
0x1800209f3  js      loc_180020B32
0x1800209f9  mov     r12d, [rsp+120h+var_E0]
0x1800209fe  mov     eax, [r13+4]
0x180020a02  add     r13, rax
0x180020a05  lea     rax, [rdi-1]
0x180020a09  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020a0d  ja      short loc_180020A23
0x180020a0f  mov     rcx, rdi; Handle
0x180020a12  call    cs:__imp_NtClose
0x180020a18  test    eax, eax
0x180020a1a  jns     short loc_180020A23
0x180020a1c  mov     ecx, 7
0x180020a21  int     29h; Win8: RtlFailFast(ecx)
0x180020a23  inc     r12d
0x180020a26  mov     [rsp+120h+var_E0], r12d
0x180020a2b  cmp     r12d, [rbx]
0x180020a2e  jb      loc_180020907
0x180020a34  mov     edi, [rsp+44h]
0x180020a38  xor     r13d, r13d
0x180020a3b  mov     al, r13b
0x180020a3e  and     dword ptr [r14+4], 0FFFFFFFEh
0x180020a43  jmp     loc_18002087C
0x180020a48  cmp     edi, 26h ; '&'
0x180020a4b  jz      short loc_180020AB7
0x180020a4d  test    edi, edi
0x180020a4f  jz      loc_180020C4F
0x180020a55  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180020a5c  mov     qword ptr [rbp+57h+FileId.dwSize], rax
0x180020a60  lea     rax, aUpdatereservem_11; "UpdateReserveManager::UntagFilesInReser"...
0x180020a67  mov     qword ptr [rbp+57h+FileId.8], rax
0x180020a6b  mov     qword ptr [rbp+57h+FileId.8+8], 0BB8h
0x180020a73  lea     rax, aLasterror; "LastError"
0x180020a7a  mov     [rbp+57h+var_58], rax
0x180020a7e  test    edi, edi
0x180020a80  jle     short loc_180020A8B
0x180020a82  movzx   edi, di
0x180020a85  or      edi, 80070000h
0x180020a8b  mov     r8d, edi
0x180020a8e  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180020a95  lea     rcx, [rbp+57h+FileId]
0x180020a99  call    RtlReportErrorOrigination
0x180020a9e  nop
0x180020a9f  test    rbx, rbx
0x180020aa2  jz      short loc_180020AAD
0x180020aa4  mov     rcx, rbx; void *
0x180020aa7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020aac  nop
0x180020aad  mov     rcx, r14; void *
0x180020ab0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020ab5  jmp     short loc_180020AFB
0x180020ab7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180020abe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180020ac3  test    al, al
0x180020ac5  jz      short loc_180020B0B
0x180020ac7  test    esi, esi
0x180020ac9  jns     short loc_180020B0B
0x180020acb  lea     rcx, [r15+4B0h]; char *
0x180020ad2  mov     r9d, [rbp+57h+var_D4]; int
0x180020ad6  mov     r8d, esi; int
0x180020ad9  mov     edx, [rsp+48h]; unsigned int
0x180020add  call    ?ReportUntagFilesInReserveFailure@CUpdateReserveManagerDiagnostics@@SAXPEBDKJJ@Z; CUpdateReserveManagerDiagnostics::ReportUntagFilesInReserveFailure(char const *,ulong,long,long)
0x180020ae2  nop
0x180020ae3  test    rbx, rbx
0x180020ae6  jz      short loc_180020AF1
0x180020ae8  mov     rcx, rbx; void *
0x180020aeb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020af0  nop
0x180020af1  mov     rcx, r14; void *
0x180020af4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020af9  mov     edi, esi
0x180020afb  lea     rcx, [rbp+57h+var_80]; this
0x180020aff  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180020b04  mov     eax, edi
0x180020b06  jmp     loc_180020C16
0x180020b0b  test    rbx, rbx
0x180020b0e  jz      short loc_180020B19
0x180020b10  mov     rcx, rbx; void *
0x180020b13  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020b18  nop
0x180020b19  mov     rcx, r14; void *
0x180020b1c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020b21  nop
0x180020b22  lea     rcx, [rbp+57h+var_80]; this
0x180020b26  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180020b2b  xor     eax, eax
0x180020b2d  jmp     loc_180020C16
0x180020b32  lea     rcx, [r15+4B0h]; char *
0x180020b39  xor     r9d, r9d; int
0x180020b3c  mov     r8d, r12d; int
0x180020b3f  mov     edx, [rsp+48h]; unsigned int
0x180020b43  call    ?ReportUntagFilesInReserveFailure@CUpdateReserveManagerDiagnostics@@SAXPEBDKJJ@Z; CUpdateReserveManagerDiagnostics::ReportUntagFilesInReserveFailure(char const *,ulong,long,long)
0x180020b48  nop
0x180020b49  mov     rcx, rdi; Handle
0x180020b4c  call    cs:__imp_NtClose
0x180020b52  test    eax, eax
0x180020b54  jns     short loc_180020B5D
0x180020b56  mov     ecx, 7
0x180020b5b  int     29h; Win8: RtlFailFast(ecx)
0x180020b5d  mov     rcx, rbx; void *
0x180020b60  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020b65  nop
0x180020b66  mov     rcx, r14; void *
0x180020b69  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020b6e  nop
0x180020b6f  lea     rcx, [rbp+57h+var_80]; this
0x180020b73  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x180020b78  mov     eax, r12d
0x180020b7b  jmp     loc_180020C16
0x180020b80  call    cs:__imp_GetLastError
0x180020b86  test    eax, eax
0x180020b88  jnz     loc_180020C3D
0x180020b8e  mov     esi, 36FDh
0x180020b93  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180020b9a  mov     [rbp+57h+var_B0], rax
0x180020b9e  lea     rax, aUpdatereservem_11; "UpdateReserveManager::UntagFilesInReser"...
0x180020ba5  mov     [rbp+57h+var_A8], rax
0x180020ba9  mov     [rbp+57h+var_A0], 0BF2h
0x180020bb1  lea     rax, aFilehandleIsva; "FileHandle.IsValid()"
0x180020bb8  mov     [rbp+57h+var_98], rax
0x180020bbc  test    esi, esi
0x180020bbe  jle     short loc_180020BC9
0x180020bc0  movzx   esi, si
0x180020bc3  or      esi, 80070000h
0x180020bc9  mov     r8d, esi
0x180020bcc  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180020bd3  lea     rcx, [rbp+57h+var_B0]
0x180020bd7  call    RtlReportErrorOrigination
0x180020bdc  nop
0x180020bdd  lea     rax, [rdi-1]
0x180020be1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020be5  ja      short loc_180020BF9
0x180020be7  mov     rcx, rdi; Handle
0x180020bea  call    cs:__imp_NtClose
0x180020bf0  test    eax, eax
0x180020bf2  jns     short loc_180020BF9
0x180020bf4  mov     rcx, r12
0x180020bf7  int     29h; Win8: RtlFailFast(ecx)
0x180020bf9  mov     rcx, rbx; void *
  ... truncated ...
```
