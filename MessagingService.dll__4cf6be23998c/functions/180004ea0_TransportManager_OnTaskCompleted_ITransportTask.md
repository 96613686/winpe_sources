# TransportManager::_OnTaskCompleted(ITransportTask *)

- ea: `0x180004ea0`
- end: `0x180005029`
- name: `?_OnTaskCompleted@TransportManager@@AEAAJPEAUITransportTask@@@Z`
- size: `393`
- prototype: `__int64 __fastcall(TransportManager *__hidden this, struct ITransportTask *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000266c`
- `0x180003928`
- `0x1800044c4`
- `0x1800044dc`
- `0x180004ea0`
- `0x1800051cc`
- `0x18000c010`

## string_xrefs

- `0x180004f41`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`
- `0x180004fd4`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`

## pseudocode

```c
__int64 __fastcall TransportManager::_OnTaskCompleted(TransportManager *this, struct ITransportTask *a2)
{
  struct ITransportTask *v4; // rbx
  __int64 *v5; // rsi
  __int64 *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  int started; // eax
  unsigned int v10; // edi
  TransportManager *v12; // [rsp+30h] [rbp-28h] BYREF
  __int64 (__fastcall *v13)(TransportManager *, __int64); // [rsp+38h] [rbp-20h] BYREF
  int v14; // [rsp+40h] [rbp-18h]
  struct ITransportTask *v15; // [rsp+48h] [rbp-10h]

  v4 = *(struct ITransportTask **)(*((_QWORD *)this + 7) + 16LL);
  v15 = v4;
  if ( v4 )
    (*(void (__fastcall **)(struct ITransportTask *))(*(_QWORD *)v4 + 8LL))(v4);
  if ( v4 != a2 )
    Log_AssertionEvent(this, a2, 178);
  v5 = (__int64 *)*((_QWORD *)this + 7);
  v6 = (__int64 *)v5[1];
  v7 = *v5;
  *v6 = *v5;
  *(_QWORD *)(v7 + 8) = v6;
  v8 = v5[2];
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
  if ( --*((_QWORD *)this + 9) )
  {
    v13 = TransportManager::_ExecuteNextTask;
    v14 = 0;
    v12 = this;
    (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)this + 8LL))(this);
    v10 = QueueAsyncWorkItem_ATL::CComPtr_TransportManager__long____cdecl_TransportManager::___void__(
            *((_QWORD *)this + 5),
            &v12,
            &v13);
    if ( v12 )
      (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)v12 + 16LL))(v12);
    if ( (v10 & 0x80000000) != 0 )
    {
      Log_HREvent_0(v10, 1, "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
      if ( v4 )
        (*(void (__fastcall **)(struct ITransportTask *))(*(_QWORD *)v4 + 16LL))(v4);
      return v10;
    }
  }
  else
  {
    started = TransportManager::_StartIdleTimer(this);
    v10 = started;
    if ( started < 0 )
    {
      Log_HREvent_0(
        (unsigned int)started,
        1,
        "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
      if ( v4 )
        (*(void (__fastcall **)(struct ITransportTask *))(*(_QWORD *)v4 + 16LL))(v4);
      return v10;
    }
  }
  if ( v4 )
    (*(void (__fastcall **)(struct ITransportTask *))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x180004ea0  mov     [rsp+arg_8], rbx
0x180004ea5  mov     [rsp+arg_10], rsi
0x180004eaa  push    rdi
0x180004eab  sub     rsp, 50h
0x180004eaf  mov     rsi, rdx
0x180004eb2  mov     rdi, rcx
0x180004eb5  mov     rax, [rcx+38h]
0x180004eb9  mov     rbx, [rax+10h]
0x180004ebd  mov     [rsp+58h+var_10], rbx
0x180004ec2  test    rbx, rbx
0x180004ec5  jz      short loc_180004ED7
0x180004ec7  mov     rax, [rbx]
0x180004eca  mov     rcx, rbx
0x180004ecd  mov     rax, [rax+8]
0x180004ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed6  nop
0x180004ed7  cmp     rbx, rsi
0x180004eda  jz      short loc_180004EE7
0x180004edc  mov     r8d, 0B2h
0x180004ee2  call    Log_AssertionEvent
0x180004ee7  mov     rsi, [rdi+38h]
0x180004eeb  mov     rcx, [rsi+8]
0x180004eef  mov     rax, [rsi]
0x180004ef2  mov     [rcx], rax
0x180004ef5  mov     [rax+8], rcx
0x180004ef9  mov     rcx, [rsi+10h]
0x180004efd  test    rcx, rcx
0x180004f00  jz      short loc_180004F0F
0x180004f02  mov     rax, [rcx]
0x180004f05  mov     rax, [rax+10h]
0x180004f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f0e  nop
0x180004f0f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004f16  mov     rcx, rsi; void *
0x180004f19  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004f1e  dec     qword ptr [rdi+48h]
0x180004f22  mov     rcx, rdi; this
0x180004f25  cmp     qword ptr [rdi+48h], 0
0x180004f2a  jnz     short loc_180004F71
0x180004f2c  call    ?_StartIdleTimer@TransportManager@@AEAAJXZ; TransportManager::_StartIdleTimer(void)
0x180004f31  mov     edi, eax
0x180004f33  test    eax, eax
0x180004f35  jns     loc_180005002
0x180004f3b  mov     r9d, 0B9h
0x180004f41  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x180004f48  mov     edx, 1
0x180004f4d  mov     ecx, eax
0x180004f4f  call    Log_HREvent_0
0x180004f54  nop
0x180004f55  test    rbx, rbx
0x180004f58  jz      short loc_180004F6A
0x180004f5a  mov     rax, [rbx]
0x180004f5d  mov     rcx, rbx
0x180004f60  mov     rax, [rax+10h]
0x180004f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f69  nop
0x180004f6a  mov     eax, edi
0x180004f6c  jmp     loc_180005019
0x180004f71  lea     rax, ?_ExecuteNextTask@TransportManager@@AEAAJXZ; TransportManager::_ExecuteNextTask(void)
0x180004f78  mov     [rsp+58h+var_20], rax
0x180004f7d  mov     [rsp+58h+var_18], 0
0x180004f85  mov     eax, [rsp+58h+var_14]
0x180004f89  mov     [rsp+58h+var_14], eax
0x180004f8d  mov     [rsp+58h+var_28], rdi
0x180004f92  mov     rax, [rdi]
0x180004f95  mov     rax, [rax+8]
0x180004f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f9e  nop
0x180004f9f  lea     r8, [rsp+58h+var_20]
0x180004fa4  lea     rdx, [rsp+58h+var_28]
0x180004fa9  mov     rcx, [rdi+28h]
0x180004fad  call    QueueAsyncWorkItem_ATL__CComPtr_TransportManager__long____cdecl_TransportManager_____void__
0x180004fb2  mov     edi, eax
0x180004fb4  mov     rcx, [rsp+58h+var_28]
0x180004fb9  test    rcx, rcx
0x180004fbc  jz      short loc_180004FCA
0x180004fbe  mov     rdx, [rcx]
0x180004fc1  mov     rax, [rdx+10h]
0x180004fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fca  test    edi, edi
0x180004fcc  jns     short loc_180005002
0x180004fce  mov     r9d, 0BDh
0x180004fd4  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x180004fdb  mov     edx, 1
0x180004fe0  mov     ecx, edi
0x180004fe2  call    Log_HREvent_0
0x180004fe7  nop
0x180004fe8  test    rbx, rbx
0x180004feb  jz      short loc_180004FFD
0x180004fed  mov     rax, [rbx]
0x180004ff0  mov     rcx, rbx
0x180004ff3  mov     rax, [rax+10h]
0x180004ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ffc  nop
0x180004ffd  jmp     loc_180004F6A
0x180005002  test    rbx, rbx
0x180005005  jz      short loc_180005017
0x180005007  mov     rax, [rbx]
0x18000500a  mov     rcx, rbx
0x18000500d  mov     rax, [rax+10h]
0x180005011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005016  nop
0x180005017  xor     eax, eax
0x180005019  mov     rbx, [rsp+58h+arg_8]
0x18000501e  mov     rsi, [rsp+58h+arg_10]
0x180005023  add     rsp, 50h
0x180005027  pop     rdi
0x180005028  retn
```
