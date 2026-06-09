# CBSSListManager::AddNeighborAPsFromRnrInfo(CBSSEntry *,ulong,DOT11_RNR_NEIGHBOR *)

- ea: `0x1400500c0`
- end: `0x140050604`
- name: `?AddNeighborAPsFromRnrInfo@CBSSListManager@@QEAAHPEAVCBSSEntry@@KPEAUDOT11_RNR_NEIGHBOR@@@Z`
- size: `1348`
- prototype: `int(CBSSListManager *__hidden this, struct CBSSEntry *, unsigned int, struct DOT11_RNR_NEIGHBOR *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140017b50`

## callees

- `0x140017a90`
- `0x14004c5b4`
- `0x1400500c0`
- `0x14005060c`
- `0x14005069c`
- `0x140050998`
- `0x140050b04`
- `0x1400bd590`
- `0x1400bd6c4`
- `0x1400bda64`
- `0x1400da4f0`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140050281`
- `ntoskrnl!RtlCompareMemory` at `0x140050281`
- `ntoskrnl!ExAllocatePool2` at `0x140050126`
- `ntoskrnl!ExAllocatePool2` at `0x140050126`

## pseudocode

```c
__int64 __fastcall CBSSListManager::AddNeighborAPsFromRnrInfo(
        CBSSListManager *this,
        struct CBSSEntry *a2,
        unsigned int a3,
        struct DOT11_RNR_NEIGHBOR *a4)
{
  __int64 v7; // rax
  int v8; // r14d
  struct WDI_NEIGHBOR_BSS *Pool2; // rax
  unsigned int v10; // edx
  int v11; // r8d
  int v12; // r8d
  int v13; // r9d
  unsigned int m_BssEntryShortSsid; // edx
  char v15; // bl
  __int64 v16; // rcx
  unsigned __int8 *m_CountryString; // rax
  unsigned __int64 v18; // rdi
  __int32 v19; // eax
  int v20; // r8d
  char v21; // dl
  unsigned int uShortSsid; // r14d
  unsigned __int8 ucValue; // bl
  struct _DOT11_SSID *v24; // r8
  DOT11_TBTT_INFORMATION::<unnamed_type_Len1> *v25; // r9
  unsigned int i; // ecx
  int v27; // r9d
  __int64 result; // rax
  const char *v29; // rax
  int ChannelNumber; // r9d
  int v31; // edx
  int v32; // [rsp+20h] [rbp-100h]
  char v33; // [rsp+40h] [rbp-E0h]
  unsigned __int8 v34; // [rsp+A0h] [rbp-80h]
  int v35; // [rsp+A4h] [rbp-7Ch]
  unsigned int v36; // [rsp+A8h] [rbp-78h]
  union DOT11_MLD_PARAMETERS v37; // [rsp+B0h] [rbp-70h] BYREF
  __int32 v38; // [rsp+C0h] [rbp-60h]
  int v39; // [rsp+C4h] [rbp-5Ch]
  unsigned int v40; // [rsp+C8h] [rbp-58h]
  unsigned int v41; // [rsp+CCh] [rbp-54h]
  struct CBSSEntry *v42; // [rsp+D0h] [rbp-50h]
  _OWORD *v43; // [rsp+D8h] [rbp-48h]
  __int64 v44; // [rsp+E0h] [rbp-40h]
  CBSSListManager *v45; // [rsp+E8h] [rbp-38h]
  _OWORD v46[2]; // [rsp+F0h] [rbp-30h] BYREF
  int v47; // [rsp+110h] [rbp-10h]

