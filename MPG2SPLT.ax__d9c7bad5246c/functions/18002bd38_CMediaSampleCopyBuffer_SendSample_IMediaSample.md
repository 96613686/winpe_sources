# CMediaSampleCopyBuffer::SendSample(IMediaSample *)

- ea: `0x18002bd38`
- end: `0x18002bd9f`
- name: `?SendSample@CMediaSampleCopyBuffer@@AEAAJPEAUIMediaSample@@@Z`
- size: `103`
- prototype: `int(CMediaSampleCopyBuffer *__hidden this, struct IMediaSample *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002b570`

## callees

- `0x180023c8c`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002bd60`
- `KERNEL32!LeaveCriticalSection` at `0x18002bd60`
- `KERNEL32!EnterCriticalSection` at `0x18002bd87`
- `KERNEL32!EnterCriticalSection` at `0x18002bd87`

## pseudocode

```c
__int64 __fastcall CMediaSampleCopyBuffer::SendSample(CMediaSampleCopyBuffer *this, struct IMediaSample *a2)
{
  unsigned int v4; // ebx

  ((void (__fastcall *)(struct IMediaSample *))a2->lpVtbl->AddRef)(a2);
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 6));
  v4 = CMPEG2DemuxOutputPin::SendSample(*((CMPEG2DemuxOutputPin **)this + 4), a2);
  ((void (__fastcall *)(struct IMediaSample *))a2->lpVtbl->Release)(a2);
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 6));
  return v4;
}

```

## disassembly

```asm
0x18002bd38  mov     [rsp+arg_0], rbx
0x18002bd3d  mov     [rsp+arg_8], rsi
0x18002bd42  push    rdi
0x18002bd43  sub     rsp, 20h
0x18002bd47  mov     rax, [rdx]
0x18002bd4a  mov     rsi, rcx
0x18002bd4d  mov     rcx, rdx
0x18002bd50  mov     rdi, rdx
0x18002bd53  mov     rax, [rax+8]
0x18002bd57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd5c  mov     rcx, [rsi+30h]; lpCriticalSection
0x18002bd60  call    cs:__imp_LeaveCriticalSection
0x18002bd66  mov     rcx, [rsi+20h]; this
0x18002bd6a  mov     rdx, rdi; struct IMediaSample *
0x18002bd6d  call    ?SendSample@CMPEG2DemuxOutputPin@@QEAAJPEAUIMediaSample@@@Z; CMPEG2DemuxOutputPin::SendSample(IMediaSample *)
0x18002bd72  mov     rcx, [rdi]
0x18002bd75  mov     ebx, eax
0x18002bd77  mov     rax, [rcx+10h]
0x18002bd7b  mov     rcx, rdi
0x18002bd7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd83  mov     rcx, [rsi+30h]; lpCriticalSection
0x18002bd87  call    cs:__imp_EnterCriticalSection
0x18002bd8d  mov     rsi, [rsp+28h+arg_8]
0x18002bd92  mov     eax, ebx
0x18002bd94  mov     rbx, [rsp+28h+arg_0]
0x18002bd99  add     rsp, 20h
0x18002bd9d  pop     rdi
0x18002bd9e  retn
```
