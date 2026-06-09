# DeinitSubjectWithTokenPointer

- ea: `0x1400047ec`
- end: `0x140004832`
- name: `DeinitSubjectWithTokenPointer`
- size: `70`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005750`
- `0x1400057ec`
- `0x140005848`

## callees

- `0x1400047ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004817`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004817`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140004805`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140004805`

## pseudocode

```c
void __fastcall DeinitSubjectWithTokenPointer(__int64 a1)
{
  struct _SECURITY_SUBJECT_CONTEXT *v2; // rcx

  v2 = *(struct _SECURITY_SUBJECT_CONTEXT **)(a1 + 8);
  if ( v2 )
  {
    *(_QWORD *)a1 = 0;
    SeReleaseSubjectContext(v2);
    ExFreePoolWithTag(*(PVOID *)(a1 + 8), 0);
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x1400047ec  push    rbx
0x1400047ee  sub     rsp, 20h
0x1400047f2  mov     rbx, rcx
0x1400047f5  mov     rcx, [rcx+8]; SubjectContext
0x1400047f9  test    rcx, rcx
0x1400047fc  jz      short loc_14000482B
0x1400047fe  mov     qword ptr [rbx], 0
0x140004805  call    cs:__imp_SeReleaseSubjectContext
0x14000480c  nop     dword ptr [rax+rax+00h]
0x140004811  mov     rcx, [rbx+8]; P
0x140004815  xor     edx, edx; Tag
0x140004817  call    cs:__imp_ExFreePoolWithTag
0x14000481e  nop     dword ptr [rax+rax+00h]
0x140004823  mov     qword ptr [rbx+8], 0
0x14000482b  add     rsp, 20h
0x14000482f  pop     rbx
0x140004830  retn
```
