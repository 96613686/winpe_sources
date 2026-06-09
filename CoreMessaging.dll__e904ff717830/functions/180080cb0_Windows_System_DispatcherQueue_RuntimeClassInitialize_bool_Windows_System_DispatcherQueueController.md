# Windows::System::DispatcherQueue::RuntimeClassInitialize(bool,Windows::System::DispatcherQueueController *)

- ea: `0x180080cb0`
- end: `0x180080e35`
- name: `?RuntimeClassInitialize@DispatcherQueue@System@Windows@@UEAAJ_NPEAVDispatcherQueueController@23@@Z`
- size: `389`
- prototype: `__int64 __fastcall(Windows::System::DispatcherQueue *__hidden this, bool, struct Windows::System::DispatcherQueueController *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001df58`
- `0x18001e0dc`
- `0x18001e760`
- `0x180020da8`
- `0x180080cb0`
- `0x18009d670`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180080e02`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180080e02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180080d60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180080d60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180080dd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180080dd5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180080deb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180080deb`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180080e10`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180080e1d`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180080e2a`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180080e10`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180080e1d`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x180080e2a`

## string_xrefs

- `0x180080dce`: `DispatcherQueue already exists.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::DispatcherQueue::RuntimeClassInitialize(
        Windows::System::DispatcherQueue *this,
        char a2,
        struct Windows::System::DispatcherQueueController *a3)
{
  __int64 v6; // rcx
  int v7; // eax
  int v8; // eax
  __int64 v9; // r8
  int v10; // eax
  unsigned int v11; // ebx
  struct Windows::System::DispatcherQueue *v12; // rcx
  HRESULT v14; // eax
  struct Windows::System::DispatcherQueue *v15; // [rsp+20h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-28h] BYREF

  v15 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  if ( !Windows::System::DispatcherQueue::GetDispatcherQueueForThread(&v15) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 80);
    if ( this == (Windows::System::DispatcherQueue *)-80LL )
    {
      v7 = -2147467261;
    }
    else
    {
      *((_QWORD *)this + 10) = 0;
      LOBYTE(v6) = 1;
      v7 = CoreUISessionCreate(v6, 0, (char *)this + 80);
      if ( v7 >= 0 )
      {
LABEL_4:
        v8 = Microsoft::WRL::ComPtr<IMessageSession>::As<IExportDispatcherQueueInterop>(
               (char *)this + 80,
               (char *)this + 88);
        if ( v8 < 0 )
          RoFailFastWithErrorContext((unsigned int)v8);
        LOBYTE(v9) = a2;
        v10 = (*(__int64 (__fastcall **)(_QWORD, Windows::System::DispatcherQueue *, __int64))(**((_QWORD **)this + 11)
                                                                                             + 24LL))(
                *((_QWORD *)this + 11),
                this,
                v9);
        if ( v10 < 0 )
          RoFailFastWithErrorContext((unsigned int)v10);
        *((_DWORD *)this + 26) = GetCurrentThreadId();
        *((_QWORD *)this + 20) = a3;
        v11 = 0;
        goto LABEL_9;
      }
    }
    RoFailFastWithErrorContext((unsigned int)v7);
    goto LABEL_4;
  }
  string = 0;
  v14 = WindowsCreateStringReference(L"DispatcherQueue already exists.", 0x1Fu, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    RaiseException(v14, 1u, 0, 0);
    __debugbreak();
  }
  v11 = -2147417842;
  RoOriginateError(2147549454LL, string);
LABEL_9:
  v12 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(struct Windows::System::DispatcherQueue *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return v11;
}

```

## disassembly

