# CDedupOptimizer::ReadFileCompletionWorker(void *)

- ea: `0x14007a2c0`
- end: `0x14007a513`
- name: `?ReadFileCompletionWorker@CDedupOptimizer@@CAKPEAX@Z`
- size: `595`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400635dc`
- `0x140075484`
- `0x140076c58`
- `0x140078814`
- `0x14007a204`
- `0x14007a2c0`
- `0x14007b4f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007a334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007a37a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007a334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007a37a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14007a3a3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14007a3a3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14007a369`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14007a369`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x14007a320`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x14007a320`

## string_xrefs

- `0x14007a38d`: `Unable to queue async read completion callback, error = 0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDedupOptimizer::ReadFileCompletionWorker(unsigned int *Parameter)
{
  DWORD LastError; // edi
  signed __int64 v3; // rsi
  bool v4; // zf
  signed __int64 v5; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  LPOVERLAPPED v7; // rdx
  char *v8; // r11
  _QWORD *i; // rcx
  __int64 v10; // r8
  __int64 v11; // r10
  __int64 v12; // rax
  __int64 v14; // [rsp+30h] [rbp-28h] BYREF
  utl::_RefCountBase *v15; // [rsp+38h] [rbp-20h]
  _BYTE v16[24]; // [rsp+40h] [rbp-18h] BYREF
  DWORD v17; // [rsp+80h] [rbp+28h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+88h] [rbp+30h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+90h] [rbp+38h] BYREF
  unsigned __int64 CompletionKey; // [rsp+98h] [rbp+40h] BYREF

  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  LastError = 0;
  Overlapped = 0;
  v3 = *((_QWORD *)Parameter + 116);
  while ( 1 )
  {
    if ( v3 )
    {
      v5 = _InterlockedCompareExchange64((volatile signed __int64 *)Parameter + 123, v3, v3);
      v4 = v3 == v5;
      v3 = v5;
      if ( v4 )
        break;
    }
    if ( GetQueuedCompletionStatus(
           *((HANDLE *)Parameter + 37),
           &NumberOfBytesTransferred,
           &CompletionKey,
           &Overlapped,
           0xFFFFFFFF) )
    {
      v7 = Overlapped;
      if ( !Overlapped )
        goto LABEL_25;
      if ( LODWORD(Overlapped[1].hEvent) > NumberOfBytesTransferred )
      {
        LODWORD(Overlapped[1].hEvent) = NumberOfBytesTransferred & -Parameter[60];
        v7 = Overlapped;
        v8 = (char *)Overlapped[1].Pointer + LODWORD(Overlapped[1].hEvent) - 1;
        for ( i = (_QWORD *)Overlapped[2].InternalHigh; i != v7[2].Pointer; i += 3 )
        {
          v10 = *i * Parameter[62];
          if ( (__int64)v8 < v10 )
          {
            v7[2].Pointer = i;
            v7 = Overlapped;
            break;
          }
          v11 = i[2];
          v12 = v10 + v11 * Parameter[62] - 1;
          if ( (__int64)v8 < v12 )
          {
            i[2] = v11 - (v12 - (__int64)v8) / Parameter[62];
            v7 = Overlapped;
          }
        }
      }
      utl::shared_ptr<CReadRequest>::shared_ptr<CReadRequest>(&v14, &v7[1]);
      HIDWORD(Overlapped[1].hEvent) = NumberOfBytesTransferred;
      _InterlockedAdd64((volatile signed __int64 *)(v14 + 64), NumberOfBytesTransferred);
      _InterlockedAdd64((volatile signed __int64 *)Parameter + 126, NumberOfBytesTransferred);
      CDedupOptimizer::QueueHashWork(Parameter, (struct SIoRun *const)Overlapped);
      Overlapped = 0;
      if ( v15 )
        utl::_RefCountBase::_DecStrong(v15);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError == 735 && !Overlapped )
        return LastError;
      if ( Overlapped )
      {
        ThreadpoolWork = CreateThreadpoolWork(
                           CDedupOptimizer::CompleteFailedAsyncReadCallback,
                           Overlapped,
                           (PTP_CALLBACK_ENVIRON)(Parameter + 78));
        if ( ThreadpoolWork )
        {
          SubmitThreadpoolWork(ThreadpoolWork);
        }
        else
        {
          v17 = GetLastError();
          DedupUtil::Print<unsigned long &>(6, L"Unable to queue async read completion callback, error = 0x%x\n", &v17);
        }
        Overlapped = 0;
      }
    }
  }
  v7 = Overlapped;
LABEL_25:
  if ( LastError && LastError != 735 && v7 )
  {
    utl::shared_ptr<CReadRequest>::shared_ptr<CReadRequest>(&v14, &v7[1]);
    _InterlockedIncrement64((volatile signed __int64 *)Parameter + 124);
    CReadRequest::FreeReadRun(v14, &v17, Overlapped);
    if ( (_BYTE)v17 )
    {
      utl::shared_ptr<CReadRequest>::shared_ptr<CReadRequest>(v16, &v14);
      CDedupOptimizer::CompleteRequest((CDedupOptimizer *)Parameter);
    }
    if ( v15 )
      utl::_RefCountBase::_DecStrong(v15);
  }
  return LastError;
}

```

