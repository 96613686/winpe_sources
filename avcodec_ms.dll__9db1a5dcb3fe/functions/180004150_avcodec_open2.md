# avcodec_open2

- ea: `0x180004150`
- end: `0x1800047ff`
- name: `avcodec_open2`
- size: `1711`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: ``

## callees

- `0x180003db0`
- `0x180003dd0`
- `0x180004150`
- `0x1800050a4`
- `0x180005550`
- `0x180006200`
- `0x180007f38`
- `0x180007f70`
- `0x18000a664`
- `0x18000a670`
- `0x18000ed70`
- `0x1800102c8`
- `0x180012c34`
- `0x18002269e`
- `0x1800226aa`
- `0x1800226c8`
- `0x18002270a`
- `0x180022710`
- `0x180022716`
- `0x18002272e`
- `0x180022740`
- `0x18002274c`
- `0x180022752`
- `0x18002275e`
- `0x180022996`
- `0x180024140`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800046ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004716`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800046ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004716`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004698`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800046ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004698`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800046ec`

## string_xrefs

- `0x180004193`: `No codec provided to avcodec_open2()\n`
- `0x1800041d3`: `This AVCodecContext was allocated for %s, but %s passed to avcodec_open2()\n`

## pseudocode

```c
__int64 __fastcall avcodec_open2(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v3; // rdi
  _QWORD *v4; // rsi
  __int64 result; // rax
  _QWORD *v7; // r9
  int v8; // ecx
  int v9; // ecx
  bool v10; // cc
  _QWORD *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rbp
  int v16; // edi
  __int64 v17; // rax
  _QWORD *v18; // rax
  __int64 v19; // rcx
  unsigned int v20; // edx
  unsigned int v21; // r8d
  unsigned int *v22; // r14
  unsigned int *v23; // rdi
  __int64 v24; // rcx
  __int64 v25; // rdx
  int v26; // r9d
  const char *v27; // r9
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  const char *v31; // rdi
  __int64 v32; // rcx
  __int64 decoder; // rax
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // [rsp+28h] [rbp-30h]

  v3 = a3;
  v4 = a2;
  if ( *(_QWORD *)(a1 + 40) )
    return 0;
  v7 = *(_QWORD **)(a1 + 16);
  if ( a2 )
  {
    if ( v7 && a2 != v7 )
    {
      av_log(a1, 16, "This AVCodecContext was allocated for %s, but %s passed to avcodec_open2()\n", *v7, *a2);
      return 4294967274LL;
    }
  }
  else
  {
    v4 = *(_QWORD **)(a1 + 16);
    if ( !v7 )
    {
      av_log(a1, 16, "No codec provided to avcodec_open2()\n");
      return 4294967274LL;
    }
  }
  v8 = *(_DWORD *)(a1 + 12);
  if ( v8 != -1 && v8 != *((_DWORD *)v4 + 4) || (v9 = *(_DWORD *)(a1 + 24)) != 0 && v9 != *((_DWORD *)v4 + 5) )
  {
    av_log(a1, 16, "Codec type or id mismatches\n");
    return 4294967274LL;
  }
  v10 = *(_DWORD *)(a1 + 80) <= 0xFFFFFBFu;
  *(_DWORD *)(a1 + 12) = *((_DWORD *)v4 + 4);
  *(_DWORD *)(a1 + 24) = *((_DWORD *)v4 + 5);
  *(_QWORD *)(a1 + 16) = v4;
  if ( !v10 )
    return 4294967274LL;
  if ( a3 )
  {
    v11 = (_QWORD *)av_dict_get(*a3, "codec_whitelist", 0, 0);
    if ( v11 )
    {
      result = av_opt_set(a1, *v11, v11[1], 0);
      if ( (int)result < 0 )
      {
        _mm_lfence();
        return result;
      }
    }
  }
  v12 = *(_QWORD *)(a1 + 768);
  if ( v12 )
  {
    LOBYTE(a3) = 44;
    if ( (int)av_match_list(*v4, v12, a3) <= 0 )
    {
      av_log(a1, 16, "Codec (%s) not on whitelist '%s'\n", *v4, *(_QWORD *)(a1 + 768));
      return 4294967274LL;
    }
  }
  if ( (v4[12] & 0x4000000) != 0 )
    v13 = sub_180007F38();
  else
    v13 = sub_18000A664();
  v15 = v13;
  if ( v13 )
  {
    *(_QWORD *)(a1 + 40) = v13;
    *(_QWORD *)(v13 + 136) = av_frame_alloc(v14);
    v17 = av_packet_alloc();
    *(_QWORD *)(v15 + 128) = v17;
    if ( !*(_QWORD *)(v15 + 136) || !v17 )
      goto LABEL_126;
    if ( *((int *)v4 + 25) <= 0 )
    {
      *(_QWORD *)(a1 + 32) = 0;
    }
    else if ( !*(_QWORD *)(a1 + 32) )
    {
      _mm_lfence();
      v18 = (_QWORD *)av_mallocz(*((int *)v4 + 25));
      *(_QWORD *)(a1 + 32) = v18;
      if ( v18 )
      {
        v19 = v4[8];
        if ( v19 )
        {
          *v18 = v19;
          av_opt_set_defaults(*(_QWORD *)(a1 + 32));
        }
        goto LABEL_37;
      }
LABEL_126:
      v16 = -12;
      goto LABEL_127;
    }
LABEL_37:
    v16 = av_opt_set_dict2(a1, v3, 1);
    if ( v16 >= 0 )
    {
      _mm_lfence();
      v20 = *(_DWORD *)(a1 + 120);
      if ( !v20 )
        goto LABEL_132;
      if ( *(_DWORD *)(a1 + 124)
        && *(_DWORD *)(a1 + 112)
        && *(_DWORD *)(a1 + 116)
        && (*(_DWORD *)(a1 + 24) == 27 || *(_DWORD *)(a1 + 24) == 92 || *(_DWORD *)(a1 + 24) == 189) )
      {
        goto LABEL_49;
      }
      _mm_lfence();
      v21 = *(_DWORD *)(a1 + 124);
      if ( !v21 )
      {
LABEL_132:
        _mm_lfence();
        v20 = *(_DWORD *)(a1 + 112);
        if ( !v20 )
          goto LABEL_49;
        _mm_lfence();
        v21 = *(_DWORD *)(a1 + 116);
        if ( !v21 )
          goto LABEL_49;
      }
      v16 = sub_180012C34(a1, v20, v21);
      if ( v16 >= 0 )
      {
LABEL_49:
        if ( *(_DWORD *)(a1 + 120)
          || *(_DWORD *)(a1 + 124)
          || (v22 = (unsigned int *)(a1 + 112), *(_DWORD *)(a1 + 112))
          || (v23 = (unsigned int *)(a1 + 116), *(_DWORD *)(a1 + 116)) )
        {
          HIDWORD(v36) = HIDWORD(a1);
          v23 = (unsigned int *)(a1 + 116);
          v22 = (unsigned int *)(a1 + 112);
          if ( (int)av_image_check_size2() < 0
            || (_mm_lfence(), HIDWORD(v36) = HIDWORD(a1), (int)av_image_check_size2() < 0) )
          {
            av_log(a1, 24, "Ignoring invalid width/height values\n");
            sub_180012C34(a1, 0, 0);
          }
        }
        v24 = *v22;
        if ( (int)v24 > 0 )
        {
          v25 = *v23;
          if ( (int)v25 > 0 )
          {
            _mm_lfence();
            if ( (int)av_image_check_sar(v24, v25, *(_QWORD *)(a1 + 128)) < 0 )
            {
              av_log(a1, 24, "ignoring invalid SAR: %u/%u\n", *(_DWORD *)(a1 + 128), *(_DWORD *)(a1 + 132));
              *(_QWORD *)(a1 + 128) = 0x100000000LL;
            }
          }
        }
        v26 = *(_DWORD *)(a1 + 344);
        if ( v26 < 0 || !v26 && *(_DWORD *)(a1 + 12) == 1 && (v4[3] & 0x400) == 0 )
        {
          av_log(a1, 16, "Invalid sample rate: %d\n");
          goto LABEL_125;
        }
        if ( *(int *)(a1 + 380) < 0 )
        {
          _mm_lfence();
          av_log(a1, 16, "Invalid block align: %d\n");
LABEL_125:
          v16 = -22;
          goto LABEL_127;
        }
        if ( *(_DWORD *)(a1 + 12) == 1 )
        {
          if ( *(_DWORD *)(a1 + 356) )
          {
LABEL_73:
            if ( !(unsigned int)av_channel_layout_check(a1 + 352) )
            {
              av_log(a1, 16, "Invalid channel layout\n");
              goto LABEL_125;
            }
LABEL_75:
            if ( *(_DWORD *)(a1 + 356) > 0x200u )
            {
              _mm_lfence();
              av_log(a1, 16, "Too many channels: %d\n");
              goto LABEL_125;
            }
            v28 = *(unsigned int *)(a1 + 24);
            *(_QWORD *)(a1 + 824) = 0;
            v29 = avcodec_descriptor_get(v28);
            v30 = *(_QWORD *)(a1 + 16);
            *(_QWORD *)(a1 + 728) = v29;
            if ( (*(_DWORD *)(v30 + 24) & 0x200) != 0 && *(int *)(a1 + 516) > -2 )
            {
              LODWORD(v36) = -2;
              v31 = "decoder";
              if ( (v4[12] & 0x4000000) == 0 )
                v31 = "encoder";
              av_log(
                a1,
                16,
                "The %s '%s' is experimental but experimental codecs are not enabled, add '-strict %d' if you want to use it.\n",
                v31,
                *v4,
                v36);
              v32 = *((unsigned int *)v4 + 5);
              if ( (v4[12] & 0x4000000) != 0 )
                decoder = avcodec_find_decoder(v32);
              else
                decoder = avcodec_find_encoder(v32);
              if ( (*(_DWORD *)(decoder + 24) & 0x200) == 0 )
                av_log(a1, 16, "Alternatively use the non experimental %s '%s'.\n", v31, *(const char **)decoder);
              v16 = -733130664;
              goto LABEL_127;
            }
            if ( *(_DWORD *)(a1 + 12) == 1 && (!*(_DWORD *)(a1 + 84) || !*(_DWORD *)(a1 + 88)) )
            {
              *(_DWORD *)(a1 + 88) = *(_DWORD *)(a1 + 344);
              *(_DWORD *)(a1 + 84) = 1;
            }
            if ( (*(_DWORD *)(v30 + 96) & 0x4000000) != 0 )
              v34 = sub_180007F70(a1);
            else
              v34 = sub_18000A670(a1);
            v16 = v34;
            if ( v34 < 0 )
              goto LABEL_127;
            if ( !*(_QWORD *)(v15 + 80) )
            {
              _mm_lfence();
              if ( (v4[12] & 1) != 0 && v4[16] )
                AcquireSRWLockExclusive(&SRWLock);
              v16 = sub_1800102C8(a1);
              if ( (v4[12] & 1) != 0 && v4[16] )
                ReleaseSRWLockExclusive(&SRWLock);
              if ( v16 < 0 )
                goto LABEL_127;
            }
            if ( (*(_BYTE *)(a1 + 664) & 1) == 0 || *(_QWORD *)(v15 + 80) )
            {
              if ( v4[16] )
              {
                _mm_lfence();
                if ( (v4[12] & 1) != 0 )
                  AcquireSRWLockExclusive(&SRWLock);
                v16 = ((__int64 (__fastcall *)(__int64))v4[16])(a1);
                if ( (v4[12] & 1) != 0 && v4[16] )
                  ReleaseSRWLockExclusive(&SRWLock);
                if ( v16 < 0 )
                {
                  *(_DWORD *)(v15 + 104) = v4[12] & 2;
                  goto LABEL_127;
                }
              }
              *(_DWORD *)(v15 + 104) = 1;
            }
            _mm_lfence();
            v16 = 0;
            if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 96LL) & 0x4000000) == 0 )
              goto LABEL_121;
            if ( !*(_QWORD *)(a1 + 56) )
            {
              _mm_lfence();
              *(_QWORD *)(a1 + 56) = sub_180005550(a1);
            }
            if ( !*(_DWORD *)(a1 + 356) || (_mm_lfence(), (unsigned int)av_channel_layout_check(a1 + 352)) )
            {
              if ( *(_DWORD *)(a1 + 356) <= 0x200u && *(int *)(a1 + 648) >= 0 )
              {
LABEL_121:
                v35 = v4[8];
                if ( v35 )
                {
                  _mm_lfence();
                  if ( **(_QWORD **)(a1 + 32) != v35 )
                  {
                    av_log(
                      0,
                      0,
                      "Assertion %s failed at %s:%d\n",
                      "*(const AVClass **)avctx->priv_data == codec->priv_class",
                      "C:/__w/1/s/FFmpegInterop/ffmpeg/libavcodec/avcodec.c",
                      369);
                    abort();
                  }
                }
                return (unsigned int)v16;
              }
            }
            goto LABEL_125;
          }
          if ( (v4[3] & 0x400) == 0 )
          {
            v27 = "Encoder";
            if ( (v4[12] & 0x4000000) != 0 )
              v27 = "Decoder";
            av_log(a1, 16, "%s requires channel layout to be set\n", v27);
            goto LABEL_125;
          }
        }
        if ( !*(_DWORD *)(a1 + 356) )
          goto LABEL_75;
        goto LABEL_73;
      }
    }
