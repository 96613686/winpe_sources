# HandleSyncHookMessage(tagCWPSTRUCT *,ulong,void (*)(void *,ulong,void * *,ulong *,void * *),void (*)(int,void *))

- ea: `0x18022f7b4`
- end: `0x18022fbb0`
- name: `?HandleSyncHookMessage@@YAXPEAUtagCWPSTRUCT@@KP6AXPEAXKPEAPEAXPEAK2@ZP6AXH1@Z@Z`
- size: `1020`
- prototype: `void __fastcall(struct tagCWPSTRUCT *, unsigned int, void (*)(void *, unsigned int, void **, unsigned int *, void **), void (*)(int, void *))`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1801f3b30`

## callees

- `0x18002f580`
- `0x180090ed4`
- `0x1800948b8`
- `0x1800984e0`
- `0x18012e8dc`
- `0x180150a5c`
- `0x1801e4558`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e88a0`
- `0x1801e9240`
- `0x18022f7b4`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18022fba4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18022fba4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18022f80a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18022f80a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18022f89e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18022f8a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18022f8f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18022f901`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18022f89e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18022f8a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18022f8f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18022f901`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18022f8ce`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18022f924`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18022f8ce`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18022f924`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18022f876`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18022f967`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18022fb03`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18022f876`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18022f967`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18022fb03`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18022facf`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18022facf`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18022f84e`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18022f84e`

## string_xrefs

