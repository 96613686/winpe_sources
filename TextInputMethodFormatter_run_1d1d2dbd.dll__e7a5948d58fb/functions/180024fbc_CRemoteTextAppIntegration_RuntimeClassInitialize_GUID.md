# CRemoteTextAppIntegration::RuntimeClassInitialize(_GUID)

- ea: `0x180024fbc`
- end: `0x180025265`
- name: `?RuntimeClassInitialize@CRemoteTextAppIntegration@@QEAAJU_GUID@@@Z`
- size: `681`
- prototype: `__int64 __fastcall(struct _GUID *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018e44`

## callees

- `0x180002270`
- `0x180012030`
- `0x180012050`
- `0x180024fbc`
- `0x1800536fc`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800251f9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800251f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002512d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002512d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025164`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800251d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025164`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800251d5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002519e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002519e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002515c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002517c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800251cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800251ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002515c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002517c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800251cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800251ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CRemoteTextAppIntegration::RuntimeClassInitialize(struct _GUID *this, struct _GUID *a2)
{
  __int64 v3; // rcx
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  int v6; // eax
  char *EventW; // rsi
  HANDLE *Data4; // r14
  HANDLE v9; // rbp
  DWORD LastError; // ebx
  char *Thread; // rsi
  struct _GUID *v12; // rdi
  void *v13; // rbp
  DWORD v14; // ebx
  const char *v15; // r9
  DWORD dwCreationFlags; // [rsp+20h] [rbp-48h]
  char v18; // [rsp+30h] [rbp-38h] BYREF
  char v19; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  this[56] = *a2;
  v3 = *(_QWORD *)&this[8].Data1;
  if ( v3 )
  {
    *(_QWORD *)&this[8].Data1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  *(_QWORD *)&this[8].Data1 = 0;
  v4 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( !v4 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
      (const char *)0x8007000ELL,
      dwCreationFlags);
  v4[7] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITextVirtualizationKeyRouting,ITextVirtualizationClient,IReconnectableEndpointOwner>::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITextVirtualizationKeyRouting,ITextVirtualizationClient,IReconnectableEndpointOwner>::`vftable'{for `ITextVirtualizationClient'};
  *((_QWORD *)v4 + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITextVirtualizationKeyRouting,ITextVirtualizationClient,IReconnectableEndpointOwner>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IReconnectableEndpointOwner>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v5 = &TextVirtualizationClient::`vftable';
  *((_QWORD *)v5 + 1) = &TextVirtualizationClient::`vftable'{for `ITextVirtualizationClient'};
  *((_QWORD *)v5 + 2) = &TextVirtualizationClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IReconnectableEndpointOwner>'};
  *((_QWORD *)v5 + 4) = 0;
  *((_QWORD *)v5 + 5) = 0;
  *((_QWORD *)v5 + 6) = 0;
  *((_QWORD *)v5 + 7) = 0;
  *((_QWORD *)v5 + 8) = 0;
  *((_QWORD *)v5 + 9) = 0;
  *((_QWORD *)v5 + 11) = 0;
  *((_QWORD *)v5 + 12) = 0;
  *((_QWORD *)v5 + 13) = 0;
  *((_OWORD *)v5 + 7) = 0;
  *((_OWORD *)v5 + 8) = 0;
  *((_QWORD *)v5 + 18) = 0;
  *((_QWORD *)v5 + 19) = 0;
  *((_QWORD *)v5 + 10) = (unsigned __int64)&this[1] & -(__int64)(this != 0);
  v6 = TextVirtualizationClient::InitializeTvServerConnection((TextVirtualizationClient *)v5);
  if ( v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textvirtualizationproxy\\TextVirtualizationClient.cpp",
      (const char *)(unsigned int)v6,
      dwCreationFlags);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 8LL))(v5);
  *(_QWORD *)&this[8].Data1 = v5;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  Data4 = (HANDLE *)this[5].Data4;
  if ( this[5].Data4 == (unsigned __int8 *)&v18 )
  {
    if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(EventW);
  }
  else
  {
    v9 = *Data4;
    if ( (char *)*Data4 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v9);
      SetLastError(LastError);
    }
    *Data4 = EventW;
  }
  Thread = (char *)CreateThread(
                     0,
                     0,
                     (LPTHREAD_START_ROUTINE)CRemoteTextAppIntegration::CoreMessagingThreadProc,
                     this,
                     0,
                     &this[6].Data1);
  v12 = this + 5;
  if ( v12 == (struct _GUID *)&v19 )
  {
    if ( (unsigned __int64)(Thread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(Thread);
  }
  else
  {
    v13 = *(void **)&v12->Data1;
    if ( (unsigned __int64)(*(_QWORD *)&v12->Data1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v14 = GetLastError();
      CloseHandle(v13);
      SetLastError(v14);
    }
    *(_QWORD *)&v12->Data1 = Thread;
  }
  if ( WaitForSingleObject(*Data4, 0xFFFFFFFF) == 258 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x9C,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
      v15);
  return 0;
}

```

## disassembly

```asm
0x180024fbc  mov     [rsp+arg_10], rbx
0x180024fc1  push    rbp
0x180024fc2  push    rsi
0x180024fc3  push    rdi
0x180024fc4  push    r14
0x180024fc6  push    r15
0x180024fc8  sub     rsp, 40h
0x180024fcc  mov     rdi, rcx
0x180024fcf  movaps  xmm0, xmmword ptr [rdx]
0x180024fd2  movdqu  xmmword ptr [rcx+380h], xmm0
0x180024fda  mov     rcx, [rcx+80h]
0x180024fe1  xor     r15d, r15d
0x180024fe4  test    rcx, rcx
0x180024fe7  jz      short loc_180024FFD
0x180024fe9  mov     [rdi+80h], r15
0x180024ff0  mov     rax, [rcx]
0x180024ff3  mov     rax, [rax+10h]
0x180024ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ffc  nop
0x180024ffd  mov     [rdi+80h], r15
0x180025004  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002500b  mov     ecx, 0A0h; unsigned __int64
0x180025010  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025015  mov     rbx, rax
0x180025018  mov     [rsp+68h+arg_0], rax
0x18002501d  test    rax, rax
0x180025020  jz      loc_180025233
0x180025026  mov     esi, 1
0x18002502b  mov     [rax+1Ch], esi
0x18002502e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITextVirtualizationKeyRouting@@UITextVirtualizationClient@@UIReconnectableEndpointOwner@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITextVirtualizationKeyRouting,ITextVirtualizationClient,IReconnectableEndpointOwner>::`vftable'
0x180025035  mov     [rbx], rax
0x180025038  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITextVirtualizationKeyRouting@@UITextVirtualizationClient@@UIReconnectableEndpointOwner@@@WRL@Microsoft@@6BITextVirtualizationClient@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITextVirtualizationKeyRouting,ITextVirtualizationClient,IReconnectableEndpointOwner>::`vftable'{for `ITextVirtualizationClient'}
0x18002503f  mov     [rbx+8], rax
0x180025043  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UITextVirtualizationKeyRouting@@UITextVirtualizationClient@@UIReconnectableEndpointOwner@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIReconnectableEndpointOwner@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ITextVirtualizationKeyRouting,ITextVirtualizationClient,IReconnectableEndpointOwner>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IReconnectableEndpointOwner>'}
0x18002504a  mov     [rbx+10h], rax
0x18002504e  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180025055  test    rcx, rcx
0x180025058  jz      short loc_180025067
0x18002505a  mov     rax, [rcx]
0x18002505d  mov     rax, [rax+8]
0x180025061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025066  nop
0x180025067  lea     rax, ??_7TextVirtualizationClient@@6B@; const TextVirtualizationClient::`vftable'
0x18002506e  mov     [rbx], rax
0x180025071  lea     rax, ??_7TextVirtualizationClient@@6BITextVirtualizationClient@@@; const TextVirtualizationClient::`vftable'{for `ITextVirtualizationClient'}
0x180025078  mov     [rbx+8], rax
0x18002507c  lea     rax, ??_7TextVirtualizationClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIReconnectableEndpointOwner@@@Details@WRL@Microsoft@@@; const TextVirtualizationClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IReconnectableEndpointOwner>'}
0x180025083  mov     [rbx+10h], rax
0x180025087  mov     [rbx+20h], r15
0x18002508b  mov     [rbx+28h], r15
0x18002508f  mov     [rbx+30h], r15
0x180025093  mov     [rbx+38h], r15
0x180025097  mov     [rbx+40h], r15
0x18002509b  mov     [rbx+48h], r15
0x18002509f  mov     [rbx+58h], r15
0x1800250a3  mov     [rbx+60h], r15
0x1800250a7  mov     [rbx+68h], r15
0x1800250ab  xorps   xmm0, xmm0
0x1800250ae  xor     eax, eax
0x1800250b0  movups  xmmword ptr [rbx+70h], xmm0
0x1800250b4  movups  xmmword ptr [rbx+80h], xmm0
0x1800250bb  mov     [rbx+90h], rax
0x1800250c2  mov     [rbx+98h], r15
0x1800250c9  mov     [rsp+68h+arg_8], rbx
0x1800250ce  mov     [rsp+68h+arg_0], r15
0x1800250d3  mov     rax, rdi
0x1800250d6  lea     rdx, [rdi+10h]
0x1800250da  neg     rax
0x1800250dd  sbb     rcx, rcx
0x1800250e0  and     rcx, rdx
0x1800250e3  mov     [rbx+50h], rcx
0x1800250e7  mov     rcx, rbx; this
0x1800250ea  call    ?InitializeTvServerConnection@TextVirtualizationClient@@AEAAJXZ; TextVirtualizationClient::InitializeTvServerConnection(void)
0x1800250ef  mov     rcx, [rsp+68h]; this
0x1800250f4  test    eax, eax
0x1800250f6  js      loc_180025250
0x1800250fc  mov     rax, [rbx]
0x1800250ff  mov     rcx, rbx
0x180025102  mov     rax, [rax+8]
0x180025106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002510b  nop
0x18002510c  mov     [rdi+80h], rbx
0x180025113  mov     rax, [rbx]
0x180025116  mov     rcx, rbx
0x180025119  mov     rax, [rax+10h]
0x18002511d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025122  nop
0x180025123  xor     r9d, r9d; lpName
0x180025126  xor     r8d, r8d; bInitialState
0x180025129  mov     edx, esi; bManualReset
0x18002512b  xor     ecx, ecx; lpEventAttributes
0x18002512d  call    cs:__imp_CreateEventW
0x180025133  mov     rsi, rax
0x180025136  lea     r14, [rdi+58h]
0x18002513a  lea     rax, [rsp+68h+var_38]
0x18002513f  cmp     r14, rax
0x180025142  jz      short loc_18002516F
0x180025144  mov     rbp, [r14]
0x180025147  lea     rdx, [rbp-1]
0x18002514b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002514f  ja      short loc_18002516A
0x180025151  call    cs:__imp_GetLastError
0x180025157  mov     ebx, eax
0x180025159  mov     rcx, rbp; hObject
0x18002515c  call    cs:__imp_CloseHandle
0x180025162  mov     ecx, ebx; dwErrCode
0x180025164  call    cs:__imp_SetLastError
0x18002516a  mov     [r14], rsi
0x18002516d  jmp     short loc_180025182
0x18002516f  lea     rax, [rsi-1]
0x180025173  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180025177  ja      short loc_180025182
0x180025179  mov     rcx, rsi; hObject
0x18002517c  call    cs:__imp_CloseHandle
0x180025182  lea     rax, [rdi+60h]
0x180025186  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18002518b  mov     [rsp+68h+dwCreationFlags], r15d; dwCreationFlags
0x180025190  mov     r9, rdi; lpParameter
0x180025193  lea     r8, ?CoreMessagingThreadProc@CRemoteTextAppIntegration@@CAKPEAX@Z; lpStartAddress
0x18002519a  xor     edx, edx; dwStackSize
0x18002519c  xor     ecx, ecx; lpThreadAttributes
0x18002519e  call    cs:__imp_CreateThread
0x1800251a4  mov     rsi, rax
0x1800251a7  add     rdi, 50h ; 'P'
0x1800251ab  lea     rax, [rsp+68h+var_30]
0x1800251b0  cmp     rdi, rax
0x1800251b3  jz      short loc_1800251E0
0x1800251b5  mov     rbp, [rdi]
0x1800251b8  lea     rdx, [rbp-1]
0x1800251bc  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800251c0  ja      short loc_1800251DB
0x1800251c2  call    cs:__imp_GetLastError
0x1800251c8  mov     ebx, eax
0x1800251ca  mov     rcx, rbp; hObject
0x1800251cd  call    cs:__imp_CloseHandle
0x1800251d3  mov     ecx, ebx; dwErrCode
0x1800251d5  call    cs:__imp_SetLastError
0x1800251db  mov     [rdi], rsi
0x1800251de  jmp     short loc_1800251F3
0x1800251e0  lea     rax, [rsi-1]
0x1800251e4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800251e8  ja      short loc_1800251F3
0x1800251ea  mov     rcx, rsi; hObject
0x1800251ed  call    cs:__imp_CloseHandle
0x1800251f3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800251f6  mov     rcx, [r14]; hHandle
0x1800251f9  call    cs:__imp_WaitForSingleObject
0x1800251ff  cmp     eax, 102h
0x180025204  jz      short loc_18002521C
0x180025206  xor     eax, eax
0x180025208  mov     rbx, [rsp+68h+arg_10]
0x180025210  add     rsp, 40h
0x180025214  pop     r15
0x180025216  pop     r14
0x180025218  pop     rdi
0x180025219  pop     rsi
0x18002521a  pop     rbp
0x18002521b  retn
0x18002521c  mov     rcx, [rsp+68h]; this
0x180025221  lea     r8, aMincoreTextinp_14; "mincore\\textinput\\dev\\virtualization"...
0x180025228  mov     edx, 9Ch; void *
0x18002522d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180025233  mov     rcx, [rsp+68h]; this
0x180025238  mov     r9d, 8007000Eh; char *
0x18002523e  lea     r8, aMincoreTextinp_14; "mincore\\textinput\\dev\\virtualization"...
0x180025245  mov     edx, 87h; void *
0x18002524a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180025250  mov     r9d, eax; char *
0x180025253  lea     r8, aMincoreTextinp_10; "mincore\\textinput\\dev\\virtualization"...
0x18002525a  mov     edx, 8Fh; void *
0x18002525f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
