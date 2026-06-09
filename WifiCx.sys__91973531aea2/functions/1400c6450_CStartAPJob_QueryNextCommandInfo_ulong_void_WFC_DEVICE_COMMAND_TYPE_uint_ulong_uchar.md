# CStartAPJob::QueryNextCommandInfo(ulong,void * *,_WFC_DEVICE_COMMAND_TYPE *,uint *,ulong *,uchar * *)

- ea: `0x1400c6450`
- end: `0x1400c6eac`
- name: `?QueryNextCommandInfo@CStartAPJob@@MEAAHKPEAPEAXPEAW4_WFC_DEVICE_COMMAND_TYPE@@PEAIPEAKPEAPEAE@Z`
- size: `2652`
- prototype: `__int64 __fastcall(CStartAPJob *__hidden this, unsigned int, void **, enum _WFC_DEVICE_COMMAND_TYPE *, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400069dc`
- `0x140016d00`
- `0x140017130`
- `0x140019d44`
- `0x14001a630`
- `0x14001d790`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140024a20`
- `0x14002bd34`
- `0x140040cc0`
- `0x14005ab30`
- `0x1400683ac`
- `0x1400684cc`
- `0x140071720`
- `0x1400735b4`
- `0x1400c4820`
- `0x1400c491c`
- `0x1400c49cc`
- `0x1400c6450`

## pseudocode

```c
__int64 __fastcall CStartAPJob::QueryNextCommandInfo(
        CStartAPJob *this,
        int a2,
        void **a3,
        enum _WFC_DEVICE_COMMAND_TYPE *a4,
        unsigned __int8 *a5,
        unsigned int *a6,
        unsigned __int8 **a7)
{
  int v10; // r8d
  CPropertyCache *PortPropertyCache; // r15
  __int64 *v12; // rdx
  unsigned int *v13; // rax
  unsigned int *v14; // r14
  unsigned __int8 **v15; // rax
  int PropertyList; // eax
  int v17; // edx
  int v18; // r8d
  int v19; // ecx
  int v20; // r9d
  unsigned __int8 *v21; // rcx
  _DWORD *v22; // r13
  int v23; // edx
  unsigned int PropertyBoolean; // ebx
  int v25; // r8d
  int v26; // r9d
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  __int64 v31; // rcx
  char v32; // bl
  __int64 AuthForGO; // rax
  __int64 v34; // r9
  __int64 v35; // r8
  unsigned int v36; // edi
  __int64 v37; // rcx
  __int64 v38; // r9
  __int64 v39; // r8
  __int64 v40; // rcx
  int PropertyBuffer; // eax
  __int64 v42; // rdx
  unsigned int v43; // r8d
  unsigned __int64 v44; // rdi
  int v45; // r12d
  unsigned __int8 *v46; // rbx
  char v47; // al
  unsigned int v48; // ecx
  unsigned int v49; // eax
  unsigned int i; // ecx
  unsigned __int8 *v51; // r10
  _DWORD *v52; // r14
  __int64 v53; // r8
  __int64 v54; // r12
  unsigned int v55; // eax
  int v56; // eax
  __int64 v57; // r9
  unsigned __int8 *v58; // r8
  __int64 v59; // r9
  unsigned __int8 *v60; // r10
  int v61; // eax
  char v62; // al
  int v63; // edx
  int v64; // r8d
  char v65; // [rsp+28h] [rbp-50h]
  int v66; // [rsp+30h] [rbp-48h]
  __int64 v67; // [rsp+38h] [rbp-40h]
  unsigned __int8 *v68; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int8 *v69; // [rsp+58h] [rbp-20h] BYREF
  unsigned int v70; // [rsp+C0h] [rbp+48h] BYREF
  int v71; // [rsp+C8h] [rbp+50h]
  unsigned int v72; // [rsp+D0h] [rbp+58h] BYREF
  unsigned int v73; // [rsp+D8h] [rbp+60h] BYREF

  v71 = a2;
  PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
  v68 = 0;
  v72 = 0;
  LOWORD(v70) = 0;
  v73 = 0;
  v12 = WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v12,
      v10,
      10,
      (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  v13 = (unsigned int *)a5;
  v14 = a6;
  *a3 = 0;
  *(_DWORD *)a4 = 2;
  *v13 = 14;
  v15 = a7;
  *v14 = 0;
  a5 = 0;
  *v15 = 0;
  if ( *((_BYTE *)this + 1096) )
  {
    PropertyList = CPropertyCache::GetPropertyList(PortPropertyCache, 5u, &v72, (unsigned __int16 *)&v70, &a5);
    if ( PropertyList || v72 != 36 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 3221225860LL;
      v20 = 11;
LABEL_111:
      LOBYTE(v17) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        v18,
        v20,
        (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        PropertyList);
      return 3221225860LL;
    }
    v19 = *(_DWORD *)a5;
    *((_QWORD *)this + 140) = a5 + 4;
  }
  else
  {
    PropertyList = CPropertyCache::GetPropertyBuffer(PortPropertyCache, 0x3Au, &v72, &a5);
    if ( PropertyList || v72 != 44 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 3221225860LL;
      v20 = 12;
      goto LABEL_111;
    }
    v21 = a5;
    *((_QWORD *)this + 140) = a5 + 12;
    v19 = *((_DWORD *)v21 + 2);
  }
  v22 = (_DWORD *)((char *)this + 1104);
  *((_DWORD *)this + 278) = v19;
  CPropertyCache::GetPropertyULong(PortPropertyCache, 0x42u, (unsigned int *)this + 284);
  PropertyBoolean = CPropertyCache::GetPropertyBoolean(PortPropertyCache, 0x45u, (unsigned __int8 *)this + 1145);
  if ( PropertyBoolean )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return PropertyBoolean;
    v26 = 13;
    goto LABEL_17;
  }
  PropertyBoolean = CPropertyCache::GetPropertyULong(PortPropertyCache, 0x43u, (unsigned int *)this + 285);
  if ( PropertyBoolean )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return PropertyBoolean;
    v26 = 14;
    goto LABEL_17;
  }
  PropertyList = CPropertyCache::GetPropertyList(
                   PortPropertyCache,
                   7u,
                   &v72,
                   (unsigned __int16 *)&v70,
                   (unsigned __int8 **)this + 145);
  v28 = (unsigned __int16)v70;
  *((_DWORD *)this + 288) = (unsigned __int16)v70;
  if ( PropertyList || !v28 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return 3221225860LL;
    v20 = 15;
    goto LABEL_111;
  }
  PropertyList = CPropertyCache::GetPropertyList(
                   PortPropertyCache,
                   9u,
                   &v72,
                   (unsigned __int16 *)&v70,
                   (unsigned __int8 **)this + 151);
  v29 = (unsigned __int16)v70;
  *((_DWORD *)this + 300) = (unsigned __int16)v70;
  if ( PropertyList || !v29 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return 3221225860LL;
    v20 = 16;
    goto LABEL_111;
  }
  PropertyList = CPropertyCache::GetPropertyList(
                   PortPropertyCache,
                   8u,
                   &v72,
                   (unsigned __int16 *)&v70,
                   (unsigned __int8 **)this + 148);
  v30 = (unsigned __int16)v70;
  *((_DWORD *)this + 294) = (unsigned __int16)v70;
  if ( PropertyList || !v30 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return 3221225860LL;
    v20 = 17;
    goto LABEL_111;
  }
  PropertyBoolean = CPropertyCache::GetPropertyULong(PortPropertyCache, 0x18u, &v73);
  if ( PropertyBoolean )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return PropertyBoolean;
    v26 = 18;
