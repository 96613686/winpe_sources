# CSetWFDAdvertisementSettings::GetDeviceCommandData(void *,uint,uint *,uint *,uint,ulong *,ulong *,uchar * *)

- ea: `0x140037930`
- end: `0x14003816b`
- name: `?GetDeviceCommandData@CSetWFDAdvertisementSettings@@UEAAHPEAXIPEAI1IPEAK2PEAPEAE@Z`
- size: `2107`
- prototype: `__int64 __usercall@<rax>(CSetWFDAdvertisementSettings *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned int *, unsigned int, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400032f0`
- `0x140016d00`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002bd34`
- `0x140037930`
- `0x140038174`
- `0x14003ffd4`
- `0x140050660`
- `0x140071720`
- `0x140074ba8`
- `0x1400bd5b8`
- `0x1400bf050`

## pseudocode

```c
__int64 __fastcall CSetWFDAdvertisementSettings::GetDeviceCommandData(
        CSetWFDAdvertisementSettings *this,
        char *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned __int8 **a9)
{
  char *v13; // rdx
  int v14; // r8d
  unsigned int WdiSetAdvertisementInformationToIhv; // ebp
  int v16; // esi
  int *v17; // rsi
  unsigned int *v18; // r14
  _DWORD *v19; // r15
  int v20; // r9d
  __int64 v21; // rdx
  unsigned int Elements; // eax
  int v23; // edx
  int v24; // r8d
  unsigned int i; // r10d
  unsigned int v26; // r11d
  unsigned int v27; // r9d
  int v28; // ecx
  unsigned int v29; // eax
  __int64 v30; // r9
  __int64 v31; // rcx
  int v32; // eax
  char *v33; // rax
  unsigned __int8 v34; // si
  CPropertyCache *PortPropertyCache; // rax
  int v36; // r8d
  int v37; // edx
  int v38; // edx
  int v39; // r8d
  char v40; // r9
  char v41; // al
  _DWORD *v42; // rcx
  unsigned __int8 v43; // cl
  unsigned __int8 v44; // r8
  unsigned __int8 v45; // cl
  unsigned __int8 v46; // r8
  unsigned __int8 v47; // cl
  unsigned __int8 v48; // r8
  unsigned __int8 v49; // cl
  int v50; // edx
  int v51; // r8d
  int v52; // ecx
  unsigned int *v54; // [rsp+38h] [rbp-90h]
  char v55; // [rsp+38h] [rbp-90h]
  int v56; // [rsp+40h] [rbp-88h]
  char v57; // [rsp+40h] [rbp-88h]
  char v58; // [rsp+48h] [rbp-80h]
  int v59; // [rsp+50h] [rbp-78h]
  int v60; // [rsp+58h] [rbp-70h]
  int v61; // [rsp+60h] [rbp-68h]
  unsigned int v62[22]; // [rsp+70h] [rbp-58h] BYREF

  if ( !(unsigned int)Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v13) = 5;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v13,
          v14,
          10,
          (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 4;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v13,
          v14,
          11,
          (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          *((_DWORD *)this + 15));
      }
    }
    switch ( *((_DWORD *)this + 15) )
    {
      case 'r':
        v16 = (_DWORD)this + 1112;
        *((_DWORD *)this + 278) |= 4u;
        v43 = (a2[4] != 0) | 2;
        if ( !a2[5] )
          v43 = a2[4] != 0;
        v44 = v43;
        v45 = v43 | 4;
        if ( !a2[6] )
          v45 = v44;
        v46 = v45;
        v47 = v45 | 8;
        if ( !a2[7] )
          v47 = v46;
        v48 = v47;
        v49 = v47 | 0x10;
        if ( !a2[8] )
          v49 = v48;
        v50 = v49;
        v51 = v49 | 0x20;
        if ( !a2[9] )
          v51 = v49;
        *((_BYTE *)this + 1241) = 63;
        *((_BYTE *)this + 1240) = v51;
        v52 = *((_DWORD *)a2 + 3);
        *((_DWORD *)this + 311) = v52;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v50) = 4;
          WPP_RECORDER_SF_qDddd(
            WPP_GLOBAL_Control->DeviceExtension,
            v50,
            v51,
            12,
            (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            v51,
            63,
            v52);
        }
        goto LABEL_79;
      case 's':
        v16 = (_DWORD)this + 1112;
        *((_DWORD *)this + 278) |= 1u;
        v42 = (_DWORD *)((char *)this + 1120);
        if ( *((_DWORD *)a2 + 2) )
        {
          *v42 |= 1u;
          *((_QWORD *)this + 142) = &a2[*((unsigned int *)a2 + 1)];
          *((_DWORD *)this + 282) = *((_DWORD *)a2 + 2);
        }
        if ( *((_DWORD *)a2 + 4) )
        {
          *v42 |= 2u;
          *((_QWORD *)this + 145) = &a2[*((unsigned int *)a2 + 3)];
          *((_DWORD *)this + 288) = *((_DWORD *)a2 + 4);
        }
        if ( *((_DWORD *)a2 + 6) )
        {
          *v42 |= 4u;
          *((_QWORD *)this + 148) = &a2[*((unsigned int *)a2 + 5)];
          *((_DWORD *)this + 294) = *((_DWORD *)a2 + 6);
        }
        goto LABEL_79;
      case 'v':
        v16 = (_DWORD)this + 1112;
        *((_DWORD *)this + 278) |= 2u;
        *((_DWORD *)this + 300) = *((_DWORD *)a2 + 1);
        *((_WORD *)this + 602) = *((_WORD *)a2 + 4);
        *((_WORD *)this + 603) = *((_WORD *)a2 + 5);
        *((_WORD *)this + 604) = *((_WORD *)a2 + 6);
        *((_WORD *)this + 607) = *((_WORD *)a2 + 7);
        *(_DWORD *)((char *)this + 1210) = *((_DWORD *)a2 + 4);
        *((_QWORD *)this + 153) = a2 + 24;
        *((_DWORD *)this + 304) = *((_DWORD *)a2 + 5);
        goto LABEL_79;
    }
    if ( *((_DWORD *)this + 15) != 122 )
    {
      if ( *((_DWORD *)this + 15) != 126 )
      {
        if ( *((_DWORD *)this + 15) == 129 )
        {
          v16 = (_DWORD)this + 1112;
          *((_QWORD *)this + 158) = a2 + 12;
          *((_DWORD *)this + 278) |= 0x10u;
          *((_DWORD *)this + 314) = *((_DWORD *)a2 + 1);
        }
        else
        {
          if ( *((_DWORD *)this + 15) != 170 )
          {
            WdiSetAdvertisementInformationToIhv = -1073741823;
LABEL_80:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
            {
              LOBYTE(v13) = 5;
              LODWORD(v54) = WdiSetAdvertisementInformationToIhv;
              WPP_RECORDER_SF_qDD(
                WPP_GLOBAL_Control->DeviceExtension,
                (_DWORD)v13,
                v14,
                21,
                (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
                (char)this,
                *((_DWORD *)this + 4),
                v54);
            }
            return WdiSetAdvertisementInformationToIhv;
          }
          v16 = (_DWORD)this + 1112;
        }
LABEL_79:
        *a4 = a3;
        *a7 = 89;
        *a8 = 0;
        WdiSetAdvertisementInformationToIhv = GenerateWdiSetAdvertisementInformationToIhv(
                                                v16,
                                                a6,
                                                (unsigned int)*((_QWORD *)this + 67) + 5384,
                                                (_DWORD)a8,
                                                (__int64)a9);
        goto LABEL_80;
      }
      v17 = (int *)(a2 + 36);
      v18 = (unsigned int *)(a2 + 8);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 4;
        WPP_RECORDER_SF_qDddd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v13,
          v14,
          15,
          (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          *v18,
          *((_DWORD *)a2 + 5),
          *v17);
      }
      if ( *v18 && *((_DWORD *)a2 + 3) < 0x28u || *((_DWORD *)a2 + 5) && *((_DWORD *)a2 + 6) < 0x28u )
        goto LABEL_30;
      v17 = (int *)(a2 + 36);
      v13 = (char *)*((unsigned int *)a2 + 9);
      if ( (_DWORD)v13 )
      {
        if ( (unsigned int)v13 < 0x28 || *((_DWORD *)a2 + 8) < 0x28u )
        {
LABEL_30:
          WdiSetAdvertisementInformationToIhv = -1073676267;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v20 = 16;
            v61 = *v17;
            v60 = *((_DWORD *)a2 + 7);
            v59 = *((_DWORD *)a2 + 4);
            v58 = 40;
            v56 = *((_DWORD *)this + 148);
            v55 = 21;
LABEL_32:
            WPP_RECORDER_SF_qDDddddd(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v13,
              v14,
              v20,
              (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
              (char)this,
              *((_DWORD *)this + 4),
              v55,
              v56,
              v58,
              v59,
              v60,
              v61);
            goto LABEL_80;
          }
          return WdiSetAdvertisementInformationToIhv;
        }
        v19 = a2 + 8;
      }
      else
      {
        v19 = a2 + 8;
      }
      if ( (unsigned __int64)&v13[*((unsigned int *)a2 + 4) + 40 + *((unsigned int *)a2 + 7)] > *((unsigned int *)this
                                                                                                + 148) )
        goto LABEL_30;
      v16 = (_DWORD)this + 1112;
      *((_DWORD *)this + 278) |= 0x20u;
      *((_WORD *)this + 656) = *((_WORD *)a2 + 2);
      v21 = (unsigned int)*v19;
      if ( !(_DWORD)v21 )
        goto LABEL_79;
      Elements = ArrayOfElements<_WDI_P2P_ADVERTISED_SERVICE_ENTRY_CONTAINER>::AllocateElements(
                   (char *)this + 1288,
                   v21,
                   0);
      WdiSetAdvertisementInformationToIhv = Elements;
      if ( !Elements )
      {
        v14 = 1;
        *((_DWORD *)this + 320) |= 1u;
        v13 = &a2[*((unsigned int *)a2 + 3)];
        for ( i = 0; i < *v18; ++i )
        {
          v26 = *((_DWORD *)v13 + 42);
          if ( v26 < 0x28
            || (v27 = *((_DWORD *)this + 148), v26 + (unsigned __int8)v13[164] > v27)
            || (v28 = *((_DWORD *)v13 + 43)) != 0 && ((v29 = *((_DWORD *)v13 + 44), v29 < 0x28) || v28 + v29 > v27) )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return WdiSetAdvertisementInformationToIhv;
            v20 = 18;
            v61 = *((_DWORD *)this + 148);
            v60 = *((_DWORD *)v13 + 43);
            v59 = *((_DWORD *)v13 + 44);
            v58 = v13[164];
            LOBYTE(v56) = *((_DWORD *)v13 + 42);
            v55 = 0;
            goto LABEL_32;
          }
          v30 = *((_QWORD *)this + 162);
          v31 = 80LL * i;
          *(_BYTE *)(v31 + v30 + 64) = v13[16];
          *(_DWORD *)(v31 + v30 + 68) = *(_DWORD *)v13;
          *(_WORD *)(v31 + v30 + 72) = *((_WORD *)v13 + 6);
          *(_DWORD *)(v31 + v30 + 8) = (unsigned __int8)v13[164];
          *(_QWORD *)(v31 + v30 + 16) = &a2[*((unsigned int *)v13 + 42)];
          *(_DWORD *)(v31 + v30 + 32) = *((_DWORD *)v13 + 1);
          *(_WORD *)(v31 + v30 + 36) = *((_WORD *)v13 + 4);
          v32 = *((_DWORD *)v13 + 43);
          if ( v32 )
          {
            *(_DWORD *)(v31 + v30 + 40) = v32;
            v33 = &a2[*((unsigned int *)v13 + 44)];
            *(_DWORD *)(v31 + v30) |= 1u;
            *(_QWORD *)(v31 + v30 + 48) = v33;
          }
          v13 += 180;
        }
        goto LABEL_79;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v23) = 2;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v23,
          v24,
          17,
          (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          Elements,
          *v19);
        goto LABEL_80;
      }
      return WdiSetAdvertisementInformationToIhv;
    }
    v34 = 0;
    v62[0] = 0;
    PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
    if ( !(unsigned int)CPropertyCache::GetPropertyULong(PortPropertyCache, 0x18u, v62) )
    {
      v36 = 1;
      v34 = (v62[0] & 0x20) != 0;
    }
    *((_BYTE *)this + 1249) = 0;
    v37 = (unsigned __int8)a2[1];
    if ( v37 == 1 )
    {
      v40 = CDot11ToWabiConverter::MapWFDGroupCapabilities(v34, a2[4], v36, a2[5], a2[6], a2[7], a2[8], 0);
      v41 = 123;
    }
    else
    {
      if ( a2[1] != 2 )
      {
        WdiSetAdvertisementInformationToIhv = -1073676267;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v57 = v37;
          LOBYTE(v37) = 2;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v37,
            v36,
            13,
            (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            21,
            v57);
          goto LABEL_80;
        }
        return WdiSetAdvertisementInformationToIhv;
      }
      v40 = CDot11ToWabiConverter::MapWFDGroupCapabilities(v34, a2[4], v36, a2[5], a2[6], a2[7], a2[8], a2[16]);
      *((_BYTE *)this + 1249) = 0x80;
      v41 = -5;
    }
    *((_BYTE *)this + 1248) = v40;
    v16 = (_DWORD)this + 1112;
    *((_DWORD *)this + 313) = *((_DWORD *)a2 + 3);
    *((_DWORD *)this + 278) |= 8u;
    *((_BYTE *)this + 1249) = v41;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v38) = 4;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v38,
        v39,
        14,
        (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v40,
        v41);
    }
    goto LABEL_79;
  }
  return CSetWFDAdvertisementSettings::GetDeviceCommandData_TLVParserStaging(this, a2, a3, a4, a5, a6, a7, a8, a9);
}

