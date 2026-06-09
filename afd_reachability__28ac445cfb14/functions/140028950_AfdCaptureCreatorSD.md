# AfdCaptureCreatorSD

- ea: `0x140028950`
- end: `0x140028a33`
- name: `AfdCaptureCreatorSD`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400218d4`

## callees

- `0x140028950`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140028995`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140028995`
- `ntoskrnl!SeLockSubjectContext` at `0x140028986`
- `ntoskrnl!SeLockSubjectContext` at `0x140028986`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400289d1`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400289d1`
- `ntoskrnl!SeAssignSecurity` at `0x1400289c0`
- `ntoskrnl!SeAssignSecurity` at `0x1400289c0`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x1400289ef`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x1400289ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028a04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028a04`

## pseudocode

```c
__int64 __fastcall AfdCaptureCreatorSD(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rax
  struct _SECURITY_SUBJECT_CONTEXT *v4; // rdi
  void **p_ClientToken; // rbx
  struct _SECURITY_SUBJECT_CONTEXT *SubjectContext; // rdi
  void *v7; // rbx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  NTSTATUS v9; // ebx
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 8);
  NewDescriptor = 0;
  v4 = *(struct _SECURITY_SUBJECT_CONTEXT **)(v2 + 8);
  p_ClientToken = &v4[2].ClientToken;
  if ( *(_WORD *)(a1 + 26) || *p_ClientToken )
  {
    SubjectContext = v4 + 1;
    SeLockSubjectContext(SubjectContext);
    v7 = *p_ClientToken;
    GenericMapping = IoGetFileObjectGenericMapping();
    v9 = SeAssignSecurity(0, v7, &NewDescriptor, 0, SubjectContext, GenericMapping, PagedPool);
    SeUnlockSubjectContext(SubjectContext);
    if ( v9 >= 0 )
    {
      v9 = ObLogSecurityDescriptor(NewDescriptor, a2, 1);
      ExFreePoolWithTag(NewDescriptor, 0);
    }
    return (unsigned int)v9;
  }
  else
  {
    *a2 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x140028950  mov     [rsp+arg_8], rbx
0x140028955  mov     [rsp+arg_10], rsi
0x14002895a  push    rdi
0x14002895b  sub     rsp, 40h
0x14002895f  mov     rax, [rcx+8]
0x140028963  mov     rsi, rdx
0x140028966  xor     edx, edx
0x140028968  mov     [rsp+48h+NewDescriptor], rdx
0x14002896d  mov     rdi, [rax+8]
0x140028971  lea     rbx, [rdi+40h]
0x140028975  cmp     [rcx+1Ah], dx
0x140028979  jz      loc_140028A23
0x14002897f  add     rdi, 20h ; ' '
0x140028983  mov     rcx, rdi; SubjectContext
0x140028986  call    cs:__imp_SeLockSubjectContext
0x14002898d  nop     dword ptr [rax+rax+00h]
0x140028992  mov     rbx, [rbx]
0x140028995  call    cs:__imp_IoGetFileObjectGenericMapping
0x14002899c  nop     dword ptr [rax+rax+00h]
0x1400289a1  mov     [rsp+48h+PoolType], 1; PoolType
0x1400289a9  lea     r8, [rsp+48h+NewDescriptor]; NewDescriptor
0x1400289ae  mov     [rsp+48h+GenericMapping], rax; GenericMapping
0x1400289b3  xor     r9d, r9d; IsDirectoryObject
0x1400289b6  mov     rdx, rbx; ExplicitDescriptor
0x1400289b9  mov     [rsp+48h+SubjectContext], rdi; SubjectContext
0x1400289be  xor     ecx, ecx; ParentDescriptor
0x1400289c0  call    cs:__imp_SeAssignSecurity
0x1400289c7  nop     dword ptr [rax+rax+00h]
0x1400289cc  mov     rcx, rdi; SubjectContext
0x1400289cf  mov     ebx, eax
0x1400289d1  call    cs:__imp_SeUnlockSubjectContext
0x1400289d8  nop     dword ptr [rax+rax+00h]
0x1400289dd  test    ebx, ebx
0x1400289df  js      short loc_140028A10
0x1400289e1  mov     rcx, [rsp+48h+NewDescriptor]
0x1400289e6  mov     r8d, 1
0x1400289ec  mov     rdx, rsi
0x1400289ef  call    cs:__imp_ObLogSecurityDescriptor
0x1400289f6  nop     dword ptr [rax+rax+00h]
0x1400289fb  mov     rcx, [rsp+48h+NewDescriptor]; P
0x140028a00  xor     edx, edx; Tag
0x140028a02  mov     ebx, eax
0x140028a04  call    cs:__imp_ExFreePoolWithTag
0x140028a0b  nop     dword ptr [rax+rax+00h]
0x140028a10  mov     eax, ebx
0x140028a12  mov     rbx, [rsp+48h+arg_8]
0x140028a17  mov     rsi, [rsp+48h+arg_10]
0x140028a1c  add     rsp, 40h
0x140028a20  pop     rdi
0x140028a21  retn
0x140028a23  cmp     [rbx], rdx
0x140028a26  jnz     loc_14002897F
0x140028a2c  mov     [rsi], rdx
0x140028a2f  mov     eax, edx
0x140028a31  jmp     short loc_140028A12
```
