# CHangReport::~CHangReport(void)

- ea: `0x14001d60c`
- end: `0x14001d76d`
- name: `??1CHangReport@@UEAA@XZ`
- size: `353`
- prototype: `void __fastcall(CHangReport *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x14001d7c0`
- `0x140022728`
- `0x1400275e0`
- `0x14005be5f`

## callees

- `0x140002728`
- `0x140004230`
- `0x14001d60c`
- `0x14001d800`
- `0x14004655c`
- `0x140056f50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001d766`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001d691`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001d6a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001d6b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001d691`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001d6a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001d6b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d6de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d6f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d70c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d6de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d6f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d70c`
- `wer!WerReportCloseHandle` at `0x14001d71e`
- `wer!WerReportCloseHandle` at `0x14001d71e`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x14001d6c7`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x14001d6c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CHangReport::~CHangReport(CHangReport *this)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rcx
  struct _TP_WAIT *v4; // rcx
  struct _TP_WAIT *v5; // rcx
  struct _TP_WAIT *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  char *v12; // rcx
  CPluginList *v13; // rcx

  *(_QWORD *)this = &CHangReport::`vftable';
  CHangReport::Cleanup((CPluginList **)this);
  `eh vector destructor iterator'(
    (char *)this + 24768,
    8u,
    0xFu,
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>);
  while ( 1 )
  {
    v2 = (_QWORD *)*((_QWORD *)this + 3095);
    if ( v2 == (_QWORD *)-1LL )
      break;
    *((_QWORD *)this + 3095) = *v2;
    v3 = (_QWORD *)v2[1];
    if ( v3 != v2 + 3 )
      operator delete(v3, (const struct std::nothrow_t *)&std::nothrow);
    operator delete(v2, (const struct std::nothrow_t *)&std::nothrow);
  }
  v4 = (struct _TP_WAIT *)*((_QWORD *)this + 3094);
  if ( v4 )
    CloseThreadpoolWait(v4);
  v5 = (struct _TP_WAIT *)*((_QWORD *)this + 3093);
  if ( v5 )
    CloseThreadpoolWait(v5);
  v6 = (struct _TP_WAIT *)*((_QWORD *)this + 3092);
  if ( v6 )
    CloseThreadpoolWait(v6);
  v7 = (void *)*((_QWORD *)this + 3091);
  if ( v7 )
    PowerSettingUnregisterNotification(v7);
  v8 = (void *)*((_QWORD *)this + 3090);
  if ( (unsigned __int64)v8 + 1 > 1 )
    CloseHandle(v8);
  v9 = (void *)*((_QWORD *)this + 3089);
  if ( (unsigned __int64)v9 + 1 > 1 )
    CloseHandle(v9);
  v10 = (void *)*((_QWORD *)this + 3088);
  if ( (unsigned __int64)v10 + 1 > 1 )
    CloseHandle(v10);
  v11 = (void *)*((_QWORD *)this + 3055);
  if ( v11 )
    WerReportCloseHandle(v11);
  CElevatedDataCollection::~CElevatedDataCollection((CHangReport *)((char *)this + 22544));
  v12 = (char *)*((_QWORD *)this + 13);
  if ( v12 != (char *)this + 120 )
    operator delete(v12, (const struct std::nothrow_t *)&std::nothrow);
  v13 = (CPluginList *)*((_QWORD *)this + 9);
  if ( v13 )
    WerPluginsDestroy(v13);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x14001d60c  mov     [rsp+arg_0], rbx
