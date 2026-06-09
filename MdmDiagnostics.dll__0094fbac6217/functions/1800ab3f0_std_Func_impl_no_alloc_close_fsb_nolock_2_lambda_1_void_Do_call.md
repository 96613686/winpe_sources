# std::_Func_impl_no_alloc___close_fsb_nolock_::_2_::_lambda_1__void_::_Do_call

- ea: `0x1800ab3f0`
- end: `0x1800ab54c`
- name: `std::_Func_impl_no_alloc___close_fsb_nolock_::_2_::_lambda_1__void_::_Do_call`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x180016c00`
- `0x180016caf`
- `0x180019508`
- `0x180019e4e`
- `0x18001ae80`
- `0x18001af20`
- `0x18001afc0`
- `0x18001b0a0`
- `0x18001b1d0`
- `0x1800a9d4d`
- `0x1800ab3f0`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab4d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab4d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800ab44a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800ab44a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab45b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab45b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall std::_Func_impl_no_alloc___close_fsb_nolock_::_2_::_lambda_1__void_::_Do_call(__int64 a1)
{
  bool v2; // bp
  __int64 v3; // rbx
  DWORD CurrentThreadId; // esi
  __int64 v5; // rcx
  __int64 v7; // rbx
  DWORD LastError; // eax
  _QWORD *system_error; // rbx
  __int128 v10; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v11[88]; // [rsp+30h] [rbp-58h] BYREF

  v2 = 0;
  v3 = *(_QWORD *)(a1 + 8);
  CurrentThreadId = pplx::details::platform::GetCurrentThreadId();
  if ( *(_DWORD *)(v3 + 140) == CurrentThreadId )
  {
    ++*(_DWORD *)(v3 + 136);
  }
  else
  {
    pplx::details::critical_section_impl::lock((LPCRITICAL_SECTION)(v3 + 72));
    *(_DWORD *)(v3 + 140) = CurrentThreadId;
    *(_DWORD *)(v3 + 136) = 1;
  }
  v5 = *(_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(v5 + 144) != -1 )
  {
    CloseThreadpoolIo(*(PTP_IO *)(v5 + 152));
    v2 = CloseHandle(*(HANDLE *)(*(_QWORD *)(a1 + 8) + 144LL));
  }
  operator delete(*(void **)(*(_QWORD *)(a1 + 8) + 32LL));
  if ( (*(_DWORD *)(v3 + 136))-- == 1 )
  {
    *(_DWORD *)(v3 + 140) = -1;
    pplx::details::critical_section_impl::unlock((LPCRITICAL_SECTION)(v3 + 72));
  }
  v7 = *(_QWORD *)(a1 + 8);
  if ( v7 )
  {
    pplx::details::critical_section_impl::~critical_section_impl((LPCRITICAL_SECTION)(v7 + 72));
    operator delete((void *)v7);
  }
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 8LL))(*(_QWORD *)(a1 + 16));
  }
  else
  {
    LastError = GetLastError();
    system_error = (_QWORD *)utility::details::create_system_error(v11, LastError);
    v10 = 0;
    __ExceptionPtrCreate(&v10);
    __ExceptionPtrCopyException(&v10, system_error, &TI4_AVsystem_error_std__);
    *system_error = &std::exception::`vftable';
    o___std_exception_destroy_0(system_error + 1);
    (*(void (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16), &v10);
    __ExceptionPtrDestroy(&v10);
  }
}

