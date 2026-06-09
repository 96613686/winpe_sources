# CReportCab::CreateWatsonUploadCab(CReport *,CReportCabStream *,long (*)(void *,unsigned __int64,unsigned __int64),void *,void *)

- ea: `0x18002bf34`
- end: `0x18002c163`
- name: `?CreateWatsonUploadCab@CReportCab@@QEAAJPEAVCReport@@PEAVCReportCabStream@@P6AJPEAX_K3@Z22@Z`
- size: `559`
- prototype: `__int64 __usercall@<rax>(CReportCab *__hidden this@<rcx>, struct CReport *@<rdx>, struct CReportCabStream *@<r8>, int (*)(void *, unsigned __int64, unsigned __int64)@<r9>, void *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003afa0`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x1800267cc`
- `0x18002bf34`
- `0x18002dbac`
- `0x180043d64`
- `0x18009d930`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002bfe9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c004`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002bfe9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002bf85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002bf97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c142`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002bf85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002bf97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002c142`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002bfa3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002c14e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002bfa3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002c14e`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18002bf8e`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18002bf8e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bfbe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002bfbe`

## pseudocode

```c
__int64 __fastcall CReportCab::CreateWatsonUploadCab(
        CReportCab *this,
        struct CReport *a2,
        struct CReportCabStream *a3,
        int (*a4)(void *, unsigned __int64, unsigned __int64),
        void *a5,
        HANDLE hHandle)
{
  HANDLE CurrentThread; // rax
  int ThreadPriority; // r15d
  HANDLE v12; // rax
  int v13; // edi
  _QWORD *v14; // rbx
  CZipArchiveFile *v15; // rax
  CZipArchiveFile *v16; // rax
  CCabArchiveFile *v17; // rax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // r9d
  unsigned int v22; // r8d
  __int64 v23; // rdx
  HANDLE v24; // rax

  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids);
    return 2147942487LL;
  }
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  v12 = GetCurrentThread();
  SetThreadPriority(v12, -1);
  if ( hHandle )
  {
    *(_QWORD *)this = hHandle;
    if ( !WaitForSingleObject(hHandle, 0) )
    {
      v13 = -2145681407;
      v14 = (_QWORD *)((char *)this + 40);
      goto LABEL_34;
    }
  }
  if ( *((_DWORD *)a3 + 4) )
  {
    v15 = (CZipArchiveFile *)HeapAlloc(g_hWerheap, 0, 0x58u);
    if ( v15 )
    {
      v16 = CZipArchiveFile::CZipArchiveFile(v15);
      goto LABEL_15;
    }
  }
  else
  {
    v17 = (CCabArchiveFile *)HeapAlloc(g_hWerheap, 0, 0x3B0u);
    if ( v17 )
    {
      v16 = CCabArchiveFile::CCabArchiveFile(v17);
      goto LABEL_15;
    }
  }
  v16 = 0;
LABEL_15:
  v14 = (_QWORD *)((char *)this + 40);
  v18 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v16;
  if ( v18 )
    utl::default_delete<ITpCommand>::operator()();
  if ( *v14 )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD, struct CReportCabStream *, __int64 (__fastcall *)(CReportManager *__hidden, unsigned __int64, unsigned __int64), void *, HANDLE))(*(_QWORD *)*v14 + 8LL))(
            *v14,
            a3,
            CReportManager::CabCompressCallback,
            a5,
            hHandle);
    if ( v13 >= 0 )
    {
      v21 = 0;
      v22 = 0x10000;
      if ( *((_DWORD *)a2 + 12947) == 3 )
      {
        v21 = 0x1000000;
        v22 = 327680;
      }
      v13 = CReportCab::AddReportFilesToCab(this, a2, v22, v21);
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 40LL))(*v14);
        if ( v13 >= 0 )
          goto LABEL_34;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_34;
        v20 = 26;
      }
      else
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_34;
        v20 = 25;
      }
    }
    else
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_34;
      v20 = 24;
    }
    WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, (unsigned int)v13);
  }
  else
  {
    v13 = -2147024882;
  }
LABEL_34:
  v23 = *v14;
  *v14 = 0;
  if ( v23 )
    utl::default_delete<ITpCommand>::operator()();
  v24 = GetCurrentThread();
  SetThreadPriority(v24, ThreadPriority);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002bf34  push    rbx
