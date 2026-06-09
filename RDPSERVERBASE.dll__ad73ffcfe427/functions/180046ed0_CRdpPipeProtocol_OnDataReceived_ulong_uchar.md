# CRdpPipeProtocol::OnDataReceived(ulong,uchar *)

- ea: `0x180046ed0`
- end: `0x180047694`
- name: `?OnDataReceived@CRdpPipeProtocol@@UEAAJKPEAE@Z`
- size: `1988`
- prototype: `__int64 __fastcall(CRdpPipeProtocol *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002aafc`
- `0x18002b14c`
- `0x180046ed0`
- `0x180077aa0`
- `0x180079724`
- `0x180079770`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x1800d748c`
- `0x180158180`
- `0x18019b31c`
- `0x18019c010`

## string_xrefs

- `0x180046ee3`: `IID_IRdpPipeProtocol`
- `0x1800470d4`: `IID_IRdpPipeProtocol`
- `0x180047131`: `IID_IRdpPipeProtocol`
- `0x1800471df`: `IID_IRdpPipeProtocol`
- `0x180047211`: `IID_IRdpPipeProtocol`
- `0x18004727a`: `IID_IRdpPipeProtocol`
- `0x1800472f7`: `IID_IRdpPipeProtocol`
- `0x1800473d9`: `IID_IRdpPipeProtocol`
- `0x18004740c`: `IID_IRdpPipeProtocol`
- `0x180047480`: `IID_IRdpPipeProtocol`
- `0x180047521`: `IID_IRdpPipeProtocol`
- `0x1800475d4`: `IID_IRdpPipeProtocol`
- `0x180047613`: `IID_IRdpPipeProtocol`
- `0x180046f03`: `BaseProtocolError_OnDataReceivedErrorState`
- `0x180046fd9`: `BaseProtocolError_OnDataReceivedNoDecoderListening`
- `0x180047035`: `BaseProtocolError_OnDataReceivedHeaderTooSmall`
- `0x1800470c7`: `BaseProtocolError_OnDataReceivedBadBufferSize`
- `0x180047124`: `BaseProtocolError_OnDataReceivedBadBufferSize`
- `0x1800471d2`: `BaseProtocolError_OnDataReceivedDecode`
- `0x180047204`: `BaseProtocolError_OnDataReceivedBadBufferSizeMulti`
- `0x18004726d`: `BaseProtocolError_OnDataReceivedBadBufferSizeMulti`
- `0x1800472ea`: `BaseProtocolError_OnDataReceivedAllocationFail`
- `0x1800473ff`: `BaseProtocolError_OnDataReceivedNoBuffer`
- `0x180047473`: `BaseProtocolError_OnDataReceivedBufferSizeWrong`
- `0x180047514`: `BaseProtocolError_OnDataReceivedBufferSizeWrongEnd`
- `0x1800475c7`: `BaseProtocolError_OnDataReceivedDecodeMulti`
- `0x1800473cc`: `BaseProtocolError_OnDataReceivedInvalidData`
- `0x180047606`: `BaseProtocolError_OnDataReceivedFail`

## pseudocode

```c
__int64 __fastcall CRdpPipeProtocol::OnDataReceived(CRdpPipeProtocol *this, unsigned int a2, unsigned __int8 *a3)
{
  __int64 v3; // rdi
  __int64 v4; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v9; // rdx
  int v10; // esi
  CRdpPipeProtocol *v11; // r15
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // r15d
  signed int v18; // eax
  void *v19; // rax
  void *v20; // rcx
  unsigned int v21; // eax
  __int64 v23; // rcx
  unsigned int v24; // r9d
  signed int v25; // eax
  unsigned int v26; // eax
  int v27; // [rsp+20h] [rbp-58h]

  v3 = 0;
  v4 = 0;
  if ( *((_DWORD *)this + 960) )
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_OnDataReceivedErrorState",
      (char *)0x5BB,
      0x80004005,
      v27);
  if ( *((_DWORD *)this + 960) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 84;
LABEL_8:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      &WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147024895);
LABEL_9:
    v10 = -2147024895;
LABEL_10:
    v11 = (CRdpPipeProtocol *)((char *)this - 8);
