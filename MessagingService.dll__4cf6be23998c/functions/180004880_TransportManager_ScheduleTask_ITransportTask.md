# TransportManager::ScheduleTask(ITransportTask *)

- ea: `0x180004880`
- end: `0x18000497b`
- name: `?ScheduleTask@TransportManager@@UEAAJPEAUITransportTask@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(wchar_t *this, struct ITransportTask *, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001148`
- `0x180003774`
- `0x1800044dc`
- `0x180004880`
- `0x18000c010`

## string_xrefs

- `0x18000492d`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`

## pseudocode

```c
__int64 __fastcall TransportManager::ScheduleTask(wchar_t *this, struct ITransportTask *a2, int a3, int a4)
{
  int v5; // ebx
  __int64 (__fastcall *v7)(TransportManager *__hidden, struct ITransportTask *); // [rsp+30h] [rbp-10h] BYREF
  int v8; // [rsp+38h] [rbp-8h]
  const wchar_t *v9; // [rsp+50h] [rbp+10h] BYREF
  struct ITransportTask *v10; // [rsp+60h] [rbp+20h] BYREF

  if ( *((_QWORD *)this + 5) )
  {
    v10 = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct ITransportTask *))(*(_QWORD *)a2 + 8LL))(a2);
    v7 = TransportManager::_ScheduleTask;
    v8 = 0;
    v9 = this;
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)this + 8LL))(this);
    v5 = QueueAsyncWorkItem_ATL::CComPtr_TransportManager__long____cdecl_TransportManager::___ITransportTask____ATL::CComPtr_ITransportTask___(
           *((_QWORD *)this + 5),
           &v9,
           &v7,
           &v10);
    if ( v9 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v9 + 16LL))(v9);
    if ( v10 )
      (*(void (__fastcall **)(struct ITransportTask *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v5 < 0 )
    {
      Log_HREvent_0((unsigned int)v5, 1, "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
      return (unsigned int)v5;
    }
  }
  else if ( (unsigned int)dword_180013018 > 3 )
  {
    v9 = L"TransportManager has shutdown.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)this,
      (unsigned int)byte_1800101AD,
      a3,
      a4,
      (__int64)&v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180004880  mov     [rsp-8+arg_8], rbx
0x180004885  push    rbp
0x180004886  mov     rbp, rsp
0x180004889  sub     rsp, 40h
0x18000488d  mov     rbx, rcx
0x180004890  cmp     qword ptr [rcx+28h], 0
0x180004895  jz      loc_180004943
0x18000489b  mov     [rbp+arg_10], rdx
0x18000489f  test    rdx, rdx
0x1800048a2  jz      short loc_1800048B4
0x1800048a4  mov     rax, [rdx]
0x1800048a7  mov     rcx, rdx
0x1800048aa  mov     rax, [rax+8]
0x1800048ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b3  nop
0x1800048b4  lea     rax, ?_ScheduleTask@TransportManager@@AEAAJPEAUITransportTask@@@Z; TransportManager::_ScheduleTask(ITransportTask *)
0x1800048bb  mov     [rbp+var_10], rax
0x1800048bf  mov     [rbp+var_8], 0
0x1800048c6  mov     eax, [rbp+var_4]
0x1800048c9  mov     [rbp+var_4], eax
0x1800048cc  mov     [rbp+arg_0], rbx
0x1800048d0  mov     rax, [rbx]
0x1800048d3  mov     rcx, rbx
0x1800048d6  mov     rax, [rax+8]
0x1800048da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048df  nop
0x1800048e0  lea     r9, [rbp+arg_10]
0x1800048e4  lea     r8, [rbp+var_10]
0x1800048e8  lea     rdx, [rbp+arg_0]
0x1800048ec  mov     rcx, [rbx+28h]
0x1800048f0  call    QueueAsyncWorkItem_ATL__CComPtr_TransportManager__long____cdecl_TransportManager_____ITransportTask____ATL__CComPtr_ITransportTask___
0x1800048f5  mov     ebx, eax
0x1800048f7  mov     rcx, [rbp+arg_0]
0x1800048fb  test    rcx, rcx
0x1800048fe  jz      short loc_18000490D
0x180004900  mov     rdx, [rcx]
0x180004903  mov     rax, [rdx+10h]
0x180004907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000490c  nop
0x18000490d  mov     rcx, [rbp+arg_10]
0x180004911  test    rcx, rcx
0x180004914  jz      short loc_180004923
0x180004916  mov     rax, [rcx]
0x180004919  mov     rax, [rax+10h]
0x18000491d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004922  nop
0x180004923  test    ebx, ebx
0x180004925  jns     short loc_18000496E
0x180004927  mov     r9d, 74h ; 't'
0x18000492d  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x180004934  lea     edx, [r9-73h]
0x180004938  mov     ecx, ebx
0x18000493a  call    Log_HREvent_0
0x18000493f  mov     eax, ebx
0x180004941  jmp     short loc_180004970
0x180004943  mov     eax, cs:dword_180013018
0x180004949  cmp     eax, 3
0x18000494c  jbe     short loc_18000496E
0x18000494e  lea     rax, aTransportmanag; "TransportManager has shutdown."
0x180004955  mov     [rbp+arg_0], rax
0x180004959  lea     rax, [rbp+arg_0]
0x18000495d  mov     [rsp+40h+var_20], rax
0x180004962  lea     rdx, byte_1800101AD
0x180004969  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000496e  xor     eax, eax
0x180004970  mov     rbx, [rsp+40h+arg_8]
0x180004975  add     rsp, 40h
0x180004979  pop     rbp
0x18000497a  retn
```
