# udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___

- ea: `0x18000dd64`
- end: `0x18000e13f`
- name: `udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___`
- size: `987`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800151ac`

## callees

- `0x180002590`
- `0x18000dd64`
- `0x18000f350`
- `0x18000f4e0`
- `0x180013fd0`
- `0x18002065c`
- `0x180033010`

## import_xrefs

- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x18000ddf1`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x18000ddf1`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // edi
  _DWORD *v6; // r13
  int v7; // eax
  _QWORD *v8; // r15
  _QWORD *i; // rsi
  unsigned __int128 v10; // kr00_16
  __int64 v11; // rax
  unsigned int v12; // r14d
  _DWORD *v13; // r15
  __int64 v14; // rax
  _DWORD *v15; // rcx
  __int128 *v16; // rdx
  _OWORD *v17; // rdx
  _DWORD *v18; // rcx
  __int64 *v19; // r8
  int v21; // [rsp+20h] [rbp-A9h]
  __int64 v22; // [rsp+30h] [rbp-99h] BYREF
  __int64 *v23; // [rsp+38h] [rbp-91h] BYREF
  __int64 *v24; // [rsp+40h] [rbp-89h] BYREF
  int v25; // [rsp+48h] [rbp-81h]
  __int64 *v26; // [rsp+50h] [rbp-79h] BYREF
  _DWORD *v27; // [rsp+58h] [rbp-71h]
  _QWORD *v28; // [rsp+60h] [rbp-69h]
  unsigned __int128 v29; // [rsp+68h] [rbp-61h] BYREF
  __int64 v30; // [rsp+78h] [rbp-51h]
  _QWORD *v31; // [rsp+80h] [rbp-49h]
  __int128 v32; // [rsp+88h] [rbp-41h] BYREF
  unsigned int v33; // [rsp+98h] [rbp-31h]
  char v34; // [rsp+9Ch] [rbp-2Dh] BYREF
  __int128 v35; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v36; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v37; // [rsp+C0h] [rbp-9h]
  __int64 v38; // [rsp+D0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v31 = a1;
  v5 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v25 = 1;
  v6 = (_DWORD *)*a3;
  v27 = (_DWORD *)a3[1];
  v29 = 0;
  v30 = 0;
  v24 = DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU;
  std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(&v29, 0, &v24);
  v26 = 0;
  v7 = DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, &v26);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\npu_detection.h",
      (const char *)(unsigned int)v7,
      v21);
  v8 = (_QWORD *)*((_QWORD *)&v29 + 1);
  v10 = v29;
  v28 = (_QWORD *)(v10 >> 64);
  for ( i = (_QWORD *)v10; i != v8; ++i )
  {
    v23 = 0;
    v11 = *v26;
    v23 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64, _QWORD, GUID *, __int64 **))(v11 + 24))(
           v26,
           1,
           *i,
           &GUID_526c7776_40e9_459b_b711_f32ad76dfc28,
           &v23) >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64 *))(*v23 + 32))(v23);
      if ( v12 )
      {
        v13 = v27;
        while ( 1 )
        {
          v22 = 0;
          v14 = *v23;
          v22 = 0;
          if ( (*(int (__fastcall **)(__int64 *, _QWORD, GUID *, __int64 *))(v14 + 24))(
                 v23,
                 v5,
                 &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e,
                 &v22) >= 0 )
          {
            if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 11) )
            {
              v32 = 0;
              v33 = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 14)
                && (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v22 + 48LL))(
                     v22,
                     14,
                     20,
                     &v32) >= 0 )
              {
                goto LABEL_13;
              }
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 3) )
              {
                v35 = 0;
                if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v22 + 48LL))(
                       v22,
                       3,
                       16,
                       &v35) >= 0 )
                  break;
              }
            }
          }
LABEL_35:
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          if ( ++v5 >= v12 )
          {
            v8 = v28;
            v5 = 0;
            goto LABEL_39;
          }
        }
        *(_QWORD *)&v32 = v35;
        v33 = HIDWORD(v35);
        DWORD2(v32) = DWORD2(v35);
LABEL_13:
        v24 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 1)
          && (*(int (__fastcall **)(__int64, __int64, __int64, __int64 **))(*(_QWORD *)v22 + 48LL))(v22, 1, 8, &v24) >= 0 )
        {
          v36 = v32;
          *(_QWORD *)&v37 = v33;
          *((_QWORD *)&v37 + 1) = v24;
          if ( v6 == v13 )
            goto LABEL_24;
          v15 = (_DWORD *)*a3;
LABEL_22:
          if ( v15 != (_DWORD *)a3[1] )
          {
            v16 = &v32;
            while ( *v15 != *(_DWORD *)v16 || v15[1] != *((_DWORD *)v16 + 1) )
            {
              v16 = (__int128 *)((char *)v16 + 20);
              if ( v16 == (__int128 *)&v34 )
              {
                v15 += 5;
                goto LABEL_22;
              }
            }
          }
          if ( v15 != (_DWORD *)a3[1] )
          {
LABEL_24:
            v17 = (_OWORD *)a1[1];
            v18 = (_DWORD *)*a1;
LABEL_30:
            if ( v18 != (_DWORD *)v17 )
            {
              v19 = (__int64 *)&v36;
              while ( *v18 != *(_DWORD *)v19 || v18[1] != *((_DWORD *)v19 + 1) )
              {
                v19 += 4;
                if ( v19 == &v38 )
                {
                  v18 += 8;
                  goto LABEL_30;
                }
              }
            }
            if ( v18 == (_DWORD *)v17 )
            {
              if ( v17 == (_OWORD *)a1[2] )
              {
                std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(
                  a1,
                  v17,
                  &v36);
              }
              else
              {
                *v17 = v36;
                v17[1] = v37;
                a1[1] += 32LL;
              }
            }
          }
        }
        goto LABEL_35;
      }
    }
LABEL_39:
    if ( v23 )
      (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
  }
  if ( v26 )
    (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
  std::vector<_GUID const *>::~vector<_GUID const *>(&v29);
  return a1;
}

```

