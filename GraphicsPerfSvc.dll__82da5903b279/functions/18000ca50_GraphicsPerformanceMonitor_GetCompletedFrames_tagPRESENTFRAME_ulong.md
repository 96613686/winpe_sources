# GraphicsPerformanceMonitor::GetCompletedFrames(tagPRESENTFRAME * *,ulong *)

- ea: `0x18000ca50`
- end: `0x18000cc01`
- name: `?GetCompletedFrames@GraphicsPerformanceMonitor@@UEAAJPEAPEAUtagPRESENTFRAME@@PEAK@Z`
- size: `433`
- prototype: `__int64 __fastcall(GraphicsPerformanceMonitor *__hidden this, struct tagPRESENTFRAME **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005c6c`
- `0x18000b734`
- `0x18000c37c`
- `0x18000c8e4`
- `0x18000ca50`
- `0x18000d7d4`
- `0x18000d8ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ca97`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ca97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cb27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cb27`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GraphicsPerformanceMonitor::GetCompletedFrames(
        GraphicsPerformanceMonitor *this,
        struct tagPRESENTFRAME **a2,
        unsigned int *a3)
{
  __int64 v5; // rdi
  unsigned int v6; // ebx
  __int64 v7; // rdx
  LPVOID v8; // rdi
  LPVOID v9; // r8
  unsigned int v10; // r8d
  const char *v11; // r9
  __int64 result; // rax
  __int64 v13; // r9
  _OWORD *v14; // rax
  unsigned int v15; // r9d
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // r9d
  struct tagPRESENTFRAME *v19; // rax
  void **v20; // [rsp+20h] [rbp-A8h] BYREF
  struct tagPRESENTFRAME *v21; // [rsp+28h] [rbp-A0h]
  _BYTE v22[32]; // [rsp+30h] [rbp-98h] BYREF
  unsigned int v23; // [rsp+50h] [rbp-78h]
  _BYTE v24[40]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE v25[48]; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  __int64 v27; // [rsp+D8h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  *a2 = 0;
  *a3 = 0;
  v5 = *((_QWORD *)this + 2);
  EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  try
  {
    v27 = v5 + 8;
    std::deque<PresentEventConsumer::PresentData>::deque<PresentEventConsumer::PresentData>(v24, v5 + 88);
    std::deque<PresentEventConsumer::PresentData>::deque<PresentEventConsumer::PresentData>(v25, v24);
    std::deque<PresentEventConsumer::PresentData>::~deque<PresentEventConsumer::PresentData>(v24);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v27);
    std::deque<PresentEventConsumer::PresentData>::deque<PresentEventConsumer::PresentData>(v22, v25);
    std::deque<PresentEventConsumer::PresentData>::~deque<PresentEventConsumer::PresentData>(v25);
    v6 = v23;
    if ( v23 )
    {
      v20 = &Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable';
      v21 = 0;
      v8 = CoTaskMemAlloc(32LL * v23);
      v9 = 0;
      if ( v8 )
      {
        Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::Close(&v20);
        v9 = v8;
        v21 = (struct tagPRESENTFRAME *)v8;
      }
      if ( !v9 )
      {
        v20 = &Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::Close(&v20);
        std::deque<PresentEventConsumer::PresentData>::~deque<PresentEventConsumer::PresentData>(v22);
        return 2147942414LL;
      }
      v13 = 0;
      do
      {
        v14 = (_OWORD *)std::queue<PresentEventConsumer::PresentData>::front(v22, v7, v9, v13, v20);
        v16 = 32LL * v15;
        *(_OWORD *)(v16 + v17) = *v14;
        *(_OWORD *)(v16 + v17 + 16) = v14[1];
        std::deque<PresentEventConsumer::PresentData>::pop_front(v22);
        v13 = (unsigned int)(v18 + 1);
      }
      while ( (unsigned int)v13 < v6 );
      v19 = v21;
      v21 = 0;
      *a2 = v19;
      *a3 = v6;
      v20 = &Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::Close(&v20);
    }
    std::deque<PresentEventConsumer::PresentData>::~deque<PresentEventConsumer::PresentData>(v22);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v27) = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x90, v10, v11);
    return (unsigned int)v27;
  }
  return result;
}

```

