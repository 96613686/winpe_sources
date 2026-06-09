# KeyMachine::KeyMachine(ContentIdString const &,Microsoft::WRL::ComPtr<ICoreForKey> const &)

- ea: `0x180020074`
- end: `0x1800202ef`
- name: `??0KeyMachine@@QEAA@AEBVContentIdString@@AEBV?$ComPtr@UICoreForKey@@@WRL@Microsoft@@@Z`
- size: `635`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001ece0`
- `0x18008516c`

## callees

- `0x18000b7fc`
- `0x180013b50`
- `0x18001fd40`
- `0x180020074`
- `0x18003a204`
- `0x1800593bc`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180020131`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180020131`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x180020296`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x180020296`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800202b9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800202b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall KeyMachine::KeyMachine(__int64 a1, const struct ContentIdString *a2, _QWORD *a3)
{
  int v6; // eax
  HRESULT Guid; // eax
  int Format; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)a1 = &IKeyForLease::`vftable';
  *(_QWORD *)(a1 + 8) = &IKeyForLease::`vftable';
  *(_QWORD *)(a1 + 16) = &IKeyForCore::`vftable';
  *(_DWORD *)(a1 + 28) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IKeyStateMachine,IKeyForLease,IKeyForCore>::`vftable';
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IKeyStateMachine,IKeyForLease,IKeyForCore>::`vftable'{for `IKeyForLease'};
  *(_QWORD *)(a1 + 16) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IKeyStateMachine,IKeyForLease,IKeyForCore>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IKeyForCore>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)(a1 + 32) = &StateMachine<KeyMachine,KeyState>::`vftable';
  *(_QWORD *)(a1 + 40) = KeyMachine::Initial::Instance;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>();
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(a1 + 88), 0, 0);
  *(_DWORD *)(a1 + 128) = 0;
  *(_QWORD *)a1 = &KeyMachine::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IKeyStateMachine,IKeyForLease,IKeyForCore>'};
  *(_QWORD *)(a1 + 8) = &RootKeyMachine::`vftable'{for `IKeyForLease'};
  *(_QWORD *)(a1 + 16) = &KeyMachine::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IKeyForCore>'};
  *(_QWORD *)(a1 + 32) = &KeyMachine::`vftable'{for `StateMachine<KeyMachine,KeyState>'};
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = *a3;
  Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(a1 + 160);
  ContentIdString::ContentIdString((ContentIdString *)(a1 + 168), a2);
  *(_OWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  *(_QWORD *)(a1 + 224) = 7;
  *(_WORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  *(_DWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = 0;
  *(_DWORD *)(a1 + 280) = 0x10000000;
  *(_DWORD *)(a1 + 284) = 1;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = 0;
  *(_QWORD *)(a1 + 304) = 0;
  *(GUID *)(a1 + 312) = GUID_NULL;
  *(_OWORD *)(a1 + 328) = 0;
  *(_QWORD *)(a1 + 344) = 0;
  *(_QWORD *)(a1 + 352) = 7;
  *(_WORD *)(a1 + 328) = 0;
  *(_QWORD *)(a1 + 360) = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const struct ContentIdString **)a2;
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
    0x62u,
    "KeyMachine::KeyMachine",
    (wchar_t *)L"Key Machine for content: %s",
    a2);
  _InterlockedIncrement64((volatile signed __int64 *)&KeyMachineCount);
  v6 = CoIncrementMTAUsage(a1 + 304);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      (const char *)(unsigned int)v6,
      Format);
  Guid = CoCreateGuid((GUID *)(a1 + 312));
  if ( Guid < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      (const char *)(unsigned int)Guid,
      Format);
  return a1;
}