```

## disassembly

```asm
0x140037930  push    rbx
0x140037932  push    rbp
0x140037933  push    rsi
0x140037934  push    rdi
0x140037935  push    r12
0x140037937  push    r13
0x140037939  push    r14
0x14003793b  push    r15
0x14003793d  sub     rsp, 88h
0x140037944  mov     r12, r9
0x140037947  mov     r13d, r8d
0x14003794a  mov     rdi, rdx
0x14003794d  mov     rbx, rcx
0x140037950  call    Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline
0x140037955  xor     r15d, r15d
0x140037958  test    eax, eax
0x14003795a  jnz     loc_140038106
0x140037960  lea     r14, WPP_RECORDER_INITIALIZED
0x140037967  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003796e  lea     rbp, WPP_298b309e0d8a33f8d841b368865bd584_Traceguids
0x140037975  jz      short loc_1400379E6
0x140037977  mov     rcx, cs:WPP_GLOBAL_Control
0x14003797e  cmp     byte ptr [rcx+29h], 5
0x140037982  jnb     short loc_14003798B
0x140037984  cmp     [rcx+48h], r15w
0x140037989  jz      short loc_1400379AD
0x14003798b  mov     eax, [rbx+10h]
0x14003798e  mov     r9d, 0Ah
0x140037994  mov     rcx, [rcx+40h]
0x140037998  mov     dl, 5
0x14003799a  mov     dword ptr [rsp+0C8h+var_98], eax
0x14003799e  mov     qword ptr [rsp+0C8h+var_A0], rbx
0x1400379a3  mov     [rsp+0C8h+var_A8], rbp
0x1400379a8  call    WPP_RECORDER_SF_qD
0x1400379ad  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400379b4  jz      short loc_1400379E6
0x1400379b6  mov     eax, [rbx+3Ch]
0x1400379b9  mov     r9d, 0Bh
0x1400379bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400379c6  mov     dl, 4
0x1400379c8  mov     dword ptr [rsp+0C8h+var_90], eax
0x1400379cc  mov     eax, [rbx+10h]
0x1400379cf  mov     dword ptr [rsp+0C8h+var_98], eax
0x1400379d3  mov     rcx, [rcx+40h]
0x1400379d7  mov     qword ptr [rsp+0C8h+var_A0], rbx
0x1400379dc  mov     [rsp+0C8h+var_A8], rbp
0x1400379e1  call    WPP_RECORDER_SF_qDD
0x1400379e6  mov     ecx, [rbx+3Ch]
0x1400379e9  sub     ecx, 72h ; 'r'
0x1400379ec  jz      loc_140037F99
0x1400379f2  sub     ecx, 1
0x1400379f5  jz      loc_140037F1C
0x1400379fb  sub     ecx, 3
0x1400379fe  jz      loc_140037EBB
0x140037a04  sub     ecx, 4
0x140037a07  jz      loc_140037D48
0x140037a0d  sub     ecx, 4
0x140037a10  jz      short loc_140037A55
0x140037a12  sub     ecx, 3
0x140037a15  jz      short loc_140037A32
0x140037a17  cmp     ecx, 29h ; ')'
0x140037a1a  jz      short loc_140037A26
0x140037a1c  mov     ebp, 0C0000001h
0x140037a21  jmp     loc_1400380B0
0x140037a26  lea     rsi, [rbx+458h]
0x140037a2d  jmp     loc_140038067
0x140037a32  lea     rax, [rdi+0Ch]
0x140037a36  lea     rsi, [rbx+458h]
0x140037a3d  mov     [rbx+4F0h], rax
0x140037a44  or      dword ptr [rsi], 10h
0x140037a47  mov     eax, [rdi+4]
0x140037a4a  mov     [rbx+4E8h], eax
0x140037a50  jmp     loc_140038067
0x140037a55  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140037a5c  lea     rsi, [rdi+24h]
0x140037a60  lea     r14, [rdi+8]
0x140037a64  jz      short loc_140037AA3
0x140037a66  mov     eax, [rsi]
0x140037a68  mov     r9d, 0Fh
0x140037a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140037a75  mov     dl, 4
0x140037a77  mov     dword ptr [rsp+0C8h+var_80], eax
0x140037a7b  mov     eax, [rdi+14h]
0x140037a7e  mov     dword ptr [rsp+0C8h+var_88], eax
0x140037a82  mov     eax, [r14]
0x140037a85  mov     rcx, [rcx+40h]
0x140037a89  mov     dword ptr [rsp+0C8h+var_90], eax
0x140037a8d  mov     eax, [rbx+10h]
0x140037a90  mov     dword ptr [rsp+0C8h+var_98], eax
0x140037a94  mov     qword ptr [rsp+0C8h+var_A0], rbx
0x140037a99  mov     [rsp+0C8h+var_A8], rbp
0x140037a9e  call    WPP_RECORDER_SF_qDddd
0x140037aa3  cmp     [r14], r15d
0x140037aa6  jz      short loc_140037AAE
0x140037aa8  cmp     dword ptr [rdi+0Ch], 28h ; '('
0x140037aac  jb      short loc_140037AF3
0x140037aae  cmp     [rdi+14h], r15d
0x140037ab2  jz      short loc_140037ABA
0x140037ab4  cmp     dword ptr [rdi+18h], 28h ; '('
0x140037ab8  jb      short loc_140037AF3
0x140037aba  lea     rsi, [rdi+24h]
0x140037abe  mov     edx, [rsi]
0x140037ac0  test    edx, edx
0x140037ac2  jz      short loc_140037AD5
0x140037ac4  cmp     edx, 28h ; '('
0x140037ac7  jb      short loc_140037AF3
0x140037ac9  cmp     dword ptr [rdi+20h], 28h ; '('
0x140037acd  jb      short loc_140037AF3
0x140037acf  lea     r15, [rdi+8]
0x140037ad3  jmp     short loc_140037AD8
0x140037ad5  mov     r15, r14
0x140037ad8  mov     eax, [rdi+10h]
0x140037adb  mov     ecx, [rdi+1Ch]
0x140037ade  add     rax, 28h ; '('
0x140037ae2  add     rcx, rax
0x140037ae5  mov     eax, [rbx+250h]
0x140037aeb  add     rcx, rdx
0x140037aee  cmp     rcx, rax
0x140037af1  jbe     short loc_140037B6D
0x140037af3  mov     ebp, 0C0010015h
0x140037af8  lea     r14, WPP_RECORDER_INITIALIZED
0x140037aff  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140037b06  jz      loc_140038102
0x140037b0c  mov     eax, [rsi]
0x140037b0e  mov     r9d, 10h
0x140037b14  mov     [rsp+0C8h+var_68], eax
0x140037b18  mov     eax, [rdi+1Ch]
0x140037b1b  mov     [rsp+0C8h+var_70], eax
0x140037b1f  mov     eax, [rdi+10h]
0x140037b22  mov     [rsp+0C8h+var_78], eax
0x140037b26  mov     eax, [rbx+250h]
0x140037b2c  mov     dword ptr [rsp+0C8h+var_80], 28h ; '('
0x140037b34  mov     dword ptr [rsp+0C8h+var_88], eax
0x140037b38  mov     dword ptr [rsp+0C8h+var_90], 0C0010015h
0x140037b40  mov     rcx, cs:WPP_GLOBAL_Control
0x140037b47  lea     rdi, WPP_298b309e0d8a33f8d841b368865bd584_Traceguids
0x140037b4e  mov     eax, [rbx+10h]
0x140037b51  mov     dword ptr [rsp+0C8h+var_98], eax
0x140037b55  mov     qword ptr [rsp+0C8h+var_A0], rbx
0x140037b5a  mov     rcx, [rcx+40h]
0x140037b5e  mov     [rsp+0C8h+var_A8], rdi
0x140037b63  call    WPP_RECORDER_SF_qDDddddd
0x140037b68  jmp     loc_1400380BE
0x140037b6d  lea     rsi, [rbx+458h]
0x140037b74  or      dword ptr [rsi], 20h
0x140037b77  movzx   eax, word ptr [rdi+4]
0x140037b7b  mov     [rbx+520h], ax
0x140037b82  mov     edx, [r15]
0x140037b85  test    edx, edx
0x140037b87  jz      loc_140037D40
0x140037b8d  lea     rcx, [rbx+508h]
0x140037b94  xor     r8d, r8d
0x140037b97  call    ?AllocateElements@?$ArrayOfElements@U_WDI_P2P_ADVERTISED_SERVICE_ENTRY_CONTAINER@@@@QEAAHI_K@Z; ArrayOfElements<_WDI_P2P_ADVERTISED_SERVICE_ENTRY_CONTAINER>::AllocateElements(uint,unsigned __int64)
0x140037b9c  mov     ebp, eax
0x140037b9e  test    eax, eax
0x140037ba0  jz      short loc_140037BF6
0x140037ba2  lea     r14, WPP_RECORDER_INITIALIZED
0x140037ba9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140037bb0  jz      loc_140038102
0x140037bb6  mov     ecx, [r15]
0x140037bb9  lea     rdi, WPP_298b309e0d8a33f8d841b368865bd584_Traceguids
0x140037bc0  mov     dword ptr [rsp+0C8h+var_88], ecx
0x140037bc4  mov     r9d, 11h
0x140037bca  mov     ecx, [rbx+10h]
0x140037bcd  mov     dl, 2
0x140037bcf  mov     dword ptr [rsp+0C8h+var_90], eax
0x140037bd3  mov     dword ptr [rsp+0C8h+var_98], ecx
0x140037bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140037bde  mov     qword ptr [rsp+0C8h+var_A0], rbx
0x140037be3  mov     [rsp+0C8h+var_A8], rdi
0x140037be8  mov     rcx, [rcx+40h]
0x140037bec  call    WPP_RECORDER_SF_qDdd
0x140037bf1  jmp     loc_1400380BE
0x140037bf6  mov     r8d, 1
0x140037bfc  or      [rbx+500h], r8d
0x140037c03  mov     edx, [rdi+0Ch]
0x140037c06  add     rdx, rdi
0x140037c09  xor     r15d, r15d
0x140037c0c  mov     r10d, r15d
0x140037c0f  cmp     r10d, [r14]
0x140037c12  jnb     loc_140038067
0x140037c18  mov     r11d, [rdx+0A8h]
0x140037c1f  cmp     r11d, 28h ; '('
0x140037c23  jb      loc_140037CEE
0x140037c29  movzx   eax, byte ptr [rdx+0A4h]
0x140037c30  mov     r9d, [rbx+250h]
0x140037c37  add     eax, r11d
0x140037c3a  cmp     eax, r9d
0x140037c3d  ja      loc_140037CEE
0x140037c43  mov     ecx, [rdx+0ACh]
0x140037c49  test    ecx, ecx
0x140037c4b  jz      short loc_140037C67
0x140037c4d  mov     eax, [rdx+0B0h]
0x140037c53  cmp     eax, 28h ; '('
0x140037c56  jb      loc_140037CEE
0x140037c5c  add     eax, ecx
0x140037c5e  cmp     eax, r9d
0x140037c61  ja      loc_140037CEE
0x140037c67  mov     r9, [rbx+510h]
0x140037c6e  mov     eax, r10d
0x140037c71  lea     rcx, [rax+rax*4]
0x140037c75  mov     al, [rdx+10h]
0x140037c78  shl     rcx, 4
0x140037c7c  mov     [rcx+r9+40h], al
0x140037c81  mov     eax, [rdx]
0x140037c83  mov     [rcx+r9+44h], eax
0x140037c88  movzx   eax, word ptr [rdx+0Ch]
0x140037c8c  mov     [rcx+r9+48h], ax
0x140037c92  movzx   eax, byte ptr [rdx+0A4h]
0x140037c99  mov     [rcx+r9+8], eax
0x140037c9e  mov     eax, [rdx+0A8h]
0x140037ca4  add     rax, rdi
0x140037ca7  mov     [rcx+r9+10h], rax
0x140037cac  mov     eax, [rdx+4]
0x140037caf  mov     [rcx+r9+20h], eax
0x140037cb4  movzx   eax, word ptr [rdx+8]
0x140037cb8  mov     [rcx+r9+24h], ax
0x140037cbe  mov     eax, [rdx+0ACh]
0x140037cc4  test    eax, eax
0x140037cc6  jz      short loc_140037CDF
0x140037cc8  mov     [rcx+r9+28h], eax
0x140037ccd  mov     eax, [rdx+0B0h]
0x140037cd3  add     rax, rdi
0x140037cd6  or      [rcx+r9], r8d
0x140037cda  mov     [rcx+r9+30h], rax
0x140037cdf  add     rdx, 0B4h
0x140037ce6  add     r10d, r8d
0x140037ce9  jmp     loc_140037C0F
0x140037cee  lea     r14, WPP_RECORDER_INITIALIZED
0x140037cf5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140037cfc  jz      loc_140038102
0x140037d02  mov     eax, [rbx+250h]
0x140037d08  mov     r9d, 12h
0x140037d0e  movzx   ecx, byte ptr [rdx+0A4h]
0x140037d15  mov     [rsp+0C8h+var_68], eax
0x140037d19  mov     eax, [rdx+0ACh]
0x140037d1f  mov     [rsp+0C8h+var_70], eax
0x140037d23  mov     eax, [rdx+0B0h]
0x140037d29  mov     [rsp+0C8h+var_78], eax
0x140037d2d  mov     dword ptr [rsp+0C8h+var_80], ecx
0x140037d31  mov     dword ptr [rsp+0C8h+var_88], r11d
0x140037d36  mov     dword ptr [rsp+0C8h+var_90], r15d
0x140037d3b  jmp     loc_140037B40
0x140037d40  xor     r15d, r15d
0x140037d43  jmp     loc_140038067
0x140037d48  mov     rcx, rbx; this
0x140037d4b  movzx   esi, r15b
0x140037d4f  mov     [rsp+0C8h+var_58], r15d
0x140037d54  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x140037d59  lea     r8, [rsp+0C8h+var_58]; unsigned int *
0x140037d5e  mov     edx, 18h; unsigned int
0x140037d63  mov     rcx, rax; this
0x140037d66  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x140037d6b  test    eax, eax
0x140037d6d  jnz     short loc_140037D7C
0x140037d6f  test    byte ptr [rsp+0C8h+var_58], 20h
0x140037d74  lea     r8d, [rax+1]; unsigned __int8
0x140037d78  cmovnz  esi, r8d
0x140037d7c  mov     [rbx+4E1h], r15b
0x140037d83  movzx   edx, byte ptr [rdi+1]
0x140037d87  mov     ecx, edx
0x140037d89  sub     ecx, 1
0x140037d8c  jz      loc_140037E23
0x140037d92  cmp     ecx, 1
0x140037d95  jz      short loc_140037DEA
0x140037d97  mov     ebp, 0C0010015h
0x140037d9c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140037da3  jz      loc_140038102
0x140037da9  mov     rcx, cs:WPP_GLOBAL_Control
0x140037db0  lea     rdi, WPP_298b309e0d8a33f8d841b368865bd584_Traceguids
0x140037db7  mov     eax, [rbx+10h]
0x140037dba  mov     r9d, 0Dh
0x140037dc0  mov     dword ptr [rsp+0C8h+var_88], edx
0x140037dc4  mov     dl, 2
0x140037dc6  mov     dword ptr [rsp+0C8h+var_90], 0C0010015h
0x140037dce  mov     rcx, [rcx+40h]
0x140037dd2  mov     dword ptr [rsp+0C8h+var_98], eax
0x140037dd6  mov     qword ptr [rsp+0C8h+var_A0], rbx
0x140037ddb  mov     [rsp+0C8h+var_A8], rdi
0x140037de0  call    WPP_RECORDER_SF_qDdd
0x140037de5  jmp     loc_1400380B7
0x140037dea  mov     al, [rdi+10h]
0x140037ded  mov     cl, sil; unsigned __int8
0x140037df0  mov     r9b, [rdi+5]; unsigned __int8
0x140037df4  mov     dl, [rdi+4]; unsigned __int8
0x140037df7  mov     byte ptr [rsp+0C8h+var_90], al; char
0x140037dfb  mov     al, [rdi+8]
0x140037dfe  mov     byte ptr [rsp+0C8h+var_98], al; char
0x140037e02  mov     al, [rdi+7]
0x140037e05  mov     [rsp+0C8h+var_A0], al; char
0x140037e09  mov     al, [rdi+6]
0x140037e0c  mov     byte ptr [rsp+0C8h+var_A8], al; char
0x140037e10  call    ?MapWFDGroupCapabilities@CDot11ToWabiConverter@@SAEEEEEEEEE@Z; CDot11ToWabiConverter::MapWFDGroupCapabilities(uchar,uchar,uchar,uchar,uchar,uchar,uchar,uchar)
0x140037e15  mov     r9b, al
0x140037e18  mov     byte ptr [rbx+4E1h], 80h
0x140037e1f  mov     al, 0FBh
0x140037e21  jmp     short loc_140037E51
0x140037e23  mov     al, [rdi+8]
0x140037e26  mov     cl, sil; unsigned __int8
0x140037e29  mov     r9b, [rdi+5]; unsigned __int8
  ... truncated ...
```
