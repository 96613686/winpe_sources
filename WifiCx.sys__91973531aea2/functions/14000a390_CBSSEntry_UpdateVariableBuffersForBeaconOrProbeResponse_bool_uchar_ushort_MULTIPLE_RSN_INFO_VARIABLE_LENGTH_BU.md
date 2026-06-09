# CBSSEntry::UpdateVariableBuffersForBeaconOrProbeResponse(bool,uchar *,ushort,MULTIPLE_RSN_INFO &,_VARIABLE_LENGTH_BUFFER_UINT8 &,_VARIABLE_LENGTH_BUFFER_UINT8 &)

- ea: `0x14000a390`
- end: `0x14000ab40`
- name: `?UpdateVariableBuffersForBeaconOrProbeResponse@CBSSEntry@@QEAAH_NPEAEGAEAUMULTIPLE_RSN_INFO@@AEAU_VARIABLE_LENGTH_BUFFER_UINT8@@3@Z`
- size: `1968`
- prototype: `int(CBSSEntry *__hidden this, bool, unsigned __int8 *, unsigned __int16, struct MULTIPLE_RSN_INFO *, struct _VARIABLE_LENGTH_BUFFER_UINT8 *, struct _VARIABLE_LENGTH_BUFFER_UINT8 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x140014f20`

## callees

- `0x140009420`
- `0x14000a030`
- `0x14000a34c`
- `0x14000a390`
- `0x14000aff0`
- `0x14000c864`
- `0x14000c940`
- `0x140013920`
- `0x14001bd10`
- `0x140024a20`
- `0x140029d24`
- `0x14002bf94`
- `0x14003abf4`
- `0x140095ff0`
- `0x1400dfe00`
- `0x1400e0100`

## pseudocode