- `0x18022fa2d`: `onecore\windows\accessibletech\uiautomationcore\SafeApis.h`
- `0x18022fb52`: `onecore\windows\accessibletech\uiautomationcore\SafeApis.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall HandleSyncHookMessage(
        struct tagCWPSTRUCT *a1,
        int a2,
        void (*a3)(void *, unsigned int, void **, unsigned int *, void **),
        void (*a4)(int, void *))
{
  HANDLE v8; // rax
  int *v9; // rax
  _DWORD *v10; // rdi
  void *v11; // rsi
  HANDLE CurrentProcess; // rbx
  HANDLE v13; // rax
  void *v14; // rsi
  HANDLE v15; // rbx
  HANDLE v16; // rax
  int v17; // r14d
  unsigned int v18; // esi
  volatile __int32 *v19; // rax
  volatile __int32 *v20; // rdi
  void *v21; // rbx
  void *v22; // rcx
  int v23; // eax
  int v24; // r14d
  unsigned int v25; // eax
  unsigned int v26; // r15d
  HANDLE FileMappingW; // rsi
  _DWORD *v28; // rax
  __int64 v29; // r8
  _DWORD *v30; // r9
  int v31; // eax
  __int64 v32; // r9
  __int64 v33; // rcx
  int dwNumberOfBytesToMap; // [rsp+20h] [rbp-E0h]
  int dwNumberOfBytesToMapa; // [rsp+20h] [rbp-E0h]
  DWORD bInheritHandle; // [rsp+28h] [rbp-D8h]
  DWORD dwOptions; // [rsp+30h] [rbp-D0h]
  int wParam; // [rsp+38h] [rbp-C8h]
  unsigned int v39[2]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v40; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v41; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hEvent; // [rsp+58h] [rbp-A8h] BYREF
  int *v43; // [rsp+60h] [rbp-A0h] BYREF
  void *Src; // [rsp+68h] [rbp-98h] BYREF
  volatile __int32 *v45; // [rsp+70h] [rbp-90h] BYREF
  HANDLE v46; // [rsp+78h] [rbp-88h] BYREF
  __int64 v47; // [rsp+80h] [rbp-80h] BYREF
  _DWORD *v48; // [rsp+88h] [rbp-78h] BYREF
  void *v49; // [rsp+90h] [rbp-70h]
  WCHAR Name[64]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  if ( (int)EnsureWindowMessagesRegistered() >= 0 && a1->message == _uWM_SYNC_HOOK_MESSAGE )
  {
    wParam = a1->wParam;
    dwOptions = a1->lParam;
    bInheritHandle = GetCurrentThreadId();
    if ( (int)StringCchPrintfW(
                Name,
                0x40u,
                L"%wsHOOK_SHMEM_%08lx_%08lx_%08lx_%08lx",
                &word_180313900,
                a2,
                bInheritHandle,
                dwOptions,
                wParam) >= 0 )
    {
      v8 = OpenFileMappingW(4u, 0, Name);
      v41 = v8;
      if ( !v8 )
      {
LABEL_25:
        AutoCleanupInfo<void *>::SafeRelease(&v41);
        return;
      }
      v9 = (int *)MapViewOfFile(v8, 4u, 0, 0, 0x18u);
      v10 = v9;
      v43 = v9;
      if ( !v9 || (v11 = (void *)v9[4], !(_DWORD)v11) )
      {
LABEL_24:
        AutoCleanupFn<RequestHeader *,&void TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>::~AutoCleanupFn<RequestHeader *,&void TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>(&v43);
        goto LABEL_25;
      }
      v40 = 0;
      CurrentProcess = GetCurrentProcess();
      v13 = GetCurrentProcess();
      if ( !DuplicateHandle(v13, v11, CurrentProcess, &v40, 0, 0, 2u)
        || (_DWORD)v11 != v10[4]
        || (v14 = (void *)(int)v10[5], !(_DWORD)v14) )
      {
LABEL_23:
        AutoCleanupInfo<void *>::SafeRelease(&v40);
        goto LABEL_24;
      }
      hEvent = 0;
      v15 = GetCurrentProcess();
      v16 = GetCurrentProcess();
      if ( !DuplicateHandle(v16, v14, v15, &hEvent, 0, 0, 2u) || (_DWORD)v14 != v10[5] )
        goto LABEL_22;
      v17 = v10[3];
      v18 = 0;
      if ( v17 != -1 )
        v18 = v10[3];
      if ( v18 + 24 < v18 )
      {
LABEL_22:
        AutoCleanupInfo<void *>::SafeRelease(&hEvent);
        goto LABEL_23;
      }
      v19 = (volatile __int32 *)MapViewOfFile(v40, 6u, 0, 0, v18 + 24);
      v20 = v19;
      v45 = v19;
      if ( !v19 || _InterlockedExchange(v19, 1) )
      {
LABEL_21:
        AutoCleanupFn<RequestHeader *,&void TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>::~AutoCleanupFn<RequestHeader *,&void TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>(&v45);
        goto LABEL_22;
      }
      v21 = 0;
      v49 = 0;
      if ( v17 != -1 )
      {
        v21 = operator new[](v18, (const struct std::nothrow_t *)std::nothrow);
        v49 = v21;
        if ( !v21 )
        {
          v22 = 0;
LABEL_20:
          operator delete(v22);
          goto LABEL_21;
        }
        v39[1] = 0;
        v23 = ULongLongToUInt(v18, &v39[1]);
        if ( v23 >= 0 )
          memcpy_0(v21, (const void *)(v20 + 6), v39[1]);
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x46,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SafeApis.h",
            (const char *)(unsigned int)v23,
            dwNumberOfBytesToMap);
      }
      v39[0] = 0;
      v47 = 0;
      Src = 0;
      ((void (__fastcall *)(void *, _QWORD, void **, unsigned int *, __int64 *))a3)(v21, v18, &Src, v39, &v47);
      if ( Src )
      {
        v24 = 0;
        v25 = v39[0];
      }
      else
      {
        v24 = 1;
        v25 = 0;
        v39[0] = 0;
      }
      v26 = v25 + 4;
      if ( v25 + 4 >= v25 )
      {
        FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, v25 + 4, 0);
        v46 = FileMappingW;
        if ( FileMappingW )
        {
          v28 = MapViewOfFile(FileMappingW, 6u, 0, 0, v26);
          v30 = v28;
          v48 = v28;
          if ( v28 )
          {
            if ( v24 )
            {
              *v28 = -1;
            }
            else
            {
              *v28 = v39[0];
              v39[1] = 0;
              v31 = ULongLongToUInt(v39[0], &v39[1]);
              if ( v31 >= 0 )
                memcpy_0((void *)(v32 + 4), Src, v39[1]);
              else
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x46,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SafeApis.h",
                  (const char *)(unsigned int)v31,
                  dwNumberOfBytesToMapa);
            }
            *((_DWORD *)v20 + 2) = (_DWORD)FileMappingW;
            v33 = 1;
            if ( _InterlockedExchange(v20 + 1, 1) == 2 )
              v33 = 0;
            else
              v46 = 0;
            ((void (__fastcall *)(__int64, __int64, __int64, _DWORD *))a4)(v33, v47, v29, v30);
            SetEvent(hEvent);
          }
          AutoCleanupFn<RequestHeader *,&void TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>::~AutoCleanupFn<RequestHeader *,&void TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>(&v48);
        }
        AutoCleanupInfo<void *>::SafeRelease(&v46);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Src);
      v22 = v21;
      goto LABEL_20;
    }
  }
}

```

