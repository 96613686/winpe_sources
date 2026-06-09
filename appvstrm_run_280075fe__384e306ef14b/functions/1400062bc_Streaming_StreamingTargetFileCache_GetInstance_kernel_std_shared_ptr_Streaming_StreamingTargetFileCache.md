# Streaming::StreamingTargetFileCache::GetInstance(kernel_std::shared_ptr<Streaming::StreamingTargetFileCache> &)

- ea: `0x1400062bc`
- end: `0x1400064dc`
- name: `?GetInstance@StreamingTargetFileCache@Streaming@@SAJAEAV?$shared_ptr@VStreamingTargetFileCache@Streaming@@@kernel_std@@@Z`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000571c`

## callees

- `0x140003b50`
- `0x1400062bc`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x140006323`
- `ntoskrnl!ExInitializeResourceLite` at `0x140006323`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400063b8`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400063b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063e0`
- `ntoskrnl!ExAllocatePool2` at `0x1400062db`
- `ntoskrnl!ExAllocatePool2` at `0x140006304`
- `ntoskrnl!ExAllocatePool2` at `0x140006369`
- `ntoskrnl!ExAllocatePool2` at `0x1400062db`
- `ntoskrnl!ExAllocatePool2` at `0x140006304`
- `ntoskrnl!ExAllocatePool2` at `0x140006369`

## pseudocode

```c
__int64 __fastcall Streaming::StreamingTargetFileCache::GetInstance(__int64 *a1)
{
  __int64 Pool2; // rax
  __int64 v3; // rdi
  struct _ERESOURCE *v4; // rax
  NTSTATUS v5; // esi
  __int64 v6; // rax
  volatile signed __int32 *v7; // rbx
  struct _ERESOURCE *v8; // rcx
  void *v9; // rcx
  volatile signed __int32 *v11; // rsi

  Pool2 = ExAllocatePool2(256, 56, 1717790323);
  v3 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 1717790323;
    *(_QWORD *)(Pool2 + 8) = 0;
    v4 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 1717790323);
    *(_QWORD *)(v3 + 8) = v4;
    if ( v4 )
      v5 = ExInitializeResourceLite(v4);
    else
      v5 = -1073741670;
    *(_DWORD *)(v3 + 16) = 0;
    *(_QWORD *)(v3 + 24) = 0;
    *(_QWORD *)(v3 + 32) = 0;
    *(_QWORD *)(v3 + 48) = v3 + 24;
    *(_QWORD *)(v3 + 40) = v3 + 24;
  }
  else
  {
    v5 = 0;
    v3 = 0;
  }
  v6 = ExAllocatePool2(256, 24, 1715758931);
  v7 = (volatile signed __int32 *)v6;
  if ( v6 )
  {
    *(_QWORD *)(v6 + 16) = v3;
    *(_DWORD *)(v6 + 8) = 1;
    *(_DWORD *)(v6 + 12) = 1;
    *(_QWORD *)v6 = &kernel_std::detail::sp_counted_impl_p<Streaming::StreamingTargetFileCache>::`vftable';
    if ( *(_DWORD *)(v6 + 8) )
      goto LABEL_16;
  }
  else
  {
    v7 = 0;
    if ( v3 )
    {
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(v3 + 16);
      v8 = *(struct _ERESOURCE **)(v3 + 8);
      if ( v8 )
      {
        ExDeleteResourceLite(v8);
        v9 = *(void **)(v3 + 8);
        if ( v9 )
          ExFreePoolWithTag(v9, 0);
      }
      ExFreePoolWithTag((PVOID)v3, 0);
    }
  }
  v3 = 0;
