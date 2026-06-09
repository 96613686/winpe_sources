# Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___

- ea: `0x140014234`
- end: `0x140014459`
- name: `Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x140014108`

## callees

- `0x1400017a0`
- `0x14000342d`
- `0x140012fdc`
- `0x140014234`
- `0x14001a340`
- `0x140023bd8`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140014384`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140014384`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x140014256`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x140014256`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___(
        _QWORD *a1)
{
  _QWORD *v2; // r14
  char *v3; // rax
  char *v4; // rdi
  __int64 v5; // rcx

  v2 = a1 + 1;
  Platform::Object::Object(a1 + 7);
  v2[3] = &off_14004A590;
  v2[4] = &off_14004A530;
  v2[5] = &off_14004A4B0;
  v2[6] = &off_14004A480;
  v2[7] = 0;
  v2[8] = 0;
  *((_DWORD *)v2 + 18) = -1;
  *((_DWORD *)v2 + 19) = 0;
  *((_DWORD *)v2 + 21) = 0;
  *((_DWORD *)v2 + 22) = 0;
  *((_DWORD *)v2 + 20) = _InterlockedIncrement(&Concurrency::details::s_asyncId);
  *v2 = &off_14004A450;
  v2[1] = &off_14004A420;
  v2[2] = &off_14004A3F0;
  v2[3] = &off_14004A380;
  v2[4] = &off_14004A320;
  v2[5] = &off_14004A2A0;
  v2[6] = &off_14004A270;
  v2[14] = 0;
  v2[15] = 0;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::_Resetp<Concurrency::details::_Task_impl<unsigned char>>(v2 + 14);
  v3 = (char *)operator new(0x70u);
  v4 = v3;
  if ( v3 )
  {
    memset_0(v3, 0, 0x70u);
    *(_QWORD *)v4 = &pplx::details::_RefCounterBase::`vftable';
    _InterlockedExchange((volatile __int32 *)v4 + 2, 1);
    *(_QWORD *)v4 = &pplx::details::_CancellationTokenState::`vftable';
    _InterlockedExchange((volatile __int32 *)v4 + 4, 0);
    pplx::details::event_impl::event_impl((pplx::details::event_impl *)(v4 + 24));
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v4 + 32), 0, 0);
    *((_QWORD *)v4 + 12) = 0;
    *((_QWORD *)v4 + 13) = 0;
    *((_QWORD *)v4 + 12) = std::_List_alloc<0,std::_List_base_types<pplx::details::_CancellationTokenRegistration *>>::_Buynode0(
                             v5,
                             0,
                             0);
  }
  else
  {
    v4 = 0;
  }
  v2[16] = v4;
  *a1 = off_14004A240;
  *v2 = off_14004A210;
  a1[2] = off_14004A1E0;
  a1[3] = off_14004A1B0;
  a1[4] = off_14004A140;
  a1[5] = off_14004A0E0;
  a1[6] = off_14004A060;
  a1[7] = off_14004A030;
  a1[19] = off_14004A008;
  a1[20] = off_140049FD8;
  a1[22] = -1;
  if ( __abi_module )
    (**(void (__fastcall ***)(struct __abi_Module *))__abi_module)(__abi_module);
  return a1;
}

