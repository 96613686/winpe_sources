# CBSSEntry::UpdateP2PFields(_WFC_BSS_ENTRY_FRAME_TYPE,ulong,uchar *,uchar (*)[6])

- ea: `0x1400413c0`
- end: `0x140041a25`
- name: `?UpdateP2PFields@CBSSEntry@@QEAAXW4_WFC_BSS_ENTRY_FRAME_TYPE@@KPEAEPEAY05E@Z`
- size: `1637`
- prototype: `void(CBSSEntry *__hidden this, enum _WFC_BSS_ENTRY_FRAME_TYPE, unsigned int, unsigned __int8 *, unsigned __int8 (*)[6])`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14007f740`
- `0x14007fac0`

## callees

- `0x140012214`
- `0x140034e04`
- `0x1400413c0`
- `0x140041a2c`
- `0x140041bdc`
- `0x140041ce8`
- `0x14004c5b4`
- `0x14005a090`
- `0x140083cb0`
- `0x1400bce28`
- `0x1400d84c0`
- `0x1400d85ec`
- `0x1400d8778`
- `0x1400da4f0`
- `0x1400da740`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140041941`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041a14`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041941`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041a14`
- `ntoskrnl!ExAllocatePool2` at `0x14004174e`
- `ntoskrnl!ExAllocatePool2` at `0x14004174e`

## pseudocode

```c
void __fastcall CBSSEntry::UpdateP2PFields(
        CBSSEntry *this,
        enum _WFC_BSS_ENTRY_FRAME_TYPE a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned __int8 (*a5)[6])
{
  __int64 v9; // r8
  unsigned __int8 *v10; // rsi
  _BSS_ENTRY_WFD_SERVICES_INFO *m_pProbeWfdServiceNames; // rdi
  __int128 v12; // xmm6
  __int128 v13; // xmm7
  __int128 v14; // xmm0
  char v15; // al
  const unsigned __int8 *v16; // rcx
  const CBSSEntryFactory *v17; // rdx
  bool v18; // al
  int v19; // edx
  const unsigned __int8 *v20; // rcx
  int v21; // r8d
  unsigned __int8 v22; // r9
  int FirstP2PIEWFDService; // r15d
  unsigned __int8 v24; // r9
  __int16 v25; // cx
  unsigned int v26; // eax
  unsigned int v27; // ecx
  unsigned __int8 *i; // rdx
  size_t v29; // r8
  __int64 v30; // rax
  const void *v31; // rdx
  __int64 v32; // r8
  int v33; // eax
  const unsigned __int8 *v34; // rcx
  unsigned __int8 v35; // r9
  unsigned __int8 *Pool2; // rax
  int v37; // edx
  int v38; // r8d
  int v39; // ecx
  int v40; // r8d
  unsigned __int16 v41; // ax
  size_t v42; // rcx
  unsigned int v43; // r9d
  int v44; // edx
  unsigned __int16 v45; // di
  int v46; // edx
  int v47; // [rsp+28h] [rbp-E0h]
  unsigned __int16 v48; // [rsp+30h] [rbp-D8h]
  unsigned __int16 v49; // [rsp+30h] [rbp-D8h]
  char v50; // [rsp+40h] [rbp-C8h]
  int v51; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v52; // [rsp+60h] [rbp-A8h] BYREF
  int v53; // [rsp+68h] [rbp-A0h]
  int v54; // [rsp+6Ch] [rbp-9Ch]
  size_t Size; // [rsp+70h] [rbp-98h] BYREF
  __m256i v56; // [rsp+78h] [rbp-90h] BYREF
  __int128 v57; // [rsp+98h] [rbp-70h] BYREF
  _OWORD v58[2]; // [rsp+A8h] [rbp-60h] BYREF
  _DWORD v59[132]; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int8 v60[6]; // [rsp+2D8h] [rbp+1D0h] BYREF
  unsigned __int8 v61; // [rsp+2DEh] [rbp+1D6h]
  unsigned __int8 v62[265]; // [rsp+2DFh] [rbp+1D7h] BYREF

