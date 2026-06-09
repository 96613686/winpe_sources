# CBssidConnectHistory::AddEntry(uchar const (&)[6],ulong,_GUID const &)

- ea: `0x1400d63f4`
- end: `0x1400d6777`
- name: `?AddEntry@CBssidConnectHistory@@QEAAXAEAY05$$CBEKAEBU_GUID@@@Z`
- size: `899`
- prototype: `void(CBssidConnectHistory *__hidden this, const unsigned __int8 (*)[6], unsigned int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400143d8`

## callees

- `0x14000187c`
- `0x1400175f8`
- `0x140072bfc`
- `0x14007e5dc`
- `0x1400d63f4`
- `0x1400d6afc`
- `0x1400da740`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400d6756`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d6756`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d644c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d644c`

## pseudocode

```c
void __fastcall CBssidConnectHistory::AddEntry(
        CBssidConnectHistory *this,
        const unsigned __int8 (*a2)[6],
        unsigned int a3,
        const struct _GUID *a4)
{
  CNdisSpinLock *m_ConnectHistoryLock; // rbx
  _BSSID_CONNECT_HISTORY_ENTRY *v8; // r13
  int v9; // edi
  int v10; // r15d
  int v11; // edx
  int v12; // r8d
  unsigned int m_maxAPsToTrack; // r9d
  unsigned int i; // edx
  _BSSID_CONNECT_HISTORY_ENTRY *v15; // r8
  __int64 v16; // r8
  unsigned __int8 *v17; // rdi
  unsigned int m_maxConnectAttempts; // ecx
  unsigned int v19; // r13d
  unsigned int v20; // r15d
  unsigned int v21; // esi
  unsigned int v22; // eax
  unsigned int m_linkQualityThreshold; // ecx
  unsigned int m_maxLinkQualityDeviation; // edx
  int v25; // ecx
  __int64 v26; // r8
  int v27; // r9d
  void *v28; // rcx
  size_t v29; // r8
  const unsigned __int8 *v30; // rdx
  KIRQL OldIrql; // dl
  int v32; // [rsp+20h] [rbp-79h]
  char v33; // [rsp+70h] [rbp-29h]
  unsigned int v34; // [rsp+74h] [rbp-25h] BYREF
  unsigned int v35; // [rsp+78h] [rbp-21h] BYREF
  unsigned int v36; // [rsp+7Ch] [rbp-1Dh] BYREF
  unsigned int v37; // [rsp+80h] [rbp-19h] BYREF
  __int64 v38; // [rsp+88h] [rbp-11h] BYREF
  __int64 v39; // [rsp+90h] [rbp-9h] BYREF
  __int64 v40; // [rsp+98h] [rbp-1h] BYREF
  __int64 v41; // [rsp+A0h] [rbp+7h] BYREF
  const struct _GUID *v42; // [rsp+A8h] [rbp+Fh] BYREF

  if ( *(_DWORD *)a2 || *(_WORD *)&(*a2)[4] )
  {
    m_ConnectHistoryLock = this->m_ConnectHistoryLock;
    v8 = 0;
    v33 = 0;
    v9 = -1;
    v10 = 0;
    m_ConnectHistoryLock->m_SpinLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&m_ConnectHistoryLock->m_SpinLock.SpinLock);
    m_ConnectHistoryLock->m_IsLocked = 1;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 4;
      WPP_RECORDER_SF__MAC_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        v12,
        11,
        (__int64)WPP_4c31500d7fc33260ec18d0c44376088e_Traceguids,
        (__int64)a2,
        a3);
    }
    m_maxAPsToTrack = this->m_maxAPsToTrack;
    for ( i = 0; i < m_maxAPsToTrack; ++i )
    {
      v15 = &this->m_bssidMRU[i];
      if ( v15->isValid )
      {
        if ( *(_DWORD *)a2 == *(_DWORD *)v15->bssid && *(_WORD *)&(*a2)[4] == *(_WORD *)&v15->bssid[4] )
        {
          v9 = i;
          v33 = 1;
          break;
        }
        if ( v9 == -1 && (!v8 || v8->connectTimes[0].time > v15->connectTimes[0].time) )
        {
          v8 = &this->m_bssidMRU[i];
          v10 = i;
        }
      }
      else if ( v9 == -1 )
      {
        v9 = i;
      }
    }
    if ( v9 != -1 )
      v10 = v9;
    v16 = 168LL * v10;
    v38 = v16;
    v17 = (unsigned __int8 *)this + v16;
    if ( v33 )
    {
      m_maxConnectAttempts = this->m_maxConnectAttempts;
      v19 = 0;
      v20 = a3;
      v21 = a3;
      while ( v19 < m_maxConnectAttempts )
      {
        if ( !v17[16 * v19 + 12] )
          break;
        v22 = *(_DWORD *)&v17[16 * v19++ + 8];
        if ( v22 )
        {
          if ( v22 >= v20 )
          {
            if ( v22 > v21 )
              v21 = v22;
          }
          else
          {
            v20 = v22;
          }
        }
      }
      m_linkQualityThreshold = this->m_linkQualityThreshold;
      if ( v20 <= m_linkQualityThreshold )
      {
        m_maxLinkQualityDeviation = this->m_maxLinkQualityDeviation;
        if ( v21 - v20 > m_maxLinkQualityDeviation )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_ddddd_MAC_(
              WPP_GLOBAL_Control->DeviceExtension,
              m_maxLinkQualityDeviation,
              v16,
              m_maxAPsToTrack,
              v32,
              v20,
              v21,
              a3,
              m_maxLinkQualityDeviation,
              m_linkQualityThreshold,
              (__int64)(v17 + 161));
            v16 = v38;
          }
          if ( (unsigned int)dword_1400F8758 > 5 )
          {
            if ( (unsigned __int8)tlgKeywordOn(&dword_1400F8758, 0x400000000000LL, v16) )
            {
              v34 = this->m_linkQualityThreshold;
              v35 = this->m_maxLinkQualityDeviation;
              v39 = *(_QWORD *)v17;
              v36 = a3;
              v37 = v21;
              LODWORD(v38) = v20;
              v40 = *(unsigned __int64 *)((char *)&this->m_bssidMRU[0].connectTimes[v19 - 1].time + v26);
              v41 = v19;
              v42 = a4;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v25,
                (unsigned int)byte_1400EF9D9,
                v26,
                v27,
                (__int64)&v42,
                (__int64)&v41,
                (__int64)&v40,
                (__int64)&v39,
                (__int64)&v38,
                (__int64)&v37,
                (__int64)&v36,
                (__int64)&v35,
                (__int64)&v34);
            }
          }
          memset(v17 + 16, 0, 0x90u);
          goto LABEL_44;
        }
      }
      v28 = v17 + 16;
      v29 = 144;
      v30 = v17;
    }
    else
    {
      if ( v17[160] )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(i) = 4;
          WPP_RECORDER_SF__MAC_(
            WPP_GLOBAL_Control->DeviceExtension,
            i,
            v16,
            13,
            (__int64)WPP_4c31500d7fc33260ec18d0c44376088e_Traceguids,
            (__int64)(v17 + 161));
        }
        memset(v17, 0, 0xA0u);
      }
      v28 = v17 + 161;
      v29 = 6;
      v30 = (const unsigned __int8 *)a2;
    }
    memmove(v28, v30, v29);
