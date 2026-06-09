# Persistence_AudioInterfaceRemoval(ushort const *)

- ea: `0x18002f6f0`
- end: `0x18002fd23`
- name: `?Persistence_AudioInterfaceRemoval@@YAJPEBG@Z`
- size: `1587`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180043b50`

## callees

- `0x180010da8`
- `0x18001ff7c`
- `0x18002f6f0`
- `0x180030f6c`
- `0x18003e920`
- `0x18003edc0`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f7d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f88a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f93f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fa00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fb4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f7d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f88a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f93f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fa00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fb4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f724`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f724`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fac1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002fac1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fab0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f960`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f973`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f973`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002fa52`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002fa52`
- `ntdll!EtwEventWriteTransfer` at `0x18002fc62`
- `ntdll!EtwEventWriteTransfer` at `0x18002fc62`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002fcc3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002fcc3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002fcb4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002fcb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f786`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f83e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f96b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f9b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002faff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f786`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f83e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f96b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f9b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002faff`

## string_xrefs

- `0x18002f76b`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18002f823`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18002f8d8`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18002f999`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18002fc8c`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18002fcdc`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Persistence_AudioInterfaceRemoval(const unsigned __int16 *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 (__fastcall *v5)(__int64, const unsigned __int16 *, __int64 *); // rdi
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 (__fastcall *v10)(__int64, LPVOID *); // r14
  int v11; // eax
  unsigned int v12; // ebx
  _QWORD *v13; // r14
  _QWORD *v14; // rsi
  _QWORD *v15; // rdi
  _QWORD *v16; // rbx
  __int64 v17; // r15
  HANDLE ProcessHeap; // rax
  _QWORD *v19; // rax
  void *v20; // rcx
  __int64 v21; // rbx
  _QWORD *v22; // rax
  __int64 v23; // r10
  const WCHAR *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // eax
  struct _TP_TIMER *v28; // rcx
  __int64 v29; // rdx
  bool v30; // r8
  int v31; // eax
  int lpString2; // [rsp+20h] [rbp-89h]
  LPVOID pv; // [rsp+30h] [rbp-79h] BYREF
  __int64 v34; // [rsp+38h] [rbp-71h] BYREF
  __int64 v35; // [rsp+40h] [rbp-69h] BYREF
  __int64 v36; // [rsp+48h] [rbp-61h] BYREF
  int v37; // [rsp+50h] [rbp-59h] BYREF
  struct _RTL_CRITICAL_SECTION *v38; // [rsp+58h] [rbp-51h]
  _DWORD v39[2]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v40; // [rsp+68h] [rbp-41h]
  unsigned __int16 *v41; // [rsp+70h] [rbp-39h] BYREF
  int v42; // [rsp+78h] [rbp-31h]
  int v43; // [rsp+7Ch] [rbp-2Dh]
  __int16 *v44; // [rsp+80h] [rbp-29h]
  int v45; // [rsp+88h] [rbp-21h]
  int v46; // [rsp+8Ch] [rbp-1Dh]
  const WCHAR *v47; // [rsp+90h] [rbp-19h]
  int v48; // [rsp+98h] [rbp-11h]
  int v49; // [rsp+9Ch] [rbp-Dh]
  int *v50; // [rsp+A0h] [rbp-9h]
  __int64 v51; // [rsp+A8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  EnterCriticalSection(&g_PersistedControlListLock);
  v38 = &g_PersistedControlListLock;
  v35 = 0;
  v34 = 0;
  pv = 0;
  v36 = 0;
  v2 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))g_DeviceEnumerator->lpVtbl->QueryInterface)(
         g_DeviceEnumerator,
         &GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0,
         &v36);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v5 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v36 + 40LL);
    v35 = 0;
    v6 = v5(v36, a1, &v35);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v34 = 0;
      v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v35)(
             v35,
             &GUID_d666063f_1587_4e43_81f1_b948e807363f,
             &v34);
      v9 = v8;
      if ( v8 >= 0 )
      {
        v10 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v34 + 40LL);
        pv = 0;
        v11 = v10(v34, &pv);
        v12 = v11;
        if ( v11 >= 0 )
        {
          v13 = 0;
          v14 = 0;
          v15 = g_PersistedControlList;
          while ( 1 )
          {
            v16 = v15;
            if ( !v15 )
              break;
            v17 = v15[2];
            v15 = (_QWORD *)*v15;
            if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v17 + 72), -1, (PCNZWCH)pv, -1) == 2 )
            {
              if ( v16 == g_PersistedControlList )
                g_PersistedControlList = (void *)*v16;
              else
                *(_QWORD *)v16[1] = *v16;
              if ( v16 == (_QWORD *)qword_180086748 )
                qword_180086748 = v16[1];
              else
                *(_QWORD *)(*v16 + 8LL) = v16[1];
              --dword_180086750;
              *v16 = 0;
              v16[1] = 0;
              operator delete(v16, 0x18u);
              ProcessHeap = GetProcessHeap();
              v19 = HeapAlloc(ProcessHeap, 0, 0x18u);
              if ( v19 )
              {
                v19[2] = v17;
                v19[1] = v14;
                *v19 = 0;
                if ( v14 )
                  *v14 = v19;
                else
                  v13 = v19;
                v14 = v19;
              }
            }
          }
          if ( pv )
            CoTaskMemFree(pv);
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          if ( v34 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          if ( v35 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          LeaveCriticalSection(&g_PersistedControlListLock);
          while ( v13 )
          {
            v20 = v13;
            v21 = v13[2];
            v22 = (_QWORD *)*v13;
            v13 = v22;
            if ( v22 )
              v22[1] = 0;
            operator delete(v20, 0x18u);
            v23 = *((_QWORD *)AudioEndpointBuilderTelemetryProvider::Instance() + 1);
            if ( *(_DWORD *)v23 > 4u )
            {
              v37 = *(_DWORD *)(v21 + 64);
              v24 = *(const WCHAR **)(v21 + 72);
              v50 = &v37;
              v51 = 4;
              if ( v24 )
              {
                v25 = -1;
                do
                  ++v25;
                while ( v24[v25] );
                v26 = 2 * v25 + 2;
              }
              else
              {
                v24 = &LocaleName;
                v26 = 2;
              }
              v47 = v24;
              v48 = v26;
              v49 = 0;
              v39[0] = 184549376;
              v39[1] = 4;
              v40 = 0;
              v41 = *(unsigned __int16 **)(v23 + 8);
              v42 = *v41;
              v43 = 2;
              v44 = word_18007794A;
              v45 = 80;
              v46 = 1;
              LODWORD(v38) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EtwEventWriteTransfer(*(_QWORD *)(v23 + 32), v39, 0, 0, 4, &v41);
            }
            if ( *(_DWORD *)(v21 + 88) )
            {
              v27 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v21 + 80) + 120LL))(
                      *(_QWORD *)(v21 + 80),
                      v21);
              if ( v27 >= 0 )
                *(_DWORD *)(v21 + 88) = 0;
              else
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1AD,
                  (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
                  (const char *)(unsigned int)v27,
                  lpString2);
            }
            v28 = *(struct _TP_TIMER **)(v21 + 56);
            if ( v28 )
            {
              SetThreadpoolTimer(v28, 0, 0, 0);
              WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(v21 + 56), 1);
              v31 = CPersistedControl::SavePersistedState((CPersistedControl *)v21, v29, v30);
              if ( v31 < 0 )
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x21A,
                  (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
                  (const char *)(unsigned int)v31,
                  lpString2);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          }
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB4,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
            (const char *)(unsigned int)v11,
            lpString2);
          if ( pv )
            CoTaskMemFree(pv);
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          if ( v34 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          if ( v35 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          LeaveCriticalSection(&g_PersistedControlListLock);
          return v12;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB3,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
          (const char *)(unsigned int)v8,
          lpString2);
        if ( v36 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        if ( v34 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        if ( v35 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        LeaveCriticalSection(&g_PersistedControlListLock);
        return v9;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
        (const char *)(unsigned int)v6,
        lpString2);
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      LeaveCriticalSection(&g_PersistedControlListLock);
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)(unsigned int)v2,
      lpString2);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    LeaveCriticalSection(&g_PersistedControlListLock);
    return v3;
  }
}