  memset(v58, 0, 28);
  v57 = 0;
  memset(v59, 0, 0x208u);
  v10 = 0;
  m_pProbeWfdServiceNames = 0;
  LOWORD(v51) = 0;
  if ( a4 && a3 && a5 )
  {
    LODWORD(v57) = *(_DWORD *)a5;
    WORD2(v57) = *(_WORD *)&(*a5)[4];
    v53 = 0;
    v15 = WfdParseWpsIe(a4, a3, v9, v59);
    v16 = &WPP_RECORDER_INITIALIZED;
    v17 = &WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids;
    if ( v15 && (v59[0] & 0x40000) != 0 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = 4;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v17,
          1,
          46,
          (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
      }
      v18 = v59[6] != 0;
    }
    else
    {
      v18 = 0;
    }
    if ( a2 == WFC_BSS_ENTRY_PROBE_RESPONSE_FRAME )
      this->m_IsSelectedRegistrarInProbeResponse = v18;
    else
      this->m_IsSelectedRegistrarInBeacon = v18;
    v52 = a3;
    Size = (size_t)a4;
    memset(&v56.m256i_u64[1], 0, 24);
    FirstP2PIEWFDService = FindFirstP2PIEWFDService(v16, (unsigned __int8 **)&Size, &v52);
    if ( FirstP2PIEWFDService >= 0
      && (v54 = 0,
          FirstP2PIEWFDService = FindAttributeInFragmentedP2PIEsWFDService(
                                   v20,
                                   (unsigned __int8 *)Size,
                                   v52,
                                   v22,
                                   (struct _WFD_ATTRIBUTE_INFO *)&v56.m256i_u64[1]),
          FirstP2PIEWFDService >= 0) )
    {
      LOWORD(v33) = v54;
      while ( 1 )
      {
        v19 = 7;
        if ( !v56.m256i_i16[6] )
          break;
        if ( v56.m256i_i16[6] < 7u )
          goto LABEL_41;
        FirstP2PIEWFDService = GetAttributeBytesWFDService(
                                 (const unsigned __int8 *)v56.m256i_u16[6],
                                 (struct _WFD_ATTRIBUTE_INFO *)&v56.m256i_u64[1],
                                 v60,
                                 v24,
                                 7u,
                                 v48);
        if ( FirstP2PIEWFDService < 0 )
          goto LABEL_14;
        if ( v61 > (unsigned int)v56.m256i_i16[6] )
        {
LABEL_41:
          FirstP2PIEWFDService = -1071448043;
          goto LABEL_17;
        }
        FirstP2PIEWFDService = GetAttributeBytesWFDService(
                                 v34,
                                 (struct _WFD_ATTRIBUTE_INFO *)&v56.m256i_u64[1],
                                 v62,
                                 v35,
                                 v61,
                                 v49);
        if ( FirstP2PIEWFDService < 0 )
          goto LABEL_14;
        HIWORD(v33) = HIWORD(v54);
        LOWORD(v33) = v54 + 1;
        v54 = v33;
      }
      LOWORD(v10) = v56.m256i_i16[5];
      v25 = v33;
      LOWORD(v51) = v56.m256i_i16[5];
      v53 = (unsigned __int16)v33;
    }
    else
    {
LABEL_14:
      v25 = v53;
    }
    if ( FirstP2PIEWFDService >= 0 && v25 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 4;
        WPP_RECORDER_SF_Ld(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          v21,
          47,
          (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
          v25,
          (char)v10);
      }
      v54 = (unsigned __int16)v10;
      v52 = (unsigned __int16)v10 + 524 * (unsigned __int16)v53 + 8;
      Size = v52;
      Pool2 = (unsigned __int8 *)ExAllocatePool2(64, v52, 1198089303);
      v10 = Pool2;
      if ( Pool2 )
      {
        memset(Pool2, 0, Size);
        *((_WORD *)v10 + 2) = 8;
        Size = (size_t)(v10 + 8);
        FirstP2PIEWFDService = WFDGetAdvertisedServiceInfo(v39, (int)a4, a3, (int)&v51, v10 + 8);
        if ( FirstP2PIEWFDService < 0 )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v46 = v53;
            LOBYTE(v46) = 4;
            WPP_RECORDER_SF_dDD(
              WPP_GLOBAL_Control->DeviceExtension,
              v46,
              v40,
              50,
              (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
              FirstP2PIEWFDService,
              v51,
              v53);
          }
          ExFreePoolWithTag(v10, 0x47696457u);
          v10 = 0;
        }
        else
        {
          v41 = v51;
          v42 = (size_t)(v10 + 8);
          v43 = 0;
          v52 = 0;
          while ( 1 )
          {
            LOWORD(v54) = v41;
            if ( (unsigned __int16)v43 >= (unsigned __int16)v53 || v41 <= 7u )
              break;
            v44 = *(unsigned __int8 *)(v42 + 6);
            v45 = v44 + 7;
            if ( (unsigned __int16)(v44 + 7) > v41 )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                v50 = v44 + 7;
                LOBYTE(v44) = 4;
                WPP_RECORDER_SF_dddd(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v44,
                  (unsigned __int16)v43,
                  48,
                  (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
                  v43,
                  *(_BYTE *)(v42 + 6),
                  v50,
                  v41);
                LOWORD(v43) = v52;
              }
              break;
            }
            LOWORD(v43) = v43 + 1;
            v52 = v43;
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
              && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
            {
              WPP_RECORDER_SF_dDDds(
                WPP_GLOBAL_Control->DeviceExtension,
                v44,
                *(unsigned __int16 *)(v42 + 4),
                (unsigned __int16)v43,
                v47,
                v43,
                *(_DWORD *)v42,
                *(_WORD *)(v42 + 4),
                v44,
                v42 + 7);
              v43 = v52;
              v42 = Size;
            }
            v42 += v45;
            v41 = v54 - v45;
            Size = v42;
          }
          *((_WORD *)v10 + 3) = v51;
          *(_WORD *)v10 = v43;
          if ( a2 )
          {
            m_pProbeWfdServiceNames = this->m_pProbeWfdServiceNames;
            this->m_pProbeWfdServiceNames = (_BSS_ENTRY_WFD_SERVICES_INFO *)v10;
          }
          else
          {
            m_pProbeWfdServiceNames = this->m_pBeaconWfdServiceNames;
            this->m_pBeaconWfdServiceNames = (_BSS_ENTRY_WFD_SERVICES_INFO *)v10;
          }
        }
      }
      else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v37) = 4;
        WPP_RECORDER_SF_dddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v37,
          v38,
          51,
          (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
          v53,
          12,
          v54,
          v52);
      }
    }
    else
    {
      v10 = 0;
    }
