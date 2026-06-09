# TraceEventInfo::TraceEventInfo(_EVENT_RECORD *,dxg::pmrlite::memory_resource *)

- ea: `0x1800265ec`
- end: `0x1800266a9`
- name: `??0TraceEventInfo@@QEAA@PEAU_EVENT_RECORD@@PEAUmemory_resource@pmrlite@dxg@@@Z`
- size: `189`
- prototype: `TraceEventInfo *__fastcall(TraceEventInfo *this, struct _EVENT_RECORD *, struct dxg::pmrlite::memory_resource *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019ee0`

## callees

- `0x18001c068`
- `0x1800265ec`
- `0x1800267d8`
- `0x180031010`

## import_xrefs

- `api-ms-win-eventing-tdh-l1-1-0!TdhGetEventInformation` at `0x18002661c`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetEventInformation` at `0x180026661`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetEventInformation` at `0x18002661c`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetEventInformation` at `0x180026661`

## string_xrefs

- `0x180026670`: `onecore\windows\directx\dxg\common\etwtracesession\traceeventinfo.cpp`

## pseudocode

```c
TraceEventInfo *__fastcall TraceEventInfo::TraceEventInfo(
        TraceEventInfo *this,
        struct _EVENT_RECORD *a2,
        struct dxg::pmrlite::memory_resource *a3)
{
  TDHSTATUS EventInformation; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  TRACE_EVENT_INFO *v7; // rax
  TDHSTATUS v8; // eax
  unsigned int BufferSize; // [rsp+20h] [rbp-18h]
  unsigned int BufferSizea; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  ULONG v13; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = a3;
  *((_QWORD *)this + 2) = a2;
  v13 = 0;
  EventInformation = TdhGetEventInformation(a2, 0, 0, 0, &v13);
  if ( EventInformation != 122 )
    wil::details::in1diag3::Throw_Win32(retaddr, v5, v6, (const char *)EventInformation, BufferSize);
  v7 = (TRACE_EVENT_INFO *)(***(__int64 (__fastcall ****)(_QWORD, _QWORD))this)(*(_QWORD *)this, v13);
  *((_QWORD *)this + 1) = v7;
  v8 = TdhGetEventInformation(*((PEVENT_RECORD *)this + 2), 0, 0, v7, &v13);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\windows\\directx\\dxg\\common\\etwtracesession\\traceeventinfo.cpp",
      (const char *)v8,
      BufferSizea);
  *((_WORD *)this + 12) = (*(_BYTE *)(*((_QWORD *)this + 2) + 4LL) & 0x20) != 0 ? 4 : 8;
  return this;
}

```

## disassembly

```asm
0x1800265ec  push    rbx
0x1800265ee  sub     rsp, 30h
0x1800265f2  mov     [rcx], r8
0x1800265f5  mov     rbx, rcx
0x1800265f8  mov     [rcx+10h], rdx
0x1800265fc  mov     rax, rdx
0x1800265ff  lea     rcx, [rsp+38h+arg_0]
0x180026604  mov     [rsp+38h+arg_0], 0
0x18002660c  mov     qword ptr [rsp+38h+BufferSize], rcx; unsigned int
0x180026611  xor     r9d, r9d; Buffer
0x180026614  mov     rcx, rax; Event
0x180026617  xor     r8d, r8d; TdhContext
0x18002661a  xor     edx, edx; TdhContextCount
0x18002661c  call    cs:__imp_TdhGetEventInformation
0x180026622  cmp     eax, 7Ah ; 'z'
0x180026625  jz      short loc_180026635
0x180026627  mov     rcx, [rsp+38h]; this
0x18002662c  mov     r9d, eax; char *
0x18002662f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180026635  mov     rcx, [rbx]
0x180026638  mov     edx, [rsp+38h+arg_0]
0x18002663c  mov     rax, [rcx]
0x18002663f  mov     rax, [rax]
0x180026642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026647  lea     rcx, [rsp+38h+arg_0]
0x18002664c  mov     [rbx+8], rax
0x180026650  mov     qword ptr [rsp+38h+BufferSize], rcx; unsigned int
0x180026655  mov     r9, rax; Buffer
0x180026658  mov     rcx, [rbx+10h]; Event
0x18002665c  xor     r8d, r8d; TdhContext
0x18002665f  xor     edx, edx; TdhContextCount
0x180026661  call    cs:__imp_TdhGetEventInformation
0x180026667  test    eax, eax
0x180026669  jz      short loc_180026685
0x18002666b  mov     rcx, [rsp+38h]; this
0x180026670  lea     r8, aOnecoreWindows_0; "onecore\\windows\\directx\\dxg\\common"...
0x180026677  mov     r9d, eax; char *
0x18002667a  mov     edx, 20h ; ' '; void *
0x18002667f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180026685  mov     rax, [rbx+10h]
0x180026689  mov     cl, [rax+4]
0x18002668c  and     cl, 20h
0x18002668f  neg     cl
0x180026691  sbb     ax, ax
0x180026694  and     ax, 0FFFCh
0x180026698  add     ax, 8
0x18002669c  mov     [rbx+18h], ax
0x1800266a0  mov     rax, rbx
0x1800266a3  add     rsp, 30h
0x1800266a7  pop     rbx
0x1800266a8  retn
```
