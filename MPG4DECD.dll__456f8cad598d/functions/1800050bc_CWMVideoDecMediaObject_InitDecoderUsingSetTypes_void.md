# CWMVideoDecMediaObject::InitDecoderUsingSetTypes(void)

- ea: `0x1800050bc`
- end: `0x180005501`
- name: `?InitDecoderUsingSetTypes@CWMVideoDecMediaObject@@IEAAJXZ`
- size: `1093`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180002a20`
- `0x180002ca0`

## callees

- `0x180001450`
- `0x180002174`
- `0x1800035f4`
- `0x180003934`
- `0x180003bd0`
- `0x1800050bc`
- `0x180006d68`
- `0x18000ab10`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005401`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005497`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005401`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005497`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800053ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005467`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800053ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005467`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x1800052ab`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x1800052ab`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::InitDecoderUsingSetTypes(struct _RTL_CRITICAL_SECTION *this)
{
  int OwningThread; // eax
  char *p_LockSemaphore; // rdx
  struct tagVIDEOINFOHEADER *v3; // r15
  unsigned __int64 v5; // r14
  unsigned __int64 v6; // rdi
  int v7; // esi
  tagVIDEOINFOHEADER *v8; // rax
  __int64 v9; // r12
  __int64 v10; // r13
  struct tagVIDEOINFOHEADER *v11; // rax
  LONG *p_biWidth; // r12
  _DWORD *p_biHeight; // rsi
  RECT *p_rcTarget; // r14
  bool v15; // sf
  LONG LockCount; // eax
  tagVIDEOINFOHEADER *v17; // rsi
  LONG RecursionCount; // eax
  unsigned int v19; // r14d
  int v20; // r12d
  __int64 v21; // r13
  CWMVideoDecMediaObject *v22; // rcx
  double v23; // xmm1_8
  __int64 v24; // r8
  __int64 v25; // rcx
  void (__fastcall ***DebugInfo)(_QWORD, _QWORD); // rcx
  unsigned int v28; // [rsp+28h] [rbp-81h]
  unsigned __int8 *v29; // [rsp+30h] [rbp-79h]
  unsigned int v30; // [rsp+38h] [rbp-71h]
  struct tagVIDEOINFOHEADER *v31; // [rsp+40h] [rbp-69h] BYREF
  tagVIDEOINFOHEADER *v32; // [rsp+48h] [rbp-61h]
  struct tagVIDEOINFOHEADER *v33; // [rsp+50h] [rbp-59h] BYREF
  tagVIDEOINFOHEADER v34; // [rsp+60h] [rbp-49h] BYREF

  OwningThread = (int)this[1].OwningThread;
  p_LockSemaphore = (char *)&this[1].LockSemaphore;
  v3 = 0;
  v33 = 0;
  v31 = 0;
  v5 = (unsigned __int64)&this[3].SpinCount & -(__int64)(HIDWORD(this[1].OwningThread) != 0);
  v6 = (unsigned __int64)&this[1].LockSemaphore & -(__int64)(OwningThread != 0);
  if ( !v6 || !v5 )
  {
    v7 = -2147220989;
    goto LABEL_67;
  }
  v34.rcSource.left = 0;
  memset_0(&v34.rcSource.top, 0, 0x54u);
  if ( *(_QWORD *)(v6 + 44) != *(_QWORD *)&FORMAT_MFVideoFormat.Data1
    || *(_QWORD *)(v6 + 52) != *(_QWORD *)FORMAT_MFVideoFormat.Data4 )
  {
    p_LockSemaphore = *(char **)&FORMAT_VideoInfo.Data1;
    v7 = 0;
    if ( *(_QWORD *)(v6 + 44) == *(_QWORD *)&FORMAT_VideoInfo.Data1
      && *(_QWORD *)(v6 + 52) == *(_QWORD *)FORMAT_VideoInfo.Data4 )
    {
      v8 = *(tagVIDEOINFOHEADER **)(v6 + 80);
      v9 = *(_QWORD *)FORMAT_VideoInfo2.Data4;
      v10 = *(_QWORD *)&FORMAT_VideoInfo2.Data1;
      goto LABEL_16;
    }
    v10 = *(_QWORD *)&FORMAT_VideoInfo2.Data1;
    v9 = *(_QWORD *)FORMAT_VideoInfo2.Data4;
    if ( *(_QWORD *)(v6 + 44) != *(_QWORD *)&FORMAT_VideoInfo2.Data1
      || *(_QWORD *)(v6 + 52) != *(_QWORD *)FORMAT_VideoInfo2.Data4 )
    {
      v8 = 0;
      goto LABEL_16;
    }
    v7 = ConvertVIH2ToVIH(*(struct tagVIDEOINFOHEADER2 **)(v6 + 80), &v34);
    if ( v7 < 0 )
      return (unsigned int)v7;
    v8 = &v34;
LABEL_7:
    p_LockSemaphore = *(char **)&FORMAT_VideoInfo.Data1;
LABEL_16:
    v32 = v8;
    if ( *(_QWORD *)(v5 + 44) == *(_QWORD *)&FORMAT_MFVideoFormat.Data1
      && *(_QWORD *)(v5 + 52) == *(_QWORD *)FORMAT_MFVideoFormat.Data4 )
    {
      v7 = ConvertMFVideoFormatToVIH2(&v31, *(struct _MFVIDEOFORMAT **)(v5 + 80));
      if ( v7 < 0 )
      {
LABEL_65:
        v3 = v31;
        goto LABEL_67;
      }
      v11 = v31;
      p_LockSemaphore = *(char **)&FORMAT_VideoInfo.Data1;
    }
    else if ( *(char **)(v5 + 44) == p_LockSemaphore && *(_QWORD *)(v5 + 52) == *(_QWORD *)FORMAT_VideoInfo.Data4 )
    {
      v11 = *(struct tagVIDEOINFOHEADER **)(v5 + 80);
    }
    else
    {
      if ( *(_QWORD *)(v5 + 44) != v10 || *(_QWORD *)(v5 + 52) != v9 )
      {
        v7 = -2147220987;
        goto LABEL_65;
      }
      v3 = *(struct tagVIDEOINFOHEADER **)(v5 + 80);
      v11 = 0;
    }
    if ( !this[24].DebugInfo )
    {
      if ( *(_QWORD *)(v5 + 44) == *(_QWORD *)&FORMAT_MFVideoFormat.Data1
        && *(_QWORD *)(v5 + 52) == *(_QWORD *)FORMAT_MFVideoFormat.Data4
        || *(char **)(v5 + 44) == p_LockSemaphore && *(_QWORD *)(v5 + 52) == *(_QWORD *)FORMAT_VideoInfo.Data4 )
      {
        p_biWidth = &v11->bmiHeader.biWidth;
        p_biHeight = &v11->bmiHeader.biHeight;
      }
      else
      {
        v11 = v3;
        p_biWidth = &v3->bmiHeader.biYPelsPerMeter;
        p_biHeight = &v3->bmiHeader.biClrUsed;
      }
      p_rcTarget = &v11->rcTarget;
      if ( IsRectEmpty(&v11->rcTarget) )
      {
        LODWORD(this[24].LockSemaphore) = *p_biWidth;
        HIDWORD(this[24].LockSemaphore) = *p_biHeight;
        this[24].OwningThread = 0;
      }
      else
      {
        LODWORD(this[24].LockSemaphore) = p_rcTarget->right - p_rcTarget->left;
        HIDWORD(this[24].LockSemaphore) = p_rcTarget->bottom - p_rcTarget->top;
        LODWORD(this[24].OwningThread) = p_rcTarget->left;
        v15 = -(p_rcTarget->bottom + *p_biHeight) < 0;
        HIDWORD(this[24].OwningThread) = -(p_rcTarget->bottom + *p_biHeight);
        if ( v15 )
          HIDWORD(this[24].OwningThread) = 0;
      }
      LockCount = this[24].LockCount;
      v17 = v32;
      if ( !LockCount )
        LockCount = v32->bmiHeader.biWidth;
      this[24].LockCount = LockCount;
      RecursionCount = this[24].RecursionCount;
      if ( !RecursionCount )
        RecursionCount = v17->bmiHeader.biHeight;
      this[24].RecursionCount = RecursionCount;
      if ( *(_QWORD *)(v6 + 44) == *(_QWORD *)&FORMAT_MFVideoFormat.Data1
        && *(_QWORD *)(v6 + 52) == *(_QWORD *)FORMAT_MFVideoFormat.Data4 )
      {
        v19 = 176;
      }
      else if ( *(_QWORD *)(v6 + 44) == *(_QWORD *)&FORMAT_VideoInfo2.Data1
             && *(_QWORD *)(v6 + 52) == *(_QWORD *)FORMAT_VideoInfo2.Data4 )
      {
        v19 = 112;
      }
      else
      {
        if ( *(_QWORD *)(v6 + 44) != *(_QWORD *)&FORMAT_VideoInfo.Data1
          || *(_QWORD *)(v6 + 52) != *(_QWORD *)FORMAT_VideoInfo.Data4 )
        {
          v7 = -2147467259;
          goto LABEL_65;
        }
        v19 = 88;
      }
      v20 = *(_DWORD *)(v6 + 72);
      v21 = *(_QWORD *)(v6 + 80);
      EnterCriticalSection(this + 23);
      if ( v17->AvgTimePerFrame )
        v23 = 10000000.0 / (double)(int)v17->AvgTimePerFrame;
      else
        v23 = 0.0;
      this[24].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)CWMVideoDecMediaObject::CreateDecoder(
                                                          v22,
                                                          *(_DWORD *)(v6 + 16),
                                                          v17->bmiHeader.biWidth,
                                                          v17->bmiHeader.biHeight,
                                                          v23,
                                                          v28,
                                                          v29,
                                                          v30);
      LeaveCriticalSection(this + 23);
      p_LockSemaphore = (char *)this[24].DebugInfo;
      if ( !p_LockSemaphore )
      {
        v7 = -2147024882;
        goto LABEL_65;
      }
      v7 = 0;
      if ( (unsigned int)NeedHeader(*(unsigned int *)(v6 + 16), p_LockSemaphore, v24) )
      {
        if ( !*((_QWORD *)p_LockSemaphore + 3) )
        {
          v7 = -1;
LABEL_59:
          EnterCriticalSection(this + 23);
          DebugInfo = (void (__fastcall ***)(_QWORD, _QWORD))this[24].DebugInfo;
          if ( DebugInfo )
            (**DebugInfo)(DebugInfo, 1);
          this[24].DebugInfo = 0;
          LeaveCriticalSection(this + 23);
          *(_QWORD *)&this[24].LockCount = 0;
          goto LABEL_65;
        }
        v25 = *((_QWORD *)p_LockSemaphore + 4);
        *(_QWORD *)v25 = v21 + v19;
        *(_DWORD *)(v25 + 8) = v20 - v19;
        *(_QWORD *)(v25 + 12) = 0;
        *(_DWORD *)(v25 + 20) = 0;
        v7 = CVideoObjectDecoder::decodeVOLHead(*((CVideoObjectDecoder **)p_LockSemaphore + 3));
        if ( v7 < 0 )
          goto LABEL_59;
      }
    }
    HIDWORD(this[8].DebugInfo) = 1;
    goto LABEL_65;
  }
  v7 = ConvertMFVideoFormatToVIH2(&v33, *(struct _MFVIDEOFORMAT **)(v6 + 80));
  if ( v7 >= 0 )
  {
    v8 = v33;
    v9 = *(_QWORD *)FORMAT_VideoInfo2.Data4;
    v10 = *(_QWORD *)&FORMAT_VideoInfo2.Data1;
    goto LABEL_7;
  }
LABEL_67:
  if ( v33 )
    operator delete(v33, (unsigned __int64)p_LockSemaphore);
  if ( v3 )
    operator delete(v3, (unsigned __int64)p_LockSemaphore);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800050bc  push    rbp
0x1800050be  push    rbx
0x1800050bf  push    rsi
0x1800050c0  push    rdi
0x1800050c1  push    r12
0x1800050c3  push    r13
0x1800050c5  push    r14
0x1800050c7  push    r15
0x1800050c9  lea     rbp, [rsp-1Fh]
0x1800050ce  sub     rsp, 0C8h
0x1800050d5  mov     eax, [rcx+38h]
0x1800050d8  lea     rdx, [rcx+40h]; unsigned __int64
0x1800050dc  xor     r15d, r15d
0x1800050df  mov     [rbp+57h+var_B0], 0
0x1800050e7  neg     eax
0x1800050e9  mov     [rbp+57h+var_C0], r15
0x1800050ed  mov     eax, [rcx+3Ch]
0x1800050f0  mov     rbx, rcx
0x1800050f3  sbb     rdi, rdi
0x1800050f6  add     rcx, 98h
0x1800050fd  neg     eax
0x1800050ff  sbb     r14, r14
0x180005102  and     r14, rcx
0x180005105  and     rdi, rdx
0x180005108  jz      loc_1800054C8
0x18000510e  test    r14, r14
0x180005111  jz      loc_1800054C8
0x180005117  xor     edx, edx; Val
0x180005119  mov     [rbp+57h+var_A0.rcSource.left], r15d
0x18000511d  lea     r8d, [r15+54h]; Size
0x180005121  lea     rcx, [rbp+57h+var_A0.rcSource.top]; void *
0x180005125  call    memset_0
0x18000512a  mov     rcx, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180005131  cmp     [rdi+2Ch], rcx
0x180005135  jnz     short loc_180005176
0x180005137  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18000513e  cmp     [rdi+34h], rax
0x180005142  jnz     short loc_180005176
0x180005144  mov     rdx, [rdi+50h]; struct _MFVIDEOFORMAT *
0x180005148  lea     rcx, [rbp+57h+var_B0]; struct tagVIDEOINFOHEADER **
0x18000514c  call    ?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)
0x180005151  mov     esi, eax
0x180005153  test    eax, eax
0x180005155  js      loc_1800054CD
0x18000515b  mov     rax, [rbp+57h+var_B0]
0x18000515f  mov     r12, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180005166  mov     r13, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18000516d  mov     rdx, qword ptr cs:FORMAT_VideoInfo.Data1
0x180005174  jmp     short loc_1800051DF
0x180005176  mov     rdx, qword ptr cs:FORMAT_VideoInfo.Data1
0x18000517d  xor     esi, esi
0x18000517f  cmp     [rdi+2Ch], rdx
0x180005183  jnz     short loc_1800051A6
0x180005185  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x18000518c  cmp     [rdi+34h], rax
0x180005190  jnz     short loc_1800051A6
0x180005192  mov     rax, [rdi+50h]
0x180005196  mov     r12, qword ptr cs:FORMAT_VideoInfo2.Data4
0x18000519d  mov     r13, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800051a4  jmp     short loc_1800051DF
0x1800051a6  mov     r13, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800051ad  mov     r12, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800051b4  cmp     [rdi+2Ch], r13
0x1800051b8  jnz     short loc_1800051DD
0x1800051ba  cmp     [rdi+34h], r12
0x1800051be  jnz     short loc_1800051DD
0x1800051c0  mov     rcx, [rdi+50h]; struct tagVIDEOINFOHEADER2 *
0x1800051c4  lea     rdx, [rbp+57h+var_A0]; struct tagVIDEOINFOHEADER *
0x1800051c8  call    ?ConvertVIH2ToVIH@@YAJPEAUtagVIDEOINFOHEADER2@@PEAUtagVIDEOINFOHEADER@@@Z; ConvertVIH2ToVIH(tagVIDEOINFOHEADER2 *,tagVIDEOINFOHEADER *)
0x1800051cd  mov     esi, eax
0x1800051cf  test    eax, eax
0x1800051d1  js      loc_1800054EB
0x1800051d7  lea     rax, [rbp+57h+var_A0]
0x1800051db  jmp     short loc_18000516D
0x1800051dd  xor     eax, eax
0x1800051df  mov     [rbp+57h+var_B8], rax
0x1800051e3  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x1800051ea  cmp     [r14+2Ch], rax
0x1800051ee  jnz     short loc_180005221
0x1800051f0  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x1800051f7  cmp     [r14+34h], rax
0x1800051fb  jnz     short loc_180005221
0x1800051fd  mov     rdx, [r14+50h]; struct _MFVIDEOFORMAT *
0x180005201  lea     rcx, [rbp+57h+var_C0]; struct tagVIDEOINFOHEADER **
0x180005205  call    ?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)
0x18000520a  mov     esi, eax
0x18000520c  test    eax, eax
0x18000520e  js      loc_1800054C2
0x180005214  mov     rax, [rbp+57h+var_C0]
0x180005218  mov     rdx, qword ptr cs:FORMAT_VideoInfo.Data1
0x18000521f  jmp     short loc_180005254
0x180005221  cmp     [r14+2Ch], rdx
0x180005225  jnz     short loc_18000523A
0x180005227  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x18000522e  cmp     [r14+34h], rax
0x180005232  jnz     short loc_18000523A
0x180005234  mov     rax, [r14+50h]
0x180005238  jmp     short loc_180005254
0x18000523a  cmp     [r14+2Ch], r13
0x18000523e  jnz     loc_1800054BD
0x180005244  cmp     [r14+34h], r12
0x180005248  jnz     loc_1800054BD
0x18000524e  mov     r15, [r14+50h]
0x180005252  xor     eax, eax
0x180005254  cmp     qword ptr [rbx+3C0h], 0
0x18000525c  jnz     loc_1800054B1
0x180005262  mov     rcx, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180005269  cmp     [r14+2Ch], rcx
0x18000526d  jnz     short loc_18000527C
0x18000526f  mov     rcx, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180005276  cmp     [r14+34h], rcx
0x18000527a  jz      short loc_18000528F
0x18000527c  cmp     [r14+2Ch], rdx
0x180005280  jnz     short loc_180005299
0x180005282  mov     rcx, qword ptr cs:FORMAT_VideoInfo.Data4
0x180005289  cmp     [r14+34h], rcx
0x18000528d  jnz     short loc_180005299
0x18000528f  lea     r12, [rax+34h]
0x180005293  lea     rsi, [rax+38h]
0x180005297  jmp     short loc_1800052A4
0x180005299  mov     rax, r15
0x18000529c  lea     r12, [r15+4Ch]
0x1800052a0  lea     rsi, [r15+50h]
0x1800052a4  lea     r14, [rax+10h]
0x1800052a8  mov     rcx, r14; lprc
0x1800052ab  call    cs:__imp_IsRectEmpty
0x1800052b1  test    eax, eax
0x1800052b3  jz      short loc_1800052D4
0x1800052b5  mov     eax, [r12]
0x1800052b9  mov     [rbx+3D8h], eax
0x1800052bf  mov     eax, [rsi]
0x1800052c1  mov     [rbx+3DCh], eax
0x1800052c7  mov     qword ptr [rbx+3D0h], 0
0x1800052d2  jmp     short loc_180005312
0x1800052d4  mov     eax, [r14+8]
0x1800052d8  sub     eax, [r14]
0x1800052db  mov     [rbx+3D8h], eax
0x1800052e1  mov     eax, [r14+0Ch]
0x1800052e5  sub     eax, [r14+4]
0x1800052e9  mov     [rbx+3DCh], eax
0x1800052ef  mov     eax, [r14]
0x1800052f2  mov     [rbx+3D0h], eax
0x1800052f8  mov     eax, [rsi]
0x1800052fa  add     eax, [r14+0Ch]
0x1800052fe  neg     eax
0x180005300  mov     [rbx+3D4h], eax
0x180005306  jns     short loc_180005312
0x180005308  mov     dword ptr [rbx+3D4h], 0
0x180005312  mov     eax, [rbx+3C8h]
0x180005318  mov     rsi, [rbp+57h+var_B8]
0x18000531c  test    eax, eax
0x18000531e  jnz     short loc_180005323
0x180005320  mov     eax, [rsi+34h]
0x180005323  mov     [rbx+3C8h], eax
0x180005329  mov     eax, [rbx+3CCh]
0x18000532f  test    eax, eax
0x180005331  jnz     short loc_180005336
0x180005333  mov     eax, [rsi+38h]
0x180005336  mov     [rbx+3CCh], eax
0x18000533c  mov     rax, [rdi+2Ch]
0x180005340  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180005347  jnz     short loc_18000535E
0x180005349  mov     rax, [rdi+34h]
0x18000534d  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180005354  jnz     short loc_18000535E
0x180005356  mov     r14d, 0B0h
0x18000535c  jmp     short loc_1800053A8
0x18000535e  mov     rax, [rdi+2Ch]
0x180005362  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180005369  jnz     short loc_180005380
0x18000536b  mov     rax, [rdi+34h]
0x18000536f  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180005376  jnz     short loc_180005380
0x180005378  mov     r14d, 70h ; 'p'
0x18000537e  jmp     short loc_1800053A8
0x180005380  mov     rax, [rdi+2Ch]
0x180005384  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x18000538b  jnz     loc_1800054AA
0x180005391  mov     rax, [rdi+34h]
0x180005395  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x18000539c  jnz     loc_1800054AA
0x1800053a2  mov     r14d, 58h ; 'X'
0x1800053a8  mov     r12d, [rdi+48h]
0x1800053ac  lea     r15, [rbx+398h]
0x1800053b3  mov     r13, [rdi+50h]
0x1800053b7  mov     rcx, r15; lpCriticalSection
0x1800053ba  call    cs:__imp_EnterCriticalSection
0x1800053c0  cmp     qword ptr [rsi+28h], 0
0x1800053c5  jz      short loc_1800053DE
0x1800053c7  movsd   xmm1, cs:__real@416312d000000000
0x1800053cf  xorps   xmm0, xmm0
0x1800053d2  cvtsi2sd xmm0, qword ptr [rsi+28h]
0x1800053d8  divsd   xmm1, xmm0
0x1800053dc  jmp     short loc_1800053E1
0x1800053de  xorps   xmm1, xmm1
0x1800053e1  mov     r9d, [rsi+38h]; int
0x1800053e5  mov     r8d, [rsi+34h]; int
0x1800053e9  mov     edx, [rdi+10h]; unsigned int
0x1800053ec  movsd   [rsp+100h+var_E0], xmm1; double
0x1800053f2  call    ?CreateDecoder@CWMVideoDecMediaObject@@IEAAPEAVSessionFrameDecoder@@KJJNKPEAEK@Z; CWMVideoDecMediaObject::CreateDecoder(ulong,long,long,double,ulong,uchar *,ulong)
0x1800053f7  mov     rcx, r15; lpCriticalSection
0x1800053fa  mov     [rbx+3C0h], rax
0x180005401  call    cs:__imp_LeaveCriticalSection
0x180005407  mov     rdx, [rbx+3C0h]
0x18000540e  test    rdx, rdx
0x180005411  jnz     short loc_18000541D
0x180005413  mov     esi, 8007000Eh
0x180005418  jmp     loc_1800054C2
0x18000541d  mov     ecx, [rdi+10h]
0x180005420  xor     esi, esi
0x180005422  call    NeedHeader
0x180005427  test    eax, eax
0x180005429  jz      loc_1800054B1
0x18000542f  cmp     [rdx+18h], rsi
0x180005433  jnz     short loc_18000543A
0x180005435  or      esi, 0FFFFFFFFh
0x180005438  jmp     short loc_180005464
0x18000543a  mov     rcx, [rdx+20h]
0x18000543e  sub     r12d, r14d
0x180005441  mov     eax, r14d
0x180005444  add     rax, r13
0x180005447  mov     [rcx], rax
0x18000544a  mov     [rcx+8], r12d
0x18000544e  mov     [rcx+0Ch], rsi
0x180005452  mov     [rcx+14h], esi
0x180005455  mov     rcx, [rdx+18h]; this
0x180005459  call    ?decodeVOLHead@CVideoObjectDecoder@@QEAAJXZ; CVideoObjectDecoder::decodeVOLHead(void)
0x18000545e  mov     esi, eax
0x180005460  test    eax, eax
0x180005462  jns     short loc_1800054B1
0x180005464  mov     rcx, r15; lpCriticalSection
0x180005467  call    cs:__imp_EnterCriticalSection
0x18000546d  mov     rcx, [rbx+3C0h]
0x180005474  test    rcx, rcx
0x180005477  jz      short loc_180005489
0x180005479  mov     rax, [rcx]
0x18000547c  mov     edx, 1
0x180005481  mov     rax, [rax]
0x180005484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005489  mov     rcx, r15; lpCriticalSection
0x18000548c  mov     qword ptr [rbx+3C0h], 0
0x180005497  call    cs:__imp_LeaveCriticalSection
0x18000549d  mov     qword ptr [rbx+3C8h], 0
0x1800054a8  jmp     short loc_1800054C2
0x1800054aa  mov     esi, 80004005h
0x1800054af  jmp     short loc_1800054C2
0x1800054b1  mov     dword ptr [rbx+144h], 1
0x1800054bb  jmp     short loc_1800054C2
0x1800054bd  mov     esi, 80040205h
0x1800054c2  mov     r15, [rbp+57h+var_C0]
0x1800054c6  jmp     short loc_1800054CD
0x1800054c8  mov     esi, 80040203h
0x1800054cd  mov     rax, [rbp+57h+var_B0]
0x1800054d1  test    rax, rax
0x1800054d4  jz      short loc_1800054DE
0x1800054d6  mov     rcx, rax; void *
0x1800054d9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800054de  test    r15, r15
0x1800054e1  jz      short loc_1800054EB
0x1800054e3  mov     rcx, r15; void *
0x1800054e6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800054eb  mov     eax, esi
0x1800054ed  add     rsp, 0C8h
0x1800054f4  pop     r15
0x1800054f6  pop     r14
0x1800054f8  pop     r13
0x1800054fa  pop     r12
0x1800054fc  pop     rdi
0x1800054fd  pop     rsi
0x1800054fe  pop     rbx
0x1800054ff  pop     rbp
0x180005500  retn
```
