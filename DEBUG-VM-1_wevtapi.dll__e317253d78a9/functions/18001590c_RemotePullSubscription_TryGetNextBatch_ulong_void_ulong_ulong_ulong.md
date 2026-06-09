# RemotePullSubscription::TryGetNextBatch(ulong,void * *,ulong,ulong,ulong *)

- ea: `0x18001590c`
- end: `0x180015f06`
- name: `?TryGetNextBatch@RemotePullSubscription@@QEAAKKPEAPEAXKKPEAK@Z`
- size: `1530`
- prototype: `__int64 __fastcall(RemotePullSubscription *this, int, void **, int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800068b0`

## callees

- `0x180007010`
- `0x18000a100`
- `0x18001590c`
- `0x180016230`
- `0x180023548`
- `0x1800236c4`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001595a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001595a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015daf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015daf`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180015b0f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180015b0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015be9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015be9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180015ae6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180015ae6`
- `RPCRT4!NdrClientCall3` at `0x1800159e1`
- `RPCRT4!NdrClientCall3` at `0x1800159e1`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180015b36`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180015b36`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RemotePullSubscription::TryGetNextBatch(
        RemotePullSubscription *this,
        int a2,
        void **a3,
        int a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned int *v10; // rsi
  DWORD v11; // eax
  unsigned int Pointer; // ebx
  __int64 v13; // rbx
  unsigned int v14; // edx
  int v15; // ecx
  void *v16; // rcx
  unsigned int v17; // edi
  __int64 v18; // rcx
  void *v19; // rdx
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  DWORD LastError; // ebx
  unsigned int v24; // ebx
  __int128 pExceptionObject; // [rsp+60h] [rbp-59h] BYREF
  __int64 v26; // [rsp+70h] [rbp-49h]
  int v27; // [rsp+78h] [rbp-41h]
  __int64 v28; // [rsp+7Ch] [rbp-3Dh]
  char v29; // [rsp+84h] [rbp-35h]
  int v30; // [rsp+88h] [rbp-31h] BYREF
  void *v31; // [rsp+90h] [rbp-29h] BYREF
  void *v32; // [rsp+98h] [rbp-21h] BYREF
  void *v33; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-11h] BYREF
  _QWORD v35[10]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned int Reply; // [rsp+118h] [rbp+5Fh] BYREF

  if ( !a2 || !a3 || (v10 = a6) == 0 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, 87);
    }
    pExceptionObject = 0;
    v26 = 0;
    v27 = 87;
    v28 = 0x120FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  v11 = WaitForSingleObject(*((HANDLE *)this + 25), 0);
  Reply = v11;
  if ( v11 == 258 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, 4317);
    }
    pExceptionObject = 0;
    v26 = 0;
    v27 = 4317;
    v28 = 0x127FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  if ( v11 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v26 = 0;
    v27 = LastError;
    v28 = 0x12CFFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *((_BYTE *)this + 273) )
  {
    *((_BYTE *)this + 273) = 0;
    v21 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)((char *)this + 64), &Reply);
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, v21);
      }
      pExceptionObject = 0;
      v26 = 0;
      v27 = v21;
      v28 = 0x139FFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    v22 = Reply;
    if ( Reply )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, Reply);
      }
      pExceptionObject = 0;
      v26 = 0;
      v27 = v22;
      v28 = 0x13FFFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
  }
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            2u,
                            0,
                            *((_QWORD *)this + 5),
                            a2,
                            a4,
                            a5,
                            v10,
                            &v33,
                            &v32,
                            &v30,
                            &v31).Pointer;
  if ( Pointer )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, Pointer);
    }
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v26 = 0;
    v27 = Pointer;
    v28 = -1;
    v29 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *v10 )
  {
    utl::make_unique<EventBatch,wmi::AutoRef<BookmarkChannels> &,unsigned long &,0>(v35, (char *)this + 216, v10);
    v13 = v35[0];
    if ( !v35[0] )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, 14);
      }
      pExceptionObject = 0;
      v26 = 0;
      v27 = 14;
      v28 = 0x175FFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    v14 = *v10;
    v15 = v30;
    *(_QWORD *)(v35[0] + 32LL) = v31;
    *(_DWORD *)(v13 + 40) = v15;
    *(_DWORD *)(v13 + 24) = v14;
    v16 = 0;
    v31 = 0;
    v17 = 0;
    if ( *v10 )
    {
      do
      {
        EventBatch::SetEventData((_QWORD *)v13, &v34, v17, *((_DWORD *)v33 + v17), *((_DWORD *)v32 + v17));
        v18 = v34;
        if ( v34 )
        {
          v19 = *(void **)(v34 + 16);
          v34 = 0;
          *(_BYTE *)(v18 + 29) = 1;
        }
        else
        {
          v19 = 0;
        }
        a3[v17] = v19;
        EvtHandleRef::~EvtHandleRef((EvtHandleRef *)&v34);
        ++v17;
      }
      while ( v17 < *v10 );
      v16 = v31;
    }
    if ( v16 )
      operator delete(v16);
    if ( v32 )
      operator delete(v32);
    if ( v33 )
      operator delete(v33);
    return 0;
  }
  else
  {
    ResetEvent(*((HANDLE *)this + 25));
    *((_BYTE *)this + 273) = 1;
    Reply = (unsigned int)Ndr64AsyncClientCall(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            3u,
                            0,
                            (char *)this + 64,
                            *((_QWORD *)this + 5)).Pointer;
    if ( Reply )
    {
      SetEvent(*((HANDLE *)this + 25));
      *((_BYTE *)this + 273) = 0;
      v24 = Reply;
      if ( !Reply )
        v24 = 1287;
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, v24);
      }
      pExceptionObject = 0;
      v26 = 0;
      v27 = v24;
      v28 = 0x16CFFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    if ( v31 )
      operator delete(v31);
    if ( v32 )
      operator delete(v32);
    if ( v33 )
      operator delete(v33);
    return 259;
  }
}

