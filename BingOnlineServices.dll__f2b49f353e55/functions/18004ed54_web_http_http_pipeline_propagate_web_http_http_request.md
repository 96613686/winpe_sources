# web::http::http_pipeline::propagate(web::http::http_request)

- ea: `0x18004ed54`
- end: `0x18004ee47`
- name: `?propagate@http_pipeline@http@web@@QEAA?AV?$task@Vhttp_response@http@web@@@pplx@@Vhttp_request@23@@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18004f010`

## callees

- `0x18000fa74`
- `0x180012d88`
- `0x1800148ac`
- `0x18004ed54`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ed96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ed96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004edde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004edde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ed7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ed7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall web::http::http_pipeline::propagate(struct _RTL_CRITICAL_SECTION *a1, __int64 a2, _QWORD *a3)
{
  DWORD CurrentThreadId; // ebp
  __int64 *DebugInfo; // rdx
  void (__fastcall *v9)(__int64, __int64, _QWORD *); // r9
  __int64 v10; // r10
  std::_Ref_count_base *v11; // rcx
  __int128 v13; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v14[3]; // [rsp+38h] [rbp-30h] BYREF

  v13 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( HIDWORD(a1[2].LockSemaphore) == CurrentThreadId )
  {
    ++LODWORD(a1[2].LockSemaphore);
  }
  else
  {
    EnterCriticalSection(a1 + 1);
    HIDWORD(a1[2].LockSemaphore) = CurrentThreadId;
    LODWORD(a1[2].LockSemaphore) = 1;
  }
  DebugInfo = (__int64 *)a1->DebugInfo;
  if ( !((__int64)(*(_QWORD *)&a1->LockCount - (unsigned __int64)a1->DebugInfo) >> 4) )
    DebugInfo = (__int64 *)&a1->LockSemaphore;
  std::shared_ptr<web::http::http_pipeline_stage>::operator=(&v13, DebugInfo);
  if ( LODWORD(a1[2].LockSemaphore)-- == 1 )
  {
    HIDWORD(a1[2].LockSemaphore) = -1;
    LeaveCriticalSection(a1 + 1);
  }
  std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(v14, a3);
  v9(v10, a2, v14);
  if ( *((_QWORD *)&v13 + 1) )
    std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v13 + 1));
  v11 = (std::_Ref_count_base *)a3[1];
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  return a2;
}

```

## disassembly

```asm
0x18004ed54  mov     rax, rsp
0x18004ed57  mov     [rax+8], rbx
0x18004ed5b  mov     [rax+20h], rbp
0x18004ed5f  mov     [rax+18h], r8
0x18004ed63  push    rsi
0x18004ed64  push    rdi
0x18004ed65  push    r14
0x18004ed67  sub     rsp, 50h
0x18004ed6b  mov     rsi, r8
0x18004ed6e  mov     rdi, rdx
0x18004ed71  mov     r14, rcx
0x18004ed74  xorps   xmm0, xmm0
0x18004ed77  movdqu  xmmword ptr [rax-40h], xmm0
0x18004ed7c  call    cs:__imp_GetCurrentThreadId
0x18004ed82  mov     ebp, eax
0x18004ed84  mov     ecx, [r14+6Ch]
0x18004ed88  cmp     ecx, eax
0x18004ed8a  jnz     short loc_18004ED92
0x18004ed8c  inc     dword ptr [r14+68h]
0x18004ed90  jmp     short loc_18004EDA8
0x18004ed92  lea     rcx, [r14+28h]; lpCriticalSection
0x18004ed96  call    cs:__imp_EnterCriticalSection
0x18004ed9c  mov     [r14+6Ch], ebp
0x18004eda0  mov     dword ptr [r14+68h], 1
0x18004eda8  mov     rdx, [r14]
0x18004edab  mov     r8, [r14+8]
0x18004edaf  sub     r8, rdx
0x18004edb2  sar     r8, 4
0x18004edb6  lea     rax, [r14+18h]
0x18004edba  test    r8, r8
0x18004edbd  cmovz   rdx, rax
0x18004edc1  lea     rcx, [rsp+68h+var_40]
0x18004edc6  call    ??4?$shared_ptr@Vhttp_pipeline_stage@http@web@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<web::http::http_pipeline_stage>::operator=(std::shared_ptr<web::http::http_pipeline_stage> const &)
0x18004edcb  sub     dword ptr [r14+68h], 1
0x18004edd0  jnz     short loc_18004EDE4
0x18004edd2  mov     dword ptr [r14+6Ch], 0FFFFFFFFh
0x18004edda  lea     rcx, [r14+28h]; lpCriticalSection
0x18004edde  call    cs:__imp_LeaveCriticalSection
0x18004ede4  mov     r10, [rsp+68h+var_40]
0x18004ede9  mov     rax, [r10]
0x18004edec  mov     r9, [rax+8]
0x18004edf0  mov     rdx, rsi
0x18004edf3  lea     rcx, [rsp+68h+var_30]
0x18004edf8  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18004edfd  lea     r8, [rsp+68h+var_30]
0x18004ee02  mov     rdx, rdi
0x18004ee05  mov     rcx, r10
0x18004ee08  mov     rax, r9
0x18004ee0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee10  nop
0x18004ee11  mov     rcx, [rsp+68h+var_38]; this
0x18004ee16  test    rcx, rcx
0x18004ee19  jz      short loc_18004EE21
0x18004ee1b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004ee20  nop
0x18004ee21  mov     rcx, [rsi+8]; this
0x18004ee25  test    rcx, rcx
0x18004ee28  jz      short loc_18004EE2F
0x18004ee2a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004ee2f  mov     rax, rdi
0x18004ee32  lea     r11, [rsp+68h+var_18]
0x18004ee37  mov     rbx, [r11+20h]
0x18004ee3b  mov     rbp, [r11+38h]
0x18004ee3f  mov     rsp, r11
0x18004ee42  pop     r14
0x18004ee44  pop     rdi
0x18004ee45  pop     rsi
0x18004ee46  retn
```
