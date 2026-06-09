# MpFgUpdateUserData

- ea: `0x140075108`
- end: `0x1400752a1`
- name: `MpFgUpdateUserData`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14005be60`

## callees

- `0x1400051bc`
- `0x140075108`
- `0x1400786f8`
- `0x1400856dc`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140075247`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140075247`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14007526c`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14007526c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007522d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007522d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140075221`
- `ntoskrnl!ExReleaseResourceLite` at `0x140075221`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400751f3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400751f3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400751e1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400751e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007525b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075285`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007525b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075285`

## pseudocode

```c
__int64 __fastcall MpFgUpdateUserData(__int64 a1, __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  char *v6; // rbx
  char *v7; // rcx
  struct _RTL_AVL_TABLE *v8; // rdi
  void *v9; // rbx
  _QWORD *v10; // rax
  char v11; // [rsp+50h] [rbp+18h] BYREF
  struct _RTL_AVL_TABLE *v12; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  v11 = 0;
  if ( !DeferredContext )
    return 3221225659LL;
  v4 = MpFgValidateUserData();
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return (unsigned int)v4;
    v5 = 23;
    goto LABEL_7;
  }
  _mm_lfence();
  v4 = MpFgCreateProtectedFoldersTable(a2, &v12, &v11);
  if ( v4 >= 0 )
  {
    v6 = (char *)DeferredContext;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v6 + 16), 1u);
    v7 = (char *)DeferredContext;
    v8 = (struct _RTL_AVL_TABLE *)*((_QWORD *)DeferredContext + 1);
    *((_QWORD *)DeferredContext + 1) = v12;
    v7[513] = v11;
    ExReleaseResourceLite((PERESOURCE)(v7 + 16));
    KeLeaveCriticalRegion();
    if ( v8 )
    {
      while ( 1 )
      {
        v10 = RtlEnumerateGenericTableAvl(v8, 1u);
        if ( !v10 )
          break;
        v9 = (void *)v10[2];
        RtlDeleteElementGenericTableAvl(v8, v10);
        ExFreePoolWithTag(v9, 0x6746504Du);
      }
      ExFreePoolWithTag(v8, 0x7046504Du);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v5 = 24;
LABEL_7:
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      WPP_d4b33eac157739e0890aa4122bf243af_Traceguids,
      KeGetCurrentThread(),
      v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140075108  mov     [rsp+arg_0], rbx
0x14007510d  push    rdi
0x14007510e  sub     rsp, 30h
0x140075112  cmp     cs:DeferredContext, 0
0x14007511a  mov     rdi, rdx
0x14007511d  mov     [rsp+38h+arg_18], 0
0x140075126  mov     [rsp+38h+arg_10], 0
0x14007512b  jnz     short loc_140075137
0x14007512d  mov     eax, 0C00000BBh
0x140075132  jmp     loc_140075295
0x140075137  call    MpFgValidateUserData
0x14007513c  mov     ebx, eax
0x14007513e  test    eax, eax
0x140075140  jns     short loc_140075196
0x140075142  mov     rcx, cs:WPP_GLOBAL_Control
0x140075149  lea     rax, WPP_GLOBAL_Control
0x140075150  cmp     rcx, rax
0x140075153  jz      loc_140075293
0x140075159  mov     ecx, [rcx+2Ch]
0x14007515c  test    cl, 1
0x14007515f  jz      loc_140075293
0x140075165  mov     edx, 17h
0x14007516a  lfence
0x14007516d  mov     r9, gs:188h
0x140075176  lea     r8, WPP_d4b33eac157739e0890aa4122bf243af_Traceguids
0x14007517d  mov     rcx, cs:WPP_GLOBAL_Control
0x140075184  mov     [rsp+38h+var_18], ebx
0x140075188  mov     rcx, [rcx+18h]
0x14007518c  call    WPP_SF_qD
0x140075191  jmp     loc_140075293
0x140075196  lfence
0x140075199  lea     r8, [rsp+38h+arg_10]
0x14007519e  mov     rcx, rdi
0x1400751a1  lea     rdx, [rsp+38h+arg_18]
0x1400751a6  call    MpFgCreateProtectedFoldersTable
0x1400751ab  mov     ebx, eax
0x1400751ad  test    eax, eax
0x1400751af  jns     short loc_1400751DA
0x1400751b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400751b8  lea     rax, WPP_GLOBAL_Control
0x1400751bf  cmp     rcx, rax
0x1400751c2  jz      loc_140075293
0x1400751c8  mov     eax, [rcx+2Ch]
0x1400751cb  test    al, 1
0x1400751cd  jz      loc_140075293
0x1400751d3  mov     edx, 18h
0x1400751d8  jmp     short loc_14007516A
0x1400751da  mov     rbx, cs:DeferredContext
0x1400751e1  call    cs:__imp_KeEnterCriticalRegion
0x1400751e8  nop     dword ptr [rax+rax+00h]
0x1400751ed  mov     dl, 1; Wait
0x1400751ef  lea     rcx, [rbx+10h]; Resource
0x1400751f3  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400751fa  nop     dword ptr [rax+rax+00h]
0x1400751ff  mov     rcx, cs:DeferredContext
0x140075206  mov     rax, [rsp+38h+arg_18]
0x14007520b  mov     rdi, [rcx+8]
0x14007520f  mov     [rcx+8], rax
0x140075213  mov     al, [rsp+38h+arg_10]
0x140075217  mov     [rcx+201h], al
0x14007521d  add     rcx, 10h; Resource
0x140075221  call    cs:__imp_ExReleaseResourceLite
0x140075228  nop     dword ptr [rax+rax+00h]
0x14007522d  call    cs:__imp_KeLeaveCriticalRegion
0x140075234  nop     dword ptr [rax+rax+00h]
0x140075239  test    rdi, rdi
0x14007523c  jnz     short loc_140075267
0x14007523e  jmp     short loc_140075291
0x140075240  mov     rbx, [rax+10h]
0x140075244  mov     rdx, rax; Buffer
0x140075247  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14007524e  nop     dword ptr [rax+rax+00h]
0x140075253  mov     edx, 6746504Dh; Tag
0x140075258  mov     rcx, rbx; P
0x14007525b  call    cs:__imp_ExFreePoolWithTag
0x140075262  nop     dword ptr [rax+rax+00h]
0x140075267  mov     dl, 1; Restart
0x140075269  mov     rcx, rdi; Table
0x14007526c  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140075273  nop     dword ptr [rax+rax+00h]
0x140075278  mov     rcx, rdi; P
0x14007527b  test    rax, rax
0x14007527e  jnz     short loc_140075240
0x140075280  mov     edx, 7046504Dh; Tag
0x140075285  call    cs:__imp_ExFreePoolWithTag
0x14007528c  nop     dword ptr [rax+rax+00h]
0x140075291  xor     ebx, ebx
0x140075293  mov     eax, ebx
0x140075295  mov     rbx, [rsp+38h+arg_0]
0x14007529a  add     rsp, 30h
0x14007529e  pop     rdi
0x14007529f  retn
```