0x14001d611  push    rdi
0x14001d612  sub     rsp, 20h
0x14001d616  mov     rbx, rcx
0x14001d619  lea     rax, ??_7CHangReport@@6B@; const CHangReport::`vftable'
0x14001d620  mov     [rcx], rax
0x14001d623  call    ?Cleanup@CHangReport@@MEAAXXZ; CHangReport::Cleanup(void)
0x14001d628  lea     rcx, [rbx+60C0h]; void *
0x14001d62f  lea     r9, ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; void (*)(void *)
0x14001d636  mov     edx, 8; unsigned __int64
0x14001d63b  lea     r8d, [rdx+7]; unsigned __int64
0x14001d63f  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14001d644  mov     rdi, [rbx+60B8h]
0x14001d64b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14001d64f  jz      short loc_14001D685
0x14001d651  mov     rax, [rdi]
0x14001d654  mov     [rbx+60B8h], rax
0x14001d65b  mov     rcx, [rdi+8]; void *
0x14001d65f  lea     rax, [rdi+18h]
0x14001d663  cmp     rcx, rax
0x14001d666  jz      short loc_14001D674
0x14001d668  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001d66f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001d674  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001d67b  mov     rcx, rdi; void *
0x14001d67e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001d683  jmp     short loc_14001D644
0x14001d685  mov     rcx, [rbx+60B0h]; pwa
0x14001d68c  test    rcx, rcx
0x14001d68f  jz      short loc_14001D697
0x14001d691  call    cs:__imp_CloseThreadpoolWait
0x14001d697  mov     rcx, [rbx+60A8h]; pwa
0x14001d69e  test    rcx, rcx
0x14001d6a1  jz      short loc_14001D6A9
0x14001d6a3  call    cs:__imp_CloseThreadpoolWait
0x14001d6a9  mov     rcx, [rbx+60A0h]; pwa
0x14001d6b0  test    rcx, rcx
0x14001d6b3  jz      short loc_14001D6BB
0x14001d6b5  call    cs:__imp_CloseThreadpoolWait
0x14001d6bb  mov     rcx, [rbx+6098h]; RegistrationHandle
0x14001d6c2  test    rcx, rcx
0x14001d6c5  jz      short loc_14001D6CD
0x14001d6c7  call    cs:__imp_PowerSettingUnregisterNotification
0x14001d6cd  mov     rcx, [rbx+6090h]; hObject
0x14001d6d4  lea     rax, [rcx+1]
0x14001d6d8  cmp     rax, 1
0x14001d6dc  jbe     short loc_14001D6E4
0x14001d6de  call    cs:__imp_CloseHandle
0x14001d6e4  mov     rcx, [rbx+6088h]; hObject
0x14001d6eb  lea     rax, [rcx+1]
0x14001d6ef  cmp     rax, 1
0x14001d6f3  jbe     short loc_14001D6FB
0x14001d6f5  call    cs:__imp_CloseHandle
0x14001d6fb  mov     rcx, [rbx+6080h]; hObject
0x14001d702  lea     rax, [rcx+1]
0x14001d706  cmp     rax, 1
0x14001d70a  jbe     short loc_14001D712
0x14001d70c  call    cs:__imp_CloseHandle
0x14001d712  mov     rcx, [rbx+5F78h]; hReportHandle
0x14001d719  test    rcx, rcx
0x14001d71c  jz      short loc_14001D724
0x14001d71e  call    cs:__imp_WerReportCloseHandle
0x14001d724  lea     rcx, [rbx+5810h]; this
0x14001d72b  call    ??1CElevatedDataCollection@@QEAA@XZ; CElevatedDataCollection::~CElevatedDataCollection(void)
0x14001d730  mov     rcx, [rbx+68h]; void *
0x14001d734  lea     rax, [rbx+78h]
0x14001d738  cmp     rcx, rax
0x14001d73b  jz      short loc_14001D749
0x14001d73d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001d744  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001d749  mov     rcx, [rbx+48h]; this
0x14001d74d  test    rcx, rcx
0x14001d750  jz      short loc_14001D758
0x14001d752  call    ?WerPluginsDestroy@@YAJPEAX@Z; WerPluginsDestroy(void *)
0x14001d757  nop
0x14001d758  lea     rcx, [rbx+10h]
0x14001d75c  mov     rbx, [rsp+28h+arg_0]
0x14001d761  add     rsp, 20h
0x14001d765  pop     rdi
0x14001d766  jmp     cs:__imp_DeleteCriticalSection
```
