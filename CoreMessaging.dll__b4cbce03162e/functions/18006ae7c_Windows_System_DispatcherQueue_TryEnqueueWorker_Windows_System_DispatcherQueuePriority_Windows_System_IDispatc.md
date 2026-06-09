# Windows::System::DispatcherQueue::TryEnqueueWorker(Windows::System::DispatcherQueuePriority,Windows::System::IDispatcherQueueHandler *,uchar *)

- ea: `0x18006ae7c`
- end: `0x18006b165`
- name: `?TryEnqueueWorker@DispatcherQueue@System@Windows@@AEAAJW4DispatcherQueuePriority@23@PEAUIDispatcherQueueHandler@23@PEAE@Z`
- size: `745`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006ae50`
- `0x18006ae70`

## callees

- `0x18001df58`
- `0x18006ae7c`
- `0x180086130`
- `0x18009a7e8`
- `0x18009d670`
- `0x1800a2108`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006af21`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006af21`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006af9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006b001`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006af9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006b001`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006b081`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006b081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006b053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006b053`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006b068`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006b0b5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006b0fb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006b068`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006b0b5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006b0fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::System::DispatcherQueue::TryEnqueueWorker(
        __int64 a1,
        int a2,
        int (__fastcall ***a3)(_QWORD, GUID *, _QWORD *),
        _BYTE *a4)
{
  int (__fastcall *v8)(_QWORD, GUID *, _QWORD *); // rbx
  unsigned int v9; // esi
  int v10; // eax
  __int64 v11; // rcx
  HRESULT v13; // eax
  unsigned int v14; // ebx
  int v15; // [rsp+20h] [rbp-39h]
  _QWORD v16[3]; // [rsp+48h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  HSTRING string; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a4 = 0;
  if ( !a3 )
  {
    string = 0;
    v13 = WindowsCreateStringReference(L"handler callback parameter is null", 0x22u, &hstringHeader, &string);
    if ( v13 >= 0 )
    {
      v14 = -2147467261;
      RoOriginateError(2147500035LL, string);
      return v14;
    }
    RaiseException(v13, 1u, 0, 0);
    goto LABEL_23;
  }
  v16[0] = 0;
  v16[1] = a3;
  ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*a3)[1])(a3);
  v8 = **a3;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16);
  if ( v8(a3, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90, v16) < 0 )
  {
LABEL_23:
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"IDispatcherQueueHandler must be agile.",
      0x27u,
      0x26u);
    v14 = -2147483620;
    RoOriginateError(2147483676LL, string);
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*a3)[2])(a3);
LABEL_25:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16);
    return v14;
  }
  if ( a2 == -10 )
  {
    v9 = 1;
    goto LABEL_6;
  }
  if ( a2 )
  {
    if ( a2 == 10 )
    {
      v9 = 4;
      goto LABEL_6;
    }
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Invalid DispatcherQueuePriority.",
      0x21u,
      0x20u);
    v14 = -2147024809;
    RoOriginateError(2147942487LL, string);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C0,
      (unsigned int)"mincore\\coreui\\dev\\dispatcherqueue\\wrtdispatcherqueue.cpp",
      (const char *)0x80070057LL,
      v15);
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*a3)[2])(a3);
    goto LABEL_25;
  }
  v9 = 3;
LABEL_6:
  AcquireSRWLockShared((PSRWLOCK)(a1 + 96));
  v16[2] = a1 + 96;
  if ( *(_DWORD *)(a1 + 176) == 5 )
  {
    if ( a1 != -96 )
      ReleaseSRWLockShared((PSRWLOCK)(a1 + 96));
  }
  else
  {
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*a3)[1])(a3);
    LOBYTE(v15) = *(_BYTE *)(a1 + 180);
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(void *), int (__fastcall ***)(_QWORD, GUID *, _QWORD *), _QWORD))(**(_QWORD **)(a1 + 88) + 40LL))(
            *(_QWORD *)(a1 + 88),
            Windows::System::DispatcherQueue::DeferInvokeCallback,
            a3,
            v9);
    if ( v10 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x3F1,
        (unsigned int)"mincore\\coreui\\dev\\dispatcherqueue\\wrtdispatcherqueue.cpp",
        (const char *)(unsigned int)v10,
        v15);
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*a3)[2])(a3);
    *a4 = 0;
    if ( a1 != -96 )
      ReleaseSRWLockShared((PSRWLOCK)(a1 + 96));
  }
  ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*a3)[2])(a3);
  v11 = v16[0];
  if ( v16[0] )
  {
    v16[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return 0;
}

```

## disassembly

