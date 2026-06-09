# CIVIAudioCodec::DecodeAll(uchar *,long,int,eSTM_TYPE,uchar *,uchar)

- ea: `0x18001ab80`
- end: `0x18001b1c6`
- name: `?DecodeAll@CIVIAudioCodec@@IEAAJPEAEJHW4eSTM_TYPE@@0E@Z`
- size: `1606`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, int, __int64, int, unsigned int *, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011860`

## callees

- `0x1800017b0`
- `0x180019d60`
- `0x18001ab80`
- `0x18001b1d0`
- `0x18001b610`
- `0x18001bb60`
- `0x18001cba0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ae2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001aeb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001af4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001afd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b0d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b14e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ae2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001aeb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001af4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001afd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b0d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b14e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001adf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001adf5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001adbf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001adbf`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001ade5`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001ade5`

## pseudocode

```c
__int64 __fastcall CIVIAudioCodec::DecodeAll(
        __int64 a1,
        unsigned __int8 *a2,
        int a3,
        __int64 a4,
        int a5,
        unsigned int *a6,
        char a7)
{
  int v8; // edx
  int v10; // r14d
  int v11; // r12d
  int v12; // esi
  int v13; // r13d
  int v14; // r15d
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdi
  GUID *v18; // rax
  int v19; // eax
  __int64 v20; // rdi
  GUID *v21; // rax
  __int64 v22; // rdi
  GUID *v23; // rax
  __int64 v24; // rdi
  GUID *v25; // rax
  __int64 v26; // rdi
  GUID *v27; // rax
  __int64 v28; // rdi
  GUID *v29; // rax
  __int64 v30; // rdi
  GUID *v31; // rax
  unsigned int v33; // [rsp+40h] [rbp-30h] BYREF
  int v34; // [rsp+44h] [rbp-2Ch] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-20h] BYREF

  v8 = *(_DWORD *)(a1 + 6220);
  v10 = *(_DWORD *)(a1 + 6324);
  v11 = *(_DWORD *)(a1 + 6312);
  v12 = *(_DWORD *)(a1 + 6316);
  v13 = *(_DWORD *)(a1 + 6320);
  v14 = *(_DWORD *)(a1 + 6256);
  if ( v8 == *(_DWORD *)(a1 + 6224) || (v15 = *(_DWORD *)(a1 + 6260), v15 == 99) )
  {
    v15 = *(_DWORD *)(a1 + 6256);
  }
  else
  {
    *(_DWORD *)(a1 + 6256) = v15;
    *(_DWORD *)(a1 + 6260) = 99;
  }
  *(_DWORD *)(a1 + 5936) = 1;
  switch ( v8 )
  {
    case 5:
      CIVIAudioCodec::DecodeLPCM(a1, a2, a3, a4, a5);
      break;
    case 3:
    case 24:
      if ( v15 == 3 )
      {
        if ( *(_DWORD *)(a1 + 6280) != 1 && (*(float *)(a1 + 6340) == 1.0 || !*(_DWORD *)(a1 + 6232)) )
          break;
        *(_DWORD *)(a1 + 6256) = 0;
        *(_DWORD *)(a1 + 6260) = 3;
      }
      else
      {
        if ( v15
          || *(_DWORD *)(a1 + 6260) != 3
          || *(_DWORD *)(a1 + 6280)
          || *(float *)(a1 + 6340) != 1.0
          || !*(_DWORD *)(a1 + 6232) )
        {
          break;
        }
        *(_DWORD *)(a1 + 6256) = 3;
        *(_DWORD *)(a1 + 6260) = 99;
      }
      *(_DWORD *)(a1 + 8) = 1;
      break;
    case 6:
      if ( v15 == 3 )
      {
        if ( *(float *)(a1 + 6340) == 1.0 || !*(_DWORD *)(a1 + 6232) )
          goto LABEL_20;
        *(_DWORD *)(a1 + 6256) = 0;
        *(_DWORD *)(a1 + 6260) = 3;
      }
      else
      {
        if ( v15 || *(_DWORD *)(a1 + 6260) != 3 || *(float *)(a1 + 6340) != 1.0 || !*(_DWORD *)(a1 + 6232) )
          goto LABEL_20;
        *(_DWORD *)(a1 + 6256) = 3;
        *(_DWORD *)(a1 + 6260) = 99;
      }
      *(_DWORD *)(a1 + 8) = 1;
LABEL_20:
      CIVIAudioCodec::DecodeDTS((int *)a1, (char *)a2, a3, a4, a5);
      break;
    case 4:
      CIVIAudioCodec::DecodeMPEG(a1, (char *)a2, a3, a4, a5, a6, a7);
      break;
    case 9:
      CIVIAudioCodec::DecodeAAC((CIVIAudioCodec *)a1, a2, a3);
      break;
  }
  v16 = *(_DWORD *)(a1 + 6220);
  if ( *(_DWORD *)(a1 + 6224) != v16 )
  {
    v33 = 0;
    v34 = v16;
    UserData.Ptr = (ULONGLONG)&v34;
    *(_QWORD *)&UserData.Size = 4;
    if ( a1 != -24 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
      if ( !*(_DWORD *)(a1 + 24) )
        EventWrite(*(_QWORD *)(a1 + 32), &MSMPEG2ADEC_AUD_CODECTYPE_CHANGE, 1u, &UserData);
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
    }
    if ( !(unsigned int)CIVIAudioCodec::MapCodecAPIToIndex(
                          (CIVIAudioCodec *)a1,
                          &GUID_e5005239_bd89_4be3_9c0f_5dde317988cc,
                          &v33) )
    {
      v17 = v33;
      if ( *(_DWORD *)(a1 + 16LL * v33 + 5768) )
      {
        v18 = (GUID *)CoTaskMemAlloc(0x20u);
        if ( v18 )
        {
          v18[1].Data1 = 0;
          *v18 = GUID_e5005239_bd89_4be3_9c0f_5dde317988cc;
          (*(void (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)a1 + 72LL))(
            a1,
            87,
            *(_QWORD *)(a1 + 16 * (v17 + 361)),
            v18);
        }
      }
    }
  }
  v19 = *(_DWORD *)(a1 + 6228);
  *(_DWORD *)(a1 + 6324) = v19;
  if ( v10 != v19 )
  {
    v33 = 0;
    if ( !(unsigned int)CIVIAudioCodec::MapCodecAPIToIndex(
                          (CIVIAudioCodec *)a1,
                          &GUID_971d2723_1acb_42e7_855c_520a4b70a5f2,
                          &v33) )
    {
      v20 = v33;
      if ( *(_DWORD *)(a1 + 16LL * v33 + 5768) )
      {
        v21 = (GUID *)CoTaskMemAlloc(0x20u);
        if ( v21 )
        {
          v21[1].Data1 = 0;
          *v21 = GUID_971d2723_1acb_42e7_855c_520a4b70a5f2;
          (*(void (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)a1 + 72LL))(
            a1,
            87,
            *(_QWORD *)(a1 + 16 * (v20 + 361)),
            v21);
        }
      }
    }
  }
  if ( *(_DWORD *)(a1 + 6328) != *(_DWORD *)(a1 + 6332) && *(_DWORD *)(a1 + 6336) >= 0xAu )
  {
    v33 = 0;
    if ( !(unsigned int)CIVIAudioCodec::MapCodecAPIToIndex(
                          (CIVIAudioCodec *)a1,
                          &GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d,
                          &v33) )
    {
      v22 = v33;
      if ( *(_DWORD *)(a1 + 16LL * v33 + 5768) )
      {
        v23 = (GUID *)CoTaskMemAlloc(0x20u);
        if ( v23 )
        {
          v23[1].Data1 = 0;
          *v23 = GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d;
          (*(void (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)a1 + 72LL))(
            a1,
            87,
            *(_QWORD *)(a1 + 16 * (v22 + 361)),
            v23);
          *(_DWORD *)(a1 + 6328) = *(_DWORD *)(a1 + 6332);
        }
      }
    }
  }
  if ( v11 != *(_DWORD *)(a1 + 6312) )
  {
    v33 = 0;
    if ( !(unsigned int)CIVIAudioCodec::MapCodecAPIToIndex(
                          (CIVIAudioCodec *)a1,
                          &GUID_1d3583c4_1583_474e_b71a_5ee463c198e4,
                          &v33) )
    {
      v24 = v33;
      if ( *(_DWORD *)(a1 + 16LL * v33 + 5768) )
      {
        v25 = (GUID *)CoTaskMemAlloc(0x20u);
        if ( v25 )
        {
          v25[1].Data1 = 0;
          *v25 = GUID_1d3583c4_1583_474e_b71a_5ee463c198e4;
          (*(void (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)a1 + 72LL))(
            a1,
            87,
            *(_QWORD *)(a1 + 16 * (v24 + 361)),
            v25);
        }
      }
    }
  }
  if ( v13 != *(_DWORD *)(a1 + 6320) )
  {
    v33 = 0;
    if ( !(unsigned int)CIVIAudioCodec::MapCodecAPIToIndex(
                          (CIVIAudioCodec *)a1,
                          &GUID_59488217_007a_4f7a_8e41_5c48b1eac5c6,
                          &v33) )
    {
      v26 = v33;
      if ( *(_DWORD *)(a1 + 16LL * v33 + 5768) )
      {
        v27 = (GUID *)CoTaskMemAlloc(0x20u);
        if ( v27 )
        {
          v27[1].Data1 = 0;
          *v27 = GUID_59488217_007a_4f7a_8e41_5c48b1eac5c6;
          (*(void (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)a1 + 72LL))(
            a1,
            87,
            *(_QWORD *)(a1 + 16 * (v26 + 361)),
            v27);
        }
      }
    }
  }
  if ( v12 != *(_DWORD *)(a1 + 6316) )
  {
    v33 = 0;
    if ( !(unsigned int)CIVIAudioCodec::MapCodecAPIToIndex(
                          (CIVIAudioCodec *)a1,
                          &GUID_17f89cb3_c38d_4368_9ede_63b94d177f9f,
                          &v33) )
    {
      v28 = v33;
      if ( *(_DWORD *)(a1 + 16LL * v33 + 5768) )
      {
        v29 = (GUID *)CoTaskMemAlloc(0x20u);
        if ( v29 )
        {
          v29[1].Data1 = 0;
          *v29 = GUID_17f89cb3_c38d_4368_9ede_63b94d177f9f;
          (*(void (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)a1 + 72LL))(
            a1,
            87,
            *(_QWORD *)(a1 + 16 * (v28 + 361)),
            v29);
        }
      }
    }
  }
  if ( v14 != *(_DWORD *)(a1 + 6256) )
  {
    v33 = 0;
    if ( !(unsigned int)CIVIAudioCodec::MapCodecAPIToIndex(
                          (CIVIAudioCodec *)a1,
                          &GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc,
                          &v33) )
    {
      v30 = v33;
      if ( *(_DWORD *)(a1 + 16LL * v33 + 5768) )
      {
        v31 = (GUID *)CoTaskMemAlloc(0x20u);
        if ( v31 )
        {
          v31[1].Data1 = 0;
          *v31 = GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc;
          (*(void (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)a1 + 72LL))(
            a1,
            87,
            *(_QWORD *)(a1 + 16 * (v30 + 361)),
            v31);
        }
      }
    }
  }
  *(_DWORD *)(a1 + 6224) = *(_DWORD *)(a1 + 6220);
  return 0;
}

