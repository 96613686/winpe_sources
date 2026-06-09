# CSceneAnalysisMFT::UpdateFormatInfo(_GUID)

- ea: `0x1800b0550`
- end: `0x1800b06f2`
- name: `?UpdateFormatInfo@CSceneAnalysisMFT@@EEAAJU_GUID@@@Z`
- size: `418`
- prototype: `int(CSceneAnalysisMFT *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000396d`
- `0x18000b490`
- `0x18000c0f8`
- `0x18002a9bc`
- `0x18002ae0c`
- `0x18002afd0`
- `0x1800b0550`
- `0x1800b15d0`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0641`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b0641`

## string_xrefs

- `0x1800b0562`: `CSceneAnalysisMFT::UpdateFormatInfo`
- `0x1800b0698`: `CSceneAnalysisMFT::UpdateFormatInfo`

## pseudocode

```c
__int64 __fastcall CSceneAnalysisMFT::UpdateFormatInfo(CSceneAnalysisMFT *this, struct _GUID *a2)
{
  unsigned __int8 v4; // si
  unsigned int v5; // ebp
  __int64 v6; // rcx
  unsigned __int8 v7; // dl
  int v8; // ebx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v13; // [rsp+50h] [rbp+8h] BYREF
  int v14; // [rsp+60h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v13, "CSceneAnalysisMFT::UpdateFormatInfo", 603);
  v4 = 16;
  if ( memcmp_0(a2, &MFVideoFormat_NV12, 0x10u) )
  {
    v5 = -1072875852;
    goto LABEL_26;
  }
  v6 = *((_QWORD *)this + 14);
  v5 = 0;
  *((_BYTE *)this + 432) = 1;
  *((_BYTE *)this + 473) = 1;
  v14 = 0;
  if ( !v6 )
    goto LABEL_26;
  if ( (*(unsigned int (__fastcall **)(__int64, const GUID *, int *))(*(_QWORD *)v6 + 56LL))(
         v6,
         &MF_MT_VIDEO_NOMINAL_RANGE,
         &v14)
    || !v14 )
  {
    goto LABEL_13;
  }
  switch ( v14 )
  {
    case 1:
      *((_BYTE *)this + 473) = 0;
      v4 = 0;
      v7 = -1;
      goto LABEL_15;
    case 2:
      goto LABEL_13;
    case 3:
      v4 = 48;
      v7 = -48;
      goto LABEL_14;
  }
  if ( v14 != 4 )
  {
LABEL_13:
    v7 = -21;
    goto LABEL_14;
  }
  v4 = 64;
  v7 = 127;
LABEL_14:
  *((_BYTE *)this + 473) = 1;
LABEL_15:
  v8 = CSceneAnalysisCore::ComputeHistogramLookup(v4, v7, (unsigned __int8 *)this + 474);
  if ( v8 < 0 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CSceneAnalysisMFT::UpdateFormatInfo", 652, v8);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_a042ef2f2a7a38ff6a18b622801eb737_Traceguids, this, v8);
  }
LABEL_26:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v13);
  return v5;
}

```

## disassembly

