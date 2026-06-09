# ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_

- ea: `0x140050870`
- end: `0x1400509d9`
- name: `ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9___`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14005ad28`

## callees

- `0x14000abf4`
- `0x14001b794`
- `0x1400272a4`
- `0x140050870`
- `0x140050e48`
- `0x140050e88`
- `0x14006886c`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x1400508dc`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400508dc`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400509b0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400509b0`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400508a5`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400508a5`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140050968`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140050968`
- `ntoskrnl!ExAllocatePool2` at `0x140050911`
- `ntoskrnl!ExAllocatePool2` at `0x140050911`

## pseudocode

```c
__int64 __fastcall ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_(__int64 a1, _QWORD *a2)
{
  struct _IO_REMOVE_LOCK *v2; // rbp
  NTSTATUS v5; // ebx
  struct _DEVICE_OBJECT *m_controlDevice; // rcx
  PIO_WORKITEM WorkItem; // rax
  struct _IO_WORKITEM *v8; // rbx
  _QWORD *Pool2; // rax
  PIO_WORKITEM IoWorkItem; // [rsp+60h] [rbp+18h] BYREF
  __int64 v12; // [rsp+68h] [rbp+20h] BYREF

  v2 = (struct _IO_REMOVE_LOCK *)(a1 + 56);
  v5 = IoAcquireRemoveLockEx(
         (PIO_REMOVE_LOCK)(a1 + 56),
         ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9____::_2_::Thunk::Invoke,
         "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\devext.h",
         0x28Bu,
         0x20u);
  if ( v5 >= 0 )
  {
    IoWorkItem = 0;
    if ( (unsigned int)Feature_59215879__private_IsEnabledDeviceUsageNoInline() )
      m_controlDevice = Driver::GetInstance()->m_controlDevice;
    else
      m_controlDevice = *(struct _DEVICE_OBJECT **)(a1 + 8);
    WorkItem = IoAllocateWorkItem(m_controlDevice);
    wil::details::unique_storage<wil::details::resource_policy<_IO_WORKITEM *,void (*)(_IO_WORKITEM *),&void IoFreeWorkItem(_IO_WORKITEM *),wistd::integral_constant<unsigned __int64,1>,_IO_WORKITEM *,_IO_WORKITEM *,0,std::nullptr_t>>::reset(
      &IoWorkItem,
      WorkItem);
    v8 = IoWorkItem;
    if ( IoWorkItem )
    {
      Pool2 = (_QWORD *)ExAllocatePool2(64, 24, 1346917442);
      v12 = 0;
      if ( Pool2 )
      {
        *Pool2 = a1;
        Pool2[1] = *a2;
        Pool2[2] = a2[1];
        a2[1] = 0;
        *a2 = 0;
        IoWorkItem = 0;
        IoQueueWorkItemEx(
          v8,
          ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9____::_2_::Thunk::Invoke,
          DelayedWorkQueue,
          Pool2);
        utl::unique_ptr__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9____::_2_::WorkItemContext_utl::default_delete__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9____::_2_::WorkItemContext___::_unique_ptr__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9____::_2_::WorkItemContext_utl::default_delete__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9____::_2_::WorkItemContext___(&v12);
        wil::details::unique_storage<wil::details::resource_policy<_IO_WORKITEM *,void (*)(_IO_WORKITEM *),&void IoFreeWorkItem(_IO_WORKITEM *),wistd::integral_constant<unsigned __int64,1>,_IO_WORKITEM *,_IO_WORKITEM *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_IO_WORKITEM *,void (*)(_IO_WORKITEM *),&void IoFreeWorkItem(_IO_WORKITEM *),wistd::integral_constant<unsigned __int64,1>,_IO_WORKITEM *,_IO_WORKITEM *,0,std::nullptr_t>>(&IoWorkItem);
        v5 = 0;
        goto LABEL_10;
      }
      utl::unique_ptr__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9____::_2_::WorkItemContext_utl::default_delete__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9____::_2_::WorkItemContext___::_unique_ptr__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9____::_2_::WorkItemContext_utl::default_delete__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9____::_2_::WorkItemContext___(&v12);
    }
    wil::details::unique_storage<wil::details::resource_policy<_IO_WORKITEM *,void (*)(_IO_WORKITEM *),&void IoFreeWorkItem(_IO_WORKITEM *),wistd::integral_constant<unsigned __int64,1>,_IO_WORKITEM *,_IO_WORKITEM *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_IO_WORKITEM *,void (*)(_IO_WORKITEM *),&void IoFreeWorkItem(_IO_WORKITEM *),wistd::integral_constant<unsigned __int64,1>,_IO_WORKITEM *,_IO_WORKITEM *,0,std::nullptr_t>>(&IoWorkItem);
    IoReleaseRemoveLockEx(v2, ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9____::_2_::Thunk::Invoke, 0x20u);
    v5 = -1073741670;
  }
LABEL_10:
  _Reset___RefObjReference_UREAD_CONNECTED_RSSI_CONTEXT___0A__M__T0A__M__T0A___QEAAXPEAUREAD_CONNECTED_RSSI_CONTEXT__PEBX_Z(a2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140050870  mov     [rsp+arg_0], rbx
0x140050875  push    rbp
0x140050876  push    rsi
0x140050877  push    rdi
0x140050878  sub     rsp, 30h
0x14005087c  lea     rbp, [rcx+38h]
0x140050880  mov     [rsp+48h+RemlockSize], 20h ; ' '; RemlockSize
0x140050888  mov     rsi, rdx
0x14005088b  lea     r8, aOnecoreDrivers_60; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140050892  mov     rdi, rcx
0x140050895  lea     rdx, _ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_______2___Thunk__Invoke; Tag
0x14005089c  mov     rcx, rbp; RemoveLock
0x14005089f  mov     r9d, 28Bh; Line
0x1400508a5  call    cs:__imp_IoAcquireRemoveLockEx
0x1400508ac  nop     dword ptr [rax+rax+00h]
0x1400508b1  mov     ebx, eax
0x1400508b3  test    eax, eax
0x1400508b5  js      loc_1400509C1
0x1400508bb  mov     [rsp+48h+IoWorkItem], 0
0x1400508c4  call    Feature_59215879__private_IsEnabledDeviceUsageNoInline
0x1400508c9  test    eax, eax
0x1400508cb  jz      short loc_1400508D8
0x1400508cd  call    ?GetInstance@Driver@@SAAEAV1@XZ; Driver::GetInstance(void)
0x1400508d2  mov     rcx, [rax+10h]
0x1400508d6  jmp     short loc_1400508DC
0x1400508d8  mov     rcx, [rdi+8]; DeviceObject
0x1400508dc  call    cs:__imp_IoAllocateWorkItem
0x1400508e3  nop     dword ptr [rax+rax+00h]
0x1400508e8  mov     rdx, rax
0x1400508eb  lea     rcx, [rsp+48h+IoWorkItem]
0x1400508f0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_IO_WORKITEM@@P6AXPEAU1@@Z$1?IoFreeWorkItem@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_IO_WORKITEM@@@Z; wil::details::unique_storage<wil::details::resource_policy<_IO_WORKITEM *,void (*)(_IO_WORKITEM *),&IoFreeWorkItem(_IO_WORKITEM *),wistd::integral_constant<unsigned __int64,1>,_IO_WORKITEM *,_IO_WORKITEM *,0,std::nullptr_t>>::reset(_IO_WORKITEM *)
0x1400508f5  mov     rbx, [rsp+48h+IoWorkItem]
0x1400508fa  test    rbx, rbx
0x1400508fd  jz      loc_140050996
0x140050903  mov     edx, 18h
0x140050908  mov     r8d, 50485442h
0x14005090e  lea     ecx, [rdx+28h]
0x140050911  call    cs:__imp_ExAllocatePool2
0x140050918  nop     dword ptr [rax+rax+00h]
0x14005091d  mov     [rsp+48h+arg_18], 0
0x140050926  test    rax, rax
0x140050929  jz      short loc_14005098C
0x14005092b  mov     [rax], rdi
0x14005092e  mov     r9, rax; Context
0x140050931  mov     rdx, [rsi]
0x140050934  mov     r8d, 1; QueueType
0x14005093a  mov     [rax+8], rdx
0x14005093e  mov     rcx, rbx; IoWorkItem
0x140050941  mov     rdx, [rsi+8]
0x140050945  mov     [rax+10h], rdx
0x140050949  lea     rdx, _ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_______2___Thunk__Invoke; WorkerRoutine
0x140050950  mov     qword ptr [rsi+8], 0
0x140050958  mov     qword ptr [rsi], 0
0x14005095f  mov     [rsp+48h+IoWorkItem], 0
0x140050968  call    cs:__imp_IoQueueWorkItemEx
0x14005096f  nop     dword ptr [rax+rax+00h]
0x140050974  lea     rcx, [rsp+48h+arg_18]
0x140050979  call    utl__unique_ptr__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_______2___WorkItemContext_utl__default_delete__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_______2___WorkItemContext______unique_ptr__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_______2___WorkItemContext_utl__default_delete__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_______2___WorkItemContext___
0x14005097e  lea     rcx, [rsp+48h+IoWorkItem]
0x140050983  call    ??1?$unique_storage@U?$resource_policy@PEAU_IO_WORKITEM@@P6AXPEAU1@@Z$1?IoFreeWorkItem@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_IO_WORKITEM *,void (*)(_IO_WORKITEM *),&IoFreeWorkItem(_IO_WORKITEM *),wistd::integral_constant<unsigned __int64,1>,_IO_WORKITEM *,_IO_WORKITEM *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_IO_WORKITEM *,void (*)(_IO_WORKITEM *),&IoFreeWorkItem(_IO_WORKITEM *),wistd::integral_constant<unsigned __int64,1>,_IO_WORKITEM *,_IO_WORKITEM *,0,std::nullptr_t>>(void)
0x140050988  xor     ebx, ebx
0x14005098a  jmp     short loc_1400509C1
0x14005098c  lea     rcx, [rsp+48h+arg_18]
0x140050991  call    utl__unique_ptr__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_______2___WorkItemContext_utl__default_delete__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_______2___WorkItemContext______unique_ptr__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_______2___WorkItemContext_utl__default_delete__ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_______2___WorkItemContext___
0x140050996  lea     rcx, [rsp+48h+IoWorkItem]
0x14005099b  call    ??1?$unique_storage@U?$resource_policy@PEAU_IO_WORKITEM@@P6AXPEAU1@@Z$1?IoFreeWorkItem@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_IO_WORKITEM *,void (*)(_IO_WORKITEM *),&IoFreeWorkItem(_IO_WORKITEM *),wistd::integral_constant<unsigned __int64,1>,_IO_WORKITEM *,_IO_WORKITEM *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_IO_WORKITEM *,void (*)(_IO_WORKITEM *),&IoFreeWorkItem(_IO_WORKITEM *),wistd::integral_constant<unsigned __int64,1>,_IO_WORKITEM *,_IO_WORKITEM *,0,std::nullptr_t>>(void)
0x1400509a0  mov     r8d, 20h ; ' '; RemlockSize
0x1400509a6  lea     rdx, _ExecuteAsync__lambda_7fb7b13f14c685282a4ef123eba0e8d9_______2___Thunk__Invoke; Tag
0x1400509ad  mov     rcx, rbp; RemoveLock
0x1400509b0  call    cs:__imp_IoReleaseRemoveLockEx
0x1400509b7  nop     dword ptr [rax+rax+00h]
0x1400509bc  mov     ebx, 0C000009Ah
0x1400509c1  mov     rcx, rsi
0x1400509c4  call    ?Reset@?$RefObjReference@UREAD_CONNECTED_RSSI_CONTEXT@@$0A@$M$$T0A@$M$$T0A@@@QEAAXPEAUREAD_CONNECTED_RSSI_CONTEXT@@PEBX@Z
0x1400509c9  mov     eax, ebx
0x1400509cb  mov     rbx, [rsp+48h+arg_0]
0x1400509d0  add     rsp, 30h
0x1400509d4  pop     rdi
0x1400509d5  pop     rsi
0x1400509d6  pop     rbp
0x1400509d7  retn
```
