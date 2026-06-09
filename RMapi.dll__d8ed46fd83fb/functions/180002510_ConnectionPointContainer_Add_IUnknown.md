# ConnectionPointContainer::Add(IUnknown *)

- ea: `0x180002510`
- end: `0x1800026e4`
- name: `?Add@ConnectionPointContainer@@QEAAKPEAUIUnknown@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct IUnknown *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001dac0`

## callees

- `0x180002510`
- `0x180003c70`
- `0x18000b120`
- `0x18000d2a0`
- `0x18000d784`
- `0x180010f80`
- `0x18001813c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000257d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000257d`

## string_xrefs

- `0x1800026c3`: `onecoreuap\net\mobility\radiomanagement\dll\radioconnectionpoint.cpp`

## pseudocode

```c
__int64 __fastcall ConnectionPointContainer::Add(LPCRITICAL_SECTION lpCriticalSection, struct IUnknown *a2)
{
  int v3; // eax
  unsigned __int32 v4; // ebp
  char *v5; // rdi
  volatile signed __int32 *v6; // rbx
  HANDLE OwningThread; // rbx
  __int64 v8; // rdi
  __int64 v9; // rcx
  int v11; // [rsp+20h] [rbp-68h]
  unsigned __int32 v12; // [rsp+30h] [rbp-58h] BYREF
  char *v13; // [rsp+38h] [rbp-50h] BYREF
  volatile signed __int32 *v14; // [rsp+40h] [rbp-48h]
  LPCRITICAL_SECTION v15; // [rsp+48h] [rbp-40h]
  __int64 v16; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v16 = 0;
  v3 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IUIRadioManagerNotifySink,
         &v16);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radioconnectionpoint.cpp",
      (const char *)(unsigned int)v3,
      v11);
  v4 = _InterlockedIncrement(&dword_180037E98);
  v12 = v4;
  EnterCriticalSection(lpCriticalSection);
  v15 = lpCriticalSection;
  v5 = (char *)operator new(0x138u);
  v13 = v5;
  *(_OWORD *)v5 = 0;
  *((_DWORD *)v5 + 2) = 1;
  *((_DWORD *)v5 + 3) = 1;
  *(_QWORD *)v5 = &std::_Ref_count_obj2<ConnectionPointContainer::CallerContext>::`vftable';
  std::_Construct_in_place<ConnectionPointContainer::CallerContext,unsigned long &,Microsoft::WRL::ComPtr<IUnknown> &>(
    v5 + 16,
    &v12,
    &v16);
  v13 = v5 + 16;
  v14 = (volatile signed __int32 *)v5;
  std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>>::emplace_back<std::shared_ptr<ConnectionPointContainer::CallerContext>>(
    &lpCriticalSection[1].LockCount,
    &v13);
  v6 = v14;
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  OwningThread = lpCriticalSection[1].OwningThread;
  v8 = *(_QWORD *)&lpCriticalSection[1].LockCount;
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_Dd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      10,
      WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids,
      v4,
      ((__int64)OwningThread - v8) >> 4);
  v9 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return v4;
}

