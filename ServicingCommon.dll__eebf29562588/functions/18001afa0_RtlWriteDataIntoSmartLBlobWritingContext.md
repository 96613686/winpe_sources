# RtlWriteDataIntoSmartLBlobWritingContext

- ea: `0x18001afa0`
- end: `0x18001b35e`
- name: `RtlWriteDataIntoSmartLBlobWritingContext`
- size: `958`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ba00`
- `0x18001bc60`
- `0x1800585d0`
- `0x180062fa8`
- `0x180068aec`

## callees

- `0x180002df0`
- `0x180003520`
- `0x18000de50`
- `0x18001afa0`
- `0x18001f4ac`
- `0x18001f5d4`
- `0x18001fd10`
- `0x180024aa0`
- `0x1800293a0`
- `0x180063844`
- `0x1800a0020`

## string_xrefs

- `0x18001afec`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x18001b038`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x18001b076`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x18001b0f5`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x18001b136`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x18001b191`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x18001b244`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x18001b2f4`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x18001b106`: `BUCL::Rtl::Add<SIZE_T>(DataLength, OldLength, TempSize)`

## pseudocode

```c
__int64 __fastcall RtlWriteDataIntoSmartLBlobWritingContext(__int64 a1, char **a2)
{
  const char *v4; // rax
  char *v6; // rsi
  char *v7; // rdi
  rsize_t v8; // r14
  unsigned __int64 *v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdi
  const char **v12; // rdx
  __int64 v13; // r8
  unsigned __int64 v14; // r8
  char *v15; // rax
  unsigned __int64 v16; // rdx
  int v17; // eax
  char *v18; // rcx
  char *v19; // rax
  unsigned int v20; // ebx
  char *v21; // rcx
  char *v22; // rax
  char *v23; // rdx
  __int128 v24; // [rsp+20h] [rbp-89h] BYREF
  __int64 v25; // [rsp+30h] [rbp-79h]
  const char *v26; // [rsp+38h] [rbp-71h]
  const char *v27; // [rsp+40h] [rbp-69h] BYREF
  const char *v28; // [rsp+48h] [rbp-61h]
  __int64 v29; // [rsp+50h] [rbp-59h]
  __int64 v30; // [rsp+58h] [rbp-51h]
  _QWORD v31[4]; // [rsp+60h] [rbp-49h] BYREF
  _QWORD v32[4]; // [rsp+80h] [rbp-29h] BYREF
  _QWORD v33[4]; // [rsp+A0h] [rbp-9h] BYREF
  int v34; // [rsp+C0h] [rbp+17h] BYREF
  unsigned __int64 v35; // [rsp+C8h] [rbp+1Fh] BYREF

  v34 = 0;
  if ( !a1 )
  {
    v25 = 1774;
    *(_QWORD *)&v24 = "onecore\\base\\lstring\\lblob.cpp";
    *((_QWORD *)&v24 + 1) = "RtlWriteDataIntoSmartLBlobWritingContext";
    v4 = "Not-null check failed: Data";
LABEL_3:
    v26 = v4;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v34,
             &v24);
  }
  if ( !(unsigned __int8)RtlIsLBlobValid() )
  {
    v25 = 1775;
    *(_QWORD *)&v24 = "onecore\\base\\lstring\\lblob.cpp";
    *((_QWORD *)&v24 + 1) = "RtlWriteDataIntoSmartLBlobWritingContext";
    v26 = "::RtlIsLBlobValid(Data)";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v34,
             &v24);
  }
  if ( !a2 )
  {
    v25 = 1776;
    *(_QWORD *)&v24 = "onecore\\base\\lstring\\lblob.cpp";
    *((_QWORD *)&v24 + 1) = "RtlWriteDataIntoSmartLBlobWritingContext";
    v4 = "Not-null check failed: Context";
    goto LABEL_3;
  }
  v6 = a2[1];
  v7 = *a2;
  v8 = *(_QWORD *)a1;
  if ( *(_QWORD *)a1 > (unsigned __int64)(v6 - *a2) )
  {
    if ( !a2[6] )
      return 3221225507LL;
    v25 = 0;
    v9 = (unsigned __int64 *)a2[4];
    v24 = 0;
    v10 = *v9;
    v35 = 0;
    v11 = v10 + v8;
    if ( v10 + v8 < v8 )
    {
      v31[2] = 1794;
      v31[0] = "onecore\\base\\lstring\\lblob.cpp";
      v12 = (const char **)v31;
      v13 = 3221225621LL;
      v31[1] = "RtlWriteDataIntoSmartLBlobWritingContext";
      v31[3] = "BUCL::Rtl::Add<SIZE_T>(DataLength, OldLength, TempSize)";
LABEL_31:
      v17 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
              &v34,
              v12,
              v13);
      goto LABEL_32;
    }
    v14 = (unsigned __int64)a2[3];
    if ( v11 > v14 )
    {
      v32[2] = 1797;
      v32[0] = "onecore\\base\\lstring\\lblob.cpp";
      v12 = (const char **)v32;
      v32[3] = 0;
      v32[1] = "RtlWriteDataIntoSmartLBlobWritingContext";
      v13 = 3221226539LL;
      goto LABEL_31;
    }
    v15 = a2[8];
    v16 = v10 + v8;
    if ( v15 )
      v17 = ((__int64 (__fastcall *)(char **, unsigned __int64, unsigned __int64 *))v15)(a2, v16, &v35);
    else
      v17 = RtlpSmartLBlobWritingContextResizePolicy(v10, v16, v14, &v35);
    if ( v17 < 0 )
      goto LABEL_32;
    if ( v35 < v11 )
    {
      v33[2] = 1813;
      v33[0] = "onecore\\base\\lstring\\lblob.cpp";
      v12 = (const char **)v33;
      v33[3] = 0;
      v33[1] = "RtlWriteDataIntoSmartLBlobWritingContext";
      v13 = 3221225507LL;
      goto LABEL_31;
    }
    v18 = a2[6];
    v19 = a2[4];
    if ( v19 == v18 )
    {
      if ( *((_QWORD *)v19 + 1) < v35 )
      {
        v17 = RtlReallocateLBlob(0, v35, a2[6]);
        if ( v17 < 0 )
          goto LABEL_32;
      }
    }
    else
    {
      if ( v19 != a2[5] )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x18001B35DLL);
      }
      if ( *((_QWORD *)v18 + 1) < v35 )
      {
        v17 = RtlReallocateLBlob(0, v35, a2[6]);
        if ( v17 < 0 )
        {
LABEL_32:
          v20 = v17;
          Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v24);
          return v20;
        }
        v18 = a2[6];
      }
      if ( memcpy_s_0(
             *((void *const *)v18 + 2),
             *((_QWORD *)v18 + 1),
             *((const void *const *)a2[4] + 2),
             *(_QWORD *)a2[4] != 0) )
      {
        v29 = 1839;
        v27 = "onecore\\base\\lstring\\lblob.cpp";
        v12 = &v27;
        v30 = 0;
        v28 = "RtlWriteDataIntoSmartLBlobWritingContext";
        v13 = 3221684490LL;
        goto LABEL_31;
      }
      *(_QWORD *)a2[6] = *(_QWORD *)a2[4];
      v21 = a2[7];
      v22 = a2[6];
      a2[4] = v22;
      if ( v21 )
        *(_QWORD *)v21 = v22;
    }
    v23 = a2[4];
    v7 = (char *)(*(_QWORD *)v23 + *((_QWORD *)v23 + 2));
    *a2 = v7;
    v6 = (char *)(*((_QWORD *)v23 + 2) + *((_QWORD *)v23 + 1));
    a2[1] = v6;
    Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v24);
  }
  if ( v8 )
  {
    if ( memcpy_s_0(v7, v6 - v7, *(const void *const *)(a1 + 16), v8) )
    {
      v29 = 1871;
      v27 = "onecore\\base\\lstring\\lblob.cpp";
      v30 = 0;
      v28 = "RtlWriteDataIntoSmartLBlobWritingContext";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v34,
               &v27,
               3221684490LL);
    }
    *(_QWORD *)a2[4] = &v7[v8 - *((_QWORD *)a2[4] + 2)];
    *a2 = &v7[v8];
  }
  return 0;
}

