# XinputHid::XinputHidInterface::DriverManagementWorkerThread(void)

- ea: `0x18000f5d4`
- end: `0x18001000c`
- name: `?DriverManagementWorkerThread@XinputHidInterface@XinputHid@@AEAAXXZ`
- size: `2616`
- prototype: `void __fastcall(XinputHid::XinputHidInterface *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180010750`

## callees

- `0x1800016c0`
- `0x180001d40`
- `0x180002158`
- `0x180009260`
- `0x18000f1a4`
- `0x18000f5d4`
- `0x180010040`
- `0x180010410`
- `0x180010ed4`
- `0x1800111fc`
- `0x180011440`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000fc84`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000fccd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000fc84`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000fccd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f6bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f6bb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fc96`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000feea`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fc96`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000feea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fb3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fbde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fb3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fbde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f738`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fd0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f738`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fd0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ff24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ff24`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000fc78`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000fc78`

## pseudocode

```c
void __fastcall XinputHid::XinputHidInterface::DriverManagementWorkerThread(XinputHid::XinputHidInterface *this)
{
  __m128i v2; // xmm6
  __m128i v3; // xmm7
  unsigned int v4; // r14d
  unsigned int i; // ebx
  char *EventW; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  volatile signed __int32 *v8; // r12
  volatile signed __int32 *v9; // rsi
  signed __int32 v10; // eax
  signed __int32 v11; // ett
  volatile signed __int32 *v12; // rbx
  signed __int32 v13; // eax
  signed __int32 v14; // ett
  volatile signed __int32 *v15; // rbx
  struct XinputHid::XInputHidDevice *v16; // r15
  struct XinputHid::XInputHidDevice *v17; // r13
  XinputHid::XinputHidInterface *v18; // rax
  _QWORD *v19; // rbx
  volatile signed __int32 *v20; // rdi
  _QWORD *v21; // r14
  __int64 v22; // rsi
  volatile signed __int32 *v23; // rcx
  signed __int32 v24; // eax
  signed __int32 v25; // ett
  volatile signed __int32 *v26; // rsi
  __int64 v27; // rcx
  __int64 v28; // rsi
  volatile signed __int32 *v29; // rcx
  signed __int32 v30; // eax
  signed __int32 v31; // ett
  volatile signed __int32 *v32; // rsi
  __int64 v33; // rcx
  char v34; // bl
  struct XinputHid::XInputHidDevice *v35; // rdx
  HANDLE *v36; // r13
  volatile signed __int32 *v37; // rbx
  volatile signed __int32 *v38; // rbx
  volatile signed __int32 *v39; // rbx
  volatile signed __int32 *v40; // rbx
  const char *v41; // r9
  signed __int32 v42; // eax
  signed __int32 v43; // ett
  __int64 v44; // rdx
  signed __int32 v45; // eax
  signed __int32 v46; // ett
  volatile signed __int32 *v47; // rbx
  struct XinputHid::XInputHidDevice *v48; // rdx
  volatile signed __int32 *v49; // rbx
  volatile signed __int32 *v50; // rbx
  HANDLE v51; // rcx
  const char *v52; // r9
  const char *v53; // r9
  int v54; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v55; // [rsp+40h] [rbp-C0h]
  __m128i v56; // [rsp+50h] [rbp-B0h] BYREF
  struct XinputHid::XInputHidDevice *v57[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v58; // [rsp+70h] [rbp-90h] BYREF
  XinputHid::XinputHidInterface *v59; // [rsp+80h] [rbp-80h]
  struct XinputHid::XInputHidDevice *v60[2]; // [rsp+88h] [rbp-78h] BYREF
  struct _RTL_CRITICAL_SECTION *v61; // [rsp+98h] [rbp-68h]
  __m128i v62; // [rsp+A0h] [rbp-60h] BYREF
  __m128i v63; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v64; // [rsp+C0h] [rbp-40h] BYREF
  int v65; // [rsp+C8h] [rbp-38h]
  HANDLE Handles[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v67[496]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v68[64]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _DWORD v69[192]; // [rsp+4D0h] [rbp+3D0h] BYREF
  struct _OVERLAPPED v70[64]; // [rsp+7D0h] [rbp+6D0h] BYREF
  bool v71[64]; // [rsp+FD0h] [rbp+ED0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1088h] [rbp+F88h]

  v59 = this;
  v2 = 0;
  v62 = 0;
  v3 = 0;
  v63 = 0;
  memset_0(v70, 0, sizeof(v70));
  memset_0(v67, 0, sizeof(v67));
  memset_0(v71, 0, sizeof(v71));
  memset_0(v69, 0, sizeof(v69));
  memset_0(v68, 0, sizeof(v68));
  Handles[0] = *((HANDLE *)this + 5);
  Handles[1] = *((HANDLE *)this + 6);
  *(_WORD *)v71 = 257;
  v4 = 2;
  for ( i = 2; i < 0x22; ++i )
  {
    EventW = (char *)CreateEventW(0, 1, 0, 0);
    v70[i].hEvent = EventW;
    if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::_FailFast_Hr(retaddr, 445, (__int64)retaddr, (const char *)0x8000FFFFLL, v54);
    Handles[i] = EventW;
  }
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  v61 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  v8 = (volatile signed __int32 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  v9 = v8;
  *(_QWORD *)&v58 = v8;
  while ( 1 )
  {
    while ( 1 )
    {
      *(_OWORD *)v60 = 0;
      *(_OWORD *)v57 = 0;
      EnterCriticalSection(v7);
      v56 = 0;
      if ( v8 )
      {
        v10 = *((_DWORD *)v8 + 2);
        while ( v10 )
        {
          v11 = v10;
          v10 = _InterlockedCompareExchange(v8 + 2, v10 + 1, v10);
          if ( v11 == v10 )
          {
            v56 = v2;
            break;
          }
        }
      }
      std::shared_ptr<XinputHid::XInputHidDevice>::operator=(v60, &v56);
      v12 = (volatile signed __int32 *)v56.m128i_i64[1];
      if ( v56.m128i_i64[1] )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(v56.m128i_i64[1] + 8)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( !_InterlockedDecrement(v12 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      v56 = 0;
      if ( v9 )
      {
        v13 = *((_DWORD *)v9 + 2);
        while ( v13 )
        {
          v14 = v13;
          v13 = _InterlockedCompareExchange(v9 + 2, v13 + 1, v13);
          if ( v14 == v13 )
          {
            v56 = v3;
            break;
          }
        }
      }
      std::shared_ptr<XinputHid::XInputHidDevice>::operator=(v57, &v56);
      v15 = (volatile signed __int32 *)v56.m128i_i64[1];
      if ( v56.m128i_i64[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v56.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      v16 = v60[0];
      v17 = v57[0];
      if ( !v57[0] || !v60[0] )
      {
        v18 = v59;
        v19 = (_QWORD *)*((_QWORD *)v59 + 13);
        v20 = (volatile signed __int32 *)v58;
        while ( 1 )
        {
          v19 = (_QWORD *)*v19;
          if ( v19 == *((_QWORD **)v18 + 13) )
          {
LABEL_70:
            *(_QWORD *)&v58 = v20;
            v2 = _mm_load_si128(&v62);
            v3 = _mm_load_si128(&v63);
            v7 = v61;
            v9 = (volatile signed __int32 *)v58;
            v4 = 2;
            break;
          }
          v21 = (_QWORD *)v19[6];
          if ( *v21 == 2 )
          {
            if ( !v16 )
            {
              v22 = v19[7];
              if ( v22 )
                _InterlockedIncrement((volatile signed __int32 *)(v22 + 12));
              else
                v21 = 0;
              v62.m128i_i64[0] = (__int64)v21;
              v23 = v8;
              v8 = (volatile signed __int32 *)v22;
              v62.m128i_i64[1] = v22;
              if ( v23 && !_InterlockedDecrement(v23 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
              v58 = 0;
              if ( v22 )
              {
                v24 = *(_DWORD *)(v22 + 8);
                while ( v24 )
                {
                  v25 = v24;
                  v24 = _InterlockedCompareExchange((volatile signed __int32 *)(v22 + 8), v24 + 1, v24);
                  if ( v25 == v24 )
                  {
                    *(_QWORD *)&v58 = v21;
                    *((_QWORD *)&v58 + 1) = v22;
                    break;
                  }
                }
              }
              std::shared_ptr<XinputHid::XInputHidDevice>::operator=(v60, &v58);
              v26 = (volatile signed __int32 *)*((_QWORD *)&v58 + 1);
              if ( *((_QWORD *)&v58 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v58 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
                  if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
                }
              }
              v27 = qword_18001A180++;
              v16 = v60[0];
              *((_QWORD *)v60[0] + 3) = v27;
LABEL_67:
              v18 = v59;
            }
LABEL_68:
            if ( v17 )
              goto LABEL_69;
          }
          else
          {
            if ( *v21 != 1 )
              goto LABEL_68;
            if ( !v17 )
            {
              v28 = v19[7];
              if ( v28 )
                _InterlockedIncrement((volatile signed __int32 *)(v28 + 12));
              else
                v21 = 0;
              v63.m128i_i64[0] = (__int64)v21;
              v29 = v20;
              v20 = (volatile signed __int32 *)v28;
              v63.m128i_i64[1] = v28;
              if ( v29 && !_InterlockedDecrement(v29 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
              v58 = 0;
              if ( v28 )
              {
                v30 = *(_DWORD *)(v28 + 8);
                while ( v30 )
                {
                  v31 = v30;
                  v30 = _InterlockedCompareExchange((volatile signed __int32 *)(v28 + 8), v30 + 1, v30);
                  if ( v31 == v30 )
                  {
                    *(_QWORD *)&v58 = v21;
                    *((_QWORD *)&v58 + 1) = v28;
                    break;
                  }
                }
              }
              std::shared_ptr<XinputHid::XInputHidDevice>::operator=(v57, &v58);
              v32 = (volatile signed __int32 *)*((_QWORD *)&v58 + 1);
              if ( *((_QWORD *)&v58 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v58 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
                  if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
                }
              }
              v33 = qword_18001A178++;
              v17 = v57[0];
              *((_QWORD *)v57[0] + 3) = v33;
              goto LABEL_67;
            }
LABEL_69:
            if ( v16 )
              goto LABEL_70;
          }
        }
      }
      v34 = 0;
      if ( v16 )
        v34 = !XinputHid::XinputHidInterface::IssueIoToXinputDriver(
                 v59,
                 v16,
                 v71,
                 v70,
                 v68,
                 (struct _GIP_SYSTEM_MANAGEMENT_BUTTONS *)v69,
                 2u,
                 0x10u,
                 *((_QWORD *)v16 + 3));
      if ( v17 )
      {
        v55 = *((_QWORD *)v17 + 3);
        v35 = v17;
        v36 = (HANDLE *)v59;
        v34 |= !XinputHid::XinputHidInterface::IssueIoToXinputDriver(
                  v59,
                  v35,
                  v71,
                  v70,
                  v68,
                  (struct _GIP_SYSTEM_MANAGEMENT_BUTTONS *)v69,
                  0x10u,
                  0x22u,
                  v55);
      }
      else
      {
        v36 = (HANDLE *)v59;
      }
      if ( !v34 )
        break;
      if ( v7 )
        LeaveCriticalSection(v7);
      v37 = (volatile signed __int32 *)v57[1];
      if ( v57[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v57[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
          if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
        }
      }
      v38 = (volatile signed __int32 *)v60[1];
      if ( v60[1] && _InterlockedExchangeAdd((volatile signed __int32 *)v60[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
        if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
      }
    }
    if ( v7 )
      LeaveCriticalSection(v7);
    v39 = (volatile signed __int32 *)v57[1];
    if ( v57[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v57[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
        if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
      }
    }
    v40 = (volatile signed __int32 *)v60[1];
    if ( v60[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v60[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
        if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
      }
    }
    WaitForMultipleObjects(0x22u, Handles, 0, 0xFFFFFFFF);
    if ( !WaitForSingleObject(v36[5], 0) )
      break;
    if ( !ResetEvent(v36[6]) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x22C,
        (int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
        v41);
    do
    {
      if ( v71[v4] && !WaitForSingleObject(v70[v4].hEvent, 0) )
      {
        if ( SLODWORD(v70[v4].Internal) < 0 )
        {
          *(_OWORD *)v57 = 0;
          EnterCriticalSection(v7);
          v60[0] = (struct XinputHid::XInputHidDevice *)v7;
          v56 = 0;
          if ( v4 >= 0x10 )
          {
            v44 = v58;
            if ( (_QWORD)v58 )
            {
              v45 = *(_DWORD *)(v58 + 8);
              while ( v45 )
              {
                v46 = v45;
                v45 = _InterlockedCompareExchange((volatile signed __int32 *)(v44 + 8), v45 + 1, v45);
                if ( v46 == v45 )
                {
                  v56 = v3;
                  break;
                }
              }
            }
          }
          else if ( v8 )
          {
            v42 = *((_DWORD *)v8 + 2);
            while ( v42 )
            {
              v43 = v42;
              v42 = _InterlockedCompareExchange(v8 + 2, v42 + 1, v42);
              if ( v43 == v42 )
              {
                v56 = v2;
                break;
              }
            }
          }
          std::shared_ptr<XinputHid::XInputHidDevice>::operator=(v57, &v56);
          v47 = (volatile signed __int32 *)v56.m128i_i64[1];
          if ( v56.m128i_i64[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v56.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
              if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
            }
          }
          v48 = v57[0];
          if ( v57[0] )
          {
            if ( v68[v4] != *((_QWORD *)v57[0] + 3) )
            {
              v56 = 0;
              std::shared_ptr<XinputHid::XInputHidDevice>::operator=(v57, &v56);
              v49 = (volatile signed __int32 *)v56.m128i_i64[1];
              if ( v56.m128i_i64[1] )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v56.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
                  if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
                }
              }
              v48 = v57[0];
            }
            if ( v48 )
              std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::erase(
                v36 + 12,
                *((_QWORD *)v48 + 2));
          }
          v64 = 0;
          v65 = 0;
          XinputHid::XinputHidInterface::FireSystemButtonEvent(
            (XinputHid::XinputHidInterface *)v36,
            (struct _GIP_SYSTEM_MANAGEMENT_BUTTONS *)&v64);
          if ( v7 )
            LeaveCriticalSection(v7);
          v50 = (volatile signed __int32 *)v57[1];
          if ( v57[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v57[1] + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
              if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
            }
          }
        }
        else
        {
          XinputHid::XinputHidInterface::FireSystemButtonEvent(
            (XinputHid::XinputHidInterface *)v36,
            (struct _GIP_SYSTEM_MANAGEMENT_BUTTONS *)&v69[3 * v4]);
        }
        if ( v4 >= 0x40uLL )
          _report_rangecheckfailure();
        v71[v4] = 0;
        *(_OWORD *)&v70[v4].Internal = 0;
        *((_OWORD *)&v70[0].Offset + 2 * v4) = 0;
        v51 = Handles[v4];
        v70[v4].hEvent = v51;
        if ( !ResetEvent(v51) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x26E,
            (int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
            v52);
      }
      ++v4;
    }
    while ( v4 < 0x22 );
    v9 = (volatile signed __int32 *)v58;
    v4 = 2;
  }
  do
  {
    if ( !CloseHandle(v70[v4].hEvent) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x27A,
        (int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
        v53);
    ++v4;
  }
  while ( v4 < 0x22 );
  if ( v9 && !_InterlockedDecrement(v9 + 3) )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
  if ( v8 && !_InterlockedDecrement(v8 + 3) )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
}

```

