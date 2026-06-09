# kernel_std::shared_ptr<appv::shared::kernel::shared_read_lock>::reset<appv::shared::kernel::shared_read_lock>(appv::shared::kernel::shared_read_lock *)

- ea: `0x140002298`
- end: `0x140002392`
- name: `??$reset@Vshared_read_lock@kernel@shared@appv@@@?$shared_ptr@Vshared_read_lock@kernel@shared@appv@@@kernel_std@@QEAAXPEAVshared_read_lock@kernel@shared@appv@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400023d8`

## callees

- `0x140002298`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400022fe`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400022fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002315`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002326`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002315`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002326`
- `ntoskrnl!ExAllocatePool2` at `0x1400022b8`
- `ntoskrnl!ExAllocatePool2` at `0x1400022b8`

## pseudocode

```c
__int64 __fastcall kernel_std::shared_ptr<appv::shared::kernel::shared_read_lock>::reset<appv::shared::kernel::shared_read_lock>(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 Pool2; // rax
  __int64 v5; // r8
  int v6; // ecx
  struct _ERESOURCE *v7; // rcx
  void *v8; // rcx
  __int64 result; // rax
  volatile signed __int32 *v10; // rbx
  signed __int32 v11; // eax
  bool v12; // zf

  Pool2 = ExAllocatePool2(256, 24, 1715758931);
  v5 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 16) = a2;
    *(_DWORD *)(Pool2 + 8) = 1;
    *(_DWORD *)(Pool2 + 12) = 1;
    *(_QWORD *)Pool2 = &kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::shared_read_lock>::`vftable';
    v6 = *(_DWORD *)(Pool2 + 8);
  }
  else
  {
    v5 = 0;
    if ( a2 )
    {
      v7 = (struct _ERESOURCE *)a2[1];
      if ( v7 )
      {
        ExDeleteResourceLite(v7);
        v8 = (void *)a2[1];
        if ( v8 )
          ExFreePoolWithTag(v8, 0);
      }
      ExFreePoolWithTag(a2, 0);
      v5 = 0;
    }
    v6 = 0;
  }
  result = 0;
  if ( v6 )
    result = (__int64)a2;
  v10 = (volatile signed __int32 *)a1[1];
  *a1 = result;
  a1[1] = v5;
  if ( v10 )
  {
    v11 = _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF);
    v12 = v11 == 1;
    result = (unsigned int)(v11 - 1);
    if ( v12 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      result = (unsigned int)_InterlockedDecrement(v10 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002298  mov     [rsp+arg_0], rbx
0x14000229d  push    rdi
0x14000229e  sub     rsp, 20h
0x1400022a2  mov     rbx, rdx
0x1400022a5  mov     rdi, rcx
0x1400022a8  mov     edx, 18h
0x1400022ad  mov     ecx, 100h
0x1400022b2  mov     r8d, 66446753h
0x1400022b8  call    cs:__imp_ExAllocatePool2
0x1400022bf  nop     dword ptr [rax+rax+00h]
0x1400022c4  mov     r8, rax
0x1400022c7  test    rax, rax
0x1400022ca  jz      short loc_1400022ED
0x1400022cc  mov     eax, 1
0x1400022d1  mov     [r8+10h], rbx
0x1400022d5  mov     [r8+8], eax
0x1400022d9  mov     [r8+0Ch], eax
0x1400022dd  lea     rax, ??_7?$sp_counted_impl_p@Vshared_read_lock@kernel@shared@appv@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::shared_read_lock>::`vftable'
0x1400022e4  mov     [r8], rax
0x1400022e7  mov     ecx, [r8+8]
0x1400022eb  jmp     short loc_140002337
0x1400022ed  xor     r8d, r8d
0x1400022f0  test    rbx, rbx
0x1400022f3  jz      short loc_140002335
0x1400022f5  mov     rcx, [rbx+8]; Resource
0x1400022f9  test    rcx, rcx
0x1400022fc  jz      short loc_140002321
0x1400022fe  call    cs:__imp_ExDeleteResourceLite
0x140002305  nop     dword ptr [rax+rax+00h]
0x14000230a  mov     rcx, [rbx+8]; P
0x14000230e  test    rcx, rcx
0x140002311  jz      short loc_140002321
0x140002313  xor     edx, edx; Tag
0x140002315  call    cs:__imp_ExFreePoolWithTag
0x14000231c  nop     dword ptr [rax+rax+00h]
0x140002321  xor     edx, edx; Tag
0x140002323  mov     rcx, rbx; P
0x140002326  call    cs:__imp_ExFreePoolWithTag
0x14000232d  nop     dword ptr [rax+rax+00h]
0x140002332  xor     r8d, r8d
0x140002335  xor     ecx, ecx
0x140002337  xor     eax, eax
0x140002339  test    ecx, ecx
0x14000233b  cmovnz  rax, rbx
0x14000233f  mov     rbx, [rdi+8]
0x140002343  mov     [rdi], rax
0x140002346  mov     [rdi+8], r8
0x14000234a  test    rbx, rbx
0x14000234d  jz      short loc_140002386
0x14000234f  or      edi, 0FFFFFFFFh
0x140002352  mov     eax, edi
0x140002354  lock xadd [rbx+8], eax
0x140002359  add     eax, edi
0x14000235b  jnz     short loc_140002386
0x14000235d  mov     rax, [rbx]
0x140002360  mov     rcx, rbx
0x140002363  mov     rax, [rax+8]
0x140002367  call    _guard_dispatch_icall
0x14000236c  mov     eax, edi
0x14000236e  lock xadd [rbx+0Ch], eax
0x140002373  add     eax, edi
0x140002375  jnz     short loc_140002386
0x140002377  mov     rax, [rbx]
0x14000237a  mov     rcx, rbx
0x14000237d  mov     rax, [rax+10h]
0x140002381  call    _guard_dispatch_icall
0x140002386  mov     rbx, [rsp+28h+arg_0]
0x14000238b  add     rsp, 20h
0x14000238f  pop     rdi
0x140002390  retn
```
