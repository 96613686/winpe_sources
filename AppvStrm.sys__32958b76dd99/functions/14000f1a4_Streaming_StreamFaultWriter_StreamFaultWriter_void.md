# Streaming::StreamFaultWriter::~StreamFaultWriter(void)

- ea: `0x14000f1a4`
- end: `0x14000f23d`
- name: `??1StreamFaultWriter@Streaming@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(Streaming::StreamFaultWriter *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c4ac`
- `0x14000d6e0`

## callees

- `0x14000f1a4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000f1ea`
- `ntoskrnl!ZwClose` at `0x14000f1ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f1b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f1d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f1b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f1d5`
- `FLTMGR!FltReleaseContext` at `0x14000f20f`
- `FLTMGR!FltReleaseContext` at `0x14000f223`
- `FLTMGR!FltReleaseContext` at `0x14000f20f`
- `FLTMGR!FltReleaseContext` at `0x14000f223`

## pseudocode

```c
void __fastcall Streaming::StreamFaultWriter::~StreamFaultWriter(Streaming::StreamFaultWriter *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  v3 = (void *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    if ( *((_BYTE *)this + 40) )
      ExFreePoolWithTag(v3, 0);
    v4 = (void *)*((_QWORD *)this + 7);
    if ( v4 )
      ZwClose(v4);
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 )
    FltReleaseContext(v5);
  if ( *(_QWORD *)this )
  {
    FltReleaseContext(*(PFLT_CONTEXT *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x14000f1a4  push    rbx
0x14000f1a6  sub     rsp, 20h
0x14000f1aa  mov     rbx, rcx
0x14000f1ad  mov     rcx, [rcx+10h]; P
0x14000f1b1  test    rcx, rcx
0x14000f1b4  jz      short loc_14000F1C4
0x14000f1b6  xor     edx, edx; Tag
0x14000f1b8  call    cs:__imp_ExFreePoolWithTag
0x14000f1bf  nop     dword ptr [rax+rax+00h]
0x14000f1c4  mov     rcx, [rbx+30h]; P
0x14000f1c8  test    rcx, rcx
0x14000f1cb  jz      short loc_14000F206
0x14000f1cd  cmp     byte ptr [rbx+28h], 0
0x14000f1d1  jz      short loc_14000F1E1
0x14000f1d3  xor     edx, edx; Tag
0x14000f1d5  call    cs:__imp_ExFreePoolWithTag
0x14000f1dc  nop     dword ptr [rax+rax+00h]
0x14000f1e1  mov     rcx, [rbx+38h]; Handle
0x14000f1e5  test    rcx, rcx
0x14000f1e8  jz      short loc_14000F1F6
0x14000f1ea  call    cs:__imp_ZwClose
0x14000f1f1  nop     dword ptr [rax+rax+00h]
0x14000f1f6  mov     qword ptr [rbx+30h], 0
0x14000f1fe  mov     qword ptr [rbx+38h], 0
0x14000f206  mov     rcx, [rbx+8]; Context
0x14000f20a  test    rcx, rcx
0x14000f20d  jz      short loc_14000F21B
0x14000f20f  call    cs:__imp_FltReleaseContext
0x14000f216  nop     dword ptr [rax+rax+00h]
0x14000f21b  mov     rcx, [rbx]; Context
0x14000f21e  test    rcx, rcx
0x14000f221  jz      short loc_14000F236
0x14000f223  call    cs:__imp_FltReleaseContext
0x14000f22a  nop     dword ptr [rax+rax+00h]
0x14000f22f  mov     qword ptr [rbx], 0
0x14000f236  add     rsp, 20h
0x14000f23a  pop     rbx
0x14000f23b  retn
```