LABEL_17:
    LODWORD(v67) = PropertyBoolean;
    v66 = *((_DWORD *)this + 4);
    v65 = (char)this;
LABEL_18:
    LOBYTE(v23) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v23,
      v25,
      v26,
      (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
      v65,
      v66,
      v67);
    return PropertyBoolean;
  }
  v32 = v73;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v23) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v23,
      1,
      19,
      (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
      v73,
      *((_DWORD *)this + 140));
  }
  if ( (v32 & 0x20) != 0 )
  {
    AuthForGO = CStartAPJob::GetAuthForGO(v31, &v69, *((unsigned int *)this + 288), *((_QWORD *)this + 145));
    v34 = *((_QWORD *)this + 148);
    v35 = *((unsigned int *)this + 294);
    *((_QWORD *)this + 157) = *(_QWORD *)AuthForGO;
    *((_DWORD *)this + 316) = *(_DWORD *)(AuthForGO + 8);
    *((_DWORD *)this + 288) = *((_DWORD *)this + 314);
    *((_QWORD *)this + 145) = (char *)this + 1260;
    v36 = *((_DWORD *)this + 315);
    *((_DWORD *)this + 318) = CStartAPJob::GetCipherForGO(v37, v36, v35, v34);
    v38 = *((_QWORD *)this + 151);
    v39 = *((unsigned int *)this + 300);
    *((_QWORD *)this + 148) = (char *)this + 1272;
    *((_DWORD *)this + 294) = 1;
    *((_DWORD *)this + 317) = CStartAPJob::GetCipherForGO(v40, v36, v39, v38);
    *((_DWORD *)this + 300) = 1;
    *((_QWORD *)this + 151) = (char *)this + 1268;
  }
  PropertyBuffer = CPropertyCache::GetPropertyBuffer(PortPropertyCache, 0x41u, &v72, &v68);
  v44 = v72;
  v45 = PropertyBuffer;
  if ( PropertyBuffer || v72 < 4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v42) = 4;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v42,
        v43,
        20,
        (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        PropertyBuffer,
        v72);
    }
    goto LABEL_93;
  }
  v46 = v68;
  if ( v68[1] )
  {
    if ( v72 >= 0xA && (v47 = v68[8]) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v42) = 4;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v42,
          v43,
          v45 + 21,
          (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v68[7],
          v47);
      }
      *v22 |= 1u;
      *((_BYTE *)this + 1227) = v46[7];
      *((_DWORD *)this + 307) = v46[8];
      *((_WORD *)this + 612) = *((_WORD *)v46 + 2);
      *((_BYTE *)this + 1226) = v46[6];
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v42) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v42,
        v43,
        22,
        (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
  }
  if ( v46[1] < 2u )
    goto LABEL_86;
  if ( (unsigned int)v44 < 0x18 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v42) = 2;
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        v42,
        v43,
        28,
        (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
        v44,
        24);
    }
    goto LABEL_86;
  }
  *((_BYTE *)this + 1146) = v46[9];
  *((_BYTE *)this + 1147) = v46[10];
  v42 = *((unsigned int *)v46 + 3);
  if ( !(_DWORD)v42
    || (v48 = *((_DWORD *)v46 + 4), v48 < 0x18)
    || (v49 = *((_DWORD *)v46 + 5), v49 < 8)
    || (unsigned int)v44 < v48 + v49 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v42) = 2;
      WPP_RECORDER_SF_dddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v42,
        v43,
        27,
        (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
        v44,
        *((_DWORD *)v46 + 3),
        *((_DWORD *)v46 + 4),
        *((_DWORD *)v46 + 5));
    }
    goto LABEL_86;
  }
  LODWORD(a5) = ArrayOfElements<_WDI_AP_BAND_CHANNEL_LIST_CONTAINER>::AllocateElements((char *)this + 1232, v42, 0);
  LOBYTE(v45) = (_BYTE)a5;
  if ( (_DWORD)a5 )
    goto LABEL_86;
  v43 = *((_DWORD *)v46 + 4);
  v72 = v43;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v67) = *((_DWORD *)v46 + 3);
    LOBYTE(v42) = 4;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v42,
      v43,
      23,
      (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v67);
    v43 = v72;
  }
  for ( i = 0; ; i = v70 + 1 )
  {
    v70 = i;
    if ( i >= *((_DWORD *)v46 + 3) )
      goto LABEL_79;
    v42 = v43 + 8;
    v51 = &v46[v43];
    v69 = v51;
    v52 = v51 + 4;
    if ( (unsigned int)v44 < (unsigned int)v42 )
      goto LABEL_74;
    v53 = (unsigned int)*v52;
    if ( v44 < v42 + 4 * v53 )
    {
      LOBYTE(i) = v70;
      v43 = v72;
LABEL_74:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        if ( (unsigned int)v44 >= (unsigned int)v42 )
          v61 = 4 * *v52;
        else
          LOBYTE(v61) = 0;
        LOBYTE(v42) = 2;
        WPP_RECORDER_SF_ddddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v42,
          v43,
          24,
          (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
          i,
          v44,
          v43,
          8,
          v61);
      }
LABEL_79:
      LOBYTE(v45) = (_BYTE)a5;
      goto LABEL_80;
    }
    v54 = 32LL * v70;
    v68 = (unsigned __int8 *)*((_QWORD *)this + 155);
    v73 = 4 * v53;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( (_DWORD)v53 )
        v55 = *((_DWORD *)v51 + 2);
      else
        LOBYTE(v55) = 0;
      LOBYTE(v42) = 4;
      WPP_RECORDER_SF_dddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v42,
        v53,
        25,
        (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
        v70,
        *(_DWORD *)v51,
        v53,
        v55);
      v51 = v69;
    }
    v56 = CDot11ToWabiConverter::MapBandID(*(unsigned int *)v51);
    *(_DWORD *)(v54 + v57 + 4) = v56;
    v42 = (unsigned int)*v52;
    if ( (_DWORD)v42 )
      break;
