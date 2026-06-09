# CmsRestarter::FlushAndCheckpoint(CmsTransactionContext *,_ML_LSN)

- ea: `0x140157904`
- end: `0x140157bf4`
- name: `?FlushAndCheckpoint@CmsRestarter@@AEAAJPEAVCmsTransactionContext@@T_ML_LSN@@@Z`
- size: `752`
- prototype: `int __high(struct CmsTransactionContext *, union _ML_LSN)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14015cf70`
- `0x14015d68c`

## callees

- `0x140008678`
- `0x140014750`
- `0x140086670`
- `0x140156178`
- `0x140156334`
- `0x140156964`
- `0x140157904`
- `0x14015efbc`
- `0x14015f214`
- `0x14017cb0c`
- `0x14017d30c`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x140157978`
- `ntoskrnl!IoGetActivityIdThread` at `0x140157b91`
- `ntoskrnl!IoGetActivityIdThread` at `0x140157978`
- `ntoskrnl!IoGetActivityIdThread` at `0x140157b91`
- `ntoskrnl!KeSetEvent` at `0x1401579ba`
- `ntoskrnl!KeSetEvent` at `0x1401579d2`
- `ntoskrnl!KeSetEvent` at `0x1401579ba`
- `ntoskrnl!KeSetEvent` at `0x1401579d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140157a81`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140157a81`
- `ntoskrnl!KeReleaseSpinLock` at `0x140157a92`
- `ntoskrnl!KeReleaseSpinLock` at `0x140157a92`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140157945`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140157945`
- `ntoskrnl!KeWaitForSingleObject` at `0x140157a6b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140157a6b`

## pseudocode

```c
__int64 __fastcall CmsRestarter::FlushAndCheckpoint(__int64 *a1, CmsTransactionContext *a2, unsigned __int64 a3)
{
  CmsTransactionContext *v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rcx
  ULONG v8; // r12d
  int v9; // edi
  __int64 v10; // rsi
  __int64 v11; // r14
  int ActivityIdThread; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 v16; // rsi
  KIRQL v17; // al
  __int64 v18; // r8
  __int64 v19; // rdx
  unsigned int v20; // edi
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // ebx
  __int64 v24; // rdi
  __int64 v25; // rsi
  int v26; // eax
  _QWORD v28[2]; // [rsp+40h] [rbp-40h] BYREF
  ULONG v29; // [rsp+50h] [rbp-30h]
  _OWORD v30[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v31; // [rsp+78h] [rbp-8h]
  int DiscardLogLsn; // [rsp+C0h] [rbp+40h] BYREF
  CmsTransactionContext *v33; // [rsp+C8h] [rbp+48h]
  __int64 v34; // [rsp+D0h] [rbp+50h] BYREF

  v33 = a2;
  v31 = 0;
  DiscardLogLsn = 0;
  memset(v30, 0, sizeof(v30));
  v5 = a2;
  v8 = 2 * KeQueryActiveProcessorCountEx(0xFFFFu);
  if ( dword_1402473A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
  {
    v9 = *((_DWORD *)a1 + 50);
    v10 = a1[12];
    v11 = a1[13];
    ActivityIdThread = IoGetActivityIdThread(v7, v6);
    McTemplateK0iix_EtwWriteTransfer(
      (unsigned int)MinstoreEventProvider_Context,
      (unsigned int)RedoPassFlushAndCheckpointStart,
      ActivityIdThread,
      v11,
      v10,
      v9);
    v5 = v33;
  }
  KeSetEvent((PRKEVENT)(a1 + 49), 0, 0);
  KeSetEvent((PRKEVENT)(a1 + 46), 0, 0);
  if ( a3 && a3 > a1[13] )
  {
    a1[13] = a3;
    ++*((_DWORD *)a1 + 26);
  }
  v28[0] = a1;
  v28[1] = &DiscardLogLsn;
  v29 = v8;
  if ( (unsigned __int8)ForEachOpenTableDepthFirst__CmsRestarter::FlushAndCheckpoint_::_2_::_lambda_1____(a1 + 15, v28) )
  {
    CmsTransactionContext::Commit(v5, v13, 0, 0);
    v15 = a1[19];
    v16 = a1[20];
    while ( v15 != v16 )
    {
      if ( !(unsigned __int8)CmsRestarter::FlushAndCheckpoint_::_2_::_lambda_1_::operator()(v28, v15) )
        goto LABEL_18;
      v15 += 72;
    }
    KeWaitForSingleObject(a1 + 49, Executive, 0, 0, 0);
    v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 52);
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 52, v17);
    v18 = a1[20];
    v19 = a1[19];
    DiscardLogLsn = *((_DWORD *)a1 + 91);
    utl::remove_if_utl::_ArrayIt_SmsOpenTable___CmsRestarter::FlushAndCheckpoint_::_20_::_lambda_2___(
      &v34,
      v19,
      v18,
      v33);
    utl::vector<SmsOpenTable,utl::allocator<SmsOpenTable>>::erase(a1 + 19, &v34, v34, a1[20]);
    v20 = DiscardLogLsn;
    if ( DiscardLogLsn >= 0 )
    {
      if ( !a3 )
        goto LABEL_16;
      v21 = *a1;
      v34 = 0;
      DiscardLogLsn = MlLogGetDiscardLogLsn(*(_QWORD *)(v21 + 72), a3, &v34);
      v20 = DiscardLogLsn;
      if ( DiscardLogLsn >= 0 )
      {
        v22 = *a1;
        a1[13] = v34;
        DiscardLogLsn = MlLogSetEndOfLog(*(void **)(v22 + 72));
        v20 = DiscardLogLsn;
        if ( DiscardLogLsn >= 0 )
        {
LABEL_16:
          DiscardLogLsn = CmsVolume::Flush(a1[1], 1, 0);
          v20 = DiscardLogLsn;
          if ( DiscardLogLsn == -1073741772 )
          {
            v20 = -1073741072;
            DiscardLogLsn = -1073741072;
          }
        }
      }
    }
  }
  else
  {
LABEL_18:
    v20 = DiscardLogLsn;
  }
  if ( dword_1402473A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
  {
    v23 = *((_DWORD *)a1 + 50);
    v24 = a1[12];
    v25 = a1[13];
    v26 = IoGetActivityIdThread(v14, v13);
    McTemplateK0iix_EtwWriteTransfer(
      (unsigned int)MinstoreEventProvider_Context,
      (unsigned int)RedoPassFlushAndCheckpointEnd,
      v26,
      v25,
      v24,
      v23);
    v20 = DiscardLogLsn;
  }
  if ( v20 == -1073741772 )
  {
    v20 = 0;
    DiscardLogLsn = 0;
  }
  SmsLookupStack::~SmsLookupStack((SmsLookupStack *)v30);
  return v20;
}

```

