# DereferenceDependencyContext

- ea: `0x18000f73c`
- end: `0x18000f914`
- name: `DereferenceDependencyContext`
- size: `472`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x180008010`
- `0x1800084f4`
- `0x180009840`
- `0x18000a874`
- `0x18000aa48`
- `0x18000aecc`
- `0x18000b5f0`
- `0x18000ce60`
- `0x18000d9d0`
- `0x18000db70`
- `0x18000eac0`
- `0x18000fa10`
- `0x18000fc50`
- `0x18001127c`

## callees

- `0x1800010b8`
- `0x180001ca8`
- `0x18000f73c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f8f7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f8f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f885`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f8bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f8d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f885`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f8bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000f8d3`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000f8eb`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000f8eb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000f76d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000f76d`
- `ntoskrnl!ObfDereferenceObject` at `0x18000f80c`
- `ntoskrnl!ObfDereferenceObject` at `0x18000f868`
- `ntoskrnl!ObfDereferenceObject` at `0x18000f80c`
- `ntoskrnl!ObfDereferenceObject` at `0x18000f868`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000f758`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000f758`

## pseudocode

```c
void __fastcall DereferenceDependencyContext(_QWORD *P, char a2, char a3)
{
  char *v6; // rax
  __int64 v7; // rcx
  char **v8; // rdx
  void *v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // rcx
  _QWORD *v13; // rdx
  _QWORD *i; // rdi
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx

  if ( !a2 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
  }
  if ( a3 )
  {
    v6 = (char *)(P + 5);
    if ( *(char **)v6 != v6 )
    {
      --dword_180005180;
      v7 = *(_QWORD *)v6;
      if ( *(char **)(*(_QWORD *)v6 + 8LL) != v6 )
        goto LABEL_22;
      v8 = (char **)P[6];
      if ( *v8 != v6 )
        goto LABEL_22;
      *v8 = (char *)v7;
      *(_QWORD *)(v7 + 8) = v8;
      P[6] = P + 5;
      *(_QWORD *)v6 = v6;
      --*((_DWORD *)P + 14);
    }
  }
  if ( (*((_DWORD *)P + 14))-- != 1 )
    goto LABEL_32;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids, P);
  }
  v10 = (void *)P[16];
  if ( v10 )
    ObfDereferenceObject(v10);
  v11 = P + 1;
  v12 = (_QWORD *)P[1];
  if ( v12 != P + 1 )
  {
    if ( (_QWORD *)v12[1] == v11 )
    {
      v13 = (_QWORD *)P[2];
      if ( (_QWORD *)*v13 == v11 )
      {
        *v13 = v12;
        v12[1] = v13;
        P[2] = P + 1;
        *v11 = v11;
        goto LABEL_19;
      }
    }
LABEL_22:
    __fastfail(3u);
  }
LABEL_19:
  for ( i = P + 3; (_QWORD *)*i != i; DepFSDeleteParentLink((char *)(*i - 40LL)) )
    ;
  v15 = (void *)P[13];
  if ( v15 )
    ObfDereferenceObject(v15);
  v16 = (void *)P[18];
  if ( v16 )
    ExFreePoolWithTag(v16, 0x70527044u);
  v17 = (void *)P[21];
  if ( v17 )
    ExFreePoolWithTag(v17, 0x63417044u);
  v18 = (void *)P[20];
  if ( v18 )
    ExFreePoolWithTag(v18, 0x64447044u);
  ExFreePoolWithTag(P, 0x63447044u);
