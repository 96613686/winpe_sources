# Streaming::StreamFaultWriterWorker::GetInstance(kernel_std::shared_ptr<Streaming::StreamFaultWriterWorker> &)

- ea: `0x140006158`
- end: `0x1400062b3`
- name: `?GetInstance@StreamFaultWriterWorker@Streaming@@SAJAEAV?$shared_ptr@VStreamFaultWriterWorker@Streaming@@@kernel_std@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000571c`

## callees

- `0x140004fec`
- `0x14000528c`
- `0x140006158`
- `0x1400073b8`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006201`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006201`
- `ntoskrnl!ExAllocatePool2` at `0x140006179`
- `ntoskrnl!ExAllocatePool2` at `0x1400061b2`
- `ntoskrnl!ExAllocatePool2` at `0x140006179`
- `ntoskrnl!ExAllocatePool2` at `0x1400061b2`

## pseudocode

```c
__int64 __fastcall Streaming::StreamFaultWriterWorker::GetInstance(char **a1)
{
  int v1; // esi
  char *Pool2; // rax
  char *v4; // rax
  char *v5; // rdi
  __int64 v6; // rax
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rcx
  int v9; // edx
  char *v10; // rax
  volatile signed __int32 *v12; // rsi
  int v13; // [rsp+58h] [rbp+10h] BYREF

  v1 = 0;
  v13 = 0;
  Pool2 = (char *)ExAllocatePool2(64, 224, 2003199603);
  if ( Pool2 )
  {
    v4 = Streaming::StreamFaultWriterWorker::StreamFaultWriterWorker(Pool2, &v13);
    v1 = v13;
    v5 = v4;
  }
  else
  {
    v5 = 0;
  }
  v6 = ExAllocatePool2(256, 24, 1715758931);
  v7 = (volatile signed __int32 *)v6;
  if ( v6 )
  {
    *(_QWORD *)(v6 + 16) = v5;
    *(_DWORD *)(v6 + 8) = 1;
    v8 = v6 + 8;
    *(_DWORD *)(v6 + 12) = 1;
    *(_QWORD *)v6 = &kernel_std::detail::sp_counted_impl_p<Streaming::StreamFaultWriterWorker>::`vftable';
    v9 = *(_DWORD *)(v6 + 8);
  }
  else
  {
    if ( v5 )
    {
      appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(v5);
      appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>((__int64)v5);
      ExFreePoolWithTag(v5, 0);
    }
    v9 = 0;
    v7 = 0;
    v8 = 8;
  }
  v10 = 0;
  if ( v9 )
    v10 = v5;
  if ( v1 >= 0 )
  {
    v12 = (volatile signed __int32 *)a1[1];
    *a1 = v10;
    a1[1] = (char *)v7;
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
    return 0;
  }
  else
  {
    if ( v7 && _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return (unsigned int)v1;
  }
}

