# File::~File(void)

- ea: `0x1800310a8`
- end: `0x180031194`
- name: `??1File@@QEAA@XZ`
- size: `236`
- prototype: `void __fastcall(File *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180026628`

## callees

- `0x18000a724`
- `0x18001585c`
- `0x1800225a8`
- `0x180031084`
- `0x1800310a8`
- `0x1800311ac`
- `0x180032350`
- `0x180034fc0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800310e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800310e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800310c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800310c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800310db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800310db`

## pseudocode

```c
void __fastcall File::~File(File *this)
{
  struct _TP_TIMER *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 82);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 82), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 82));
    *((_QWORD *)this + 82) = 0;
  }
  if ( *((_BYTE *)this + 833) )
  {
    v3 = *((_QWORD *)this + 84);
    *((_QWORD *)this + 84) = 0;
    v4 = v3;
    CloseAndDelete(&v4);
  }
  else
  {
    File::FullFlush(this);
  }
  *((_QWORD *)this + 96) = -1;
  _InterlockedDecrement(&g_ActiveChannels);
  utl::condition_variable_any::~condition_variable_any((File *)((char *)this + 744));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit((char *)this + 712);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit((char *)this + 680);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 672);
  FileView::~FileView((File *)((char *)this + 160));
  utl::unique_ptr<FileHeader,utl::default_delete<FileHeader>>::~unique_ptr<FileHeader,utl::default_delete<FileHeader>>((char *)this + 144);
}

```

## disassembly

```asm
0x1800310a8  mov     [rsp+arg_0], rcx
0x1800310ad  push    rbx
0x1800310ae  sub     rsp, 20h
0x1800310b2  mov     rbx, rcx
0x1800310b5  mov     rcx, [rcx+290h]; pti
0x1800310bc  test    rcx, rcx
0x1800310bf  jz      short loc_1800310F9
0x1800310c1  xor     r9d, r9d; msWindowLength
0x1800310c4  xor     r8d, r8d; msPeriod
0x1800310c7  xor     edx, edx; pftDueTime
0x1800310c9  call    cs:__imp_SetThreadpoolTimer
0x1800310cf  mov     edx, 1; fCancelPendingCallbacks
0x1800310d4  mov     rcx, [rbx+290h]; pti
0x1800310db  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800310e1  mov     rcx, [rbx+290h]; pti
0x1800310e8  call    cs:__imp_CloseThreadpoolTimer
0x1800310ee  mov     qword ptr [rbx+290h], 0
0x1800310f9  cmp     byte ptr [rbx+341h], 0
0x180031100  jz      short loc_180031125
0x180031102  mov     rax, [rbx+2A0h]
0x180031109  mov     qword ptr [rbx+2A0h], 0
0x180031114  mov     [rsp+28h+arg_8], rax
0x180031119  lea     rcx, [rsp+28h+arg_8]
0x18003111e  call    CloseAndDelete
0x180031123  jmp     short loc_18003112E
0x180031125  mov     rcx, rbx
0x180031128  call    ?FullFlush@File@@QEAAKW4FlushType@@@Z; File::FullFlush(FlushType)
0x18003112d  nop
0x18003112e  jmp     short loc_180031135
0x180031130  mov     rbx, [rsp+28h+arg_0]
0x180031135  mov     qword ptr [rbx+300h], 0FFFFFFFFFFFFFFFFh
0x180031140  lock dec cs:?g_ActiveChannels@@3JA; long g_ActiveChannels
0x180031147  lea     rcx, [rbx+2E8h]; this
0x18003114e  call    ??1condition_variable_any@utl@@QEAA@XZ; utl::condition_variable_any::~condition_variable_any(void)
0x180031153  lea     rcx, [rbx+2C8h]
0x18003115a  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18003115f  lea     rcx, [rbx+2A8h]
0x180031166  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18003116b  lea     rcx, [rbx+2A0h]
0x180031172  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180031177  lea     rcx, [rbx+0A0h]; this
0x18003117e  call    ??1FileView@@QEAA@XZ; FileView::~FileView(void)
0x180031183  lea     rcx, [rbx+90h]
0x18003118a  add     rsp, 20h
0x18003118e  pop     rbx
0x18003118f  jmp     ??1?$unique_ptr@UFileHeader@@U?$default_delete@UFileHeader@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<FileHeader,utl::default_delete<FileHeader>>::~unique_ptr<FileHeader,utl::default_delete<FileHeader>>(void)
```
