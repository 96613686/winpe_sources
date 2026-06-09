# TaskSchedulerSignalFactory::ConstructSignal(__int64,TimeSignal::Spec const &,std::vector<_bstr_t,std::allocator<_bstr_t>> const &)

- ea: `0x18002a01c`
- end: `0x18002a241`
- name: `?ConstructSignal@TaskSchedulerSignalFactory@@AEAA?AV?$unique_ptr@VTaskSchedulerSignal@@U?$default_delete@VTaskSchedulerSignal@@@std@@@std@@_JAEBUSpec@TimeSignal@@AEBV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@3@@Z`
- size: `549`
- prototype: `RTL_SRWLOCK **__fastcall(RTL_SRWLOCK *, RTL_SRWLOCK **, __int64, _OWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002a584`
- `0x18002a978`

## callees

- `0x18000459c`
- `0x180005140`
- `0x18000b5b0`
- `0x180011ea8`
- `0x180028c68`
- `0x1800291d0`
- `0x180029568`
- `0x18002a01c`
- `0x18002b3bc`
- `0x18002d62c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a1bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a1bb`

## pseudocode

```c
RTL_SRWLOCK **__fastcall TaskSchedulerSignalFactory::ConstructSignal(
        RTL_SRWLOCK *a1,
        RTL_SRWLOCK **a2,
        __int64 a3,
        _OWORD *a4,
        _QWORD *a5)
{
  RTL_SRWLOCK *v8; // r14
  RTL_SRWLOCK *v9; // rbx
  __int64 v10; // rcx
  _OWORD *v11; // rax
  __int64 v12; // rcx
  _OWORD *v13; // rax
  _OWORD *v14; // rcx
  __int64 v15; // rdx
  _QWORD *Ptr; // rcx
  __int64 *v17; // rcx
  __int64 v18; // rbp
  __int64 i; // rdi
  RTL_SRWLOCK *v20; // rbx
  __int64 v21; // rax
  RTL_SRWLOCK *v22; // rbx
  unsigned int v23; // eax
  _BYTE v25[16]; // [rsp+28h] [rbp-150h] BYREF
  _BYTE v26[296]; // [rsp+38h] [rbp-140h] BYREF
  RTL_SRWLOCK *v27; // [rsp+180h] [rbp+8h] BYREF
  RTL_SRWLOCK **v28; // [rsp+188h] [rbp+10h]

  v28 = a2;
  v27 = a1;
  v8 = (RTL_SRWLOCK *)operator new(0x38u);
  v27 = v8;
  GenericPlugin::DefaultSignal::DefaultSignal((GenericPlugin::DefaultSignal *)v8, a3);
  v8->Ptr = &TaskSchedulerSignal::`vftable';
  v9 = (RTL_SRWLOCK *)operator new(0x138u);
  v27 = v9;
  std::vector<_bstr_t>::vector<_bstr_t>(v9);
  *(_DWORD *)(v10 + 24) = 0;
  memset_0((void *)(v10 + 28), 0, 0x118u);
  v8[6].Ptr = v9;
  *a2 = v8;
  v11 = v26;
  v12 = 2;
  do
  {
    *v11 = *a4;
    v11[1] = a4[1];
    v11[2] = a4[2];
    v11[3] = a4[3];
    v11[4] = a4[4];
    v11[5] = a4[5];
    v11[6] = a4[6];
    v11[7] = a4[7];
    v11 += 8;
    a4 += 8;
    --v12;
  }
  while ( v12 );
  *v11 = *a4;
  *(_OWORD *)((char *)v11 + 12) = *(_OWORD *)((char *)a4 + 12);
  v13 = (char *)v8[6].Ptr + 24;
  v14 = v26;
  v15 = 2;
  do
  {
    *v13 = *v14;
    v13[1] = v14[1];
    v13[2] = v14[2];
    v13[3] = v14[3];
    v13[4] = v14[4];
    v13[5] = v14[5];
    v13[6] = v14[6];
    v13[7] = v14[7];
    v13 += 8;
    v14 += 8;
    --v15;
  }
  while ( v15 );
  *v13 = *v14;
  *(_OWORD *)((char *)v13 + 12) = *(_OWORD *)((char *)v14 + 12);
  Ptr = (*a2)[6].Ptr;
  if ( Ptr != a5 )
    std::vector<_bstr_t>::_Assign_counted_range<_bstr_t *>(Ptr, *a5, (__int64)(a5[1] - *a5) >> 3);
  AcquireSRWLockExclusive(&stru_18005FCC8);
  v27 = &stru_18005FCC8;
  v17 = (__int64 *)(*a2)[6].Ptr;
  v18 = v17[1];
  for ( i = *v17; i != v18; i += 8 )
  {
    v20 = *a2;
    v21 = std::map<_bstr_t,TaskSchedulerSignal *>::_Try_emplace<_bstr_t const &,>(v17, v25, i);
    v17 = *(__int64 **)v21;
    *(_QWORD *)(*(_QWORD *)v21 + 40LL) = v20;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
  v22 = *a2;
  v23 = EvaluateTimeSpec((char *)(*a2)[6].Ptr + 24, 2);
  GenericPlugin::DefaultSignal::SetState(v22, v23);
  return a2;
}

