# Streaming::WriteFault::~WriteFault(void)

- ea: `0x14000db20`
- end: `0x14000db82`
- name: `??1WriteFault@Streaming@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(Streaming::WriteFault *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000de2c`
- `0x14000f040`

## callees

- `0x14000a1ac`
- `0x14000db20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000db34`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db34`
- `FLTMGR!FltReleaseContext` at `0x14000db68`
- `FLTMGR!FltReleaseContext` at `0x14000db68`

## pseudocode

```c
void __fastcall Streaming::WriteFault::~WriteFault(Streaming::WriteFault *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 5);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(
      (REGHANDLE *)PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      (const EVENT_DESCRIPTOR *)StrmFlt_LOAD_FILE_STOP,
      (const GUID *)this + 1);
  if ( *(_QWORD *)this )
  {
    FltReleaseContext(*(PFLT_CONTEXT *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x14000db20  push    rbx
0x14000db22  sub     rsp, 20h
0x14000db26  mov     rbx, rcx
0x14000db29  mov     rcx, [rcx+28h]; P
0x14000db2d  test    rcx, rcx
0x14000db30  jz      short loc_14000DB40
0x14000db32  xor     edx, edx; Tag
0x14000db34  call    cs:__imp_ExFreePoolWithTag
0x14000db3b  nop     dword ptr [rax+rax+00h]
0x14000db40  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x14000db47  jz      short loc_14000DB60
0x14000db49  lea     r8, [rbx+10h]
0x14000db4d  lea     rdx, StrmFlt_LOAD_FILE_STOP
0x14000db54  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x14000db5b  call    McTemplateK0_EtwWriteTransfer
0x14000db60  mov     rcx, [rbx]; Context
0x14000db63  test    rcx, rcx
0x14000db66  jz      short loc_14000DB7B
0x14000db68  call    cs:__imp_FltReleaseContext
0x14000db6f  nop     dword ptr [rax+rax+00h]
0x14000db74  mov     qword ptr [rbx], 0
0x14000db7b  add     rsp, 20h
0x14000db7f  pop     rbx
0x14000db80  retn
```