## disassembly

```asm
0x140157904  mov     [rsp-38h+arg_18], rbx
0x140157909  mov     [rsp-38h+arg_8], rdx
0x14015790e  push    rbp
0x14015790f  push    rsi
0x140157910  push    rdi
0x140157911  push    r12
0x140157913  push    r13
0x140157915  push    r14
0x140157917  push    r15
0x140157919  mov     rbp, rsp
0x14015791c  sub     rsp, 80h
0x140157923  xorps   xmm0, xmm0
0x140157926  xor     eax, eax
0x140157928  mov     r15, rcx
0x14015792b  mov     [rbp+var_8], rax
0x14015792f  mov     ecx, 0FFFFh; GroupNumber
0x140157934  mov     [rbp+arg_0], eax
0x140157937  movups  [rbp+var_28], xmm0
0x14015793b  mov     rbx, r8
0x14015793e  mov     rdi, rdx
0x140157941  movups  [rbp+var_18], xmm0
0x140157945  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14015794c  nop     dword ptr [rax+rax+00h]
0x140157951  mov     r12d, eax
0x140157954  add     r12d, r12d
0x140157957  cmp     cs:dword_1402473A4, 1
0x14015795e  jnz     short loc_1401579AB
0x140157960  test    cs:Microsoft_Windows_MinstoreEnableBits, 1
0x140157967  jz      short loc_1401579AB
0x140157969  mov     edi, [r15+0C8h]
0x140157970  mov     rsi, [r15+60h]
0x140157974  mov     r14, [r15+68h]
0x140157978  call    cs:__imp_IoGetActivityIdThread
0x14015797f  nop     dword ptr [rax+rax+00h]
0x140157984  mov     [rsp+80h+var_58], rdi
0x140157989  lea     rdx, RedoPassFlushAndCheckpointStart
0x140157990  mov     r8, rax
0x140157993  mov     [rsp+80h+Timeout], rsi
0x140157998  mov     r9, r14
0x14015799b  lea     rcx, MinstoreEventProvider_Context
0x1401579a2  call    McTemplateK0iix_EtwWriteTransfer
0x1401579a7  mov     rdi, [rbp+arg_8]
0x1401579ab  lea     r13, [r15+188h]
0x1401579b2  xor     r8d, r8d; Wait
0x1401579b5  mov     rcx, r13; Event
0x1401579b8  xor     edx, edx; Increment
0x1401579ba  call    cs:__imp_KeSetEvent
0x1401579c1  nop     dword ptr [rax+rax+00h]
0x1401579c6  lea     rcx, [r15+170h]; Event
0x1401579cd  xor     r8d, r8d; Wait
0x1401579d0  xor     edx, edx; Increment
0x1401579d2  call    cs:__imp_KeSetEvent
0x1401579d9  nop     dword ptr [rax+rax+00h]
0x1401579de  test    rbx, rbx
0x1401579e1  jz      short loc_1401579F1
0x1401579e3  cmp     rbx, [r15+68h]
0x1401579e7  jbe     short loc_1401579F1
0x1401579e9  mov     [r15+68h], rbx
0x1401579ed  inc     dword ptr [r15+68h]
0x1401579f1  lea     rax, [rbp+arg_0]
0x1401579f5  mov     [rbp+var_40], r15
0x1401579f9  lea     rcx, [r15+78h]
0x1401579fd  mov     [rbp+var_38], rax
0x140157a01  lea     rdx, [rbp+var_40]
0x140157a05  mov     [rbp+var_30], r12d
0x140157a09  call    ForEachOpenTableDepthFirst__CmsRestarter__FlushAndCheckpoint____2____lambda_1____
0x140157a0e  mov     r12d, 0C0000034h
0x140157a14  test    al, al
0x140157a16  jz      loc_140157B6D
0x140157a1c  xor     r9d, r9d; unsigned __int8
0x140157a1f  xor     r8d, r8d; struct _SmsLsn *
0x140157a22  mov     rcx, rdi; this
0x140157a25  call    ?Commit@CmsTransactionContext@@QEAAJEPEAU_SmsLsn@@E@Z; CmsTransactionContext::Commit(uchar,_SmsLsn *,uchar)
0x140157a2a  lea     r14, [r15+98h]
0x140157a31  mov     rdi, [r14]
0x140157a34  mov     rsi, [r14+8]
0x140157a38  cmp     rdi, rsi
0x140157a3b  jz      short loc_140157A57
0x140157a3d  mov     rdx, rdi
0x140157a40  lea     rcx, [rbp+var_40]
0x140157a44  call    _CmsRestarter__FlushAndCheckpoint____2____lambda_1___operator__
0x140157a49  test    al, al
0x140157a4b  jz      loc_140157B6D
0x140157a51  add     rdi, 48h ; 'H'
0x140157a55  jmp     short loc_140157A38
0x140157a57  xor     r9d, r9d; Alertable
0x140157a5a  mov     [rsp+80h+Timeout], 0; Timeout
0x140157a63  xor     r8d, r8d; WaitMode
0x140157a66  xor     edx, edx; WaitReason
0x140157a68  mov     rcx, r13; Object
0x140157a6b  call    cs:__imp_KeWaitForSingleObject
0x140157a72  nop     dword ptr [rax+rax+00h]
0x140157a77  lea     rdi, [r15+1A0h]
0x140157a7e  mov     rcx, rdi; SpinLock
0x140157a81  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140157a88  nop     dword ptr [rax+rax+00h]
0x140157a8d  mov     dl, al; NewIrql
0x140157a8f  mov     rcx, rdi; SpinLock
0x140157a92  call    cs:__imp_KeReleaseSpinLock
0x140157a99  nop     dword ptr [rax+rax+00h]
0x140157a9e  mov     eax, [r15+16Ch]
0x140157aa5  lea     rcx, [rbp+arg_10]
0x140157aa9  mov     r8, [r15+0A0h]
0x140157ab0  mov     rdx, [r14]
0x140157ab3  mov     r9, [rbp+arg_8]
0x140157ab7  mov     [rbp+arg_0], eax
0x140157aba  call    utl__remove_if_utl___ArrayIt_SmsOpenTable___CmsRestarter__FlushAndCheckpoint____20____lambda_2___
0x140157abf  mov     r9, [r15+0A0h]
0x140157ac6  lea     rdx, [rbp+arg_10]
0x140157aca  mov     r8, [rbp+arg_10]
0x140157ace  mov     rcx, r14
0x140157ad1  call    ?erase@?$vector@USmsOpenTable@@V?$allocator@USmsOpenTable@@@utl@@@utl@@QEAA?AV?$_ArrayIt@USmsOpenTable@@@2@V?$_ArrayConstIt@USmsOpenTable@@@2@0@Z; utl::vector<SmsOpenTable,utl::allocator<SmsOpenTable>>::erase(utl::_ArrayConstIt<SmsOpenTable>,utl::_ArrayConstIt<SmsOpenTable>)
0x140157ad6  mov     edi, [rbp+arg_0]
0x140157ad9  test    edi, edi
0x140157adb  js      loc_140157B70
0x140157ae1  test    rbx, rbx
0x140157ae4  jz      short loc_140157B2B
0x140157ae6  mov     rcx, [r15]
0x140157ae9  lea     r8, [rbp+arg_10]
0x140157aed  mov     rdx, rbx
0x140157af0  mov     [rbp+arg_10], 0
0x140157af8  mov     rcx, [rcx+48h]
0x140157afc  call    MlLogGetDiscardLogLsn
0x140157b01  mov     [rbp+arg_0], eax
0x140157b04  mov     edi, eax
0x140157b06  test    eax, eax
0x140157b08  js      short loc_140157B70
0x140157b0a  mov     rcx, [r15]
0x140157b0d  mov     r8, [rbp+arg_10]
0x140157b11  mov     rdx, [r15+8]
0x140157b15  mov     [r15+68h], r8
0x140157b19  mov     rcx, [rcx+48h]; Src
0x140157b1d  call    MlLogSetEndOfLog
0x140157b22  mov     [rbp+arg_0], eax
0x140157b25  mov     edi, eax
0x140157b27  test    eax, eax
0x140157b29  js      short loc_140157B70
0x140157b2b  mov     rcx, [r15+8]
0x140157b2f  xor     r9d, r9d
0x140157b32  mov     [rsp+80h+var_50], 0
0x140157b3b  xor     r8d, r8d
0x140157b3e  mov     [rsp+80h+var_58], 0
0x140157b47  mov     [rsp+80h+Timeout], 0
0x140157b50  lea     edx, [r9+1]
0x140157b54  call    ?Flush@CmsVolume@@QEAAJW4EmsTreeUpdateFlags@@PEAXKPEA_N2PEAU_KEVENT@@@Z; CmsVolume::Flush(EmsTreeUpdateFlags,void *,ulong,bool *,bool *,_KEVENT *)
0x140157b59  mov     [rbp+arg_0], eax
0x140157b5c  mov     edi, eax
0x140157b5e  cmp     eax, r12d
0x140157b61  jnz     short loc_140157B70
0x140157b63  mov     edi, 0C00002F0h
0x140157b68  mov     [rbp+arg_0], edi
0x140157b6b  jmp     short loc_140157B70
0x140157b6d  mov     edi, [rbp+arg_0]
0x140157b70  cmp     cs:dword_1402473A4, 1
0x140157b77  jnz     short loc_140157BC3
0x140157b79  test    cs:Microsoft_Windows_MinstoreEnableBits, 1
0x140157b80  jz      short loc_140157BC3
0x140157b82  mov     ebx, [r15+0C8h]
0x140157b89  mov     rdi, [r15+60h]
0x140157b8d  mov     rsi, [r15+68h]
0x140157b91  call    cs:__imp_IoGetActivityIdThread
0x140157b98  nop     dword ptr [rax+rax+00h]
0x140157b9d  mov     [rsp+80h+var_58], rbx
0x140157ba2  lea     rdx, RedoPassFlushAndCheckpointEnd
0x140157ba9  mov     r8, rax
0x140157bac  mov     [rsp+80h+Timeout], rdi
0x140157bb1  mov     r9, rsi
0x140157bb4  lea     rcx, MinstoreEventProvider_Context
0x140157bbb  call    McTemplateK0iix_EtwWriteTransfer
0x140157bc0  mov     edi, [rbp+arg_0]
0x140157bc3  cmp     edi, r12d
0x140157bc6  jnz     short loc_140157BCD
0x140157bc8  xor     edi, edi
0x140157bca  mov     [rbp+arg_0], edi
0x140157bcd  lea     rcx, [rbp+var_28]; this
0x140157bd1  call    ??1SmsLookupStack@@QEAA@XZ; SmsLookupStack::~SmsLookupStack(void)
0x140157bd6  mov     rbx, [rsp+80h+arg_18]
0x140157bde  mov     eax, edi
0x140157be0  add     rsp, 80h
0x140157be7  pop     r15
0x140157be9  pop     r14
0x140157beb  pop     r13
0x140157bed  pop     r12
0x140157bef  pop     rdi
0x140157bf0  pop     rsi
0x140157bf1  pop     rbp
0x140157bf2  retn
```
