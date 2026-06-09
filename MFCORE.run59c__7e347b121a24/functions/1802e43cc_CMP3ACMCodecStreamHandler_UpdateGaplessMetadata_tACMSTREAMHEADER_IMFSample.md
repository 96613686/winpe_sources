# CMP3ACMCodecStreamHandler::UpdateGaplessMetadata(tACMSTREAMHEADER *,IMFSample *)

- ea: `0x1802e43cc`
- end: `0x1802e47d5`
- name: `?UpdateGaplessMetadata@CMP3ACMCodecStreamHandler@@AEAAJPEAUtACMSTREAMHEADER@@PEAUIMFSample@@@Z`
- size: `1033`
- prototype: `__int64 __fastcall(CMP3ACMCodecStreamHandler *__hidden this, struct tACMSTREAMHEADER *, struct IMFSample *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1802e2ca4`

## callees

- `0x180028498`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x180111d68`
- `0x1802e43cc`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e478e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e47a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e478e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e47a6`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x1802e4433`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x1802e45cf`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x1802e4433`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x1802e45cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e4455`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e4531`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e45f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e46ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e4455`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e4531`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e45f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e46ef`

## string_xrefs

- `0x1802e43ec`: `CMP3ACMCodecStreamHandler::UpdateGaplessMetadata`

## pseudocode

