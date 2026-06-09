# CPort::SaveNetworkConnectHistory(_DOT11_SSID *,CBSSEntry *)

- ea: `0x1400678f4`
- end: `0x140067b61`
- name: `?SaveNetworkConnectHistory@CPort@@QEAAHPEAU_DOT11_SSID@@PEAVCBSSEntry@@@Z`
- size: `621`
- prototype: `int(CPort *__hidden this, struct _DOT11_SSID *, struct CBSSEntry *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14005e334`

## callees

- `0x140013000`
- `0x140034e04`
- `0x140034ec4`
- `0x14004c5b4`
- `0x14005c568`
- `0x1400678f4`
- `0x1400d6244`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400679f9`
- `ntoskrnl!RtlCompareMemory` at `0x1400679f9`

## pseudocode

```c
__int64 __fastcall CPort::SaveNetworkConnectHistory(CPort *this, struct _DOT11_SSID *a2, struct CBSSEntry *a3)
{
  unsigned int v4; // ebx
  struct _DOT11_SSID *v5; // rbp
  int v7; // edx
  int v8; // eax
  int v9; // edx
  struct CNetworkHistory *v10; // r13
  int v11; // r8d
  unsigned int Channel; // ebp
  enum _WDI_BAND_ID BandId; // r15d
  __int64 v15; // [rsp+28h] [rbp-50h]
  struct CNetworkHistory *v16; // [rsp+80h] [rbp+8h] BYREF

  v4 = 0;
  v16 = 0;
  v5 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      444,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
  }
  if ( CPropertyCache::GetPropertyBooleanOrDefault(&this->m_PortPropertyCache, 0x20u, 0) )
  {
    v8 = CNetworkHistoryList::UpdateOrAddNetworkToTable(this->m_pConnectHistory, v5, &v16);
    v4 = v8;
    if ( v8 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v4;
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        445,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        v8);
    }
    else
    {
      v10 = v16;
      if ( RtlCompareMemory(v16->LastBssid, a3->m_BssID, 6u) == 6 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return v4;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v7) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v7,
            1,
            446,
            (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
        }
      }
      else
      {
        Channel = a3->m_BssChannelInfo.Channel;
        BandId = a3->m_BssChannelInfo.BandId;
        *(_DWORD *)v10->LastBssid = *(_DWORD *)a3->m_BssID;
        *(_WORD *)&v10->LastBssid[4] = *(_WORD *)&a3->m_BssID[4];
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v7) = 5;
          WPP_RECORDER_SF_dddd(
            WPP_GLOBAL_Control->DeviceExtension,
            v7,
            v11,
            447,
            (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
            BandId,
            Channel,
            a3->m_SignalInfo.LinkQuality,
            a3->m_CachedRank);
        }
        CNetworkHistory::FindOrAddChannelEntry(v10, BandId, Channel);
      }
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v15) = v4;
    LOBYTE(v7) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      448,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      v15);
  }
  return v4;
}

