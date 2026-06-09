# Microsoft::DiagnosticsHub::StandardCollector::AgentController::~AgentController(void)

- ea: `0x1800029bc`
- end: `0x180002b39`
- name: `??1AgentController@StandardCollector@DiagnosticsHub@Microsoft@@UEAA@XZ`
- size: `381`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::AgentController *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180002b40`
- `0x180002c4c`
- `0x18004bc70`

## callees

- `0x1800029bc`
- `0x18000334c`
- `0x180003418`
- `0x18000348c`
- `0x18004a078`
- `0x18004b640`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800029da`
- `KERNEL32!DeleteCriticalSection` at `0x180002a5a`
- `KERNEL32!DeleteCriticalSection` at `0x180002a73`
- `KERNEL32!DeleteCriticalSection` at `0x180002a98`
- `KERNEL32!DeleteCriticalSection` at `0x180002ab1`
- `KERNEL32!DeleteCriticalSection` at `0x180002ad3`
- `KERNEL32!DeleteCriticalSection` at `0x180002af5`
- `KERNEL32!DeleteCriticalSection` at `0x180002b0b`
- `KERNEL32!DeleteCriticalSection` at `0x180002b1e`
- `KERNEL32!DeleteCriticalSection` at `0x1800029da`
- `KERNEL32!DeleteCriticalSection` at `0x180002a5a`
- `KERNEL32!DeleteCriticalSection` at `0x180002a73`
- `KERNEL32!DeleteCriticalSection` at `0x180002a98`
- `KERNEL32!DeleteCriticalSection` at `0x180002ab1`
- `KERNEL32!DeleteCriticalSection` at `0x180002ad3`
- `KERNEL32!DeleteCriticalSection` at `0x180002af5`
- `KERNEL32!DeleteCriticalSection` at `0x180002b0b`
- `KERNEL32!DeleteCriticalSection` at `0x180002b1e`
- `KERNEL32!DeleteCriticalSection` at `0x180002b32`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::AgentController::~AgentController(
        Microsoft::DiagnosticsHub::StandardCollector::AgentController *this)
{
  _QWORD **v2; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx
  __int64 v5; // rcx

  *(_QWORD *)this = &Microsoft::DiagnosticsHub::StandardCollector::AgentController::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 19);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>((char *)this + 720);
  v2 = (_QWORD **)*((_QWORD *)this + 88);
  *v2[1] = 0;
  v3 = *v2;
  if ( *v2 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      operator delete(v3);
      v3 = v4;
    }
    while ( v4 );
  }
  operator delete(*((void **)this + 88));
  v5 = *((_QWORD *)this + 85);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>((char *)this + 648);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>((char *)this + 584);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
  std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>((char *)this + 520);
  std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>((char *)this + 488);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
  std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>((char *)this + 424);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>((char *)this + 344);
  std::list<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorGraphingAgent>>>::~list<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorGraphingAgent>>>((char *)this + 328);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 7);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>((char *)this + 240);
  std::list<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorGraphingAgent>>>::~list<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorGraphingAgent>>>((char *)this + 224);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>((char *)this + 152);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>((char *)this + 88);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800029bc  mov     [rsp+arg_8], rbx
