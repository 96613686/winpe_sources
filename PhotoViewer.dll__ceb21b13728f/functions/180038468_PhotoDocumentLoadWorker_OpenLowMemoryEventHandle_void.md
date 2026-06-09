# PhotoDocumentLoadWorker::OpenLowMemoryEventHandle(void)

- ea: `0x180038468`
- end: `0x180038520`
- name: `?OpenLowMemoryEventHandle@PhotoDocumentLoadWorker@@AEAAPEAXXZ`
- size: `184`
- prototype: `void *__fastcall(PhotoDocumentLoadWorker *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e164`
- `0x180061bcc`

## callees

- `0x180038468`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x1800384d6`
- `KERNEL32!InitOnceComplete` at `0x1800384d6`
- `KERNEL32!InitOnceBeginInitialize` at `0x180038496`
- `KERNEL32!InitOnceBeginInitialize` at `0x180038501`
- `KERNEL32!InitOnceBeginInitialize` at `0x180038496`
- `KERNEL32!InitOnceBeginInitialize` at `0x180038501`
- `KERNEL32!CloseHandle` at `0x1800384e5`
- `KERNEL32!CloseHandle` at `0x1800384e5`
- `KERNEL32!CreateEventW` at `0x1800384b7`
- `KERNEL32!CreateEventW` at `0x1800384b7`

## string_xrefs

- `0x1800384aa`: `Local\PhotoDocumentLoadWorkerUnloadCachedFramesEvent`

## pseudocode

```c
HANDLE __fastcall PhotoDocumentLoadWorker::OpenLowMemoryEventHandle(PhotoDocumentLoadWorker *this)
{
  HANDLE EventW; // rax
  BOOL fPending; // [rsp+30h] [rbp+8h] BYREF
  int v4; // [rsp+34h] [rbp+Ch]
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF

  v4 = HIDWORD(this);
  fPending = 0;
  hObject = 0;
  if ( InitOnceBeginInitialize(&PhotoDocumentLoadWorker::m_sLowMemoryInitOnce, 2u, &fPending, &hObject)
    && (!fPending
     || (EventW = CreateEventW(0, 1, 0, L"Local\\PhotoDocumentLoadWorkerUnloadCachedFramesEvent"),
         (hObject = EventW) != 0)
     && (InitOnceComplete(&PhotoDocumentLoadWorker::m_sLowMemoryInitOnce, 2u, EventW)
      || (CloseHandle(hObject),
          InitOnceBeginInitialize(&PhotoDocumentLoadWorker::m_sLowMemoryInitOnce, 1u, &fPending, &hObject))
      && !fPending)) )
  {
    return hObject;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180038468  mov     rax, rsp
0x18003846b  mov     [rax+8], rcx
0x18003846f  sub     rsp, 28h
0x180038473  lea     r9, [rax+10h]; lpContext
0x180038477  mov     dword ptr [rax+8], 0
0x18003847e  lea     r8, [rax+8]; fPending
0x180038482  mov     qword ptr [rax+10h], 0
0x18003848a  mov     edx, 2; dwFlags
0x18003848f  lea     rcx, ?m_sLowMemoryInitOnce@PhotoDocumentLoadWorker@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x180038496  call    cs:__imp_InitOnceBeginInitialize
0x18003849c  test    eax, eax
0x18003849e  jz      short loc_180038519
0x1800384a0  cmp     [rsp+28h+fPending], 0
0x1800384a5  jz      short loc_180038512
0x1800384a7  xor     r8d, r8d; bInitialState
0x1800384aa  lea     r9, Name; "Local\\PhotoDocumentLoadWorkerUnloadCac"...
0x1800384b1  xor     ecx, ecx; lpEventAttributes
0x1800384b3  lea     edx, [r8+1]; bManualReset
0x1800384b7  call    cs:__imp_CreateEventW
0x1800384bd  mov     [rsp+28h+hObject], rax
0x1800384c2  test    rax, rax
0x1800384c5  jz      short loc_180038519
0x1800384c7  mov     r8, rax; lpContext
0x1800384ca  lea     rcx, ?m_sLowMemoryInitOnce@PhotoDocumentLoadWorker@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x1800384d1  mov     edx, 2; dwFlags
0x1800384d6  call    cs:__imp_InitOnceComplete
0x1800384dc  test    eax, eax
0x1800384de  jnz     short loc_180038512
0x1800384e0  mov     rcx, [rsp+28h+hObject]; hObject
0x1800384e5  call    cs:__imp_CloseHandle
0x1800384eb  lea     r9, [rsp+28h+hObject]; lpContext
0x1800384f0  mov     edx, 1; dwFlags
0x1800384f5  lea     r8, [rsp+28h+fPending]; fPending
0x1800384fa  lea     rcx, ?m_sLowMemoryInitOnce@PhotoDocumentLoadWorker@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x180038501  call    cs:__imp_InitOnceBeginInitialize
0x180038507  test    eax, eax
0x180038509  jz      short loc_180038519
0x18003850b  cmp     [rsp+28h+fPending], 0
0x180038510  jnz     short loc_180038519
0x180038512  mov     rax, [rsp+28h+hObject]
0x180038517  jmp     short loc_18003851B
0x180038519  xor     eax, eax
0x18003851b  add     rsp, 28h
0x18003851f  retn
```