LABEL_17:
    if ( !this->m_IsWFDServiceUpdated )
    {
      v26 = 1;
      v52 = 1;
      if ( v10 != (unsigned __int8 *)m_pProbeWfdServiceNames )
      {
        if ( v10 && m_pProbeWfdServiceNames )
        {
          FirstP2PIEWFDService = WFDCompareAdvertisedServiceInfo(
                                   *((unsigned __int16 *)v10 + 3),
                                   (unsigned int)v10 + *((unsigned __int16 *)v10 + 2),
                                   m_pProbeWfdServiceNames->usServiceNamesDescriptorLength,
                                   (unsigned int)m_pProbeWfdServiceNames
                                 + m_pProbeWfdServiceNames->usServicesDescriptorOffset,
                                   (__int64)&v52);
          v26 = v52;
        }
        else
        {
          v26 = 0;
        }
      }
      if ( !FirstP2PIEWFDService && !v26 )
        this->m_IsWFDServiceUpdated = 1;
    }
    v27 = a3;
    for ( i = a4; v27 >= 2; i += v30 )
    {
      v29 = i[1];
      v30 = (unsigned int)(v29 + 2);
      if ( v27 < (unsigned int)v30 )
        break;
      if ( !*i )
      {
        v31 = i + 2;
        if ( v31 )
        {
          if ( (unsigned __int8)v29 <= 0x20u )
          {
            DWORD2(v57) = v29;
            memmove((char *)&v57 + 12, v31, v29);
            if ( (int)WFDGetCapability(a4, a3, v32, &this->m_GroupCaps) >= 0 )
            {
              v12 = *(_OWORD *)((char *)v58 + 12);
              v13 = v57;
              goto LABEL_5;
            }
          }
        }
        break;
      }
      v27 -= v30;
    }
  }
  v12 = 0;
  v13 = 0;
  memset(v58, 0, 28);
