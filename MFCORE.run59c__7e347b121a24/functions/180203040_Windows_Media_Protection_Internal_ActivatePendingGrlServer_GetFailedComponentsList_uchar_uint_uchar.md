# Windows::Media::Protection::Internal::ActivatePendingGrlServer::GetFailedComponentsList(uchar,uint *,uchar * *)

- ea: `0x180203040`
- end: `0x1802035ad`
- name: `?GetFailedComponentsList@ActivatePendingGrlServer@Internal@Protection@Media@Windows@@UEAAJEPEAIPEAPEAE@Z`
- size: `1389`
- prototype: `int(Windows::Media::Protection::Internal::ActivatePendingGrlServer *__hidden this, unsigned __int8, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800402c0`
- `0x1800ec0e0`
- `0x180111d68`
- `0x180203040`
- `0x1802035b4`
- `0x18027a218`
- `0x1803143bc`
- `0x180344ce4`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180203131`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180203364`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180203579`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180203131`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180203364`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180203579`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020358d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020358d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180203146`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180203146`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180203378`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180203378`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180203561`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180203561`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802030c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18020316f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180203214`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802032b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802033a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180203439`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802034e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802030c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18020316f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180203214`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802032b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802033a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180203439`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802034e1`

## string_xrefs

- `0x1802031d3`: `Windows::Media::Protection::Internal::ActivatePendingGrlServer::GetFailedComponentsList`
- `0x1802034a5`: `Windows::Media::Protection::Internal::ActivatePendingGrlServer::GetFailedComponentsList`
- `0x18020353f`: `Windows::Media::Protection::Internal::ActivatePendingGrlServer::GetFailedComponentsList`

## pseudocode

```c
__int64 __fastcall Windows::Media::Protection::Internal::ActivatePendingGrlServer::GetFailedComponentsList(
        Windows::Media::Protection::Internal::ActivatePendingGrlServer *this,
        __int64 a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  struct _PEAUTH_COMPONENT_HASH_INFO *v6; // rdi
  __int64 v7; // rdx
  int ComponentList; // ebx
  __int64 v9; // r8
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v13; // r8d
  HANDLE ProcessHeap; // rax
  struct _PEAUTH_COMPONENT_HASH_INFO *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  __int64 v20; // rdx
  void *v21; // rcx
  __int64 v22; // r8
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  size_t v25; // rsi
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  HANDLE v30; // rax
  SIZE_T v31; // rax
  __int64 v32; // rdx
  void *v33; // rcx
  __int64 v34; // r8
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  int v38; // r8d
  size_t v39; // rsi
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  HANDLE v47; // rax
  _QWORD v49[5]; // [rsp+20h] [rbp-28h] BYREF
  SIZE_T dwBytes; // [rsp+A0h] [rbp+58h] BYREF

  v6 = 0;
  if ( a3 && a4 )
  {
    *a4 = 0;
    *a3 = 0;
    if ( (_BYTE)a2 )
    {
      LODWORD(dwBytes) = 0;
      v49[0] = 0;
      v49[2] = 0;
      ComponentList = CPEAuthHandShake::GetComponentList((CPEAuthHandShake *)v49, 0, 0, (unsigned int *)&dwBytes);
      if ( (int)(ComponentList + 0x80000000) >= 0 && ComponentList != -1072860816 )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v9);
          CallStackTracing::s_wpInstance = v11;
          if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
          {
            v10 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v10 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( !*((_BYTE *)v10 + 8) )
          goto LABEL_24;
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)ThreadRelativeContext + 499) == ComponentList )
          goto LABEL_24;
        v13 = 85;
LABEL_23:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "Windows::Media::Protection::Internal::ActivatePendingGrlServer::GetFailedComponentsList",
          v13,
          ComponentList);
