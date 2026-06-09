# BfsExpandDirectory

- ea: `0x140011458`
- end: `0x14001169a`
- name: `BfsExpandDirectory`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140011d18`

## callees

- `0x140001008`
- `0x1400105ac`
- `0x140011458`
- `0x1400117a4`
- `0x140012ab0`
- `0x140013730`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400114b2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400114b2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001165f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001165f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001162d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011643`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001162d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011643`
- `ntoskrnl!ExAllocatePool2` at `0x1400114e5`
- `ntoskrnl!ExAllocatePool2` at `0x140011529`
- `ntoskrnl!ExAllocatePool2` at `0x1400114e5`
- `ntoskrnl!ExAllocatePool2` at `0x140011529`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400114a1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400114a1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001166b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001166b`

## pseudocode

```c
__int64 __fastcall BfsExpandDirectory(__int64 a1, _DWORD *a2, __int64 a3, _QWORD *a4, _QWORD *a5)
{
  _DWORD *v5; // rdi
  __int64 v8; // rbx
  NTSTATUS v9; // ebx
  __int64 Pool2; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // r15d
  _QWORD *v14; // rsi
  __int64 v15; // rcx
  bool v16; // cc
  __int64 v17; // rax
  __int64 v18; // rax
  _QWORD *v19; // rcx
  NTSTATUS v20; // eax
  __int64 v21; // rdx
  void *v22; // r8
  int v24; // [rsp+20h] [rbp-51h]
  int v25; // [rsp+30h] [rbp-41h] BYREF
  _DWORD *v26; // [rsp+38h] [rbp-39h]
  __int64 v27; // [rsp+40h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+48h] [rbp-29h] BYREF
  int *v29; // [rsp+68h] [rbp-9h]
  __int64 v30; // [rsp+70h] [rbp-1h]

  v5 = 0;
  *a4 = 0;
  v27 = a3;
  v26 = a2;
  *a5 = 0;
  v8 = *(_QWORD *)(a1 + 8);
  v25 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v8, 0);
  v9 = BfsAllocateBlock(*(_QWORD *)(a1 + 8), &v25);
  if ( v9 < 0 )
    goto LABEL_23;
  Pool2 = ExAllocatePool2(256, 32, 1282631234);
  v13 = v25;
  v14 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    v15 = (unsigned int)dword_140019000;
    v16 = (unsigned int)dword_140019000 <= 3;
    goto LABEL_4;
  }
  v17 = ExAllocatePool2(256, 0x4000, 1651729986);
  v5 = (_DWORD *)v17;
  if ( !v17 )
  {
    v16 = (unsigned int)dword_140019000 <= 3;
LABEL_4:
    v9 = -1073741801;
    if ( !v16 )
    {
      v25 = -1073741801;
LABEL_17:
      v30 = 4;
      v29 = &v25;
      tlgWriteTransfer_EtwWriteTransfer(v15, (unsigned __int8 *)&byte_140016D91, v11, v12, v24, &v28);
      goto LABEL_18;
    }
    goto LABEL_18;
  }
  v14[2] = v17;
  *((_DWORD *)v14 + 6) = v13;
  v18 = *(_QWORD *)(a1 + 16);
  v19 = *(_QWORD **)(v18 + 8);
  if ( *v19 != v18 )
    __fastfail(3u);
  v14[1] = v19;
  *v14 = v18;
  *v19 = v14;
  *(_QWORD *)(v18 + 8) = v14;
  memset(v5 + 1, 0, 0x3FFCu);
  *v5 = 1148413506;
  v20 = BfsWriteBlock(*(_QWORD *)(a1 + 8), v13, v5);
  v9 = v20;
  if ( v20 >= 0 )
  {
    v9 = BfsWriteBlock(*(_QWORD *)(a1 + 8), 0, *(void **)(*(_QWORD *)(a1 + 8) + 16LL));
    if ( v9 >= 0 )
    {
      v21 = v27;
      v22 = v26;
      v26[1] = v13;
      v9 = BfsWriteBlock(*(_QWORD *)(a1 + 8), *(_DWORD *)(v21 + 24), v22);
      if ( v9 >= 0 )
      {
        *a5 = v14;
        *a4 = v5;
        goto LABEL_23;
      }
    }
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_18;
    v25 = v9;
    goto LABEL_17;
  }
  v15 = (unsigned int)dword_140019000;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v25 = v20;
    goto LABEL_17;
  }
LABEL_18:
  BfsFreeBlock(*(_QWORD *)(a1 + 8), v13);
  if ( v14 )
    ExFreePoolWithTag(v14, 0);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
LABEL_23:
  ExReleasePushLockExclusiveEx(*(_QWORD *)(a1 + 8), 0);
  KeLeaveCriticalRegion();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140011458  push    rbp
0x14001145a  push    rbx
0x14001145b  push    rsi
0x14001145c  push    rdi
0x14001145d  push    r12
0x14001145f  push    r13
0x140011461  push    r14
0x140011463  push    r15
0x140011465  lea     rbp, [rsp-17h]
0x14001146a  sub     rsp, 88h
0x140011471  mov     rax, cs:__security_cookie
0x140011478  xor     rax, rsp
0x14001147b  mov     [rbp+4Fh+var_48], rax
0x14001147f  mov     r13, [rbp+4Fh+arg_20]
0x140011483  xor     edi, edi
0x140011485  mov     [r9], rdi
0x140011488  mov     r12, r9
0x14001148b  mov     [rbp+4Fh+var_80], r8
0x14001148f  mov     r14, rcx
0x140011492  mov     [rbp+4Fh+var_88], rdx
0x140011496  mov     [r13+0], rdi
0x14001149a  mov     rbx, [rcx+8]
0x14001149e  mov     [rbp+4Fh+var_90], edi
0x1400114a1  call    cs:__imp_KeEnterCriticalRegion
0x1400114a8  nop     dword ptr [rax+rax+00h]
0x1400114ad  xor     edx, edx
0x1400114af  mov     rcx, rbx
0x1400114b2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400114b9  nop     dword ptr [rax+rax+00h]
0x1400114be  mov     rcx, [r14+8]
0x1400114c2  lea     rdx, [rbp+4Fh+var_90]
0x1400114c6  call    BfsAllocateBlock
0x1400114cb  mov     ebx, eax
0x1400114cd  test    eax, eax
0x1400114cf  js      loc_140011659
0x1400114d5  mov     ebx, 100h
0x1400114da  lea     edx, [rdi+20h]
0x1400114dd  mov     ecx, ebx
0x1400114df  mov     r8d, 4C736642h
0x1400114e5  call    cs:__imp_ExAllocatePool2
0x1400114ec  nop     dword ptr [rax+rax+00h]
0x1400114f1  mov     r15d, [rbp+4Fh+var_90]
0x1400114f5  mov     rsi, rax
0x1400114f8  test    rax, rax
0x1400114fb  jnz     short loc_14001151B
0x1400114fd  mov     ecx, cs:dword_140019000
0x140011503  cmp     ecx, 3
0x140011506  mov     edx, 0C0000017h
0x14001150b  mov     ebx, edx
0x14001150d  jbe     loc_140011617
0x140011513  mov     [rbp+4Fh+var_90], edx
0x140011516  jmp     loc_1400115F2
0x14001151b  mov     edx, 4000h
0x140011520  mov     r8d, 62736642h
0x140011526  mov     rcx, rbx
0x140011529  call    cs:__imp_ExAllocatePool2
0x140011530  nop     dword ptr [rax+rax+00h]
0x140011535  mov     rdi, rax
0x140011538  test    rax, rax
0x14001153b  jnz     short loc_140011548
0x14001153d  mov     eax, cs:dword_140019000
0x140011543  cmp     eax, 3
0x140011546  jmp     short loc_140011506
0x140011548  mov     [rsi+10h], rdi
0x14001154c  mov     [rsi+18h], r15d
0x140011550  mov     rax, [r14+10h]
0x140011554  mov     rcx, [rax+8]
0x140011558  cmp     [rcx], rax
0x14001155b  jz      short loc_140011564
0x14001155d  mov     ecx, 3
0x140011562  int     29h; Win8: RtlFailFast(ecx)
0x140011564  mov     [rsi+8], rcx
0x140011568  xor     edx, edx; Val
0x14001156a  mov     [rsi], rax
0x14001156d  mov     r8d, 3FFCh; Size
0x140011573  mov     [rcx], rsi
0x140011576  lea     rcx, [rdi+4]; void *
0x14001157a  mov     [rax+8], rsi
0x14001157e  call    memset
0x140011583  mov     dword ptr [rdi], 44736642h
0x140011589  mov     r8, rdi
0x14001158c  mov     rcx, [r14+8]
0x140011590  mov     edx, r15d
0x140011593  call    BfsWriteBlock
0x140011598  mov     ebx, eax
0x14001159a  test    eax, eax
0x14001159c  jns     short loc_1400115AE
0x14001159e  mov     ecx, cs:dword_140019000
0x1400115a4  cmp     ecx, 3
0x1400115a7  jbe     short loc_140011617
0x1400115a9  mov     [rbp+4Fh+var_90], eax
0x1400115ac  jmp     short loc_1400115F2
0x1400115ae  mov     rcx, [r14+8]
0x1400115b2  xor     edx, edx
0x1400115b4  mov     r8, [rcx+10h]
0x1400115b8  call    BfsWriteBlock
0x1400115bd  mov     ebx, eax
0x1400115bf  test    eax, eax
0x1400115c1  js      short loc_1400115E4
0x1400115c3  mov     rax, [rbp+4Fh+var_88]
0x1400115c7  mov     rdx, [rbp+4Fh+var_80]
0x1400115cb  mov     r8, rax
0x1400115ce  mov     [rax+4], r15d
0x1400115d2  mov     edx, [rdx+18h]
0x1400115d5  mov     rcx, [r14+8]
0x1400115d9  call    BfsWriteBlock
0x1400115de  mov     ebx, eax
0x1400115e0  test    eax, eax
0x1400115e2  jns     short loc_140011651
0x1400115e4  mov     eax, cs:dword_140019000
0x1400115ea  cmp     eax, 3
0x1400115ed  jbe     short loc_140011617
0x1400115ef  mov     [rbp+4Fh+var_90], ebx
0x1400115f2  lea     rax, [rbp+4Fh+var_90]
0x1400115f6  mov     [rbp+4Fh+var_50], 4
0x1400115fe  mov     [rbp+4Fh+var_58], rax
0x140011602  lea     rdx, byte_140016D91; int
0x140011609  lea     rax, [rbp+4Fh+var_78]
0x14001160d  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x140011612  call    _tlgWriteTransfer_EtwWriteTransfer
0x140011617  mov     rcx, [r14+8]
0x14001161b  mov     edx, r15d
0x14001161e  call    BfsFreeBlock
0x140011623  test    rsi, rsi
0x140011626  jz      short loc_140011639
0x140011628  xor     edx, edx; Tag
0x14001162a  mov     rcx, rsi; P
0x14001162d  call    cs:__imp_ExFreePoolWithTag
0x140011634  nop     dword ptr [rax+rax+00h]
0x140011639  test    rdi, rdi
0x14001163c  jz      short loc_140011659
0x14001163e  xor     edx, edx; Tag
0x140011640  mov     rcx, rdi; P
0x140011643  call    cs:__imp_ExFreePoolWithTag
0x14001164a  nop     dword ptr [rax+rax+00h]
0x14001164f  jmp     short loc_140011659
0x140011651  mov     [r13+0], rsi
0x140011655  mov     [r12], rdi
0x140011659  mov     rcx, [r14+8]
0x14001165d  xor     edx, edx
0x14001165f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140011666  nop     dword ptr [rax+rax+00h]
0x14001166b  call    cs:__imp_KeLeaveCriticalRegion
0x140011672  nop     dword ptr [rax+rax+00h]
0x140011677  mov     eax, ebx
0x140011679  mov     rcx, [rbp+4Fh+var_48]
0x14001167d  xor     rcx, rsp; StackCookie
0x140011680  call    __security_check_cookie
0x140011685  add     rsp, 88h
0x14001168c  pop     r15
0x14001168e  pop     r14
0x140011690  pop     r13
0x140011692  pop     r12
0x140011694  pop     rdi
0x140011695  pop     rsi
0x140011696  pop     rbx
0x140011697  pop     rbp
0x140011698  retn
```