LABEL_70:
    v43 = v73 + v72 + 8;
    v72 = v43;
  }
  LODWORD(a5) = ArrayOfElements<enum _WDI_BAND_ID>::AllocateElements(v57 + v54 + 8, v42, 0);
  if ( !(_DWORD)a5 )
  {
    v58 = v68;
    v59 = 0;
    if ( *v52 )
    {
      v60 = v69;
      do
      {
        *(_DWORD *)(*(_QWORD *)&v58[v54 + 16] + 4 * v59) = *(_DWORD *)&v60[4 * v59 + 8];
        v59 = (unsigned int)(v59 + 1);
      }
      while ( (unsigned int)v59 < *v52 );
    }
    *(_DWORD *)&v58[v54] |= 1u;
    goto LABEL_70;
  }
  LOBYTE(v45) = (_BYTE)a5;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v42) = 2;
    WPP_RECORDER_SF_Ld(
      WPP_GLOBAL_Control->DeviceExtension,
      v42,
      v43,
      26,
      (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
      *v52,
      (char)a5);
  }
LABEL_80:
  if ( v70 >= *((_DWORD *)v46 + 3) )
    *v22 |= 2u;
LABEL_86:
  if ( v46[1] >= 3u )
  {
    if ( (unsigned int)v44 < 0x1C )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v42) = 2;
        WPP_RECORDER_SF_Ld(
          WPP_GLOBAL_Control->DeviceExtension,
          v42,
          v43,
          29,
          (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
          v44,
          28);
      }
    }
    else
    {
      *((_BYTE *)this + 1148) = v46[24];
    }
  }
  v62 = v46[1];
  if ( (unsigned __int8)v62 > 3u && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v42) = 2;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v42,
      v43,
      30,
      (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v45,
      v62);
  }
  LODWORD(v14) = (_DWORD)a6;
