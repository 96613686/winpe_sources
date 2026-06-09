# Windows::UI::Composition::BatchController::CreateBatchSet(Windows::UI::Composition::BatchSet * *,Windows::UI::Composition::CompositionBatch * *)

- ea: `0x18009f34c`
- end: `0x18009f413`
- name: `?CreateBatchSet@BatchController@Composition@UI@Windows@@AEAAXPEAPEAUBatchSet@234@PEAPEAVCompositionBatch@234@@Z`
- size: `199`
- prototype: `void __fastcall(Windows::UI::Composition::BatchController *__hidden this, struct Windows::UI::Composition::BatchSet **, struct Windows::UI::Composition::CompositionBatch **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800343d8`
- `0x180034590`

## callees

- `0x18009f34c`
- `0x1800ea11c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f3d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009f3d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f3c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009f3c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f370`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f3b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f370`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f3b2`

## pseudocode

```c
void __fastcall Windows::UI::Composition::BatchController::CreateBatchSet(
        Windows::UI::Composition::BatchController *this,
        struct Windows::UI::Composition::BatchSet **a2,
        struct Windows::UI::Composition::CompositionBatch **a3)
{
  unsigned int v6; // edi
  DWORD CurrentThreadId; // eax
  __int64 v8; // r9
  DWORD v9; // ebp
  HANDLE ProcessHeap; // rax
  struct Windows::UI::Composition::BatchSet *v11; // rax
  __int64 v12; // rdx
  __int64 i; // rcx

  *a2 = 0;
  *a3 = 0;
  v6 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v8 = *((_QWORD *)this + 4);
  if ( v8 )
  {
    do
    {
      if ( *(_DWORD *)(v8 + 152) == CurrentThreadId )
      {
        if ( !*a3 )
          *a3 = (struct Windows::UI::Composition::CompositionBatch *)v8;
        ++v6;
      }
      v8 = *(_QWORD *)(v8 + 208);
    }
    while ( v8 );
    if ( v6 > 1 )
    {
      *a2 = 0;
      v9 = GetCurrentThreadId();
      ProcessHeap = GetProcessHeap();
      v11 = (struct Windows::UI::Composition::BatchSet *)HeapAlloc(ProcessHeap, 0, 8LL * (v6 - 1) + 16);
      *a2 = v11;
      if ( !v11 )
        Microsoft::WRL2::FailFast::Do();
      *(_DWORD *)v11 = 1;
      v12 = 0;
      *((_DWORD *)v11 + 1) = v6;
      for ( i = *((_QWORD *)this + 4); i; i = *(_QWORD *)(i + 208) )
      {
        if ( *(_DWORD *)(i + 152) == v9 )
        {
          *((_QWORD *)v11 + v12 + 1) = i;
          v12 = (unsigned int)(v12 + 1);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18009f34c  push    rbx
0x18009f34e  push    rbp
0x18009f34f  push    rsi
0x18009f350  push    rdi
0x18009f351  push    r14
0x18009f353  sub     rsp, 20h
0x18009f357  mov     rbx, r8
0x18009f35a  mov     qword ptr [rdx], 0
0x18009f361  mov     r14, rdx
0x18009f364  mov     qword ptr [r8], 0
0x18009f36b  mov     rsi, rcx
0x18009f36e  xor     edi, edi
0x18009f370  call    cs:__imp_GetCurrentThreadId
0x18009f376  mov     r9, [rsi+20h]
0x18009f37a  test    r9, r9
0x18009f37d  jnz     short loc_18009F38A
0x18009f37f  add     rsp, 20h
0x18009f383  pop     r14
0x18009f385  pop     rdi
0x18009f386  pop     rsi
0x18009f387  pop     rbp
0x18009f388  pop     rbx
0x18009f389  retn
0x18009f38a  cmp     [r9+98h], eax
0x18009f391  jnz     short loc_18009F39E
0x18009f393  cmp     qword ptr [rbx], 0
0x18009f397  jnz     short loc_18009F39C
0x18009f399  mov     [rbx], r9
0x18009f39c  inc     edi
0x18009f39e  mov     r9, [r9+0D0h]
0x18009f3a5  test    r9, r9
0x18009f3a8  jnz     short loc_18009F38A
0x18009f3aa  cmp     edi, 1
0x18009f3ad  jbe     short loc_18009F37F
0x18009f3af  mov     [r14], r9
0x18009f3b2  call    cs:__imp_GetCurrentThreadId
0x18009f3b8  lea     ecx, [rdi-1]
0x18009f3bb  mov     ebp, eax
0x18009f3bd  lea     rbx, ds:10h[rcx*8]
0x18009f3c5  call    cs:__imp_GetProcessHeap
0x18009f3cb  mov     r8, rbx; dwBytes
0x18009f3ce  xor     edx, edx; dwFlags
0x18009f3d0  mov     rcx, rax; hHeap
0x18009f3d3  call    cs:__imp_HeapAlloc
0x18009f3d9  mov     [r14], rax
0x18009f3dc  test    rax, rax
0x18009f3df  jz      short loc_18009F40D
0x18009f3e1  mov     dword ptr [rax], 1
0x18009f3e7  xor     edx, edx
0x18009f3e9  mov     [rax+4], edi
0x18009f3ec  mov     rcx, [rsi+20h]
0x18009f3f0  test    rcx, rcx
0x18009f3f3  jz      short loc_18009F37F
0x18009f3f5  cmp     [rcx+98h], ebp
0x18009f3fb  jnz     short loc_18009F404
0x18009f3fd  mov     [rax+rdx*8+8], rcx
0x18009f402  inc     edx
0x18009f404  mov     rcx, [rcx+0D0h]
0x18009f40b  jmp     short loc_18009F3F0
0x18009f40d  call    ?Do@FailFast@WRL2@Microsoft@@SAXXZ; Microsoft::WRL2::FailFast::Do(void)
```
