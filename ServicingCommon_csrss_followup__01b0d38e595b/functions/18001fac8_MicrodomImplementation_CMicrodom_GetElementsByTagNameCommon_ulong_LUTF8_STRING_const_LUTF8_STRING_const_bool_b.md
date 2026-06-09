# MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(ulong,_LUTF8_STRING const *,_LUTF8_STRING const *,bool,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *,unsigned __int64 *)

- ea: `0x18001fac8`
- end: `0x18001fd88`
- name: `?GetElementsByTagNameCommon@CMicrodom@MicrodomImplementation@@AEAAJKPEBU_LUTF8_STRING@@0_N1PEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@PEA_K@Z`
- size: `704`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001fac8`
- `0x180057e50`

## callees

- `0x180006980`
- `0x18001e820`
- `0x18001f840`
- `0x18001fac8`
- `0x1800217cc`
- `0x18002d2b0`
- `0x180056194`
- `0x180056658`
- `0x180056cc0`
- `0x180056e18`
- `0x18005863c`
- `0x1800981e0`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18001fd7b`
- `ntdll!RtlRaiseStatus` at `0x18001fd7b`

## string_xrefs

- `0x18001fc01`: `onecore\base\xml\udom_microdom.cpp`
- `0x18001fd20`: `onecore\base\xml\udom_microdom.cpp`
- `0x18001fc18`: `MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon`
- `0x18001fd37`: `MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon`
- `0x18001fc27`: `TempElements.Allocate(NewCapacity)`

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
  unsigned __int64 i; // rsi
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
    goto LABEL_30;
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
LABEL_30:
      RtlRaiseStatus(-1073741595);
    }
  }
