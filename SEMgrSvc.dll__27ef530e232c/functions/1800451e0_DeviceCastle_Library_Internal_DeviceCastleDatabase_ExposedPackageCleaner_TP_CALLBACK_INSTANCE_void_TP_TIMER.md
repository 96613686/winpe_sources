# DeviceCastle::Library::Internal::DeviceCastleDatabase::ExposedPackageCleaner(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800451e0`
- end: `0x180045396`
- name: `?ExposedPackageCleaner@DeviceCastleDatabase@Internal@Library@DeviceCastle@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `438`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800451e0`
- `0x180045d34`
- `0x180046db0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004537c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004537c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180045366`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180045366`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004524e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004524e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800452ab`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800452e0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180045329`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800452ab`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800452e0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180045329`

## pseudocode

```c
void __fastcall DeviceCastle::Library::Internal::DeviceCastleDatabase::ExposedPackageCleaner(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_TIMER Timer)
{
  __int64 v5; // rbx
  __int64 v6; // r14
  __int64 v7; // rdi
  const FILETIME **i; // rbx
  const FILETIME *v9; // rdx
  __int64 v10; // rax
  FILETIME v11; // [rsp+20h] [rbp-30h] BYREF
  FILETIME FileTime1; // [rsp+28h] [rbp-28h] BYREF
  struct _FILETIME v13; // [rsp+30h] [rbp-20h] BYREF
  struct _FILETIME v14; // [rsp+38h] [rbp-18h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-10h] BYREF
  char v16; // [rsp+48h] [rbp-8h]
  FILETIME FileTime2; // [rsp+88h] [rbp+38h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp+48h] BYREF

  SystemTimeAsFileTime = 0;
  v11 = 0;
  FileTime1 = 0;
  v5 = 10000LL * *((unsigned int *)DeviceCastle::Library::Internal::g_pCastleInstance + 40);
  FileTime2.dwLowDateTime = -1;
  FileTime2.dwHighDateTime = -1;
  lpCriticalSection = (LPCRITICAL_SECTION)(Context + 16);
  v16 = 0;
  ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&lpCriticalSection);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v6 = *((_QWORD *)Context + 8);
  v13 = SystemTimeAsFileTime;
  v7 = *((_QWORD *)Context + 7);
  v14 = (struct _FILETIME)v5;
  FileTime1 = (FILETIME)(*(_QWORD *)&SystemTimeAsFileTime - v5);
  while ( v7 != v6 )
  {
LABEL_2:
    for ( i = *(const FILETIME ***)(*(_QWORD *)v7 + 128LL); i != *(const FILETIME ***)(*(_QWORD *)v7 + 136LL); i += 2 )
    {
      if ( !LOBYTE((*i)[15].dwLowDateTime) )
      {
        if ( CompareFileTime(&FileTime1, *i) >= 0 )
        {
          std::vector<std::shared_ptr<DeviceCastle::Library::Internal::ExposedCryptogramMaterialInformation>>::erase(
            *(_QWORD *)v7 + 128LL,
            &v13,
            i);
          goto LABEL_2;
        }
        v9 = *i;
        v14 = SystemTimeAsFileTime;
        v11 = (FILETIME)(*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)v9);
        if ( CompareFileTime(&v11, &FileTime2) == -1 )
          FileTime2 = v11;
      }
    }
    v7 += 16;
  }
  if ( CompareFileTime(&FileTime2, &SFILETIME_MAX) == -1 )
  {
    v10 = -*(__int64 *)&FileTime2;
    FileTime2.dwLowDateTime = -FileTime2.dwLowDateTime;
    FileTime2.dwHighDateTime = HIDWORD(v10);
    SetThreadpoolTimer(Timer, &FileTime2, 0, 0);
  }
  else
  {
    _InterlockedDecrement((volatile signed __int32 *)Context + 2);
  }
  if ( v16 )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x1800451e0  mov     [rsp-28h+arg_0], rbx