```

## disassembly

```asm
0x1400678f4  mov     rax, rsp
0x1400678f7  mov     [rax+10h], rbx
0x1400678fb  mov     [rax+18h], rbp
0x1400678ff  push    rsi
0x140067900  push    rdi
0x140067901  push    r13
0x140067903  push    r14
0x140067905  push    r15
0x140067907  sub     rsp, 50h
0x14006790b  xor     r15d, r15d
0x14006790e  mov     rsi, r8
0x140067911  mov     ebx, r15d
0x140067914  mov     [rax+8], r15
0x140067918  mov     rbp, rdx
0x14006791b  mov     rdi, rcx
0x14006791e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140067925  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14006792c  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140067933  jz      short loc_140067965
0x140067935  mov     rcx, cs:WPP_GLOBAL_Control
0x14006793c  cmp     byte ptr [rcx+29h], 5
0x140067940  jnb     short loc_140067949
0x140067942  cmp     [rcx+48h], r15w
0x140067947  jz      short loc_140067965
0x140067949  mov     rcx, [rcx+40h]
0x14006794d  mov     r9d, 1BCh
0x140067953  mov     r8d, 1
0x140067959  mov     [rsp+78h+var_58], r14
0x14006795e  mov     dl, 5
0x140067960  call    WPP_RECORDER_SF_
0x140067965  xor     r8d, r8d; unsigned __int8
0x140067968  lea     rcx, [rdi+3A8h]; this
0x14006796f  lea     edx, [r8+20h]; unsigned int
0x140067973  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x140067978  test    al, al
0x14006797a  jz      loc_140067AF8
0x140067980  mov     rcx, [rdi+410h]; this
0x140067987  lea     r8, [rsp+78h+arg_0]; struct CNetworkHistory **
0x14006798f  mov     rdx, rbp; struct _DOT11_SSID *
0x140067992  call    ?UpdateOrAddNetworkToTable@CNetworkHistoryList@@QEAAHPEAU_DOT11_SSID@@PEAPEAVCNetworkHistory@@@Z; CNetworkHistoryList::UpdateOrAddNetworkToTable(_DOT11_SSID *,CNetworkHistory * *)
0x140067997  mov     ebx, eax
0x140067999  test    eax, eax
0x14006799b  jz      short loc_1400679DD
0x14006799d  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400679a4  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400679ab  jz      loc_140067B45
0x1400679b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400679b8  mov     r9d, 1BDh
0x1400679be  mov     dword ptr [rsp+78h+var_50], eax
0x1400679c2  mov     r8d, 1
0x1400679c8  mov     dl, 2
0x1400679ca  mov     [rsp+78h+var_58], r14
0x1400679cf  mov     rcx, [rcx+40h]
0x1400679d3  call    WPP_RECORDER_SF_D
0x1400679d8  jmp     loc_140067B08
0x1400679dd  mov     r13, [rsp+78h+arg_0]
0x1400679e5  lea     r14, [rsi+1BCh]
0x1400679ec  mov     r8d, 6; Length
0x1400679f2  mov     rdx, r14; Source2
0x1400679f5  lea     rcx, [r13+30h]; Source1
0x1400679f9  call    cs:__imp_RtlCompareMemory
0x140067a00  nop     dword ptr [rax+rax+00h]
0x140067a05  cmp     rax, 6
0x140067a09  jnz     short loc_140067A5F
0x140067a0b  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140067a12  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140067a19  jz      loc_140067B45
0x140067a1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140067a26  cmp     byte ptr [rcx+29h], 5
0x140067a2a  jnb     short loc_140067A37
0x140067a2c  cmp     [rcx+48h], r15w
0x140067a31  jz      loc_140067B01
0x140067a37  mov     rcx, [rcx+40h]
0x140067a3b  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140067a42  mov     r9d, 1BEh
0x140067a48  mov     [rsp+78h+var_58], r14
0x140067a4d  mov     r8d, 1
0x140067a53  mov     dl, 5
0x140067a55  call    WPP_RECORDER_SF_
0x140067a5a  jmp     loc_140067B08
0x140067a5f  mov     eax, [r14]
0x140067a62  mov     ebp, [rsi+208h]
0x140067a68  mov     r15d, [rsi+20Ch]
0x140067a6f  mov     [r13+30h], eax
0x140067a73  movzx   eax, word ptr [r14+4]
0x140067a78  mov     [r13+34h], ax
0x140067a7d  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140067a84  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140067a8b  jz      short loc_140067ADE
0x140067a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140067a94  cmp     byte ptr [rcx+29h], 5
0x140067a98  jnb     short loc_140067AA2
0x140067a9a  xor     eax, eax
0x140067a9c  cmp     [rcx+48h], ax
0x140067aa0  jz      short loc_140067ADE
0x140067aa2  mov     eax, [rsi+250h]
0x140067aa8  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140067aaf  mov     rcx, [rcx+40h]
0x140067ab3  mov     r9d, 1BFh
0x140067ab9  mov     [rsp+78h+var_38], eax
0x140067abd  mov     dl, 5
0x140067abf  mov     eax, [rsi+1D4h]
0x140067ac5  mov     [rsp+78h+var_40], eax
0x140067ac9  mov     [rsp+78h+var_48], ebp
0x140067acd  mov     dword ptr [rsp+78h+var_50], r15d
0x140067ad2  mov     [rsp+78h+var_58], r14
0x140067ad7  call    WPP_RECORDER_SF_dddd
0x140067adc  jmp     short loc_140067AE5
0x140067ade  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140067ae5  mov     r8d, ebp; unsigned int
0x140067ae8  mov     edx, r15d; enum _WDI_BAND_ID
0x140067aeb  mov     rcx, r13; this
0x140067aee  call    ?FindOrAddChannelEntry@CNetworkHistory@@QEAAXW4_WDI_BAND_ID@@I@Z; CNetworkHistory::FindOrAddChannelEntry(_WDI_BAND_ID,uint)
0x140067af3  xor     r15d, r15d
0x140067af6  jmp     short loc_140067B08
0x140067af8  lea     rdi, WPP_RECORDER_INITIALIZED
0x140067aff  jmp     short loc_140067B08
0x140067b01  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x140067b08  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140067b0f  jz      short loc_140067B45
0x140067b11  mov     rcx, cs:WPP_GLOBAL_Control
0x140067b18  cmp     byte ptr [rcx+29h], 5
0x140067b1c  jnb     short loc_140067B25
0x140067b1e  cmp     [rcx+48h], r15w
0x140067b23  jz      short loc_140067B45
0x140067b25  mov     rcx, [rcx+40h]
0x140067b29  mov     r9d, 1C0h
0x140067b2f  mov     dword ptr [rsp+78h+var_50], ebx
0x140067b33  mov     r8d, 1
0x140067b39  mov     dl, 5
0x140067b3b  mov     [rsp+78h+var_58], r14
0x140067b40  call    WPP_RECORDER_SF_D
0x140067b45  lea     r11, [rsp+78h+var_28]
0x140067b4a  mov     eax, ebx
0x140067b4c  mov     rbx, [r11+38h]
0x140067b50  mov     rbp, [r11+40h]
0x140067b54  mov     rsp, r11
0x140067b57  pop     r15
0x140067b59  pop     r14
0x140067b5b  pop     r13
0x140067b5d  pop     rdi
0x140067b5e  pop     rsi
0x140067b5f  retn
```
