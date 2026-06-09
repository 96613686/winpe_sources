# VfsCreateDirQuerySubContext

- ea: `0x14000783c`
- end: `0x140007a0c`
- name: `VfsCreateDirQuerySubContext`
- size: `464`
- prototype: `__int64 __usercall@<rax>(PVOID FltObject@<rcx>, char, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140007124`
- `0x1400076d0`

## callees

- `0x14000783c`
- `0x140007a48`
- `0x14001070c`
- `0x140012acc`
- `0x140014000`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400079d0`
- `ntoskrnl!ObfDereferenceObject` at `0x140014c37`
- `ntoskrnl!ObfDereferenceObject` at `0x1400079d0`
- `ntoskrnl!ObfDereferenceObject` at `0x140014c37`
- `ntoskrnl!ExAllocatePool2` at `0x14000793c`
- `ntoskrnl!ExAllocatePool2` at `0x14000793c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400078f0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400078f0`
- `FLTMGR!FltObjectReference` at `0x140007963`
- `FLTMGR!FltObjectReference` at `0x140007963`
- `FLTMGR!FltClose` at `0x1400079e1`
- `FLTMGR!FltClose` at `0x140014c47`
- `FLTMGR!FltClose` at `0x1400079e1`
- `FLTMGR!FltClose` at `0x140014c47`

## string_xrefs

- `0x1400078d0`: `VfsCreateDirQuerySubContext() - Failed to open file: %wZ\n Status: 0x%08X`
- `0x14000797c`: `VfsCreateDirQuerySubContext() - Failed to reference instance: %p\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCreateDirQuerySubContext(
        struct _FLT_INSTANCE *FltObject,
        void *a2,
        struct _FLT_INSTANCE *a3,
        unsigned int a4,
        char a5,
        _QWORD *a6)
{
  __int64 v6; // r12
  char *v9; // rdi
  NTSTATUS v10; // eax
  int v11; // ebx
  struct _FLT_INSTANCE *v12; // r9
  const WCHAR *v13; // r8
  char *v14; // rax
  __int64 Pool2; // rax
  __int64 v17; // [rsp+20h] [rbp-78h]
  HANDLE FileHandle; // [rsp+48h] [rbp-50h] BYREF
  PVOID Object; // [rsp+50h] [rbp-48h] BYREF
  char *v20; // [rsp+58h] [rbp-40h]

  v6 = a4;
  v9 = 0;
  v20 = 0;
  FileHandle = 0;
  Object = 0;
  *a6 = 0;
  if ( a2 )
  {
    FileHandle = 0;
    Object = a2;
  }
  else
  {
    v10 = VfsOpenFile(FltObject, 1u, 0x4020u, &FileHandle, (PFILE_OBJECT *)&Object);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( v10 == -1073741766 || v10 == -1073741772 )
      {
        v11 = 0;
        goto LABEL_17;
      }
      v12 = a3;
      v13 = L"VfsCreateDirQuerySubContext() - Failed to open file: %wZ\n Status: 0x%08X";
      goto LABEL_15;
    }
  }
  v14 = (char *)ExAllocateFromPagedLookasideList(&stru_14001FA00);
  v9 = v14;
  v20 = v14;
  if ( !v14 )
    goto LABEL_9;
  memset(v14, 0, 0x78u);
  if ( a5 )
    *((_DWORD *)v9 + 4) = 1;
  Pool2 = ExAllocatePool2(256, v6, 1648641622);
  *((_QWORD *)v9 + 6) = Pool2;
  if ( !Pool2 )
  {
LABEL_9:
    v11 = -1073741670;
    goto LABEL_17;
  }
  *((_DWORD *)v9 + 14) = v6;
  *(_QWORD *)(v9 + 60) = 0;
  *((_DWORD *)v9 + 17) = 0;
  v10 = FltObjectReference(FltObject);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = FltObject;
    v13 = L"VfsCreateDirQuerySubContext() - Failed to reference instance: %p\n Status: 0x%08X";
