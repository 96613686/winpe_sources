# CINetEdge::ReadDataHere(uchar *,ulong,ulong *)

- ea: `0x1800461d0`
- end: `0x18004690e`
- name: `?ReadDataHere@CINetEdge@@IEAAJPEAEKPEAK@Z`
- size: `1854`
- prototype: `__int64 __fastcall(CINetEdge *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180045e70`

## callees

- `0x180007730`
- `0x18000a110`
- `0x18000a270`
- `0x18000cef0`
- `0x18000eb40`
- `0x18000f808`
- `0x180045b8c`
- `0x1800461d0`
- `0x180057860`
- `0x180073b18`
- `0x1800d7ac4`
- `0x1800e3628`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180046696`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180046736`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180046696`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180046736`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004627b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800462b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046370`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800463d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046478`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004627b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800462b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046370`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800463d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046478`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004626c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800462a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046361`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800463c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046468`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004626c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800462a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046361`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800463c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046468`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004667c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004667c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18004663b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18004663b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004642d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004642d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046725`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004672e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046725`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004672e`
- `WININET!InternetReadFile` at `0x180046423`
- `WININET!InternetReadFile` at `0x180046423`
- `WININET!InternetQueryDataAvailable` at `0x18004631a`
- `WININET!InternetQueryDataAvailable` at `0x18004631a`

## pseudocode

```c
__int64 __fastcall CINetEdge::ReadDataHere(CINetEdge *this, unsigned __int8 *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v6; // esi
  bool v7; // dl
  int v8; // edi
  unsigned int v9; // r12d
  int v10; // edi
  unsigned int v11; // eax
  int v12; // edx
  int v13; // edi
  DWORD v14; // r14d
  void *v15; // rcx
  unsigned __int8 *v16; // rdx
  int v17; // edx
  int v18; // r14d
  struct IInternetBindInfo *RefCountedBindInfo; // rax
  struct IInternetBindInfo *v20; // rdi
  RTL_SRWLOCK *v21; // r14
  RTL_SRWLOCK *v22; // r14
  volatile signed __int32 *Ptr; // rdi
  _QWORD *v24; // r14
  unsigned __int8 *v25; // r12
  _QWORD *v26; // r14
  int v27; // edx
  int v28; // ecx
  __int64 v29; // r9
  __int64 v30; // rdx
  struct ITransactionInternal *v31; // rcx
  unsigned int v33; // [rsp+30h] [rbp-D0h] BYREF
  struct ITransactionInternal *v34; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 *v35; // [rsp+40h] [rbp-C0h] BYREF
  CINetEdge *v36; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  CINetEdge *v38; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  CINetEdge *v40; // [rsp+68h] [rbp-98h] BYREF
  char v41; // [rsp+70h] [rbp-90h]
  struct _EVENT_DATA_DESCRIPTOR v42[2]; // [rsp+80h] [rbp-80h] BYREF
  CINetEdge **v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+A8h] [rbp-58h]
  unsigned __int8 **v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+B8h] [rbp-48h]
  struct ITransactionInternal **v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  unsigned int *v49; // [rsp+D0h] [rbp-30h]
  __int64 v50; // [rsp+D8h] [rbp-28h]
  CINetEdge **v51; // [rsp+E0h] [rbp-20h]
  __int64 v52; // [rsp+E8h] [rbp-18h]

  v33 = a3;
  v35 = a2;
  v6 = -2147467259;
  *a4 = 0;
  v40 = this;
  v41 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 300);
  if ( !CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v40) )
    goto LABEL_81;
  if ( *((_DWORD *)this + 31) == -2146828287 )
  {
    v6 = 1;
LABEL_54:
    v21 = (RTL_SRWLOCK *)*((_QWORD *)this + 133);
    if ( v21 )
    {
      v22 = v21 + 1;
      AcquireSRWLockShared(v22);
      Ptr = (volatile signed __int32 *)v22[1].Ptr;
      if ( Ptr )
      {
        _InterlockedIncrement(Ptr + 4);
        ReleaseSRWLockShared(v22);
        v24 = *(_QWORD **)Ptr;
        if ( *((_DWORD *)Ptr + 2) )
        {
          v25 = v35;
          do
          {
            (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int8 *, _QWORD))(*(_QWORD *)*v24 + 48LL))(
              *v24,
              *((unsigned int *)this + 264),
              v25,
              *a4);
            ++v24;
          }
          while ( v24 != (_QWORD *)(*(_QWORD *)Ptr + 8LL * *((unsigned int *)Ptr + 2)) );
        }
        if ( _InterlockedExchangeAdd(Ptr + 4, 0xFFFFFFFF) == 1 )
        {
          v26 = *(_QWORD **)Ptr;
          if ( *((_DWORD *)Ptr + 2) )
          {
            do
            {
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 16LL))(*v26);
              ++v26;
            }
            while ( v26 != (_QWORD *)(*(_QWORD *)Ptr + 8LL * *((unsigned int *)Ptr + 2)) );
          }
          CoTaskMemFree(*(LPVOID *)Ptr);
          CoTaskMemFree((LPVOID)Ptr);
        }
      }
      else
      {
        ReleaseSRWLockShared(v22);
      }
    }
    goto LABEL_64;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  v8 = *((_DWORD *)this + 123);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  if ( v8 )
  {
    v6 = -2147483638;
    goto LABEL_51;
  }
  v6 = 0;
  v9 = 0;
  v34 = (struct ITransactionInternal *)*((_QWORD *)this + 52);
  *((_DWORD *)this + 31) = 0;
  while ( 1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
    v10 = *((_DWORD *)this + 107);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
    if ( v10 )
      goto LABEL_18;
    (*(void (__fastcall **)(CINetEdge *))(*(_QWORD *)this + 400LL))(this);
    v11 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 34);
    if ( v11 != 1 )
      goto LABEL_36;
    if ( (unsigned int)CINetEdge::SetStatePending(this, 2147483658LL, 6) )
      break;
    if ( InternetQueryDataAvailable(*((HINTERNET *)this + 47), (LPDWORD)this + 106, 0, 0) )
    {
      v13 = *((_DWORD *)this + 106);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
      *((_DWORD *)this + 107) += v13;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
      CINetEdge::SetStatePending(this, 0, 6);
      if ( !*((_DWORD *)this + 106) )
      {
        *((_DWORD *)this + 31) = -2146828287;
        v6 = -2146828287;
      }
      v12 = 35;
    }
    else
    {
      if ( GetLastError() == 997 )
        break;
      CINetEdge::SetStatePending(this, 0, 6);
      v12 = 36;
      *((_DWORD *)this + 31) = -2146697209;
      v6 = -2146697209;
    }
    v11 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, v12);
    if ( v11 != 1 )
    {
LABEL_36:
      v6 = CINetEdge::CheckTransitionStatusAndDispatchAbort(this, v11, v6);
      goto LABEL_81;
    }
    if ( v6 )
      goto LABEL_31;
