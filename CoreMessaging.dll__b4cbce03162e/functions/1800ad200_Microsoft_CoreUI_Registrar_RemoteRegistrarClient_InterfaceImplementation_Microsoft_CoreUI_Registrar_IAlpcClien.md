# Microsoft::CoreUI::Registrar::RemoteRegistrarClient::InterfaceImplementation$::_Microsoft_CoreUI_Registrar_IAlpcClientHost::Dispatcher::OnServerDisconnected(System::Object *)

- ea: `0x1800ad200`
- end: `0x1800ad236`
- name: `?OnServerDisconnected@Dispatcher@_Microsoft_CoreUI_Registrar_IAlpcClientHost@InterfaceImplementation$@RemoteRegistrarClient@Registrar@CoreUI@Microsoft@@UEBAXPEAVObject@System@@@Z`
- size: `54`
- prototype: `void __fastcall(Microsoft::CoreUI::Registrar::RemoteRegistrarClient::InterfaceImplementation$::_Microsoft_CoreUI_Registrar_IAlpcClientHost::Dispatcher *__hidden this, struct System::Object *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1800036a0`
- `0x18004f1ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800ad221`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800ad221`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ad212`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ad212`

## pseudocode

```c
void __fastcall Microsoft::CoreUI::Registrar::RemoteRegistrarClient::InterfaceImplementation$::_Microsoft_CoreUI_Registrar_IAlpcClientHost::Dispatcher::OnServerDisconnected(
        Microsoft::CoreUI::Registrar::RemoteRegistrarClient::InterfaceImplementation$::_Microsoft_CoreUI_Registrar_IAlpcClientHost::Dispatcher *this,
        struct System::Object *a2)
{
  HANDLE CurrentThread; // rax
  char v3; // [rsp+38h] [rbp+10h] BYREF

  CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoopBridge>::Copy((char *)a2 + 32, &v3);
  CurrentThread = GetCurrentThread();
  WaitForSingleObjectEx(CurrentThread, 0xFFFFFFFF, 0);
  CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>::~SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>(&v3);
}

```

## disassembly

```asm
0x1800ad200  sub     rsp, 28h
0x1800ad204  lea     rcx, [rdx+20h]
0x1800ad208  lea     rdx, [rsp+28h+arg_8]
0x1800ad20d  call    ?Copy@?$SmartPtr@VEventLoopBridge@Dispatch@CoreUI@Microsoft@@@CFlat@@QEBA?AV12@XZ; CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoopBridge>::Copy(void)
0x1800ad212  call    cs:__imp_GetCurrentThread
0x1800ad218  xor     r8d, r8d; bAlertable
0x1800ad21b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800ad21e  mov     rcx, rax; hHandle
0x1800ad221  call    cs:__imp_WaitForSingleObjectEx
0x1800ad227  lea     rcx, [rsp+28h+arg_8]
0x1800ad22c  call    ??1?$SmartPtr@VEventLoop@Dispatch@CoreUI@Microsoft@@@CFlat@@QEAA@XZ; CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>::~SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>(void)
0x1800ad231  add     rsp, 28h
0x1800ad235  retn
```
