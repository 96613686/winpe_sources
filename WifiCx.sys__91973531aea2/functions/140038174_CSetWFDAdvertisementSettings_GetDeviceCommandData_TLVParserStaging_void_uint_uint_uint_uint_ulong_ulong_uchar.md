# CSetWFDAdvertisementSettings::GetDeviceCommandData_TLVParserStaging(void *,uint,uint *,uint *,uint,ulong *,ulong *,uchar * *)

- ea: `0x140038174`
- end: `0x140038953`
- name: `?GetDeviceCommandData_TLVParserStaging@CSetWFDAdvertisementSettings@@IEAAHPEAXIPEAI1IPEAK2PEAPEAE@Z`
- size: `2015`
- prototype: `__int64 __usercall@<rax>(CSetWFDAdvertisementSettings *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned int *, unsigned int, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140037930`

## callees

- `0x140016d00`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002bd34`
- `0x140038174`
- `0x14003ffd4`
- `0x140050660`
- `0x140071720`
- `0x140074ba8`
- `0x1400bd5b8`
- `0x1400bf050`

## pseudocode

```c
__int64 __fastcall CSetWFDAdvertisementSettings::GetDeviceCommandData_TLVParserStaging(
        CSetWFDAdvertisementSettings *this,
        unsigned __int64 a2,
        int a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned __int8 **a9)
{
  unsigned int v10; // r13d
  _DWORD *v11; // rdi
  unsigned int WdiSetAdvertisementInformationToIhv; // ebp
  int v14; // esi
  int *v15; // rsi
  unsigned int *v16; // r14
  _DWORD *v17; // r15
  int v18; // r9d
  __int64 v19; // rdx
  unsigned int Elements; // eax
  int v21; // edx
  int v22; // r8d
  unsigned int i; // r10d
  unsigned int v24; // r11d
  unsigned int v25; // r9d
  int v26; // ecx
  unsigned int v27; // eax
  __int64 v28; // r9
  __int64 v29; // rcx
  int v30; // eax
  char *v31; // rax
  unsigned __int8 v32; // si
  CPropertyCache *PortPropertyCache; // rax
  int v34; // r8d
  int v35; // edx
  int v36; // edx
  int v37; // r8d
  char v38; // r9
  char v39; // al
  _DWORD *v40; // rcx
  unsigned __int8 v41; // cl
  unsigned __int8 v42; // r8
  unsigned __int8 v43; // cl
  unsigned __int8 v44; // r8
  unsigned __int8 v45; // cl
  unsigned __int8 v46; // r8
  unsigned __int8 v47; // cl
  int v48; // edx
  int v49; // r8d
  int v50; // ecx
  unsigned int *v51; // rax
  unsigned int *v52; // r9
  unsigned int v53; // edx
  unsigned __int8 **v54; // rax
  char v56[8]; // [rsp+38h] [rbp-80h]
  char v57; // [rsp+38h] [rbp-80h]
  int v58; // [rsp+40h] [rbp-78h]
  char v59; // [rsp+40h] [rbp-78h]
  char v60; // [rsp+48h] [rbp-70h]
  int v61; // [rsp+50h] [rbp-68h]
  int v62; // [rsp+58h] [rbp-60h]
  int v63; // [rsp+60h] [rbp-58h]
  unsigned int v64; // [rsp+C0h] [rbp+8h] BYREF

  v10 = a3;
  v11 = (_DWORD *)a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        22,
        (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        23,
        (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        *((_DWORD *)this + 15));
    }
  }
  switch ( *((_DWORD *)this + 15) )
  {
    case 'r':
      v14 = (_DWORD)this + 1320;
      *((_DWORD *)this + 330) |= 4u;
      v41 = (*((_BYTE *)v11 + 4) != 0) | 2;
      if ( !*((_BYTE *)v11 + 5) )
        v41 = *((_BYTE *)v11 + 4) != 0;
      v42 = v41;
      v43 = v41 | 4;
      if ( !*((_BYTE *)v11 + 6) )
        v43 = v42;
      v44 = v43;
      v45 = v43 | 8;
      if ( !*((_BYTE *)v11 + 7) )
        v45 = v44;
      v46 = v45;
      v47 = v45 | 0x10;
      if ( !*((_BYTE *)v11 + 8) )
        v47 = v46;
      v48 = v47;
      v49 = v47 | 0x20;
      if ( !*((_BYTE *)v11 + 9) )
        v49 = v47;
      *((_BYTE *)this + 1449) = 63;
      *((_BYTE *)this + 1448) = v49;
      v50 = v11[3];
      *((_DWORD *)this + 363) = v50;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v48) = 4;
        WPP_RECORDER_SF_qDddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v48,
          v49,
          24,
          (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v49,
          63,
          v50);
      }
      goto LABEL_78;
    case 's':
      v14 = (_DWORD)this + 1320;
      *((_DWORD *)this + 330) |= 1u;
      v40 = (_DWORD *)((char *)this + 1328);
      if ( v11[2] )
      {
        *v40 |= 1u;
        *((_QWORD *)this + 168) = (char *)v11 + (unsigned int)v11[1];
        *((_DWORD *)this + 334) = v11[2];
      }
      if ( v11[4] )
      {
        *v40 |= 2u;
        *((_QWORD *)this + 171) = (char *)v11 + (unsigned int)v11[3];
        *((_DWORD *)this + 340) = v11[4];
      }
      if ( v11[6] )
      {
        *v40 |= 4u;
        *((_QWORD *)this + 174) = (char *)v11 + (unsigned int)v11[5];
        *((_DWORD *)this + 346) = v11[6];
      }
      goto LABEL_78;
    case 'v':
      v14 = (_DWORD)this + 1320;
      *((_DWORD *)this + 330) |= 2u;
      *((_DWORD *)this + 352) = v11[1];
      *((_WORD *)this + 706) = *((_WORD *)v11 + 4);
      *((_WORD *)this + 707) = *((_WORD *)v11 + 5);
      *((_WORD *)this + 708) = *((_WORD *)v11 + 6);
      *((_WORD *)this + 711) = *((_WORD *)v11 + 7);
      *(_DWORD *)((char *)this + 1418) = v11[4];
      *((_QWORD *)this + 179) = v11 + 6;
      *((_DWORD *)this + 356) = v11[5];
      goto LABEL_78;
    case 'z':
      v32 = 0;
      v64 = 0;
      PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
      if ( !(unsigned int)CPropertyCache::GetPropertyULong(PortPropertyCache, 0x18u, &v64) )
      {
        v34 = 1;
        v32 = (v64 & 0x20) != 0;
      }
      *((_BYTE *)this + 1457) = 0;
      v35 = *((unsigned __int8 *)v11 + 1);
      if ( v35 == 1 )
      {
        v38 = CDot11ToWabiConverter::MapWFDGroupCapabilities(
                v32,
                *((_BYTE *)v11 + 4),
                v34,
                *((_BYTE *)v11 + 5),
                *((_BYTE *)v11 + 6),
                *((_BYTE *)v11 + 7),
                *((_BYTE *)v11 + 8),
                0);
        v39 = 123;
      }
      else
      {
        if ( *((_BYTE *)v11 + 1) != 2 )
        {
          WdiSetAdvertisementInformationToIhv = -1073676267;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return WdiSetAdvertisementInformationToIhv;
          v59 = v35;
          LOBYTE(v35) = 2;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v35,
            v34,
            25,
            (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            21,
            v59);
          goto LABEL_79;
        }
        v38 = CDot11ToWabiConverter::MapWFDGroupCapabilities(
                v32,
                *((_BYTE *)v11 + 4),
                v34,
                *((_BYTE *)v11 + 5),
                *((_BYTE *)v11 + 6),
                *((_BYTE *)v11 + 7),
                *((_BYTE *)v11 + 8),
                *((_BYTE *)v11 + 16));
        *((_BYTE *)this + 1457) = 0x80;
        v39 = -5;
      }
      *((_BYTE *)this + 1456) = v38;
      v14 = (_DWORD)this + 1320;
      *((_DWORD *)this + 365) = v11[3];
      *((_DWORD *)this + 330) |= 8u;
      *((_BYTE *)this + 1457) = v39;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v36) = 4;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v36,
          v37,
          26,
          (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v38,
          v39);
      }
      goto LABEL_78;
  }
  if ( *((_DWORD *)this + 15) != 126 )
  {
    if ( *((_DWORD *)this + 15) == 129 )
    {
      v14 = (_DWORD)this + 1320;
      *((_QWORD *)this + 184) = v11 + 3;
      *((_DWORD *)this + 330) |= 0x10u;
      *((_DWORD *)this + 366) = v11[1];
    }
    else
    {
      if ( *((_DWORD *)this + 15) != 170 )
      {
        WdiSetAdvertisementInformationToIhv = -1073741823;
        goto LABEL_79;
      }
      v14 = (_DWORD)this + 1320;
    }
LABEL_78:
    v51 = a7;
    v52 = a8;
    v53 = a6;
    *a4 = v10;
    *v51 = 89;
    v54 = a9;
    *v52 = 0;
    WdiSetAdvertisementInformationToIhv = GenerateWdiSetAdvertisementInformationToIhv(
                                            v14,
                                            v53,
                                            (unsigned int)*((_QWORD *)this + 67) + 5384,
                                            (_DWORD)v52,
                                            (__int64)v54);
    goto LABEL_79;
  }
  v15 = v11 + 9;
  v16 = v11 + 2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qDddd(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      27,
      (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      *v16,
      v11[5],
      *v15);
  }
  if ( (!*v16 || v11[3] >= 0x28u) && (!v11[5] || v11[6] >= 0x28u) )
  {
    v15 = v11 + 9;
    a2 = (unsigned int)v11[9];
    if ( (_DWORD)a2 )
    {
      if ( (unsigned int)a2 < 0x28 || v11[8] < 0x28u )
        goto LABEL_29;
      v17 = v11 + 2;
    }
    else
    {
      v17 = v11 + 2;
    }
    if ( a2 + (unsigned int)v11[4] + 40LL + (unsigned int)v11[7] <= *((unsigned int *)this + 148) )
    {
      v14 = (_DWORD)this + 1320;
      *((_DWORD *)this + 330) |= 0x20u;
      *((_WORD *)this + 760) = *((_WORD *)v11 + 2);
      v19 = (unsigned int)*v17;
      if ( (_DWORD)v19 )
      {
        Elements = ArrayOfElements<_WDI_P2P_ADVERTISED_SERVICE_ENTRY_CONTAINER>::AllocateElements(
                     (char *)this + 1496,
                     v19,
                     0);
        WdiSetAdvertisementInformationToIhv = Elements;
        if ( Elements )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return WdiSetAdvertisementInformationToIhv;
          LOBYTE(v21) = 2;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v21,
            v22,
            29,
            (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            Elements,
            *v17);
          goto LABEL_79;
        }
        a3 = 1;
        *((_DWORD *)this + 372) |= 1u;
        a2 = (unsigned __int64)v11 + (unsigned int)v11[3];
        for ( i = 0; i < *v16; ++i )
        {
          v24 = *(_DWORD *)(a2 + 168);
          if ( v24 < 0x28
            || (v25 = *((_DWORD *)this + 148), v24 + *(unsigned __int8 *)(a2 + 164) > v25)
            || (v26 = *(_DWORD *)(a2 + 172)) != 0 && ((v27 = *(_DWORD *)(a2 + 176), v27 < 0x28) || v26 + v27 > v25) )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return WdiSetAdvertisementInformationToIhv;
            v18 = 30;
            v63 = *((_DWORD *)this + 148);
            v62 = *(_DWORD *)(a2 + 172);
            v61 = *(_DWORD *)(a2 + 176);
            v60 = *(_BYTE *)(a2 + 164);
            LOBYTE(v58) = *(_DWORD *)(a2 + 168);
            v57 = 0;
            goto LABEL_31;
          }
          v28 = *((_QWORD *)this + 188);
          v29 = 80LL * i;
          *(_BYTE *)(v29 + v28 + 64) = *(_BYTE *)(a2 + 16);
          *(_DWORD *)(v29 + v28 + 68) = *(_DWORD *)a2;
          *(_WORD *)(v29 + v28 + 72) = *(_WORD *)(a2 + 12);
          *(_DWORD *)(v29 + v28 + 8) = *(unsigned __int8 *)(a2 + 164);
          *(_QWORD *)(v29 + v28 + 16) = (char *)v11 + *(unsigned int *)(a2 + 168);
          *(_DWORD *)(v29 + v28 + 32) = *(_DWORD *)(a2 + 4);
          *(_WORD *)(v29 + v28 + 36) = *(_WORD *)(a2 + 8);
          v30 = *(_DWORD *)(a2 + 172);
          if ( v30 )
          {
            *(_DWORD *)(v29 + v28 + 40) = v30;
            v31 = (char *)v11 + *(unsigned int *)(a2 + 176);
            *(_DWORD *)(v29 + v28) |= 1u;
            *(_QWORD *)(v29 + v28 + 48) = v31;
          }
          a2 += 180LL;
        }
      }
      goto LABEL_78;
    }
  }