0x1800451e5  push    rbp
0x1800451e6  push    rsi
0x1800451e7  push    rdi
0x1800451e8  push    r14
0x1800451ea  push    r15
0x1800451ec  mov     rbp, rsp
0x1800451ef  sub     rsp, 50h
0x1800451f3  mov     rax, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; DeviceCastle::Library::DeviceCastleInternal * DeviceCastle::Library::Internal::g_pCastleInstance
0x1800451fa  mov     r15, r8
0x1800451fd  mov     rsi, rdx
0x180045200  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180045208  mov     qword ptr [rbp+var_30.dwLowDateTime], 0
0x180045210  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x180045218  mov     ecx, [rax+0A0h]
0x18004521e  or      eax, 0FFFFFFFFh
0x180045221  imul    rbx, rcx, 2710h
0x180045228  mov     [rbp+FileTime2.dwLowDateTime], eax
0x18004522b  lea     rcx, [rbp+lpCriticalSection]; this
0x18004522f  mov     [rbp+FileTime2.dwHighDateTime], eax
0x180045232  mov     rdi, rbx
0x180045235  lea     rax, [rdx+10h]
0x180045239  shr     rdi, 20h
0x18004523d  mov     [rbp+lpCriticalSection], rax
0x180045241  mov     [rbp+var_8], 0
0x180045245  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x18004524a  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004524e  call    cs:__imp_GetSystemTimeAsFileTime
0x180045254  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180045257  mov     ecx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x18004525a  mov     r14, [rsi+40h]
0x18004525e  mov     dword ptr [rbp+var_20+4], ecx
0x180045261  mov     dword ptr [rbp+var_20], eax
0x180045264  mov     rax, [rbp+var_20]
0x180045268  mov     dword ptr [rbp+var_18+4], edi
0x18004526b  mov     rdi, [rsi+38h]
0x18004526f  mov     dword ptr [rbp+var_18], ebx
0x180045272  sub     rax, [rbp+var_18]
0x180045276  mov     rcx, rax
0x180045279  mov     [rbp+FileTime1.dwLowDateTime], eax
0x18004527c  shr     rcx, 20h
0x180045280  mov     [rbp+FileTime1.dwHighDateTime], ecx
0x180045283  jmp     loc_180045315
0x180045288  mov     rbx, [rdi]
0x18004528b  mov     rbx, [rbx+80h]
0x180045292  mov     rax, [rdi]
0x180045295  cmp     rbx, [rax+88h]
0x18004529c  jz      short loc_180045311
0x18004529e  mov     rdx, [rbx]; lpFileTime2
0x1800452a1  cmp     byte ptr [rdx+78h], 0
0x1800452a5  jnz     short loc_1800452F3
0x1800452a7  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800452ab  call    cs:__imp_CompareFileTime
0x1800452b1  test    eax, eax
0x1800452b3  jns     short loc_1800452F9
0x1800452b5  mov     rdx, [rbx]
0x1800452b8  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800452bb  mov     ecx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x1800452be  mov     dword ptr [rbp+var_18+4], ecx
0x1800452c1  mov     dword ptr [rbp+var_18], eax
0x1800452c4  mov     rax, [rbp+var_18]
0x1800452c8  sub     rax, [rdx]
0x1800452cb  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x1800452cf  mov     rcx, rax
0x1800452d2  mov     [rbp+var_30.dwLowDateTime], eax
0x1800452d5  shr     rcx, 20h
0x1800452d9  mov     [rbp+var_30.dwHighDateTime], ecx
0x1800452dc  lea     rcx, [rbp+var_30]; lpFileTime1
0x1800452e0  call    cs:__imp_CompareFileTime
0x1800452e6  cmp     eax, 0FFFFFFFFh
0x1800452e9  jnz     short loc_1800452F3
0x1800452eb  mov     rax, qword ptr [rbp+var_30.dwLowDateTime]
0x1800452ef  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x1800452f3  add     rbx, 10h
0x1800452f7  jmp     short loc_180045292
0x1800452f9  mov     rcx, [rdi]
0x1800452fc  lea     rdx, [rbp+var_20]
0x180045300  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180045304  mov     r8, rbx
0x180045307  call    ?erase@?$vector@V?$shared_ptr@VExposedCryptogramMaterialInformation@Internal@Library@DeviceCastle@@@std@@V?$allocator@V?$shared_ptr@VExposedCryptogramMaterialInformation@Internal@Library@DeviceCastle@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VExposedCryptogramMaterialInformation@Internal@Library@DeviceCastle@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VExposedCryptogramMaterialInformation@Internal@Library@DeviceCastle@@@std@@@std@@@std@@@2@@Z; std::vector<std::shared_ptr<DeviceCastle::Library::Internal::ExposedCryptogramMaterialInformation>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<DeviceCastle::Library::Internal::ExposedCryptogramMaterialInformation>>>>)
0x18004530c  jmp     loc_180045288
0x180045311  add     rdi, 10h
0x180045315  cmp     rdi, r14
0x180045318  jnz     loc_180045288
0x18004531e  lea     rdx, ?SFILETIME_MAX@@3U_FILETIME@@B; lpFileTime2
0x180045325  lea     rcx, [rbp+FileTime2]; lpFileTime1
0x180045329  call    cs:__imp_CompareFileTime
0x18004532f  cmp     eax, 0FFFFFFFFh
0x180045332  jnz     short loc_18004536E
0x180045334  mov     eax, [rbp+FileTime2.dwLowDateTime]
0x180045337  lea     rdx, [rbp+FileTime2]; pftDueTime
0x18004533b  mov     ecx, [rbp+FileTime2.dwHighDateTime]
0x18004533e  xor     r9d, r9d; msWindowLength
0x180045341  mov     [rbp+FileTime2.dwLowDateTime], eax
0x180045344  xor     r8d, r8d; msPeriod
0x180045347  mov     [rbp+FileTime2.dwHighDateTime], ecx
0x18004534a  mov     rcx, r15; pti
0x18004534d  mov     rax, qword ptr [rbp+FileTime2.dwLowDateTime]
0x180045351  neg     rax
0x180045354  mov     [rbp+FileTime2.dwLowDateTime], eax
0x180045357  shr     rax, 20h
0x18004535b  mov     [rbp+FileTime2.dwHighDateTime], eax
0x18004535e  mov     rax, qword ptr [rbp+FileTime2.dwLowDateTime]
0x180045362  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x180045366  call    cs:__imp_SetThreadpoolTimer
0x18004536c  jmp     short loc_180045372
0x18004536e  lock dec dword ptr [rsi+8]
0x180045372  cmp     [rbp+var_8], 0
0x180045376  jz      short loc_180045382
0x180045378  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18004537c  call    cs:__imp_LeaveCriticalSection
0x180045382  mov     rbx, [rsp+50h+arg_0]
0x18004538a  add     rsp, 50h
0x18004538e  pop     r15
0x180045390  pop     r14
0x180045392  pop     rdi
0x180045393  pop     rsi
0x180045394  pop     rbp
0x180045395  retn
```
