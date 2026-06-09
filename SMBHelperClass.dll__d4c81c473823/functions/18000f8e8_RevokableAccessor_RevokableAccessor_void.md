# RevokableAccessor::~RevokableAccessor(void)

- ea: `0x18000f8e8`
- end: `0x18000f967`
- name: `??1RevokableAccessor@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(RevokableAccessor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800051b4`

## callees

- `0x18000d3d8`
- `0x18000f8e8`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000f94c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000f94c`
- `KERNEL32!ReleaseMutex` at `0x18000f91b`
- `KERNEL32!ReleaseMutex` at `0x18000f933`
- `KERNEL32!ReleaseMutex` at `0x18000f91b`
- `KERNEL32!ReleaseMutex` at `0x18000f933`
- `KERNEL32!CloseHandle` at `0x18000f955`
- `KERNEL32!CloseHandle` at `0x18000f955`

## pseudocode

```c
void __fastcall RevokableAccessor::~RevokableAccessor(RevokableAccessor *this, __int64 a2, unsigned int a3)
{
  void **v4; // rbx
  HANDLE hMutex; // [rsp+30h] [rbp+8h] BYREF

  v4 = (void **)((char *)this + 32);
  if ( *((_DWORD *)this + 6) )
  {
    AutoMutex::AutoMutex((AutoMutex *)&hMutex, *v4, a3);
    **((_DWORD **)this + 1) = 1;
    ReleaseMutex(hMutex);
  }
  AutoMutex::AutoMutex((AutoMutex *)&hMutex, *v4, a3);
  ReleaseMutex(hMutex);
  if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)this + 2), 0xFFFFFFFF) == 1 )
  {
    operator delete[](*(void **)this);
    CloseHandle(*v4);
  }
}

```

## disassembly

```asm
0x18000f8e8  mov     [rsp+arg_8], rbx
0x18000f8ed  push    rdi
0x18000f8ee  sub     rsp, 20h
0x18000f8f2  mov     rdi, rcx
0x18000f8f5  lea     rbx, [rcx+20h]
0x18000f8f9  cmp     dword ptr [rcx+18h], 0
0x18000f8fd  jz      short loc_18000F921
0x18000f8ff  mov     rdx, [rbx]; void *
0x18000f902  lea     rcx, [rsp+28h+hMutex]; this
0x18000f907  call    ??0AutoMutex@@QEAA@PEAXK@Z; AutoMutex::AutoMutex(void *,ulong)
0x18000f90c  mov     rax, [rdi+8]
0x18000f910  mov     dword ptr [rax], 1
0x18000f916  mov     rcx, [rsp+28h+hMutex]; hMutex
0x18000f91b  call    cs:__imp_ReleaseMutex
0x18000f921  mov     rdx, [rbx]; void *
0x18000f924  lea     rcx, [rsp+28h+hMutex]; this
0x18000f929  call    ??0AutoMutex@@QEAA@PEAXK@Z; AutoMutex::AutoMutex(void *,ulong)
0x18000f92e  mov     rcx, [rsp+28h+hMutex]; hMutex
0x18000f933  call    cs:__imp_ReleaseMutex
0x18000f939  mov     rdx, [rdi+10h]
0x18000f93d  or      eax, 0FFFFFFFFh
0x18000f940  lock xadd [rdx], eax
0x18000f944  cmp     eax, 1
0x18000f947  jnz     short loc_18000F95C
0x18000f949  mov     rcx, [rdi]
0x18000f94c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000f952  mov     rcx, [rbx]; hObject
0x18000f955  call    cs:__imp_CloseHandle
0x18000f95b  nop
0x18000f95c  mov     rbx, [rsp+28h+arg_8]
0x18000f961  add     rsp, 20h
0x18000f965  pop     rdi
0x18000f966  retn
```
