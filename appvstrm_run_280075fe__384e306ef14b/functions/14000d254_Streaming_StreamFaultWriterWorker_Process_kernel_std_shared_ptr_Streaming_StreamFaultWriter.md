# Streaming::StreamFaultWriterWorker::Process(kernel_std::shared_ptr<Streaming::StreamFaultWriter>)

- ea: `0x14000d254`
- end: `0x14000d378`
- name: `?Process@StreamFaultWriterWorker@Streaming@@QEAAJV?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@@Z`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c4ac`

## callees

- `0x14000d254`
- `0x14000d380`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d2c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d2c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d2b8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d2b8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000d29d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000d29d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d28b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d28b`

## pseudocode

```c
__int64 __fastcall Streaming::StreamFaultWriterWorker::Process(PERESOURCE *a1, _QWORD *a2)
{
  int v4; // edi
  BOOLEAN v5; // al
  struct _ERESOURCE *v6; // rcx
  volatile signed __int32 *v7; // rdi
  unsigned int v9; // eax
  volatile signed __int32 *v10; // rdi
  unsigned int v11; // ebp

  if ( !*((_DWORD *)a1 + 54) || (*(_DWORD *)(*a2 + 64LL) & 0x2000000) == 0 )
    goto LABEL_14;
  if ( a1[6] )
  {
    KeEnterCriticalRegion();
    v5 = ExAcquireResourceSharedLite(a1[6], 1u);
    v4 = *(_DWORD *)a1;
    if ( v5 == 1 )
    {
      v6 = a1[6];
      if ( v6 )
      {
        ExReleaseResourceLite(v6);
        KeLeaveCriticalRegion();
      }
    }
  }
  else
  {
    v4 = *(_DWORD *)a1;
  }
  if ( v4 > *((_DWORD *)a1 + 54) )
  {
    v7 = (volatile signed __int32 *)a2[1];
    if ( v7 && _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return 3221225626LL;
  }
  else
  {
LABEL_14:
    v9 = appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::QueueWorkItem(
           a1,
           a2);
    v10 = (volatile signed __int32 *)a2[1];
    v11 = v9;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
    return v11;
  }
}

```

## disassembly

```asm
0x14000d254  push    rbx
0x14000d256  push    rbp
0x14000d257  push    rsi
0x14000d258  push    rdi
0x14000d259  sub     rsp, 28h
0x14000d25d  cmp     dword ptr [rcx+0D8h], 0
0x14000d264  mov     rsi, rdx
0x14000d267  mov     rbx, rcx
0x14000d26a  jz      loc_14000D31F
0x14000d270  mov     rax, [rdx]
0x14000d273  test    dword ptr [rax+40h], 2000000h
0x14000d27a  jz      loc_14000D31F
0x14000d280  cmp     qword ptr [rcx+30h], 0
0x14000d285  jnz     short loc_14000D28B
0x14000d287  mov     edi, [rcx]
0x14000d289  jmp     short loc_14000D2D0
0x14000d28b  call    cs:__imp_KeEnterCriticalRegion
0x14000d292  nop     dword ptr [rax+rax+00h]
0x14000d297  mov     rcx, [rbx+30h]; Resource
0x14000d29b  mov     dl, 1; Wait
0x14000d29d  call    cs:__imp_ExAcquireResourceSharedLite
0x14000d2a4  nop     dword ptr [rax+rax+00h]
0x14000d2a9  mov     edi, [rbx]
0x14000d2ab  cmp     al, 1
0x14000d2ad  jnz     short loc_14000D2D0
0x14000d2af  mov     rcx, [rbx+30h]; Resource
0x14000d2b3  test    rcx, rcx
0x14000d2b6  jz      short loc_14000D2D0
0x14000d2b8  call    cs:__imp_ExReleaseResourceLite
0x14000d2bf  nop     dword ptr [rax+rax+00h]
0x14000d2c4  call    cs:__imp_KeLeaveCriticalRegion
0x14000d2cb  nop     dword ptr [rax+rax+00h]
0x14000d2d0  cmp     edi, [rbx+0D8h]
0x14000d2d6  jle     short loc_14000D31F
0x14000d2d8  mov     rdi, [rsi+8]
0x14000d2dc  test    rdi, rdi
0x14000d2df  jz      short loc_14000D318
0x14000d2e1  or      ebx, 0FFFFFFFFh
0x14000d2e4  mov     eax, ebx
0x14000d2e6  lock xadd [rdi+8], eax
0x14000d2eb  add     eax, ebx
0x14000d2ed  jnz     short loc_14000D318
0x14000d2ef  mov     rax, [rdi]
0x14000d2f2  mov     rcx, rdi
0x14000d2f5  mov     rax, [rax+8]
0x14000d2f9  call    _guard_dispatch_icall
0x14000d2fe  mov     eax, ebx
0x14000d300  lock xadd [rdi+0Ch], eax
0x14000d305  add     eax, ebx
0x14000d307  jnz     short loc_14000D318
0x14000d309  mov     rax, [rdi]
0x14000d30c  mov     rcx, rdi
0x14000d30f  mov     rax, [rax+10h]
0x14000d313  call    _guard_dispatch_icall
0x14000d318  mov     eax, 0C000009Ah
0x14000d31d  jmp     short loc_14000D36E
0x14000d31f  mov     rdx, rsi
0x14000d322  mov     rcx, rbx
0x14000d325  call    ?QueueWorkItem@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAAJAEAV?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@@Z; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::QueueWorkItem(kernel_std::shared_ptr<Streaming::StreamFaultWriter> &)
0x14000d32a  mov     rdi, [rsi+8]
0x14000d32e  mov     ebp, eax
0x14000d330  test    rdi, rdi
0x14000d333  jz      short loc_14000D36C
0x14000d335  or      ebx, 0FFFFFFFFh
0x14000d338  mov     ecx, ebx
0x14000d33a  lock xadd [rdi+8], ecx
0x14000d33f  add     ecx, ebx
0x14000d341  jnz     short loc_14000D36C
0x14000d343  mov     rdx, [rdi]
0x14000d346  mov     rcx, rdi
0x14000d349  mov     rax, [rdx+8]
0x14000d34d  call    _guard_dispatch_icall
0x14000d352  mov     eax, ebx
0x14000d354  lock xadd [rdi+0Ch], eax
0x14000d359  add     eax, ebx
0x14000d35b  jnz     short loc_14000D36C
0x14000d35d  mov     rax, [rdi]
0x14000d360  mov     rcx, rdi
0x14000d363  mov     rax, [rax+10h]
0x14000d367  call    _guard_dispatch_icall
0x14000d36c  mov     eax, ebp
0x14000d36e  add     rsp, 28h
0x14000d372  pop     rdi
0x14000d373  pop     rsi
0x14000d374  pop     rbp
0x14000d375  pop     rbx
0x14000d376  retn
```