0x1800029c1  push    rdi
0x1800029c2  sub     rsp, 20h
0x1800029c6  mov     rdi, rcx
0x1800029c9  lea     rax, ??_7AgentController@StandardCollector@DiagnosticsHub@Microsoft@@6B@; const Microsoft::DiagnosticsHub::StandardCollector::AgentController::`vftable'
0x1800029d0  mov     [rcx], rax
0x1800029d3  add     rcx, 2F8h; lpCriticalSection
0x1800029da  call    cs:__imp_DeleteCriticalSection
0x1800029e0  lea     rcx, [rdi+2D0h]
0x1800029e7  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(void)
0x1800029ec  mov     rdx, [rdi+2C0h]
0x1800029f3  mov     rax, [rdx+8]
0x1800029f7  mov     qword ptr [rax], 0
0x1800029fe  mov     rcx, [rdx]; Block
0x180002a01  test    rcx, rcx
0x180002a04  jz      short loc_180002A1B
0x180002a06  mov     rbx, [rcx]
0x180002a09  mov     edx, 20h ; ' '
0x180002a0e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002a13  mov     rcx, rbx
0x180002a16  test    rbx, rbx
0x180002a19  jnz     short loc_180002A06
0x180002a1b  mov     edx, 20h ; ' '
0x180002a20  mov     rcx, [rdi+2C0h]; Block
0x180002a27  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002a2c  nop
0x180002a2d  mov     rcx, [rdi+2A8h]
0x180002a34  test    rcx, rcx
0x180002a37  jz      short loc_180002A47
0x180002a39  mov     rax, [rcx]
0x180002a3c  mov     rax, [rax+10h]
0x180002a40  call    cs:__guard_dispatch_icall_fptr
0x180002a46  nop
0x180002a47  lea     rbx, [rdi+260h]
0x180002a4e  lea     rcx, [rbx+28h]
0x180002a52  call    ??1?$vector@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>(void)
0x180002a57  mov     rcx, rbx; lpCriticalSection
0x180002a5a  call    cs:__imp_DeleteCriticalSection
0x180002a60  lea     rbx, [rdi+220h]
0x180002a67  lea     rcx, [rbx+28h]
0x180002a6b  call    ??1?$vector@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>(void)
0x180002a70  mov     rcx, rbx; lpCriticalSection
0x180002a73  call    cs:__imp_DeleteCriticalSection
0x180002a79  lea     rcx, [rdi+208h]
0x180002a80  call    ??1?$vector@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>(void)
0x180002a85  lea     rbx, [rdi+1C0h]
0x180002a8c  lea     rcx, [rbx+28h]
0x180002a90  call    ??1?$vector@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>(void)
0x180002a95  mov     rcx, rbx; lpCriticalSection
0x180002a98  call    cs:__imp_DeleteCriticalSection
0x180002a9e  lea     rbx, [rdi+180h]
0x180002aa5  lea     rcx, [rbx+28h]
0x180002aa9  call    ??1?$vector@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>(void)
0x180002aae  mov     rcx, rbx; lpCriticalSection
0x180002ab1  call    cs:__imp_DeleteCriticalSection
0x180002ab7  lea     rbx, [rdi+118h]
0x180002abe  lea     rcx, [rbx+40h]
0x180002ac2  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(void)
0x180002ac7  lea     rcx, [rbx+30h]
0x180002acb  call    ??1?$list@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorGraphingAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorGraphingAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorGraphingAgent>>>::~list<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorGraphingAgent>>>(void)
0x180002ad0  mov     rcx, rbx; lpCriticalSection
0x180002ad3  call    cs:__imp_DeleteCriticalSection
0x180002ad9  lea     rbx, [rdi+0B0h]
0x180002ae0  lea     rcx, [rbx+40h]
0x180002ae4  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(void)
0x180002ae9  lea     rcx, [rbx+30h]
0x180002aed  call    ??1?$list@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorGraphingAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorGraphingAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorGraphingAgent>>>::~list<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorGraphingAgent>>>(void)
0x180002af2  mov     rcx, rbx; lpCriticalSection
0x180002af5  call    cs:__imp_DeleteCriticalSection
0x180002afb  lea     rcx, [rdi+98h]
0x180002b02  call    ??1?$vector@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>(void)
0x180002b07  lea     rcx, [rdi+70h]; lpCriticalSection
0x180002b0b  call    cs:__imp_DeleteCriticalSection
0x180002b11  lea     rcx, [rdi+58h]
0x180002b15  call    ??1?$vector@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@U?$AgentContainer@UIStandardCollectorAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>::~vector<Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorAgent>>(void)
0x180002b1a  lea     rcx, [rdi+30h]; lpCriticalSection
0x180002b1e  call    cs:__imp_DeleteCriticalSection
0x180002b24  lea     rcx, [rdi+8]
0x180002b28  mov     rbx, [rsp+28h+arg_8]
0x180002b2d  add     rsp, 20h
0x180002b31  pop     rdi
0x180002b32  jmp     cs:__imp_DeleteCriticalSection
```