```

## disassembly

```asm
0x18001ab80  mov     [rsp-38h+arg_18], rbx
0x18001ab85  push    rbp
0x18001ab86  push    rsi
0x18001ab87  push    rdi
0x18001ab88  push    r12
0x18001ab8a  push    r13
0x18001ab8c  push    r14
0x18001ab8e  push    r15
0x18001ab90  mov     rbp, rsp
0x18001ab93  sub     rsp, 70h
0x18001ab97  mov     rax, cs:__security_cookie
0x18001ab9e  xor     rax, rsp
0x18001aba1  mov     [rbp+var_10], rax
0x18001aba5  mov     r11, [rbp+arg_28]
0x18001aba9  mov     r10, rdx
0x18001abac  mov     edx, [rcx+184Ch]
0x18001abb2  mov     rbx, rcx
0x18001abb5  mov     r14d, [rcx+18B4h]
0x18001abbc  mov     r12d, [rcx+18A8h]
0x18001abc3  mov     esi, [rcx+18ACh]
0x18001abc9  mov     r13d, [rcx+18B0h]
0x18001abd0  mov     r15d, [rcx+1870h]
0x18001abd7  cmp     edx, [rcx+1850h]
0x18001abdd  jz      short loc_18001ABFC
0x18001abdf  mov     eax, [rcx+1874h]
0x18001abe5  cmp     eax, 63h ; 'c'
0x18001abe8  jz      short loc_18001ABFC
0x18001abea  mov     [rcx+1870h], eax
0x18001abf0  mov     dword ptr [rcx+1874h], 63h ; 'c'
0x18001abfa  jmp     short loc_18001ABFF
0x18001abfc  mov     eax, r15d
0x18001abff  xor     edi, edi
0x18001ac01  mov     dword ptr [rcx+1730h], 1
0x18001ac0b  cmp     edx, 5
0x18001ac0e  jnz     short loc_18001AC24
0x18001ac10  mov     eax, [rbp+arg_20]
0x18001ac13  mov     rdx, r10
0x18001ac16  mov     [rsp+70h+var_50], eax
0x18001ac1a  call    ?DecodeLPCM@CIVIAudioCodec@@IEAAJPEAEJHW4eSTM_TYPE@@@Z; CIVIAudioCodec::DecodeLPCM(uchar *,long,int,eSTM_TYPE)
0x18001ac1f  jmp     loc_18001AD8A
0x18001ac24  cmp     edx, 3
0x18001ac27  jz      loc_18001AD04
0x18001ac2d  cmp     edx, 18h
0x18001ac30  jz      loc_18001AD04
0x18001ac36  cmp     edx, 6
0x18001ac39  jnz     loc_18001ACC8
0x18001ac3f  cmp     eax, 3
0x18001ac42  jnz     short loc_18001AC71
0x18001ac44  movss   xmm0, dword ptr [rcx+18C4h]
0x18001ac4c  ucomiss xmm0, cs:__real@3f800000
0x18001ac53  jp      short loc_18001AC57
0x18001ac55  jz      short loc_18001ACB4
0x18001ac57  cmp     [rcx+1858h], edi
0x18001ac5d  jz      short loc_18001ACB4
0x18001ac5f  mov     [rcx+1870h], edi
0x18001ac65  mov     dword ptr [rcx+1874h], 3
0x18001ac6f  jmp     short loc_18001ACAD
0x18001ac71  test    eax, eax
0x18001ac73  jnz     short loc_18001ACB4
0x18001ac75  cmp     dword ptr [rcx+1874h], 3
0x18001ac7c  jnz     short loc_18001ACB4
0x18001ac7e  movss   xmm0, dword ptr [rcx+18C4h]
0x18001ac86  ucomiss xmm0, cs:__real@3f800000
0x18001ac8d  jp      short loc_18001ACB4
0x18001ac8f  jnz     short loc_18001ACB4
0x18001ac91  cmp     [rcx+1858h], edi
0x18001ac97  jz      short loc_18001ACB4
0x18001ac99  mov     dword ptr [rcx+1870h], 3
0x18001aca3  mov     dword ptr [rcx+1874h], 63h ; 'c'
0x18001acad  mov     dword ptr [rcx+8], 1
0x18001acb4  mov     eax, [rbp+arg_20]
0x18001acb7  mov     rdx, r10
0x18001acba  mov     [rsp+70h+var_50], eax
0x18001acbe  call    ?DecodeDTS@CIVIAudioCodec@@IEAAJPEAEJHW4eSTM_TYPE@@@Z; CIVIAudioCodec::DecodeDTS(uchar *,long,int,eSTM_TYPE)
0x18001acc3  jmp     loc_18001AD8A
0x18001acc8  cmp     edx, 4
0x18001accb  jnz     short loc_18001ACEE
0x18001accd  movzx   eax, [rbp+arg_30]
0x18001acd1  mov     rdx, r10
0x18001acd4  mov     [rsp+70h+var_40], al
0x18001acd8  mov     eax, [rbp+arg_20]
0x18001acdb  mov     [rsp+70h+var_48], r11
0x18001ace0  mov     [rsp+70h+var_50], eax
0x18001ace4  call    ?DecodeMPEG@CIVIAudioCodec@@IEAAJPEAEJHW4eSTM_TYPE@@0E@Z; CIVIAudioCodec::DecodeMPEG(uchar *,long,int,eSTM_TYPE,uchar *,uchar)
0x18001ace9  jmp     loc_18001AD8A
0x18001acee  cmp     edx, 9
0x18001acf1  jnz     loc_18001AD8A
0x18001acf7  mov     rdx, r10; unsigned __int8 *
0x18001acfa  call    ?DecodeAAC@CIVIAudioCodec@@IEAAJPEAEJ@Z; CIVIAudioCodec::DecodeAAC(uchar *,long)
0x18001acff  jmp     loc_18001AD8A
0x18001ad04  cmp     eax, 3
0x18001ad07  jnz     short loc_18001AD3F
0x18001ad09  cmp     dword ptr [rcx+1888h], 1
0x18001ad10  jz      short loc_18001AD2D
0x18001ad12  movss   xmm0, dword ptr [rcx+18C4h]
0x18001ad1a  ucomiss xmm0, cs:__real@3f800000
0x18001ad21  jp      short loc_18001AD25
0x18001ad23  jz      short loc_18001AD8A
0x18001ad25  cmp     [rcx+1858h], edi
0x18001ad2b  jz      short loc_18001AD8A
0x18001ad2d  mov     [rcx+1870h], edi
0x18001ad33  mov     dword ptr [rcx+1874h], 3
0x18001ad3d  jmp     short loc_18001AD83
0x18001ad3f  test    eax, eax
0x18001ad41  jnz     short loc_18001AD8A
0x18001ad43  cmp     dword ptr [rcx+1874h], 3
0x18001ad4a  jnz     short loc_18001AD8A
0x18001ad4c  cmp     [rcx+1888h], edi
0x18001ad52  jnz     short loc_18001AD8A
0x18001ad54  movss   xmm0, dword ptr [rcx+18C4h]
0x18001ad5c  ucomiss xmm0, cs:__real@3f800000
0x18001ad63  jp      short loc_18001AD8A
0x18001ad65  jnz     short loc_18001AD8A
0x18001ad67  cmp     [rcx+1858h], edi
0x18001ad6d  jz      short loc_18001AD8A
0x18001ad6f  mov     dword ptr [rcx+1870h], 3
0x18001ad79  mov     dword ptr [rcx+1874h], 63h ; 'c'
0x18001ad83  mov     dword ptr [rcx+8], 1
0x18001ad8a  mov     eax, [rbx+184Ch]
0x18001ad90  cmp     [rbx+1850h], eax
0x18001ad96  jz      loc_18001AE74
0x18001ad9c  mov     [rbp+var_30], edi
0x18001ad9f  lea     rdi, [rbx+18h]
0x18001ada3  mov     [rbp+var_2C], eax
0x18001ada6  lea     rax, [rbp+var_2C]
0x18001adaa  mov     [rbp+UserData.Ptr], rax
0x18001adae  mov     qword ptr [rbp+UserData.Size], 4
0x18001adb6  test    rdi, rdi
0x18001adb9  jz      short loc_18001AE01
0x18001adbb  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001adbf  call    cs:__imp_EnterCriticalSection
0x18001adc6  nop     dword ptr [rax+rax+00h]
0x18001adcb  cmp     dword ptr [rdi], 0
0x18001adce  jnz     short loc_18001ADF1
0x18001add0  mov     rcx, [rdi+8]; RegHandle
0x18001add4  lea     r9, [rbp+UserData]; UserData
0x18001add8  mov     r8d, 1; UserDataCount
0x18001adde  lea     rdx, MSMPEG2ADEC_AUD_CODECTYPE_CHANGE; EventDescriptor
0x18001ade5  call    cs:__imp_EventWrite
0x18001adec  nop     dword ptr [rax+rax+00h]
0x18001adf1  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001adf5  call    cs:__imp_LeaveCriticalSection
0x18001adfc  nop     dword ptr [rax+rax+00h]
0x18001ae01  lea     r8, [rbp+var_30]; unsigned int *
0x18001ae05  lea     rdx, _GUID_e5005239_bd89_4be3_9c0f_5dde317988cc; struct _GUID *
0x18001ae0c  call    ?MapCodecAPIToIndex@CIVIAudioCodec@@IEAAJPEBU_GUID@@PEAK@Z; CIVIAudioCodec::MapCodecAPIToIndex(_GUID const *,ulong *)
0x18001ae11  test    eax, eax
0x18001ae13  jnz     short loc_18001AE74
0x18001ae15  mov     edi, [rbp+var_30]
0x18001ae18  mov     eax, edi
0x18001ae1a  add     rax, rax
0x18001ae1d  cmp     dword ptr [rbx+rax*8+1688h], 0
0x18001ae25  jz      short loc_18001AE74
0x18001ae27  mov     ecx, 20h ; ' '; cb
0x18001ae2c  call    cs:__imp_CoTaskMemAlloc
0x18001ae33  nop     dword ptr [rax+rax+00h]
0x18001ae38  mov     r9, rax
0x18001ae3b  test    rax, rax
0x18001ae3e  jz      short loc_18001AE74
0x18001ae40  movups  xmm0, xmmword ptr cs:_GUID_e5005239_bd89_4be3_9c0f_5dde317988cc.Data1
0x18001ae47  mov     dword ptr [rax+10h], 0
0x18001ae4e  lea     r8, [rdi+169h]
0x18001ae55  add     r8, r8
0x18001ae58  mov     edx, 57h ; 'W'
0x18001ae5d  movups  xmmword ptr [rax], xmm0
0x18001ae60  mov     rcx, [rbx]
0x18001ae63  mov     r8, [rbx+r8*8]
0x18001ae67  mov     rax, [rcx+48h]
0x18001ae6b  mov     rcx, rbx
0x18001ae6e  call    cs:__guard_dispatch_icall_fptr
0x18001ae74  mov     eax, [rbx+1854h]
0x18001ae7a  mov     [rbx+18B4h], eax
0x18001ae80  cmp     r14d, eax
0x18001ae83  jz      short loc_18001AEFE
0x18001ae85  xor     r14d, r14d
0x18001ae88  lea     r8, [rbp+var_30]; unsigned int *
0x18001ae8c  lea     rdx, _GUID_971d2723_1acb_42e7_855c_520a4b70a5f2; struct _GUID *
0x18001ae93  mov     [rbp+var_30], r14d
0x18001ae97  call    ?MapCodecAPIToIndex@CIVIAudioCodec@@IEAAJPEBU_GUID@@PEAK@Z; CIVIAudioCodec::MapCodecAPIToIndex(_GUID const *,ulong *)
0x18001ae9c  test    eax, eax
0x18001ae9e  jnz     short loc_18001AF01
0x18001aea0  mov     edi, [rbp+var_30]
0x18001aea3  mov     eax, edi
0x18001aea5  add     rax, rax
0x18001aea8  cmp     [rbx+rax*8+1688h], r14d
0x18001aeb0  jz      short loc_18001AF01
0x18001aeb2  mov     ecx, 20h ; ' '; cb
0x18001aeb7  call    cs:__imp_CoTaskMemAlloc
0x18001aebe  nop     dword ptr [rax+rax+00h]
0x18001aec3  mov     r9, rax
0x18001aec6  test    rax, rax
0x18001aec9  jz      short loc_18001AF01
0x18001aecb  movups  xmm0, xmmword ptr cs:_GUID_971d2723_1acb_42e7_855c_520a4b70a5f2.Data1
0x18001aed2  mov     [rax+10h], r14d
0x18001aed6  lea     r8, [rdi+169h]
0x18001aedd  add     r8, r8
0x18001aee0  mov     edx, 57h ; 'W'
0x18001aee5  movups  xmmword ptr [rax], xmm0
0x18001aee8  mov     rcx, [rbx]
0x18001aeeb  mov     r8, [rbx+r8*8]
0x18001aeef  mov     rax, [rcx+48h]
0x18001aef3  mov     rcx, rbx
0x18001aef6  call    cs:__guard_dispatch_icall_fptr
0x18001aefc  jmp     short loc_18001AF01
0x18001aefe  xor     r14d, r14d
0x18001af01  mov     eax, [rbx+18BCh]
0x18001af07  cmp     [rbx+18B8h], eax
0x18001af0d  jz      loc_18001AFA0
0x18001af13  cmp     dword ptr [rbx+18C0h], 0Ah
0x18001af1a  jb      loc_18001AFA0
0x18001af20  lea     r8, [rbp+var_30]; unsigned int *
0x18001af24  mov     [rbp+var_30], r14d
0x18001af28  lea     rdx, _GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d; struct _GUID *
0x18001af2f  call    ?MapCodecAPIToIndex@CIVIAudioCodec@@IEAAJPEBU_GUID@@PEAK@Z; CIVIAudioCodec::MapCodecAPIToIndex(_GUID const *,ulong *)
0x18001af34  test    eax, eax
0x18001af36  jnz     short loc_18001AFA0
0x18001af38  mov     edi, [rbp+var_30]
0x18001af3b  mov     eax, edi
0x18001af3d  add     rax, rax
0x18001af40  cmp     dword ptr [rbx+rax*8+1688h], 0
0x18001af48  jz      short loc_18001AFA0
0x18001af4a  mov     ecx, 20h ; ' '; cb
0x18001af4f  call    cs:__imp_CoTaskMemAlloc
0x18001af56  nop     dword ptr [rax+rax+00h]
0x18001af5b  mov     r9, rax
0x18001af5e  test    rax, rax
0x18001af61  jz      short loc_18001AFA0
0x18001af63  movups  xmm0, xmmword ptr cs:_GUID_4a52cda8_30f8_4216_be0f_ba0b2025921d.Data1
0x18001af6a  mov     [rax+10h], r14d
0x18001af6e  lea     r8, [rdi+169h]
0x18001af75  add     r8, r8
0x18001af78  mov     edx, 57h ; 'W'
0x18001af7d  movups  xmmword ptr [rax], xmm0
0x18001af80  mov     rcx, [rbx]
0x18001af83  mov     r8, [rbx+r8*8]
0x18001af87  mov     rax, [rcx+48h]
0x18001af8b  mov     rcx, rbx
0x18001af8e  call    cs:__guard_dispatch_icall_fptr
0x18001af94  mov     eax, [rbx+18BCh]
0x18001af9a  mov     [rbx+18B8h], eax
0x18001afa0  cmp     r12d, [rbx+18A8h]
0x18001afa7  jz      short loc_18001B01D
0x18001afa9  lea     r8, [rbp+var_30]; unsigned int *
0x18001afad  mov     [rbp+var_30], r14d
0x18001afb1  lea     rdx, _GUID_1d3583c4_1583_474e_b71a_5ee463c198e4; struct _GUID *
0x18001afb8  call    ?MapCodecAPIToIndex@CIVIAudioCodec@@IEAAJPEBU_GUID@@PEAK@Z; CIVIAudioCodec::MapCodecAPIToIndex(_GUID const *,ulong *)
0x18001afbd  test    eax, eax
0x18001afbf  jnz     short loc_18001B01D
0x18001afc1  mov     edi, [rbp+var_30]
0x18001afc4  mov     eax, edi
0x18001afc6  add     rax, rax
0x18001afc9  cmp     dword ptr [rbx+rax*8+1688h], 0
0x18001afd1  jz      short loc_18001B01D
0x18001afd3  mov     ecx, 20h ; ' '; cb
0x18001afd8  call    cs:__imp_CoTaskMemAlloc
0x18001afdf  nop     dword ptr [rax+rax+00h]
0x18001afe4  mov     r9, rax
0x18001afe7  test    rax, rax
0x18001afea  jz      short loc_18001B01D
0x18001afec  movups  xmm0, xmmword ptr cs:_GUID_1d3583c4_1583_474e_b71a_5ee463c198e4.Data1
0x18001aff3  mov     [rax+10h], r14d
0x18001aff7  lea     r8, [rdi+169h]
0x18001affe  add     r8, r8
0x18001b001  mov     edx, 57h ; 'W'
0x18001b006  movups  xmmword ptr [rax], xmm0
0x18001b009  mov     rcx, [rbx]
0x18001b00c  mov     r8, [rbx+r8*8]
0x18001b010  mov     rax, [rcx+48h]
0x18001b014  mov     rcx, rbx
0x18001b017  call    cs:__guard_dispatch_icall_fptr
0x18001b01d  cmp     r13d, [rbx+18B0h]
0x18001b024  jz      short loc_18001B09A
0x18001b026  lea     r8, [rbp+var_30]; unsigned int *
0x18001b02a  mov     [rbp+var_30], r14d
0x18001b02e  lea     rdx, _GUID_59488217_007a_4f7a_8e41_5c48b1eac5c6; struct _GUID *
0x18001b035  call    ?MapCodecAPIToIndex@CIVIAudioCodec@@IEAAJPEBU_GUID@@PEAK@Z; CIVIAudioCodec::MapCodecAPIToIndex(_GUID const *,ulong *)
0x18001b03a  test    eax, eax
0x18001b03c  jnz     short loc_18001B09A
0x18001b03e  mov     edi, [rbp+var_30]
0x18001b041  mov     eax, edi
0x18001b043  add     rax, rax
0x18001b046  cmp     dword ptr [rbx+rax*8+1688h], 0
0x18001b04e  jz      short loc_18001B09A
0x18001b050  mov     ecx, 20h ; ' '; cb
0x18001b055  call    cs:__imp_CoTaskMemAlloc
0x18001b05c  nop     dword ptr [rax+rax+00h]
0x18001b061  mov     r9, rax
0x18001b064  test    rax, rax
0x18001b067  jz      short loc_18001B09A
0x18001b069  movups  xmm0, xmmword ptr cs:_GUID_59488217_007a_4f7a_8e41_5c48b1eac5c6.Data1
0x18001b070  mov     [rax+10h], r14d
0x18001b074  lea     r8, [rdi+169h]
0x18001b07b  add     r8, r8
0x18001b07e  mov     edx, 57h ; 'W'
0x18001b083  movups  xmmword ptr [rax], xmm0
0x18001b086  mov     rcx, [rbx]
0x18001b089  mov     r8, [rbx+r8*8]
0x18001b08d  mov     rax, [rcx+48h]
0x18001b091  mov     rcx, rbx
0x18001b094  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
