# MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(ulong,_LUTF8_STRING const *,_LUTF8_STRING const *,bool,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *,unsigned __int64 *)

- ea: `0x18005622c`
- end: `0x1800564d9`
- name: `?GetElementsByTagNameCommon@CMicrodom@MicrodomImplementation@@AEAAJKPEBU_LUTF8_STRING@@0_N1PEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@PEA_K@Z`
- size: `685`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055c60`
- `0x18005622c`

## callees

- `0x1800100a0`
- `0x18001f554`
- `0x18001f5d4`
- `0x18001fd10`
- `0x1800293a0`
- `0x180053c54`
- `0x180053f74`
- `0x1800541f8`
- `0x180054880`
- `0x1800549d0`
- `0x18005622c`
- `0x180056e28`
- `0x18009a070`

## string_xrefs

- `0x18005635a`: `onecore\base\xml\udom_microdom.cpp`
- `0x18005647f`: `onecore\base\xml\udom_microdom.cpp`
- `0x180056371`: `MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon`
- `0x180056496`: `MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon`
- `0x180056380`: `TempElements.Allocate(NewCapacity)`

## pseudocode

```c
int __fastcall MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(
        __int64 a1,
        __int64 a2,
        struct _LUTF8_STRING *a3,
        struct _LUTF8_STRING *a4,
        char a5,
        char a6,
        __int64 a7,
        unsigned __int64 *a8)
{
  unsigned int v10; // esi
  int result; // eax
  unsigned __int64 v13; // rax
  int v14; // eax
  __int128 v15; // xmm1
  struct _MICRODOM_DOM_NODE_HEADER *v16; // r14
  __int64 v17; // rsi
  __int64 v18; // rdx
  int v19; // ebx
  bool v20[16]; // [rsp+40h] [rbp-91h] BYREF
  struct _MICRODOM_DOM_NODE_ELEMENT *v21[2]; // [rsp+50h] [rbp-81h] BYREF
  struct _MICRODOM_DOM_NODE_HEADER *v22; // [rsp+60h] [rbp-71h] BYREF
  struct _LUTF8_STRING *v23; // [rsp+68h] [rbp-69h]
  struct _LUTF8_STRING *v24; // [rsp+70h] [rbp-61h]
  _QWORD v25[4]; // [rsp+78h] [rbp-59h] BYREF
  _QWORD v26[4]; // [rsp+98h] [rbp-39h] BYREF
  int v27; // [rsp+B8h] [rbp-19h] BYREF

  v23 = a4;
  v24 = a3;
  v10 = a2;
  v27 = 0;
  if ( !a4 || !a7 || !a8 || *a8 > *(_QWORD *)(a7 + 8) )
    goto LABEL_29;
  v21[0] = 0;
  v22 = 0;
  v20[0] = 0;
  result = MicrodomImplementation::CMicrodom::FindObject<1,_MICRODOM_DOM_NODE_ELEMENT const *>(a1, a2, v21);
  if ( result < 0 )
    return result;
  if ( a6 )
  {
    if ( a5 )
      result = MicrodomImplementation::CMicrodom::CompareElementByTagNameNS(
                 (MicrodomImplementation::CMicrodom *)a1,
                 v21[0],
                 a3,
                 a4,
                 v20);
    else
      result = MicrodomImplementation::CMicrodom::CompareElementByTagName(
                 (MicrodomImplementation::CMicrodom *)a1,
                 v21[0],
                 a4,
                 v20);
    if ( result < 0 )
      return result;
    if ( v20[0] )
    {
      v13 = *a8;
      if ( *(_QWORD *)(a7 + 8) == *a8 )
      {
        v21[0] = 0;
        v21[1] = 0;
        if ( v13 + 10 < v13 )
        {
          v26[2] = 1826;
          v26[0] = "onecore\\base\\xml\\udom_microdom.cpp";
          v26[1] = "MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon";
          v26[3] = "::BUCL::Rtl::Add<SIZE_T>( *pcElements, 10, NewCapacity)";
          v14 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                  &v27,
                  v26,
                  3221225621LL);
          goto LABEL_28;
        }
        if ( !Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(
                v21,
                v13 + 10) )
        {
          v25[2] = 1828;
          v25[0] = "onecore\\base\\xml\\udom_microdom.cpp";
          v25[1] = "MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon";
          v25[3] = "TempElements.Allocate(NewCapacity)";
          v14 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
                  &v27,
                  v25);
LABEL_28:
          v19 = v14;
          Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(v21);
          return v19;
        }
        memmove(v21[0], *(const void **)a7, 16 * *a8);
        v15 = *(_OWORD *)v21;
        *(_OWORD *)v21 = *(_OWORD *)a7;
        *(_OWORD *)a7 = v15;
        Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(v21);
      }
      if ( *a8 < *(_QWORD *)(a7 + 8) )
      {
        *(_DWORD *)(*(_QWORD *)a7 + 16 * (*a8)++ + 8) = v10;
        goto LABEL_20;
      }
LABEL_29:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x1800564D8LL);
    }
  }