```

## disassembly

```asm
0x140006158  push    rbx
0x14000615a  push    rsi
0x14000615b  push    rdi
0x14000615c  push    r14
0x14000615e  sub     rsp, 28h
0x140006162  xor     esi, esi
0x140006164  mov     r14, rcx
0x140006167  mov     edx, 0E0h
0x14000616c  mov     [rsp+48h+arg_8], esi
0x140006170  mov     r8d, 77666673h
0x140006176  lea     ecx, [rsi+40h]
0x140006179  call    cs:__imp_ExAllocatePool2
0x140006180  nop     dword ptr [rax+rax+00h]
0x140006185  test    rax, rax
0x140006188  jz      short loc_1400061A0
0x14000618a  lea     rdx, [rsp+48h+arg_8]; int *
0x14000618f  mov     rcx, rax; StartContext
0x140006192  call    ??0StreamFaultWriterWorker@Streaming@@AEAA@AEAJ@Z; Streaming::StreamFaultWriterWorker::StreamFaultWriterWorker(long &)
0x140006197  mov     esi, [rsp+48h+arg_8]
0x14000619b  mov     rdi, rax
0x14000619e  jmp     short loc_1400061A2
0x1400061a0  xor     edi, edi
0x1400061a2  mov     edx, 18h
0x1400061a7  mov     ecx, 100h
0x1400061ac  mov     r8d, 66446753h
0x1400061b2  call    cs:__imp_ExAllocatePool2
0x1400061b9  nop     dword ptr [rax+rax+00h]
0x1400061be  mov     rbx, rax
0x1400061c1  test    rax, rax
0x1400061c4  jz      short loc_1400061E7
0x1400061c6  mov     eax, 1
0x1400061cb  mov     [rbx+10h], rdi
0x1400061cf  mov     [rbx+8], eax
0x1400061d2  lea     rcx, [rbx+8]
0x1400061d6  mov     [rbx+0Ch], eax
0x1400061d9  lea     rax, ??_7?$sp_counted_impl_p@VStreamFaultWriterWorker@Streaming@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<Streaming::StreamFaultWriterWorker>::`vftable'
0x1400061e0  mov     [rbx], rax
0x1400061e3  mov     edx, [rcx]
0x1400061e5  jmp     short loc_140006214
0x1400061e7  test    rdi, rdi
0x1400061ea  jz      short loc_14000620D
0x1400061ec  mov     rcx, rdi
0x1400061ef  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(void)
0x1400061f4  mov     rcx, rdi
0x1400061f7  call    ??1?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x1400061fc  xor     edx, edx; Tag
0x1400061fe  mov     rcx, rdi; P
0x140006201  call    cs:__imp_ExFreePoolWithTag
0x140006208  nop     dword ptr [rax+rax+00h]
0x14000620d  xor     edx, edx
0x14000620f  xor     ebx, ebx
0x140006211  lea     ecx, [rdx+8]
0x140006214  xor     eax, eax
0x140006216  test    edx, edx
0x140006218  cmovnz  rax, rdi
0x14000621c  test    esi, esi
0x14000621e  jns     short loc_14000625F
0x140006220  test    rbx, rbx
0x140006223  jz      short loc_14000625B
0x140006225  or      edi, 0FFFFFFFFh
0x140006228  mov     eax, edi
0x14000622a  lock xadd [rcx], eax
0x14000622e  add     eax, edi
0x140006230  jnz     short loc_14000625B
0x140006232  mov     rax, [rbx]
0x140006235  mov     rcx, rbx
0x140006238  mov     rax, [rax+8]
0x14000623c  call    _guard_dispatch_icall
0x140006241  mov     edx, edi
0x140006243  lock xadd [rbx+0Ch], edx
0x140006248  add     edx, edi
0x14000624a  jnz     short loc_14000625B
0x14000624c  mov     rdx, [rbx]
0x14000624f  mov     rcx, rbx
0x140006252  mov     rax, [rdx+10h]
0x140006256  call    _guard_dispatch_icall
0x14000625b  mov     eax, esi
0x14000625d  jmp     short loc_1400062A8
0x14000625f  mov     rsi, [r14+8]
0x140006263  mov     [r14], rax
0x140006266  mov     [r14+8], rbx
0x14000626a  test    rsi, rsi
0x14000626d  jz      short loc_1400062A6
0x14000626f  or      edi, 0FFFFFFFFh
0x140006272  mov     eax, edi
0x140006274  lock xadd [rsi+8], eax
0x140006279  add     eax, edi
0x14000627b  jnz     short loc_1400062A6
0x14000627d  mov     rax, [rsi]
0x140006280  mov     rcx, rsi
0x140006283  mov     rax, [rax+8]
0x140006287  call    _guard_dispatch_icall
0x14000628c  mov     eax, edi
0x14000628e  lock xadd [rsi+0Ch], eax
0x140006293  add     eax, edi
0x140006295  jnz     short loc_1400062A6
0x140006297  mov     rax, [rsi]
0x14000629a  mov     rcx, rsi
0x14000629d  mov     rax, [rax+10h]
0x1400062a1  call    _guard_dispatch_icall
0x1400062a6  xor     eax, eax
0x1400062a8  add     rsp, 28h
0x1400062ac  pop     r14
0x1400062ae  pop     rdi
0x1400062af  pop     rsi
0x1400062b0  pop     rbx
0x1400062b1  retn
```