```

## disassembly

```asm
0x140014234  mov     [rsp+arg_18], rbx
0x140014239  mov     [rsp+arg_0], rcx
0x14001423e  push    rsi
0x14001423f  push    rdi
0x140014240  push    r14
0x140014242  sub     rsp, 20h
0x140014246  mov     rsi, rcx
0x140014249  lea     r14, [rcx+8]
0x14001424d  mov     [rsp+38h+arg_0], r14
0x140014252  lea     rcx, [r14+30h]
0x140014256  call    cs:__imp_??0Object@Platform@@QE$AAA@XZ; Platform::Object::Object(void)
0x14001425c  lea     rax, off_14004A590
0x140014263  mov     [r14+18h], rax
0x140014267  lea     rax, off_14004A530
0x14001426e  mov     [r14+20h], rax
0x140014272  lea     rax, off_14004A4B0
0x140014279  mov     [r14+28h], rax
0x14001427d  lea     rax, off_14004A480
0x140014284  mov     [r14+30h], rax
0x140014288  mov     qword ptr [r14+38h], 0
0x140014290  mov     qword ptr [r14+40h], 0
0x140014298  mov     dword ptr [r14+48h], 0FFFFFFFFh
0x1400142a0  mov     dword ptr [r14+4Ch], 0
0x1400142a8  mov     dword ptr [r14+54h], 0
0x1400142b0  mov     dword ptr [r14+58h], 0
0x1400142b8  mov     ebx, 1
0x1400142bd  mov     eax, ebx
0x1400142bf  lock xadd cs:?s_asyncId@details@Concurrency@@3JC, eax; long volatile Concurrency::details::s_asyncId
0x1400142c7  add     eax, ebx
0x1400142c9  mov     [r14+50h], eax
0x1400142cd  lea     rax, off_14004A450
0x1400142d4  mov     [r14], rax
0x1400142d7  lea     rax, off_14004A420
0x1400142de  mov     [r14+8], rax
0x1400142e2  lea     rax, off_14004A3F0
0x1400142e9  mov     [r14+10h], rax
0x1400142ed  lea     rax, off_14004A380
0x1400142f4  mov     [r14+18h], rax
0x1400142f8  lea     rax, off_14004A320
0x1400142ff  mov     [r14+20h], rax
0x140014303  lea     rax, off_14004A2A0
0x14001430a  mov     [r14+28h], rax
0x14001430e  lea     rax, off_14004A270
0x140014315  mov     [r14+30h], rax
0x140014319  lea     rcx, [r14+70h]
0x14001431d  mov     qword ptr [rcx], 0
0x140014324  mov     qword ptr [rcx+8], 0
0x14001432c  call    ??$_Resetp@U?$_Task_impl@E@details@Concurrency@@@?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@AEAAXPEAU?$_Task_impl@E@details@Concurrency@@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::_Resetp<Concurrency::details::_Task_impl<uchar>>(Concurrency::details::_Task_impl<uchar> *)
0x140014331  nop
0x140014332  lea     ecx, [rbx+6Fh]; Size
0x140014335  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001433a  mov     rdi, rax
0x14001433d  mov     [rsp+38h+arg_8], rax
0x140014342  test    rax, rax
0x140014345  jz      short loc_1400143AB
0x140014347  xor     edx, edx; Val
0x140014349  lea     r8d, [rbx+6Fh]; Size
0x14001434d  mov     rcx, rax; void *
0x140014350  call    memset_0
0x140014355  lea     rax, ??_7_RefCounterBase@details@pplx@@6B@; const pplx::details::_RefCounterBase::`vftable'
0x14001435c  mov     [rdi], rax
0x14001435f  xchg    ebx, [rdi+8]
0x140014362  lea     rax, ??_7_CancellationTokenState@details@pplx@@6B@; const pplx::details::_CancellationTokenState::`vftable'
0x140014369  mov     [rdi], rax
0x14001436c  xor     eax, eax
0x14001436e  xchg    eax, [rdi+10h]
0x140014371  lea     rcx, [rdi+18h]; this
0x140014375  call    ??0event_impl@details@pplx@@QEAA@XZ; pplx::details::event_impl::event_impl(void)
0x14001437a  nop
0x14001437b  lea     rcx, [rdi+20h]; lpCriticalSection
0x14001437f  xor     r8d, r8d; Flags
0x140014382  xor     edx, edx; dwSpinCount
0x140014384  call    cs:__imp_InitializeCriticalSectionEx
0x14001438a  nop
0x14001438b  mov     qword ptr [rdi+60h], 0
0x140014393  mov     qword ptr [rdi+68h], 0
0x14001439b  xor     r8d, r8d
0x14001439e  xor     edx, edx
0x1400143a0  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAV_CancellationTokenRegistration@details@pplx@@V?$allocator@PEAV_CancellationTokenRegistration@details@pplx@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAV_CancellationTokenRegistration@details@pplx@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<pplx::details::_CancellationTokenRegistration *>>::_Buynode0(std::_List_node<pplx::details::_CancellationTokenRegistration *,void *> *,std::_List_node<pplx::details::_CancellationTokenRegistration *,void *> *)
0x1400143a5  mov     [rdi+60h], rax
0x1400143a9  jmp     short loc_1400143AD
0x1400143ab  xor     edi, edi
0x1400143ad  mov     [r14+80h], rdi
0x1400143b4  lea     rax, off_14004A240
0x1400143bb  mov     [rsi], rax
0x1400143be  lea     rax, off_14004A210
0x1400143c5  mov     [r14], rax
0x1400143c8  lea     rax, off_14004A1E0
0x1400143cf  mov     [rsi+10h], rax
0x1400143d3  lea     rax, off_14004A1B0
0x1400143da  mov     [rsi+18h], rax
0x1400143de  lea     rax, off_14004A140
0x1400143e5  mov     [rsi+20h], rax
0x1400143e9  lea     rax, off_14004A0E0
0x1400143f0  mov     [rsi+28h], rax
0x1400143f4  lea     rax, off_14004A060
0x1400143fb  mov     [rsi+30h], rax
0x1400143ff  lea     rax, off_14004A030
0x140014406  mov     [rsi+38h], rax
0x14001440a  lea     rax, off_14004A008
0x140014411  mov     [rsi+98h], rax
0x140014418  lea     rax, off_140049FD8
0x14001441f  mov     [rsi+0A0h], rax
0x140014426  mov     qword ptr [rsi+0B0h], 0FFFFFFFFFFFFFFFFh
0x140014431  mov     rcx, cs:?__abi_module@@3PEAU__abi_Module@@EA; __abi_Module * __abi_module
0x140014438  test    rcx, rcx
0x14001443b  jz      short loc_140014448
0x14001443d  mov     rax, [rcx]
0x140014440  mov     rax, [rax]
0x140014443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014448  mov     rax, rsi
0x14001444b  mov     rbx, [rsp+38h+arg_18]
0x140014450  add     rsp, 20h
0x140014454  pop     r14
0x140014456  pop     rdi
0x140014457  pop     rsi
0x140014458  retn
```