LABEL_24:
        CPEAuthHandShake::Close((CPEAuthHandShake *)v49);
        goto LABEL_76;
      }
      ProcessHeap = GetProcessHeap();
      v15 = (struct _PEAUTH_COMPONENT_HASH_INFO *)HeapAlloc(ProcessHeap, 0, (unsigned int)dwBytes);
      v6 = v15;
      if ( !v15 )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        ComponentList = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( !*((_BYTE *)v18 + 8) )
          goto LABEL_24;
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)ThreadRelativeContext + 499) == -2147024882 )
          goto LABEL_24;
        v13 = 89;
        goto LABEL_23;
      }
      ComponentList = CPEAuthHandShake::GetComponentList((CPEAuthHandShake *)v49, 0, v15, (unsigned int *)&dwBytes);
      if ( ComponentList < 0 )
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( !*((_BYTE *)v23 + 8) )
          goto LABEL_24;
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)ThreadRelativeContext + 499) == ComponentList )
          goto LABEL_24;
        v13 = 96;
        goto LABEL_23;
      }
      v25 = (unsigned int)dwBytes;
      if ( (_DWORD)dwBytes )
      {
        ComponentList = CTCoAllocPolicy::Alloc(v21, 1u, (unsigned int)dwBytes, (void **)a4);
        if ( ComponentList >= 0 )
        {
          memcpy_0(*a4, v6, v25);
          *a3 = v25;
          v6 = (struct _PEAUTH_COMPONENT_HASH_INFO *)_InterlockedExchange64(
                                                       (volatile __int64 *)&g_cachedComponentList,
                                                       (__int64)v6);
          CPEAuthHandShake::Close((CPEAuthHandShake *)v49);
          goto LABEL_78;
        }
        v28 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( !*((_BYTE *)v28 + 8) )
          goto LABEL_24;
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)ThreadRelativeContext + 499) == ComponentList )
          goto LABEL_24;
        v13 = 107;
        goto LABEL_23;
      }
      ComponentList = 0;
      CPEAuthHandShake::Close((CPEAuthHandShake *)v49);
LABEL_79:
      v47 = GetProcessHeap();
      HeapFree(v47, 0, v6);
      return (unsigned int)ComponentList;
    }
    v6 = (struct _PEAUTH_COMPONENT_HASH_INFO *)_InterlockedExchange64((volatile __int64 *)&g_cachedComponentList, 0);
    ComponentList = 0;
    if ( !v6 )
      return (unsigned int)ComponentList;
    LODWORD(dwBytes) = 0;
    v30 = GetProcessHeap();
    v31 = HeapSize(v30, 0, v6);
    ComponentList = ULongLongToULong(v31, (unsigned int *)&dwBytes);
    if ( ComponentList >= 0 )
    {
      v39 = (unsigned int)dwBytes;
      ComponentList = CTCoAllocPolicy::Alloc(v33, 1u, (unsigned int)dwBytes, (void **)a4);
      if ( ComponentList >= 0 )
      {
        memcpy_0(*a4, v6, v39);
        *a3 = v39;
        goto LABEL_79;
      }
      v42 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41);
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v42 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( !*((_BYTE *)v42 + 8) )
        goto LABEL_76;
      v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
      if ( *((_DWORD *)v37 + 499) == ComponentList )
        goto LABEL_76;
      v38 = 129;
    }
    else
    {
      v35 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v34);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( !*((_BYTE *)v35 + 8) )
        goto LABEL_76;
      v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
      if ( *((_DWORD *)v37 + 499) == ComponentList )
        goto LABEL_76;
      v38 = 128;
    }
    CallStackContext::TraceFailure(
      v37,
      "Windows::Media::Protection::Internal::ActivatePendingGrlServer::GetFailedComponentsList",
      v38,
      ComponentList);
LABEL_76:
    if ( *a4 )
    {
      CoTaskMemFree(*a4);
      *a4 = 0;
      *a3 = 0;
    }
    goto LABEL_78;
  }
  v44 = (__int64 *)CallStackTracing::s_wpInstance;
  ComponentList = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, a2, a3);
    CallStackTracing::s_wpInstance = v45;
    if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
    {
      v44 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v44 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v44 + 8) )
  {
    v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
    if ( *((_DWORD *)v46 + 499) != -2147024809 )
      CallStackContext::TraceFailure(
        v46,
        "Windows::Media::Protection::Internal::ActivatePendingGrlServer::GetFailedComponentsList",
        64,
        -2147024809);
  }
  if ( a4 )
    goto LABEL_76;
LABEL_78:
  if ( v6 )
    goto LABEL_79;
  return (unsigned int)ComponentList;
}

