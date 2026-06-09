# TransportManager::_ScheduleTask(ITransportTask *)

- ea: `0x180005030`
- end: `0x1800051c5`
- name: `?_ScheduleTask@TransportManager@@AEAAJPEAUITransportTask@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(TransportManager *__hidden this, struct ITransportTask *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002678`
- `0x180003928`
- `0x1800044dc`
- `0x180005030`
- `0x180005364`
- `0x18000c010`

## string_xrefs

- `0x180005051`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`
- `0x180005144`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`
- `0x18000518e`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`

## pseudocode

```c
__int64 __fastcall TransportManager::_ScheduleTask(TransportManager *this, struct ITransportTask *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  _QWORD *v8; // rax
  TransportManager *v10; // [rsp+30h] [rbp-48h] BYREF
  __int64 (__fastcall *v11)(TransportManager *, __int64); // [rsp+38h] [rbp-40h] BYREF
  int v12; // [rsp+40h] [rbp-38h]
  struct ITransportTask *v13; // [rsp+48h] [rbp-30h]

  v4 = TransportManager::_StopIdleTimer(this);
  v5 = v4;
  if ( v4 < 0 )
  {
    Log_HREvent_0((unsigned int)v4, 1, "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
    return v5;
  }
  v13 = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct ITransportTask *))(*(_QWORD *)a2 + 8LL))(a2);
  v6 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( !v6 )
  {
    v5 = -2147024882;
    Log_HREvent_0(2147942414LL, 0, "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
    if ( a2 )
      (*(void (__fastcall **)(struct ITransportTask *))(*(_QWORD *)a2 + 16LL))(a2);
    return v5;
  }
  v6[2] = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct ITransportTask *))(*(_QWORD *)a2 + 8LL))(a2);
  v8 = (_QWORD *)*((_QWORD *)this + 8);
  v7[1] = v8;
  *v7 = (char *)this + 56;
  *v8 = v7;
  *((_QWORD *)this + 8) = v7;
  if ( ++*((_QWORD *)this + 9) == 1 )
  {
    v11 = TransportManager::_ExecuteNextTask;
    v12 = 0;
    v10 = this;
    (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)this + 8LL))(this);
    v5 = QueueAsyncWorkItem_ATL::CComPtr_TransportManager__long____cdecl_TransportManager::___void__(
           *((_QWORD *)this + 5),
           &v10,
           &v11);
    if ( v10 )
      (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( (v5 & 0x80000000) != 0 )
    {
      Log_HREvent_0(v5, 1, "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
      if ( a2 )
        (*(void (__fastcall **)(struct ITransportTask *))(*(_QWORD *)a2 + 16LL))(a2);
      return v5;
    }
  }
  if ( a2 )
    (*(void (__fastcall **)(struct ITransportTask *))(*(_QWORD *)a2 + 16LL))(a2);
  return 0;
}

