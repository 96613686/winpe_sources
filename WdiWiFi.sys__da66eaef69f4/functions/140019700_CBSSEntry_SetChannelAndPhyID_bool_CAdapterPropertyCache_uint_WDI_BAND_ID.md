# CBSSEntry::SetChannelAndPhyID(bool,CAdapterPropertyCache *,uint,_WDI_BAND_ID)

- ea: `0x140019700`
- end: `0x140019b5d`
- name: `?SetChannelAndPhyID@CBSSEntry@@QEAAX_NPEAVCAdapterPropertyCache@@IW4_WDI_BAND_ID@@@Z`
- size: `1117`
- prototype: `void(CBSSEntry *__hidden this, bool, struct CAdapterPropertyCache *, unsigned int, enum _WDI_BAND_ID)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140017b50`
- `0x1400b40f4`

## callees

- `0x140012150`
- `0x140012214`
- `0x140019700`
- `0x14001a0e8`
- `0x14001a3d0`
- `0x140034e04`
- `0x140034ec4`
- `0x14004c5b4`
- `0x14005360c`
- `0x140084f00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001987d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001987d`

## pseudocode

```c
void __fastcall CBSSEntry::SetChannelAndPhyID(
        CBSSEntry *this,
        unsigned int m_CachedChannelCenterFrequency,
        struct CAdapterPropertyCache *a3,
        unsigned int a4,
        enum _WDI_BAND_ID a5)
{
  unsigned int m_CachedChannelNumber; // r10d
  enum _WDI_BAND_ID v6; // eax
  char v8; // r11
  _WDI_BAND_ID m_CachedBandID; // r8d
  int BandCacheHelperForBandID; // eax
  int v12; // edx
  PVOID v13; // rdi
  unsigned int v14; // edx
  CBandCacheHelper *v15; // rcx
  int v16; // r8d
  int v17; // r9d
  unsigned int v18; // ecx
  bool v19; // al
  int dataLength; // edx
  unsigned __int16 v21; // ax
  unsigned __int8 *pBuffer; // r8
  int v23; // r8d
  int v24; // r9d
  int v25; // r8d
  unsigned __int8 *v26; // r15
  unsigned int Channel; // edx
  int v28; // [rsp+20h] [rbp-78h]
  void **v29; // [rsp+28h] [rbp-70h]
  PVOID P; // [rsp+60h] [rbp-38h] BYREF
  void *v31; // [rsp+A0h] [rbp+8h] BYREF

  m_CachedChannelNumber = this->m_CachedChannelNumber;
  v6 = a5;
  P = 0;
  v8 = m_CachedChannelCenterFrequency;
  this->m_BssChannelInfo.Channel = a4;
  this->m_BssChannelInfo.BandId = v6;
  if ( m_CachedChannelNumber == a4 )
  {
    m_CachedBandID = this->m_CachedBandID;
    if ( m_CachedBandID == v6 )
    {
      if ( m_CachedChannelNumber && (m_CachedChannelCenterFrequency = this->m_CachedChannelCenterFrequency) != 0 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(m_CachedChannelCenterFrequency) = 5;
          WPP_RECORDER_SF_ddddd(
            WPP_GLOBAL_Control->DeviceExtension,
            m_CachedChannelCenterFrequency,
            m_CachedBandID,
            64,
            (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
            m_CachedBandID,
            m_CachedChannelNumber,
            this->m_CachedDot11PhyID,
            this->m_CachedChannelCenterFrequency,
            this->m_CachedChannelInfoAvailable);
        }
        this->m_CachedChannelInfoAvailable = 1;
      }
      else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(m_CachedChannelCenterFrequency) = 2;
        WPP_RECORDER_SF_dddd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_WORD)m_CachedChannelCenterFrequency,
          m_CachedBandID,
          65,
          (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
          m_CachedBandID,
          m_CachedChannelNumber,
          this->m_CachedDot11PhyID,
          this->m_CachedChannelCenterFrequency);
      }
      return;
    }
  }
  dataLength = this->m_ProbeResponseFrameBody.dataLength;
  if ( this->m_CachedBandID == WDI_BAND_ID_60000 )
  {
    v23 = 2 - ((_WORD)dataLength != 0);
  }
  else
  {
    v21 = this->m_BeaconFrameBody.dataLength;
    if ( !(_WORD)dataLength )
    {
      if ( !v21 )
        goto LABEL_32;
      goto LABEL_26;
    }
    if ( !v21 )
    {
LABEL_30:
      pBuffer = this->m_ProbeResponseFrameBody.pBuffer;
      goto LABEL_31;
    }
    v23 = this->m_ProbeResponseTime > this->m_BeaconTime;
  }
  if ( v23 )
  {
    if ( v23 != 1 )
      goto LABEL_32;
    goto LABEL_30;
  }
LABEL_26:
  pBuffer = this->m_BeaconFrameBody.pBuffer;
  dataLength = this->m_BeaconFrameBody.dataLength;
LABEL_31:
  if ( pBuffer && (_WORD)dataLength )
  {
    if ( v8 )
    {
      if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine & 0x20) != 0 && a4 < 0xE )
      {
        LOBYTE(a5) = 0;
        v31 = 0;
        if ( !(unsigned int)Dot11GetInfoElementFromIEBlob(
                              pBuffer + 12,
                              (unsigned int)(unsigned __int16)dataLength - 12,
                              3u,
                              0,
                              (unsigned __int8 *)&a5,
                              &v31) )
        {
          v26 = (unsigned __int8 *)v31;
          if ( v31 )
          {
            if ( (_BYTE)a5 == WDI_BAND_ID_2400 )
            {
              Channel = this->m_BssChannelInfo.Channel;
              if ( Channel != *(unsigned __int8 *)v31 )
              {
                if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
                  && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
                {
                  LOBYTE(Channel) = 5;
                  WPP_RECORDER_SF_Ld(
                    WPP_GLOBAL_Control->DeviceExtension,
                    Channel,
                    v25,
                    67,
                    (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
                    this->m_BssChannelInfo.Channel,
                    *(_BYTE *)v31);
                }
                this->m_BssChannelInfo.Channel = *v26;
              }
            }
          }
        }
      }
    }
    BandCacheHelperForBandID = CAdapterPropertyCache::CreateBandCacheHelperForBandID(
                                 a3,
                                 this->m_BssChannelInfo.BandId,
                                 (struct CBandCacheHelper **)&P);
    v13 = P;
    if ( BandCacheHelperForBandID )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v24 = 68;
        goto LABEL_38;
      }
    }
    else
    {
      v14 = this->m_BssChannelInfo.Channel;
      v15 = (CBandCacheHelper *)P;
      this->m_CachedDot11PhyID = 0;
      BandCacheHelperForBandID = CBandCacheHelper::ConvertChannelNumberToFrequency(
                                   v15,
                                   v14,
                                   &this->m_CachedChannelCenterFrequency);
      if ( !BandCacheHelperForBandID )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          WPP_RECORDER_SF_dddddd(
            WPP_GLOBAL_Control->DeviceExtension,
            v12,
            v16,
            v17,
            v28,
            this->m_CachedBandID,
            this->m_BssChannelInfo.BandId,
            this->m_CachedChannelNumber,
            this->m_BssChannelInfo.Channel,
            this->m_CachedDot11PhyID,
            this->m_CachedChannelCenterFrequency);
        }
        v18 = this->m_BssChannelInfo.Channel;
        if ( v18 )
        {
          this->m_CachedBandID = this->m_BssChannelInfo.BandId;
          v19 = 1;
          this->m_CachedChannelNumber = v18;
        }
        else
        {
          v19 = 0;
        }
        this->m_CachedChannelInfoAvailable = v19;
        goto LABEL_20;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v24 = 69;
LABEL_38:
        LODWORD(v29) = BandCacheHelperForBandID;
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          1,
          v24,
          (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
          v29);
      }
    }
LABEL_20:
    if ( v13 )
      ExFreePoolWithTag(v13, 0x47696457u);
    return;
  }
LABEL_32:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(dataLength) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      dataLength,
      1,
      66,
      (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
  }
}

```

