# Streaming::StreamFault::~StreamFault(void)

- ea: `0x14000c1d4`
- end: `0x14000c2a4`
- name: `??1StreamFault@Streaming@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(Streaming::StreamFault *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000db88`
- `0x14000f000`

## callees

- `0x14000a1ac`
- `0x14000c1d4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000c259`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c259`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c205`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c23c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c205`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c23c`
- `FLTMGR!FltReleaseContext` at `0x14000c276`
- `FLTMGR!FltReleaseContext` at `0x14000c28a`
- `FLTMGR!FltReleaseContext` at `0x14000c276`
- `FLTMGR!FltReleaseContext` at `0x14000c28a`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x14000c1ee`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x14000c1ee`

## pseudocode

```c
void __fastcall Streaming::StreamFault::~StreamFault(Streaming::StreamFault *this)
{
  void *v1; // rdx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  v1 = (void *)*((_QWORD *)this + 5);
  if ( v1 )
    FltCbdqRemoveNextIo((PFLT_CALLBACK_DATA_QUEUE)(*((_QWORD *)this + 1) + 104LL), v1);
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      StrmFlt_STREAM_FAULT_STOP,
      (char *)this + 48);
  v4 = (void *)*((_QWORD *)this + 5);
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0);
    *((_QWORD *)this + 5) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    ObfDereferenceObject(v5);
    *((_QWORD *)this + 2) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
    FltReleaseContext(v6);
  if ( *(_QWORD *)this )
  {
    FltReleaseContext(*(PFLT_CONTEXT *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x14000c1d4  push    rbx
0x14000c1d6  sub     rsp, 20h
0x14000c1da  mov     rdx, [rcx+28h]; PeekContext
0x14000c1de  mov     rbx, rcx
0x14000c1e1  test    rdx, rdx
0x14000c1e4  jz      short loc_14000C1FA
0x14000c1e6  mov     rcx, [rcx+8]
0x14000c1ea  add     rcx, 68h ; 'h'; Cbdq
0x14000c1ee  call    cs:__imp_FltCbdqRemoveNextIo
0x14000c1f5  nop     dword ptr [rax+rax+00h]
0x14000c1fa  mov     rcx, [rbx+48h]; P
0x14000c1fe  test    rcx, rcx
0x14000c201  jz      short loc_14000C211
0x14000c203  xor     edx, edx; Tag
0x14000c205  call    cs:__imp_ExFreePoolWithTag
0x14000c20c  nop     dword ptr [rax+rax+00h]
0x14000c211  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x14000c218  jz      short loc_14000C231
0x14000c21a  lea     r8, [rbx+30h]
0x14000c21e  lea     rdx, StrmFlt_STREAM_FAULT_STOP
0x14000c225  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x14000c22c  call    McTemplateK0_EtwWriteTransfer
0x14000c231  mov     rcx, [rbx+28h]; P
0x14000c235  test    rcx, rcx
0x14000c238  jz      short loc_14000C250
0x14000c23a  xor     edx, edx; Tag
0x14000c23c  call    cs:__imp_ExFreePoolWithTag
0x14000c243  nop     dword ptr [rax+rax+00h]
0x14000c248  mov     qword ptr [rbx+28h], 0
0x14000c250  mov     rcx, [rbx+10h]; Object
0x14000c254  test    rcx, rcx
0x14000c257  jz      short loc_14000C26D
0x14000c259  call    cs:__imp_ObfDereferenceObject
0x14000c260  nop     dword ptr [rax+rax+00h]
0x14000c265  mov     qword ptr [rbx+10h], 0
0x14000c26d  mov     rcx, [rbx+8]; Context
0x14000c271  test    rcx, rcx
0x14000c274  jz      short loc_14000C282
0x14000c276  call    cs:__imp_FltReleaseContext
0x14000c27d  nop     dword ptr [rax+rax+00h]
0x14000c282  mov     rcx, [rbx]; Context
0x14000c285  test    rcx, rcx
0x14000c288  jz      short loc_14000C29D
0x14000c28a  call    cs:__imp_FltReleaseContext
0x14000c291  nop     dword ptr [rax+rax+00h]
0x14000c296  mov     qword ptr [rbx], 0
0x14000c29d  add     rsp, 20h
0x14000c2a1  pop     rbx
0x14000c2a2  retn
```