```asm
0x18006ae7c  mov     [rsp-8+arg_8], rbx
0x18006ae81  push    rbp
0x18006ae82  push    rsi
0x18006ae83  push    rdi
0x18006ae84  push    r14
0x18006ae86  push    r15
0x18006ae88  lea     rbp, [rsp-37h]
0x18006ae8d  sub     rsp, 90h
0x18006ae94  mov     rax, cs:__security_cookie
0x18006ae9b  xor     rax, rsp
0x18006ae9e  mov     [rbp+57h+var_30], rax
0x18006aea2  mov     r15, r9
0x18006aea5  mov     rdi, r8
0x18006aea8  mov     esi, edx
0x18006aeaa  mov     r14, rcx
0x18006aead  mov     byte ptr [r9], 0
0x18006aeb1  test    r8, r8
0x18006aeb4  jz      loc_18006B037
0x18006aeba  mov     [rbp+57h+var_68], 0
0x18006aec2  mov     [rbp+57h+var_60], r8
0x18006aec6  mov     rax, [r8]
0x18006aec9  mov     rcx, r8
0x18006aecc  mov     rax, [rax+8]
0x18006aed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aed5  nop
0x18006aed6  mov     rax, [rdi]
0x18006aed9  mov     rbx, [rax]
0x18006aedc  lea     rcx, [rbp+57h+var_68]
0x18006aee0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006aee5  lea     r8, [rbp+57h+var_68]
0x18006aee9  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x18006aef0  mov     rcx, rdi
0x18006aef3  mov     rax, rbx
0x18006aef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aefb  nop
0x18006aefc  test    eax, eax
0x18006aefe  js      loc_18006B088
0x18006af04  cmp     esi, 0FFFFFFF6h
0x18006af07  jz      loc_18006B01A
0x18006af0d  test    esi, esi
0x18006af0f  jnz     loc_18006B024
0x18006af15  mov     esi, 3
0x18006af1a  lea     rbx, [r14+60h]
0x18006af1e  mov     rcx, rbx; SRWLock
0x18006af21  call    cs:__imp_AcquireSRWLockShared
0x18006af27  mov     [rbp+57h+var_58], rbx
0x18006af2b  cmp     dword ptr [r14+0B0h], 5
0x18006af33  jz      loc_18006AFF9
0x18006af39  mov     rax, [rdi]
0x18006af3c  mov     rcx, rdi
0x18006af3f  mov     rax, [rax+8]
0x18006af43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af48  mov     [rbp+57h+var_70], 0
0x18006af4c  mov     rcx, [r14+58h]
0x18006af50  mov     rax, [rcx]
0x18006af53  lea     rdx, [rbp+57h+var_70]
0x18006af57  mov     [rsp+0B0h+var_88], rdx
0x18006af5c  mov     dl, [r14+0B4h]
0x18006af63  mov     byte ptr [rsp+0B0h+var_90], dl; int
0x18006af67  mov     r9d, esi
0x18006af6a  mov     r8, rdi
0x18006af6d  lea     rdx, ?DeferInvokeCallback@DispatcherQueue@System@Windows@@CAJPEAX@Z; Windows::System::DispatcherQueue::DeferInvokeCallback(void *)
0x18006af74  mov     rax, [rax+28h]
0x18006af78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af7d  mov     rcx, [rbp+5Fh]; this
0x18006af81  test    eax, eax
0x18006af83  js      loc_18006B138
0x18006af89  mov     al, [rbp+57h+var_70]
0x18006af8c  test    al, al
0x18006af8e  jz      loc_18006B14D
0x18006af94  mov     [r15], al
0x18006af97  test    rbx, rbx
0x18006af9a  jz      short loc_18006AFA6
0x18006af9c  mov     rcx, rbx; SRWLock
0x18006af9f  call    cs:__imp_ReleaseSRWLockShared
0x18006afa5  nop
0x18006afa6  mov     rax, [rdi]
0x18006afa9  mov     rcx, rdi
0x18006afac  mov     rax, [rax+10h]
0x18006afb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afb5  nop
0x18006afb6  mov     rcx, [rbp+57h+var_68]
0x18006afba  test    rcx, rcx
0x18006afbd  jz      short loc_18006AFD4
0x18006afbf  mov     [rbp+57h+var_68], 0
0x18006afc7  mov     rax, [rcx]
0x18006afca  mov     rax, [rax+10h]
0x18006afce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afd3  nop
0x18006afd4  xor     eax, eax
0x18006afd6  mov     rcx, [rbp+57h+var_30]
0x18006afda  xor     rcx, rsp; StackCookie
0x18006afdd  call    __security_check_cookie
0x18006afe2  mov     rbx, [rsp+0B0h+arg_8]
0x18006afea  add     rsp, 90h
0x18006aff1  pop     r15
0x18006aff3  pop     r14
0x18006aff5  pop     rdi
0x18006aff6  pop     rsi
0x18006aff7  pop     rbp
0x18006aff8  retn
0x18006aff9  test    rbx, rbx
0x18006affc  jz      short loc_18006B008
0x18006affe  mov     rcx, rbx; SRWLock
0x18006b001  call    cs:__imp_ReleaseSRWLockShared
0x18006b007  nop
0x18006b008  mov     rax, [rdi]
0x18006b00b  mov     rcx, rdi
0x18006b00e  mov     rax, [rax+10h]
0x18006b012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b017  nop
0x18006b018  jmp     short loc_18006AFB6
0x18006b01a  mov     esi, 1
0x18006b01f  jmp     loc_18006AF1A
0x18006b024  cmp     esi, 0Ah
0x18006b027  jnz     loc_18006B0CE
0x18006b02d  mov     esi, 4
0x18006b032  jmp     loc_18006AF1A
0x18006b037  mov     [rbp+57h+string], 0
0x18006b03f  lea     r9, [rbp+57h+string]; string
0x18006b043  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006b047  mov     edx, 22h ; '"'; length
0x18006b04c  lea     rcx, aHandlerCallbac; "handler callback parameter is null"
0x18006b053  call    cs:__imp_WindowsCreateStringReference
0x18006b059  test    eax, eax
0x18006b05b  js      short loc_18006B075
0x18006b05d  mov     rdx, [rbp+57h+string]
0x18006b061  mov     ebx, 80004003h
0x18006b066  mov     ecx, ebx
0x18006b068  call    cs:__imp_RoOriginateError
0x18006b06e  mov     eax, ebx
0x18006b070  jmp     loc_18006AFD6
0x18006b075  xor     r9d, r9d; lpArguments
0x18006b078  xor     r8d, r8d; nNumberOfArguments
0x18006b07b  lea     edx, [r9+1]; dwExceptionFlags
0x18006b07f  mov     ecx, eax; dwExceptionCode
0x18006b081  call    cs:__imp_RaiseException
0x18006b087  nop
0x18006b088  mov     [rbp+57h+string], 0
0x18006b090  mov     r9d, 26h ; '&'; unsigned int
0x18006b096  lea     r8d, [r9+1]; unsigned int
0x18006b09a  lea     rdx, aIdispatcherque_0; "IDispatcherQueueHandler must be agile."
0x18006b0a1  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18006b0a5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x18006b0aa  mov     rdx, [rbp+57h+string]
0x18006b0ae  mov     ebx, 8000001Ch
0x18006b0b3  mov     ecx, ebx
0x18006b0b5  call    cs:__imp_RoOriginateError
0x18006b0bb  nop
0x18006b0bc  mov     rax, [rdi]
0x18006b0bf  mov     rcx, rdi
0x18006b0c2  mov     rax, [rax+10h]
0x18006b0c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b0cb  nop
0x18006b0cc  jmp     short loc_18006B12A
0x18006b0ce  mov     [rbp+57h+string], 0
0x18006b0d6  mov     r9d, 20h ; ' '; unsigned int
0x18006b0dc  lea     r8d, [r9+1]; unsigned int
0x18006b0e0  lea     rdx, aInvalidDispatc; "Invalid DispatcherQueuePriority."
0x18006b0e7  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18006b0eb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x18006b0f0  mov     rdx, [rbp+57h+string]
0x18006b0f4  mov     ebx, 80070057h
0x18006b0f9  mov     ecx, ebx
0x18006b0fb  call    cs:__imp_RoOriginateError
0x18006b101  mov     rcx, [rbp+5Fh]; this
0x18006b105  mov     r9d, ebx; char *
0x18006b108  lea     r8, aMincoreCoreuiD_2; "mincore\\coreui\\dev\\dispatcherqueue\\"...
0x18006b10f  mov     edx, 3C0h; void *
0x18006b114  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b119  nop
0x18006b11a  mov     rcx, [rdi]
0x18006b11d  mov     rax, [rcx+10h]
0x18006b121  mov     rcx, rdi
0x18006b124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b129  nop
0x18006b12a  lea     rcx, [rbp+57h+var_68]
0x18006b12e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006b133  jmp     loc_18006B06E
0x18006b138  mov     r9d, eax; char *
0x18006b13b  lea     r8, aMincoreCoreuiD_2; "mincore\\coreui\\dev\\dispatcherqueue\\"...
0x18006b142  mov     edx, 3F1h; void *
0x18006b147  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18006b14d  mov     rax, [rdi]
0x18006b150  mov     rcx, rdi
0x18006b153  mov     rax, [rax+10h]
0x18006b157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b15c  mov     al, [rbp+57h+var_70]
0x18006b15f  jmp     loc_18006AF94
```
