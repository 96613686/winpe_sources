# DependentFSDismountForUnsurface

- ea: `0x18000b5f0`
- end: `0x18000b95e`
- name: `DependentFSDismountForUnsurface`
- size: `878`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001020`
- `0x180001150`
- `0x1800015a8`
- `0x18000aecc`
- `0x18000b5f0`
- `0x18000eac0`
- `0x18000f73c`

## import_xrefs

- `ntoskrnl!KeWaitForMultipleObjects` at `0x18000b74d`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x18000b7b2`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x18000b74d`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x18000b7b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b777`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b8fb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b777`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b8fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b8c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b8c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000b76b`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000b8ef`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000b76b`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000b8ef`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000b68c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000b7fb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000b68c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000b7fb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000b677`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000b7e5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000b677`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000b7e5`

## pseudocode

```c
__int64 __fastcall DependentFSDismountForUnsurface(__int64 a1, __int64 a2, __int64 a3, __int64 **a4)
{
  unsigned int v6; // esi
  __int64 v7; // rbx
  char v8; // di
  __int64 **v9; // rax
  __int64 *v10; // rcx
  int WaitMode; // [rsp+20h] [rbp-40h]
  union _LARGE_INTEGER Timeout; // [rsp+40h] [rbp-20h] BYREF
  PVOID P; // [rsp+48h] [rbp-18h] BYREF
  PVOID Object[2]; // [rsp+50h] [rbp-10h] BYREF

  P = 0;
  *(_OWORD *)Object = 0;
  Timeout.QuadPart = 0;
  if ( byte_180005194 || byte_180005196 )
    return 0;
  v6 = 0;
  v7 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, a1, a4);
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  v8 = 1;
  if ( byte_180005194 )
    goto LABEL_33;
  if ( byte_180005196 )
    goto LABEL_33;
  if ( !dword_180005180 )
    goto LABEL_33;
  v9 = (__int64 **)qword_1800051B0;
  if ( (__int64 *)qword_1800051B0 == &qword_1800051B0 )
    goto LABEL_33;
  do
  {
    v10 = *v9;
    if ( *v9 != (__int64 *)v9 )
    {
      v7 = (__int64)(v9 - 5);
      if ( v9 - 5 == a4 && (*(_DWORD *)(v7 + 92) & 3) == 0 )
        break;
    }
    v9 = (__int64 **)*v9;
    v7 = 0;
  }
  while ( v10 != &qword_1800051B0 );
  if ( !v7 )
    goto LABEL_33;
  ++*(_DWORD *)(v7 + 56);
  _InterlockedIncrement((volatile signed __int32 *)(v7 + 96));
  Timeout.QuadPart = 0;
  Object[0] = (PVOID)(v7 + 200);
  Object[1] = &Event;
  v6 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, &Timeout, 0);
  if ( v6 > 1 )
  {
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    Timeout.QuadPart = -1800000000;
    KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, &Timeout, 0);
    if ( byte_180005194 || byte_180005196 || !dword_180005180 )
      goto LABEL_32;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( byte_180005194
      || byte_180005196
      || !dword_180005180
      || *(_QWORD *)(v7 + 40) == v7 + 40
      || (*(_DWORD *)(v7 + 92) & 3) != 0 )
    {
LABEL_33:
      if ( P )
        ExFreePoolWithTag(P, 0x6C447044u);
      if ( !v7 )
        goto LABEL_37;
      goto LABEL_36;
    }
  }
  LOBYTE(WaitMode) = 1;
  v6 = DepFSGenerateDependencyList(v7, 0, 0, &P, WaitMode, 256);
  if ( (v6 & 0x80000000) != 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, v6);
  }
  v8 = 1;
  if ( P )
  {
    v6 = DepFSDismountDependencyList((__int64)P, v7, 0);
LABEL_32:
    v8 = 0;
    goto LABEL_33;
  }
LABEL_36:
  DereferenceDependencyContext((PVOID)v7);
LABEL_37:
  if ( v8 )
  {
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, a1, a4, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18000b5f0  push    rbp
0x18000b5f2  push    rbx
0x18000b5f3  push    rsi
0x18000b5f4  push    rdi
0x18000b5f5  push    r12
0x18000b5f7  push    r14
0x18000b5f9  push    r15
0x18000b5fb  mov     rbp, rsp
0x18000b5fe  sub     rsp, 60h
0x18000b602  xor     r12d, r12d
0x18000b605  xorps   xmm0, xmm0
0x18000b608  cmp     cs:byte_180005194, r12b
0x18000b60f  mov     r14, r9
0x18000b612  mov     r15, rcx
0x18000b615  mov     [rbp+P], r12
0x18000b619  movups  xmmword ptr [rbp+Object], xmm0
0x18000b61d  mov     qword ptr [rbp+var_20], r12
0x18000b621  jnz     loc_18000B94C
0x18000b627  cmp     cs:byte_180005196, r12b
0x18000b62e  jnz     loc_18000B94C
0x18000b634  mov     esi, r12d
0x18000b637  mov     ebx, r12d
0x18000b63a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b641  lea     rax, WPP_GLOBAL_Control
0x18000b648  cmp     rcx, rax
0x18000b64b  jz      short loc_18000B677
0x18000b64d  mov     eax, [rcx+2Ch]
0x18000b650  test    al, 10h
0x18000b652  jz      short loc_18000B677
0x18000b654  cmp     byte ptr [rcx+29h], 4
0x18000b658  jb      short loc_18000B677
0x18000b65a  mov     rcx, [rcx+18h]
0x18000b65e  lea     edx, [r12+17h]
0x18000b663  mov     qword ptr [rsp+60h+WaitMode], r9
0x18000b668  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000b66f  mov     r9, r15
0x18000b672  call    WPP_SF_qq
0x18000b677  call    cs:__imp_KeEnterCriticalRegion
0x18000b67e  nop     dword ptr [rax+rax+00h]
0x18000b683  mov     dl, 1; Wait
0x18000b685  lea     rcx, Resource; Resource
0x18000b68c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000b693  nop     dword ptr [rax+rax+00h]
0x18000b698  cmp     cs:byte_180005194, r12b
0x18000b69f  mov     dil, 1
0x18000b6a2  jnz     loc_18000B8B6
0x18000b6a8  cmp     cs:byte_180005196, r12b
0x18000b6af  jnz     loc_18000B8B6
0x18000b6b5  cmp     cs:dword_180005180, r12d
0x18000b6bc  jz      loc_18000B8B6
0x18000b6c2  mov     rax, cs:qword_1800051B0
0x18000b6c9  lea     rdx, qword_1800051B0
0x18000b6d0  cmp     rax, rdx
0x18000b6d3  jz      loc_18000B8B6
0x18000b6d9  mov     rcx, [rax]
0x18000b6dc  cmp     rcx, rax
0x18000b6df  jz      short loc_18000B6F1
0x18000b6e1  lea     rbx, [rax-28h]
0x18000b6e5  cmp     rbx, r14
0x18000b6e8  jnz     short loc_18000B6F1
0x18000b6ea  mov     eax, [rbx+5Ch]
0x18000b6ed  test    al, 3
0x18000b6ef  jz      short loc_18000B6FC
0x18000b6f1  mov     rax, rcx
0x18000b6f4  mov     rbx, r12
0x18000b6f7  cmp     rcx, rdx
0x18000b6fa  jnz     short loc_18000B6D9
0x18000b6fc  test    rbx, rbx
0x18000b6ff  jz      loc_18000B8B6
0x18000b705  inc     dword ptr [rbx+38h]
0x18000b708  lock inc dword ptr [rbx+60h]
0x18000b70c  xor     r9d, r9d; WaitReason
0x18000b70f  mov     [rsp+60h+WaitBlockArray], r12; WaitBlockArray
0x18000b714  lea     rax, [rbx+0C8h]
0x18000b71b  mov     qword ptr [rbp+var_20], r12
0x18000b71f  mov     [rbp+Object], rax
0x18000b723  lea     rdx, [rbp+Object]; Object
0x18000b727  lea     rax, Event
0x18000b72e  mov     [rbp+Object+8], rax
0x18000b732  lea     r8d, [r9+1]; WaitType
0x18000b736  lea     rax, [rbp+var_20]
0x18000b73a  mov     [rsp+60h+Timeout], rax; Timeout
0x18000b73f  lea     ecx, [r9+2]; Count
0x18000b743  mov     [rsp+60h+Alertable], r12b; Alertable
0x18000b748  mov     [rsp+60h+WaitMode], r12b; WaitMode
0x18000b74d  call    cs:__imp_KeWaitForMultipleObjects
0x18000b754  nop     dword ptr [rax+rax+00h]
0x18000b759  mov     esi, eax
0x18000b75b  cmp     eax, 1
0x18000b75e  jbe     loc_18000B83E
0x18000b764  lea     rcx, Resource; Resource
0x18000b76b  call    cs:__imp_ExReleaseResourceLite
0x18000b772  nop     dword ptr [rax+rax+00h]
0x18000b777  call    cs:__imp_KeLeaveCriticalRegion
0x18000b77e  nop     dword ptr [rax+rax+00h]
0x18000b783  xor     r9d, r9d; WaitReason
0x18000b786  mov     [rsp+60h+WaitBlockArray], r12; WaitBlockArray
0x18000b78b  lea     rax, [rbp+var_20]
0x18000b78f  mov     qword ptr [rbp+var_20], 0FFFFFFFF94B62E00h
0x18000b797  mov     [rsp+60h+Timeout], rax; Timeout
0x18000b79c  lea     rdx, [rbp+Object]; Object
0x18000b7a0  mov     [rsp+60h+Alertable], r12b; Alertable
0x18000b7a5  lea     r8d, [r9+1]; WaitType
0x18000b7a9  mov     [rsp+60h+WaitMode], r12b; WaitMode
0x18000b7ae  lea     ecx, [r9+2]; Count
0x18000b7b2  call    cs:__imp_KeWaitForMultipleObjects
0x18000b7b9  nop     dword ptr [rax+rax+00h]
0x18000b7be  cmp     cs:byte_180005194, r12b
0x18000b7c5  jnz     loc_18000B8B3
0x18000b7cb  cmp     cs:byte_180005196, r12b
0x18000b7d2  jnz     loc_18000B8B3
0x18000b7d8  cmp     cs:dword_180005180, r12d
0x18000b7df  jz      loc_18000B8B3
0x18000b7e5  call    cs:__imp_KeEnterCriticalRegion
0x18000b7ec  nop     dword ptr [rax+rax+00h]
0x18000b7f1  mov     dl, dil; Wait
0x18000b7f4  lea     rcx, Resource; Resource
0x18000b7fb  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000b802  nop     dword ptr [rax+rax+00h]
0x18000b807  cmp     cs:byte_180005194, r12b
0x18000b80e  jnz     loc_18000B8B6
0x18000b814  cmp     cs:byte_180005196, r12b
0x18000b81b  jnz     loc_18000B8B6
0x18000b821  cmp     cs:dword_180005180, r12d
0x18000b828  jz      loc_18000B8B6
0x18000b82e  lea     rax, [rbx+28h]
0x18000b832  cmp     [rax], rax
0x18000b835  jz      short loc_18000B8B6
0x18000b837  mov     eax, [rbx+5Ch]
0x18000b83a  test    al, 3
0x18000b83c  jnz     short loc_18000B8B6
0x18000b83e  mov     dword ptr [rsp+60h+Alertable], 100h
0x18000b846  lea     r9, [rbp+P]
0x18000b84a  xor     r8d, r8d
0x18000b84d  mov     [rsp+60h+WaitMode], 1
0x18000b852  xor     edx, edx
0x18000b854  mov     rcx, rbx
0x18000b857  call    DepFSGenerateDependencyList
0x18000b85c  mov     esi, eax
0x18000b85e  test    eax, eax
0x18000b860  jns     short loc_18000B89A
0x18000b862  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b869  lea     rax, WPP_GLOBAL_Control
0x18000b870  cmp     rcx, rax
0x18000b873  jz      short loc_18000B89A
0x18000b875  mov     eax, [rcx+2Ch]
0x18000b878  test    al, 1
0x18000b87a  jz      short loc_18000B89A
0x18000b87c  cmp     byte ptr [rcx+29h], 2
0x18000b880  jb      short loc_18000B89A
0x18000b882  mov     rcx, [rcx+18h]
0x18000b886  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000b88d  mov     edx, 18h
0x18000b892  mov     r9d, esi
0x18000b895  call    WPP_SF_D
0x18000b89a  mov     rcx, [rbp+P]
0x18000b89e  mov     dil, 1
0x18000b8a1  test    rcx, rcx
0x18000b8a4  jz      short loc_18000B8D5
0x18000b8a6  xor     r8d, r8d
0x18000b8a9  mov     rdx, rbx
0x18000b8ac  call    DepFSDismountDependencyList
0x18000b8b1  mov     esi, eax
0x18000b8b3  mov     dil, r12b
0x18000b8b6  mov     rcx, [rbp+P]; P
0x18000b8ba  test    rcx, rcx
0x18000b8bd  jz      short loc_18000B8D0
0x18000b8bf  mov     edx, 6C447044h; Tag
0x18000b8c4  call    cs:__imp_ExFreePoolWithTag
0x18000b8cb  nop     dword ptr [rax+rax+00h]
0x18000b8d0  test    rbx, rbx
0x18000b8d3  jz      short loc_18000B8E3
0x18000b8d5  xor     r8d, r8d
0x18000b8d8  mov     dl, dil
0x18000b8db  mov     rcx, rbx; P
0x18000b8de  call    DereferenceDependencyContext
0x18000b8e3  test    dil, dil
0x18000b8e6  jz      short loc_18000B907
0x18000b8e8  lea     rcx, Resource; Resource
0x18000b8ef  call    cs:__imp_ExReleaseResourceLite
0x18000b8f6  nop     dword ptr [rax+rax+00h]
0x18000b8fb  call    cs:__imp_KeLeaveCriticalRegion
0x18000b902  nop     dword ptr [rax+rax+00h]
0x18000b907  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b90e  lea     rax, WPP_GLOBAL_Control
0x18000b915  cmp     rcx, rax
0x18000b918  jz      short loc_18000B948
0x18000b91a  mov     eax, [rcx+2Ch]
0x18000b91d  test    al, 10h
0x18000b91f  jz      short loc_18000B948
0x18000b921  cmp     byte ptr [rcx+29h], 4
0x18000b925  jb      short loc_18000B948
0x18000b927  mov     rcx, [rcx+18h]
0x18000b92b  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000b932  mov     edx, 19h
0x18000b937  mov     dword ptr [rsp+60h+Alertable], esi
0x18000b93b  mov     r9, r15
0x18000b93e  mov     qword ptr [rsp+60h+WaitMode], r14
0x18000b943  call    WPP_SF_qqD
0x18000b948  mov     eax, esi
0x18000b94a  jmp     short loc_18000B94E
0x18000b94c  xor     eax, eax
0x18000b94e  add     rsp, 60h
0x18000b952  pop     r15
0x18000b954  pop     r14
0x18000b956  pop     r12
0x18000b958  pop     rdi
0x18000b959  pop     rsi
0x18000b95a  pop     rbx
0x18000b95b  pop     rbp
0x18000b95c  retn
```
