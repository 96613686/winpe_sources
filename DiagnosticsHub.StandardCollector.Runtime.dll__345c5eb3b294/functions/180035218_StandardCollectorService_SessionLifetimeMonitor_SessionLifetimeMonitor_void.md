# StandardCollectorService::SessionLifetimeMonitor::~SessionLifetimeMonitor(void)

- ea: `0x180035218`
- end: `0x1800352e9`
- name: `??1SessionLifetimeMonitor@StandardCollectorService@@QEAA@XZ`
- size: `209`
- prototype: `void __fastcall(StandardCollectorService::SessionLifetimeMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x180036370`

## callees

- `0x180017274`
- `0x180035218`
- `0x18004a078`
- `0x18004b640`

## import_xrefs

- `KERNEL32!UnregisterWait` at `0x180035233`
- `KERNEL32!UnregisterWait` at `0x180035233`
- `KERNEL32!CloseHandle` at `0x180035254`
- `KERNEL32!CloseHandle` at `0x1800352d3`
- `KERNEL32!CloseHandle` at `0x180035254`
- `KERNEL32!CloseHandle` at `0x1800352d3`
- `KERNEL32!DeleteCriticalSection` at `0x180035245`
- `KERNEL32!DeleteCriticalSection` at `0x180035266`
- `KERNEL32!DeleteCriticalSection` at `0x180035245`
- `KERNEL32!DeleteCriticalSection` at `0x180035266`

## pseudocode

```c
void __fastcall StandardCollectorService::SessionLifetimeMonitor::~SessionLifetimeMonitor(
        StandardCollectorService::SessionLifetimeMonitor *this)
{
  void *v2; // rcx
  void *v3; // rcx
  _QWORD *v4; // rdi
  void *v5; // rcx
  __int64 v6; // rcx
  void *v7; // rcx

  v2 = (void *)*((_QWORD *)this + 12);
  if ( v2 )
  {
    UnregisterWait(v2);
    *((_QWORD *)this + 12) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v3 = (void *)*((_QWORD *)this + 13);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 13) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v4 = *(_QWORD **)(*((_QWORD *)this + 5) + 8LL);
  while ( !*((_BYTE *)v4 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<unsigned int>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned int,void *>>>(
      (char *)this + 40,
      (char *)this + 40,
      v4[2]);
    v5 = v4;
    v4 = (_QWORD *)*v4;
    operator delete(v5);
  }
  operator delete(*((void **)this + 5));
  v6 = *((_QWORD *)this + 4);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = (void *)*((_QWORD *)this + 2);
  if ( v7 != (void *)-1LL )
  {
    *((_QWORD *)this + 2) = -1;
    CloseHandle(v7);
  }
}

```

## disassembly

```asm
0x180035218  mov     [rsp+arg_8], rbx
0x18003521d  mov     [rsp+arg_10], rsi
0x180035222  push    rdi
0x180035223  sub     rsp, 20h
0x180035227  mov     rbx, rcx
0x18003522a  mov     rcx, [rcx+60h]; WaitHandle
0x18003522e  test    rcx, rcx
0x180035231  jz      short loc_180035241
0x180035233  call    cs:__imp_UnregisterWait
0x180035239  mov     qword ptr [rbx+60h], 0
0x180035241  lea     rcx, [rbx+70h]; lpCriticalSection
0x180035245  call    cs:__imp_DeleteCriticalSection
0x18003524b  mov     rcx, [rbx+68h]; hObject
0x18003524f  test    rcx, rcx
0x180035252  jz      short loc_180035262
0x180035254  call    cs:__imp_CloseHandle
0x18003525a  mov     qword ptr [rbx+68h], 0
0x180035262  lea     rcx, [rbx+38h]; lpCriticalSection
0x180035266  call    cs:__imp_DeleteCriticalSection
0x18003526c  lea     rsi, [rbx+28h]
0x180035270  mov     rax, [rsi]
0x180035273  mov     rdi, [rax+8]
0x180035277  jmp     short loc_180035298
0x180035279  mov     r8, [rdi+10h]
0x18003527d  mov     rdx, rsi
0x180035280  mov     rcx, rsi
0x180035283  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@IPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@IPEAX@std@@@1@PEAU?$_Tree_node@IPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<uint>>::_Erase_tree<std::allocator<std::_Tree_node<uint,void *>>>(std::allocator<std::_Tree_node<uint,void *>> &,std::_Tree_node<uint,void *> *)
0x180035288  mov     rcx, rdi; Block
0x18003528b  mov     edx, 20h ; ' '
0x180035290  mov     rdi, [rdi]
0x180035293  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180035298  cmp     byte ptr [rdi+19h], 0
0x18003529c  jz      short loc_180035279
0x18003529e  mov     rcx, [rsi]; Block
0x1800352a1  mov     edx, 20h ; ' '
0x1800352a6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800352ab  mov     rcx, [rbx+20h]
0x1800352af  test    rcx, rcx
0x1800352b2  jz      short loc_1800352C1
0x1800352b4  mov     rax, [rcx]
0x1800352b7  mov     rax, [rax+10h]
0x1800352bb  call    cs:__guard_dispatch_icall_fptr
0x1800352c1  mov     rcx, [rbx+10h]; hObject
0x1800352c5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800352c9  jz      short loc_1800352D9
0x1800352cb  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x1800352d3  call    cs:__imp_CloseHandle
0x1800352d9  mov     rbx, [rsp+28h+arg_8]
0x1800352de  mov     rsi, [rsp+28h+arg_10]
0x1800352e3  add     rsp, 20h
0x1800352e7  pop     rdi
0x1800352e8  retn
```
