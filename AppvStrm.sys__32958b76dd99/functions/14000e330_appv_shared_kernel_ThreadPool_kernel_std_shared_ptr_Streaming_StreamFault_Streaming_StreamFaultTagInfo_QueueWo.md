# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::QueueWorkItem(kernel_std::shared_ptr<Streaming::StreamFault> &)

- ea: `0x14000e330`
- end: `0x14000e464`
- name: `?QueueWorkItem@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAAJAEAV?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000db88`

## callees

- `0x14000e330`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e399`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e42d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e399`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e42d`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000e44c`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000e44c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e38d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e421`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e38d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e421`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000e361`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000e361`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e34e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e34e`
- `ntoskrnl!ExAllocatePool2` at `0x14000e3bd`
- `ntoskrnl!ExAllocatePool2` at `0x14000e3bd`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::QueueWorkItem(
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
    Pool2 = (_QWORD *)ExAllocatePool2(64, 32, 1886611059);
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
0x14000e330  push    rbx
0x14000e332  push    rbp
0x14000e333  push    rsi
0x14000e334  push    rdi
0x14000e335  sub     rsp, 28h
0x14000e339  xor     sil, sil
0x14000e33c  mov     rdi, rdx
0x14000e33f  cmp     qword ptr [rcx+30h], 0
0x14000e344  mov     rbx, rcx
0x14000e347  mov     ebp, 1
0x14000e34c  jz      short loc_14000E377
0x14000e34e  call    cs:__imp_KeEnterCriticalRegion
0x14000e355  nop     dword ptr [rax+rax+00h]
0x14000e35a  mov     rcx, [rbx+30h]; Resource
0x14000e35e  mov     dl, bpl; Wait
0x14000e361  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000e368  nop     dword ptr [rax+rax+00h]
0x14000e36d  cmp     al, bpl
0x14000e370  movzx   esi, sil
0x14000e374  cmovz   esi, ebp
0x14000e377  cmp     dword ptr [rbx], 0FFFFh
0x14000e37d  jb      short loc_14000E3AF
0x14000e37f  test    sil, sil
0x14000e382  jz      short loc_14000E3A5
0x14000e384  mov     rcx, [rbx+30h]; Resource
0x14000e388  test    rcx, rcx
0x14000e38b  jz      short loc_14000E3A5
0x14000e38d  call    cs:__imp_ExReleaseResourceLite
0x14000e394  nop     dword ptr [rax+rax+00h]
0x14000e399  call    cs:__imp_KeLeaveCriticalRegion
0x14000e3a0  nop     dword ptr [rax+rax+00h]
0x14000e3a5  mov     edi, 8000001Ah
0x14000e3aa  jmp     loc_14000E458
0x14000e3af  mov     edx, 20h ; ' '
0x14000e3b4  mov     r8d, 70736673h
0x14000e3ba  lea     ecx, [rdx+20h]
0x14000e3bd  call    cs:__imp_ExAllocatePool2
0x14000e3c4  nop     dword ptr [rax+rax+00h]
0x14000e3c9  mov     rdx, rax
0x14000e3cc  test    rax, rax
0x14000e3cf  jz      short loc_14000E40E
0x14000e3d1  mov     rcx, [rdi]
0x14000e3d4  mov     [rax], rcx
0x14000e3d7  mov     rax, [rdi+8]
0x14000e3db  mov     [rdx+8], rax
0x14000e3df  test    rax, rax
0x14000e3e2  jz      short loc_14000E3E8
0x14000e3e4  lock add [rax+8], ebp
0x14000e3e8  mov     [rdx+18h], rdx
0x14000e3ec  lea     rax, [rbx+8]
0x14000e3f0  mov     [rdx+10h], rdx
0x14000e3f4  add     [rbx], ebp
0x14000e3f6  mov     rcx, [rax+10h]
0x14000e3fa  xor     edi, edi
0x14000e3fc  mov     [rdx+18h], rax
0x14000e400  mov     [rdx+10h], rcx
0x14000e404  mov     [rcx+18h], rdx
0x14000e408  mov     [rbx+18h], rdx
0x14000e40c  jmp     short loc_14000E413
0x14000e40e  mov     edi, 0C000009Ah
0x14000e413  test    sil, sil
0x14000e416  jz      short loc_14000E439
0x14000e418  mov     rcx, [rbx+30h]; Resource
0x14000e41c  test    rcx, rcx
0x14000e41f  jz      short loc_14000E439
0x14000e421  call    cs:__imp_ExReleaseResourceLite
0x14000e428  nop     dword ptr [rax+rax+00h]
0x14000e42d  call    cs:__imp_KeLeaveCriticalRegion
0x14000e434  nop     dword ptr [rax+rax+00h]
0x14000e439  test    edi, edi
0x14000e43b  js      short loc_14000E458
0x14000e43d  lea     rcx, [rbx+90h]; Semaphore
0x14000e444  xor     r9d, r9d; Wait
0x14000e447  mov     r8d, ebp; Adjustment
0x14000e44a  xor     edx, edx; Increment
0x14000e44c  call    cs:__imp_KeReleaseSemaphore
0x14000e453  nop     dword ptr [rax+rax+00h]
0x14000e458  mov     eax, edi
0x14000e45a  add     rsp, 28h
0x14000e45e  pop     rdi
0x14000e45f  pop     rsi
0x14000e460  pop     rbp
0x14000e461  pop     rbx
0x14000e462  retn
```
