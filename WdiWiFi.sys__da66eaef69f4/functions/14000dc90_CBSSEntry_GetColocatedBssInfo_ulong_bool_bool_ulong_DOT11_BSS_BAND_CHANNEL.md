# CBSSEntry::GetColocatedBssInfo(ulong,bool,bool,ulong *,DOT11_BSS_BAND_CHANNEL *)

- ea: `0x14000dc90`
- end: `0x14000e268`
- name: `?GetColocatedBssInfo@CBSSEntry@@QEAAKK_N0PEAKPEAUDOT11_BSS_BAND_CHANNEL@@@Z`
- size: `1496`
- prototype: `unsigned int __fastcall(CBSSEntry *__hidden this, unsigned int, bool, bool, unsigned int *, struct DOT11_BSS_BAND_CHANNEL *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400205c0`
- `0x1400471a0`
- `0x14005e334`

## callees

- `0x14000d820`
- `0x14000dc90`
- `0x14000e270`
- `0x1400bcfd4`
- `0x1400bd1c8`
- `0x1400da4f0`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000e09e`
- `ntoskrnl!RtlCompareMemory` at `0x14000e09e`

## pseudocode

```c
__int64 __fastcall CBSSEntry::GetColocatedBssInfo(
        CBSSEntry *this,
        unsigned int a2,
        __int64 a3,
        char a4,
        unsigned int *a5,
        struct DOT11_BSS_BAND_CHANNEL *a6)
{
  unsigned int v7; // r15d
  __int64 v8; // rdi
  enum _DOT11_BAND_ID v9; // eax
  unsigned int v10; // edx
  char v11; // r9
  unsigned int m_NumOutgoingNeighborBssLinks; // ebp
  unsigned int m_BssEntryShortSsid; // r8d
  unsigned int m_NumIncomingNeighborBssLinks; // r10d
  __int64 j; // rdx
  CBSSEntry_vtbl *v16; // rax
  int v17; // r8d
  int v18; // r9d
  __int64 v20; // r14
  WDI_NEIGHBOR_BSS *m_pOutgoingNeighborBssLinks; // r11
  _DOT11_BAND_ID BandId; // r13d
  WDI_NEIGHBOR_BSS *v23; // rcx
  DOT11_TBTT_INFORMATION_HEADER v24; // r12
  __int64 v25; // rcx
  WDI_NEIGHBOR_BSS *v26; // rcx
  __int64 v27; // rbp
  WDI_NEIGHBOR_BSS *m_pIncomingNeighborBssLinks; // r11
  WDI_NEIGHBOR_BSS *v29; // rcx
  _DOT11_BAND_ID v30; // r13d
  DOT11_TBTT_INFORMATION_HEADER v31; // r14
  __int64 i; // r14
  WDI_NEIGHBOR_BSS *v33; // rcx
  WDI_NEIGHBOR_BSS *v34; // rdx
  __int64 v35; // rcx
  WDI_NEIGHBOR_BSS *v36; // rcx
  __int64 k; // rcx
  __int64 v38; // r8
  __int128 v39; // xmm2
  __int64 v40; // xmm3_8
  __int64 v41; // rcx
  int v42; // [rsp+20h] [rbp-F8h]
  unsigned int v44; // [rsp+84h] [rbp-94h]
  enum _DOT11_BAND_ID v46; // [rsp+8Ch] [rbp-8Ch]
  _OWORD v47[2]; // [rsp+98h] [rbp-80h] BYREF
  int v48; // [rsp+B8h] [rbp-60h]