LABEL_20:
  result = MicrodomImplementation::CMicrodom::GetNodeChildren(a1, v10, &v22, 0);
  if ( result >= 0 )
  {
    v16 = v22;
    v17 = 0;
    if ( *((_QWORD *)v22 + 1) )
    {
      while ( 1 )
      {
        v18 = *(_QWORD *)v16;
        v22 = 0;
        result = MicrodomImplementation::CDomLayoutCache::FindObject(
                   (MicrodomImplementation::CDomLayoutCache *)(a1 + 48),
                   *(_DWORD *)(v18 + 16 * v17 + 8),
                   &v22);
        if ( result < 0 )
          break;
        if ( (*(_BYTE *)v22 & 0xF) == 1 )
        {
          result = MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(
                     a1,
                     *(_DWORD *)(*(_QWORD *)v16 + 16 * v17 + 8),
                     (_DWORD)v24,
                     (_DWORD)v23,
                     a5,
                     1,
                     a7,
                     (__int64)a8);
          if ( result < 0 )
            break;
        }
        if ( (unsigned __int64)++v17 >= *((_QWORD *)v16 + 1) )
          return 0;
      }
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005622c  push    rbp
0x18005622e  push    rbx
0x18005622f  push    rsi
0x180056230  push    rdi
0x180056231  push    r12
0x180056233  push    r13
0x180056235  push    r14
0x180056237  push    r15
0x180056239  lea     rbp, [rsp-7]
0x18005623e  sub     rsp, 0D8h
0x180056245  mov     rax, cs:__security_cookie
0x18005624c  xor     rax, rsp
0x18005624f  mov     [rbp+3Fh+var_50], rax
0x180056253  mov     rdi, [rbp+3Fh+arg_30]
0x180056257  xor     r13d, r13d
0x18005625a  mov     rbx, [rbp+3Fh+arg_38]
0x180056261  mov     r14, r9
0x180056264  mov     [rbp+3Fh+var_A8], r9
0x180056268  mov     r12, r8
0x18005626b  mov     [rbp+3Fh+var_A0], r8
0x18005626f  mov     esi, edx
0x180056271  mov     [rbp+3Fh+var_58], r13d
0x180056275  mov     r15, rcx
0x180056278  test    r9, r9
0x18005627b  jz      loc_1800564CE
0x180056281  test    rdi, rdi
0x180056284  jz      loc_1800564CE
0x18005628a  test    rbx, rbx
0x18005628d  jz      loc_1800564CE
0x180056293  mov     rax, [rdi+8]
0x180056297  cmp     [rbx], rax
0x18005629a  ja      loc_1800564CE
0x1800562a0  lea     r8, [rsp+110h+var_C0]
0x1800562a5  mov     [rsp+110h+var_C0], r13
0x1800562aa  mov     [rbp+3Fh+var_B0], r13
0x1800562ae  mov     [rsp+110h+var_D0], r13b
0x1800562b3  call    ??$FindObject@$00PEBU_MICRODOM_DOM_NODE_ELEMENT@@@CMicrodom@MicrodomImplementation@@AEAAJKAEAPEBU_MICRODOM_DOM_NODE_ELEMENT@@@Z; MicrodomImplementation::CMicrodom::FindObject<1,_MICRODOM_DOM_NODE_ELEMENT const *>(ulong,_MICRODOM_DOM_NODE_ELEMENT const * &)
0x1800562b8  test    eax, eax
0x1800562ba  js      short loc_1800562ED
0x1800562bc  cmp     [rbp+3Fh+arg_28], r13b
0x1800562c0  jz      loc_1800563DF
0x1800562c6  mov     rcx, r15; this
0x1800562c9  mov     rdx, [rsp+110h+var_C0]; struct _MICRODOM_DOM_NODE_ELEMENT *
0x1800562ce  cmp     [rbp+3Fh+arg_20], r13b
0x1800562d2  jz      short loc_18005630E
0x1800562d4  lea     rax, [rsp+110h+var_D0]
0x1800562d9  mov     r9, r14; struct _LUTF8_STRING *
0x1800562dc  mov     r8, r12; struct _LUTF8_STRING *
0x1800562df  mov     [rsp+110h+var_F0], rax; bool *
0x1800562e4  call    ?CompareElementByTagNameNS@CMicrodom@MicrodomImplementation@@AEAAJPEBU_MICRODOM_DOM_NODE_ELEMENT@@PEBU_LUTF8_STRING@@1PEA_N@Z; MicrodomImplementation::CMicrodom::CompareElementByTagNameNS(_MICRODOM_DOM_NODE_ELEMENT const *,_LUTF8_STRING const *,_LUTF8_STRING const *,bool *)
0x1800562e9  test    eax, eax
0x1800562eb  jns     short loc_18005631D
0x1800562ed  mov     rcx, [rbp+3Fh+var_50]
0x1800562f1  xor     rcx, rsp; StackCookie
0x1800562f4  call    __security_check_cookie
0x1800562f9  add     rsp, 0D8h
0x180056300  pop     r15
0x180056302  pop     r14
0x180056304  pop     r13
0x180056306  pop     r12
0x180056308  pop     rdi
0x180056309  pop     rsi
0x18005630a  pop     rbx
0x18005630b  pop     rbp
0x18005630c  retn
0x18005630e  lea     r9, [rsp+110h+var_D0]; bool *
0x180056313  mov     r8, r14; struct _LUTF8_STRING *
0x180056316  call    ?CompareElementByTagName@CMicrodom@MicrodomImplementation@@AEAAJPEBU_MICRODOM_DOM_NODE_ELEMENT@@PEBU_LUTF8_STRING@@PEA_N@Z; MicrodomImplementation::CMicrodom::CompareElementByTagName(_MICRODOM_DOM_NODE_ELEMENT const *,_LUTF8_STRING const *,bool *)
0x18005631b  jmp     short loc_1800562E9
0x18005631d  cmp     [rsp+110h+var_D0], r13b
0x180056322  jz      loc_1800563DF
0x180056328  mov     rax, [rbx]
0x18005632b  cmp     [rdi+8], rax
0x18005632f  jnz     loc_1800563C5
0x180056335  lea     rdx, [rax+0Ah]
0x180056339  mov     [rsp+110h+var_C0], r13
0x18005633e  mov     [rbp+3Fh+var_C0+8], r13
0x180056342  cmp     rdx, rax
0x180056345  jb      loc_18005647F
0x18005634b  lea     rcx, [rsp+110h+var_C0]
0x180056350  call    ?Allocate@?$AutoVectorBase@V?$MicrodomVectorTraits@UElement@Rtl@Microdom@Windows@@@Microdom@Windows@@V?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@3@@Windows@@QEAAPEAUElement@Rtl@Microdom@2@_K@Z; Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(unsigned __int64)
0x180056355  test    rax, rax
0x180056358  jnz     short loc_180056395
0x18005635a  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180056361  mov     [rbp+3Fh+var_88], 724h
0x180056369  mov     [rbp+3Fh+var_98], rax
0x18005636d  lea     rdx, [rbp+3Fh+var_98]
0x180056371  lea     rax, aMicrodomimplem_14; "MicrodomImplementation::CMicrodom::GetE"...
0x180056378  mov     [rbp+3Fh+var_90], rax
0x18005637c  lea     rcx, [rbp+3Fh+var_58]
0x180056380  lea     rax, aTempelementsAl; "TempElements.Allocate(NewCapacity)"
0x180056387  mov     [rbp+3Fh+var_80], rax
0x18005638b  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180056390  jmp     loc_1800564BB
0x180056395  mov     r8, [rbx]
0x180056398  mov     rdx, [rdi]; Src
0x18005639b  mov     rcx, [rsp+110h+var_C0]; void *
0x1800563a0  shl     r8, 4; Size
0x1800563a4  call    memmove
0x1800563a9  movups  xmm0, xmmword ptr [rdi]
0x1800563ac  lea     rcx, [rsp+110h+var_C0]
0x1800563b1  movaps  xmm1, xmmword ptr [rsp+110h+var_C0]
0x1800563b6  movdqu  xmmword ptr [rsp+110h+var_C0], xmm0
0x1800563bc  movdqu  xmmword ptr [rdi], xmm1
0x1800563c0  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x1800563c5  mov     rcx, [rbx]
0x1800563c8  cmp     rcx, [rdi+8]
0x1800563cc  jnb     loc_1800564CE
0x1800563d2  mov     rax, [rdi]
0x1800563d5  add     rcx, rcx
0x1800563d8  mov     [rax+rcx*8+8], esi
0x1800563dc  inc     qword ptr [rbx]
0x1800563df  xor     r9d, r9d
0x1800563e2  lea     r8, [rbp+3Fh+var_B0]
0x1800563e6  mov     edx, esi
0x1800563e8  mov     rcx, r15
0x1800563eb  call    ?GetNodeChildren@CMicrodom@MicrodomImplementation@@QEAAJKPEAPEAU?$Vector@$$CBUNode@Rtl@Microdom@Windows@@@Windows@@0@Z; MicrodomImplementation::CMicrodom::GetNodeChildren(ulong,Windows::Vector<Windows::Microdom::Rtl::Node const> * *,Windows::Vector<Windows::Microdom::Rtl::Node const> * *)
0x1800563f0  test    eax, eax
0x1800563f2  js      loc_1800562ED
0x1800563f8  mov     r14, [rbp+3Fh+var_B0]
0x1800563fc  mov     rsi, r13
0x1800563ff  cmp     [r14+8], r13
0x180056403  jbe     short loc_180056478
0x180056405  mov     rdx, [r14]
0x180056408  lea     r8, [rbp+3Fh+var_B0]; struct _MICRODOM_DOM_NODE_HEADER **
0x18005640c  mov     r12, rsi
0x18005640f  mov     [rbp+3Fh+var_B0], r13
0x180056413  add     r12, r12
0x180056416  lea     rcx, [r15+30h]; this
0x18005641a  mov     edx, [rdx+r12*8+8]; unsigned int
0x18005641f  call    ?FindObject@CDomLayoutCache@MicrodomImplementation@@QEAAJKAEAPEBU_MICRODOM_DOM_NODE_HEADER@@@Z; MicrodomImplementation::CDomLayoutCache::FindObject(ulong,_MICRODOM_DOM_NODE_HEADER const * &)
0x180056424  test    eax, eax
0x180056426  js      loc_1800562ED
0x18005642c  mov     rax, [rbp+3Fh+var_B0]
0x180056430  mov     cl, [rax]
0x180056432  and     cl, 0Fh
0x180056435  cmp     cl, 1
0x180056438  jnz     short loc_18005646F
0x18005643a  mov     rdx, [r14]
0x18005643d  mov     al, [rbp+3Fh+arg_20]
0x180056440  mov     r9, [rbp+3Fh+var_A8]
0x180056444  mov     r8, [rbp+3Fh+var_A0]
0x180056448  mov     edx, [rdx+r12*8+8]
0x18005644d  mov     [rsp+110h+var_D8], rbx
0x180056452  mov     [rsp+110h+var_E0], rdi
0x180056457  mov     [rsp+110h+var_E8], cl
0x18005645b  mov     rcx, r15
0x18005645e  mov     byte ptr [rsp+110h+var_F0], al
0x180056462  call    ?GetElementsByTagNameCommon@CMicrodom@MicrodomImplementation@@AEAAJKPEBU_LUTF8_STRING@@0_N1PEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@PEA_K@Z; MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(ulong,_LUTF8_STRING const *,_LUTF8_STRING const *,bool,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *,unsigned __int64 *)
0x180056467  test    eax, eax
0x180056469  js      loc_1800562ED
0x18005646f  inc     rsi
0x180056472  cmp     rsi, [r14+8]
0x180056476  jb      short loc_180056405
0x180056478  xor     eax, eax
0x18005647a  jmp     loc_1800562ED
0x18005647f  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180056486  mov     [rbp+3Fh+var_68], 722h
0x18005648e  mov     [rbp+3Fh+var_78], rax
0x180056492  lea     rdx, [rbp+3Fh+var_78]
0x180056496  lea     rax, aMicrodomimplem_14; "MicrodomImplementation::CMicrodom::GetE"...
0x18005649d  mov     r8d, 0C0000095h
0x1800564a3  mov     [rbp+3Fh+var_70], rax
0x1800564a7  lea     rcx, [rbp+3Fh+var_58]
0x1800564ab  lea     rax, aBuclRtlAddSize_3; "::BUCL::Rtl::Add<SIZE_T>( *pcElements, "...
0x1800564b2  mov     [rbp+3Fh+var_60], rax
0x1800564b6  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800564bb  lea     rcx, [rsp+110h+var_C0]
0x1800564c0  mov     ebx, eax
0x1800564c2  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x1800564c7  mov     eax, ebx
0x1800564c9  jmp     loc_1800562ED
0x1800564ce  mov     ecx, 0C00000E5h; int
0x1800564d3  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
