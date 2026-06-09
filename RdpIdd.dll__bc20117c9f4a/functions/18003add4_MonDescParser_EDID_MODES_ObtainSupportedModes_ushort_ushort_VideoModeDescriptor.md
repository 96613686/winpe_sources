# MonDescParser::EDID_MODES::ObtainSupportedModes(ushort *,ushort *,_VideoModeDescriptor *)

- ea: `0x18003add4`
- end: `0x18003b350`
- name: `?ObtainSupportedModes@EDID_MODES@MonDescParser@@QEAAJPEAG0PEAU_VideoModeDescriptor@@@Z`
- size: `1404`
- prototype: `__int64 __fastcall(MonDescParser::EDID_MODES *__hidden this, unsigned __int16 *, unsigned __int16 *, struct _VideoModeDescriptor *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180036fcc`

## callees

- `0x180007b38`
- `0x180039e3c`
- `0x180039e88`
- `0x180039edc`
- `0x180039fe4`
- `0x18003a010`
- `0x18003a190`
- `0x18003a368`
- `0x18003a50c`
- `0x18003a77c`
- `0x18003a840`
- `0x18003abc4`
- `0x18003acfc`
- `0x18003add4`

## pseudocode

```c
signed int __fastcall MonDescParser::EDID_MODES::ObtainSupportedModes(
        MonDescParser::EDID_MODES *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct _VideoModeDescriptor *a4)
{
  unsigned __int16 *v4; // r13
  signed int result; // eax
  unsigned __int16 v7; // di
  int v8; // r15d
  int v9; // r14d
  unsigned __int16 v10; // si
  __int64 v11; // rbx
  bool v12; // r9
  unsigned __int16 v13; // r12
  struct _VideoModeDescriptor *v14; // r11
  __int64 v15; // r8
  int v16; // ecx
  unsigned __int16 i; // di
  __int64 v18; // rax
  char v19; // r13
  unsigned int v20; // esi
  struct _EDID_V1_CEA_861_DATA_HEADER *v21; // r14
  unsigned __int16 j; // di
  __int64 v23; // r9
  int v24; // r8d
  int v25; // edx
  __int64 v26; // rcx
  MonDescParser::EDID_PARSER **v27; // rsi
  int v28; // ecx
  __int64 *v29; // rax
  unsigned int v30; // r10d
  union _EDID_V1_BLOCK **IterAtElement; // rax
  unsigned __int16 k; // di
  struct _VideoModeDescriptor *v33; // r11
  struct _VideoModeDescriptor *v34; // r11
  unsigned int v35; // edi
  struct _VideoModeDescriptor *v36; // r11
  struct _EDID_V1_CEA_861_DATA_HEADER *v37; // r14
  const struct _EDID_V1_CEA_861_SHORT_VIDEO_DESC *v38; // r15
  unsigned int m; // esi
  unsigned int v40; // eax
  unsigned __int16 v41[2]; // [rsp+48h] [rbp-29h] BYREF
  unsigned __int16 v42[2]; // [rsp+4Ch] [rbp-25h] BYREF
  struct _VideoModeDescriptor *v43; // [rsp+50h] [rbp-21h]
  unsigned __int16 v44[2]; // [rsp+58h] [rbp-19h] BYREF
  unsigned __int16 v45; // [rsp+5Ch] [rbp-15h] BYREF
  unsigned __int16 v46[4]; // [rsp+60h] [rbp-11h] BYREF
  struct _EDID_V1_CEA_861_DATA_HEADER *v47[2]; // [rsp+68h] [rbp-9h] BYREF
  _OWORD v48[5]; // [rsp+78h] [rbp+7h] BYREF

  v4 = a3;
  if ( !a2 || (!a4 || !a3) && *a2 )
    return -1073741811;
  v47[0] = 0;
  v41[0] = 0;
  v45 = 0;
  v46[0] = 0;
  v42[0] = 0;
  v44[0] = 0;
  result = MonDescParser::EDID_MODES::GetModeCounts(this, v41, &v45, v46, v47, v42, v44);
  if ( result < 0 )
    return result;
  v7 = v41[0];
  if ( v41[0] > 0x11u )
    return -1071841278;
  v8 = v45;
  if ( v45 > 8u )
    return -1071841278;
  v9 = v46[0];
  if ( v46[0] > 6u )
    return -1071841278;
  v10 = v42[0];
  if ( v42[0] > 4u )
    return -1071841278;
  v11 = *a2;
  if ( (_WORD)v11 )
  {
    LOBYTE(v41[0]) = 0;
    memset_0(a4, 0, 56 * v11);
    *v4 = -1;
    v13 = 0;
    v43 = a4;
    v14 = a4;
    if ( (unsigned __int16)v11 < v7 )
    {
      LOBYTE(v41[0]) = 1;
      v7 = v11;
    }
    if ( v7 )
    {
      result = MonDescParser::EDID_MODES::ModesFromEstablishedTimings(this, v7, a4);
      if ( result < 0 )
        return result;
      v4 = a3;
      LOWORD(v11) = v11 - v7;
      v13 = v7;
      v14 = (struct _VideoModeDescriptor *)(v15 + 56LL * v7);
      v43 = v14;
    }
    if ( (unsigned __int16)v11 < v10 )
    {
      LOBYTE(v41[0]) = 1;
      v10 = v11;
    }
    *(_DWORD *)v42 = 0;
    LOWORD(v16) = 0;
    for ( i = 0; i < v10; *(_DWORD *)v42 = v16 )
    {
      if ( (unsigned __int16)v16 >= 4u )
        break;
      *(_QWORD *)v46 = 0;
      if ( MonDescParser::EDID_PARSER::GetDetTimParser(
             *(MonDescParser::EDID_PARSER **)this,
             (unsigned __int16)v16,
             (struct MonDescParser::EDID_PARSER_DETAILED_TIMING *)v46,
             v12) )
      {
        result = MonDescParser::EDID_MODES::ModeFromDetailedTimingBlock(
                   this,
                   (struct MonDescParser::EDID_PARSER_DETAILED_TIMING *)v46,
                   v14);
        if ( result == -1071841271 )
        {
          v14 = v43;
        }
        else
        {
          if ( result < 0 )
            return result;
          if ( !i )
            *v4 = v13;
          v14 = v43;
          if ( !v13
            || (v18 = MonDescParser::IndexOf<_VideoModeDescriptor *,_VideoModeDescriptor>(
                        a4,
                        (char *)a4 + 56 * v13,
                        v43),
                v18 == -1) )
          {
            LOWORD(v11) = v11 - 1;
            ++i;
            ++v13;
            v14 = (struct _VideoModeDescriptor *)((char *)v14 + 56);
            v43 = v14;
          }
          else if ( !i )
          {
            *v4 = v18;
          }
        }
      }
      HIWORD(v16) = v42[1];
      LOWORD(v16) = v42[0] + 1;
    }
    if ( (unsigned __int16)v11 >= (unsigned __int16)v8 )
    {
      if ( (unsigned __int16)v11 >= (unsigned int)(v8 + v9) )
      {
        v19 = v41[0];
      }
      else
      {
        v19 = 1;
        LOWORD(v9) = v11 - v8;
      }
    }
    else
    {
      v19 = 1;
      LOWORD(v8) = v11;
      LOWORD(v9) = 0;
    }
    v20 = (unsigned __int16)v8 + (unsigned __int16)v9;
    if ( v20 )
    {
      v21 = v47[0];
      for ( j = 0; j < v20; ++j )
      {
        v23 = **(_QWORD **)this;
        if ( j < (unsigned __int16)v8 )
        {
          *(_QWORD *)&v48[0] = v23 + 38 + 2LL * j;
          DWORD2(v48[0]) = *(unsigned __int8 *)(v23 + 18);
          HIDWORD(v48[0]) = *(unsigned __int8 *)(v23 + 19);
        }
        else
        {
          v24 = 0;
          v47[0] = (struct _EDID_V1_CEA_861_DATA_HEADER *)((char *)v21 + 2
                                                                       * (j - (unsigned __int64)(unsigned __int16)v8));
          do
          {
            v25 = *(unsigned __int8 *)((unsigned int)v24 + v23 + 18);
            v26 = 4 * v24++ + 8;
            *(_DWORD *)((char *)v47 + v26) = v25;
          }
          while ( v24 < 2 );
          v14 = v43;
          v48[0] = *(_OWORD *)v47;
        }
        result = MonDescParser::EDID_MODES::ModeFromStandardTimingBlock(
                   this,
                   (struct MonDescParser::EDID_PARSER_STANDARD_TIMING *)v48,
                   j >= (unsigned __int16)v8,
                   v14);
        if ( result == -1071841276 )
        {
          v14 = v43;
        }
        else
        {
          if ( result < 0 )
            return result;
          v14 = v43;
          if ( !v13
            || MonDescParser::IndexOf<_VideoModeDescriptor *,_VideoModeDescriptor>(a4, (char *)a4 + 56 * v13, v43) == -1 )
          {
            LOWORD(v11) = v11 - 1;
            ++v13;
            v14 = (struct _VideoModeDescriptor *)((char *)v14 + 56);
            v43 = v14;
          }
        }
      }
    }
    v27 = (MonDescParser::EDID_PARSER **)this;
    LOWORD(v28) = 0;
    if ( (unsigned __int16)v11 < v44[0] )
      v19 = 1;
    *(_QWORD *)&v48[0] = 0;
    DWORD2(v48[0]) = 0;
    v29 = *(__int64 **)this;
    *(_DWORD *)v42 = 0;
    *(_DWORD *)v46 = *((_DWORD *)v29 + 20);
    if ( *(_DWORD *)v46 )
    {
      do
      {
        if ( (unsigned int)MonDescParser::EDID_PARSER::GetBlockType(*v27, (unsigned __int16)v28) == 2 )
        {
          IterAtElement = (union _EDID_V1_BLOCK **)MonDescParser::EDID_PARSER::GetIterAtElement(*v27, v30);
          MonDescParser::EDID_PARSER_CEA_861_EXT::ChangeCEABlock(
            (MonDescParser::EDID_PARSER_CEA_861_EXT *)v48,
            *IterAtElement);
          v47[0] = 0;
          for ( k = 0;
                (_WORD)v11
             && MonDescParser::EDID_PARSER_CEA_861_EXT::GetDetTimParser(
                  (MonDescParser::EDID_PARSER_CEA_861_EXT *)v48,
                  k,
                  (struct MonDescParser::EDID_PARSER_DETAILED_TIMING *)v47);
                ++k )
          {
            result = MonDescParser::EDID_MODES::ModeFromDetailedTimingBlock(
                       (MonDescParser::EDID_MODES *)v27,
                       (struct MonDescParser::EDID_PARSER_DETAILED_TIMING *)v47,
                       v33);
            if ( result != -1071841271 )
            {
              if ( result < 0 )
                return result;
              v34 = v43;
              if ( !v13
                || MonDescParser::IndexOf<_VideoModeDescriptor *,_VideoModeDescriptor>(a4, (char *)a4 + 56 * v13, v43) == -1 )
              {
                ++v13;
                LOWORD(v11) = v11 - 1;
                v43 = (struct _VideoModeDescriptor *)((char *)v34 + 56);
              }
            }
          }
          v35 = 0;
          if ( (_WORD)v11 )
          {
            do
            {
              if ( v35 >= DWORD2(v48[0]) )
                break;
              v47[0] = 0;
              if ( MonDescParser::EDID_PARSER_CEA_861_EXT::GetDataBlock(
                     (MonDescParser::EDID_PARSER_CEA_861_EXT *)v48,
                     v35,
                     v47) )
              {
                v37 = v47[0];
                if ( (*(_BYTE *)v47[0] & 0xE0) == 0x40 )
                {
                  v38 = (struct _EDID_V1_CEA_861_DATA_HEADER *)((char *)v47[0] + 1);
                  for ( m = 0; (_WORD)v11 && m < (*(_BYTE *)v37 & 0x1Fu); ++m )
                  {
                    result = MonDescParser::EDID_MODES::ModeFromCeaVideoFormat(this, v38, v36);
                    if ( result == -1071841278 )
                    {
                      v36 = v43;
                    }
                    else
                    {
                      if ( result < 0 )
                        return result;
                      ++v13;
                      LOWORD(v11) = v11 - 1;
                      v36 = (struct _VideoModeDescriptor *)((char *)v43 + 56);
                      v43 = (struct _VideoModeDescriptor *)((char *)v43 + 56);
                    }
                    v38 = (const struct _EDID_V1_CEA_861_SHORT_VIDEO_DESC *)((char *)v38 + 1);
                  }
                }
              }
              ++v35;
            }
            while ( (_WORD)v11 );
            v27 = (MonDescParser::EDID_PARSER **)this;
          }
        }
        HIWORD(v28) = v42[1];
        LOWORD(v28) = v42[0] + 1;
        v40 = (unsigned __int16)(v42[0] + 1);
        *(_DWORD *)v42 = v28;
      }
      while ( v40 < *(_DWORD *)v46 );
    }
    *a2 = v13;
    return v19 != 0 ? 0xC0000023 : 0;
  }
  else
  {
    *a2 = v41[0] + v45 + v46[0] + v42[0] + v44[0];
    return -1073741789;
  }
}

```