LABEL_109:
    operator delete(*((void **)this + 478));
    *((_QWORD *)this + 478) = 0;
    CRdpPipeProtocol::SetProtocolErrorState(v11, v10);
    goto LABEL_71;
  }
  CTSCriticalSection::Lock((CRdpPipeProtocol *)((char *)this + 704));
  v12 = *((_QWORD *)this + 19);
  if ( v12 )
  {
    v3 = *((_QWORD *)this + 19);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  }
  v13 = *((_QWORD *)this + 23);
  if ( v13 )
  {
    v4 = *((_QWORD *)this + 23);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  }
  if ( this != (CRdpPipeProtocol *)-704LL )
    CTSCriticalSection::UnLock((CRdpPipeProtocol *)((char *)this + 704));
  if ( !v3 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_OnDataReceivedNoDecoderListening",
      (char *)0x5C8,
      0x80004005,
      v27);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 85;
    goto LABEL_8;
  }
  if ( a2 < 8 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_OnDataReceivedHeaderTooSmall",
      (char *)0x5CF,
      0x80004005,
      v27);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_28;
    }
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 86;
LABEL_27:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      &WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids,
      v14,
      -2147024883);
LABEL_28:
    v10 = -2147024883;
    goto LABEL_10;
  }
  v16 = *((_DWORD *)a3 + 1) & 3;
  v17 = a2 - 8;
  if ( v16 != 3 )
  {
    if ( v16 == 1 )
    {
      if ( v17 >= *(_DWORD *)a3 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
          "BaseProtocolError_OnDataReceivedBadBufferSizeMulti",
          (char *)0x5FE,
          0x80004005,
          v27);
        if ( v17 >= *(_DWORD *)a3 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_28;
          }
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 89;
          goto LABEL_27;
        }
      }
      if ( *(_DWORD *)a3 > 0x103EEu )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
          "BaseProtocolError_OnDataReceivedBadBufferSizeMulti",
          (char *)0x605,
          0x80004005,
          v27);
        if ( *(_DWORD *)a3 > 0x103EEu )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_28;
          }
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 90;
          goto LABEL_27;
        }
      }
      operator delete(*((void **)this + 478));
      v19 = operator new(*(unsigned int *)a3);
      *((_QWORD *)this + 478) = v19;
      if ( !v19 )
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
          "BaseProtocolError_OnDataReceivedAllocationFail",
          (char *)0x60E,
          0x80004003,
          v27);
      v20 = (void *)*((_QWORD *)this + 478);
      if ( !v20 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            91,
            (unsigned int)&WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids,
            v21,
            (__int64)"UCHAR");
        }
        v10 = -2147024882;
        goto LABEL_10;
      }
      *((_DWORD *)this + 958) = *(_DWORD *)a3;
      memcpy_0(v20, a3 + 8, v17);
      *((_DWORD *)this + 959) = v17;
    }
    else
    {
      if ( !*((_QWORD *)this + 478) )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
          "BaseProtocolError_OnDataReceivedNoBuffer",
          (char *)0x621,
          0x80004005,
          v27);
        if ( !*((_QWORD *)this + 478) )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_28;
          }
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 92;
          goto LABEL_27;
        }
      }
      if ( v17 > *((_DWORD *)this + 958) - *((_DWORD *)this + 959) )
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
          "BaseProtocolError_OnDataReceivedBufferSizeWrong",
          (char *)0x62B,
          0x80004005,
          v27);
      v23 = *((unsigned int *)this + 959);
      if ( v17 > *((_DWORD *)this + 958) - (int)v23 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 93;
        goto LABEL_27;
      }
      memcpy_0((void *)(*((_QWORD *)this + 478) + v23), a3 + 8, v17);
      *((_DWORD *)this + 959) += v17;
      if ( (*((_DWORD *)a3 + 1) & 3) == 2 )
      {
        if ( *((_DWORD *)this + 958) != *((_DWORD *)this + 959) )
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
            "BaseProtocolError_OnDataReceivedBufferSizeWrongEnd",
            (char *)0x63B,
            0x80004005,
            v27);
        v24 = *((_DWORD *)this + 959);
        if ( *((_DWORD *)this + 958) != v24 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_28;
          }
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 94;
          goto LABEL_27;
        }
        if ( v4 )
          v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v4 + 24LL))(
                  v4,
                  v24,
                  *((_QWORD *)this + 478));
        else
          v25 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD))(*(_QWORD *)v3 + 32LL))(
                  v3,
                  ((unsigned __int64)this + 24) & -(__int64)(this != (CRdpPipeProtocol *)8),
                  *((_QWORD *)this + 478));
        v10 = v25;
        if ( v25 < 0 )
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
            "BaseProtocolError_OnDataReceivedDecodeMulti",
            (char *)0x64A,
            v25,
            v27);
        operator delete(*((void **)this + 478));
        *((_QWORD *)this + 478) = 0;
        if ( v10 < 0 )
        {
          v11 = (CRdpPipeProtocol *)((char *)this - 8);
          goto LABEL_104;
        }
      }
    }