  v7 = 0;
  v8 = 0;
  v9 = CWabiToDot11Converter::MapBandID(this->m_BssChannelInfo.BandId);
  m_NumOutgoingNeighborBssLinks = this->m_NumOutgoingNeighborBssLinks;
  m_BssEntryShortSsid = this->m_BssEntryShortSsid;
  v46 = v9;
  v44 = m_BssEntryShortSsid;
  if ( m_NumOutgoingNeighborBssLinks )
  {
    v20 = 0;
    do
    {
      m_pOutgoingNeighborBssLinks = this->m_pOutgoingNeighborBssLinks;
      BandId = m_pOutgoingNeighborBssLinks[v20].BssBandChannel.BandId;
      v23 = &m_pOutgoingNeighborBssLinks[v20];
      v24.0 = ($4BB66463F66E060C3CE4216DB70F2816)v23->TBTTInformationHeader;
      if ( BandId != DOT11_BAND_ID_6000 )
        v11 = 0;
      if ( ((*(_BYTE *)&v24.0 & 4) != 0 || (v23->BssParameters.ucValue & 0x40) != 0)
        && (!v11 || m_pOutgoingNeighborBssLinks[v20].BssBandChannel.uShortSsid == m_BssEntryShortSsid) )
      {
        if ( (unsigned int)v8 < v10 )
        {
          v25 = v8;
          v8 = (unsigned int)(v8 + 1);
          *(_OWORD *)a6[v25].Bssid = *(_OWORD *)m_pOutgoingNeighborBssLinks[v20].BssBandChannel.Bssid;
          *(_QWORD *)&a6[v25].Channel = *(_QWORD *)&m_pOutgoingNeighborBssLinks[v20].BssBandChannel.Channel;
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v26 = this->m_pOutgoingNeighborBssLinks;
            WPP_RECORDER_SF_dd_MAC_Ddd(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v26 + 16 + 40 * v20,
              m_BssEntryShortSsid,
              235,
              v42,
              v8,
              this->m_NumOutgoingNeighborBssLinks,
              (__int64)&v26[v20].BssBandChannel,
              v26[v20].BssBandChannel.uShortSsid,
              v26[v20].BssBandChannel.BandId,
              v26[v20].BssBandChannel.Channel);
          }
        }
        ++v7;
      }
      else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_ddDDDD_MAC_Ddd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)m_pOutgoingNeighborBssLinks + 16 + 40 * v20,
          (v23->BssParameters.ucValue >> 6) & 1,
          234,
          v42,
          v8,
          m_NumOutgoingNeighborBssLinks,
          v11,
          (*(_BYTE *)&v24.0 & 4) != 0,
          (v23->BssParameters.ucValue & 0x40) != 0,
          v44,
          (__int64)&m_pOutgoingNeighborBssLinks[v20].BssBandChannel,
          m_pOutgoingNeighborBssLinks[v20].BssBandChannel.uShortSsid,
          BandId,
          m_pOutgoingNeighborBssLinks[v20].BssBandChannel.Channel);
      }
      m_NumOutgoingNeighborBssLinks = this->m_NumOutgoingNeighborBssLinks;
      v20 = (unsigned int)(v20 + 1);
      v10 = a2;
      m_BssEntryShortSsid = v44;
      v11 = a4;
    }
    while ( (unsigned int)v20 < m_NumOutgoingNeighborBssLinks );
  }
  m_NumIncomingNeighborBssLinks = this->m_NumIncomingNeighborBssLinks;
  if ( m_NumIncomingNeighborBssLinks )
  {
    v27 = 0;
    do
    {
      m_pIncomingNeighborBssLinks = this->m_pIncomingNeighborBssLinks;
      v29 = &m_pIncomingNeighborBssLinks[v27];
      v30 = v29->BssBandChannel.BandId;
      v31.0 = ($4BB66463F66E060C3CE4216DB70F2816)v29->TBTTInformationHeader;
      if ( v30 != DOT11_BAND_ID_6000 )
        v11 = 0;
      if ( ((*(_BYTE *)&v31.0 & 4) != 0 || (v29->BssParameters.ucValue & 0x40) != 0)
        && (!v11 || v29->BssBandChannel.uShortSsid == m_BssEntryShortSsid) )
      {
        for ( i = 0; (unsigned int)i < (unsigned int)v8; i = (unsigned int)(i + 1) )
        {
          if ( RtlCompareMemory(
                 &a6[i],
                 (char *)&this->m_pIncomingNeighborBssLinks->BssBandChannel + 32 * v27 + 8 * v27,
                 6u) == 6 )
          {
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v33 = this->m_pIncomingNeighborBssLinks;
              WPP_RECORDER_SF_dd_MAC_Ddd(
                WPP_GLOBAL_Control->DeviceExtension,
                (_DWORD)v33 + 16 + 40 * v27,
                5 * v27,
                237,
                v42,
                v8,
                this->m_NumIncomingNeighborBssLinks,
                (__int64)&v33[v27].BssBandChannel,
                v33[v27].BssBandChannel.uShortSsid,
                v33[v27].BssBandChannel.BandId,
                v33[v27].BssBandChannel.Channel);
            }
            goto LABEL_41;
          }
        }
        if ( (unsigned int)v8 < a2 )
        {
          v34 = this->m_pIncomingNeighborBssLinks;
          v35 = v8;
          v8 = (unsigned int)(v8 + 1);
          *(_OWORD *)a6[v35].Bssid = *(_OWORD *)v34[v27].BssBandChannel.Bssid;
          *(_QWORD *)&a6[v35].Channel = *(_QWORD *)&v34[v27].BssBandChannel.Channel;
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v36 = this->m_pIncomingNeighborBssLinks;
            WPP_RECORDER_SF_dd_MAC_Ddd(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v36 + 16 + 40 * v27,
              5 * v27,
              238,
              v42,
              v8,
              this->m_NumIncomingNeighborBssLinks,
              (__int64)&v36[v27].BssBandChannel,
              v36[v27].BssBandChannel.uShortSsid,
              v36[v27].BssBandChannel.BandId,
              v36[v27].BssBandChannel.Channel);
          }
        }
        ++v7;
      }
      else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_ddDDDD_MAC_Ddd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)m_pIncomingNeighborBssLinks + 16 + 40 * v27,
          (m_pIncomingNeighborBssLinks[v27].BssParameters.ucValue >> 6) & 1,
          236,
          v42,
          v8,
          m_NumIncomingNeighborBssLinks,
          v11,
          (*(_BYTE *)&v31.0 & 4) != 0,
          (m_pIncomingNeighborBssLinks[v27].BssParameters.ucValue & 0x40) != 0,
          v44,
          (__int64)&m_pIncomingNeighborBssLinks[v27].BssBandChannel,
          m_pIncomingNeighborBssLinks[v27].BssBandChannel.uShortSsid,
          v30,
          m_pIncomingNeighborBssLinks[v27].BssBandChannel.Channel);
      }