LABEL_5:
  if ( m_pProbeWfdServiceNames )
    ExFreePoolWithTag(m_pProbeWfdServiceNames, 0x47696457u);
  v14 = v58[0];
  *(_OWORD *)this->m_GroupId.DeviceAddress = v13;
  *(_OWORD *)&this->m_GroupId.SSID.ucSSID[4] = v14;
  *(_OWORD *)&this->m_GroupId.SSID.ucSSID[16] = v12;
}

```

## disassembly

```asm
0x1400413c0  mov     rax, rsp
0x1400413c3  mov     [rax+10h], rbx
0x1400413c7  push    rbp
0x1400413c8  push    rsi
0x1400413c9  push    rdi
0x1400413ca  push    r12
0x1400413cc  push    r13
0x1400413ce  push    r14
0x1400413d0  push    r15
0x1400413d2  lea     rbp, [rax-348h]
0x1400413d9  sub     rsp, 410h
0x1400413e0  movaps  xmmword ptr [rax-48h], xmm6
0x1400413e4  movaps  xmmword ptr [rax-58h], xmm7
0x1400413e8  mov     rax, cs:__security_cookie
0x1400413ef  xor     rax, rsp
0x1400413f2  mov     [rbp+340h+var_60], rax
0x1400413f9  mov     r15, [rbp+340h+arg_20]
0x140041400  xorps   xmm0, xmm0
0x140041403  mov     r12d, r8d
0x140041406  mov     r13d, edx
0x140041409  mov     rbx, rcx
0x14004140c  xor     edx, edx; Val
0x14004140e  movups  xmmword ptr [rbp+340h+var_3A0], xmm0
0x140041412  mov     r8d, 208h; Size
0x140041418  lea     rcx, [rbp+340h+var_380]; void *
0x14004141c  movups  xmmword ptr [rbp+340h+var_3A0+0Ch], xmm0
0x140041420  mov     r14, r9
0x140041423  movups  [rbp+340h+var_3B0], xmm0
0x140041427  call    memset
0x14004142c  xor     esi, esi
0x14004142e  xor     edi, edi
0x140041430  mov     word ptr [rsp+440h+var_3F0], si
0x140041435  test    r14, r14
0x140041438  jz      short loc_140041444
0x14004143a  test    r12d, r12d
0x14004143d  jz      short loc_140041444
0x14004143f  test    r15, r15
0x140041442  jnz     short loc_1400414A9
0x140041444  xorps   xmm6, xmm6
0x140041447  xorps   xmm7, xmm7
0x14004144a  movups  xmmword ptr [rbp+340h+var_3A0], xmm6
0x14004144e  movups  xmmword ptr [rbp+340h+var_3A0+0Ch], xmm6
0x140041452  test    rdi, rdi
0x140041455  jnz     loc_140041A0C
0x14004145b  movups  xmm0, xmmword ptr [rbp+340h+var_3A0]
0x14004145f  movups  xmmword ptr [rbx+298h], xmm7
0x140041466  movups  xmmword ptr [rbx+2A8h], xmm0
0x14004146d  movups  xmmword ptr [rbx+2B4h], xmm6
0x140041474  mov     rcx, [rbp+340h+var_60]
0x14004147b  xor     rcx, rsp; StackCookie
0x14004147e  call    __security_check_cookie
0x140041483  lea     r11, [rsp+440h+var_30]
0x14004148b  mov     rbx, [r11+48h]
0x14004148f  movaps  xmm6, xmmword ptr [r11-10h]
0x140041494  movaps  xmm7, xmmword ptr [r11-20h]
0x140041499  mov     rsp, r11
0x14004149c  pop     r15
0x14004149e  pop     r14
0x1400414a0  pop     r13
0x1400414a2  pop     r12
0x1400414a4  pop     rdi
0x1400414a5  pop     rsi
0x1400414a6  pop     rbp
0x1400414a7  retn
0x1400414a9  mov     eax, [r15]
0x1400414ac  lea     r9, [rbp+340h+var_380]
0x1400414b0  mov     dword ptr [rbp+340h+var_3B0], eax
0x1400414b3  mov     edx, r12d
0x1400414b6  movzx   eax, word ptr [r15+4]
0x1400414bb  mov     rcx, r14
0x1400414be  mov     word ptr [rbp+340h+var_3B0+4], ax
0x1400414c2  mov     dword ptr [rsp+440h+var_3E0], esi
0x1400414c6  call    WfdParseWpsIe
0x1400414cb  lea     rcx, WPP_RECORDER_INITIALIZED; unsigned __int8 *
0x1400414d2  lea     rdx, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x1400414d9  test    al, al
0x1400414db  jnz     loc_1400415F1
0x1400414e1  xor     al, al
0x1400414e3  cmp     r13d, 1
0x1400414e7  jz      loc_140041635
0x1400414ed  mov     [rbx+2C6h], al
0x1400414f3  xor     eax, eax
0x1400414f5  mov     [rsp+440h+var_3E8], r12d
0x1400414fa  xorps   xmm0, xmm0
0x1400414fd  mov     [rbp+340h+var_3B8], rax
0x140041501  lea     r8, [rsp+440h+var_3E8]; unsigned int *
0x140041506  mov     [rsp+440h+Size], r14
0x14004150b  lea     rdx, [rsp+440h+Size]; unsigned __int8 **
0x140041510  movups  xmmword ptr [rsp+440h+var_3D0+8], xmm0
0x140041515  call    ?FindFirstP2PIEWFDService@@YAJPEBEPEAPEAEPEAK@Z; FindFirstP2PIEWFDService(uchar const *,uchar * *,ulong *)
0x14004151a  mov     r15d, eax
0x14004151d  test    eax, eax
0x14004151f  js      short loc_140041549
0x140041521  mov     r8d, [rsp+440h+var_3E8]; unsigned int
0x140041526  lea     rax, [rsp+440h+var_3D0+8]
0x14004152b  mov     rdx, [rsp+440h+Size]; unsigned __int8 *
0x140041530  mov     [rsp+440h+var_420], rax; struct _WFD_ATTRIBUTE_INFO *
0x140041535  mov     dword ptr [rsp+440h+var_3E0+4], esi
0x140041539  call    ?FindAttributeInFragmentedP2PIEsWFDService@@YAJPEBEPEAEKEPEAU_WFD_ATTRIBUTE_INFO@@@Z; FindAttributeInFragmentedP2PIEsWFDService(uchar const *,uchar *,ulong,uchar,_WFD_ATTRIBUTE_INFO *)
0x14004153e  mov     r15d, eax
0x140041541  test    eax, eax
0x140041543  jns     loc_140041640
0x140041549  mov     ecx, dword ptr [rsp+440h+var_3E0]
0x14004154d  test    r15d, r15d
0x140041550  jns     loc_1400416D6
0x140041556  mov     rsi, rdi
0x140041559  cmp     byte ptr [rbx+2ECh], 0
0x140041560  jnz     short loc_14004157D
0x140041562  mov     eax, 1
0x140041567  mov     [rsp+440h+var_3E8], eax
0x14004156b  cmp     rsi, rdi
0x14004156e  jnz     loc_1400419B4
0x140041574  test    r15d, r15d
0x140041577  jz      loc_1400419F8
0x14004157d  mov     ecx, r12d
0x140041580  mov     rdx, r14
0x140041583  cmp     ecx, 2
0x140041586  jb      loc_140041444
0x14004158c  movzx   r8d, byte ptr [rdx+1]; Size
0x140041591  lea     eax, [r8+2]
0x140041595  cmp     ecx, eax
0x140041597  jb      loc_140041444
0x14004159d  cmp     byte ptr [rdx], 0
0x1400415a0  jz      short loc_1400415A9
0x1400415a2  sub     ecx, eax
0x1400415a4  add     rdx, rax
0x1400415a7  jmp     short loc_140041583
0x1400415a9  add     rdx, 2; Src
0x1400415ad  jz      loc_140041444
0x1400415b3  cmp     r8b, 20h ; ' '
0x1400415b7  ja      loc_140041444
0x1400415bd  lea     rcx, [rbp+340h+var_3B0+0Ch]; void *
0x1400415c1  mov     dword ptr [rbp+340h+var_3B0+8], r8d
0x1400415c5  call    memmove
0x1400415ca  lea     r9, [rbx+2C4h]
0x1400415d1  mov     edx, r12d
0x1400415d4  mov     rcx, r14
0x1400415d7  call    WFDGetCapability
0x1400415dc  test    eax, eax
0x1400415de  js      loc_140041444
0x1400415e4  movups  xmm6, xmmword ptr [rbp+340h+var_3A0+0Ch]
0x1400415e8  movups  xmm7, [rbp+340h+var_3B0]
0x1400415ec  jmp     loc_140041452
0x1400415f1  test    [rbp+340h+var_380], 40000h
0x1400415f8  jz      loc_1400414E1
0x1400415fe  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x140041605  jz      short loc_14004162A
0x140041607  mov     rcx, cs:WPP_GLOBAL_Control
0x14004160e  mov     r9d, 2Eh ; '.'
0x140041614  mov     [rsp+440h+var_420], rdx
0x140041619  mov     r8d, 1
0x14004161f  mov     dl, 4
0x140041621  mov     rcx, [rcx+40h]
0x140041625  call    WPP_RECORDER_SF_
0x14004162a  cmp     [rbp+340h+var_368], esi
0x14004162d  setnz   al
0x140041630  jmp     loc_1400414E3
0x140041635  mov     [rbx+2C5h], al
0x14004163b  jmp     loc_1400414F3
0x140041640  mov     eax, dword ptr [rsp+440h+var_3E0+4]
0x140041644  movzx   ecx, word ptr [rsp+440h+var_3D0+0Ch]; unsigned __int8 *
0x140041649  mov     edx, 7
0x14004164e  test    cx, cx
0x140041651  jz      short loc_1400416C0
0x140041653  cmp     cx, dx
0x140041656  jb      short loc_1400416B5
0x140041658  mov     word ptr [rsp+440h+var_420], dx; unsigned __int16
0x14004165d  lea     r8, [rbp+340h+var_170]; unsigned __int8 *
0x140041664  lea     rdx, [rsp+440h+var_3D0+8]; struct _WFD_ATTRIBUTE_INFO *
0x140041669  call    ?GetAttributeBytesWFDService@@YAJPEBEPEAU_WFD_ATTRIBUTE_INFO@@PEAEEGG@Z; GetAttributeBytesWFDService(uchar const *,_WFD_ATTRIBUTE_INFO *,uchar *,uchar,ushort,ushort)
0x14004166e  mov     r15d, eax
0x140041671  test    eax, eax
0x140041673  js      loc_140041549
0x140041679  movzx   eax, [rbp+340h+var_16A]
0x140041680  cmp     ax, word ptr [rsp+440h+var_3D0+0Ch]
0x140041685  ja      short loc_1400416B5
0x140041687  lea     r8, [rbp+340h+var_169]; unsigned __int8 *
0x14004168e  mov     word ptr [rsp+440h+var_420], ax; unsigned __int16
0x140041693  lea     rdx, [rsp+440h+var_3D0+8]; struct _WFD_ATTRIBUTE_INFO *
0x140041698  call    ?GetAttributeBytesWFDService@@YAJPEBEPEAU_WFD_ATTRIBUTE_INFO@@PEAEEGG@Z; GetAttributeBytesWFDService(uchar const *,_WFD_ATTRIBUTE_INFO *,uchar *,uchar,ushort,ushort)
0x14004169d  mov     r15d, eax
0x1400416a0  test    eax, eax
0x1400416a2  js      loc_140041549
0x1400416a8  mov     eax, dword ptr [rsp+440h+var_3E0+4]
0x1400416ac  inc     ax
0x1400416af  mov     dword ptr [rsp+440h+var_3E0+4], eax
0x1400416b3  jmp     short loc_140041644
0x1400416b5  mov     r15d, 0C0230015h
0x1400416bb  jmp     loc_140041559
0x1400416c0  movzx   esi, word ptr [rsp+440h+var_3D0+0Ah]
0x1400416c5  movzx   ecx, ax
0x1400416c8  mov     word ptr [rsp+440h+var_3F0], si
0x1400416cd  mov     dword ptr [rsp+440h+var_3E0], ecx
0x1400416d1  jmp     loc_14004154D
0x1400416d6  test    cx, cx
0x1400416d9  jz      loc_140041556
0x1400416df  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400416e6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400416ed  jz      short loc_140041721
0x1400416ef  movzx   ecx, cx
0x1400416f2  mov     r9d, 2Fh ; '/'
0x1400416f8  movzx   eax, si
0x1400416fb  mov     dl, 4
0x1400416fd  mov     [rsp+440h+var_410], eax
0x140041701  lea     rax, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x140041708  mov     dword ptr [rsp+440h+var_418], ecx
0x14004170c  mov     rcx, cs:WPP_GLOBAL_Control
0x140041713  mov     [rsp+440h+var_420], rax
0x140041718  mov     rcx, [rcx+40h]
0x14004171c  call    WPP_RECORDER_SF_Ld
0x140041721  movzx   eax, word ptr [rsp+440h+var_3E0]
0x140041726  mov     r8d, 47696457h
0x14004172c  imul    eax, 20Ch
0x140041732  movzx   ecx, si
0x140041735  mov     dword ptr [rsp+440h+var_3E0+4], ecx
0x140041739  add     eax, 8
0x14004173c  add     eax, ecx
0x14004173e  mov     ecx, 40h ; '@'
0x140041743  mov     edx, eax
0x140041745  mov     [rsp+440h+var_3E8], eax
0x140041749  mov     [rsp+440h+Size], rax
0x14004174e  call    cs:__imp_ExAllocatePool2
0x140041755  nop     dword ptr [rax+rax+00h]
0x14004175a  mov     rsi, rax
0x14004175d  test    rax, rax
0x140041760  jz      loc_140041954
0x140041766  mov     r8, [rsp+440h+Size]; Size
0x14004176b  xor     edx, edx; Val
0x14004176d  mov     rcx, rax; void *
0x140041770  call    memset
0x140041775  lea     rax, [rsi+8]
0x140041779  mov     word ptr [rsi+4], 8
0x14004177f  lea     r9, [rsp+440h+var_3F0]; int
0x140041784  mov     [rsp+440h+Size], rax
0x140041789  mov     r8d, r12d; int
0x14004178c  mov     [rsp+440h+var_420], rax; unsigned __int8 *
0x140041791  mov     rdx, r14; int
0x140041794  call    WFDGetAdvertisedServiceInfo
0x140041799  mov     r15d, eax
0x14004179c  test    eax, eax
0x14004179e  js      loc_1400418EC
0x1400417a4  movzx   eax, word ptr [rsp+440h+var_3F0]
0x1400417a9  lea     rcx, [rsi+8]
0x1400417ad  xor     r9d, r9d
0x1400417b0  lea     r8, WPP_RECORDER_INITIALIZED
0x1400417b7  mov     [rsp+440h+var_3E8], r9d
0x1400417bc  mov     word ptr [rsp+440h+var_3E0+4], ax
0x1400417c1  cmp     r9w, word ptr [rsp+440h+var_3E0]
0x1400417c7  jnb     loc_1400418B4
0x1400417cd  cmp     ax, 7
0x1400417d1  jbe     loc_1400418B4
0x1400417d7  movzx   edx, byte ptr [rcx+6]
0x1400417db  lea     edi, [rdx+7]
0x1400417de  cmp     di, ax
0x1400417e1  ja      loc_140041867
0x1400417e7  inc     r9w
0x1400417eb  mov     [rsp+440h+var_3E8], r9d
0x1400417f0  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x1400417f7  jz      short loc_14004184F
0x1400417f9  mov     r10, cs:WPP_GLOBAL_Control
0x140041800  cmp     byte ptr [r10+29h], 5
0x140041805  jnb     short loc_14004180F
0x140041807  cmp     word ptr [r10+48h], 0
0x14004180d  jz      short loc_14004184F
0x14004180f  movzx   r8d, word ptr [rcx+4]
0x140041814  lea     rax, [rcx+7]
0x140041818  mov     qword ptr [rsp+440h+var_3F8], rax
0x14004181d  mov     eax, [rcx]
0x14004181f  mov     rcx, [r10+40h]
0x140041823  mov     dword ptr [rsp+440h+var_400], edx
0x140041827  mov     dword ptr [rsp+440h+var_408], r8d
0x14004182c  movzx   r9d, r9w
0x140041830  mov     [rsp+440h+var_410], eax
0x140041834  mov     dword ptr [rsp+440h+var_418], r9d
0x140041839  call    WPP_RECORDER_SF_dDDds
0x14004183e  mov     r9d, [rsp+440h+var_3E8]
0x140041843  lea     r8, WPP_RECORDER_INITIALIZED
0x14004184a  mov     rcx, [rsp+440h+Size]
0x14004184f  movzx   eax, di
0x140041852  add     rcx, rax
0x140041855  movzx   eax, word ptr [rsp+440h+var_3E0+4]
0x14004185a  sub     ax, di
0x14004185d  mov     [rsp+440h+Size], rcx
0x140041862  jmp     loc_1400417BC
0x140041867  cmp     cs:WPP_RECORDER_INITIALIZED, r8; __annotation("TMF:",
0x14004186e  jz      short loc_1400418B4
0x140041870  movzx   eax, ax
0x140041873  mov     dword ptr [rsp+440h+var_400], eax
0x140041877  lea     rax, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x14004187e  movzx   r8d, r9w
0x140041882  mov     r9d, 30h ; '0'
0x140041888  movzx   ecx, di
0x14004188b  mov     dword ptr [rsp+440h+var_408], ecx
0x14004188f  mov     rcx, cs:WPP_GLOBAL_Control
0x140041896  mov     [rsp+440h+var_410], edx
0x14004189a  mov     dl, 4
0x14004189c  mov     dword ptr [rsp+440h+var_418], r8d
0x1400418a1  mov     [rsp+440h+var_420], rax
0x1400418a6  mov     rcx, [rcx+40h]
0x1400418aa  call    WPP_RECORDER_SF_dddd
  ... truncated ...
```