## disassembly

```asm
0x18000dd64  push    rbp
0x18000dd66  push    rbx
0x18000dd67  push    rsi
0x18000dd68  push    rdi
0x18000dd69  push    r12
0x18000dd6b  push    r13
0x18000dd6d  push    r14
0x18000dd6f  push    r15
0x18000dd71  lea     rbp, [rsp-1Fh]
0x18000dd76  sub     rsp, 0E8h
0x18000dd7d  mov     rax, cs:__security_cookie
0x18000dd84  xor     rax, rsp
0x18000dd87  mov     [rbp+57h+var_50], rax
0x18000dd8b  mov     r12, r8
0x18000dd8e  mov     rbx, rcx
0x18000dd91  mov     [rbp+57h+var_A0], rcx
0x18000dd95  xor     edi, edi
0x18000dd97  mov     [rsp+120h+var_D8], edi
0x18000dd9b  mov     [rcx], rdi
0x18000dd9e  mov     [rcx+8], rdi
0x18000dda2  mov     [rcx+10h], rdi
0x18000dda6  mov     [rsp+120h+var_D8], 1
0x18000ddae  mov     r13, [r8]
0x18000ddb1  mov     rax, [r8+8]
0x18000ddb5  mov     [rbp+57h+var_C8], rax
0x18000ddb9  xorps   xmm0, xmm0
0x18000ddbc  movdqu  [rbp+57h+var_B8], xmm0
0x18000ddc1  mov     [rbp+57h+var_A8], rdi
0x18000ddc5  lea     rax, DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU
0x18000ddcc  mov     [rsp+120h+var_E0], rax
0x18000ddd1  lea     r8, [rsp+120h+var_E0]
0x18000ddd6  xor     edx, edx
0x18000ddd8  lea     rcx, [rbp+57h+var_B8]
0x18000dddc  call    ??$_Emplace_reallocate@PEBU_GUID@@@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@AEAAPEAPEBU_GUID@@QEAPEBU2@$$QEAPEBU2@@Z; std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(_GUID const * * const,_GUID const * &&)
0x18000dde1  nop
0x18000dde2  mov     [rbp+57h+var_D0], rdi
0x18000dde6  lea     rdx, [rbp+57h+var_D0]
0x18000ddea  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x18000ddf1  call    cs:__imp_DXCoreCreateAdapterFactory
0x18000ddf7  mov     rcx, [rbp+5Fh]; this
0x18000ddfb  test    eax, eax
0x18000ddfd  js      loc_18000E12A
0x18000de03  mov     rsi, qword ptr [rbp+57h+var_B8]
0x18000de07  mov     r15, qword ptr [rbp+57h+var_B8+8]
0x18000de0b  mov     [rbp+57h+var_C0], r15
0x18000de0f  jmp     loc_18000E0DF
0x18000de14  mov     [rsp+120h+var_E8], rdi
0x18000de19  mov     rcx, [rbp+57h+var_D0]
0x18000de1d  mov     rax, [rcx]
0x18000de20  mov     [rsp+120h+var_E8], rdi
0x18000de25  lea     rdx, [rsp+120h+var_E8]
0x18000de2a  mov     qword ptr [rsp+120h+var_100], rdx
0x18000de2f  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x18000de36  mov     r8, [rsi]
0x18000de39  mov     edx, 1
0x18000de3e  mov     rax, [rax+18h]
0x18000de42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de47  test    eax, eax
0x18000de49  jns     short loc_18000DE50
0x18000de4b  jmp     loc_18000E0C4
0x18000de50  mov     rcx, [rsp+120h+var_E8]
0x18000de55  mov     rax, [rcx]
0x18000de58  mov     rax, [rax+20h]
0x18000de5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de61  mov     r14d, eax
0x18000de64  test    eax, eax
0x18000de66  jnz     short loc_18000DE6D
0x18000de68  jmp     loc_18000E0C4
0x18000de6d  test    r14d, r14d
0x18000de70  jz      loc_18000E0C2
0x18000de76  mov     r15, [rbp+57h+var_C8]
0x18000de7a  mov     [rsp+120h+var_F0], 0
0x18000de83  mov     rcx, [rsp+120h+var_E8]
0x18000de88  mov     rax, [rcx]
0x18000de8b  mov     [rsp+120h+var_F0], 0
0x18000de94  lea     r9, [rsp+120h+var_F0]
0x18000de99  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x18000dea0  mov     edx, edi
0x18000dea2  mov     rax, [rax+18h]
0x18000dea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deab  test    eax, eax
0x18000dead  jns     short loc_18000DEB4
0x18000deaf  jmp     loc_18000E09C
0x18000deb4  mov     rcx, [rsp+120h+var_F0]
0x18000deb9  mov     rax, [rcx]
0x18000debc  mov     edx, 0Bh
0x18000dec1  mov     rax, [rax+28h]
0x18000dec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deca  test    al, al
0x18000decc  jnz     short loc_18000DED3
0x18000dece  jmp     loc_18000E09C
0x18000ded3  xorps   xmm0, xmm0
0x18000ded6  xor     eax, eax
0x18000ded8  movups  [rbp+57h+var_98], xmm0
0x18000dedc  mov     [rbp+57h+var_88], eax
0x18000dedf  mov     rcx, [rsp+120h+var_F0]
0x18000dee4  mov     rax, [rcx]
0x18000dee7  mov     edx, 0Eh
0x18000deec  mov     rax, [rax+28h]
0x18000def0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000def5  test    al, al
0x18000def7  jz      short loc_18000DF1B
0x18000def9  mov     rcx, [rsp+120h+var_F0]
0x18000defe  mov     rax, [rcx]
0x18000df01  lea     r9, [rbp+57h+var_98]
0x18000df05  mov     edx, 0Eh
0x18000df0a  lea     r8d, [rdx+6]
0x18000df0e  mov     rax, [rax+30h]
0x18000df12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df17  test    eax, eax
0x18000df19  jns     short loc_18000DF7E
0x18000df1b  mov     rcx, [rsp+120h+var_F0]
0x18000df20  mov     rax, [rcx]
0x18000df23  mov     edx, 3
0x18000df28  mov     rax, [rax+28h]
0x18000df2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df31  test    al, al
0x18000df33  jz      loc_18000E09C
0x18000df39  xorps   xmm0, xmm0
0x18000df3c  movups  [rbp+57h+var_80], xmm0
0x18000df40  mov     rcx, [rsp+120h+var_F0]
0x18000df45  mov     rax, [rcx]
0x18000df48  lea     r9, [rbp+57h+var_80]
0x18000df4c  mov     edx, 3
0x18000df51  lea     r8d, [rdx+0Dh]
0x18000df55  mov     rax, [rax+30h]
0x18000df59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df5e  test    eax, eax
0x18000df60  js      loc_18000E09C
0x18000df66  mov     eax, dword ptr [rbp+57h+var_80]
0x18000df69  mov     dword ptr [rbp+57h+var_98], eax
0x18000df6c  mov     eax, dword ptr [rbp+57h+var_80+4]
0x18000df6f  mov     dword ptr [rbp+57h+var_98+4], eax
0x18000df72  mov     eax, dword ptr [rbp+57h+var_80+0Ch]
0x18000df75  mov     [rbp+57h+var_88], eax
0x18000df78  mov     eax, dword ptr [rbp+57h+var_80+8]
0x18000df7b  mov     dword ptr [rbp+57h+var_98+8], eax
0x18000df7e  mov     [rsp+120h+var_E0], 0
0x18000df87  mov     rcx, [rsp+120h+var_F0]
0x18000df8c  mov     rax, [rcx]
0x18000df8f  mov     edx, 1
0x18000df94  mov     rax, [rax+28h]
0x18000df98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df9d  test    al, al
0x18000df9f  jz      loc_18000E09A
0x18000dfa5  mov     rcx, [rsp+120h+var_F0]
0x18000dfaa  mov     rax, [rcx]
0x18000dfad  lea     r9, [rsp+120h+var_E0]
0x18000dfb2  mov     edx, 1
0x18000dfb7  lea     r8d, [rdx+7]
0x18000dfbb  mov     rax, [rax+30h]
0x18000dfbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfc4  test    eax, eax
0x18000dfc6  js      loc_18000E09A
0x18000dfcc  mov     eax, dword ptr [rbp+57h+var_98]
0x18000dfcf  mov     dword ptr [rbp+57h+var_70], eax
0x18000dfd2  mov     eax, dword ptr [rbp+57h+var_98+4]
0x18000dfd5  mov     dword ptr [rbp+57h+var_70+4], eax
0x18000dfd8  mov     eax, dword ptr [rbp+57h+var_98+8]
0x18000dfdb  mov     dword ptr [rbp+57h+var_70+8], eax
0x18000dfde  mov     eax, dword ptr [rbp+57h+var_98+0Ch]
0x18000dfe1  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x18000dfe4  mov     eax, [rbp+57h+var_88]
0x18000dfe7  mov     dword ptr [rbp+57h+var_60], eax
0x18000dfea  xor     eax, eax
0x18000dfec  mov     dword ptr [rbp+57h+var_60+4], eax
0x18000dfef  mov     rax, [rsp+120h+var_E0]
0x18000dff4  mov     qword ptr [rbp+57h+var_60+8], rax
0x18000dff8  cmp     r13, r15
0x18000dffb  jz      short loc_18000E036
0x18000dffd  mov     rcx, [r12]
0x18000e001  jmp     short loc_18000E028
0x18000e003  lea     rdx, [rbp+57h+var_98]
0x18000e007  mov     r8d, [rcx]
0x18000e00a  cmp     r8d, [rdx]
0x18000e00d  jnz     short loc_18000E017
0x18000e00f  mov     eax, [rdx+4]
0x18000e012  cmp     [rcx+4], eax
0x18000e015  jz      short loc_18000E02F
0x18000e017  add     rdx, 14h
0x18000e01b  lea     rax, [rbp+57h+var_84]
0x18000e01f  cmp     rdx, rax
0x18000e022  jnz     short loc_18000E00A
0x18000e024  add     rcx, 14h
0x18000e028  cmp     rcx, [r12+8]
0x18000e02d  jnz     short loc_18000E003
0x18000e02f  cmp     rcx, [r12+8]
0x18000e034  jz      short loc_18000E098
0x18000e036  mov     rdx, [rbx+8]
0x18000e03a  mov     rcx, [rbx]
0x18000e03d  jmp     short loc_18000E065
0x18000e03f  lea     r8, [rbp+57h+var_70]
0x18000e043  mov     r9d, [rcx]
0x18000e046  cmp     r9d, [r8]
0x18000e049  jnz     short loc_18000E054
0x18000e04b  mov     eax, [r8+4]
0x18000e04f  cmp     [rcx+4], eax
0x18000e052  jz      short loc_18000E06A
0x18000e054  add     r8, 20h ; ' '
0x18000e058  lea     rax, [rbp+57h+var_50]
0x18000e05c  cmp     r8, rax
0x18000e05f  jnz     short loc_18000E046
0x18000e061  add     rcx, 20h ; ' '
0x18000e065  cmp     rcx, rdx
0x18000e068  jnz     short loc_18000E03F
0x18000e06a  cmp     rcx, rdx
0x18000e06d  jnz     short loc_18000E098
0x18000e06f  cmp     rdx, [rbx+10h]
0x18000e073  jz      short loc_18000E08B
0x18000e075  movups  xmm0, [rbp+57h+var_70]
0x18000e079  movups  xmmword ptr [rdx], xmm0
0x18000e07c  movups  xmm1, [rbp+57h+var_60]
0x18000e080  movups  xmmword ptr [rdx+10h], xmm1
0x18000e084  add     qword ptr [rbx+8], 20h ; ' '
0x18000e089  jmp     short loc_18000E098
0x18000e08b  lea     r8, [rbp+57h+var_70]
0x18000e08f  mov     rcx, rbx
0x18000e092  call    ??$_Emplace_reallocate@AEBUFoundNpu@npu_detection@udk@@@?$vector@UFoundNpu@npu_detection@udk@@V?$allocator@UFoundNpu@npu_detection@udk@@@std@@@std@@AEAAPEAUFoundNpu@npu_detection@udk@@QEAU234@AEBU234@@Z; std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(udk::npu_detection::FoundNpu * const,udk::npu_detection::FoundNpu const &)
0x18000e097  nop
0x18000e098  jmp     short loc_18000E09C
0x18000e09a  jmp     short $+2
0x18000e09c  mov     rcx, [rsp+120h+var_F0]
0x18000e0a1  test    rcx, rcx
0x18000e0a4  jz      short loc_18000E0B3
0x18000e0a6  mov     rax, [rcx]
0x18000e0a9  mov     rax, [rax+10h]
0x18000e0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0b2  nop
0x18000e0b3  inc     edi
0x18000e0b5  cmp     edi, r14d
0x18000e0b8  jb      loc_18000DE7A
0x18000e0be  mov     r15, [rbp+57h+var_C0]
0x18000e0c2  xor     edi, edi
0x18000e0c4  mov     rcx, [rsp+120h+var_E8]
0x18000e0c9  test    rcx, rcx
0x18000e0cc  jz      short loc_18000E0DB
0x18000e0ce  mov     rax, [rcx]
0x18000e0d1  mov     rax, [rax+10h]
0x18000e0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0da  nop
0x18000e0db  add     rsi, 8
0x18000e0df  cmp     rsi, r15
0x18000e0e2  jnz     loc_18000DE14
0x18000e0e8  mov     rcx, [rbp+57h+var_D0]
0x18000e0ec  test    rcx, rcx
0x18000e0ef  jz      short loc_18000E0FE
0x18000e0f1  mov     rdx, [rcx]
0x18000e0f4  mov     rax, [rdx+10h]
0x18000e0f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0fd  nop
0x18000e0fe  lea     rcx, [rbp+57h+var_B8]
0x18000e102  call    ??1?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID const *>::~vector<_GUID const *>(void)
0x18000e107  mov     rax, rbx
0x18000e10a  mov     rcx, [rbp+57h+var_50]
0x18000e10e  xor     rcx, rsp; StackCookie
0x18000e111  call    __security_check_cookie
0x18000e116  add     rsp, 0E8h
0x18000e11d  pop     r15
0x18000e11f  pop     r14
0x18000e121  pop     r13
0x18000e123  pop     r12
0x18000e125  pop     rdi
0x18000e126  pop     rsi
0x18000e127  pop     rbx
0x18000e128  pop     rbp
0x18000e129  retn
0x18000e12a  mov     r9d, eax; char *
0x18000e12d  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Shell\\inc\\npu_dete"...
0x18000e134  mov     edx, 17Dh; void *
0x18000e139  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
