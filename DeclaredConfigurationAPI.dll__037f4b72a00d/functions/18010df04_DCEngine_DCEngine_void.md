# DCEngine::~DCEngine(void)

- ea: `0x18010df04`
- end: `0x18010e063`
- name: `??1DCEngine@@QEAA@XZ`
- size: `351`
- prototype: `void __fastcall(DCEngine *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18010e494`

## callees

- `0x18000be80`
- `0x180013d4c`
- `0x180058630`
- `0x18010d704`
- `0x18010dec0`
- `0x18010df04`
- `0x18010e07c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18010e01f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18010e02c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18010e01f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18010e02c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010df80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010df99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010dfb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010dfcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010dfe8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010df80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010df99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010dfb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010dfcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010dfe8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010df72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010df8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010dfa4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010dfbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010dfda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010df72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010df8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010dfa4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010dfbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010dfda`

## pseudocode

```c
void __fastcall DCEngine::~DCEngine(DCEngine *this)
{
  _QWORD *v1; // rsi
  void *v3; // rcx
  _QWORD *v4; // rbx
  void *v5; // r15
  void *v6; // rbp
  void *v7; // r14
  void *v8; // r12
  void *v9; // r13
  HANDLE ProcessHeap; // rax
  HANDLE v11; // rax
  HANDLE v12; // rax
  HANDLE v13; // rax
  HANDLE v14; // rax
  __int64 v15; // rcx

  v1 = (_QWORD *)((char *)this + 304);
  *(_QWORD *)this = &DCEngine::`vftable';
  v3 = (void *)*((_QWORD *)this + 38);
  *v1 = 0;
  if ( v3 )
    operator delete(v3);
  v4 = (_QWORD *)*((_QWORD *)this + 36);
  while ( 1 )
  {
    v4 = (_QWORD *)*v4;
    if ( v4 == *((_QWORD **)this + 36) )
      break;
    v5 = (void *)v4[2];
    v6 = (void *)v4[3];
    v7 = (void *)v4[4];
    v8 = (void *)v4[5];
    v9 = (void *)v4[6];
    if ( v5 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
    }
    if ( v6 )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v6);
    }
    if ( v7 )
    {
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v7);
    }
    if ( v8 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v8);
    }
    if ( v9 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v9);
    }
  }
  std::unique_ptr<ISymbolTranslator>::~unique_ptr<ISymbolTranslator>(v1);
  std::_List_node<OrchestratorInstanceVariableTag,void *>::_Free_non_head<std::allocator<std::_List_node<OrchestratorInstanceVariableTag,void *>>>(
    v15,
    *((_QWORD *)this + 36));
  std::_Deallocate<16>(*((void **)this + 36), 0x38u);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 176);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 168);
  DeclaredConfigurations::RequestQueue::~RequestQueue((DCEngine *)((char *)this + 8));
}

