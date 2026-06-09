# CHangReport::~CHangReport(void)

- ea: `0x14001e8d0`
- end: `0x14001ea66`
- name: `??1CHangReport@@UEAA@XZ`
- size: `406`
- prototype: `void __fastcall(CHangReport *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x14001eac0`
- `0x140023dc8`
- `0x140028fd0`
- `0x14005fbf0`

## callees

- `0x140002748`
- `0x140004280`
- `0x14001e8d0`
- `0x14001ecd0`
- `0x140049798`
- `0x14005ac6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001ea5a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001e955`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001e96d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001e985`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001e955`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001e96d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001e985`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001e9ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001e9d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001e9f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001e9ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001e9d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001e9f4`
- `wer!WerReportCloseHandle` at `0x14001ea0c`
- `wer!WerReportCloseHandle` at `0x14001ea0c`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x14001e99d`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x14001e99d`

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
0x14001e8d0  mov     [rsp+arg_0], rbx
0x14001e8d5  push    rdi
0x14001e8d6  sub     rsp, 20h
0x14001e8da  mov     rbx, rcx
0x14001e8dd  lea     rax, ??_7CHangReport@@6B@; const CHangReport::`vftable'
0x14001e8e4  mov     [rcx], rax
0x14001e8e7  call    ?Cleanup@CHangReport@@MEAAXXZ; CHangReport::Cleanup(void)
0x14001e8ec  lea     rcx, [rbx+60C0h]; void *
0x14001e8f3  lea     r9, ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; void (*)(void *)
0x14001e8fa  mov     edx, 8; unsigned __int64
0x14001e8ff  lea     r8d, [rdx+7]; unsigned __int64
0x14001e903  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14001e908  mov     rdi, [rbx+60B8h]
0x14001e90f  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14001e913  jz      short loc_14001E949
0x14001e915  mov     rax, [rdi]
0x14001e918  mov     [rbx+60B8h], rax
0x14001e91f  mov     rcx, [rdi+8]; void *
0x14001e923  lea     rax, [rdi+18h]
0x14001e927  cmp     rcx, rax
0x14001e92a  jz      short loc_14001E938
0x14001e92c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001e933  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001e938  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001e93f  mov     rcx, rdi; void *
0x14001e942  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001e947  jmp     short loc_14001E908
0x14001e949  mov     rcx, [rbx+60B0h]; pwa
0x14001e950  test    rcx, rcx
0x14001e953  jz      short loc_14001E961
0x14001e955  call    cs:__imp_CloseThreadpoolWait
0x14001e95c  nop     dword ptr [rax+rax+00h]
0x14001e961  mov     rcx, [rbx+60A8h]; pwa
0x14001e968  test    rcx, rcx
0x14001e96b  jz      short loc_14001E979
0x14001e96d  call    cs:__imp_CloseThreadpoolWait
0x14001e974  nop     dword ptr [rax+rax+00h]
0x14001e979  mov     rcx, [rbx+60A0h]; pwa
0x14001e980  test    rcx, rcx
0x14001e983  jz      short loc_14001E991
0x14001e985  call    cs:__imp_CloseThreadpoolWait
0x14001e98c  nop     dword ptr [rax+rax+00h]
0x14001e991  mov     rcx, [rbx+6098h]; RegistrationHandle
0x14001e998  test    rcx, rcx
0x14001e99b  jz      short loc_14001E9A9
0x14001e99d  call    cs:__imp_PowerSettingUnregisterNotification
0x14001e9a4  nop     dword ptr [rax+rax+00h]
0x14001e9a9  mov     rcx, [rbx+6090h]; hObject
0x14001e9b0  lea     rax, [rcx+1]
0x14001e9b4  cmp     rax, 1
0x14001e9b8  jbe     short loc_14001E9C6
0x14001e9ba  call    cs:__imp_CloseHandle
0x14001e9c1  nop     dword ptr [rax+rax+00h]
0x14001e9c6  mov     rcx, [rbx+6088h]; hObject
0x14001e9cd  lea     rax, [rcx+1]
0x14001e9d1  cmp     rax, 1
0x14001e9d5  jbe     short loc_14001E9E3
0x14001e9d7  call    cs:__imp_CloseHandle
0x14001e9de  nop     dword ptr [rax+rax+00h]
0x14001e9e3  mov     rcx, [rbx+6080h]; hObject
0x14001e9ea  lea     rax, [rcx+1]
0x14001e9ee  cmp     rax, 1
0x14001e9f2  jbe     short loc_14001EA00
0x14001e9f4  call    cs:__imp_CloseHandle
0x14001e9fb  nop     dword ptr [rax+rax+00h]
0x14001ea00  mov     rcx, [rbx+5F78h]; hReportHandle
0x14001ea07  test    rcx, rcx
0x14001ea0a  jz      short loc_14001EA18
0x14001ea0c  call    cs:__imp_WerReportCloseHandle
0x14001ea13  nop     dword ptr [rax+rax+00h]
0x14001ea18  lea     rcx, [rbx+5810h]; this
0x14001ea1f  call    ??1CElevatedDataCollection@@QEAA@XZ; CElevatedDataCollection::~CElevatedDataCollection(void)
0x14001ea24  mov     rcx, [rbx+68h]; void *
0x14001ea28  lea     rax, [rbx+78h]
0x14001ea2c  cmp     rcx, rax
0x14001ea2f  jz      short loc_14001EA3D
0x14001ea31  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001ea38  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001ea3d  mov     rcx, [rbx+48h]; this
0x14001ea41  test    rcx, rcx
0x14001ea44  jz      short loc_14001EA4C
0x14001ea46  call    ?WerPluginsDestroy@@YAJPEAX@Z; WerPluginsDestroy(void *)
0x14001ea4b  nop
0x14001ea4c  lea     rcx, [rbx+10h]
0x14001ea50  mov     rbx, [rsp+28h+arg_0]
0x14001ea55  add     rsp, 20h
0x14001ea59  pop     rdi
0x14001ea5a  jmp     cs:__imp_DeleteCriticalSection
```