```asm
0x180080cb0  mov     r11, rsp
0x180080cb3  mov     [r11+18h], rbx
0x180080cb7  mov     [r11+20h], rbp
0x180080cbb  push    rsi
0x180080cbc  push    rdi
0x180080cbd  push    r14
0x180080cbf  sub     rsp, 50h
0x180080cc3  mov     rax, cs:__security_cookie
0x180080cca  xor     rax, rsp
0x180080ccd  mov     [rsp+68h+var_20], rax
0x180080cd2  mov     rbp, r8
0x180080cd5  mov     r14b, dl
0x180080cd8  mov     rdi, rcx
0x180080cdb  mov     qword ptr [r11-48h], 0
0x180080ce3  lea     rcx, [r11-48h]
0x180080ce7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180080cec  lea     rcx, [rsp+68h+var_48]; struct Windows::System::DispatcherQueue **
0x180080cf1  call    ?GetDispatcherQueueForThread@DispatcherQueue@System@Windows@@SA_NPEAPEAV123@@Z; Windows::System::DispatcherQueue::GetDispatcherQueueForThread(Windows::System::DispatcherQueue * *)
0x180080cf6  test    al, al
0x180080cf8  jnz     loc_180080DB6
0x180080cfe  lea     rbx, [rdi+50h]
0x180080d02  mov     rcx, rbx
0x180080d05  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180080d0a  test    rbx, rbx
0x180080d0d  jz      loc_180080E09
0x180080d13  mov     qword ptr [rbx], 0
0x180080d1a  mov     r8, rbx
0x180080d1d  xor     edx, edx
0x180080d1f  mov     cl, 1
0x180080d21  call    ?CoreUISessionCreate@@YAJ_NW4MsgCreateFlags@@PEAPEAUIMessageSession@@@Z; CoreUISessionCreate(bool,MsgCreateFlags,IMessageSession * *)
0x180080d26  test    eax, eax
0x180080d28  js      loc_180080E0E
0x180080d2e  lea     rdx, [rdi+58h]
0x180080d32  mov     rcx, rbx
0x180080d35  call    ??$As@UIExportDispatcherQueueInterop@@@?$ComPtr@UIMessageSession@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIExportDispatcherQueueInterop@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IMessageSession>::As<IExportDispatcherQueueInterop>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IExportDispatcherQueueInterop>>)
0x180080d3a  test    eax, eax
0x180080d3c  js      loc_180080E1B
0x180080d42  mov     rcx, [rdi+58h]
0x180080d46  mov     rax, [rcx]
0x180080d49  mov     r8b, r14b
0x180080d4c  mov     rdx, rdi
0x180080d4f  mov     rax, [rax+18h]
0x180080d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080d58  test    eax, eax
0x180080d5a  js      loc_180080E28
0x180080d60  call    cs:__imp_GetCurrentThreadId
0x180080d66  mov     [rdi+68h], eax
0x180080d69  mov     [rdi+0A0h], rbp
0x180080d70  xor     ebx, ebx
0x180080d72  mov     rcx, [rsp+68h+var_48]
0x180080d77  test    rcx, rcx
0x180080d7a  jz      short loc_180080D92
0x180080d7c  mov     [rsp+68h+var_48], 0
0x180080d85  mov     rdx, [rcx]
0x180080d88  mov     rax, [rdx+10h]
0x180080d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080d91  nop
0x180080d92  mov     eax, ebx
0x180080d94  mov     rcx, [rsp+68h+var_20]
0x180080d99  xor     rcx, rsp; StackCookie
0x180080d9c  call    __security_check_cookie
0x180080da1  lea     r11, [rsp+68h+var_18]
0x180080da6  mov     rbx, [r11+30h]
0x180080daa  mov     rbp, [r11+38h]
0x180080dae  mov     rsp, r11
0x180080db1  pop     r14
0x180080db3  pop     rdi
0x180080db4  pop     rsi
0x180080db5  retn
0x180080db6  mov     [rsp+68h+string], 0
0x180080dbf  lea     r9, [rsp+68h+string]; string
0x180080dc4  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x180080dc9  mov     edx, 1Fh; length
0x180080dce  lea     rcx, aDispatcherqueu; "DispatcherQueue already exists."
0x180080dd5  call    cs:__imp_WindowsCreateStringReference
0x180080ddb  test    eax, eax
0x180080ddd  js      short loc_180080DF6
0x180080ddf  mov     rdx, [rsp+68h+string]
0x180080de4  mov     ebx, 8001010Eh
0x180080de9  mov     ecx, ebx
0x180080deb  call    cs:__imp_RoOriginateError
0x180080df1  jmp     loc_180080D72
0x180080df6  xor     r9d, r9d; lpArguments
0x180080df9  xor     r8d, r8d; nNumberOfArguments
0x180080dfc  lea     edx, [r9+1]; dwExceptionFlags
0x180080e00  mov     ecx, eax; dwExceptionCode
0x180080e02  call    cs:__imp_RaiseException
0x180080e08  int     3; Trap to Debugger
0x180080e09  mov     eax, 80004003h
0x180080e0e  mov     ecx, eax
0x180080e10  call    cs:__imp_RoFailFastWithErrorContext
0x180080e16  jmp     loc_180080D2E
0x180080e1b  mov     ecx, eax
0x180080e1d  call    cs:__imp_RoFailFastWithErrorContext
0x180080e23  jmp     loc_180080D42
0x180080e28  mov     ecx, eax
0x180080e2a  call    cs:__imp_RoFailFastWithErrorContext
0x180080e30  jmp     loc_180080D60
```
