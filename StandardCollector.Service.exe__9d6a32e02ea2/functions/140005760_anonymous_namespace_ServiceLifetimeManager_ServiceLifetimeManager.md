# _anonymous_namespace_::ServiceLifetimeManager::ServiceLifetimeManager

- ea: `0x140005760`
- end: `0x140005a0d`
- name: `_anonymous_namespace_::ServiceLifetimeManager::ServiceLifetimeManager`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400010e0`

## callees

- `0x140004b0c`
- `0x140005760`
- `0x14000a42c`
- `0x14000f728`
- `0x140013834`
- `0x140014c70`

## import_xrefs

- `KERNEL32!InitializeSRWLock` at `0x1400057ed`
- `KERNEL32!InitializeSRWLock` at `0x1400057ed`
- `KERNEL32!InitializeCriticalSection` at `0x140005953`
- `KERNEL32!InitializeCriticalSection` at `0x140005953`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 *anonymous_namespace_::ServiceLifetimeManager::ServiceLifetimeManager()
{
  _QWORD *v0; // rax
  _QWORD *v1; // rax
  __int64 v2; // rdx
  const struct DiagHubCommon::Logger *Logger; // rax
  __int64 v4; // r8
  _QWORD *v5; // rdx
  _QWORD v7[7]; // [rsp+40h] [rbp+7h] BYREF
  _QWORD *v8; // [rsp+78h] [rbp+3Fh]
  void *v9; // [rsp+80h] [rbp+47h]

  dword_140024840 = 1;
  qword_140024838 = (__int64)&CModuleRefCount::`vftable';
  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&CModuleRefCount::s_ulcModuleRef) >= 0x7FFFFFFF )
    __fastfail(0xEu);
  qword_140024830 = (__int64)&`anonymous namespace'::ServiceLifetimeManager::`vftable';
  qword_140024838 = (__int64)`anonymous namespace'::ServiceLifetimeManager::`vftable';
  qword_140024848 = 0;
  byte_140024850 = 0;
  InitializeSRWLock(&stru_140024858);
  dword_140024860 = 0;
  qword_140024868 = 0;
  qword_140024870 = 0;
  v0 = operator new(0x20u);
  *v0 = v0;
  v0[1] = v0;
  qword_140024868 = (__int64)v0;
  qword_140024878 = 0;
  xmmword_140024880 = 0;
  qword_140024890 = 7;
  qword_140024898 = 8;
  dword_140024860 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(
    (__int64)&qword_140024878,
    0x10u,
    (unsigned __int64)v0);
  v7[0] = &std::_Func_impl_no_alloc<_lambda_9cd31561f792f2a14f6f5f137ab04a18_,void,unsigned int>::`vftable';
  v7[1] = &qword_140024830;
  v8 = v7;
  v9 = &dword_1400248A0;
  dword_1400248A0 = 0;
  qword_1400248A8 = 0;
  qword_1400248B0 = 0;
  v1 = operator new(0x40u);
  *v1 = v1;
  v1[1] = v1;
  qword_1400248A8 = (__int64)v1;
  qword_1400248B8 = 0;
  xmmword_1400248C0 = 0;
  qword_1400248D0 = 7;
  qword_1400248D8 = 8;
  dword_1400248A0 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(
    (__int64)&qword_1400248B8,
    0x10u,
    (unsigned __int64)v1);
  *(_OWORD *)&stru_1400248E0.DebugInfo = 0;
  *(_OWORD *)&stru_1400248E0.OwningThread = 0;
  stru_1400248E0.SpinCount = 0;
  InitializeCriticalSection(&stru_1400248E0);
  qword_140024940 = 0;
  if ( v8 )
  {
    if ( v8 == v7 )
    {
      qword_140024940 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v8 + 8LL))(v8, qword_140024908);
      if ( !v8 )
        goto LABEL_9;
      LOBYTE(v2) = v8 != v7;
      (*(void (__fastcall **)(_QWORD *, __int64))(*v8 + 32LL))(v8, v2);
    }
    else
    {
      qword_140024940 = (__int64)v8;
    }
    v8 = 0;
  }
LABEL_9:
  Logger = DiagHubCommon::Logger::GetLogger();
  DiagHubCommon::Logger::Logger((DiagHubCommon::Logger *)qword_140024948, Logger, v4);
  if ( v8 )
  {
    v5 = v7;
    LOBYTE(v5) = v8 != v7;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v8 + 32LL))(v8, v5);
  }
  return &qword_140024830;
}

```

