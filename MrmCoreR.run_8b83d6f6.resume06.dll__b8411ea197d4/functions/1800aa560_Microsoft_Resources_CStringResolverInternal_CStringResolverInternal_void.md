# Microsoft::Resources::CStringResolverInternal::~CStringResolverInternal(void)

- ea: `0x1800aa560`
- end: `0x1800aa63c`
- name: `??1CStringResolverInternal@Resources@Microsoft@@QEAA@XZ`
- size: `220`
- prototype: `void __fastcall(Microsoft::Resources::CStringResolverInternal *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008debc`

## callees

- `0x1800371a8`
- `0x1800373f8`
- `0x18008679c`
- `0x1800aa560`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aa592`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aa592`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa5a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa5a0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aa615`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aa615`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800aa624`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800aa624`

## pseudocode

```c
void __fastcall Microsoft::Resources::CStringResolverInternal::~CStringResolverInternal(
        Microsoft::Resources::CStringResolverInternal *this,
        const struct std::nothrow_t *a2)
{
  Microsoft::Resources::Runtime::CContext *v3; // rcx
  void *v4; // rcx
  void *v5; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v7; // rcx
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  Microsoft::Resources::Runtime::CResourceManagerInternal *v10; // rcx

  v3 = (Microsoft::Resources::Runtime::CContext *)*((_QWORD *)this + 10);
  if ( v3 )
    Microsoft::Resources::Runtime::CContext::`scalar deleting destructor'(v3, (unsigned int)a2);
  v4 = (void *)*((_QWORD *)this + 11);
  if ( v4 )
    operator delete(v4, a2);
  v5 = (void *)*((_QWORD *)this + 4);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 56LL))(v7, 1);
  v8 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 1);
  if ( v8 )
    (**v8)(v8, 1);
  v9 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 6);
  if ( v9 )
    (**v9)(v9, 1);
  v10 = (Microsoft::Resources::Runtime::CResourceManagerInternal *)*((_QWORD *)this + 7);
  if ( v10 )
    Microsoft::Resources::Runtime::CResourceManagerInternal::`scalar deleting destructor'(v10, (unsigned int)a2);
  if ( *(_QWORD *)this )
    (***(void (__fastcall ****)(_QWORD, __int64))this)(*(_QWORD *)this, 1);
  if ( GetFileAttributesW((LPCWSTR)this + 56) != -1 )
    DeleteFileW((LPCWSTR)this + 56);
  *((_DWORD *)this + 18) = 0;
}

```

## disassembly

```asm
0x1800aa560  mov     [rsp+arg_0], rbx
0x1800aa565  push    rdi
0x1800aa566  sub     rsp, 20h
0x1800aa56a  mov     rbx, rcx
0x1800aa56d  mov     rcx, [rcx+50h]; this
0x1800aa571  test    rcx, rcx
0x1800aa574  jz      short loc_1800AA57B
0x1800aa576  call    ??_GCContext@Runtime@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::Runtime::CContext::`scalar deleting destructor'(uint)
0x1800aa57b  mov     rcx, [rbx+58h]; void *
0x1800aa57f  test    rcx, rcx
0x1800aa582  jz      short loc_1800AA589
0x1800aa584  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aa589  mov     rdi, [rbx+20h]
0x1800aa58d  test    rdi, rdi
0x1800aa590  jz      short loc_1800AA5A6
0x1800aa592  call    cs:__imp_GetProcessHeap
0x1800aa598  mov     r8, rdi; lpMem
0x1800aa59b  xor     edx, edx; dwFlags
0x1800aa59d  mov     rcx, rax; hHeap
0x1800aa5a0  call    cs:__imp_HeapFree
0x1800aa5a6  mov     rcx, [rbx+18h]
0x1800aa5aa  mov     edi, 1
0x1800aa5af  test    rcx, rcx
0x1800aa5b2  jz      short loc_1800AA5C2
0x1800aa5b4  mov     rax, [rcx]
0x1800aa5b7  mov     edx, edi
0x1800aa5b9  mov     rax, [rax+38h]
0x1800aa5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa5c2  mov     rcx, [rbx+8]
0x1800aa5c6  test    rcx, rcx
0x1800aa5c9  jz      short loc_1800AA5D8
0x1800aa5cb  mov     rax, [rcx]
0x1800aa5ce  mov     edx, edi
0x1800aa5d0  mov     rax, [rax]
0x1800aa5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa5d8  mov     rcx, [rbx+30h]
0x1800aa5dc  test    rcx, rcx
0x1800aa5df  jz      short loc_1800AA5EE
0x1800aa5e1  mov     rax, [rcx]
0x1800aa5e4  mov     edx, edi
0x1800aa5e6  mov     rax, [rax]
0x1800aa5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa5ee  mov     rcx, [rbx+38h]; this
0x1800aa5f2  test    rcx, rcx
0x1800aa5f5  jz      short loc_1800AA5FC
0x1800aa5f7  call    ??_GCResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::`scalar deleting destructor'(uint)
0x1800aa5fc  mov     rcx, [rbx]
0x1800aa5ff  test    rcx, rcx
0x1800aa602  jz      short loc_1800AA611
0x1800aa604  mov     rax, [rcx]
0x1800aa607  mov     edx, edi
0x1800aa609  mov     rax, [rax]
0x1800aa60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa611  lea     rcx, [rbx+70h]; lpFileName
0x1800aa615  call    cs:__imp_GetFileAttributesW
0x1800aa61b  cmp     eax, 0FFFFFFFFh
0x1800aa61e  jz      short loc_1800AA62A
0x1800aa620  lea     rcx, [rbx+70h]; lpFileName
0x1800aa624  call    cs:__imp_DeleteFileW
0x1800aa62a  mov     dword ptr [rbx+48h], 0
0x1800aa631  mov     rbx, [rsp+28h+arg_0]
0x1800aa636  add     rsp, 20h
0x1800aa63a  pop     rdi
0x1800aa63b  retn
```
