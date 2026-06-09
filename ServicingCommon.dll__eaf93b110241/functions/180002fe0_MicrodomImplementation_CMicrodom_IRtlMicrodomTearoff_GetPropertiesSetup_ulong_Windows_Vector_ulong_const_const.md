# MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetPropertiesSetup(ulong,Windows::Vector<ulong const> const &,Windows::Vector<ulong const> const &,Windows::Vector<Windows::Microdom::Rtl::NodePropertyResult> const &)

- ea: `0x180002fe0`
- end: `0x1800031d2`
- name: `?GetPropertiesSetup@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@QEAAJKAEBU?$Vector@$$CBK@Windows@@0AEBU?$Vector@UNodePropertyResult@Rtl@Microdom@Windows@@@4@@Z`
- size: `498`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180014fc0`
- `0x180057170`
- `0x180057200`
- `0x180057290`
- `0x180057320`
- `0x1800573b0`
- `0x180057440`
- `0x1800574d0`

## callees

- `0x180002fe0`
- `0x1800031e0`
- `0x18001f4ac`
- `0x1800293a0`

## string_xrefs

- `0x1800030e1`: `onecore\base\xml\udom_microdom.cpp`
- `0x180003127`: `onecore\base\xml\udom_microdom.cpp`
- `0x180003170`: `onecore\base\xml\udom_microdom.cpp`
- `0x180003197`: `onecore\base\xml\udom_microdom.cpp`
- `0x180003110`: `NodeIndex < m_pTargetObject->m_LayoutCache.TotalObjectCount()`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetPropertiesSetup(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3,
        _QWORD *a4,
        __int64 *a5)
{
  unsigned __int64 i; // r9
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // r11
  unsigned __int64 j; // rdx
  unsigned __int64 v13; // rcx
  unsigned __int64 k; // rax
  const char *v16; // rax
  __int128 v17; // [rsp+20h] [rbp-30h] BYREF
  __int64 v18; // [rsp+30h] [rbp-20h]
  const char *v19; // [rsp+38h] [rbp-18h]
  int v20; // [rsp+40h] [rbp-10h] BYREF

  v20 = 0;
  if ( *a5 )
  {
    for ( i = 0; i < a5[1]; *(_QWORD *)(v9 + 8 * v10 + 16) = 0 )
    {
      v9 = *a5;
      v10 = 3 * i;
      v17 = 0u;
      ++i;
      *(_OWORD *)(v9 + 8 * v10) = 0u;
    }
  }
  v11 = a3[1];
  if ( v11 == a5[1] )
  {
    if ( *a3 && *a5 )
    {
      for ( j = 0; j < v11; ++j )
      {
        v13 = a4[1];
        for ( k = 0; k < v13; ++k )
        {
          if ( *(_DWORD *)(*a4 + 4 * k) == *(_DWORD *)(*a3 + 4 * j) )
            break;
        }
        if ( k >= v13 )
        {
          v18 = 2686;
          *(_QWORD *)&v17 = "onecore\\base\\xml\\udom_microdom.cpp";
          *((_QWORD *)&v17 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetPropertiesSetup";
          v16 = "j < ValidProperties.Length";
          goto LABEL_20;
        }
      }
      if ( a2 >= *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 96LL) + 8LL) )
      {
        v18 = 2689;
        *(_QWORD *)&v17 = "onecore\\base\\xml\\udom_microdom.cpp";
        *((_QWORD *)&v17 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetPropertiesSetup";
        v19 = "NodeIndex < m_pTargetObject->m_LayoutCache.TotalObjectCount()";
        RtlReportErrorOrigination(&v17, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
        return 3221225485LL;
      }
      else
      {
        return 0;
      }
    }
    else
    {
      v18 = 2674;
      *(_QWORD *)&v17 = "onecore\\base\\xml\\udom_microdom.cpp";
      *((_QWORD *)&v17 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetPropertiesSetup";
      v16 = "(Properties.Elements != 0) && (Results.Elements != 0)";
LABEL_20:
      v19 = v16;
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
               &v20,
               &v17);
    }
  }
  else
  {
    v18 = 2673;
    *(_QWORD *)&v17 = "onecore\\base\\xml\\udom_microdom.cpp";
    *((_QWORD *)&v17 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetPropertiesSetup";
    v19 = "Properties.Length == Results.Length";
    RtlReportErrorOrigination(&v17, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180002fe0  mov     [rsp-18h+arg_8], rsi
0x180002fe5  mov     [rsp-18h+arg_10], rdi
0x180002fea  push    rbp
0x180002feb  push    r14
0x180002fed  push    r15
0x180002fef  mov     rbp, rsp
0x180002ff2  sub     rsp, 50h
0x180002ff6  mov     rax, cs:__security_cookie
0x180002ffd  xor     rax, rsp
0x180003000  mov     [rbp+var_8], rax
0x180003004  mov     r10, [rbp+arg_20]
0x180003008  xor     r15d, r15d
0x18000300b  mov     rdi, r9
0x18000300e  mov     [rbp+var_10], r15d
0x180003012  mov     esi, edx
0x180003014  mov     r14, rcx
0x180003017  cmp     [r10], r15
0x18000301a  jz      short loc_18000304A
0x18000301c  mov     r9d, r15d
0x18000301f  cmp     [r10+8], r15
0x180003023  jbe     short loc_18000304A
0x180003025  mov     rax, [r10]
0x180003028  lea     rcx, [r9+r9*2]
0x18000302c  mov     qword ptr [rbp+var_30], r15
0x180003030  inc     r9
0x180003033  mov     qword ptr [rbp+var_30+8], r15
0x180003037  movups  xmm0, [rbp+var_30]
0x18000303b  movups  xmmword ptr [rax+rcx*8], xmm0
0x18000303f  mov     [rax+rcx*8+10h], r15
0x180003044  cmp     r9, [r10+8]
0x180003048  jb      short loc_180003025
0x18000304a  mov     r11, [r8+8]
0x18000304e  cmp     r11, [r10+8]
0x180003052  jnz     loc_180003127
0x180003058  mov     [rsp+50h+arg_0], rbx
0x18000305d  mov     rbx, [r8]
0x180003060  test    rbx, rbx
0x180003063  jz      loc_180003197
0x180003069  cmp     [r10], r15
0x18000306c  jz      loc_180003197
0x180003072  mov     rdx, r15
0x180003075  cmp     rdx, r11
0x180003078  jnb     short loc_1800030A9
0x18000307a  mov     rcx, [rdi+8]
0x18000307e  mov     rax, r15
0x180003081  test    rcx, rcx
0x180003084  jz      short loc_18000309B
0x180003086  mov     r8d, [rbx+rdx*4]
0x18000308a  mov     r9, [rdi]
0x18000308d  cmp     [r9+rax*4], r8d
0x180003091  jz      short loc_18000309B
0x180003093  inc     rax
0x180003096  cmp     rax, rcx
0x180003099  jb      short loc_18000308D
0x18000309b  cmp     rax, rcx
0x18000309e  jnb     loc_180003170
0x1800030a4  inc     rdx
0x1800030a7  jmp     short loc_180003075
0x1800030a9  mov     rax, [r14+8]
0x1800030ad  mov     rcx, [rax+60h]
0x1800030b1  cmp     esi, [rcx+8]
0x1800030b4  jnb     short loc_1800030E1
0x1800030b6  xor     eax, eax
0x1800030b8  mov     rbx, [rsp+50h+arg_0]
0x1800030bd  mov     rcx, [rbp+var_8]
0x1800030c1  xor     rcx, rsp; StackCookie
0x1800030c4  call    __security_check_cookie
0x1800030c9  mov     rsi, [rsp+50h+arg_8]
0x1800030ce  mov     rdi, [rsp+50h+arg_10]
0x1800030d6  add     rsp, 50h
0x1800030da  pop     r15
0x1800030dc  pop     r14
0x1800030de  pop     rbp
0x1800030df  retn
0x1800030e1  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800030e8  mov     [rbp+var_20], 0A81h
0x1800030f0  mov     qword ptr [rbp+var_30], rax
0x1800030f4  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800030fb  lea     rax, aMicrodomimplem_25; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180003102  mov     r8d, 0C000000Dh
0x180003108  mov     qword ptr [rbp+var_30+8], rax
0x18000310c  lea     rcx, [rbp+var_30]
0x180003110  lea     rax, aNodeindexMPtar; "NodeIndex < m_pTargetObject->m_LayoutCa"...
0x180003117  mov     [rbp+var_18], rax
0x18000311b  call    RtlReportErrorOrigination
0x180003120  mov     eax, 0C000000Dh
0x180003125  jmp     short loc_1800030B8
0x180003127  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18000312e  mov     [rbp+var_20], 0A71h
0x180003136  mov     qword ptr [rbp+var_30], rax
0x18000313a  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180003141  lea     rax, aMicrodomimplem_25; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180003148  mov     r8d, 0C000000Dh
0x18000314e  mov     qword ptr [rbp+var_30+8], rax
0x180003152  lea     rcx, [rbp+var_30]
0x180003156  lea     rax, aPropertiesLeng; "Properties.Length == Results.Length"
0x18000315d  mov     [rbp+var_18], rax
0x180003161  call    RtlReportErrorOrigination
0x180003166  mov     eax, 0C000000Dh
0x18000316b  jmp     loc_1800030BD
0x180003170  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180003177  mov     [rbp+var_20], 0A7Eh
0x18000317f  mov     qword ptr [rbp+var_30], rax
0x180003183  lea     rax, aMicrodomimplem_25; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18000318a  mov     qword ptr [rbp+var_30+8], rax
0x18000318e  lea     rax, aJValidproperti; "j < ValidProperties.Length"
0x180003195  jmp     short loc_1800031BC
0x180003197  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18000319e  mov     [rbp+var_20], 0A72h
0x1800031a6  mov     qword ptr [rbp+var_30], rax
0x1800031aa  lea     rax, aMicrodomimplem_25; "MicrodomImplementation::CMicrodom_IRtlM"...
0x1800031b1  mov     qword ptr [rbp+var_30+8], rax
0x1800031b5  lea     rax, aPropertiesElem; "(Properties.Elements != 0) && (Results."...
0x1800031bc  lea     rdx, [rbp+var_30]
0x1800031c0  mov     [rbp+var_18], rax
0x1800031c4  lea     rcx, [rbp+var_10]
0x1800031c8  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800031cd  jmp     loc_1800030B8
```
