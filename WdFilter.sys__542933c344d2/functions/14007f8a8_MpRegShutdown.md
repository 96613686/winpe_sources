# MpRegShutdown

- ea: `0x14007f8a8`
- end: `0x14007fa82`
- name: `MpRegShutdown`
- size: `474`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14007bef0`
- `0x14008f314`

## callees

- `0x14007f8a8`
- `0x14007fd30`

## import_xrefs

- `ntoskrnl!CmUnRegisterCallback` at `0x14007f8c2`
- `ntoskrnl!CmUnRegisterCallback` at `0x14007f942`
- `ntoskrnl!CmUnRegisterCallback` at `0x14007f8c2`
- `ntoskrnl!CmUnRegisterCallback` at `0x14007f942`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f908`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f91c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f96e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fa6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f908`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f91c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f96e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007fa6f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007f98a`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007f9a4`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007f9be`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007f9d8`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007f9f2`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007fa0c`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007fa26`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007fa40`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007f98a`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007f9a4`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007f9be`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007f9d8`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007f9f2`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007fa0c`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007fa26`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14007fa40`
- `FLTMGR!FltDeletePushLock` at `0x14007fa57`
- `FLTMGR!FltDeletePushLock` at `0x14007fa57`

## pseudocode

```c
void MpRegShutdown()
{
  _QWORD *v0; // rax
  _QWORD *v1; // rcx
  _QWORD *v2; // rbx
  __int64 v3; // rax
  void *v4; // rcx
  void *v5; // rcx

  if ( MpRegData )
  {
    CmUnRegisterCallback(*(LARGE_INTEGER *)((char *)MpRegData + 48));
    while ( 1 )
    {
      v0 = MpRegData;
      v1 = (char *)MpRegData + 280;
      v2 = (_QWORD *)*((_QWORD *)MpRegData + 35);
      if ( v2 == (_QWORD *)((char *)MpRegData + 280) )
        break;
      if ( (_QWORD *)v2[1] != v1 || (v3 = *v2, *(_QWORD **)(*v2 + 8LL) != v2) )
        __fastfail(3u);
      *v1 = v3;
      *(_QWORD *)(v3 + 8) = v1;
      v4 = (void *)v2[2];
      if ( v4 )
        ExFreePoolWithTag(v4, 0x4B72504Du);
      ExFreePoolWithTag(v2, 0x7461504Du);
    }
    if ( *((_QWORD *)MpRegData + 31) )
    {
      CmUnRegisterCallback(*(LARGE_INTEGER *)((char *)MpRegData + 248));
      v0 = MpRegData;
      *((_QWORD *)MpRegData + 31) = 0;
    }
    v5 = (void *)v0[2];
    if ( v5 )
      ExFreePoolWithTag(v5, 0x4D72504Du);
    MpRegpFreeAllCallContextsUnsafe();
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64));
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 3);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 4);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 5);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 6);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 7);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 8);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 9);
    FltDeletePushLock((PULONG_PTR)MpRegData + 1);
    ExFreePoolWithTag(MpRegData, 0x4472504Du);
  }
}