## disassembly

```asm
0x18000f5d4  push    rbp
0x18000f5d6  push    rbx
0x18000f5d7  push    rsi
0x18000f5d8  push    rdi
0x18000f5d9  push    r12
0x18000f5db  push    r13
0x18000f5dd  push    r14
0x18000f5df  push    r15
0x18000f5e1  lea     rbp, [rsp-0F48h]
0x18000f5e9  mov     eax, 1048h
0x18000f5ee  call    _alloca_probe
0x18000f5f3  sub     rsp, rax
0x18000f5f6  movaps  [rsp+1080h+var_50], xmm6
0x18000f5fe  movaps  [rsp+1080h+var_60], xmm7
0x18000f606  mov     rax, cs:__security_cookie
0x18000f60d  xor     rax, rsp
0x18000f610  mov     [rbp+0F80h+var_70], rax
0x18000f617  mov     r13, rcx
0x18000f61a  mov     [rbp+0F80h+var_1000], rcx
0x18000f61e  xorps   xmm6, xmm6
0x18000f621  movdqa  [rbp+0F80h+var_FE0], xmm6
0x18000f626  xorps   xmm7, xmm7
0x18000f629  movdqa  [rbp+0F80h+var_FD0], xmm7
0x18000f62e  xor     edx, edx; Val
0x18000f630  mov     r8d, 800h; Size
0x18000f636  lea     rcx, [rbp+0F80h+var_8B0]; void *
0x18000f63d  call    memset_0
0x18000f642  xor     edx, edx; Val
0x18000f644  mov     r8d, 1F0h; Size
0x18000f64a  lea     rcx, [rbp+0F80h+var_FA0]; void *
0x18000f64e  call    memset_0
0x18000f653  xor     edx, edx; Val
0x18000f655  lea     r8d, [rdx+40h]; Size
0x18000f659  lea     rcx, [rbp+0F80h+var_B0]; void *
0x18000f660  call    memset_0
0x18000f665  xor     edx, edx; Val
0x18000f667  mov     r8d, 300h; Size
0x18000f66d  lea     rcx, [rbp+0F80h+var_BB0]; void *
0x18000f674  call    memset_0
0x18000f679  xor     edx, edx; Val
0x18000f67b  mov     r8d, 200h; Size
0x18000f681  lea     rcx, [rbp+0F80h+var_DB0]; void *
0x18000f688  call    memset_0
0x18000f68d  mov     rax, [r13+28h]
0x18000f691  mov     [rbp+0F80h+Handles], rax
0x18000f695  mov     rax, [r13+30h]
0x18000f699  mov     [rbp+0F80h+var_FA8], rax
0x18000f69d  mov     word ptr [rbp+0F80h+var_B0], 101h
0x18000f6a6  mov     r14d, 2
0x18000f6ac  mov     ebx, r14d
0x18000f6af  xor     r9d, r9d; lpName
0x18000f6b2  xor     r8d, r8d; bInitialState
0x18000f6b5  lea     edx, [r9+1]; bManualReset
0x18000f6b9  xor     ecx, ecx; lpEventAttributes
0x18000f6bb  call    cs:__imp_CreateEventW
0x18000f6c1  mov     edx, ebx
0x18000f6c3  mov     ecx, ebx
0x18000f6c5  shl     rcx, 5
0x18000f6c9  mov     [rbp+rcx+0F80h+var_8B0.hEvent], rax
0x18000f6d1  lea     rcx, [rax-1]
0x18000f6d5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000f6d9  setnbe  cl
0x18000f6dc  mov     r8, [rbp+0F88h]; unsigned int
0x18000f6e3  test    cl, cl
0x18000f6e5  jnz     loc_18000FFCB
0x18000f6eb  mov     [rbp+rdx*8+0F80h+Handles], rax
0x18000f6f0  inc     ebx
0x18000f6f2  cmp     ebx, 22h ; '"'
0x18000f6f5  jb      short loc_18000F6AF
0x18000f6f7  lea     rdi, [r13+38h]
0x18000f6fb  mov     [rbp+0F80h+var_FE8], rdi
0x18000f6ff  movdqa  xmm0, xmm6
0x18000f703  psrldq  xmm0, 8
0x18000f708  movq    r12, xmm0
0x18000f70d  movdqa  xmm1, xmm7
0x18000f711  psrldq  xmm1, 8
0x18000f716  movq    rsi, xmm1
0x18000f71b  mov     qword ptr [rsp+1080h+var_1010], rsi
0x18000f720  or      r15d, 0FFFFFFFFh
0x18000f724  xorps   xmm0, xmm0
0x18000f727  movdqu  xmmword ptr [rbp+0F80h+var_FF8], xmm0
0x18000f72c  xorps   xmm1, xmm1
0x18000f72f  movdqu  xmmword ptr [rsp+1080h+var_1020], xmm1
0x18000f735  mov     rcx, rdi; lpCriticalSection
0x18000f738  call    cs:__imp_EnterCriticalSection
0x18000f73e  xorps   xmm0, xmm0
0x18000f741  movdqa  [rsp+1080h+var_1030], xmm0
0x18000f747  test    r12, r12
0x18000f74a  jz      short loc_18000F76B
0x18000f74c  mov     eax, [r12+8]
0x18000f751  jmp     short loc_18000F75F
0x18000f753  lea     ecx, [rax+1]
0x18000f756  lock cmpxchg [r12+8], ecx
0x18000f75d  jz      short loc_18000F765
0x18000f75f  test    eax, eax
0x18000f761  jnz     short loc_18000F753
0x18000f763  jmp     short loc_18000F76B
0x18000f765  movdqa  [rsp+1080h+var_1030], xmm6
0x18000f76b  lea     rdx, [rsp+1080h+var_1030]
0x18000f770  lea     rcx, [rbp+0F80h+var_FF8]
0x18000f774  call    ??4?$shared_ptr@UXInputHidDevice@XinputHid@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<XinputHid::XInputHidDevice>::operator=(std::shared_ptr<XinputHid::XInputHidDevice> &&)
0x18000f779  mov     rbx, qword ptr [rsp+1080h+var_1030+8]
0x18000f77e  test    rbx, rbx
0x18000f781  jz      short loc_18000F7BA
0x18000f783  mov     eax, r15d
0x18000f786  lock xadd [rbx+8], eax
0x18000f78b  add     eax, r15d
0x18000f78e  jnz     short loc_18000F7BA
0x18000f790  mov     rax, [rbx]
0x18000f793  mov     rcx, rbx
0x18000f796  mov     rax, [rax]
0x18000f799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f79e  mov     eax, r15d
0x18000f7a1  lock xadd [rbx+0Ch], eax
0x18000f7a6  add     eax, r15d
0x18000f7a9  jnz     short loc_18000F7BA
0x18000f7ab  mov     rax, [rbx]
0x18000f7ae  mov     rcx, rbx
0x18000f7b1  mov     rax, [rax+8]
0x18000f7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7ba  xorps   xmm0, xmm0
0x18000f7bd  movdqa  [rsp+1080h+var_1030], xmm0
0x18000f7c3  test    rsi, rsi
0x18000f7c6  jz      short loc_18000F7E3
0x18000f7c8  mov     eax, [rsi+8]
0x18000f7cb  jmp     short loc_18000F7D7
0x18000f7cd  lea     ecx, [rax+1]
0x18000f7d0  lock cmpxchg [rsi+8], ecx
0x18000f7d5  jz      short loc_18000F7DD
0x18000f7d7  test    eax, eax
0x18000f7d9  jnz     short loc_18000F7CD
0x18000f7db  jmp     short loc_18000F7E3
0x18000f7dd  movdqa  [rsp+1080h+var_1030], xmm7
0x18000f7e3  lea     rdx, [rsp+1080h+var_1030]
0x18000f7e8  lea     rcx, [rsp+1080h+var_1020]
0x18000f7ed  call    ??4?$shared_ptr@UXInputHidDevice@XinputHid@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<XinputHid::XInputHidDevice>::operator=(std::shared_ptr<XinputHid::XInputHidDevice> &&)
0x18000f7f2  mov     rbx, qword ptr [rsp+1080h+var_1030+8]
0x18000f7f7  test    rbx, rbx
0x18000f7fa  jz      short loc_18000F833
0x18000f7fc  mov     eax, r15d
0x18000f7ff  lock xadd [rbx+8], eax
0x18000f804  add     eax, r15d
0x18000f807  jnz     short loc_18000F833
0x18000f809  mov     rax, [rbx]
0x18000f80c  mov     rcx, rbx
0x18000f80f  mov     rax, [rax]
0x18000f812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f817  mov     eax, r15d
0x18000f81a  lock xadd [rbx+0Ch], eax
0x18000f81f  add     eax, r15d
0x18000f822  jnz     short loc_18000F833
0x18000f824  mov     rax, [rbx]
0x18000f827  mov     rcx, rbx
0x18000f82a  mov     rax, [rax+8]
0x18000f82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f833  mov     r15, [rbp+0F80h+var_FF8]
0x18000f837  mov     r13, [rsp+1080h+var_1020]
0x18000f83c  test    r13, r13
0x18000f83f  jz      short loc_18000F84A
0x18000f841  test    r15, r15
0x18000f844  jnz     loc_18000FA79
0x18000f84a  mov     rax, [rbp+0F80h+var_1000]
0x18000f84e  mov     rbx, [rax+68h]
0x18000f852  mov     rdi, qword ptr [rsp+1080h+var_1010]
0x18000f857  mov     rbx, [rbx]
0x18000f85a  cmp     rbx, [rax+68h]
0x18000f85e  jz      loc_18000FA5B
0x18000f864  mov     r14, [rbx+30h]
0x18000f868  cmp     qword ptr [r14], 2
0x18000f86c  jnz     loc_18000F958
0x18000f872  test    r15, r15
0x18000f875  jnz     loc_18000FA49
0x18000f87b  mov     rsi, [rbx+38h]
0x18000f87f  test    rsi, rsi
0x18000f882  jz      short loc_18000F88A
0x18000f884  lock inc dword ptr [rsi+0Ch]
0x18000f888  jmp     short loc_18000F88D
0x18000f88a  xor     r14d, r14d
0x18000f88d  mov     qword ptr [rbp+0F80h+var_FE0], r14
0x18000f891  mov     rcx, r12
0x18000f894  mov     r12, rsi
0x18000f897  mov     qword ptr [rbp+0F80h+var_FE0+8], rsi
0x18000f89b  or      r15d, 0FFFFFFFFh
0x18000f89f  test    rcx, rcx
0x18000f8a2  jz      short loc_18000F8BD
0x18000f8a4  mov     eax, r15d
0x18000f8a7  lock xadd [rcx+0Ch], eax
0x18000f8ac  add     eax, r15d
0x18000f8af  jnz     short loc_18000F8BD
0x18000f8b1  mov     rax, [rcx]
0x18000f8b4  mov     rax, [rax+8]
0x18000f8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8bd  xorps   xmm0, xmm0
0x18000f8c0  movdqu  [rsp+1080h+var_1010], xmm0
0x18000f8c6  test    rsi, rsi
0x18000f8c9  jz      short loc_18000F8EA
0x18000f8cb  mov     eax, [rsi+8]
0x18000f8ce  jmp     short loc_18000F8DA
0x18000f8d0  lea     ecx, [rax+1]
0x18000f8d3  lock cmpxchg [rsi+8], ecx
0x18000f8d8  jz      short loc_18000F8E0
0x18000f8da  test    eax, eax
0x18000f8dc  jnz     short loc_18000F8D0
0x18000f8de  jmp     short loc_18000F8EA
0x18000f8e0  mov     qword ptr [rsp+1080h+var_1010], r14
0x18000f8e5  mov     qword ptr [rsp+1080h+var_1010+8], rsi
0x18000f8ea  lea     rdx, [rsp+1080h+var_1010]
0x18000f8ef  lea     rcx, [rbp+0F80h+var_FF8]
0x18000f8f3  call    ??4?$shared_ptr@UXInputHidDevice@XinputHid@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<XinputHid::XInputHidDevice>::operator=(std::shared_ptr<XinputHid::XInputHidDevice> &&)
0x18000f8f8  mov     rsi, qword ptr [rsp+1080h+var_1010+8]
0x18000f8fd  test    rsi, rsi
0x18000f900  jz      short loc_18000F939
0x18000f902  mov     eax, r15d
0x18000f905  lock xadd [rsi+8], eax
0x18000f90a  add     eax, r15d
0x18000f90d  jnz     short loc_18000F939
0x18000f90f  mov     rax, [rsi]
0x18000f912  mov     rcx, rsi
0x18000f915  mov     rax, [rax]
0x18000f918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f91d  mov     eax, r15d
0x18000f920  lock xadd [rsi+0Ch], eax
0x18000f925  add     eax, r15d
0x18000f928  jnz     short loc_18000F939
0x18000f92a  mov     rax, [rsi]
0x18000f92d  mov     rcx, rsi
0x18000f930  mov     rax, [rax+8]
0x18000f934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f939  mov     rcx, cs:qword_18001A180
0x18000f940  lea     rax, [rcx+1]
0x18000f944  mov     cs:qword_18001A180, rax
0x18000f94b  mov     r15, [rbp+0F80h+var_FF8]
0x18000f94f  mov     [r15+18h], rcx
0x18000f953  jmp     loc_18000FA45
0x18000f958  cmp     qword ptr [r14], 1
0x18000f95c  jnz     loc_18000FA49
0x18000f962  test    r13, r13
0x18000f965  jnz     loc_18000FA52
0x18000f96b  mov     rsi, [rbx+38h]
0x18000f96f  test    rsi, rsi
0x18000f972  jz      short loc_18000F97A
0x18000f974  lock inc dword ptr [rsi+0Ch]
0x18000f978  jmp     short loc_18000F97D
0x18000f97a  xor     r14d, r14d
0x18000f97d  mov     qword ptr [rbp+0F80h+var_FD0], r14
0x18000f981  mov     rcx, rdi
0x18000f984  mov     rdi, rsi
0x18000f987  mov     qword ptr [rbp+0F80h+var_FD0+8], rsi
0x18000f98b  or      r13d, 0FFFFFFFFh
0x18000f98f  test    rcx, rcx
0x18000f992  jz      short loc_18000F9AD
0x18000f994  mov     eax, r13d
0x18000f997  lock xadd [rcx+0Ch], eax
0x18000f99c  add     eax, r13d
0x18000f99f  jnz     short loc_18000F9AD
0x18000f9a1  mov     rax, [rcx]
0x18000f9a4  mov     rax, [rax+8]
0x18000f9a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9ad  xorps   xmm0, xmm0
0x18000f9b0  movdqu  [rsp+1080h+var_1010], xmm0
0x18000f9b6  test    rsi, rsi
0x18000f9b9  jz      short loc_18000F9DA
0x18000f9bb  mov     eax, [rsi+8]
0x18000f9be  jmp     short loc_18000F9CA
0x18000f9c0  lea     ecx, [rax+1]
0x18000f9c3  lock cmpxchg [rsi+8], ecx
0x18000f9c8  jz      short loc_18000F9D0
0x18000f9ca  test    eax, eax
0x18000f9cc  jnz     short loc_18000F9C0
0x18000f9ce  jmp     short loc_18000F9DA
0x18000f9d0  mov     qword ptr [rsp+1080h+var_1010], r14
0x18000f9d5  mov     qword ptr [rsp+1080h+var_1010+8], rsi
0x18000f9da  lea     rdx, [rsp+1080h+var_1010]
0x18000f9df  lea     rcx, [rsp+1080h+var_1020]
0x18000f9e4  call    ??4?$shared_ptr@UXInputHidDevice@XinputHid@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<XinputHid::XInputHidDevice>::operator=(std::shared_ptr<XinputHid::XInputHidDevice> &&)
0x18000f9e9  mov     rsi, qword ptr [rsp+1080h+var_1010+8]
0x18000f9ee  test    rsi, rsi
0x18000f9f1  jz      short loc_18000FA2A
0x18000f9f3  mov     eax, r13d
0x18000f9f6  lock xadd [rsi+8], eax
0x18000f9fb  add     eax, r13d
0x18000f9fe  jnz     short loc_18000FA2A
0x18000fa00  mov     rax, [rsi]
0x18000fa03  mov     rcx, rsi
0x18000fa06  mov     rax, [rax]
0x18000fa09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa0e  mov     eax, r13d
0x18000fa11  lock xadd [rsi+0Ch], eax
0x18000fa16  add     eax, r13d
0x18000fa19  jnz     short loc_18000FA2A
0x18000fa1b  mov     rax, [rsi]
0x18000fa1e  mov     rcx, rsi
0x18000fa21  mov     rax, [rax+8]
0x18000fa25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa2a  mov     rcx, cs:qword_18001A178
0x18000fa31  lea     rax, [rcx+1]
0x18000fa35  mov     cs:qword_18001A178, rax
0x18000fa3c  mov     r13, [rsp+1080h+var_1020]
0x18000fa41  mov     [r13+18h], rcx
0x18000fa45  mov     rax, [rbp+0F80h+var_1000]
  ... truncated ...
```