```

## disassembly

```asm
0x180005030  push    rbx
0x180005032  push    rsi
0x180005033  push    rdi
0x180005034  push    r14
0x180005036  sub     rsp, 58h
0x18000503a  mov     rdi, rdx
0x18000503d  mov     r14, rcx
0x180005040  call    ?_StopIdleTimer@TransportManager@@AEAAJXZ; TransportManager::_StopIdleTimer(void)
0x180005045  mov     ebx, eax
0x180005047  test    eax, eax
0x180005049  jns     short loc_180005069
0x18000504b  mov     r9d, 84h
0x180005051  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x180005058  mov     edx, 1
0x18000505d  mov     ecx, eax
0x18000505f  call    Log_HREvent_0
0x180005064  jmp     loc_1800051B9
0x180005069  mov     [rsp+78h+var_30], rdi
0x18000506e  test    rdi, rdi
0x180005071  jz      short loc_180005083
0x180005073  mov     rax, [rdi]
0x180005076  mov     rcx, rdi
0x180005079  mov     rax, [rax+8]
0x18000507d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005082  nop
0x180005083  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000508a  mov     ecx, 18h; unsigned __int64
0x18000508f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005094  mov     rbx, rax
0x180005097  test    rax, rax
0x18000509a  jz      loc_180005188
0x1800050a0  lea     rsi, [r14+38h]
0x1800050a4  mov     [rax+10h], rdi
0x1800050a8  test    rdi, rdi
0x1800050ab  jz      short loc_1800050BD
0x1800050ad  mov     rax, [rdi]
0x1800050b0  mov     rcx, rdi
0x1800050b3  mov     rax, [rax+8]
0x1800050b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050bc  nop
0x1800050bd  mov     rax, [rsi+8]
0x1800050c1  mov     [rbx+8], rax
0x1800050c5  mov     [rbx], rsi
0x1800050c8  mov     [rax], rbx
0x1800050cb  mov     [rsi+8], rbx
0x1800050cf  inc     qword ptr [rsi+10h]
0x1800050d3  cmp     qword ptr [r14+48h], 1
0x1800050d8  jnz     loc_18000516F
0x1800050de  lea     rax, ?_ExecuteNextTask@TransportManager@@AEAAJXZ; TransportManager::_ExecuteNextTask(void)
0x1800050e5  mov     [rsp+78h+var_40], rax
0x1800050ea  mov     [rsp+78h+var_38], 0
0x1800050f2  mov     eax, [rsp+78h+var_34]
0x1800050f6  mov     [rsp+78h+var_34], eax
0x1800050fa  mov     [rsp+78h+var_48], r14
0x1800050ff  mov     rax, [r14]
0x180005102  mov     rcx, r14
0x180005105  mov     rax, [rax+8]
0x180005109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000510e  nop
0x18000510f  lea     r8, [rsp+78h+var_40]
0x180005114  lea     rdx, [rsp+78h+var_48]
0x180005119  mov     rcx, [r14+28h]
0x18000511d  call    QueueAsyncWorkItem_ATL__CComPtr_TransportManager__long____cdecl_TransportManager_____void__
0x180005122  mov     ebx, eax
0x180005124  mov     rcx, [rsp+78h+var_48]
0x180005129  test    rcx, rcx
0x18000512c  jz      short loc_18000513A
0x18000512e  mov     rdx, [rcx]
0x180005131  mov     rax, [rdx+10h]
0x180005135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000513a  test    ebx, ebx
0x18000513c  jns     short loc_18000516F
0x18000513e  mov     r9d, 8Ch
0x180005144  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x18000514b  mov     edx, 1
0x180005150  mov     ecx, ebx
0x180005152  call    Log_HREvent_0
0x180005157  nop
0x180005158  test    rdi, rdi
0x18000515b  jz      short loc_18000516D
0x18000515d  mov     rax, [rdi]
0x180005160  mov     rcx, rdi
0x180005163  mov     rax, [rax+10h]
0x180005167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000516c  nop
0x18000516d  jmp     short loc_1800051B9
0x18000516f  test    rdi, rdi
0x180005172  jz      short loc_180005184
0x180005174  mov     rax, [rdi]
0x180005177  mov     rcx, rdi
0x18000517a  mov     rax, [rax+10h]
0x18000517e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005183  nop
0x180005184  xor     eax, eax
0x180005186  jmp     short loc_1800051BB
0x180005188  mov     r9d, 87h
0x18000518e  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x180005195  xor     edx, edx
0x180005197  mov     ebx, 8007000Eh
0x18000519c  mov     ecx, ebx
0x18000519e  call    Log_HREvent_0
0x1800051a3  nop
0x1800051a4  test    rdi, rdi
0x1800051a7  jz      short loc_1800051B9
0x1800051a9  mov     rcx, [rdi]
0x1800051ac  mov     rax, [rcx+10h]
0x1800051b0  mov     rcx, rdi
0x1800051b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051b8  nop
0x1800051b9  mov     eax, ebx
0x1800051bb  add     rsp, 58h
0x1800051bf  pop     r14
0x1800051c1  pop     rdi
0x1800051c2  pop     rsi
0x1800051c3  pop     rbx
0x1800051c4  retn
```
