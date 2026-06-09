# _anonymous_namespace_::EncryptKeyPair

- ea: `0x140051840`
- end: `0x140051de2`
- name: `_anonymous_namespace_::EncryptKeyPair`
- size: `1442`
- prototype: ``
- caller_count: `3`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005240c`
- `0x1400524f4`
- `0x140052948`

## callees

- `0x1400080c0`
- `0x140008420`
- `0x140009b1c`
- `0x140009be0`
- `0x140009fa0`
- `0x14000ac7c`
- `0x14000b658`
- `0x14000e034`
- `0x140010514`
- `0x140018904`
- `0x14001b160`
- `0x14001b224`
- `0x140050fe4`
- `0x1400514a4`
- `0x14005152c`
- `0x140051840`
- `0x140051de8`
- `0x140052044`
- `0x1400520a0`
- `0x1400520fc`
- `0x1400522cc`
- `0x140052f14`

## string_xrefs

- `0x1400518a3`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\softwarekey.cpp`
- `0x1400518ef`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\softwarekey.cpp`
- `0x1400519c8`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\softwarekey.cpp`
- `0x140051a20`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\softwarekey.cpp`
- `0x140051bd7`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\softwarekey.cpp`
- `0x140051c94`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\softwarekey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall anonymous_namespace_::EncryptKeyPair(
        SoftwareKey::KeyPair *this,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rdx
  unsigned __int8 *v18; // rbx
  int v19; // eax
  unsigned __int8 *v20; // r14
  unsigned __int64 v21; // rsi
  unsigned __int8 *v22; // r8
  int v23; // eax
  __int64 v24; // rdx
  unsigned __int8 *v25; // rbx
  unsigned __int8 *v26; // rbx
  int v27; // eax
  unsigned __int8 *v28; // rbx
  unsigned __int8 *v29; // r8
  __int64 v30; // rcx
  int v31; // edi
  __int64 v32; // rdx
  int v34; // [rsp+20h] [rbp-B9h]
  unsigned __int8 *v35; // [rsp+30h] [rbp-A9h] BYREF
  void *v36; // [rsp+38h] [rbp-A1h]
  __int64 v37; // [rsp+40h] [rbp-99h]
  unsigned __int8 *v38; // [rsp+48h] [rbp-91h] BYREF
  void *v39; // [rsp+50h] [rbp-89h]
  __int64 v40; // [rsp+58h] [rbp-81h]
  unsigned __int64 v41; // [rsp+60h] [rbp-79h] BYREF
  unsigned __int64 v42; // [rsp+68h] [rbp-71h] BYREF
  unsigned __int64 v43; // [rsp+70h] [rbp-69h] BYREF
  unsigned __int64 v44; // [rsp+78h] [rbp-61h] BYREF
  unsigned __int8 *v45; // [rsp+80h] [rbp-59h] BYREF
  void *v46; // [rsp+88h] [rbp-51h]
  __int64 v47; // [rsp+90h] [rbp-49h]
  unsigned __int8 *v48; // [rsp+98h] [rbp-41h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-39h]
  _BYTE v50[8]; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-21h] BYREF
  unsigned __int64 v52; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v53; // [rsp+C8h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+3Fh]

  v51 = 0;
  v13 = SoftwareKey::SymmetricKey::Generate(this, v50);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v41 = 0;
    v13 = SoftwareKey::SymmetricKey::ExportKey((SoftwareKey::SymmetricKey *)v50, 0, 0, &v41);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = 122;
      goto LABEL_5;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
      &v38,
      v41);
    v16 = SoftwareKey::SymmetricKey::ExportKey((SoftwareKey::SymmetricKey *)v50, (_BYTE *)v39 - v38, v38, &v41);
    v14 = v16;
    if ( v16 < 0 )
    {
      v17 = 124;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\softwarekey.cpp",
        (const char *)(unsigned int)v16,
        v34);