0x18002bf36  push    rbp
0x18002bf37  push    rsi
0x18002bf38  push    rdi
0x18002bf39  push    r14
0x18002bf3b  push    r15
0x18002bf3d  sub     rsp, 38h
0x18002bf41  mov     r14, r8
0x18002bf44  mov     rbp, rdx
0x18002bf47  mov     rsi, rcx
0x18002bf4a  test    rdx, rdx
0x18002bf4d  jnz     short loc_18002BF85
0x18002bf4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf56  lea     rax, WPP_GLOBAL_Control
0x18002bf5d  cmp     rcx, rax
0x18002bf60  jz      short loc_18002BF7B
0x18002bf62  test    byte ptr [rcx+1Ch], 1
0x18002bf66  jz      short loc_18002BF7B
0x18002bf68  mov     rcx, [rcx+10h]
0x18002bf6c  lea     edx, [rbp+17h]
0x18002bf6f  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18002bf76  call    WPP_SF_
0x18002bf7b  mov     eax, 80070057h
0x18002bf80  jmp     loc_18002C156
0x18002bf85  call    cs:__imp_GetCurrentThread
0x18002bf8b  mov     rcx, rax; hThread
0x18002bf8e  call    cs:__imp_GetThreadPriority
0x18002bf94  mov     r15d, eax
0x18002bf97  call    cs:__imp_GetCurrentThread
0x18002bf9d  mov     rcx, rax; hThread
0x18002bfa0  or      edx, 0FFFFFFFFh; nPriority
0x18002bfa3  call    cs:__imp_SetThreadPriority
0x18002bfa9  mov     rdi, [rsp+68h+hHandle]
0x18002bfb1  test    rdi, rdi
0x18002bfb4  jz      short loc_18002BFD6
0x18002bfb6  xor     edx, edx; dwMilliseconds
0x18002bfb8  mov     [rsi], rdi
0x18002bfbb  mov     rcx, rdi; hHandle
0x18002bfbe  call    cs:__imp_WaitForSingleObject
0x18002bfc4  test    eax, eax
0x18002bfc6  jnz     short loc_18002BFD6
0x18002bfc8  mov     edi, 801B8001h
0x18002bfcd  lea     rbx, [rsi+28h]
0x18002bfd1  jmp     loc_18002C12E
0x18002bfd6  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002bfdd  xor     edx, edx; dwFlags
0x18002bfdf  cmp     [r14+10h], edx
0x18002bfe3  jz      short loc_18002BFFE
0x18002bfe5  lea     r8d, [rdx+58h]; dwBytes
0x18002bfe9  call    cs:__imp_HeapAlloc
0x18002bfef  test    rax, rax
0x18002bff2  jz      short loc_18002C019
0x18002bff4  mov     rcx, rax; this
0x18002bff7  call    ??0CZipArchiveFile@@QEAA@XZ; CZipArchiveFile::CZipArchiveFile(void)
0x18002bffc  jmp     short loc_18002C01B
0x18002bffe  mov     r8d, 3B0h; dwBytes
0x18002c004  call    cs:__imp_HeapAlloc
0x18002c00a  test    rax, rax
0x18002c00d  jz      short loc_18002C019
0x18002c00f  mov     rcx, rax; this
0x18002c012  call    ??0CCabArchiveFile@@QEAA@XZ; CCabArchiveFile::CCabArchiveFile(void)
0x18002c017  jmp     short loc_18002C01B
0x18002c019  xor     eax, eax
0x18002c01b  lea     rbx, [rsi+28h]
0x18002c01f  mov     rdx, [rbx]
0x18002c022  mov     [rbx], rax
0x18002c025  test    rdx, rdx
0x18002c028  jz      short loc_18002C02F
0x18002c02a  call    ??R?$default_delete@VITpCommand@@@utl@@QEBAXPEAVITpCommand@@@Z; utl::default_delete<ITpCommand>::operator()(ITpCommand *)
0x18002c02f  mov     rcx, [rbx]
0x18002c032  test    rcx, rcx
0x18002c035  jnz     short loc_18002C041
0x18002c037  mov     edi, 8007000Eh
0x18002c03c  jmp     loc_18002C12E
0x18002c041  mov     rax, [rcx]
0x18002c044  lea     r8, ?CabCompressCallback@CReportManager@@AEAAJ_K0@Z; CReportManager::CabCompressCallback(unsigned __int64,unsigned __int64)
0x18002c04b  mov     r9, [rsp+68h+arg_20]
0x18002c053  mov     rdx, r14
0x18002c056  mov     [rsp+68h+var_48], rdi
0x18002c05b  mov     rax, [rax+8]
0x18002c05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c064  mov     edi, eax
0x18002c066  test    eax, eax
0x18002c068  jns     short loc_18002C095
0x18002c06a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c071  lea     rax, WPP_GLOBAL_Control
0x18002c078  cmp     rcx, rax
0x18002c07b  jz      loc_18002C12E
0x18002c081  test    byte ptr [rcx+1Ch], 1
0x18002c085  jz      loc_18002C12E
0x18002c08b  mov     edx, 18h
0x18002c090  jmp     loc_18002C11B
0x18002c095  xor     r9d, r9d
0x18002c098  mov     ecx, 1000000h
0x18002c09d  cmp     dword ptr [rbp+0CA4Ch], 3
0x18002c0a4  mov     r8d, 10000h
0x18002c0aa  mov     rdx, rbp; struct CReport *
0x18002c0ad  cmovz   r9d, ecx; unsigned int
0x18002c0b1  mov     ecx, 50000h
0x18002c0b6  cmovz   r8d, ecx; unsigned int
0x18002c0ba  mov     rcx, rsi; this
0x18002c0bd  call    ?AddReportFilesToCab@CReportCab@@IEAAJPEAVCReport@@KK@Z; CReportCab::AddReportFilesToCab(CReport *,ulong,ulong)
0x18002c0c2  mov     edi, eax
0x18002c0c4  test    eax, eax
0x18002c0c6  jns     short loc_18002C0E8
0x18002c0c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0cf  lea     rax, WPP_GLOBAL_Control
0x18002c0d6  cmp     rcx, rax
0x18002c0d9  jz      short loc_18002C12E
0x18002c0db  test    byte ptr [rcx+1Ch], 1
0x18002c0df  jz      short loc_18002C12E
0x18002c0e1  mov     edx, 19h
0x18002c0e6  jmp     short loc_18002C11B
0x18002c0e8  mov     rcx, [rbx]
0x18002c0eb  mov     rax, [rcx]
0x18002c0ee  mov     rax, [rax+28h]
0x18002c0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0f7  mov     edi, eax
0x18002c0f9  test    eax, eax
0x18002c0fb  jns     short loc_18002C12E
0x18002c0fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c104  lea     rax, WPP_GLOBAL_Control
0x18002c10b  cmp     rcx, rax
0x18002c10e  jz      short loc_18002C12E
0x18002c110  test    byte ptr [rcx+1Ch], 1
0x18002c114  jz      short loc_18002C12E
0x18002c116  mov     edx, 1Ah
0x18002c11b  mov     rcx, [rcx+10h]
0x18002c11f  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18002c126  mov     r9d, edi
0x18002c129  call    WPP_SF_d
0x18002c12e  mov     rdx, [rbx]
0x18002c131  mov     qword ptr [rbx], 0
0x18002c138  test    rdx, rdx
0x18002c13b  jz      short loc_18002C142
0x18002c13d  call    ??R?$default_delete@VITpCommand@@@utl@@QEBAXPEAVITpCommand@@@Z; utl::default_delete<ITpCommand>::operator()(ITpCommand *)
0x18002c142  call    cs:__imp_GetCurrentThread
0x18002c148  mov     rcx, rax; hThread
0x18002c14b  mov     edx, r15d; nPriority
0x18002c14e  call    cs:__imp_SetThreadPriority
0x18002c154  mov     eax, edi
0x18002c156  add     rsp, 38h
0x18002c15a  pop     r15
0x18002c15c  pop     r14
0x18002c15e  pop     rdi
0x18002c15f  pop     rsi
0x18002c160  pop     rbp
0x18002c161  pop     rbx
0x18002c162  retn
```