## disassembly

```asm
0x140005760  mov     [rsp-8+arg_0], r15
0x140005765  push    rbp
0x140005766  lea     rbp, [rsp-57h]
0x14000576b  sub     rsp, 90h
0x140005772  mov     rax, [rbp+57h+var_70]
0x140005776  mov     [rbp+57h+var_70], rax
0x14000577a  lea     r15, qword_140024830
0x140005781  mov     [rbp+57h+var_70], r15
0x140005785  mov     ecx, 1
0x14000578a  mov     cs:dword_140024840, ecx
0x140005790  lea     rax, ??_7CModuleRefCount@@6B@; const CModuleRefCount::`vftable'
0x140005797  mov     cs:qword_140024838, rax
0x14000579e  mov     eax, ecx
0x1400057a0  lock xadd cs:?s_ulcModuleRef@CModuleRefCount@@0KA, eax; ulong CModuleRefCount::s_ulcModuleRef
0x1400057a8  add     eax, ecx
0x1400057aa  cmp     eax, 7FFFFFFFh
0x1400057af  jb      short loc_1400057B8
0x1400057b1  mov     ecx, 0Eh
0x1400057b6  int     29h; Win8: RtlFailFast(ecx)
0x1400057b8  lea     rax, ??_7ServiceLifetimeManager@?A0x9847eaf5@@6B@; const `anonymous namespace'::ServiceLifetimeManager::`vftable'
0x1400057bf  mov     cs:qword_140024830, rax
0x1400057c6  lea     rax, ??_7ServiceLifetimeManager@?A0x9847eaf5@@6B@_0; const `anonymous namespace'::ServiceLifetimeManager::`vftable'
0x1400057cd  mov     cs:qword_140024838, rax
0x1400057d4  mov     cs:qword_140024848, 0
0x1400057df  mov     cs:byte_140024850, 0
0x1400057e6  lea     rcx, stru_140024858; SRWLock
0x1400057ed  call    cs:__imp_InitializeSRWLock
0x1400057f3  lea     rax, dword_140024860
0x1400057fa  mov     [rbp+57h+var_60], rax
0x1400057fe  mov     cs:dword_140024860, 0
0x140005808  mov     cs:qword_140024868, 0
0x140005813  mov     cs:qword_140024870, 0
0x14000581e  mov     ecx, 20h ; ' '; Size
0x140005823  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005828  mov     [rax], rax
0x14000582b  mov     [rax+8], rax
0x14000582f  mov     cs:qword_140024868, rax
0x140005836  mov     cs:qword_140024878, 0
0x140005841  xorps   xmm0, xmm0
0x140005844  movdqa  cs:xmmword_140024880, xmm0
0x14000584c  mov     cs:qword_140024890, 7
0x140005857  mov     cs:qword_140024898, 8
0x140005862  mov     cs:dword_140024860, 3F800000h
0x14000586c  mov     r8, rax
0x14000586f  mov     edx, 10h
0x140005874  lea     rcx, qword_140024878
0x14000587b  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>)
0x140005880  nop
0x140005881  lea     rcx, dword_1400248A0
0x140005888  mov     [rbp+57h+var_60], rcx
0x14000588c  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_9cd31561f792f2a14f6f5f137ab04a18_@@XI@std@@6B@; const std::_Func_impl_no_alloc<_lambda_9cd31561f792f2a14f6f5f137ab04a18_,void,uint>::`vftable'
0x140005893  mov     [rbp+57h+var_50], rax
0x140005897  mov     [rbp+57h+var_48], r15
0x14000589b  lea     rax, [rbp+57h+var_50]
0x14000589f  mov     [rbp+57h+var_18], rax
0x1400058a3  lea     rax, [rbp+57h+var_50]
0x1400058a7  mov     [rbp+57h+var_58], rax
0x1400058ab  mov     [rbp+57h+var_10], rcx
0x1400058af  mov     cs:dword_1400248A0, 0
0x1400058b9  mov     cs:qword_1400248A8, 0
0x1400058c4  mov     cs:qword_1400248B0, 0
0x1400058cf  mov     ecx, 40h ; '@'; Size
0x1400058d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400058d9  mov     [rax], rax
0x1400058dc  mov     [rax+8], rax
0x1400058e0  mov     cs:qword_1400248A8, rax
0x1400058e7  mov     cs:qword_1400248B8, 0
0x1400058f2  xorps   xmm0, xmm0
0x1400058f5  movdqa  cs:xmmword_1400248C0, xmm0
0x1400058fd  mov     cs:qword_1400248D0, 7
0x140005908  mov     cs:qword_1400248D8, 8
0x140005913  mov     cs:dword_1400248A0, 3F800000h
0x14000591d  mov     r8, rax
0x140005920  mov     edx, 10h
0x140005925  lea     rcx, qword_1400248B8
0x14000592c  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>)
0x140005931  nop
0x140005932  xorps   xmm0, xmm0
0x140005935  xor     eax, eax
0x140005937  movups  xmmword ptr cs:stru_1400248E0.DebugInfo, xmm0
0x14000593e  movups  xmmword ptr cs:stru_1400248E0.OwningThread, xmm0
0x140005945  mov     cs:stru_1400248E0.SpinCount, rax
0x14000594c  lea     rcx, stru_1400248E0; lpCriticalSection
0x140005953  call    cs:__imp_InitializeCriticalSection
0x140005959  nop
0x14000595a  mov     cs:qword_140024940, 0
0x140005965  mov     rcx, [rbp+57h+var_18]
0x140005969  test    rcx, rcx
0x14000596c  jz      short loc_1400059C3
0x14000596e  lea     rax, [rbp+57h+var_50]
0x140005972  cmp     rcx, rax
0x140005975  jnz     short loc_1400059B4
0x140005977  mov     rax, [rcx]
0x14000597a  lea     rdx, qword_140024908
0x140005981  mov     rax, [rax+8]
0x140005985  call    cs:__guard_dispatch_icall_fptr
0x14000598b  mov     cs:qword_140024940, rax
0x140005992  mov     rcx, [rbp+57h+var_18]
0x140005996  test    rcx, rcx
0x140005999  jz      short loc_1400059C3
0x14000599b  lea     rax, [rbp+57h+var_50]
0x14000599f  cmp     rcx, rax
0x1400059a2  setnz   dl
0x1400059a5  mov     rax, [rcx]
0x1400059a8  mov     rax, [rax+20h]
0x1400059ac  call    cs:__guard_dispatch_icall_fptr
0x1400059b2  jmp     short loc_1400059BB
0x1400059b4  mov     cs:qword_140024940, rcx
0x1400059bb  mov     [rbp+57h+var_18], 0
0x1400059c3  call    ?GetLogger@Logger@DiagHubCommon@@SAAEAV12@XZ; DiagHubCommon::Logger::GetLogger(void)
0x1400059c8  mov     rdx, rax; struct DiagHubCommon::Logger *
0x1400059cb  lea     rcx, qword_140024948; this
0x1400059d2  call    ??0Logger@DiagHubCommon@@QEAA@AEBV01@@Z; DiagHubCommon::Logger::Logger(DiagHubCommon::Logger const &)
0x1400059d7  nop
0x1400059d8  mov     rcx, [rbp+57h+var_18]
0x1400059dc  test    rcx, rcx
0x1400059df  jz      short loc_1400059F9
0x1400059e1  lea     rdx, [rbp+57h+var_50]
0x1400059e5  cmp     rcx, rdx
0x1400059e8  setnz   dl
0x1400059eb  mov     r8, [rcx]
0x1400059ee  mov     rax, [r8+20h]
0x1400059f2  call    cs:__guard_dispatch_icall_fptr
0x1400059f8  nop
0x1400059f9  mov     rax, r15
0x1400059fc  mov     r15, [rsp+90h+arg_0]
0x140005a04  add     rsp, 90h
0x140005a0b  pop     rbp
0x140005a0c  retn
```