LABEL_41:
      m_NumIncomingNeighborBssLinks = this->m_NumIncomingNeighborBssLinks;
      v27 = (unsigned int)(v27 + 1);
      m_BssEntryShortSsid = v44;
      v11 = a4;
    }
    while ( (unsigned int)v27 < m_NumIncomingNeighborBssLinks );
  }
  for ( j = 0; (unsigned int)j < (unsigned int)v8; j = (unsigned int)(j + 1) )
  {
    if ( a6[j].BandId == v46 )
    {
      for ( k = (unsigned int)(v8 - 1); (unsigned int)k > (unsigned int)j; k = (unsigned int)(k - 1) )
      {
        v38 = k;
        if ( a6[k].BandId != v46 )
        {
          v39 = *(_OWORD *)a6[k].Bssid;
          v40 = *(_QWORD *)&a6[k].Channel;
          *(_OWORD *)a6[k].Bssid = *(_OWORD *)a6[j].Bssid;
          v41 = j;
          *(_QWORD *)&a6[v38].Channel = *(_QWORD *)&a6[j].Channel;
          *(_OWORD *)a6[v41].Bssid = v39;
          *(_QWORD *)&a6[v41].Channel = v40;
          break;
        }
      }
    }
  }
  v48 = 0;
  v16 = this->__vftable;
  memset(v47, 0, sizeof(v47));
  v16->GetSSID(this, (_DOT11_SSID *)v47);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q_MAC__SSID_Dddddd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)this + 444,
      v17,
      v18,
      v42,
      (char)this,
      (__int64)this->m_BssID,
      (__int64)v47,
      this->m_BssEntryShortSsid,
      v8,
      a2,
      v7,
      this->m_NumIncomingNeighborBssLinks,
      this->m_NumOutgoingNeighborBssLinks);
  *a5 = v8;
  return v7;
}

