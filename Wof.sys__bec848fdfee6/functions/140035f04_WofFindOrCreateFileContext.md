# WofFindOrCreateFileContext

- ea: `0x140035f04`
- end: `0x140036033`
- name: `WofFindOrCreateFileContext`
- size: `303`
- prototype: `NTSTATUS __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, __int64, char, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140024448`
- `0x140033930`

## callees

- `0x1400119c0`
- `0x140035f04`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x140035fae`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140035fae`
- `ntoskrnl!KeInitializeEvent` at `0x140035f99`
- `ntoskrnl!KeInitializeEvent` at `0x140035f99`
- `FLTMGR!FltSetFileContext` at `0x140035fe3`
- `FLTMGR!FltSetFileContext` at `0x140035fe3`
- `FLTMGR!FltReleaseContext` at `0x140036011`
- `FLTMGR!FltReleaseContext` at `0x140036011`
- `FLTMGR!FltAllocateContext` at `0x140035f4e`
- `FLTMGR!FltAllocateContext` at `0x140035f4e`

## pseudocode

```c
NTSTATUS __fastcall WofFindOrCreateFileContext(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a3,
        char a4,
        _QWORD *a5)
{
  NTSTATUS result; // eax
  char *v10; // rcx
  PFLT_CONTEXT v11; // rbx
  NTSTATUS v12; // edi
  PFLT_CONTEXT NewContext; // [rsp+30h] [rbp-38h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+38h] [rbp-30h] BYREF

  OldContext = 0;
  NewContext = 0;
  result = FltAllocateContext(WofGlobal, 4u, 0x58u, (POOL_TYPE)512, &NewContext);
  if ( result >= 0 )
  {
    memset(NewContext, 0, 0x58u);
    v10 = (char *)NewContext;
    *((_DWORD *)NewContext + 8) = 1;
    *((_QWORD *)v10 + 5) = 0;
    *((_DWORD *)v10 + 12) = 0;
    KeInitializeEvent((PRKEVENT)(v10 + 56), SynchronizationEvent, 0);
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)NewContext + 3);
    *((_QWORD *)NewContext + 1) = a3;
    v11 = NewContext;
    if ( a4 )
      *(_DWORD *)NewContext |= 1u;
    v12 = FltSetFileContext(Instance, FileObject, FLT_SET_CONTEXT_KEEP_IF_EXISTS, v11, &OldContext);
    if ( v12 < 0 )
    {
      FltReleaseContext(v11);
      if ( v12 != -1071906814 )
        return v12;
      v11 = OldContext;
      v12 = 0;
    }
    *a5 = v11;
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x140035f04  mov     r11, rsp
0x140035f07  push    rbx
0x140035f08  push    rbp
0x140035f09  push    rsi
0x140035f0a  push    rdi
0x140035f0b  push    r15
0x140035f0d  sub     rsp, 40h
0x140035f11  mov     rdi, rdx
0x140035f14  mov     qword ptr [r11-30h], 0
0x140035f1c  mov     edx, 4; ContextType
0x140035f21  mov     qword ptr [r11-38h], 0
0x140035f29  mov     bpl, r9b
0x140035f2c  lea     rax, [r11-38h]
0x140035f30  mov     rbx, r8
0x140035f33  mov     [r11-48h], rax
0x140035f37  mov     rsi, rcx
0x140035f3a  mov     r9d, 200h; PoolType
0x140035f40  mov     rcx, cs:WofGlobal; Filter
0x140035f47  lea     r15d, [rdx+54h]
0x140035f4b  mov     r8d, r15d; ContextSize
0x140035f4e  call    cs:__imp_FltAllocateContext
0x140035f55  nop     dword ptr [rax+rax+00h]
0x140035f5a  test    eax, eax
0x140035f5c  js      loc_140036002
0x140035f62  mov     rcx, [rsp+68h+NewContext]; void *
0x140035f67  mov     r8d, r15d; Size
0x140035f6a  xor     edx, edx; Val
0x140035f6c  call    memset
0x140035f71  mov     rcx, [rsp+68h+NewContext]
0x140035f76  mov     r15d, 1
0x140035f7c  xor     r8d, r8d; State
0x140035f7f  mov     edx, r15d; Type
0x140035f82  mov     [rcx+20h], r15d
0x140035f86  mov     qword ptr [rcx+28h], 0
0x140035f8e  mov     dword ptr [rcx+30h], 0
0x140035f95  add     rcx, 38h ; '8'; Event
0x140035f99  call    cs:__imp_KeInitializeEvent
0x140035fa0  nop     dword ptr [rax+rax+00h]
0x140035fa5  mov     rcx, [rsp+68h+NewContext]
0x140035faa  add     rcx, 18h; RunRef
0x140035fae  call    cs:__imp_ExInitializeRundownProtection
0x140035fb5  nop     dword ptr [rax+rax+00h]
0x140035fba  mov     rax, [rsp+68h+NewContext]
0x140035fbf  mov     [rax+8], rbx
0x140035fc3  mov     rbx, [rsp+68h+NewContext]
0x140035fc8  test    bpl, bpl
0x140035fcb  jnz     short loc_14003602E
0x140035fcd  lea     rax, [rsp+68h+var_30]
0x140035fd2  mov     r9, rbx; NewContext
0x140035fd5  mov     r8d, r15d; Operation
0x140035fd8  mov     [rsp+68h+OldContext], rax; OldContext
0x140035fdd  mov     rdx, rdi; FileObject
0x140035fe0  mov     rcx, rsi; Instance
0x140035fe3  call    cs:__imp_FltSetFileContext
0x140035fea  nop     dword ptr [rax+rax+00h]
0x140035fef  mov     edi, eax
0x140035ff1  test    eax, eax
0x140035ff3  js      short loc_14003600E
0x140035ff5  mov     rax, [rsp+68h+arg_20]
0x140035ffd  mov     [rax], rbx
0x140036000  mov     eax, edi
0x140036002  add     rsp, 40h
0x140036006  pop     r15
0x140036008  pop     rdi
0x140036009  pop     rsi
0x14003600a  pop     rbp
0x14003600b  pop     rbx
0x14003600c  retn
0x14003600e  mov     rcx, rbx; Context
0x140036011  call    cs:__imp_FltReleaseContext
0x140036018  nop     dword ptr [rax+rax+00h]
0x14003601d  cmp     edi, 0C01C0002h
0x140036023  jnz     short loc_140036000
0x140036025  mov     rbx, [rsp+68h+var_30]
0x14003602a  xor     edi, edi
0x14003602c  jmp     short loc_140035FF5
0x14003602e  or      [rbx], r15d
0x140036031  jmp     short loc_140035FCD
```
