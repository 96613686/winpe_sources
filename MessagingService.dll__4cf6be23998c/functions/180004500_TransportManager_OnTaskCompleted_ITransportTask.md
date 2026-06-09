# TransportManager::OnTaskCompleted(ITransportTask *)

- ea: `0x180004500`
- end: `0x18000460f`
- name: `?OnTaskCompleted@TransportManager@@UEAAJPEAUITransportTask@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(TransportManager *this, struct ITransportTask *, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001148`
- `0x180003774`
- `0x1800044dc`
- `0x180004500`
- `0x18000c010`

## string_xrefs

- `0x1800045bb`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`

## pseudocode

```c
__int64 __fastcall TransportManager::OnTaskCompleted(
        TransportManager *this,
        struct ITransportTask *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 *v5; // rbx
  int v6; // ebx
  __int64 (__fastcall *v8)(TransportManager *, struct ITransportTask *); // [rsp+30h] [rbp-10h] BYREF
  int v9; // [rsp+38h] [rbp-8h]
  const wchar_t *v10; // [rsp+50h] [rbp+10h] BYREF
  struct ITransportTask *v11; // [rsp+60h] [rbp+20h] BYREF

  v5 = (__int64 *)((char *)this - 8);
  if ( *((_QWORD *)this + 4) )
  {
    v11 = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct ITransportTask *))(*(_QWORD *)a2 + 8LL))(a2);
    v8 = TransportManager::_OnTaskCompleted;
    v9 = 0;
    v10 = (const wchar_t *)v5;
    if ( v5 )
      (*(void (__fastcall **)(__int64 *))(*v5 + 8))(v5);
    v6 = QueueAsyncWorkItem_ATL::CComPtr_TransportManager__long____cdecl_TransportManager::___ITransportTask____ATL::CComPtr_ITransportTask___(
           *((_QWORD *)this + 4),
           &v10,
           &v8,
           &v11);
    if ( v10 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v11 )
      (*(void (__fastcall **)(struct ITransportTask *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v6 < 0 )
    {
      Log_HREvent_0((unsigned int)v6, 1, "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
      return (unsigned int)v6;
    }
  }
  else if ( (unsigned int)dword_180013018 > 3 )
  {
    v10 = L"TransportManager has shutdown.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)this,
      (int)byte_180010173,
      a3,
      a4,
      (__int64 **)&v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180004500  mov     [rsp-8+arg_8], rbx
0x180004505  mov     [rsp-8+arg_18], rdi
0x18000450a  push    rbp
0x18000450b  mov     rbp, rsp
0x18000450e  sub     rsp, 40h
0x180004512  mov     rdi, rcx
0x180004515  lea     rbx, [rcx-8]
0x180004519  cmp     qword ptr [rbx+28h], 0
0x18000451e  jz      loc_1800045D2
0x180004524  mov     [rbp+arg_10], rdx
0x180004528  test    rdx, rdx
0x18000452b  jz      short loc_18000453D
0x18000452d  mov     rax, [rdx]
0x180004530  mov     rcx, rdx
0x180004533  mov     rax, [rax+8]
0x180004537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000453c  nop
0x18000453d  lea     rax, ?_OnTaskCompleted@TransportManager@@AEAAJPEAUITransportTask@@@Z; TransportManager::_OnTaskCompleted(ITransportTask *)
0x180004544  mov     [rbp+var_10], rax
0x180004548  mov     [rbp+var_8], 0
0x18000454f  mov     eax, [rbp+var_4]
0x180004552  mov     [rbp+var_4], eax
0x180004555  mov     [rbp+arg_0], rbx
0x180004559  test    rbx, rbx
0x18000455c  jz      short loc_18000456E
0x18000455e  mov     rax, [rbx]
0x180004561  mov     rcx, rbx
0x180004564  mov     rax, [rax+8]
0x180004568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000456d  nop
0x18000456e  lea     r9, [rbp+arg_10]
0x180004572  lea     r8, [rbp+var_10]
0x180004576  lea     rdx, [rbp+arg_0]
0x18000457a  mov     rcx, [rdi+20h]
0x18000457e  call    QueueAsyncWorkItem_ATL__CComPtr_TransportManager__long____cdecl_TransportManager_____ITransportTask____ATL__CComPtr_ITransportTask___
0x180004583  mov     ebx, eax
0x180004585  mov     rcx, [rbp+arg_0]
0x180004589  test    rcx, rcx
0x18000458c  jz      short loc_18000459B
0x18000458e  mov     rdx, [rcx]
0x180004591  mov     rax, [rdx+10h]
0x180004595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000459a  nop
0x18000459b  mov     rcx, [rbp+arg_10]
0x18000459f  test    rcx, rcx
0x1800045a2  jz      short loc_1800045B1
0x1800045a4  mov     rax, [rcx]
0x1800045a7  mov     rax, [rax+10h]
0x1800045ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045b0  nop
0x1800045b1  test    ebx, ebx
0x1800045b3  jns     short loc_1800045FD
0x1800045b5  mov     r9d, 0A1h
0x1800045bb  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x1800045c2  mov     edx, 1
0x1800045c7  mov     ecx, ebx
0x1800045c9  call    Log_HREvent_0
0x1800045ce  mov     eax, ebx
0x1800045d0  jmp     short loc_1800045FF
0x1800045d2  mov     eax, cs:dword_180013018
0x1800045d8  cmp     eax, 3
0x1800045db  jbe     short loc_1800045FD
0x1800045dd  lea     rax, aTransportmanag; "TransportManager has shutdown."
0x1800045e4  mov     [rbp+arg_0], rax
0x1800045e8  lea     rax, [rbp+arg_0]
0x1800045ec  mov     [rsp+40h+var_20], rax
0x1800045f1  lea     rdx, byte_180010173
0x1800045f8  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800045fd  xor     eax, eax
0x1800045ff  mov     rbx, [rsp+40h+arg_8]
0x180004604  mov     rdi, [rsp+40h+arg_18]
0x180004609  add     rsp, 40h
0x18000460d  pop     rbp
0x18000460e  retn
```