```

## disassembly

```asm
0x18001afa0  mov     [rsp-8+arg_10], rbx
0x18001afa5  push    rbp
0x18001afa6  push    rsi
0x18001afa7  push    rdi
0x18001afa8  push    r14
0x18001afaa  push    r15
0x18001afac  lea     rbp, [rsp-37h]
0x18001afb1  sub     rsp, 0E0h
0x18001afb8  mov     rax, cs:__security_cookie
0x18001afbf  xor     rax, rsp
0x18001afc2  mov     [rbp+57h+var_30], rax
0x18001afc6  mov     [rbp+57h+var_40], 0
0x18001afcd  mov     rbx, rdx
0x18001afd0  mov     r15, rcx
0x18001afd3  test    rcx, rcx
0x18001afd6  jnz     short loc_18001B016
0x18001afd8  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001afdf  mov     [rbp+57h+var_D0], 6EEh
0x18001afe7  mov     qword ptr [rsp+100h+var_E0], rax
0x18001afec  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x18001aff3  mov     qword ptr [rsp+100h+var_E0+8], rax
0x18001aff8  lea     rax, aNotNullCheckFa_15; "Not-null check failed: Data"
0x18001afff  lea     rdx, [rsp+100h+var_E0]
0x18001b004  mov     [rbp+57h+var_C8], rax
0x18001b008  lea     rcx, [rbp+57h+var_40]
0x18001b00c  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001b011  jmp     loc_18001B32F
0x18001b016  call    RtlIsLBlobValid
0x18001b01b  test    al, al
0x18001b01d  jnz     short loc_18001B05D
0x18001b01f  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001b026  mov     [rbp+57h+var_D0], 6EFh
0x18001b02e  mov     qword ptr [rsp+100h+var_E0], rax
0x18001b033  lea     rdx, [rsp+100h+var_E0]
0x18001b038  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x18001b03f  mov     qword ptr [rsp+100h+var_E0+8], rax
0x18001b044  lea     rcx, [rbp+57h+var_40]
0x18001b048  lea     rax, aRtlislblobvali_2; "::RtlIsLBlobValid(Data)"
0x18001b04f  mov     [rbp+57h+var_C8], rax
0x18001b053  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001b058  jmp     loc_18001B32F
0x18001b05d  test    rbx, rbx
0x18001b060  jnz     short loc_18001B08E
0x18001b062  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001b069  mov     [rbp+57h+var_D0], 6F0h
0x18001b071  mov     qword ptr [rsp+100h+var_E0], rax
0x18001b076  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x18001b07d  mov     qword ptr [rsp+100h+var_E0+8], rax
0x18001b082  lea     rax, aNotNullCheckFa_7; "Not-null check failed: Context"
0x18001b089  jmp     loc_18001AFFF
0x18001b08e  mov     rsi, [rbx+8]
0x18001b092  mov     rdi, [rbx]
0x18001b095  mov     rax, rsi
0x18001b098  mov     r14, [r15]
0x18001b09b  sub     rax, rdi
0x18001b09e  cmp     r14, rax
0x18001b0a1  jbe     loc_18001B2BF
0x18001b0a7  cmp     qword ptr [rbx+30h], 0
0x18001b0ac  jnz     short loc_18001B0B8
0x18001b0ae  mov     eax, 0C0000023h
0x18001b0b3  jmp     loc_18001B32F
0x18001b0b8  xor     eax, eax
0x18001b0ba  xorps   xmm0, xmm0
0x18001b0bd  mov     [rbp+57h+var_D0], rax
0x18001b0c1  mov     rax, [rbx+20h]
0x18001b0c5  movups  [rsp+100h+var_E0], xmm0
0x18001b0ca  mov     rcx, [rax]; unsigned __int64
0x18001b0cd  mov     [rbp+57h+var_38], 0
0x18001b0d5  lea     rdi, [rcx+r14]
0x18001b0d9  cmp     rdi, r14
0x18001b0dc  jnb     short loc_18001B116
0x18001b0de  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001b0e5  mov     [rbp+57h+var_90], 702h
0x18001b0ed  mov     [rbp+57h+var_A0], rax
0x18001b0f1  lea     rdx, [rbp+57h+var_A0]
0x18001b0f5  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x18001b0fc  mov     r8d, 0C0000095h
0x18001b102  mov     [rbp+57h+var_98], rax
0x18001b106  lea     rax, aBuclRtlAddSize_0; "BUCL::Rtl::Add<SIZE_T>(DataLength, OldL"...
0x18001b10d  mov     [rbp+57h+var_88], rax
0x18001b111  jmp     loc_18001B25D
0x18001b116  mov     r8, [rbx+18h]; unsigned __int64
0x18001b11a  cmp     rdi, r8
0x18001b11d  jbe     short loc_18001B154
0x18001b11f  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001b126  mov     [rbp+57h+var_70], 705h
0x18001b12e  mov     [rbp+57h+var_80], rax
0x18001b132  lea     rdx, [rbp+57h+var_80]
0x18001b136  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x18001b13d  mov     [rbp+57h+var_68], 0
0x18001b145  mov     [rbp+57h+var_78], rax
0x18001b149  mov     r8d, 0C000042Bh
0x18001b14f  jmp     loc_18001B25D
0x18001b154  mov     rax, [rbx+40h]
0x18001b158  mov     rdx, rdi; unsigned __int64
0x18001b15b  test    rax, rax
0x18001b15e  jnz     short loc_18001B1AF
0x18001b160  lea     r9, [rbp+57h+var_38]; unsigned __int64 *
0x18001b164  call    ?RtlpSmartLBlobWritingContextResizePolicy@@YAJ_K00PEA_K@Z; RtlpSmartLBlobWritingContextResizePolicy(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001b169  test    eax, eax
0x18001b16b  js      loc_18001B266
0x18001b171  mov     rdx, [rbp+57h+var_38]
0x18001b175  cmp     rdx, rdi
0x18001b178  jnb     short loc_18001B1BD
0x18001b17a  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001b181  mov     [rbp+57h+var_50], 715h
0x18001b189  mov     [rbp+57h+var_60], rax
0x18001b18d  lea     rdx, [rbp+57h+var_60]
0x18001b191  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x18001b198  mov     [rbp+57h+var_48], 0
0x18001b1a0  mov     [rbp+57h+var_58], rax
0x18001b1a4  mov     r8d, 0C0000023h
0x18001b1aa  jmp     loc_18001B25D
0x18001b1af  lea     r8, [rbp+57h+var_38]
0x18001b1b3  mov     rcx, rbx
0x18001b1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1bb  jmp     short loc_18001B169
0x18001b1bd  mov     rcx, [rbx+30h]
0x18001b1c1  mov     rax, [rbx+20h]
0x18001b1c5  cmp     rax, rcx
0x18001b1c8  jnz     short loc_18001B1E8
0x18001b1ca  cmp     [rax+8], rdx
0x18001b1ce  jnb     loc_18001B29B
0x18001b1d4  mov     r8, rcx
0x18001b1d7  xor     ecx, ecx
0x18001b1d9  call    RtlReallocateLBlob
0x18001b1de  test    eax, eax
0x18001b1e0  jns     loc_18001B29B
0x18001b1e6  jmp     short loc_18001B266
0x18001b1e8  cmp     rax, [rbx+28h]
0x18001b1ec  jnz     loc_18001B353
0x18001b1f2  cmp     [rcx+8], rdx
0x18001b1f6  jnb     short loc_18001B20A
0x18001b1f8  mov     r8, rcx
0x18001b1fb  xor     ecx, ecx
0x18001b1fd  call    RtlReallocateLBlob
0x18001b202  test    eax, eax
0x18001b204  js      short loc_18001B266
0x18001b206  mov     rcx, [rbx+30h]
0x18001b20a  mov     r8, [rbx+20h]
0x18001b20e  xor     r9d, r9d
0x18001b211  mov     rdx, [rcx+8]; DestinationSize
0x18001b215  mov     rcx, [rcx+10h]; Destination
0x18001b219  cmp     [r8], r9
0x18001b21c  mov     r8, [r8+10h]; Source
0x18001b220  setnz   r9b; SourceSize
0x18001b224  call    memcpy_s_0
0x18001b229  test    eax, eax
0x18001b22b  jz      short loc_18001B279
0x18001b22d  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001b234  mov     [rbp+57h+var_B0], 72Fh
0x18001b23c  mov     [rbp+57h+var_C0], rax
0x18001b240  lea     rdx, [rbp+57h+var_C0]
0x18001b244  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x18001b24b  mov     [rbp+57h+var_A8], 0
0x18001b253  mov     [rbp+57h+var_B8], rax
0x18001b257  mov     r8d, 0C007010Ah
0x18001b25d  lea     rcx, [rbp+57h+var_40]
0x18001b261  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18001b266  lea     rcx, [rsp+100h+var_E0]
0x18001b26b  mov     ebx, eax
0x18001b26d  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x18001b272  mov     eax, ebx
0x18001b274  jmp     loc_18001B32F
0x18001b279  mov     rax, [rbx+20h]
0x18001b27d  mov     rcx, [rbx+30h]
0x18001b281  mov     rax, [rax]
0x18001b284  mov     [rcx], rax
0x18001b287  mov     rcx, [rbx+38h]
0x18001b28b  mov     rax, [rbx+30h]
0x18001b28f  mov     [rbx+20h], rax
0x18001b293  test    rcx, rcx
0x18001b296  jz      short loc_18001B29B
0x18001b298  mov     [rcx], rax
0x18001b29b  mov     rdx, [rbx+20h]
0x18001b29f  lea     rcx, [rsp+100h+var_E0]
0x18001b2a4  mov     rdi, [rdx+10h]
0x18001b2a8  add     rdi, [rdx]
0x18001b2ab  mov     [rbx], rdi
0x18001b2ae  mov     rsi, [rdx+8]
0x18001b2b2  add     rsi, [rdx+10h]
0x18001b2b6  mov     [rbx+8], rsi
0x18001b2ba  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x18001b2bf  test    r14, r14
0x18001b2c2  jz      short loc_18001B32D
0x18001b2c4  mov     r8, [r15+10h]; Source
0x18001b2c8  sub     rsi, rdi
0x18001b2cb  mov     rdx, rsi; DestinationSize
0x18001b2ce  mov     r9, r14; SourceSize
0x18001b2d1  mov     rcx, rdi; Destination
0x18001b2d4  call    memcpy_s_0
0x18001b2d9  test    eax, eax
0x18001b2db  jz      short loc_18001B318
0x18001b2dd  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001b2e4  mov     [rbp+57h+var_B0], 74Fh
0x18001b2ec  mov     [rbp+57h+var_C0], rax
0x18001b2f0  lea     rdx, [rbp+57h+var_C0]
0x18001b2f4  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x18001b2fb  mov     [rbp+57h+var_A8], 0
0x18001b303  mov     r8d, 0C007010Ah
0x18001b309  mov     [rbp+57h+var_B8], rax
0x18001b30d  lea     rcx, [rbp+57h+var_40]
0x18001b311  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18001b316  jmp     short loc_18001B32F
0x18001b318  mov     rcx, [rbx+20h]
0x18001b31c  lea     rdx, [r14+rdi]
0x18001b320  mov     rax, rdx
0x18001b323  sub     rax, [rcx+10h]
0x18001b327  mov     [rcx], rax
0x18001b32a  mov     [rbx], rdx
0x18001b32d  xor     eax, eax
0x18001b32f  mov     rcx, [rbp+57h+var_30]
0x18001b333  xor     rcx, rsp; StackCookie
0x18001b336  call    __security_check_cookie
0x18001b33b  mov     rbx, [rsp+100h+arg_10]
0x18001b343  add     rsp, 0E0h
0x18001b34a  pop     r15
0x18001b34c  pop     r14
0x18001b34e  pop     rdi
0x18001b34f  pop     rsi
0x18001b350  pop     rbp
0x18001b351  retn
0x18001b353  mov     ecx, 0C00000E5h; int
0x18001b358  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