LABEL_18:
    if ( !*((_DWORD *)this + 31) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
      v14 = *((_DWORD *)this + 107);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
      if ( v33 - v9 <= v14 )
        v14 = v33 - v9;
      v11 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 27);
      if ( v11 != 1 )
        goto LABEL_36;
      v15 = (void *)*((_QWORD *)this + 47);
      v16 = &v35[v9];
      *((_DWORD *)this + 110) = 0;
      if ( InternetReadFile(v15, v16, v14, (LPDWORD)this + 110) )
      {
        v18 = *((_DWORD *)this + 110);
        if ( v18 )
        {
          v6 = 0;
        }
        else
        {
          *((_DWORD *)this + 31) = -2146828287;
          v6 = -2146828287;
        }
        v9 += v18;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
        *((_DWORD *)this + 107) -= v18;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
        v17 = 28;
        *((_QWORD *)this + 52) += *((unsigned int *)this + 110);
      }
      else
      {
        GetLastError();
        v17 = 29;
        *((_DWORD *)this + 31) = -2146697208;
        v6 = -2146697208;
      }
      v11 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, v17);
      if ( v11 != 1 )
        goto LABEL_36;
      if ( v6 )
        goto LABEL_31;
    }
    if ( v9 >= v33 )
      goto LABEL_31;
  }
  v6 = -2147483638;
