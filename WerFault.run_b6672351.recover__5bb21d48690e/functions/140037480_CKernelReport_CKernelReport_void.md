# CKernelReport::~CKernelReport(void)

- ea: `0x140037480`
- end: `0x14003758c`
- name: `??1CKernelReport@@QEAA@XZ`
- size: `268`
- prototype: `void(CKernelReport *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140036e5c`
- `0x14005fe91`

## callees

- `0x140002748`
- `0x1400372dc`
- `0x1400373d0`
- `0x140037480`
- `0x140049798`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400374e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037573`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400374e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140037573`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140037500`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140037500`

## string_xrefs

- `0x1400374a4`: `Reporting not cancelled during destructor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CKernelReport::~CKernelReport(CKernelReport *this)
{
  void *v2; // rcx
  CPluginList *v3; // rcx
  char *v4; // rcx
  CPluginList *v5; // rcx
  void *v6; // rcx
  wil::details *v7; // [rsp+20h] [rbp-18h]
  const char *v8; // [rsp+30h] [rbp-8h]
  wil::details::in1diag4 *retaddr; // [rsp+38h] [rbp+0h]

  if ( (unsigned __int64)(*((_QWORD *)this + 81) + 1LL) > 1 )
  {
    LODWORD(v7) = 0x80000000;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x168,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::~CKernelReport",
      v7,
      (int)"Reporting not cancelled during destructor",
      v8);
    v2 = (void *)*((_QWORD *)this + 81);
    *((_QWORD *)this + 81) = 0;
    if ( (unsigned __int64)v2 + 1 > 1 )
      CloseHandle(v2);
  }
  if ( *((_WORD *)this + 64) )
    DeleteFileW((LPCWSTR)this + 64);
  v3 = (CPluginList *)*((_QWORD *)this + 85);
  *((_QWORD *)this + 85) = 0;
  if ( v3 )
    WerPluginsDestroy(v3);
  v4 = (char *)*((_QWORD *)this + 86);
  if ( v4 != (char *)this + 704 )
    operator delete(v4, (const struct std::nothrow_t *)&std::nothrow);
  v5 = (CPluginList *)*((_QWORD *)this + 85);
  if ( v5 )
    WerPluginsDestroy(v5);
  utl::list<KERNEL_QUEUED_REPORT,utl::allocator<KERNEL_QUEUED_REPORT>>::~list<KERNEL_QUEUED_REPORT,utl::allocator<KERNEL_QUEUED_REPORT>>((char *)this + 656);
  v6 = (void *)*((_QWORD *)this + 81);
  if ( (unsigned __int64)v6 + 1 > 1 )
    CloseHandle(v6);
}

```

## disassembly

```asm
0x140037480  mov     [rsp+arg_0], rbx
0x140037485  push    rdi; char *
0x140037486  sub     rsp, 30h
0x14003748a  mov     rbx, rcx
0x14003748d  mov     rax, [rcx+288h]
0x140037494  inc     rax
0x140037497  xor     edi, edi
0x140037499  cmp     rax, 1
0x14003749d  jbe     short loc_1400374F4
0x14003749f  mov     rcx, [rsp+38h]; this
0x1400374a4  lea     rax, aReportingNotCa; "Reporting not cancelled during destruct"...
0x1400374ab  mov     qword ptr [rsp+38h+var_10], rax; int
0x1400374b0  mov     dword ptr [rsp+38h+var_18], 80000000h; wil::details *
0x1400374b8  lea     r9, aCkernelreportC_4; "CKernelReport::~CKernelReport"
0x1400374bf  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x1400374c6  mov     edx, 168h; void *
0x1400374cb  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400374d0  mov     rcx, [rbx+288h]; hObject
0x1400374d7  mov     [rbx+288h], rdi
0x1400374de  lea     rax, [rcx+1]
0x1400374e2  cmp     rax, 1
0x1400374e6  jbe     short loc_1400374F4
0x1400374e8  call    cs:__imp_CloseHandle
0x1400374ef  nop     dword ptr [rax+rax+00h]
0x1400374f4  lea     rcx, [rbx+80h]; lpFileName
0x1400374fb  cmp     [rcx], di
0x1400374fe  jz      short loc_14003750C
0x140037500  call    cs:__imp_DeleteFileW
0x140037507  nop     dword ptr [rax+rax+00h]
0x14003750c  mov     rcx, [rbx+2A8h]; this
0x140037513  mov     [rbx+2A8h], rdi
0x14003751a  test    rcx, rcx
0x14003751d  jz      short loc_140037525
0x14003751f  call    ?WerPluginsDestroy@@YAJPEAX@Z; WerPluginsDestroy(void *)
0x140037524  nop
0x140037525  mov     rcx, [rbx+2B0h]; void *
0x14003752c  lea     rax, [rbx+2C0h]
0x140037533  cmp     rcx, rax
0x140037536  jz      short loc_140037544
0x140037538  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003753f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140037544  mov     rcx, [rbx+2A8h]; this
0x14003754b  test    rcx, rcx
0x14003754e  jz      short loc_140037556
0x140037550  call    ?WerPluginsDestroy@@YAJPEAX@Z; WerPluginsDestroy(void *)
0x140037555  nop
0x140037556  lea     rcx, [rbx+290h]
0x14003755d  call    ??1?$list@UKERNEL_QUEUED_REPORT@@V?$allocator@UKERNEL_QUEUED_REPORT@@@utl@@@utl@@QEAA@XZ; utl::list<KERNEL_QUEUED_REPORT,utl::allocator<KERNEL_QUEUED_REPORT>>::~list<KERNEL_QUEUED_REPORT,utl::allocator<KERNEL_QUEUED_REPORT>>(void)
0x140037562  mov     rcx, [rbx+288h]; hObject
0x140037569  lea     rax, [rcx+1]
0x14003756d  cmp     rax, 1
0x140037571  jbe     short loc_140037580
0x140037573  call    cs:__imp_CloseHandle
0x14003757a  nop     dword ptr [rax+rax+00h]
0x14003757f  nop
0x140037580  mov     rbx, [rsp+38h+arg_0]
0x140037585  add     rsp, 30h
0x140037589  pop     rdi
0x14003758a  retn
```
