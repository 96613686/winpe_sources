# CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::~CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>(void)

- ea: `0x18009855c`
- end: `0x1800985ad`
- name: `??1?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@UEAA@XZ`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180098800`
- `0x180098890`
- `0x180098930`

## callees

- `0x180002e18`
- `0x18009e664`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098599`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098599`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::~CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>(
        __int64 a1)
{
  unsigned __int64 v2; // rdx

  *(_QWORD *)a1 = &CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::`vftable';
  CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_DeleteAllItems(a1);
  operator delete(*(void **)(a1 + 48), v2);
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
}

```

## disassembly

```asm
0x18009855c  push    rbx
0x18009855e  sub     rsp, 30h
0x180098562  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18009856b  mov     rbx, rcx
0x18009856e  lea     rax, ??_7?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@6B@; const CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::`vftable'
0x180098575  mov     [rcx], rax
0x180098578  call    ?_DeleteAllItems@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@IEAAJXZ; CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_DeleteAllItems(void)
0x18009857d  mov     rcx, [rbx+30h]; void *
0x180098581  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180098586  mov     qword ptr [rbx+30h], 0
0x18009858e  mov     dword ptr [rbx+38h], 0
0x180098595  lea     rcx, [rbx+8]; lpCriticalSection
0x180098599  call    cs:__imp_DeleteCriticalSection
0x1800985a0  nop     dword ptr [rax+rax+00h]
0x1800985a5  nop
0x1800985a6  add     rsp, 30h
0x1800985aa  pop     rbx
0x1800985ab  retn
```
