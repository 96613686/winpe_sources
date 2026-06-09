# CHangReport::Cleanup(void)

- ea: `0x14001d800`
- end: `0x14001da8b`
- name: `?Cleanup@CHangReport@@MEAAXXZ`
- size: `651`
- prototype: `void __fastcall(CPluginList **this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x14001d60c`
- `0x140022b50`

## callees

- `0x140002728`
- `0x14001d800`
- `0x14001f200`
- `0x14004655c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d924`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d924`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001d951`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001d951`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001d985`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001d9ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001d9d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001d985`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001d9ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001d9d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001d990`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001d9b7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001d9de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001d990`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001d9b7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001d9de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001d999`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001d9c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001d9e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001d999`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001d9c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001d9e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d8b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d93c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d95c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d9fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001da74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d8b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d93c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d95c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d9fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001da74`
- `wer!WerReportCloseHandle` at `0x14001da14`
- `wer!WerReportCloseHandle` at `0x14001da14`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x14001d972`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x14001d972`

## pseudocode

```c
void __fastcall CHangReport::Cleanup(CPluginList **this)
{
  CPluginList *v2; // r13
  CPluginList *v3; // rdi
  struct _TP_WAIT *v4; // r14
  struct _TP_WAIT *v5; // rbp
  struct _TP_WAIT *v6; // r15
  unsigned int i; // ebx
  CPluginList *v8; // rcx
  CPluginList *v9; // r12
  CPluginList *v10; // rbx
  CPluginList *v11; // rsi
  _QWORD *v12; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-58h] BYREF
  char v14; // [rsp+28h] [rbp-50h]
  CPluginList *RegistrationHandle; // [rsp+80h] [rbp+8h]
  CPluginList *hObject; // [rsp+88h] [rbp+10h]
  CPluginList *hReportHandle; // [rsp+90h] [rbp+18h]
  CPluginList *v18; // [rsp+98h] [rbp+20h]

  CHangReport::Lock(this, &lpCriticalSection, L"CHangReport::Cleanup");
  v2 = this[3088];
  this[3088] = 0;
  v3 = v2;
  v4 = this[3094];
  this[3094] = 0;
  v5 = this[3093];
  this[3093] = 0;
  v6 = this[3092];
  this[3092] = 0;
  v18 = this[9];
  this[9] = 0;
  hReportHandle = this[3055];
  this[3055] = 0;
  this[2988] = 0;
  this[3054] = 0;
  for ( i = 0; i < 0xF; ++i )
  {
    v8 = this[(int)i + 3096];
    if ( (unsigned __int64)v8 + 1 <= 1 )
      break;
    this[(int)i + 3096] = 0;
    CloseHandle(v8);
  }
  v9 = this[3090];
  this[3090] = 0;
  hObject = this[3089];
  this[3089] = 0;
  v10 = this[3095];
  this[3095] = (CPluginList *)-1LL;
  RegistrationHandle = this[3091];
  this[3091] = 0;
  if ( !v14 )
    __int2c();
  LeaveCriticalSection(lpCriticalSection);
  if ( (unsigned __int64)v9 + 1 > 1 )
    CloseHandle(v9);
  if ( (unsigned __int64)v2 + 1 > 1 )
  {
    WaitForSingleObject(v2, 0xFFFFFFFF);
    v3 = 0;
    CloseHandle(v2);
  }
  if ( RegistrationHandle )
    PowerSettingUnregisterNotification(RegistrationHandle);
  if ( v6 )
  {
    SetThreadpoolWait(v6, 0, 0);
    WaitForThreadpoolWaitCallbacks(v6, 1);
    CloseThreadpoolWait(v6);
  }
  if ( v4 )
  {
    SetThreadpoolWait(v4, 0, 0);
    WaitForThreadpoolWaitCallbacks(v4, 1);
    CloseThreadpoolWait(v4);
  }
  if ( v5 )
  {
    SetThreadpoolWait(v5, 0, 0);
    WaitForThreadpoolWaitCallbacks(v5, 1);
    CloseThreadpoolWait(v5);
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( hReportHandle )
    WerReportCloseHandle(hReportHandle);
  if ( v18 )
    WerPluginsDestroy(v18);
  while ( v10 != (CPluginList *)-1LL )
  {
    v11 = v10;
    v10 = *(CPluginList **)v10;
    v12 = (_QWORD *)*((_QWORD *)v11 + 1);
    if ( v12 != (_QWORD *)((char *)v11 + 24) )
      operator delete(v12, (const struct std::nothrow_t *)&std::nothrow);
    operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
  }
  if ( (unsigned __int64)v3 + 1 > 1 )
    CloseHandle(v3);
}

```

