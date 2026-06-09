# ConnectionPointContainer::Copy(IEnumConnections * *)

- ea: `0x1800188e0`
- end: `0x1800189f0`
- name: `?Copy@ConnectionPointContainer@@QEAAJPEAPEAUIEnumConnections@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(ConnectionPointContainer *__hidden this, struct IEnumConnections **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e780`

## callees

- `0x180002ec0`
- `0x18000c2a4`
- `0x180010468`
- `0x180017b08`
- `0x180017bbc`
- `0x180018370`
- `0x180018540`
- `0x1800188e0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018900`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018900`

## string_xrefs

- `0x180018925`: `onecoreuap\net\mobility\radiomanagement\dll\radioconnectionpoint.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConnectionPointContainer::Copy(struct _RTL_CRITICAL_SECTION *this, struct IEnumConnections **a2)
{
  int v4; // eax
  __int64 v5; // r8
  unsigned int v6; // ebx
  __int64 v8; // rax
  struct IEnumConnections *v9; // rbx
  unsigned int v10; // edi
  int v11[2]; // [rsp+20h] [rbp-28h] BYREF
  struct IEnumConnections *v12; // [rsp+28h] [rbp-20h] BYREF
  _BYTE v13[24]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a2 = 0;
  v12 = 0;
  EnterCriticalSection(this);
  *(_QWORD *)v11 = this;
  v4 = CheckForUseCountOverflow(&this[1].LockCount);
  v6 = v4;
  if ( v4 >= 0 )
  {
    v8 = Microsoft::WRL::Details::Make<EnumConnections,std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>> &>(
           v13,
           v5);
    Microsoft::WRL::ComPtr<IEnumConnectionPoints>::operator=<EnumConnectionPoints>(&v12, v8);
    Microsoft::WRL::ComPtr<EnumConnectionPoints>::~ComPtr<EnumConnectionPoints>(v13);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v11);
    v9 = v12;
    if ( v12 )
    {
      ((void (__fastcall *)(struct IEnumConnections *))v12->lpVtbl->AddRef)(v12);
      *a2 = v9;
      v10 = 0;
    }
    else
    {
      v10 = -2147024882;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids, v10);
    if ( v9 )
      ((void (__fastcall *)(struct IEnumConnections *))v9->lpVtbl->Release)(v9);
    return v10;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radioconnectionpoint.cpp",
      (const char *)(unsigned int)v4,
      v11[0]);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v11);
    return v6;
  }
}

```

## disassembly

```asm
0x1800188e0  mov     [rsp+arg_10], rbx
0x1800188e5  push    rdi
0x1800188e6  sub     rsp, 40h
0x1800188ea  mov     rdi, rdx
0x1800188ed  mov     rbx, rcx
0x1800188f0  mov     qword ptr [rdx], 0
0x1800188f7  mov     [rsp+48h+var_20], 0
0x180018900  call    cs:__imp_EnterCriticalSection
0x180018906  mov     qword ptr [rsp+48h+var_28], rbx; int
0x18001890b  lea     r8, [rbx+30h]
0x18001890f  mov     rcx, r8
0x180018912  call    ?CheckForUseCountOverflow@@YAJAEBV?$vector@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@V?$allocator@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@@2@@std@@@Z; CheckForUseCountOverflow(std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>> const &)
0x180018917  mov     ebx, eax
0x180018919  test    eax, eax
0x18001891b  jns     short loc_180018948
0x18001891d  mov     rcx, [rsp+48h]; this
0x180018922  mov     r9d, eax; char *
0x180018925  lea     r8, aOnecoreuapNetM_1; "onecoreuap\\net\\mobility\\radiomanagem"...
0x18001892c  mov     edx, 76h ; 'v'; void *
0x180018931  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018936  lea     rcx, [rsp+48h+var_28]
0x18001893b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180018940  nop
0x180018941  mov     eax, ebx
0x180018943  jmp     loc_1800189E5
0x180018948  mov     rdx, r8
0x18001894b  lea     rcx, [rsp+48h+var_18]
0x180018950  call    ??$Make@VEnumConnections@@AEAV?$vector@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@V?$allocator@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@@2@@std@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VEnumConnections@@@12@AEAV?$vector@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@V?$allocator@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@@2@@std@@@Z; Microsoft::WRL::Details::Make<EnumConnections,std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>> &>(std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>> &)
0x180018955  mov     rdx, rax
0x180018958  lea     rcx, [rsp+48h+var_20]
0x18001895d  call    ??$?4VEnumConnectionPoints@@@?$ComPtr@UIEnumConnectionPoints@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV?$ComPtr@VEnumConnectionPoints@@@12@@Z; Microsoft::WRL::ComPtr<IEnumConnectionPoints>::operator=<EnumConnectionPoints>(Microsoft::WRL::ComPtr<EnumConnectionPoints> &&)
0x180018962  lea     rcx, [rsp+48h+var_18]
0x180018967  call    ??1?$ComPtr@VEnumConnectionPoints@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<EnumConnectionPoints>::~ComPtr<EnumConnectionPoints>(void)
0x18001896c  lea     rcx, [rsp+48h+var_28]
0x180018971  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180018976  mov     rbx, [rsp+48h+var_20]
0x18001897b  test    rbx, rbx
0x18001897e  jz      short loc_180018997
0x180018980  mov     rax, [rbx]
0x180018983  mov     rcx, rbx
0x180018986  mov     rax, [rax+8]
0x18001898a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001898f  nop
0x180018990  mov     [rdi], rbx
0x180018993  xor     edi, edi
0x180018995  jmp     short loc_18001899C
0x180018997  mov     edi, 8007000Eh
0x18001899c  lea     rax, WPP_GLOBAL_Control
0x1800189a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189aa  cmp     rcx, rax
0x1800189ad  jz      short loc_1800189CE
0x1800189af  test    byte ptr [rcx+1Ch], 4
0x1800189b3  jz      short loc_1800189CE
0x1800189b5  mov     edx, 0Eh
0x1800189ba  mov     r9d, edi
0x1800189bd  lea     r8, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids
0x1800189c4  mov     rcx, [rcx+10h]
0x1800189c8  call    WPP_SF_d
0x1800189cd  nop
0x1800189ce  test    rbx, rbx
0x1800189d1  jz      short loc_1800189E3
0x1800189d3  mov     rdx, [rbx]
0x1800189d6  mov     rcx, rbx
0x1800189d9  mov     rax, [rdx+10h]
0x1800189dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189e2  nop
0x1800189e3  mov     eax, edi
0x1800189e5  mov     rbx, [rsp+48h+arg_10]
0x1800189ea  add     rsp, 40h
0x1800189ee  pop     rdi
0x1800189ef  retn
```