```

## disassembly

```asm
0x18002a01c  mov     rax, rsp
0x18002a01f  mov     [rax+18h], rbx
0x18002a023  mov     [rax+20h], rbp
0x18002a027  mov     [rax+10h], rdx
0x18002a02b  mov     [rax+8], rcx
0x18002a02f  push    rsi
0x18002a030  push    rdi
0x18002a031  push    r14
0x18002a033  sub     rsp, 160h
0x18002a03a  mov     rdi, r9
0x18002a03d  mov     rbx, r8
0x18002a040  mov     rsi, rdx
0x18002a043  mov     [rsp+178h+var_158], 0
0x18002a04b  mov     ecx, 38h ; '8'; Size
0x18002a050  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a055  mov     r14, rax
0x18002a058  mov     [rsp+178h+arg_0], rax
0x18002a060  mov     rdx, rbx; __int64
0x18002a063  mov     rcx, rax; this
0x18002a066  call    ??0DefaultSignal@GenericPlugin@@QEAA@_J@Z; GenericPlugin::DefaultSignal::DefaultSignal(__int64)
0x18002a06b  nop
0x18002a06c  lea     rax, ??_7TaskSchedulerSignal@@6B@; const TaskSchedulerSignal::`vftable'
0x18002a073  mov     [r14], rax
0x18002a076  mov     ecx, 138h; Size
0x18002a07b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a080  mov     rbx, rax
0x18002a083  mov     [rsp+178h+arg_0], rax
0x18002a08b  mov     rcx, rax
0x18002a08e  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x18002a093  mov     dword ptr [rcx+18h], 0
0x18002a09a  lea     rcx, [rcx+1Ch]; void *
0x18002a09e  xor     edx, edx; Val
0x18002a0a0  mov     r8d, 118h; Size
0x18002a0a6  call    memset_0
0x18002a0ab  mov     [r14+30h], rbx
0x18002a0af  mov     [rsi], r14
0x18002a0b2  mov     [rsp+178h+var_158], 1
0x18002a0ba  lea     rax, [rsp+178h+var_140]
0x18002a0bf  mov     ecx, 2
0x18002a0c4  lea     r8d, [rcx+7Eh]
0x18002a0c8  movups  xmm0, xmmword ptr [rdi]
0x18002a0cb  movups  xmmword ptr [rax], xmm0
0x18002a0ce  movups  xmm1, xmmword ptr [rdi+10h]
0x18002a0d2  movups  xmmword ptr [rax+10h], xmm1
0x18002a0d6  movups  xmm0, xmmword ptr [rdi+20h]
0x18002a0da  movups  xmmword ptr [rax+20h], xmm0
0x18002a0de  movups  xmm1, xmmword ptr [rdi+30h]
0x18002a0e2  movups  xmmword ptr [rax+30h], xmm1
0x18002a0e6  movups  xmm0, xmmword ptr [rdi+40h]
0x18002a0ea  movups  xmmword ptr [rax+40h], xmm0
0x18002a0ee  movups  xmm1, xmmword ptr [rdi+50h]
0x18002a0f2  movups  xmmword ptr [rax+50h], xmm1
0x18002a0f6  movups  xmm0, xmmword ptr [rdi+60h]
0x18002a0fa  movups  xmmword ptr [rax+60h], xmm0
0x18002a0fe  movups  xmm1, xmmword ptr [rdi+70h]
0x18002a102  movups  xmmword ptr [rax+70h], xmm1
0x18002a106  add     rax, r8
0x18002a109  add     rdi, r8
0x18002a10c  sub     rcx, 1
0x18002a110  jnz     short loc_18002A0C8
0x18002a112  movups  xmm0, xmmword ptr [rdi]
0x18002a115  movups  xmmword ptr [rax], xmm0
0x18002a118  movups  xmm1, xmmword ptr [rdi+0Ch]
0x18002a11c  movups  xmmword ptr [rax+0Ch], xmm1
0x18002a120  mov     rax, [r14+30h]
0x18002a124  add     rax, 18h
0x18002a128  lea     rcx, [rsp+178h+var_140]
0x18002a12d  mov     edx, 2
0x18002a132  movups  xmm0, xmmword ptr [rcx]
0x18002a135  movups  xmmword ptr [rax], xmm0
0x18002a138  movups  xmm1, xmmword ptr [rcx+10h]
0x18002a13c  movups  xmmword ptr [rax+10h], xmm1
0x18002a140  movups  xmm0, xmmword ptr [rcx+20h]
0x18002a144  movups  xmmword ptr [rax+20h], xmm0
0x18002a148  movups  xmm1, xmmword ptr [rcx+30h]
0x18002a14c  movups  xmmword ptr [rax+30h], xmm1
0x18002a150  movups  xmm0, xmmword ptr [rcx+40h]
0x18002a154  movups  xmmword ptr [rax+40h], xmm0
0x18002a158  movups  xmm1, xmmword ptr [rcx+50h]
0x18002a15c  movups  xmmword ptr [rax+50h], xmm1
0x18002a160  movups  xmm0, xmmword ptr [rcx+60h]
0x18002a164  movups  xmmword ptr [rax+60h], xmm0
0x18002a168  movups  xmm1, xmmword ptr [rcx+70h]
0x18002a16c  movups  xmmword ptr [rax+70h], xmm1
0x18002a170  add     rax, r8
0x18002a173  add     rcx, r8
0x18002a176  sub     rdx, 1
0x18002a17a  jnz     short loc_18002A132
0x18002a17c  movups  xmm0, xmmword ptr [rcx]
0x18002a17f  movups  xmmword ptr [rax], xmm0
0x18002a182  movups  xmm1, xmmword ptr [rcx+0Ch]
0x18002a186  movups  xmmword ptr [rax+0Ch], xmm1
0x18002a18a  mov     rax, [rsi]
0x18002a18d  mov     rcx, [rax+30h]
0x18002a191  mov     rdx, [rsp+178h+arg_20]
0x18002a199  cmp     rcx, rdx
0x18002a19c  jz      short loc_18002A1B1
0x18002a19e  mov     r8, [rdx+8]
0x18002a1a2  sub     r8, [rdx]
0x18002a1a5  sar     r8, 3
0x18002a1a9  mov     rdx, [rdx]
0x18002a1ac  call    ??$_Assign_counted_range@PEAV_bstr_t@@@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEAAXPEAV_bstr_t@@_K@Z; std::vector<_bstr_t>::_Assign_counted_range<_bstr_t *>(_bstr_t *,unsigned __int64)
0x18002a1b1  lea     rbx, stru_18005FCC8
0x18002a1b8  mov     rcx, rbx; SRWLock
0x18002a1bb  call    cs:__imp_AcquireSRWLockExclusive
0x18002a1c1  mov     [rsp+178h+arg_0], rbx
0x18002a1c9  mov     rax, [rsi]
0x18002a1cc  mov     rcx, [rax+30h]
0x18002a1d0  mov     rbp, [rcx+8]
0x18002a1d4  mov     rdi, [rcx]
0x18002a1d7  jmp     short loc_18002A1F4
0x18002a1d9  mov     rbx, [rsi]
0x18002a1dc  mov     r8, rdi
0x18002a1df  lea     rdx, [rsp+178h+var_150]
0x18002a1e4  call    ??$_Try_emplace@AEBV_bstr_t@@$$V@?$map@V_bstr_t@@PEAVTaskSchedulerSignal@@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@PEAX@std@@_N@1@AEBV_bstr_t@@@Z; std::map<_bstr_t,TaskSchedulerSignal *>::_Try_emplace<_bstr_t const &,>(_bstr_t const &)
0x18002a1e9  mov     rcx, [rax]
0x18002a1ec  mov     [rcx+28h], rbx
0x18002a1f0  add     rdi, 8
0x18002a1f4  cmp     rdi, rbp
0x18002a1f7  jnz     short loc_18002A1D9
0x18002a1f9  lea     rcx, [rsp+178h+arg_0]
0x18002a201  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002a206  mov     rbx, [rsi]
0x18002a209  mov     rcx, [rbx+30h]
0x18002a20d  add     rcx, 18h
0x18002a211  mov     edx, 2
0x18002a216  call    EvaluateTimeSpec
0x18002a21b  mov     edx, eax
0x18002a21d  mov     rcx, rbx
0x18002a220  call    ?SetState@DefaultSignal@GenericPlugin@@QEAAXW4NA_RULE_STATE@@@Z; GenericPlugin::DefaultSignal::SetState(NA_RULE_STATE)
0x18002a225  mov     rax, rsi
0x18002a228  lea     r11, [rsp+178h+var_18]
0x18002a230  mov     rbx, [r11+30h]
0x18002a234  mov     rbp, [r11+38h]
0x18002a238  mov     rsp, r11
0x18002a23b  pop     r14
0x18002a23d  pop     rdi
0x18002a23e  pop     rsi
0x18002a23f  retn
```
