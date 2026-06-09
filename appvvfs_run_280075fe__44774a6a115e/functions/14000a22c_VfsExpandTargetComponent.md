# VfsExpandTargetComponent

- ea: `0x14000a22c`
- end: `0x14000a3b5`
- name: `VfsExpandTargetComponent`
- size: `393`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, __int64, ULONG)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a5a0`

## callees

- `0x140008c04`
- `0x14000a088`
- `0x14000a22c`
- `0x1400107c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a39a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a39a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e6a`
- `FLTMGR!FltObjectDereference` at `0x14000a382`
- `FLTMGR!FltObjectDereference` at `0x140014e53`
- `FLTMGR!FltObjectDereference` at `0x14000a382`
- `FLTMGR!FltObjectDereference` at `0x140014e53`

## pseudocode

```c
__int64 __fastcall VfsExpandTargetComponent(
        PFLT_INSTANCE Instance,
        __int128 *a2,
        struct _UNICODE_STRING *a3,
        __int64 *a4,
        _DWORD *a5,
        ULONG Length)
{
  __int64 v8; // rdi
  signed int MappedTarget; // ebx
  __int64 v10; // rdi
  PVOID FltObject; // [rsp+38h] [rbp-50h] BYREF
  __int128 v13; // [rsp+40h] [rbp-48h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-38h] BYREF

  v13 = 0;
  *(_OWORD *)P = 0;
  FltObject = 0;
  a5[2] = 0;
  v13 = *a2;
  v8 = *a4;
  if ( !*a4 )
    goto LABEL_6;
  MappedTarget = VfsGetMappedTarget(Instance, (__int64)P, (__int64)&FltObject);
  if ( MappedTarget == -1073741811 )
    MappedTarget = VfsExpandComponentByMapping(v8, (__int64)&v13, a3, (__int64)a5, Length) == 0 ? 0xC0000225 : 0;
  if ( MappedTarget >= 0 && !a5[2] )
  {
LABEL_6:
    if ( FltObject )
    {
      MappedTarget = VfsQueryDirectoryFileName((PFLT_INSTANCE)FltObject, (__int64)P, a3, a5, Length);
      if ( (unsigned int)(MappedTarget + 1073741809) > 0x2B )
        goto LABEL_15;
      v10 = 0x82000000001LL;
      if ( !_bittest64(&v10, MappedTarget + 1073741809) )
        goto LABEL_15;
    }
    else
    {
      v10 = 0x82000000001LL;
    }
    if ( !Instance
      || (MappedTarget = VfsQueryDirectoryFileName(Instance, (__int64)&v13, a3, a5, Length),
          (unsigned int)(MappedTarget + 1073741809) <= 0x2B)
      && _bittest64(&v10, MappedTarget + 1073741809) )
    {
      MappedTarget = -1073741275;
    }
  }
LABEL_15:
  if ( FltObject )
  {
    FltObjectDereference(FltObject);
    if ( P[1] )
      ExFreePoolWithTag(P[1], 0);
  }
  return (unsigned int)MappedTarget;
}