## disassembly

```asm
0x14007a2c0  push    rbp
0x14007a2c2  push    rbx
0x14007a2c3  push    rsi
0x14007a2c4  push    rdi
0x14007a2c5  mov     rbp, rsp
0x14007a2c8  sub     rsp, 58h
0x14007a2cc  mov     rbx, rcx
0x14007a2cf  mov     [rbp+NumberOfBytesTransferred], 0
0x14007a2d6  mov     [rbp+CompletionKey], 0
0x14007a2de  xor     edi, edi
0x14007a2e0  mov     [rbp+Overlapped], rdi
0x14007a2e4  mov     rsi, [rcx+3A0h]
0x14007a2eb  test    rsi, rsi
0x14007a2ee  jz      short loc_14007A305
0x14007a2f0  mov     rax, rsi
0x14007a2f3  lock cmpxchg [rbx+3D8h], rsi
0x14007a2fc  mov     rsi, rax
0x14007a2ff  jz      loc_14007A49A
0x14007a305  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x14007a30d  lea     r9, [rbp+Overlapped]; lpOverlapped
0x14007a311  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x14007a315  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x14007a319  mov     rcx, [rbx+128h]; CompletionPort
0x14007a320  call    cs:__imp_GetQueuedCompletionStatus
0x14007a327  nop     dword ptr [rax+rax+00h]
0x14007a32c  test    eax, eax
0x14007a32e  jnz     loc_14007A3BC
0x14007a334  call    cs:__imp_GetLastError
0x14007a33b  nop     dword ptr [rax+rax+00h]
0x14007a340  mov     edi, eax
0x14007a342  mov     rdx, [rbp+Overlapped]; pv
0x14007a346  cmp     eax, 2DFh
0x14007a34b  jnz     short loc_14007A356
0x14007a34d  test    rdx, rdx
0x14007a350  jz      loc_14007A507
0x14007a356  test    rdx, rdx
0x14007a359  jz      short loc_14007A2EB
0x14007a35b  lea     r8, [rbx+138h]; pcbe
0x14007a362  lea     rcx, ?CompleteFailedAsyncReadCallback@CDedupOptimizer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14007a369  call    cs:__imp_CreateThreadpoolWork
0x14007a370  nop     dword ptr [rax+rax+00h]
0x14007a375  test    rax, rax
0x14007a378  jnz     short loc_14007A3A0
0x14007a37a  call    cs:__imp_GetLastError
0x14007a381  nop     dword ptr [rax+rax+00h]
0x14007a386  mov     [rbp+arg_0], eax
0x14007a389  lea     r8, [rbp+arg_0]
0x14007a38d  lea     rdx, aUnableToQueueA_0; "Unable to queue async read completion c"...
0x14007a394  mov     ecx, 6
0x14007a399  call    ??$Print@AEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAK@Z; DedupUtil::Print<ulong &>(DedupUtil::MessageType,ushort const *,ulong &)
0x14007a39e  jmp     short loc_14007A3AF
0x14007a3a0  mov     rcx, rax; pwk
0x14007a3a3  call    cs:__imp_SubmitThreadpoolWork
0x14007a3aa  nop     dword ptr [rax+rax+00h]
0x14007a3af  mov     [rbp+Overlapped], 0
0x14007a3b7  jmp     loc_14007A2EB
0x14007a3bc  mov     rdx, [rbp+Overlapped]
0x14007a3c0  test    rdx, rdx
0x14007a3c3  jz      loc_14007A49E
0x14007a3c9  mov     ecx, [rbp+NumberOfBytesTransferred]
0x14007a3cc  cmp     [rdx+38h], ecx
0x14007a3cf  jbe     short loc_14007A443
0x14007a3d1  mov     eax, [rbx+0F0h]
0x14007a3d7  neg     eax
0x14007a3d9  and     eax, ecx
0x14007a3db  mov     [rdx+38h], eax
0x14007a3de  mov     rdx, [rbp+Overlapped]
0x14007a3e2  mov     ecx, [rdx+38h]
0x14007a3e5  mov     r11, [rdx+30h]
0x14007a3e9  dec     rcx
0x14007a3ec  add     r11, rcx
0x14007a3ef  mov     rcx, [rdx+48h]
0x14007a3f3  cmp     rcx, [rdx+50h]
0x14007a3f7  jz      short loc_14007A443
0x14007a3f9  mov     r9d, [rbx+0F8h]
0x14007a400  mov     r8d, r9d
0x14007a403  imul    r8, [rcx]
0x14007a407  cmp     r11, r8
0x14007a40a  jl      short loc_14007A43B
0x14007a40c  mov     r10, [rcx+10h]
0x14007a410  mov     eax, r9d
0x14007a413  imul    rax, r10
0x14007a417  dec     rax
0x14007a41a  add     rax, r8
0x14007a41d  cmp     r11, rax
0x14007a420  jge     short loc_14007A435
0x14007a422  sub     rax, r11
0x14007a425  cqo
0x14007a427  idiv    r9
0x14007a42a  sub     r10, rax
0x14007a42d  mov     [rcx+10h], r10
0x14007a431  mov     rdx, [rbp+Overlapped]
0x14007a435  add     rcx, 18h
0x14007a439  jmp     short loc_14007A3F3
0x14007a43b  mov     [rdx+50h], rcx
0x14007a43f  mov     rdx, [rbp+Overlapped]
0x14007a443  add     rdx, 20h ; ' '
0x14007a447  lea     rcx, [rbp+var_28]
0x14007a44b  call    ??0?$shared_ptr@VCReadRequest@@@utl@@QEAA@AEBV01@@Z; utl::shared_ptr<CReadRequest>::shared_ptr<CReadRequest>(utl::shared_ptr<CReadRequest> const &)
0x14007a450  nop
0x14007a451  mov     ecx, [rbp+NumberOfBytesTransferred]
0x14007a454  mov     rax, [rbp+Overlapped]
0x14007a458  mov     [rax+3Ch], ecx
0x14007a45b  mov     ecx, [rbp+NumberOfBytesTransferred]
0x14007a45e  mov     rax, [rbp+var_28]
0x14007a462  lock add [rax+40h], rcx
0x14007a467  mov     eax, [rbp+NumberOfBytesTransferred]
0x14007a46a  lock add [rbx+3F0h], rax
0x14007a472  mov     rdx, [rbp+Overlapped]; struct SIoRun *
0x14007a476  mov     rcx, rbx; pv
0x14007a479  call    ?QueueHashWork@CDedupOptimizer@@AEAAXQEAUSIoRun@@@Z; CDedupOptimizer::QueueHashWork(SIoRun * const)
0x14007a47e  mov     [rbp+Overlapped], 0
0x14007a486  mov     rcx, [rbp+var_20]; this
0x14007a48a  test    rcx, rcx
0x14007a48d  jz      short loc_14007A495
0x14007a48f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14007a494  nop
0x14007a495  jmp     loc_14007A2EB
0x14007a49a  mov     rdx, [rbp+Overlapped]
0x14007a49e  test    edi, edi
0x14007a4a0  jz      short loc_14007A507
0x14007a4a2  cmp     edi, 2DFh
0x14007a4a8  jz      short loc_14007A507
0x14007a4aa  test    rdx, rdx
0x14007a4ad  jz      short loc_14007A507
0x14007a4af  add     rdx, 20h ; ' '
0x14007a4b3  lea     rcx, [rbp+var_28]
0x14007a4b7  call    ??0?$shared_ptr@VCReadRequest@@@utl@@QEAA@AEBV01@@Z; utl::shared_ptr<CReadRequest>::shared_ptr<CReadRequest>(utl::shared_ptr<CReadRequest> const &)
0x14007a4bc  nop
0x14007a4bd  lock inc qword ptr [rbx+3E0h]
0x14007a4c5  mov     r8, [rbp+Overlapped]
0x14007a4c9  lea     rdx, [rbp+arg_0]
0x14007a4cd  mov     rcx, [rbp+var_28]
0x14007a4d1  call    ?FreeReadRun@CReadRequest@@QEAA?AU?$pair@_N_N@std@@PEAUSIoRun@@@Z; CReadRequest::FreeReadRun(SIoRun *)
0x14007a4d6  cmp     byte ptr [rbp+arg_0], 0
0x14007a4da  jz      short loc_14007A4F8
0x14007a4dc  lea     rdx, [rbp+var_28]
0x14007a4e0  lea     rcx, [rbp+var_18]
0x14007a4e4  call    ??0?$shared_ptr@VCReadRequest@@@utl@@QEAA@AEBV01@@Z; utl::shared_ptr<CReadRequest>::shared_ptr<CReadRequest>(utl::shared_ptr<CReadRequest> const &)
0x14007a4e9  mov     r8d, edi
0x14007a4ec  mov     rdx, rax
0x14007a4ef  mov     rcx, rbx
0x14007a4f2  call    ?CompleteRequest@CDedupOptimizer@@AEAAKV?$shared_ptr@VCReadRequest@@@utl@@K@Z; CDedupOptimizer::CompleteRequest(utl::shared_ptr<CReadRequest>,ulong)
0x14007a4f7  nop
0x14007a4f8  mov     rcx, [rbp+var_20]; this
0x14007a4fc  test    rcx, rcx
0x14007a4ff  jz      short loc_14007A507
0x14007a501  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14007a506  nop
0x14007a507  mov     eax, edi
0x14007a509  add     rsp, 58h
0x14007a50d  pop     rdi
0x14007a50e  pop     rsi
0x14007a50f  pop     rbx
0x14007a510  pop     rbp
0x14007a511  retn
```
