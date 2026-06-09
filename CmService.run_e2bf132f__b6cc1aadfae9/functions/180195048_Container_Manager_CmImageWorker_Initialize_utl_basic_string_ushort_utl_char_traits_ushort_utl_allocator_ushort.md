# Container::Manager::CmImageWorker::Initialize(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&,Container::Manager::CmImageWorkerContextType)

- ea: `0x180195048`
- end: `0x180195225`
- name: `?Initialize@CmImageWorker@Manager@Container@@AEAAJ$$QEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4CmImageWorkerContextType@23@@Z`
- size: `477`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18019522c`
- `0x1801952ec`

## callees

- `0x180008bf0`
- `0x18000da68`
- `0x18000da88`
- `0x18002e2b4`
- `0x1800471dc`
- `0x18004e6c4`
- `0x180195048`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1801950d0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1801950d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18019514a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180195195`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1801951e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18019514a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180195195`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1801951e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180195184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180195184`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801951a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801951a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801950b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180195205`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801950b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180195205`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180195066`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180195066`

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
0x180195048  push    rbx
0x18019504a  push    rbp
0x18019504b  push    rsi
0x18019504c  push    rdi
0x18019504d  push    r12
0x18019504f  push    r13
0x180195051  push    r14
0x180195053  push    r15
0x180195055  sub     rsp, 48h
0x180195059  mov     r12d, r8d
0x18019505c  mov     r13, rdx
0x18019505f  mov     rsi, rcx
0x180195062  xor     edx, edx; lpName
0x180195064  xor     ecx, ecx; lpJobAttributes
0x180195066  call    cs:__imp_CreateJobObjectW
0x18019506d  nop     dword ptr [rax+rax+00h]
0x180195072  mov     rdi, rax
0x180195075  mov     [rsp+88h+hObject], rax
0x18019507d  inc     rax
0x180195080  test    rax, 0FFFFFFFFFFFFFFFEh
0x180195086  jnz     short loc_1801950C3
0x180195088  mov     rcx, [rsp+88h]; this
0x180195090  lea     r8, aOnecoreBaseGen_16; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180195097  mov     edx, 0EDh; void *
0x18019509c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801950a1  mov     ebx, eax
0x1801950a3  lea     rcx, [rdi-1]
0x1801950a7  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801950ab  ja      short loc_1801950BC
0x1801950ad  mov     rcx, rdi; hObject
0x1801950b0  call    cs:__imp_CloseHandle
0x1801950b7  nop     dword ptr [rax+rax+00h]
0x1801950bc  mov     eax, ebx
0x1801950be  jmp     loc_180195213
0x1801950c3  xor     r8d, r8d; pcbe
0x1801950c6  mov     rdx, rsi; pv
0x1801950c9  lea     rcx, ?OnWorkerProcessExited@CmImageWorker@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1801950d0  call    cs:__imp_CreateThreadpoolWait
0x1801950d7  nop     dword ptr [rax+rax+00h]
0x1801950dc  mov     rbx, rax
0x1801950df  test    rax, rax
0x1801950e2  jnz     short loc_180195101
0x1801950e4  mov     rcx, [rsp+88h]; this
0x1801950ec  lea     r8, aOnecoreBaseGen_16; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1801950f3  mov     edx, 0F3h; void *
0x1801950f8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801950fd  mov     ebx, eax
0x1801950ff  jmp     short loc_1801950AD
0x180195101  lea     rcx, [rsp+88h+var_60]
0x180195106  call    ??$make_shared@V?$CompletionEvent@X@Csl@@$$V@utl@@YA?AV?$shared_ptr@V?$CompletionEvent@X@Csl@@@0@XZ; utl::make_shared<Csl::CompletionEvent<void>,>(void)
0x18019510b  mov     r15, [rsp+88h+var_60]
0x180195110  test    r15, r15
0x180195113  jnz     short loc_18019515D
0x180195115  mov     rcx, [rsp+88h]; this
0x18019511d  mov     esi, 8007000Eh
0x180195122  mov     r9d, esi; char *
0x180195125  lea     r8, aOnecoreBaseGen_16; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x18019512c  mov     edx, 0F7h; void *
0x180195131  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195136  nop
0x180195137  mov     rcx, [rsp+88h+var_58]; this
0x18019513c  test    rcx, rcx
0x18019513f  jz      short loc_180195147
0x180195141  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180195146  nop
0x180195147  mov     rcx, rbx; pwa
0x18019514a  call    cs:__imp_CloseThreadpoolWait
0x180195151  nop     dword ptr [rax+rax+00h]
0x180195156  mov     ebx, esi
0x180195158  jmp     loc_1801950AD
0x18019515d  lea     rcx, [rsi+30h]
0x180195161  lea     rdx, [rsp+88h+hObject]
0x180195169  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18019516e  lea     r14, [rsi+38h]
0x180195172  lea     rax, [rsp+88h+var_68]
0x180195177  cmp     r14, rax
0x18019517a  jz      short loc_1801951B4
0x18019517c  mov     rbp, [r14]
0x18019517f  test    rbp, rbp
0x180195182  jz      short loc_1801951AF
0x180195184  call    cs:__imp_GetLastError
0x18019518b  nop     dword ptr [rax+rax+00h]
0x180195190  mov     edi, eax
0x180195192  mov     rcx, rbp; pwa
0x180195195  call    cs:__imp_CloseThreadpoolWait
0x18019519c  nop     dword ptr [rax+rax+00h]
0x1801951a1  mov     ecx, edi; dwErrCode
0x1801951a3  call    cs:__imp_SetLastError
0x1801951aa  nop     dword ptr [rax+rax+00h]
0x1801951af  mov     [r14], rbx
0x1801951b2  xor     ebx, ebx
0x1801951b4  mov     [rsi+20h], r15
0x1801951b8  mov     rcx, [rsi+28h]; this
0x1801951bc  mov     rax, [rsp+88h+var_58]
0x1801951c1  mov     [rsi+28h], rax
0x1801951c5  test    rcx, rcx
0x1801951c8  jz      short loc_1801951D0
0x1801951ca  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1801951cf  nop
0x1801951d0  mov     rdx, r13
0x1801951d3  mov     rcx, rsi
0x1801951d6  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1801951db  mov     [rsi+58h], r12d
0x1801951df  test    rbx, rbx
0x1801951e2  jz      short loc_1801951F3
0x1801951e4  mov     rcx, rbx; pwa
0x1801951e7  call    cs:__imp_CloseThreadpoolWait
0x1801951ee  nop     dword ptr [rax+rax+00h]
0x1801951f3  mov     rcx, [rsp+88h+hObject]; hObject
0x1801951fb  lea     rax, [rcx-1]
0x1801951ff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180195203  ja      short loc_180195211
0x180195205  call    cs:__imp_CloseHandle
0x18019520c  nop     dword ptr [rax+rax+00h]
0x180195211  xor     eax, eax
0x180195213  add     rsp, 48h
0x180195217  pop     r15
0x180195219  pop     r14
0x18019521b  pop     r13
0x18019521d  pop     r12
0x18019521f  pop     rdi
0x180195220  pop     rsi
0x180195221  pop     rbp
0x180195222  pop     rbx
0x180195223  retn
```
