# DeviceCastle::Library::Internal::DeviceCastleDatabase::DeclareExposedCryptogramMaterialPackage(std::shared_ptr<DeviceCastle::Library::Internal::ExposedCryptogramMaterialInformation> const &)

- ea: `0x180044dec`
- end: `0x180044ed9`
- name: `?DeclareExposedCryptogramMaterialPackage@DeviceCastleDatabase@Internal@Library@DeviceCastle@@QEAAXAEBV?$shared_ptr@VExposedCryptogramMaterialInformation@Internal@Library@DeviceCastle@@@std@@@Z`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180046968`
- `0x18004d358`

## callees

- `0x180044dec`
- `0x180045d34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044ec8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044ec8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180044ea9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180044ea9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180044e3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180044e3b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180044e1e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180044e1e`

## pseudocode

```c
void __fastcall DeviceCastle::Library::Internal::DeviceCastleDatabase::DeclareExposedCryptogramMaterialPackage(
        __int64 a1,
        LPFILETIME *a2)
{
  DeviceCastle::Library::DeviceCastleInternal *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  struct _TP_TIMER *v7; // rcx
  bool v8; // zf
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-18h] BYREF
  char v10; // [rsp+28h] [rbp-10h]
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  v10 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 16);
  ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&lpCriticalSection);
  if ( !CompareFileTime(&FILETIME_MAX, *a2)
    || (v4 = DeviceCastle::Library::Internal::g_pCastleInstance,
        *((_BYTE *)DeviceCastle::Library::Internal::g_pCastleInstance + 156)) )
  {
    GetSystemTimeAsFileTime(*a2);
    v4 = DeviceCastle::Library::Internal::g_pCastleInstance;
  }
  if ( *(_QWORD *)(a1 + 112) )
  {
    v5 = *((unsigned int *)v4 + 40);
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 8)) == 1 )
    {
      pftDueTime = (struct _FILETIME)(10000 * v5);
      v6 = 10000 * v5;
      v7 = *(struct _TP_TIMER **)(a1 + 112);
      pftDueTime = (struct _FILETIME)-v6;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0);
    }
    else
    {
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 8));
    }
  }
  v8 = v10 == 0;
  LOBYTE((*a2)[15].dwLowDateTime) = 0;
  if ( !v8 )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180044dec  mov     [rsp+arg_8], rbx
0x180044df1  push    rdi
0x180044df2  sub     rsp, 30h
0x180044df6  lea     rax, [rcx+10h]
0x180044dfa  mov     [rsp+38h+var_10], 0
0x180044dff  mov     rbx, rcx
0x180044e02  mov     [rsp+38h+lpCriticalSection], rax
0x180044e07  lea     rcx, [rsp+38h+lpCriticalSection]; this
0x180044e0c  mov     rdi, rdx
0x180044e0f  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x180044e14  mov     rdx, [rdi]; lpFileTime2
0x180044e17  lea     rcx, ?FILETIME_MAX@@3U_FILETIME@@B; lpFileTime1
0x180044e1e  call    cs:__imp_CompareFileTime
0x180044e24  test    eax, eax
0x180044e26  jz      short loc_180044E38
0x180044e28  mov     rax, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; DeviceCastle::Library::DeviceCastleInternal * DeviceCastle::Library::Internal::g_pCastleInstance
0x180044e2f  cmp     byte ptr [rax+9Ch], 0
0x180044e36  jz      short loc_180044E48
0x180044e38  mov     rcx, [rdi]; lpSystemTimeAsFileTime
0x180044e3b  call    cs:__imp_GetSystemTimeAsFileTime
0x180044e41  mov     rax, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; DeviceCastle::Library::DeviceCastleInternal * DeviceCastle::Library::Internal::g_pCastleInstance
0x180044e48  cmp     qword ptr [rbx+70h], 0
0x180044e4d  jz      short loc_180044EB5
0x180044e4f  mov     ecx, [rax+0A0h]
0x180044e55  mov     eax, 1
0x180044e5a  lock xadd [rbx+8], eax
0x180044e5f  inc     eax
0x180044e61  cmp     eax, 1
0x180044e64  jnz     short loc_180044EB1
0x180044e66  imul    rax, rcx, 2710h
0x180044e6d  xor     r9d, r9d; msWindowLength
0x180044e70  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180044e75  mov     [rsp+38h+pftDueTime.dwLowDateTime], eax
0x180044e79  mov     rcx, rax
0x180044e7c  shr     rcx, 20h
0x180044e80  xor     r8d, r8d; msPeriod
0x180044e83  mov     [rsp+38h+pftDueTime.dwHighDateTime], ecx
0x180044e87  mov     rax, qword ptr [rsp+38h+pftDueTime.dwLowDateTime]
0x180044e8c  mov     rcx, [rbx+70h]; pti
0x180044e90  neg     rax
0x180044e93  mov     [rsp+38h+pftDueTime.dwLowDateTime], eax
0x180044e97  shr     rax, 20h
0x180044e9b  mov     [rsp+38h+pftDueTime.dwHighDateTime], eax
0x180044e9f  mov     rax, qword ptr [rsp+38h+pftDueTime.dwLowDateTime]
0x180044ea4  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180044ea9  call    cs:__imp_SetThreadpoolTimer
0x180044eaf  jmp     short loc_180044EB5
0x180044eb1  lock dec dword ptr [rbx+8]
0x180044eb5  cmp     [rsp+38h+var_10], 0
0x180044eba  mov     rax, [rdi]
0x180044ebd  mov     byte ptr [rax+78h], 0
0x180044ec1  jz      short loc_180044ECE
0x180044ec3  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x180044ec8  call    cs:__imp_LeaveCriticalSection
0x180044ece  mov     rbx, [rsp+38h+arg_8]
0x180044ed3  add     rsp, 30h
0x180044ed7  pop     rdi
0x180044ed8  retn
```
