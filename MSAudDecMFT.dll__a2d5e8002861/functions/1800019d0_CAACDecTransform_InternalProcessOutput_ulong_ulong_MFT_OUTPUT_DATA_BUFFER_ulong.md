# CAACDecTransform::InternalProcessOutput(ulong,ulong,_MFT_OUTPUT_DATA_BUFFER *,ulong *)

- ea: `0x1800019d0`
- end: `0x180002053`
- name: `?InternalProcessOutput@CAACDecTransform@@MEAAJKKPEAU_MFT_OUTPUT_DATA_BUFFER@@PEAK@Z`
- size: `1667`
- prototype: `__int64 __fastcall(CAACDecTransform *this, int, __int64, struct _MFT_OUTPUT_DATA_BUFFER *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callees

- `0x1800019d0`
- `0x18000231c`
- `0x180002550`
- `0x180003664`
- `0x180003af0`
- `0x180003d64`
- `0x180003e24`
- `0x180004e54`
- `0x180030924`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x180001a72`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x180001da5`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x180001a72`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x180001da5`
- `api-ms-win-crt-runtime-l1-1-0!_control87` at `0x180001a4e`
- `api-ms-win-crt-runtime-l1-1-0!_control87` at `0x180001a85`
- `api-ms-win-crt-runtime-l1-1-0!_control87` at `0x180001dbd`
- `api-ms-win-crt-runtime-l1-1-0!_control87` at `0x180001a4e`
- `api-ms-win-crt-runtime-l1-1-0!_control87` at `0x180001a85`
- `api-ms-win-crt-runtime-l1-1-0!_control87` at `0x180001dbd`

## string_xrefs

- `0x180001c4b`: `AACDecTransform::InternalProcessOutput() OUTPUT MFSampleExtension_CleanPoint on output sample`
- `0x180001fbd`: `AACDecTransform::InternalProcessOutput() pOutputSample->SetUINT32(MFSampleExtension_Discontinuity,TRUE) failed with hrLoc = 0x%x`

## pseudocode

```c
__int64 __fastcall CAACDecTransform::InternalProcessOutput(
        CAACDecTransform *this,
        int a2,
        __int64 a3,
        struct _MFT_OUTPUT_DATA_BUFFER *a4,
        unsigned int *a5)
{
  CAACDecTransform *v5; // r14
  TraceLoggingHelperBase *v7; // rbp
  signed int v9; // eax
  _DWORD *v10; // rsi
  int v11; // edi
  DWORD *p_dwStatus; // r12
  unsigned __int8 *v13; // rdx
  CAACDec *v14; // r13
  int v15; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rsi
  _QWORD *v18; // rax
  __int64 *v19; // r12
  int v21; // eax
  int v22; // eax
  bool v23; // zf
  __int64 v24; // rcx
  __int64 v25; // [rsp+28h] [rbp-60h]
  struct IMFSample *pSample; // [rsp+40h] [rbp-48h] BYREF
  int NewValue; // [rsp+90h] [rbp+8h]
  unsigned __int8 *v28; // [rsp+A8h] [rbp+20h] BYREF

  v5 = (CAACDecTransform *)((char *)this - 24);
  v7 = (CAACDecTransform *)((char *)this + 246640);
  TraceLoggingHelperBase::TraceVA(
    (CAACDecTransform *)((char *)this + 246640),
    4u,
    "CAACDecTransform::InternalProcessOutput",
    0xB52u,
    "CAACDecTransform::InternalProcessOutput(dwFlags=0x%X, Status=0x%X, m_fDrain = %d)",
    a2,
    *a5,
    *((_DWORD *)this + 64049));
  v28 = 0;
  *((_QWORD *)this + 27) = 0;
  v9 = _control87(0, 0);
  if ( v9 < 0 )
    v9 = 524319;
  NewValue = v9 & 0x308031F;
  _clearfp();
  _control87(0x108001Fu, 0x308031Fu);
  if ( !a4 )
  {
    TraceLoggingHelperBase::TraceVA(
      v7,
      4u,
      "CAACDecTransform::InternalProcessOutput",
      0xB63u,
      "CAACDecTransform::InternalProcessOutput() pOutputSamples or/and pdwStatus is NULL");
    v11 = -2147024809;
    goto LABEL_28;
  }
  v10 = (_DWORD *)((char *)this + 256196);
  if ( !*((_QWORD *)this + 9) && !*v10 )
  {
    v11 = -1072861838;
    a4->dwStatus = 768;
    goto LABEL_28;
  }
  pSample = a4->pSample;
  v11 = CAACDecTransform::_LockOutputBuffer(v5, &pSample);
  if ( v11 >= 0 )
  {
    p_dwStatus = &a4->dwStatus;
    if ( *((_QWORD *)this + 9) || !*v10 )
    {
      if ( *((_QWORD *)this + 32017) )
      {
        if ( *((_DWORD *)v5 + 64061) )
          v13 = (unsigned __int8 *)*((_QWORD *)this + 32028);
        else
          v13 = (unsigned __int8 *)*((_QWORD *)this + 32018);
      }
      else
      {
        v11 = CAACDecTransform::_LockInputBuffer(v5, (struct IMFSample **)this + 9, &v28);
        if ( v11 < 0 )
          goto LABEL_28;
        v13 = v28;
      }
      v14 = (CAACDecTransform *)((char *)this + 152);
      v11 = CAACDec::DecodeAAC((CAACDecTransform *)((char *)this + 152), v13, *((_DWORD *)this + 64038), &a4->dwStatus);
      if ( v11 != -1072861838 )
        goto LABEL_11;
    }
    else
    {
      v11 = -1072861838;
      v14 = (CAACDecTransform *)((char *)this + 152);
    }
    if ( *v10 )
    {
      v11 = CAACDec::DecodeDrainAAC(v14, &a4->dwStatus);
      if ( (*p_dwStatus & 0x1000000) == 0 )
        *v10 = 0;
    }
LABEL_11:
    TraceLoggingHelperBase::TraceVA(
      v7,
      5u,
      "CAACDecTransform::InternalProcessOutput",
      0xBE6u,
      "CAACDecTransform::InternalProcessOutput() m_dwOutputSampleBufferOffset=%d, SampleStatus=0x%X, OutputStatus=0x%X",
      *((_DWORD *)this + 64045),
      *p_dwStatus,
      *a5);
    switch ( v11 )
    {
      case -1072861855:
        v24 = *((_QWORD *)this + 10);
        if ( v24 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          *((_QWORD *)this + 10) = 0;
        }
        *((_BYTE *)this + 246092) = 1;
        TraceLoggingHelperBase::TraceVA(
          v7,
          4u,
          "CAACDecTransform::InternalProcessOutput",
          0xBF9u,
          "Media type change initiated by the decoder");
        v11 = CAACDecTransform::_ConfigOutputTypes(v5);
        if ( v11 >= 0 )
          v11 = -1072861855;
        break;
      case -1072861838:
        TraceLoggingHelperBase::TraceVA(
          v7,
          5u,
          "CAACDecTransform::InternalProcessOutput",
          0xC08u,
          "CAACDecTransform::InternalProcessOutput() release input sample");
        CAACDecTransform::ReleaseInputSample(v5);
        break;
      case 0:
        v15 = *((_DWORD *)this + 61524);
        if ( v15 == 2 || v15 == 5 )
          CAACDecTransform::ReleaseInputSample(v5);
        ++*((_DWORD *)this + 64047);
        if ( a4->pSample )
        {
          if ( *((_DWORD *)this + 50) )
          {
            if ( (unsigned int)(*((_DWORD *)this + 61524) - 3) <= 1 )
            {
              if ( *((_DWORD *)this + 61522) )
                v21 = *((_DWORD *)this + 46);
              else
                v21 = 0;
              v17 = *((_QWORD *)this + 24) - v21;
              if ( *((_DWORD *)this + 64059) )
              {
                v17 -= *((_QWORD *)this + 23);
                *((_DWORD *)this + 64059) = 0;
              }
            }
            else
            {
              if ( *((_BYTE *)this + 232) && *((_DWORD *)this + 61522) )
              {
                v16 = (_QWORD *)((char *)this + 208);
                v17 = *((_QWORD *)this + 26);
                v18 = (_QWORD *)((char *)this + 192);
              }
              else
              {
                v18 = (_QWORD *)((char *)this + 192);
                v17 = *((_QWORD *)this + 24);
                v16 = (_QWORD *)((char *)this + 208);
              }
              *v16 = *v18;
            }
            *((_DWORD *)this + 50) = 0;
            v19 = (__int64 *)((char *)this + 224);
          }
          else
          {
            v19 = (__int64 *)((char *)this + 224);
            v17 = *((_QWORD *)this + 28);
          }
          ((void (__fastcall *)(IMFSample *, const GUID *, __int64))a4->pSample->lpVtbl->SetUINT32)(
            a4->pSample,
            &MFSampleExtension_CleanPoint,
            1);
          TraceLoggingHelperBase::TraceVA(
            v7,
            5u,
            "CAACDecTransform::InternalProcessOutput",
            0xC95u,
            "AACDecTransform::InternalProcessOutput() OUTPUT MFSampleExtension_CleanPoint on output sample");
          ((void (__fastcall *)(IMFSample *, __int64))a4->pSample->lpVtbl->SetSampleTime)(a4->pSample, v17);
          TraceLoggingHelperBase::TraceVA(
            v7,
            5u,
            "CAACDecTransform::InternalProcessOutput",
            0xC98u,
            "AACDecTransform::InternalProcessOutput() OUTPUT sample time = %12I64d",
            v17);
          ((void (__fastcall *)(IMFSample *, _QWORD))a4->pSample->lpVtbl->SetSampleDuration)(
            a4->pSample,
            *((_QWORD *)this + 27));
          TraceLoggingHelperBase::TraceVA(
            v7,
            5u,
            "CAACDecTransform::InternalProcessOutput",
            0xC9Bu,
            "AACDecTransform::InternalProcessOutput() OUTPUT sample duration = %12I64d",
            *((_QWORD *)this + 27));
          TraceLoggingHelperBase::TraceVA(
            v7,
            5u,
            "CAACDecTransform::InternalProcessOutput",
            0xC9Du,
            "AACDecTransform::InternalProcessOutput() OUTPUT time stamp gap = OUTPUT time - (Prev OUTPUT time + Prev OUTP"
            "UT duration) = %12I64d",
            v17 - *v19);
          v25 = v17 + *((_QWORD *)this + 27);
          *v19 = v25;
          TraceLoggingHelperBase::TraceVA(
            v7,
            5u,
            "CAACDecTransform::InternalProcessOutput",
            0xCA0u,
            "AACDecTransform::InternalProcessOutput() OUTPUT sample time + duration = %12I64d",
            v25);
          if ( *(_DWORD *)((char *)this + (*((_DWORD *)this + 61522) != 0 ? 4 : 0) + 236) )
          {
            v22 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))a4->pSample->lpVtbl->SetUINT32)(
                    a4->pSample,
                    &MFSampleExtension_Discontinuity,
                    1);
            if ( v22 < 0 )
              TraceLoggingHelperBase::TraceVA(
                v7,
                5u,
                "CAACDecTransform::InternalProcessOutput",
                0xCAEu,
                "AACDecTransform::InternalProcessOutput() pOutputSample->SetUINT32(MFSampleExtension_Discontinuity,TRUE) "
                "failed with hrLoc = 0x%x",
                v22);
            else
              TraceLoggingHelperBase::TraceVA(
                v7,
                5u,
                "CAACDecTransform::InternalProcessOutput",
                0xCAAu,
                "AACDecTransform::InternalProcessOutput() Output sample discontinuity attribute was set successfully");
          }
          if ( *((_DWORD *)this + 59) )
          {
            v23 = *((_DWORD *)this + 61522) == 0;
            *((_DWORD *)this + 59) = 0;
            *((_DWORD *)this + 60) = !v23;
          }
          else
          {
            *((_DWORD *)this + 60) = 0;
          }
        }
        break;
    }
    CAACDecTransform::_UnLockOutputBuffer(v5);
  }