  v45 = this;
  v47 = 0;
  v35 = 0;
  v7 = 40LL * a3;
  memset(v46, 0, sizeof(v46));
  v8 = 0;
  if ( !is_mul_ok(a3, 0x28u) )
    v7 = -1;
  Pool2 = (struct WDI_NEIGHBOR_BSS *)ExAllocatePool2(64, v7, 1198089303);
  if ( Pool2 )
  {
    v40 = 0;
    CBSSEntry::ReplaceOutgoingNeighborLinks(a2, v10, a3, Pool2);
    a2->GetSSID(a2, (_DOT11_SSID *)v46);
    m_BssEntryShortSsid = a2->m_BssEntryShortSsid;
    v41 = m_BssEntryShortSsid;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      WPP_RECORDER_SF_q_SSID_D_MAC_d(WPP_GLOBAL_Control->DeviceExtension, m_BssEntryShortSsid, v12, v13);
    }
    v15 = 0;
    v36 = 0;
    if ( a3 )
    {
      v16 = 0;
      m_CountryString = a2->m_CountryString;
      v44 = 0;
      do
      {
        v34 = 0;
        v18 = 5 * v16;
        *(_WORD *)((char *)&v38 + 1) = 0;
        v19 = ConvertCountryCodeOperatingClassToBand(m_CountryString, a4[v16].OperatingClass);
        v21 = *((_BYTE *)&a4[v18 / 5].TBTTInformationHeader.0 + 1);
        v38 = v19;
        if ( (unsigned __int8)(v21 - 8) <= 1u )
        {
          ucValue = a4[v18 / 5].TBTTInformation.Len8.BssParameters.ucValue;
          uShortSsid = 0;
          LOWORD(v39) = 0;
        }
        else if ( (unsigned __int8)(v21 - 12) > 1u )
        {
          if ( (unsigned __int8)v21 <= 0xFu )
          {
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v33 = v21;
              v31 = v8 + 1;
              LOBYTE(v31) = 2;
              WPP_RECORDER_SF_dddd(
                WPP_GLOBAL_Control->DeviceExtension,
                v31,
                v20,
                147,
                (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
                v8 + 1,
                v15 + 1,
                a3,
                v33);
            }
            goto LABEL_27;
          }
          uShortSsid = a4[v18 / 5].TBTTInformation.Len11.uShortSsid;
          ucValue = a4[v18 / 5].TBTTInformation.Len12.BssParameters.ucValue;
          v34 = a4[v18 / 5].TBTTInformation.Len16.MLDParameters.Value[0];
          v39 = *(unsigned __int16 *)((char *)&a4[v18 / 5].TBTTInformation.Len16.MLDParameters.0 + 1);
        }
        else
        {
          uShortSsid = a4[v18 / 5].TBTTInformation.Len11.uShortSsid;
          ucValue = a4[v18 / 5].TBTTInformation.Len12.BssParameters.ucValue;
          v39 = 0;
        }
        LODWORD(v24) = v41;
        v43 = 0;
        v25 = &a4[v18 / 5].TBTTInformation.Len1 + 1;
        v42 = (struct CBSSEntry *)v25;
        if ( v41 )
        {
          if ( (((a4[v18 / 5].TBTTInformationHeader.usValue & 4) == 0) & (unsigned __int8)~(ucValue >> 1)) != 0
            || uShortSsid )
          {
            if ( uShortSsid != v41 )
              goto LABEL_21;
          }
          else
          {
            uShortSsid = v41;
          }
          if ( LODWORD(v46[0]) )
          {
            for ( i = 0; i < LODWORD(v46[0]); ++i )
            {
              if ( *((_BYTE *)v46 + i + 4) )
              {
                v43 = v46;
                break;
              }
            }
          }
        }
LABEL_21:
        if ( !uShortSsid )
          goto LABEL_39;
        if ( RtlCompareMemory(&a4[v18 / 5].TBTTInformation.Len1 + 1, a2->m_BssID, 6u) == 6 )
        {
          v25 = (DOT11_TBTT_INFORMATION::<unnamed_type_Len1> *)v42;
LABEL_39:
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            WPP_RECORDER_SF_dddD_MAC_(
              WPP_GLOBAL_Control->DeviceExtension,
              v35 + 1,
              (_DWORD)v24,
              (_DWORD)v25,
              v32,
              v35 + 1,
              v36 + 1,
              a3,
              uShortSsid,
              (__int64)v25);
          }
          goto LABEL_26;
        }
        v37.Value[0] = v34;
        *(_WORD *)((char *)&v37.0 + 1) = v39;
        v42 = CBSSListManager::AddNeighborAP(
                v45,
                a2,
                v24,
                uShortSsid,
                a4[v18 / 5].TBTTInformationHeader,
                (union DOT11_BSS_PARAMETERS)ucValue,
                &v37,
                (unsigned __int8 (*)[6])a4[v18 / 5].TBTTInformation.Len7.Bssid,
                (enum _DOT11_BAND_ID)v38,
                a4[v18 / 5].ChannelNumber);
        if ( v42 )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            v29 = "Same";
            if ( !v43 )
              v29 = "None";
            ChannelNumber = a4[v18 / 5].ChannelNumber;
            WPP_RECORDER_SF_dddqqddDD_MAC_D_SSID__MAC_Ds(
              WPP_GLOBAL_Control->DeviceExtension,
              ucValue,
              a4[v18 / 5].TBTTInformationHeader.usValue,
              ChannelNumber,
              v32,
              v35 + 1,
              v36 + 1,
              a3,
              (char)a2,
              (char)v42,
              v38,
              ChannelNumber,
              a4[v18 / 5].TBTTInformationHeader.usValue,
              ucValue,
              (__int64)a2->m_BssID,
              a2->m_BssEntryShortSsid,
              (__int64)v46,
              (__int64)(&a4[v18 / 5].TBTTInformation.Len1 + 1),
              uShortSsid,
              (__int64)v29);
          }
          v8 = ++v35;
          goto LABEL_27;
        }
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dddD_MAC__MAC_(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)a4 + 5 + 4 * v18,
            0,
            v27,
            v32,
            v35 + 1,
            v36 + 1,
            a3,
            uShortSsid,
            (__int64)a2->m_BssID,
            (__int64)(&a4[v18 / 5].TBTTInformation.Len1 + 1));
