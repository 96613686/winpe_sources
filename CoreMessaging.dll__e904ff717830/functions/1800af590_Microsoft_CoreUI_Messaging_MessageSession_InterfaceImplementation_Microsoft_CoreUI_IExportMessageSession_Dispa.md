# Microsoft::CoreUI::Messaging::MessageSession::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageSession::Dispatcher::SendInPlace(System::Object *,Microsoft::CoreUI::HENDPOINT,Microsoft::CoreUI::Dispatch::ExternalPriority,uint)

- ea: `0x1800af590`
- end: `0x1800af61c`
- name: `?SendInPlace@Dispatcher@_Microsoft_CoreUI_IExportMessageSession@InterfaceImplementation$@MessageSession@Messaging@CoreUI@Microsoft@@UEBAPEAXPEAVObject@System@@UHENDPOINT@67@W4ExternalPriority@Dispatch@67@I@Z`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800111dc`
- `0x18003e878`
- `0x180079b3c`
- `0x18008ae1c`
- `0x1800af590`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800af5c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800af5c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::CoreUI::Messaging::MessageSession::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageSession::Dispatcher::SendInPlace(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5)
{
  int v6; // ebx
  System::Exception **InvalidDestination; // rax
  DWORD CurrentThreadId; // eax
  int v10; // r8d
  __int64 v11; // rcx
  _BYTE v13[24]; // [rsp+40h] [rbp-18h] BYREF
  char v14; // [rsp+70h] [rbp+18h] BYREF

  v6 = a3;
  if ( !a3 )
  {
    InvalidDestination = (System::Exception **)Microsoft::CoreUI::Messaging::MessagingValidationException::get_InvalidDestination(v13);
    System::Exception::Throw$(*InvalidDestination);
  }
  CurrentThreadId = GetCurrentThreadId();
  v11 = *(_QWORD *)(a2 + 96);
  if ( CurrentThreadId != *(_DWORD *)(v11 + 176) )
    CFlat::Abandonment::Fail((const char16_t *)v11);
  v14 = 0;
  LOBYTE(v10) = 1;
  return Microsoft::CoreUI::Messaging::MessageSession::AllocateMessage(a2, v6, v10, a4, a5, 1, (__int64)&v14);
}

```

## disassembly

```asm
0x1800af590  mov     [rsp+arg_0], rbx
0x1800af595  mov     [rsp+arg_8], rsi
0x1800af59a  push    rdi
0x1800af59b  sub     rsp, 50h
0x1800af59f  mov     esi, r9d
0x1800af5a2  mov     rbx, r8
0x1800af5a5  mov     rdi, rdx
0x1800af5a8  test    r8, r8
0x1800af5ab  jnz     short loc_1800AF5C1
0x1800af5ad  lea     rcx, [rsp+58h+var_18]
0x1800af5b2  call    ?get_InvalidDestination@MessagingValidationException@Messaging@CoreUI@Microsoft@@SA?AV?$SmartPtr@VException@System@@@CFlat@@XZ; Microsoft::CoreUI::Messaging::MessagingValidationException::get_InvalidDestination(void)
0x1800af5b7  nop
0x1800af5b8  mov     rcx, [rax]; this
0x1800af5bb  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
0x1800af5c0  nop
0x1800af5c1  call    cs:__imp_GetCurrentThreadId
0x1800af5c7  mov     rcx, [rdi+60h]; char16_t *
0x1800af5cb  cmp     eax, [rcx+0B0h]
0x1800af5d1  jz      short loc_1800AF5D9
0x1800af5d3  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800af5d9  mov     [rsp+58h+arg_10], 0
0x1800af5de  lea     rax, [rsp+58h+arg_10]
0x1800af5e3  mov     [rsp+58h+var_28], rax
0x1800af5e8  mov     [rsp+58h+var_30], 1
0x1800af5f0  mov     eax, [rsp+58h+arg_20]
0x1800af5f7  mov     [rsp+58h+var_38], eax
0x1800af5fb  mov     r9d, esi
0x1800af5fe  mov     r8b, 1
0x1800af601  mov     rdx, rbx
0x1800af604  mov     rcx, rdi
0x1800af607  call    ?AllocateMessage@MessageSession@Messaging@CoreUI@Microsoft@@QEAAPEAXUHENDPOINT@34@_NW4ExternalPriority@Dispatch@34@IW4FlushMode@734@U?$Ref@_N@CFlat@@@Z; Microsoft::CoreUI::Messaging::MessageSession::AllocateMessage(Microsoft::CoreUI::HENDPOINT,bool,Microsoft::CoreUI::Dispatch::ExternalPriority,uint,Microsoft::CoreUI::Dispatch::FlushMode,CFlat::Ref<bool>)
0x1800af60c  mov     rbx, [rsp+58h+arg_0]
0x1800af611  mov     rsi, [rsp+58h+arg_8]
0x1800af616  add     rsp, 50h
0x1800af61a  pop     rdi
0x1800af61b  retn
```
