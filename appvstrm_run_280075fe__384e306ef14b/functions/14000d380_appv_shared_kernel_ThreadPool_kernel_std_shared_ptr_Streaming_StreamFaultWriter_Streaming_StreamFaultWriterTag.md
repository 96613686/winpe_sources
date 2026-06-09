# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::QueueWorkItem(kernel_std::shared_ptr<Streaming::StreamFaultWriter> &)

- ea: `0x14000d380`
- end: `0x14000d4b6`
- name: `?QueueWorkItem@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAAJAEAV?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d254`

## callees

- `0x14000d380`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d3e9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d47f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d3e9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d47f`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000d49e`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000d49e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d3dd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d473`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d3dd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d473`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000d3b1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000d3b1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d39e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d39e`
- `ntoskrnl!ExAllocatePool2` at `0x14000d40f`
- `ntoskrnl!ExAllocatePool2` at `0x14000d40f`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::QueueWorkItem(
        __int64 a1,
        _QWORD *a2)
{
  bool v2; // si
  struct _ERESOURCE *v5; // rcx
  int v6; // edi
  _QWORD *Pool2; // rax
  _QWORD *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rcx
  struct _ERESOURCE *v11; // rcx

  v2 = 0;
  if ( *(_QWORD *)(a1 + 48) )
  {
    KeEnterCriticalRegion();
    v2 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 48), 1u) == 1;
  }
  if ( *(_DWORD *)a1 < 0xFFFFu )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(256, 32, 2003199603);
    v8 = Pool2;
    if ( Pool2 )
    {
      *Pool2 = *a2;
      v9 = a2[1];
      v8[1] = v9;
      if ( v9 )
        _InterlockedAdd((volatile signed __int32 *)(v9 + 8), 1u);
      v8[3] = v8;
      v8[2] = v8;
      ++*(_DWORD *)a1;
      v10 = *(_QWORD *)(a1 + 24);
      v6 = 0;
      v8[3] = a1 + 8;
      v8[2] = v10;
      *(_QWORD *)(v10 + 24) = v8;
      *(_QWORD *)(a1 + 24) = v8;
    }
    else
    {
      v6 = -1073741670;
    }
    if ( v2 )
    {
      v11 = *(struct _ERESOURCE **)(a1 + 48);
      if ( v11 )
      {
        ExReleaseResourceLite(v11);
        KeLeaveCriticalRegion();
      }
    }
    if ( v6 >= 0 )
      KeReleaseSemaphore((PRKSEMAPHORE)(a1 + 144), 0, 1, 0);
  }
  else
  {
    if ( v2 )
    {
      v5 = *(struct _ERESOURCE **)(a1 + 48);
      if ( v5 )
      {
        ExReleaseResourceLite(v5);
        KeLeaveCriticalRegion();
      }
    }
    return (unsigned int)-2147483622;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000d380  push    rbx
0x14000d382  push    rbp
0x14000d383  push    rsi
0x14000d384  push    rdi
0x14000d385  sub     rsp, 28h
0x14000d389  xor     sil, sil
0x14000d38c  mov     rdi, rdx
0x14000d38f  cmp     qword ptr [rcx+30h], 0
0x14000d394  mov     rbx, rcx
0x14000d397  mov     ebp, 1
0x14000d39c  jz      short loc_14000D3C7
0x14000d39e  call    cs:__imp_KeEnterCriticalRegion
0x14000d3a5  nop     dword ptr [rax+rax+00h]
0x14000d3aa  mov     rcx, [rbx+30h]; Resource
0x14000d3ae  mov     dl, bpl; Wait
0x14000d3b1  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000d3b8  nop     dword ptr [rax+rax+00h]
0x14000d3bd  cmp     al, bpl
0x14000d3c0  movzx   esi, sil
0x14000d3c4  cmovz   esi, ebp
0x14000d3c7  cmp     dword ptr [rbx], 0FFFFh
0x14000d3cd  jb      short loc_14000D3FF
0x14000d3cf  test    sil, sil
0x14000d3d2  jz      short loc_14000D3F5
0x14000d3d4  mov     rcx, [rbx+30h]; Resource
0x14000d3d8  test    rcx, rcx
0x14000d3db  jz      short loc_14000D3F5
0x14000d3dd  call    cs:__imp_ExReleaseResourceLite
0x14000d3e4  nop     dword ptr [rax+rax+00h]
0x14000d3e9  call    cs:__imp_KeLeaveCriticalRegion
0x14000d3f0  nop     dword ptr [rax+rax+00h]
0x14000d3f5  mov     edi, 8000001Ah
0x14000d3fa  jmp     loc_14000D4AA
0x14000d3ff  mov     edx, 20h ; ' '
0x14000d404  mov     ecx, 100h
0x14000d409  mov     r8d, 77666673h
0x14000d40f  call    cs:__imp_ExAllocatePool2
0x14000d416  nop     dword ptr [rax+rax+00h]
0x14000d41b  mov     rdx, rax
0x14000d41e  test    rax, rax
0x14000d421  jz      short loc_14000D460
0x14000d423  mov     rcx, [rdi]
0x14000d426  mov     [rax], rcx
0x14000d429  mov     rax, [rdi+8]
0x14000d42d  mov     [rdx+8], rax
0x14000d431  test    rax, rax
0x14000d434  jz      short loc_14000D43A
0x14000d436  lock add [rax+8], ebp
0x14000d43a  mov     [rdx+18h], rdx
0x14000d43e  lea     rax, [rbx+8]
0x14000d442  mov     [rdx+10h], rdx
0x14000d446  add     [rbx], ebp
0x14000d448  mov     rcx, [rax+10h]
0x14000d44c  xor     edi, edi
0x14000d44e  mov     [rdx+18h], rax
0x14000d452  mov     [rdx+10h], rcx
0x14000d456  mov     [rcx+18h], rdx
0x14000d45a  mov     [rbx+18h], rdx
0x14000d45e  jmp     short loc_14000D465
0x14000d460  mov     edi, 0C000009Ah
0x14000d465  test    sil, sil
0x14000d468  jz      short loc_14000D48B
0x14000d46a  mov     rcx, [rbx+30h]; Resource
0x14000d46e  test    rcx, rcx
0x14000d471  jz      short loc_14000D48B
0x14000d473  call    cs:__imp_ExReleaseResourceLite
0x14000d47a  nop     dword ptr [rax+rax+00h]
0x14000d47f  call    cs:__imp_KeLeaveCriticalRegion
0x14000d486  nop     dword ptr [rax+rax+00h]
0x14000d48b  test    edi, edi
0x14000d48d  js      short loc_14000D4AA
0x14000d48f  lea     rcx, [rbx+90h]; Semaphore
0x14000d496  xor     r9d, r9d; Wait
0x14000d499  mov     r8d, ebp; Adjustment
0x14000d49c  xor     edx, edx; Increment
0x14000d49e  call    cs:__imp_KeReleaseSemaphore
0x14000d4a5  nop     dword ptr [rax+rax+00h]
0x14000d4aa  mov     eax, edi
0x14000d4ac  add     rsp, 28h
0x14000d4b0  pop     rdi
0x14000d4b1  pop     rsi
0x14000d4b2  pop     rbp
0x14000d4b3  pop     rbx
0x14000d4b4  retn
```