## disassembly

```asm
0x18003add4  mov     rax, rsp
0x18003add7  mov     [rax+20h], r9
0x18003addb  mov     [rax+18h], r8
0x18003addf  mov     [rax+10h], rdx
0x18003ade3  mov     [rax+8], rcx
0x18003ade7  push    rbp
0x18003ade8  push    rbx
0x18003ade9  push    rsi
0x18003adea  push    rdi
0x18003adeb  push    r12
0x18003aded  push    r13
0x18003adef  push    r14
0x18003adf1  push    r15
0x18003adf3  lea     rbp, [rax-5Fh]
0x18003adf7  sub     rsp, 88h
0x18003adfe  xor     ebx, ebx
0x18003ae00  mov     rax, r9
0x18003ae03  mov     r13, r8
0x18003ae06  mov     r12, rdx
0x18003ae09  test    rdx, rdx
0x18003ae0c  jz      loc_18003B336
0x18003ae12  test    rax, rax
0x18003ae15  jz      short loc_18003AE1C
0x18003ae17  test    r8, r8
0x18003ae1a  jnz     short loc_18003AE25
0x18003ae1c  cmp     bx, [rdx]
0x18003ae1f  jnz     loc_18003B336
0x18003ae25  lea     rax, [rbp+57h+var_70]
0x18003ae29  mov     [rbp+57h+var_60], rbx
0x18003ae2d  mov     [rsp+30h], rax; unsigned __int16 *
0x18003ae32  lea     r9, [rbp+57h+var_68]; unsigned __int16 *
0x18003ae36  lea     rax, [rbp+57h+var_7C]
0x18003ae3a  mov     [rbp+57h+var_80], bx
0x18003ae3e  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x18003ae43  lea     r8, [rbp+57h+var_6C]; unsigned __int16 *
0x18003ae47  lea     rax, [rbp+57h+var_60]
0x18003ae4b  mov     [rbp+57h+var_6C], bx
0x18003ae4f  lea     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x18003ae53  mov     [rsp+0C0h+var_A0], rax; struct __EDID_V1_MONDESC_EXTRA_STANDARD_TIMINGS **
0x18003ae58  mov     [rbp+57h+var_68], bx
0x18003ae5c  mov     [rbp+57h+var_7C], bx
0x18003ae60  mov     [rbp+57h+var_70], bx
0x18003ae64  call    ?GetModeCounts@EDID_MODES@MonDescParser@@QEAAJPEAG00PEAPEBU__EDID_V1_MONDESC_EXTRA_STANDARD_TIMINGS@@00@Z; MonDescParser::EDID_MODES::GetModeCounts(ushort *,ushort *,ushort *,__EDID_V1_MONDESC_EXTRA_STANDARD_TIMINGS const * *,ushort *,ushort *)
0x18003ae69  test    eax, eax
0x18003ae6b  js      loc_18003B33B
0x18003ae71  movzx   edi, [rbp+57h+var_80]
0x18003ae75  cmp     di, 11h
0x18003ae79  ja      loc_18003B32F
0x18003ae7f  movzx   r15d, [rbp+57h+var_6C]
0x18003ae84  cmp     r15d, 8
0x18003ae88  ja      loc_18003B32F
0x18003ae8e  movzx   r14d, [rbp+57h+var_68]
0x18003ae93  cmp     r14d, 6
0x18003ae97  ja      loc_18003B32F
0x18003ae9d  movzx   esi, [rbp+57h+var_7C]
0x18003aea1  cmp     si, 4
0x18003aea5  ja      loc_18003B32F
0x18003aeab  movzx   ebx, word ptr [r12]
0x18003aeb0  xor     ecx, ecx
0x18003aeb2  cmp     cx, bx
0x18003aeb5  jz      loc_18003B311
0x18003aebb  mov     byte ptr [rbp+57h+var_80], cl
0x18003aebe  xor     edx, edx; Val
0x18003aec0  mov     rcx, [rbp+57h+arg_18]; void *
0x18003aec4  imul    r8, rbx, 38h ; '8'; Size
0x18003aec8  call    memset_0
0x18003aecd  mov     r8, [rbp+57h+arg_18]; struct _VideoModeDescriptor *
0x18003aed1  xor     edx, edx
0x18003aed3  mov     word ptr [r13+0], 0FFFFh
0x18003aeda  mov     r12d, edx
0x18003aedd  mov     [rbp+57h+var_78], r8
0x18003aee1  mov     r11, r8
0x18003aee4  lea     ecx, [rdx+1]
0x18003aee7  cmp     bx, di
0x18003aeea  jnb     short loc_18003AEF2
0x18003aeec  mov     byte ptr [rbp+57h+var_80], cl
0x18003aeef  movzx   edi, bx
0x18003aef2  cmp     dx, di
0x18003aef5  jz      short loc_18003AF2A
0x18003aef7  mov     rcx, [rbp+57h+arg_0]; this
0x18003aefb  movzx   r13d, di
0x18003aeff  mov     edx, r13d; unsigned __int64
0x18003af02  call    ?ModesFromEstablishedTimings@EDID_MODES@MonDescParser@@QEAAJ_KPEAU_VideoModeDescriptor@@@Z; MonDescParser::EDID_MODES::ModesFromEstablishedTimings(unsigned __int64,_VideoModeDescriptor *)
0x18003af07  xor     edx, edx
0x18003af09  test    eax, eax
0x18003af0b  js      loc_18003B33B
0x18003af11  imul    r11, r13, 38h ; '8'
0x18003af15  mov     r13, [rbp+57h+arg_10]
0x18003af19  lea     ecx, [rdx+1]
0x18003af1c  sub     bx, di
0x18003af1f  movzx   r12d, di
0x18003af23  add     r11, r8
0x18003af26  mov     [rbp+57h+var_78], r11
0x18003af2a  cmp     bx, si
0x18003af2d  jnb     short loc_18003AF35
0x18003af2f  mov     byte ptr [rbp+57h+var_80], cl
0x18003af32  movzx   esi, bx
0x18003af35  mov     dword ptr [rbp+57h+var_7C], edx
0x18003af38  mov     ecx, edx
0x18003af3a  mov     edi, edx
0x18003af3c  cmp     dx, si
0x18003af3f  jnb     loc_18003B005
0x18003af45  cmp     cx, 4
0x18003af49  jnb     loc_18003B005
0x18003af4f  mov     rax, [rbp+57h+arg_0]
0x18003af53  lea     r8, [rbp+57h+var_68]; struct MonDescParser::EDID_PARSER_DETAILED_TIMING *
0x18003af57  mov     qword ptr [rbp+57h+var_68], rdx
0x18003af5b  movzx   edx, cx; int
0x18003af5e  mov     rcx, [rax]; this
0x18003af61  call    ?GetDetTimParser@EDID_PARSER@MonDescParser@@QEAA_NHAEAVEDID_PARSER_DETAILED_TIMING@2@_N@Z; MonDescParser::EDID_PARSER::GetDetTimParser(int,MonDescParser::EDID_PARSER_DETAILED_TIMING &,bool)
0x18003af66  xor     edx, edx
0x18003af68  test    al, al
0x18003af6a  jz      loc_18003AFF3
0x18003af70  mov     rcx, [rbp+57h+arg_0]; this
0x18003af74  lea     rdx, [rbp+57h+var_68]; struct MonDescParser::EDID_PARSER_DETAILED_TIMING *
0x18003af78  mov     r8, r11; struct _VideoModeDescriptor *
0x18003af7b  call    ?ModeFromDetailedTimingBlock@EDID_MODES@MonDescParser@@QEAAJAEAVEDID_PARSER_DETAILED_TIMING@2@PEAU_VideoModeDescriptor@@@Z; MonDescParser::EDID_MODES::ModeFromDetailedTimingBlock(MonDescParser::EDID_PARSER_DETAILED_TIMING &,_VideoModeDescriptor *)
0x18003af80  xor     edx, edx
0x18003af82  cmp     eax, 0C01D0009h
0x18003af87  jz      short loc_18003AFEF
0x18003af89  test    eax, eax
0x18003af8b  js      loc_18003B33B
0x18003af91  cmp     dx, di
0x18003af94  jnz     short loc_18003AF9B
0x18003af96  mov     [r13+0], r12w
0x18003af9b  mov     r11, [rbp+57h+var_78]
0x18003af9f  test    r12w, r12w
0x18003afa3  jz      short loc_18003AFD1
0x18003afa5  mov     rcx, [rbp+57h+arg_18]
0x18003afa9  mov     r8, r11
0x18003afac  movzx   eax, r12w
0x18003afb0  imul    rdx, rax, 38h ; '8'
0x18003afb4  add     rdx, [rbp+57h+arg_18]
0x18003afb8  call    ??$IndexOf@PEAU_VideoModeDescriptor@@U1@@MonDescParser@@YA_KPEAU_VideoModeDescriptor@@0AEAU1@@Z; MonDescParser::IndexOf<_VideoModeDescriptor *,_VideoModeDescriptor>(_VideoModeDescriptor *,_VideoModeDescriptor *,_VideoModeDescriptor &)
0x18003afbd  xor     edx, edx
0x18003afbf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003afc3  jz      short loc_18003AFD1
0x18003afc5  cmp     dx, di
0x18003afc8  jnz     short loc_18003AFF3
0x18003afca  mov     [r13+0], ax
0x18003afcf  jmp     short loc_18003AFF3
0x18003afd1  mov     ecx, 1
0x18003afd6  mov     eax, 0FFFFh
0x18003afdb  add     bx, ax
0x18003afde  add     di, cx
0x18003afe1  add     r12w, cx
0x18003afe5  add     r11, 38h ; '8'
0x18003afe9  mov     [rbp+57h+var_78], r11
0x18003afed  jmp     short loc_18003AFF3
0x18003afef  mov     r11, [rbp+57h+var_78]
0x18003aff3  mov     ecx, dword ptr [rbp+57h+var_7C]
0x18003aff6  inc     cx
0x18003aff9  mov     dword ptr [rbp+57h+var_7C], ecx
0x18003affc  cmp     di, si
0x18003afff  jb      loc_18003AF45
0x18003b005  cmp     bx, r15w
0x18003b009  jnb     short loc_18003B017
0x18003b00b  mov     r13b, 1
0x18003b00e  movzx   r15d, bx
0x18003b012  mov     r14d, edx
0x18003b015  jmp     short loc_18003B033
0x18003b017  lea     ecx, [r15+r14]
0x18003b01b  movzx   eax, bx
0x18003b01e  cmp     eax, ecx
0x18003b020  jnb     short loc_18003B02F
0x18003b022  movzx   r14d, bx
0x18003b026  mov     r13b, 1
0x18003b029  sub     r14w, r15w
0x18003b02d  jmp     short loc_18003B033
0x18003b02f  mov     r13b, byte ptr [rbp+57h+var_80]
0x18003b033  movzx   esi, r14w
0x18003b037  movzx   eax, r15w
0x18003b03b  add     esi, eax
0x18003b03d  jz      loc_18003B13F
0x18003b043  mov     r14, [rbp+57h+var_60]
0x18003b047  mov     edi, edx
0x18003b049  mov     rax, [rbp+57h+arg_0]
0x18003b04d  cmp     di, r15w
0x18003b051  movzx   ecx, di
0x18003b054  setnb   r10b
0x18003b058  mov     rax, [rax]
0x18003b05b  mov     r9, [rax]
0x18003b05e  test    r10b, r10b
0x18003b061  jz      short loc_18003B0A5
0x18003b063  movzx   eax, r15w
0x18003b067  mov     r8d, edx
0x18003b06a  sub     rcx, rax
0x18003b06d  lea     rax, [r14+rcx*2]
0x18003b071  mov     [rbp+57h+var_60], rax
0x18003b075  mov     eax, r8d
0x18003b078  movzx   edx, byte ptr [rax+r9+12h]
0x18003b07e  lea     eax, ds:8[r8*4]
0x18003b086  movsxd  rcx, eax
0x18003b089  inc     r8d
0x18003b08c  mov     dword ptr [rbp+rcx+57h+var_60], edx
0x18003b090  cmp     r8d, 2
0x18003b094  jl      short loc_18003B075
0x18003b096  movaps  xmm0, xmmword ptr [rbp+57h+var_60]
0x18003b09a  mov     r11, [rbp+57h+var_78]
0x18003b09e  movdqa  [rbp+57h+var_50], xmm0
0x18003b0a3  jmp     short loc_18003B0C1
0x18003b0a5  lea     rax, [r9+26h]
0x18003b0a9  lea     rax, [rax+rcx*2]
0x18003b0ad  mov     qword ptr [rbp+57h+var_50], rax
0x18003b0b1  movzx   eax, byte ptr [r9+12h]
0x18003b0b6  mov     dword ptr [rbp+57h+var_50+8], eax
0x18003b0b9  movzx   eax, byte ptr [r9+13h]
0x18003b0be  mov     dword ptr [rbp+57h+var_50+0Ch], eax
0x18003b0c1  mov     rcx, [rbp+57h+arg_0]; this
0x18003b0c5  lea     rdx, [rbp+57h+var_50]; struct MonDescParser::EDID_PARSER_STANDARD_TIMING *
0x18003b0c9  mov     r9, r11; struct _VideoModeDescriptor *
0x18003b0cc  mov     r8b, r10b; unsigned __int8
0x18003b0cf  call    ?ModeFromStandardTimingBlock@EDID_MODES@MonDescParser@@QEAAJAEAVEDID_PARSER_STANDARD_TIMING@2@EPEAU_VideoModeDescriptor@@@Z; MonDescParser::EDID_MODES::ModeFromStandardTimingBlock(MonDescParser::EDID_PARSER_STANDARD_TIMING &,uchar,_VideoModeDescriptor *)
0x18003b0d4  cmp     eax, 0C01D0004h
0x18003b0d9  jz      short loc_18003B126
0x18003b0db  test    eax, eax
0x18003b0dd  js      loc_18003B33B
0x18003b0e3  mov     r11, [rbp+57h+var_78]
0x18003b0e7  test    r12w, r12w
0x18003b0eb  jz      short loc_18003B10B
0x18003b0ed  mov     rcx, [rbp+57h+arg_18]
0x18003b0f1  mov     r8, r11
0x18003b0f4  movzx   eax, r12w
0x18003b0f8  imul    rdx, rax, 38h ; '8'
0x18003b0fc  add     rdx, [rbp+57h+arg_18]
0x18003b100  call    ??$IndexOf@PEAU_VideoModeDescriptor@@U1@@MonDescParser@@YA_KPEAU_VideoModeDescriptor@@0AEAU1@@Z; MonDescParser::IndexOf<_VideoModeDescriptor *,_VideoModeDescriptor>(_VideoModeDescriptor *,_VideoModeDescriptor *,_VideoModeDescriptor &)
0x18003b105  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003b109  jnz     short loc_18003B12A
0x18003b10b  mov     eax, 0FFFFh
0x18003b110  add     bx, ax
0x18003b113  mov     eax, 1
0x18003b118  add     r12w, ax
0x18003b11c  add     r11, 38h ; '8'
0x18003b120  mov     [rbp+57h+var_78], r11
0x18003b124  jmp     short loc_18003B12F
0x18003b126  mov     r11, [rbp+57h+var_78]
0x18003b12a  mov     eax, 1
0x18003b12f  add     di, ax
0x18003b132  xor     edx, edx
0x18003b134  movzx   eax, di
0x18003b137  cmp     eax, esi
0x18003b139  jb      loc_18003B049
0x18003b13f  cmp     bx, [rbp+57h+var_70]
0x18003b143  mov     r14d, 1
0x18003b149  mov     rsi, [rbp+57h+arg_0]
0x18003b14d  mov     ecx, edx
0x18003b14f  movzx   r13d, r13b
0x18003b153  cmovb   r13d, r14d
0x18003b157  mov     qword ptr [rbp+57h+var_50], rdx
0x18003b15b  mov     dword ptr [rbp+57h+var_50+8], edx
0x18003b15e  mov     rax, [rsi]
0x18003b161  mov     dword ptr [rbp+57h+var_7C], edx
0x18003b164  mov     eax, [rax+50h]
0x18003b167  mov     dword ptr [rbp+57h+var_68], eax
0x18003b16a  test    eax, eax
0x18003b16c  jz      loc_18003B2FD
0x18003b172  movzx   r10d, cx
0x18003b176  mov     rcx, [rsi]
0x18003b179  mov     edx, r10d
0x18003b17c  call    ?GetBlockType@EDID_PARSER@MonDescParser@@QEBA?AW4EDID_V1_BLOCK_TYPE@2@I@Z; MonDescParser::EDID_PARSER::GetBlockType(uint)
0x18003b181  cmp     eax, 2
0x18003b184  jnz     loc_18003B2E1
0x18003b18a  mov     rcx, [rsi]; this
0x18003b18d  mov     edx, r10d; unsigned int
0x18003b190  call    ?GetIterAtElement@EDID_PARSER@MonDescParser@@AEBAPEBQEAT_EDID_V1_BLOCK@@I@Z; MonDescParser::EDID_PARSER::GetIterAtElement(uint)
0x18003b195  lea     rcx, [rbp+57h+var_50]; this
0x18003b199  mov     rdx, [rax]; union _EDID_V1_BLOCK *
0x18003b19c  call    ?ChangeCEABlock@EDID_PARSER_CEA_861_EXT@MonDescParser@@QEAAXPEAT_EDID_V1_BLOCK@@@Z; MonDescParser::EDID_PARSER_CEA_861_EXT::ChangeCEABlock(_EDID_V1_BLOCK *)
0x18003b1a1  xor     r15d, r15d
0x18003b1a4  mov     [rbp+57h+var_60], r15
0x18003b1a8  mov     edi, r15d
0x18003b1ab  jmp     short loc_18003B225
0x18003b1ad  movzx   edx, di; int
0x18003b1b0  lea     r8, [rbp+57h+var_60]; struct MonDescParser::EDID_PARSER_DETAILED_TIMING *
0x18003b1b4  lea     rcx, [rbp+57h+var_50]; this
0x18003b1b8  call    ?GetDetTimParser@EDID_PARSER_CEA_861_EXT@MonDescParser@@QEAA_NHAEAVEDID_PARSER_DETAILED_TIMING@2@@Z; MonDescParser::EDID_PARSER_CEA_861_EXT::GetDetTimParser(int,MonDescParser::EDID_PARSER_DETAILED_TIMING &)
0x18003b1bd  test    al, al
0x18003b1bf  jz      short loc_18003B22A
0x18003b1c1  mov     r8, r11; struct _VideoModeDescriptor *
0x18003b1c4  lea     rdx, [rbp+57h+var_60]; struct MonDescParser::EDID_PARSER_DETAILED_TIMING *
0x18003b1c8  mov     rcx, rsi; this
0x18003b1cb  call    ?ModeFromDetailedTimingBlock@EDID_MODES@MonDescParser@@QEAAJAEAVEDID_PARSER_DETAILED_TIMING@2@PEAU_VideoModeDescriptor@@@Z; MonDescParser::EDID_MODES::ModeFromDetailedTimingBlock(MonDescParser::EDID_PARSER_DETAILED_TIMING &,_VideoModeDescriptor *)
0x18003b1d0  cmp     eax, 0C01D0009h
0x18003b1d5  jz      short loc_18003B21D
0x18003b1d7  test    eax, eax
0x18003b1d9  js      loc_18003B33B
0x18003b1df  mov     r11, [rbp+57h+var_78]
0x18003b1e3  test    r12w, r12w
0x18003b1e7  jz      short loc_18003B207
0x18003b1e9  mov     rcx, [rbp+57h+arg_18]
0x18003b1ed  mov     r8, r11
0x18003b1f0  movzx   eax, r12w
0x18003b1f4  imul    rdx, rax, 38h ; '8'
0x18003b1f8  add     rdx, [rbp+57h+arg_18]
0x18003b1fc  call    ??$IndexOf@PEAU_VideoModeDescriptor@@U1@@MonDescParser@@YA_KPEAU_VideoModeDescriptor@@0AEAU1@@Z; MonDescParser::IndexOf<_VideoModeDescriptor *,_VideoModeDescriptor>(_VideoModeDescriptor *,_VideoModeDescriptor *,_VideoModeDescriptor &)
0x18003b201  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003b205  jnz     short loc_18003B221
0x18003b207  mov     eax, 0FFFFh
0x18003b20c  add     r12w, r14w
0x18003b210  add     bx, ax
  ... truncated ...
```