```c
__int64 __fastcall CBSSEntry::UpdateVariableBuffersForBeaconOrProbeResponse(
        CBSSEntry *this,
        unsigned __int8 a2,
        char *a3,
        unsigned __int16 a4,
        struct MULTIPLE_RSN_INFO *a5,
        struct _VARIABLE_LENGTH_BUFFER_UINT8 *a6,
        struct _VARIABLE_LENGTH_BUFFER_UINT8 *a7)
{
  __int64 v7; // r15
  char *v10; // rbx
  char *v11; // r14
  char v12; // cl
  int v13; // eax
  int v14; // edx
  unsigned __int64 v15; // xmm1_8
  char v16; // r8
  __int128 v17; // xmm0
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // r9
  __int64 v21; // rdx
  unsigned __int16 v22; // bx
  int IsEnabledDeviceUsageNoInline; // eax
  int v24; // r8d
  unsigned __int8 v25; // r12
  char v26; // cl
  struct _VARIABLE_LENGTH_BUFFER_UINT8 *v27; // rdi
  size_t v28; // rsi
  void *v29; // r14
  void *v30; // rcx
  struct MULTIPLE_RSN_INFO *v31; // r9
  CBSSEntry *v32; // rcx
  unsigned __int16 v33; // r8
  unsigned __int8 *v34; // rdx
  char v35; // al
  char v36[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *Src[4]; // [rsp+48h] [rbp-B8h] BYREF
  char *v38; // [rsp+68h] [rbp-98h]
  _OWORD v39[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h] BYREF
  __int64 v41; // [rsp+98h] [rbp-68h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v45[23]; // [rsp+B9h] [rbp-47h]
  char v46; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v47[23]; // [rsp+D9h] [rbp-27h]
  char v48; // [rsp+F0h] [rbp-10h]
  int v49; // [rsp+F1h] [rbp-Fh]
  __int16 v50; // [rsp+F5h] [rbp-Bh]
  char v51; // [rsp+F7h] [rbp-9h]
  bool v52; // [rsp+100h] [rbp+0h] BYREF
  int v53; // [rsp+101h] [rbp+1h]
  __int16 v54; // [rsp+105h] [rbp+5h]
  char v55; // [rsp+107h] [rbp+7h]
  __int64 v56; // [rsp+108h] [rbp+8h]
  void *v57[3]; // [rsp+110h] [rbp+10h] BYREF
  void *v58[3]; // [rsp+128h] [rbp+28h] BYREF
  void *v59[3]; // [rsp+140h] [rbp+40h] BYREF
  void *v60[3]; // [rsp+158h] [rbp+58h] BYREF
  void *v61[3]; // [rsp+170h] [rbp+70h] BYREF
  void *v62[3]; // [rsp+188h] [rbp+88h] BYREF
  void *v63[3]; // [rsp+1A0h] [rbp+A0h] BYREF
  void *v64[3]; // [rsp+1B8h] [rbp+B8h] BYREF
  void *v65[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v66[6]; // [rsp+1F0h] [rbp+F0h] BYREF
  bool v67; // [rsp+220h] [rbp+120h] BYREF
  __int16 v68; // [rsp+221h] [rbp+121h]
  char v69; // [rsp+223h] [rbp+123h]
  __int64 v70; // [rsp+228h] [rbp+128h]
  char v71[24]; // [rsp+230h] [rbp+130h] BYREF
  char v72[24]; // [rsp+248h] [rbp+148h] BYREF
  char v73[24]; // [rsp+260h] [rbp+160h] BYREF
  char v74[24]; // [rsp+278h] [rbp+178h] BYREF
  char v75[24]; // [rsp+290h] [rbp+190h] BYREF
  char v76[24]; // [rsp+2A8h] [rbp+1A8h] BYREF
  char v77[24]; // [rsp+2C0h] [rbp+1C0h] BYREF
  char v78[24]; // [rsp+2D8h] [rbp+1D8h] BYREF
  char v79[24]; // [rsp+2F0h] [rbp+1F0h] BYREF
  char v80; // [rsp+308h] [rbp+208h]
  CBSSEntry *v81; // [rsp+350h] [rbp+250h] BYREF
  unsigned __int8 v82; // [rsp+358h] [rbp+258h]
  int v83; // [rsp+368h] [rbp+268h]

  v82 = a2;
  v81 = this;
  v7 = a4;
  if ( a4 <= 0xCu )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        (_DWORD)a3,
        71,
        (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
        a4,
        12);
    *(_WORD *)a6 = 0;
    return 3221225485LL;
  }
  memset(a5, 0, 0x1C0u);
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  utl::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>(v57);
  utl::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>(v58);
  utl::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>(v59);
  utl::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>(v60);
  utl::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>(v61);
  utl::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>(v62);
  utl::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>(v63);
  utl::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>(v64);
  utl::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>::vector<wlan::parsers::TlvView<unsigned char,unsigned char>,utl::allocator<wlan::parsers::TlvView<unsigned char,unsigned char>>>(v65);
  v40 = 0;
  v66[0] = &v52;
  v42 = 0;
  v66[1] = &v40;
  v41 = 0;
  v66[2] = &v44;
  v66[3] = &v42;
  v66[4] = &v41;
  v66[5] = &v43;
  Src[1] = a3 + 12;
  Src[2] = (void *)(v7 - 12);
  v44 = 0;
  v43 = 0;
  LOBYTE(Src[0]) = 1;
  wlan::parsers::details::TlvWalker<wlan::parsers::TlvView<unsigned char,unsigned char>,0>::GetNextTlv(Src, &v46);
  v10 = (char *)Src[2];
  v11 = (char *)Src[1];
  v12 = v48;
  LOBYTE(v83) = Src[0];
  while ( v12 )
  {
    v13 = wlan::parsers::GatherRsnIEs_::_2_::_lambda_1_::operator()_wlan::parsers::TlvView_unsigned_char_unsigned_char___(
            v66,
            &v46);
    v14 = v13;
    if ( (v13 & 0xC0000000) == 0xC0000000 )
    {
      v83 = v13;
      goto LABEL_23;
    }
    if ( v10 )
    {
      v36[0] = 0;
      memcpy_s(v36, 1u, v11, 1u);
      if ( v10 == (char *)1 )
      {
        v15 = 0;
        v16 = 0;
        LOBYTE(v83) = 0;
        memset(v39, 0, sizeof(v39));
        v12 = 0;
        v17 = *(_OWORD *)((char *)v39 + 1);
      }
      else
      {
        LOBYTE(v81) = 0;
        memcpy_s(&v81, 1u, v11 + 1, 1u);
        v18 = (unsigned __int8)v81;
        v38 = v11 + 2;
        if ( (unsigned __int64)(v10 - 2) >= (unsigned __int8)v81 )
        {
          v20 = (__int64)&v11[(unsigned __int8)v81 + 2];
          *(_DWORD *)((char *)Src + 1) = *(_DWORD *)((char *)&v38 + 1);
          v19 = (__int64)&v10[-(unsigned __int8)v81 - 2];
          *(_WORD *)((char *)Src + 5) = *(_WORD *)((char *)&v38 + 5);
          HIBYTE(Src[0]) = HIBYTE(v38);
          v12 = 1;
          LOBYTE(Src[0]) = (_BYTE)v11 + 2;
        }
        else
        {
          v19 = 0;
          memset(Src, 0, 24);
          v12 = 0;
          v20 = 0;
          v18 = 0;
        }
        if ( v12 )
        {
          v16 = v36[0];
          v10 = (char *)v19;
          v11 = (char *)v20;
          Src[1] = Src[0];
          v15 = v18;
          Src[2] = (void *)v18;
          v12 = 1;
          v17 = *(_OWORD *)((char *)Src + 1);
        }
        else
        {
          v15 = 0;
          LOBYTE(v83) = 0;
          memset(v39, 0, sizeof(v39));
          v16 = 0;
          v17 = *(_OWORD *)((char *)v39 + 1);
        }
      }
    }
    else
    {
      v15 = 0;
      v16 = 0;
      memset(v39, 0, sizeof(v39));
      v12 = 0;
      v17 = *(_OWORD *)((char *)v39 + 1);
    }
    *(_OWORD *)v45 = v17;
    v49 = *(_DWORD *)((char *)&v39[1] + 9);
    *(_QWORD *)&v45[15] = v15;
    v50 = *(_WORD *)((char *)&v39[1] + 13);
    *(_OWORD *)v47 = *(_OWORD *)v45;
    v51 = HIBYTE(v39[1]);
    *(_QWORD *)&v47[15] = v15;
    v46 = v16;
    v48 = v12;
  }
  v14 = 0;
  if ( !(_BYTE)v83 )
    v14 = -1073739509;
  v83 = v14;
LABEL_23:
  if ( (v14 & 0xC0000000) == 0xC0000000 )
  {
    v68 = *(_WORD *)((char *)&v83 + 1);
    v69 = HIBYTE(v83);
    v67 = v14;
    v80 = 0;
    wlan::parsers::RsnIEsView::~RsnIEsView((wlan::parsers::RsnIEsView *)&v52);
  }
  else
  {
    if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline() && v40 && (v42 || v41) && (v44 || v43) )
    {
      v21 = v40 + v42 + v44 + v43 + v41 + 4;
      v56 = v21;
    }
    else
    {
      v21 = v56;
    }
    v70 = v21;
    v67 = v52;
    utl::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>(
      v71,
      v57);
    utl::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>(
      v72,
      v58);
    utl::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>(
      v73,
      v59);
    utl::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>(
      v74,
      v60);
    utl::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>(
      v75,
      v61);
    utl::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>(
      v76,
      v62);
    utl::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>(
      v77,
      v63);
    utl::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>(
      v78,
      v64);
    utl::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>::vector<enum RSNA_AKM_SUITE,utl::allocator<enum RSNA_AKM_SUITE>>(
      v79,
      v65);
    v80 = 1;
    if ( v65[0] != (void *)-1LL )
    {
      v65[1] = v65[0];
      operator delete(v65[0]);
    }
    if ( v64[0] != (void *)-1LL )
    {
      v64[1] = v64[0];
      operator delete(v64[0]);
    }
    if ( v63[0] != (void *)-1LL )
    {
      v63[1] = v63[0];
      operator delete(v63[0]);
    }
    if ( v62[0] != (void *)-1LL )
    {
      v62[1] = v62[0];
      operator delete(v62[0]);
    }
    if ( v61[0] != (void *)-1LL )
    {
      v61[1] = v61[0];
      operator delete(v61[0]);
    }
    if ( v60[0] != (void *)-1LL )
    {
      v60[1] = v60[0];
      operator delete(v60[0]);
    }
    if ( v59[0] != (void *)-1LL )
    {
      v59[1] = v59[0];
      operator delete(v59[0]);
    }
    if ( v58[0] != (void *)-1LL )
    {
      v58[1] = v58[0];
      operator delete(v58[0]);
    }
    if ( v57[0] != (void *)-1LL )
    {
      v57[1] = v57[0];
      operator delete(v57[0]);
    }
  }
  v22 = v7;
  IsEnabledDeviceUsageNoInline = Feature_53299205__private_IsEnabledDeviceUsageNoInline();
  v25 = v82;
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( v82 )
    {
      v26 = v80;
      if ( v80 )
      {
        v22 = v7 + v70;
        if ( (unsigned __int16)(v7 + v70) < (unsigned __int16)v7 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_Ld(
              WPP_GLOBAL_Control->DeviceExtension,
              2,
              v24,
              72,
              (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
              v7,
              v70);
            v26 = v80;
          }
          if ( v26 )
            wlan::parsers::RsnIEsView::~RsnIEsView((wlan::parsers::RsnIEsView *)&v67);
          return 3221225485LL;
        }
      }
    }
  }
  v27 = a6;
  if ( *((_QWORD *)a6 + 1) && *((_WORD *)a6 + 1) >= v22 )
  {
    v28 = v22;
LABEL_70:
    if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( v25 && v22 > (unsigned __int16)v7 )
      {
        if ( !v80 )
          __int2c();
        v22 = RsnOParser::IntegrateMRsnOverridesIntoBeacon(
                (RsnOParser *)(unsigned __int16)v7,
                a3,
                (unsigned __int8 *)&v67,
                (struct wlan::parsers::RsnIEsView *)v22,
                *((char **)v27 + 1));
        v33 = v7;
        v34 = (unsigned __int8 *)a3;
      }
      else
      {
        memmove(*((void **)v27 + 1), a3, v28);
        v33 = 0;
        v34 = 0;
      }
      CBSSEntry::UpdateVariableBuffers(v32, v34, v33, a7);
    }
    else
    {
      memmove(*((void **)v27 + 1), a3, v28);
    }
    v35 = v80;
    if ( v80 )
    {
      RsnOParser::GetAllRsnIEs((RsnOParser *)v25, (bool)&v67, a5, v31);
      v35 = v80;
    }
    *(_WORD *)v27 = v22;
    if ( v35 )
      wlan::parsers::RsnIEsView::~RsnIEsView((wlan::parsers::RsnIEsView *)&v67);
    return 0;
  }
  v28 = v22;
  v29 = operator new(v22);
  if ( v29 )
  {
    v30 = (void *)*((_QWORD *)v27 + 1);
    if ( v30 )
      operator delete(v30);
    *((_QWORD *)v27 + 1) = v29;
    *((_WORD *)v27 + 1) = v22;
    goto LABEL_70;
  }
  if ( v80 )
    wlan::parsers::RsnIEsView::~RsnIEsView((wlan::parsers::RsnIEsView *)&v67);
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000a390  mov     [rsp-8+arg_8], dl
0x14000a394  mov     [rsp-8+arg_0], rcx
0x14000a399  push    rbp
0x14000a39a  push    r12
0x14000a39c  push    r13
0x14000a39e  push    r15
0x14000a3a0  lea     rbp, [rsp-228h]
0x14000a3a8  sub     rsp, 328h
0x14000a3af  movzx   r15d, r9w
0x14000a3b3  mov     r13, r8
0x14000a3b6  cmp     r15d, 0Ch
0x14000a3ba  ja      short loc_14000A420
0x14000a3bc  lea     rax, WPP_RECORDER_INITIALIZED
0x14000a3c3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000a3ca  jz      short loc_14000A3FD
0x14000a3cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a3d3  lea     rax, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x14000a3da  mov     [rsp+340h+var_310], 0Ch
0x14000a3e2  mov     r9d, 47h ; 'G'
0x14000a3e8  mov     [rsp+340h+var_318], r15d
0x14000a3ed  mov     dl, 2
0x14000a3ef  mov     qword ptr [rsp+340h+var_320], rax
0x14000a3f4  mov     rcx, [rcx+40h]
0x14000a3f8  call    WPP_RECORDER_SF_Ld
0x14000a3fd  mov     rax, [rbp+240h+arg_28]
0x14000a404  xor     r12d, r12d
0x14000a407  mov     [rax], r12w
0x14000a40b  mov     eax, 0C000000Dh
0x14000a410  add     rsp, 328h
0x14000a417  pop     r15
0x14000a419  pop     r13
0x14000a41b  pop     r12
0x14000a41d  pop     rbp
0x14000a41e  retn
0x14000a420  mov     rcx, [rbp+240h+arg_20]; void *
0x14000a427  xor     edx, edx; Val
0x14000a429  mov     [rsp+340h+arg_10], rbx
0x14000a431  mov     r8d, 1C0h; Size
0x14000a437  mov     [rsp+340h+var_20], rsi
0x14000a43f  mov     [rsp+340h+var_28], rdi
0x14000a447  mov     [rsp+340h+var_30], r14
0x14000a44f  call    memset
0x14000a454  xor     eax, eax
0x14000a456  mov     [rbp+240h+var_240], 0
0x14000a45a  xor     r12d, r12d
0x14000a45d  mov     [rbp+240h+var_23F], eax
0x14000a460  lea     rcx, [rbp+240h+var_230]
0x14000a464  mov     [rbp+240h+var_23B], ax
0x14000a468  mov     [rbp+240h+var_239], al
0x14000a46b  mov     [rbp+240h+var_238], r12
0x14000a46f  call    ??0?$vector@V?$TlvView@EE@parsers@wlan@@V?$allocator@V?$TlvView@EE@parsers@wlan@@@utl@@@utl@@QEAA@XZ; utl::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>(void)
0x14000a474  lea     rcx, [rbp+240h+var_218]
0x14000a478  call    ??0?$vector@V?$TlvView@EE@parsers@wlan@@V?$allocator@V?$TlvView@EE@parsers@wlan@@@utl@@@utl@@QEAA@XZ; utl::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>(void)
0x14000a47d  lea     rcx, [rbp+240h+var_200]
0x14000a481  call    ??0?$vector@V?$TlvView@EE@parsers@wlan@@V?$allocator@V?$TlvView@EE@parsers@wlan@@@utl@@@utl@@QEAA@XZ; utl::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>(void)
0x14000a486  lea     rcx, [rbp+240h+var_1E8]
0x14000a48a  call    ??0?$vector@V?$TlvView@EE@parsers@wlan@@V?$allocator@V?$TlvView@EE@parsers@wlan@@@utl@@@utl@@QEAA@XZ; utl::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>(void)
0x14000a48f  lea     rcx, [rbp+240h+var_1D0]
0x14000a493  call    ??0?$vector@V?$TlvView@EE@parsers@wlan@@V?$allocator@V?$TlvView@EE@parsers@wlan@@@utl@@@utl@@QEAA@XZ; utl::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>(void)
0x14000a498  lea     rcx, [rbp+240h+var_1B8]
0x14000a49f  call    ??0?$vector@V?$TlvView@EE@parsers@wlan@@V?$allocator@V?$TlvView@EE@parsers@wlan@@@utl@@@utl@@QEAA@XZ; utl::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>(void)
0x14000a4a4  lea     rcx, [rbp+240h+var_1A0]
0x14000a4ab  call    ??0?$vector@V?$TlvView@EE@parsers@wlan@@V?$allocator@V?$TlvView@EE@parsers@wlan@@@utl@@@utl@@QEAA@XZ; utl::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>(void)
0x14000a4b0  lea     rcx, [rbp+240h+var_188]
0x14000a4b7  call    ??0?$vector@V?$TlvView@EE@parsers@wlan@@V?$allocator@V?$TlvView@EE@parsers@wlan@@@utl@@@utl@@QEAA@XZ; utl::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>(void)
0x14000a4bc  lea     rcx, [rbp+240h+var_170]
0x14000a4c3  call    ??0?$vector@V?$TlvView@EE@parsers@wlan@@V?$allocator@V?$TlvView@EE@parsers@wlan@@@utl@@@utl@@QEAA@XZ; utl::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>::vector<wlan::parsers::TlvView<uchar,uchar>,utl::allocator<wlan::parsers::TlvView<uchar,uchar>>>(void)
0x14000a4c8  lea     rax, [rbp+240h+var_240]
0x14000a4cc  mov     [rbp+240h+var_2B0], r12
0x14000a4d0  mov     [rbp+240h+var_150], rax
0x14000a4d7  lea     rdx, [rbp+240h+var_268]
0x14000a4db  lea     rax, [rbp+240h+var_2B0]
0x14000a4df  mov     [rbp+240h+var_2A0], r12
0x14000a4e3  mov     [rbp+240h+var_148], rax
0x14000a4ea  lea     rcx, [rsp+340h+Src]
0x14000a4ef  lea     rax, [rbp+240h+var_290]
0x14000a4f3  mov     [rbp+240h+var_2A8], r12
0x14000a4f7  mov     [rbp+240h+var_140], rax
0x14000a4fe  lea     rax, [rbp+240h+var_2A0]
0x14000a502  mov     [rbp+240h+var_138], rax
0x14000a509  lea     rax, [rbp+240h+var_2A8]
0x14000a50d  mov     [rbp+240h+var_130], rax
0x14000a514  lea     rax, [rbp+240h+var_298]
0x14000a518  mov     [rbp+240h+var_128], rax
0x14000a51f  lea     rax, [r13+0Ch]
0x14000a523  mov     [rsp+340h+Src+8], rax
0x14000a528  lea     rax, [r15-0Ch]
0x14000a52c  mov     [rsp+340h+var_2E8], rax
0x14000a531  mov     [rbp+240h+var_290], r12
0x14000a535  mov     [rbp+240h+var_298], r12
0x14000a539  mov     byte ptr [rsp+340h+Src], 1
0x14000a53e  call    ?GetNextTlv@?$TlvWalker@V?$TlvView@EE@parsers@wlan@@$0A@@details@parsers@wlan@@QEAA?AV?$optional@V?$TlvView@EE@parsers@wlan@@@utl@@XZ; wlan::parsers::details::TlvWalker<wlan::parsers::TlvView<uchar,uchar>,0>::GetNextTlv(void)
0x14000a543  movzx   edi, byte ptr [rsp+340h+Src]
0x14000a548  mov     rbx, [rsp+340h+var_2E8]
0x14000a54d  mov     r14, [rsp+340h+Src+8]
0x14000a552  movzx   ecx, [rbp+240h+var_250]
0x14000a556  mov     byte ptr [rbp+240h+arg_18], dil
0x14000a55d  nop     dword ptr [rax]
0x14000a560  test    cl, cl
0x14000a562  jz      loc_14000A721
0x14000a568  lea     rdx, [rbp+240h+var_268]
0x14000a56c  lea     rcx, [rbp+240h+var_150]
0x14000a573  call    _wlan__parsers__GatherRsnIEs____2____lambda_1___operator___wlan__parsers__TlvView_unsigned_char_unsigned_char___
0x14000a578  mov     ecx, eax
0x14000a57a  mov     edx, eax
0x14000a57c  and     ecx, 0C0000000h
0x14000a582  cmp     ecx, 0C0000000h
0x14000a588  jz      loc_14000A719
0x14000a58e  test    rbx, rbx
0x14000a591  jnz     short loc_14000A5AE
0x14000a593  xorps   xmm1, xmm1
0x14000a596  xor     r8b, r8b
0x14000a599  movups  [rsp+340h+var_2D0], xmm1
0x14000a59e  xor     cl, cl
0x14000a5a0  movups  [rbp+240h+var_2C0], xmm1
0x14000a5a4  movups  xmm0, [rsp+340h+var_2D0+1]
0x14000a5a9  jmp     loc_14000A6E2
0x14000a5ae  cmp     rbx, 1
0x14000a5b2  jnb     short loc_14000A5D7
0x14000a5b4  xorps   xmm1, xmm1
0x14000a5b7  xor     al, al
0x14000a5b9  xor     r8b, r8b
0x14000a5bc  mov     byte ptr [rbp+240h+arg_18], al
0x14000a5c2  movups  [rsp+340h+var_2D0], xmm1
0x14000a5c7  xor     cl, cl
0x14000a5c9  movups  [rbp+240h+var_2C0], xmm1
0x14000a5cd  movups  xmm0, [rsp+340h+var_2D0+1]
0x14000a5d2  jmp     loc_14000A6E2
0x14000a5d7  mov     r9d, 1; MaxCount
0x14000a5dd  mov     [rsp+340h+var_300], r12b
0x14000a5e2  mov     edx, r9d; DstSize
0x14000a5e5  lea     rcx, [rsp+340h+var_300]; void *
0x14000a5ea  mov     r8, r14; Src
0x14000a5ed  call    memcpy_s
0x14000a5f2  lea     rdi, [rbx-1]
0x14000a5f6  cmp     rdi, 1
0x14000a5fa  jnb     short loc_14000A61F
0x14000a5fc  xorps   xmm1, xmm1
0x14000a5ff  xor     al, al
0x14000a601  xor     r8b, r8b
0x14000a604  mov     byte ptr [rbp+240h+arg_18], al
0x14000a60a  movups  [rsp+340h+var_2D0], xmm1
0x14000a60f  xor     cl, cl
0x14000a611  movups  [rbp+240h+var_2C0], xmm1
0x14000a615  movups  xmm0, [rsp+340h+var_2D0+1]
0x14000a61a  jmp     loc_14000A6E2
0x14000a61f  mov     r9d, 1; MaxCount
0x14000a625  mov     byte ptr [rbp+240h+arg_0], r12b
0x14000a62c  mov     edx, r9d; DstSize
0x14000a62f  lea     r8, [r14+1]; Src
0x14000a633  lea     rcx, [rbp+240h+arg_0]; void *
0x14000a63a  call    memcpy_s
0x14000a63f  movzx   edx, byte ptr [rbp+240h+arg_0]
0x14000a646  lea     rax, [rdi-1]
0x14000a64a  lea     r8, [r14+2]
0x14000a64e  mov     [rsp+340h+var_2D8], r8
0x14000a653  cmp     rax, rdx
0x14000a656  jnb     short loc_14000A671
0x14000a658  xor     eax, eax
0x14000a65a  xorps   xmm0, xmm0
0x14000a65d  movups  xmmword ptr [rsp+340h+Src], xmm0
0x14000a662  mov     [rsp+340h+var_2E8], rax
0x14000a667  xor     cl, cl
0x14000a669  mov     r9, r12
0x14000a66c  mov     rdx, r12
0x14000a66f  jmp     short loc_14000A69A
0x14000a671  mov     ecx, dword ptr [rsp+340h+var_2D8+1]
0x14000a675  lea     r9, [rdx+r8]
0x14000a679  mov     dword ptr [rsp+340h+Src+1], ecx
0x14000a67d  sub     rax, rdx
0x14000a680  movzx   ecx, word ptr [rsp+340h+var_2D8+5]
0x14000a685  mov     word ptr [rsp+340h+Src+5], cx
0x14000a68a  movzx   ecx, byte ptr [rsp+340h+var_2D8+7]
0x14000a68f  mov     byte ptr [rsp+340h+Src+7], cl
0x14000a693  mov     cl, 1
0x14000a695  mov     byte ptr [rsp+340h+Src], r8b
0x14000a69a  test    cl, cl
0x14000a69c  jnz     short loc_14000A6BB
0x14000a69e  xorps   xmm1, xmm1
0x14000a6a1  mov     byte ptr [rbp+240h+arg_18], r12b
0x14000a6a8  movups  [rsp+340h+var_2D0], xmm1
0x14000a6ad  xor     r8b, r8b
0x14000a6b0  movups  [rbp+240h+var_2C0], xmm1
0x14000a6b4  movups  xmm0, [rsp+340h+var_2D0+1]
0x14000a6b9  jmp     short loc_14000A6E2
0x14000a6bb  movzx   r8d, [rsp+340h+var_300]
0x14000a6c1  mov     rbx, rax
0x14000a6c4  mov     rax, [rsp+340h+Src]
0x14000a6c9  mov     r14, r9
0x14000a6cc  mov     [rsp+340h+Src+8], rax
0x14000a6d1  movq    xmm1, rdx
0x14000a6d6  mov     [rsp+340h+var_2E8], rdx
0x14000a6db  mov     cl, 1
0x14000a6dd  movups  xmm0, xmmword ptr [rsp+340h+Src+1]
0x14000a6e2  mov     eax, dword ptr [rbp+240h+var_2C0+9]
0x14000a6e5  movups  xmmword ptr [rbp+240h+var_287], xmm0
0x14000a6e9  mov     [rbp+240h+var_24F], eax
0x14000a6ec  movzx   eax, word ptr [rbp+240h+var_2C0+0Dh]
0x14000a6f0  movsd   qword ptr [rbp+240h+var_287+0Fh], xmm1
0x14000a6f5  movups  xmm0, xmmword ptr [rbp+240h+var_287]
0x14000a6f9  mov     [rbp+240h+var_24B], ax
0x14000a6fd  movzx   eax, byte ptr [rbp+240h+var_2C0+0Fh]
0x14000a701  movups  xmmword ptr [rbp+240h+var_267], xmm0
0x14000a705  mov     [rbp+240h+var_249], al
0x14000a708  movsd   qword ptr [rbp+240h+var_267+0Fh], xmm1
0x14000a70d  mov     [rbp+240h+var_268], r8b
0x14000a711  mov     [rbp+240h+var_250], cl
0x14000a714  jmp     loc_14000A560
0x14000a719  mov     [rbp+240h+arg_18], eax
0x14000a71f  jmp     short loc_14000A739
0x14000a721  cmp     byte ptr [rbp+240h+arg_18], r12b
0x14000a728  mov     edx, r12d
0x14000a72b  mov     ecx, 0C000090Bh
0x14000a730  cmovz   edx, ecx
0x14000a733  mov     [rbp+240h+arg_18], edx
0x14000a739  mov     eax, edx
0x14000a73b  and     eax, 0C0000000h
0x14000a740  cmp     eax, 0C0000000h
0x14000a745  jnz     short loc_14000A77D
0x14000a747  movzx   eax, word ptr [rbp+240h+arg_18+1]
0x14000a74e  lea     rcx, [rbp+240h+var_240]; this
0x14000a752  mov     [rbp+240h+var_11F], ax
0x14000a759  movzx   eax, byte ptr [rbp+240h+arg_18+3]
0x14000a760  mov     [rbp+240h+var_11D], al
0x14000a766  mov     [rbp+240h+var_120], dl
0x14000a76c  mov     [rbp+240h+var_38], r12b
0x14000a773  call    ??1RsnIEsView@parsers@wlan@@QEAA@XZ; wlan::parsers::RsnIEsView::~RsnIEsView(void)
0x14000a778  jmp     loc_14000A944
0x14000a77d  call    Feature_53299205__private_IsEnabledDeviceUsageNoInline
0x14000a782  test    eax, eax
0x14000a784  jz      short loc_14000A7C9
0x14000a786  mov     rcx, [rbp+240h+var_2B0]
0x14000a78a  test    rcx, rcx
0x14000a78d  jz      short loc_14000A7C9
0x14000a78f  mov     r8, [rbp+240h+var_2A0]
0x14000a793  mov     rdx, [rbp+240h+var_2A8]
0x14000a797  test    r8, r8
0x14000a79a  jnz     short loc_14000A7A1
0x14000a79c  test    rdx, rdx
0x14000a79f  jz      short loc_14000A7C9
0x14000a7a1  mov     r9, [rbp+240h+var_290]
0x14000a7a5  mov     rax, [rbp+240h+var_298]
0x14000a7a9  test    r9, r9
0x14000a7ac  jnz     short loc_14000A7B3
0x14000a7ae  test    rax, rax
0x14000a7b1  jz      short loc_14000A7C9
0x14000a7b3  add     rdx, 4
0x14000a7b7  add     rax, r9
0x14000a7ba  add     rdx, rax
0x14000a7bd  add     rdx, r8
0x14000a7c0  add     rdx, rcx
0x14000a7c3  mov     [rbp+240h+var_238], rdx
0x14000a7c7  jmp     short loc_14000A7CD
0x14000a7c9  mov     rdx, [rbp+240h+var_238]
0x14000a7cd  movzx   eax, [rbp+240h+var_240]
0x14000a7d1  lea     rcx, [rbp+240h+var_110]
0x14000a7d8  mov     [rbp+240h+var_118], rdx
0x14000a7df  lea     rdx, [rbp+240h+var_230]
0x14000a7e3  mov     [rbp+240h+var_120], al
0x14000a7e9  call    ??0?$vector@W4RSNA_AKM_SUITE@@V?$allocator@W4RSNA_AKM_SUITE@@@utl@@@utl@@QEAA@$$QEAV01@@Z; utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>(utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>> &&)
0x14000a7ee  lea     rdx, [rbp+240h+var_218]
0x14000a7f2  lea     rcx, [rbp+240h+var_F8]
0x14000a7f9  call    ??0?$vector@W4RSNA_AKM_SUITE@@V?$allocator@W4RSNA_AKM_SUITE@@@utl@@@utl@@QEAA@$$QEAV01@@Z; utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>(utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>> &&)
0x14000a7fe  lea     rdx, [rbp+240h+var_200]
0x14000a802  lea     rcx, [rbp+240h+var_E0]
0x14000a809  call    ??0?$vector@W4RSNA_AKM_SUITE@@V?$allocator@W4RSNA_AKM_SUITE@@@utl@@@utl@@QEAA@$$QEAV01@@Z; utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>(utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>> &&)
0x14000a80e  lea     rdx, [rbp+240h+var_1E8]
0x14000a812  lea     rcx, [rbp+240h+var_C8]
0x14000a819  call    ??0?$vector@W4RSNA_AKM_SUITE@@V?$allocator@W4RSNA_AKM_SUITE@@@utl@@@utl@@QEAA@$$QEAV01@@Z; utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>(utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>> &&)
0x14000a81e  lea     rdx, [rbp+240h+var_1D0]
0x14000a822  lea     rcx, [rbp+240h+var_B0]
0x14000a829  call    ??0?$vector@W4RSNA_AKM_SUITE@@V?$allocator@W4RSNA_AKM_SUITE@@@utl@@@utl@@QEAA@$$QEAV01@@Z; utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>(utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>> &&)
0x14000a82e  lea     rdx, [rbp+240h+var_1B8]
0x14000a835  lea     rcx, [rbp+240h+var_98]
0x14000a83c  call    ??0?$vector@W4RSNA_AKM_SUITE@@V?$allocator@W4RSNA_AKM_SUITE@@@utl@@@utl@@QEAA@$$QEAV01@@Z; utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>(utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>> &&)
0x14000a841  lea     rdx, [rbp+240h+var_1A0]
0x14000a848  lea     rcx, [rbp+240h+var_80]
0x14000a84f  call    ??0?$vector@W4RSNA_AKM_SUITE@@V?$allocator@W4RSNA_AKM_SUITE@@@utl@@@utl@@QEAA@$$QEAV01@@Z; utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>(utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>> &&)
0x14000a854  lea     rdx, [rbp+240h+var_188]
0x14000a85b  lea     rcx, [rbp+240h+var_68]
0x14000a862  call    ??0?$vector@W4RSNA_AKM_SUITE@@V?$allocator@W4RSNA_AKM_SUITE@@@utl@@@utl@@QEAA@$$QEAV01@@Z; utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>(utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>> &&)
0x14000a867  lea     rdx, [rbp+240h+var_170]
0x14000a86e  lea     rcx, [rbp+240h+var_50]
0x14000a875  call    ??0?$vector@W4RSNA_AKM_SUITE@@V?$allocator@W4RSNA_AKM_SUITE@@@utl@@@utl@@QEAA@$$QEAV01@@Z; utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>>(utl::vector<RSNA_AKM_SUITE,utl::allocator<RSNA_AKM_SUITE>> &&)
0x14000a87a  mov     rcx, [rbp+240h+var_170]; void *
0x14000a881  mov     [rbp+240h+var_38], 1
0x14000a888  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000a88c  jz      short loc_14000A89A
0x14000a88e  mov     [rbp+240h+var_168], rcx
0x14000a895  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000a89a  mov     rcx, [rbp+240h+var_188]; void *
0x14000a8a1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000a8a5  jz      short loc_14000A8B3
0x14000a8a7  mov     [rbp+240h+var_180], rcx
0x14000a8ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000a8b3  mov     rcx, [rbp+240h+var_1A0]; void *
0x14000a8ba  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000a8be  jz      short loc_14000A8CC
0x14000a8c0  mov     [rbp+240h+var_198], rcx
0x14000a8c7  call    ??3@YAXPEAX@Z; operator delete(void *)
  ... truncated ...
```