```

## disassembly

```asm
0x18001590c  push    rbp
0x18001590e  push    rbx
0x18001590f  push    rsi
0x180015910  push    rdi
0x180015911  push    r12
0x180015913  push    r13
0x180015915  push    r14
0x180015917  push    r15
0x180015919  lea     rbp, [rsp-0Fh]
0x18001591e  sub     rsp, 0C8h
0x180015925  mov     r13d, r9d
0x180015928  mov     r15, r8
0x18001592b  mov     r12d, edx
0x18001592e  mov     rdi, rcx
0x180015931  xor     ebx, ebx
0x180015933  test    edx, edx
0x180015935  jz      loc_180015E9E
0x18001593b  test    r8, r8
0x18001593e  jz      loc_180015E9E
0x180015944  mov     rsi, [rbp+47h+arg_28]
0x180015948  test    rsi, rsi
0x18001594b  jz      loc_180015E9E
0x180015951  xor     edx, edx; dwMilliseconds
0x180015953  mov     rcx, [rcx+0C8h]; hHandle
0x18001595a  call    cs:__imp_WaitForSingleObject
0x180015960  mov     [rbp+47h+Reply], eax
0x180015963  cmp     eax, 102h
0x180015968  jz      loc_180015B7D
0x18001596e  test    eax, eax
0x180015970  jnz     loc_180015BE9
0x180015976  lea     r14, [rdi+40h]
0x18001597a  cmp     [rdi+111h], bl
0x180015980  jnz     loc_180015AD9
0x180015986  mov     [rbp+47h+var_78], ebx
0x180015989  mov     [rbp+47h+var_70], rbx
0x18001598d  mov     [rbp+47h+var_68], rbx
0x180015991  mov     [rbp+47h+var_60], rbx
0x180015995  lea     rax, [rbp+47h+var_70]
0x180015999  mov     [rsp+100h+var_A8], rax
0x18001599e  lea     rax, [rbp+47h+var_78]
0x1800159a2  mov     [rsp+100h+var_B0], rax
0x1800159a7  lea     rax, [rbp+47h+var_68]
0x1800159ab  mov     [rsp+100h+var_B8], rax
0x1800159b0  lea     rax, [rbp+47h+var_60]
0x1800159b4  mov     [rsp+100h+var_C0], rax
0x1800159b9  mov     [rsp+100h+var_C8], rsi
0x1800159be  mov     eax, [rbp+47h+arg_20]
0x1800159c1  mov     [rsp+100h+var_D0], eax
0x1800159c5  mov     [rsp+100h+var_D8], r13d
0x1800159ca  mov     dword ptr [rsp+100h+var_E0], r12d
0x1800159cf  mov     r9, [rdi+28h]
0x1800159d3  xor     r8d, r8d; pReturnValue
0x1800159d6  lea     edx, [r8+2]; nProcNum
0x1800159da  lea     rcx, pProxyInfo; pProxyInfo
0x1800159e1  call    cs:__imp_NdrClientCall3
0x1800159e7  mov     rbx, rax
0x1800159ea  xor     r12d, r12d
0x1800159ed  test    eax, eax
0x1800159ef  jnz     loc_180015D3E
0x1800159f5  cmp     [rsi], r12d
0x1800159f8  jz      loc_180015B08
0x1800159fe  lea     rdx, [rdi+0D8h]
0x180015a05  mov     r8, rsi
0x180015a08  lea     rcx, [rbp+47h+var_50]
0x180015a0c  call    ??$make_unique@VEventBatch@@AEAV?$AutoRef@VBookmarkChannels@@@wmi@@AEAK$0A@@utl@@YA?AV?$unique_ptr@VEventBatch@@U?$default_delete@VEventBatch@@@utl@@@0@AEAV?$AutoRef@VBookmarkChannels@@@wmi@@AEAK@Z; utl::make_unique<EventBatch,wmi::AutoRef<BookmarkChannels> &,ulong &,0>(wmi::AutoRef<BookmarkChannels> &,ulong &)
0x180015a11  nop
0x180015a12  mov     rbx, [rbp+47h+var_50]
0x180015a16  test    rbx, rbx
0x180015a19  jz      loc_180015E36
0x180015a1f  mov     edx, [rsi]
0x180015a21  mov     ecx, [rbp+47h+var_78]
0x180015a24  mov     rax, [rbp+47h+var_70]
0x180015a28  mov     [rbx+20h], rax
0x180015a2c  mov     [rbx+28h], ecx
0x180015a2f  mov     [rbx+18h], edx
0x180015a32  mov     ecx, r12d
0x180015a35  mov     [rbp+47h+var_70], rcx
0x180015a39  mov     edi, r12d
0x180015a3c  cmp     [rsi], r12d
0x180015a3f  jbe     short loc_180015A9B
0x180015a41  mov     r14d, edi
0x180015a44  mov     rax, [rbp+47h+var_68]
0x180015a48  mov     ecx, [rax+r14*4]
0x180015a4c  mov     dword ptr [rsp+100h+var_E0], ecx
0x180015a50  mov     r9, [rbp+47h+var_60]
0x180015a54  mov     r9d, [r9+r14*4]
0x180015a58  mov     r8d, edi
0x180015a5b  lea     rdx, [rbp+47h+var_58]
0x180015a5f  mov     rcx, rbx
0x180015a62  call    ?SetEventData@EventBatch@@QEAA?AVEvtHandleRef@@KKK@Z; EventBatch::SetEventData(ulong,ulong,ulong)
0x180015a67  mov     rcx, [rbp+47h+var_58]
0x180015a6b  test    rcx, rcx
0x180015a6e  jz      loc_180015E2E
0x180015a74  mov     rdx, [rcx+10h]
0x180015a78  mov     [rbp+47h+var_58], r12
0x180015a7c  mov     eax, 1
0x180015a81  xchg    al, [rcx+1Dh]
0x180015a84  mov     [r15+r14*8], rdx
0x180015a88  lea     rcx, [rbp+47h+var_58]; this
0x180015a8c  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x180015a91  inc     edi
0x180015a93  cmp     edi, [rsi]
0x180015a95  jb      short loc_180015A41
0x180015a97  mov     rcx, [rbp+47h+var_70]; void *
0x180015a9b  test    rcx, rcx
0x180015a9e  jz      short loc_180015AA6
0x180015aa0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015aa5  nop
0x180015aa6  mov     rcx, [rbp+47h+var_68]; void *
0x180015aaa  test    rcx, rcx
0x180015aad  jz      short loc_180015AB5
0x180015aaf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015ab4  nop
0x180015ab5  mov     rcx, [rbp+47h+var_60]; void *
0x180015ab9  test    rcx, rcx
0x180015abc  jz      short loc_180015AC3
0x180015abe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015ac3  xor     eax, eax
0x180015ac5  add     rsp, 0C8h
0x180015acc  pop     r15
0x180015ace  pop     r14
0x180015ad0  pop     r13
0x180015ad2  pop     r12
0x180015ad4  pop     rdi
0x180015ad5  pop     rsi
0x180015ad6  pop     rbx
0x180015ad7  pop     rbp
0x180015ad8  retn
0x180015ad9  mov     [rdi+111h], bl
0x180015adf  lea     rdx, [rbp+47h+Reply]; Reply
0x180015ae3  mov     rcx, r14; pAsync
0x180015ae6  call    cs:__imp_RpcAsyncCompleteCall
0x180015aec  mov     ebx, eax
0x180015aee  test    eax, eax
0x180015af0  jnz     loc_180015C64
0x180015af6  mov     ebx, [rbp+47h+Reply]
0x180015af9  test    ebx, ebx
0x180015afb  jnz     loc_180015CCD
0x180015b01  xor     ebx, ebx
0x180015b03  jmp     loc_180015986
0x180015b08  mov     rcx, [rdi+0C8h]; hEvent
0x180015b0f  call    cs:__imp_ResetEvent
0x180015b15  mov     byte ptr [rdi+111h], 1
0x180015b1c  mov     rax, [rdi+28h]
0x180015b20  mov     [rsp+100h+var_E0], rax
0x180015b25  mov     r9, r14
0x180015b28  xor     r8d, r8d; pReturnValue
0x180015b2b  lea     edx, [r8+3]; nProcNum
0x180015b2f  lea     rcx, pProxyInfo; pProxyInfo
0x180015b36  call    cs:__imp_Ndr64AsyncClientCall
0x180015b3c  mov     [rbp+47h+Reply], eax
0x180015b3f  test    eax, eax
0x180015b41  jnz     loc_180015DA8
0x180015b47  mov     rcx, [rbp+47h+var_70]; void *
0x180015b4b  test    rcx, rcx
0x180015b4e  jz      short loc_180015B56
0x180015b50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015b55  nop
0x180015b56  mov     rcx, [rbp+47h+var_68]; void *
0x180015b5a  test    rcx, rcx
0x180015b5d  jz      short loc_180015B65
0x180015b5f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015b64  nop
0x180015b65  mov     rcx, [rbp+47h+var_60]; void *
0x180015b69  test    rcx, rcx
0x180015b6c  jz      short loc_180015B73
0x180015b6e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015b73  mov     eax, 103h
0x180015b78  jmp     loc_180015AC5
0x180015b7d  lea     rax, WPP_GLOBAL_Control
0x180015b84  mov     edi, 10DDh
0x180015b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b90  cmp     rcx, rax
0x180015b93  jz      short loc_180015BA1
0x180015b95  test    byte ptr [rcx+1Ch], 80h
0x180015b99  jz      short loc_180015BA1
0x180015b9b  cmp     byte ptr [rcx+19h], 2
0x180015b9f  jnb     short loc_180015BCF
0x180015ba1  xorps   xmm0, xmm0
0x180015ba4  movdqu  [rbp+47h+pExceptionObject], xmm0
0x180015ba9  mov     [rbp+47h+var_90], rbx
0x180015bad  mov     [rbp+47h+var_88], edi
0x180015bb0  mov     dword ptr [rbp+47h+var_84], 0FFFFFFFFh
0x180015bb7  mov     dword ptr [rbp+47h+var_84+4], 127h
0x180015bbe  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180015bc5  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x180015bc9  call    _CxxThrowException_0
0x180015bcf  mov     edx, 15h
0x180015bd4  mov     r9d, edi
0x180015bd7  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x180015bde  mov     rcx, [rcx+10h]
0x180015be2  call    WPP_SF_D
0x180015be7  jmp     short loc_180015BA1
0x180015be9  call    cs:__imp_GetLastError
0x180015bef  mov     ebx, eax
0x180015bf1  mov     eax, 507h
0x180015bf6  test    ebx, ebx
0x180015bf8  cmovz   ebx, eax
0x180015bfb  lea     rax, WPP_GLOBAL_Control
0x180015c02  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c09  cmp     rcx, rax
0x180015c0c  jz      short loc_180015C32
0x180015c0e  test    byte ptr [rcx+1Ch], 80h
0x180015c12  jz      short loc_180015C32
0x180015c14  cmp     byte ptr [rcx+19h], 2
0x180015c18  jb      short loc_180015C32
0x180015c1a  mov     edx, 16h
0x180015c1f  mov     r9d, ebx
0x180015c22  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x180015c29  mov     rcx, [rcx+10h]
0x180015c2d  call    WPP_SF_D
0x180015c32  xorps   xmm0, xmm0
0x180015c35  movdqu  [rbp+47h+pExceptionObject], xmm0
0x180015c3a  mov     [rbp+47h+var_90], 0
0x180015c42  mov     [rbp+47h+var_88], ebx
0x180015c45  mov     dword ptr [rbp+47h+var_84], 0FFFFFFFFh
0x180015c4c  mov     dword ptr [rbp+47h+var_84+4], 12Ch
0x180015c53  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180015c5a  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x180015c5e  call    _CxxThrowException_0
0x180015c64  lea     rax, WPP_GLOBAL_Control
0x180015c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c72  cmp     rcx, rax
0x180015c75  jz      short loc_180015C9B
0x180015c77  test    byte ptr [rcx+1Ch], 80h
0x180015c7b  jz      short loc_180015C9B
0x180015c7d  cmp     byte ptr [rcx+19h], 2
0x180015c81  jb      short loc_180015C9B
0x180015c83  mov     edx, 17h
0x180015c88  mov     r9d, ebx
0x180015c8b  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x180015c92  mov     rcx, [rcx+10h]
0x180015c96  call    WPP_SF_D
0x180015c9b  xorps   xmm0, xmm0
0x180015c9e  movdqu  [rbp+47h+pExceptionObject], xmm0
0x180015ca3  mov     [rbp+47h+var_90], 0
0x180015cab  mov     [rbp+47h+var_88], ebx
0x180015cae  mov     dword ptr [rbp+47h+var_84], 0FFFFFFFFh
0x180015cb5  mov     dword ptr [rbp+47h+var_84+4], 139h
0x180015cbc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180015cc3  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x180015cc7  call    _CxxThrowException_0
0x180015ccd  mov     eax, 507h
0x180015cd2  cmovz   ebx, eax
0x180015cd5  lea     rax, WPP_GLOBAL_Control
0x180015cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ce3  cmp     rcx, rax
0x180015ce6  jz      short loc_180015D0C
0x180015ce8  test    byte ptr [rcx+1Ch], 80h
0x180015cec  jz      short loc_180015D0C
0x180015cee  cmp     byte ptr [rcx+19h], 2
0x180015cf2  jb      short loc_180015D0C
0x180015cf4  mov     edx, 18h
0x180015cf9  mov     r9d, ebx
0x180015cfc  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x180015d03  mov     rcx, [rcx+10h]
0x180015d07  call    WPP_SF_D
0x180015d0c  xorps   xmm0, xmm0
0x180015d0f  movdqu  [rbp+47h+pExceptionObject], xmm0
0x180015d14  mov     [rbp+47h+var_90], 0
0x180015d1c  mov     [rbp+47h+var_88], ebx
0x180015d1f  mov     dword ptr [rbp+47h+var_84], 0FFFFFFFFh
0x180015d26  mov     dword ptr [rbp+47h+var_84+4], 13Fh
0x180015d2d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180015d34  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x180015d38  call    _CxxThrowException_0
0x180015d3e  lea     rax, WPP_GLOBAL_Control
0x180015d45  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d4c  cmp     rcx, rax
0x180015d4f  jz      short loc_180015D75
0x180015d51  test    byte ptr [rcx+1Ch], 80h
0x180015d55  jz      short loc_180015D75
0x180015d57  cmp     byte ptr [rcx+19h], 2
0x180015d5b  jb      short loc_180015D75
0x180015d5d  mov     edx, 19h
0x180015d62  mov     r9d, ebx
0x180015d65  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x180015d6c  mov     rcx, [rcx+10h]
0x180015d70  call    WPP_SF_D
0x180015d75  lea     rax, word_18004024A
0x180015d7c  mov     qword ptr [rbp+47h+pExceptionObject], rax
0x180015d80  mov     qword ptr [rbp+47h+pExceptionObject+8], r12
0x180015d84  mov     [rbp+47h+var_90], r12
0x180015d88  mov     [rbp+47h+var_88], ebx
0x180015d8b  mov     [rbp+47h+var_84], 0FFFFFFFFFFFFFFFFh
0x180015d93  mov     [rbp+47h+var_7C], r12b
0x180015d97  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180015d9e  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x180015da2  call    _CxxThrowException_0
0x180015da8  mov     rcx, [rdi+0C8h]; hEvent
0x180015daf  call    cs:__imp_SetEvent
0x180015db5  mov     [rdi+111h], r12b
0x180015dbc  mov     ebx, [rbp+47h+Reply]
0x180015dbf  mov     eax, 507h
0x180015dc4  test    ebx, ebx
0x180015dc6  cmovz   ebx, eax
0x180015dc9  lea     rax, WPP_GLOBAL_Control
0x180015dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180015dd7  cmp     rcx, rax
0x180015dda  jz      short loc_180015E00
  ... truncated ...
```
