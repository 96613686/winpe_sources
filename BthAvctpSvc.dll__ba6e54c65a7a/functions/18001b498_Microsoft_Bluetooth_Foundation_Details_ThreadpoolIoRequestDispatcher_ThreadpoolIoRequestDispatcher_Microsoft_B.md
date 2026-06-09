# Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::ThreadpoolIoRequestDispatcher(Microsoft::Bluetooth::Foundation::DeviceIoTarget &,void *)

- ea: `0x18001b498`
- end: `0x18001b542`
- name: `??0ThreadpoolIoRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@QEAA@AEAVDeviceIoTarget@234@PEAX@Z`
- size: `170`
- prototype: `char *__fastcall(char *pv, struct Microsoft::Bluetooth::Foundation::DeviceIoTarget *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a99c`

## callees

- `0x18000dca8`
- `0x18001b498`
- `0x18001f62c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001b4da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001b4da`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x18001b501`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x18001b501`

## pseudocode

```c
char *__fastcall Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::ThreadpoolIoRequestDispatcher(
        char *pv,
        struct Microsoft::Bluetooth::Foundation::DeviceIoTarget *a2,
        void *a3)
{
  _QWORD *v4; // rbx
  PTP_IO ThreadpoolIo; // rax
  const char *v6; // r9
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *((_QWORD *)pv + 1) = a2;
  *(_QWORD *)pv = &Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::`vftable';
  *((_QWORD *)pv + 2) = a3;
  v4 = pv + 24;
  *((_QWORD *)pv + 3) = 0;
  ThreadpoolIo = CreateThreadpoolIo(
                   a3,
                   Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::IoCallbackThunk,
                   pv,
                   0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&public: static void wil::details::DestroyThreadPoolIo<1>::Destroy(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::reset(
    v4,
    ThreadpoolIo);
  if ( !*v4 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x581,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\DeviceIoTarget.h",
      v6);
  if ( !SetFileCompletionNotificationModes(*((HANDLE *)pv + 2), 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x585,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\DeviceIoTarget.h",
      v7);
  return pv;
}

```

## disassembly

```asm
0x18001b498  mov     [rsp+arg_8], rbx
0x18001b49d  mov     [rsp+arg_0], rcx
0x18001b4a2  push    rdi
0x18001b4a3  sub     rsp, 20h
0x18001b4a7  mov     rax, r8
0x18001b4aa  mov     rdi, rcx
0x18001b4ad  mov     [rcx+8], rdx
0x18001b4b1  lea     rcx, ??_7ThreadpoolIoRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::Foundation::Details::ThreadpoolIoRequestDispatcher::`vftable'
0x18001b4b8  mov     [rdi], rcx
0x18001b4bb  mov     [rdi+10h], rax
0x18001b4bf  lea     rbx, [rdi+18h]
0x18001b4c3  mov     qword ptr [rbx], 0
0x18001b4ca  xor     r9d, r9d; pcbe
0x18001b4cd  mov     r8, rdi; pv
0x18001b4d0  lea     rdx, ?IoCallbackThunk@ThreadpoolIoRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x18001b4d7  mov     rcx, rax; fl
0x18001b4da  call    cs:__imp_CreateThreadpoolIo
0x18001b4e0  mov     rdx, rax
0x18001b4e3  mov     rcx, rbx
0x18001b4e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolIo@$00@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_IO@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&wil::details::DestroyThreadPoolIo<1>::Destroy(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::reset(_TP_IO *)
0x18001b4eb  cmp     qword ptr [rbx], 0
0x18001b4ef  setz    al
0x18001b4f2  mov     rcx, [rsp+28h]; this
0x18001b4f7  test    al, al
0x18001b4f9  jnz     short loc_18001B530
0x18001b4fb  mov     dl, 1; Flags
0x18001b4fd  mov     rcx, [rdi+10h]; FileHandle
0x18001b501  call    cs:__imp_SetFileCompletionNotificationModes
0x18001b507  mov     rcx, [rsp+28h]; this
0x18001b50c  test    eax, eax
0x18001b50e  jz      short loc_18001B51E
0x18001b510  mov     rax, rdi
0x18001b513  mov     rbx, [rsp+28h+arg_8]
0x18001b518  add     rsp, 20h
0x18001b51c  pop     rdi
0x18001b51d  retn
0x18001b51e  lea     r8, aOnecoreDrivers_19; "onecore\\drivers\\bluetooth\\foundation"...
0x18001b525  mov     edx, 585h; void *
0x18001b52a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001b530  lea     r8, aOnecoreDrivers_19; "onecore\\drivers\\bluetooth\\foundation"...
0x18001b537  mov     edx, 581h; void *
0x18001b53c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