LABEL_15:
    LODWORD(v17) = v10;
    LogWrite(1, 0, v13, v12, v17);
    goto LABEL_17;
  }
  *((_QWORD *)v9 + 3) = FltObject;
  *((_QWORD *)v9 + 5) = FileHandle;
  *((_QWORD *)v9 + 4) = Object;
  FileHandle = 0;
  Object = 0;
  *a6 = v9;
LABEL_17:
  if ( v11 < 0 )
  {
    if ( FileHandle )
    {
      ObfDereferenceObject(Object);
      FltClose(FileHandle);
    }
    if ( v9 )
      VfsDeleteDirQuerySubContext(v9);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000783c  mov     rax, rsp
0x14000783f  push    rbx
0x140007840  push    rdi
0x140007841  push    r12
0x140007843  push    r13
0x140007845  push    r14
0x140007847  push    r15
0x140007849  sub     rsp, 68h
0x14000784d  mov     r12d, r9d
0x140007850  mov     r15, r8
0x140007853  mov     r14, rcx
0x140007856  xor     ebx, ebx
0x140007858  mov     [rax-58h], ebx
0x14000785b  mov     edi, ebx
0x14000785d  mov     [rax-40h], rbx
0x140007861  mov     [rax-50h], rbx
0x140007865  mov     [rax-48h], rbx
0x140007869  mov     r13, [rsp+98h+arg_28]
0x140007871  mov     [r13+0], rbx
0x140007875  test    rdx, rdx
0x140007878  jz      short loc_140007884
0x14000787a  mov     [rax-50h], rbx
0x14000787e  mov     [rax-48h], rdx
0x140007882  jmp     short loc_1400078E9
0x140007884  lea     rax, [rsp+98h+Object]
0x140007889  mov     [rsp+98h+FileObject], rax; FileObject
0x14000788e  lea     rax, [rsp+98h+FileHandle]
0x140007893  mov     [rsp+98h+var_68], rax; FileHandle
0x140007898  mov     [rsp+98h+var_70], 4020h; ULONG
0x1400078a0  mov     dword ptr [rsp+98h+var_78], 1; ULONG
0x1400078a8  xor     edx, edx
0x1400078aa  mov     r9d, 100001h
0x1400078b0  call    VfsOpenFile
0x1400078b5  mov     ebx, eax
0x1400078b7  mov     [rsp+98h+var_58], eax
0x1400078bb  test    eax, eax
0x1400078bd  jns     short loc_1400078E7
0x1400078bf  cmp     eax, 0C000003Ah
0x1400078c4  jz      short loc_1400078DC
0x1400078c6  cmp     eax, 0C0000034h
0x1400078cb  jz      short loc_1400078DC
0x1400078cd  mov     r9, r15
0x1400078d0  lea     r8, aVfscreatedirqu; "VfsCreateDirQuerySubContext() - Failed "...
0x1400078d7  jmp     loc_140007983
0x1400078dc  xor     ebx, ebx
0x1400078de  mov     [rsp+98h+var_58], ebx
0x1400078e2  jmp     loc_1400079BF
0x1400078e7  xor     ebx, ebx
0x1400078e9  lea     rcx, stru_14001FA00; Lookaside
0x1400078f0  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400078f7  nop     dword ptr [rax+rax+00h]
0x1400078fc  mov     rdi, rax
0x1400078ff  mov     [rsp+98h+var_40], rax
0x140007904  test    rax, rax
0x140007907  jnz     short loc_140007910
0x140007909  mov     ebx, 0C000009Ah
0x14000790e  jmp     short loc_1400078DE
0x140007910  xor     edx, edx; Val
0x140007912  lea     r8d, [rdx+78h]; Size
0x140007916  mov     rcx, rdi; void *
0x140007919  call    memset
0x14000791e  cmp     [rsp+98h+arg_20], bl
0x140007925  jz      short loc_14000792E
0x140007927  mov     dword ptr [rdi+10h], 1
0x14000792e  mov     rdx, r12
0x140007931  mov     ecx, 100h
0x140007936  mov     r8d, 62444656h
0x14000793c  call    cs:__imp_ExAllocatePool2
0x140007943  nop     dword ptr [rax+rax+00h]
0x140007948  mov     [rdi+30h], rax
0x14000794c  test    rax, rax
0x14000794f  jz      short loc_140007909
0x140007951  mov     [rdi+38h], r12d
0x140007955  mov     qword ptr [rdi+3Ch], 0
0x14000795d  mov     [rdi+44h], ebx
0x140007960  mov     rcx, r14; FltObject
0x140007963  call    cs:__imp_FltObjectReference
0x14000796a  nop     dword ptr [rax+rax+00h]
0x14000796f  mov     ebx, eax
0x140007971  mov     [rsp+98h+var_58], eax
0x140007975  test    eax, eax
0x140007977  jns     short loc_140007993
0x140007979  mov     r9, r14
0x14000797c  lea     r8, aVfscreatedirqu_0; "VfsCreateDirQuerySubContext() - Failed "...
0x140007983  mov     dword ptr [rsp+98h+var_78], eax
0x140007987  xor     edx, edx
0x140007989  lea     ecx, [rdx+1]
0x14000798c  call    LogWrite
0x140007991  jmp     short loc_1400079BF
0x140007993  mov     [rdi+18h], r14
0x140007997  mov     rax, [rsp+98h+FileHandle]
0x14000799c  mov     [rdi+28h], rax
0x1400079a0  mov     rax, [rsp+98h+Object]
0x1400079a5  mov     [rdi+20h], rax
0x1400079a9  mov     [rsp+98h+FileHandle], 0
0x1400079b2  mov     [rsp+98h+Object], 0
0x1400079bb  mov     [r13+0], rdi
0x1400079bf  test    ebx, ebx
0x1400079c1  jns     short loc_1400079FA
0x1400079c3  cmp     [rsp+98h+FileHandle], 0
0x1400079c9  jz      short loc_1400079ED
0x1400079cb  mov     rcx, [rsp+98h+Object]; Object
0x1400079d0  call    cs:__imp_ObfDereferenceObject
0x1400079d7  nop     dword ptr [rax+rax+00h]
0x1400079dc  mov     rcx, [rsp+98h+FileHandle]; FileHandle
0x1400079e1  call    cs:__imp_FltClose
0x1400079e8  nop     dword ptr [rax+rax+00h]
0x1400079ed  test    rdi, rdi
0x1400079f0  jz      short loc_1400079FA
0x1400079f2  mov     rcx, rdi; Entry
0x1400079f5  call    VfsDeleteDirQuerySubContext
0x1400079fa  mov     eax, ebx
0x1400079fc  add     rsp, 68h
0x140007a00  pop     r15
0x140007a02  pop     r14
0x140007a04  pop     r13
0x140007a06  pop     r12
0x140007a08  pop     rdi
0x140007a09  pop     rbx
0x140007a0a  retn
0x140014c1d  push    rbp
0x140014c1f  sub     rsp, 40h
0x140014c23  mov     rbp, rdx
0x140014c26  cmp     dword ptr [rbp+40h], 0
0x140014c2a  jge     short loc_140014C63
0x140014c2c  cmp     qword ptr [rbp+48h], 0
0x140014c31  jz      short loc_140014C54
0x140014c33  mov     rcx, [rbp+50h]; Object
0x140014c37  call    cs:__imp_ObfDereferenceObject
0x140014c3e  nop     dword ptr [rax+rax+00h]
0x140014c43  mov     rcx, [rbp+48h]; FileHandle
0x140014c47  call    cs:__imp_FltClose
0x140014c4e  nop     dword ptr [rax+rax+00h]
0x140014c53  nop
0x140014c54  mov     rcx, [rbp+58h]; Entry
0x140014c58  test    rcx, rcx
0x140014c5b  jz      short loc_140014C63
0x140014c5d  call    VfsDeleteDirQuerySubContext
0x140014c62  nop
0x140014c63  add     rsp, 40h
0x140014c67  pop     rbp
0x140014c68  retn
```