```

## disassembly

```asm
0x14000a22c  mov     r11, rsp
0x14000a22f  push    rbx
0x14000a230  push    rsi
0x14000a231  push    rdi
0x14000a232  push    r14
0x14000a234  push    r15
0x14000a236  sub     rsp, 60h
0x14000a23a  mov     r15, r8
0x14000a23d  mov     r14, rcx
0x14000a240  xorps   xmm0, xmm0
0x14000a243  movups  [rsp+88h+var_48], xmm0
0x14000a248  xorps   xmm1, xmm1
0x14000a24b  movups  xmmword ptr [rsp+88h+P], xmm1
0x14000a250  mov     qword ptr [r11-50h], 0
0x14000a258  mov     rsi, [rsp+88h+arg_20]
0x14000a260  mov     dword ptr [rsi+8], 0
0x14000a267  movups  xmm0, xmmword ptr [rdx]
0x14000a26a  movdqu  [rsp+88h+var_48], xmm0
0x14000a270  mov     rdi, [r9]
0x14000a273  test    rdi, rdi
0x14000a276  jz      short loc_14000A2E0
0x14000a278  lea     rax, [r11-50h]
0x14000a27c  mov     [r11-60h], rax
0x14000a280  lea     rax, [r11-38h]
0x14000a284  mov     [r11-68h], rax
0x14000a288  mov     r9, rdi
0x14000a28b  xor     r8d, r8d
0x14000a28e  lea     rdx, [r11-48h]
0x14000a292  call    VfsGetMappedTarget
0x14000a297  mov     ebx, eax
0x14000a299  cmp     eax, 0C000000Dh
0x14000a29e  jnz     short loc_14000A2CA
0x14000a2a0  mov     eax, [rsp+88h+arg_28]
0x14000a2a7  mov     [rsp+88h+Length], eax
0x14000a2ab  mov     r9, rsi
0x14000a2ae  mov     r8, r15
0x14000a2b1  lea     rdx, [rsp+88h+var_48]
0x14000a2b6  mov     rcx, rdi
0x14000a2b9  call    VfsExpandComponentByMapping
0x14000a2be  neg     al
0x14000a2c0  sbb     ebx, ebx
0x14000a2c2  not     ebx
0x14000a2c4  and     ebx, 0C0000225h
0x14000a2ca  mov     [rsp+88h+var_58], ebx
0x14000a2ce  test    ebx, ebx
0x14000a2d0  js      loc_14000A378
0x14000a2d6  cmp     dword ptr [rsi+8], 0
0x14000a2da  jnz     loc_14000A378
0x14000a2e0  mov     rcx, [rsp+88h+FltObject]; Instance
0x14000a2e5  test    rcx, rcx
0x14000a2e8  jz      short loc_14000A32A
0x14000a2ea  mov     eax, [rsp+88h+arg_28]
0x14000a2f1  mov     [rsp+88h+Length], eax; Length
0x14000a2f5  mov     r9, rsi
0x14000a2f8  mov     r8, r15
0x14000a2fb  lea     rdx, [rsp+88h+P]
0x14000a300  call    VfsQueryDirectoryFileName
0x14000a305  mov     ebx, eax
0x14000a307  mov     [rsp+88h+var_58], eax
0x14000a30b  add     eax, 3FFFFFF1h
0x14000a310  cmp     eax, 2Bh ; '+'
0x14000a313  ja      short loc_14000A378
0x14000a315  movsxd  rcx, eax
0x14000a318  mov     rdi, 82000000001h
0x14000a322  bt      rdi, rcx
0x14000a326  jnb     short loc_14000A378
0x14000a328  jmp     short loc_14000A334
0x14000a32a  mov     rdi, 82000000001h
0x14000a334  test    r14, r14
0x14000a337  jz      short loc_14000A36F
0x14000a339  mov     eax, [rsp+88h+arg_28]
0x14000a340  mov     [rsp+88h+Length], eax; Length
0x14000a344  mov     r9, rsi
0x14000a347  mov     r8, r15
0x14000a34a  lea     rdx, [rsp+88h+var_48]
0x14000a34f  mov     rcx, r14; Instance
0x14000a352  call    VfsQueryDirectoryFileName
0x14000a357  mov     ebx, eax
0x14000a359  mov     [rsp+88h+var_58], eax
0x14000a35d  add     eax, 3FFFFFF1h
0x14000a362  cmp     eax, 2Bh ; '+'
0x14000a365  ja      short loc_14000A378
0x14000a367  cdqe
0x14000a369  bt      rdi, rax
0x14000a36d  jnb     short loc_14000A378
0x14000a36f  mov     ebx, 0C0000225h
0x14000a374  mov     [rsp+88h+var_58], ebx
0x14000a378  mov     rcx, [rsp+88h+FltObject]; FltObject
0x14000a37d  test    rcx, rcx
0x14000a380  jz      short loc_14000A3A6
0x14000a382  call    cs:__imp_FltObjectDereference
0x14000a389  nop     dword ptr [rax+rax+00h]
0x14000a38e  mov     rcx, [rsp+88h+P+8]; P
0x14000a393  test    rcx, rcx
0x14000a396  jz      short loc_14000A3A6
0x14000a398  xor     edx, edx; Tag
0x14000a39a  call    cs:__imp_ExFreePoolWithTag
0x14000a3a1  nop     dword ptr [rax+rax+00h]
0x14000a3a6  mov     eax, ebx
0x14000a3a8  add     rsp, 60h
0x14000a3ac  pop     r15
0x14000a3ae  pop     r14
0x14000a3b0  pop     rdi
0x14000a3b1  pop     rsi
0x14000a3b2  pop     rbx
0x14000a3b3  retn
0x140014e41  push    rbp
0x140014e43  sub     rsp, 30h
0x140014e47  mov     rbp, rdx
0x140014e4a  mov     rcx, [rbp+38h]; FltObject
0x140014e4e  test    rcx, rcx
0x140014e51  jz      short loc_140014E77
0x140014e53  call    cs:__imp_FltObjectDereference
0x140014e5a  nop     dword ptr [rax+rax+00h]
0x140014e5f  mov     rcx, [rbp+58h]; P
0x140014e63  test    rcx, rcx
0x140014e66  jz      short loc_140014E77
0x140014e68  xor     edx, edx; Tag
0x140014e6a  call    cs:__imp_ExFreePoolWithTag
0x140014e71  nop     dword ptr [rax+rax+00h]
0x140014e76  nop
0x140014e77  add     rsp, 30h
0x140014e7b  pop     rbp
0x140014e7c  retn
```