LABEL_44:
    v17[160] = 1;
    v17[12] = 1;
    *(_QWORD *)v17 = MEMORY[0xFFFFF78000000014];
    *((_DWORD *)v17 + 2) = a3;
    OldIrql = m_ConnectHistoryLock->m_SpinLock.OldIrql;
    m_ConnectHistoryLock->m_IsLocked = 0;
    KeReleaseSpinLock(&m_ConnectHistoryLock->m_SpinLock.SpinLock, OldIrql);
  }
}

```

## disassembly

```asm
0x1400d63f4  mov     [rsp-8+arg_18], r9
0x1400d63f9  push    rbp
0x1400d63fa  push    rbx
0x1400d63fb  push    rsi
0x1400d63fc  push    rdi
0x1400d63fd  push    r12
0x1400d63ff  push    r13
0x1400d6401  push    r14
0x1400d6403  push    r15
0x1400d6405  lea     rbp, [rsp-1Fh]
0x1400d640a  sub     rsp, 0B8h
0x1400d6411  mov     eax, cs:dword_1400EE954
0x1400d6417  mov     r12d, r8d
0x1400d641a  mov     rsi, rdx
0x1400d641d  mov     r14, rcx
0x1400d6420  cmp     eax, [rdx]
0x1400d6422  jnz     short loc_1400D6435
0x1400d6424  movzx   eax, cs:word_1400EE958
0x1400d642b  cmp     ax, [rdx+4]
0x1400d642f  jz      loc_1400D6762
0x1400d6435  mov     rbx, [rcx+2B8h]
0x1400d643c  xor     r13d, r13d
0x1400d643f  mov     rcx, rbx; SpinLock
0x1400d6442  mov     [rbp+57h+var_80], r13b
0x1400d6446  or      edi, 0FFFFFFFFh
0x1400d6449  xor     r15d, r15d
0x1400d644c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400d6453  nop     dword ptr [rax+rax+00h]
0x1400d6458  mov     [rbx+8], al
0x1400d645b  mov     byte ptr [rbx+10h], 1
0x1400d645f  lea     r11, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d6466  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x1400d646d  lea     r10, WPP_4c31500d7fc33260ec18d0c44376088e_Traceguids
0x1400d6474  jz      short loc_1400D64A9
0x1400d6476  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d647d  lea     r9d, [rdi+0Ch]
0x1400d6481  mov     dword ptr [rsp+0F0h+var_C0], r12d
0x1400d6486  mov     dl, 4
0x1400d6488  mov     [rsp+0F0h+var_C8], rsi
0x1400d648d  mov     [rsp+0F0h+var_D0], r10
0x1400d6492  mov     rcx, [rcx+40h]
0x1400d6496  call    WPP_RECORDER_SF__MAC_d
0x1400d649b  lea     r10, WPP_4c31500d7fc33260ec18d0c44376088e_Traceguids
0x1400d64a2  lea     r11, WPP_RECORDER_INITIALIZED
0x1400d64a9  mov     r9d, [r14+2A4h]
0x1400d64b0  xor     edx, edx
0x1400d64b2  test    r9d, r9d
0x1400d64b5  jz      short loc_1400D6516
0x1400d64b7  mov     eax, edx
0x1400d64b9  imul    r8, rax, 0A8h
0x1400d64c0  add     r8, r14
0x1400d64c3  cmp     byte ptr [r8+0A0h], 0
0x1400d64cb  jz      short loc_1400D6501
0x1400d64cd  mov     eax, [rsi]
0x1400d64cf  cmp     eax, [r8+0A1h]
0x1400d64d6  jnz     short loc_1400D64E6
0x1400d64d8  movzx   eax, word ptr [rsi+4]
0x1400d64dc  cmp     ax, [r8+0A5h]
0x1400d64e4  jz      short loc_1400D6510
0x1400d64e6  cmp     edi, 0FFFFFFFFh
0x1400d64e9  jnz     short loc_1400D6507
0x1400d64eb  test    r13, r13
0x1400d64ee  jz      short loc_1400D64F9
0x1400d64f0  mov     rax, [r8]
0x1400d64f3  cmp     [r13+0], rax
0x1400d64f7  jbe     short loc_1400D6507
0x1400d64f9  mov     r13, r8
0x1400d64fc  mov     r15d, edx
0x1400d64ff  jmp     short loc_1400D6507
0x1400d6501  cmp     edi, 0FFFFFFFFh
0x1400d6504  cmovz   edi, edx
0x1400d6507  inc     edx
0x1400d6509  cmp     edx, r9d
0x1400d650c  jb      short loc_1400D64B7
0x1400d650e  jmp     short loc_1400D6516
0x1400d6510  mov     edi, edx
0x1400d6512  mov     [rbp+57h+var_80], 1
0x1400d6516  cmp     edi, 0FFFFFFFFh
0x1400d6519  cmovnz  r15d, edi
0x1400d651d  movsxd  rax, r15d
0x1400d6520  imul    r8, rax, 0A8h
0x1400d6527  cmp     [rbp+57h+var_80], 0
0x1400d652b  mov     [rbp+57h+var_68], r8
0x1400d652f  lea     rdi, [r8+r14]
0x1400d6533  jz      loc_1400D66D0
0x1400d6539  mov     ecx, [r14+2A0h]
0x1400d6540  xor     r13d, r13d
0x1400d6543  mov     r15d, r12d
0x1400d6546  mov     esi, r12d
0x1400d6549  test    ecx, ecx
0x1400d654b  jz      short loc_1400D6579
0x1400d654d  mov     eax, r13d
0x1400d6550  add     rax, rax
0x1400d6553  cmp     byte ptr [rdi+rax*8+0Ch], 0
0x1400d6558  jz      short loc_1400D6579
0x1400d655a  mov     eax, [rdi+rax*8+8]
0x1400d655e  inc     r13d
0x1400d6561  test    eax, eax
0x1400d6563  jz      short loc_1400D6574
0x1400d6565  cmp     eax, r15d
0x1400d6568  jnb     short loc_1400D656F
0x1400d656a  mov     r15d, eax
0x1400d656d  jmp     short loc_1400D6574
0x1400d656f  cmp     eax, esi
0x1400d6571  cmova   esi, eax
0x1400d6574  cmp     r13d, ecx
0x1400d6577  jb      short loc_1400D654D
0x1400d6579  mov     ecx, [r14+2ACh]
0x1400d6580  cmp     r15d, ecx
0x1400d6583  ja      loc_1400D66C1
0x1400d6589  mov     edx, [r14+2A8h]
0x1400d6590  mov     eax, esi
0x1400d6592  sub     eax, r15d
0x1400d6595  cmp     eax, edx
0x1400d6597  jbe     loc_1400D66C1
0x1400d659d  cmp     cs:WPP_RECORDER_INITIALIZED, r11; __annotation("TMF:",
0x1400d65a4  jz      short loc_1400D65DC
0x1400d65a6  lea     rax, [rdi+0A1h]
0x1400d65ad  mov     [rsp+0F0h+var_A0], rax
0x1400d65b2  mov     dword ptr [rsp+0F0h+var_A8], ecx
0x1400d65b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d65bd  mov     dword ptr [rsp+0F0h+var_B0], edx
0x1400d65c1  mov     dword ptr [rsp+0F0h+var_B8], r12d
0x1400d65c6  mov     dword ptr [rsp+0F0h+var_C0], esi
0x1400d65ca  mov     rcx, [rcx+40h]
0x1400d65ce  mov     dword ptr [rsp+0F0h+var_C8], r15d
0x1400d65d3  call    WPP_RECORDER_SF_ddddd_MAC_
0x1400d65d8  mov     r8, [rbp+57h+var_68]
0x1400d65dc  mov     eax, cs:dword_1400F8758
0x1400d65e2  cmp     eax, 5
0x1400d65e5  jbe     loc_1400D66AE
0x1400d65eb  mov     rdx, 400000000000h
0x1400d65f5  lea     rcx, dword_1400F8758
0x1400d65fc  call    _tlgKeywordOn
0x1400d6601  test    al, al
0x1400d6603  jz      loc_1400D66AE
0x1400d6609  mov     eax, [r14+2ACh]
0x1400d6610  lea     rdx, byte_1400EF9D9
0x1400d6617  mov     [rbp+57h+var_7C], eax
0x1400d661a  mov     eax, [r14+2A8h]
0x1400d6621  mov     [rbp+57h+var_78], eax
0x1400d6624  mov     rax, [rdi]
0x1400d6627  mov     [rbp+57h+var_60], rax
0x1400d662b  lea     eax, [r13-1]
0x1400d662f  shl     rax, 4
0x1400d6633  add     rax, r8
0x1400d6636  mov     [rbp+57h+var_74], r12d
0x1400d663a  mov     [rbp+57h+var_70], esi
0x1400d663d  mov     dword ptr [rbp+57h+var_68], r15d
0x1400d6641  mov     rax, [rax+r14]
0x1400d6645  mov     [rbp+57h+var_58], rax
0x1400d6649  mov     eax, r13d
0x1400d664c  mov     [rbp+57h+var_50], rax
0x1400d6650  mov     rax, [rbp+57h+arg_18]
0x1400d6654  mov     [rbp+57h+var_48], rax
0x1400d6658  lea     rax, [rbp+57h+var_7C]
0x1400d665c  mov     [rsp+0F0h+var_90], rax
0x1400d6661  lea     rax, [rbp+57h+var_78]
0x1400d6665  mov     [rsp+0F0h+var_98], rax
0x1400d666a  lea     rax, [rbp+57h+var_74]
0x1400d666e  mov     [rsp+0F0h+var_A0], rax
0x1400d6673  lea     rax, [rbp+57h+var_70]
0x1400d6677  mov     [rsp+0F0h+var_A8], rax
0x1400d667c  lea     rax, [rbp+57h+var_68]
0x1400d6680  mov     [rsp+0F0h+var_B0], rax
0x1400d6685  lea     rax, [rbp+57h+var_60]
0x1400d6689  mov     [rsp+0F0h+var_B8], rax
0x1400d668e  lea     rax, [rbp+57h+var_58]
0x1400d6692  mov     [rsp+0F0h+var_C0], rax
0x1400d6697  lea     rax, [rbp+57h+var_50]
0x1400d669b  mov     [rsp+0F0h+var_C8], rax
0x1400d66a0  lea     rax, [rbp+57h+var_48]
0x1400d66a4  mov     [rsp+0F0h+var_D0], rax
0x1400d66a9  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapperByVal@$03@@5555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400d66ae  lea     rcx, [rdi+10h]; void *
0x1400d66b2  xor     edx, edx; Val
0x1400d66b4  mov     r8d, 90h; Size
0x1400d66ba  call    memset
0x1400d66bf  jmp     short loc_1400D6730
0x1400d66c1  lea     rcx, [rdi+10h]
0x1400d66c5  mov     r8d, 90h
0x1400d66cb  mov     rdx, rdi
0x1400d66ce  jmp     short loc_1400D672B
0x1400d66d0  cmp     byte ptr [rdi+0A0h], 0
0x1400d66d7  jz      short loc_1400D671B
0x1400d66d9  cmp     cs:WPP_RECORDER_INITIALIZED, r11; __annotation("TMF:",
0x1400d66e0  jz      short loc_1400D670B
0x1400d66e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d66e9  lea     rax, [rdi+0A1h]
0x1400d66f0  mov     [rsp+0F0h+var_C8], rax
0x1400d66f5  mov     r9d, 0Dh
0x1400d66fb  mov     dl, 4
0x1400d66fd  mov     [rsp+0F0h+var_D0], r10
0x1400d6702  mov     rcx, [rcx+40h]
0x1400d6706  call    WPP_RECORDER_SF__MAC_
0x1400d670b  xor     edx, edx; Val
0x1400d670d  mov     r8d, 0A0h; Size
0x1400d6713  mov     rcx, rdi; void *
0x1400d6716  call    memset
0x1400d671b  lea     rcx, [rdi+0A1h]; void *
0x1400d6722  mov     r8d, 6; Size
0x1400d6728  mov     rdx, rsi; Src
0x1400d672b  call    memmove
0x1400d6730  mov     byte ptr [rdi+0A0h], 1
0x1400d6737  mov     rcx, rbx; SpinLock
0x1400d673a  mov     byte ptr [rdi+0Ch], 1
0x1400d673e  mov     rax, ds:0FFFFF78000000014h
0x1400d6748  mov     [rdi], rax
0x1400d674b  mov     [rdi+8], r12d
0x1400d674f  mov     dl, [rbx+8]; NewIrql
0x1400d6752  mov     byte ptr [rbx+10h], 0
0x1400d6756  call    cs:__imp_KeReleaseSpinLock
0x1400d675d  nop     dword ptr [rax+rax+00h]
0x1400d6762  add     rsp, 0B8h
0x1400d6769  pop     r15
0x1400d676b  pop     r14
0x1400d676d  pop     r13
0x1400d676f  pop     r12
0x1400d6771  pop     rdi
0x1400d6772  pop     rsi
0x1400d6773  pop     rbx
0x1400d6774  pop     rbp
0x1400d6775  retn
```