```

## disassembly

```asm
0x180020074  mov     [rsp+arg_8], rbx
0x180020079  mov     [rsp+arg_18], rbp
0x18002007e  mov     [rsp+arg_0], rcx
0x180020083  push    rsi
0x180020084  push    rdi
0x180020085  push    r14
0x180020087  sub     rsp, 30h
0x18002008b  mov     rsi, r8
0x18002008e  mov     rdi, rdx
0x180020091  mov     rbx, rcx
0x180020094  lea     rax, ??_7IKeyForLease@@6B@; const IKeyForLease::`vftable'
0x18002009b  mov     [rcx], rax
0x18002009e  lea     rax, ??_7IKeyForLease@@6B@; const IKeyForLease::`vftable'
0x1800200a5  mov     [rcx+8], rax
0x1800200a9  lea     rax, ??_7IKeyForCore@@6B@; const IKeyForCore::`vftable'
0x1800200b0  mov     [rcx+10h], rax
0x1800200b4  mov     dword ptr [rcx+1Ch], 1
0x1800200bb  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIKeyStateMachine@@UIKeyForLease@@UIKeyForCore@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IKeyStateMachine,IKeyForLease,IKeyForCore>::`vftable'
0x1800200c2  mov     [rcx], rax
0x1800200c5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIKeyStateMachine@@UIKeyForLease@@UIKeyForCore@@@WRL@Microsoft@@6BIKeyForLease@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IKeyStateMachine,IKeyForLease,IKeyForCore>::`vftable'{for `IKeyForLease'}
0x1800200cc  mov     [rcx+8], rax
0x1800200d0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIKeyStateMachine@@UIKeyForLease@@UIKeyForCore@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIKeyForCore@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IKeyStateMachine,IKeyForLease,IKeyForCore>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IKeyForCore>'}
0x1800200d7  mov     [rcx+10h], rax
0x1800200db  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800200e2  xor     ebp, ebp
0x1800200e4  test    rcx, rcx
0x1800200e7  jz      short loc_1800200F6
0x1800200e9  mov     rax, [rcx]
0x1800200ec  mov     rax, [rax+8]
0x1800200f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200f5  nop
0x1800200f6  lea     rax, ??_7?$StateMachine@VKeyMachine@@VKeyState@@@@6B@; const StateMachine<KeyMachine,KeyState>::`vftable'
0x1800200fd  mov     [rbx+20h], rax
0x180020101  lea     rax, ?Instance@Initial@KeyMachine@@2V12@A; KeyMachine::Initial KeyMachine::Initial::Instance
0x180020108  mov     [rbx+28h], rax
0x18002010c  lea     rcx, [rbx+30h]
0x180020110  mov     [rcx], rbp
0x180020113  mov     [rcx+8], rbp
0x180020117  mov     [rcx+10h], rbp
0x18002011b  mov     [rcx+18h], rbp
0x18002011f  mov     [rcx+20h], rbp
0x180020123  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x180020128  lea     rcx, [rbx+58h]; lpCriticalSection
0x18002012c  xor     r8d, r8d; Flags
0x18002012f  xor     edx, edx; dwSpinCount
0x180020131  call    cs:__imp_InitializeCriticalSectionEx
0x180020137  mov     [rbx+80h], ebp
0x18002013d  lea     rax, ??_7KeyMachine@@6B?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIKeyStateMachine@@UIKeyForLease@@UIKeyForCore@@@WRL@Microsoft@@@; const KeyMachine::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IKeyStateMachine,IKeyForLease,IKeyForCore>'}
0x180020144  mov     [rbx], rax
0x180020147  lea     rax, ??_7RootKeyMachine@@6BIKeyForLease@@@; const RootKeyMachine::`vftable'{for `IKeyForLease'}
0x18002014e  mov     [rbx+8], rax
0x180020152  lea     rax, ??_7KeyMachine@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIKeyForCore@@@Details@WRL@Microsoft@@@; const KeyMachine::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IKeyForCore>'}
0x180020159  mov     [rbx+10h], rax
0x18002015d  lea     rax, ??_7KeyMachine@@6B?$StateMachine@VKeyMachine@@VKeyState@@@@@; const KeyMachine::`vftable'{for `StateMachine<KeyMachine,KeyState>'}
0x180020164  mov     [rbx+20h], rax
0x180020168  mov     [rbx+88h], rbp
0x18002016f  mov     [rbx+90h], rbp
0x180020176  mov     [rbx+98h], rbp
0x18002017d  lea     rcx, [rbx+0A0h]
0x180020184  mov     rax, [rsi]
0x180020187  mov     [rcx], rax
0x18002018a  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x18002018f  nop
0x180020190  lea     rcx, [rbx+0A8h]; this
0x180020197  mov     rdx, rdi; struct ContentIdString *
0x18002019a  call    ??0ContentIdString@@QEAA@AEBV0@@Z; ContentIdString::ContentIdString(ContentIdString const &)
0x18002019f  nop
0x1800201a0  xorps   xmm0, xmm0
0x1800201a3  movups  xmmword ptr [rbx+0C8h], xmm0
0x1800201aa  mov     [rbx+0D8h], rbp
0x1800201b1  mov     ecx, 7
0x1800201b6  mov     [rbx+0E0h], rcx
0x1800201bd  mov     [rbx+0C8h], bp
0x1800201c4  mov     [rbx+0E8h], rbp
0x1800201cb  mov     [rbx+0F0h], rbp
0x1800201d2  mov     [rbx+0F8h], rbp
0x1800201d9  mov     [rbx+100h], ebp
0x1800201df  mov     [rbx+108h], rbp
0x1800201e6  mov     [rbx+110h], rbp
0x1800201ed  mov     dword ptr [rbx+118h], 10000000h
0x1800201f7  mov     dword ptr [rbx+11Ch], 1
0x180020201  mov     [rbx+120h], rbp
0x180020208  mov     [rbx+128h], rbp
0x18002020f  lea     r14, [rbx+130h]
0x180020216  mov     [r14], rbp
0x180020219  lea     rsi, [rbx+138h]
0x180020220  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180020227  movdqu  xmmword ptr [rsi], xmm0
0x18002022b  xorps   xmm1, xmm1
0x18002022e  movups  xmmword ptr [rbx+148h], xmm1
0x180020235  mov     [rbx+158h], rbp
0x18002023c  mov     [rbx+160h], rcx
0x180020243  mov     [rbx+148h], bp
0x18002024a  mov     [rbx+168h], rbp
0x180020251  cmp     [rdi+18h], rcx
0x180020255  jbe     short loc_18002025A
0x180020257  mov     rdi, [rdi]
0x18002025a  mov     [rsp+48h+var_20], rdi
0x18002025f  lea     rax, aKeyMachineForC; "Key Machine for content: %s"
0x180020266  mov     [rsp+48h+Format], rax; int
0x18002026b  lea     r9, aKeymachineKeym; "KeyMachine::KeyMachine"
0x180020272  mov     r8d, 62h ; 'b'; unsigned int
0x180020278  lea     rdi, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x18002027f  mov     rdx, rdi; char *
0x180020282  lea     ecx, [r8-5Fh]; unsigned int
0x180020286  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18002028b  lock inc cs:?KeyMachineCount@@3_KA; unsigned __int64 KeyMachineCount
0x180020293  mov     rcx, r14
0x180020296  call    cs:__imp_CoIncrementMTAUsage
0x18002029c  mov     rcx, [rsp+48h]; this
0x1800202a1  test    eax, eax
0x1800202a3  jns     short loc_1800202B6
0x1800202a5  mov     r9d, eax; char *
0x1800202a8  mov     r8, rdi; unsigned int
0x1800202ab  mov     edx, 69h ; 'i'; void *
0x1800202b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800202b6  mov     rcx, rsi; pguid
0x1800202b9  call    cs:__imp_CoCreateGuid
0x1800202bf  mov     rcx, [rsp+48h]; this
0x1800202c4  test    eax, eax
0x1800202c6  jns     short loc_1800202D9
0x1800202c8  mov     r9d, eax; char *
0x1800202cb  mov     r8, rdi; unsigned int
0x1800202ce  mov     edx, 6Ah ; 'j'; void *
0x1800202d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800202d9  mov     rax, rbx
0x1800202dc  mov     rbx, [rsp+48h+arg_8]
0x1800202e1  mov     rbp, [rsp+48h+arg_18]
0x1800202e6  add     rsp, 30h
0x1800202ea  pop     r14
0x1800202ec  pop     rdi
0x1800202ed  pop     rsi
0x1800202ee  retn
```