```

## disassembly

```asm
0x18010df04  push    rbx
0x18010df06  push    rbp
0x18010df07  push    rsi
0x18010df08  push    rdi
0x18010df09  push    r12
0x18010df0b  push    r13
0x18010df0d  push    r14
0x18010df0f  push    r15
0x18010df11  sub     rsp, 28h
0x18010df15  lea     rsi, [rcx+130h]
0x18010df1c  mov     rdi, rcx
0x18010df1f  lea     rax, ??_7DCEngine@@6B@; const DCEngine::`vftable'
0x18010df26  mov     [rcx], rax
0x18010df29  mov     rcx, [rsi]; Block
0x18010df2c  mov     qword ptr [rsi], 0
0x18010df33  test    rcx, rcx
0x18010df36  jz      short loc_18010DF42
0x18010df38  mov     edx, 8
0x18010df3d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18010df42  mov     rbx, [rdi+120h]
0x18010df49  mov     rbx, [rbx]
0x18010df4c  cmp     rbx, [rdi+120h]
0x18010df53  jz      loc_18010DFF3
0x18010df59  mov     r15, [rbx+10h]
0x18010df5d  mov     rbp, [rbx+18h]
0x18010df61  mov     r14, [rbx+20h]
0x18010df65  mov     r12, [rbx+28h]
0x18010df69  mov     r13, [rbx+30h]
0x18010df6d  test    r15, r15
0x18010df70  jz      short loc_18010DF86
0x18010df72  call    cs:__imp_GetProcessHeap
0x18010df78  mov     r8, r15; lpMem
0x18010df7b  xor     edx, edx; dwFlags
0x18010df7d  mov     rcx, rax; hHeap
0x18010df80  call    cs:__imp_HeapFree
0x18010df86  test    rbp, rbp
0x18010df89  jz      short loc_18010DF9F
0x18010df8b  call    cs:__imp_GetProcessHeap
0x18010df91  mov     r8, rbp; lpMem
0x18010df94  xor     edx, edx; dwFlags
0x18010df96  mov     rcx, rax; hHeap
0x18010df99  call    cs:__imp_HeapFree
0x18010df9f  test    r14, r14
0x18010dfa2  jz      short loc_18010DFB8
0x18010dfa4  call    cs:__imp_GetProcessHeap
0x18010dfaa  mov     r8, r14; lpMem
0x18010dfad  xor     edx, edx; dwFlags
0x18010dfaf  mov     rcx, rax; hHeap
0x18010dfb2  call    cs:__imp_HeapFree
0x18010dfb8  test    r12, r12
0x18010dfbb  jz      short loc_18010DFD1
0x18010dfbd  call    cs:__imp_GetProcessHeap
0x18010dfc3  mov     r8, r12; lpMem
0x18010dfc6  xor     edx, edx; dwFlags
0x18010dfc8  mov     rcx, rax; hHeap
0x18010dfcb  call    cs:__imp_HeapFree
0x18010dfd1  test    r13, r13
0x18010dfd4  jz      loc_18010DF49
0x18010dfda  call    cs:__imp_GetProcessHeap
0x18010dfe0  mov     r8, r13; lpMem
0x18010dfe3  xor     edx, edx; dwFlags
0x18010dfe5  mov     rcx, rax; hHeap
0x18010dfe8  call    cs:__imp_HeapFree
0x18010dfee  jmp     loc_18010DF49
0x18010dff3  mov     rcx, rsi
0x18010dff6  call    ??1?$unique_ptr@UISymbolTranslator@@U?$default_delete@UISymbolTranslator@@@std@@@std@@QEAA@XZ; std::unique_ptr<ISymbolTranslator>::~unique_ptr<ISymbolTranslator>(void)
0x18010dffb  mov     rdx, [rdi+120h]
0x18010e002  call    ??$_Free_non_head@V?$allocator@U?$_List_node@UOrchestratorInstanceVariableTag@@PEAX@std@@@std@@@?$_List_node@UOrchestratorInstanceVariableTag@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@UOrchestratorInstanceVariableTag@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<OrchestratorInstanceVariableTag,void *>::_Free_non_head<std::allocator<std::_List_node<OrchestratorInstanceVariableTag,void *>>>(std::allocator<std::_List_node<OrchestratorInstanceVariableTag,void *>> &,std::_List_node<OrchestratorInstanceVariableTag,void *> *)
0x18010e007  mov     rcx, [rdi+120h]
0x18010e00e  mov     edx, 38h ; '8'
0x18010e013  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18010e018  lea     rcx, [rdi+0E0h]; lpCriticalSection
0x18010e01f  call    cs:__imp_DeleteCriticalSection
0x18010e025  lea     rcx, [rdi+0B8h]; lpCriticalSection
0x18010e02c  call    cs:__imp_DeleteCriticalSection
0x18010e032  lea     rcx, [rdi+0B0h]
0x18010e039  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010e03e  lea     rcx, [rdi+0A8h]
0x18010e045  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010e04a  lea     rcx, [rdi+8]; this
0x18010e04e  add     rsp, 28h
0x18010e052  pop     r15
0x18010e054  pop     r14
0x18010e056  pop     r13
0x18010e058  pop     r12
0x18010e05a  pop     rdi
0x18010e05b  pop     rsi
0x18010e05c  pop     rbp
0x18010e05d  pop     rbx
0x18010e05e  jmp     ??1RequestQueue@DeclaredConfigurations@@QEAA@XZ; DeclaredConfigurations::RequestQueue::~RequestQueue(void)
```
