# UnionFs::Utils::OpenAsReparsePointResults::~OpenAsReparsePointResults(void)

- ea: `0x14005d718`
- end: `0x14005d778`
- name: `??1OpenAsReparsePointResults@Utils@UnionFs@@QEAA@XZ`
- size: `96`
- prototype: `void __fastcall(UnionFs::Utils::OpenAsReparsePointResults *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x14006c3ec`

## callees

- `0x14005d718`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14005d751`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d751`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14005d734`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14005d734`
- `FLTMGR!FltClose` at `0x14005d765`
- `FLTMGR!FltClose` at `0x14005d765`

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
0x14005d718  push    rbx
0x14005d71a  sub     rsp, 20h
0x14005d71e  mov     rdx, [rcx+10h]; EcpContext
0x14005d722  mov     rbx, rcx
0x14005d725  test    rdx, rdx
0x14005d728  jz      short loc_14005D740
0x14005d72a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14005d731  mov     rcx, [rcx]; Filter
0x14005d734  call    cs:__imp_FltFreeExtraCreateParameter
0x14005d73b  nop     dword ptr [rax+rax+00h]
0x14005d740  mov     rcx, [rbx+8]; Object
0x14005d744  mov     qword ptr [rbx+8], 0
0x14005d74c  test    rcx, rcx
0x14005d74f  jz      short loc_14005D75D
0x14005d751  call    cs:__imp_ObfDereferenceObject
0x14005d758  nop     dword ptr [rax+rax+00h]
0x14005d75d  mov     rcx, [rbx]; FileHandle
0x14005d760  test    rcx, rcx
0x14005d763  jz      short loc_14005D771
0x14005d765  call    cs:__imp_FltClose
0x14005d76c  nop     dword ptr [rax+rax+00h]
0x14005d771  add     rsp, 20h
0x14005d775  pop     rbx
0x14005d776  retn
```
