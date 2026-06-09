# ATL::CComObject<CGenericEnum>::`vector deleting destructor'(uint)

- ea: `0x18000b760`
- end: `0x18000b830`
- name: `??_E?$CComObject@VCGenericEnum@@@ATL@@UEAAPEAXI@Z`
- size: `208`
- prototype: `char *__fastcall(char *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000b760`
- `0x18000b840`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b7f1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b7f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b7a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b7b4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b7e2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b7e2`

## pseudocode

```c
char *__fastcall ATL::CComObject<CGenericEnum>::`vector deleting destructor'(char *a1, char a2)
{
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  int v7; // ebp
  __int64 i; // rbx
  __int64 v9; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<CGenericEnum>::`vftable';
  *((_DWORD *)a1 + 2) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( *((_QWORD *)a1 + 8) )
  {
    v7 = *((_DWORD *)a1 + 18);
    for ( i = 0; (int)i < v7; i = (unsigned int)(i + 1) )
    {
      v9 = *(_QWORD *)(*((_QWORD *)a1 + 8) + 8 * i);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  v4 = (void *)*((_QWORD *)a1 + 8);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *((_QWORD *)a1 + 8) = 0;
    *((_QWORD *)a1 + 9) = 0;
  }
  CDynamicArray<IUnknown *>::RemoveAll(a1 + 64);
  if ( a1[56] )
  {
    a1[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000b760  push    rbx
0x18000b762  push    rbp
0x18000b763  push    rsi
0x18000b764  push    rdi
0x18000b765  push    r14
0x18000b767  sub     rsp, 20h
0x18000b76b  mov     r14d, edx
0x18000b76e  mov     rsi, rcx
0x18000b771  lea     rax, ??_7?$CComObject@VCGenericEnum@@@ATL@@6B@; const ATL::CComObject<CGenericEnum>::`vftable'
0x18000b778  mov     [rcx], rax
0x18000b77b  mov     dword ptr [rcx+8], 0C0000001h
0x18000b782  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b789  mov     rax, [rcx]
0x18000b78c  mov     rax, [rax+10h]
0x18000b790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b795  nop
0x18000b796  cmp     qword ptr [rsi+40h], 0
0x18000b79b  jnz     short loc_18000B805
0x18000b79d  mov     rbx, [rsi+40h]
0x18000b7a1  test    rbx, rbx
0x18000b7a4  jz      short loc_18000B7CA
0x18000b7a6  call    cs:__imp_GetProcessHeap
0x18000b7ac  mov     r8, rbx; lpMem
0x18000b7af  xor     edx, edx; dwFlags
0x18000b7b1  mov     rcx, rax; hHeap
0x18000b7b4  call    cs:__imp_HeapFree
0x18000b7ba  mov     qword ptr [rsi+40h], 0
0x18000b7c2  mov     qword ptr [rsi+48h], 0
0x18000b7ca  lea     rcx, [rsi+40h]
0x18000b7ce  call    ?RemoveAll@?$CDynamicArray@PEAUIUnknown@@@@QEAAXXZ; CDynamicArray<IUnknown *>::RemoveAll(void)
0x18000b7d3  nop
0x18000b7d4  lea     rcx, [rsi+10h]; lpCriticalSection
0x18000b7d8  cmp     byte ptr [rcx+28h], 0
0x18000b7dc  jz      short loc_18000B7E8
0x18000b7de  mov     byte ptr [rcx+28h], 0
0x18000b7e2  call    cs:__imp_DeleteCriticalSection
0x18000b7e8  test    r14b, 1
0x18000b7ec  jz      short loc_18000B7F7
0x18000b7ee  mov     rcx, rsi
0x18000b7f1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b7f7  mov     rax, rsi
0x18000b7fa  add     rsp, 20h
0x18000b7fe  pop     r14
0x18000b800  pop     rdi
0x18000b801  pop     rsi
0x18000b802  pop     rbp
0x18000b803  pop     rbx
0x18000b804  retn
0x18000b805  mov     ebp, [rsi+48h]
0x18000b808  xor     ebx, ebx
0x18000b80a  test    ebp, ebp
0x18000b80c  jle     short loc_18000B79D
0x18000b80e  xchg    ax, ax
0x18000b810  mov     rax, [rsi+40h]
0x18000b814  mov     rcx, [rax+rbx*8]
0x18000b818  mov     rax, [rcx]
0x18000b81b  mov     rax, [rax+10h]
0x18000b81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b824  inc     ebx
0x18000b826  cmp     ebx, ebp
0x18000b828  jl      short loc_18000B810
0x18000b82a  jmp     loc_18000B79D
```
