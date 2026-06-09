# RtlWriteDataIntoSmartLBlobWritingContext

- ea: `0x180017af0`
- end: `0x180017eb5`
- name: `RtlWriteDataIntoSmartLBlobWritingContext`
- size: `965`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180017750`
- `0x1800180e0`
- `0x180059650`
- `0x180063ca0`
- `0x180068f1c`

## callees

- `0x180005258`
- `0x18000bd10`
- `0x180017220`
- `0x180017af0`
- `0x18001f1d8`
- `0x18001f840`
- `0x1800289b0`
- `0x18002d2b0`
- `0x18006452c`
- `0x18009e020`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180017e6d`
- `ntdll!RtlRaiseStatus` at `0x180017e6d`

## string_xrefs

- `0x180017b3c`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x180017b88`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x180017bc6`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x180017c45`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x180017c86`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x180017ce1`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x180017d94`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x180017e44`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x180017c56`: `BUCL::Rtl::Add<SIZE_T>(DataLength, OldLength, TempSize)`

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
        RtlRaiseStatus(-1073741595);
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
0x180017af0  mov     [rsp-8+arg_10], rbx
0x180017af5  push    rbp
0x180017af6  push    rsi
0x180017af7  push    rdi
0x180017af8  push    r14
0x180017afa  push    r15
0x180017afc  lea     rbp, [rsp-37h]
0x180017b01  sub     rsp, 0E0h
0x180017b08  mov     rax, cs:__security_cookie
0x180017b0f  xor     rax, rsp
0x180017b12  mov     [rbp+57h+var_30], rax
0x180017b16  mov     [rbp+57h+var_40], 0
0x180017b1d  mov     rbx, rdx
0x180017b20  mov     r15, rcx
0x180017b23  test    rcx, rcx
0x180017b26  jnz     short loc_180017B66
0x180017b28  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180017b2f  mov     [rbp+57h+var_D0], 6EEh
0x180017b37  mov     qword ptr [rsp+100h+var_E0], rax
0x180017b3c  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x180017b43  mov     qword ptr [rsp+100h+var_E0+8], rax
0x180017b48  lea     rax, aNotNullCheckFa_15; "Not-null check failed: Data"
0x180017b4f  lea     rdx, [rsp+100h+var_E0]
0x180017b54  mov     [rbp+57h+var_C8], rax
0x180017b58  lea     rcx, [rbp+57h+var_40]
0x180017b5c  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180017b61  jmp     loc_180017E91
0x180017b66  call    RtlIsLBlobValid
0x180017b6b  test    al, al
0x180017b6d  jnz     short loc_180017BAD
0x180017b6f  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180017b76  mov     [rbp+57h+var_D0], 6EFh
0x180017b7e  mov     qword ptr [rsp+100h+var_E0], rax
0x180017b83  lea     rdx, [rsp+100h+var_E0]
0x180017b88  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x180017b8f  mov     qword ptr [rsp+100h+var_E0+8], rax
0x180017b94  lea     rcx, [rbp+57h+var_40]
0x180017b98  lea     rax, aRtlislblobvali_2; "::RtlIsLBlobValid(Data)"
0x180017b9f  mov     [rbp+57h+var_C8], rax
0x180017ba3  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180017ba8  jmp     loc_180017E91
0x180017bad  test    rbx, rbx
0x180017bb0  jnz     short loc_180017BDE
0x180017bb2  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180017bb9  mov     [rbp+57h+var_D0], 6F0h
0x180017bc1  mov     qword ptr [rsp+100h+var_E0], rax
0x180017bc6  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x180017bcd  mov     qword ptr [rsp+100h+var_E0+8], rax
0x180017bd2  lea     rax, aNotNullCheckFa_7; "Not-null check failed: Context"
0x180017bd9  jmp     loc_180017B4F
0x180017bde  mov     rsi, [rbx+8]
0x180017be2  mov     rdi, [rbx]
0x180017be5  mov     rax, rsi
0x180017be8  mov     r14, [r15]
0x180017beb  sub     rax, rdi
0x180017bee  cmp     r14, rax
0x180017bf1  jbe     loc_180017E0F
0x180017bf7  cmp     qword ptr [rbx+30h], 0
0x180017bfc  jnz     short loc_180017C08
0x180017bfe  mov     eax, 0C0000023h
0x180017c03  jmp     loc_180017E91
0x180017c08  xor     eax, eax
0x180017c0a  xorps   xmm0, xmm0
0x180017c0d  mov     [rbp+57h+var_D0], rax
0x180017c11  mov     rax, [rbx+20h]
0x180017c15  movups  [rsp+100h+var_E0], xmm0
0x180017c1a  mov     rcx, [rax]; unsigned __int64
0x180017c1d  mov     [rbp+57h+var_38], 0
0x180017c25  lea     rdi, [rcx+r14]
0x180017c29  cmp     rdi, r14
0x180017c2c  jnb     short loc_180017C66
0x180017c2e  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180017c35  mov     [rbp+57h+var_90], 702h
0x180017c3d  mov     [rbp+57h+var_A0], rax
0x180017c41  lea     rdx, [rbp+57h+var_A0]
0x180017c45  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x180017c4c  mov     r8d, 0C0000095h
0x180017c52  mov     [rbp+57h+var_98], rax
0x180017c56  lea     rax, aBuclRtlAddSize_0; "BUCL::Rtl::Add<SIZE_T>(DataLength, OldL"...
0x180017c5d  mov     [rbp+57h+var_88], rax
0x180017c61  jmp     loc_180017DAD
0x180017c66  mov     r8, [rbx+18h]; unsigned __int64
0x180017c6a  cmp     rdi, r8
0x180017c6d  jbe     short loc_180017CA4
0x180017c6f  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180017c76  mov     [rbp+57h+var_70], 705h
0x180017c7e  mov     [rbp+57h+var_80], rax
0x180017c82  lea     rdx, [rbp+57h+var_80]
0x180017c86  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x180017c8d  mov     [rbp+57h+var_68], 0
0x180017c95  mov     [rbp+57h+var_78], rax
0x180017c99  mov     r8d, 0C000042Bh
0x180017c9f  jmp     loc_180017DAD
0x180017ca4  mov     rax, [rbx+40h]
0x180017ca8  mov     rdx, rdi; unsigned __int64
0x180017cab  test    rax, rax
0x180017cae  jnz     short loc_180017CFF
0x180017cb0  lea     r9, [rbp+57h+var_38]; unsigned __int64 *
0x180017cb4  call    ?RtlpSmartLBlobWritingContextResizePolicy@@YAJ_K00PEA_K@Z; RtlpSmartLBlobWritingContextResizePolicy(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180017cb9  test    eax, eax
0x180017cbb  js      loc_180017DB6
0x180017cc1  mov     rdx, [rbp+57h+var_38]
0x180017cc5  cmp     rdx, rdi
0x180017cc8  jnb     short loc_180017D0D
0x180017cca  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180017cd1  mov     [rbp+57h+var_50], 715h
0x180017cd9  mov     [rbp+57h+var_60], rax
0x180017cdd  lea     rdx, [rbp+57h+var_60]
0x180017ce1  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x180017ce8  mov     [rbp+57h+var_48], 0
0x180017cf0  mov     [rbp+57h+var_58], rax
0x180017cf4  mov     r8d, 0C0000023h
0x180017cfa  jmp     loc_180017DAD
0x180017cff  lea     r8, [rbp+57h+var_38]
0x180017d03  mov     rcx, rbx
0x180017d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d0b  jmp     short loc_180017CB9
0x180017d0d  mov     rcx, [rbx+30h]
0x180017d11  mov     rax, [rbx+20h]
0x180017d15  cmp     rax, rcx
0x180017d18  jnz     short loc_180017D38
0x180017d1a  cmp     [rax+8], rdx
0x180017d1e  jnb     loc_180017DEB
0x180017d24  mov     r8, rcx
0x180017d27  xor     ecx, ecx
0x180017d29  call    RtlReallocateLBlob
0x180017d2e  test    eax, eax
0x180017d30  jns     loc_180017DEB
0x180017d36  jmp     short loc_180017DB6
0x180017d38  cmp     rax, [rbx+28h]
0x180017d3c  jnz     loc_180017E68
0x180017d42  cmp     [rcx+8], rdx
0x180017d46  jnb     short loc_180017D5A
0x180017d48  mov     r8, rcx
0x180017d4b  xor     ecx, ecx
0x180017d4d  call    RtlReallocateLBlob
0x180017d52  test    eax, eax
0x180017d54  js      short loc_180017DB6
0x180017d56  mov     rcx, [rbx+30h]
0x180017d5a  mov     r8, [rbx+20h]
0x180017d5e  xor     r9d, r9d
0x180017d61  mov     rdx, [rcx+8]; DestinationSize
0x180017d65  mov     rcx, [rcx+10h]; Destination
0x180017d69  cmp     [r8], r9
0x180017d6c  mov     r8, [r8+10h]; Source
0x180017d70  setnz   r9b; SourceSize
0x180017d74  call    memcpy_s_0
0x180017d79  test    eax, eax
0x180017d7b  jz      short loc_180017DC9
0x180017d7d  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180017d84  mov     [rbp+57h+var_B0], 72Fh
0x180017d8c  mov     [rbp+57h+var_C0], rax
0x180017d90  lea     rdx, [rbp+57h+var_C0]
0x180017d94  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x180017d9b  mov     [rbp+57h+var_A8], 0
0x180017da3  mov     [rbp+57h+var_B8], rax
0x180017da7  mov     r8d, 0C007010Ah
0x180017dad  lea     rcx, [rbp+57h+var_40]
0x180017db1  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180017db6  lea     rcx, [rsp+100h+var_E0]
0x180017dbb  mov     ebx, eax
0x180017dbd  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180017dc2  mov     eax, ebx
0x180017dc4  jmp     loc_180017E91
0x180017dc9  mov     rax, [rbx+20h]
0x180017dcd  mov     rcx, [rbx+30h]
0x180017dd1  mov     rax, [rax]
0x180017dd4  mov     [rcx], rax
0x180017dd7  mov     rcx, [rbx+38h]
0x180017ddb  mov     rax, [rbx+30h]
0x180017ddf  mov     [rbx+20h], rax
0x180017de3  test    rcx, rcx
0x180017de6  jz      short loc_180017DEB
0x180017de8  mov     [rcx], rax
0x180017deb  mov     rdx, [rbx+20h]
0x180017def  lea     rcx, [rsp+100h+var_E0]
0x180017df4  mov     rdi, [rdx+10h]
0x180017df8  add     rdi, [rdx]
0x180017dfb  mov     [rbx], rdi
0x180017dfe  mov     rsi, [rdx+8]
0x180017e02  add     rsi, [rdx+10h]
0x180017e06  mov     [rbx+8], rsi
0x180017e0a  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180017e0f  test    r14, r14
0x180017e12  jz      short loc_180017E8F
0x180017e14  mov     r8, [r15+10h]; Source
0x180017e18  sub     rsi, rdi
0x180017e1b  mov     rdx, rsi; DestinationSize
0x180017e1e  mov     r9, r14; SourceSize
0x180017e21  mov     rcx, rdi; Destination
0x180017e24  call    memcpy_s_0
0x180017e29  test    eax, eax
0x180017e2b  jz      short loc_180017E7A
0x180017e2d  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180017e34  mov     [rbp+57h+var_B0], 74Fh
0x180017e3c  mov     [rbp+57h+var_C0], rax
0x180017e40  lea     rdx, [rbp+57h+var_C0]
0x180017e44  lea     rax, aRtlwritedatain_0; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x180017e4b  mov     [rbp+57h+var_A8], 0
0x180017e53  mov     r8d, 0C007010Ah
0x180017e59  mov     [rbp+57h+var_B8], rax
0x180017e5d  lea     rcx, [rbp+57h+var_40]
0x180017e61  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180017e66  jmp     short loc_180017E91
0x180017e68  mov     ecx, 0C00000E5h; Status
0x180017e6d  call    cs:__imp_RtlRaiseStatus
0x180017e74  nop     dword ptr [rax+rax+00h]
0x180017e79  int     3; Trap to Debugger
0x180017e7a  mov     rcx, [rbx+20h]
0x180017e7e  lea     rdx, [r14+rdi]
0x180017e82  mov     rax, rdx
0x180017e85  sub     rax, [rcx+10h]
0x180017e89  mov     [rcx], rax
0x180017e8c  mov     [rbx], rdx
0x180017e8f  xor     eax, eax
0x180017e91  mov     rcx, [rbp+57h+var_30]
0x180017e95  xor     rcx, rsp; StackCookie
0x180017e98  call    __security_check_cookie
0x180017e9d  mov     rbx, [rsp+100h+arg_10]
0x180017ea5  add     rsp, 0E0h
0x180017eac  pop     r15
0x180017eae  pop     r14
0x180017eb0  pop     rdi
0x180017eb1  pop     rsi
0x180017eb2  pop     rbp
0x180017eb3  retn
```
