# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::QueueWorkItem(kernel_std::shared_ptr<Streaming::WriteFault> &)

- ea: `0x14000e46c`
- end: `0x14000e5a2`
- name: `?QueueWorkItem@?$ThreadPool@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAAJAEAV?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000de2c`

## callees

- `0x14000e46c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e4d5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e56b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e4d5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e56b`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000e58a`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000e58a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e4c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e55f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e4c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e55f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000e49d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000e49d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e48a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e48a`
- `ntoskrnl!ExAllocatePool2` at `0x14000e4fb`
- `ntoskrnl!ExAllocatePool2` at `0x14000e4fb`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::QueueWorkItem(
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
    Pool2 = (_QWORD *)ExAllocatePool2(256, 32, 1886873203);
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
0x14000e46c  push    rbx
0x14000e46e  push    rbp
0x14000e46f  push    rsi
0x14000e470  push    rdi
0x14000e471  sub     rsp, 28h
0x14000e475  xor     sil, sil
0x14000e478  mov     rdi, rdx
0x14000e47b  cmp     qword ptr [rcx+30h], 0
0x14000e480  mov     rbx, rcx
0x14000e483  mov     ebp, 1
0x14000e488  jz      short loc_14000E4B3
0x14000e48a  call    cs:__imp_KeEnterCriticalRegion
0x14000e491  nop     dword ptr [rax+rax+00h]
0x14000e496  mov     rcx, [rbx+30h]; Resource
0x14000e49a  mov     dl, bpl; Wait
0x14000e49d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000e4a4  nop     dword ptr [rax+rax+00h]
0x14000e4a9  cmp     al, bpl
0x14000e4ac  movzx   esi, sil
0x14000e4b0  cmovz   esi, ebp
0x14000e4b3  cmp     dword ptr [rbx], 0FFFFh
0x14000e4b9  jb      short loc_14000E4EB
0x14000e4bb  test    sil, sil
0x14000e4be  jz      short loc_14000E4E1
0x14000e4c0  mov     rcx, [rbx+30h]; Resource
0x14000e4c4  test    rcx, rcx
0x14000e4c7  jz      short loc_14000E4E1
0x14000e4c9  call    cs:__imp_ExReleaseResourceLite
0x14000e4d0  nop     dword ptr [rax+rax+00h]
0x14000e4d5  call    cs:__imp_KeLeaveCriticalRegion
0x14000e4dc  nop     dword ptr [rax+rax+00h]
0x14000e4e1  mov     edi, 8000001Ah
0x14000e4e6  jmp     loc_14000E596
0x14000e4eb  mov     edx, 20h ; ' '
0x14000e4f0  mov     ecx, 100h
0x14000e4f5  mov     r8d, 70776673h
0x14000e4fb  call    cs:__imp_ExAllocatePool2
0x14000e502  nop     dword ptr [rax+rax+00h]
0x14000e507  mov     rdx, rax
0x14000e50a  test    rax, rax
0x14000e50d  jz      short loc_14000E54C
0x14000e50f  mov     rcx, [rdi]
0x14000e512  mov     [rax], rcx
0x14000e515  mov     rax, [rdi+8]
0x14000e519  mov     [rdx+8], rax
0x14000e51d  test    rax, rax
0x14000e520  jz      short loc_14000E526
0x14000e522  lock add [rax+8], ebp
0x14000e526  mov     [rdx+18h], rdx
0x14000e52a  lea     rax, [rbx+8]
0x14000e52e  mov     [rdx+10h], rdx
0x14000e532  add     [rbx], ebp
0x14000e534  mov     rcx, [rax+10h]
0x14000e538  xor     edi, edi
0x14000e53a  mov     [rdx+18h], rax
0x14000e53e  mov     [rdx+10h], rcx
0x14000e542  mov     [rcx+18h], rdx
0x14000e546  mov     [rbx+18h], rdx
0x14000e54a  jmp     short loc_14000E551
0x14000e54c  mov     edi, 0C000009Ah
0x14000e551  test    sil, sil
0x14000e554  jz      short loc_14000E577
0x14000e556  mov     rcx, [rbx+30h]; Resource
0x14000e55a  test    rcx, rcx
0x14000e55d  jz      short loc_14000E577
0x14000e55f  call    cs:__imp_ExReleaseResourceLite
0x14000e566  nop     dword ptr [rax+rax+00h]
0x14000e56b  call    cs:__imp_KeLeaveCriticalRegion
0x14000e572  nop     dword ptr [rax+rax+00h]
0x14000e577  test    edi, edi
0x14000e579  js      short loc_14000E596
0x14000e57b  lea     rcx, [rbx+90h]; Semaphore
0x14000e582  xor     r9d, r9d; Wait
0x14000e585  mov     r8d, ebp; Adjustment
0x14000e588  xor     edx, edx; Increment
0x14000e58a  call    cs:__imp_KeReleaseSemaphore
0x14000e591  nop     dword ptr [rax+rax+00h]
0x14000e596  mov     eax, edi
0x14000e598  add     rsp, 28h
0x14000e59c  pop     rdi
0x14000e59d  pop     rsi
0x14000e59e  pop     rbp
0x14000e59f  pop     rbx
0x14000e5a0  retn
```
