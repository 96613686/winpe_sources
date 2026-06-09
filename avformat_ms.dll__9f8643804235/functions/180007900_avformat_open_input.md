# avformat_open_input

- ea: `0x180007900`
- end: `0x180007d88`
- name: `avformat_open_input`
- size: `1160`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: ``

## callees

- `0x180001810`
- `0x180002bb0`
- `0x1800049e0`
- `0x180004e00`
- `0x180007900`
- `0x18000a258`
- `0x18000be8c`
- `0x18000c7b0`
- `0x180010bf4`
- `0x180010cb8`
- `0x180010da0`
- `0x180010e40`
- `0x180010f9c`
- `0x180019290`
- `0x18001b380`
- `0x18001bb58`
- `0x18001bb7c`
- `0x18001bb82`
- `0x18001bb94`
- `0x18001bbac`
- `0x18001bbe2`
- `0x18001bbfa`
- `0x18001bc00`
- `0x18001bdd2`
- `0x18001d6e0`

## pseudocode

```c
__int64 __fastcall avformat_open_input(__int64 *a1, __int16 *a2, __int64 a3, _QWORD *a4)
{
  __int64 v4; // rbx
  __int64 result; // rax
  int v10; // edi
  __int16 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 (__fastcall *v26)(__int64); // rax
  _QWORD *v27; // rdi
  void (__fastcall *v28)(__int64); // rax
  __int64 v29; // rcx
  _QWORD v30[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v31; // [rsp+60h] [rbp+30h] BYREF

  v4 = *a1;
  v30[0] = 0;
  v31 = 0;
  if ( !v4 )
  {
    v4 = avformat_alloc_context();
    if ( !v4 )
      return 4294967284LL;
  }
  if ( !*(_QWORD *)v4 )
  {
    av_log(0, 16, "Input context has not been properly allocated by avformat_alloc_context() and is not NULL either\n");
    return 4294967274LL;
  }
  if ( a3 )
    *(_QWORD *)(v4 + 8) = a3;
  if ( a4 )
    av_dict_copy();
  if ( *(_QWORD *)(v4 + 32) )
    *(_DWORD *)(v4 + 128) |= 0x80u;
  v10 = av_opt_set_dict(v4, v30);
  if ( v10 < 0 )
    goto LABEL_17;
  v11 = word_180020A62;
  if ( a2 )
    v11 = a2;
  v12 = av_strdup(v11);
  *(_QWORD *)(v4 + 88) = v12;
  if ( !v12 )
    goto LABEL_16;
  _mm_lfence();
  v13 = sub_18000A258(v4, a2, v30);
  v10 = v13;
  if ( v13 < 0 )
    goto LABEL_17;
  *(_DWORD *)(v4 + 324) = v13;
  if ( !*(_QWORD *)(v4 + 352) )
  {
    _mm_lfence();
    v15 = *(_QWORD *)(v4 + 32);
    if ( v15 )
    {
      v16 = *(_QWORD *)(v15 + 144);
      if ( v16 )
      {
        v17 = av_strdup(v16);
        *(_QWORD *)(v4 + 352) = v17;
        if ( !v17 )
          goto LABEL_16;
      }
    }
  }
  if ( !*(_QWORD *)(v4 + 360) )
  {
    _mm_lfence();
    v18 = *(_QWORD *)(v4 + 32);
    if ( v18 )
    {
      v19 = *(_QWORD *)(v18 + 152);
      if ( v19 )
      {
        v20 = av_strdup(v19);
        *(_QWORD *)(v4 + 360) = v20;
        if ( !v20 )
          goto LABEL_16;
      }
    }
  }
  _mm_lfence();
  v21 = *(_QWORD *)(v4 + 344);
  if ( v21 )
  {
    _mm_lfence();
    LOBYTE(v14) = 44;
    if ( (int)av_match_list(**(_QWORD **)(v4 + 8), v21, v14) <= 0 )
    {
      _mm_lfence();
      av_log(v4, 16, "Format not on whitelist '%s'\n", *(const char **)(v4 + 344));
LABEL_33:
      v10 = -22;
      goto LABEL_17;
    }
  }
  _mm_lfence();
  avio_skip(*(_QWORD *)(v4 + 32), *(_QWORD *)(v4 + 304));
  if ( (*(_BYTE *)(*(_QWORD *)(v4 + 8) + 16LL) & 2) != 0 )
  {
    _mm_lfence();
    if ( !(unsigned int)av_filename_number_test(a2) )
      goto LABEL_33;
  }
  _mm_lfence();
  *(_QWORD *)(v4 + 96) = 0x8000000000000000uLL;
  *(_QWORD *)(v4 + 104) = 0x8000000000000000uLL;
  v22 = *(int *)(*(_QWORD *)(v4 + 8) + 60LL);
  if ( (int)v22 > 0 )
  {
    _mm_lfence();
    v23 = (_QWORD *)av_mallocz(v22);
    *(_QWORD *)(v4 + 24) = v23;
    if ( v23 )
    {
      _mm_lfence();
      v24 = *(_QWORD *)(*(_QWORD *)(v4 + 8) + 40LL);
      if ( v24 )
      {
        _mm_lfence();
        *v23 = v24;
        av_opt_set_defaults(*(_QWORD *)(v4 + 24));
        v10 = av_opt_set_dict(*(_QWORD *)(v4 + 24), v30);
        if ( v10 < 0 )
          goto LABEL_17;
      }
      goto LABEL_40;
    }
LABEL_16:
    v10 = -12;
LABEL_17:
    sub_180010BF4(&v31);
    av_dict_free(v30);
    if ( *(_QWORD *)(v4 + 32) )
    {
      if ( *(char *)(v4 + 128) >= 0 )
        avio_closep(v4 + 32);
    }
    avformat_free_context(v4);
    result = (unsigned int)v10;
    *a1 = 0;
    return result;
  }
LABEL_40:
  _mm_lfence();
  v25 = *(_QWORD *)(v4 + 32);
  if ( v25 )
  {
    _mm_lfence();
    sub_180010F9C(v25, v4 + 528, "ID3", &v31);
  }
  v26 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v4 + 8) + 80LL);
  if ( v26 )
  {
    _mm_lfence();
    v10 = v26(v4);
    if ( v10 < 0 )
    {
      _mm_lfence();
      if ( (*(_BYTE *)(*(_QWORD *)(v4 + 8) + 64LL) & 1) == 0 )
        goto LABEL_17;
LABEL_61:
      _mm_lfence();
      v28 = *(void (__fastcall **)(__int64))(*(_QWORD *)(v4 + 8) + 96LL);
      if ( v28 )
      {
        _mm_lfence();
        v28(v4);
      }
      goto LABEL_17;
    }
  }
  v27 = (_QWORD *)(v4 + 528);
  if ( *(_QWORD *)(v4 + 192) )
  {
    if ( *v27 )
    {
      _mm_lfence();
      av_log(v4, 24, "Discarding ID3 tags because more suitable tags were found.\n");
      av_dict_free(v4 + 528);
    }
  }
  else
  {
    *(_QWORD *)(v4 + 192) = *v27;
    *v27 = 0;
  }
  if ( v31 )
  {
    _mm_lfence();
    if ( !strcmp(**(const char ***)(v4 + 8), "mp3")
      || (_mm_lfence(), !strcmp(**(const char ***)(v4 + 8), "aac"))
      || (_mm_lfence(), !strcmp(**(const char ***)(v4 + 8), "tta"))
      || (_mm_lfence(), !strcmp(**(const char ***)(v4 + 8), "wav")) )
    {
      _mm_lfence();
      v10 = sub_180010CB8(v4, v31);
      if ( v10 < 0 )
        goto LABEL_61;
      _mm_lfence();
      v10 = sub_180010DA0(v4, v31);
      if ( v10 < 0 )
        goto LABEL_61;
      _mm_lfence();
      v10 = sub_180010E40(v4, v31);
      if ( v10 < 0 )
        goto LABEL_61;
    }
    else
    {
      _mm_lfence();
      av_log(v4, 48, "demuxer does not support additional id3 data, skipping\n");
    }
    sub_180010BF4(&v31);
  }
  _mm_lfence();
  v10 = avformat_queue_attached_pictures(v4);
  if ( v10 < 0 )
    goto LABEL_61;
  _mm_lfence();
  v29 = *(_QWORD *)(v4 + 32);
  if ( v29 && !*(_QWORD *)(v4 + 496) )
    *(_QWORD *)(v4 + 496) = avio_seek(v29, 0, 1);
  *(_DWORD *)(v4 + 560) = 0;
  sub_18000BE8C(v4);
  if ( a4 )
  {
    av_dict_free(a4);
    *a4 = v30[0];
  }
  *a1 = v4;
  return 0;
}

```