```

## disassembly

```asm
0x14007f8a8  push    rbx
0x14007f8aa  sub     rsp, 20h
0x14007f8ae  mov     rcx, cs:MpRegData
0x14007f8b5  test    rcx, rcx
0x14007f8b8  jz      loc_14007FA7B
0x14007f8be  mov     rcx, [rcx+30h]; Cookie
0x14007f8c2  call    cs:__imp_CmUnRegisterCallback
0x14007f8c9  nop     dword ptr [rax+rax+00h]
0x14007f8ce  mov     rax, cs:MpRegData
0x14007f8d5  lea     rcx, [rax+118h]
0x14007f8dc  mov     rbx, [rcx]
0x14007f8df  cmp     rbx, rcx
0x14007f8e2  jz      short loc_14007F931
0x14007f8e4  cmp     [rbx+8], rcx
0x14007f8e8  jnz     short loc_14007F92A
0x14007f8ea  mov     rax, [rbx]
0x14007f8ed  cmp     [rax+8], rbx
0x14007f8f1  jnz     short loc_14007F92A
0x14007f8f3  mov     [rcx], rax
0x14007f8f6  mov     [rax+8], rcx
0x14007f8fa  mov     rcx, [rbx+10h]; P
0x14007f8fe  test    rcx, rcx
0x14007f901  jz      short loc_14007F914
0x14007f903  mov     edx, 4B72504Dh; Tag
0x14007f908  call    cs:__imp_ExFreePoolWithTag
0x14007f90f  nop     dword ptr [rax+rax+00h]
0x14007f914  mov     edx, 7461504Dh; Tag
0x14007f919  mov     rcx, rbx; P
0x14007f91c  call    cs:__imp_ExFreePoolWithTag
0x14007f923  nop     dword ptr [rax+rax+00h]
0x14007f928  jmp     short loc_14007F8CE
0x14007f92a  mov     ecx, 3
0x14007f92f  int     29h; Win8: RtlFailFast(ecx)
0x14007f931  cmp     qword ptr [rax+0F8h], 0
0x14007f939  jz      short loc_14007F960
0x14007f93b  mov     rcx, [rax+0F8h]; Cookie
0x14007f942  call    cs:__imp_CmUnRegisterCallback
0x14007f949  nop     dword ptr [rax+rax+00h]
0x14007f94e  mov     rax, cs:MpRegData
0x14007f955  mov     qword ptr [rax+0F8h], 0
0x14007f960  mov     rcx, [rax+10h]; P
0x14007f964  test    rcx, rcx
0x14007f967  jz      short loc_14007F97A
0x14007f969  mov     edx, 4D72504Dh; Tag
0x14007f96e  call    cs:__imp_ExFreePoolWithTag
0x14007f975  nop     dword ptr [rax+rax+00h]
0x14007f97a  call    MpRegpFreeAllCallContextsUnsafe
0x14007f97f  mov     rcx, cs:MpRegData
0x14007f986  add     rcx, 40h ; '@'; Lookaside
0x14007f98a  call    cs:__imp_ExDeletePagedLookasideList
0x14007f991  nop     dword ptr [rax+rax+00h]
0x14007f996  mov     rcx, cs:MpRegData
0x14007f99d  add     rcx, 180h; Lookaside
0x14007f9a4  call    cs:__imp_ExDeletePagedLookasideList
0x14007f9ab  nop     dword ptr [rax+rax+00h]
0x14007f9b0  mov     rcx, cs:MpRegData
0x14007f9b7  add     rcx, 200h; Lookaside
0x14007f9be  call    cs:__imp_ExDeletePagedLookasideList
0x14007f9c5  nop     dword ptr [rax+rax+00h]
0x14007f9ca  mov     rcx, cs:MpRegData
0x14007f9d1  add     rcx, 280h; Lookaside
0x14007f9d8  call    cs:__imp_ExDeletePagedLookasideList
0x14007f9df  nop     dword ptr [rax+rax+00h]
0x14007f9e4  mov     rcx, cs:MpRegData
0x14007f9eb  add     rcx, 300h; Lookaside
0x14007f9f2  call    cs:__imp_ExDeletePagedLookasideList
0x14007f9f9  nop     dword ptr [rax+rax+00h]
0x14007f9fe  mov     rcx, cs:MpRegData
0x14007fa05  add     rcx, 380h; Lookaside
0x14007fa0c  call    cs:__imp_ExDeletePagedLookasideList
0x14007fa13  nop     dword ptr [rax+rax+00h]
0x14007fa18  mov     rcx, cs:MpRegData
0x14007fa1f  add     rcx, 400h; Lookaside
0x14007fa26  call    cs:__imp_ExDeletePagedLookasideList
0x14007fa2d  nop     dword ptr [rax+rax+00h]
0x14007fa32  mov     rcx, cs:MpRegData
0x14007fa39  add     rcx, 480h; Lookaside
0x14007fa40  call    cs:__imp_ExDeletePagedLookasideList
0x14007fa47  nop     dword ptr [rax+rax+00h]
0x14007fa4c  mov     rcx, cs:MpRegData
0x14007fa53  add     rcx, 8; PushLock
0x14007fa57  call    cs:__imp_FltDeletePushLock
0x14007fa5e  nop     dword ptr [rax+rax+00h]
0x14007fa63  mov     rcx, cs:MpRegData; P
0x14007fa6a  mov     edx, 4472504Dh; Tag
0x14007fa6f  call    cs:__imp_ExFreePoolWithTag
0x14007fa76  nop     dword ptr [rax+rax+00h]
0x14007fa7b  add     rsp, 20h
0x14007fa7f  pop     rbx
0x14007fa80  retn
```
