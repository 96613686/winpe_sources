# AppReadiness::Groups::InstallPackage::OnComplete(long)

- ea: `0x18001b370`
- end: `0x18001b7aa`
- name: `?OnComplete@InstallPackage@Groups@AppReadiness@@MEAAXJ@Z`
- size: `1082`
- prototype: `void __fastcall(RTL_SRWLOCK *this, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180005270`
- `0x180009d60`
- `0x180009e10`
- `0x1800192a0`
- `0x18001b370`
- `0x18002a970`
- `0x18002bfa8`
- `0x18003d7e8`
- `0x18003e210`
- `0x180060f74`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001b449`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001b449`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b577`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b5d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b577`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b5d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b563`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b58d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b563`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b58d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18001b50d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18001b50d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b555`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b6f6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b555`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b6f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b4e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b4e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b4da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b4da`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b4b2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b4b2`

## pseudocode

```c
void __fastcall AppReadiness::Groups::InstallPackage::OnComplete(RTL_SRWLOCK *this, int a2)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  signed __int32 v6; // eax
  signed __int32 v7; // ett
  __int64 v8; // rcx
  __int64 v9; // r14
  char *v10; // rbx
  __int64 v11; // rax
  HANDLE v12; // r12
  DWORD v13; // r13d
  HKEY v14; // rsi
  HKEY v15; // rcx
  int v16; // eax
  int Ptr; // esi
  PVOID v18; // rsi
  __int64 v19; // rcx
  __int64 v20; // rcx
  std::_Ref_count_base *v21; // rbx
  __int64 v22; // rax
  __int64 (__fastcall ***v23)(); // rdx
  int LastError; // eax
  const unsigned __int16 *v25; // rbx
  struct AppReadiness::User *v26; // rax
  WCHAR *v27; // rbx
  int v28; // eax
  struct AppReadiness::User *v29; // rax
  __int64 v30; // rax
  BYTE Data[8]; // [rsp+50h] [rbp-69h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-61h] BYREF
  __int64 v33; // [rsp+60h] [rbp-59h]
  std::_Ref_count_base *v34[2]; // [rsp+68h] [rbp-51h] BYREF
  void **v35; // [rsp+78h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-39h]
  __int64 (__fastcall **v37)(); // [rsp+90h] [rbp-29h] BYREF
  int v38; // [rsp+98h] [rbp-21h]
  int v39; // [rsp+9Ch] [rbp-1Dh]
  BYTE *v40; // [rsp+A0h] [rbp-19h]
  std::_Ref_count_base **v41; // [rsp+A8h] [rbp-11h]
  __int64 (__fastcall ***v42)(); // [rsp+C8h] [rbp+Fh]

  v4 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, HKEY *))this->Ptr + 10))(this, &phkResult);
  *(_OWORD *)v34 = 0;
  v5 = *(_QWORD *)(v4 + 8);
  if ( v5 )
  {
    v6 = *(_DWORD *)(v5 + 8);
    while ( v6 )
    {
      v7 = v6;
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 8), v6 + 1, v6);
      if ( v7 == v6 )
      {
        v34[0] = *(std::_Ref_count_base **)v4;
        v34[1] = *(std::_Ref_count_base **)(v4 + 8);
        break;
      }
    }
  }
  v8 = v33;
  if ( v33 && _InterlockedExchangeAdd((volatile signed __int32 *)(v33 + 12), 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 8LL))(v8, v5, v4);
  v9 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, __int64, __int64))this->Ptr + 3))(this, v5, v4);
  v10 = (char *)v34[0] + 40;
  v11 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 14))(this);
  AppReadiness::Storage::PackageList::OpenUserQueueRoot(&v35, v11, 0x20006u);
  v12 = hSemaphore;
  v13 = WaitForSingleObjectEx(hSemaphore, 0xFFFFFFFF, 0);
  if ( *(_QWORD *)(v9 + 24) > 7u )
    v9 = *(_QWORD *)v9;
  if ( *((_QWORD *)v10 + 3) > 7u )
    v10 = *(char **)v10;
  v14 = hKey;
  *(_DWORD *)Data = a2;
  phkResult = 0;
  if ( v10 && *(_WORD *)v10 )
  {
    if ( RegCreateKeyExW(hKey, (LPCWSTR)v10, 0, 0, 0, 2u, 0, &phkResult, 0) )
      goto LABEL_20;
    v15 = phkResult;
  }
  else
  {
    v15 = hKey;
    phkResult = hKey;
  }
  RegSetValueExW(v15, (LPCWSTR)v9, 0, 4u, Data, 4u);
  if ( phkResult != v14 )
    RegCloseKey(phkResult);
LABEL_20:
  if ( v12 && (v13 & 0xFFFFFF7F) == 0 && !ReleaseSemaphore(v12, 1, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
LABEL_51:
    if ( this[44].Ptr )
    {
      v25 = (const unsigned __int16 *)&this[42];
      if ( this[45].Ptr > (PVOID)7 )
        v25 = *(const unsigned __int16 **)v25;
      v26 = (struct AppReadiness::User *)(*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 14))(this);
      AppReadiness::PackageInfo::MarkStatusForEndOfLifePackage(v26, v25, a2);
    }
    v27 = (WCHAR *)v34[0];
    v28 = *((_DWORD *)v34[0] + 35);
    if ( (v28 & 0x100) != 0 )
    {
      if ( a2 >= 0 )
      {
        v30 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 14))(this);
        AppReadiness::Storage::PBRPackageList::RemovePackage(v30 + 64, v27 + 36);
      }
    }
    else if ( (v28 & 2) != 0 )
    {
      v29 = (struct AppReadiness::User *)(*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 14))(this);
      AppReadiness::PackageInfo::MarkStatus((AppReadiness::PackageInfo *)v27, v29, a2);
    }
LABEL_40:
    v20 = *(_QWORD *)Data;
    if ( *(_QWORD *)Data )
    {
      *(_QWORD *)Data = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    goto LABEL_42;
  }
  v35 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  if ( hKey
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(&v35) )
  {
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    RaiseException(v16, 1u, 0, 0);
    __debugbreak();
  }
  AcquireSRWLockShared(this + 7);
  Ptr = (int)this[40].Ptr;
  if ( this != (RTL_SRWLOCK *)-56LL )
    ReleaseSRWLockShared(this + 7);
  if ( Ptr == 1 )
  {
    *(_QWORD *)Data = 0;
    AcquireSRWLockShared(this + 7);
    v18 = this[41].Ptr;
    if ( *(PVOID *)Data != v18 )
    {
      if ( v18 )
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)v18 + 8LL))(this[41].Ptr);
      v19 = *(_QWORD *)Data;
      *(_QWORD *)Data = v18;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    if ( this != (RTL_SRWLOCK *)-56LL )
      ReleaseSRWLockShared(this + 7);
    if ( *(_QWORD *)Data )
    {
      v22 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 14))(this);
      v37 = off_18007A930;
      v38 = a2;
      v39 = HIDWORD(v35);
      v40 = Data;
      v41 = v34;
      v42 = &v37;
      AppReadiness::User::ExecuteUnderContext(v22, (__int64)&v37);
      if ( v42 )
      {
        v23 = &v37;
        LOBYTE(v23) = v42 != &v37;
        ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v42)[4])(v42, v23);
      }
    }
    if ( AppReadiness::Impl::BaseTask::IsCanceled((AppReadiness::Impl::BaseTask *)this) )
      goto LABEL_40;
    goto LABEL_51;
  }
LABEL_42:
  v21 = v34[1];
  if ( v34[1] && _InterlockedExchangeAdd((volatile signed __int32 *)v34[1] + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *))v21)(v21);
    std::_Ref_count_base::_Decwref(v21);
  }
}

```