LABEL_26:
        v8 = v35;
LABEL_27:
        v16 = v44 + 1;
        ++v36;
        ++v44;
        v15 = v36;
        m_CountryString = a2->m_CountryString;
      }
      while ( v36 < a3 );
    }
  }
  else
  {
    v40 = -1073741670;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        145,
        (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
        a3);
    }
  }
  result = 0;
  if ( !v8 )
    return v40;
  return result;
}

```

## disassembly

```asm
0x1400500c0  push    rbp
0x1400500c2  push    rbx
0x1400500c3  push    rsi
0x1400500c4  push    rdi
0x1400500c5  push    r12
0x1400500c7  push    r13
0x1400500c9  push    r14
0x1400500cb  push    r15
0x1400500cd  lea     rbp, [rsp-8]
0x1400500d2  sub     rsp, 128h
0x1400500d9  mov     rax, cs:__security_cookie
0x1400500e0  xor     rax, rsp
0x1400500e3  mov     [rbp+40h+var_48], rax
0x1400500e7  xor     edi, edi
0x1400500e9  mov     esi, r8d
0x1400500ec  xor     eax, eax
0x1400500ee  mov     [rbp+40h+var_78], rcx
0x1400500f2  mov     [rbp+40h+var_50], eax
0x1400500f5  mov     r12, rdx
0x1400500f8  xorps   xmm0, xmm0
0x1400500fb  mov     [rbp+40h+var_BC], edi
0x1400500fe  lea     rcx, [rdi-1]
0x140050102  mov     r8d, 47696457h
0x140050108  lea     eax, [rdi+28h]
0x14005010b  mov     r15, r9
0x14005010e  mul     rsi
0x140050111  movups  [rbp+40h+var_70], xmm0
0x140050115  movups  [rbp+40h+var_60], xmm0
0x140050119  mov     r14d, edi
0x14005011c  cmovb   rax, rcx
0x140050120  lea     ecx, [rdi+40h]
0x140050123  mov     rdx, rax
0x140050126  call    cs:__imp_ExAllocatePool2
0x14005012d  nop     dword ptr [rax+rax+00h]
0x140050132  test    rax, rax
0x140050135  jz      loc_1400504A6
0x14005013b  mov     r9, rax; struct WDI_NEIGHBOR_BSS *
0x14005013e  mov     [rbp+40h+var_98], edi
0x140050141  mov     r8d, esi; unsigned int
0x140050144  mov     rcx, r12; this
0x140050147  call    ?ReplaceOutgoingNeighborLinks@CBSSEntry@@QEAAXKKPEAUWDI_NEIGHBOR_BSS@@@Z; CBSSEntry::ReplaceOutgoingNeighborLinks(ulong,ulong,WDI_NEIGHBOR_BSS *)
0x14005014c  mov     rax, [r12]
0x140050150  lea     rdx, [rbp+40h+var_70]
0x140050154  mov     rcx, r12
0x140050157  mov     rax, [rax+10h]
0x14005015b  call    _guard_dispatch_icall
0x140050160  mov     edx, [r12+210h]
0x140050168  mov     [rbp+40h+var_94], edx
0x14005016b  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140050172  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140050179  jz      short loc_140050196
0x14005017b  mov     rcx, cs:WPP_GLOBAL_Control
0x140050182  cmp     byte ptr [rcx+29h], 5
0x140050186  jnb     loc_1400504EE
0x14005018c  cmp     [rcx+48h], di
0x140050190  jnz     loc_1400504EE
0x140050196  mov     ebx, edi
0x140050198  mov     [rbp+40h+var_B8], ebx
0x14005019b  test    esi, esi
0x14005019d  jz      loc_14005032E
0x1400501a3  mov     rcx, rdi
0x1400501a6  lea     rax, [r12+2E5h]
0x1400501ae  mov     [rbp+40h+var_80], rcx
0x1400501b2  xor     edx, edx
0x1400501b4  mov     [rbp+40h+var_C0], dil
0x1400501b8  lea     rdi, [rcx+rcx*4]
0x1400501bc  mov     [rbp+40h+var_9F], dx
0x1400501c0  mov     dl, [r15+rdi*4+2]
0x1400501c5  mov     rcx, rax
0x1400501c8  call    ConvertCountryCodeOperatingClassToBand
0x1400501cd  movzx   edx, byte ptr [r15+rdi*4+1]
0x1400501d3  mov     [rbp-60h], eax
0x1400501d6  lea     ecx, [rdx-8]
0x1400501d9  cmp     cl, 1
0x1400501dc  jbe     loc_14005043E
0x1400501e2  lea     ecx, [rdx-0Ch]
0x1400501e5  cmp     cl, 1
0x1400501e8  ja      loc_14005051F
0x1400501ee  mov     r14d, [r15+rdi*4+0Bh]
0x1400501f3  xor     r10d, r10d
0x1400501f6  mov     bl, [r15+rdi*4+0Fh]
0x1400501fb  mov     [rbp+40h+var_9C], r10d
0x1400501ff  mov     r8d, [rbp+40h+var_94]
0x140050203  lea     r9, [r15+5]
0x140050207  mov     [rbp+40h+var_88], r10
0x14005020b  lea     r9, [r9+rdi*4]
0x14005020f  mov     [rbp+40h+var_90], r9
0x140050213  test    r8d, r8d
0x140050216  jz      short loc_140050267
0x140050218  movzx   eax, word ptr [r15+rdi*4]
0x14005021d  mov     cl, bl
0x14005021f  shr     cl, 1
0x140050221  mov     edx, 2
0x140050226  bt      ax, dx
0x14005022a  not     cl
0x14005022c  setnb   al
0x14005022f  and     cl, al
0x140050231  test    cl, 1
0x140050234  jnz     short loc_14005023F
0x140050236  test    r14d, r14d
0x140050239  jz      loc_140050596
0x14005023f  cmp     r14d, r8d
0x140050242  jnz     short loc_140050267
0x140050244  cmp     dword ptr [rbp+40h+var_70], r10d
0x140050248  jz      short loc_140050267
0x14005024a  mov     ecx, r10d
0x14005024d  cmp     ecx, dword ptr [rbp+40h+var_70]
0x140050250  jnb     short loc_140050267
0x140050252  mov     eax, ecx
0x140050254  cmp     byte ptr [rbp+rax+40h+var_70+4], r10b
0x140050259  jz      loc_140050358
0x14005025f  lea     rax, [rbp+40h+var_70]
0x140050263  mov     [rbp+40h+var_88], rax
0x140050267  test    r14d, r14d
0x14005026a  jz      loc_140050453
0x140050270  lea     rdx, [r12+1BCh]; Source2
0x140050278  mov     r8d, 6; Length
0x14005027e  mov     rcx, r9; Source1
0x140050281  call    cs:__imp_RtlCompareMemory
0x140050288  nop     dword ptr [rax+rax+00h]
0x14005028d  cmp     rax, 6
0x140050291  jz      loc_1400505F8
0x140050297  mov     al, [rbp+40h+var_C0]
0x14005029a  mov     r9d, r14d; unsigned int
0x14005029d  mov     rcx, [rbp+40h+var_78]; this
0x1400502a1  mov     rdx, r12; struct CBSSEntry *
0x1400502a4  mov     byte ptr [rbp+40h+var_B0], al
0x1400502a7  mov     eax, [rbp+40h+var_9C]
0x1400502aa  mov     word ptr [rbp+40h+var_B0+1], ax
0x1400502ae  mov     al, [r15+rdi*4+3]
0x1400502b3  mov     [rsp+160h+var_118], al; unsigned __int8
0x1400502b7  mov     eax, [rbp-60h]
0x1400502ba  mov     [rsp+160h+var_120], eax; enum _DOT11_BAND_ID
0x1400502be  lea     rax, [r15+5]
0x1400502c2  lea     rax, [rax+rdi*4]
0x1400502c6  mov     [rsp+160h+var_128], rax; unsigned __int8 (*)[6]
0x1400502cb  lea     rax, [rbp+40h+var_B0]
0x1400502cf  mov     [rsp+160h+var_130], rax; union DOT11_MLD_PARAMETERS
0x1400502d4  movzx   eax, word ptr [r15+rdi*4]
0x1400502d9  mov     byte ptr [rsp+160h+var_138], bl; union DOT11_BSS_PARAMETERS
0x1400502dd  mov     word ptr [rsp+160h+var_140], ax; union DOT11_TBTT_INFORMATION_HEADER
0x1400502e2  call    ?AddNeighborAP@CBSSListManager@@QEAAPEAVCBSSEntry@@PEAV2@QEAU_DOT11_SSID@@ITDOT11_TBTT_INFORMATION_HEADER@@TDOT11_BSS_PARAMETERS@@TDOT11_MLD_PARAMETERS@@PEAY05EW4_DOT11_BAND_ID@@E@Z; CBSSListManager::AddNeighborAP(CBSSEntry *,_DOT11_SSID * const,uint,DOT11_TBTT_INFORMATION_HEADER,DOT11_BSS_PARAMETERS,DOT11_MLD_PARAMETERS,uchar (*)[6],_DOT11_BAND_ID,uchar)
0x1400502e7  xor     r8d, r8d
0x1400502ea  mov     [rbp+40h+var_90], rax
0x1400502ee  test    rax, rax
0x1400502f1  jnz     short loc_14005035F
0x1400502f3  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400502fa  jnz     loc_1400505AE
0x140050300  mov     r14d, [rbp+40h+var_BC]
0x140050304  mov     eax, [rbp+40h+var_B8]
0x140050307  mov     edi, 0
0x14005030c  mov     rcx, [rbp+40h+var_80]
0x140050310  inc     eax
0x140050312  inc     rcx
0x140050315  mov     [rbp+40h+var_B8], eax
0x140050318  cmp     eax, esi
0x14005031a  mov     [rbp+40h+var_80], rcx
0x14005031e  mov     ebx, eax
0x140050320  lea     rax, [r12+2E5h]
0x140050328  jb      loc_1400501B2
0x14005032e  test    r14d, r14d
0x140050331  mov     eax, edi
0x140050333  cmovz   eax, [rbp+40h+var_98]
0x140050337  mov     rcx, [rbp+40h+var_48]
0x14005033b  xor     rcx, rsp; StackCookie
0x14005033e  call    __security_check_cookie
0x140050343  add     rsp, 128h
0x14005034a  pop     r15
0x14005034c  pop     r14
0x14005034e  pop     r13
0x140050350  pop     r12
0x140050352  pop     rdi
0x140050353  pop     rsi
0x140050354  pop     rbx
0x140050355  pop     rbp
0x140050356  retn
0x140050358  inc     ecx
0x14005035a  jmp     loc_14005024D
0x14005035f  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140050366  jz      loc_14005042E
0x14005036c  mov     rcx, cs:WPP_GLOBAL_Control
0x140050373  cmp     byte ptr [rcx+29h], 5
0x140050377  jb      loc_14005059E
0x14005037d  cmp     [rbp+40h+var_88], r8
0x140050381  lea     rdx, aNone; "None"
0x140050388  movzx   r8d, word ptr [r15+rdi*4]
0x14005038d  lea     rax, aSame; "Same"
0x140050394  movzx   r9d, byte ptr [r15+rdi*4+3]
0x14005039a  cmovz   rax, rdx
0x14005039e  mov     r10d, [rbp+40h+var_B8]
0x1400503a2  mov     r11d, [rbp+40h+var_BC]
0x1400503a6  inc     r10d
0x1400503a9  mov     rcx, [rcx+40h]
0x1400503ad  inc     r11d
0x1400503b0  mov     [rsp+160h+var_C8], rax
0x1400503b8  lea     rax, [r15+5]
0x1400503bc  mov     [rsp+160h+var_D0], r14d
0x1400503c4  lea     rax, [rax+rdi*4]
0x1400503c8  mov     [rsp+160h+var_D8], rax
0x1400503d0  lea     rax, [rbp+40h+var_70]
0x1400503d4  mov     [rsp+160h+var_E0], rax
0x1400503dc  mov     eax, [r12+210h]
0x1400503e4  mov     [rsp+160h+var_E8], eax
0x1400503e8  mov     eax, [rbp-60h]
0x1400503eb  movzx   edx, bl
0x1400503ee  lea     rbx, [r12+1BCh]
0x1400503f6  mov     [rsp+160h+var_F0], rbx
0x1400503fb  mov     [rsp+160h+var_F8], edx
0x1400503ff  mov     [rsp+160h+var_100], r8d
0x140050404  mov     [rsp+160h+var_108], r9d
0x140050409  mov     dword ptr [rsp+160h+var_110], eax
0x14005040d  mov     rax, [rbp+40h+var_90]
0x140050411  mov     qword ptr [rsp+160h+var_118], rax
0x140050416  mov     qword ptr [rsp+160h+var_120], r12
0x14005041b  mov     dword ptr [rsp+160h+var_128], esi
0x14005041f  mov     dword ptr [rsp+160h+var_130], r10d
0x140050424  mov     dword ptr [rsp+160h+var_138], r11d
0x140050429  call    WPP_RECORDER_SF_dddqqddDD_MAC_D_SSID__MAC_Ds
0x14005042e  mov     r14d, [rbp+40h+var_BC]
0x140050432  inc     r14d
0x140050435  mov     [rbp+40h+var_BC], r14d
0x140050439  jmp     loc_140050304
0x14005043e  mov     bl, [r15+rdi*4+0Bh]
0x140050443  xor     r10d, r10d
0x140050446  mov     r14d, r10d
0x140050449  mov     word ptr [rbp+40h+var_9C], r10w
0x14005044e  jmp     loc_1400501FF
0x140050453  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14005045a  jz      loc_140050300
0x140050460  mov     rcx, cs:WPP_GLOBAL_Control
0x140050467  cmp     byte ptr [rcx+29h], 5
0x14005046b  jnb     short loc_140050478
0x14005046d  cmp     [rcx+48h], r10w
0x140050472  jz      loc_140050300
0x140050478  mov     eax, [rbp+40h+var_B8]
0x14005047b  mov     edx, [rbp+40h+var_BC]
0x14005047e  inc     eax
0x140050480  mov     rcx, [rcx+40h]
0x140050484  inc     edx
0x140050486  mov     qword ptr [rsp+160h+var_118], r9
0x14005048b  mov     [rsp+160h+var_120], r14d
0x140050490  mov     dword ptr [rsp+160h+var_128], esi
0x140050494  mov     dword ptr [rsp+160h+var_130], eax
0x140050498  mov     dword ptr [rsp+160h+var_138], edx
0x14005049c  call    WPP_RECORDER_SF_dddD_MAC_
0x1400504a1  jmp     loc_140050300
0x1400504a6  mov     [rbp+40h+var_98], 0C000009Ah
0x1400504ad  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400504b4  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400504bb  jz      loc_14005032E
0x1400504c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400504c8  lea     rax, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400504cf  mov     r9d, 91h
0x1400504d5  mov     dword ptr [rsp+160h+var_138], esi
0x1400504d9  mov     dl, 2
0x1400504db  mov     qword ptr [rsp+160h+var_140], rax
0x1400504e0  mov     rcx, [rcx+40h]
0x1400504e4  call    WPP_RECORDER_SF_d
0x1400504e9  jmp     loc_14005032E
0x1400504ee  mov     rcx, [rcx+40h]
0x1400504f2  lea     rax, [r12+1BCh]
0x1400504fa  mov     dword ptr [rsp+160h+var_118], esi
0x1400504fe  mov     qword ptr [rsp+160h+var_120], rax
0x140050503  lea     rax, [rbp+40h+var_70]
0x140050507  mov     dword ptr [rsp+160h+var_128], edx
0x14005050b  mov     [rsp+160h+var_130], rax
0x140050510  mov     qword ptr [rsp+160h+var_138], r12
0x140050515  call    WPP_RECORDER_SF_q_SSID_D_MAC_d
0x14005051a  jmp     loc_140050196
0x14005051f  cmp     dl, 0Fh
0x140050522  ja      short loc_140050573
0x140050524  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14005052b  jz      loc_140050304
0x140050531  mov     eax, edx
0x140050533  lea     ecx, [rbx+1]
0x140050536  mov     [rsp+160h+var_120], eax
0x14005053a  lea     edx, [r14+1]
0x14005053e  mov     dword ptr [rsp+160h+var_128], esi
0x140050542  lea     rax, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x140050549  mov     dword ptr [rsp+160h+var_130], ecx
0x14005054d  mov     r9d, 93h
0x140050553  mov     rcx, cs:WPP_GLOBAL_Control
0x14005055a  mov     dword ptr [rsp+160h+var_138], edx
0x14005055e  mov     dl, 2
0x140050560  mov     qword ptr [rsp+160h+var_140], rax
0x140050565  mov     rcx, [rcx+40h]
0x140050569  call    WPP_RECORDER_SF_dddd
0x14005056e  jmp     loc_140050304
0x140050573  mov     al, [r15+rdi*4+11h]
0x140050578  xor     r10d, r10d
0x14005057b  mov     r14d, [r15+rdi*4+0Bh]
0x140050580  mov     bl, [r15+rdi*4+0Fh]
0x140050585  mov     [rbp+40h+var_C0], al
0x140050588  movzx   eax, word ptr [r15+rdi*4+12h]
0x14005058e  mov     [rbp+40h+var_9C], eax
0x140050591  jmp     loc_1400501FF
0x140050596  mov     r14d, r8d
0x140050599  jmp     loc_140050244
0x14005059e  cmp     [rcx+48h], r8w
0x1400505a3  jz      loc_14005042E
  ... truncated ...
```
