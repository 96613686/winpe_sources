# SensorActivity::MergeActivityReport(IMFSensorActivityReportInternal *)

- ea: `0x180013580`
- end: `0x1800137e7`
- name: `?MergeActivityReport@SensorActivity@@UEAAJPEAUIMFSensorActivityReportInternal@@@Z`
- size: `615`
- prototype: `__int64 __fastcall(SensorActivity *__hidden this, struct IMFSensorActivityReportInternal *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005fa0`
- `0x180013580`
- `0x180015354`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800135b3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800135b3`

## pseudocode

```c
__int64 __fastcall SensorActivity::MergeActivityReport(const WCHAR *this, const WCHAR *a2)
{
  unsigned int v4; // edi
  char *v6; // r12
  unsigned int v7; // ebp
  __m128i *v8; // r9
  char *i; // rdx
  unsigned int v10; // ecx
  __m128i v11; // xmm1
  unsigned int v12; // r9d
  unsigned int v13; // r11d
  int v14; // r13d
  char *v15; // rdx
  char *j; // r8
  unsigned int v17; // ecx
  __int16 v18; // ax
  signed __int64 v19; // rax
  __int64 v20; // rdx
  __m128i v21[5]; // [rsp+30h] [rbp-58h] BYREF

  if ( !a2 )
  {
    v4 = -2147467261;
    if ( !g_wppLevels )
      return v4;
    v20 = 28;
LABEL_39:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_5376953b7b7f340645b111671399d7a0_Traceguids, this, v4);
    return v4;
  }
  if ( CompareStringOrdinal(this + 6, -1, a2 + 6, -1, 1) != 2 )
    return (unsigned int)-1072875819;
  v4 = 0;
  v6 = (char *)(a2 + 528);
  v7 = 0;
  while ( 2 )
  {
    if ( v7 < *((_DWORD *)v6 + 92) )
    {
      v8 = 0;
      for ( i = v6; i; i = (char *)*((_QWORD *)i + 45) )
      {
        v10 = *((_DWORD *)i + 2);
        if ( v7 >= v10 && v7 < v10 + 20 )
        {
          if ( ((unsigned __int8)i[((unsigned __int64)(v7 - v10) >> 3) + 32]
              & *((_BYTE *)&CTSparseBlock<unsigned long,ProfileEntry *,20,1>::s_bSingleBitMasks
                + (((_BYTE)v7 - (_BYTE)v10) & 7))) != 0 )
            v8 = (__m128i *)&i[16 * (v7 - v10) + 40];
          break;
        }
      }
      v11 = *v8;
      v12 = 0;
      v13 = *((_DWORD *)this + 356);
      v14 = _mm_cvtsi128_si32(_mm_srli_si128(v11, 4));
      v21[0] = v11;
      while ( v12 < v13 )
      {
        v15 = 0;
        for ( j = (char *)(this + 528); j; j = (char *)*((_QWORD *)j + 45) )
        {
          v17 = *((_DWORD *)j + 2);
          if ( v12 >= v17 && v12 < v17 + 20 )
          {
            v6 = (char *)(a2 + 528);
            if ( ((unsigned __int8)j[((unsigned __int64)(v12 - v17) >> 3) + 32]
                & *((_BYTE *)&CTSparseBlock<unsigned long,ProfileEntry *,20,1>::s_bSingleBitMasks
                  + (((_BYTE)v12 - (_BYTE)v17) & 7))) != 0 )
              v15 = &j[16 * (v12 - v17) + 40];
            break;
          }
        }
        if ( *((_DWORD *)v15 + 1) == v14 && *((_WORD *)v15 + 1) == (unsigned __int16)_mm_extract_epi16(v11, 1) )
        {
          v18 = _mm_cvtsi128_si32(v11);
          if ( v18 == *(_WORD *)v15 )
          {
            v19 = _mm_srli_si128(v11, 8).m128i_u64[0];
            if ( *((_QWORD *)v15 + 1) < v19 )
              v19 = *((_QWORD *)v15 + 1);
            *((_QWORD *)v15 + 1) = v19;
          }
          else if ( v18 == 1 )
          {
            *((_QWORD *)v15 + 1) = _mm_srli_si128(v11, 8).m128i_u64[0];
            *(_WORD *)v15 = 1;
          }
          if ( *((_DWORD *)this + 263) != *((_DWORD *)a2 + 263) )
            *((_DWORD *)this + 263) = 2;
          goto LABEL_34;
        }
        ++v12;
      }
      if ( *((_DWORD *)this + 263) != *((_DWORD *)a2 + 263) )
        *((_DWORD *)this + 263) = 2;
      if ( (int)CTSparseBlock<unsigned long,_WNF_KSCAMERA_PROCESSINFO,20,0>::SetValue(this + 528, v13, v21) >= 0 )
      {
        ++*((_DWORD *)this + 356);
LABEL_34:
        ++v7;
        continue;
      }
      v4 = -2147024882;
      if ( g_wppLevels )
      {
        v20 = 29;
        goto LABEL_39;
      }
    }
    return v4;
  }
}