LABEL_20:
  result = MicrodomImplementation::CMicrodom::GetNodeChildren(a1, v10, &v22, 0);
  if ( result >= 0 )
  {
    v16 = v22;
    for ( i = 0; i < *((_QWORD *)v16 + 1); ++i )
    {
      v18 = *(_QWORD *)v16;
      v22 = 0;
      result = MicrodomImplementation::CDomLayoutCache::FindObject(
                 (MicrodomImplementation::CDomLayoutCache *)(a1 + 48),
                 *(_DWORD *)(v18 + 16 * i + 8),
                 &v22);
      if ( result < 0 )
        return result;
      if ( (*(_BYTE *)v22 & 0xF) == 1 )
      {
        result = MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(
                   a1,
                   *(_DWORD *)(*(_QWORD *)v16 + 16 * i + 8),
                   (_DWORD)v24,
                   (_DWORD)v23,
                   a5,
                   1,
                   a7,
                   (__int64)a8);
        if ( result < 0 )
          return result;
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001fac8  push    rbp
0x18001faca  push    rbx
0x18001facb  push    rsi
0x18001facc  push    rdi
0x18001facd  push    r12
0x18001facf  push    r13
0x18001fad1  push    r14
0x18001fad3  push    r15
0x18001fad5  lea     rbp, [rsp-7]
0x18001fada  sub     rsp, 0D8h
0x18001fae1  mov     rax, cs:__security_cookie
0x18001fae8  xor     rax, rsp
0x18001faeb  mov     [rbp+3Fh+var_50], rax
0x18001faef  mov     rdi, [rbp+3Fh+arg_30]
0x18001faf3  xor     r12d, r12d
0x18001faf6  mov     rbx, [rbp+3Fh+arg_38]
0x18001fafd  mov     r14, r9
0x18001fb00  mov     [rbp+3Fh+var_A8], r9
0x18001fb04  mov     r15, r8
0x18001fb07  mov     [rbp+3Fh+var_A0], r8
0x18001fb0b  mov     esi, edx
0x18001fb0d  mov     [rbp+3Fh+var_58], r12d
0x18001fb11  mov     r13, rcx
0x18001fb14  test    r9, r9
0x18001fb17  jz      loc_18001FD76
0x18001fb1d  test    rdi, rdi
0x18001fb20  jz      loc_18001FD76
0x18001fb26  test    rbx, rbx
0x18001fb29  jz      loc_18001FD76
0x18001fb2f  mov     rax, [rdi+8]
0x18001fb33  cmp     [rbx], rax
0x18001fb36  ja      loc_18001FD76
0x18001fb3c  lea     r8, [rsp+110h+var_C0]
0x18001fb41  mov     [rsp+110h+var_C0], r12
0x18001fb46  mov     [rbp+3Fh+var_B0], r12
0x18001fb4a  mov     [rsp+110h+var_D0], r12b
0x18001fb4f  call    ??$FindObject@$00PEBU_MICRODOM_DOM_NODE_ELEMENT@@@CMicrodom@MicrodomImplementation@@AEAAJKAEAPEBU_MICRODOM_DOM_NODE_ELEMENT@@@Z; MicrodomImplementation::CMicrodom::FindObject<1,_MICRODOM_DOM_NODE_ELEMENT const *>(ulong,_MICRODOM_DOM_NODE_ELEMENT const * &)
0x18001fb54  test    eax, eax
0x18001fb56  js      short loc_18001FB8C
0x18001fb58  cmp     [rbp+3Fh+arg_28], 0
0x18001fb5c  mov     r12b, [rbp+3Fh+arg_20]
0x18001fb60  jz      loc_18001FC86
0x18001fb66  mov     rdx, [rsp+110h+var_C0]; struct _MICRODOM_DOM_NODE_ELEMENT *
0x18001fb6b  mov     rcx, r13; this
0x18001fb6e  test    r12b, r12b
0x18001fb71  jz      short loc_18001FBAD
0x18001fb73  lea     rax, [rsp+110h+var_D0]
0x18001fb78  mov     r9, r14; struct _LUTF8_STRING *
0x18001fb7b  mov     r8, r15; struct _LUTF8_STRING *
0x18001fb7e  mov     [rsp+110h+var_F0], rax; bool *
0x18001fb83  call    ?CompareElementByTagNameNS@CMicrodom@MicrodomImplementation@@AEAAJPEBU_MICRODOM_DOM_NODE_ELEMENT@@PEBU_LUTF8_STRING@@1PEA_N@Z; MicrodomImplementation::CMicrodom::CompareElementByTagNameNS(_MICRODOM_DOM_NODE_ELEMENT const *,_LUTF8_STRING const *,_LUTF8_STRING const *,bool *)
0x18001fb88  test    eax, eax
0x18001fb8a  jns     short loc_18001FBBC
0x18001fb8c  mov     rcx, [rbp+3Fh+var_50]
0x18001fb90  xor     rcx, rsp; StackCookie
0x18001fb93  call    __security_check_cookie
0x18001fb98  add     rsp, 0D8h
0x18001fb9f  pop     r15
0x18001fba1  pop     r14
0x18001fba3  pop     r13
0x18001fba5  pop     r12
0x18001fba7  pop     rdi
0x18001fba8  pop     rsi
0x18001fba9  pop     rbx
0x18001fbaa  pop     rbp
0x18001fbab  retn
0x18001fbad  lea     r9, [rsp+110h+var_D0]; bool *
0x18001fbb2  mov     r8, r14; struct _LUTF8_STRING *
0x18001fbb5  call    ?CompareElementByTagName@CMicrodom@MicrodomImplementation@@AEAAJPEBU_MICRODOM_DOM_NODE_ELEMENT@@PEBU_LUTF8_STRING@@PEA_N@Z; MicrodomImplementation::CMicrodom::CompareElementByTagName(_MICRODOM_DOM_NODE_ELEMENT const *,_LUTF8_STRING const *,bool *)
0x18001fbba  jmp     short loc_18001FB88
0x18001fbbc  cmp     [rsp+110h+var_D0], 0
0x18001fbc1  jz      loc_18001FC86
0x18001fbc7  mov     rax, [rbx]
0x18001fbca  cmp     [rdi+8], rax
0x18001fbce  jnz     loc_18001FC6C
0x18001fbd4  lea     rdx, [rax+0Ah]
0x18001fbd8  mov     [rsp+110h+var_C0], 0
0x18001fbe1  mov     [rbp+3Fh+var_C0+8], 0
0x18001fbe9  cmp     rdx, rax
0x18001fbec  jb      loc_18001FD20
0x18001fbf2  lea     rcx, [rsp+110h+var_C0]
0x18001fbf7  call    ?Allocate@?$AutoVectorBase@V?$MicrodomVectorTraits@UElement@Rtl@Microdom@Windows@@@Microdom@Windows@@V?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@3@@Windows@@QEAAPEAUElement@Rtl@Microdom@2@_K@Z; Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(unsigned __int64)
0x18001fbfc  test    rax, rax
0x18001fbff  jnz     short loc_18001FC3C
0x18001fc01  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18001fc08  mov     [rbp+3Fh+var_88], 724h
0x18001fc10  mov     [rbp+3Fh+var_98], rax
0x18001fc14  lea     rdx, [rbp+3Fh+var_98]
0x18001fc18  lea     rax, aMicrodomimplem_14; "MicrodomImplementation::CMicrodom::GetE"...
0x18001fc1f  mov     [rbp+3Fh+var_90], rax
0x18001fc23  lea     rcx, [rbp+3Fh+var_58]
0x18001fc27  lea     rax, aTempelementsAl; "TempElements.Allocate(NewCapacity)"
0x18001fc2e  mov     [rbp+3Fh+var_80], rax
0x18001fc32  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001fc37  jmp     loc_18001FD5C
0x18001fc3c  mov     r8, [rbx]
0x18001fc3f  mov     rdx, [rdi]; Src
0x18001fc42  mov     rcx, [rsp+110h+var_C0]; void *
0x18001fc47  shl     r8, 4; Size
0x18001fc4b  call    memmove
0x18001fc50  movups  xmm0, xmmword ptr [rdi]
0x18001fc53  lea     rcx, [rsp+110h+var_C0]
0x18001fc58  movaps  xmm1, xmmword ptr [rsp+110h+var_C0]
0x18001fc5d  movdqu  xmmword ptr [rsp+110h+var_C0], xmm0
0x18001fc63  movdqu  xmmword ptr [rdi], xmm1
0x18001fc67  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18001fc6c  mov     rcx, [rbx]
0x18001fc6f  cmp     rcx, [rdi+8]
0x18001fc73  jnb     loc_18001FD76
0x18001fc79  mov     rax, [rdi]
0x18001fc7c  add     rcx, rcx
0x18001fc7f  mov     [rax+rcx*8+8], esi
0x18001fc83  inc     qword ptr [rbx]
0x18001fc86  xor     r9d, r9d
0x18001fc89  lea     r8, [rbp+3Fh+var_B0]
0x18001fc8d  mov     edx, esi
0x18001fc8f  mov     rcx, r13
0x18001fc92  call    ?GetNodeChildren@CMicrodom@MicrodomImplementation@@QEAAJKPEAPEAU?$Vector@$$CBUNode@Rtl@Microdom@Windows@@@Windows@@0@Z; MicrodomImplementation::CMicrodom::GetNodeChildren(ulong,Windows::Vector<Windows::Microdom::Rtl::Node const> * *,Windows::Vector<Windows::Microdom::Rtl::Node const> * *)
0x18001fc97  test    eax, eax
0x18001fc99  js      loc_18001FB8C
0x18001fc9f  mov     r14, [rbp+3Fh+var_B0]
0x18001fca3  xor     esi, esi
0x18001fca5  cmp     rsi, [r14+8]
0x18001fca9  jnb     loc_18001FD6F
0x18001fcaf  mov     rdx, [r14]
0x18001fcb2  lea     rcx, [r13+30h]; this
0x18001fcb6  mov     r15, rsi
0x18001fcb9  mov     [rbp+3Fh+var_B0], 0
0x18001fcc1  add     r15, r15
0x18001fcc4  lea     r8, [rbp+3Fh+var_B0]; struct _MICRODOM_DOM_NODE_HEADER **
0x18001fcc8  mov     edx, [rdx+r15*8+8]; unsigned int
0x18001fccd  call    ?FindObject@CDomLayoutCache@MicrodomImplementation@@QEAAJKAEAPEBU_MICRODOM_DOM_NODE_HEADER@@@Z; MicrodomImplementation::CDomLayoutCache::FindObject(ulong,_MICRODOM_DOM_NODE_HEADER const * &)
0x18001fcd2  test    eax, eax
0x18001fcd4  js      loc_18001FB8C
0x18001fcda  mov     rax, [rbp+3Fh+var_B0]
0x18001fcde  mov     cl, [rax]
0x18001fce0  and     cl, 0Fh
0x18001fce3  cmp     cl, 1
0x18001fce6  jnz     short loc_18001FD1B
0x18001fce8  mov     rdx, [r14]
0x18001fceb  mov     r9, [rbp+3Fh+var_A8]
0x18001fcef  mov     r8, [rbp+3Fh+var_A0]
0x18001fcf3  mov     [rsp+110h+var_D8], rbx
0x18001fcf8  mov     edx, [rdx+r15*8+8]
0x18001fcfd  mov     [rsp+110h+var_E0], rdi
0x18001fd02  mov     [rsp+110h+var_E8], cl
0x18001fd06  mov     rcx, r13
0x18001fd09  mov     byte ptr [rsp+110h+var_F0], r12b
0x18001fd0e  call    ?GetElementsByTagNameCommon@CMicrodom@MicrodomImplementation@@AEAAJKPEBU_LUTF8_STRING@@0_N1PEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@PEA_K@Z; MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(ulong,_LUTF8_STRING const *,_LUTF8_STRING const *,bool,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *,unsigned __int64 *)
0x18001fd13  test    eax, eax
0x18001fd15  js      loc_18001FB8C
0x18001fd1b  inc     rsi
0x18001fd1e  jmp     short loc_18001FCA5
0x18001fd20  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18001fd27  mov     [rbp+3Fh+var_68], 722h
0x18001fd2f  mov     [rbp+3Fh+var_78], rax
0x18001fd33  lea     rdx, [rbp+3Fh+var_78]
0x18001fd37  lea     rax, aMicrodomimplem_14; "MicrodomImplementation::CMicrodom::GetE"...
0x18001fd3e  mov     r8d, 0C0000095h
0x18001fd44  mov     [rbp+3Fh+var_70], rax
0x18001fd48  lea     rcx, [rbp+3Fh+var_58]
0x18001fd4c  lea     rax, aBuclRtlAddSize_3; "::BUCL::Rtl::Add<SIZE_T>( *pcElements, "...
0x18001fd53  mov     [rbp+3Fh+var_60], rax
0x18001fd57  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18001fd5c  lea     rcx, [rsp+110h+var_C0]
0x18001fd61  mov     ebx, eax
0x18001fd63  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x18001fd68  mov     eax, ebx
0x18001fd6a  jmp     loc_18001FB8C
0x18001fd6f  xor     eax, eax
0x18001fd71  jmp     loc_18001FB8C
0x18001fd76  mov     ecx, 0C00000E5h; Status
0x18001fd7b  call    cs:__imp_RtlRaiseStatus
0x18001fd82  nop     dword ptr [rax+rax+00h]
0x18001fd87  int     3; Trap to Debugger
```