LABEL_70:
    v10 = 0;
    goto LABEL_71;
  }
  if ( v17 != *(_DWORD *)a3 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_OnDataReceivedBadBufferSize",
      (char *)0x5DE,
      0x80004005,
      v27);
    if ( v17 != *(_DWORD *)a3 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_28;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 87;
      goto LABEL_27;
    }
  }
  if ( *(_DWORD *)a3 > 0x103EEu )
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
      "BaseProtocolError_OnDataReceivedBadBufferSize",
      (char *)0x5E5,
      0x80004005,
      v27);
  if ( *(_DWORD *)a3 > 0x103EEu )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_28;
    }
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 88;
    goto LABEL_27;
  }
  if ( v4 )
  {
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 *))(*(_QWORD *)v4 + 24LL))(
            v4,
            *(unsigned int *)a3,
            a3 + 8);
    v11 = (CRdpPipeProtocol *)((char *)this - 8);
  }
  else
  {
    v11 = (CRdpPipeProtocol *)((char *)this - 8);
    v18 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, unsigned __int8 *))(*(_QWORD *)v3 + 32LL))(
            v3,
            ((unsigned __int64)this + 24) & -(__int64)(this != (CRdpPipeProtocol *)8),
            a3 + 8);
  }
  v10 = v18;
  if ( v18 >= 0 )
    goto LABEL_70;
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
    "BaseProtocolError_OnDataReceivedDecode",
    (char *)0x5F4,
    v18,
    v27);
LABEL_104:
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    (RDPGraphicsTraceLogging *)"IID_IRdpPipeProtocol",
    "BaseProtocolError_OnDataReceivedFail",
    (char *)0x658,
    v10,
    v27);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v26 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids, v26, v10);
  }
  if ( v10 < 0 )
    goto LABEL_109;
