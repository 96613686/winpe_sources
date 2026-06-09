# WORK_QUEUE::ScheduleNewThreadCreation(void)

- ea: `0x180001e44`
- end: `0x180001ee0`
- name: `?ScheduleNewThreadCreation@WORK_QUEUE@@QEAAHXZ`
- size: `156`
- prototype: `__int64 __fastcall(WORK_QUEUE *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000240c`
- `0x180040fe0`

## callees

- `0x180001e44`
- `0x180001ee8`
- `0x1800411ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001e7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001e7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001ed6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001ed6`

## pseudocode

```c
__int64 __fastcall WORK_QUEUE::ScheduleNewThreadCreation(WORK_QUEUE *this)
{
  __int64 v1; // rsi
  unsigned int v3; // edi
  char *v5; // rax
  void *v6; // rbx

  v1 = *((int *)this + 14);
  if ( (_DWORD)v1 )
  {
    v5 = (char *)CoTaskMemAlloc(0x40u);
    v6 = v5;
    if ( v5 )
    {
      *((_QWORD *)v5 + 1) = v5 + 8;
      *((_QWORD *)v5 + 2) = 0;
      *((_QWORD *)v5 + 3) = 0;
      *((_QWORD *)v5 + 7) = this;
      v3 = 1;
      *((_DWORD *)v5 + 12) = 0;
      *((_QWORD *)v5 + 5) = v5;
      *((_QWORD *)v5 + 4) = WORK_QUEUE::DELAYED_THREAD_CREATION::StaticOnDelayedThreadCreationTimeout;
      if ( (int)TIMEOUT_ENTRY::TimeoutAfter((TIMEOUT_ENTRY *)v5, 10000 * v1) >= 0 )
        return v3;
      CoTaskMemFree(v6);
    }
    return 0;
  }
  return (unsigned int)WORK_QUEUE::StartNewThread(this);
}

```

## disassembly

```asm
0x180001e44  mov     [rsp+arg_0], rbx
0x180001e49  mov     [rsp+arg_8], rsi
0x180001e4e  push    rdi
0x180001e4f  sub     rsp, 20h
0x180001e53  movsxd  rsi, dword ptr [rcx+38h]
0x180001e57  mov     rdi, rcx
0x180001e5a  test    esi, esi
0x180001e5c  jnz     short loc_180001E77
0x180001e5e  call    ?StartNewThread@WORK_QUEUE@@QEAAHXZ; WORK_QUEUE::StartNewThread(void)
0x180001e63  mov     edi, eax
0x180001e65  mov     rbx, [rsp+28h+arg_0]
0x180001e6a  mov     eax, edi
0x180001e6c  mov     rsi, [rsp+28h+arg_8]
0x180001e71  add     rsp, 20h
0x180001e75  pop     rdi
0x180001e76  retn
0x180001e77  mov     ecx, 40h ; '@'; cb
0x180001e7c  call    cs:__imp_CoTaskMemAlloc
0x180001e82  mov     rbx, rax
0x180001e85  test    rax, rax
0x180001e88  jz      short loc_180001EDC
0x180001e8a  lea     rcx, [rax+8]
0x180001e8e  mov     [rcx], rcx
0x180001e91  mov     qword ptr [rcx+8], 0
0x180001e99  mov     qword ptr [rcx+10h], 0
0x180001ea1  mov     rcx, rbx; this
0x180001ea4  mov     [rax+38h], rdi
0x180001ea8  mov     edi, 1
0x180001ead  mov     dword ptr [rax+30h], 0
0x180001eb4  mov     [rax+28h], rax
0x180001eb8  lea     rax, ?StaticOnDelayedThreadCreationTimeout@DELAYED_THREAD_CREATION@WORK_QUEUE@@SAXPEAX@Z; WORK_QUEUE::DELAYED_THREAD_CREATION::StaticOnDelayedThreadCreationTimeout(void *)
0x180001ebf  imul    rdx, rsi, 2710h; __int64
0x180001ec6  mov     [rbx+20h], rax
0x180001eca  call    ?TimeoutAfter@TIMEOUT_ENTRY@@QEAAJ_J@Z; TIMEOUT_ENTRY::TimeoutAfter(__int64)
0x180001ecf  test    eax, eax
0x180001ed1  jns     short loc_180001E65
0x180001ed3  mov     rcx, rbx; pv
0x180001ed6  call    cs:__imp_CoTaskMemFree
0x180001edc  xor     edi, edi
0x180001ede  jmp     short loc_180001E65
```