```c
__int64 __fastcall CMP3ACMCodecStreamHandler::UpdateGaplessMetadata(
        CMP3ACMCodecStreamHandler *this,
        struct tACMSTREAMHEADER *a2,
        struct IMFSample *a3)
{
  __int64 *v3; // r14
  __int64 v7; // rdx
  HRESULT v8; // ebx
  __int64 v9; // r8
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  WAVEFORMATEX *v14; // rbx
  unsigned __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  IMFMediaType *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v34; // [rsp+70h] [rbp+40h] BYREF
  WAVEFORMATEX *ppWF; // [rsp+78h] [rbp+48h] BYREF
  WAVEFORMATEX *v36; // [rsp+88h] [rbp+58h] BYREF

  v3 = (__int64 *)((char *)this + 232);
  *((_QWORD *)this + 32) += a2->cbSrcLengthUsed;
  v36 = 0;
  ppWF = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v34,
    "CMP3ACMCodecStreamHandler::UpdateGaplessMetadata",
    1937);
  v8 = MFCreateWaveFormatExFromMFMediaType(*((IMFMediaType **)this + 4), &ppWF, 0, 0);
  if ( v8 >= 0 )
  {
    v14 = ppWF;
    v15 = llMulDiv(*((_QWORD *)this + 32), 8, ppWF->wBitsPerSample, 0) / (unsigned __int64)v14->nChannels;
    v34 = 0;
    *((_QWORD *)this + 30) = v15;
    v8 = ULongLongToULong(a2->dwUser, &v34);
    if ( v8 >= 0 )
    {
      v21 = (IMFMediaType *)*((_QWORD *)this + 5);
      *((_QWORD *)this + 31) += a2->cbDstLengthUsed;
      v8 = MFCreateWaveFormatExFromMFMediaType(v21, &v36, 0, 0);
      if ( v8 >= 0 )
      {
        v27 = llMulDiv(*((_QWORD *)this + 31), 576LL * ppWF->nChannels, v34, 0);
        *v3 = v27;
        LODWORD(v27) = v27 - *((_DWORD *)this + 60) - 672;
        *((_DWORD *)this + 67) = 672;
        *((_DWORD *)this + 66) = v27;
        v8 = ((__int64 (__fastcall *)(struct IMFSample *, void *, __int64 *, __int64))a3->lpVtbl->SetBlob)(
               a3,
               &MFSampleExtension_ENCODED_STREAMINFO,
               v3,
               40);
        if ( v8 < 0 )
        {
          v30 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29);
            CallStackTracing::s_wpInstance = v31;
            if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
            {
              v30 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v30 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v30 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CMP3ACMCodecStreamHandler::UpdateGaplessMetadata",
                1955,
                v8);
          }
          if ( g_wppLevels )
          {
            v13 = 163;
            goto LABEL_45;
          }
        }
      }
      else
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)v26 + 499) != v8 )
            CallStackContext::TraceFailure(v26, "CMP3ACMCodecStreamHandler::UpdateGaplessMetadata", 1945, v8);
        }
        if ( g_wppLevels )
        {
          v13 = 162;
          goto LABEL_45;
        }
      }
    }
    else
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != v8 )
          CallStackContext::TraceFailure(v20, "CMP3ACMCodecStreamHandler::UpdateGaplessMetadata", 1943, v8);
      }
      if ( g_wppLevels )
      {
        v13 = 161;
        goto LABEL_45;
      }
    }
  }
  else
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != v8 )
        CallStackContext::TraceFailure(v12, "CMP3ACMCodecStreamHandler::UpdateGaplessMetadata", 1937, v8);
    }
    if ( g_wppLevels )
    {
      v13 = 160;
LABEL_45:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_a3216b5dee8234e6df5ca2fe73b99a91_Traceguids, this, v8);
    }
  }
  CoTaskMemFree(ppWF);
  ppWF = 0;
  CoTaskMemFree(v36);
  v36 = 0;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v34);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1802e43cc  push    rbp
0x1802e43ce  push    rbx
0x1802e43cf  push    rsi
0x1802e43d0  push    rdi
0x1802e43d1  push    r13
0x1802e43d3  push    r14
0x1802e43d5  push    r15
0x1802e43d7  mov     rbp, rsp
0x1802e43da  sub     rsp, 30h
0x1802e43de  mov     eax, [rdx+1Ch]
0x1802e43e1  lea     r14, [rcx+0E8h]
0x1802e43e8  add     rax, [r14+18h]
0x1802e43ec  lea     r13, aCmp3acmcodecst_0; "CMP3ACMCodecStreamHandler::UpdateGaples"...
0x1802e43f3  mov     [rcx+100h], rax
0x1802e43fa  mov     r15, r8
0x1802e43fd  mov     rsi, rdx
0x1802e4400  mov     [rbp+arg_18], 0
0x1802e4408  mov     rdi, rcx
0x1802e440b  mov     [rbp+ppWF], 0
0x1802e4413  lea     rcx, [rbp+arg_0]; this
0x1802e4417  mov     r8d, 791h; int
0x1802e441d  mov     rdx, r13; char *
0x1802e4420  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802e4425  mov     rcx, [rdi+20h]; pMFType
0x1802e4429  lea     rdx, [rbp+ppWF]; ppWF
0x1802e442d  xor     r9d, r9d; Flags
0x1802e4430  xor     r8d, r8d; pcbSize
0x1802e4433  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x1802e443a  nop     dword ptr [rax+rax+00h]
0x1802e443f  mov     ebx, eax
0x1802e4441  test    eax, eax
0x1802e4443  jns     loc_1802E44DB
0x1802e4449  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e4450  test    rcx, rcx
0x1802e4453  jnz     short loc_1802E449D
0x1802e4455  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e445c  nop     dword ptr [rax+rax+00h]
0x1802e4461  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e4468  mov     rcx, rax
0x1802e446b  test    rax, rax
0x1802e446e  jz      short loc_1802E448F
0x1802e4470  mov     rax, [rax]
0x1802e4473  mov     edx, 7F0h
0x1802e4478  mov     rax, [rax+8]
0x1802e447c  call    cs:__guard_dispatch_icall_fptr
0x1802e4482  test    eax, eax
0x1802e4484  jz      short loc_1802E448F
0x1802e4486  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e448d  jmp     short loc_1802E449D
0x1802e448f  lea     rcx, qword_1803CE250; this
0x1802e4496  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e449d  cmp     byte ptr [rcx+8], 0
0x1802e44a1  jz      short loc_1802E44C4
0x1802e44a3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e44a8  cmp     [rax+7CCh], ebx
0x1802e44ae  jz      short loc_1802E44C4
0x1802e44b0  mov     r9d, ebx; int
0x1802e44b3  mov     r8d, 791h; int
0x1802e44b9  mov     rdx, r13; char *
0x1802e44bc  mov     rcx, rax; this
0x1802e44bf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e44c4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e44cb  jb      loc_1802E478A
0x1802e44d1  mov     edx, 0A0h
0x1802e44d6  jmp     loc_1802E476C
0x1802e44db  mov     rbx, [rbp+ppWF]
0x1802e44df  xor     r9d, r9d; __int64
0x1802e44e2  mov     rcx, [rdi+100h]; __int64
0x1802e44e9  movzx   r8d, word ptr [rbx+0Eh]; __int64
0x1802e44ee  lea     edx, [r9+8]; __int64
0x1802e44f2  call    ?llMulDiv@@YA_J_J000@Z; llMulDiv(__int64,__int64,__int64,__int64)
0x1802e44f7  movzx   ecx, word ptr [rbx+2]
0x1802e44fb  xor     edx, edx
0x1802e44fd  div     rcx
0x1802e4500  lea     rdx, [rbp+arg_0]; unsigned int *
0x1802e4504  mov     [rbp+arg_0], 0
0x1802e450b  mov     [rdi+0F0h], rax
0x1802e4512  mov     rcx, [rsi+8]; unsigned __int64
0x1802e4516  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1802e451b  mov     ebx, eax
0x1802e451d  test    eax, eax
0x1802e451f  jns     loc_1802E45B7
0x1802e4525  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e452c  test    rcx, rcx
0x1802e452f  jnz     short loc_1802E4579
0x1802e4531  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e4538  nop     dword ptr [rax+rax+00h]
0x1802e453d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e4544  mov     rcx, rax
0x1802e4547  test    rax, rax
0x1802e454a  jz      short loc_1802E456B
0x1802e454c  mov     rax, [rax]
0x1802e454f  mov     edx, 7F0h
0x1802e4554  mov     rax, [rax+8]
0x1802e4558  call    cs:__guard_dispatch_icall_fptr
0x1802e455e  test    eax, eax
0x1802e4560  jz      short loc_1802E456B
0x1802e4562  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e4569  jmp     short loc_1802E4579
0x1802e456b  lea     rcx, qword_1803CE250; this
0x1802e4572  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e4579  cmp     byte ptr [rcx+8], 0
0x1802e457d  jz      short loc_1802E45A0
0x1802e457f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e4584  cmp     [rax+7CCh], ebx
0x1802e458a  jz      short loc_1802E45A0
0x1802e458c  mov     r9d, ebx; int
0x1802e458f  mov     r8d, 797h; int
0x1802e4595  mov     rdx, r13; char *
0x1802e4598  mov     rcx, rax; this
0x1802e459b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e45a0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e45a7  jb      loc_1802E478A
0x1802e45ad  mov     edx, 0A1h
0x1802e45b2  jmp     loc_1802E476C
0x1802e45b7  mov     eax, [rsi+34h]
0x1802e45ba  lea     rdx, [rbp+arg_18]; ppWF
0x1802e45be  mov     rcx, [rdi+28h]; pMFType
0x1802e45c2  xor     r9d, r9d; Flags
0x1802e45c5  add     [rdi+0F8h], rax
0x1802e45cc  xor     r8d, r8d; pcbSize
0x1802e45cf  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x1802e45d6  nop     dword ptr [rax+rax+00h]
0x1802e45db  mov     ebx, eax
0x1802e45dd  test    eax, eax
0x1802e45df  jns     loc_1802E4677
0x1802e45e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e45ec  test    rcx, rcx
0x1802e45ef  jnz     short loc_1802E4639
0x1802e45f1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e45f8  nop     dword ptr [rax+rax+00h]
0x1802e45fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e4604  mov     rcx, rax
0x1802e4607  test    rax, rax
0x1802e460a  jz      short loc_1802E462B
0x1802e460c  mov     rax, [rax]
0x1802e460f  mov     edx, 7F0h
0x1802e4614  mov     rax, [rax+8]
0x1802e4618  call    cs:__guard_dispatch_icall_fptr
0x1802e461e  test    eax, eax
0x1802e4620  jz      short loc_1802E462B
0x1802e4622  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e4629  jmp     short loc_1802E4639
0x1802e462b  lea     rcx, qword_1803CE250; this
0x1802e4632  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e4639  cmp     byte ptr [rcx+8], 0
0x1802e463d  jz      short loc_1802E4660
0x1802e463f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e4644  cmp     [rax+7CCh], ebx
0x1802e464a  jz      short loc_1802E4660
0x1802e464c  mov     r9d, ebx; int
0x1802e464f  mov     r8d, 799h; int
0x1802e4655  mov     rdx, r13; char *
0x1802e4658  mov     rcx, rax; this
0x1802e465b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e4660  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e4667  jb      loc_1802E478A
0x1802e466d  mov     edx, 0A2h
0x1802e4672  jmp     loc_1802E476C
0x1802e4677  mov     rax, [rbp+ppWF]
0x1802e467b  xor     r9d, r9d; __int64
0x1802e467e  mov     r8d, [rbp+arg_0]; __int64
0x1802e4682  movzx   ecx, word ptr [rax+2]
0x1802e4686  lea     rdx, [rcx+rcx*8]
0x1802e468a  mov     rcx, [rdi+0F8h]; __int64
0x1802e4691  shl     rdx, 6; __int64
0x1802e4695  call    ?llMulDiv@@YA_J_J000@Z; llMulDiv(__int64,__int64,__int64,__int64)
0x1802e469a  mov     [r14], rax
0x1802e469d  lea     rdx, MFSampleExtension_ENCODED_STREAMINFO
0x1802e46a4  sub     eax, [rdi+0F0h]
0x1802e46aa  mov     ecx, 2A0h
0x1802e46af  sub     eax, ecx
0x1802e46b1  mov     [rdi+10Ch], ecx
0x1802e46b7  mov     [rdi+108h], eax
0x1802e46bd  mov     r9d, 28h ; '('
0x1802e46c3  mov     rax, [r15]
0x1802e46c6  mov     r8, r14
0x1802e46c9  mov     rcx, r15
0x1802e46cc  mov     rax, [rax+0D0h]
0x1802e46d3  call    cs:__guard_dispatch_icall_fptr
0x1802e46d9  mov     ebx, eax
0x1802e46db  test    eax, eax
0x1802e46dd  jns     loc_1802E478A
0x1802e46e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e46ea  test    rcx, rcx
0x1802e46ed  jnz     short loc_1802E4737
0x1802e46ef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e46f6  nop     dword ptr [rax+rax+00h]
0x1802e46fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e4702  mov     rcx, rax
0x1802e4705  test    rax, rax
0x1802e4708  jz      short loc_1802E4729
0x1802e470a  mov     rax, [rax]
0x1802e470d  mov     edx, 7F0h
0x1802e4712  mov     rax, [rax+8]
0x1802e4716  call    cs:__guard_dispatch_icall_fptr
0x1802e471c  test    eax, eax
0x1802e471e  jz      short loc_1802E4729
0x1802e4720  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e4727  jmp     short loc_1802E4737
0x1802e4729  lea     rcx, qword_1803CE250; this
0x1802e4730  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e4737  cmp     byte ptr [rcx+8], 0
0x1802e473b  jz      short loc_1802E475E
0x1802e473d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e4742  cmp     [rax+7CCh], ebx
0x1802e4748  jz      short loc_1802E475E
0x1802e474a  mov     r9d, ebx; int
0x1802e474d  mov     r8d, 7A3h; int
0x1802e4753  mov     rdx, r13; char *
0x1802e4756  mov     rcx, rax; this
0x1802e4759  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e475e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e4765  jb      short loc_1802E478A
0x1802e4767  mov     edx, 0A3h
0x1802e476c  mov     rcx, cs:WPP_GLOBAL_Control
0x1802e4773  lea     r8, WPP_a3216b5dee8234e6df5ca2fe73b99a91_Traceguids
0x1802e477a  mov     r9, rdi
0x1802e477d  mov     [rsp+30h+var_10], ebx
0x1802e4781  mov     rcx, [rcx+10h]
0x1802e4785  call    WPP_SF_qD
0x1802e478a  mov     rcx, [rbp+ppWF]; pv
0x1802e478e  call    cs:__imp_CoTaskMemFree
0x1802e4795  nop     dword ptr [rax+rax+00h]
0x1802e479a  mov     rcx, [rbp+arg_18]; pv
0x1802e479e  mov     [rbp+ppWF], 0
0x1802e47a6  call    cs:__imp_CoTaskMemFree
0x1802e47ad  nop     dword ptr [rax+rax+00h]
0x1802e47b2  lea     rcx, [rbp+arg_0]; this
0x1802e47b6  mov     [rbp+arg_18], 0
0x1802e47be  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1802e47c3  mov     eax, ebx
0x1802e47c5  add     rsp, 30h
0x1802e47c9  pop     r15
0x1802e47cb  pop     r14
0x1802e47cd  pop     r13
0x1802e47cf  pop     rdi
0x1802e47d0  pop     rsi
0x1802e47d1  pop     rbx
0x1802e47d2  pop     rbp
0x1802e47d3  retn
```