```

## disassembly

```asm
0x14000dc90  push    rbx
0x14000dc92  push    rbp
0x14000dc93  push    rsi
0x14000dc94  push    rdi
0x14000dc95  push    r12
0x14000dc97  push    r13
0x14000dc99  push    r14
0x14000dc9b  push    r15
0x14000dc9d  sub     rsp, 0D8h
0x14000dca4  mov     rax, cs:__security_cookie
0x14000dcab  xor     rax, rsp
0x14000dcae  mov     [rsp+118h+var_58], rax
0x14000dcb6  mov     rax, [rsp+118h+arg_20]
0x14000dcbe  mov     rbx, rcx
0x14000dcc1  mov     rsi, [rsp+118h+arg_28]
0x14000dcc9  xor     r15d, r15d
0x14000dccc  mov     ecx, [rcx+20Ch]; enum _WDI_BAND_ID
0x14000dcd2  xor     edi, edi
0x14000dcd4  mov     [rsp+118h+var_88], rax
0x14000dcdc  mov     [rsp+118h+var_98], r9b
0x14000dce4  mov     [rsp+118h+var_90], edx
0x14000dceb  call    ?MapBandID@CWabiToDot11Converter@@SA?AW4_DOT11_BAND_ID@@W4_WDI_BAND_ID@@@Z; CWabiToDot11Converter::MapBandID(_WDI_BAND_ID)
0x14000dcf0  mov     ebp, [rbx+21Ch]
0x14000dcf6  mov     r8d, [rbx+210h]
0x14000dcfd  mov     [rsp+118h+var_8C], eax
0x14000dd04  mov     [rsp+118h+var_94], r8d
0x14000dd0c  test    ebp, ebp
0x14000dd0e  jnz     loc_14000DE03
0x14000dd14  mov     r10d, [rbx+228h]
0x14000dd1b  test    r10d, r10d
0x14000dd1e  jnz     loc_14000DF8D
0x14000dd24  xor     edx, edx
0x14000dd26  test    edi, edi
0x14000dd28  jnz     loc_14000E200
0x14000dd2e  xor     eax, eax
0x14000dd30  lea     rdx, [rsp+118h+var_80]
0x14000dd38  mov     [rsp+118h+var_60], eax
0x14000dd3f  xorps   xmm0, xmm0
0x14000dd42  mov     rax, [rbx]
0x14000dd45  mov     rcx, rbx
0x14000dd48  movups  [rsp+118h+var_80], xmm0
0x14000dd50  movups  [rsp+118h+var_70], xmm0
0x14000dd58  mov     rax, [rax+10h]
0x14000dd5c  call    _guard_dispatch_icall
0x14000dd61  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000dd68  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000dd6f  jz      short loc_14000DDD1
0x14000dd71  mov     eax, [rbx+21Ch]
0x14000dd77  lea     rdx, [rbx+1BCh]
0x14000dd7e  mov     ecx, [rbx+210h]
0x14000dd84  mov     [rsp+118h+var_B0], eax
0x14000dd88  mov     eax, [rbx+228h]
0x14000dd8e  mov     [rsp+118h+var_B8], eax
0x14000dd92  mov     eax, [rsp+118h+var_90]
0x14000dd99  mov     dword ptr [rsp+118h+var_C0], r15d
0x14000dd9e  mov     [rsp+118h+var_C8], eax
0x14000dda2  lea     rax, [rsp+118h+var_80]
0x14000ddaa  mov     [rsp+118h+var_D0], edi
0x14000ddae  mov     [rsp+118h+var_D8], ecx
0x14000ddb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ddb9  mov     [rsp+118h+var_E0], rax
0x14000ddbe  mov     [rsp+118h+var_E8], rdx
0x14000ddc3  mov     [rsp+118h+var_F0], rbx
0x14000ddc8  mov     rcx, [rcx+40h]
0x14000ddcc  call    WPP_RECORDER_SF_q_MAC__SSID_Dddddd
0x14000ddd1  mov     rax, [rsp+118h+var_88]
0x14000ddd9  mov     [rax], edi
0x14000dddb  mov     eax, r15d
0x14000ddde  mov     rcx, [rsp+118h+var_58]
0x14000dde6  xor     rcx, rsp; StackCookie
0x14000dde9  call    __security_check_cookie
0x14000ddee  add     rsp, 0D8h
0x14000ddf5  pop     r15
0x14000ddf7  pop     r14
0x14000ddf9  pop     r13
0x14000ddfb  pop     r12
0x14000ddfd  pop     rdi
0x14000ddfe  pop     rsi
0x14000ddff  pop     rbp
0x14000de00  pop     rbx
0x14000de01  retn
0x14000de03  xor     r14d, r14d
0x14000de06  mov     r11, [rbx+220h]
0x14000de0d  lea     r10, [r14+r14*4]
0x14000de11  xor     eax, eax
0x14000de13  movzx   r9d, r9b
0x14000de17  mov     r13d, [r11+r10*8+1Ch]
0x14000de1c  lea     rcx, [r11+r10*8]
0x14000de20  movzx   r12d, word ptr [r11+r10*8+8]
0x14000de26  cmp     r13d, 5
0x14000de2a  cmovnz  r9d, eax
0x14000de2e  test    r12b, 4
0x14000de32  jnz     short loc_14000DE78
0x14000de34  test    byte ptr [rcx+0Ah], 40h
0x14000de38  jnz     short loc_14000DE78
0x14000de3a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000de41  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000de48  jnz     loc_14000DF14
0x14000de4e  mov     ebp, [rbx+21Ch]
0x14000de54  inc     r14d
0x14000de57  mov     edx, [rsp+118h+var_90]
0x14000de5e  mov     r8d, [rsp+118h+var_94]
0x14000de66  mov     r9b, [rsp+118h+var_98]
0x14000de6e  cmp     r14d, ebp
0x14000de71  jb      short loc_14000DE06
0x14000de73  jmp     loc_14000DD14
0x14000de78  test    r9b, r9b
0x14000de7b  jz      short loc_14000DE84
0x14000de7d  cmp     [r11+r10*8+18h], r8d
0x14000de82  jnz     short loc_14000DE3A
0x14000de84  cmp     edi, edx
0x14000de86  jnb     loc_14000DF0C
0x14000de8c  movups  xmm0, xmmword ptr [r11+r10*8+10h]
0x14000de92  lea     rcx, [rdi+rdi*2]
0x14000de96  inc     edi
0x14000de98  movups  xmmword ptr [rsi+rcx*8], xmm0
0x14000de9c  movsd   xmm1, qword ptr [r11+r10*8+20h]
0x14000dea3  movsd   qword ptr [rsi+rcx*8+10h], xmm1
0x14000dea9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000deb0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000deb7  jz      short loc_14000DF0C
0x14000deb9  mov     rcx, [rbx+220h]
0x14000dec0  mov     r9d, 0EBh
0x14000dec6  mov     eax, [rcx+r10*8+20h]
0x14000decb  lea     rdx, [rcx+10h]
0x14000decf  mov     [rsp+118h+var_C8], eax
0x14000ded3  lea     rdx, [rdx+r10*8]
0x14000ded7  mov     eax, [rcx+r10*8+1Ch]
0x14000dedc  mov     [rsp+118h+var_D0], eax
0x14000dee0  mov     eax, [rcx+r10*8+18h]
0x14000dee5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000deec  mov     [rsp+118h+var_D8], eax
0x14000def0  mov     eax, [rbx+21Ch]
0x14000def6  mov     [rsp+118h+var_E0], rdx
0x14000defb  mov     rcx, [rcx+40h]
0x14000deff  mov     dword ptr [rsp+118h+var_E8], eax
0x14000df03  mov     dword ptr [rsp+118h+var_F0], edi
0x14000df07  call    WPP_RECORDER_SF_dd_MAC_Ddd
0x14000df0c  inc     r15d
0x14000df0f  jmp     loc_14000DE4E
0x14000df14  movzx   r8d, byte ptr [rcx+0Ah]
0x14000df19  lea     rdx, [r11+10h]
0x14000df1d  mov     eax, [r11+r10*8+20h]
0x14000df22  lea     rdx, [rdx+r10*8]
0x14000df26  mov     [rsp+118h+var_A8], eax
0x14000df2a  mov     eax, [r11+r10*8+18h]
0x14000df2f  mov     [rsp+118h+var_B0], r13d
0x14000df34  mov     [rsp+118h+var_B8], eax
0x14000df38  mov     eax, [rsp+118h+var_94]
0x14000df3f  mov     [rsp+118h+var_C0], rdx
0x14000df44  mov     [rsp+118h+var_C8], eax
0x14000df48  movzx   ecx, r9b
0x14000df4c  mov     r9d, 0EAh
0x14000df52  shr     r8d, 6
0x14000df56  shr     r12d, 2
0x14000df5a  and     r8d, 1
0x14000df5e  mov     [rsp+118h+var_D0], r8d
0x14000df63  and     r12d, 1
0x14000df67  mov     [rsp+118h+var_D8], r12d
0x14000df6c  mov     dword ptr [rsp+118h+var_E0], ecx
0x14000df70  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df77  mov     dword ptr [rsp+118h+var_E8], ebp
0x14000df7b  mov     dword ptr [rsp+118h+var_F0], edi
0x14000df7f  mov     rcx, [rcx+40h]
0x14000df83  call    WPP_RECORDER_SF_ddDDDD_MAC_Ddd
0x14000df88  jmp     loc_14000DE4E
0x14000df8d  xor     ebp, ebp
0x14000df8f  mov     r11, [rbx+230h]
0x14000df96  lea     r12, ds:0[rbp*4]
0x14000df9e  add     r12, rbp
0x14000dfa1  movzx   r9d, r9b
0x14000dfa5  xor     eax, eax
0x14000dfa7  lea     rcx, [r11+r12*8]
0x14000dfab  mov     r13d, [rcx+1Ch]
0x14000dfaf  cmp     r13d, 5
0x14000dfb3  movzx   r14d, word ptr [rcx+8]
0x14000dfb8  cmovnz  r9d, eax
0x14000dfbc  test    r14b, 4
0x14000dfc0  jnz     short loc_14000DFC8
0x14000dfc2  test    byte ptr [rcx+0Ah], 40h
0x14000dfc6  jz      short loc_14000DFDB
0x14000dfc8  test    r9b, r9b
0x14000dfcb  jz      loc_14000E06A
0x14000dfd1  cmp     [rcx+18h], r8d
0x14000dfd5  jz      loc_14000E06A
0x14000dfdb  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000dfe2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000dfe9  jz      loc_14000E1D9
0x14000dfef  mov     eax, [r11+r12*8+20h]
0x14000dff4  lea     rdx, [r11+10h]
0x14000dff8  movzx   r8d, byte ptr [r11+r12*8+0Ah]
0x14000dffe  lea     rdx, [rdx+r12*8]
0x14000e002  mov     [rsp+118h+var_A8], eax
0x14000e006  mov     eax, [r11+r12*8+18h]
0x14000e00b  mov     [rsp+118h+var_B0], r13d
0x14000e010  mov     [rsp+118h+var_B8], eax
0x14000e014  mov     eax, [rsp+118h+var_94]
0x14000e01b  mov     [rsp+118h+var_C0], rdx
0x14000e020  mov     [rsp+118h+var_C8], eax
0x14000e024  movzx   ecx, r9b
0x14000e028  mov     r9d, 0ECh
0x14000e02e  shr     r8d, 6
0x14000e032  shr     r14d, 2
0x14000e036  and     r8d, 1
0x14000e03a  mov     [rsp+118h+var_D0], r8d
0x14000e03f  and     r14d, 1
0x14000e043  mov     [rsp+118h+var_D8], r14d
0x14000e048  mov     dword ptr [rsp+118h+var_E0], ecx
0x14000e04c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e053  mov     dword ptr [rsp+118h+var_E8], r10d
0x14000e058  mov     dword ptr [rsp+118h+var_F0], edi
0x14000e05c  mov     rcx, [rcx+40h]
0x14000e060  call    WPP_RECORDER_SF_ddDDDD_MAC_Ddd
0x14000e065  jmp     loc_14000E1D9
0x14000e06a  xor     r14d, r14d
0x14000e06d  cmp     r14d, edi
0x14000e070  jnb     loc_14000E12C
0x14000e076  mov     rax, [rbx+230h]
0x14000e07d  lea     rcx, ds:0[rbp*4]
0x14000e085  add     rcx, 2
0x14000e089  mov     r8d, 6; Length
0x14000e08f  add     rcx, rbp
0x14000e092  lea     rdx, [rax+rcx*8]; Source2
0x14000e096  lea     rcx, [r14+r14*2]
0x14000e09a  lea     rcx, [rsi+rcx*8]; Source1
0x14000e09e  call    cs:__imp_RtlCompareMemory
0x14000e0a5  nop     dword ptr [rax+rax+00h]
0x14000e0aa  cmp     rax, 6
0x14000e0ae  jz      short loc_14000E0B5
0x14000e0b0  inc     r14d
0x14000e0b3  jmp     short loc_14000E06D
0x14000e0b5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000e0bc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000e0c3  jz      loc_14000E1D9
0x14000e0c9  mov     rcx, [rbx+230h]
0x14000e0d0  lea     r8, ds:0[rbp*4]
0x14000e0d8  add     r8, rbp
0x14000e0db  mov     r9d, 0EDh
0x14000e0e1  lea     rdx, [rcx+10h]
0x14000e0e5  mov     eax, [rcx+r8*8+20h]
0x14000e0ea  lea     rdx, [rdx+r8*8]
0x14000e0ee  mov     [rsp+118h+var_C8], eax
0x14000e0f2  mov     eax, [rcx+r8*8+1Ch]
0x14000e0f7  mov     [rsp+118h+var_D0], eax
0x14000e0fb  mov     eax, [rcx+r8*8+18h]
0x14000e100  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e107  mov     [rsp+118h+var_D8], eax
0x14000e10b  mov     eax, [rbx+228h]
0x14000e111  mov     [rsp+118h+var_E0], rdx
0x14000e116  mov     rcx, [rcx+40h]
0x14000e11a  mov     dword ptr [rsp+118h+var_E8], eax
0x14000e11e  mov     dword ptr [rsp+118h+var_F0], edi
0x14000e122  call    WPP_RECORDER_SF_dd_MAC_Ddd
0x14000e127  jmp     loc_14000E1D9
0x14000e12c  cmp     edi, [rsp+118h+var_90]
0x14000e133  jnb     loc_14000E1D6
0x14000e139  mov     rdx, [rbx+230h]
0x14000e140  lea     rcx, [rdi+rdi*2]
0x14000e144  lea     r8, ds:0[rbp*4]
0x14000e14c  add     r8, rbp
0x14000e14f  inc     edi
0x14000e151  movups  xmm0, xmmword ptr [rdx+r8*8+10h]
0x14000e157  movups  xmmword ptr [rsi+rcx*8], xmm0
0x14000e15b  movsd   xmm1, qword ptr [rdx+r8*8+20h]
0x14000e162  movsd   qword ptr [rsi+rcx*8+10h], xmm1
0x14000e168  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000e16f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000e176  jz      short loc_14000E1D6
0x14000e178  mov     rcx, [rbx+230h]
0x14000e17f  lea     r8, ds:0[rbp*4]
0x14000e187  add     r8, rbp
0x14000e18a  mov     r9d, 0EEh
0x14000e190  lea     rdx, [rcx+10h]
0x14000e194  mov     eax, [rcx+r8*8+20h]
0x14000e199  lea     rdx, [rdx+r8*8]
0x14000e19d  mov     [rsp+118h+var_C8], eax
0x14000e1a1  mov     eax, [rcx+r8*8+1Ch]
0x14000e1a6  mov     [rsp+118h+var_D0], eax
0x14000e1aa  mov     eax, [rcx+r8*8+18h]
0x14000e1af  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e1b6  mov     [rsp+118h+var_D8], eax
0x14000e1ba  mov     eax, [rbx+228h]
0x14000e1c0  mov     [rsp+118h+var_E0], rdx
0x14000e1c5  mov     rcx, [rcx+40h]
0x14000e1c9  mov     dword ptr [rsp+118h+var_E8], eax
0x14000e1cd  mov     dword ptr [rsp+118h+var_F0], edi
0x14000e1d1  call    WPP_RECORDER_SF_dd_MAC_Ddd
0x14000e1d6  inc     r15d
0x14000e1d9  mov     r10d, [rbx+228h]
0x14000e1e0  inc     ebp
0x14000e1e2  mov     r8d, [rsp+118h+var_94]
0x14000e1ea  mov     r9b, [rsp+118h+var_98]
0x14000e1f2  cmp     ebp, r10d
0x14000e1f5  jb      loc_14000DF8F
0x14000e1fb  jmp     loc_14000DD24
0x14000e200  mov     r9d, [rsp+118h+var_8C]
0x14000e208  lea     rcx, [rdx+rdx*2]
0x14000e20c  cmp     [rsi+rcx*8+0Ch], r9d
0x14000e211  jnz     short loc_14000E25D
0x14000e213  lea     ecx, [rdi-1]
  ... truncated ...
```