LABEL_28:
  _clearfp();
  _control87(NewValue, 0x308031Fu);
  TraceLoggingHelperBase::TraceVA(
    v7,
    4u,
    "CAACDecTransform::InternalProcessOutput",
    0xCCCu,
    "CAACDecTransform::InternalProcessOutput() returns hr = 0x%x",
    v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800019d0  mov     [rsp+arg_8], rbx
0x1800019d5  push    rbp
0x1800019d6  push    rsi
0x1800019d7  push    rdi
0x1800019d8  push    r12
0x1800019da  push    r13
0x1800019dc  push    r14
0x1800019de  push    r15
0x1800019e0  sub     rsp, 50h
0x1800019e4  lea     r14, [rcx-18h]
0x1800019e8  mov     r15, r9
0x1800019eb  mov     eax, [r14+3E8DCh]
0x1800019f2  lea     rbp, [rcx+3C370h]
0x1800019f9  mov     [rsp+88h+var_50], eax
0x1800019fd  lea     r8, aCaacdectransfo_55; "CAACDecTransform::InternalProcessOutput"
0x180001a04  mov     rax, [rsp+88h+arg_20]
0x180001a0c  mov     rbx, rcx
0x180001a0f  mov     r9d, 0B52h; unsigned int
0x180001a15  mov     rcx, rbp; this
0x180001a18  mov     eax, [rax]
0x180001a1a  mov     [rsp+88h+var_58], eax
0x180001a1e  lea     rax, aCaacdectransfo_16; "CAACDecTransform::InternalProcessOutput"...
0x180001a25  mov     dword ptr [rsp+88h+var_60], edx
0x180001a29  mov     edx, 4; unsigned __int8
0x180001a2e  mov     [rsp+88h+Format], rax; Format
0x180001a33  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180001a38  xor     r12d, r12d
0x180001a3b  xor     edx, edx; Mask
0x180001a3d  xor     ecx, ecx; NewValue
0x180001a3f  mov     [rsp+88h+arg_18], r12
0x180001a47  mov     [rbx+0D8h], r12
0x180001a4e  call    cs:__imp__control87
0x180001a55  nop     dword ptr [rax+rax+00h]
0x180001a5a  mov     ecx, 8001Fh
0x180001a5f  mov     edi, 308031Fh
0x180001a64  test    eax, eax
0x180001a66  cmovs   eax, ecx
0x180001a69  and     eax, edi
0x180001a6b  mov     [rsp+88h+NewValue], eax
0x180001a72  call    cs:__imp__clearfp
0x180001a79  nop     dword ptr [rax+rax+00h]
0x180001a7e  mov     edx, edi; Mask
0x180001a80  mov     ecx, 108001Fh; NewValue
0x180001a85  call    cs:__imp__control87
0x180001a8c  nop     dword ptr [rax+rax+00h]
0x180001a91  test    r15, r15
0x180001a94  jz      loc_180001E29
0x180001a9a  lea     r13, [rbx+48h]
0x180001a9e  lea     rsi, [rbx+3E8C4h]
0x180001aa5  cmp     [r13+0], r12
0x180001aa9  jz      loc_180001E0E
0x180001aaf  mov     rax, [r15+8]
0x180001ab3  lea     rdx, [rsp+88h+var_48]; struct IMFSample **
0x180001ab8  mov     rcx, r14; this
0x180001abb  mov     [rsp+88h+var_48], rax
0x180001ac0  call    ?_LockOutputBuffer@CAACDecTransform@@AEAAJPEAPEAUIMFSample@@@Z; CAACDecTransform::_LockOutputBuffer(IMFSample * *)
0x180001ac5  mov     edi, eax
0x180001ac7  test    eax, eax
0x180001ac9  js      loc_180001DA5
0x180001acf  xor     eax, eax
0x180001ad1  lea     r12, [r15+10h]
0x180001ad5  cmp     [r13+0], rax
0x180001ad9  jz      loc_180001F1F
0x180001adf  cmp     [rbx+3E888h], rax
0x180001ae6  jnz     loc_180001F38
0x180001aec  lea     r8, [rsp+88h+arg_18]; unsigned __int8 **
0x180001af4  mov     rdx, r13; struct IMFSample **
0x180001af7  mov     rcx, r14; this
0x180001afa  call    ?_LockInputBuffer@CAACDecTransform@@AEAAJPEAPEAUIMFSample@@PEAPEAE@Z; CAACDecTransform::_LockInputBuffer(IMFSample * *,uchar * *)
0x180001aff  mov     edi, eax
0x180001b01  test    eax, eax
0x180001b03  js      loc_180001DA5
0x180001b09  mov     rdx, [rsp+88h+arg_18]; unsigned __int8 *
0x180001b11  mov     r8d, [rbx+3E898h]; int
0x180001b18  lea     r13, [rbx+98h]
0x180001b1f  mov     rcx, r13; this
0x180001b22  mov     r9, r12; unsigned int *
0x180001b25  call    ?DecodeAAC@CAACDec@@IEAAJPEAEJPEAK@Z; CAACDec::DecodeAAC(uchar *,long,ulong *)
0x180001b2a  mov     edi, eax
0x180001b2c  cmp     eax, 0C00D6D72h
0x180001b31  jz      loc_180001EAF
0x180001b37  xor     r13d, r13d
0x180001b3a  mov     rax, [rsp+88h+arg_20]
0x180001b42  lea     r8, aCaacdectransfo_55; "CAACDecTransform::InternalProcessOutput"
0x180001b49  mov     esi, 5
0x180001b4e  mov     r9d, 0BE6h; unsigned int
0x180001b54  mov     edx, esi; unsigned __int8
0x180001b56  mov     rcx, rbp; this
0x180001b59  mov     eax, [rax]
0x180001b5b  mov     [rsp+88h+var_50], eax
0x180001b5f  mov     eax, [r12]
0x180001b63  mov     [rsp+88h+var_58], eax
0x180001b67  mov     eax, [rbx+3E8B4h]
0x180001b6d  mov     dword ptr [rsp+88h+var_60], eax
0x180001b71  lea     rax, aCaacdectransfo_53; "CAACDecTransform::InternalProcessOutput"...
0x180001b78  mov     [rsp+88h+Format], rax; Format
0x180001b7d  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180001b82  mov     r12d, 0C00D6D61h
0x180001b88  cmp     edi, r12d
0x180001b8b  jz      loc_180001FF2
0x180001b91  cmp     edi, 0C00D6D72h
0x180001b97  jz      loc_180001E7F
0x180001b9d  test    edi, edi
0x180001b9f  jnz     loc_180001D9D
0x180001ba5  mov     eax, [rbx+3C150h]
0x180001bab  cmp     eax, 2
0x180001bae  jnz     loc_180001F59
0x180001bb4  mov     rcx, r14; this
0x180001bb7  call    ?ReleaseInputSample@CAACDecTransform@@AEAAXXZ; CAACDecTransform::ReleaseInputSample(void)
0x180001bbc  inc     dword ptr [rbx+3E8BCh]
0x180001bc2  cmp     [r15+8], r13
0x180001bc6  jz      loc_180001D9D
0x180001bcc  cmp     [rbx+0C8h], r13d
0x180001bd3  jz      loc_180001E6F
0x180001bd9  mov     eax, [rbx+3C150h]
0x180001bdf  sub     eax, 3
0x180001be2  cmp     eax, 1
0x180001be5  jbe     loc_180001EDF
0x180001beb  cmp     [rbx+0E8h], r13b
0x180001bf2  jz      loc_180001E59
0x180001bf8  cmp     [rbx+3C148h], r13d
0x180001bff  jz      loc_180001E59
0x180001c05  lea     rcx, [rbx+0D0h]
0x180001c0c  mov     rsi, [rcx]
0x180001c0f  lea     rax, [rbx+0C0h]
0x180001c16  mov     rax, [rax]
0x180001c19  mov     [rcx], rax
0x180001c1c  mov     [rbx+0C8h], r13d
0x180001c23  lea     r12, [rbx+0E0h]
0x180001c2a  mov     rcx, [r15+8]
0x180001c2e  lea     rdx, MFSampleExtension_CleanPoint
0x180001c35  mov     r8d, 1
0x180001c3b  mov     rax, [rcx]
0x180001c3e  mov     rax, [rax+0A8h]
0x180001c45  call    cs:__guard_dispatch_icall_fptr
0x180001c4b  lea     rax, aAacdectransfor_2; "AACDecTransform::InternalProcessOutput("...
0x180001c52  mov     r9d, 0C95h; unsigned int
0x180001c58  lea     r8, aCaacdectransfo_55; "CAACDecTransform::InternalProcessOutput"
0x180001c5f  mov     [rsp+88h+Format], rax; Format
0x180001c64  mov     edx, 5; unsigned __int8
0x180001c69  mov     rcx, rbp; this
0x180001c6c  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180001c71  mov     rcx, [r15+8]
0x180001c75  mov     rdx, rsi
0x180001c78  mov     rax, [rcx]
0x180001c7b  mov     rax, [rax+120h]
0x180001c82  call    cs:__guard_dispatch_icall_fptr
0x180001c88  lea     rax, aAacdectransfor_1; "AACDecTransform::InternalProcessOutput("...
0x180001c8f  mov     [rsp+88h+var_60], rsi
0x180001c94  mov     r9d, 0C98h; unsigned int
0x180001c9a  mov     [rsp+88h+Format], rax; Format
0x180001c9f  lea     r8, aCaacdectransfo_55; "CAACDecTransform::InternalProcessOutput"
0x180001ca6  mov     edx, 5; unsigned __int8
0x180001cab  mov     rcx, rbp; this
0x180001cae  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180001cb3  mov     rcx, [r15+8]
0x180001cb7  mov     rdx, [rbx+0D8h]
0x180001cbe  mov     rax, [rcx]
0x180001cc1  mov     rax, [rax+130h]
0x180001cc8  call    cs:__guard_dispatch_icall_fptr
0x180001cce  mov     rax, [rbx+0D8h]
0x180001cd5  lea     r8, aCaacdectransfo_55; "CAACDecTransform::InternalProcessOutput"
0x180001cdc  mov     [rsp+88h+var_60], rax
0x180001ce1  mov     r9d, 0C9Bh; unsigned int
0x180001ce7  lea     rax, aAacdectransfor; "AACDecTransform::InternalProcessOutput("...
0x180001cee  mov     edx, 5; unsigned __int8
0x180001cf3  mov     rcx, rbp; this
0x180001cf6  mov     [rsp+88h+Format], rax; Format
0x180001cfb  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180001d00  mov     rax, rsi
0x180001d03  lea     r8, aCaacdectransfo_55; "CAACDecTransform::InternalProcessOutput"
0x180001d0a  sub     rax, [r12]
0x180001d0e  mov     r9d, 0C9Dh; unsigned int
0x180001d14  mov     [rsp+88h+var_60], rax
0x180001d19  mov     edx, 5; unsigned __int8
0x180001d1e  lea     rax, aAacdectransfor_5; "AACDecTransform::InternalProcessOutput("...
0x180001d25  mov     rcx, rbp; this
0x180001d28  mov     [rsp+88h+Format], rax; Format
0x180001d2d  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180001d32  mov     rcx, [rbx+0D8h]
0x180001d39  lea     rax, aAacdectransfor_4; "AACDecTransform::InternalProcessOutput("...
0x180001d40  add     rcx, rsi
0x180001d43  lea     r8, aCaacdectransfo_55; "CAACDecTransform::InternalProcessOutput"
0x180001d4a  mov     [rsp+88h+var_60], rcx
0x180001d4f  mov     esi, 5
0x180001d54  mov     [r12], rcx
0x180001d58  mov     edx, esi; unsigned __int8
0x180001d5a  mov     rcx, rbp; this
0x180001d5d  mov     [rsp+88h+Format], rax; Format
0x180001d62  mov     r9d, 0CA0h; unsigned int
0x180001d68  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180001d6d  mov     eax, [rbx+3C148h]
0x180001d73  neg     eax
0x180001d75  sbb     rcx, rcx
0x180001d78  and     ecx, 4
0x180001d7b  cmp     [rcx+rbx+0ECh], r13d
0x180001d83  jnz     loc_180001F66
0x180001d89  cmp     [rbx+0ECh], r13d
0x180001d90  jnz     loc_180001FD3
0x180001d96  mov     [rbx+0F0h], r13d
0x180001d9d  mov     rcx, r14; this
0x180001da0  call    ?_UnLockOutputBuffer@CAACDecTransform@@AEAAJXZ; CAACDecTransform::_UnLockOutputBuffer(void)
0x180001da5  call    cs:__imp__clearfp
0x180001dac  nop     dword ptr [rax+rax+00h]
0x180001db1  mov     ecx, [rsp+88h+NewValue]; NewValue
0x180001db8  mov     edx, 308031Fh; Mask
0x180001dbd  call    cs:__imp__control87
0x180001dc4  nop     dword ptr [rax+rax+00h]
0x180001dc9  lea     rax, aCaacdectransfo_58; "CAACDecTransform::InternalProcessOutput"...
0x180001dd0  mov     dword ptr [rsp+88h+var_60], edi
0x180001dd4  mov     r9d, 0CCCh; unsigned int
0x180001dda  mov     [rsp+88h+Format], rax; Format
0x180001ddf  lea     r8, aCaacdectransfo_55; "CAACDecTransform::InternalProcessOutput"
0x180001de6  mov     edx, 4; unsigned __int8
0x180001deb  mov     rcx, rbp; this
0x180001dee  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180001df3  mov     rbx, [rsp+88h+arg_8]
0x180001dfb  mov     eax, edi
0x180001dfd  add     rsp, 50h
0x180001e01  pop     r15
0x180001e03  pop     r14
0x180001e05  pop     r13
0x180001e07  pop     r12
0x180001e09  pop     rdi
0x180001e0a  pop     rsi
0x180001e0b  pop     rbp
0x180001e0c  retn
0x180001e0e  cmp     [rsi], r12d
0x180001e11  jnz     loc_180001AAF
0x180001e17  mov     edi, 0C00D6D72h
0x180001e1c  mov     dword ptr [r15+10h], 300h
0x180001e24  jmp     loc_180001DA5
0x180001e29  lea     rax, aCaacdectransfo_1; "CAACDecTransform::InternalProcessOutput"...
0x180001e30  mov     r9d, 0B63h; unsigned int
0x180001e36  lea     r8, aCaacdectransfo_55; "CAACDecTransform::InternalProcessOutput"
0x180001e3d  mov     [rsp+88h+Format], rax; Format
0x180001e42  mov     edx, 4; unsigned __int8
0x180001e47  mov     rcx, rbp; this
0x180001e4a  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180001e4f  mov     edi, 80070057h
0x180001e54  jmp     loc_180001DA5
0x180001e59  lea     rax, [rbx+0C0h]
0x180001e60  mov     rsi, [rax]
0x180001e63  lea     rcx, [rbx+0D0h]
0x180001e6a  jmp     loc_180001C16
0x180001e6f  lea     r12, [rbx+0E0h]
0x180001e76  mov     rsi, [r12]
0x180001e7a  jmp     loc_180001C2A
0x180001e7f  lea     rax, aCaacdectransfo_4; "CAACDecTransform::InternalProcessOutput"...
0x180001e86  mov     r9d, 0C08h; unsigned int
0x180001e8c  lea     r8, aCaacdectransfo_55; "CAACDecTransform::InternalProcessOutput"
0x180001e93  mov     [rsp+88h+Format], rax; Format
0x180001e98  mov     edx, esi; unsigned __int8
0x180001e9a  mov     rcx, rbp; this
0x180001e9d  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180001ea2  mov     rcx, r14; this
0x180001ea5  call    ?ReleaseInputSample@CAACDecTransform@@AEAAXXZ; CAACDecTransform::ReleaseInputSample(void)
0x180001eaa  jmp     loc_180001D9D
0x180001eaf  xor     eax, eax
0x180001eb1  cmp     [rsi], eax
0x180001eb3  jz      loc_180001B37
0x180001eb9  mov     rdx, r12; unsigned int *
0x180001ebc  mov     rcx, r13; this
0x180001ebf  call    ?DecodeDrainAAC@CAACDec@@IEAAJPEAK@Z; CAACDec::DecodeDrainAAC(ulong *)
0x180001ec4  xor     r13d, r13d
0x180001ec7  mov     edi, eax
0x180001ec9  test    dword ptr [r12], 1000000h
0x180001ed1  jnz     loc_180001B3A
0x180001ed7  mov     [rsi], r13d
0x180001eda  jmp     loc_180001B3A
0x180001edf  cmp     [rbx+3C148h], r13d
0x180001ee6  jz      short loc_180001F1A
0x180001ee8  mov     eax, [rbx+0B8h]
0x180001eee  mov     rsi, [rbx+0C0h]
0x180001ef5  cdqe
0x180001ef7  sub     rsi, rax
0x180001efa  cmp     [rbx+3E8ECh], r13d
0x180001f01  jz      loc_180001C1C
0x180001f07  sub     rsi, [rbx+0B8h]
0x180001f0e  mov     [rbx+3E8ECh], r13d
0x180001f15  jmp     loc_180001C1C
0x180001f1a  mov     eax, r13d
0x180001f1d  jmp     short loc_180001EEE
0x180001f1f  cmp     [rsi], eax
0x180001f21  jz      loc_180001ADF
0x180001f27  mov     edi, 0C00D6D72h
0x180001f2c  lea     r13, [rbx+98h]
0x180001f33  jmp     loc_180001EB1
0x180001f38  cmp     [r14+3E8F4h], eax
0x180001f3f  jz      short loc_180001F4D
0x180001f41  mov     rdx, [rbx+3E8E0h]
0x180001f48  jmp     loc_180001B11
0x180001f4d  mov     rdx, [rbx+3E890h]
0x180001f54  jmp     loc_180001B11
0x180001f59  cmp     eax, esi
0x180001f5b  jnz     loc_180001BBC
0x180001f61  jmp     loc_180001BB4
0x180001f66  mov     rcx, [r15+8]
0x180001f6a  lea     rdx, MFSampleExtension_Discontinuity
0x180001f71  mov     r8d, 1
  ... truncated ...
```
