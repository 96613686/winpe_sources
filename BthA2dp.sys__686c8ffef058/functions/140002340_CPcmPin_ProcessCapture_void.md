# CPcmPin::ProcessCapture(void)

- ea: `0x140002340`
- end: `0x140002c62`
- name: `?ProcessCapture@CPcmPin@@AEAAJXZ`
- size: `2338`
- prototype: `__int64 __fastcall(CPcmPin *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting`

## callers

- `0x1400030d0`
- `0x140003a20`

## callees

- `0x14000132c`
- `0x1400017a4`
- `0x1400017f4`
- `0x140001890`
- `0x14000192c`
- `0x1400019d4`
- `0x140002340`
- `0x140003530`
- `0x140005a50`
- `0x140006380`
- `0x140006410`
- `0x14000700c`
- `0x14000f570`
- `0x140014788`
- `0x140014d0c`
- `0x14001bbc4`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x14000237e`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x14000237e`
- `ks!KsStreamPointerAdvance` at `0x1400024ce`
- `ks!KsStreamPointerAdvance` at `0x1400024ce`
- `ks!KsStreamPointerAdvanceOffsets` at `0x140002a40`
- `ks!KsStreamPointerAdvanceOffsets` at `0x140002a40`
- `ks!KsStreamPointerDelete` at `0x14000275e`
- `ks!KsStreamPointerDelete` at `0x14000275e`
- `ks!KsPinGetFirstCloneStreamPointer` at `0x140002391`
- `ks!KsPinGetFirstCloneStreamPointer` at `0x1400028ea`
- `ks!KsPinGetFirstCloneStreamPointer` at `0x140002391`
- `ks!KsPinGetFirstCloneStreamPointer` at `0x1400028ea`
- `ks!KsPinReleaseProcessingMutex` at `0x140002c3e`
- `ks!KsPinReleaseProcessingMutex` at `0x140002c3e`
- `ks!KsPinAcquireProcessingMutex` at `0x140002360`
- `ks!KsPinAcquireProcessingMutex` at `0x140002360`

## pseudocode

