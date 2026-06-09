# UnionFs::Utils::OpenAsReparsePointResults::~OpenAsReparsePointResults(void)

- ea: `0x14005d598`
- end: `0x14005d5f8`
- name: `??1OpenAsReparsePointResults@Utils@UnionFs@@QEAA@XZ`
- size: `96`
- prototype: `void __fastcall(UnionFs::Utils::OpenAsReparsePointResults *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x14006c1fc`

## callees

- `0x14005d598`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14005d5d1`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d5d1`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14005d5b4`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14005d5b4`
- `FLTMGR!FltClose` at `0x14005d5e5`
- `FLTMGR!FltClose` at `0x14005d5e5`

## pseudocode

```c
void __fastcall UnionFs::Utils::OpenAsReparsePointResults::~OpenAsReparsePointResults(
        UnionFs::Utils::OpenAsReparsePointResults *this)
{
  void *v1; // rdx
  void *v3; // rcx

  v1 = (void *)*((_QWORD *)this + 2);
  if ( v1 )
    FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, v1);
  v3 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v3 )
    ObfDereferenceObject(v3);
  if ( *(_QWORD *)this )
    FltClose(*(HANDLE *)this);
}

```

## disassembly

```asm
0x14005d598  push    rbx
0x14005d59a  sub     rsp, 20h
0x14005d59e  mov     rdx, [rcx+10h]; EcpContext
0x14005d5a2  mov     rbx, rcx
0x14005d5a5  test    rdx, rdx
0x14005d5a8  jz      short loc_14005D5C0
0x14005d5aa  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14005d5b1  mov     rcx, [rcx]; Filter
0x14005d5b4  call    cs:__imp_FltFreeExtraCreateParameter
0x14005d5bb  nop     dword ptr [rax+rax+00h]
0x14005d5c0  mov     rcx, [rbx+8]; Object
0x14005d5c4  mov     qword ptr [rbx+8], 0
0x14005d5cc  test    rcx, rcx
0x14005d5cf  jz      short loc_14005D5DD
0x14005d5d1  call    cs:__imp_ObfDereferenceObject
0x14005d5d8  nop     dword ptr [rax+rax+00h]
0x14005d5dd  mov     rcx, [rbx]; FileHandle
0x14005d5e0  test    rcx, rcx
0x14005d5e3  jz      short loc_14005D5F1
0x14005d5e5  call    cs:__imp_FltClose
0x14005d5ec  nop     dword ptr [rax+rax+00h]
0x14005d5f1  add     rsp, 20h
0x14005d5f5  pop     rbx
0x14005d5f6  retn
```
