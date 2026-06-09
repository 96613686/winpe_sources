# CHangReport::Cleanup(void)

- ea: `0x14001ecd0`
- end: `0x14001efc8`
- name: `?Cleanup@CHangReport@@MEAAXXZ`
- size: `760`
- prototype: `void __fastcall(CHangReport *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x14001e8d0`
- `0x140024220`

## callees

- `0x140002748`
- `0x14001ecd0`
- `0x1400207c4`
- `0x140049798`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001edfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001edfa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001ee33`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001ee33`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001ee79`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001eeb2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001eeeb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001ee79`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001eeb2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001eeeb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001ee8a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001eec3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001eefc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001ee8a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001eec3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001eefc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001ee99`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001eed2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001ef0b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001ee99`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001eed2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001ef0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ed87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ee18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ee44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ef28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001efaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ed87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ee18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ee44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ef28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001efaa`
- `wer!WerReportCloseHandle` at `0x14001ef44`
- `wer!WerReportCloseHandle` at `0x14001ef44`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x14001ee60`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x14001ee60`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x14001ecd0  push    rbx
0x14001ecd2  push    rbp
0x14001ecd3  push    rsi
0x14001ecd4  push    rdi
0x14001ecd5  push    r12
0x14001ecd7  push    r13
0x14001ecd9  push    r14
0x14001ecdb  push    r15
0x14001ecdd  sub     rsp, 38h
0x14001ece1  mov     rsi, rcx
0x14001ece4  lea     r8, aChangreportCle; "CHangReport::Cleanup"
0x14001eceb  lea     rdx, [rsp+78h+lpCriticalSection]
0x14001ecf0  call    ?Lock@CHangReport@@IEAA?AV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEB_W@Z; CHangReport::Lock(wchar_t const *)
0x14001ecf5  mov     r13, [rsi+6080h]
0x14001ecfc  xor     r8d, r8d
0x14001ecff  mov     [rsi+6080h], r8
0x14001ed06  mov     rdi, r13
0x14001ed09  mov     r14, [rsi+60B0h]
0x14001ed10  mov     [rsi+60B0h], r8
0x14001ed17  mov     rbp, [rsi+60A8h]
0x14001ed1e  mov     [rsi+60A8h], r8
0x14001ed25  mov     r15, [rsi+60A0h]
0x14001ed2c  mov     [rsi+60A0h], r8
0x14001ed33  mov     rax, [rsi+48h]
0x14001ed37  mov     [rsp+78h+arg_18], rax
0x14001ed3f  mov     [rsi+48h], r8
0x14001ed43  mov     rax, [rsi+5F78h]
0x14001ed4a  mov     [rsp+78h+hReportHandle], rax
0x14001ed52  mov     [rsi+5F78h], r8
0x14001ed59  mov     [rsi+5D60h], r8
0x14001ed60  mov     [rsi+5F70h], r8
0x14001ed67  mov     ebx, r8d
0x14001ed6a  movsxd  rdx, ebx
0x14001ed6d  mov     rcx, [rsi+rdx*8+60C0h]; hObject
0x14001ed75  lea     rax, [rcx+1]
0x14001ed79  cmp     rax, 1
0x14001ed7d  jbe     short loc_14001EDA0
0x14001ed7f  mov     [rsi+rdx*8+60C0h], r8
0x14001ed87  call    cs:__imp_CloseHandle
0x14001ed8e  nop     dword ptr [rax+rax+00h]
0x14001ed93  inc     ebx
0x14001ed95  cmp     ebx, 0Fh
0x14001ed98  mov     r8d, 0
0x14001ed9e  jb      short loc_14001ED6A
0x14001eda0  mov     r12, [rsi+6090h]
0x14001eda7  mov     [rsi+6090h], r8
0x14001edae  mov     rax, [rsi+6088h]
0x14001edb5  mov     [rsp+78h+hObject], rax
0x14001edbd  mov     [rsi+6088h], r8
0x14001edc4  mov     rbx, [rsi+60B8h]
0x14001edcb  mov     qword ptr [rsi+60B8h], 0FFFFFFFFFFFFFFFFh
0x14001edd6  mov     rax, [rsi+6098h]
0x14001eddd  mov     [rsp+78h+RegistrationHandle], rax
0x14001ede5  mov     [rsi+6098h], r8
0x14001edec  cmp     [rsp+78h+var_50], r8b
0x14001edf1  jnz     short loc_14001EDF5
0x14001edf3  int     2Ch; Windows NT - assertion failure
0x14001edf5  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x14001edfa  call    cs:__imp_LeaveCriticalSection
0x14001ee01  nop     dword ptr [rax+rax+00h]
0x14001ee06  lea     rax, [r12+1]
0x14001ee0b  mov     esi, 1
0x14001ee10  cmp     rax, rsi
0x14001ee13  jbe     short loc_14001EE24
0x14001ee15  mov     rcx, r12; hObject
0x14001ee18  call    cs:__imp_CloseHandle
0x14001ee1f  nop     dword ptr [rax+rax+00h]
0x14001ee24  lea     rax, [r13+1]
0x14001ee28  cmp     rax, rsi
0x14001ee2b  jbe     short loc_14001EE50
0x14001ee2d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001ee30  mov     rcx, r13; hHandle
0x14001ee33  call    cs:__imp_WaitForSingleObject
0x14001ee3a  nop     dword ptr [rax+rax+00h]
0x14001ee3f  xor     edi, edi
0x14001ee41  mov     rcx, r13; hObject
0x14001ee44  call    cs:__imp_CloseHandle
0x14001ee4b  nop     dword ptr [rax+rax+00h]
0x14001ee50  mov     rax, [rsp+78h+RegistrationHandle]
0x14001ee58  test    rax, rax
0x14001ee5b  jz      short loc_14001EE6C
0x14001ee5d  mov     rcx, rax; RegistrationHandle
0x14001ee60  call    cs:__imp_PowerSettingUnregisterNotification
0x14001ee67  nop     dword ptr [rax+rax+00h]
0x14001ee6c  test    r15, r15
0x14001ee6f  jz      short loc_14001EEA5
0x14001ee71  xor     r8d, r8d; pftTimeout
0x14001ee74  xor     edx, edx; h
0x14001ee76  mov     rcx, r15; pwa
0x14001ee79  call    cs:__imp_SetThreadpoolWait
0x14001ee80  nop     dword ptr [rax+rax+00h]
0x14001ee85  mov     edx, esi; fCancelPendingCallbacks
0x14001ee87  mov     rcx, r15; pwa
0x14001ee8a  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x14001ee91  nop     dword ptr [rax+rax+00h]
0x14001ee96  mov     rcx, r15; pwa
0x14001ee99  call    cs:__imp_CloseThreadpoolWait
0x14001eea0  nop     dword ptr [rax+rax+00h]
0x14001eea5  test    r14, r14
0x14001eea8  jz      short loc_14001EEDE
0x14001eeaa  xor     r8d, r8d; pftTimeout
0x14001eead  xor     edx, edx; h
0x14001eeaf  mov     rcx, r14; pwa
0x14001eeb2  call    cs:__imp_SetThreadpoolWait
0x14001eeb9  nop     dword ptr [rax+rax+00h]
0x14001eebe  mov     edx, esi; fCancelPendingCallbacks
0x14001eec0  mov     rcx, r14; pwa
0x14001eec3  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x14001eeca  nop     dword ptr [rax+rax+00h]
0x14001eecf  mov     rcx, r14; pwa
0x14001eed2  call    cs:__imp_CloseThreadpoolWait
0x14001eed9  nop     dword ptr [rax+rax+00h]
0x14001eede  test    rbp, rbp
0x14001eee1  jz      short loc_14001EF17
0x14001eee3  xor     r8d, r8d; pftTimeout
0x14001eee6  xor     edx, edx; h
0x14001eee8  mov     rcx, rbp; pwa
0x14001eeeb  call    cs:__imp_SetThreadpoolWait
0x14001eef2  nop     dword ptr [rax+rax+00h]
0x14001eef7  mov     edx, esi; fCancelPendingCallbacks
0x14001eef9  mov     rcx, rbp; pwa
0x14001eefc  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x14001ef03  nop     dword ptr [rax+rax+00h]
0x14001ef08  mov     rcx, rbp; pwa
0x14001ef0b  call    cs:__imp_CloseThreadpoolWait
0x14001ef12  nop     dword ptr [rax+rax+00h]
0x14001ef17  mov     rcx, [rsp+78h+hObject]; hObject
0x14001ef1f  lea     rax, [rcx+1]
0x14001ef23  cmp     rax, rsi
0x14001ef26  jbe     short loc_14001EF34
0x14001ef28  call    cs:__imp_CloseHandle
0x14001ef2f  nop     dword ptr [rax+rax+00h]
0x14001ef34  mov     rax, [rsp+78h+hReportHandle]
0x14001ef3c  test    rax, rax
0x14001ef3f  jz      short loc_14001EF51
0x14001ef41  mov     rcx, rax; hReportHandle
0x14001ef44  call    cs:__imp_WerReportCloseHandle
0x14001ef4b  nop     dword ptr [rax+rax+00h]
0x14001ef50  nop
0x14001ef51  mov     rax, [rsp+78h+arg_18]
0x14001ef59  test    rax, rax
0x14001ef5c  jz      short loc_14001EF67
0x14001ef5e  mov     rcx, rax; this
0x14001ef61  call    ?WerPluginsDestroy@@YAJPEAX@Z; WerPluginsDestroy(void *)
0x14001ef66  nop
0x14001ef67  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14001ef6b  jz      short loc_14001EF9D
0x14001ef6d  mov     rsi, rbx
0x14001ef70  mov     rbx, [rbx]
0x14001ef73  mov     rcx, [rsi+8]; void *
0x14001ef77  lea     rax, [rsi+18h]
0x14001ef7b  cmp     rcx, rax
0x14001ef7e  jz      short loc_14001EF8C
0x14001ef80  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001ef87  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001ef8c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001ef93  mov     rcx, rsi; void *
0x14001ef96  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001ef9b  jmp     short loc_14001EF67
0x14001ef9d  lea     rax, [rdi+1]
0x14001efa1  cmp     rax, 1
0x14001efa5  jbe     short loc_14001EFB6
0x14001efa7  mov     rcx, rdi; hObject
0x14001efaa  call    cs:__imp_CloseHandle
0x14001efb1  nop     dword ptr [rax+rax+00h]
0x14001efb6  add     rsp, 38h
0x14001efba  pop     r15
0x14001efbc  pop     r14
0x14001efbe  pop     r13
0x14001efc0  pop     r12
0x14001efc2  pop     rdi
0x14001efc3  pop     rsi
0x14001efc4  pop     rbp
0x14001efc5  pop     rbx
0x14001efc6  retn
```