LABEL_16:
  if ( v5 < 0 )
  {
    if ( v7 && _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return (unsigned int)v5;
  }
  if ( !v7 )
    return 3221225626LL;
  if ( !v3 || !*((_DWORD *)v7 + 2) )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return 3221225626LL;
  }
  v11 = (volatile signed __int32 *)a1[1];
  *a1 = v3;
  a1[1] = (__int64)v7;
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400062bc  push    rbx
0x1400062be  push    rsi
0x1400062bf  push    rdi
0x1400062c0  push    r14
0x1400062c2  sub     rsp, 28h
0x1400062c6  mov     r14, rcx
0x1400062c9  mov     ebx, 66636673h
0x1400062ce  mov     r8d, ebx
0x1400062d1  mov     edx, 38h ; '8'
0x1400062d6  mov     ecx, 100h
0x1400062db  call    cs:__imp_ExAllocatePool2
0x1400062e2  nop     dword ptr [rax+rax+00h]
0x1400062e7  mov     rdi, rax
0x1400062ea  test    rax, rax
0x1400062ed  jz      short loc_140006355
0x1400062ef  mov     edx, 68h ; 'h'
0x1400062f4  mov     [rax], ebx
0x1400062f6  mov     r8d, ebx
0x1400062f9  mov     qword ptr [rax+8], 0
0x140006301  lea     ecx, [rdx-28h]
0x140006304  call    cs:__imp_ExAllocatePool2
0x14000630b  nop     dword ptr [rax+rax+00h]
0x140006310  mov     [rdi+8], rax
0x140006314  test    rax, rax
0x140006317  jnz     short loc_140006320
0x140006319  mov     esi, 0C000009Ah
0x14000631e  jmp     short loc_140006331
0x140006320  mov     rcx, rax; Resource
0x140006323  call    cs:__imp_ExInitializeResourceLite
0x14000632a  nop     dword ptr [rax+rax+00h]
0x14000632f  mov     esi, eax
0x140006331  lea     rax, [rdi+18h]
0x140006335  mov     dword ptr [rdi+10h], 0
0x14000633c  mov     qword ptr [rax], 0
0x140006343  mov     qword ptr [rax+8], 0
0x14000634b  mov     [rax+18h], rax
0x14000634f  mov     [rax+10h], rax
0x140006353  jmp     short loc_140006359
0x140006355  xor     esi, esi
0x140006357  xor     edi, edi
0x140006359  mov     edx, 18h
0x14000635e  mov     ecx, 100h
0x140006363  mov     r8d, 66446753h
0x140006369  call    cs:__imp_ExAllocatePool2
0x140006370  nop     dword ptr [rax+rax+00h]
0x140006375  mov     rbx, rax
0x140006378  test    rax, rax
0x14000637b  jz      short loc_14000639F
0x14000637d  mov     eax, 1
0x140006382  mov     [rbx+10h], rdi
0x140006386  mov     [rbx+8], eax
0x140006389  mov     [rbx+0Ch], eax
0x14000638c  lea     rax, ??_7?$sp_counted_impl_p@VStreamingTargetFileCache@Streaming@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<Streaming::StreamingTargetFileCache>::`vftable'
0x140006393  mov     [rbx], rax
0x140006396  mov     eax, [rbx+8]
0x140006399  test    eax, eax
0x14000639b  jnz     short loc_1400063EE
0x14000639d  jmp     short loc_1400063EC
0x14000639f  xor     ebx, ebx
0x1400063a1  test    rdi, rdi
0x1400063a4  jz      short loc_1400063EC
0x1400063a6  lea     rcx, [rdi+10h]
0x1400063aa  call    ??1?$doubly_linked_list@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x1400063af  mov     rcx, [rdi+8]; Resource
0x1400063b3  test    rcx, rcx
0x1400063b6  jz      short loc_1400063DB
0x1400063b8  call    cs:__imp_ExDeleteResourceLite
0x1400063bf  nop     dword ptr [rax+rax+00h]
0x1400063c4  mov     rcx, [rdi+8]; P
0x1400063c8  test    rcx, rcx
0x1400063cb  jz      short loc_1400063DB
0x1400063cd  xor     edx, edx; Tag
0x1400063cf  call    cs:__imp_ExFreePoolWithTag
0x1400063d6  nop     dword ptr [rax+rax+00h]
0x1400063db  xor     edx, edx; Tag
0x1400063dd  mov     rcx, rdi; P
0x1400063e0  call    cs:__imp_ExFreePoolWithTag
0x1400063e7  nop     dword ptr [rax+rax+00h]
0x1400063ec  xor     edi, edi
0x1400063ee  test    esi, esi
0x1400063f0  jns     short loc_140006435
0x1400063f2  test    rbx, rbx
0x1400063f5  jz      short loc_14000642E
0x1400063f7  or      edi, 0FFFFFFFFh
0x1400063fa  mov     eax, edi
0x1400063fc  lock xadd [rbx+8], eax
0x140006401  add     eax, edi
0x140006403  jnz     short loc_14000642E
0x140006405  mov     rax, [rbx]
0x140006408  mov     rcx, rbx
0x14000640b  mov     rax, [rax+8]
0x14000640f  call    _guard_dispatch_icall
0x140006414  mov     eax, edi
0x140006416  lock xadd [rbx+0Ch], eax
0x14000641b  add     eax, edi
0x14000641d  jnz     short loc_14000642E
0x14000641f  mov     rax, [rbx]
0x140006422  mov     rcx, rbx
0x140006425  mov     rax, [rax+10h]
0x140006429  call    _guard_dispatch_icall
0x14000642e  mov     eax, esi
0x140006430  jmp     loc_1400064D1
0x140006435  test    rbx, rbx
0x140006438  jz      loc_1400064CC
0x14000643e  test    rdi, rdi
0x140006441  jz      short loc_140006495
0x140006443  mov     eax, [rbx+8]
0x140006446  test    eax, eax
0x140006448  jz      short loc_140006495
0x14000644a  mov     rsi, [r14+8]
0x14000644e  mov     [r14], rdi
0x140006451  mov     [r14+8], rbx
0x140006455  test    rsi, rsi
0x140006458  jz      short loc_140006491
0x14000645a  or      edi, 0FFFFFFFFh
0x14000645d  mov     eax, edi
0x14000645f  lock xadd [rsi+8], eax
0x140006464  add     eax, edi
0x140006466  jnz     short loc_140006491
0x140006468  mov     rax, [rsi]
0x14000646b  mov     rcx, rsi
0x14000646e  mov     rax, [rax+8]
0x140006472  call    _guard_dispatch_icall
0x140006477  mov     eax, edi
0x140006479  lock xadd [rsi+0Ch], eax
0x14000647e  add     eax, edi
0x140006480  jnz     short loc_140006491
0x140006482  mov     rax, [rsi]
0x140006485  mov     rcx, rsi
0x140006488  mov     rax, [rax+10h]
0x14000648c  call    _guard_dispatch_icall
0x140006491  xor     eax, eax
0x140006493  jmp     short loc_1400064D1
0x140006495  or      edi, 0FFFFFFFFh
0x140006498  mov     eax, edi
0x14000649a  lock xadd [rbx+8], eax
0x14000649f  add     eax, edi
0x1400064a1  jnz     short loc_1400064CC
0x1400064a3  mov     rax, [rbx]
0x1400064a6  mov     rcx, rbx
0x1400064a9  mov     rax, [rax+8]
0x1400064ad  call    _guard_dispatch_icall
0x1400064b2  mov     ecx, edi
0x1400064b4  lock xadd [rbx+0Ch], ecx
0x1400064b9  add     ecx, edi
0x1400064bb  jnz     short loc_1400064CC
0x1400064bd  mov     rcx, [rbx]
0x1400064c0  mov     rax, [rcx+10h]
0x1400064c4  mov     rcx, rbx
0x1400064c7  call    _guard_dispatch_icall
0x1400064cc  mov     eax, 0C000009Ah
0x1400064d1  add     rsp, 28h
0x1400064d5  pop     r14
0x1400064d7  pop     rdi
0x1400064d8  pop     rsi
0x1400064d9  pop     rbx
0x1400064da  retn
```
