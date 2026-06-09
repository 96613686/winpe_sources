# Windows::System::DispatcherQueueStatic::GetForCurrentThread(Windows::System::IDispatcherQueue * *)

- ea: `0x18001df90`
- end: `0x18001e0d5`
- name: `?GetForCurrentThread@DispatcherQueueStatic@System@Windows@@UEAAJPEAPEAUIDispatcherQueue@23@@Z`
- size: `325`
- prototype: `__int64 __fastcall(Windows::System::DispatcherQueueStatic *__hidden this, struct Windows::System::IDispatcherQueue **)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001df58`
- `0x18001df90`
- `0x18001e0dc`
- `0x18009d670`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e0c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001e0c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e095`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e0aa`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e0aa`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x18001e0ca`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x18001e0ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::DispatcherQueueStatic::GetForCurrentThread(
        Windows::System::DispatcherQueueStatic *this,
        struct Windows::System::IDispatcherQueue **a2)
{
  struct Windows::System::DispatcherQueue *v3; // rbx
  __int64 (__fastcall *v4)(struct Windows::System::DispatcherQueue *, GUID *, struct Windows::System::IDispatcherQueue **); // rdi
  int v5; // eax
  struct Windows::System::IDispatcherQueue *v6; // rax
  unsigned int v7; // ebx
  struct Windows::System::IDispatcherQueue *v8; // rcx
  struct Windows::System::DispatcherQueue *v9; // rcx
  HRESULT v11; // eax
  struct Windows::System::IDispatcherQueue *v12; // [rsp+20h] [rbp-48h] BYREF
  struct Windows::System::DispatcherQueue *v13; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF

  v13 = 0;
  v12 = 0;
  if ( a2 )
  {
    *a2 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    if ( Windows::System::DispatcherQueue::GetDispatcherQueueForThread(&v13) )
    {
      v3 = v13;
      v4 = **(__int64 (__fastcall ***)(struct Windows::System::DispatcherQueue *, GUID *, struct Windows::System::IDispatcherQueue **))v13;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
      v5 = v4(v3, &GUID_603e88e4_a338_4ffe_a457_a5cfb9ceb899, &v12);
      if ( v5 < 0 )
        RoFailFastWithErrorContext((unsigned int)v5);
      v6 = v12;
      v12 = 0;
      *a2 = v6;
    }
    v7 = 0;
  }
  else
  {
    string = 0;
    v11 = WindowsCreateStringReference(L"Out parameter (DispatcherQueue) is null", 0x27u, &hstringHeader, &string);
    if ( v11 < 0 )
    {
      RaiseException(v11, 1u, 0, 0);
      __debugbreak();
    }
    v7 = -2147467261;
    RoOriginateError(2147500035LL, string);
  }
  v8 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(struct Windows::System::IDispatcherQueue *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = v13;
  if ( v13 )
  {
    v13 = 0;
    (*(void (__fastcall **)(struct Windows::System::DispatcherQueue *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18001df90  push    rbp
0x18001df92  push    rbx
0x18001df93  push    rsi
0x18001df94  push    rdi
0x18001df95  mov     rbp, rsp
0x18001df98  sub     rsp, 68h
0x18001df9c  mov     rax, cs:__security_cookie
0x18001dfa3  xor     rax, rsp
0x18001dfa6  mov     [rbp+var_18], rax
0x18001dfaa  mov     rsi, rdx
0x18001dfad  mov     [rbp+var_40], 0
0x18001dfb5  mov     [rbp+var_48], 0
0x18001dfbd  test    rdx, rdx
0x18001dfc0  jz      loc_18001E079
0x18001dfc6  mov     qword ptr [rdx], 0
0x18001dfcd  lea     rcx, [rbp+var_40]
0x18001dfd1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dfd6  lea     rcx, [rbp+var_40]; struct Windows::System::DispatcherQueue **
0x18001dfda  call    ?GetDispatcherQueueForThread@DispatcherQueue@System@Windows@@SA_NPEAPEAV123@@Z; Windows::System::DispatcherQueue::GetDispatcherQueueForThread(Windows::System::DispatcherQueue * *)
0x18001dfdf  test    al, al
0x18001dfe1  jz      short loc_18001E024
0x18001dfe3  mov     rbx, [rbp+var_40]
0x18001dfe7  mov     rax, [rbx]
0x18001dfea  mov     rdi, [rax]
0x18001dfed  lea     rcx, [rbp+var_48]
0x18001dff1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dff6  lea     r8, [rbp+var_48]
0x18001dffa  lea     rdx, _GUID_603e88e4_a338_4ffe_a457_a5cfb9ceb899
0x18001e001  mov     rcx, rbx
0x18001e004  mov     rax, rdi
0x18001e007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e00c  nop
0x18001e00d  test    eax, eax
0x18001e00f  js      loc_18001E0C8
0x18001e015  mov     rax, [rbp+var_48]
0x18001e019  mov     [rbp+var_48], 0
0x18001e021  mov     [rsi], rax
0x18001e024  xor     ebx, ebx
0x18001e026  mov     rcx, [rbp+var_48]
0x18001e02a  test    rcx, rcx
0x18001e02d  jz      short loc_18001E044
0x18001e02f  mov     [rbp+var_48], 0
0x18001e037  mov     rax, [rcx]
0x18001e03a  mov     rax, [rax+10h]
0x18001e03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e043  nop
0x18001e044  mov     rcx, [rbp+var_40]
0x18001e048  test    rcx, rcx
0x18001e04b  jz      short loc_18001E062
0x18001e04d  mov     [rbp+var_40], 0
0x18001e055  mov     rdx, [rcx]
0x18001e058  mov     rax, [rdx+10h]
0x18001e05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e061  nop
0x18001e062  mov     eax, ebx
0x18001e064  mov     rcx, [rbp+var_18]
0x18001e068  xor     rcx, rsp; StackCookie
0x18001e06b  call    __security_check_cookie
0x18001e070  add     rsp, 68h
0x18001e074  pop     rdi
0x18001e075  pop     rsi
0x18001e076  pop     rbx
0x18001e077  pop     rbp
0x18001e078  retn
0x18001e079  mov     [rbp+string], 0
0x18001e081  lea     r9, [rbp+string]; string
0x18001e085  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001e089  mov     edx, 27h ; '''; length
0x18001e08e  lea     rcx, sourceString; "Out parameter (DispatcherQueue) is null"
0x18001e095  call    cs:__imp_WindowsCreateStringReference
0x18001e09b  test    eax, eax
0x18001e09d  js      short loc_18001E0B5
0x18001e09f  mov     rdx, [rbp+string]
0x18001e0a3  mov     ebx, 80004003h
0x18001e0a8  mov     ecx, ebx
0x18001e0aa  call    cs:__imp_RoOriginateError
0x18001e0b0  jmp     loc_18001E026
0x18001e0b5  xor     r9d, r9d; lpArguments
0x18001e0b8  xor     r8d, r8d; nNumberOfArguments
0x18001e0bb  lea     edx, [r9+1]; dwExceptionFlags
0x18001e0bf  mov     ecx, eax; dwExceptionCode
0x18001e0c1  call    cs:__imp_RaiseException
0x18001e0c7  int     3; Trap to Debugger
0x18001e0c8  mov     ecx, eax
0x18001e0ca  call    cs:__imp_RoFailFastWithErrorContext
0x18001e0d0  jmp     loc_18001E015
```
