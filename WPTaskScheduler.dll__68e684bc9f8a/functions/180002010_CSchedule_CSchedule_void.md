# CSchedule::~CSchedule(void)

- ea: `0x180002010`
- end: `0x18000207d`
- name: `??1CSchedule@@QEAA@XZ`
- size: `109`
- prototype: `void __fastcall(void **this)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001ea0`
- `0x180002d90`
- `0x180005d40`

## callees

- `0x180002084`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000206b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000206b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002021`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002021`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002034`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002034`

## pseudocode

```c
void __fastcall CSchedule::~CSchedule(void **this)
{
  void **v1; // rbx

  v1 = this;
  operator delete[](this[4]);
  v1[4] = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 28));
  v1 += 35;
  std::_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>::_Erase(
    v1,
    *((_QWORD *)*v1 + 1));
  *((_QWORD *)*v1 + 1) = *v1;
  *(_QWORD *)*v1 = *v1;
  *((_QWORD *)*v1 + 2) = *v1;
  v1[1] = 0;
  operator delete(*v1);
}

```

## disassembly

```asm
0x180002010  mov     [rsp+arg_0], rbx
0x180002015  push    rdi
0x180002016  sub     rsp, 20h
0x18000201a  mov     rbx, rcx
0x18000201d  mov     rcx, [rcx+20h]
0x180002021  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002027  xor     edi, edi
0x180002029  mov     [rbx+20h], rdi
0x18000202d  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180002034  call    cs:__imp_DeleteCriticalSection
0x18000203a  add     rbx, 118h
0x180002041  mov     rdx, [rbx]
0x180002044  mov     rdx, [rdx+8]
0x180002048  mov     rcx, rbx
0x18000204b  call    ?_Erase@?$_Tree@V?$_Tmap_traits@_KPEAU_EVENT_SUBSCRIPTION@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>::_Erase(std::_Tree_node<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>,void *> *)
0x180002050  mov     rax, [rbx]
0x180002053  mov     [rax+8], rax
0x180002057  mov     rax, [rbx]
0x18000205a  mov     [rax], rax
0x18000205d  mov     rax, [rbx]
0x180002060  mov     [rax+10h], rax
0x180002064  mov     [rbx+8], rdi
0x180002068  mov     rcx, [rbx]
0x18000206b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002071  nop
0x180002072  mov     rbx, [rsp+28h+arg_0]
0x180002077  add     rsp, 20h
0x18000207b  pop     rdi
0x18000207c  retn
```