LABEL_31:
  if ( *((_QWORD *)this + 52) < 0xFFEFFFFF )
  {
    *a4 = v9;
  }
  else
  {
    *a4 = 0;
    RefCountedBindInfo = CINetEdge::GetRefCountedBindInfo(this, v7);
    v20 = RefCountedBindInfo;
    if ( RefCountedBindInfo )
    {
      if ( (unsigned int)CINetEdge::IsDownloading64BitEnabled(this, RefCountedBindInfo) )
      {
        if ( CINetEdge::IsFetchModeClient(this) )
          *a4 = v9;
      }
      else
      {
        *((_DWORD *)this + 31) = -2146697208;
        v6 = -2146697208;
      }
    }
    else
    {
      v6 = -2147467260;
    }
    if ( (unsigned __int64)v34 < 0xFFEFFFFF
      && (unsigned int)dword_180159000 > 5
      && (qword_180159010 & 0x20) != 0
      && (qword_180159018 & 0x20) == qword_180159018 )
    {
      v37 = *((_QWORD *)this + 52);
      v33 = v6;
      v49 = &v33;
      v47 = &v34;
      v36 = this;
      v45 = (unsigned __int8 **)&v37;
      v43 = &v36;
      v50 = 4;
      v48 = 8;
      v46 = 8;
      v44 = 8;
      tlgWriteTransfer_BrowserWriteTransfer((__int64)&dword_180159000, byte_180145196, 0, 0, 6u, v42);
    }
    if ( v20 )
      ((void (__fastcall *)(struct IInternetBindInfo *))v20->lpVtbl->Release)(v20);
  }
  if ( v6 == -2146828287 )
  {
    v6 = *a4 == 0;
    goto LABEL_54;
  }
  if ( (v6 & 0x80000000) == 0 )
    goto LABEL_54;
LABEL_51:
  InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
  if ( byte_18015DE34 && v6 == -2147483638 && *a4 )
    goto LABEL_54;
LABEL_64:
  v33 = 0;
  v34 = 0;
  if ( !(unsigned int)CINetEdge::GetTransactionInternal(this, v7, &v34) )
    (*(void (__fastcall **)(struct ITransactionInternal *, unsigned int *))(*(_QWORD *)v34 + 96LL))(v34, &v33);
  if ( (unsigned int)dword_180159000 > 5 )
  {
    v28 = qword_180159018;
    if ( (qword_180159010 & 0x20) != 0 && (qword_180159018 & 0x20) == qword_180159018 )
    {
      LODWORD(v36) = v33;
      v39 = *((_QWORD *)this + 52);
      LODWORD(v35) = *a4;
      v51 = &v36;
      v49 = (unsigned int *)&v37;
      v47 = (struct ITransactionInternal **)&v39;
      v45 = &v35;
      v43 = &v38;
      LODWORD(v37) = v6;
      v38 = this;
      v52 = 4;
      v50 = 4;
      v48 = 8;
      v46 = 4;
      v44 = 8;
      tlgWriteTransfer_BrowserWriteTransfer((__int64)&dword_180159000, byte_180145138, 0, 0, 7u, v42);
    }
  }
  if ( (Microsoft_Windows_URLMonEnableBits & 1) != 0 )
    McTemplateU0qzq_EventWriteTransfer(v28, v27, v33, *((_QWORD *)this + 23), *a4);
  if ( v6 != -2147483638 && *((_DWORD *)this + 31) )
  {
    v29 = *((_QWORD *)this + 51);
    if ( !v29 )
      v29 = *((_QWORD *)this + 50);
    v30 = v6;
    if ( v6 == 1 )
      v30 = 0;
    (*(void (__fastcall **)(CINetEdge *, __int64, _QWORD, __int64, _QWORD))(*(_QWORD *)this + 288LL))(
      this,
      v30,
      *((_QWORD *)this + 52),
      v29,
      0);
  }
  v31 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(struct ITransactionInternal *))(*(_QWORD *)v31 + 16LL))(v31);
  }
LABEL_81:
  CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v40);
  return v6;
}