```

## disassembly

```asm
0x180203040  push    rbp
0x180203042  push    rbx
0x180203043  push    rsi
0x180203044  push    rdi
0x180203045  push    r12
0x180203047  push    r13
0x180203049  push    r14
0x18020304b  push    r15
0x18020304d  mov     rbp, rsp
0x180203050  sub     rsp, 48h
0x180203054  xor     r13d, r13d
0x180203057  mov     r14, r9
0x18020305a  mov     r12, r8
0x18020305d  mov     edi, r13d
0x180203060  test    r8, r8
0x180203063  jz      loc_1802034D0
0x180203069  test    r9, r9
0x18020306c  jz      loc_1802034D0
0x180203072  mov     [r9], r13
0x180203075  mov     [r8], r13d
0x180203078  test    dl, dl
0x18020307a  jz      loc_18020334D
0x180203080  lea     r9, [rbp+dwBytes]; unsigned int *
0x180203084  mov     dword ptr [rbp+dwBytes], r13d
0x180203088  xor     r8d, r8d; struct _PEAUTH_COMPONENT_HASH_INFO *
0x18020308b  mov     [rbp+var_28], r13
0x18020308f  xor     edx, edx; unsigned int
0x180203091  mov     [rbp+var_18], r13
0x180203095  lea     rcx, [rbp+var_28]; this
0x180203099  call    ?GetComponentList@CPEAuthHandShake@@QEAAJKPEAU_PEAUTH_COMPONENT_HASH_INFO@@PEAK@Z; CPEAuthHandShake::GetComponentList(ulong,_PEAUTH_COMPONENT_HASH_INFO *,ulong *)
0x18020309e  mov     ecx, 80000000h
0x1802030a3  mov     ebx, eax
0x1802030a5  add     eax, ecx
0x1802030a7  test    ecx, eax
0x1802030a9  jnz     loc_180203131
0x1802030af  cmp     ebx, 0C00D7170h
0x1802030b5  jz      short loc_180203131
0x1802030b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802030be  test    rcx, rcx
0x1802030c1  jnz     short loc_18020310B
0x1802030c3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802030ca  nop     dword ptr [rax+rax+00h]
0x1802030cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802030d6  mov     rcx, rax
0x1802030d9  test    rax, rax
0x1802030dc  jz      short loc_1802030FD
0x1802030de  mov     rax, [rax]
0x1802030e1  mov     edx, 7F0h
0x1802030e6  mov     rax, [rax+8]
0x1802030ea  call    cs:__guard_dispatch_icall_fptr
0x1802030f0  test    eax, eax
0x1802030f2  jz      short loc_1802030FD
0x1802030f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802030fb  jmp     short loc_18020310B
0x1802030fd  lea     rcx, qword_1803CE250; this
0x180203104  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18020310b  cmp     [rcx+8], r13b
0x18020310f  jz      loc_1802031E2
0x180203115  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18020311a  cmp     [rax+7CCh], ebx
0x180203120  jz      loc_1802031E2
0x180203126  mov     r8d, 55h ; 'U'
0x18020312c  jmp     loc_1802031D0
0x180203131  call    cs:__imp_GetProcessHeap
0x180203138  nop     dword ptr [rax+rax+00h]
0x18020313d  mov     r8d, dword ptr [rbp+dwBytes]; dwBytes
0x180203141  xor     edx, edx; dwFlags
0x180203143  mov     rcx, rax; hHeap
0x180203146  call    cs:__imp_HeapAlloc
0x18020314d  nop     dword ptr [rax+rax+00h]
0x180203152  mov     rdi, rax
0x180203155  test    rax, rax
0x180203158  jnz     loc_1802031F0
0x18020315e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180203165  mov     ebx, 8007000Eh
0x18020316a  test    rcx, rcx
0x18020316d  jnz     short loc_1802031B7
0x18020316f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180203176  nop     dword ptr [rax+rax+00h]
0x18020317b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180203182  mov     rcx, rax
0x180203185  test    rax, rax
0x180203188  jz      short loc_1802031A9
0x18020318a  mov     rax, [rax]
0x18020318d  mov     edx, 7F0h
0x180203192  mov     rax, [rax+8]
0x180203196  call    cs:__guard_dispatch_icall_fptr
0x18020319c  test    eax, eax
0x18020319e  jz      short loc_1802031A9
0x1802031a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802031a7  jmp     short loc_1802031B7
0x1802031a9  lea     rcx, qword_1803CE250; this
0x1802031b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802031b7  cmp     [rcx+8], r13b
0x1802031bb  jz      short loc_1802031E2
0x1802031bd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802031c2  cmp     [rax+7CCh], ebx
0x1802031c8  jz      short loc_1802031E2
0x1802031ca  mov     r8d, 59h ; 'Y'; int
0x1802031d0  mov     r9d, ebx; int
0x1802031d3  lea     rdx, aWindowsMediaPr; "Windows::Media::Protection::Internal::A"...
0x1802031da  mov     rcx, rax; this
0x1802031dd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802031e2  lea     rcx, [rbp+var_28]; this
0x1802031e6  call    ?Close@CPEAuthHandShake@@QEAAXXZ; CPEAuthHandShake::Close(void)
0x1802031eb  jmp     loc_180203559
0x1802031f0  lea     r9, [rbp+dwBytes]; unsigned int *
0x1802031f4  mov     r8, rdi; struct _PEAUTH_COMPONENT_HASH_INFO *
0x1802031f7  xor     edx, edx; unsigned int
0x1802031f9  lea     rcx, [rbp+var_28]; this
0x1802031fd  call    ?GetComponentList@CPEAuthHandShake@@QEAAJKPEAU_PEAUTH_COMPONENT_HASH_INFO@@PEAK@Z; CPEAuthHandShake::GetComponentList(ulong,_PEAUTH_COMPONENT_HASH_INFO *,ulong *)
0x180203202  mov     ebx, eax
0x180203204  test    eax, eax
0x180203206  jns     short loc_18020327E
0x180203208  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18020320f  test    rcx, rcx
0x180203212  jnz     short loc_18020325C
0x180203214  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18020321b  nop     dword ptr [rax+rax+00h]
0x180203220  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180203227  mov     rcx, rax
0x18020322a  test    rax, rax
0x18020322d  jz      short loc_18020324E
0x18020322f  mov     rax, [rax]
0x180203232  mov     edx, 7F0h
0x180203237  mov     rax, [rax+8]
0x18020323b  call    cs:__guard_dispatch_icall_fptr
0x180203241  test    eax, eax
0x180203243  jz      short loc_18020324E
0x180203245  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18020324c  jmp     short loc_18020325C
0x18020324e  lea     rcx, qword_1803CE250; this
0x180203255  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18020325c  cmp     [rcx+8], r13b
0x180203260  jz      short loc_1802031E2
0x180203262  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180203267  cmp     [rax+7CCh], ebx
0x18020326d  jz      loc_1802031E2
0x180203273  mov     r8d, 60h ; '`'
0x180203279  jmp     loc_1802031D0
0x18020327e  mov     esi, dword ptr [rbp+dwBytes]
0x180203281  test    esi, esi
0x180203283  jnz     short loc_180203296
0x180203285  lea     rcx, [rbp+var_28]; this
0x180203289  mov     ebx, r13d
0x18020328c  call    ?Close@CPEAuthHandShake@@QEAAXXZ; CPEAuthHandShake::Close(void)
0x180203291  jmp     loc_180203579
0x180203296  mov     r9, r14; void **
0x180203299  mov     r8, rsi; unsigned __int64
0x18020329c  mov     edx, 1; unsigned int
0x1802032a1  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1802032a6  mov     ebx, eax
0x1802032a8  test    eax, eax
0x1802032aa  jns     short loc_180203326
0x1802032ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802032b3  test    rcx, rcx
0x1802032b6  jnz     short loc_180203300
0x1802032b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802032bf  nop     dword ptr [rax+rax+00h]
0x1802032c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802032cb  mov     rcx, rax
0x1802032ce  test    rax, rax
0x1802032d1  jz      short loc_1802032F2
0x1802032d3  mov     rax, [rax]
0x1802032d6  mov     edx, 7F0h
0x1802032db  mov     rax, [rax+8]
0x1802032df  call    cs:__guard_dispatch_icall_fptr
0x1802032e5  test    eax, eax
0x1802032e7  jz      short loc_1802032F2
0x1802032e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802032f0  jmp     short loc_180203300
0x1802032f2  lea     rcx, qword_1803CE250; this
0x1802032f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180203300  cmp     [rcx+8], r13b
0x180203304  jz      loc_1802031E2
0x18020330a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18020330f  cmp     [rax+7CCh], ebx
0x180203315  jz      loc_1802031E2
0x18020331b  mov     r8d, 6Bh ; 'k'
0x180203321  jmp     loc_1802031D0
0x180203326  mov     rcx, [r14]; void *
0x180203329  mov     r8, rsi; Size
0x18020332c  mov     rdx, rdi; Src
0x18020332f  call    memcpy_0
0x180203334  mov     [r12], esi
0x180203338  lea     rcx, [rbp+var_28]; this
0x18020333c  xchg    rdi, cs:?g_cachedComponentList@@3VCFreeComponentList@@A; CFreeComponentList g_cachedComponentList
0x180203343  call    ?Close@CPEAuthHandShake@@QEAAXXZ; CPEAuthHandShake::Close(void)
0x180203348  jmp     loc_180203574
0x18020334d  xchg    rdi, cs:?g_cachedComponentList@@3VCFreeComponentList@@A; CFreeComponentList g_cachedComponentList
0x180203354  mov     ebx, r13d
0x180203357  test    rdi, rdi
0x18020335a  jz      loc_180203599
0x180203360  mov     dword ptr [rbp+dwBytes], r13d
0x180203364  call    cs:__imp_GetProcessHeap
0x18020336b  nop     dword ptr [rax+rax+00h]
0x180203370  mov     r8, rdi; lpMem
0x180203373  xor     edx, edx; dwFlags
0x180203375  mov     rcx, rax; hHeap
0x180203378  call    cs:__imp_HeapSize
0x18020337f  nop     dword ptr [rax+rax+00h]
0x180203384  mov     rcx, rax; unsigned __int64
0x180203387  lea     rdx, [rbp+dwBytes]; unsigned int *
0x18020338b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180203390  mov     ebx, eax
0x180203392  test    eax, eax
0x180203394  jns     short loc_180203410
0x180203396  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18020339d  test    rcx, rcx
0x1802033a0  jnz     short loc_1802033EA
0x1802033a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802033a9  nop     dword ptr [rax+rax+00h]
0x1802033ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802033b5  mov     rcx, rax
0x1802033b8  test    rax, rax
0x1802033bb  jz      short loc_1802033DC
0x1802033bd  mov     rax, [rax]
0x1802033c0  mov     edx, 7F0h
0x1802033c5  mov     rax, [rax+8]
0x1802033c9  call    cs:__guard_dispatch_icall_fptr
0x1802033cf  test    eax, eax
0x1802033d1  jz      short loc_1802033DC
0x1802033d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802033da  jmp     short loc_1802033EA
0x1802033dc  lea     rcx, qword_1803CE250; this
0x1802033e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802033ea  cmp     [rcx+8], r13b
0x1802033ee  jz      loc_180203559
0x1802033f4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802033f9  cmp     [rax+7CCh], ebx
0x1802033ff  jz      loc_180203559
0x180203405  mov     r8d, 80h
0x18020340b  jmp     loc_1802034A2
0x180203410  mov     esi, dword ptr [rbp+dwBytes]
0x180203413  mov     r9, r14; void **
0x180203416  mov     r8d, esi; unsigned __int64
0x180203419  mov     edx, 1; unsigned int
0x18020341e  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180203423  mov     ebx, eax
0x180203425  test    eax, eax
0x180203427  jns     loc_1802034B9
0x18020342d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180203434  test    rcx, rcx
0x180203437  jnz     short loc_180203481
0x180203439  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180203440  nop     dword ptr [rax+rax+00h]
0x180203445  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18020344c  mov     rcx, rax
0x18020344f  test    rax, rax
0x180203452  jz      short loc_180203473
0x180203454  mov     rax, [rax]
0x180203457  mov     edx, 7F0h
0x18020345c  mov     rax, [rax+8]
0x180203460  call    cs:__guard_dispatch_icall_fptr
0x180203466  test    eax, eax
0x180203468  jz      short loc_180203473
0x18020346a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180203471  jmp     short loc_180203481
0x180203473  lea     rcx, qword_1803CE250; this
0x18020347a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180203481  cmp     [rcx+8], r13b
0x180203485  jz      loc_180203559
0x18020348b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180203490  cmp     [rax+7CCh], ebx
0x180203496  jz      loc_180203559
0x18020349c  mov     r8d, 81h; int
0x1802034a2  mov     r9d, ebx; int
0x1802034a5  lea     rdx, aWindowsMediaPr; "Windows::Media::Protection::Internal::A"...
0x1802034ac  mov     rcx, rax; this
0x1802034af  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802034b4  jmp     loc_180203559
0x1802034b9  mov     rcx, [r14]; void *
0x1802034bc  mov     r8, rsi; Size
0x1802034bf  mov     rdx, rdi; Src
0x1802034c2  call    memcpy_0
0x1802034c7  mov     [r12], esi
0x1802034cb  jmp     loc_180203579
0x1802034d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802034d7  mov     ebx, 80070057h
0x1802034dc  test    rcx, rcx
0x1802034df  jnz     short loc_180203529
0x1802034e1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802034e8  nop     dword ptr [rax+rax+00h]
0x1802034ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802034f4  mov     rcx, rax
0x1802034f7  test    rax, rax
0x1802034fa  jz      short loc_18020351B
0x1802034fc  mov     rax, [rax]
0x1802034ff  mov     edx, 7F0h
0x180203504  mov     rax, [rax+8]
0x180203508  call    cs:__guard_dispatch_icall_fptr
0x18020350e  test    eax, eax
0x180203510  jz      short loc_18020351B
0x180203512  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180203519  jmp     short loc_180203529
0x18020351b  lea     rcx, qword_1803CE250; this
0x180203522  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180203529  cmp     [rcx+8], r13b
0x18020352d  jz      short loc_180203554
0x18020352f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
  ... truncated ...
```
