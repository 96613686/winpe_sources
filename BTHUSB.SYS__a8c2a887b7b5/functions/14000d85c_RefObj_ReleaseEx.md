# RefObj_ReleaseEx

- ea: `0x14000d85c`
- end: `0x14000d9fa`
- name: `RefObj_ReleaseEx`
- size: `414`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400076e8`
- `0x140008120`
- `0x1400081b0`
- `0x1400094f8`
- `0x140009a10`
- `0x140009a90`

## callees

- `0x14000d85c`
- `0x14000de00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000d91f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d9ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d91f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d9ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d8e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d976`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d8e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d976`
- `ntoskrnl!ExFreePool` at `0x14000d94f`
- `ntoskrnl!ExFreePool` at `0x14000d993`
- `ntoskrnl!ExFreePool` at `0x14000d9de`
- `ntoskrnl!ExFreePool` at `0x14000d94f`
- `ntoskrnl!ExFreePool` at `0x14000d993`
- `ntoskrnl!ExFreePool` at `0x14000d9de`

## pseudocode

```c
__int64 __fastcall RefObj_ReleaseEx(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v5; // rcx
  signed __int32 v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rdx
  KIRQL v10; // al
  _QWORD **v11; // rdx
  _QWORD *v12; // rbx
  _QWORD *v13; // rcx
  unsigned __int32 v14; // esi
  KSPIN_LOCK *v15; // rbp
  KIRQL v16; // r15
  void (__fastcall *v17)(__int64); // rax

  v5 = *(_QWORD *)(a1 + 16);
  if ( v5 )
  {
    v7 = _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 1028), 1u);
    v8 = *(_QWORD *)(a1 + 16);
    v9 = 5LL * (v7 % 25);
    *(_DWORD *)(v8 + 8 * v9 + 24) = 1;
    *(_DWORD *)(v8 + 8 * v9 + 40) = a3;
    *(_QWORD *)(v8 + 8 * v9 + 48) = a2;
    *(_QWORD *)(v8 + 8 * v9 + 32) = a4;
    *(_QWORD *)(v8 + 8 * v9 + 56) = MEMORY[0xFFFFF78000000320];
    v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(a1 + 16) + 8LL));
    v11 = (_QWORD **)(*(_QWORD *)(a1 + 16) + 16LL);
    v12 = *v11;
    if ( *v11 )
    {
      while ( 1 )
      {
        v13 = (_QWORD *)*v12;
        if ( v12[1] == a2 )
          break;
        v11 = (_QWORD **)v12;
        v12 = (_QWORD *)*v12;
        if ( !v13 )
          goto LABEL_7;
      }
      *v11 = v13;
    }
LABEL_7:
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 16) + 8LL), v10);
    if ( v12 )
    {
      ExFreePool(v12);
    }
    else if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 4LL)) < 0 )
    {
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 4LL), 1u);
      NT_ASSERT("Releasing tag on ref that was not acquired
");
    }
  }
  v14 = _InterlockedDecrement((volatile signed __int32 *)a1);
  if ( !v14 )
  {
    v15 = *(KSPIN_LOCK **)(a1 + 16);
    if ( v15 )
    {
      v16 = KeAcquireSpinLockRaiseToDpc(v15 + 1);
      if ( v15[2] )
        NT_ASSERT("Abandonded tags on ref
");
      KeReleaseSpinLock(v15 + 1, v16);
    }
    v17 = *(void (__fastcall **)(__int64))(a1 + 8);
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
    v17(a1);
    if ( v15 )
      ExFreePool(v15);
  }
  return v14;
}

```

## disassembly