```

## disassembly

```asm
0x18002f6f0  push    rbp
0x18002f6f2  push    rbx
0x18002f6f3  push    rsi
0x18002f6f4  push    rdi
0x18002f6f5  push    r12
0x18002f6f7  push    r13
0x18002f6f9  push    r14
0x18002f6fb  push    r15
0x18002f6fd  lea     rbp, [rsp-1Fh]
0x18002f702  sub     rsp, 0C8h
0x18002f709  mov     rax, cs:__security_cookie
0x18002f710  xor     rax, rsp
0x18002f713  mov     [rbp+57h+var_50], rax
0x18002f717  mov     rsi, rcx
0x18002f71a  lea     r13, ?g_PersistedControlListLock@@3Vcritical_section@wil@@A; wil::critical_section g_PersistedControlListLock
0x18002f721  mov     rcx, r13; lpCriticalSection
0x18002f724  call    cs:__imp_EnterCriticalSection
0x18002f72a  mov     [rbp+57h+var_A8], r13
0x18002f72e  xor     r12d, r12d
0x18002f731  mov     [rbp+57h+var_C0], r12
0x18002f735  mov     [rbp+57h+var_C8], r12
0x18002f739  mov     [rbp+57h+pv], r12
0x18002f73d  mov     [rbp+57h+var_B8], r12
0x18002f741  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18002f748  mov     rax, [rcx]
0x18002f74b  lea     r8, [rbp+57h+var_B8]
0x18002f74f  lea     rdx, _GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0
0x18002f756  mov     rax, [rax]
0x18002f759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f75e  mov     ebx, eax
0x18002f760  test    eax, eax
0x18002f762  jns     short loc_18002F7DF
0x18002f764  mov     rcx, [rbp+5Fh]; this
0x18002f768  mov     r9d, eax; char *
0x18002f76b  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x18002f772  mov     edx, 0B1h; void *
0x18002f777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f77c  nop
0x18002f77d  mov     rcx, [rbp+57h+pv]; pv
0x18002f781  test    rcx, rcx
0x18002f784  jz      short loc_18002F78D
0x18002f786  call    cs:__imp_CoTaskMemFree
0x18002f78c  nop
0x18002f78d  mov     rcx, [rbp+57h+var_B8]
0x18002f791  test    rcx, rcx
0x18002f794  jz      short loc_18002F7A3
0x18002f796  mov     rax, [rcx]
0x18002f799  mov     rax, [rax+10h]
0x18002f79d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7a2  nop
0x18002f7a3  mov     rcx, [rbp+57h+var_C8]
0x18002f7a7  test    rcx, rcx
0x18002f7aa  jz      short loc_18002F7B9
0x18002f7ac  mov     rax, [rcx]
0x18002f7af  mov     rax, [rax+10h]
0x18002f7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7b8  nop
0x18002f7b9  mov     rcx, [rbp+57h+var_C0]
0x18002f7bd  test    rcx, rcx
0x18002f7c0  jz      short loc_18002F7CF
0x18002f7c2  mov     rax, [rcx]
0x18002f7c5  mov     rax, [rax+10h]
0x18002f7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7ce  nop
0x18002f7cf  mov     rcx, r13; lpCriticalSection
0x18002f7d2  call    cs:__imp_LeaveCriticalSection
0x18002f7d8  mov     eax, ebx
0x18002f7da  jmp     loc_18002FD03
0x18002f7df  mov     rbx, [rbp+57h+var_B8]
0x18002f7e3  mov     rax, [rbx]
0x18002f7e6  mov     rdi, [rax+28h]
0x18002f7ea  mov     rcx, [rbp+57h+var_C0]
0x18002f7ee  mov     [rbp+57h+var_C0], r12
0x18002f7f2  test    rcx, rcx
0x18002f7f5  jz      short loc_18002F804
0x18002f7f7  mov     r8, [rcx]
0x18002f7fa  mov     rax, [r8+10h]
0x18002f7fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f803  nop
0x18002f804  lea     r8, [rbp+57h+var_C0]
0x18002f808  mov     rdx, rsi
0x18002f80b  mov     rcx, rbx
0x18002f80e  mov     rax, rdi
0x18002f811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f816  mov     ebx, eax
0x18002f818  test    eax, eax
0x18002f81a  jns     short loc_18002F897
0x18002f81c  mov     rcx, [rbp+5Fh]; this
0x18002f820  mov     r9d, eax; char *
0x18002f823  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x18002f82a  mov     edx, 0B2h; void *
0x18002f82f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f834  nop
0x18002f835  mov     rcx, [rbp+57h+pv]; pv
0x18002f839  test    rcx, rcx
0x18002f83c  jz      short loc_18002F845
0x18002f83e  call    cs:__imp_CoTaskMemFree
0x18002f844  nop
0x18002f845  mov     rcx, [rbp+57h+var_B8]
0x18002f849  test    rcx, rcx
0x18002f84c  jz      short loc_18002F85B
0x18002f84e  mov     rax, [rcx]
0x18002f851  mov     rax, [rax+10h]
0x18002f855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f85a  nop
0x18002f85b  mov     rcx, [rbp+57h+var_C8]
0x18002f85f  test    rcx, rcx
0x18002f862  jz      short loc_18002F871
0x18002f864  mov     rax, [rcx]
0x18002f867  mov     rax, [rax+10h]
0x18002f86b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f870  nop
0x18002f871  mov     rcx, [rbp+57h+var_C0]
0x18002f875  test    rcx, rcx
0x18002f878  jz      short loc_18002F887
0x18002f87a  mov     rax, [rcx]
0x18002f87d  mov     rax, [rax+10h]
0x18002f881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f886  nop
0x18002f887  mov     rcx, r13; lpCriticalSection
0x18002f88a  call    cs:__imp_LeaveCriticalSection
0x18002f890  mov     eax, ebx
0x18002f892  jmp     loc_18002FD03
0x18002f897  mov     rcx, [rbp+57h+var_C8]
0x18002f89b  mov     [rbp+57h+var_C8], r12
0x18002f89f  test    rcx, rcx
0x18002f8a2  jz      short loc_18002F8B1
0x18002f8a4  mov     rax, [rcx]
0x18002f8a7  mov     rax, [rax+10h]
0x18002f8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8b0  nop
0x18002f8b1  mov     rcx, [rbp+57h+var_C0]
0x18002f8b5  mov     rax, [rcx]
0x18002f8b8  lea     r8, [rbp+57h+var_C8]
0x18002f8bc  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x18002f8c3  mov     rax, [rax]
0x18002f8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8cb  mov     ebx, eax
0x18002f8cd  test    eax, eax
0x18002f8cf  jns     short loc_18002F94C
0x18002f8d1  mov     rcx, [rbp+5Fh]; this
0x18002f8d5  mov     r9d, eax; char *
0x18002f8d8  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x18002f8df  mov     edx, 0B3h; void *
0x18002f8e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f8e9  nop
0x18002f8ea  mov     rcx, [rbp+57h+pv]; pv
0x18002f8ee  test    rcx, rcx
0x18002f8f1  jz      short loc_18002F8FA
0x18002f8f3  call    cs:__imp_CoTaskMemFree
0x18002f8f9  nop
0x18002f8fa  mov     rcx, [rbp+57h+var_B8]
0x18002f8fe  test    rcx, rcx
0x18002f901  jz      short loc_18002F910
0x18002f903  mov     rax, [rcx]
0x18002f906  mov     rax, [rax+10h]
0x18002f90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f90f  nop
0x18002f910  mov     rcx, [rbp+57h+var_C8]
0x18002f914  test    rcx, rcx
0x18002f917  jz      short loc_18002F926
0x18002f919  mov     rax, [rcx]
0x18002f91c  mov     rax, [rax+10h]
0x18002f920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f925  nop
0x18002f926  mov     rcx, [rbp+57h+var_C0]
0x18002f92a  test    rcx, rcx
0x18002f92d  jz      short loc_18002F93C
0x18002f92f  mov     rax, [rcx]
0x18002f932  mov     rax, [rax+10h]
0x18002f936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f93b  nop
0x18002f93c  mov     rcx, r13; lpCriticalSection
0x18002f93f  call    cs:__imp_LeaveCriticalSection
0x18002f945  mov     eax, ebx
0x18002f947  jmp     loc_18002FD03
0x18002f94c  mov     rsi, [rbp+57h+var_C8]
0x18002f950  mov     rax, [rsi]
0x18002f953  mov     r14, [rax+28h]
0x18002f957  mov     rdi, [rbp+57h+pv]
0x18002f95b  test    rdi, rdi
0x18002f95e  jz      short loc_18002F979
0x18002f960  call    cs:__imp_GetLastError
0x18002f966  mov     ebx, eax
0x18002f968  mov     rcx, rdi; pv
0x18002f96b  call    cs:__imp_CoTaskMemFree
0x18002f971  mov     ecx, ebx; dwErrCode
0x18002f973  call    cs:__imp_SetLastError
0x18002f979  mov     [rbp+57h+pv], r12
0x18002f97d  lea     rdx, [rbp+57h+pv]
0x18002f981  mov     rcx, rsi
0x18002f984  mov     rax, r14
0x18002f987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f98c  mov     ebx, eax
0x18002f98e  test    eax, eax
0x18002f990  jns     short loc_18002FA0D
0x18002f992  mov     rcx, [rbp+5Fh]; this
0x18002f996  mov     r9d, eax; char *
0x18002f999  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x18002f9a0  mov     edx, 0B4h; void *
0x18002f9a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f9aa  nop
0x18002f9ab  mov     rcx, [rbp+57h+pv]; pv
0x18002f9af  test    rcx, rcx
0x18002f9b2  jz      short loc_18002F9BB
0x18002f9b4  call    cs:__imp_CoTaskMemFree
0x18002f9ba  nop
0x18002f9bb  mov     rcx, [rbp+57h+var_B8]
0x18002f9bf  test    rcx, rcx
0x18002f9c2  jz      short loc_18002F9D1
0x18002f9c4  mov     rax, [rcx]
0x18002f9c7  mov     rax, [rax+10h]
0x18002f9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9d0  nop
0x18002f9d1  mov     rcx, [rbp+57h+var_C8]
0x18002f9d5  test    rcx, rcx
0x18002f9d8  jz      short loc_18002F9E7
0x18002f9da  mov     rax, [rcx]
0x18002f9dd  mov     rax, [rax+10h]
0x18002f9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9e6  nop
0x18002f9e7  mov     rcx, [rbp+57h+var_C0]
0x18002f9eb  test    rcx, rcx
0x18002f9ee  jz      short loc_18002F9FD
0x18002f9f0  mov     rax, [rcx]
0x18002f9f3  mov     rax, [rax+10h]
0x18002f9f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9fc  nop
0x18002f9fd  mov     rcx, r13; lpCriticalSection
0x18002fa00  call    cs:__imp_LeaveCriticalSection
0x18002fa06  mov     eax, ebx
0x18002fa08  jmp     loc_18002FD03
0x18002fa0d  mov     r14, r12
0x18002fa10  mov     rsi, r12
0x18002fa13  mov     rdi, cs:?g_PersistedControlList@@3V?$TList@VCPersistedControl@@@@A; TList<CPersistedControl> g_PersistedControlList
0x18002fa1a  mov     rbx, rdi
0x18002fa1d  test    rdi, rdi
0x18002fa20  jz      loc_18002FAF6
0x18002fa26  mov     r15, [rdi+10h]
0x18002fa2a  mov     rdi, [rdi]
0x18002fa2d  mov     rax, [rbp+57h+pv]
0x18002fa31  mov     [rsp+100h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002fa39  mov     [rsp+100h+lpString2], rax; lpString2
0x18002fa3e  mov     r9d, 0FFFFFFFFh; cchCount1
0x18002fa44  mov     r8, [r15+48h]; lpString1
0x18002fa48  mov     edx, 1; dwCmpFlags
0x18002fa4d  mov     ecx, 7Fh; Locale
0x18002fa52  call    cs:__imp_CompareStringW
0x18002fa58  cmp     eax, 2
0x18002fa5b  jnz     short loc_18002FA1A
0x18002fa5d  mov     rcx, [rbx]
0x18002fa60  cmp     rbx, cs:?g_PersistedControlList@@3V?$TList@VCPersistedControl@@@@A; TList<CPersistedControl> g_PersistedControlList
0x18002fa67  jnz     short loc_18002FA72
0x18002fa69  mov     cs:?g_PersistedControlList@@3V?$TList@VCPersistedControl@@@@A, rcx; TList<CPersistedControl> g_PersistedControlList
0x18002fa70  jmp     short loc_18002FA79
0x18002fa72  mov     rax, [rbx+8]
0x18002fa76  mov     [rax], rcx
0x18002fa79  mov     rcx, [rbx+8]
0x18002fa7d  cmp     rbx, cs:qword_180086748
0x18002fa84  jnz     short loc_18002FA8F
0x18002fa86  mov     cs:qword_180086748, rcx
0x18002fa8d  jmp     short loc_18002FA96
0x18002fa8f  mov     rax, [rbx]
0x18002fa92  mov     [rax+8], rcx
0x18002fa96  dec     cs:dword_180086750
0x18002fa9c  mov     [rbx], r12
0x18002fa9f  mov     [rbx+8], r12
0x18002faa3  mov     edx, 18h; unsigned __int64
0x18002faa8  mov     rcx, rbx; void *
0x18002faab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fab0  call    cs:__imp_GetProcessHeap
0x18002fab6  mov     rcx, rax; hHeap
0x18002fab9  xor     edx, edx; dwFlags
0x18002fabb  mov     r8d, 18h; dwBytes
0x18002fac1  call    cs:__imp_HeapAlloc
0x18002fac7  test    rax, rax
0x18002faca  jz      loc_18002FA1A
0x18002fad0  mov     [rax+10h], r15
0x18002fad4  mov     [rax+8], rsi
0x18002fad8  mov     [rax], r12
0x18002fadb  test    rsi, rsi
0x18002fade  jnz     short loc_18002FAEB
0x18002fae0  mov     r14, rax
0x18002fae3  mov     rsi, rax
0x18002fae6  jmp     loc_18002FA1A
0x18002faeb  mov     [rsi], rax
0x18002faee  mov     rsi, rax
0x18002faf1  jmp     loc_18002FA1A
0x18002faf6  mov     rcx, [rbp+57h+pv]; pv
0x18002fafa  test    rcx, rcx
0x18002fafd  jz      short loc_18002FB06
0x18002faff  call    cs:__imp_CoTaskMemFree
0x18002fb05  nop
0x18002fb06  mov     rcx, [rbp+57h+var_B8]
0x18002fb0a  test    rcx, rcx
0x18002fb0d  jz      short loc_18002FB1C
0x18002fb0f  mov     rax, [rcx]
0x18002fb12  mov     rax, [rax+10h]
0x18002fb16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb1b  nop
  ... truncated ...
```