LABEL_93:
  if ( !(unsigned int)CPropertyCache::SetPropertyBoolean(PortPropertyCache, 0x46u, *((_BYTE *)this + 1146)) )
  {
    PropertyBoolean = GenerateWdiTaskStartApToIhv(
                        (int)this + 1104,
                        v71,
                        (unsigned int)*((_QWORD *)this + 67) + 5384,
                        (_DWORD)v14,
                        (__int64)a7);
    if ( !PropertyBoolean || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return PropertyBoolean;
    v26 = 32;
    LODWORD(v67) = PropertyBoolean;
    v66 = *((_DWORD *)this + 4);
    v65 = (char)this;
    goto LABEL_18;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v63) = 4;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v63,
      v64,
      31,
      (__int64)WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  return 3221225860LL;
}

```

## disassembly

```asm
0x1400c6450  mov     [rsp-40h+arg_8], edx
0x1400c6454  push    rbp
0x1400c6455  push    rbx
0x1400c6456  push    rsi
0x1400c6457  push    rdi
0x1400c6458  push    r12
0x1400c645a  push    r13
0x1400c645c  push    r14
0x1400c645e  push    r15
0x1400c6460  mov     rbp, rsp
0x1400c6463  sub     rsp, 78h
0x1400c6467  mov     rbx, r9
0x1400c646a  mov     rdi, r8
0x1400c646d  mov     rsi, rcx
0x1400c6470  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400c6475  xor     r12d, r12d
0x1400c6478  mov     r15, rax
0x1400c647b  mov     [rbp+var_28], r12
0x1400c647f  mov     [rbp+arg_10], r12d
0x1400c6483  mov     word ptr [rbp+arg_0], r12w
0x1400c6488  mov     [rbp+arg_18], r12d
0x1400c648c  lea     r13, WPP_RECORDER_INITIALIZED
0x1400c6493  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400c649a  lea     rdx, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c64a1  jz      short loc_1400C64D9
0x1400c64a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c64aa  cmp     byte ptr [rcx+29h], 5
0x1400c64ae  jnb     short loc_1400C64B7
0x1400c64b0  cmp     [rcx+48h], r12w
0x1400c64b5  jz      short loc_1400C64D9
0x1400c64b7  mov     eax, [rsi+10h]
0x1400c64ba  mov     r9d, 0Ah
0x1400c64c0  mov     rcx, [rcx+40h]
0x1400c64c4  mov     [rsp+78h+var_48], eax
0x1400c64c8  mov     [rsp+78h+var_50], rsi
0x1400c64cd  mov     [rsp+78h+var_58], rdx
0x1400c64d2  mov     dl, 5
0x1400c64d4  call    WPP_RECORDER_SF_qD
0x1400c64d9  mov     rax, [rbp+arg_20]
0x1400c64dd  lea     r8, [rbp+arg_10]; unsigned int *
0x1400c64e1  mov     r14, [rbp+arg_28]
0x1400c64e5  mov     rcx, r15; this
0x1400c64e8  mov     [rdi], r12
0x1400c64eb  mov     dword ptr [rbx], 2
0x1400c64f1  mov     dword ptr [rax], 0Eh
0x1400c64f7  mov     rax, [rbp+arg_30]
0x1400c64fb  mov     [r14], r12d
0x1400c64fe  mov     [rbp+arg_20], r12
0x1400c6502  mov     [rax], r12
0x1400c6505  cmp     [rsi+448h], r12b
0x1400c650c  jz      short loc_1400C655A
0x1400c650e  lea     rax, [rbp+arg_20]
0x1400c6512  mov     edx, 5; unsigned int
0x1400c6517  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x1400c651b  mov     [rsp+78h+var_58], rax; unsigned __int8 **
0x1400c6520  call    ?GetPropertyList@CPropertyCache@@QEBAHKPEAKPEAGPEAPEAE@Z; CPropertyCache::GetPropertyList(ulong,ulong *,ushort *,uchar * *)
0x1400c6525  test    eax, eax
0x1400c6527  jnz     short loc_1400C6542
0x1400c6529  cmp     [rbp+arg_10], 24h ; '$'
0x1400c652d  jnz     short loc_1400C6542
0x1400c652f  mov     rax, [rbp+arg_20]
0x1400c6533  mov     ecx, [rax]
0x1400c6535  add     rax, 4
0x1400c6539  mov     [rsi+460h], rax
0x1400c6540  jmp     short loc_1400C658C
0x1400c6542  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400c6549  jz      loc_1400C6E95
0x1400c654f  mov     r9d, 0Bh
0x1400c6555  jmp     loc_1400C6E67
0x1400c655a  lea     r9, [rbp+arg_20]; unsigned __int8 **
0x1400c655e  mov     edx, 3Ah ; ':'; unsigned int
0x1400c6563  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400c6568  test    eax, eax
0x1400c656a  jnz     loc_1400C6E58
0x1400c6570  cmp     [rbp+arg_10], 2Ch ; ','
0x1400c6574  jnz     loc_1400C6E58
0x1400c657a  mov     rcx, [rbp+arg_20]
0x1400c657e  lea     rax, [rcx+0Ch]
0x1400c6582  mov     [rsi+460h], rax
0x1400c6589  mov     ecx, [rcx+8]
0x1400c658c  lea     r13, [rsi+450h]
0x1400c6593  mov     edx, 42h ; 'B'; unsigned int
0x1400c6598  mov     [r13+8], ecx
0x1400c659c  lea     r8, [r13+20h]; unsigned int *
0x1400c65a0  mov     rcx, r15; this
0x1400c65a3  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400c65a8  lea     r8, [r13+29h]; unsigned __int8 *
0x1400c65ac  mov     edx, 45h ; 'E'; unsigned int
0x1400c65b1  mov     rcx, r15; this
0x1400c65b4  call    ?GetPropertyBoolean@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyBoolean(ulong,uchar *)
0x1400c65b9  mov     ebx, eax
0x1400c65bb  test    eax, eax
0x1400c65bd  jz      short loc_1400C660A
0x1400c65bf  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400c65c6  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400c65cd  jz      short loc_1400C6603
0x1400c65cf  mov     r9d, 0Dh
0x1400c65d5  mov     ecx, [rsi+10h]
0x1400c65d8  lea     rax, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c65df  mov     dword ptr [rsp+78h+var_40], ebx
0x1400c65e3  mov     [rsp+78h+var_48], ecx
0x1400c65e7  mov     [rsp+78h+var_50], rsi
0x1400c65ec  mov     [rsp+78h+var_58], rax
0x1400c65f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c65f8  mov     dl, 2
0x1400c65fa  mov     rcx, [rcx+40h]
0x1400c65fe  call    WPP_RECORDER_SF_qDD
0x1400c6603  mov     eax, ebx
0x1400c6605  jmp     loc_1400C6E9A
0x1400c660a  lea     r8, [r13+24h]; unsigned int *
0x1400c660e  mov     edx, 43h ; 'C'; unsigned int
0x1400c6613  mov     rcx, r15; this
0x1400c6616  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400c661b  mov     ebx, eax
0x1400c661d  test    eax, eax
0x1400c661f  jz      short loc_1400C6639
0x1400c6621  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400c6628  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400c662f  jz      short loc_1400C6603
0x1400c6631  mov     r9d, 0Eh
0x1400c6637  jmp     short loc_1400C65D5
0x1400c6639  lea     rax, [r13+38h]
0x1400c663d  mov     edx, 7; unsigned int
0x1400c6642  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x1400c6646  mov     [rsp+78h+var_58], rax; unsigned __int8 **
0x1400c664b  lea     r8, [rbp+arg_10]; unsigned int *
0x1400c664f  mov     rcx, r15; this
0x1400c6652  call    ?GetPropertyList@CPropertyCache@@QEBAHKPEAKPEAGPEAPEAE@Z; CPropertyCache::GetPropertyList(ulong,ulong *,ushort *,uchar * *)
0x1400c6657  movzx   ecx, word ptr [rbp+arg_0]
0x1400c665b  mov     [rsi+480h], ecx
0x1400c6661  test    eax, eax
0x1400c6663  jnz     loc_1400C6E40
0x1400c6669  test    ecx, ecx
0x1400c666b  jz      loc_1400C6E40
0x1400c6671  lea     rax, [r13+68h]
0x1400c6675  mov     edx, 9; unsigned int
0x1400c667a  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x1400c667e  mov     [rsp+78h+var_58], rax; unsigned __int8 **
0x1400c6683  lea     r8, [rbp+arg_10]; unsigned int *
0x1400c6687  mov     rcx, r15; this
0x1400c668a  call    ?GetPropertyList@CPropertyCache@@QEBAHKPEAKPEAGPEAPEAE@Z; CPropertyCache::GetPropertyList(ulong,ulong *,ushort *,uchar * *)
0x1400c668f  movzx   ecx, word ptr [rbp+arg_0]
0x1400c6693  mov     [rsi+4B0h], ecx
0x1400c6699  test    eax, eax
0x1400c669b  jnz     loc_1400C6E28
0x1400c66a1  test    ecx, ecx
0x1400c66a3  jz      loc_1400C6E28
0x1400c66a9  lea     rax, [r13+50h]
0x1400c66ad  mov     edx, 8; unsigned int
0x1400c66b2  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x1400c66b6  mov     [rsp+78h+var_58], rax; unsigned __int8 **
0x1400c66bb  lea     r8, [rbp+arg_10]; unsigned int *
0x1400c66bf  mov     rcx, r15; this
0x1400c66c2  call    ?GetPropertyList@CPropertyCache@@QEBAHKPEAKPEAGPEAPEAE@Z; CPropertyCache::GetPropertyList(ulong,ulong *,ushort *,uchar * *)
0x1400c66c7  movzx   ecx, word ptr [rbp+arg_0]
0x1400c66cb  mov     [rsi+498h], ecx
0x1400c66d1  test    eax, eax
0x1400c66d3  jnz     loc_1400C6E10
0x1400c66d9  test    ecx, ecx
0x1400c66db  jz      loc_1400C6E10
0x1400c66e1  lea     r8, [rbp+arg_18]; unsigned int *
0x1400c66e5  mov     rcx, r15; this
0x1400c66e8  lea     edx, [rax+18h]; unsigned int
0x1400c66eb  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400c66f0  mov     ebx, eax
0x1400c66f2  test    eax, eax
0x1400c66f4  jz      short loc_1400C6715
0x1400c66f6  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400c66fd  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400c6704  jz      loc_1400C6603
0x1400c670a  mov     r9d, 12h
0x1400c6710  jmp     loc_1400C65D5
0x1400c6715  mov     ebx, [rbp+arg_18]
0x1400c6718  lea     rax, WPP_RECORDER_INITIALIZED
0x1400c671f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c6726  mov     r12d, 1
0x1400c672c  jz      short loc_1400C6762
0x1400c672e  mov     eax, [rsi+230h]
0x1400c6734  lea     r9d, [r12+12h]
0x1400c6739  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c6740  mov     r8d, r12d
0x1400c6743  mov     [rsp+78h+var_48], eax
0x1400c6747  mov     dl, 4
0x1400c6749  lea     rax, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c6750  mov     dword ptr [rsp+78h+var_50], ebx
0x1400c6754  mov     [rsp+78h+var_58], rax
0x1400c6759  mov     rcx, [rcx+40h]
0x1400c675d  call    WPP_RECORDER_SF_DD
0x1400c6762  test    bl, 20h
0x1400c6765  jz      loc_1400C680F
0x1400c676b  mov     r9, [rsi+488h]
0x1400c6772  lea     rdx, [rbp+var_20]
0x1400c6776  mov     r8d, [rsi+480h]
0x1400c677d  call    ?GetAuthForGO@CStartAPJob@@IEAA?AUAuthAlgoList@1@IPEAW4_WDI_AUTH_ALGORITHM@@@Z; CStartAPJob::GetAuthForGO(uint,_WDI_AUTH_ALGORITHM *)
0x1400c6782  mov     r9, [rsi+4A0h]
0x1400c6789  lea     rbx, [rsi+4F8h]
0x1400c6790  mov     r8d, [rsi+498h]
0x1400c6797  movsd   xmm0, qword ptr [rax]
0x1400c679b  movsd   qword ptr [rsi+4E8h], xmm0
0x1400c67a3  mov     eax, [rax+8]
0x1400c67a6  mov     [rsi+4F0h], eax
0x1400c67ac  mov     eax, [rsi+4E8h]
0x1400c67b2  mov     [rsi+480h], eax
0x1400c67b8  lea     rax, [rsi+4ECh]
0x1400c67bf  mov     [rsi+488h], rax
0x1400c67c6  mov     edi, [rsi+4ECh]
0x1400c67cc  mov     edx, edi
0x1400c67ce  call    ?GetCipherForGO@CStartAPJob@@IEAA?AW4_WDI_CIPHER_ALGORITHM@@W4_WDI_AUTH_ALGORITHM@@IPEAW42@@Z; CStartAPJob::GetCipherForGO(_WDI_AUTH_ALGORITHM,uint,_WDI_CIPHER_ALGORITHM *)
0x1400c67d3  mov     [rbx], eax
0x1400c67d5  mov     edx, edi
0x1400c67d7  mov     r9, [rsi+4B8h]
0x1400c67de  mov     r8d, [rsi+4B0h]
0x1400c67e5  mov     [rsi+4A0h], rbx
0x1400c67ec  lea     rbx, [rsi+4F4h]
0x1400c67f3  mov     [rsi+498h], r12d
0x1400c67fa  call    ?GetCipherForGO@CStartAPJob@@IEAA?AW4_WDI_CIPHER_ALGORITHM@@W4_WDI_AUTH_ALGORITHM@@IPEAW42@@Z; CStartAPJob::GetCipherForGO(_WDI_AUTH_ALGORITHM,uint,_WDI_CIPHER_ALGORITHM *)
0x1400c67ff  mov     [rbx], eax
0x1400c6801  mov     [rsi+4B0h], r12d
0x1400c6808  mov     [rsi+4B8h], rbx
0x1400c680f  lea     r9, [rbp+var_28]; unsigned __int8 **
0x1400c6813  mov     edx, 41h ; 'A'; unsigned int
0x1400c6818  lea     r8, [rbp+arg_10]; unsigned int *
0x1400c681c  mov     rcx, r15; this
0x1400c681f  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400c6824  mov     edi, [rbp+arg_10]
0x1400c6827  mov     r12d, eax
0x1400c682a  test    eax, eax
0x1400c682c  jnz     loc_1400C6D5C
0x1400c6832  cmp     edi, 4
0x1400c6835  jb      loc_1400C6D5C
0x1400c683b  mov     rbx, [rbp+var_28]
0x1400c683f  cmp     byte ptr [rbx+1], 1
0x1400c6843  jb      loc_1400C68D5
0x1400c6849  cmp     edi, 0Ah
0x1400c684c  jb      loc_1400C6A0C
0x1400c6852  movzx   eax, byte ptr [rbx+8]
0x1400c6856  test    al, al
0x1400c6858  jz      loc_1400C6A0C
0x1400c685e  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400c6865  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400c686c  jz      short loc_1400C68A9
0x1400c686e  movzx   ecx, byte ptr [rbx+7]
0x1400c6872  lea     r9d, [r12+15h]
0x1400c6877  mov     [rsp+78h+var_38], eax
0x1400c687b  mov     dl, 4
0x1400c687d  mov     eax, [rsi+10h]
0x1400c6880  mov     dword ptr [rsp+78h+var_40], ecx
0x1400c6884  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c688b  mov     [rsp+78h+var_48], eax
0x1400c688f  lea     rax, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c6896  mov     [rsp+78h+var_50], rsi
0x1400c689b  mov     [rsp+78h+var_58], rax
0x1400c68a0  mov     rcx, [rcx+40h]
0x1400c68a4  call    WPP_RECORDER_SF_qDdd
0x1400c68a9  or      dword ptr [r13+0], 1
0x1400c68ae  mov     al, [rbx+7]
0x1400c68b1  mov     [rsi+4CBh], al
0x1400c68b7  movzx   eax, byte ptr [rbx+8]
0x1400c68bb  mov     [rsi+4CCh], eax
0x1400c68c1  movzx   eax, word ptr [rbx+4]
0x1400c68c5  mov     [rsi+4C8h], ax
0x1400c68cc  mov     al, [rbx+6]
0x1400c68cf  mov     [rsi+4CAh], al
0x1400c68d5  lea     r14, WPP_RECORDER_INITIALIZED
0x1400c68dc  cmp     byte ptr [rbx+1], 2
0x1400c68e0  jb      loc_1400C6C4F
0x1400c68e6  cmp     edi, 18h
0x1400c68e9  jb      loc_1400C6C16
0x1400c68ef  mov     al, [rbx+9]
0x1400c68f2  mov     [rsi+47Ah], al
0x1400c68f8  mov     al, [rbx+0Ah]
0x1400c68fb  mov     [rsi+47Bh], al
0x1400c6901  mov     edx, [rbx+0Ch]
0x1400c6904  test    edx, edx
0x1400c6906  jz      loc_1400C6BD1
0x1400c690c  mov     ecx, [rbx+10h]
0x1400c690f  cmp     ecx, 18h
0x1400c6912  jb      loc_1400C6BD1
0x1400c6918  mov     eax, [rbx+14h]
0x1400c691b  cmp     eax, 8
0x1400c691e  jb      loc_1400C6BD1
0x1400c6924  add     eax, ecx
0x1400c6926  cmp     edi, eax
0x1400c6928  jb      loc_1400C6BD1
0x1400c692e  lea     rcx, [r13+80h]
0x1400c6935  xor     r8d, r8d
0x1400c6938  call    ?AllocateElements@?$ArrayOfElements@U_WDI_AP_BAND_CHANNEL_LIST_CONTAINER@@@@QEAAHI_K@Z; ArrayOfElements<_WDI_AP_BAND_CHANNEL_LIST_CONTAINER>::AllocateElements(uint,unsigned __int64)
0x1400c693d  mov     dword ptr [rbp+arg_20], eax
0x1400c6940  mov     r12d, eax
0x1400c6943  test    eax, eax
0x1400c6945  jnz     loc_1400C6C4F
0x1400c694b  mov     r8d, [rbx+10h]
0x1400c694f  mov     [rbp+arg_10], r8d
0x1400c6953  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400c695a  jz      short loc_1400C6995
0x1400c695c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c6963  lea     r9d, [rax+17h]
0x1400c6967  mov     eax, [rbx+0Ch]
0x1400c696a  lea     r12, WPP_0375a23a244f3148eb5ba69ebbd77fb2_Traceguids
0x1400c6971  mov     dword ptr [rsp+78h+var_40], eax
  ... truncated ...
```