## disassembly

```asm
0x18001b370  mov     [rsp-8+arg_10], rbx
0x18001b375  push    rbp
0x18001b376  push    rsi
0x18001b377  push    rdi
0x18001b378  push    r12
0x18001b37a  push    r13
0x18001b37c  push    r14
0x18001b37e  push    r15
0x18001b380  lea     rbp, [rsp-27h]
0x18001b385  sub     rsp, 0E0h
0x18001b38c  mov     rax, cs:__security_cookie
0x18001b393  xor     rax, rsp
0x18001b396  mov     [rbp+57h+var_40], rax
0x18001b39a  mov     r15d, edx
0x18001b39d  mov     rdi, rcx
0x18001b3a0  mov     rax, [rcx]
0x18001b3a3  lea     rdx, [rbp+57h+var_B8]
0x18001b3a7  mov     rax, [rax+50h]
0x18001b3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3b0  mov     r8, rax
0x18001b3b3  xorps   xmm0, xmm0
0x18001b3b6  movdqu  xmmword ptr [rbp+57h+var_A8], xmm0
0x18001b3bb  mov     rdx, [rax+8]
0x18001b3bf  test    rdx, rdx
0x18001b3c2  jz      short loc_18001B3E4
0x18001b3c4  mov     eax, [rdx+8]
0x18001b3c7  test    eax, eax
0x18001b3c9  jz      short loc_18001B3E4
0x18001b3cb  lea     ecx, [rax+1]
0x18001b3ce  lock cmpxchg [rdx+8], ecx
0x18001b3d3  jnz     short loc_18001B3C7
0x18001b3d5  mov     rax, [r8]
0x18001b3d8  mov     [rbp+57h+var_A8], rax
0x18001b3dc  mov     rax, [r8+8]
0x18001b3e0  mov     [rbp+57h+var_A8+8], rax
0x18001b3e4  mov     rcx, [rbp+57h+var_B0]
0x18001b3e8  test    rcx, rcx
0x18001b3eb  jz      short loc_18001B3FE
0x18001b3ed  or      eax, 0FFFFFFFFh
0x18001b3f0  lock xadd [rcx+0Ch], eax
0x18001b3f5  cmp     eax, 1
0x18001b3f8  jz      loc_18001B76E
0x18001b3fe  mov     rax, [rdi]
0x18001b401  mov     rcx, rdi
0x18001b404  mov     rax, [rax+18h]
0x18001b408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b40d  mov     r14, rax
0x18001b410  mov     rbx, [rbp+57h+var_A8]
0x18001b414  add     rbx, 28h ; '('
0x18001b418  mov     rax, [rdi]
0x18001b41b  mov     rcx, rdi
0x18001b41e  mov     rax, [rax+70h]
0x18001b422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b427  mov     r8d, 20006h
0x18001b42d  mov     rdx, rax
0x18001b430  lea     rcx, [rbp+57h+var_98]
0x18001b434  call    ?OpenUserQueueRoot@PackageList@Storage@AppReadiness@@SA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@PEBVUser@3@K@Z; AppReadiness::Storage::PackageList::OpenUserQueueRoot(AppReadiness::User const *,ulong)
0x18001b439  mov     r12, cs:hSemaphore
0x18001b440  xor     r8d, r8d; bAlertable
0x18001b443  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001b446  mov     rcx, r12; hHandle
0x18001b449  call    cs:__imp_WaitForSingleObjectEx
0x18001b44f  mov     r13d, eax
0x18001b452  cmp     qword ptr [r14+18h], 7
0x18001b457  jbe     short loc_18001B45C
0x18001b459  mov     r14, [r14]
0x18001b45c  cmp     qword ptr [rbx+18h], 7
0x18001b461  jbe     short loc_18001B466
0x18001b463  mov     rbx, [rbx]
0x18001b466  mov     rsi, [rbp+57h+hKey]
0x18001b46a  mov     dword ptr [rbp+57h+Data], r15d
0x18001b46e  xor     ecx, ecx
0x18001b470  mov     [rbp+57h+var_B8], rcx
0x18001b474  test    rbx, rbx
0x18001b477  jnz     short loc_18001B482
0x18001b479  mov     rcx, rsi
0x18001b47c  mov     [rbp+57h+var_B8], rcx
0x18001b480  jmp     short loc_18001B4C0
0x18001b482  cmp     [rbx], cx
0x18001b485  jz      short loc_18001B479
0x18001b487  mov     [rsp+110h+lpdwDisposition], rcx; lpdwDisposition
0x18001b48c  lea     rax, [rbp+57h+var_B8]
0x18001b490  mov     [rsp+110h+phkResult], rax; phkResult
0x18001b495  mov     [rsp+110h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x18001b49a  mov     [rsp+110h+samDesired], 2; samDesired
0x18001b4a2  mov     [rsp+110h+dwOptions], ecx; dwOptions
0x18001b4a6  xor     r9d, r9d; lpClass
0x18001b4a9  xor     r8d, r8d; Reserved
0x18001b4ac  mov     rdx, rbx; lpSubKey
0x18001b4af  mov     rcx, rsi; hKey
0x18001b4b2  call    cs:__imp_RegCreateKeyExW
0x18001b4b8  test    eax, eax
0x18001b4ba  jnz     short loc_18001B4EF
0x18001b4bc  mov     rcx, [rbp+57h+var_B8]; hKey
0x18001b4c0  mov     r9d, 4; dwType
0x18001b4c6  mov     [rsp+110h+samDesired], r9d; cbData
0x18001b4cb  lea     rax, [rbp+57h+Data]
0x18001b4cf  mov     qword ptr [rsp+110h+dwOptions], rax; lpData
0x18001b4d4  xor     r8d, r8d; Reserved
0x18001b4d7  mov     rdx, r14; lpValueName
0x18001b4da  call    cs:__imp_RegSetValueExW
0x18001b4e0  mov     rcx, [rbp+57h+var_B8]; hKey
0x18001b4e4  cmp     rcx, rsi
0x18001b4e7  jz      short loc_18001B4EF
0x18001b4e9  call    cs:__imp_RegCloseKey
0x18001b4ef  mov     ebx, 1
0x18001b4f4  xor     r14d, r14d
0x18001b4f7  test    r12, r12
0x18001b4fa  jz      short loc_18001B51B
0x18001b4fc  test    r13d, 0FFFFFF7Fh
0x18001b503  jnz     short loc_18001B51B
0x18001b505  xor     r8d, r8d; lpPreviousCount
0x18001b508  mov     edx, ebx; lReleaseCount
0x18001b50a  mov     rcx, r12; hSemaphore
0x18001b50d  call    cs:__imp_ReleaseSemaphore
0x18001b513  test    eax, eax
0x18001b515  jz      loc_18001B6DA
0x18001b51b  lea     rax, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x18001b522  mov     [rbp+57h+var_98], rax
0x18001b526  cmp     [rbp+57h+hKey], r14
0x18001b52a  jz      short loc_18001B55C
0x18001b52c  lea     rcx, [rbp+57h+var_98]
0x18001b530  call    ?InternalClose@?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(void)
0x18001b535  test    al, al
0x18001b537  jnz     short loc_18001B55C
0x18001b539  call    cs:__imp_GetLastError
0x18001b53f  test    eax, eax
0x18001b541  jle     short loc_18001B54B
0x18001b543  movzx   eax, ax
0x18001b546  or      eax, 80070000h
0x18001b54b  xor     r9d, r9d; lpArguments
0x18001b54e  xor     r8d, r8d; nNumberOfArguments
0x18001b551  mov     edx, ebx; dwExceptionFlags
0x18001b553  mov     ecx, eax; dwExceptionCode
0x18001b555  call    cs:__imp_RaiseException
0x18001b55b  int     3; Trap to Debugger
0x18001b55c  lea     rbx, [rdi+38h]
0x18001b560  mov     rcx, rbx; SRWLock
0x18001b563  call    cs:__imp_AcquireSRWLockShared
0x18001b569  mov     esi, [rdi+140h]
0x18001b56f  test    rbx, rbx
0x18001b572  jz      short loc_18001B57D
0x18001b574  mov     rcx, rbx; SRWLock
0x18001b577  call    cs:__imp_ReleaseSRWLockShared
0x18001b57d  cmp     esi, 1
0x18001b580  jnz     loc_18001B60D
0x18001b586  mov     qword ptr [rbp+57h+Data], r14
0x18001b58a  mov     rcx, rbx; SRWLock
0x18001b58d  call    cs:__imp_AcquireSRWLockShared
0x18001b593  mov     rsi, [rdi+148h]
0x18001b59a  cmp     qword ptr [rbp+57h+Data], rsi
0x18001b59e  jz      short loc_18001B5CF
0x18001b5a0  test    rsi, rsi
0x18001b5a3  jz      short loc_18001B5B5
0x18001b5a5  mov     rax, [rsi]
0x18001b5a8  mov     rcx, rsi
0x18001b5ab  mov     rax, [rax+8]
0x18001b5af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5b4  nop
0x18001b5b5  mov     rcx, qword ptr [rbp+57h+Data]
0x18001b5b9  mov     qword ptr [rbp+57h+Data], rsi
0x18001b5bd  test    rcx, rcx
0x18001b5c0  jz      short loc_18001B5CF
0x18001b5c2  mov     rax, [rcx]
0x18001b5c5  mov     rax, [rax+10h]
0x18001b5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5ce  nop
0x18001b5cf  test    rbx, rbx
0x18001b5d2  jz      short loc_18001B5DD
0x18001b5d4  mov     rcx, rbx; SRWLock
0x18001b5d7  call    cs:__imp_ReleaseSRWLockShared
0x18001b5dd  cmp     qword ptr [rbp+57h+Data], r14
0x18001b5e1  jnz     short loc_18001B64E
0x18001b5e3  mov     rcx, rdi; this
0x18001b5e6  call    ?IsCanceled@BaseTask@Impl@AppReadiness@@IEAA_NXZ; AppReadiness::Impl::BaseTask::IsCanceled(void)
0x18001b5eb  test    al, al
0x18001b5ed  jz      loc_18001B6FD
0x18001b5f3  mov     rcx, qword ptr [rbp+57h+Data]
0x18001b5f7  test    rcx, rcx
0x18001b5fa  jz      short loc_18001B60D
0x18001b5fc  mov     qword ptr [rbp+57h+Data], r14
0x18001b600  mov     rax, [rcx]
0x18001b603  mov     rax, [rax+10h]
0x18001b607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b60c  nop
0x18001b60d  mov     rbx, [rbp+57h+var_A8+8]
0x18001b611  test    rbx, rbx
0x18001b614  jz      short loc_18001B627
0x18001b616  or      eax, 0FFFFFFFFh
0x18001b619  lock xadd [rbx+8], eax
0x18001b61e  cmp     eax, 1
0x18001b621  jz      loc_18001B6BF
0x18001b627  mov     rcx, [rbp+57h+var_40]
0x18001b62b  xor     rcx, rsp; StackCookie
0x18001b62e  call    __security_check_cookie
0x18001b633  mov     rbx, [rsp+110h+arg_10]
0x18001b63b  add     rsp, 0E0h
0x18001b642  pop     r15
0x18001b644  pop     r14
0x18001b646  pop     r13
0x18001b648  pop     r12
0x18001b64a  pop     rdi
0x18001b64b  pop     rsi
0x18001b64c  pop     rbp
0x18001b64d  retn
0x18001b64e  mov     rax, [rdi]
0x18001b651  mov     rcx, rdi
0x18001b654  mov     rax, [rax+70h]
0x18001b658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b65d  lea     rcx, off_18007A930
0x18001b664  mov     [rbp+57h+var_80], rcx
0x18001b668  mov     [rbp+57h+var_78], r15d
0x18001b66c  mov     ecx, dword ptr [rbp+57h+var_98+4]
0x18001b66f  mov     [rbp+57h+var_74], ecx
0x18001b672  lea     rcx, [rbp+57h+Data]
0x18001b676  mov     [rbp+57h+var_70], rcx
0x18001b67a  lea     rcx, [rbp+57h+var_A8]
0x18001b67e  mov     [rbp+57h+var_68], rcx
0x18001b682  lea     rcx, [rbp+57h+var_80]
0x18001b686  mov     [rbp+57h+var_48], rcx
0x18001b68a  lea     rdx, [rbp+57h+var_80]
0x18001b68e  mov     rcx, rax
0x18001b691  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x18001b696  nop
0x18001b697  mov     rcx, [rbp+57h+var_48]
0x18001b69b  test    rcx, rcx
0x18001b69e  jz      loc_18001B5E3
0x18001b6a4  mov     rax, [rcx]
0x18001b6a7  lea     rdx, [rbp+57h+var_80]
0x18001b6ab  cmp     rcx, rdx
0x18001b6ae  setnz   dl
0x18001b6b1  mov     rax, [rax+20h]
0x18001b6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6ba  jmp     loc_18001B5E3
0x18001b6bf  mov     rax, [rbx]
0x18001b6c2  mov     rcx, rbx
0x18001b6c5  mov     rax, [rax]
0x18001b6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6cd  mov     rcx, rbx; this
0x18001b6d0  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18001b6d5  jmp     loc_18001B627
0x18001b6da  call    cs:__imp_GetLastError
0x18001b6e0  test    eax, eax
0x18001b6e2  jle     short loc_18001B6EC
0x18001b6e4  movzx   eax, ax
0x18001b6e7  or      eax, 80070000h
0x18001b6ec  xor     r9d, r9d; lpArguments
0x18001b6ef  xor     r8d, r8d; nNumberOfArguments
0x18001b6f2  mov     edx, ebx; dwExceptionFlags
0x18001b6f4  mov     ecx, eax; dwExceptionCode
0x18001b6f6  call    cs:__imp_RaiseException
0x18001b6fc  nop
0x18001b6fd  cmp     [rdi+160h], r14
0x18001b704  jz      short loc_18001B734
0x18001b706  lea     rbx, [rdi+150h]
0x18001b70d  cmp     qword ptr [rbx+18h], 7
0x18001b712  jbe     short loc_18001B717
0x18001b714  mov     rbx, [rbx]
0x18001b717  mov     rax, [rdi]
0x18001b71a  mov     rcx, rdi
0x18001b71d  mov     rax, [rax+70h]
0x18001b721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b726  mov     r8d, r15d; int
0x18001b729  mov     rdx, rbx; unsigned __int16 *
0x18001b72c  mov     rcx, rax; this
0x18001b72f  call    ?MarkStatusForEndOfLifePackage@PackageInfo@AppReadiness@@SAXPEAVUser@2@PEBGJ@Z; AppReadiness::PackageInfo::MarkStatusForEndOfLifePackage(AppReadiness::User *,ushort const *,long)
0x18001b734  mov     rbx, [rbp+57h+var_A8]
0x18001b738  mov     eax, [rbx+8Ch]
0x18001b73e  bt      eax, 8
0x18001b742  jb      short loc_18001B77F
0x18001b744  test    al, 2
0x18001b746  jz      loc_18001B5F3
0x18001b74c  mov     rax, [rdi]
0x18001b74f  mov     rcx, rdi
0x18001b752  mov     rax, [rax+70h]
0x18001b756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b75b  mov     r8d, r15d; int
0x18001b75e  mov     rdx, rax; struct AppReadiness::User *
0x18001b761  mov     rcx, rbx; this
0x18001b764  call    ?MarkStatus@PackageInfo@AppReadiness@@QEBAXPEAVUser@2@J@Z; AppReadiness::PackageInfo::MarkStatus(AppReadiness::User *,long)
0x18001b769  jmp     loc_18001B5F3
0x18001b76e  mov     rax, [rcx]
0x18001b771  mov     rax, [rax+8]
0x18001b775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b77a  jmp     loc_18001B3FE
0x18001b77f  test    r15d, r15d
0x18001b782  js      loc_18001B5F3
0x18001b788  mov     rax, [rdi]
0x18001b78b  mov     rcx, rdi
0x18001b78e  mov     rax, [rax+70h]
0x18001b792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b797  lea     rcx, [rax+40h]
0x18001b79b  lea     rdx, [rbx+48h]
0x18001b79f  call    ?RemovePackage@PBRPackageList@Storage@AppReadiness@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; AppReadiness::Storage::PBRPackageList::RemovePackage(std::wstring const &,std::wstring const &)
0x18001b7a4  jmp     loc_18001B5F3
```