LABEL_9:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v38);
      goto LABEL_67;
    }
    if ( v41 >= (_BYTE *)v39 - v38 )
    {
      if ( v41 > (_BYTE *)v39 - v38 )
      {
        if ( v41 <= v40 - (__int64)v38 )
        {
          v18 = &v38[v41];
          memset_0(v39, 0, v41 - ((_BYTE *)v39 - v38));
          v39 = v18;
        }
        else
        {
          std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Resize_reallocate<std::_Value_init_tag>(
            &v38,
            v41);
        }
      }
    }
    else
    {
      v39 = &v38[v41];
    }
    v42 = 0;
    v16 = SoftwareKey::KeyPair::ExportPrivateKey(this, 0, 0, &v42);
    v14 = v16;
    if ( v16 < 0 )
    {
      v17 = 129;
      goto LABEL_8;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
      &v35,
      v42);
    v19 = SoftwareKey::KeyPair::ExportPrivateKey(this, (_BYTE *)v36 - v35, v35, &v42);
    v14 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\softwarekey.cpp",
        (const char *)(unsigned int)v19,
        v34);
LABEL_20:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v35);
      goto LABEL_9;
    }
    std::vector<unsigned char>::vector<unsigned char>(&v48, 16);
    v20 = v48;
    v21 = v49 - (_QWORD)v48;
    v23 = SoftwareKey::GenRandom((int)v49 - (int)v48, (unsigned __int64)v48, v22);
    v14 = v23;
    if ( v23 < 0 )
    {
      v24 = 135;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\softwarekey.cpp",
        (const char *)(unsigned int)v23,
        v34);
LABEL_24:
      std::vector<unsigned char>::_Tidy(&v48);
      goto LABEL_20;
    }
    v23 = SoftwareKey::SymmetricKey::SetInitializationVector((SoftwareKey::SymmetricKey *)v50, v21, v20);
    v14 = v23;
    if ( v23 < 0 )
    {
      v24 = 136;
      goto LABEL_23;
    }
    v43 = 0;
    v23 = SoftwareKey::SymmetricKey::EncryptData((SoftwareKey::SymmetricKey *)v50, (_BYTE *)v36 - v35, v35, 0, 0, &v43);
    v14 = v23;
    if ( v23 < 0 )
    {
      v24 = 144;
      goto LABEL_23;
    }
    v25 = (unsigned __int8 *)v36;
    if ( v43 >= (_BYTE *)v36 - v35 )
    {
      if ( v43 <= (_BYTE *)v36 - v35 )
        goto LABEL_36;
      if ( v43 > v37 - (__int64)v35 )
      {
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Resize_reallocate<std::_Value_init_tag>(
          &v35,
          v43);
        v25 = (unsigned __int8 *)v36;
        goto LABEL_36;
      }
      v25 = &v35[v43];
      memset_0(v36, 0, v43 - ((_BYTE *)v36 - v35));
    }
    else
    {
      v25 = &v35[v43];
    }
    v36 = v25;