## disassembly

```asm
0x140019700  mov     [rsp+arg_10], rbx
0x140019705  push    rbp
0x140019706  push    rsi
0x140019707  push    rdi
0x140019708  push    r12
0x14001970a  push    r14
0x14001970c  sub     rsp, 70h
0x140019710  mov     r10d, [rcx+268h]
0x140019717  xor     r12d, r12d
0x14001971a  mov     eax, [rsp+98h+arg_20]
0x140019721  mov     rdi, r8
0x140019724  mov     [rsp+98h+P], r12
0x140019729  movzx   r11d, dl
0x14001972d  mov     [rcx+208h], r9d
0x140019734  mov     rbx, rcx
0x140019737  mov     [rcx+20Ch], eax
0x14001973d  cmp     r10d, r9d
0x140019740  jnz     loc_14001989E
0x140019746  mov     r8d, [rcx+26Ch]
0x14001974d  cmp     r8d, eax
0x140019750  jnz     loc_14001989E
0x140019756  test    r10d, r10d
0x140019759  jz      loc_1400199A0
0x14001975f  mov     edx, [rcx+278h]
0x140019765  test    edx, edx
0x140019767  jz      loc_1400199A0
0x14001976d  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140019774  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001977b  jz      short loc_140019799
0x14001977d  mov     rcx, cs:WPP_GLOBAL_Control
0x140019784  cmp     byte ptr [rcx+29h], 5
0x140019788  jnb     loc_140019A45
0x14001978e  cmp     [rcx+48h], r12w
0x140019793  jnz     loc_140019A45
0x140019799  mov     byte ptr [rbx+270h], 1
0x1400197a0  jmp     loc_140019889
0x1400197a5  test    dx, dx
0x1400197a8  jz      loc_1400198F7
0x1400197ae  mov     [rsp+98h+arg_8], r15
0x1400197b6  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400197bd  lea     rbp, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400197c4  test    r11b, r11b
0x1400197c7  jz      short loc_1400197D7
0x1400197c9  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+18h
0x1400197cf  test    al, 20h
0x1400197d1  jnz     loc_140019A8A
0x1400197d7  mov     edx, [rbx+20Ch]; unsigned int
0x1400197dd  lea     r8, [rsp+98h+P]; struct CBandCacheHelper **
0x1400197e2  mov     rcx, rdi; this
0x1400197e5  call    ?CreateBandCacheHelperForBandID@CAdapterPropertyCache@@QEAAHKPEAPEAVCBandCacheHelper@@@Z; CAdapterPropertyCache::CreateBandCacheHelperForBandID(ulong,CBandCacheHelper * *)
0x1400197ea  mov     rdi, [rsp+98h+P]
0x1400197ef  test    eax, eax
0x1400197f1  jnz     loc_14001998B
0x1400197f7  mov     edx, [rbx+208h]; unsigned int
0x1400197fd  lea     r8, [rbx+278h]; unsigned int *
0x140019804  mov     rcx, rdi; this
0x140019807  mov     [rbx+274h], r12d
0x14001980e  call    ?ConvertChannelNumberToFrequency@CBandCacheHelper@@QEAAHKPEAK@Z; CBandCacheHelper::ConvertChannelNumberToFrequency(ulong,ulong *)
0x140019813  test    eax, eax
0x140019815  jnz     loc_140019952
0x14001981b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140019822  jz      short loc_140019840
0x140019824  mov     rcx, cs:WPP_GLOBAL_Control
0x14001982b  cmp     byte ptr [rcx+29h], 5
0x14001982f  jnb     loc_1400199FB
0x140019835  cmp     [rcx+48h], r12w
0x14001983a  jnz     loc_1400199FB
0x140019840  mov     ecx, [rbx+208h]
0x140019846  test    ecx, ecx
0x140019848  jz      loc_140019B56
0x14001984e  mov     eax, [rbx+20Ch]
0x140019854  mov     [rbx+26Ch], eax
0x14001985a  mov     al, 1
0x14001985c  mov     [rbx+268h], ecx
0x140019862  mov     [rbx+270h], al
0x140019868  mov     r15, [rsp+98h+arg_8]
0x140019870  test    rdi, rdi
0x140019873  jz      short loc_140019889
0x140019875  mov     edx, 47696457h; Tag
0x14001987a  mov     rcx, rdi; P
0x14001987d  call    cs:__imp_ExFreePoolWithTag
0x140019884  nop     dword ptr [rax+rax+00h]
0x140019889  mov     rbx, [rsp+98h+arg_10]
0x140019891  add     rsp, 70h
0x140019895  pop     r14
0x140019897  pop     r12
0x140019899  pop     rdi
0x14001989a  pop     rsi
0x14001989b  pop     rbp
0x14001989c  retn
0x14001989e  cmp     dword ptr [rcx+26Ch], 3
0x1400198a5  movzx   edx, word ptr [rcx+1D8h]
0x1400198ac  jz      short loc_1400198CF
0x1400198ae  movzx   eax, word ptr [rcx+1F0h]
0x1400198b5  test    dx, dx
0x1400198b8  jnz     short loc_140019936
0x1400198ba  test    ax, ax
0x1400198bd  jz      short loc_1400198F7
0x1400198bf  mov     r8, [rcx+1F8h]
0x1400198c6  movzx   edx, word ptr [rcx+1F0h]
0x1400198cd  jmp     short loc_1400198EE
0x1400198cf  movzx   eax, dx
0x1400198d2  neg     ax
0x1400198d5  sbb     r8d, r8d
0x1400198d8  add     r8d, 2
0x1400198dc  test    r8d, r8d
0x1400198df  jz      short loc_1400198BF
0x1400198e1  cmp     r8d, 1
0x1400198e5  jnz     short loc_1400198F7
0x1400198e7  mov     r8, [rcx+1E0h]
0x1400198ee  test    r8, r8
0x1400198f1  jnz     loc_1400197A5
0x1400198f7  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400198fe  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140019905  jz      short loc_140019889
0x140019907  mov     rcx, cs:WPP_GLOBAL_Control
0x14001990e  lea     rbp, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x140019915  mov     r9d, 42h ; 'B'
0x14001991b  mov     [rsp+98h+var_78], rbp
0x140019920  mov     r8d, 1
0x140019926  mov     dl, 2
0x140019928  mov     rcx, [rcx+40h]
0x14001992c  call    WPP_RECORDER_SF_
0x140019931  jmp     loc_140019889
0x140019936  test    ax, ax
0x140019939  jz      short loc_1400198E7
0x14001993b  mov     rax, [rcx+200h]
0x140019942  mov     r8d, r12d
0x140019945  cmp     [rcx+1E8h], rax
0x14001994c  setnbe  r8b
0x140019950  jmp     short loc_1400198DC
0x140019952  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140019959  jz      loc_140019868
0x14001995f  mov     r9d, 45h ; 'E'
0x140019965  mov     rcx, cs:WPP_GLOBAL_Control
0x14001996c  mov     r8d, 1
0x140019972  mov     dword ptr [rsp+98h+var_70], eax
0x140019976  mov     dl, 2
0x140019978  mov     [rsp+98h+var_78], rbp
0x14001997d  mov     rcx, [rcx+40h]
0x140019981  call    WPP_RECORDER_SF_D
0x140019986  jmp     loc_140019868
0x14001998b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140019992  jz      loc_140019868
0x140019998  mov     r9d, 44h ; 'D'
0x14001999e  jmp     short loc_140019965
0x1400199a0  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400199a7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400199ae  jz      loc_140019889
0x1400199b4  mov     eax, [rcx+278h]
0x1400199ba  lea     rbp, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400199c1  mov     [rsp+98h+var_58], eax
0x1400199c5  mov     r9d, 41h ; 'A'
0x1400199cb  mov     eax, [rcx+274h]
0x1400199d1  mov     dl, 2
0x1400199d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400199da  mov     [rsp+98h+var_60], eax
0x1400199de  mov     [rsp+98h+var_68], r10d
0x1400199e3  mov     dword ptr [rsp+98h+var_70], r8d
0x1400199e8  mov     rcx, [rcx+40h]
0x1400199ec  mov     [rsp+98h+var_78], rbp
0x1400199f1  call    WPP_RECORDER_SF_dddd
0x1400199f6  jmp     loc_140019889
0x1400199fb  mov     eax, [rbx+278h]
0x140019a01  mov     rcx, [rcx+40h]
0x140019a05  mov     [rsp+98h+var_48], eax
0x140019a09  mov     eax, [rbx+274h]
0x140019a0f  mov     [rsp+98h+var_50], eax
0x140019a13  mov     eax, [rbx+208h]
0x140019a19  mov     [rsp+98h+var_58], eax
0x140019a1d  mov     eax, [rbx+268h]
0x140019a23  mov     [rsp+98h+var_60], eax
0x140019a27  mov     eax, [rbx+20Ch]
0x140019a2d  mov     [rsp+98h+var_68], eax
0x140019a31  mov     eax, [rbx+26Ch]
0x140019a37  mov     dword ptr [rsp+98h+var_70], eax
0x140019a3b  call    WPP_RECORDER_SF_dddddd
0x140019a40  jmp     loc_140019840
0x140019a45  movzx   eax, byte ptr [rbx+270h]
0x140019a4c  lea     rbp, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x140019a53  mov     rcx, [rcx+40h]
0x140019a57  mov     r9d, 40h ; '@'
0x140019a5d  mov     [rsp+98h+var_50], eax
0x140019a61  mov     eax, [rbx+274h]
0x140019a67  mov     [rsp+98h+var_58], edx
0x140019a6b  mov     dl, 5
0x140019a6d  mov     [rsp+98h+var_60], eax
0x140019a71  mov     [rsp+98h+var_68], r10d
0x140019a76  mov     dword ptr [rsp+98h+var_70], r8d
0x140019a7b  mov     [rsp+98h+var_78], rbp
0x140019a80  call    WPP_RECORDER_SF_ddddd
0x140019a85  jmp     loc_140019799
0x140019a8a  cmp     r9d, 0Eh
0x140019a8e  jnb     loc_1400197D7
0x140019a94  lea     rax, [rsp+98h+arg_0]
0x140019a9c  movzx   edx, dx
0x140019a9f  mov     [rsp+98h+var_70], rax; void **
0x140019aa4  lea     rcx, [r8+0Ch]; unsigned __int8 *
0x140019aa8  lea     rax, [rsp+98h+arg_20]
0x140019ab0  mov     byte ptr [rsp+98h+arg_20], r12b
0x140019ab8  sub     edx, 0Ch; unsigned int
0x140019abb  mov     [rsp+98h+var_78], rax; unsigned __int8 *
0x140019ac0  xor     r9d, r9d; unsigned int
0x140019ac3  mov     [rsp+98h+arg_0], r12
0x140019acb  mov     r8b, 3; unsigned __int8
0x140019ace  call    ?Dot11GetInfoElementFromIEBlob@@YAHPEAEKEK0PEAPEAX@Z; Dot11GetInfoElementFromIEBlob(uchar *,ulong,uchar,ulong,uchar *,void * *)
0x140019ad3  test    eax, eax
0x140019ad5  jnz     loc_1400197D7
0x140019adb  mov     r15, [rsp+98h+arg_0]
0x140019ae3  test    r15, r15
0x140019ae6  jz      loc_1400197D7
0x140019aec  cmp     byte ptr [rsp+98h+arg_20], 1
0x140019af4  jnz     loc_1400197D7
0x140019afa  movzx   eax, byte ptr [r15]
0x140019afe  mov     edx, [rbx+208h]
0x140019b04  cmp     edx, eax
0x140019b06  jz      loc_1400197D7
0x140019b0c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140019b13  jz      short loc_140019B47
0x140019b15  mov     rcx, cs:WPP_GLOBAL_Control
0x140019b1c  cmp     byte ptr [rcx+29h], 5
0x140019b20  jnb     short loc_140019B29
0x140019b22  cmp     [rcx+48h], r12w
0x140019b27  jz      short loc_140019B47
0x140019b29  mov     rcx, [rcx+40h]
0x140019b2d  mov     r9d, 43h ; 'C'
0x140019b33  mov     [rsp+98h+var_68], eax
0x140019b37  mov     dword ptr [rsp+98h+var_70], edx
0x140019b3b  mov     dl, 5
0x140019b3d  mov     [rsp+98h+var_78], rbp
0x140019b42  call    WPP_RECORDER_SF_Ld
0x140019b47  movzx   eax, byte ptr [r15]
0x140019b4b  mov     [rbx+208h], eax
0x140019b51  jmp     loc_1400197D7
0x140019b56  xor     al, al
0x140019b58  jmp     loc_140019862
```
