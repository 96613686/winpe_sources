# NgcIsoContainerImpl::UnprotectEncryptionKeyWithTpmPassword(unsigned __int64,uchar const *,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> *,std::vector<uchar,wil::secure_allocator<uchar>> *,std::vector<uchar,wil::secure_allocator<uchar>> *)

- ea: `0x140049150`
- end: `0x1400494c4`
- name: `?UnprotectEncryptionKeyWithTpmPassword@NgcIsoContainerImpl@@IEAAJ_KPEBEAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV23@33@Z`
- size: `884`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140045960`

## callees

- `0x140008420`
- `0x140009b1c`
- `0x14000aac8`
- `0x14000b3a0`
- `0x14000b658`
- `0x14000cfd0`
- `0x14000e034`
- `0x140010514`
- `0x14001b160`
- `0x14001eb54`
- `0x140043c7c`
- `0x140046f6c`
- `0x14004907c`
- `0x140049150`
- `0x140051250`
- `0x140052724`
- `0x140052f14`
- `0x140071010`

## string_xrefs

- `0x140049190`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\ngcisocontainerimpl.cpp`
- `0x1400491f3`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\ngcisocontainerimpl.cpp`
- `0x14004927a`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\ngcisocontainerimpl.cpp`
- `0x14004931a`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\ngcisocontainerimpl.cpp`
- `0x14004942e`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\ngcisocontainerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NgcIsoContainerImpl::UnprotectEncryptionKeyWithTpmPassword(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  const unsigned __int8 *v11; // r9
  unsigned __int64 v12; // rdx
  unsigned int v13; // ebx
  int v14; // eax
  signed __int64 v15; // rcx
  int v16; // eax
  unsigned __int8 *v17; // rbx
  int v18; // eax
  __int64 v19; // rdx
  unsigned __int8 *v20; // rbx
  int v21; // eax
  int v23; // [rsp+20h] [rbp-91h]
  int v24; // [rsp+20h] [rbp-91h]
  unsigned __int8 *v25; // [rsp+40h] [rbp-71h] BYREF
  void *v26; // [rsp+48h] [rbp-69h]
  __int64 v27; // [rsp+50h] [rbp-61h]
  unsigned __int8 v28[8]; // [rsp+58h] [rbp-59h] BYREF
  __int64 v29; // [rsp+60h] [rbp-51h] BYREF
  unsigned __int64 v30; // [rsp+68h] [rbp-49h] BYREF
  __int128 v31; // [rsp+70h] [rbp-41h] BYREF
  __int64 v32; // [rsp+80h] [rbp-31h]
  _BYTE v33[24]; // [rsp+88h] [rbp-29h] BYREF
  int v34[20]; // [rsp+A0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+47h]
  unsigned __int64 v36; // [rsp+118h] [rbp+67h] BYREF

  v11 = *(const unsigned __int8 **)a4;
  v12 = *(_QWORD *)(a4 + 8);
  if ( v12 - (unsigned __int64)v11 >= 0x10 )
  {
    v31 = 0;
    v32 = 0;
    *(_QWORD *)v28 = v11 + 16;
    v36 = v12;
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Construct_n<unsigned char const *,unsigned char const *>(
      &v31,
      v12 - (_QWORD)(v11 + 16),
      v28,
      &v36);
    v14 = anonymous_namespace_::TpmUnsealWithPasswordInPlace(a2);
    v13 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x175,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\ngcisocontainerimpl.cpp",
        (const char *)(unsigned int)v14,
        v23);
LABEL_33:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v31);
      return v13;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
      &v25,
      a5);
    LOBYTE(v36) = 0;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1) == 1 )
    {
      *(_QWORD *)v28 = 0;
      v16 = NgcIsoTrustlet::DecryptData(
              (NgcIsoTrustlet *)((_BYTE *)v26 - v25),
              (unsigned __int64)v25,
              0,
              0,
              (const unsigned __int8 *)((_BYTE *)v26 - v25),
              (unsigned __int64)v25,
              v28,
              &v36,
              (bool *)v25);
      v13 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x187,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\ngcisocontainerimpl.cpp",
          (const char *)(unsigned int)v16,
          v23);
LABEL_8:
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v25);
        goto LABEL_33;
      }
      v15 = (_BYTE *)v26 - v25;
      if ( *(_QWORD *)v28 >= (unsigned __int64)((_BYTE *)v26 - v25) )
      {
        if ( *(_QWORD *)v28 > (unsigned __int64)((_BYTE *)v26 - v25) )
        {
          if ( *(_QWORD *)v28 <= (unsigned __int64)(v27 - (_QWORD)v25) )
          {
            v17 = &v25[*(_QWORD *)v28];
            memset_0(v26, 0, *(_QWORD *)v28 - v15);
            v26 = v17;
          }
          else
          {
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Resize_reallocate<std::_Value_init_tag>(
              &v25,
              *(_QWORD *)v28);
          }
        }
      }
      else
      {
        v26 = &v25[*(_QWORD *)v28];
      }
    }
    v29 = 0;
    v18 = SoftwareKey::SymmetricKey::Import(v15, *((_QWORD *)&v31 + 1) - v31, v31, v28);
    v13 = v18;
    if ( v18 >= 0 )
    {
      v18 = SoftwareKey::SymmetricKey::SetInitializationVector(
              (SoftwareKey::SymmetricKey *)v28,
              0x10u,
              *(const unsigned __int8 **)a4);
      v13 = v18;
      if ( v18 >= 0 )
      {
        v30 = 0;
        v18 = SoftwareKey::SymmetricKey::DecryptData(
                (SoftwareKey::SymmetricKey *)v28,
                (_BYTE *)v26 - v25,
                v25,
                (_BYTE *)v26 - v25,
                v25,
                &v30);
        v13 = v18;
        if ( v18 >= 0 )
        {
          if ( v30 >= (_BYTE *)v26 - v25 )
          {
            if ( v30 > (_BYTE *)v26 - v25 )
            {
              if ( v30 <= v27 - (__int64)v25 )
              {
                v20 = &v25[v30];
                memset_0(v26, 0, v30 - ((_BYTE *)v26 - v25));
                v26 = v20;
              }
              else
              {
                std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Resize_reallocate<std::_Value_init_tag>(
                  &v25,
                  v30);
              }
            }
          }
          else
          {
            v26 = &v25[v30];
          }
          std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v33);
          std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v34);
          if ( !(_BYTE)v36
            || (std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=(v33, &v25),
                v21 = NgcIsoContainerImpl::ProtectEncryptionKeyWithTpmPassword(
                        a1,
                        a2,
                        a3,
                        (unsigned int)v33,
                        (__int64)v34),
                v13 = v21,
                v21 >= 0) )
          {
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=(a5, &v25);
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=(a6, v33);
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=(a7, v34);
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v34);
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v33);
            wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v29);
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v25);
            v13 = 0;
            goto LABEL_33;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AA,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\ngcisocontainerimpl.cpp",
            (const char *)(unsigned int)v21,
            v24);
          std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v34);
          std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v33);
          goto LABEL_18;
        }
        v19 = 414;
      }
      else
      {
        v19 = 406;
      }
    }
    else
    {
      v19 = 401;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\ngcisocontainerimpl.cpp",
      (const char *)(unsigned int)v18,
      v23);
LABEL_18:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v29);
    goto LABEL_8;
  }
  v13 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x171,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\lib\\ngcisocontainerimpl.cpp",
    (const char *)0x80070057LL,
    v23);
  return v13;
}

```

