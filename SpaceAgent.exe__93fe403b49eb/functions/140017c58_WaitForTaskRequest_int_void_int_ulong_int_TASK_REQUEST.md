# WaitForTaskRequest(int,void *,int *,ulong *,int *,TASK_REQUEST * *)

- ea: `0x140017c58`
- end: `0x140017d6a`
- name: `?WaitForTaskRequest@@YAHHPEAXPEAHPEAK1PEAPEAUTASK_REQUEST@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(__int64, void *, int *, unsigned int *, struct TASK_PAYLOAD *, struct TASK_REQUEST **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140002b98`

## callees

- `0x140017498`
- `0x1400178d0`
- `0x140017b08`
- `0x140017c58`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140017c94`
- `KERNEL32!EnterCriticalSection` at `0x140017c94`
- `KERNEL32!LeaveCriticalSection` at `0x140017d0f`
- `KERNEL32!LeaveCriticalSection` at `0x140017d0f`
- `KERNEL32!HeapFree` at `0x140017d31`
- `KERNEL32!HeapFree` at `0x140017d31`
- `KERNEL32!SetLastError` at `0x140017cfa`
- `KERNEL32!SetLastError` at `0x140017d4d`
- `KERNEL32!SetLastError` at `0x140017cfa`
- `KERNEL32!SetLastError` at `0x140017d4d`
- `KERNEL32!GetLastError` at `0x140017d00`
- `KERNEL32!GetLastError` at `0x140017d00`

## pseudocode

```c
__int64 __fastcall WaitForTaskRequest(
        __int64 a1,
        void *a2,
        int *a3,
        unsigned int *a4,
        struct TASK_PAYLOAD *a5,
        struct TASK_REQUEST **a6)
{
  struct TASK_REQUEST *v6; // rbx
  int v10; // ecx
  unsigned int v11; // eax
  int v12; // r14d
  unsigned int v13; // edi
  void *TaskServerHandle; // rax
  HANDLE v15; // r8
  unsigned int v16; // eax
  DWORD LastError; // esi
  int v19; // [rsp+60h] [rbp+40h] BYREF
  int v20; // [rsp+70h] [rbp+50h] BYREF
  unsigned int v21; // [rsp+78h] [rbp+58h] BYREF

  v6 = 0;
  v19 = 0;
  a5 = 0;
  v21 = 0;
  v20 = 0;
  EnterCriticalSection(&TaskLock);
  v11 = WaitForTaskClient(v10, &v19, &v21, &v20);
  v12 = v19;
  v13 = v11;
  if ( v11 )
  {
    if ( !v19 && !v20 )
    {
      GetTaskServerHandle(1u);
      TaskServerHandle = GetTaskServerHandle(0);
      v16 = ReadTaskPipe(a2, TaskServerHandle, v15, &a5);
      v6 = a5;
      v13 = v16;
      if ( v16 )
      {
        if ( a5 && *(_QWORD *)a5 < 0x10u )
        {
          v13 = 0;
          SetLastError(0x18u);
        }
      }
    }
  }
  LastError = GetLastError();
  LeaveCriticalSection(&TaskLock);
  *a4 = v21;
  *a3 = v12;
  if ( v13 )
  {
    *a6 = v6;
  }
  else
  {
    if ( v6 )
      HeapFree(a2, 0, v6);
    *a6 = 0;
  }
  SetLastError(LastError);
  return v13;
}

