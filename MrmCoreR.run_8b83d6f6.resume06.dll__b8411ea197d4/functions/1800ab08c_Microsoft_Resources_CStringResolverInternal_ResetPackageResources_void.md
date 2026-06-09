# Microsoft::Resources::CStringResolverInternal::_ResetPackageResources(void)

- ea: `0x1800ab08c`
- end: `0x1800ab12f`
- name: `?_ResetPackageResources@CStringResolverInternal@Resources@Microsoft@@AEAAXXZ`
- size: `163`
- prototype: `void __fastcall(Microsoft::Resources::CStringResolverInternal *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800aac98`

## callees

- `0x1800371a8`
- `0x1800ab08c`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab0e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab0e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab0f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab0f6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ab108`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ab108`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ab117`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ab117`

## pseudocode

```c
void __fastcall Microsoft::Resources::CStringResolverInternal::_ResetPackageResources(
        Microsoft::Resources::CStringResolverInternal *this,
        unsigned int a2)
{
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  Microsoft::Resources::Runtime::CResourceManagerInternal *v4; // rcx
  void *v5; // rdi
  HANDLE ProcessHeap; // rax

  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 6);
  if ( v3 )
  {
    (**v3)(v3, 1);
    *((_QWORD *)this + 6) = 0;
  }
  v4 = (Microsoft::Resources::Runtime::CResourceManagerInternal *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    Microsoft::Resources::Runtime::CResourceManagerInternal::`scalar deleting destructor'(v4, a2);
    *((_QWORD *)this + 7) = 0;
  }
  if ( *((_QWORD *)this + 8) )
    *((_QWORD *)this + 8) = 0;
  v5 = (void *)*((_QWORD *)this + 4);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
    *((_QWORD *)this + 4) = 0;
  }
  if ( GetFileAttributesW((LPCWSTR)this + 56) != -1 )
    DeleteFileW((LPCWSTR)this + 56);
  *((_DWORD *)this + 18) = 0;
}

```

## disassembly

```asm
0x1800ab08c  mov     [rsp+arg_0], rbx
0x1800ab091  push    rdi
0x1800ab092  sub     rsp, 20h
0x1800ab096  mov     rbx, rcx
0x1800ab099  mov     rcx, [rcx+30h]
0x1800ab09d  test    rcx, rcx
0x1800ab0a0  jz      short loc_1800AB0BA
0x1800ab0a2  mov     rax, [rcx]
0x1800ab0a5  mov     edx, 1
0x1800ab0aa  mov     rax, [rax]
0x1800ab0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab0b2  mov     qword ptr [rbx+30h], 0
0x1800ab0ba  mov     rcx, [rbx+38h]; this
0x1800ab0be  test    rcx, rcx
0x1800ab0c1  jz      short loc_1800AB0D0
0x1800ab0c3  call    ??_GCResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::`scalar deleting destructor'(uint)
0x1800ab0c8  mov     qword ptr [rbx+38h], 0
0x1800ab0d0  cmp     qword ptr [rbx+40h], 0
0x1800ab0d5  jz      short loc_1800AB0DF
0x1800ab0d7  mov     qword ptr [rbx+40h], 0
0x1800ab0df  mov     rdi, [rbx+20h]
0x1800ab0e3  test    rdi, rdi
0x1800ab0e6  jz      short loc_1800AB104
0x1800ab0e8  call    cs:__imp_GetProcessHeap
0x1800ab0ee  mov     r8, rdi; lpMem
0x1800ab0f1  xor     edx, edx; dwFlags
0x1800ab0f3  mov     rcx, rax; hHeap
0x1800ab0f6  call    cs:__imp_HeapFree
0x1800ab0fc  mov     qword ptr [rbx+20h], 0
0x1800ab104  lea     rcx, [rbx+70h]; lpFileName
0x1800ab108  call    cs:__imp_GetFileAttributesW
0x1800ab10e  cmp     eax, 0FFFFFFFFh
0x1800ab111  jz      short loc_1800AB11D
0x1800ab113  lea     rcx, [rbx+70h]; lpFileName
0x1800ab117  call    cs:__imp_DeleteFileW
0x1800ab11d  mov     dword ptr [rbx+48h], 0
0x1800ab124  mov     rbx, [rsp+28h+arg_0]
0x1800ab129  add     rsp, 20h
0x1800ab12d  pop     rdi
0x1800ab12e  retn
```