## disassembly

```asm
0x140049150  push    rbp
0x140049152  push    rbx
0x140049153  push    rsi
0x140049154  push    rdi
0x140049155  push    r14
0x140049157  push    r15
0x140049159  lea     rbp, [rsp-17h]
0x14004915e  sub     rsp, 0C8h
0x140049165  mov     rdi, r9
0x140049168  mov     r14, r8
0x14004916b  mov     r15, rdx
0x14004916e  mov     rsi, rcx
0x140049171  mov     r9, [r9]
0x140049174  mov     rdx, [rdi+8]
0x140049178  mov     rax, rdx
0x14004917b  sub     rax, r9
0x14004917e  cmp     rax, 10h
0x140049182  jnb     short loc_1400491A6
0x140049184  mov     rcx, [rbp+47h]; this
0x140049188  mov     ebx, 80070057h
0x14004918d  mov     r9d, ebx; char *
0x140049190  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140049197  mov     edx, 171h; void *
0x14004919c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400491a1  jmp     loc_1400494B2
0x1400491a6  lea     rax, [r9+10h]
0x1400491aa  xorps   xmm0, xmm0
0x1400491ad  movdqu  [rbp+3Fh+var_80], xmm0
0x1400491b2  mov     [rbp+3Fh+var_70], 0
0x1400491ba  mov     qword ptr [rbp+3Fh+var_98], rax
0x1400491be  mov     [rbp+3Fh+arg_18], rdx
0x1400491c2  sub     rdx, rax
0x1400491c5  lea     r9, [rbp+3Fh+arg_18]
0x1400491c9  lea     r8, [rbp+3Fh+var_98]
0x1400491cd  lea     rcx, [rbp+3Fh+var_80]
0x1400491d1  call    ??$_Construct_n@PEBEPEBE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAX_K$$QEAPEBE1@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Construct_n<uchar const *,uchar const *>(unsigned __int64,uchar const * &&,uchar const * &&)
0x1400491d6  nop
0x1400491d7  lea     r8, [rbp+3Fh+var_80]
0x1400491db  mov     rdx, r14
0x1400491de  mov     rcx, r15; int
0x1400491e1  call    _anonymous_namespace___TpmUnsealWithPasswordInPlace
0x1400491e6  mov     ebx, eax
0x1400491e8  test    eax, eax
0x1400491ea  jns     short loc_140049209
0x1400491ec  mov     rcx, [rbp+47h]; this
0x1400491f0  mov     r9d, eax; char *
0x1400491f3  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1400491fa  mov     edx, 175h; void *
0x1400491ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140049204  jmp     loc_1400494A9
0x140049209  mov     rdx, [rbp+3Fh+arg_20]
0x14004920d  lea     rcx, [rbp+3Fh+var_B0]
0x140049211  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@AEBV01@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x140049216  nop
0x140049217  mov     byte ptr [rbp+3Fh+arg_18], 0
0x14004921b  mov     rax, [rsi]
0x14004921e  mov     rcx, rsi
0x140049221  mov     rax, [rax+8]
0x140049225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004922a  cmp     eax, 1
0x14004922d  jnz     loc_1400492EC
0x140049233  mov     qword ptr [rbp+3Fh+var_98], 0
0x14004923b  mov     rdx, [rbp+3Fh+var_B0]; unsigned __int64
0x14004923f  mov     rcx, [rbp+3Fh+var_A8]
0x140049243  sub     rcx, rdx; this
0x140049246  lea     rax, [rbp+3Fh+arg_18]
0x14004924a  mov     [rsp+0F0h+var_B8], rax; unsigned __int64 *
0x14004924f  lea     rax, [rbp+3Fh+var_98]
0x140049253  mov     [rsp+0F0h+var_C0], rax; unsigned __int8 *
0x140049258  mov     [rsp+0F0h+var_C8], rdx; unsigned __int64
0x14004925d  mov     [rsp+0F0h+var_D0], rcx; int
0x140049262  xor     r9d, r9d; unsigned __int64
0x140049265  xor     r8d, r8d; unsigned __int8 *
0x140049268  call    ?DecryptData@NgcIsoTrustlet@@YAJ_KPEBE010PEAEPEA_KPEA_N@Z; NgcIsoTrustlet::DecryptData(unsigned __int64,uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar *,unsigned __int64 *,bool *)
0x14004926d  mov     ebx, eax
0x14004926f  test    eax, eax
0x140049271  jns     short loc_14004929A
0x140049273  mov     rcx, [rbp+47h]; this
0x140049277  mov     r9d, eax; char *
0x14004927a  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140049281  mov     edx, 187h; void *
0x140049286  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004928b  nop
0x14004928c  lea     rcx, [rbp+3Fh+var_B0]
0x140049290  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x140049295  jmp     loc_1400494A9
0x14004929a  mov     r8, qword ptr [rbp+3Fh+var_98]
0x14004929e  mov     rdx, [rbp+3Fh+var_B0]
0x1400492a2  mov     r9, [rbp+3Fh+var_A8]
0x1400492a6  mov     rcx, r9
0x1400492a9  sub     rcx, rdx
0x1400492ac  cmp     r8, rcx
0x1400492af  jnb     short loc_1400492BB
0x1400492b1  lea     rax, [rdx+r8]
0x1400492b5  mov     [rbp+3Fh+var_A8], rax
0x1400492b9  jmp     short loc_1400492EC
0x1400492bb  jbe     short loc_1400492EC
0x1400492bd  mov     rax, [rbp+3Fh+var_A0]
0x1400492c1  sub     rax, rdx
0x1400492c4  cmp     r8, rax
0x1400492c7  jbe     short loc_1400492D7
0x1400492c9  mov     rdx, r8
0x1400492cc  lea     rcx, [rbp+3Fh+var_B0]
0x1400492d0  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1400492d5  jmp     short loc_1400492EC
0x1400492d7  sub     r8, rcx; Size
0x1400492da  lea     rbx, [r8+r9]
0x1400492de  xor     edx, edx; Val
0x1400492e0  mov     rcx, r9; void *
0x1400492e3  call    memset_0
0x1400492e8  mov     [rbp+3Fh+var_A8], rbx
0x1400492ec  mov     [rbp+3Fh+var_90], 0
0x1400492f4  mov     r8, qword ptr [rbp+3Fh+var_80]
0x1400492f8  mov     rdx, qword ptr [rbp+3Fh+var_80+8]
0x1400492fc  sub     rdx, r8
0x1400492ff  lea     r9, [rbp+3Fh+var_98]
0x140049303  call    ?Import@SymmetricKey@SoftwareKey@@SAJW4Algorithm@@_KPEBEPEAV12@@Z; SoftwareKey::SymmetricKey::Import(Algorithm,unsigned __int64,uchar const *,SoftwareKey::SymmetricKey *)
0x140049308  mov     ebx, eax
0x14004930a  test    eax, eax
0x14004930c  jns     short loc_140049335
0x14004930e  mov     edx, 191h; void *
0x140049313  mov     rcx, [rbp+47h]; this
0x140049317  mov     r9d, eax; char *
0x14004931a  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140049321  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140049326  nop
0x140049327  lea     rcx, [rbp+3Fh+var_90]
0x14004932b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140049330  jmp     loc_14004928C
0x140049335  mov     r8, [rdi]; unsigned __int8 *
0x140049338  mov     edx, 10h; unsigned __int64
0x14004933d  lea     rcx, [rbp+3Fh+var_98]; this
0x140049341  call    ?SetInitializationVector@SymmetricKey@SoftwareKey@@QEAAJ_KPEBE@Z; SoftwareKey::SymmetricKey::SetInitializationVector(unsigned __int64,uchar const *)
0x140049346  mov     ebx, eax
0x140049348  test    eax, eax
0x14004934a  jns     short loc_140049353
0x14004934c  mov     edx, 196h
0x140049351  jmp     short loc_140049313
0x140049353  mov     [rbp+3Fh+var_88], 0
0x14004935b  mov     r8, [rbp+3Fh+var_B0]; unsigned __int8 *
0x14004935f  mov     rdx, [rbp+3Fh+var_A8]
0x140049363  sub     rdx, r8; unsigned __int64
0x140049366  lea     rax, [rbp+3Fh+var_88]
0x14004936a  mov     [rsp+0F0h+var_C8], rax; unsigned __int64 *
0x14004936f  mov     [rsp+0F0h+var_D0], r8; unsigned __int8 *
0x140049374  mov     r9, rdx; unsigned __int64
0x140049377  lea     rcx, [rbp+3Fh+var_98]; this
0x14004937b  call    ?DecryptData@SymmetricKey@SoftwareKey@@QEBAJ_KPEBE0PEAEPEA_K@Z; SoftwareKey::SymmetricKey::DecryptData(unsigned __int64,uchar const *,unsigned __int64,uchar *,unsigned __int64 *)
0x140049380  mov     ebx, eax
0x140049382  test    eax, eax
0x140049384  jns     short loc_14004938D
0x140049386  mov     edx, 19Eh
0x14004938b  jmp     short loc_140049313
0x14004938d  mov     r8, [rbp+3Fh+var_88]
0x140049391  mov     rdx, [rbp+3Fh+var_B0]
0x140049395  mov     r9, [rbp+3Fh+var_A8]
0x140049399  mov     rcx, r9
0x14004939c  sub     rcx, rdx
0x14004939f  cmp     r8, rcx
0x1400493a2  jnb     short loc_1400493AE
0x1400493a4  lea     rax, [rdx+r8]
0x1400493a8  mov     [rbp+3Fh+var_A8], rax
0x1400493ac  jmp     short loc_1400493DF
0x1400493ae  jbe     short loc_1400493DF
0x1400493b0  mov     rax, [rbp+3Fh+var_A0]
0x1400493b4  sub     rax, rdx
0x1400493b7  cmp     r8, rax
0x1400493ba  jbe     short loc_1400493CA
0x1400493bc  mov     rdx, r8
0x1400493bf  lea     rcx, [rbp+3Fh+var_B0]
0x1400493c3  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1400493c8  jmp     short loc_1400493DF
0x1400493ca  sub     r8, rcx; Size
0x1400493cd  lea     rbx, [r8+r9]
0x1400493d1  xor     edx, edx; Val
0x1400493d3  mov     rcx, r9; void *
0x1400493d6  call    memset_0
0x1400493db  mov     [rbp+3Fh+var_A8], rbx
0x1400493df  lea     rcx, [rbp+3Fh+var_68]
0x1400493e3  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1400493e8  nop
0x1400493e9  lea     rcx, [rbp+3Fh+var_50]
0x1400493ed  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1400493f2  nop
0x1400493f3  cmp     byte ptr [rbp+3Fh+arg_18], 0
0x1400493f7  jz      short loc_140049458
0x1400493f9  lea     rdx, [rbp+3Fh+var_B0]
0x1400493fd  lea     rcx, [rbp+3Fh+var_68]
0x140049401  call    ??4?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::operator=(std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x140049406  lea     rax, [rbp+3Fh+var_50]
0x14004940a  mov     [rsp+0F0h+var_D0], rax; int
0x14004940f  lea     r9, [rbp+3Fh+var_68]
0x140049413  mov     r8, r14
0x140049416  mov     rdx, r15
0x140049419  mov     rcx, rsi
0x14004941c  call    ?ProtectEncryptionKeyWithTpmPassword@NgcIsoContainerImpl@@IEAAJ_KPEBEPEAV?$vector@EU?$secure_allocator@E@wil@@@std@@2@Z; NgcIsoContainerImpl::ProtectEncryptionKeyWithTpmPassword(unsigned __int64,uchar const *,std::vector<uchar,wil::secure_allocator<uchar>> *,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x140049421  mov     ebx, eax
0x140049423  test    eax, eax
0x140049425  jns     short loc_140049458
0x140049427  mov     rcx, [rbp+47h]; this
0x14004942b  mov     r9d, eax; char *
0x14004942e  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140049435  mov     edx, 1AAh; void *
0x14004943a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004943f  nop
0x140049440  lea     rcx, [rbp+3Fh+var_50]
0x140049444  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x140049449  nop
0x14004944a  lea     rcx, [rbp+3Fh+var_68]
0x14004944e  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x140049453  jmp     loc_140049327
0x140049458  lea     rdx, [rbp+3Fh+var_B0]
0x14004945c  mov     rcx, [rbp+3Fh+arg_20]
0x140049460  call    ??4?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::operator=(std::vector<uchar,wil::secure_allocator<uchar>> &&)
0x140049465  lea     rdx, [rbp+3Fh+var_68]
0x140049469  mov     rcx, [rbp+3Fh+arg_28]
0x14004946d  call    ??4?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::operator=(std::vector<uchar,wil::secure_allocator<uchar>> &&)
0x140049472  lea     rdx, [rbp+3Fh+var_50]
0x140049476  mov     rcx, [rbp+3Fh+arg_30]
0x14004947a  call    ??4?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::operator=(std::vector<uchar,wil::secure_allocator<uchar>> &&)
0x14004947f  nop
0x140049480  lea     rcx, [rbp+3Fh+var_50]
0x140049484  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x140049489  nop
0x14004948a  lea     rcx, [rbp+3Fh+var_68]
0x14004948e  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x140049493  nop
0x140049494  lea     rcx, [rbp+3Fh+var_90]
0x140049498  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14004949d  nop
0x14004949e  lea     rcx, [rbp+3Fh+var_B0]
0x1400494a2  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1400494a7  xor     ebx, ebx
0x1400494a9  lea     rcx, [rbp+3Fh+var_80]
0x1400494ad  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1400494b2  mov     eax, ebx
0x1400494b4  add     rsp, 0C8h
0x1400494bb  pop     r15
0x1400494bd  pop     r14
0x1400494bf  pop     rdi
0x1400494c0  pop     rsi
0x1400494c1  pop     rbx
0x1400494c2  pop     rbp
0x1400494c3  retn
```