```

## disassembly

```asm
0x140017c58  mov     [rsp-38h+arg_8], rbx
0x140017c5d  mov     [rsp-38h+arg_0], ecx
0x140017c61  push    rbp
0x140017c62  push    rsi
0x140017c63  push    rdi
0x140017c64  push    r12
0x140017c66  push    r13
0x140017c68  push    r14
0x140017c6a  push    r15
0x140017c6c  mov     rbp, rsp
0x140017c6f  sub     rsp, 20h
0x140017c73  xor     esi, esi
0x140017c75  lea     rcx, ?TaskLock@@3UAUTOINIT_CRITICAL_SECTION@@A; lpCriticalSection
0x140017c7c  mov     ebx, esi
0x140017c7e  mov     [rbp+arg_0], esi
0x140017c81  mov     [rbp+arg_20], rbx
0x140017c85  mov     r12, r9
0x140017c88  mov     r13, r8
0x140017c8b  mov     [rbp+arg_18], esi
0x140017c8e  mov     r15, rdx
0x140017c91  mov     [rbp+arg_10], esi
0x140017c94  call    cs:__imp_EnterCriticalSection
0x140017c9a  lea     r9, [rbp+arg_10]; int *
0x140017c9e  lea     r8, [rbp+arg_18]; unsigned int *
0x140017ca2  lea     rdx, [rbp+arg_0]; int *
0x140017ca6  call    ?WaitForTaskClient@@YAHHPEAHPEAK0@Z; WaitForTaskClient(int,int *,ulong *,int *)
0x140017cab  mov     r14d, [rbp+arg_0]
0x140017caf  mov     edi, eax
0x140017cb1  test    eax, eax
0x140017cb3  jz      short loc_140017D00
0x140017cb5  test    r14d, r14d
0x140017cb8  jnz     short loc_140017D00
0x140017cba  cmp     [rbp+arg_10], esi
0x140017cbd  jnz     short loc_140017D00
0x140017cbf  lea     ecx, [rsi+1]; unsigned int
0x140017cc2  call    ?GetTaskServerHandle@@YAPEAXI@Z; GetTaskServerHandle(uint)
0x140017cc7  xor     ecx, ecx; unsigned int
0x140017cc9  mov     r8, rax
0x140017ccc  call    ?GetTaskServerHandle@@YAPEAXI@Z; GetTaskServerHandle(uint)
0x140017cd1  mov     rdx, rax; hFile
0x140017cd4  lea     r9, [rbp+arg_20]; struct TASK_PAYLOAD **
0x140017cd8  mov     rcx, r15; hHeap
0x140017cdb  call    ?ReadTaskPipe@@YAHPEAX00PEAPEAUTASK_PAYLOAD@@@Z; ReadTaskPipe(void *,void *,void *,TASK_PAYLOAD * *)
0x140017ce0  mov     rbx, [rbp+arg_20]
0x140017ce4  mov     edi, eax
0x140017ce6  test    eax, eax
0x140017ce8  jz      short loc_140017D00
0x140017cea  test    rbx, rbx
0x140017ced  jz      short loc_140017D00
0x140017cef  cmp     qword ptr [rbx], 10h
0x140017cf3  jnb     short loc_140017D00
0x140017cf5  lea     ecx, [rsi+18h]; dwErrCode
0x140017cf8  mov     edi, esi
0x140017cfa  call    cs:__imp_SetLastError
0x140017d00  call    cs:__imp_GetLastError
0x140017d06  lea     rcx, ?TaskLock@@3UAUTOINIT_CRITICAL_SECTION@@A; lpCriticalSection
0x140017d0d  mov     esi, eax
0x140017d0f  call    cs:__imp_LeaveCriticalSection
0x140017d15  mov     ecx, [rbp+arg_18]
0x140017d18  mov     [r12], ecx
0x140017d1c  mov     [r13+0], r14d
0x140017d20  test    edi, edi
0x140017d22  jnz     short loc_140017D44
0x140017d24  test    rbx, rbx
0x140017d27  jz      short loc_140017D37
0x140017d29  mov     r8, rbx; lpMem
0x140017d2c  xor     edx, edx; dwFlags
0x140017d2e  mov     rcx, r15; hHeap
0x140017d31  call    cs:__imp_HeapFree
0x140017d37  mov     rax, [rbp+arg_28]
0x140017d3b  mov     qword ptr [rax], 0
0x140017d42  jmp     short loc_140017D4B
0x140017d44  mov     rax, [rbp+arg_28]
0x140017d48  mov     [rax], rbx
0x140017d4b  mov     ecx, esi; dwErrCode
0x140017d4d  call    cs:__imp_SetLastError
0x140017d53  mov     rbx, [rsp+20h+arg_8]
0x140017d58  mov     eax, edi
0x140017d5a  add     rsp, 20h
0x140017d5e  pop     r15
0x140017d60  pop     r14
0x140017d62  pop     r13
0x140017d64  pop     r12
0x140017d66  pop     rdi
0x140017d67  pop     rsi
0x140017d68  pop     rbp
0x140017d69  retn
```