```c
__int64 __fastcall CPcmPin::ProcessCapture(CPcmPin *this)
{
  unsigned __int64 v2; // r15
  int v3; // edx
  int v4; // r8d
  PKSSTREAM_POINTER FirstCloneStreamPointer; // r14
  bool v6; // di
  NTSTATUS v7; // r13d
  _UNKNOWN **v8; // r8
  _UNKNOWN **v9; // r8
  __int64 v10; // rcx
  __int64 CurrentSelectedCodec; // rax
  utl::_RefCountBase *v12; // r12
  int v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // r12d
  A2dpRole *v16; // rcx
  char v17; // r9
  unsigned int v18; // eax
  __int64 v19; // r8
  __int16 v20; // r10
  unsigned int v21; // r9d
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  PKSSTREAM_HEADER StreamHeader; // r8
  __int64 v25; // rdx
  unsigned __int64 v26; // r12
  __int64 v27; // r8
  int v28; // r9d
  __int64 v29; // rcx
  int v30; // r8d
  int v31; // r9d
  unsigned __int64 v32; // rcx
  _UNKNOWN **v33; // r8
  int v34; // r8d
  int v35; // r9d
  unsigned int v36; // eax
  __int64 v37; // r8
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // r8
  int v41; // r9d
  unsigned __int64 v42; // rcx
  __int64 v43; // rcx
  unsigned __int64 v45; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int64 v46; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int64 v47; // [rsp+60h] [rbp-39h] BYREF
  utl::_RefCountBase *v48[2]; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int64 v49; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int64 v50; // [rsp+80h] [rbp-19h] BYREF
  __int64 v51; // [rsp+88h] [rbp-11h] BYREF
  PKSPIN Pin; // [rsp+90h] [rbp-9h]
  _BYTE v53[8]; // [rsp+98h] [rbp-1h] BYREF
  utl::_RefCountBase *v54; // [rsp+A0h] [rbp+7h]
  unsigned __int64 OutUsed; // [rsp+100h] [rbp+67h] BYREF
  unsigned __int64 v56; // [rsp+108h] [rbp+6Fh] BYREF
  unsigned __int64 v57; // [rsp+110h] [rbp+77h] BYREF
  __int64 v58; // [rsp+118h] [rbp+7Fh] BYREF

  KsPinAcquireProcessingMutex(*((PKSPIN *)this + 2));
  Pin = (PKSPIN)*((_QWORD *)this + 2);
  v58 = 0;
  v2 = KeQueryInterruptTimePrecise(&v58);
  FirstCloneStreamPointer = KsPinGetFirstCloneStreamPointer(*((PKSPIN *)this + 2));
  if ( FirstCloneStreamPointer )
  {
    v7 = 0;
    while ( 1 )
    {
      v8 = &WPP_RECORDER_INITIALIZED;
      if ( !FirstCloneStreamPointer )
        goto LABEL_94;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || (LOBYTE(v3) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
      {
        LOBYTE(v3) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (LOBYTE(v8) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v8) = 0;
      }
      if ( (_BYTE)v3 || (_BYTE)v8 )
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v3,
          (_DWORD)v8,
          WPP_GLOBAL_Control->DeviceExtension,
          5,
          5,
          45,
          (__int64)WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids,
          (char)FirstCloneStreamPointer);
      if ( !FirstCloneStreamPointer->StreamHeader->Data )
      {
        v7 = KsStreamPointerAdvance(FirstCloneStreamPointer);
        LOBYTE(v3) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
        v9 = &WPP_RECORDER_INITIALIZED;
        if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v3,
            (_DWORD)v9,
            WPP_GLOBAL_Control->DeviceExtension,
            3,
            5,
            46,
            (__int64)WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids);
        }
        goto LABEL_60;
      }
      v10 = *((_QWORD *)this + 4);
      *(_OWORD *)v48 = 0;
      if ( !v10 )
        goto LABEL_91;
      CurrentSelectedCodec = A2dpRole::GetCurrentSelectedCodec(*(_QWORD *)(v10 + 8), v53);
      utl::shared_ptr<A2dpAudioCodec>::operator=(v48, CurrentSelectedCodec);
      if ( v54 )
        utl::_RefCountBase::_DecStrong(v54);
      v12 = v48[0];
      if ( !v48[0] )
      {
LABEL_91:
        v7 = -1073741300;
LABEL_92:
        if ( v48[1] )
          utl::_RefCountBase::_DecStrong(v48[1]);
        goto LABEL_94;
      }
      v13 = (*(__int64 (__fastcall **)(utl::_RefCountBase *))(*(_QWORD *)v48[0] + 96LL))(v48[0]);
      v14 = *(_QWORD *)v12;
      LODWORD(v56) = v13;
      v15 = 2 * (*(__int64 (__fastcall **)(utl::_RefCountBase *))(v14 + 104))(v12);
      v16 = *(A2dpRole **)(*((_QWORD *)this + 4) + 8LL);
      v17 = *((_BYTE *)this + 216) == 0;
      LODWORD(v57) = v15;
      v18 = A2dpRole::CaptureAudio(v16, FirstCloneStreamPointer, v2, v17);
      v20 = 0;
      LODWORD(OutUsed) = v18;
      v21 = v18;
      if ( !v18 )
        goto LABEL_41;
      if ( !*((_BYTE *)this + 216) )
        break;
LABEL_42:
      StreamHeader = FirstCloneStreamPointer->StreamHeader;
      v25 = *((unsigned int *)this + 52) * (StreamHeader->PresentationTime.Time - *((_QWORD *)this + 25))
          % *((unsigned int *)this + 53);
      v26 = StreamHeader->Duration
          + *((unsigned int *)this + 52)
          * (StreamHeader->PresentationTime.Time - *((_QWORD *)this + 25))
          / *((unsigned int *)this + 53)
          + *((_QWORD *)this + 24);
      if ( v21 != FirstCloneStreamPointer->Offset->Remaining )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
          || (LOBYTE(v25) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
        {
          LOBYTE(v25) = v20;
        }
        v33 = &WPP_RECORDER_INITIALIZED;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          || (LOBYTE(v33) = 1, LOWORD(WPP_GLOBAL_Control->DeviceType) == v20) )
        {
          LOBYTE(v33) = v20;
        }
        if ( (_BYTE)v25 || (_BYTE)v33 )
          WPP_RECORDER_AND_TRACE_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            v25,
            (_DWORD)v33,
            WPP_GLOBAL_Control->DeviceExtension,
            5,
            5,
            47,
            (__int64)WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids,
            (char)FirstCloneStreamPointer,
            v21);
        if ( (unsigned int)dword_14006F0F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 1, v33) )
        {
          v36 = FirstCloneStreamPointer->Offset->Remaining / (unsigned int)v57;
          v45 = (unsigned __int64)FirstCloneStreamPointer;
          LODWORD(v56) = v36;
          v57 = v26 / 0x2710;
          v46 = v2 / 0x2710;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            948328779,
            (unsigned int)byte_140069E0B,
            v34,
            v35,
            (__int64)&v45,
            (__int64)&v46,
            (__int64)&v57,
            (__int64)&v56);
        }
        v7 = KsStreamPointerAdvanceOffsets(FirstCloneStreamPointer, 0, OutUsed, 0);
        if ( v26 <= v2 )
        {
          if ( (unsigned int)dword_14006F0F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 1, v37) )
          {
            OutUsed = v26 / 0x2710;
            v56 = v2 / 0x2710;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              948328779,
              (unsigned int)&word_140069DCE,
              v38,
              v39,
              (__int64)&v56,
              (__int64)&OutUsed);
          }
          if ( *((_BYTE *)this + 216) )
            *((_BYTE *)this + 216) = 0;
          CPcmPin::SetTimer(this, 200000);
          ++*((_QWORD *)this + 22);
          if ( v2 - *((_QWORD *)this + 21) > 0x5F5E100 )
          {
            if ( (unsigned int)dword_14006F0F8 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 0x400000000001LL, v40) )
            {
              OutUsed = *(_QWORD *)(*((_QWORD *)this + 4) + 720LL);
              v42 = *((_QWORD *)this + 22);
              v56 = (v2 - *((_QWORD *)this + 21)) / 0x2710;
              v57 = v42;
              v46 = v26 / 0x2710;
              v47 = 50333696;
              v45 = v2 / 0x2710;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                v42,
                (unsigned int)byte_140069D2D,
                948328779,
                v41,
                (__int64)&v47,
                (__int64)&v45,
                (__int64)&v46,
                (__int64)&v57,
                (__int64)&v56,
                (__int64)&OutUsed);
            }
            *((_QWORD *)this + 21) = v2;
            *((_QWORD *)this + 22) = 0;
          }
        }
        else
        {
          CPcmPin::SetTimer(this, v26 - v2);
        }
        goto LABEL_92;
      }
      KsStreamPointerDelete(FirstCloneStreamPointer);
      if ( (unsigned int)dword_14006F0F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 1, v27) )
      {
        v57 = (unsigned __int64)FirstCloneStreamPointer;
        OutUsed = v26 / 0x2710;
        v56 = v2 / 0x2710;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          948328779,
          (unsigned int)byte_140069F03,
          v27,
          v28,
          (__int64)&v57,
          (__int64)&v56,
          (__int64)&OutUsed);
      }
      if ( v26 > v2 )
      {
        if ( (unsigned int)dword_14006F0F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 1, v27) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v29,
            word_140069EDA);
        if ( *((_BYTE *)this + 216) )
          *((_BYTE *)this + 216) = 0;
        ++*((_QWORD *)this + 20);
        if ( v2 - *((_QWORD *)this + 19) > 0x5F5E100 )
        {
          if ( (unsigned int)dword_14006F0F8 > 5
            && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 0x400000000001LL, v27) )
          {
            v51 = *(_QWORD *)(*((_QWORD *)this + 4) + 720LL);
            v32 = v2 - *((_QWORD *)this + 19);
            v45 = *((_QWORD *)this + 20);
            v47 = v32 / 0x2710;
            v46 = 33556480;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              v32,
              (unsigned int)&dword_140069E5C,
              v30,
              v31,
              (__int64)&v46,
              (__int64)&v45,
              (__int64)&v47,
              (__int64)&v51);
          }
          *((_QWORD *)this + 19) = v2;
          *((_QWORD *)this + 20) = 0;
        }
      }
      FirstCloneStreamPointer = KsPinGetFirstCloneStreamPointer(*((PKSPIN *)this + 2));
      if ( !*((_BYTE *)this + 216) )
      {
LABEL_87:
        if ( (unsigned int)dword_14006F0F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 1, v19) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v43,
            &byte_140069CFF);
        CPcmPin::SetTimer(this, 200000);
        v7 = 259;
        goto LABEL_92;
      }
      if ( v48[1] )
        utl::_RefCountBase::_DecStrong(v48[1]);
LABEL_60:
      if ( v7 < 0 )
        goto LABEL_94;
    }
    *(KSTIME *)((char *)this + 200) = FirstCloneStreamPointer->StreamHeader->PresentationTime;
    v22 = 10000000 * (unsigned __int64)(v18 / v15) / (int)v56;
    *((_BYTE *)this + 216) = 1;
    *((_QWORD *)this + 24) = v2 - v22;
    *((_QWORD *)this + 25) += (FirstCloneStreamPointer->Offset->Count - FirstCloneStreamPointer->Offset->Remaining)
                            / v15;
    if ( (unsigned int)dword_14006F0F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 1, v19) )
    {
      v23 = *((_QWORD *)this + 25) * *((unsigned int *)this + 52) / (__int64)*((unsigned int *)this + 53);
      v56 = v23 / 10000;
      v49 = *((_QWORD *)this + 24) / 0x2710uLL;
      v50 = v2 / 0x2710;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v23,
        (unsigned int)byte_140069F43,
        948328779,
        v21,
        (__int64)&v50,
        (__int64)&v49,
        (__int64)&v56);
      v21 = OutUsed;
      v20 = 0;
    }
LABEL_41:
    if ( *((_BYTE *)this + 216) == (_BYTE)v20 )
      goto LABEL_87;
    goto LABEL_42;
  }
  v6 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = v6;
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      v4,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      44,
      (__int64)WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids);
  }
  v7 = 259;
LABEL_94:
  KsPinReleaseProcessingMutex(Pin);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140002340  push    rbp
0x140002342  push    rbx
0x140002343  push    rsi
0x140002344  push    rdi
0x140002345  push    r12
0x140002347  push    r13
0x140002349  push    r14
0x14000234b  push    r15
0x14000234d  lea     rbp, [rsp-1Fh]
0x140002352  sub     rsp, 0B8h
0x140002359  mov     rbx, rcx
0x14000235c  mov     rcx, [rcx+10h]; Pin
0x140002360  call    cs:__imp_KsPinAcquireProcessingMutex
0x140002367  nop     dword ptr [rax+rax+00h]
0x14000236c  mov     rax, [rbx+10h]
0x140002370  lea     rcx, [rbp+57h+arg_18]
0x140002374  xor     edx, edx
0x140002376  mov     [rbp+57h+Pin], rax
0x14000237a  mov     [rbp+57h+arg_18], rdx
0x14000237e  call    cs:__imp_KeQueryInterruptTimePrecise
0x140002385  nop     dword ptr [rax+rax+00h]
0x14000238a  mov     rcx, [rbx+10h]; Pin
0x14000238e  mov     r15, rax
0x140002391  call    cs:__imp_KsPinGetFirstCloneStreamPointer
0x140002398  nop     dword ptr [rax+rax+00h]
0x14000239d  xor     r10d, r10d
0x1400023a0  mov     r14, rax
0x1400023a3  test    rax, rax
0x1400023a6  jnz     loc_14000242C
0x1400023ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023b3  lea     rax, WPP_GLOBAL_Control
0x1400023ba  cmp     rcx, rax
0x1400023bd  jz      short loc_1400023D2
0x1400023bf  mov     eax, [rcx+2Ch]
0x1400023c2  test    al, 10h
0x1400023c4  jz      short loc_1400023D2
0x1400023c6  cmp     byte ptr [rcx+29h], 4
0x1400023ca  jb      short loc_1400023D2
0x1400023cc  lea     edi, [r14+1]
0x1400023d0  jmp     short loc_1400023D5
0x1400023d2  mov     dil, r10b
0x1400023d5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400023dc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400023e3  setnz   r8b
0x1400023e7  test    dil, dil
0x1400023ea  jnz     short loc_1400023F1
0x1400023ec  test    r8b, r8b
0x1400023ef  jz      short loc_140002421
0x1400023f1  mov     r9, [rcx+40h]
0x1400023f5  lea     rax, WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids
0x1400023fc  mov     rcx, [rcx+18h]
0x140002400  mov     dl, dil
0x140002403  mov     [rsp+0F0h+var_B8], rax
0x140002408  mov     word ptr [rsp+0F0h+var_C0], 2Ch ; ','
0x14000240f  mov     dword ptr [rsp+0F0h+var_C8], 5
0x140002417  mov     byte ptr [rsp+0F0h+var_D0], 4
0x14000241c  call    WPP_RECORDER_AND_TRACE_SF_
0x140002421  mov     r13d, 103h
0x140002427  jmp     loc_140002C3A
0x14000242c  mov     edi, 1
0x140002431  lea     r12, WPP_GLOBAL_Control
0x140002438  mov     r13d, r10d
0x14000243b  lea     esi, [rdi+4]
0x14000243e  lea     r9, WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids
0x140002445  lea     r8, WPP_RECORDER_INITIALIZED
0x14000244c  test    r14, r14
0x14000244f  jz      loc_140002C3A
0x140002455  mov     rcx, cs:WPP_GLOBAL_Control
0x14000245c  cmp     rcx, r12
0x14000245f  jz      short loc_140002471
0x140002461  mov     eax, [rcx+2Ch]
0x140002464  test    al, 10h
0x140002466  jz      short loc_140002471
0x140002468  mov     dl, dil
0x14000246b  cmp     [rcx+29h], sil
0x14000246f  jnb     short loc_140002474
0x140002471  mov     dl, r10b
0x140002474  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x14000247b  jz      short loc_140002487
0x14000247d  mov     r8b, dil
0x140002480  cmp     [rcx+48h], r10w
0x140002485  jnz     short loc_14000248A
0x140002487  mov     r8b, r10b
0x14000248a  test    dl, dl
0x14000248c  jnz     short loc_140002493
0x14000248e  test    r8b, r8b
0x140002491  jz      short loc_1400024BD
0x140002493  mov     [rsp+0F0h+var_B0], r14
0x140002498  mov     [rsp+0F0h+var_B8], r9
0x14000249d  mov     r9, [rcx+40h]
0x1400024a1  mov     rcx, [rcx+18h]
0x1400024a5  mov     word ptr [rsp+0F0h+var_C0], 2Dh ; '-'
0x1400024ac  mov     dword ptr [rsp+0F0h+var_C8], esi
0x1400024b0  mov     byte ptr [rsp+0F0h+var_D0], sil
0x1400024b5  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400024ba  xor     r10d, r10d
0x1400024bd  mov     rax, [r14+10h]
0x1400024c1  cmp     [rax+28h], r10
0x1400024c5  jnz     loc_140002555
0x1400024cb  mov     rcx, r14; StreamPointer
0x1400024ce  call    cs:__imp_KsStreamPointerAdvance
0x1400024d5  nop     dword ptr [rax+rax+00h]
0x1400024da  mov     r13d, eax
0x1400024dd  mov     rax, cs:WPP_GLOBAL_Control
0x1400024e4  cmp     rax, r12
0x1400024e7  jz      short loc_1400024FF
0x1400024e9  mov     ecx, [rax+2Ch]
0x1400024ec  test    cl, 10h
0x1400024ef  jz      short loc_1400024FF
0x1400024f1  cmp     byte ptr [rax+29h], 3
0x1400024f5  jb      short loc_1400024FF
0x1400024f7  mov     dl, dil
0x1400024fa  xor     r10d, r10d
0x1400024fd  jmp     short loc_140002505
0x1400024ff  xor     r10d, r10d
0x140002502  mov     dl, r10b
0x140002505  lea     r8, WPP_RECORDER_INITIALIZED
0x14000250c  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140002513  setnz   r8b
0x140002517  test    dl, dl
0x140002519  jnz     short loc_140002524
0x14000251b  test    r8b, r8b
0x14000251e  jz      loc_140002921
0x140002524  mov     rcx, [rax+18h]
0x140002528  lea     r9, WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids
0x14000252f  mov     [rsp+0F0h+var_B8], r9
0x140002534  mov     r9, [rax+40h]
0x140002538  mov     word ptr [rsp+0F0h+var_C0], 2Eh ; '.'
0x14000253f  mov     dword ptr [rsp+0F0h+var_C8], esi
0x140002543  mov     byte ptr [rsp+0F0h+var_D0], 3
0x140002548  call    WPP_RECORDER_AND_TRACE_SF_
0x14000254d  xor     r10d, r10d
0x140002550  jmp     loc_140002921
0x140002555  mov     rcx, [rbx+20h]
0x140002559  xorps   xmm0, xmm0
0x14000255c  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x140002561  test    rcx, rcx
0x140002564  jz      loc_140002C26
0x14000256a  mov     rcx, [rcx+8]
0x14000256e  lea     rdx, [rbp+57h+var_58]
0x140002572  call    ?GetCurrentSelectedCodec@A2dpRole@@QEBA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@XZ; A2dpRole::GetCurrentSelectedCodec(void)
0x140002577  mov     rdx, rax
0x14000257a  lea     rcx, [rbp+57h+var_88]
0x14000257e  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> &&)
0x140002583  mov     rcx, [rbp+57h+var_50]; this
0x140002587  test    rcx, rcx
0x14000258a  jz      short loc_140002591
0x14000258c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140002591  mov     r12, [rbp+57h+var_88]
0x140002595  test    r12, r12
0x140002598  jz      loc_140002C26
0x14000259e  mov     rax, [r12]
0x1400025a2  mov     rcx, r12
0x1400025a5  mov     rax, [rax+60h]
0x1400025a9  call    _guard_dispatch_icall
0x1400025ae  mov     rdx, [r12]
0x1400025b2  mov     rcx, r12
0x1400025b5  mov     dword ptr [rbp+57h+arg_8], eax
0x1400025b8  mov     rax, [rdx+68h]
0x1400025bc  call    _guard_dispatch_icall
0x1400025c1  mov     rcx, [rbx+20h]
0x1400025c5  xor     edx, edx
0x1400025c7  mov     r12d, eax
0x1400025ca  mov     r8, r15; unsigned __int64
0x1400025cd  add     r12d, r12d
0x1400025d0  cmp     [rbx+0D8h], dl
0x1400025d6  mov     rdx, r14; struct _KSSTREAM_POINTER *
0x1400025d9  mov     rcx, [rcx+8]; this
0x1400025dd  setz    r9b; bool
0x1400025e1  mov     dword ptr [rbp+57h+arg_10], r12d
0x1400025e5  call    ?CaptureAudio@A2dpRole@@QEAAKPEAU_KSSTREAM_POINTER@@_K_N@Z; A2dpRole::CaptureAudio(_KSSTREAM_POINTER *,unsigned __int64,bool)
0x1400025ea  xor     r10d, r10d
0x1400025ed  mov     dword ptr [rbp+57h+OutUsed], eax
0x1400025f0  mov     r9d, eax
0x1400025f3  test    eax, eax
0x1400025f5  jz      loc_14000270E
0x1400025fb  cmp     [rbx+0D8h], r10b
0x140002602  jnz     loc_14000271B
0x140002608  mov     rcx, [r14+10h]
0x14000260c  xor     edx, edx
0x14000260e  div     r12d
0x140002611  movups  xmm0, xmmword ptr [rcx+8]
0x140002615  mov     ecx, eax
0x140002617  xor     edx, edx
0x140002619  imul    rax, rcx, 989680h
0x140002620  movdqu  xmmword ptr [rbx+0C8h], xmm0
0x140002628  movsxd  rcx, dword ptr [rbp+57h+arg_8]
0x14000262c  div     rcx
0x14000262f  mov     [rbx+0D8h], dil
0x140002636  xor     edx, edx
0x140002638  mov     rcx, r15
0x14000263b  sub     rcx, rax
0x14000263e  mov     [rbx+0C0h], rcx
0x140002645  mov     rax, [r14+18h]
0x140002649  mov     ecx, [rax+0Ch]
0x14000264c  mov     eax, [rax+8]
0x14000264f  sub     eax, ecx
0x140002651  div     r12d
0x140002654  mov     ecx, eax
0x140002656  add     [rbx+0C8h], rcx
0x14000265d  mov     eax, cs:dword_14006F0F8
0x140002663  cmp     eax, esi
0x140002665  jbe     loc_14000270E
0x14000266b  mov     rdx, rdi
0x14000266e  lea     rcx, dword_14006F0F8
0x140002675  call    _tlgKeywordOn
0x14000267a  test    al, al
0x14000267c  jz      loc_14000270E
0x140002682  mov     ecx, [rbx+0D4h]
0x140002688  mov     r8, 346DC5D63886594Bh
0x140002692  mov     eax, [rbx+0D0h]
0x140002698  imul    rax, [rbx+0C8h]
0x1400026a0  cqo
0x1400026a2  idiv    rcx
0x1400026a5  mov     rcx, rax
0x1400026a8  mov     rax, r8
0x1400026ab  imul    rcx
0x1400026ae  sar     rdx, 0Bh
0x1400026b2  mov     rax, rdx
0x1400026b5  shr     rax, 3Fh
0x1400026b9  add     rdx, rax
0x1400026bc  mov     rax, r8
0x1400026bf  mov     [rbp+57h+arg_8], rdx
0x1400026c3  mul     qword ptr [rbx+0C0h]
0x1400026ca  mov     rax, r8
0x1400026cd  shr     rdx, 0Bh
0x1400026d1  mov     [rbp+57h+var_78], rdx
0x1400026d5  mul     r15
0x1400026d8  lea     rax, [rbp+57h+arg_8]
0x1400026dc  mov     [rsp+0F0h+var_C0], rax
0x1400026e1  lea     rax, [rbp+57h+var_78]
0x1400026e5  shr     rdx, 0Bh
0x1400026e9  mov     [rsp+0F0h+var_C8], rax
0x1400026ee  lea     rax, [rbp+57h+var_70]
0x1400026f2  mov     [rbp+57h+var_70], rdx
0x1400026f6  lea     rdx, byte_140069F43
0x1400026fd  mov     [rsp+0F0h+var_D0], rax
0x140002702  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x140002707  mov     r9d, dword ptr [rbp+57h+OutUsed]
0x14000270b  xor     r10d, r10d
0x14000270e  cmp     [rbx+0D8h], r10b
0x140002715  jz      loc_140002BE8
0x14000271b  mov     r8, [r14+10h]
0x14000271f  mov     ecx, [rbx+0D0h]
0x140002725  mov     r12, [rbx+0C0h]
0x14000272c  mov     rax, [r8+8]
0x140002730  sub     rax, [rbx+0C8h]
0x140002737  imul    rax, rcx
0x14000273b  mov     ecx, [rbx+0D4h]
0x140002741  cqo
0x140002743  idiv    rcx
0x140002746  add     rax, [r8+18h]
0x14000274a  add     r12, rax
0x14000274d  mov     rax, [r14+18h]
0x140002751  cmp     r9d, [rax+0Ch]
0x140002755  jnz     loc_14000292F
0x14000275b  mov     rcx, r14; StreamPointer
0x14000275e  call    cs:__imp_KsStreamPointerDelete
0x140002765  nop     dword ptr [rax+rax+00h]
0x14000276a  mov     eax, cs:dword_14006F0F8
0x140002770  cmp     eax, esi
0x140002772  jbe     short loc_1400027D8
0x140002774  mov     rdx, rdi
0x140002777  lea     rcx, dword_14006F0F8
0x14000277e  call    _tlgKeywordOn
0x140002783  test    al, al
0x140002785  jz      short loc_1400027D8
0x140002787  mov     rcx, 346DC5D63886594Bh
0x140002791  mov     [rbp+57h+arg_10], r14
0x140002795  mov     rax, rcx
0x140002798  mul     r12
0x14000279b  mov     rax, rcx
0x14000279e  shr     rdx, 0Bh
0x1400027a2  mov     [rbp+57h+OutUsed], rdx
0x1400027a6  mul     r15
0x1400027a9  lea     rax, [rbp+57h+OutUsed]
0x1400027ad  mov     [rsp+0F0h+var_C0], rax
0x1400027b2  lea     rax, [rbp+57h+arg_8]
0x1400027b6  shr     rdx, 0Bh
0x1400027ba  mov     [rsp+0F0h+var_C8], rax
0x1400027bf  lea     rax, [rbp+57h+arg_10]
0x1400027c3  mov     [rbp+57h+arg_8], rdx
0x1400027c7  lea     rdx, byte_140069F03
0x1400027ce  mov     [rsp+0F0h+var_D0], rax
0x1400027d3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1400027d8  cmp     r12, r15
0x1400027db  jbe     loc_1400028E6
0x1400027e1  mov     eax, cs:dword_14006F0F8
0x1400027e7  cmp     eax, esi
0x1400027e9  jbe     short loc_14000280F
0x1400027eb  mov     rdx, rdi
0x1400027ee  lea     rcx, dword_14006F0F8
0x1400027f5  call    _tlgKeywordOn
0x1400027fa  xor     r14d, r14d
0x1400027fd  test    al, al
0x1400027ff  jz      short loc_140002812
0x140002801  lea     rdx, word_140069EDA
0x140002808  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x14000280d  jmp     short loc_140002812
0x14000280f  xor     r14d, r14d
  ... truncated ...
```
