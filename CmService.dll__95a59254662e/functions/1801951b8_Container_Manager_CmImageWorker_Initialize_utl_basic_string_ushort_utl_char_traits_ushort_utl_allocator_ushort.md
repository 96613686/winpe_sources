# Container::Manager::CmImageWorker::Initialize(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&,Container::Manager::CmImageWorkerContextType)

- ea: `0x1801951b8`
- end: `0x180195395`
- name: `?Initialize@CmImageWorker@Manager@Container@@AEAAJ$$QEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4CmImageWorkerContextType@23@@Z`
- size: `477`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18019539c`
- `0x18019545c`

## callees

- `0x180008bf0`
- `0x18000da68`
- `0x18000da88`
- `0x18002e2b4`
- `0x1800471dc`
- `0x18004e6c4`
- `0x1801951b8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180195240`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180195240`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1801952ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180195305`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180195357`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1801952ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180195305`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180195357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801952f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801952f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180195313`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180195313`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180195220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180195375`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180195220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180195375`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1801951d6`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1801951d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::CmImageWorker::Initialize(utl::_RefCountBase **pv, __int64 a2, int a3)
{
  char *JobObjectW; // rdi
  const char *v7; // r9
  unsigned int LastError; // ebx
  struct _TP_WAIT *ThreadpoolWait; // rbx
  const char *v11; // r9
  utl::_RefCountBase *v12; // r15
  struct _TP_WAIT **v13; // r14
  struct _TP_WAIT *v14; // rbp
  DWORD v15; // edi
  utl::_RefCountBase *v16; // rcx
  int v17; // [rsp+20h] [rbp-68h] BYREF
  utl::_RefCountBase *v18; // [rsp+28h] [rbp-60h] BYREF
  utl::_RefCountBase *v19; // [rsp+30h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  HANDLE hObject; // [rsp+A8h] [rbp+20h] BYREF

  JobObjectW = (char *)CreateJobObjectW(0, 0);
  hObject = JobObjectW;
  if ( ((unsigned __int64)(JobObjectW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xED,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\lib\\cmimageworker.cpp",
                  v7);
    if ( (unsigned __int64)(JobObjectW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return LastError;
LABEL_3:
    CloseHandle(JobObjectW);
    return LastError;
  }
  ThreadpoolWait = CreateThreadpoolWait(Container::Manager::CmImageWorker::OnWorkerProcessExited, pv, 0);
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xF3,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\lib\\cmimageworker.cpp",
                  v11);
    goto LABEL_3;
  }
  utl::make_shared<Csl::CompletionEvent<void>,>(&v18);
  v12 = v18;
  if ( !v18 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\lib\\cmimageworker.cpp",
      (const char *)0x8007000ELL,
      v17);
    if ( v19 )
      utl::_RefCountBase::_DecStrong(v19);
    CloseThreadpoolWait(ThreadpoolWait);
    LastError = -2147024882;
    goto LABEL_3;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    pv + 6,
    &hObject);
  v13 = pv + 7;
  if ( pv + 7 != (utl::_RefCountBase **)&v17 )
  {
    v14 = *v13;
    if ( *v13 )
    {
      v15 = GetLastError();
      CloseThreadpoolWait(v14);
      SetLastError(v15);
    }
    *v13 = ThreadpoolWait;
    ThreadpoolWait = 0;
  }
  pv[4] = v12;
  v16 = pv[5];
  pv[5] = v19;
  if ( v16 )
    utl::_RefCountBase::_DecStrong(v16);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(pv, a2);
  *((_DWORD *)pv + 22) = a3;
  if ( ThreadpoolWait )
    CloseThreadpoolWait(ThreadpoolWait);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x1801951b8  push    rbx
0x1801951ba  push    rbp
0x1801951bb  push    rsi
0x1801951bc  push    rdi
0x1801951bd  push    r12
0x1801951bf  push    r13
0x1801951c1  push    r14
0x1801951c3  push    r15
0x1801951c5  sub     rsp, 48h
0x1801951c9  mov     r12d, r8d
0x1801951cc  mov     r13, rdx
0x1801951cf  mov     rsi, rcx
0x1801951d2  xor     edx, edx; lpName
0x1801951d4  xor     ecx, ecx; lpJobAttributes
0x1801951d6  call    cs:__imp_CreateJobObjectW
0x1801951dd  nop     dword ptr [rax+rax+00h]
0x1801951e2  mov     rdi, rax
0x1801951e5  mov     [rsp+88h+hObject], rax
0x1801951ed  inc     rax
0x1801951f0  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801951f6  jnz     short loc_180195233
0x1801951f8  mov     rcx, [rsp+88h]; this
0x180195200  lea     r8, aOnecoreBaseGen_16; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180195207  mov     edx, 0EDh; void *
0x18019520c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180195211  mov     ebx, eax
0x180195213  lea     rcx, [rdi-1]
0x180195217  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18019521b  ja      short loc_18019522C
0x18019521d  mov     rcx, rdi; hObject
0x180195220  call    cs:__imp_CloseHandle
0x180195227  nop     dword ptr [rax+rax+00h]
0x18019522c  mov     eax, ebx
0x18019522e  jmp     loc_180195383
0x180195233  xor     r8d, r8d; pcbe
0x180195236  mov     rdx, rsi; pv
0x180195239  lea     rcx, ?OnWorkerProcessExited@CmImageWorker@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180195240  call    cs:__imp_CreateThreadpoolWait
0x180195247  nop     dword ptr [rax+rax+00h]
0x18019524c  mov     rbx, rax
0x18019524f  test    rax, rax
0x180195252  jnz     short loc_180195271
0x180195254  mov     rcx, [rsp+88h]; this
0x18019525c  lea     r8, aOnecoreBaseGen_16; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180195263  mov     edx, 0F3h; void *
0x180195268  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019526d  mov     ebx, eax
0x18019526f  jmp     short loc_18019521D
0x180195271  lea     rcx, [rsp+88h+var_60]
0x180195276  call    ??$make_shared@V?$CompletionEvent@X@Csl@@$$V@utl@@YA?AV?$shared_ptr@V?$CompletionEvent@X@Csl@@@0@XZ; utl::make_shared<Csl::CompletionEvent<void>,>(void)
0x18019527b  mov     r15, [rsp+88h+var_60]
0x180195280  test    r15, r15
0x180195283  jnz     short loc_1801952CD
0x180195285  mov     rcx, [rsp+88h]; this
0x18019528d  mov     esi, 8007000Eh
0x180195292  mov     r9d, esi; char *
0x180195295  lea     r8, aOnecoreBaseGen_16; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x18019529c  mov     edx, 0F7h; void *
0x1801952a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801952a6  nop
0x1801952a7  mov     rcx, [rsp+88h+var_58]; this
0x1801952ac  test    rcx, rcx
0x1801952af  jz      short loc_1801952B7
0x1801952b1  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1801952b6  nop
0x1801952b7  mov     rcx, rbx; pwa
0x1801952ba  call    cs:__imp_CloseThreadpoolWait
0x1801952c1  nop     dword ptr [rax+rax+00h]
0x1801952c6  mov     ebx, esi
0x1801952c8  jmp     loc_18019521D
0x1801952cd  lea     rcx, [rsi+30h]
0x1801952d1  lea     rdx, [rsp+88h+hObject]
0x1801952d9  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1801952de  lea     r14, [rsi+38h]
0x1801952e2  lea     rax, [rsp+88h+var_68]
0x1801952e7  cmp     r14, rax
0x1801952ea  jz      short loc_180195324
0x1801952ec  mov     rbp, [r14]
0x1801952ef  test    rbp, rbp
0x1801952f2  jz      short loc_18019531F
0x1801952f4  call    cs:__imp_GetLastError
0x1801952fb  nop     dword ptr [rax+rax+00h]
0x180195300  mov     edi, eax
0x180195302  mov     rcx, rbp; pwa
0x180195305  call    cs:__imp_CloseThreadpoolWait
0x18019530c  nop     dword ptr [rax+rax+00h]
0x180195311  mov     ecx, edi; dwErrCode
0x180195313  call    cs:__imp_SetLastError
0x18019531a  nop     dword ptr [rax+rax+00h]
0x18019531f  mov     [r14], rbx
0x180195322  xor     ebx, ebx
0x180195324  mov     [rsi+20h], r15
0x180195328  mov     rcx, [rsi+28h]; this
0x18019532c  mov     rax, [rsp+88h+var_58]
0x180195331  mov     [rsi+28h], rax
0x180195335  test    rcx, rcx
0x180195338  jz      short loc_180195340
0x18019533a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18019533f  nop
0x180195340  mov     rdx, r13
0x180195343  mov     rcx, rsi
0x180195346  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18019534b  mov     [rsi+58h], r12d
0x18019534f  test    rbx, rbx
0x180195352  jz      short loc_180195363
0x180195354  mov     rcx, rbx; pwa
0x180195357  call    cs:__imp_CloseThreadpoolWait
0x18019535e  nop     dword ptr [rax+rax+00h]
0x180195363  mov     rcx, [rsp+88h+hObject]; hObject
0x18019536b  lea     rax, [rcx-1]
0x18019536f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180195373  ja      short loc_180195381
0x180195375  call    cs:__imp_CloseHandle
0x18019537c  nop     dword ptr [rax+rax+00h]
0x180195381  xor     eax, eax
0x180195383  add     rsp, 48h
0x180195387  pop     r15
0x180195389  pop     r14
0x18019538b  pop     r13
0x18019538d  pop     r12
0x18019538f  pop     rdi
0x180195390  pop     rsi
0x180195391  pop     rbp
0x180195392  pop     rbx
0x180195393  retn
```