LABEL_36:
    v23 = SoftwareKey::SymmetricKey::EncryptData((SoftwareKey::SymmetricKey *)v50, v42, v35, v25 - v35, v35, &v43);
    v14 = v23;
    if ( v23 < 0 )
    {
      v24 = 154;
      goto LABEL_23;
    }
    if ( v43 >= (_BYTE *)v36 - v35 )
    {
      if ( v43 > (_BYTE *)v36 - v35 )
      {
        if ( v43 <= v37 - (__int64)v35 )
        {
          v26 = &v35[v43];
          memset_0(v36, 0, v43 - ((_BYTE *)v36 - v35));
          v36 = v26;
        }
        else
        {
          std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Resize_reallocate<std::_Value_init_tag>(
            &v35,
            v43);
        }
      }
    }
    else
    {
      v36 = &v35[v43];
    }
    v44 = 0;
    v23 = SoftwareKey::KeyPair::ExportPublicKey(this, 0, 0, &v44);
    v14 = v23;
    if ( v23 < 0 )
    {
      v24 = 159;
      goto LABEL_23;
    }
    std::vector<unsigned char>::vector<unsigned char>(&v45, v44);
    v27 = SoftwareKey::KeyPair::ExportPublicKey(this, (_BYTE *)v46 - v45, v45, &v44);
    v14 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\softwarekey.cpp",
        (const char *)(unsigned int)v27,
        v34);
      std::vector<unsigned char>::_Tidy(&v45);
      goto LABEL_24;
    }
    if ( v44 >= (_BYTE *)v46 - v45 )
    {
      if ( v44 > (_BYTE *)v46 - v45 )
      {
        if ( v44 <= v47 - (__int64)v45 )
        {
          v28 = &v45[v44];
          memset_0(v46, 0, v44 - ((_BYTE *)v46 - v45));
          v46 = v28;
        }
        else
        {
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v45, v44);
        }
      }
    }
    else
    {
      v46 = &v45[v44];
    }
    if ( (unsigned __int8)VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>>()
      && a6 )
    {
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
        &v52,
        32);
      v31 = SoftwareKey::GenRandom((int)v53 - (int)v52, v52, v29);
      if ( v31 < 0 )
      {
        v32 = 169;
LABEL_58:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v32,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\softwarekey.cpp",
          (const char *)(unsigned int)v31,
          v34);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v52);
        std::vector<unsigned char>::_Tidy(&v45);
        std::vector<unsigned char>::_Tidy(&v48);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v35);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v38);
        v14 = v31;
        goto LABEL_67;
      }
      if ( a5 )
      {
        if ( a4 )
        {
          v31 = SoftwareKey::CalculateHmacSecret(a3, a4, (int)v53 - (int)v52, v52, a5);
          if ( v31 < 0 )
          {
            v32 = 178;
            goto LABEL_58;
          }
        }
      }
      v34 = (int)v20;
      v31 = SoftwareKey::EncryptInPlace(v30, (_BYTE *)v39 - v38, v38, v21);
      if ( v31 < 0 )
      {
        v32 = 187;
        goto LABEL_58;
      }
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=(a6, &v52);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v52);
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=(a7, &v38);
    std::vector<unsigned char>::operator=(a8, &v48);
    std::vector<unsigned char>::operator=(a9, &v45);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=(a10, &v35);
    std::vector<unsigned char>::_Tidy(&v45);
    std::vector<unsigned char>::_Tidy(&v48);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v35);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v38);
    v14 = 0;
    goto LABEL_67;
  }
  v15 = 118;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\softwarekey.cpp",
    (const char *)(unsigned int)v13,
    v34);
LABEL_67:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v51);
  return v14;
}