```

## disassembly

```asm
0x180013580  push    rbx
0x180013582  push    rbp
0x180013583  push    rsi
0x180013584  push    rdi
0x180013585  push    r12
0x180013587  push    r13
0x180013589  push    r14
0x18001358b  push    r15
0x18001358d  sub     rsp, 48h
0x180013591  mov     r14, rdx
0x180013594  mov     rsi, rcx
0x180013597  test    rdx, rdx
0x18001359a  jz      short loc_1800135C5
0x18001359c  lea     r8, [rdx+0Ch]; lpString2
0x1800135a0  mov     ebx, 1
0x1800135a5  or      edx, 0FFFFFFFFh; cchCount1
0x1800135a8  mov     [rsp+88h+bIgnoreCase], ebx; bIgnoreCase
0x1800135ac  mov     r9d, edx; cchCount2
0x1800135af  add     rcx, 0Ch; lpString1
0x1800135b3  call    cs:__imp_CompareStringOrdinal
0x1800135b9  cmp     eax, 2
0x1800135bc  jz      short loc_1800135EE
0x1800135be  mov     edi, 0C00D36D5h
0x1800135c3  jmp     short loc_1800135DB
0x1800135c5  mov     edi, 80004003h
0x1800135ca  mov     ebx, 1
0x1800135cf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800135d5  jnb     loc_180013775
0x1800135db  mov     eax, edi
0x1800135dd  add     rsp, 48h
0x1800135e1  pop     r15
0x1800135e3  pop     r14
0x1800135e5  pop     r13
0x1800135e7  pop     r12
0x1800135e9  pop     rdi
0x1800135ea  pop     rsi
0x1800135eb  pop     rbp
0x1800135ec  pop     rbx
0x1800135ed  retn
0x1800135ee  xor     edi, edi
0x1800135f0  lea     r12, [r14+420h]
0x1800135f7  xor     ebp, ebp
0x1800135f9  lea     r10, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAVProfileEntry@@$0BE@$00@@0QBEB; uchar const near * const CTSparseBlock<ulong,ProfileEntry *,20,1>::s_bSingleBitMasks
0x180013600  cmp     ebp, [r12+170h]
0x180013608  jnb     short loc_1800135DB
0x18001360a  xor     r9d, r9d
0x18001360d  mov     rdx, r12
0x180013610  test    rdx, rdx
0x180013613  jz      short loc_180013651
0x180013615  mov     ecx, [rdx+8]
0x180013618  cmp     ebp, ecx
0x18001361a  jb      loc_18001375D
0x180013620  lea     eax, [rcx+14h]
0x180013623  cmp     ebp, eax
0x180013625  jnb     loc_18001375D
0x18001362b  mov     eax, ebp
0x18001362d  sub     eax, ecx
0x18001362f  mov     r8d, eax
0x180013632  mov     ecx, r8d
0x180013635  shr     rax, 3
0x180013639  and     ecx, 7
0x18001363c  mov     al, [rax+rdx+20h]
0x180013640  test    [rcx+r10], al
0x180013644  jz      short loc_180013651
0x180013646  shl     r8, 4
0x18001364a  lea     r9, [r8+28h]
0x18001364e  add     r9, rdx
0x180013651  movups  xmm1, xmmword ptr [r9]
0x180013655  lea     r15, [rsi+420h]
0x18001365c  xor     r9d, r9d
0x18001365f  mov     r11d, [r15+170h]
0x180013666  movdqa  xmm0, xmm1
0x18001366a  psrldq  xmm0, 4
0x18001366f  movd    r13d, xmm0
0x180013674  movups  [rsp+88h+var_58], xmm1
0x180013679  cmp     r9d, r11d
0x18001367c  jb      short loc_1800136B5
0x18001367e  mov     eax, [r14+41Ch]
0x180013685  cmp     [rsi+41Ch], eax
0x18001368b  jnz     loc_1800137C5
0x180013691  lea     r8, [rsp+88h+var_58]
0x180013696  mov     edx, r11d
0x180013699  mov     rcx, r15
0x18001369c  call    ?SetValue@?$CTSparseBlock@KU_WNF_KSCAMERA_PROCESSINFO@@$0BE@$0A@@@QEAAJKAEBU_WNF_KSCAMERA_PROCESSINFO@@@Z; CTSparseBlock<ulong,_WNF_KSCAMERA_PROCESSINFO,20,0>::SetValue(ulong,_WNF_KSCAMERA_PROCESSINFO const &)
0x1800136a1  test    eax, eax
0x1800136a3  js      loc_1800137D4
0x1800136a9  add     [r15+170h], ebx
0x1800136b0  jmp     loc_18001374E
0x1800136b5  xor     edx, edx
0x1800136b7  mov     r8, r15
0x1800136ba  test    r8, r8
0x1800136bd  jz      short loc_18001370E
0x1800136bf  mov     ecx, [r8+8]
0x1800136c3  cmp     r9d, ecx
0x1800136c6  jb      loc_180013769
0x1800136cc  lea     eax, [rcx+14h]
0x1800136cf  cmp     r9d, eax
0x1800136d2  jnb     loc_180013769
0x1800136d8  mov     eax, r9d
0x1800136db  lea     r12, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAVProfileEntry@@$0BE@$00@@0QBEB; uchar const near * const CTSparseBlock<ulong,ProfileEntry *,20,1>::s_bSingleBitMasks
0x1800136e2  sub     eax, ecx
0x1800136e4  mov     r10d, eax
0x1800136e7  mov     ecx, r10d
0x1800136ea  shr     rax, 3
0x1800136ee  and     ecx, 7
0x1800136f1  mov     al, [rax+r8+20h]
0x1800136f6  test    [rcx+r12], al
0x1800136fa  lea     r12, [r14+420h]
0x180013701  jz      short loc_18001370E
0x180013703  shl     r10, 4
0x180013707  lea     rdx, [r10+28h]
0x18001370b  add     rdx, r8
0x18001370e  cmp     [rdx+4], r13d
0x180013712  jnz     short loc_180013755
0x180013714  pextrw  eax, xmm1, 1
0x180013719  cmp     [rdx+2], ax
0x18001371d  jnz     short loc_180013755
0x18001371f  movd    eax, xmm1
0x180013723  cmp     ax, [rdx]
0x180013726  jnz     short loc_1800137A4
0x180013728  psrldq  xmm1, 8
0x18001372d  movq    rax, xmm1
0x180013732  cmp     [rdx+8], rax
0x180013736  cmovl   rax, [rdx+8]
0x18001373b  mov     [rdx+8], rax
0x18001373f  mov     eax, [r14+41Ch]
0x180013746  cmp     [rsi+41Ch], eax
0x18001374c  jnz     short loc_1800137B9
0x18001374e  add     ebp, ebx
0x180013750  jmp     loc_1800135F9
0x180013755  add     r9d, ebx
0x180013758  jmp     loc_180013679
0x18001375d  mov     rdx, [rdx+168h]
0x180013764  jmp     loc_180013610
0x180013769  mov     r8, [r8+168h]
0x180013770  jmp     loc_1800136BA
0x180013775  mov     edx, 1Ch
0x18001377a  jmp     short loc_180013781
0x18001377c  mov     edx, 1Dh
0x180013781  mov     rcx, cs:WPP_GLOBAL_Control
0x180013788  lea     r8, WPP_5376953b7b7f340645b111671399d7a0_Traceguids
0x18001378f  mov     r9, rsi
0x180013792  mov     [rsp+88h+bIgnoreCase], edi
0x180013796  mov     rcx, [rcx+10h]
0x18001379a  call    WPP_SF_qD
0x18001379f  jmp     loc_1800135DB
0x1800137a4  cmp     ax, bx
0x1800137a7  jnz     short loc_18001373F
0x1800137a9  psrldq  xmm1, 8
0x1800137ae  movq    qword ptr [rdx+8], xmm1
0x1800137b4  mov     [rdx], bx
0x1800137b7  jmp     short loc_18001373F
0x1800137b9  mov     dword ptr [rsi+41Ch], 2
0x1800137c3  jmp     short loc_18001374E
0x1800137c5  mov     dword ptr [rsi+41Ch], 2
0x1800137cf  jmp     loc_180013691
0x1800137d4  mov     edi, 8007000Eh
0x1800137d9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800137df  jb      loc_1800135DB
0x1800137e5  jmp     short loc_18001377C
```