```asm
0x1800b0550  mov     [rsp+arg_8], rbx
0x1800b0555  push    rbp
0x1800b0556  push    rsi
0x1800b0557  push    rdi
0x1800b0558  sub     rsp, 30h
0x1800b055c  mov     rbx, rdx
0x1800b055f  mov     rdi, rcx
0x1800b0562  lea     rdx, aCsceneanalysis_12; "CSceneAnalysisMFT::UpdateFormatInfo"
0x1800b0569  mov     r8d, 25Bh; int
0x1800b056f  lea     rcx, [rsp+48h+arg_0]; this
0x1800b0574  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b0579  mov     esi, 10h
0x1800b057e  lea     rdx, MFVideoFormat_NV12; Buf2
0x1800b0585  mov     r8d, esi; Size
0x1800b0588  mov     rcx, rbx; Buf1
0x1800b058b  call    memcmp_0
0x1800b0590  test    eax, eax
0x1800b0592  jz      short loc_1800B059E
0x1800b0594  mov     ebp, 0C00D36B4h
0x1800b0599  jmp     loc_1800B06D9
0x1800b059e  mov     rcx, [rdi+70h]
0x1800b05a2  xor     ebp, ebp
0x1800b05a4  mov     byte ptr [rdi+1B0h], 1
0x1800b05ab  mov     byte ptr [rdi+1D9h], 1
0x1800b05b2  mov     [rsp+48h+arg_10], ebp
0x1800b05b6  test    rcx, rcx
0x1800b05b9  jz      loc_1800B06D9
0x1800b05bf  mov     rax, [rcx]
0x1800b05c2  lea     r8, [rsp+48h+arg_10]
0x1800b05c7  lea     rdx, MF_MT_VIDEO_NOMINAL_RANGE
0x1800b05ce  mov     rax, [rax+38h]
0x1800b05d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b05d7  test    eax, eax
0x1800b05d9  jnz     short loc_1800B0613
0x1800b05db  mov     ecx, [rsp+48h+arg_10]
0x1800b05df  test    ecx, ecx
0x1800b05e1  jz      short loc_1800B0613
0x1800b05e3  sub     ecx, 1
0x1800b05e6  jz      short loc_1800B0605
0x1800b05e8  sub     ecx, 1
0x1800b05eb  jz      short loc_1800B0613
0x1800b05ed  sub     ecx, 1
0x1800b05f0  jz      short loc_1800B05FE
0x1800b05f2  cmp     ecx, 1
0x1800b05f5  jnz     short loc_1800B0613
0x1800b05f7  mov     sil, 40h ; '@'
0x1800b05fa  mov     dl, 7Fh
0x1800b05fc  jmp     short loc_1800B0615
0x1800b05fe  mov     sil, 30h ; '0'
0x1800b0601  mov     dl, 0D0h
0x1800b0603  jmp     short loc_1800B0615
0x1800b0605  mov     [rdi+1D9h], bpl
0x1800b060c  xor     sil, sil
0x1800b060f  mov     dl, 0FFh
0x1800b0611  jmp     short loc_1800B061C
0x1800b0613  mov     dl, 0EBh; unsigned __int8
0x1800b0615  mov     byte ptr [rdi+1D9h], 1
0x1800b061c  lea     r8, [rdi+1DAh]; unsigned __int8 *
0x1800b0623  mov     cl, sil; unsigned __int8
0x1800b0626  call    ?ComputeHistogramLookup@CSceneAnalysisCore@@SAJEEPEAE@Z; CSceneAnalysisCore::ComputeHistogramLookup(uchar,uchar,uchar *)
0x1800b062b  mov     ebx, eax
0x1800b062d  test    eax, eax
0x1800b062f  jns     loc_1800B06D9
0x1800b0635  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b063c  test    rcx, rcx
0x1800b063f  jnz     short loc_1800B0682
0x1800b0641  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b0647  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b064e  mov     rcx, rax
0x1800b0651  test    rax, rax
0x1800b0654  jz      short loc_1800B0674
0x1800b0656  mov     rax, [rax]
0x1800b0659  mov     edx, 7F0h
0x1800b065e  mov     rax, [rax+8]
0x1800b0662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0667  test    eax, eax
0x1800b0669  jz      short loc_1800B0674
0x1800b066b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0672  jmp     short loc_1800B0682
0x1800b0674  lea     rcx, qword_18015FF10; this
0x1800b067b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b0682  cmp     [rcx+8], bpl
0x1800b0686  jz      short loc_1800B06AD
0x1800b0688  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b068d  cmp     [rax+7CCh], ebx
0x1800b0693  jz      short loc_1800B06AD
0x1800b0695  mov     r9d, ebx; int
0x1800b0698  lea     rdx, aCsceneanalysis_12; "CSceneAnalysisMFT::UpdateFormatInfo"
0x1800b069f  mov     r8d, 28Ch; int
0x1800b06a5  mov     rcx, rax; this
0x1800b06a8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b06ad  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800b06b2  cmp     al, 1
0x1800b06b4  jb      short loc_1800B06D9
0x1800b06b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b06bd  lea     r8, WPP_a042ef2f2a7a38ff6a18b622801eb737_Traceguids
0x1800b06c4  mov     edx, 52h ; 'R'
0x1800b06c9  mov     [rsp+48h+var_28], ebx
0x1800b06cd  mov     r9, rdi
0x1800b06d0  mov     rcx, [rcx+10h]
0x1800b06d4  call    WPP_SF_qD
0x1800b06d9  lea     rcx, [rsp+48h+arg_0]; this
0x1800b06de  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b06e3  mov     rbx, [rsp+48h+arg_8]
0x1800b06e8  mov     eax, ebp
0x1800b06ea  add     rsp, 30h
0x1800b06ee  pop     rdi
0x1800b06ef  pop     rsi
0x1800b06f0  pop     rbp
0x1800b06f1  retn
```