## disassembly

```asm
0x180007900  mov     [rsp-28h+arg_8], rbx
0x180007905  mov     [rsp-28h+arg_10], rsi
0x18000790a  push    rbp
0x18000790b  push    rdi
0x18000790c  push    r12
0x18000790e  push    r14
0x180007910  push    r15
0x180007912  mov     rbp, rsp
0x180007915  sub     rsp, 30h
0x180007919  mov     rbx, [rcx]
0x18000791c  xor     r12d, r12d
0x18000791f  mov     [rbp+var_10], r12
0x180007923  mov     rsi, r9
0x180007926  mov     [rbp+arg_0], r12
0x18000792a  mov     rdi, r8
0x18000792d  mov     r14, rdx
0x180007930  mov     r15, rcx
0x180007933  test    rbx, rbx
0x180007936  jnz     short loc_18000794D
0x180007938  call    avformat_alloc_context
0x18000793d  mov     rbx, rax
0x180007940  test    rax, rax
0x180007943  jnz     short loc_18000794D
0x180007945  lea     eax, [rbx-0Ch]
0x180007948  jmp     loc_180007A04
0x18000794d  cmp     [rbx], r12
0x180007950  jnz     short loc_18000796F
0x180007952  lea     r8, aInputContextHa; "Input context has not been properly all"...
0x180007959  mov     edx, 10h
0x18000795e  xor     ecx, ecx
0x180007960  call    av_log
0x180007965  mov     eax, 0FFFFFFEAh
0x18000796a  jmp     loc_180007A04
0x18000796f  test    rdi, rdi
0x180007972  jz      short loc_180007978
0x180007974  mov     [rbx+8], rdi
0x180007978  test    rsi, rsi
0x18000797b  jz      short loc_18000798C
0x18000797d  mov     rdx, [rsi]
0x180007980  lea     rcx, [rbp+var_10]
0x180007984  xor     r8d, r8d
0x180007987  call    av_dict_copy
0x18000798c  cmp     [rbx+20h], r12
0x180007990  jz      short loc_18000799A
0x180007992  bts     dword ptr [rbx+80h], 7
0x18000799a  lea     rdx, [rbp+var_10]
0x18000799e  mov     rcx, rbx
0x1800079a1  call    av_opt_set_dict
0x1800079a6  mov     edi, eax
0x1800079a8  test    eax, eax
0x1800079aa  js      short loc_1800079CD
0x1800079ac  test    r14, r14
0x1800079af  lea     rcx, word_180020A62
0x1800079b6  cmovnz  rcx, r14
0x1800079ba  call    av_strdup
0x1800079bf  mov     [rbx+58h], rax
0x1800079c3  test    rax, rax
0x1800079c6  jnz     short loc_180007A1B
0x1800079c8  mov     edi, 0FFFFFFF4h
0x1800079cd  lea     rcx, [rbp+arg_0]
0x1800079d1  call    sub_180010BF4
0x1800079d6  lea     rcx, [rbp+var_10]
0x1800079da  call    av_dict_free
0x1800079df  cmp     [rbx+20h], r12
0x1800079e3  jz      short loc_1800079F7
0x1800079e5  test    byte ptr [rbx+80h], 80h
0x1800079ec  jnz     short loc_1800079F7
0x1800079ee  lea     rcx, [rbx+20h]
0x1800079f2  call    avio_closep
0x1800079f7  mov     rcx, rbx
0x1800079fa  call    avformat_free_context
0x1800079ff  mov     eax, edi
0x180007a01  mov     [r15], r12
0x180007a04  mov     rbx, [rsp+30h+arg_8]
0x180007a09  mov     rsi, [rsp+30h+arg_10]
0x180007a0e  add     rsp, 30h
0x180007a12  pop     r15
0x180007a14  pop     r14
0x180007a16  pop     r12
0x180007a18  pop     rdi
0x180007a19  pop     rbp
0x180007a1a  retn
0x180007a1b  lfence
0x180007a1e  lea     r8, [rbp+var_10]
0x180007a22  mov     rdx, r14
0x180007a25  mov     rcx, rbx
0x180007a28  call    sub_18000A258
0x180007a2d  mov     edi, eax
0x180007a2f  test    eax, eax
0x180007a31  js      short loc_1800079CD
0x180007a33  mov     [rbx+144h], eax
0x180007a39  cmp     [rbx+160h], r12
0x180007a40  jnz     short loc_180007A6F
0x180007a42  lfence
0x180007a45  mov     rax, [rbx+20h]
0x180007a49  test    rax, rax
0x180007a4c  jz      short loc_180007A6F
0x180007a4e  mov     rcx, [rax+90h]
0x180007a55  test    rcx, rcx
0x180007a58  jz      short loc_180007A6F
0x180007a5a  call    av_strdup
0x180007a5f  mov     [rbx+160h], rax
0x180007a66  test    rax, rax
0x180007a69  jz      loc_1800079C8
0x180007a6f  cmp     [rbx+168h], r12
0x180007a76  jnz     short loc_180007AA5
0x180007a78  lfence
0x180007a7b  mov     rax, [rbx+20h]
0x180007a7f  test    rax, rax
0x180007a82  jz      short loc_180007AA5
0x180007a84  mov     rcx, [rax+98h]
0x180007a8b  test    rcx, rcx
0x180007a8e  jz      short loc_180007AA5
0x180007a90  call    av_strdup
0x180007a95  mov     [rbx+168h], rax
0x180007a9c  test    rax, rax
0x180007a9f  jz      loc_1800079C8
0x180007aa5  lfence
0x180007aa8  mov     rdx, [rbx+158h]
0x180007aaf  test    rdx, rdx
0x180007ab2  jz      short loc_180007AF2
0x180007ab4  lfence
0x180007ab7  mov     rcx, [rbx+8]
0x180007abb  mov     r8b, 2Ch ; ','
0x180007abe  mov     rcx, [rcx]
0x180007ac1  call    av_match_list
0x180007ac6  test    eax, eax
0x180007ac8  jg      short loc_180007AF2
0x180007aca  lfence
0x180007acd  mov     r9, [rbx+158h]
0x180007ad4  lea     r8, aFormatNotOnWhi; "Format not on whitelist '%s'\n"
0x180007adb  mov     edx, 10h
0x180007ae0  mov     rcx, rbx
0x180007ae3  call    av_log
0x180007ae8  mov     edi, 0FFFFFFEAh
0x180007aed  jmp     loc_1800079CD
0x180007af2  lfence
0x180007af5  mov     rdx, [rbx+130h]
0x180007afc  mov     rcx, [rbx+20h]
0x180007b00  call    avio_skip
0x180007b05  mov     rax, [rbx+8]
0x180007b09  test    byte ptr [rax+10h], 2
0x180007b0d  jz      short loc_180007B1E
0x180007b0f  lfence
0x180007b12  mov     rcx, r14
0x180007b15  call    av_filename_number_test
0x180007b1a  test    eax, eax
0x180007b1c  jz      short loc_180007AE8
0x180007b1e  lfence
0x180007b21  mov     rax, 8000000000000000h
0x180007b2b  mov     [rbx+60h], rax
0x180007b2f  mov     [rbx+68h], rax
0x180007b33  mov     rax, [rbx+8]
0x180007b37  movsxd  rcx, dword ptr [rax+3Ch]
0x180007b3b  test    ecx, ecx
0x180007b3d  jle     short loc_180007B8D
0x180007b3f  lfence
0x180007b42  call    av_mallocz
0x180007b47  mov     [rbx+18h], rax
0x180007b4b  mov     rcx, rax
0x180007b4e  test    rax, rax
0x180007b51  jz      loc_1800079C8
0x180007b57  lfence
0x180007b5a  mov     rax, [rbx+8]
0x180007b5e  mov     rdx, [rax+28h]
0x180007b62  test    rdx, rdx
0x180007b65  jz      short loc_180007B8D
0x180007b67  lfence
0x180007b6a  mov     [rcx], rdx
0x180007b6d  mov     rcx, [rbx+18h]
0x180007b71  call    av_opt_set_defaults
0x180007b76  mov     rcx, [rbx+18h]
0x180007b7a  lea     rdx, [rbp+var_10]
0x180007b7e  call    av_opt_set_dict
0x180007b83  mov     edi, eax
0x180007b85  test    eax, eax
0x180007b87  js      loc_1800079CD
0x180007b8d  lfence
0x180007b90  mov     rcx, [rbx+20h]
0x180007b94  test    rcx, rcx
0x180007b97  jz      short loc_180007BB3
0x180007b99  lfence
0x180007b9c  lea     rdx, [rbx+210h]
0x180007ba3  lea     r9, [rbp+arg_0]
0x180007ba7  lea     r8, aId3; "ID3"
0x180007bae  call    sub_180010F9C
0x180007bb3  mov     rax, [rbx+8]
0x180007bb7  mov     rax, [rax+50h]
0x180007bbb  test    rax, rax
0x180007bbe  jz      short loc_180007BE8
0x180007bc0  lfence
0x180007bc3  mov     rcx, rbx
0x180007bc6  call    cs:__guard_dispatch_icall_fptr
0x180007bcc  mov     edi, eax
0x180007bce  test    eax, eax
0x180007bd0  jns     short loc_180007BE8
0x180007bd2  lfence
0x180007bd5  mov     rax, [rbx+8]
0x180007bd9  test    byte ptr [rax+40h], 1
0x180007bdd  jnz     loc_180007D0F
0x180007be3  jmp     loc_1800079CD
0x180007be8  lea     rdi, [rbx+210h]
0x180007bef  cmp     [rbx+0C0h], r12
0x180007bf6  jnz     short loc_180007C07
0x180007bf8  mov     rax, [rdi]
0x180007bfb  mov     [rbx+0C0h], rax
0x180007c02  mov     [rdi], r12
0x180007c05  jmp     short loc_180007C2B
0x180007c07  cmp     [rdi], r12
0x180007c0a  jz      short loc_180007C2B
0x180007c0c  lfence
0x180007c0f  lea     r8, aDiscardingId3T; "Discarding ID3 tags because more suitab"...
0x180007c16  mov     edx, 18h
0x180007c1b  mov     rcx, rbx
0x180007c1e  call    av_log
0x180007c23  mov     rcx, rdi
0x180007c26  call    av_dict_free
0x180007c2b  cmp     [rbp+arg_0], r12
0x180007c2f  jz      loc_180007CFE
0x180007c35  lfence
0x180007c38  mov     rcx, [rbx+8]
0x180007c3c  lea     rdx, aMp3; "mp3"
0x180007c43  mov     rcx, [rcx]; Str1
0x180007c46  call    strcmp
0x180007c4b  test    eax, eax
0x180007c4d  jz      short loc_180007CB6
0x180007c4f  lfence
0x180007c52  mov     rcx, [rbx+8]
0x180007c56  lea     rdx, aAac; "aac"
0x180007c5d  mov     rcx, [rcx]; Str1
0x180007c60  call    strcmp
0x180007c65  test    eax, eax
0x180007c67  jz      short loc_180007CB6
0x180007c69  lfence
0x180007c6c  mov     rcx, [rbx+8]
0x180007c70  lea     rdx, aTta; "tta"
0x180007c77  mov     rcx, [rcx]; Str1
0x180007c7a  call    strcmp
0x180007c7f  test    eax, eax
0x180007c81  jz      short loc_180007CB6
0x180007c83  lfence
0x180007c86  mov     rcx, [rbx+8]
0x180007c8a  lea     rdx, aWav; "wav"
0x180007c91  mov     rcx, [rcx]; Str1
0x180007c94  call    strcmp
0x180007c99  test    eax, eax
0x180007c9b  jz      short loc_180007CB6
0x180007c9d  lfence
0x180007ca0  lea     r8, aDemuxerDoesNot; "demuxer does not support additional id3"...
0x180007ca7  mov     edx, 30h ; '0'
0x180007cac  mov     rcx, rbx
0x180007caf  call    av_log
0x180007cb4  jmp     short loc_180007CF5
0x180007cb6  lfence
0x180007cb9  mov     rdx, [rbp+arg_0]
0x180007cbd  mov     rcx, rbx
0x180007cc0  call    sub_180010CB8
0x180007cc5  mov     edi, eax
0x180007cc7  test    eax, eax
0x180007cc9  js      short loc_180007D0F
0x180007ccb  lfence
0x180007cce  mov     rdx, [rbp+arg_0]
0x180007cd2  mov     rcx, rbx
0x180007cd5  call    sub_180010DA0
0x180007cda  mov     edi, eax
0x180007cdc  test    eax, eax
0x180007cde  js      short loc_180007D0F
0x180007ce0  lfence
0x180007ce3  mov     rdx, [rbp+arg_0]
0x180007ce7  mov     rcx, rbx
0x180007cea  call    sub_180010E40
0x180007cef  mov     edi, eax
0x180007cf1  test    eax, eax
0x180007cf3  js      short loc_180007D0F
0x180007cf5  lea     rcx, [rbp+arg_0]
0x180007cf9  call    sub_180010BF4
0x180007cfe  lfence
0x180007d01  mov     rcx, rbx
0x180007d04  call    avformat_queue_attached_pictures
0x180007d09  mov     edi, eax
0x180007d0b  test    eax, eax
0x180007d0d  jns     short loc_180007D34
0x180007d0f  lfence
0x180007d12  mov     rax, [rbx+8]
0x180007d16  mov     rax, [rax+60h]
0x180007d1a  test    rax, rax
0x180007d1d  jz      loc_1800079CD
0x180007d23  lfence
0x180007d26  mov     rcx, rbx
0x180007d29  call    cs:__guard_dispatch_icall_fptr
0x180007d2f  jmp     loc_1800079CD
0x180007d34  lfence
0x180007d37  mov     rcx, [rbx+20h]
0x180007d3b  test    rcx, rcx
0x180007d3e  jz      short loc_180007D5B
0x180007d40  cmp     [rbx+1F0h], r12
0x180007d47  jnz     short loc_180007D5B
0x180007d49  xor     edx, edx
0x180007d4b  lea     r8d, [rdx+1]
0x180007d4f  call    avio_seek
  ... truncated ...
```