LABEL_29:
  WdiSetAdvertisementInformationToIhv = -1073676267;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WdiSetAdvertisementInformationToIhv;
  v18 = 28;
  v63 = *v15;
  v62 = v11[7];
  v61 = v11[4];
  v60 = 40;
  v58 = *((_DWORD *)this + 148);
  v57 = 21;
LABEL_31:
  WPP_RECORDER_SF_qDDddddd(
    WPP_GLOBAL_Control->DeviceExtension,
    a2,
    a3,
    v18,
    (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
    (char)this,
    *((_DWORD *)this + 4),
    v57,
    v58,
    v60,
    v61,
    v62,
    v63);
LABEL_79:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    *(_DWORD *)v56 = WdiSetAdvertisementInformationToIhv;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      31,
      (__int64)WPP_298b309e0d8a33f8d841b368865bd584_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      *(_QWORD *)v56);
  }
  return WdiSetAdvertisementInformationToIhv;
}

```

## disassembly

```asm
0x140038174  push    rbx
0x140038176  push    rbp
0x140038177  push    rsi
0x140038178  push    rdi
0x140038179  push    r12
0x14003817b  push    r13
0x14003817d  push    r14
0x14003817f  push    r15
0x140038181  sub     rsp, 78h
0x140038185  mov     r12, r9
0x140038188  mov     r13d, r8d
0x14003818b  mov     rdi, rdx
0x14003818e  mov     rbx, rcx
0x140038191  lea     r14, WPP_RECORDER_INITIALIZED
0x140038198  xor     r15d, r15d
0x14003819b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400381a2  lea     rbp, WPP_298b309e0d8a33f8d841b368865bd584_Traceguids
0x1400381a9  jz      short loc_14003821A
0x1400381ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400381b2  cmp     byte ptr [rcx+29h], 5
0x1400381b6  jnb     short loc_1400381BF
0x1400381b8  cmp     [rcx+48h], r15w
0x1400381bd  jz      short loc_1400381E1
0x1400381bf  mov     eax, [rbx+10h]
0x1400381c2  mov     r9d, 16h
0x1400381c8  mov     rcx, [rcx+40h]
0x1400381cc  mov     dl, 5
0x1400381ce  mov     dword ptr [rsp+0B8h+var_88], eax
0x1400381d2  mov     qword ptr [rsp+0B8h+var_90], rbx
0x1400381d7  mov     qword ptr [rsp+0B8h+var_98], rbp
0x1400381dc  call    WPP_RECORDER_SF_qD
0x1400381e1  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400381e8  jz      short loc_14003821A
0x1400381ea  mov     eax, [rbx+3Ch]
0x1400381ed  mov     r9d, 17h
0x1400381f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400381fa  mov     dl, 4
0x1400381fc  mov     dword ptr [rsp+0B8h+var_80], eax
0x140038200  mov     eax, [rbx+10h]
0x140038203  mov     dword ptr [rsp+0B8h+var_88], eax
0x140038207  mov     rcx, [rcx+40h]
0x14003820b  mov     qword ptr [rsp+0B8h+var_90], rbx
0x140038210  mov     qword ptr [rsp+0B8h+var_98], rbp
0x140038215  call    WPP_RECORDER_SF_qDD
0x14003821a  mov     ecx, [rbx+3Ch]
0x14003821d  sub     ecx, 72h ; 'r'
0x140038220  jz      loc_1400387D6
0x140038226  sub     ecx, 1
0x140038229  jz      loc_140038759
0x14003822f  sub     ecx, 3
0x140038232  jz      loc_1400386F8
0x140038238  sub     ecx, 4
0x14003823b  jz      loc_14003857C
0x140038241  sub     ecx, 4
0x140038244  jz      short loc_140038289
0x140038246  sub     ecx, 3
0x140038249  jz      short loc_140038266
0x14003824b  cmp     ecx, 29h ; ')'
0x14003824e  jz      short loc_14003825A
0x140038250  mov     ebp, 0C0000001h
0x140038255  jmp     loc_1400388ED
0x14003825a  lea     rsi, [rbx+528h]
0x140038261  jmp     loc_1400388A4
0x140038266  lea     rax, [rdi+0Ch]
0x14003826a  lea     rsi, [rbx+528h]
0x140038271  mov     [rbx+5C0h], rax
0x140038278  or      dword ptr [rsi], 10h
0x14003827b  mov     eax, [rdi+4]
0x14003827e  mov     [rbx+5B8h], eax
0x140038284  jmp     loc_1400388A4
0x140038289  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140038290  lea     rsi, [rdi+24h]
0x140038294  lea     r14, [rdi+8]
0x140038298  jz      short loc_1400382D7
0x14003829a  mov     eax, [rsi]
0x14003829c  mov     r9d, 1Bh
0x1400382a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400382a9  mov     dl, 4
0x1400382ab  mov     dword ptr [rsp+0B8h+var_70], eax
0x1400382af  mov     eax, [rdi+14h]
0x1400382b2  mov     dword ptr [rsp+0B8h+var_78], eax
0x1400382b6  mov     eax, [r14]
0x1400382b9  mov     rcx, [rcx+40h]
0x1400382bd  mov     dword ptr [rsp+0B8h+var_80], eax
0x1400382c1  mov     eax, [rbx+10h]
0x1400382c4  mov     dword ptr [rsp+0B8h+var_88], eax
0x1400382c8  mov     qword ptr [rsp+0B8h+var_90], rbx
0x1400382cd  mov     qword ptr [rsp+0B8h+var_98], rbp
0x1400382d2  call    WPP_RECORDER_SF_qDddd
0x1400382d7  cmp     [r14], r15d
0x1400382da  jz      short loc_1400382E2
0x1400382dc  cmp     dword ptr [rdi+0Ch], 28h ; '('
0x1400382e0  jb      short loc_140038327
0x1400382e2  cmp     [rdi+14h], r15d
0x1400382e6  jz      short loc_1400382EE
0x1400382e8  cmp     dword ptr [rdi+18h], 28h ; '('
0x1400382ec  jb      short loc_140038327
0x1400382ee  lea     rsi, [rdi+24h]
0x1400382f2  mov     edx, [rsi]
0x1400382f4  test    edx, edx
0x1400382f6  jz      short loc_140038309
0x1400382f8  cmp     edx, 28h ; '('
0x1400382fb  jb      short loc_140038327
0x1400382fd  cmp     dword ptr [rdi+20h], 28h ; '('
0x140038301  jb      short loc_140038327
0x140038303  lea     r15, [rdi+8]
0x140038307  jmp     short loc_14003830C
0x140038309  mov     r15, r14
0x14003830c  mov     eax, [rdi+10h]
0x14003830f  mov     ecx, [rdi+1Ch]
0x140038312  add     rax, 28h ; '('
0x140038316  add     rcx, rax
0x140038319  mov     eax, [rbx+250h]
0x14003831f  add     rcx, rdx
0x140038322  cmp     rcx, rax
0x140038325  jbe     short loc_1400383A1
0x140038327  mov     ebp, 0C0010015h
0x14003832c  lea     r14, WPP_RECORDER_INITIALIZED
0x140038333  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003833a  jz      loc_14003893F
0x140038340  mov     eax, [rsi]
0x140038342  mov     r9d, 1Ch
0x140038348  mov     [rsp+0B8h+var_58], eax
0x14003834c  mov     eax, [rdi+1Ch]
0x14003834f  mov     [rsp+0B8h+var_60], eax
0x140038353  mov     eax, [rdi+10h]
0x140038356  mov     [rsp+0B8h+var_68], eax
0x14003835a  mov     eax, [rbx+250h]
0x140038360  mov     dword ptr [rsp+0B8h+var_70], 28h ; '('
0x140038368  mov     dword ptr [rsp+0B8h+var_78], eax
0x14003836c  mov     dword ptr [rsp+0B8h+var_80], 0C0010015h
0x140038374  mov     rcx, cs:WPP_GLOBAL_Control
0x14003837b  lea     rdi, WPP_298b309e0d8a33f8d841b368865bd584_Traceguids
0x140038382  mov     eax, [rbx+10h]
0x140038385  mov     dword ptr [rsp+0B8h+var_88], eax
0x140038389  mov     qword ptr [rsp+0B8h+var_90], rbx
0x14003838e  mov     rcx, [rcx+40h]
0x140038392  mov     qword ptr [rsp+0B8h+var_98], rdi
0x140038397  call    WPP_RECORDER_SF_qDDddddd
0x14003839c  jmp     loc_1400388FB
0x1400383a1  lea     rsi, [rbx+528h]
0x1400383a8  or      dword ptr [rsi], 20h
0x1400383ab  movzx   eax, word ptr [rdi+4]
0x1400383af  mov     [rbx+5F0h], ax
0x1400383b6  mov     edx, [r15]
0x1400383b9  test    edx, edx
0x1400383bb  jz      loc_140038574
0x1400383c1  lea     rcx, [rbx+5D8h]
0x1400383c8  xor     r8d, r8d
0x1400383cb  call    ?AllocateElements@?$ArrayOfElements@U_WDI_P2P_ADVERTISED_SERVICE_ENTRY_CONTAINER@@@@QEAAHI_K@Z; ArrayOfElements<_WDI_P2P_ADVERTISED_SERVICE_ENTRY_CONTAINER>::AllocateElements(uint,unsigned __int64)
0x1400383d0  mov     ebp, eax
0x1400383d2  test    eax, eax
0x1400383d4  jz      short loc_14003842A
0x1400383d6  lea     r14, WPP_RECORDER_INITIALIZED
0x1400383dd  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400383e4  jz      loc_14003893F
0x1400383ea  mov     ecx, [r15]
0x1400383ed  lea     rdi, WPP_298b309e0d8a33f8d841b368865bd584_Traceguids
0x1400383f4  mov     dword ptr [rsp+0B8h+var_78], ecx
0x1400383f8  mov     r9d, 1Dh
0x1400383fe  mov     ecx, [rbx+10h]
0x140038401  mov     dl, 2
0x140038403  mov     dword ptr [rsp+0B8h+var_80], eax
0x140038407  mov     dword ptr [rsp+0B8h+var_88], ecx
0x14003840b  mov     rcx, cs:WPP_GLOBAL_Control
0x140038412  mov     qword ptr [rsp+0B8h+var_90], rbx
0x140038417  mov     qword ptr [rsp+0B8h+var_98], rdi
0x14003841c  mov     rcx, [rcx+40h]
0x140038420  call    WPP_RECORDER_SF_qDdd
0x140038425  jmp     loc_1400388FB
0x14003842a  mov     r8d, 1
0x140038430  or      [rbx+5D0h], r8d
0x140038437  mov     edx, [rdi+0Ch]
0x14003843a  add     rdx, rdi
0x14003843d  xor     r15d, r15d
0x140038440  mov     r10d, r15d
0x140038443  cmp     r10d, [r14]
0x140038446  jnb     loc_1400388A4
0x14003844c  mov     r11d, [rdx+0A8h]
0x140038453  cmp     r11d, 28h ; '('
0x140038457  jb      loc_140038522
0x14003845d  movzx   eax, byte ptr [rdx+0A4h]
0x140038464  mov     r9d, [rbx+250h]
0x14003846b  add     eax, r11d
0x14003846e  cmp     eax, r9d
0x140038471  ja      loc_140038522
0x140038477  mov     ecx, [rdx+0ACh]
0x14003847d  test    ecx, ecx
0x14003847f  jz      short loc_14003849B
0x140038481  mov     eax, [rdx+0B0h]
0x140038487  cmp     eax, 28h ; '('
0x14003848a  jb      loc_140038522
0x140038490  add     eax, ecx
0x140038492  cmp     eax, r9d
0x140038495  ja      loc_140038522
0x14003849b  mov     r9, [rbx+5E0h]
0x1400384a2  mov     eax, r10d
0x1400384a5  lea     rcx, [rax+rax*4]
0x1400384a9  mov     al, [rdx+10h]
0x1400384ac  shl     rcx, 4
0x1400384b0  mov     [rcx+r9+40h], al
0x1400384b5  mov     eax, [rdx]
0x1400384b7  mov     [rcx+r9+44h], eax
0x1400384bc  movzx   eax, word ptr [rdx+0Ch]
0x1400384c0  mov     [rcx+r9+48h], ax
0x1400384c6  movzx   eax, byte ptr [rdx+0A4h]
0x1400384cd  mov     [rcx+r9+8], eax
0x1400384d2  mov     eax, [rdx+0A8h]
0x1400384d8  add     rax, rdi
0x1400384db  mov     [rcx+r9+10h], rax
0x1400384e0  mov     eax, [rdx+4]
0x1400384e3  mov     [rcx+r9+20h], eax
0x1400384e8  movzx   eax, word ptr [rdx+8]
0x1400384ec  mov     [rcx+r9+24h], ax
0x1400384f2  mov     eax, [rdx+0ACh]
0x1400384f8  test    eax, eax
0x1400384fa  jz      short loc_140038513
0x1400384fc  mov     [rcx+r9+28h], eax
0x140038501  mov     eax, [rdx+0B0h]
0x140038507  add     rax, rdi
0x14003850a  or      [rcx+r9], r8d
0x14003850e  mov     [rcx+r9+30h], rax
0x140038513  add     rdx, 0B4h
0x14003851a  add     r10d, r8d
0x14003851d  jmp     loc_140038443
0x140038522  lea     r14, WPP_RECORDER_INITIALIZED
0x140038529  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140038530  jz      loc_14003893F
0x140038536  mov     eax, [rbx+250h]
0x14003853c  mov     r9d, 1Eh
0x140038542  movzx   ecx, byte ptr [rdx+0A4h]
0x140038549  mov     [rsp+0B8h+var_58], eax
0x14003854d  mov     eax, [rdx+0ACh]
0x140038553  mov     [rsp+0B8h+var_60], eax
0x140038557  mov     eax, [rdx+0B0h]
0x14003855d  mov     [rsp+0B8h+var_68], eax
0x140038561  mov     dword ptr [rsp+0B8h+var_70], ecx
0x140038565  mov     dword ptr [rsp+0B8h+var_78], r11d
0x14003856a  mov     dword ptr [rsp+0B8h+var_80], r15d
0x14003856f  jmp     loc_140038374
0x140038574  xor     r15d, r15d
0x140038577  jmp     loc_1400388A4
0x14003857c  mov     rcx, rbx; this
0x14003857f  movzx   esi, r15b
0x140038583  mov     [rsp+0B8h+arg_0], r15d
0x14003858b  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x140038590  lea     r8, [rsp+0B8h+arg_0]; unsigned int *
0x140038598  mov     edx, 18h; unsigned int
0x14003859d  mov     rcx, rax; this
0x1400385a0  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400385a5  test    eax, eax
0x1400385a7  jnz     short loc_1400385B9
0x1400385a9  test    byte ptr [rsp+0B8h+arg_0], 20h
0x1400385b1  lea     r8d, [rax+1]; unsigned __int8
0x1400385b5  cmovnz  esi, r8d
0x1400385b9  mov     [rbx+5B1h], r15b
0x1400385c0  movzx   edx, byte ptr [rdi+1]
0x1400385c4  mov     ecx, edx
0x1400385c6  sub     ecx, 1
0x1400385c9  jz      loc_140038660
0x1400385cf  cmp     ecx, 1
0x1400385d2  jz      short loc_140038627
0x1400385d4  mov     ebp, 0C0010015h
0x1400385d9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400385e0  jz      loc_14003893F
0x1400385e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400385ed  lea     rdi, WPP_298b309e0d8a33f8d841b368865bd584_Traceguids
0x1400385f4  mov     eax, [rbx+10h]
0x1400385f7  mov     r9d, 19h
0x1400385fd  mov     dword ptr [rsp+0B8h+var_78], edx
0x140038601  mov     dl, 2
0x140038603  mov     dword ptr [rsp+0B8h+var_80], 0C0010015h
0x14003860b  mov     rcx, [rcx+40h]
0x14003860f  mov     dword ptr [rsp+0B8h+var_88], eax
0x140038613  mov     qword ptr [rsp+0B8h+var_90], rbx
0x140038618  mov     qword ptr [rsp+0B8h+var_98], rdi
0x14003861d  call    WPP_RECORDER_SF_qDdd
0x140038622  jmp     loc_1400388F4
0x140038627  mov     al, [rdi+10h]
0x14003862a  mov     cl, sil; unsigned __int8
0x14003862d  mov     r9b, [rdi+5]; unsigned __int8
0x140038631  mov     dl, [rdi+4]; unsigned __int8
0x140038634  mov     [rsp+0B8h+var_80], al; char
0x140038638  mov     al, [rdi+8]
0x14003863b  mov     [rsp+0B8h+var_88], al; char
0x14003863f  mov     al, [rdi+7]
0x140038642  mov     [rsp+0B8h+var_90], al; char
0x140038646  mov     al, [rdi+6]
0x140038649  mov     [rsp+0B8h+var_98], al; char
0x14003864d  call    ?MapWFDGroupCapabilities@CDot11ToWabiConverter@@SAEEEEEEEEE@Z; CDot11ToWabiConverter::MapWFDGroupCapabilities(uchar,uchar,uchar,uchar,uchar,uchar,uchar,uchar)
0x140038652  mov     r9b, al
0x140038655  mov     byte ptr [rbx+5B1h], 80h
0x14003865c  mov     al, 0FBh
0x14003865e  jmp     short loc_14003868E
0x140038660  mov     al, [rdi+8]
0x140038663  mov     cl, sil; unsigned __int8
0x140038666  mov     r9b, [rdi+5]; unsigned __int8
0x14003866a  mov     dl, [rdi+4]; unsigned __int8
0x14003866d  mov     [rsp+0B8h+var_80], r15b; char
0x140038672  mov     [rsp+0B8h+var_88], al; char
  ... truncated ...
```
