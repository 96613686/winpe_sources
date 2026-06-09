# VisitArray<tagRepairInfo>(tagRepairInfo *,Visitor<tagRepairInfo *> &,unsigned __int64)

- ea: `0x18000c334`
- end: `0x18000c384`
- name: `??$VisitArray@UtagRepairInfo@@@@YAXPEAUtagRepairInfo@@AEAV?$Visitor@PEAUtagRepairInfo@@@@_K@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001101e`

## callees

- `0x18000c334`
- `0x180012010`

## pseudocode

```c
void __fastcall VisitArray<tagRepairInfo>(__int64 a1, __int64 *a2, unsigned __int64 a3)
{
  unsigned int i; // ebx
  __int64 v7; // rax
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF

  if ( a3 )
  {
    for ( i = 0; i < a3; ++i )
    {
      v7 = *a2;
      v8 = a1 + 112LL * i;
      if ( !(*(unsigned int (__fastcall **)(__int64 *, __int64 *))(v7 + 8))(a2, &v8) )
        break;
    }
  }
}

```

## disassembly

```asm
0x18000c334  test    r8, r8
0x18000c337  jz      short locret_18000C383
0x18000c339  push    rbx
0x18000c33a  push    rbp
0x18000c33b  push    rsi
0x18000c33c  push    rdi
0x18000c33d  sub     rsp, 28h
0x18000c341  mov     rdi, r8
0x18000c344  mov     rsi, rdx
0x18000c347  mov     rbp, rcx
0x18000c34a  xor     ebx, ebx
0x18000c34c  mov     eax, ebx
0x18000c34e  lea     rdx, [rsp+48h+arg_10]
0x18000c353  imul    r9, rax, 70h ; 'p'
0x18000c357  mov     rax, [rsi]
0x18000c35a  mov     rcx, rsi
0x18000c35d  add     r9, rbp
0x18000c360  mov     [rsp+48h+arg_10], r9
0x18000c365  mov     rax, [rax+8]
0x18000c369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c36e  test    eax, eax
0x18000c370  jz      short loc_18000C37B
0x18000c372  inc     ebx
0x18000c374  mov     eax, ebx
0x18000c376  cmp     rax, rdi
0x18000c379  jb      short loc_18000C34C
0x18000c37b  add     rsp, 28h
0x18000c37f  pop     rdi
0x18000c380  pop     rsi
0x18000c381  pop     rbp
0x18000c382  pop     rbx
0x18000c383  retn
```
