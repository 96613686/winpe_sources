# CAACDecTransform::OnInputTypeChanged(void)

- ea: `0x180042270`
- end: `0x1800427a8`
- name: `?OnInputTypeChanged@CAACDecTransform@@MEAAJXZ`
- size: `1336`
- prototype: `__int64 __fastcall(CAACDecTransform *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180003af0`
- `0x180004fe0`
- `0x180030924`
- `0x180042270`
- `0x18004cf10`
- `0x18004cf1c`
- `0x1800960c0`

## import_xrefs

- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x1800422ed`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x1800422ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042787`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042787`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAACDecTransform::OnInputTypeChanged(CAACDecTransform *this)
{
  TraceLoggingHelperBase *v2; // r14
  IMFMediaType *v3; // rcx
  HRESULT v4; // edi
  WAVEFORMATEX *v5; // rcx
  __int16 v6; // dx
  DWORD nSamplesPerSec; // eax
  unsigned int *v8; // rsi
  _DWORD *v9; // rdi
  unsigned int v10; // r8d
  unsigned int v11; // edx
  int v12; // ecx
  int v13; // eax
  DWORD v14; // r9d
  int i; // ecx
  __int64 v16; // rdx
  _DWORD *v17; // rdi
  void *v18; // rcx
  void *v19; // r8
  int v20; // ebp
  unsigned int v21; // ecx
  _BYTE *v22; // rdx
  WAVEFORMATEX *ppWF; // [rsp+90h] [rbp+8h] BYREF

  v2 = (CAACDecTransform *)((char *)this + 246640);
  TraceLoggingHelperBase::TraceVA(
    (CAACDecTransform *)((char *)this + 246640),
    4u,
    "CAACDecTransform::OnInputTypeChanged",
    0x419u,
    "CAACDecTransform::OnInputTypeChanged()");
  ppWF = 0;
  *((_DWORD *)this + 61524) = 0;
  v3 = (IMFMediaType *)*((_QWORD *)this + 5);
  if ( !v3 )
  {
    v4 = -1072861856;
    goto LABEL_79;
  }
  v4 = MFCreateWaveFormatExFromMFMediaType(v3, &ppWF, 0, 0);
  if ( v4 >= 0 )
  {
    v5 = ppWF;
    switch ( ppWF->wFormatTag )
    {
      case 0xFFu:
        *((_DWORD *)this + 61524) = 5;
        break;
      case 0x1600u:
        goto LABEL_14;
      case 0x1610u:
        v6 = *((_WORD *)this + 123103);
        switch ( v6 )
        {
          case 0:
            *((_DWORD *)this + 61524) = 2;
            goto LABEL_16;
          case 1:
LABEL_14:
            *((_DWORD *)this + 61524) = 3;
            break;
          case 3:
            *((_DWORD *)this + 61524) = 4;
            break;
          default:
            TraceLoggingHelperBase::TraceVA(
              v2,
              4u,
              "CAACDecTransform::OnInputTypeChanged",
              0x449u,
              "CAACDecTransform::OnInputTypeChanged() Payload type must be 0, 1 or 3. Reject input media type");
            v4 = -1072875843;
            goto LABEL_79;
        }
        break;
      default:
        TraceLoggingHelperBase::TraceVA(
          v2,
          4u,
          "CAACDecTransform::OnInputTypeChanged",
          0x457u,
          "CAACDecTransform::OnInputTypeChanged() Unrecognized wave format tag. Reject input media type");
        v4 = -1072875852;
        goto LABEL_79;
    }
LABEL_16:
    if ( v4 )
      goto LABEL_79;
    nSamplesPerSec = v5->nSamplesPerSec;
    *((_DWORD *)this + 61513) = nSamplesPerSec;
    *((_DWORD *)this + 61525) = nSamplesPerSec;
    LOWORD(nSamplesPerSec) = v5->nChannels;
    *((_WORD *)this + 123028) = nSamplesPerSec;
    *((_WORD *)this + 123030) = nSamplesPerSec;
    v8 = (unsigned int *)((char *)this + 246072);
    v9 = (_DWORD *)((char *)this + 246220);
    if ( (*(unsigned int (__fastcall **)(_QWORD, const GUID *, char *))(**((_QWORD **)this + 5) + 56LL))(
           *((_QWORD *)this + 5),
           &MF_MT_AUDIO_CHANNEL_MASK,
           (char *)this + 246072) )
    {
      if ( *v9 )
      {
        v10 = *((_DWORD *)this + 61625);
        *v8 = v10;
      }
      else
      {
        *v8 = 0;
        v10 = 0;
      }
    }
    else
    {
      v10 = *v8;
    }
    *((_DWORD *)this + 61517) = v10;
    if ( !*v9 )
    {
LABEL_41:
      if ( !*((_DWORD *)this + 61525) )
        *((_DWORD *)this + 61525) = 48000;
      if ( !*((_WORD *)this + 123030) )
        *((_WORD *)this + 123030) = 2;
      for ( i = 0; v10; v10 >>= 1 )
        i += v10 & 1;
      v16 = *((unsigned __int16 *)this + 123030);
      if ( i != (_DWORD)v16
        || *((_DWORD *)this + 61517) != 3
        && *((_DWORD *)this + 61517) != 4
        && *((_DWORD *)this + 61517) != 7
        && *((_DWORD *)this + 61517) != 51
        && *((_DWORD *)this + 61517) != 55
        && *((_DWORD *)this + 61517) != 63
        && *((_DWORD *)this + 61517) != 259
        && *((_DWORD *)this + 61517) != 263 )
      {
        *((_DWORD *)this + 61517) = dword_1800B6000[v16];
      }
      *((_DWORD *)this + 64050) = 0;
      if ( *((_WORD *)this + 123028) > 2u )
      {
        v17 = (_DWORD *)((char *)this + 256216);
        if ( (*(int (__fastcall **)(_QWORD, const GUID *, char *))(**((_QWORD **)this + 5) + 112LL))(
               *((_QWORD *)this + 5),
               &MF_MT_MPEG4_SAMPLE_DESCRIPTION,
               (char *)this + 256216) >= 0 )
        {
          if ( *v17 )
          {
            v18 = (void *)*((_QWORD *)this + 32026);
            if ( v18 )
            {
              operator delete(v18);
              *((_QWORD *)this + 32026) = 0;
            }
            v19 = operator new[]((unsigned int)*v17);
            *((_QWORD *)this + 32026) = v19;
            if ( v19 )
            {
              v20 = *((unsigned __int16 *)this + 123030);
              if ( (*(int (__fastcall **)(_QWORD, const GUID *, void *, _QWORD, char *))(**((_QWORD **)this + 5) + 120LL))(
                     *((_QWORD *)this + 5),
                     &MF_MT_MPEG4_SAMPLE_DESCRIPTION,
                     v19,
                     (unsigned int)*v17,
                     (char *)this + 256216) >= 0 )
              {
                v21 = 4 * v20 + 16;
                if ( *v17 > v21 )
                {
                  v22 = (_BYTE *)(*((_QWORD *)this + 32026) + *v17 - v21);
                  if ( v22 )
                  {
                    if ( *v22 == 83 && v22[1] == 65 && v22[2] == 51 && v22[3] == 68 )
                      *((_DWORD *)this + 64050) = 1;
                  }
                }
              }
            }
          }
        }
      }
      if ( *((_DWORD *)this + 61524) != 2 )
      {
        if ( *((_DWORD *)this + 61524) == 3 )
        {
          *((_DWORD *)this + 61532) = 2;
          goto LABEL_77;
        }
        if ( *((_DWORD *)this + 61524) == 4 )
        {
          *((_DWORD *)this + 61532) = 10;
          goto LABEL_77;
        }
      }
      *((_DWORD *)this + 61532) = 0;
LABEL_77:
      v4 = CAACDecTransform::_ConfigOutputTypes((CAACDecTransform *)((char *)this - 24));
      if ( v4 >= 0 )
        CAACDec::CloseUpAACDec((CAACDecTransform *)((char *)this + 152));
      goto LABEL_79;
    }
    v11 = *((_DWORD *)this + 61558);
    *((_DWORD *)this + 61525) = v11;
    if ( *((_DWORD *)this + 61556) == 42 )
    {
      *((_WORD *)this + 123030) = dword_1800B5F20[2
                                                * *(int *)&byte_1800B5E60[8 * *((int *)this + 61564)
                                                                        + (-(__int64)(*((_DWORD *)this + 61519) == 0) & 4)]];
      goto LABEL_41;
    }
    *((_DWORD *)this + 61513) = v11;
    v12 = *((_DWORD *)this + 61562);
    if ( v12 == 1 )
    {
      v13 = *((_DWORD *)this + 61561);
      goto LABEL_27;
    }
    if ( v12 == -1 && ppWF->wFormatTag == 255 && (v14 = ppWF->nSamplesPerSec, v14 == 2 * *((_DWORD *)this + 61558)) )
    {
      *((_DWORD *)this + 61525) = v14;
    }
    else if ( ppWF->wFormatTag == 5648 && v11 <= 0x5DC0 && !*((_DWORD *)this + 64032) )
    {
      v13 = 2 * v11;
LABEL_27:
      *((_DWORD *)this + 61525) = v13;
      if ( v10 == 4 )
      {
        if ( *((_WORD *)this + 123030) == 1 )
        {
          *((_WORD *)this + 123030) = 2;
          *((_DWORD *)this + 61517) = 3;
          v10 = 3;
        }
        else
        {
          v10 = 4;
        }
      }
    }
    if ( *((_DWORD *)this + 61563) == 1 )
    {
      *((_WORD *)this + 123030) = 2;
      *((_DWORD *)this + 61517) = 3;
      v10 = 3;
    }
    goto LABEL_41;
  }
LABEL_79:
  TraceLoggingHelperBase::TraceVA(
    v2,
    4u,
    "CAACDecTransform::OnInputTypeChanged",
    0x51Du,
    "CAACDecTransform::OnInputTypeChanged() m_wOutputAudioChannelCount = %d, m_dwOutSamplesPerSec=%d, m_dwOutputChannelMask=%d",
    *((unsigned __int16 *)this + 123030),
    *((_DWORD *)this + 61525),
    *((_DWORD *)this + 61517));
  if ( v4 )
    TraceLoggingHelperBase::TraceVA(
      v2,
      2u,
      "CAACDecTransform::OnInputTypeChanged",
      0x51Eu,
      "Error %08X returned: File: %s, Line: %d",
      v4,
      "avcore\\codecdsp\\audio\\aacdec\\current\\mft\\aacdectransformxheaac.cpp",
      1310);
  CoTaskMemFree(ppWF);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180042270  push    rbx
0x180042272  push    rbp
0x180042273  push    rsi
0x180042274  push    rdi
0x180042275  push    r12
0x180042277  push    r13
0x180042279  push    r14
0x18004227b  push    r15
0x18004227d  sub     rsp, 48h
0x180042281  mov     rbx, rcx
0x180042284  lea     r14, [rcx+3C370h]
0x18004228b  lea     rax, aCaacdectransfo_41; "CAACDecTransform::OnInputTypeChanged()"
0x180042292  mov     [rsp+88h+Format], rax; Format
0x180042297  mov     r9d, 419h; unsigned int
0x18004229d  lea     r8, aCaacdectransfo_61; "CAACDecTransform::OnInputTypeChanged"
0x1800422a4  mov     r12d, 4
0x1800422aa  mov     edx, r12d; unsigned __int8
0x1800422ad  mov     rcx, r14; this
0x1800422b0  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800422b5  xor     r15d, r15d
0x1800422b8  mov     [rsp+88h+ppWF], r15
0x1800422c0  mov     [rbx+3C150h], r15d
0x1800422c7  mov     rcx, [rbx+28h]; pMFType
0x1800422cb  lea     r13d, [r12-2]
0x1800422d0  test    rcx, rcx
0x1800422d3  jnz     short loc_1800422DF
0x1800422d5  mov     edi, 0C00D6D60h
0x1800422da  jmp     loc_1800426FE
0x1800422df  xor     r9d, r9d; Flags
0x1800422e2  xor     r8d, r8d; pcbSize
0x1800422e5  lea     rdx, [rsp+88h+ppWF]; ppWF
0x1800422ed  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x1800422f4  nop     dword ptr [rax+rax+00h]
0x1800422f9  mov     edi, eax
0x1800422fb  test    eax, eax
0x1800422fd  js      loc_1800426FE
0x180042303  mov     rcx, [rsp+88h+ppWF]
0x18004230b  movzx   eax, word ptr [rcx]
0x18004230e  mov     ebp, 3
0x180042313  lea     r8d, [rbp-2]
0x180042317  sub     eax, 0FFh
0x18004231c  jz      loc_1800423C0
0x180042322  sub     eax, 1501h
0x180042327  jz      loc_1800423B8
0x18004232d  cmp     eax, 10h
0x180042330  jz      short loc_180042360
0x180042332  lea     rax, aCaacdectransfo_64; "CAACDecTransform::OnInputTypeChanged() "...
0x180042339  mov     [rsp+88h+Format], rax; Format
0x18004233e  mov     r9d, 457h; unsigned int
0x180042344  lea     r8, aCaacdectransfo_61; "CAACDecTransform::OnInputTypeChanged"
0x18004234b  mov     edx, r12d; unsigned __int8
0x18004234e  mov     rcx, r14; this
0x180042351  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180042356  mov     edi, 0C00D36B4h
0x18004235b  jmp     loc_1800426FE
0x180042360  movzx   edx, word ptr [rbx+3C1BEh]
0x180042367  cmp     r15w, dx
0x18004236b  jnz     short loc_180042376
0x18004236d  mov     [rbx+3C150h], r13d
0x180042374  jmp     short loc_1800423CA
0x180042376  cmp     r8w, dx
0x18004237a  jz      short loc_1800423B8
0x18004237c  cmp     bp, dx
0x18004237f  jnz     short loc_18004238A
0x180042381  mov     [rbx+3C150h], r12d
0x180042388  jmp     short loc_1800423CA
0x18004238a  lea     rax, aCaacdectransfo_62; "CAACDecTransform::OnInputTypeChanged() "...
0x180042391  mov     [rsp+88h+Format], rax; Format
0x180042396  mov     r9d, 449h; unsigned int
0x18004239c  lea     r8, aCaacdectransfo_61; "CAACDecTransform::OnInputTypeChanged"
0x1800423a3  mov     edx, r12d; unsigned __int8
0x1800423a6  mov     rcx, r14; this
0x1800423a9  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800423ae  mov     edi, 0C00D36BDh
0x1800423b3  jmp     loc_1800426FE
0x1800423b8  mov     [rbx+3C150h], ebp
0x1800423be  jmp     short loc_1800423CA
0x1800423c0  mov     dword ptr [rbx+3C150h], 5
0x1800423ca  test    edi, edi
0x1800423cc  jnz     loc_1800426FE
0x1800423d2  mov     eax, [rcx+4]
0x1800423d5  mov     [rbx+3C124h], eax
0x1800423db  mov     [rbx+3C154h], eax
0x1800423e1  movzx   eax, word ptr [rcx+2]
0x1800423e5  mov     [rbx+3C128h], ax
0x1800423ec  mov     [rbx+3C12Ch], ax
0x1800423f3  mov     rcx, [rbx+28h]
0x1800423f7  lea     rsi, [rbx+3C138h]
0x1800423fe  lea     rdi, [rbx+3C1CCh]
0x180042405  mov     rax, [rcx]
0x180042408  mov     r8, rsi
0x18004240b  lea     rdx, MF_MT_AUDIO_CHANNEL_MASK
0x180042412  mov     rax, [rax+38h]
0x180042416  call    cs:__guard_dispatch_icall_fptr
0x18004241c  test    eax, eax
0x18004241e  jnz     short loc_180042425
0x180042420  mov     r8d, [rsi]
0x180042423  jmp     short loc_18004243C
0x180042425  cmp     [rdi], r15d
0x180042428  jz      short loc_180042436
0x18004242a  mov     r8d, [rbx+3C2E4h]
0x180042431  mov     [rsi], r8d
0x180042434  jmp     short loc_18004243C
0x180042436  mov     [rsi], r15d
0x180042439  mov     r8d, r15d
0x18004243c  mov     [rbx+3C134h], r8d
0x180042443  lea     r11, __ImageBase
0x18004244a  mov     r10d, 1
0x180042450  cmp     [rdi], r15d
0x180042453  jz      loc_180042554
0x180042459  mov     edx, [rbx+3C1D8h]
0x18004245f  mov     [rbx+3C154h], edx
0x180042465  cmp     dword ptr [rbx+3C1D0h], 2Ah ; '*'
0x18004246c  jnz     short loc_1800424A7
0x18004246e  movsxd  rdx, dword ptr [rbx+3C1F0h]
0x180042475  mov     eax, [rbx+3C13Ch]
0x18004247b  neg     eax
0x18004247d  sbb     rcx, rcx
0x180042480  not     rcx
0x180042483  and     rcx, r12
0x180042486  lea     rax, [rcx+rdx*8]
0x18004248a  movsxd  rax, dword ptr [rax+r11+0B5E60h]
0x180042492  movzx   eax, word ptr ds:rva dword_1800B5F20[r11+rax*8]
0x18004249b  mov     [rbx+3C12Ch], ax
0x1800424a2  jmp     loc_180042554
0x1800424a7  mov     [rbx+3C124h], edx
0x1800424ad  mov     ecx, [rbx+3C1E8h]
0x1800424b3  cmp     ecx, r10d
0x1800424b6  jnz     short loc_1800424E6
0x1800424b8  mov     eax, [rbx+3C1E4h]
0x1800424be  cmp     r8d, r12d
0x1800424c1  mov     [rbx+3C154h], eax
0x1800424c7  jnz     short loc_18004253A
0x1800424c9  cmp     r10w, [rbx+3C12Ch]
0x1800424d1  jnz     short loc_180042537
0x1800424d3  mov     [rbx+3C12Ch], r13w
0x1800424db  mov     [rbx+3C134h], ebp
0x1800424e1  mov     r8d, ebp
0x1800424e4  jmp     short loc_18004253A
0x1800424e6  mov     rax, [rsp+88h+ppWF]
0x1800424ee  cmp     ecx, 0FFFFFFFFh
0x1800424f1  jnz     short loc_180042517
0x1800424f3  mov     ecx, 0FFh
0x1800424f8  cmp     cx, [rax]
0x1800424fb  jnz     short loc_180042517
0x1800424fd  mov     r9d, [rax+4]
0x180042501  mov     ecx, [rbx+3C1D8h]
0x180042507  add     ecx, ecx
0x180042509  cmp     r9d, ecx
0x18004250c  jnz     short loc_180042517
0x18004250e  mov     [rbx+3C154h], r9d
0x180042515  jmp     short loc_18004253A
0x180042517  mov     ecx, 1610h
0x18004251c  cmp     cx, [rax]
0x18004251f  jnz     short loc_18004253A
0x180042521  cmp     edx, 5DC0h
0x180042527  ja      short loc_18004253A
0x180042529  cmp     [rbx+3E880h], r15d
0x180042530  jnz     short loc_18004253A
0x180042532  lea     eax, [rdx+rdx]
0x180042535  jmp     short loc_1800424BE
0x180042537  mov     r8d, r12d
0x18004253a  cmp     [rbx+3C1ECh], r10d
0x180042541  jnz     short loc_180042554
0x180042543  mov     [rbx+3C12Ch], r13w
0x18004254b  mov     [rbx+3C134h], ebp
0x180042551  mov     r8d, ebp
0x180042554  cmp     [rbx+3C154h], r15d
0x18004255b  jnz     short loc_180042567
0x18004255d  mov     dword ptr [rbx+3C154h], 0BB80h
0x180042567  cmp     [rbx+3C12Ch], r15w
0x18004256f  jnz     short loc_180042579
0x180042571  mov     [rbx+3C12Ch], r13w
0x180042579  mov     ecx, r15d
0x18004257c  test    r8d, r8d
0x18004257f  jz      short loc_18004258E
0x180042581  mov     eax, r8d
0x180042584  and     eax, r10d
0x180042587  add     ecx, eax
0x180042589  shr     r8d, 1
0x18004258c  jnz     short loc_180042581
0x18004258e  movzx   edx, word ptr [rbx+3C12Ch]
0x180042595  cmp     ecx, edx
0x180042597  jnz     short loc_1800425C8
0x180042599  mov     ecx, [rbx+3C134h]
0x18004259f  sub     ecx, ebp
0x1800425a1  jz      short loc_1800425D6
0x1800425a3  sub     ecx, 1
0x1800425a6  jz      short loc_1800425D6
0x1800425a8  sub     ecx, ebp
0x1800425aa  jz      short loc_1800425D6
0x1800425ac  sub     ecx, 2Ch ; ','
0x1800425af  jz      short loc_1800425D6
0x1800425b1  sub     ecx, r12d
0x1800425b4  jz      short loc_1800425D6
0x1800425b6  sub     ecx, 8
0x1800425b9  jz      short loc_1800425D6
0x1800425bb  sub     ecx, 0C4h
0x1800425c1  jz      short loc_1800425D6
0x1800425c3  cmp     ecx, r12d
0x1800425c6  jz      short loc_1800425D6
0x1800425c8  mov     eax, ds:rva dword_1800B6000[r11+rdx*4]
0x1800425d0  mov     [rbx+3C134h], eax
0x1800425d6  mov     [rbx+3E8C8h], r15d
0x1800425dd  cmp     [rbx+3C128h], r13w
0x1800425e5  jbe     loc_1800426B2
0x1800425eb  mov     rcx, [rbx+28h]
0x1800425ef  lea     rdi, [rbx+3E8D8h]
0x1800425f6  mov     rax, [rcx]
0x1800425f9  mov     r8, rdi
0x1800425fc  lea     rdx, MF_MT_MPEG4_SAMPLE_DESCRIPTION
0x180042603  mov     rax, [rax+70h]
0x180042607  call    cs:__guard_dispatch_icall_fptr
0x18004260d  test    eax, eax
0x18004260f  js      loc_1800426B2
0x180042615  cmp     [rdi], r15d
0x180042618  jz      loc_1800426B2
0x18004261e  mov     rcx, [rbx+3E8D0h]; Block
0x180042625  test    rcx, rcx
0x180042628  jz      short loc_180042636
0x18004262a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004262f  mov     [rbx+3E8D0h], r15
0x180042636  mov     ecx, [rdi]; unsigned __int64
0x180042638  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004263d  mov     r8, rax
0x180042640  mov     [rbx+3E8D0h], rax
0x180042647  test    rax, rax
0x18004264a  jz      short loc_1800426B2
0x18004264c  movzx   ebp, word ptr [rbx+3C12Ch]
0x180042653  mov     rcx, [rbx+28h]
0x180042657  mov     rdx, [rcx]
0x18004265a  mov     rax, [rdx+78h]
0x18004265e  mov     [rsp+88h+Format], rdi
0x180042663  mov     r9d, [rdi]
0x180042666  lea     rdx, MF_MT_MPEG4_SAMPLE_DESCRIPTION
0x18004266d  call    cs:__guard_dispatch_icall_fptr
0x180042673  test    eax, eax
0x180042675  js      short loc_1800426B2
0x180042677  lea     ecx, ds:10h[rbp*4]
0x18004267e  mov     eax, [rdi]
0x180042680  cmp     eax, ecx
0x180042682  jbe     short loc_1800426B2
0x180042684  sub     eax, ecx
0x180042686  mov     edx, eax
0x180042688  add     rdx, [rbx+3E8D0h]
0x18004268f  jz      short loc_1800426B2
0x180042691  cmp     byte ptr [rdx], 53h ; 'S'
0x180042694  jnz     short loc_1800426B2
0x180042696  cmp     byte ptr [rdx+1], 41h ; 'A'
0x18004269a  jnz     short loc_1800426B2
0x18004269c  cmp     byte ptr [rdx+2], 33h ; '3'
0x1800426a0  jnz     short loc_1800426B2
0x1800426a2  cmp     byte ptr [rdx+3], 44h ; 'D'
0x1800426a6  jnz     short loc_1800426B2
0x1800426a8  mov     dword ptr [rbx+3E8C8h], 1
0x1800426b2  mov     ecx, [rbx+3C150h]
0x1800426b8  sub     ecx, r13d
0x1800426bb  jz      short loc_1800426DC
0x1800426bd  sub     ecx, 1
0x1800426c0  jz      short loc_1800426D3
0x1800426c2  cmp     ecx, 1
0x1800426c5  jnz     short loc_1800426DC
0x1800426c7  mov     dword ptr [rbx+3C170h], 0Ah
0x1800426d1  jmp     short loc_1800426E3
0x1800426d3  mov     [rbx+3C170h], r13d
0x1800426da  jmp     short loc_1800426E3
0x1800426dc  mov     [rbx+3C170h], r15d
0x1800426e3  lea     rcx, [rbx-18h]; this
0x1800426e7  call    ?_ConfigOutputTypes@CAACDecTransform@@AEAAJXZ; CAACDecTransform::_ConfigOutputTypes(void)
0x1800426ec  mov     edi, eax
0x1800426ee  test    eax, eax
0x1800426f0  js      short loc_1800426FE
0x1800426f2  lea     rcx, [rbx+98h]; this
0x1800426f9  call    ?CloseUpAACDec@CAACDec@@QEAAXXZ; CAACDec::CloseUpAACDec(void)
0x1800426fe  movzx   ecx, word ptr [rbx+3C12Ch]
0x180042705  mov     eax, [rbx+3C134h]
0x18004270b  mov     [rsp+88h+var_50], eax
0x18004270f  mov     eax, [rbx+3C154h]
0x180042715  mov     dword ptr [rsp+88h+var_58], eax
0x180042719  mov     [rsp+88h+var_60], ecx
0x18004271d  lea     rax, aCaacdectransfo_67; "CAACDecTransform::OnInputTypeChanged() "...
0x180042724  mov     [rsp+88h+Format], rax; Format
0x180042729  mov     r9d, 51Dh; unsigned int
0x18004272f  lea     r8, aCaacdectransfo_61; "CAACDecTransform::OnInputTypeChanged"
0x180042736  mov     edx, r12d; unsigned __int8
0x180042739  mov     rcx, r14; this
0x18004273c  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180042741  test    edi, edi
0x180042743  jz      short loc_18004277F
0x180042745  mov     r9d, 51Eh; unsigned int
0x18004274b  mov     [rsp+88h+var_50], r9d
0x180042750  lea     rax, aAvcoreCodecdsp_0; "avcore\\codecdsp\\audio\\aacdec\\curren"...
0x180042757  mov     [rsp+88h+var_58], rax
0x18004275c  mov     [rsp+88h+var_60], edi
0x180042760  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x180042767  mov     [rsp+88h+Format], rax; Format
0x18004276c  lea     r8, aCaacdectransfo_61; "CAACDecTransform::OnInputTypeChanged"
0x180042773  mov     edx, r13d; unsigned __int8
0x180042776  mov     rcx, r14; this
0x180042779  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
  ... truncated ...
```
