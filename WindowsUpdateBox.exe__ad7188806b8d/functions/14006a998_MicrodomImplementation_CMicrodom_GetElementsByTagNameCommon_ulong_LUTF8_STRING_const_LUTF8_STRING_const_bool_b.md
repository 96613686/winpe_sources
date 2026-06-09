# MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(ulong,_LUTF8_STRING const *,_LUTF8_STRING const *,bool,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *,unsigned __int64 *)

- ea: `0x14006a998`
- end: `0x14006aca0`
- name: `?GetElementsByTagNameCommon@CMicrodom@MicrodomImplementation@@AEAAJKPEBU_LUTF8_STRING@@0_N1PEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@PEA_K@Z`
- size: `776`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14006a280`
- `0x14006a998`

## callees

- `0x140002326`
- `0x1400674ac`
- `0x140067d00`
- `0x140067e60`
- `0x1400691f8`
- `0x14006a998`
- `0x14006b728`
- `0x140072764`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14006ab2a`
- `ntdll!RtlFreeHeap` at `0x14006ab88`
- `ntdll!RtlFreeHeap` at `0x14006ab2a`
- `ntdll!RtlFreeHeap` at `0x14006ab88`
- `ntdll!RtlRaiseStatus` at `0x14006ac93`
- `ntdll!RtlRaiseStatus` at `0x14006ac93`

## string_xrefs