## disassembly

```asm
0x18022f7b4  push    rbp
0x18022f7b6  push    rbx
0x18022f7b7  push    rsi
0x18022f7b8  push    rdi
0x18022f7b9  push    r12
0x18022f7bb  push    r13
0x18022f7bd  push    r14
0x18022f7bf  push    r15
0x18022f7c1  lea     rbp, [rsp-38h]
0x18022f7c6  sub     rsp, 138h
0x18022f7cd  mov     rax, cs:__security_cookie
0x18022f7d4  xor     rax, rsp
0x18022f7d7  mov     [rbp+70h+var_50], rax
0x18022f7db  mov     r12, r9
0x18022f7de  mov     r15, r8
0x18022f7e1  mov     esi, edx
0x18022f7e3  mov     rdi, rcx
0x18022f7e6  call    ?EnsureWindowMessagesRegistered@@YAJXZ; EnsureWindowMessagesRegistered(void)
0x18022f7eb  xor     r13d, r13d
0x18022f7ee  test    eax, eax
0x18022f7f0  js      loc_18022F9F0
0x18022f7f6  mov     eax, cs:?_uWM_SYNC_HOOK_MESSAGE@@3IA; uint _uWM_SYNC_HOOK_MESSAGE
0x18022f7fc  cmp     [rdi+10h], eax
0x18022f7ff  jnz     loc_18022F9F0
0x18022f805  mov     ebx, [rdi+8]
0x18022f808  mov     edi, [rdi]
0x18022f80a  call    cs:__imp_GetCurrentThreadId
0x18022f810  mov     [rsp+170h+var_138], ebx
0x18022f814  mov     [rsp+170h+dwOptions], edi
0x18022f818  mov     [rsp+170h+bInheritHandle], eax
0x18022f81c  mov     dword ptr [rsp+170h+dwNumberOfBytesToMap], esi
0x18022f820  lea     r9, word_180313900
0x18022f827  lea     r8, aWshookShmem08l; "%wsHOOK_SHMEM_%08lx_%08lx_%08lx_%08lx"
0x18022f82e  lea     edx, [r13+40h]; unsigned __int64
0x18022f832  lea     rcx, [rbp+70h+Name]; unsigned __int16 *
0x18022f836  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18022f83b  test    eax, eax
0x18022f83d  js      loc_18022F9F0
0x18022f843  lea     r8, [rbp+70h+Name]; lpName
0x18022f847  xor     edx, edx; bInheritHandle
0x18022f849  lea     ebx, [rdx+4]
0x18022f84c  mov     ecx, ebx; dwDesiredAccess
0x18022f84e  call    cs:__imp_OpenFileMappingW
0x18022f854  mov     [rsp+170h+var_120], rax
0x18022f859  test    rax, rax
0x18022f85c  jz      loc_18022F9E6
0x18022f862  mov     [rsp+170h+dwNumberOfBytesToMap], 18h; dwNumberOfBytesToMap
0x18022f86b  xor     r9d, r9d; dwFileOffsetLow
0x18022f86e  xor     r8d, r8d; dwFileOffsetHigh
0x18022f871  mov     edx, ebx; dwDesiredAccess
0x18022f873  mov     rcx, rax; hFileMappingObject
0x18022f876  call    cs:__imp_MapViewOfFile
0x18022f87c  mov     rdi, rax
0x18022f87f  mov     [rsp+170h+var_110], rax
0x18022f884  test    rax, rax
0x18022f887  jz      loc_18022F9DB
0x18022f88d  movsxd  rsi, dword ptr [rax+10h]
0x18022f891  test    esi, esi
0x18022f893  jz      loc_18022F9DB
0x18022f899  mov     [rsp+170h+var_128], r13
0x18022f89e  call    cs:__imp_GetCurrentProcess
0x18022f8a4  mov     rbx, rax
0x18022f8a7  call    cs:__imp_GetCurrentProcess
0x18022f8ad  mov     rdx, rsi; hSourceHandle
0x18022f8b0  lea     r14d, [r13+2]
0x18022f8b4  mov     [rsp+170h+dwOptions], r14d; dwOptions
0x18022f8b9  mov     [rsp+170h+bInheritHandle], r13d; bInheritHandle
0x18022f8be  mov     dword ptr [rsp+170h+dwNumberOfBytesToMap], r13d; dwDesiredAccess
0x18022f8c3  lea     r9, [rsp+170h+var_128]; lpTargetHandle
0x18022f8c8  mov     r8, rbx; hTargetProcessHandle
0x18022f8cb  mov     rcx, rax; hSourceProcessHandle
0x18022f8ce  call    cs:__imp_DuplicateHandle
0x18022f8d4  test    eax, eax
0x18022f8d6  jz      loc_18022F9D0
0x18022f8dc  mov     eax, [rdi+10h]
0x18022f8df  cmp     esi, eax
0x18022f8e1  jnz     loc_18022F9D0
0x18022f8e7  movsxd  rsi, dword ptr [rdi+14h]
0x18022f8eb  test    esi, esi
0x18022f8ed  jz      loc_18022F9D0
0x18022f8f3  mov     [rsp+170h+hEvent], r13
0x18022f8f8  call    cs:__imp_GetCurrentProcess
0x18022f8fe  mov     rbx, rax
0x18022f901  call    cs:__imp_GetCurrentProcess
0x18022f907  mov     rdx, rsi; hSourceHandle
0x18022f90a  mov     [rsp+170h+dwOptions], r14d; dwOptions
0x18022f90f  mov     [rsp+170h+bInheritHandle], r13d; bInheritHandle
0x18022f914  mov     dword ptr [rsp+170h+dwNumberOfBytesToMap], r13d; dwDesiredAccess
0x18022f919  lea     r9, [rsp+170h+hEvent]; lpTargetHandle
0x18022f91e  mov     r8, rbx; hTargetProcessHandle
0x18022f921  mov     rcx, rax; hSourceProcessHandle
0x18022f924  call    cs:__imp_DuplicateHandle
0x18022f92a  test    eax, eax
0x18022f92c  jz      loc_18022F9C5
0x18022f932  mov     eax, [rdi+14h]
0x18022f935  cmp     esi, eax
0x18022f937  jnz     loc_18022F9C5
0x18022f93d  mov     r14d, [rdi+0Ch]
0x18022f941  mov     esi, r13d
0x18022f944  cmp     r14d, 0FFFFFFFFh
0x18022f948  cmovnz  esi, r14d
0x18022f94c  lea     eax, [rsi+18h]
0x18022f94f  cmp     eax, esi
0x18022f951  jb      short loc_18022F9C5
0x18022f953  mov     [rsp+170h+dwNumberOfBytesToMap], rax; int
0x18022f958  xor     r9d, r9d; dwFileOffsetLow
0x18022f95b  xor     r8d, r8d; dwFileOffsetHigh
0x18022f95e  lea     edx, [r13+6]; dwDesiredAccess
0x18022f962  mov     rcx, [rsp+170h+var_128]; hFileMappingObject
0x18022f967  call    cs:__imp_MapViewOfFile
0x18022f96d  mov     rdi, rax
0x18022f970  mov     [rsp+170h+var_100], rax
0x18022f975  test    rax, rax
0x18022f978  jz      short loc_18022F9BA
0x18022f97a  lea     eax, [r13+1]
0x18022f97e  xchg    eax, [rdi]
0x18022f980  test    eax, eax
0x18022f982  jnz     short loc_18022F9BA
0x18022f984  mov     ebx, r13d
0x18022f987  mov     [rbp+70h+var_E0], rbx
0x18022f98b  cmp     r14d, 0FFFFFFFFh
0x18022f98f  jz      loc_18022FA51
0x18022f995  mov     r14d, esi
0x18022f998  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18022f99f  mov     ecx, esi; unsigned __int64
0x18022f9a1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18022f9a6  mov     rbx, rax
0x18022f9a9  mov     [rbp+70h+var_E0], rax
0x18022f9ad  test    rax, rax
0x18022f9b0  jnz     short loc_18022FA10
0x18022f9b2  xor     ecx, ecx; Block
0x18022f9b4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18022f9b9  nop
0x18022f9ba  lea     rcx, [rsp+170h+var_100]
0x18022f9bf  call    ??1?$AutoCleanupFn@PEAURequestHeader@@$1??$TUnmapViewOfFile@PEAURequestHeader@@@@YAXPEAU1@@Z@@QEAA@XZ; AutoCleanupFn<RequestHeader *,&TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>::~AutoCleanupFn<RequestHeader *,&TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>(void)
0x18022f9c4  nop
0x18022f9c5  lea     rcx, [rsp+170h+hEvent]
0x18022f9ca  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x18022f9cf  nop
0x18022f9d0  lea     rcx, [rsp+170h+var_128]
0x18022f9d5  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x18022f9da  nop
0x18022f9db  lea     rcx, [rsp+170h+var_110]
0x18022f9e0  call    ??1?$AutoCleanupFn@PEAURequestHeader@@$1??$TUnmapViewOfFile@PEAURequestHeader@@@@YAXPEAU1@@Z@@QEAA@XZ; AutoCleanupFn<RequestHeader *,&TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>::~AutoCleanupFn<RequestHeader *,&TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>(void)
0x18022f9e5  nop
0x18022f9e6  lea     rcx, [rsp+170h+var_120]
0x18022f9eb  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x18022f9f0  mov     rcx, [rbp+70h+var_50]
0x18022f9f4  xor     rcx, rsp; StackCookie
0x18022f9f7  call    __security_check_cookie
0x18022f9fc  add     rsp, 138h
0x18022fa03  pop     r15
0x18022fa05  pop     r14
0x18022fa07  pop     r13
0x18022fa09  pop     r12
0x18022fa0b  pop     rdi
0x18022fa0c  pop     rsi
0x18022fa0d  pop     rbx
0x18022fa0e  pop     rbp
0x18022fa0f  retn
0x18022fa10  mov     [rsp+170h+var_130+4], r13d
0x18022fa15  lea     rdx, [rsp+170h+var_130+4]; unsigned int *
0x18022fa1a  mov     rcx, r14; unsigned __int64
0x18022fa1d  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18022fa22  test    eax, eax
0x18022fa24  jns     short loc_18022FA40
0x18022fa26  mov     rcx, [rbp+78h]; this
0x18022fa2a  mov     r9d, eax; char *
0x18022fa2d  lea     r8, aOnecoreWindows_51; "onecore\\windows\\accessibletech\\uiaut"...
0x18022fa34  mov     edx, 46h ; 'F'; void *
0x18022fa39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022fa3e  jmp     short loc_18022FA51
0x18022fa40  mov     r8d, [rsp+170h+var_130+4]; Size
0x18022fa45  lea     rdx, [rdi+18h]; Src
0x18022fa49  mov     rcx, rbx; void *
0x18022fa4c  call    memcpy_0
0x18022fa51  mov     [rsp+170h+var_130], r13d
0x18022fa56  mov     [rbp+70h+var_F0], r13
0x18022fa5a  mov     [rsp+170h+Src], r13
0x18022fa5f  lea     rax, [rbp+70h+var_F0]
0x18022fa63  mov     [rsp+170h+dwNumberOfBytesToMap], rax
0x18022fa68  lea     r9, [rsp+170h+var_130]
0x18022fa6d  lea     r8, [rsp+170h+Src]
0x18022fa72  mov     edx, esi
0x18022fa74  mov     rcx, rbx
0x18022fa77  mov     rax, r15
0x18022fa7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022fa7f  cmp     [rsp+170h+Src], r13
0x18022fa84  jnz     short loc_18022FA95
0x18022fa86  mov     r14d, 1
0x18022fa8c  mov     eax, r13d
0x18022fa8f  mov     [rsp+170h+var_130], eax
0x18022fa93  jmp     short loc_18022FA9C
0x18022fa95  mov     r14d, r13d
0x18022fa98  mov     eax, [rsp+170h+var_130]
0x18022fa9c  lea     r15d, [rax+4]
0x18022faa0  cmp     r15d, eax
0x18022faa3  jnb     short loc_18022FAB8
0x18022faa5  lea     rcx, [rsp+170h+Src]
0x18022faaa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18022faaf  nop
0x18022fab0  mov     rcx, rbx
0x18022fab3  jmp     loc_18022F9B4
0x18022fab8  mov     qword ptr [rsp+170h+bInheritHandle], r13; lpName
0x18022fabd  mov     dword ptr [rsp+170h+dwNumberOfBytesToMap], r15d; dwMaximumSizeLow
0x18022fac2  xor     r9d, r9d; dwMaximumSizeHigh
0x18022fac5  xor     edx, edx; lpFileMappingAttributes
0x18022fac7  lea     r8d, [r9+4]; flProtect
0x18022facb  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18022facf  call    cs:__imp_CreateFileMappingW
0x18022fad5  mov     rsi, rax
0x18022fad8  mov     [rsp+170h+var_F8], rax
0x18022fadd  test    rax, rax
0x18022fae0  jnz     short loc_18022FAEE
0x18022fae2  lea     rcx, [rsp+170h+var_F8]
0x18022fae7  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x18022faec  jmp     short loc_18022FAA5
0x18022faee  mov     eax, r15d
0x18022faf1  mov     [rsp+170h+dwNumberOfBytesToMap], rax; int
0x18022faf6  xor     r9d, r9d; dwFileOffsetLow
0x18022faf9  xor     r8d, r8d; dwFileOffsetHigh
0x18022fafc  lea     edx, [r9+6]; dwDesiredAccess
0x18022fb00  mov     rcx, rsi; hFileMappingObject
0x18022fb03  call    cs:__imp_MapViewOfFile
0x18022fb09  mov     r9, rax
0x18022fb0c  mov     [rbp+70h+var_E8], rax
0x18022fb10  test    rax, rax
0x18022fb13  jnz     short loc_18022FB20
0x18022fb15  lea     rcx, [rbp+70h+var_E8]
0x18022fb19  call    ??1?$AutoCleanupFn@PEAURequestHeader@@$1??$TUnmapViewOfFile@PEAURequestHeader@@@@YAXPEAU1@@Z@@QEAA@XZ; AutoCleanupFn<RequestHeader *,&TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>::~AutoCleanupFn<RequestHeader *,&TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>(void)
0x18022fb1e  jmp     short loc_18022FAE2
0x18022fb20  test    r14d, r14d
0x18022fb23  jz      short loc_18022FB2D
0x18022fb25  mov     dword ptr [rax], 0FFFFFFFFh
0x18022fb2b  jmp     short loc_18022FB78
0x18022fb2d  mov     eax, [rsp+170h+var_130]
0x18022fb31  mov     [r9], eax
0x18022fb34  mov     [rsp+170h+var_130+4], r13d
0x18022fb39  mov     ecx, [rsp+170h+var_130]; unsigned __int64
0x18022fb3d  lea     rdx, [rsp+170h+var_130+4]; unsigned int *
0x18022fb42  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18022fb47  test    eax, eax
0x18022fb49  jns     short loc_18022FB65
0x18022fb4b  mov     rcx, [rbp+78h]; this
0x18022fb4f  mov     r9d, eax; char *
0x18022fb52  lea     r8, aOnecoreWindows_51; "onecore\\windows\\accessibletech\\uiaut"...
0x18022fb59  mov     edx, 46h ; 'F'; void *
0x18022fb5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022fb63  jmp     short loc_18022FB78
0x18022fb65  mov     r8d, [rsp+170h+var_130+4]; Size
0x18022fb6a  lea     rcx, [r9+4]; void *
0x18022fb6e  mov     rdx, [rsp+170h+Src]; Src
0x18022fb73  call    memcpy_0
0x18022fb78  mov     [rdi+8], esi
0x18022fb7b  mov     ecx, 1
0x18022fb80  mov     eax, ecx
0x18022fb82  xchg    eax, [rdi+4]
0x18022fb85  mov     rdx, [rbp+70h+var_F0]
0x18022fb89  cmp     eax, 2
0x18022fb8c  mov     rax, r12
0x18022fb8f  jnz     short loc_18022FB95
0x18022fb91  xor     ecx, ecx
0x18022fb93  jmp     short loc_18022FB9A
0x18022fb95  mov     [rsp+170h+var_F8], r13
0x18022fb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022fb9f  mov     rcx, [rsp+170h+hEvent]; hEvent
0x18022fba4  call    cs:__imp_SetEvent
0x18022fbaa  jmp     loc_18022FB15
```