LABEL_127:
    sub_1800050A4(a1);
    return (unsigned int)v16;
  }
  return (unsigned int)-12;
}

```

## disassembly

```asm
0x180004150  mov     [rsp+arg_8], rbx
0x180004155  mov     [rsp+arg_10], rbp
0x18000415a  mov     [rsp+arg_18], rsi
0x18000415f  push    rdi
0x180004160  push    r12
0x180004162  push    r13
0x180004164  push    r14
0x180004166  push    r15
0x180004168  sub     rsp, 30h
0x18000416c  xor     r15d, r15d
0x18000416f  mov     rdi, r8
0x180004172  mov     rsi, rdx
0x180004175  mov     rbx, rcx
0x180004178  cmp     [rcx+28h], r15
0x18000417c  jz      short loc_180004182
0x18000417e  xor     eax, eax
0x180004180  jmp     short loc_1800041A9
0x180004182  mov     r9, [rcx+10h]
0x180004186  test    rdx, rdx
0x180004189  jnz     short loc_1800041C6
0x18000418b  mov     rsi, r9
0x18000418e  test    r9, r9
0x180004191  jnz     short loc_1800041EE
0x180004193  lea     r8, aNoCodecProvide; "No codec provided to avcodec_open2()\n"
0x18000419a  mov     edx, 10h
0x18000419f  call    av_log
0x1800041a4  mov     eax, 0FFFFFFEAh
0x1800041a9  mov     rbx, [rsp+58h+arg_8]
0x1800041ae  mov     rbp, [rsp+58h+arg_10]
0x1800041b3  mov     rsi, [rsp+58h+arg_18]
0x1800041b8  add     rsp, 30h
0x1800041bc  pop     r15
0x1800041be  pop     r14
0x1800041c0  pop     r13
0x1800041c2  pop     r12
0x1800041c4  pop     rdi
0x1800041c5  retn
0x1800041c6  test    r9, r9
0x1800041c9  jz      short loc_1800041EE
0x1800041cb  cmp     rdx, r9
0x1800041ce  jz      short loc_1800041EE
0x1800041d0  mov     rax, [rdx]
0x1800041d3  lea     r8, aThisAvcodeccon; "This AVCodecContext was allocated for %"...
0x1800041da  mov     r9, [r9]
0x1800041dd  mov     edx, 10h
0x1800041e2  mov     [rsp+58h+var_38], rax
0x1800041e7  call    av_log
0x1800041ec  jmp     short loc_1800041A4
0x1800041ee  mov     ecx, [rcx+0Ch]
0x1800041f1  cmp     ecx, 0FFFFFFFFh
0x1800041f4  jz      short loc_1800041FB
0x1800041f6  cmp     ecx, [rsi+10h]
0x1800041f9  jnz     short loc_180004207
0x1800041fb  mov     ecx, [rbx+18h]
0x1800041fe  test    ecx, ecx
0x180004200  jz      short loc_180004213
0x180004202  cmp     ecx, [rsi+14h]
0x180004205  jz      short loc_180004213
0x180004207  lea     r8, aCodecTypeOrIdM; "Codec type or id mismatches\n"
0x18000420e  mov     rcx, rbx
0x180004211  jmp     short loc_18000419A
0x180004213  cmp     dword ptr [rbx+50h], 0FFFFFBFh
0x18000421a  mov     eax, [rsi+10h]
0x18000421d  mov     [rbx+0Ch], eax
0x180004220  mov     eax, [rsi+14h]
0x180004223  mov     [rbx+18h], eax
0x180004226  mov     [rbx+10h], rsi
0x18000422a  ja      loc_1800041A4
0x180004230  test    rdi, rdi
0x180004233  jz      short loc_18000426D
0x180004235  mov     rcx, [rdi]
0x180004238  lea     rdx, aCodecWhitelist; "codec_whitelist"
0x18000423f  xor     r9d, r9d
0x180004242  xor     r8d, r8d
0x180004245  call    av_dict_get
0x18000424a  test    rax, rax
0x18000424d  jz      short loc_18000426D
0x18000424f  mov     r8, [rax+8]
0x180004253  xor     r9d, r9d
0x180004256  mov     rdx, [rax]
0x180004259  mov     rcx, rbx
0x18000425c  call    av_opt_set
0x180004261  test    eax, eax
0x180004263  jns     short loc_18000426D
0x180004265  lfence
0x180004268  jmp     loc_1800041A9
0x18000426d  mov     rdx, [rbx+300h]
0x180004274  test    rdx, rdx
0x180004277  jz      short loc_1800042A1
0x180004279  mov     rcx, [rsi]
0x18000427c  mov     r8b, 2Ch ; ','
0x18000427f  call    av_match_list
0x180004284  test    eax, eax
0x180004286  jg      short loc_1800042A1
0x180004288  mov     rax, [rbx+300h]
0x18000428f  lea     r8, aCodecSNotOnWhi; "Codec (%s) not on whitelist '%s'\n"
0x180004296  mov     r9, [rsi]
0x180004299  mov     rcx, rbx
0x18000429c  jmp     loc_1800041DD
0x1800042a1  test    dword ptr [rsi+60h], 4000000h
0x1800042a8  jz      short loc_1800042B1
0x1800042aa  call    sub_180007F38
0x1800042af  jmp     short loc_1800042B6
0x1800042b1  call    sub_18000A664
0x1800042b6  mov     rbp, rax
0x1800042b9  test    rax, rax
0x1800042bc  jnz     short loc_1800042C6
0x1800042be  lea     edi, [rax-0Ch]
0x1800042c1  jmp     loc_1800047C7
0x1800042c6  mov     [rbx+28h], rbp
0x1800042ca  call    av_frame_alloc
0x1800042cf  mov     [rbp+88h], rax
0x1800042d6  call    av_packet_alloc
0x1800042db  mov     [rbp+80h], rax
0x1800042e2  cmp     [rbp+88h], r15
0x1800042e9  jz      loc_1800047BA
0x1800042ef  test    rax, rax
0x1800042f2  jz      loc_1800047BA
0x1800042f8  movsxd  rax, dword ptr [rsi+64h]
0x1800042fc  test    eax, eax
0x1800042fe  jle     short loc_180004335
0x180004300  cmp     [rbx+20h], r15
0x180004304  jnz     short loc_180004339
0x180004306  lfence
0x180004309  mov     rcx, rax
0x18000430c  call    av_mallocz
0x180004311  mov     [rbx+20h], rax
0x180004315  test    rax, rax
0x180004318  jz      loc_1800047BA
0x18000431e  mov     rcx, [rsi+40h]
0x180004322  test    rcx, rcx
0x180004325  jz      short loc_180004339
0x180004327  mov     [rax], rcx
0x18000432a  mov     rcx, [rbx+20h]
0x18000432e  call    av_opt_set_defaults
0x180004333  jmp     short loc_180004339
0x180004335  mov     [rbx+20h], r15
0x180004339  mov     r12d, 1
0x18000433f  mov     rdx, rdi
0x180004342  mov     r8d, r12d
0x180004345  mov     rcx, rbx
0x180004348  call    av_opt_set_dict2
0x18000434d  mov     edi, eax
0x18000434f  test    eax, eax
0x180004351  js      loc_1800047BF
0x180004357  lfence
0x18000435a  mov     edx, [rbx+78h]
0x18000435d  test    edx, edx
0x18000435f  jz      short loc_180004394
0x180004361  cmp     [rbx+7Ch], r15d
0x180004365  jz      short loc_180004388
0x180004367  cmp     [rbx+70h], r15d
0x18000436b  jz      short loc_180004388
0x18000436d  cmp     [rbx+74h], r15d
0x180004371  jz      short loc_180004388
0x180004373  cmp     dword ptr [rbx+18h], 1Bh
0x180004377  jz      short loc_1800043BC
0x180004379  cmp     dword ptr [rbx+18h], 5Ch ; '\'
0x18000437d  jz      short loc_1800043BC
0x18000437f  cmp     dword ptr [rbx+18h], 0BDh
0x180004386  jz      short loc_1800043BC
0x180004388  lfence
0x18000438b  mov     r8d, [rbx+7Ch]
0x18000438f  test    r8d, r8d
0x180004392  jnz     short loc_1800043AA
0x180004394  lfence
0x180004397  mov     edx, [rbx+70h]
0x18000439a  test    edx, edx
0x18000439c  jz      short loc_1800043BC
0x18000439e  lfence
0x1800043a1  mov     r8d, [rbx+74h]
0x1800043a5  test    r8d, r8d
0x1800043a8  jz      short loc_1800043BC
0x1800043aa  mov     rcx, rbx
0x1800043ad  call    sub_180012C34
0x1800043b2  mov     edi, eax
0x1800043b4  test    eax, eax
0x1800043b6  js      loc_1800047BF
0x1800043bc  mov     ecx, [rbx+78h]
0x1800043bf  mov     r13d, 18h
0x1800043c5  test    ecx, ecx
0x1800043c7  jnz     short loc_1800043E1
0x1800043c9  cmp     [rbx+7Ch], r15d
0x1800043cd  jnz     short loc_1800043E1
0x1800043cf  lea     r14, [rbx+70h]
0x1800043d3  cmp     [r14], r15d
0x1800043d6  jnz     short loc_1800043E1
0x1800043d8  lea     rdi, [rbx+74h]
0x1800043dc  cmp     [rdi], r15d
0x1800043df  jz      short loc_18000444F
0x1800043e1  mov     r8, [rbx+318h]
0x1800043e8  or      r9d, 0FFFFFFFFh
0x1800043ec  mov     edx, [rbx+7Ch]
0x1800043ef  mov     [rsp+58h+var_30], rbx
0x1800043f4  mov     dword ptr [rsp+58h+var_38], r15d
0x1800043f9  call    av_image_check_size2
0x1800043fe  lea     rdi, [rbx+74h]
0x180004402  lea     r14, [rbx+70h]
0x180004406  test    eax, eax
0x180004408  js      short loc_180004430
0x18000440a  lfence
0x18000440d  mov     r8, [rbx+318h]
0x180004414  or      r9d, 0FFFFFFFFh
0x180004418  mov     edx, [rdi]
0x18000441a  mov     ecx, [r14]
0x18000441d  mov     [rsp+58h+var_30], rbx
0x180004422  mov     dword ptr [rsp+58h+var_38], r15d
0x180004427  call    av_image_check_size2
0x18000442c  test    eax, eax
0x18000442e  jns     short loc_18000444F
0x180004430  lea     r8, aIgnoringInvali; "Ignoring invalid width/height values\n"
0x180004437  mov     edx, r13d
0x18000443a  mov     rcx, rbx
0x18000443d  call    av_log
0x180004442  xor     r8d, r8d
0x180004445  xor     edx, edx
0x180004447  mov     rcx, rbx
0x18000444a  call    sub_180012C34
0x18000444f  mov     ecx, [r14]
0x180004452  test    ecx, ecx
0x180004454  jle     short loc_1800044A8
0x180004456  mov     edx, [rdi]
0x180004458  test    edx, edx
0x18000445a  jle     short loc_1800044A8
0x18000445c  lfence
0x18000445f  mov     r8, [rbx+80h]
0x180004466  call    av_image_check_sar
0x18000446b  test    eax, eax
0x18000446d  jns     short loc_1800044A8
0x18000446f  mov     eax, [rbx+84h]
0x180004475  lea     r8, aIgnoringInvali_0; "ignoring invalid SAR: %u/%u\n"
0x18000447c  mov     r9d, [rbx+80h]
0x180004483  mov     edx, r13d
0x180004486  mov     rcx, rbx
0x180004489  mov     dword ptr [rsp+58h+var_38], eax
0x18000448d  call    av_log
0x180004492  mov     dword ptr [rsp+58h+arg_0], r15d
0x180004497  mov     dword ptr [rsp+58h+arg_0+4], r12d
0x18000449c  mov     rax, [rsp+58h+arg_0]
0x1800044a1  mov     [rbx+80h], rax
0x1800044a8  mov     r9d, [rbx+158h]
0x1800044af  test    r9d, r9d
0x1800044b2  js      loc_18000479F
0x1800044b8  mov     eax, 400h
0x1800044bd  jnz     short loc_1800044CE
0x1800044bf  cmp     [rbx+0Ch], r12d
0x1800044c3  jnz     short loc_1800044CE
0x1800044c5  test    [rsi+18h], eax
0x1800044c8  jz      loc_18000479F
0x1800044ce  mov     r9d, [rbx+17Ch]
0x1800044d5  test    r9d, r9d
0x1800044d8  jns     short loc_1800044E9
0x1800044da  lfence
0x1800044dd  lea     r8, aInvalidBlockAl; "Invalid block align: %d\n"
0x1800044e4  jmp     loc_1800047A6
0x1800044e9  cmp     [rbx+0Ch], r12d
0x1800044ed  jnz     short loc_18000452F
0x1800044ef  cmp     [rbx+164h], r15d
0x1800044f6  jnz     short loc_180004538
0x1800044f8  test    [rsi+18h], eax
0x1800044fb  jnz     short loc_18000452F
0x1800044fd  test    dword ptr [rsi+60h], 4000000h
0x180004504  lea     rax, aDecoder; "Decoder"
0x18000450b  lea     r9, aEncoder; "Encoder"
0x180004512  mov     edx, 10h
0x180004517  cmovnz  r9, rax
0x18000451b  lea     r8, aSRequiresChann; "%s requires channel layout to be set\n"
0x180004522  mov     rcx, rbx
0x180004525  call    av_log
0x18000452a  jmp     loc_1800047B3
0x18000452f  cmp     [rbx+164h], r15d
0x180004536  jz      short loc_18000455F
0x180004538  lea     rcx, [rbx+160h]
0x18000453f  call    av_channel_layout_check
0x180004544  test    eax, eax
0x180004546  jnz     short loc_18000455F
0x180004548  lea     r8, aInvalidChannel; "Invalid channel layout\n"
0x18000454f  mov     rcx, rbx
0x180004552  lea     edx, [rax+10h]
0x180004555  call    av_log
0x18000455a  jmp     loc_1800047B3
0x18000455f  mov     r9d, [rbx+164h]
0x180004566  mov     r13d, 200h
0x18000456c  cmp     r9d, r13d
0x18000456f  jbe     short loc_180004580
0x180004571  lfence
0x180004574  lea     r8, aTooManyChannel; "Too many channels: %d\n"
0x18000457b  jmp     loc_1800047A6
0x180004580  mov     ecx, [rbx+18h]
0x180004583  mov     [rbx+338h], r15
0x18000458a  call    avcodec_descriptor_get
0x18000458f  mov     rcx, [rbx+10h]
0x180004593  mov     [rbx+2D8h], rax
0x18000459a  test    [rcx+18h], r13d
0x18000459e  jz      loc_180004635
0x1800045a4  cmp     dword ptr [rbx+204h], 0FFFFFFFEh
0x1800045ab  jle     loc_180004635
0x1800045b1  lea     rax, aEncoder_0; "encoder"
0x1800045b8  mov     dword ptr [rsp+58h+var_30], 0FFFFFFFEh
0x1800045c0  mov     ebp, 4000000h
  ... truncated ...
```