- `0x14006aa1f`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006aada`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006ac4c`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006aaf1`: `MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon`
- `0x14006ac63`: `MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon`
- `0x14006ab02`: `TempElements.Allocate(NewCapacity)`

## pseudocode

```c
int __fastcall MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(
        __int64 a1,
        unsigned int a2,
        struct _LUTF8_STRING *a3,
        const struct _LUTF8_STRING *a4,
        char a5,
        char a6,
        __int64 a7,
        unsigned __int64 *a8)
{
  __int64 v8; // r15
  int result; // eax
  PVOID v14; // rdx
  unsigned __int64 v15; // rax
  __int64 v16; // rdx
  void *v17; // r8
  struct _MICRODOM_DOM_NODE_HEADER *v18; // r14
  __int64 i; // rsi
  __int64 v20; // rdx
  bool v21; // [rsp+40h] [rbp-61h] BYREF
  struct _MICRODOM_DOM_NODE_HEADER *v22; // [rsp+48h] [rbp-59h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-51h] BYREF
  __int64 v24; // [rsp+60h] [rbp-41h]
  const char *v25; // [rsp+68h] [rbp-39h]
  const char *v26; // [rsp+70h] [rbp-31h] BYREF
  const char *v27; // [rsp+78h] [rbp-29h]
  __int64 v28; // [rsp+80h] [rbp-21h]
  const char *v29; // [rsp+88h] [rbp-19h]
  struct _LUTF8_STRING *v30; // [rsp+90h] [rbp-11h]

  v8 = 0;
  v30 = a3;
  if ( !a4 || !a7 || !a8 || *a8 > *(_QWORD *)(a7 + 8) )
    goto LABEL_34;
  v22 = 0;
  v21 = 0;
  P[0] = 0;
  result = MicrodomImplementation::CDomLayoutCache::FindObject(
             (MicrodomImplementation::CDomLayoutCache *)(a1 + 48),
             a2,
             (const struct _MICRODOM_DOM_NODE_HEADER **)P);
  if ( result < 0 )
    return result;
  v14 = P[0];
  if ( (*(_BYTE *)P[0] & 0xF) != 1 )
  {
    v24 = 2371;
    P[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    P[1] = "MicrodomImplementation::CMicrodom::FindObject";
    v25 = "ObjectHeader->uElementType == ucObjectType";
    RtlReportErrorOrigination(P, v14, 3221225508LL);
    return -1073741788;
  }
  if ( a6 )
  {
    if ( a5 )
      result = MicrodomImplementation::CMicrodom::CompareElementByTagNameNS(
                 (MicrodomImplementation::CMicrodom *)a1,
                 (const struct _MICRODOM_DOM_NODE_ELEMENT *)P[0],
                 a3,
                 a4,
                 &v21);
    else
      result = MicrodomImplementation::CMicrodom::CompareElementByTagName(
                 (MicrodomImplementation::CMicrodom *)a1,
                 (const struct _MICRODOM_DOM_NODE_ELEMENT *)P[0],
                 a4,
                 &v21);
    if ( result < 0 )
      return result;
    if ( v21 )
    {
      v15 = *a8;
      if ( *(_QWORD *)(a7 + 8) == *a8 )
      {
        P[0] = 0;
        P[1] = 0;
        if ( v15 + 10 < v15 )
        {
          v28 = 1826;
          v26 = "onecore\\base\\xml\\udom_microdom.cpp";
          v27 = "MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon";
          v29 = "::BUCL::Rtl::Add<SIZE_T>( *pcElements, 10, NewCapacity)";
          RtlReportErrorOrigination(&v26, v15 + 10, 3221225621LL);
          return -1073741675;
        }
        if ( !Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(P) )
        {
          v28 = 1828;
          v26 = "onecore\\base\\xml\\udom_microdom.cpp";
          v27 = "MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon";
          v29 = "TempElements.Allocate(NewCapacity)";
          RtlReportErrorOrigination(&v26, v16, 3221225495LL);
          if ( P[0] )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
          return -1073741801;
        }
        memcpy_0(P[0], *(const void **)a7, 16 * *a8);
        v17 = *(void **)a7;
        *(_OWORD *)a7 = *(_OWORD *)P;
        if ( v17 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
      }
      if ( *a8 < *(_QWORD *)(a7 + 8) )
      {
        *(_DWORD *)(*(_QWORD *)a7 + 16 * (*a8)++ + 8) = a2;
        goto LABEL_25;
      }
LABEL_34:
      RtlRaiseStatus(-1073741595);
    }
  }
LABEL_25:
  result = MicrodomImplementation::CMicrodom::GetNodeChildren(a1, a2, &v22, 0);
  if ( result >= 0 )
  {
    v18 = v22;
    if ( *((_QWORD *)v22 + 1) )
    {
      for ( i = 0; ; i += 16 )
      {
        v20 = *(_QWORD *)v18;
        v22 = 0;
        result = MicrodomImplementation::CDomLayoutCache::FindObject(
                   (MicrodomImplementation::CDomLayoutCache *)(a1 + 48),
                   *(_DWORD *)(i + v20 + 8),
                   &v22);
        if ( result < 0 )
          break;
        if ( (*(_BYTE *)v22 & 0xF) == 1 )
        {
          result = MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(
                     a1,
                     *(_DWORD *)(i + *(_QWORD *)v18 + 8),
                     (_DWORD)v30,
                     (_DWORD)a4,
                     a5,
                     1,
                     a7,
                     (__int64)a8);
          if ( result < 0 )
            break;
        }
        if ( (unsigned __int64)++v8 >= *((_QWORD *)v18 + 1) )
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
0x14006a998  push    rbp
0x14006a99a  push    rbx
0x14006a99b  push    rsi
0x14006a99c  push    rdi
0x14006a99d  push    r12
0x14006a99f  push    r13
0x14006a9a1  push    r14
0x14006a9a3  push    r15
0x14006a9a5  lea     rbp, [rsp-7]
0x14006a9aa  sub     rsp, 0A8h
0x14006a9b1  mov     rdi, [rbp+3Fh+arg_30]
0x14006a9b5  xor     r15d, r15d
0x14006a9b8  mov     rbx, [rbp+3Fh+arg_38]
0x14006a9bf  mov     r12, r9
0x14006a9c2  mov     [rbp+3Fh+var_50], r8
0x14006a9c6  mov     r14, r8
0x14006a9c9  mov     esi, edx
0x14006a9cb  mov     r13, rcx
0x14006a9ce  test    r9, r9
0x14006a9d1  jz      loc_14006AC8E
0x14006a9d7  test    rdi, rdi
0x14006a9da  jz      loc_14006AC8E
0x14006a9e0  test    rbx, rbx
0x14006a9e3  jz      loc_14006AC8E
0x14006a9e9  mov     rax, [rdi+8]
0x14006a9ed  cmp     [rbx], rax
0x14006a9f0  ja      loc_14006AC8E
0x14006a9f6  add     rcx, 30h ; '0'; this
0x14006a9fa  mov     [rbp+3Fh+var_98], r15
0x14006a9fe  lea     r8, [rbp+3Fh+P]; struct _MICRODOM_DOM_NODE_HEADER **
0x14006aa02  mov     [rbp+3Fh+var_A0], r15b
0x14006aa06  mov     [rbp+3Fh+P], r15
0x14006aa0a  call    ?FindObject@CDomLayoutCache@MicrodomImplementation@@QEAAJKAEAPEBU_MICRODOM_DOM_NODE_HEADER@@@Z; MicrodomImplementation::CDomLayoutCache::FindObject(ulong,_MICRODOM_DOM_NODE_HEADER const * &)
0x14006aa0f  test    eax, eax
0x14006aa11  js      short loc_14006AA5C
0x14006aa13  mov     rdx, [rbp+3Fh+P]; struct _MICRODOM_DOM_NODE_ELEMENT *
0x14006aa17  mov     al, [rdx]
0x14006aa19  and     al, 0Fh
0x14006aa1b  cmp     al, 1
0x14006aa1d  jz      short loc_14006AA71
0x14006aa1f  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006aa26  mov     [rbp+3Fh+var_80], 943h
0x14006aa2e  mov     [rbp+3Fh+P], rax
0x14006aa32  lea     rcx, [rbp+3Fh+P]
0x14006aa36  lea     rax, aMicrodomimplem_3; "MicrodomImplementation::CMicrodom::Find"...
0x14006aa3d  mov     r8d, 0C0000024h
0x14006aa43  mov     [rbp+3Fh+P+8], rax
0x14006aa47  lea     rax, aObjectheaderUe; "ObjectHeader->uElementType == ucObjectT"...
0x14006aa4e  mov     [rbp+3Fh+var_78], rax
0x14006aa52  call    RtlReportErrorOrigination
0x14006aa57  mov     eax, 0C0000024h
0x14006aa5c  add     rsp, 0A8h
0x14006aa63  pop     r15
0x14006aa65  pop     r14
0x14006aa67  pop     r13
0x14006aa69  pop     r12
0x14006aa6b  pop     rdi
0x14006aa6c  pop     rsi
0x14006aa6d  pop     rbx
0x14006aa6e  pop     rbp
0x14006aa6f  retn
0x14006aa71  cmp     [rbp+3Fh+arg_28], r15b
0x14006aa75  jz      loc_14006ABAE
0x14006aa7b  mov     rcx, r13; this
0x14006aa7e  cmp     [rbp+3Fh+arg_20], r15b
0x14006aa82  jz      loc_14006AB40
0x14006aa88  lea     rax, [rbp+3Fh+var_A0]
0x14006aa8c  mov     r9, r12; struct _LUTF8_STRING *
0x14006aa8f  mov     r8, r14; struct _LUTF8_STRING *
0x14006aa92  mov     [rsp+0E0h+var_C0], rax; bool *
0x14006aa97  call    ?CompareElementByTagNameNS@CMicrodom@MicrodomImplementation@@AEAAJPEBU_MICRODOM_DOM_NODE_ELEMENT@@PEBU_LUTF8_STRING@@1PEA_N@Z; MicrodomImplementation::CMicrodom::CompareElementByTagNameNS(_MICRODOM_DOM_NODE_ELEMENT const *,_LUTF8_STRING const *,_LUTF8_STRING const *,bool *)
0x14006aa9c  test    eax, eax
0x14006aa9e  js      short loc_14006AA5C
0x14006aaa0  cmp     [rbp+3Fh+var_A0], r15b
0x14006aaa4  jz      loc_14006ABAE
0x14006aaaa  mov     rax, [rbx]
0x14006aaad  cmp     [rdi+8], rax
0x14006aab1  jnz     loc_14006AB94
0x14006aab7  lea     rdx, [rax+0Ah]
0x14006aabb  mov     [rbp+3Fh+P], r15
0x14006aabf  mov     [rbp+3Fh+P+8], r15
0x14006aac3  cmp     rdx, rax
0x14006aac6  jb      loc_14006AC4C
0x14006aacc  lea     rcx, [rbp+3Fh+P]
0x14006aad0  call    ?Allocate@?$AutoVectorBase@V?$MicrodomVectorTraits@UElement@Rtl@Microdom@Windows@@@Microdom@Windows@@V?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@3@@Windows@@QEAAPEAUElement@Rtl@Microdom@2@_K@Z; Windows::AutoVectorBase<Windows::Microdom::MicrodomVectorTraits<Windows::Microdom::Rtl::Element>,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>>>::Allocate(unsigned __int64)
0x14006aad5  test    rax, rax
0x14006aad8  jnz     short loc_14006AB51
0x14006aada  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006aae1  mov     [rbp+3Fh+var_60], 724h
0x14006aae9  mov     [rbp+3Fh+var_70], rax
0x14006aaed  lea     rcx, [rbp+3Fh+var_70]
0x14006aaf1  lea     rax, aMicrodomimplem_12; "MicrodomImplementation::CMicrodom::GetE"...
0x14006aaf8  mov     r8d, 0C0000017h
0x14006aafe  mov     [rbp+3Fh+var_68], rax
0x14006ab02  lea     rax, aTempelementsAl; "TempElements.Allocate(NewCapacity)"
0x14006ab09  mov     [rbp+3Fh+var_58], rax
0x14006ab0d  call    RtlReportErrorOrigination
0x14006ab12  mov     r8, [rbp+3Fh+P]; P
0x14006ab16  test    r8, r8
0x14006ab19  jz      short loc_14006AB36
0x14006ab1b  mov     rcx, gs:60h
0x14006ab24  xor     edx, edx; Flags
0x14006ab26  mov     rcx, [rcx+30h]; HeapHandle
0x14006ab2a  call    cs:__imp_RtlFreeHeap
0x14006ab31  nop     dword ptr [rax+rax+00h]
0x14006ab36  mov     eax, 0C0000017h
0x14006ab3b  jmp     loc_14006AA5C
0x14006ab40  lea     r9, [rbp+3Fh+var_A0]; bool *
0x14006ab44  mov     r8, r12; struct _LUTF8_STRING *
0x14006ab47  call    ?CompareElementByTagName@CMicrodom@MicrodomImplementation@@AEAAJPEBU_MICRODOM_DOM_NODE_ELEMENT@@PEBU_LUTF8_STRING@@PEA_N@Z; MicrodomImplementation::CMicrodom::CompareElementByTagName(_MICRODOM_DOM_NODE_ELEMENT const *,_LUTF8_STRING const *,bool *)
0x14006ab4c  jmp     loc_14006AA9C
0x14006ab51  mov     r8, [rbx]
0x14006ab54  mov     rdx, [rdi]; Src
0x14006ab57  mov     rcx, [rbp+3Fh+P]; void *
0x14006ab5b  shl     r8, 4; Size
0x14006ab5f  call    memcpy_0
0x14006ab64  movups  xmm1, xmmword ptr [rdi]
0x14006ab67  movaps  xmm0, xmmword ptr [rbp+3Fh+P]
0x14006ab6b  movq    r8, xmm1; P
0x14006ab70  movdqu  xmmword ptr [rdi], xmm0
0x14006ab74  test    r8, r8
0x14006ab77  jz      short loc_14006AB94
0x14006ab79  mov     rcx, gs:60h
0x14006ab82  xor     edx, edx; Flags
0x14006ab84  mov     rcx, [rcx+30h]; HeapHandle
0x14006ab88  call    cs:__imp_RtlFreeHeap
0x14006ab8f  nop     dword ptr [rax+rax+00h]
0x14006ab94  mov     rcx, [rbx]
0x14006ab97  cmp     rcx, [rdi+8]
0x14006ab9b  jnb     loc_14006AC8E
0x14006aba1  mov     rax, [rdi]
0x14006aba4  add     rcx, rcx
0x14006aba7  mov     [rax+rcx*8+8], esi
0x14006abab  inc     qword ptr [rbx]
0x14006abae  xor     r9d, r9d
0x14006abb1  lea     r8, [rbp+3Fh+var_98]
0x14006abb5  mov     edx, esi
0x14006abb7  mov     rcx, r13
0x14006abba  call    ?GetNodeChildren@CMicrodom@MicrodomImplementation@@QEAAJKPEAPEAU?$Vector@$$CBUNode@Rtl@Microdom@Windows@@@Windows@@0@Z; MicrodomImplementation::CMicrodom::GetNodeChildren(ulong,Windows::Vector<Windows::Microdom::Rtl::Node const> * *,Windows::Vector<Windows::Microdom::Rtl::Node const> * *)
0x14006abbf  test    eax, eax
0x14006abc1  js      loc_14006AA5C
0x14006abc7  mov     r14, [rbp+3Fh+var_98]
0x14006abcb  cmp     [r14+8], r15
0x14006abcf  jbe     short loc_14006AC45
0x14006abd1  xor     esi, esi
0x14006abd3  mov     rdx, [r14]
0x14006abd6  lea     r8, [rbp+3Fh+var_98]; struct _MICRODOM_DOM_NODE_HEADER **
0x14006abda  lea     rcx, [r13+30h]; this
0x14006abde  mov     [rbp+3Fh+var_98], 0
0x14006abe6  mov     edx, [rsi+rdx+8]; unsigned int
0x14006abea  call    ?FindObject@CDomLayoutCache@MicrodomImplementation@@QEAAJKAEAPEBU_MICRODOM_DOM_NODE_HEADER@@@Z; MicrodomImplementation::CDomLayoutCache::FindObject(ulong,_MICRODOM_DOM_NODE_HEADER const * &)
0x14006abef  test    eax, eax
0x14006abf1  js      loc_14006AA5C
0x14006abf7  mov     rax, [rbp+3Fh+var_98]
0x14006abfb  mov     cl, [rax]
0x14006abfd  and     cl, 0Fh
0x14006ac00  cmp     cl, 1
0x14006ac03  jnz     short loc_14006AC38
0x14006ac05  mov     rdx, [r14]
0x14006ac08  mov     r9, r12
0x14006ac0b  mov     al, [rbp+3Fh+arg_20]
0x14006ac0e  mov     r8, [rbp+3Fh+var_50]
0x14006ac12  mov     [rsp+0E0h+var_A8], rbx
0x14006ac17  mov     edx, [rsi+rdx+8]
0x14006ac1b  mov     [rsp+0E0h+var_B0], rdi
0x14006ac20  mov     [rsp+0E0h+var_B8], cl
0x14006ac24  mov     rcx, r13
0x14006ac27  mov     byte ptr [rsp+0E0h+var_C0], al
0x14006ac2b  call    ?GetElementsByTagNameCommon@CMicrodom@MicrodomImplementation@@AEAAJKPEBU_LUTF8_STRING@@0_N1PEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@PEA_K@Z; MicrodomImplementation::CMicrodom::GetElementsByTagNameCommon(ulong,_LUTF8_STRING const *,_LUTF8_STRING const *,bool,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *,unsigned __int64 *)
0x14006ac30  test    eax, eax
0x14006ac32  js      loc_14006AA5C
0x14006ac38  inc     r15
0x14006ac3b  add     rsi, 10h
0x14006ac3f  cmp     r15, [r14+8]
0x14006ac43  jb      short loc_14006ABD3
0x14006ac45  xor     eax, eax
0x14006ac47  jmp     loc_14006AA5C
0x14006ac4c  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006ac53  mov     [rbp+3Fh+var_60], 722h
0x14006ac5b  mov     [rbp+3Fh+var_70], rax
0x14006ac5f  lea     rcx, [rbp+3Fh+var_70]
0x14006ac63  lea     rax, aMicrodomimplem_12; "MicrodomImplementation::CMicrodom::GetE"...
0x14006ac6a  mov     r8d, 0C0000095h
0x14006ac70  mov     [rbp+3Fh+var_68], rax
0x14006ac74  lea     rax, aBuclRtlAddSize_3; "::BUCL::Rtl::Add<SIZE_T>( *pcElements, "...
0x14006ac7b  mov     [rbp+3Fh+var_58], rax
0x14006ac7f  call    RtlReportErrorOrigination
0x14006ac84  mov     eax, 0C0000095h
0x14006ac89  jmp     loc_14006AA5C
0x14006ac8e  mov     ecx, 0C00000E5h; Status
0x14006ac93  call    cs:__imp_RtlRaiseStatus
0x14006ac9a  nop     dword ptr [rax+rax+00h]
0x14006ac9f  int     3; Trap to Debugger
```
