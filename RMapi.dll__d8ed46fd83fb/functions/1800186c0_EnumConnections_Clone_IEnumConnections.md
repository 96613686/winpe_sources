# EnumConnections::Clone(IEnumConnections * *)

- ea: `0x1800186c0`
- end: `0x1800187fe`
- name: `?Clone@EnumConnections@@UEAAJPEAPEAUIEnumConnections@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(EnumConnections *__hidden this, struct IEnumConnections **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002ec0`
- `0x18000c2a4`
- `0x180010468`
- `0x180017b08`
- `0x180017bbc`
- `0x180018540`
- `0x1800186c0`
- `0x180018e20`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800186fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800186fb`

## string_xrefs

- `0x18001871d`: `onecoreuap\net\mobility\radiomanagement\dll\radioconnectionpoint.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EnumConnections::Clone(EnumConnections *this, struct IEnumConnections **a2)
{
  char *v5; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  struct IEnumConnections *v11; // rbx
  unsigned int v12; // edi
  __int64 v13; // [rsp+20h] [rbp-28h] BYREF
  char *v14; // [rsp+28h] [rbp-20h] BYREF
  struct IEnumConnections *v15; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v15 = 0;
  v5 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v14 = v5;
  v6 = CheckForUseCountOverflow((char *)this + 56);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = Microsoft::WRL::Details::Make<EnumConnections,std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>> &>(
           &v13,
           (char *)this + 56);
    Microsoft::WRL::ComPtr<IEnumConnectionPoints>::operator=<EnumConnectionPoints>(&v15, v8);
    v10 = v13;
    if ( v13 )
    {
      v13 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEnumConnectionPoints>::Release(
        v10,
        v9);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v14);
    v11 = v15;
    if ( v15 )
    {
      ((void (__fastcall *)(struct IEnumConnections *))v15->lpVtbl->AddRef)(v15);
      *a2 = v11;
      v12 = 0;
    }
    else
    {
      v12 = -2147024882;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids, v12);
    if ( v11 )
      ((void (__fastcall *)(struct IEnumConnections *))v11->lpVtbl->Release)(v11);
    return v12;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radioconnectionpoint.cpp",
      (const char *)(unsigned int)v6,
      v13);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v14);
    return v7;
  }
}

```

## disassembly

```asm
0x1800186c0  mov     [rsp+arg_10], rbx
0x1800186c5  mov     [rsp+arg_18], rsi
0x1800186ca  push    rdi
0x1800186cb  sub     rsp, 40h
0x1800186cf  mov     rdi, rdx
0x1800186d2  mov     rsi, rcx
0x1800186d5  test    rdx, rdx
0x1800186d8  jnz     short loc_1800186E4
0x1800186da  mov     eax, 80004003h
0x1800186df  jmp     loc_1800187EE
0x1800186e4  mov     qword ptr [rdx], 0
0x1800186eb  mov     [rsp+48h+var_18], 0
0x1800186f4  lea     rbx, [rcx+10h]
0x1800186f8  mov     rcx, rbx; lpCriticalSection
0x1800186fb  call    cs:__imp_EnterCriticalSection
0x180018701  mov     [rsp+48h+var_20], rbx
0x180018706  lea     rcx, [rsi+38h]
0x18001870a  call    ?CheckForUseCountOverflow@@YAJAEBV?$vector@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@V?$allocator@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@@2@@std@@@Z; CheckForUseCountOverflow(std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>> const &)
0x18001870f  mov     ebx, eax
0x180018711  test    eax, eax
0x180018713  jns     short loc_180018741
0x180018715  mov     rcx, [rsp+48h]; this
0x18001871a  mov     r9d, eax; char *
0x18001871d  lea     r8, aOnecoreuapNetM_1; "onecoreuap\\net\\mobility\\radiomanagem"...
0x180018724  mov     edx, 129h; void *
0x180018729  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001872e  nop
0x18001872f  lea     rcx, [rsp+48h+var_20]
0x180018734  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180018739  nop
0x18001873a  mov     eax, ebx
0x18001873c  jmp     loc_1800187EE
0x180018741  lea     rdx, [rsi+38h]
0x180018745  lea     rcx, [rsp+48h+var_28]
0x18001874a  call    ??$Make@VEnumConnections@@AEAV?$vector@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@V?$allocator@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@@2@@std@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VEnumConnections@@@12@AEAV?$vector@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@V?$allocator@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@@2@@std@@@Z; Microsoft::WRL::Details::Make<EnumConnections,std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>> &>(std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>> &)
0x18001874f  mov     rdx, rax
0x180018752  lea     rcx, [rsp+48h+var_18]
0x180018757  call    ??$?4VEnumConnectionPoints@@@?$ComPtr@UIEnumConnectionPoints@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV?$ComPtr@VEnumConnectionPoints@@@12@@Z; Microsoft::WRL::ComPtr<IEnumConnectionPoints>::operator=<EnumConnectionPoints>(Microsoft::WRL::ComPtr<EnumConnectionPoints> &&)
0x18001875c  mov     rcx, [rsp+48h+var_28]
0x180018761  test    rcx, rcx
0x180018764  jz      short loc_180018775
0x180018766  mov     [rsp+48h+var_28], 0
0x18001876f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEnumConnectionPoints@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEnumConnectionPoints>::Release(void)
0x180018774  nop
0x180018775  lea     rcx, [rsp+48h+var_20]
0x18001877a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001877f  mov     rbx, [rsp+48h+var_18]
0x180018784  test    rbx, rbx
0x180018787  jz      short loc_1800187A0
0x180018789  mov     rax, [rbx]
0x18001878c  mov     rcx, rbx
0x18001878f  mov     rax, [rax+8]
0x180018793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018798  nop
0x180018799  mov     [rdi], rbx
0x18001879c  xor     edi, edi
0x18001879e  jmp     short loc_1800187A5
0x1800187a0  mov     edi, 8007000Eh
0x1800187a5  lea     rax, WPP_GLOBAL_Control
0x1800187ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187b3  cmp     rcx, rax
0x1800187b6  jz      short loc_1800187D7
0x1800187b8  test    byte ptr [rcx+1Ch], 4
0x1800187bc  jz      short loc_1800187D7
0x1800187be  mov     edx, 19h
0x1800187c3  mov     r9d, edi
0x1800187c6  lea     r8, WPP_2ce43deefc5a38284e7a25a8a4237130_Traceguids
0x1800187cd  mov     rcx, [rcx+10h]
0x1800187d1  call    WPP_SF_d
0x1800187d6  nop
0x1800187d7  test    rbx, rbx
0x1800187da  jz      short loc_1800187EC
0x1800187dc  mov     rdx, [rbx]
0x1800187df  mov     rcx, rbx
0x1800187e2  mov     rax, [rdx+10h]
0x1800187e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187eb  nop
0x1800187ec  mov     eax, edi
0x1800187ee  mov     rbx, [rsp+48h+arg_10]
0x1800187f3  mov     rsi, [rsp+48h+arg_18]
0x1800187f8  add     rsp, 40h
0x1800187fc  pop     rdi
0x1800187fd  retn
```