```

## disassembly

```asm
0x1800ab3f0  push    rbx
0x1800ab3f2  push    rbp
0x1800ab3f3  push    rsi
0x1800ab3f4  push    rdi
0x1800ab3f5  sub     rsp, 68h
0x1800ab3f9  mov     rdi, rcx
0x1800ab3fc  xor     bpl, bpl
0x1800ab3ff  mov     rbx, [rcx+8]
0x1800ab403  call    ?GetCurrentThreadId@platform@details@pplx@@YAJXZ; pplx::details::platform::GetCurrentThreadId(void)
0x1800ab408  mov     esi, eax
0x1800ab40a  mov     edx, [rbx+8Ch]
0x1800ab410  cmp     edx, eax
0x1800ab412  jnz     short loc_1800AB41C
0x1800ab414  inc     dword ptr [rbx+88h]
0x1800ab41a  jmp     short loc_1800AB435
0x1800ab41c  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800ab420  call    ?lock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::lock(void)
0x1800ab425  mov     [rbx+8Ch], esi
0x1800ab42b  mov     dword ptr [rbx+88h], 1
0x1800ab435  mov     rcx, [rdi+8]
0x1800ab439  cmp     qword ptr [rcx+90h], 0FFFFFFFFFFFFFFFFh
0x1800ab441  jz      short loc_1800AB467
0x1800ab443  mov     rcx, [rcx+98h]; pio
0x1800ab44a  call    cs:__imp_CloseThreadpoolIo
0x1800ab450  mov     rcx, [rdi+8]
0x1800ab454  mov     rcx, [rcx+90h]; hObject
0x1800ab45b  call    cs:__imp_CloseHandle
0x1800ab461  test    eax, eax
0x1800ab463  setnz   bpl
0x1800ab467  mov     rcx, [rdi+8]
0x1800ab46b  mov     edx, 1
0x1800ab470  mov     rcx, [rcx+20h]; Block
0x1800ab474  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab479  nop
0x1800ab47a  sub     dword ptr [rbx+88h], 1
0x1800ab481  jnz     short loc_1800AB497
0x1800ab483  mov     dword ptr [rbx+8Ch], 0FFFFFFFFh
0x1800ab48d  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800ab491  call    ?unlock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::unlock(void)
0x1800ab496  nop
0x1800ab497  mov     rbx, [rdi+8]
0x1800ab49b  test    rbx, rbx
0x1800ab49e  jz      short loc_1800AB4B6
0x1800ab4a0  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800ab4a4  call    ??1critical_section_impl@details@pplx@@QEAA@XZ; pplx::details::critical_section_impl::~critical_section_impl(void)
0x1800ab4a9  mov     edx, 0A0h
0x1800ab4ae  mov     rcx, rbx; Block
0x1800ab4b1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab4b6  test    bpl, bpl
0x1800ab4b9  jz      short loc_1800AB4D3
0x1800ab4bb  mov     rcx, [rdi+10h]
0x1800ab4bf  mov     rax, [rcx]
0x1800ab4c2  mov     rax, [rax+8]
0x1800ab4c6  add     rsp, 68h
0x1800ab4ca  pop     rdi
0x1800ab4cb  pop     rsi
0x1800ab4cc  pop     rbp
0x1800ab4cd  pop     rbx
0x1800ab4ce  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab4d3  call    cs:__imp_GetLastError
0x1800ab4d9  mov     edx, eax
0x1800ab4db  lea     rcx, [rsp+88h+var_58]
0x1800ab4e0  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800ab4e5  mov     rbx, rax
0x1800ab4e8  xorps   xmm0, xmm0
0x1800ab4eb  movdqu  [rsp+88h+var_68], xmm0
0x1800ab4f1  lea     rcx, [rsp+88h+var_68]; void *
0x1800ab4f6  call    ?__ExceptionPtrCreate@@YAXPEAX@Z_0; __ExceptionPtrCreate(void *)
0x1800ab4fb  lea     r8, _TI4?AVsystem_error@std@@; void *
0x1800ab502  mov     rdx, rbx; void *
0x1800ab505  lea     rcx, [rsp+88h+var_68]; void *
0x1800ab50a  call    ?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z_0; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800ab50f  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800ab516  mov     [rbx], rax
0x1800ab519  lea     rcx, [rbx+8]
0x1800ab51d  call    _o___std_exception_destroy_0
0x1800ab522  nop
0x1800ab523  mov     rcx, [rdi+10h]
0x1800ab527  mov     rax, [rcx]
0x1800ab52a  lea     rdx, [rsp+88h+var_68]
0x1800ab52f  mov     rax, [rax+10h]
0x1800ab533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab538  nop
0x1800ab539  lea     rcx, [rsp+88h+var_68]; void *
0x1800ab53e  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z_0; __ExceptionPtrDestroy(void *)
0x1800ab543  add     rsp, 68h
0x1800ab547  pop     rdi
0x1800ab548  pop     rsi
0x1800ab549  pop     rbp
0x1800ab54a  pop     rbx
0x1800ab54b  retn
```
