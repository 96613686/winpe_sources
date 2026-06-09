# CWMVideoDecMediaObject::InitDecoderUsingSetTypes(void)

- ea: `0x180004ffc`
- end: `0x180005441`
- name: `?InitDecoderUsingSetTypes@CWMVideoDecMediaObject@@IEAAJXZ`
- size: `1093`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180002960`
- `0x180002be0`

## callees

- `0x180001420`
- `0x180002144`
- `0x180003534`
- `0x180003874`
- `0x180003b10`
- `0x180004ffc`
- `0x180006ca8`
- `0x18000aa50`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005341`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005341`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800052fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800053a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800052fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800053a7`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x1800051eb`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x1800051eb`

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
0x180004ffc  push    rbp
0x180004ffe  push    rbx
0x180004fff  push    rsi
0x180005000  push    rdi
0x180005001  push    r12
0x180005003  push    r13
0x180005005  push    r14
0x180005007  push    r15
0x180005009  lea     rbp, [rsp-1Fh]
0x18000500e  sub     rsp, 0C8h
0x180005015  mov     eax, [rcx+38h]
0x180005018  lea     rdx, [rcx+40h]; unsigned __int64
0x18000501c  xor     r15d, r15d
0x18000501f  mov     [rbp+57h+var_B0], 0
0x180005027  neg     eax
0x180005029  mov     [rbp+57h+var_C0], r15
0x18000502d  mov     eax, [rcx+3Ch]
0x180005030  mov     rbx, rcx
0x180005033  sbb     rdi, rdi
0x180005036  add     rcx, 98h
0x18000503d  neg     eax
0x18000503f  sbb     r14, r14
0x180005042  and     r14, rcx
0x180005045  and     rdi, rdx
0x180005048  jz      loc_180005408
0x18000504e  test    r14, r14
0x180005051  jz      loc_180005408
0x180005057  xor     edx, edx; Val
0x180005059  mov     [rbp+57h+var_A0.rcSource.left], r15d
0x18000505d  lea     r8d, [r15+54h]; Size
0x180005061  lea     rcx, [rbp+57h+var_A0.rcSource.top]; void *
0x180005065  call    memset_0
0x18000506a  mov     rcx, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180005071  cmp     [rdi+2Ch], rcx
0x180005075  jnz     short loc_1800050B6
0x180005077  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18000507e  cmp     [rdi+34h], rax
0x180005082  jnz     short loc_1800050B6
0x180005084  mov     rdx, [rdi+50h]; struct _MFVIDEOFORMAT *
0x180005088  lea     rcx, [rbp+57h+var_B0]; struct tagVIDEOINFOHEADER **
0x18000508c  call    ?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)
0x180005091  mov     esi, eax
0x180005093  test    eax, eax
0x180005095  js      loc_18000540D
0x18000509b  mov     rax, [rbp+57h+var_B0]
0x18000509f  mov     r12, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800050a6  mov     r13, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800050ad  mov     rdx, qword ptr cs:FORMAT_VideoInfo.Data1
0x1800050b4  jmp     short loc_18000511F
0x1800050b6  mov     rdx, qword ptr cs:FORMAT_VideoInfo.Data1
0x1800050bd  xor     esi, esi
0x1800050bf  cmp     [rdi+2Ch], rdx
0x1800050c3  jnz     short loc_1800050E6
0x1800050c5  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800050cc  cmp     [rdi+34h], rax
0x1800050d0  jnz     short loc_1800050E6
0x1800050d2  mov     rax, [rdi+50h]
0x1800050d6  mov     r12, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800050dd  mov     r13, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800050e4  jmp     short loc_18000511F
0x1800050e6  mov     r13, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800050ed  mov     r12, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800050f4  cmp     [rdi+2Ch], r13
0x1800050f8  jnz     short loc_18000511D
0x1800050fa  cmp     [rdi+34h], r12
0x1800050fe  jnz     short loc_18000511D
0x180005100  mov     rcx, [rdi+50h]; struct tagVIDEOINFOHEADER2 *
0x180005104  lea     rdx, [rbp+57h+var_A0]; struct tagVIDEOINFOHEADER *
0x180005108  call    ?ConvertVIH2ToVIH@@YAJPEAUtagVIDEOINFOHEADER2@@PEAUtagVIDEOINFOHEADER@@@Z; ConvertVIH2ToVIH(tagVIDEOINFOHEADER2 *,tagVIDEOINFOHEADER *)
0x18000510d  mov     esi, eax
0x18000510f  test    eax, eax
0x180005111  js      loc_18000542B
0x180005117  lea     rax, [rbp+57h+var_A0]
0x18000511b  jmp     short loc_1800050AD
0x18000511d  xor     eax, eax
0x18000511f  mov     [rbp+57h+var_B8], rax
0x180005123  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x18000512a  cmp     [r14+2Ch], rax
0x18000512e  jnz     short loc_180005161
0x180005130  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180005137  cmp     [r14+34h], rax
0x18000513b  jnz     short loc_180005161
0x18000513d  mov     rdx, [r14+50h]; struct _MFVIDEOFORMAT *
0x180005141  lea     rcx, [rbp+57h+var_C0]; struct tagVIDEOINFOHEADER **
0x180005145  call    ?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)
0x18000514a  mov     esi, eax
0x18000514c  test    eax, eax
0x18000514e  js      loc_180005402
0x180005154  mov     rax, [rbp+57h+var_C0]
0x180005158  mov     rdx, qword ptr cs:FORMAT_VideoInfo.Data1
0x18000515f  jmp     short loc_180005194
0x180005161  cmp     [r14+2Ch], rdx
0x180005165  jnz     short loc_18000517A
0x180005167  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x18000516e  cmp     [r14+34h], rax
0x180005172  jnz     short loc_18000517A
0x180005174  mov     rax, [r14+50h]
0x180005178  jmp     short loc_180005194
0x18000517a  cmp     [r14+2Ch], r13
0x18000517e  jnz     loc_1800053FD
0x180005184  cmp     [r14+34h], r12
0x180005188  jnz     loc_1800053FD
0x18000518e  mov     r15, [r14+50h]
0x180005192  xor     eax, eax
0x180005194  cmp     qword ptr [rbx+3C0h], 0
0x18000519c  jnz     loc_1800053F1
0x1800051a2  mov     rcx, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x1800051a9  cmp     [r14+2Ch], rcx
0x1800051ad  jnz     short loc_1800051BC
0x1800051af  mov     rcx, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x1800051b6  cmp     [r14+34h], rcx
0x1800051ba  jz      short loc_1800051CF
0x1800051bc  cmp     [r14+2Ch], rdx
0x1800051c0  jnz     short loc_1800051D9
0x1800051c2  mov     rcx, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800051c9  cmp     [r14+34h], rcx
0x1800051cd  jnz     short loc_1800051D9
0x1800051cf  lea     r12, [rax+34h]
0x1800051d3  lea     rsi, [rax+38h]
0x1800051d7  jmp     short loc_1800051E4
0x1800051d9  mov     rax, r15
0x1800051dc  lea     r12, [r15+4Ch]
0x1800051e0  lea     rsi, [r15+50h]
0x1800051e4  lea     r14, [rax+10h]
0x1800051e8  mov     rcx, r14; lprc
0x1800051eb  call    cs:__imp_IsRectEmpty
0x1800051f1  test    eax, eax
0x1800051f3  jz      short loc_180005214
0x1800051f5  mov     eax, [r12]
0x1800051f9  mov     [rbx+3D8h], eax
0x1800051ff  mov     eax, [rsi]
0x180005201  mov     [rbx+3DCh], eax
0x180005207  mov     qword ptr [rbx+3D0h], 0
0x180005212  jmp     short loc_180005252
0x180005214  mov     eax, [r14+8]
0x180005218  sub     eax, [r14]
0x18000521b  mov     [rbx+3D8h], eax
0x180005221  mov     eax, [r14+0Ch]
0x180005225  sub     eax, [r14+4]
0x180005229  mov     [rbx+3DCh], eax
0x18000522f  mov     eax, [r14]
0x180005232  mov     [rbx+3D0h], eax
0x180005238  mov     eax, [rsi]
0x18000523a  add     eax, [r14+0Ch]
0x18000523e  neg     eax
0x180005240  mov     [rbx+3D4h], eax
0x180005246  jns     short loc_180005252
0x180005248  mov     dword ptr [rbx+3D4h], 0
0x180005252  mov     eax, [rbx+3C8h]
0x180005258  mov     rsi, [rbp+57h+var_B8]
0x18000525c  test    eax, eax
0x18000525e  jnz     short loc_180005263
0x180005260  mov     eax, [rsi+34h]
0x180005263  mov     [rbx+3C8h], eax
0x180005269  mov     eax, [rbx+3CCh]
0x18000526f  test    eax, eax
0x180005271  jnz     short loc_180005276
0x180005273  mov     eax, [rsi+38h]
0x180005276  mov     [rbx+3CCh], eax
0x18000527c  mov     rax, [rdi+2Ch]
0x180005280  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180005287  jnz     short loc_18000529E
0x180005289  mov     rax, [rdi+34h]
0x18000528d  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180005294  jnz     short loc_18000529E
0x180005296  mov     r14d, 0B0h
0x18000529c  jmp     short loc_1800052E8
0x18000529e  mov     rax, [rdi+2Ch]
0x1800052a2  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800052a9  jnz     short loc_1800052C0
0x1800052ab  mov     rax, [rdi+34h]
0x1800052af  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800052b6  jnz     short loc_1800052C0
0x1800052b8  mov     r14d, 70h ; 'p'
0x1800052be  jmp     short loc_1800052E8
0x1800052c0  mov     rax, [rdi+2Ch]
0x1800052c4  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x1800052cb  jnz     loc_1800053EA
0x1800052d1  mov     rax, [rdi+34h]
0x1800052d5  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800052dc  jnz     loc_1800053EA
0x1800052e2  mov     r14d, 58h ; 'X'
0x1800052e8  mov     r12d, [rdi+48h]
0x1800052ec  lea     r15, [rbx+398h]
0x1800052f3  mov     r13, [rdi+50h]
0x1800052f7  mov     rcx, r15; lpCriticalSection
0x1800052fa  call    cs:__imp_EnterCriticalSection
0x180005300  cmp     qword ptr [rsi+28h], 0
0x180005305  jz      short loc_18000531E
0x180005307  movsd   xmm1, cs:__real@416312d000000000
0x18000530f  xorps   xmm0, xmm0
0x180005312  cvtsi2sd xmm0, qword ptr [rsi+28h]
0x180005318  divsd   xmm1, xmm0
0x18000531c  jmp     short loc_180005321
0x18000531e  xorps   xmm1, xmm1
0x180005321  mov     r9d, [rsi+38h]; int
0x180005325  mov     r8d, [rsi+34h]; int
0x180005329  mov     edx, [rdi+10h]; unsigned int
0x18000532c  movsd   [rsp+100h+var_E0], xmm1; double
0x180005332  call    ?CreateDecoder@CWMVideoDecMediaObject@@IEAAPEAVSessionFrameDecoder@@KJJNKPEAEK@Z; CWMVideoDecMediaObject::CreateDecoder(ulong,long,long,double,ulong,uchar *,ulong)
0x180005337  mov     rcx, r15; lpCriticalSection
0x18000533a  mov     [rbx+3C0h], rax
0x180005341  call    cs:__imp_LeaveCriticalSection
0x180005347  mov     rdx, [rbx+3C0h]
0x18000534e  test    rdx, rdx
0x180005351  jnz     short loc_18000535D
0x180005353  mov     esi, 8007000Eh
0x180005358  jmp     loc_180005402
0x18000535d  mov     ecx, [rdi+10h]
0x180005360  xor     esi, esi
0x180005362  call    NeedHeader
0x180005367  test    eax, eax
0x180005369  jz      loc_1800053F1
0x18000536f  cmp     [rdx+18h], rsi
0x180005373  jnz     short loc_18000537A
0x180005375  or      esi, 0FFFFFFFFh
0x180005378  jmp     short loc_1800053A4
0x18000537a  mov     rcx, [rdx+20h]
0x18000537e  sub     r12d, r14d
0x180005381  mov     eax, r14d
0x180005384  add     rax, r13
0x180005387  mov     [rcx], rax
0x18000538a  mov     [rcx+8], r12d
0x18000538e  mov     [rcx+0Ch], rsi
0x180005392  mov     [rcx+14h], esi
0x180005395  mov     rcx, [rdx+18h]; this
0x180005399  call    ?decodeVOLHead@CVideoObjectDecoder@@QEAAJXZ; CVideoObjectDecoder::decodeVOLHead(void)
0x18000539e  mov     esi, eax
0x1800053a0  test    eax, eax
0x1800053a2  jns     short loc_1800053F1
0x1800053a4  mov     rcx, r15; lpCriticalSection
0x1800053a7  call    cs:__imp_EnterCriticalSection
0x1800053ad  mov     rcx, [rbx+3C0h]
0x1800053b4  test    rcx, rcx
0x1800053b7  jz      short loc_1800053C9
0x1800053b9  mov     rax, [rcx]
0x1800053bc  mov     edx, 1
0x1800053c1  mov     rax, [rax]
0x1800053c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053c9  mov     rcx, r15; lpCriticalSection
0x1800053cc  mov     qword ptr [rbx+3C0h], 0
0x1800053d7  call    cs:__imp_LeaveCriticalSection
0x1800053dd  mov     qword ptr [rbx+3C8h], 0
0x1800053e8  jmp     short loc_180005402
0x1800053ea  mov     esi, 80004005h
0x1800053ef  jmp     short loc_180005402
0x1800053f1  mov     dword ptr [rbx+144h], 1
0x1800053fb  jmp     short loc_180005402
0x1800053fd  mov     esi, 80040205h
0x180005402  mov     r15, [rbp+57h+var_C0]
0x180005406  jmp     short loc_18000540D
0x180005408  mov     esi, 80040203h
0x18000540d  mov     rax, [rbp+57h+var_B0]
0x180005411  test    rax, rax
0x180005414  jz      short loc_18000541E
0x180005416  mov     rcx, rax; void *
0x180005419  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000541e  test    r15, r15
0x180005421  jz      short loc_18000542B
0x180005423  mov     rcx, r15; void *
0x180005426  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000542b  mov     eax, esi
0x18000542d  add     rsp, 0C8h
0x180005434  pop     r15
0x180005436  pop     r14
0x180005438  pop     r13
0x18000543a  pop     r12
0x18000543c  pop     rdi
0x18000543d  pop     rsi
0x18000543e  pop     rbx
0x18000543f  pop     rbp
0x180005440  retn
```
