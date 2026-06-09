# DepFSCleanupVolumeContext

- ea: `0x180010c00`
- end: `0x180010d8f`
- name: `DepFSCleanupVolumeContext`
- size: `399`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180010da0`
- `0x180010fd0`

## callees

- `0x1800010b8`
- `0x180001150`
- `0x180001ca8`
- `0x180010c00`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010d6e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180010d6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010d47`
- `ntoskrnl!ExFreePoolWithTag` at `0x180010d47`
- `ntoskrnl!ExReleaseResourceLite` at `0x180010d62`
- `ntoskrnl!ExReleaseResourceLite` at `0x180010d62`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010c25`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010c25`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180010c10`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180010c10`

## pseudocode

```c
void __fastcall DepFSCleanupVolumeContext(_QWORD *a1)
{
  _QWORD *i; // rbx
  _QWORD *v3; // rbx
  _QWORD *v4; // rsi
  _QWORD *v5; // r14
  _QWORD *v6; // rcx
  _QWORD *v7; // r8
  _QWORD *v8; // rdx
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  __int64 v11; // rax
  _QWORD *v12; // rcx
  void *v13; // rcx

  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  for ( i = a1 + 3; (_QWORD *)*i != i; DepFSDeleteParentLink((char *)(*i - 24LL)) )
    ;
  v3 = a1 + 1;
  v4 = (_QWORD *)a1[1];
  if ( v4 != a1 + 1 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qq(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x17u,
          (__int64)WPP_f74f0f1428a330a1ddba74e336bf7301_Traceguids,
          v4 - 1,
          a1);
      }
      v4[13] = 0;
      v6 = (_QWORD *)*v4;
      if ( *(_QWORD **)(*v4 + 8LL) != v4 )
        goto LABEL_24;
      v7 = v4 + 1;
      v8 = (_QWORD *)v4[1];
      if ( (_QWORD *)*v8 != v4 )
        goto LABEL_24;
      *v8 = v6;
      v9 = v4;
      v6[1] = v8;
      v4 = v5;
      *v7 = v9;
      *v9 = v9;
    }
    while ( v5 != v3 );
    a1[2] = a1 + 1;
    *v3 = v3;
  }
  v10 = a1 + 5;
  if ( (_QWORD *)*v10 != v10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x18u,
        (__int64)WPP_f74f0f1428a330a1ddba74e336bf7301_Traceguids,
        a1);
    }
    v11 = *v10;
    if ( *(_QWORD **)(*v10 + 8LL) != v10 || (v12 = (_QWORD *)a1[6], (_QWORD *)*v12 != v10) )
LABEL_24:
      __fastfail(3u);
    *v12 = v11;
    *(_QWORD *)(v11 + 8) = v12;
    a1[6] = a1 + 5;
    *v10 = v10;
    --dword_180005190;
  }
  v13 = (void *)a1[15];
  if ( v13 )
  {
    ExFreePoolWithTag(v13, 0x73447044u);
    a1[15] = 0;
  }
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x180010c00  push    rbx
0x180010c02  push    rbp
0x180010c03  push    rsi
0x180010c04  push    rdi
0x180010c05  push    r14
0x180010c07  push    r15
0x180010c09  sub     rsp, 38h
0x180010c0d  mov     rdi, rcx
0x180010c10  call    cs:__imp_KeEnterCriticalRegion
0x180010c17  nop     dword ptr [rax+rax+00h]
0x180010c1c  mov     dl, 1; Wait
0x180010c1e  lea     rcx, Resource; Resource
0x180010c25  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180010c2c  nop     dword ptr [rax+rax+00h]
0x180010c31  lea     rbx, [rdi+18h]
0x180010c35  mov     rcx, [rbx]
0x180010c38  cmp     rcx, rbx
0x180010c3b  jz      short loc_180010C48
0x180010c3d  add     rcx, 0FFFFFFFFFFFFFFE8h; P
0x180010c41  call    DepFSDeleteParentLink
0x180010c46  jmp     short loc_180010C35
0x180010c48  lea     rbx, [rdi+8]
0x180010c4c  mov     rsi, [rbx]
0x180010c4f  lea     r15, WPP_GLOBAL_Control
0x180010c56  cmp     rsi, rbx
0x180010c59  jz      short loc_180010CD9
0x180010c5b  mov     r14, [rsi]
0x180010c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c65  cmp     rcx, r15
0x180010c68  jz      short loc_180010C95
0x180010c6a  mov     eax, [rcx+2Ch]
0x180010c6d  test    al, 20h
0x180010c6f  jz      short loc_180010C95
0x180010c71  cmp     byte ptr [rcx+29h], 4
0x180010c75  jb      short loc_180010C95
0x180010c77  mov     rcx, [rcx+18h]
0x180010c7b  lea     r9, [rsi-8]
0x180010c7f  mov     edx, 17h
0x180010c84  mov     [rsp+68h+var_48], rdi
0x180010c89  lea     r8, WPP_f74f0f1428a330a1ddba74e336bf7301_Traceguids
0x180010c90  call    WPP_SF_qq
0x180010c95  mov     qword ptr [rsi+68h], 0
0x180010c9d  mov     rcx, [rsi]
0x180010ca0  cmp     [rcx+8], rsi
0x180010ca4  jnz     loc_180010D88
0x180010caa  lea     r8, [rsi+8]
0x180010cae  mov     rdx, [r8]
0x180010cb1  cmp     [rdx], rsi
0x180010cb4  jnz     loc_180010D88
0x180010cba  mov     [rdx], rcx
0x180010cbd  mov     rax, rsi
0x180010cc0  mov     [rcx+8], rdx
0x180010cc4  mov     rsi, r14
0x180010cc7  mov     [r8], rax
0x180010cca  mov     [rax], rax
0x180010ccd  cmp     r14, rbx
0x180010cd0  jnz     short loc_180010C5B
0x180010cd2  mov     [rbx+8], rbx
0x180010cd6  mov     [rbx], rbx
0x180010cd9  lea     rbx, [rdi+28h]
0x180010cdd  cmp     [rbx], rbx
0x180010ce0  jz      short loc_180010D39
0x180010ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ce9  cmp     rcx, r15
0x180010cec  jz      short loc_180010D13
0x180010cee  mov     eax, [rcx+2Ch]
0x180010cf1  test    al, 20h
0x180010cf3  jz      short loc_180010D13
0x180010cf5  cmp     byte ptr [rcx+29h], 4
0x180010cf9  jb      short loc_180010D13
0x180010cfb  mov     rcx, [rcx+18h]
0x180010cff  lea     r8, WPP_f74f0f1428a330a1ddba74e336bf7301_Traceguids
0x180010d06  mov     edx, 18h
0x180010d0b  mov     r9, rdi
0x180010d0e  call    WPP_SF_q
0x180010d13  mov     rax, [rbx]
0x180010d16  cmp     [rax+8], rbx
0x180010d1a  jnz     short loc_180010D88
0x180010d1c  mov     rcx, [rbx+8]
0x180010d20  cmp     [rcx], rbx
0x180010d23  jnz     short loc_180010D88
0x180010d25  mov     [rcx], rax
0x180010d28  mov     [rax+8], rcx
0x180010d2c  mov     [rbx+8], rbx
0x180010d30  mov     [rbx], rbx
0x180010d33  dec     cs:dword_180005190
0x180010d39  mov     rcx, [rdi+78h]; P
0x180010d3d  test    rcx, rcx
0x180010d40  jz      short loc_180010D5B
0x180010d42  mov     edx, 73447044h; Tag
0x180010d47  call    cs:__imp_ExFreePoolWithTag
0x180010d4e  nop     dword ptr [rax+rax+00h]
0x180010d53  mov     qword ptr [rdi+78h], 0
0x180010d5b  lea     rcx, Resource; Resource
0x180010d62  call    cs:__imp_ExReleaseResourceLite
0x180010d69  nop     dword ptr [rax+rax+00h]
0x180010d6e  call    cs:__imp_KeLeaveCriticalRegion
0x180010d75  nop     dword ptr [rax+rax+00h]
0x180010d7a  add     rsp, 38h
0x180010d7e  pop     r15
0x180010d80  pop     r14
0x180010d82  pop     rdi
0x180010d83  pop     rsi
0x180010d84  pop     rbp
0x180010d85  pop     rbx
0x180010d86  retn
0x180010d88  mov     ecx, 3
0x180010d8d  int     29h; Win8: RtlFailFast(ecx)
```