```asm
0x14000d85c  push    rbx
0x14000d85e  push    rbp
0x14000d85f  push    rsi
0x14000d860  push    rdi
0x14000d861  push    r14
0x14000d863  push    r15
0x14000d865  sub     rsp, 28h
0x14000d869  mov     rdi, rcx
0x14000d86c  or      ebp, 0FFFFFFFFh
0x14000d86f  mov     rcx, [rcx+10h]
0x14000d873  mov     rsi, rdx
0x14000d876  test    rcx, rcx
0x14000d879  jz      loc_14000D95B
0x14000d87f  lea     r14d, [rbp+2]
0x14000d883  mov     eax, r14d
0x14000d886  lock xadd [rcx+404h], eax
0x14000d88e  lea     ecx, [r14+rax]
0x14000d892  mov     eax, 51EB851Fh
0x14000d897  dec     ecx
0x14000d899  imul    ecx
0x14000d89b  sar     edx, 3
0x14000d89e  mov     eax, edx
0x14000d8a0  shr     eax, 1Fh
0x14000d8a3  add     edx, eax
0x14000d8a5  imul    eax, edx, 19h
0x14000d8a8  sub     ecx, eax
0x14000d8aa  movsxd  rax, ecx
0x14000d8ad  mov     rcx, [rdi+10h]
0x14000d8b1  lea     rdx, [rax+rax*4]
0x14000d8b5  mov     [rcx+rdx*8+18h], r14d
0x14000d8ba  mov     [rcx+rdx*8+28h], r8d
0x14000d8bf  mov     [rcx+rdx*8+30h], rsi
0x14000d8c4  mov     [rcx+rdx*8+20h], r9
0x14000d8c9  mov     rax, ds:0FFFFF78000000320h
0x14000d8d3  mov     [rcx+rdx*8+38h], rax
0x14000d8d8  mov     rcx, [rdi+10h]
0x14000d8dc  add     rcx, 8; SpinLock
0x14000d8e0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d8e7  nop     dword ptr [rax+rax+00h]
0x14000d8ec  mov     rdx, [rdi+10h]
0x14000d8f0  add     rdx, 10h
0x14000d8f4  mov     rbx, [rdx]
0x14000d8f7  test    rbx, rbx
0x14000d8fa  jz      short loc_14000D915
0x14000d8fc  mov     rcx, [rbx]
0x14000d8ff  cmp     [rbx+8], rsi
0x14000d903  jz      short loc_14000D912
0x14000d905  mov     rdx, rbx
0x14000d908  mov     rbx, rcx
0x14000d90b  test    rcx, rcx
0x14000d90e  jnz     short loc_14000D8FC
0x14000d910  jmp     short loc_14000D915
0x14000d912  mov     [rdx], rcx
0x14000d915  mov     rcx, [rdi+10h]
0x14000d919  mov     dl, al; NewIrql
0x14000d91b  add     rcx, 8; SpinLock
0x14000d91f  call    cs:__imp_KeReleaseSpinLock
0x14000d926  nop     dword ptr [rax+rax+00h]
0x14000d92b  test    rbx, rbx
0x14000d92e  jnz     short loc_14000D94C
0x14000d930  mov     rcx, [rdi+10h]
0x14000d934  mov     eax, ebp
0x14000d936  lock xadd [rcx+4], eax
0x14000d93b  add     eax, ebp
0x14000d93d  jns     short loc_14000D95B
0x14000d93f  mov     rax, [rdi+10h]
0x14000d943  lock add [rax+4], r14d
0x14000d948  int     2Ch; NT_ASSERT("Releasing tag on ref that was not acquired
0x14000d94a  jmp     short loc_14000D95B
0x14000d94c  mov     rcx, rbx; P
0x14000d94f  call    cs:__imp_ExFreePool
0x14000d956  nop     dword ptr [rax+rax+00h]
0x14000d95b  mov     esi, ebp
0x14000d95d  lock xadd [rdi], esi
0x14000d961  add     esi, ebp
0x14000d963  jnz     loc_14000D9EA
0x14000d969  mov     rbp, [rdi+10h]
0x14000d96d  test    rbp, rbp
0x14000d970  jz      short loc_14000D9BA
0x14000d972  lea     rcx, [rbp+8]; SpinLock
0x14000d976  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d97d  nop     dword ptr [rax+rax+00h]
0x14000d982  mov     rcx, [rbp+10h]; P
0x14000d986  mov     r15b, al
0x14000d989  test    rcx, rcx
0x14000d98c  jz      short loc_14000D9A7
0x14000d98e  int     2Ch; NT_ASSERT("Abandonded tags on ref
0x14000d990  mov     rbx, [rcx]
0x14000d993  call    cs:__imp_ExFreePool
0x14000d99a  nop     dword ptr [rax+rax+00h]
0x14000d99f  mov     rcx, rbx
0x14000d9a2  test    rbx, rbx
0x14000d9a5  jnz     short loc_14000D990
0x14000d9a7  mov     dl, r15b; NewIrql
0x14000d9aa  lea     rcx, [rbp+8]; SpinLock
0x14000d9ae  call    cs:__imp_KeReleaseSpinLock
0x14000d9b5  nop     dword ptr [rax+rax+00h]
0x14000d9ba  mov     rax, [rdi+8]
0x14000d9be  mov     rcx, rdi
0x14000d9c1  mov     qword ptr [rdi+8], 0
0x14000d9c9  mov     qword ptr [rdi+10h], 0
0x14000d9d1  call    _guard_dispatch_icall
0x14000d9d6  test    rbp, rbp
0x14000d9d9  jz      short loc_14000D9EA
0x14000d9db  mov     rcx, rbp; P
0x14000d9de  call    cs:__imp_ExFreePool
0x14000d9e5  nop     dword ptr [rax+rax+00h]
0x14000d9ea  mov     eax, esi
0x14000d9ec  add     rsp, 28h
0x14000d9f0  pop     r15
0x14000d9f2  pop     r14
0x14000d9f4  pop     rdi
0x14000d9f5  pop     rsi
0x14000d9f6  pop     rbp
0x14000d9f7  pop     rbx
0x14000d9f8  retn
```