LABEL_71:
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180046ed0  push    rbx
0x180046ed2  push    rbp
0x180046ed3  push    rsi
0x180046ed4  push    rdi
0x180046ed5  push    r12
0x180046ed7  push    r13
0x180046ed9  push    r14
0x180046edb  push    r15
0x180046edd  sub     rsp, 38h
0x180046ee1  xor     edi, edi
0x180046ee3  lea     r13, aIidIrdppipepro; "IID_IRdpPipeProtocol"
0x180046eea  xor     ebx, ebx
0x180046eec  mov     rsi, r8
0x180046eef  mov     r15d, edx
0x180046ef2  mov     rbp, rcx
0x180046ef5  cmp     [rcx+0F00h], ebx
0x180046efb  jz      short loc_180046F18
0x180046efd  mov     r9d, 80004005h; unsigned int
0x180046f03  lea     rdx, aBaseprotocoler_48; "BaseProtocolError_OnDataReceivedErrorSt"...
0x180046f0a  mov     r8d, 5BBh; char *
0x180046f10  mov     rcx, r13; this
0x180046f13  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180046f18  cmp     [rbp+0F00h], ebx
0x180046f1e  jz      short loc_180046F7C
0x180046f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180046f27  lea     rax, WPP_GLOBAL_Control
0x180046f2e  cmp     rcx, rax
0x180046f31  jz      short loc_180046F6E
0x180046f33  test    byte ptr [rcx+1Ch], 8
0x180046f37  jz      short loc_180046F6E
0x180046f39  mov     r14b, 2
0x180046f3c  cmp     [rcx+19h], r14b
0x180046f40  jb      short loc_180046F6E
0x180046f42  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046f47  mov     edx, 54h ; 'T'
0x180046f4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180046f53  lea     r8, WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids
0x180046f5a  mov     r9d, eax
0x180046f5d  mov     [rsp+78h+var_58], 80070001h
0x180046f65  mov     rcx, [rcx+10h]
0x180046f69  call    WPP_SF_Dd
0x180046f6e  mov     esi, 80070001h
0x180046f73  lea     r15, [rbp-8]
0x180046f77  jmp     loc_18004766E
0x180046f7c  lea     r14, [rbp+2C0h]
0x180046f83  mov     rcx, r14; this
0x180046f86  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180046f8b  mov     rcx, [rbp+98h]
0x180046f92  test    rcx, rcx
0x180046f95  jz      short loc_180046FA6
0x180046f97  mov     rax, [rcx]
0x180046f9a  mov     rdi, rcx
0x180046f9d  mov     rax, [rax+8]
0x180046fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fa6  mov     rcx, [rbp+0B8h]
0x180046fad  test    rcx, rcx
0x180046fb0  jz      short loc_180046FC1
0x180046fb2  mov     rax, [rcx]
0x180046fb5  mov     rbx, rcx
0x180046fb8  mov     rax, [rax+8]
0x180046fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fc1  test    r14, r14
0x180046fc4  jz      short loc_180046FCE
0x180046fc6  mov     rcx, r14; this
0x180046fc9  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x180046fce  test    rdi, rdi
0x180046fd1  jnz     short loc_180047029
0x180046fd3  mov     r9d, 80004005h; unsigned int
0x180046fd9  lea     rdx, aBaseprotocoler_8; "BaseProtocolError_OnDataReceivedNoDecod"...
0x180046fe0  mov     r8d, 5C8h; char *
0x180046fe6  mov     rcx, r13; this
0x180046fe9  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180046fee  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ff5  lea     rax, WPP_GLOBAL_Control
0x180046ffc  cmp     rcx, rax
0x180046fff  jz      loc_180046F6E
0x180047005  test    byte ptr [rcx+1Ch], 8
0x180047009  jz      loc_180046F6E
0x18004700f  mov     r14b, 2
0x180047012  cmp     [rcx+19h], r14b
0x180047016  jb      loc_180046F6E
0x18004701c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180047021  lea     edx, [rdi+55h]
0x180047024  jmp     loc_180046F4C
0x180047029  cmp     r15d, 8
0x18004702d  jnb     short loc_1800470A2
0x18004702f  mov     r9d, 80004005h; unsigned int
0x180047035  lea     rdx, aBaseprotocoler_9; "BaseProtocolError_OnDataReceivedHeaderT"...
0x18004703c  mov     r8d, 5CFh; char *
0x180047042  mov     rcx, r13; this
0x180047045  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18004704a  mov     rcx, cs:WPP_GLOBAL_Control
0x180047051  lea     rax, WPP_GLOBAL_Control
0x180047058  cmp     rcx, rax
0x18004705b  jz      short loc_180047098
0x18004705d  test    byte ptr [rcx+1Ch], 8
0x180047061  jz      short loc_180047098
0x180047063  mov     r14b, 2
0x180047066  cmp     [rcx+19h], r14b
0x18004706a  jb      short loc_180047098
0x18004706c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180047071  mov     edx, 56h ; 'V'
0x180047076  mov     rcx, cs:WPP_GLOBAL_Control
0x18004707d  lea     r8, WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids
0x180047084  mov     r9d, eax
0x180047087  mov     [rsp+78h+var_58], 8007000Dh
0x18004708f  mov     rcx, [rcx+10h]
0x180047093  call    WPP_SF_Dd
0x180047098  mov     esi, 8007000Dh
0x18004709d  jmp     loc_180046F73
0x1800470a2  mov     eax, [rsi+4]
0x1800470a5  lea     r13, [rsi+8]
0x1800470a9  and     eax, 3
0x1800470ac  add     r15d, 0FFFFFFF8h
0x1800470b0  mov     r14b, 2
0x1800470b3  cmp     eax, 3
0x1800470b6  jnz     loc_1800471F0
0x1800470bc  cmp     r15d, [rsi]
0x1800470bf  jz      short loc_180047113
0x1800470c1  mov     r9d, 80004005h; unsigned int
0x1800470c7  lea     rdx, aBaseprotocoler_44; "BaseProtocolError_OnDataReceivedBadBuff"...
0x1800470ce  mov     r8d, 5DEh; char *
0x1800470d4  lea     rcx, aIidIrdppipepro; "IID_IRdpPipeProtocol"
0x1800470db  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800470e0  cmp     r15d, [rsi]
0x1800470e3  jz      short loc_180047113
0x1800470e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800470ec  lea     rax, WPP_GLOBAL_Control
0x1800470f3  cmp     rcx, rax
0x1800470f6  jz      short loc_180047098
0x1800470f8  test    byte ptr [rcx+1Ch], 8
0x1800470fc  jz      short loc_180047098
0x1800470fe  cmp     [rcx+19h], r14b
0x180047102  jb      short loc_180047098
0x180047104  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180047109  mov     edx, 57h ; 'W'
0x18004710e  jmp     loc_180047076
0x180047113  mov     r12d, 103EEh
0x180047119  cmp     [rsi], r12d
0x18004711c  jbe     short loc_18004713D
0x18004711e  mov     r9d, 80004005h; unsigned int
0x180047124  lea     rdx, aBaseprotocoler_44; "BaseProtocolError_OnDataReceivedBadBuff"...
0x18004712b  mov     r8d, 5E5h; char *
0x180047131  lea     rcx, aIidIrdppipepro; "IID_IRdpPipeProtocol"
0x180047138  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18004713d  mov     r9d, [rsi]
0x180047140  cmp     r9d, r12d
0x180047143  jbe     short loc_18004717F
0x180047145  mov     rcx, cs:WPP_GLOBAL_Control
0x18004714c  lea     rax, WPP_GLOBAL_Control
0x180047153  cmp     rcx, rax
0x180047156  jz      loc_180047098
0x18004715c  test    byte ptr [rcx+1Ch], 8
0x180047160  jz      loc_180047098
0x180047166  cmp     [rcx+19h], r14b
0x18004716a  jb      loc_180047098
0x180047170  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180047175  mov     edx, 58h ; 'X'
0x18004717a  jmp     loc_180047076
0x18004717f  test    rbx, rbx
0x180047182  jz      short loc_18004719F
0x180047184  mov     rax, [rbx]
0x180047187  mov     r8, r13
0x18004718a  mov     edx, r9d
0x18004718d  mov     rcx, rbx
0x180047190  mov     rax, [rax+18h]
0x180047194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047199  lea     r15, [rbp-8]
0x18004719d  jmp     short loc_1800471C5
0x18004719f  mov     r8, [rdi]
0x1800471a2  lea     rcx, [rbp+18h]
0x1800471a6  lea     r15, [rbp-8]
0x1800471aa  mov     rax, r15
0x1800471ad  neg     rax
0x1800471b0  mov     rax, [r8+20h]
0x1800471b4  mov     r8, r13
0x1800471b7  sbb     rdx, rdx
0x1800471ba  and     rdx, rcx
0x1800471bd  mov     rcx, rdi
0x1800471c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471c5  mov     esi, eax
0x1800471c7  test    eax, eax
0x1800471c9  jns     loc_180047382
0x1800471cf  mov     r9d, eax; unsigned int
0x1800471d2  lea     rdx, aBaseprotocoler_28; "BaseProtocolError_OnDataReceivedDecode"
0x1800471d9  mov     r8d, 5F4h; char *
0x1800471df  lea     rcx, aIidIrdppipepro; "IID_IRdpPipeProtocol"
0x1800471e6  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800471eb  jmp     loc_180047603
0x1800471f0  cmp     eax, 1
0x1800471f3  jnz     loc_1800473BF
0x1800471f9  cmp     r15d, [rsi]
0x1800471fc  jb      short loc_18004725C
0x1800471fe  mov     r9d, 80004005h; unsigned int
0x180047204  lea     rdx, aBaseprotocoler_2; "BaseProtocolError_OnDataReceivedBadBuff"...
0x18004720b  mov     r8d, 5FEh; char *
0x180047211  lea     rcx, aIidIrdppipepro; "IID_IRdpPipeProtocol"
0x180047218  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18004721d  cmp     r15d, [rsi]
0x180047220  jb      short loc_18004725C
0x180047222  mov     rcx, cs:WPP_GLOBAL_Control
0x180047229  lea     rax, WPP_GLOBAL_Control
0x180047230  cmp     rcx, rax
0x180047233  jz      loc_180047098
0x180047239  test    byte ptr [rcx+1Ch], 8
0x18004723d  jz      loc_180047098
0x180047243  cmp     [rcx+19h], r14b
0x180047247  jb      loc_180047098
0x18004724d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180047252  mov     edx, 59h ; 'Y'
0x180047257  jmp     loc_180047076
0x18004725c  mov     r12d, 103EEh
0x180047262  cmp     [rsi], r12d
0x180047265  jbe     short loc_1800472C5
0x180047267  mov     r9d, 80004005h; unsigned int
0x18004726d  lea     rdx, aBaseprotocoler_2; "BaseProtocolError_OnDataReceivedBadBuff"...
0x180047274  mov     r8d, 605h; char *
0x18004727a  lea     rcx, aIidIrdppipepro; "IID_IRdpPipeProtocol"
0x180047281  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180047286  cmp     [rsi], r12d
0x180047289  jbe     short loc_1800472C5
0x18004728b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047292  lea     rax, WPP_GLOBAL_Control
0x180047299  cmp     rcx, rax
0x18004729c  jz      loc_180047098
0x1800472a2  test    byte ptr [rcx+1Ch], 8
0x1800472a6  jz      loc_180047098
0x1800472ac  cmp     [rcx+19h], r14b
0x1800472b0  jb      loc_180047098
0x1800472b6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800472bb  mov     edx, 5Ah ; 'Z'
0x1800472c0  jmp     loc_180047076
0x1800472c5  mov     rcx, [rbp+0EF0h]; Block
0x1800472cc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800472d1  mov     ecx, [rsi]; Size
0x1800472d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800472d8  mov     [rbp+0EF0h], rax
0x1800472df  test    rax, rax
0x1800472e2  jnz     short loc_180047303
0x1800472e4  mov     r9d, 80004003h; unsigned int
0x1800472ea  lea     rdx, aBaseprotocoler_45; "BaseProtocolError_OnDataReceivedAllocat"...
0x1800472f1  mov     r8d, 60Eh; char *
0x1800472f7  lea     rcx, aIidIrdppipepro; "IID_IRdpPipeProtocol"
0x1800472fe  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180047303  mov     rcx, [rbp+0EF0h]; void *
0x18004730a  test    rcx, rcx
0x18004730d  jnz     short loc_180047368
0x18004730f  mov     rcx, cs:WPP_GLOBAL_Control
0x180047316  lea     rax, WPP_GLOBAL_Control
0x18004731d  cmp     rcx, rax
0x180047320  jz      short loc_18004735E
0x180047322  test    byte ptr [rcx+1Ch], 8
0x180047326  jz      short loc_18004735E
0x180047328  cmp     [rcx+19h], r14b
0x18004732c  jb      short loc_18004735E
0x18004732e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180047333  lea     rcx, aUchar; "UCHAR"
0x18004733a  mov     edx, 5Bh ; '['
0x18004733f  mov     qword ptr [rsp+78h+var_58], rcx
0x180047344  lea     r8, WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids
0x18004734b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047352  mov     r9d, eax
0x180047355  mov     rcx, [rcx+10h]
0x180047359  call    WPP_SF_Ds
0x18004735e  mov     esi, 8007000Eh
0x180047363  jmp     loc_180046F73
0x180047368  mov     eax, [rsi]
0x18004736a  mov     rdx, r13; Src
0x18004736d  mov     r8d, r15d; Size
0x180047370  mov     [rbp+0EF8h], eax
0x180047376  call    memcpy_0
0x18004737b  mov     [rbp+0EFCh], r15d
0x180047382  xor     esi, esi
0x180047384  test    rbx, rbx
0x180047387  jz      short loc_180047398
0x180047389  mov     rax, [rbx]
0x18004738c  mov     rcx, rbx
0x18004738f  mov     rax, [rax+10h]
0x180047393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047398  test    rdi, rdi
0x18004739b  jz      short loc_1800473AC
0x18004739d  mov     rcx, [rdi]
0x1800473a0  mov     rax, [rcx+10h]
0x1800473a4  mov     rcx, rdi
0x1800473a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473ac  mov     eax, esi
0x1800473ae  add     rsp, 38h
0x1800473b2  pop     r15
0x1800473b4  pop     r14
0x1800473b6  pop     r13
0x1800473b8  pop     r12
0x1800473ba  pop     rdi
0x1800473bb  pop     rsi
0x1800473bc  pop     rbp
0x1800473bd  pop     rbx
0x1800473be  retn
0x1800473bf  test    eax, 0FFFFFFFDh
0x1800473c4  jz      short loc_1800473EF
0x1800473c6  mov     r9d, 80004005h; unsigned int
0x1800473cc  lea     rdx, aBaseprotocoler_32; "BaseProtocolError_OnDataReceivedInvalid"...
  ... truncated ...
```