## disassembly

```asm
0x18000ca50  mov     [rsp+arg_0], rbx
0x18000ca55  mov     [rsp+arg_10], rsi
0x18000ca5a  push    rdi
0x18000ca5b  push    r12
0x18000ca5d  push    r14
0x18000ca5f  sub     rsp, 0B0h
0x18000ca66  mov     rsi, r8
0x18000ca69  mov     r14, rdx
0x18000ca6c  test    rdx, rdx
0x18000ca6f  jz      loc_18000CBD9
0x18000ca75  test    r8, r8
0x18000ca78  jz      loc_18000CBD9
0x18000ca7e  mov     qword ptr [rdx], 0
0x18000ca85  mov     dword ptr [r8], 0
0x18000ca8c  mov     rdi, [rcx+10h]
0x18000ca90  lea     rbx, [rdi+8]
0x18000ca94  mov     rcx, rbx; lpCriticalSection
0x18000ca97  call    cs:__imp_EnterCriticalSection
0x18000ca9d  mov     [rsp+0C8h+arg_8], rbx
0x18000caa5  lea     rdx, [rdi+58h]
0x18000caa9  lea     rcx, [rsp+0C8h+var_70]
0x18000caae  call    ??0?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAA@$$QEAV01@@Z; std::deque<PresentEventConsumer::PresentData>::deque<PresentEventConsumer::PresentData>(std::deque<PresentEventConsumer::PresentData> &&)
0x18000cab3  nop
0x18000cab4  lea     rdx, [rsp+0C8h+var_70]
0x18000cab9  lea     rcx, [rsp+0C8h+var_48]
0x18000cac1  call    ??0?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAA@$$QEAV01@@Z; std::deque<PresentEventConsumer::PresentData>::deque<PresentEventConsumer::PresentData>(std::deque<PresentEventConsumer::PresentData> &&)
0x18000cac6  nop
0x18000cac7  lea     rcx, [rsp+0C8h+var_70]
0x18000cacc  call    ??1?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAA@XZ; std::deque<PresentEventConsumer::PresentData>::~deque<PresentEventConsumer::PresentData>(void)
0x18000cad1  nop
0x18000cad2  lea     rcx, [rsp+0C8h+arg_8]
0x18000cada  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000cadf  nop
0x18000cae0  lea     rdx, [rsp+0C8h+var_48]
0x18000cae8  lea     rcx, [rsp+0C8h+var_98]
0x18000caed  call    ??0?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAA@$$QEAV01@@Z; std::deque<PresentEventConsumer::PresentData>::deque<PresentEventConsumer::PresentData>(std::deque<PresentEventConsumer::PresentData> &&)
0x18000caf2  nop
0x18000caf3  lea     rcx, [rsp+0C8h+var_48]
0x18000cafb  call    ??1?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAA@XZ; std::deque<PresentEventConsumer::PresentData>::~deque<PresentEventConsumer::PresentData>(void)
0x18000cb00  mov     ebx, [rsp+0C8h+var_78]
0x18000cb04  test    ebx, ebx
0x18000cb06  jz      loc_18000CBCB
0x18000cb0c  lea     r12, ??_7?$HandleT@UCoTaskMemBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::`vftable'
0x18000cb13  mov     [rsp+0C8h+var_A8], r12
0x18000cb18  mov     [rsp+0C8h+var_A0], 0
0x18000cb21  mov     ecx, ebx
0x18000cb23  shl     rcx, 5; cb
0x18000cb27  call    cs:__imp_CoTaskMemAlloc
0x18000cb2d  mov     rdi, rax
0x18000cb30  mov     r8, [rsp+0C8h+var_A0]
0x18000cb35  cmp     rax, r8
0x18000cb38  jz      short loc_18000CB4C
0x18000cb3a  lea     rcx, [rsp+0C8h+var_A8]
0x18000cb3f  call    ?Close@?$HandleT@UCoTaskMemBufferTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::Close(void)
0x18000cb44  mov     r8, rdi
0x18000cb47  mov     [rsp+0C8h+var_A0], rdi
0x18000cb4c  test    r8, r8
0x18000cb4f  jnz     short loc_18000CB71
0x18000cb51  mov     [rsp+0C8h+var_A8], r12
0x18000cb56  lea     rcx, [rsp+0C8h+var_A8]
0x18000cb5b  call    ?Close@?$HandleT@UCoTaskMemBufferTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::Close(void)
0x18000cb60  lea     rcx, [rsp+0C8h+var_98]
0x18000cb65  call    ??1?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAA@XZ; std::deque<PresentEventConsumer::PresentData>::~deque<PresentEventConsumer::PresentData>(void)
0x18000cb6a  mov     eax, 8007000Eh
0x18000cb6f  jmp     short loc_18000CBE7
0x18000cb71  xor     r9d, r9d
0x18000cb74  lea     rcx, [rsp+0C8h+var_98]
0x18000cb79  call    ?front@?$queue@UPresentData@PresentEventConsumer@@V?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@@std@@QEAAAEAUPresentData@PresentEventConsumer@@XZ; std::queue<PresentEventConsumer::PresentData>::front(void)
0x18000cb7e  mov     ecx, r9d
0x18000cb81  shl     rcx, 5
0x18000cb85  movups  xmm0, xmmword ptr [rax]
0x18000cb88  movups  xmmword ptr [rcx+r8], xmm0
0x18000cb8d  movups  xmm1, xmmword ptr [rax+10h]
0x18000cb91  movups  xmmword ptr [rcx+r8+10h], xmm1
0x18000cb97  lea     rcx, [rsp+0C8h+var_98]
0x18000cb9c  call    ?pop_front@?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAAXXZ; std::deque<PresentEventConsumer::PresentData>::pop_front(void)
0x18000cba1  inc     r9d
0x18000cba4  cmp     r9d, ebx
0x18000cba7  jb      short loc_18000CB74
0x18000cba9  mov     rax, [rsp+0C8h+var_A0]
0x18000cbae  mov     [rsp+0C8h+var_A0], 0
0x18000cbb7  mov     [r14], rax
0x18000cbba  mov     [rsi], ebx
0x18000cbbc  mov     [rsp+0C8h+var_A8], r12
0x18000cbc1  lea     rcx, [rsp+0C8h+var_A8]
0x18000cbc6  call    ?Close@?$HandleT@UCoTaskMemBufferTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::Close(void)
0x18000cbcb  lea     rcx, [rsp+0C8h+var_98]
0x18000cbd0  call    ??1?$deque@UPresentData@PresentEventConsumer@@V?$allocator@UPresentData@PresentEventConsumer@@@std@@@std@@QEAA@XZ; std::deque<PresentEventConsumer::PresentData>::~deque<PresentEventConsumer::PresentData>(void)
0x18000cbd5  xor     eax, eax
0x18000cbd7  jmp     short loc_18000CBE7
0x18000cbd9  mov     eax, 80004003h
0x18000cbde  jmp     short loc_18000CBE7
0x18000cbe0  mov     eax, dword ptr [rsp+0C8h+arg_8]
0x18000cbe7  lea     r11, [rsp+0C8h+var_18]
0x18000cbef  mov     rbx, [r11+20h]
0x18000cbf3  mov     rsi, [r11+30h]
0x18000cbf7  mov     rsp, r11
0x18000cbfa  pop     r14
0x18000cbfc  pop     r12
0x18000cbfe  pop     rdi
0x18000cbff  retn
```