LABEL_32:
  if ( !a2 )
  {
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x18000f73c  mov     [rsp+arg_0], rbx
0x18000f741  mov     [rsp+arg_10], rsi
0x18000f746  push    rdi
0x18000f747  sub     rsp, 20h
0x18000f74b  mov     dil, r8b
0x18000f74e  mov     sil, dl
0x18000f751  mov     rbx, rcx
0x18000f754  test    dl, dl
0x18000f756  jnz     short loc_18000F779
0x18000f758  call    cs:__imp_KeEnterCriticalRegion
0x18000f75f  nop     dword ptr [rax+rax+00h]
0x18000f764  mov     dl, 1; Wait
0x18000f766  lea     rcx, Resource; Resource
0x18000f76d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000f774  nop     dword ptr [rax+rax+00h]
0x18000f779  or      r8d, 0FFFFFFFFh
0x18000f77d  test    dil, dil
0x18000f780  jz      short loc_18000F7BE
0x18000f782  lea     rax, [rbx+28h]
0x18000f786  cmp     [rax], rax
0x18000f789  jz      short loc_18000F7BE
0x18000f78b  add     cs:dword_180005180, r8d
0x18000f792  mov     rcx, [rax]
0x18000f795  cmp     [rcx+8], rax
0x18000f799  jnz     loc_18000F858
0x18000f79f  mov     rdx, [rax+8]
0x18000f7a3  cmp     [rdx], rax
0x18000f7a6  jnz     loc_18000F858
0x18000f7ac  mov     [rdx], rcx
0x18000f7af  mov     [rcx+8], rdx
0x18000f7b3  mov     [rax+8], rax
0x18000f7b7  mov     [rax], rax
0x18000f7ba  add     [rbx+38h], r8d
0x18000f7be  add     [rbx+38h], r8d
0x18000f7c2  jnz     loc_18000F8DF
0x18000f7c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7cf  lea     rax, WPP_GLOBAL_Control
0x18000f7d6  cmp     rcx, rax
0x18000f7d9  jz      short loc_18000F800
0x18000f7db  mov     eax, [rcx+2Ch]
0x18000f7de  test    al, 20h
0x18000f7e0  jz      short loc_18000F800
0x18000f7e2  cmp     byte ptr [rcx+29h], 4
0x18000f7e6  jb      short loc_18000F800
0x18000f7e8  mov     rcx, [rcx+18h]
0x18000f7ec  lea     r8, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids
0x18000f7f3  mov     edx, 0Dh
0x18000f7f8  mov     r9, rbx
0x18000f7fb  call    WPP_SF_q
0x18000f800  mov     rcx, [rbx+80h]; Object
0x18000f807  test    rcx, rcx
0x18000f80a  jz      short loc_18000F818
0x18000f80c  call    cs:__imp_ObfDereferenceObject
0x18000f813  nop     dword ptr [rax+rax+00h]
0x18000f818  lea     rax, [rbx+8]
0x18000f81c  mov     rcx, [rax]
0x18000f81f  cmp     rcx, rax
0x18000f822  jz      short loc_18000F841
0x18000f824  cmp     [rcx+8], rax
0x18000f828  jnz     short loc_18000F858
0x18000f82a  mov     rdx, [rax+8]
0x18000f82e  cmp     [rdx], rax
0x18000f831  jnz     short loc_18000F858
0x18000f833  mov     [rdx], rcx
0x18000f836  mov     [rcx+8], rdx
0x18000f83a  mov     [rax+8], rax
0x18000f83e  mov     [rax], rax
0x18000f841  lea     rdi, [rbx+18h]
0x18000f845  mov     rcx, [rdi]
0x18000f848  cmp     rcx, rdi
0x18000f84b  jz      short loc_18000F85F
0x18000f84d  add     rcx, 0FFFFFFFFFFFFFFD8h; P
0x18000f851  call    DepFSDeleteParentLink
0x18000f856  jmp     short loc_18000F845
0x18000f858  mov     ecx, 3
0x18000f85d  int     29h; Win8: RtlFailFast(ecx)
0x18000f85f  mov     rcx, [rbx+68h]; Object
0x18000f863  test    rcx, rcx
0x18000f866  jz      short loc_18000F874
0x18000f868  call    cs:__imp_ObfDereferenceObject
0x18000f86f  nop     dword ptr [rax+rax+00h]
0x18000f874  mov     rcx, [rbx+90h]; P
0x18000f87b  test    rcx, rcx
0x18000f87e  jz      short loc_18000F891
0x18000f880  mov     edx, 70527044h; Tag
0x18000f885  call    cs:__imp_ExFreePoolWithTag
0x18000f88c  nop     dword ptr [rax+rax+00h]
0x18000f891  mov     rcx, [rbx+0A8h]; P
0x18000f898  test    rcx, rcx
0x18000f89b  jz      short loc_18000F8AE
0x18000f89d  mov     edx, 63417044h; Tag
0x18000f8a2  call    cs:__imp_ExFreePoolWithTag
0x18000f8a9  nop     dword ptr [rax+rax+00h]
0x18000f8ae  mov     rcx, [rbx+0A0h]; P
0x18000f8b5  test    rcx, rcx
0x18000f8b8  jz      short loc_18000F8CB
0x18000f8ba  mov     edx, 64447044h; Tag
0x18000f8bf  call    cs:__imp_ExFreePoolWithTag
0x18000f8c6  nop     dword ptr [rax+rax+00h]
0x18000f8cb  mov     edx, 63447044h; Tag
0x18000f8d0  mov     rcx, rbx; P
0x18000f8d3  call    cs:__imp_ExFreePoolWithTag
0x18000f8da  nop     dword ptr [rax+rax+00h]
0x18000f8df  test    sil, sil
0x18000f8e2  jnz     short loc_18000F903
0x18000f8e4  lea     rcx, Resource; Resource
0x18000f8eb  call    cs:__imp_ExReleaseResourceLite
0x18000f8f2  nop     dword ptr [rax+rax+00h]
0x18000f8f7  call    cs:__imp_KeLeaveCriticalRegion
0x18000f8fe  nop     dword ptr [rax+rax+00h]
0x18000f903  mov     rbx, [rsp+28h+arg_0]
0x18000f908  mov     rsi, [rsp+28h+arg_10]
0x18000f90d  add     rsp, 20h
0x18000f911  pop     rdi
0x18000f912  retn
```