```

## disassembly

```asm
0x1800461d0  push    rbp
0x1800461d2  push    rbx
0x1800461d3  push    rsi
0x1800461d4  push    r13
0x1800461d6  lea     rbp, [rsp-28h]
0x1800461db  sub     rsp, 128h
0x1800461e2  mov     rax, cs:__security_cookie
0x1800461e9  xor     rax, rsp
0x1800461ec  mov     [rbp+40h+var_50], rax
0x1800461f0  mov     r13, r9
0x1800461f3  mov     [rsp+140h+var_110], r8d
0x1800461f8  mov     [rsp+140h+var_100], rdx
0x1800461fd  mov     rbx, rcx
0x180046200  mov     esi, 80004005h
0x180046205  mov     dword ptr [r9], 0
0x18004620c  mov     [rsp+140h+var_D8], rcx
0x180046211  mov     [rsp+140h+var_D0], 0
0x180046216  lock inc dword ptr [rcx+4B0h]
0x18004621d  lea     rcx, [rsp+140h+var_D8]; this
0x180046222  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x180046227  test    al, al
0x180046229  jz      loc_1800468E9
0x18004622f  cmp     dword ptr [rbx+7Ch], 800A0001h
0x180046236  mov     [rsp+140h+var_20], rdi
0x18004623e  mov     [rsp+140h+var_28], r12
0x180046246  mov     [rsp+140h+var_30], r14
0x18004624e  mov     [rsp+140h+var_38], r15
0x180046256  jnz     short loc_180046262
0x180046258  mov     esi, 1
0x18004625d  jmp     loc_180046665
0x180046262  lea     r15, [rbx+3D8h]
0x180046269  mov     rcx, r15; lpCriticalSection
0x18004626c  call    cs:__imp_EnterCriticalSection
0x180046272  mov     edi, [rbx+1ECh]
0x180046278  mov     rcx, r15; lpCriticalSection
0x18004627b  call    cs:__imp_LeaveCriticalSection
0x180046281  test    edi, edi
0x180046283  jz      short loc_18004628F
0x180046285  mov     esi, 8000000Ah
0x18004628a  jmp     loc_180046627
0x18004628f  mov     r14, [rbx+1A0h]
0x180046296  xor     esi, esi
0x180046298  xor     r12d, r12d
0x18004629b  mov     [rsp+140h+var_108], r14
0x1800462a0  mov     [rbx+7Ch], esi
0x1800462a3  mov     rcx, r15; lpCriticalSection
0x1800462a6  call    cs:__imp_EnterCriticalSection
0x1800462ac  mov     edi, [rbx+1ACh]
0x1800462b2  mov     rcx, r15; lpCriticalSection
0x1800462b5  call    cs:__imp_LeaveCriticalSection
0x1800462bb  test    edi, edi
0x1800462bd  jnz     loc_1800463B9
0x1800462c3  mov     rax, [rbx]
0x1800462c6  mov     rcx, rbx
0x1800462c9  mov     rax, [rax+190h]
0x1800462d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800462d5  mov     edx, 22h ; '"'
0x1800462da  mov     rcx, rbx
0x1800462dd  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x1800462e2  cmp     eax, 1
0x1800462e5  jnz     loc_1800464F9
0x1800462eb  mov     edx, 8000000Ah
0x1800462f0  mov     r8d, 6
0x1800462f6  mov     rcx, rbx
0x1800462f9  call    ?SetStatePending@CINetEdge@@IEAAJJW4ePendingStateReason@1@H@Z; CINetEdge::SetStatePending(long,CINetEdge::ePendingStateReason,int)
0x1800462fe  test    eax, eax
0x180046300  jnz     loc_1800464F2
0x180046306  mov     rcx, [rbx+178h]; hFile
0x18004630d  lea     rdx, [rbx+1A8h]; lpdwNumberOfBytesAvailable
0x180046314  xor     r9d, r9d; dwContext
0x180046317  xor     r8d, r8d; dwFlags
0x18004631a  call    cs:__imp_InternetQueryDataAvailable
0x180046320  test    eax, eax
0x180046322  jnz     short loc_180046358
0x180046324  call    cs:__imp_GetLastError
0x18004632a  cmp     eax, 3E5h
0x18004632f  jz      loc_1800464F2
0x180046335  xor     edx, edx
0x180046337  mov     r8d, 6
0x18004633d  mov     rcx, rbx
0x180046340  call    ?SetStatePending@CINetEdge@@IEAAJJW4ePendingStateReason@1@H@Z; CINetEdge::SetStatePending(long,CINetEdge::ePendingStateReason,int)
0x180046345  mov     edx, 24h ; '$'
0x18004634a  mov     dword ptr [rbx+7Ch], 800C0007h
0x180046351  mov     esi, 800C0007h
0x180046356  jmp     short loc_1800463A0
0x180046358  mov     edi, [rbx+1A8h]
0x18004635e  mov     rcx, r15; lpCriticalSection
0x180046361  call    cs:__imp_EnterCriticalSection
0x180046367  add     [rbx+1ACh], edi
0x18004636d  mov     rcx, r15; lpCriticalSection
0x180046370  call    cs:__imp_LeaveCriticalSection
0x180046376  xor     edx, edx
0x180046378  mov     r8d, 6
0x18004637e  mov     rcx, rbx
0x180046381  call    ?SetStatePending@CINetEdge@@IEAAJJW4ePendingStateReason@1@H@Z; CINetEdge::SetStatePending(long,CINetEdge::ePendingStateReason,int)
0x180046386  cmp     dword ptr [rbx+1A8h], 0
0x18004638d  jnz     short loc_18004639B
0x18004638f  mov     dword ptr [rbx+7Ch], 800A0001h
0x180046396  mov     esi, 800A0001h
0x18004639b  mov     edx, 23h ; '#'
0x1800463a0  mov     rcx, rbx
0x1800463a3  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x1800463a8  cmp     eax, 1
0x1800463ab  jnz     loc_1800464F9
0x1800463b1  test    esi, esi
0x1800463b3  jnz     loc_1800464AC
0x1800463b9  cmp     dword ptr [rbx+7Ch], 0
0x1800463bd  jnz     loc_1800464A1
0x1800463c3  mov     rcx, r15; lpCriticalSection
0x1800463c6  call    cs:__imp_EnterCriticalSection
0x1800463cc  mov     r14d, [rbx+1ACh]
0x1800463d3  mov     rcx, r15; lpCriticalSection
0x1800463d6  call    cs:__imp_LeaveCriticalSection
0x1800463dc  mov     eax, [rsp+140h+var_110]
0x1800463e0  mov     edx, 1Bh
0x1800463e5  sub     eax, r12d
0x1800463e8  mov     rcx, rbx
0x1800463eb  cmp     eax, r14d
0x1800463ee  cmovbe  r14d, eax
0x1800463f2  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x1800463f7  cmp     eax, 1
0x1800463fa  jnz     loc_1800464F9
0x180046400  mov     rcx, [rbx+178h]; hFile
0x180046407  lea     r9, [rbx+1B8h]; lpdwNumberOfBytesRead
0x18004640e  mov     edx, r12d
0x180046411  mov     r8d, r14d; dwNumberOfBytesToRead
0x180046414  add     rdx, [rsp+140h+var_100]; lpBuffer
0x180046419  mov     dword ptr [rbx+1B8h], 0
0x180046423  call    cs:__imp_InternetReadFile
0x180046429  test    eax, eax
0x18004642b  jnz     short loc_180046446
0x18004642d  call    cs:__imp_GetLastError
0x180046433  mov     edx, 1Dh
0x180046438  mov     dword ptr [rbx+7Ch], 800C0008h
0x18004643f  mov     esi, 800C0008h
0x180046444  jmp     short loc_180046490
0x180046446  mov     r14d, [rbx+1B8h]
0x18004644d  test    r14d, r14d
0x180046450  jnz     short loc_180046460
0x180046452  mov     dword ptr [rbx+7Ch], 800A0001h
0x180046459  mov     esi, 800A0001h
0x18004645e  jmp     short loc_180046462
0x180046460  xor     esi, esi
0x180046462  mov     rcx, r15; lpCriticalSection
0x180046465  add     r12d, r14d
0x180046468  call    cs:__imp_EnterCriticalSection
0x18004646e  sub     [rbx+1ACh], r14d
0x180046475  mov     rcx, r15; lpCriticalSection
0x180046478  call    cs:__imp_LeaveCriticalSection
0x18004647e  mov     eax, [rbx+1B8h]
0x180046484  mov     edx, 1Ch
0x180046489  add     [rbx+1A0h], rax
0x180046490  mov     rcx, rbx
0x180046493  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x180046498  cmp     eax, 1
0x18004649b  jnz     short loc_1800464F9
0x18004649d  test    esi, esi
0x18004649f  jnz     short loc_1800464AC
0x1800464a1  cmp     r12d, [rsp+140h+var_110]
0x1800464a6  jb      loc_1800462A3
0x1800464ac  mov     eax, 0FFEFFFFFh
0x1800464b1  xor     r15d, r15d
0x1800464b4  cmp     [rbx+1A0h], rax
0x1800464bb  jb      loc_180046609
0x1800464c1  mov     rcx, rbx; this
0x1800464c4  mov     [r13+0], r15d
0x1800464c8  call    ?GetRefCountedBindInfo@CINetEdge@@IEAAPEAUIInternetBindInfo@@_N@Z; CINetEdge::GetRefCountedBindInfo(bool)
0x1800464cd  mov     rdi, rax
0x1800464d0  test    rax, rax
0x1800464d3  jz      short loc_18004651F
0x1800464d5  mov     rdx, rax; struct IInternetBindInfo *
0x1800464d8  mov     rcx, rbx; this
0x1800464db  call    ?IsDownloading64BitEnabled@CINetEdge@@IEAAHPEAUIInternetBindInfo@@@Z; CINetEdge::IsDownloading64BitEnabled(IInternetBindInfo *)
0x1800464e0  test    eax, eax
0x1800464e2  jnz     short loc_18004650D
0x1800464e4  mov     dword ptr [rbx+7Ch], 800C0008h
0x1800464eb  mov     esi, 800C0008h
0x1800464f0  jmp     short loc_180046524
0x1800464f2  mov     esi, 8000000Ah
0x1800464f7  jmp     short loc_1800464AC
0x1800464f9  mov     r8d, esi
0x1800464fc  mov     edx, eax
0x1800464fe  mov     rcx, rbx
0x180046501  call    ?CheckTransitionStatusAndDispatchAbort@CINetEdge@@IEAAJW4INetEdgeStateTransition@@J@Z; CINetEdge::CheckTransitionStatusAndDispatchAbort(INetEdgeStateTransition,long)
0x180046506  mov     esi, eax
0x180046508  jmp     loc_1800468C9
0x18004650d  mov     rcx, rbx; this
0x180046510  call    ?IsFetchModeClient@CINetEdge@@IEAA_NXZ; CINetEdge::IsFetchModeClient(void)
0x180046515  test    al, al
0x180046517  jz      short loc_180046524
0x180046519  mov     [r13+0], r12d
0x18004651d  jmp     short loc_180046524
0x18004651f  mov     esi, 80004004h
0x180046524  mov     r14, [rsp+140h+var_108]
0x180046529  mov     eax, 0FFEFFFFFh
0x18004652e  cmp     r14, rax
0x180046531  jnb     loc_1800465F3
0x180046537  mov     eax, cs:dword_180159000
0x18004653d  cmp     eax, 5
0x180046540  jbe     loc_1800465F3
0x180046546  mov     rcx, cs:qword_180159018
0x18004654d  mov     rax, cs:qword_180159010
0x180046554  test    al, 20h
0x180046556  jz      loc_1800465F3
0x18004655c  mov     rax, rcx
0x18004655f  and     eax, 20h
0x180046562  cmp     rax, rcx
0x180046565  jnz     loc_1800465F3
0x18004656b  mov     rax, [rbx+1A0h]
0x180046572  lea     rdx, byte_180145196
0x180046579  mov     [rsp+140h+var_F0], rax
0x18004657e  lea     rcx, dword_180159000
0x180046585  lea     rax, [rsp+140h+var_110]
0x18004658a  mov     [rsp+140h+var_110], esi
0x18004658e  mov     [rbp+40h+var_70], rax
0x180046592  xor     r9d, r9d
0x180046595  lea     rax, [rsp+140h+var_108]
0x18004659a  mov     [rsp+140h+var_108], r14
0x18004659f  mov     [rbp+40h+var_80], rax
0x1800465a3  xor     r8d, r8d
0x1800465a6  lea     rax, [rsp+140h+var_F0]
0x1800465ab  mov     [rsp+140h+var_F8], rbx
0x1800465b0  mov     [rbp+40h+var_90], rax
0x1800465b4  lea     rax, [rsp+140h+var_F8]
0x1800465b9  mov     [rbp+40h+var_A0], rax
0x1800465bd  lea     rax, [rbp+40h+var_C0]
0x1800465c1  mov     [rsp+140h+var_118], rax
0x1800465c6  mov     dword ptr [rsp+140h+var_120], 6
0x1800465ce  mov     [rbp+40h+var_68], 4
0x1800465d6  mov     [rbp+40h+var_78], 8
0x1800465de  mov     [rbp+40h+var_88], 8
0x1800465e6  mov     [rbp+40h+var_98], 8
0x1800465ee  call    _tlgWriteTransfer_BrowserWriteTransfer
0x1800465f3  test    rdi, rdi
0x1800465f6  jz      short loc_18004660D
0x1800465f8  mov     rax, [rdi]
0x1800465fb  mov     rcx, rdi
0x1800465fe  mov     rax, [rax+10h]
0x180046602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046607  jmp     short loc_18004660D
0x180046609  mov     [r13+0], r12d
0x18004660d  cmp     esi, 800A0001h
0x180046613  jnz     short loc_180046623
0x180046615  cmp     dword ptr [r13+0], 0
0x18004661a  mov     esi, r15d
0x18004661d  setz    sil
0x180046621  jmp     short loc_180046665
0x180046623  test    esi, esi
0x180046625  jns     short loc_180046665
0x180046627  xor     r9d, r9d; Context
0x18004662a  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180046631  xor     r8d, r8d; Parameter
0x180046634  lea     rcx, stru_18015EA38; InitOnce
0x18004663b  call    cs:__imp_InitOnceExecuteOnce
0x180046641  cmp     cs:byte_18015DE34, 0
0x180046648  jz      loc_18004673C
0x18004664e  cmp     esi, 8000000Ah
0x180046654  jnz     loc_18004673C
0x18004665a  cmp     dword ptr [r13+0], 0
0x18004665f  jbe     loc_18004673C
0x180046665  mov     r14, [rbx+428h]
0x18004666c  test    r14, r14
0x18004666f  jz      loc_18004673C
0x180046675  add     r14, 8
0x180046679  mov     rcx, r14; SRWLock
0x18004667c  call    cs:__imp_AcquireSRWLockShared
0x180046682  mov     rdi, [r14+8]
0x180046686  mov     rcx, r14; SRWLock
0x180046689  test    rdi, rdi
0x18004668c  jz      loc_180046736
0x180046692  lock inc dword ptr [rdi+10h]
0x180046696  call    cs:__imp_ReleaseSRWLockShared
0x18004669c  cmp     dword ptr [rdi+8], 0
0x1800466a0  mov     r14, [rdi]
0x1800466a3  jz      short loc_1800466DF
0x1800466a5  mov     r12, [rsp+140h+var_100]
0x1800466aa  nop     word ptr [rax+rax+00h]
0x1800466b0  mov     rcx, [r14]
0x1800466b3  mov     r8, r12
0x1800466b6  mov     r9d, [r13+0]
0x1800466ba  mov     edx, [rbx+420h]
0x1800466c0  mov     rax, [rcx]
0x1800466c3  mov     rax, [rax+30h]
0x1800466c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466cc  mov     ecx, [rdi+8]
0x1800466cf  add     r14, 8
0x1800466d3  mov     rax, [rdi]
0x1800466d6  lea     rcx, [rax+rcx*8]
0x1800466da  cmp     r14, rcx
0x1800466dd  jnz     short loc_1800466B0
0x1800466df  mov     eax, 0FFFFFFFFh
0x1800466e4  lock xadd [rdi+10h], eax
0x1800466e9  cmp     eax, 1
0x1800466ec  jnz     short loc_18004673C
0x1800466ee  mov     edx, [rdi+8]
0x1800466f1  mov     r14, [rdi]
0x1800466f4  test    edx, edx
0x1800466f6  jz      short loc_180046722
0x1800466f8  nop     dword ptr [rax+rax+00000000h]
0x180046700  mov     rcx, [r14]
  ... truncated ...
```
