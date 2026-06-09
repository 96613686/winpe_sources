# COutputQueue::InitialThreadProc(void *)

- ea: `0x180033510`
- end: `0x180033545`
- name: `?InitialThreadProc@COutputQueue@@KAKPEAX@Z`
- size: `53`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800070c4`
- `0x180033510`
- `0x1800338e0`

## import_xrefs

- `ole32!CoUninitialize` at `0x180033532`
- `ole32!CoUninitialize` at `0x180033532`

## pseudocode

```c
__int64 __fastcall COutputQueue::InitialThreadProc(COutputQueue *lpThreadParameter)
{
  int v2; // edi
  unsigned int v3; // ebx

  v2 = CAMThread::CoInitializeHelper();
  v3 = COutputQueue::ThreadProc(lpThreadParameter);
  if ( !v2 )
    CoUninitialize();
  return v3;
}

```

## disassembly

```asm
0x180033510  mov     [rsp+arg_0], rbx
0x180033515  push    rdi
0x180033516  sub     rsp, 20h
0x18003351a  mov     rbx, rcx
0x18003351d  call    ?CoInitializeHelper@CAMThread@@SAJXZ; CAMThread::CoInitializeHelper(void)
0x180033522  mov     rcx, rbx; this
0x180033525  mov     edi, eax
0x180033527  call    ?ThreadProc@COutputQueue@@IEAAKXZ; COutputQueue::ThreadProc(void)
0x18003352c  mov     ebx, eax
0x18003352e  test    edi, edi
0x180033530  jnz     short loc_180033538
0x180033532  call    cs:__imp_CoUninitialize
0x180033538  mov     eax, ebx
0x18003353a  mov     rbx, [rsp+28h+arg_0]
0x18003353f  add     rsp, 20h
0x180033543  pop     rdi
0x180033544  retn
```