## disassembly

```asm
0x14001d800  push    rbx
0x14001d802  push    rbp
0x14001d803  push    rsi
0x14001d804  push    rdi
0x14001d805  push    r12
0x14001d807  push    r13
0x14001d809  push    r14
0x14001d80b  push    r15
0x14001d80d  sub     rsp, 38h
0x14001d811  mov     rsi, rcx
0x14001d814  lea     r8, aChangreportCle; "CHangReport::Cleanup"
0x14001d81b  lea     rdx, [rsp+78h+lpCriticalSection]
0x14001d820  call    ?Lock@CHangReport@@IEAA?AV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEB_W@Z; CHangReport::Lock(wchar_t const *)
0x14001d825  mov     r13, [rsi+6080h]
0x14001d82c  xor     r8d, r8d
0x14001d82f  mov     [rsi+6080h], r8
0x14001d836  mov     rdi, r13
0x14001d839  mov     r14, [rsi+60B0h]
0x14001d840  mov     [rsi+60B0h], r8
0x14001d847  mov     rbp, [rsi+60A8h]
0x14001d84e  mov     [rsi+60A8h], r8
0x14001d855  mov     r15, [rsi+60A0h]
0x14001d85c  mov     [rsi+60A0h], r8
0x14001d863  mov     rax, [rsi+48h]
0x14001d867  mov     [rsp+78h+arg_18], rax
0x14001d86f  mov     [rsi+48h], r8
0x14001d873  mov     rax, [rsi+5F78h]
0x14001d87a  mov     [rsp+78h+hReportHandle], rax
0x14001d882  mov     [rsi+5F78h], r8
0x14001d889  mov     [rsi+5D60h], r8
0x14001d890  mov     [rsi+5F70h], r8
0x14001d897  mov     ebx, r8d
0x14001d89a  movsxd  rdx, ebx
0x14001d89d  mov     rcx, [rsi+rdx*8+60C0h]; hObject
0x14001d8a5  lea     rax, [rcx+1]
0x14001d8a9  cmp     rax, 1
0x14001d8ad  jbe     short loc_14001D8CA
0x14001d8af  mov     [rsi+rdx*8+60C0h], r8
0x14001d8b7  call    cs:__imp_CloseHandle
0x14001d8bd  inc     ebx
0x14001d8bf  cmp     ebx, 0Fh
0x14001d8c2  mov     r8d, 0
0x14001d8c8  jb      short loc_14001D89A
0x14001d8ca  mov     r12, [rsi+6090h]
0x14001d8d1  mov     [rsi+6090h], r8
0x14001d8d8  mov     rax, [rsi+6088h]
0x14001d8df  mov     [rsp+78h+hObject], rax
0x14001d8e7  mov     [rsi+6088h], r8
0x14001d8ee  mov     rbx, [rsi+60B8h]
0x14001d8f5  mov     qword ptr [rsi+60B8h], 0FFFFFFFFFFFFFFFFh
0x14001d900  mov     rax, [rsi+6098h]
0x14001d907  mov     [rsp+78h+RegistrationHandle], rax
0x14001d90f  mov     [rsi+6098h], r8
0x14001d916  cmp     [rsp+78h+var_50], r8b
0x14001d91b  jnz     short loc_14001D91F
0x14001d91d  int     2Ch; Windows NT - assertion failure
0x14001d91f  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x14001d924  call    cs:__imp_LeaveCriticalSection
0x14001d92a  lea     rax, [r12+1]
0x14001d92f  mov     esi, 1
0x14001d934  cmp     rax, rsi
0x14001d937  jbe     short loc_14001D942
0x14001d939  mov     rcx, r12; hObject
0x14001d93c  call    cs:__imp_CloseHandle
0x14001d942  lea     rax, [r13+1]
0x14001d946  cmp     rax, rsi
0x14001d949  jbe     short loc_14001D962
0x14001d94b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001d94e  mov     rcx, r13; hHandle
0x14001d951  call    cs:__imp_WaitForSingleObject
0x14001d957  xor     edi, edi
0x14001d959  mov     rcx, r13; hObject
0x14001d95c  call    cs:__imp_CloseHandle
0x14001d962  mov     rax, [rsp+78h+RegistrationHandle]
0x14001d96a  test    rax, rax
0x14001d96d  jz      short loc_14001D978
0x14001d96f  mov     rcx, rax; RegistrationHandle
0x14001d972  call    cs:__imp_PowerSettingUnregisterNotification
0x14001d978  test    r15, r15
0x14001d97b  jz      short loc_14001D99F
0x14001d97d  xor     r8d, r8d; pftTimeout
0x14001d980  xor     edx, edx; h
0x14001d982  mov     rcx, r15; pwa
0x14001d985  call    cs:__imp_SetThreadpoolWait
0x14001d98b  mov     edx, esi; fCancelPendingCallbacks
0x14001d98d  mov     rcx, r15; pwa
0x14001d990  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x14001d996  mov     rcx, r15; pwa
0x14001d999  call    cs:__imp_CloseThreadpoolWait
0x14001d99f  test    r14, r14
0x14001d9a2  jz      short loc_14001D9C6
0x14001d9a4  xor     r8d, r8d; pftTimeout
0x14001d9a7  xor     edx, edx; h
0x14001d9a9  mov     rcx, r14; pwa
0x14001d9ac  call    cs:__imp_SetThreadpoolWait
0x14001d9b2  mov     edx, esi; fCancelPendingCallbacks
0x14001d9b4  mov     rcx, r14; pwa
0x14001d9b7  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x14001d9bd  mov     rcx, r14; pwa
0x14001d9c0  call    cs:__imp_CloseThreadpoolWait
0x14001d9c6  test    rbp, rbp
0x14001d9c9  jz      short loc_14001D9ED
0x14001d9cb  xor     r8d, r8d; pftTimeout
0x14001d9ce  xor     edx, edx; h
0x14001d9d0  mov     rcx, rbp; pwa
0x14001d9d3  call    cs:__imp_SetThreadpoolWait
0x14001d9d9  mov     edx, esi; fCancelPendingCallbacks
0x14001d9db  mov     rcx, rbp; pwa
0x14001d9de  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x14001d9e4  mov     rcx, rbp; pwa
0x14001d9e7  call    cs:__imp_CloseThreadpoolWait
0x14001d9ed  mov     rcx, [rsp+78h+hObject]; hObject
0x14001d9f5  lea     rax, [rcx+1]
0x14001d9f9  cmp     rax, rsi
0x14001d9fc  jbe     short loc_14001DA04
0x14001d9fe  call    cs:__imp_CloseHandle
0x14001da04  mov     rax, [rsp+78h+hReportHandle]
0x14001da0c  test    rax, rax
0x14001da0f  jz      short loc_14001DA1B
0x14001da11  mov     rcx, rax; hReportHandle
0x14001da14  call    cs:__imp_WerReportCloseHandle
0x14001da1a  nop
0x14001da1b  mov     rax, [rsp+78h+arg_18]
0x14001da23  test    rax, rax
0x14001da26  jz      short loc_14001DA31
0x14001da28  mov     rcx, rax; this
0x14001da2b  call    ?WerPluginsDestroy@@YAJPEAX@Z; WerPluginsDestroy(void *)
0x14001da30  nop
0x14001da31  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14001da35  jz      short loc_14001DA67
0x14001da37  mov     rsi, rbx
0x14001da3a  mov     rbx, [rbx]
0x14001da3d  mov     rcx, [rsi+8]; void *
0x14001da41  lea     rax, [rsi+18h]
0x14001da45  cmp     rcx, rax
0x14001da48  jz      short loc_14001DA56
0x14001da4a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001da51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001da56  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001da5d  mov     rcx, rsi; void *
0x14001da60  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001da65  jmp     short loc_14001DA31
0x14001da67  lea     rax, [rdi+1]
0x14001da6b  cmp     rax, 1
0x14001da6f  jbe     short loc_14001DA7A
0x14001da71  mov     rcx, rdi; hObject
0x14001da74  call    cs:__imp_CloseHandle
0x14001da7a  add     rsp, 38h
0x14001da7e  pop     r15
0x14001da80  pop     r14
0x14001da82  pop     r13
0x14001da84  pop     r12
0x14001da86  pop     rdi
0x14001da87  pop     rsi
0x14001da88  pop     rbp
0x14001da89  pop     rbx
0x14001da8a  retn
```
