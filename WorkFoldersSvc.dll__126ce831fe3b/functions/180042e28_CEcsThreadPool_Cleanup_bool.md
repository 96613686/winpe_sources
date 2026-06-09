# CEcsThreadPool::Cleanup(bool)

- ea: `0x180042e28`
- end: `0x180042ebf`
- name: `?Cleanup@CEcsThreadPool@@QEAAX_N@Z`
- size: `151`
- prototype: `void __fastcall(CEcsThreadPool *__hidden this, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800429b4`
- `0x18004414c`

## callees

- `0x180007e10`
- `0x180042e28`

## import_xrefs

- `KERNEL32!CloseThreadpool` at `0x180042e8b`
- `KERNEL32!CloseThreadpool` at `0x180042e8b`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180042e75`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180042e75`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180042e6b`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180042e6b`

## string_xrefs

- `0x180042e46`: `CEcsThreadPool::Cleanup`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CEcsThreadPool::Cleanup(CEcsThreadPool *this)
{
  struct _TP_CLEANUP_GROUP *v2; // rcx
  _DWORD v3[2]; // [rsp+20h] [rbp-28h] BYREF
  char v4; // [rsp+28h] [rbp-20h]
  const char *v5; // [rsp+30h] [rbp-18h]
  __int64 v6; // [rsp+38h] [rbp-10h]

  v3[0] = 0;
  v3[1] = 110;
  v4 = 0;
  v5 = "CEcsThreadPool::Cleanup";
  v6 = 0;
  v2 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    CloseThreadpoolCleanupGroupMembers(v2, 1, 0);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  if ( *(_QWORD *)this )
  {
    CloseThreadpool(*(PTP_POOL *)this);
    *(_QWORD *)this = 0;
  }
  *(_OWORD *)((char *)this + 88) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  *(_OWORD *)((char *)this + 120) = 0;
  *(_OWORD *)((char *)this + 136) = 0;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)v3);
}

```

## disassembly

```asm
0x180042e28  push    rbx
0x180042e2a  sub     rsp, 40h
0x180042e2e  mov     rbx, rcx
0x180042e31  mov     [rsp+48h+var_28], 0
0x180042e39  mov     [rsp+48h+var_24], 6Eh ; 'n'
0x180042e41  mov     [rsp+48h+var_20], 0
0x180042e46  lea     rax, aCecsthreadpool_2; "CEcsThreadPool::Cleanup"
0x180042e4d  mov     [rsp+48h+var_18], rax
0x180042e52  mov     [rsp+48h+var_10], 0
0x180042e5b  mov     rcx, [rcx+8]; ptpcg
0x180042e5f  test    rcx, rcx
0x180042e62  jz      short loc_180042E83
0x180042e64  xor     r8d, r8d; pvCleanupContext
0x180042e67  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180042e6b  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180042e71  mov     rcx, [rbx+8]; ptpcg
0x180042e75  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180042e7b  mov     qword ptr [rbx+8], 0
0x180042e83  mov     rcx, [rbx]; ptpp
0x180042e86  test    rcx, rcx
0x180042e89  jz      short loc_180042E98
0x180042e8b  call    cs:__imp_CloseThreadpool
0x180042e91  mov     qword ptr [rbx], 0
0x180042e98  xorps   xmm0, xmm0
0x180042e9b  movups  xmmword ptr [rbx+58h], xmm0
0x180042e9f  movups  xmmword ptr [rbx+68h], xmm0
0x180042ea3  movups  xmmword ptr [rbx+78h], xmm0
0x180042ea7  movups  xmmword ptr [rbx+88h], xmm0
0x180042eae  lea     rcx, [rsp+48h+var_28]; this
0x180042eb3  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180042eb8  nop
0x180042eb9  add     rsp, 40h
0x180042ebd  pop     rbx
0x180042ebe  retn
```
