# Microsoft::CoreUI::Messaging::MessageSession::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageSessionPrivate::Dispatcher::AllocateMessage(System::Object *,Microsoft::CoreUI::HENDPOINT,Microsoft::CoreUI::Dispatch::ExternalPriority,uint,CFlat::Ref<bool>)

- ea: `0x1800aedc0`
- end: `0x1800aee2b`
- name: `?AllocateMessage@Dispatcher@_Microsoft_CoreUI_IExportMessageSessionPrivate@InterfaceImplementation$@MessageSession@Messaging@CoreUI@Microsoft@@UEBAPEAXPEAVObject@System@@UHENDPOINT@67@W4ExternalPriority@Dispatch@67@IU?$Ref@_N@CFlat@@@Z`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18003e878`
- `0x18008ae1c`
- `0x1800aedc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aedd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aedd8`

## pseudocode

```c
__int64 __fastcall Microsoft::CoreUI::Messaging::MessageSession::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageSessionPrivate::Dispatcher::AllocateMessage(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        __int64 a6)
{
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx

  CurrentThreadId = GetCurrentThreadId();
  v10 = *(_QWORD *)(a2 + 96);
  if ( CurrentThreadId != *(_DWORD *)(v10 + 176) )
    CFlat::Abandonment::Fail((const char16_t *)v10);
  return Microsoft::CoreUI::Messaging::MessageSession::AllocateMessage(a2, a3, 0, a4, a5, 2, a6);
}

```

## disassembly

```asm
0x1800aedc0  mov     [rsp+arg_0], rbx
0x1800aedc5  mov     [rsp+arg_8], rsi
0x1800aedca  push    rdi
0x1800aedcb  sub     rsp, 40h
0x1800aedcf  mov     esi, r9d
0x1800aedd2  mov     rbx, r8
0x1800aedd5  mov     rdi, rdx
0x1800aedd8  call    cs:__imp_GetCurrentThreadId
0x1800aedde  mov     rcx, [rdi+60h]; char16_t *
0x1800aede2  cmp     eax, [rcx+0B0h]
0x1800aede8  jz      short loc_1800AEDF0
0x1800aedea  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800aedf0  mov     rax, [rsp+48h+arg_28]
0x1800aedf5  mov     r9d, esi
0x1800aedf8  mov     [rsp+48h+var_18], rax
0x1800aedfd  xor     r8d, r8d
0x1800aee00  mov     eax, [rsp+48h+arg_20]
0x1800aee04  mov     rdx, rbx
0x1800aee07  mov     [rsp+48h+var_20], 2
0x1800aee0f  mov     rcx, rdi
0x1800aee12  mov     [rsp+48h+var_28], eax
0x1800aee16  call    ?AllocateMessage@MessageSession@Messaging@CoreUI@Microsoft@@QEAAPEAXUHENDPOINT@34@_NW4ExternalPriority@Dispatch@34@IW4FlushMode@734@U?$Ref@_N@CFlat@@@Z; Microsoft::CoreUI::Messaging::MessageSession::AllocateMessage(Microsoft::CoreUI::HENDPOINT,bool,Microsoft::CoreUI::Dispatch::ExternalPriority,uint,Microsoft::CoreUI::Dispatch::FlushMode,CFlat::Ref<bool>)
0x1800aee1b  mov     rbx, [rsp+48h+arg_0]
0x1800aee20  mov     rsi, [rsp+48h+arg_8]
0x1800aee25  add     rsp, 40h
0x1800aee29  pop     rdi
0x1800aee2a  retn
```