```

## disassembly

```asm
0x180002510  mov     [rsp+arg_10], rbx
0x180002515  push    rbp
0x180002516  push    rsi
0x180002517  push    rdi
0x180002518  push    r14
0x18000251a  push    r15
0x18000251c  sub     rsp, 60h
0x180002520  mov     rax, cs:__security_cookie
0x180002527  xor     rax, rsp
0x18000252a  mov     [rsp+88h+var_30], rax
0x18000252f  mov     r9, rdx
0x180002532  mov     r14, rcx
0x180002535  xor     r15d, r15d
0x180002538  mov     [rsp+88h+var_38], r15
0x18000253d  mov     rax, [rdx]
0x180002540  lea     r8, [rsp+88h+var_38]
0x180002545  lea     rdx, IID_IUIRadioManagerNotifySink
0x18000254c  mov     rcx, r9
0x18000254f  mov     rax, [rax]
0x180002552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002557  mov     rcx, [rsp+88h]; this
0x18000255f  test    eax, eax
0x180002561  js      loc_1800026C0
0x180002567  mov     ebp, 1
0x18000256c  lock xadd cs:dword_180037E98, ebp
0x180002574  inc     ebp
0x180002576  mov     [rsp+88h+var_58], ebp
0x18000257a  mov     rcx, r14; lpCriticalSection
0x18000257d  call    cs:__imp_EnterCriticalSection
0x180002583  mov     [rsp+88h+var_40], r14
0x180002588  mov     ecx, 138h; Size
0x18000258d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002592  mov     rdi, rax
0x180002595  mov     qword ptr [rsp+88h+var_50], rax
0x18000259a  xorps   xmm0, xmm0
0x18000259d  movups  xmmword ptr [rax], xmm0
0x1800025a0  mov     dword ptr [rax+8], 1
0x1800025a7  mov     dword ptr [rax+0Ch], 1
0x1800025ae  lea     rax, ??_7?$_Ref_count_obj2@UCallerContext@ConnectionPointContainer@@@std@@6B@; const std::_Ref_count_obj2<ConnectionPointContainer::CallerContext>::`vftable'
0x1800025b5  mov     [rdi], rax
0x1800025b8  lea     rbx, [rdi+10h]
0x1800025bc  lea     r8, [rsp+88h+var_38]
0x1800025c1  lea     rdx, [rsp+88h+var_58]
0x1800025c6  mov     rcx, rbx
0x1800025c9  call    ??$_Construct_in_place@UCallerContext@ConnectionPointContainer@@AEAKAEAV?$ComPtr@UIUnknown@@@WRL@Microsoft@@@std@@YAXAEAUCallerContext@ConnectionPointContainer@@AEAKAEAV?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Z; std::_Construct_in_place<ConnectionPointContainer::CallerContext,ulong &,Microsoft::WRL::ComPtr<IUnknown> &>(ConnectionPointContainer::CallerContext &,ulong &,Microsoft::WRL::ComPtr<IUnknown> &)
0x1800025ce  nop
0x1800025cf  xorps   xmm0, xmm0
0x1800025d2  movups  [rsp+88h+var_50], xmm0
0x1800025d7  mov     qword ptr [rsp+88h+var_50], rbx
0x1800025dc  mov     qword ptr [rsp+88h+var_50+8], rdi
0x1800025e1  lea     rdx, [rsp+88h+var_50]
0x1800025e6  lea     rcx, [r14+30h]
0x1800025ea  call    ??$emplace_back@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@@?$vector@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@V?$allocator@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@UCallerContext@ConnectionPointContainer@@@1@$$QEAV21@@Z; std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>>::emplace_back<std::shared_ptr<ConnectionPointContainer::CallerContext>>(std::shared_ptr<ConnectionPointContainer::CallerContext> &&)
0x1800025ef  nop
0x1800025f0  mov     rbx, qword ptr [rsp+88h+var_50+8]
0x1800025f5  test    rbx, rbx
0x1800025f8  jz      short loc_180002632
0x1800025fa  mov     edi, 0FFFFFFFFh
0x1800025ff  mov     eax, edi
0x180002601  lock xadd [rbx+8], eax
0x180002606  cmp     eax, 1
0x180002609  jnz     short loc_180002632
0x18000260b  mov     rax, [rbx]
0x18000260e  mov     rcx, rbx
0x180002611  mov     rax, [rax]
0x180002614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002619  lock xadd [rbx+0Ch], edi
0x18000261e  cmp     edi, 1
0x180002621  jnz     short loc_180002632
0x180002623  mov     rax, [rbx]
0x180002626  mov     rcx, rbx
0x180002629  mov     rax, [rax+8]
0x18000262d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002632  mov     rbx, [r14+38h]
0x180002636  mov     rdi, [r14+30h]
0x18000263a  test    r14, r14
0x18000263d  jnz     loc_1800026D5
0x180002643  lea     rax, WPP_GLOBAL_Control
0x18000264a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002651  cmp     rcx, rax
0x180002654  jz      short loc_18000265C
0x180002656  test    byte ptr [rcx+1Ch], 4
0x18000265a  jnz     short loc_18000269B
0x18000265c  mov     rcx, [rsp+88h+var_38]
0x180002661  test    rcx, rcx
0x180002664  jz      short loc_180002678
0x180002666  mov     [rsp+88h+var_38], r15
0x18000266b  mov     rdx, [rcx]
0x18000266e  mov     rax, [rdx+10h]
0x180002672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002677  nop
0x180002678  mov     eax, ebp
0x18000267a  mov     rcx, [rsp+88h+var_30]
0x18000267f  xor     rcx, rsp; StackCookie
0x180002682  call    __security_check_cookie
0x180002687  mov     rbx, [rsp+88h+arg_10]
0x18000268f  add     rsp, 60h
0x180002693  pop     r15
0x180002695  pop     r14
0x180002697  pop     rdi
0x180002698  pop     rsi
0x180002699  pop     rbp
0x18000269a  retn
0x18000269b  sub     rbx, rdi
0x18000269e  sar     rbx, 4
0x1800026a2  mov     edx, 0Ah
0x1800026a7  mov     [rsp+88h+var_68], ebx
0x1800026ab  mov     r9d, ebp
0x1800026ae  lea     r8, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids
0x1800026b5  mov     rcx, [rcx+10h]
0x1800026b9  call    WPP_SF_Dd
0x1800026be  jmp     short loc_18000265C
0x1800026c0  mov     r9d, eax; char *
0x1800026c3  lea     r8, aOnecoreuapNetM_1; "onecoreuap\\net\\mobility\\radiomanagem"...
0x1800026ca  mov     edx, 23h ; '#'; void *
0x1800026cf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800026d5  mov     rcx, r14; lpCriticalSection
0x1800026d8  call    cs:__imp_LeaveCriticalSection
0x1800026de  jmp     loc_180002643
```
