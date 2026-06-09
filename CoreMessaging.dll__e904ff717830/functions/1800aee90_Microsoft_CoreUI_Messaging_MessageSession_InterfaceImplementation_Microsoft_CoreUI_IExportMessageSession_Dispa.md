# Microsoft::CoreUI::Messaging::MessageSession::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageSession::Dispatcher::CancelSendInPlace(System::Object *,void *)

- ea: `0x1800aee90`
- end: `0x1800aef04`
- name: `?CancelSendInPlace@Dispatcher@_Microsoft_CoreUI_IExportMessageSession@InterfaceImplementation$@MessageSession@Messaging@CoreUI@Microsoft@@UEBAXPEAVObject@System@@PEAX@Z`
- size: `116`
- prototype: `void(Microsoft::CoreUI::Messaging::MessageSession::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageSession::Dispatcher *__hidden this, struct System::Object *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800111dc`
- `0x18007abdc`
- `0x18007df5c`
- `0x18008ae1c`
- `0x18008b6cc`
- `0x1800aee90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aeeb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aeeb9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::CoreUI::Messaging::MessageSession::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageSession::Dispatcher::CancelSendInPlace(
        Microsoft::CoreUI::Messaging::MessageSession::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageSession::Dispatcher *this,
        struct System::Object *a2,
        char *a3)
{
  System::Exception **ArgumentNull; // rax
  DWORD CurrentThreadId; // eax
  void *v7; // rdx
  __int64 v8; // rcx
  System::Exception **ArgumentInvalid; // rax
  char v10; // [rsp+40h] [rbp+18h] BYREF

  if ( !a3 )
  {
    ArgumentNull = (System::Exception **)Microsoft::CoreUI::ValidationException::get_ArgumentNull(&v10);
    System::Exception::Throw$(*ArgumentNull);
  }
  CurrentThreadId = GetCurrentThreadId();
  v8 = *((_QWORD *)a2 + 12);
  if ( CurrentThreadId != *(_DWORD *)(v8 + 176) )
    CFlat::Abandonment::Fail((const char16_t *)v8);
  if ( a3 - 16 != *((char **)a2 + 24) )
  {
    ArgumentInvalid = (System::Exception **)Microsoft::CoreUI::ValidationException::get_ArgumentInvalid(&v10);
    System::Exception::Throw$(*ArgumentInvalid);
  }
  Microsoft::CoreUI::Messaging::MessageSession::CancelMessage(a2, v7);
}

```

## disassembly

```asm
0x1800aee90  mov     [rsp+arg_0], rbx
0x1800aee95  push    rdi
0x1800aee96  sub     rsp, 20h
0x1800aee9a  mov     rdi, r8
0x1800aee9d  mov     rbx, rdx
0x1800aeea0  test    r8, r8
0x1800aeea3  jnz     short loc_1800AEEB9
0x1800aeea5  lea     rcx, [rsp+28h+arg_10]
0x1800aeeaa  call    ?get_ArgumentNull@ValidationException@CoreUI@Microsoft@@SA?AV?$SmartPtr@VValidationException@CoreUI@Microsoft@@@CFlat@@XZ; Microsoft::CoreUI::ValidationException::get_ArgumentNull(void)
0x1800aeeaf  nop
0x1800aeeb0  mov     rcx, [rax]; this
0x1800aeeb3  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
0x1800aeeb8  nop
0x1800aeeb9  call    cs:__imp_GetCurrentThreadId
0x1800aeebf  mov     rcx, [rbx+60h]; char16_t *
0x1800aeec3  cmp     eax, [rcx+0B0h]
0x1800aeec9  jz      short loc_1800AEED1
0x1800aeecb  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800aeed1  lea     rax, [rdi-10h]
0x1800aeed5  cmp     rax, [rbx+0C0h]
0x1800aeedc  jz      short loc_1800AEEF2
0x1800aeede  lea     rcx, [rsp+28h+arg_10]
0x1800aeee3  call    ?get_ArgumentInvalid@ValidationException@CoreUI@Microsoft@@SA?AV?$SmartPtr@VValidationException@CoreUI@Microsoft@@@CFlat@@XZ; Microsoft::CoreUI::ValidationException::get_ArgumentInvalid(void)
0x1800aeee8  nop
0x1800aeee9  mov     rcx, [rax]; this
0x1800aeeec  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
0x1800aeef1  nop
0x1800aeef2  mov     rcx, rbx; this
0x1800aeef5  mov     rbx, [rsp+28h+arg_0]
0x1800aeefa  add     rsp, 20h
0x1800aeefe  pop     rdi
0x1800aeeff  jmp     ?CancelMessage@MessageSession@Messaging@CoreUI@Microsoft@@AEAAXPEAX@Z; Microsoft::CoreUI::Messaging::MessageSession::CancelMessage(void *)
```