```

## disassembly

```asm
0x140051840  push    rbp
0x140051842  push    rbx
0x140051843  push    rsi
0x140051844  push    rdi
0x140051845  push    r12
0x140051847  push    r14
0x140051849  push    r15
0x14005184b  lea     rbp, [rsp-7]
0x140051850  sub     rsp, 0E0h
0x140051857  mov     r15, r9
0x14005185a  mov     r12d, r8d
0x14005185d  mov     rdi, rcx
0x140051860  mov     [rbp+37h+var_58], 0
0x140051868  lea     rdx, [rbp+37h+var_60]
0x14005186c  call    ?Generate@SymmetricKey@SoftwareKey@@SAJW4Algorithm@@PEAV12@@Z; SoftwareKey::SymmetricKey::Generate(Algorithm,SoftwareKey::SymmetricKey *)
0x140051871  mov     ebx, eax
0x140051873  test    eax, eax
0x140051875  jns     short loc_14005187E
0x140051877  mov     edx, 76h ; 'v'
0x14005187c  jmp     short loc_1400518A3
0x14005187e  mov     [rbp+37h+var_B0], 0
0x140051886  lea     r9, [rbp+37h+var_B0]; unsigned __int64 *
0x14005188a  xor     r8d, r8d; unsigned __int8 *
0x14005188d  xor     edx, edx; unsigned __int64
0x14005188f  lea     rcx, [rbp+37h+var_60]; this
0x140051893  call    ?ExportKey@SymmetricKey@SoftwareKey@@QEBAJ_KPEAEPEA_K@Z; SoftwareKey::SymmetricKey::ExportKey(unsigned __int64,uchar *,unsigned __int64 *)
0x140051898  mov     ebx, eax
0x14005189a  test    eax, eax
0x14005189c  jns     short loc_1400518BB
0x14005189e  mov     edx, 7Ah ; 'z'; void *
0x1400518a3  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1400518aa  mov     r9d, eax; char *
0x1400518ad  mov     rcx, [rbp+3Fh]; this
0x1400518b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400518b6  jmp     loc_140051DC5
0x1400518bb  mov     rdx, [rbp+37h+var_B0]
0x1400518bf  lea     rcx, [rsp+110h+var_C8]
0x1400518c4  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x1400518c9  nop
0x1400518ca  mov     r8, [rsp+110h+var_C8]; unsigned __int8 *
0x1400518cf  mov     rdx, [rsp+110h+var_C0]
0x1400518d4  sub     rdx, r8; unsigned __int64
0x1400518d7  lea     r9, [rbp+37h+var_B0]; unsigned __int64 *
0x1400518db  lea     rcx, [rbp+37h+var_60]; this
0x1400518df  call    ?ExportKey@SymmetricKey@SoftwareKey@@QEBAJ_KPEAEPEA_K@Z; SoftwareKey::SymmetricKey::ExportKey(unsigned __int64,uchar *,unsigned __int64 *)
0x1400518e4  mov     ebx, eax
0x1400518e6  test    eax, eax
0x1400518e8  jns     short loc_140051912
0x1400518ea  mov     edx, 7Ch ; '|'; void *
0x1400518ef  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1400518f6  mov     r9d, eax; char *
0x1400518f9  mov     rcx, [rbp+3Fh]; this
0x1400518fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140051902  nop
0x140051903  lea     rcx, [rsp+110h+var_C8]
0x140051908  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x14005190d  jmp     loc_140051DC5
0x140051912  mov     r8, [rbp+37h+var_B0]
0x140051916  mov     rdx, [rsp+110h+var_C8]
0x14005191b  mov     r9, [rsp+110h+var_C0]
0x140051920  mov     rcx, r9
0x140051923  sub     rcx, rdx
0x140051926  cmp     r8, rcx
0x140051929  jnb     short loc_140051936
0x14005192b  lea     rax, [r8+rdx]
0x14005192f  mov     [rsp+110h+var_C0], rax
0x140051934  jmp     short loc_14005196A
0x140051936  jbe     short loc_14005196A
0x140051938  mov     rax, [rsp+110h+var_B8]
0x14005193d  sub     rax, rdx
0x140051940  cmp     r8, rax
0x140051943  jbe     short loc_140051954
0x140051945  mov     rdx, r8
0x140051948  lea     rcx, [rsp+110h+var_C8]
0x14005194d  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140051952  jmp     short loc_14005196A
0x140051954  sub     r8, rcx; Size
0x140051957  lea     rbx, [r8+r9]
0x14005195b  xor     edx, edx; Val
0x14005195d  mov     rcx, r9; void *
0x140051960  call    memset_0
0x140051965  mov     [rsp+110h+var_C0], rbx
0x14005196a  mov     [rbp+37h+var_A8], 0
0x140051972  lea     r9, [rbp+37h+var_A8]; unsigned __int64 *
0x140051976  xor     r8d, r8d; unsigned __int8 *
0x140051979  xor     edx, edx; unsigned __int64
0x14005197b  mov     rcx, rdi; this
0x14005197e  call    ?ExportPrivateKey@KeyPair@SoftwareKey@@QEBAJ_KPEAEPEA_K@Z; SoftwareKey::KeyPair::ExportPrivateKey(unsigned __int64,uchar *,unsigned __int64 *)
0x140051983  mov     ebx, eax
0x140051985  test    eax, eax
0x140051987  jns     short loc_140051993
0x140051989  mov     edx, 81h
0x14005198e  jmp     loc_1400518EF
0x140051993  mov     rdx, [rbp+37h+var_A8]
0x140051997  lea     rcx, [rsp+110h+var_E0]
0x14005199c  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x1400519a1  nop
0x1400519a2  mov     r8, [rsp+110h+var_E0]; unsigned __int8 *
0x1400519a7  mov     rdx, [rsp+110h+var_D8]
0x1400519ac  sub     rdx, r8; unsigned __int64
0x1400519af  lea     r9, [rbp+37h+var_A8]; unsigned __int64 *
0x1400519b3  mov     rcx, rdi; this
0x1400519b6  call    ?ExportPrivateKey@KeyPair@SoftwareKey@@QEBAJ_KPEAEPEA_K@Z; SoftwareKey::KeyPair::ExportPrivateKey(unsigned __int64,uchar *,unsigned __int64 *)
0x1400519bb  mov     ebx, eax
0x1400519bd  test    eax, eax
0x1400519bf  jns     short loc_1400519E9
0x1400519c1  mov     rcx, [rbp+3Fh]; this
0x1400519c5  mov     r9d, eax; char *
0x1400519c8  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1400519cf  mov     edx, 83h; void *
0x1400519d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400519d9  nop
0x1400519da  lea     rcx, [rsp+110h+var_E0]
0x1400519df  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1400519e4  jmp     loc_140051903
0x1400519e9  mov     edx, 10h
0x1400519ee  lea     rcx, [rbp+37h+var_78]
0x1400519f2  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1400519f7  nop
0x1400519f8  mov     rsi, [rbp+37h+var_70]
0x1400519fc  mov     r14, [rbp+37h+var_78]
0x140051a00  sub     rsi, r14
0x140051a03  mov     rdx, r14; unsigned __int64
0x140051a06  mov     rcx, rsi; cbBuffer
0x140051a09  call    ?GenRandom@SoftwareKey@@YAJ_KPEAE@Z; SoftwareKey::GenRandom(unsigned __int64,uchar *)
0x140051a0e  mov     ebx, eax
0x140051a10  test    eax, eax
0x140051a12  jns     short loc_140051A38
0x140051a14  mov     edx, 87h; void *
0x140051a19  mov     rcx, [rbp+3Fh]; this
0x140051a1d  mov     r9d, eax; char *
0x140051a20  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140051a27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140051a2c  nop
0x140051a2d  lea     rcx, [rbp+37h+var_78]
0x140051a31  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140051a36  jmp     short loc_1400519DA
0x140051a38  mov     r8, r14; unsigned __int8 *
0x140051a3b  mov     rdx, rsi; unsigned __int64
0x140051a3e  lea     rcx, [rbp+37h+var_60]; this
0x140051a42  call    ?SetInitializationVector@SymmetricKey@SoftwareKey@@QEAAJ_KPEBE@Z; SoftwareKey::SymmetricKey::SetInitializationVector(unsigned __int64,uchar const *)
0x140051a47  mov     ebx, eax
0x140051a49  test    eax, eax
0x140051a4b  jns     short loc_140051A54
0x140051a4d  mov     edx, 88h
0x140051a52  jmp     short loc_140051A19
0x140051a54  mov     [rbp+37h+var_A0], 0
0x140051a5c  mov     r8, [rsp+110h+var_E0]; unsigned __int8 *
0x140051a61  mov     rdx, [rsp+110h+var_D8]
0x140051a66  sub     rdx, r8; unsigned __int64
0x140051a69  lea     rax, [rbp+37h+var_A0]
0x140051a6d  mov     [rsp+110h+var_E8], rax; unsigned __int64 *
0x140051a72  mov     [rsp+110h+var_F0], 0; unsigned __int8 *
0x140051a7b  xor     r9d, r9d; unsigned __int64
0x140051a7e  lea     rcx, [rbp+37h+var_60]; this
0x140051a82  call    ?EncryptData@SymmetricKey@SoftwareKey@@QEBAJ_KPEBE0PEAEPEA_K@Z; SoftwareKey::SymmetricKey::EncryptData(unsigned __int64,uchar const *,unsigned __int64,uchar *,unsigned __int64 *)
0x140051a87  mov     ebx, eax
0x140051a89  test    eax, eax
0x140051a8b  jns     short loc_140051A94
0x140051a8d  mov     edx, 90h
0x140051a92  jmp     short loc_140051A19
0x140051a94  mov     r8, [rbp+37h+var_A0]
0x140051a98  mov     rdx, [rsp+110h+var_E0]
0x140051a9d  mov     rbx, [rsp+110h+var_D8]
0x140051aa2  mov     r9, rbx
0x140051aa5  mov     rcx, rbx
0x140051aa8  sub     rcx, rdx
0x140051aab  cmp     r8, rcx
0x140051aae  jnb     short loc_140051AB6
0x140051ab0  lea     rbx, [r8+rdx]
0x140051ab4  jmp     short loc_140051AE9
0x140051ab6  jbe     short loc_140051AEE
0x140051ab8  mov     rax, [rsp+110h+var_D0]
0x140051abd  sub     rax, rdx
0x140051ac0  cmp     r8, rax
0x140051ac3  jbe     short loc_140051AD9
0x140051ac5  mov     rdx, r8
0x140051ac8  lea     rcx, [rsp+110h+var_E0]
0x140051acd  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140051ad2  mov     rbx, [rsp+110h+var_D8]
0x140051ad7  jmp     short loc_140051AEE
0x140051ad9  sub     r8, rcx; Size
0x140051adc  add     rbx, r8
0x140051adf  xor     edx, edx; Val
0x140051ae1  mov     rcx, r9; void *
0x140051ae4  call    memset_0
0x140051ae9  mov     [rsp+110h+var_D8], rbx
0x140051aee  mov     r8, [rsp+110h+var_E0]; unsigned __int8 *
0x140051af3  sub     rbx, r8
0x140051af6  lea     rax, [rbp+37h+var_A0]
0x140051afa  mov     [rsp+110h+var_E8], rax; unsigned __int64 *
0x140051aff  mov     [rsp+110h+var_F0], r8; int
0x140051b04  mov     r9, rbx; unsigned __int64
0x140051b07  mov     rdx, [rbp+37h+var_A8]; unsigned __int64
0x140051b0b  lea     rcx, [rbp+37h+var_60]; this
0x140051b0f  call    ?EncryptData@SymmetricKey@SoftwareKey@@QEBAJ_KPEBE0PEAEPEA_K@Z; SoftwareKey::SymmetricKey::EncryptData(unsigned __int64,uchar const *,unsigned __int64,uchar *,unsigned __int64 *)
0x140051b14  mov     ebx, eax
0x140051b16  test    eax, eax
0x140051b18  jns     short loc_140051B24
0x140051b1a  mov     edx, 9Ah
0x140051b1f  jmp     loc_140051A19
0x140051b24  mov     r8, [rbp+37h+var_A0]
0x140051b28  mov     rdx, [rsp+110h+var_E0]
0x140051b2d  mov     r9, [rsp+110h+var_D8]
0x140051b32  mov     rcx, r9
0x140051b35  sub     rcx, rdx
0x140051b38  cmp     r8, rcx
0x140051b3b  jnb     short loc_140051B48
0x140051b3d  lea     rax, [r8+rdx]
0x140051b41  mov     [rsp+110h+var_D8], rax
0x140051b46  jmp     short loc_140051B7C
0x140051b48  jbe     short loc_140051B7C
0x140051b4a  mov     rax, [rsp+110h+var_D0]
0x140051b4f  sub     rax, rdx
0x140051b52  cmp     r8, rax
0x140051b55  jbe     short loc_140051B66
0x140051b57  mov     rdx, r8
0x140051b5a  lea     rcx, [rsp+110h+var_E0]
0x140051b5f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140051b64  jmp     short loc_140051B7C
0x140051b66  sub     r8, rcx; Size
0x140051b69  lea     rbx, [r8+r9]
0x140051b6d  xor     edx, edx; Val
0x140051b6f  mov     rcx, r9; void *
0x140051b72  call    memset_0
0x140051b77  mov     [rsp+110h+var_D8], rbx
0x140051b7c  mov     [rbp+37h+var_98], 0
0x140051b84  lea     r9, [rbp+37h+var_98]; unsigned __int64 *
0x140051b88  xor     r8d, r8d; unsigned __int8 *
0x140051b8b  xor     edx, edx; unsigned __int64
0x140051b8d  mov     rcx, rdi; this
0x140051b90  call    ?ExportPublicKey@KeyPair@SoftwareKey@@QEBAJ_KPEAEPEA_K@Z; SoftwareKey::KeyPair::ExportPublicKey(unsigned __int64,uchar *,unsigned __int64 *)
0x140051b95  mov     ebx, eax
0x140051b97  test    eax, eax
0x140051b99  jns     short loc_140051BA5
0x140051b9b  mov     edx, 9Fh
0x140051ba0  jmp     loc_140051A19
0x140051ba5  mov     rdx, [rbp+37h+var_98]
0x140051ba9  lea     rcx, [rbp+37h+var_90]
0x140051bad  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140051bb2  nop
0x140051bb3  mov     r8, [rbp+37h+var_90]; unsigned __int8 *
0x140051bb7  mov     rdx, [rbp+37h+var_88]
0x140051bbb  sub     rdx, r8; unsigned __int64
0x140051bbe  lea     r9, [rbp+37h+var_98]; unsigned __int64 *
0x140051bc2  mov     rcx, rdi; this
0x140051bc5  call    ?ExportPublicKey@KeyPair@SoftwareKey@@QEBAJ_KPEAEPEA_K@Z; SoftwareKey::KeyPair::ExportPublicKey(unsigned __int64,uchar *,unsigned __int64 *)
0x140051bca  mov     ebx, eax
0x140051bcc  test    eax, eax
0x140051bce  jns     short loc_140051BF7
0x140051bd0  mov     rcx, [rbp+3Fh]; this
0x140051bd4  mov     r9d, eax; char *
0x140051bd7  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140051bde  mov     edx, 0A1h; void *
0x140051be3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140051be8  nop
0x140051be9  lea     rcx, [rbp+37h+var_90]
0x140051bed  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140051bf2  jmp     loc_140051A2D
0x140051bf7  mov     r8, [rbp+37h+var_98]
0x140051bfb  mov     rdx, [rbp+37h+var_90]
0x140051bff  mov     r9, [rbp+37h+var_88]
0x140051c03  mov     rcx, r9
0x140051c06  sub     rcx, rdx
0x140051c09  cmp     r8, rcx
0x140051c0c  jnb     short loc_140051C18
0x140051c0e  lea     rax, [r8+rdx]
0x140051c12  mov     [rbp+37h+var_88], rax
0x140051c16  jmp     short loc_140051C49
0x140051c18  jbe     short loc_140051C49
0x140051c1a  mov     rax, [rbp+37h+var_80]
0x140051c1e  sub     rax, rdx
0x140051c21  cmp     r8, rax
0x140051c24  jbe     short loc_140051C34
0x140051c26  mov     rdx, r8
0x140051c29  lea     rcx, [rbp+37h+var_90]
0x140051c2d  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140051c32  jmp     short loc_140051C49
0x140051c34  sub     r8, rcx; Size
0x140051c37  lea     rbx, [r8+r9]
0x140051c3b  xor     edx, edx; Val
0x140051c3d  mov     rcx, r9; void *
0x140051c40  call    memset_0
0x140051c45  mov     [rbp+37h+var_88], rbx
0x140051c49  call    ??$IsEnabled@V?$Feature@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@wil@@@Velocity@VsmUtils@@SA_NXZ; VsmUtils::Velocity::IsEnabled<wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>>(void)
0x140051c4e  test    al, al
0x140051c50  jz      loc_140051D5D
0x140051c56  mov     rbx, [rbp+37h+arg_28]
0x140051c5a  test    rbx, rbx
0x140051c5d  jz      loc_140051D5D
0x140051c63  mov     edx, 20h ; ' '
0x140051c68  lea     rcx, [rbp+37h+var_50]
0x140051c6c  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x140051c71  nop
0x140051c72  mov     rdx, [rbp+37h+var_50]; unsigned __int64
0x140051c76  mov     rcx, [rbp+37h+var_48]
0x140051c7a  sub     rcx, rdx; cbBuffer
0x140051c7d  call    ?GenRandom@SoftwareKey@@YAJ_KPEAE@Z; SoftwareKey::GenRandom(unsigned __int64,uchar *)
0x140051c82  mov     edi, eax
0x140051c84  test    eax, eax
  ... truncated ...
```
