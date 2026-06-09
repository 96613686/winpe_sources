# MbbUtilValidateAndMbbToNdisWwanNwParamsInfo(_MBB_REQUEST_CONTEXT *,_MBB_NW_PARAMS_INFO *,ulong,_NDIS_WWAN_NETWORK_PARAMS_INFO * &,ulong &)

- ea: `0x14004041c`
- end: `0x140040e21`
- name: `?MbbUtilValidateAndMbbToNdisWwanNwParamsInfo@@YAKPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_NW_PARAMS_INFO@@KAEAPEAU_NDIS_WWAN_NETWORK_PARAMS_INFO@@AEAK@Z`
- size: `2565`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, struct _MBB_NW_PARAMS_INFO *, int, struct _NDIS_WWAN_NETWORK_PARAMS_INFO **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x140031550`

## callees

- `0x140001db8`
- `0x1400051ac`
- `0x14004041c`
- `0x140047530`
- `0x1400476d0`
- `0x14004773c`
- `0x140047814`
- `0x1400478e4`
- `0x140047978`
- `0x140048040`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140040a00`
- `ntoskrnl!ExAllocatePool2` at `0x140040a00`

## pseudocode

```c
__int64 __fastcall MbbUtilValidateAndMbbToNdisWwanNwParamsInfo(
        struct _MBB_REQUEST_CONTEXT *a1,
        struct _MBB_NW_PARAMS_INFO *a2,
        int a3,
        struct _NDIS_WWAN_NETWORK_PARAMS_INFO **a4,
        unsigned int *a5)
{
  unsigned int *v5; // r14
  int v6; // r8d
  struct _NDIS_WWAN_NETWORK_PARAMS_INFO **v8; // rdi
  mbbcx_p *v9; // rsi
  unsigned int v10; // r13d
  unsigned int v11; // r15d
  mbbcx_p *v12; // r13
  struct _MBB_TLV_IE *v13; // rax
  int v14; // edx
  mbbcx_p *v15; // rdi
  int v16; // ecx
  unsigned int v17; // r9d
  int v18; // r12d
  _BYTE *v19; // r11
  int v20; // r9d
  __int64 v21; // r11
  unsigned int v22; // eax
  int v23; // eax
  int v24; // r9d
  int SNSSAICountInTlv; // eax
  int v26; // eax
  int v27; // eax
  unsigned int v28; // r8d
  unsigned __int8 *v29; // r9
  int v30; // ecx
  unsigned int v31; // r10d
  int v32; // eax
  unsigned int v33; // edx
  unsigned int v34; // esi
  unsigned int v35; // eax
  struct _NDIS_WWAN_NETWORK_PARAMS_INFO *Pool2; // rax
  int v37; // r9d
  unsigned int v38; // esi
  int v39; // r9d
  size_t v40; // r8
  struct _NDIS_WWAN_NETWORK_PARAMS_INFO *v41; // rbx
  unsigned int v42; // edi
  struct _MBB_NW_PARAMS_INFO *v43; // rcx
  mbbcx_p *v44; // rax
  unsigned int v45; // r12d
  _DWORD *v46; // r14
  __int64 v47; // r15
  unsigned int v48; // esi
  mbbcx_p *v49; // rcx
  int v50; // edx
  struct _WWAN_SINGLE_NSSAI *v51; // r8
  __int64 v52; // rax
  mbbcx_p *v53; // r9
  int v54; // ecx
  struct _WWAN_SINGLE_NSSAI *v55; // r8
  __int64 v56; // rax
  int v57; // ecx
  unsigned int v58; // r11d
  _BYTE *v59; // rdx
  __int64 v60; // rax
  __int64 v61; // r10
  char *v62; // r9
  _WORD *v63; // rcx
  mbbcx_p *v64; // r9
  unsigned int v65; // ecx
  struct _WWAN_SINGLE_NSSAI *v66; // r8
  __int64 v67; // rax
  mbbcx_p *v68; // rdx
  char *v69; // rbx
  struct _MBB_TLV_IE *v70; // rax
  char *v71; // rdi
  mbbcx_p *v72; // rbx
  char v74; // [rsp+38h] [rbp-61h]
  unsigned int v75; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v76; // [rsp+4Ch] [rbp-4Dh] BYREF
  struct _WWAN_SINGLE_NSSAI *v77; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v78; // [rsp+58h] [rbp-41h]
  struct _WWAN_SINGLE_NSSAI *v79; // [rsp+5Ch] [rbp-3Dh] BYREF
  mbbcx_p *v80; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int8 *v81; // [rsp+70h] [rbp-29h] BYREF
  int v82; // [rsp+78h] [rbp-21h]
  int v83; // [rsp+7Ch] [rbp-1Dh]
  mbbcx_p *v84; // [rsp+80h] [rbp-19h]
  mbbcx_p *v85; // [rsp+88h] [rbp-11h]
  mbbcx_p *v86; // [rsp+90h] [rbp-9h]
  mbbcx_p *v87; // [rsp+98h] [rbp-1h]
  mbbcx_p *v88; // [rsp+A0h] [rbp+7h]
  char *v89; // [rsp+A8h] [rbp+Fh] BYREF
  struct _MBB_NW_PARAMS_INFO *v90; // [rsp+100h] [rbp+67h] BYREF
  unsigned __int8 *v91; // [rsp+108h] [rbp+6Fh] BYREF
  struct _NDIS_WWAN_NETWORK_PARAMS_INFO **v92; // [rsp+110h] [rbp+77h]

  v92 = a4;
  v90 = a2;
  v5 = a5;
  v6 = a3 - 8;
  v89 = (char *)a2 + 8;
  LODWORD(v81) = v6;
  *a5 = 68;
  v8 = a4;
  LODWORD(v91) = 0;
  v9 = 0;
  v85 = 0;
  v10 = 0;
  v86 = 0;
  v11 = 0;
  v87 = 0;
  v88 = 0;
  v80 = 0;
  v84 = 0;
  LODWORD(a5) = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v75 = 0;
  HIDWORD(v81) = 0;
  v82 = 0;
  v83 = 0;
  v76 = 0;
  if ( v6 )
  {
    v12 = 0;
    while ( 1 )
    {
      v13 = mbbcx_p::ExtractValidateNextTlv((mbbcx_p *)&v89, &v81, (unsigned int *)&v91, 0);
      v15 = v13;
      if ( !v13 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return (unsigned int)-1073479677;
        LOBYTE(SNSSAICountInTlv) = (_BYTE)v91;
        v39 = 64;
LABEL_116:
        v74 = SNSSAICountInTlv;
LABEL_117:
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          3,
          v39,
          (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
          *((_DWORD *)a1 + 4),
          v74);
        return (unsigned int)-1073479677;
      }
      v16 = *(unsigned __int16 *)v13;
      if ( v16 == 9 )
      {
        if ( v12 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return (unsigned int)-1073479677;
          v37 = 65;
LABEL_92:
          LOBYTE(v14) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            3,
            v37,
            (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
            *((_DWORD *)a1 + 4));
          return (unsigned int)-1073479677;
        }
        v17 = *((_DWORD *)v13 + 1);
        v18 = 0;
        v11 = 0;
        LODWORD(a5) = 0;
        if ( v17 )
        {
          v19 = (char *)v13 + 8;
          do
          {
            LODWORD(v91) = 0;
            LODWORD(a5) = 0;
            v14 = mbbcx_p::ValidateAndCalculateBothMbbAndWwanSingleTaiListSize(v19, &v91, (unsigned int *)&a5, v17);
            if ( v14 )
              break;
            if ( v11 > -1 - (int)v91 )
              break;
            ++v18;
            v11 += (unsigned int)v91;
            v19 = (_BYTE *)((unsigned int)a5 + v21);
            v17 = v20 - (_DWORD)a5;
          }
          while ( v17 );
          v22 = 0;
          LODWORD(v91) = v14;
          if ( !v14 )
            v22 = v11;
          v11 = v22;
          v23 = 0;
          if ( !v14 )
            v23 = v18;
          LODWORD(a5) = v23;
          if ( v14 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return (unsigned int)-1073479677;
            v39 = 66;
            v74 = v14;
            goto LABEL_117;
          }
          if ( v11 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v14) = 4;
              WPP_RECORDER_SF_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v14,
                3,
                68,
                (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
                *((_DWORD *)a1 + 4));
            }
            *v5 += v11;
            v12 = v15;
            v85 = v15;
            goto LABEL_87;
          }
        }
        else
        {
          LODWORD(v91) = 0;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v24 = 67;
LABEL_20:
          LOBYTE(v14) = 3;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            3,
            v24,
            (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
            *((_DWORD *)a1 + 4));
        }
      }
      else
      {
        v14 = 3;
        if ( (_WORD)v16 == 3 )
        {
          if ( v86 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return (unsigned int)-1073479677;
            v37 = 69;
            goto LABEL_92;
          }
          SNSSAICountInTlv = mbbcx_p::GetSNSSAICountInTlv((__int64)v13, &v77);
          LODWORD(v91) = SNSSAICountInTlv;
          if ( SNSSAICountInTlv )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return (unsigned int)-1073479677;
            v39 = 70;
            goto LABEL_116;
          }
          if ( (_DWORD)v77 )
          {
            v26 = 16 * (_DWORD)v77 + 4;
            *v5 += v26;
            HIDWORD(v81) = v26;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v14) = 4;
              WPP_RECORDER_SF_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v14,
                3,
                72,
                (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
                *((_DWORD *)a1 + 4));
            }
            v86 = v15;
            goto LABEL_87;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v24 = 71;
            goto LABEL_20;
          }
        }
        else
        {
          switch ( v16 )
          {
            case 4:
              if ( v87 )
              {
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  return (unsigned int)-1073479677;
                v37 = 73;
                goto LABEL_92;
              }
              SNSSAICountInTlv = mbbcx_p::GetSNSSAICountInTlv((__int64)v13, (_DWORD *)&v77 + 1);
              LODWORD(v91) = SNSSAICountInTlv;
              if ( SNSSAICountInTlv )
              {
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  return (unsigned int)-1073479677;
                v39 = 74;
                goto LABEL_116;
              }
              if ( HIDWORD(v77) )
              {
                v27 = 16 * HIDWORD(v77) + 4;
                *v5 += v27;
                v82 = v27;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v14) = 4;
                  WPP_RECORDER_SF_d(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v14,
                    3,
                    76,
                    (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
                    *((_DWORD *)a1 + 4));
                }
                v87 = v15;
                break;
              }
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v24 = 75;
                goto LABEL_20;
              }
              break;
            case 7:
              if ( v88 )
              {
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  return (unsigned int)-1073479677;
                v37 = 77;
                goto LABEL_92;
              }
              v28 = *((_DWORD *)v13 + 1);
              v29 = (unsigned __int8 *)v13 + 8;
              v30 = 0;
              v31 = 0;
              if ( v28 )
              {
                do
                {
                  if ( v30 )
                    break;
                  v32 = *v29;
                  if ( (_BYTE)v32 == 1 || (_BYTE)v32 == 4 )
                  {
                    v33 = v32 + 2;
                    if ( v28 >= v32 + 2 )
                    {
                      if ( v29[1] <= 2u )
                      {
                        v28 -= v33;
                        v29 += v33;
                        ++v31;
                      }
                      else
                      {
                        v30 = 20;
                      }
                    }
                    else
                    {
                      v30 = 14;
                    }
                  }
                  else
                  {
                    v30 = 13;
                  }
                }
                while ( v28 );
                v14 = 3;
              }
              v34 = 0;
              LODWORD(v91) = v30;
              if ( !v30 )
                v34 = v31;
              v78 = v34;
              if ( v30 )
              {
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  return (unsigned int)-1073479677;
                v39 = 78;
                v74 = v30;
                goto LABEL_117;
              }
              if ( v34 )
              {
                *v5 += 8 * v34 + 4;
                v83 = 8 * v34 + 4;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v14) = 4;
                  WPP_RECORDER_SF_d(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v14,
                    3,
                    80,
                    (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
                    *((_DWORD *)a1 + 4));
                }
                v88 = v15;
              }
              else
              {
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_SF_d(
                    WPP_GLOBAL_Control->DeviceExtension,
                    3,
                    3,
                    79,
                    (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
                    *((_DWORD *)a1 + 4));
                v78 = 0;
              }
              v9 = v84;
              break;
            case 5:
              if ( v80 )
              {
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  return (unsigned int)-1073479677;
                v37 = 81;
                goto LABEL_92;
              }
              SNSSAICountInTlv = mbbcx_p::GetSNSSAICountInTlv((__int64)v13, &v79);
              LODWORD(v91) = SNSSAICountInTlv;
              if ( SNSSAICountInTlv )
              {
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  return (unsigned int)-1073479677;
                v39 = 82;
                goto LABEL_116;
              }
              if ( (_DWORD)v79 )
              {
                v35 = 16 * (_DWORD)v79 + 4;
                *v5 += v35;
                v76 = v35;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v14) = 4;
                  WPP_RECORDER_SF_d(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v14,
                    3,
                    84,
                    (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
                    *((_DWORD *)a1 + 4));
                }
                v80 = v15;
                break;
              }
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v24 = 83;
                goto LABEL_20;
              }
              break;
            case 8:
              if ( v9 )
              {
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  v37 = 85;
                  goto LABEL_92;
                }
                return (unsigned int)-1073479677;
              }
              SNSSAICountInTlv = mbbcx_p::ValidateAndCalculateWwanLadnListSize(
                                   (__int64)v13,
                                   (unsigned int *)&v79 + 1,
                                   &v75);
              LODWORD(v91) = SNSSAICountInTlv;
              if ( SNSSAICountInTlv )
              {
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  return (unsigned int)-1073479677;
                v39 = 86;
                goto LABEL_116;
              }
              if ( HIDWORD(v79) )
              {
                *v5 += HIDWORD(v79);
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v14) = 4;
                  WPP_RECORDER_SF_d(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v14,
                    3,
                    88,
                    (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
                    *((_DWORD *)a1 + 4));
                }
                v9 = v15;
                v84 = v15;
              }
              else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v14) = 3;
                WPP_RECORDER_SF_d(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v14,
                  3,
                  87,
                  (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
                  *((_DWORD *)a1 + 4));
              }
              break;
            default:
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_DD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  3,
                  3,
                  89,
                  (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
                  *((_DWORD *)a1 + 4),
                  v16);
              break;
          }
        }
      }
LABEL_87:
      if ( !(_DWORD)v81 )
      {
        v10 = v75;
        v8 = v92;
        break;
      }
    }
  }
  Pool2 = (struct _NDIS_WWAN_NETWORK_PARAMS_INFO *)ExAllocatePool2(64, *v5, 1683505741);
  *v8 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v37 = 90;
      goto LABEL_92;
    }
    return (unsigned int)-1073479677;
  }
  v40 = *v5;
  v38 = 0;
  v75 = 0;
  memset(Pool2, 0, v40);
  v41 = *v8;
  v42 = 56;
  v43 = v90;
  *((_DWORD *)v41 + 2) = *(_DWORD *)v90;
  *((_DWORD *)v41 + 3) = *((_DWORD *)v43 + 1);
  v44 = v85;
  if ( v85 )
  {
    if ( v11 )
    {
      v45 = 0;
      *((_DWORD *)v41 + 4) = 56;
      v42 = v11 + 56;
      *((_DWORD *)v41 + 5) = v11;
      v46 = (_DWORD *)((char *)v41 + 64);
      LODWORD(v91) = 0;
      v47 = (__int64)v44 + 8;
      LODWORD(v90) = 0;
      if ( (_DWORD)a5 )
      {
        v48 = (unsigned int)a5;
        do
        {
          mbbcx_p::ParseMbbSingleTaiListInfo(v47, &v90, v46, &v91);
          ++v45;
          v46 = (_DWORD *)((char *)v46 + (unsigned int)v91);
          v47 += (unsigned int)v90;
        }
        while ( v45 < v48 );
        v38 = v75;
      }
    }
  }
  v49 = v86;
  if ( v86 )
  {
    v50 = HIDWORD(v81);
    if ( HIDWORD(v81) )
    {
      v51 = (struct _WWAN_SINGLE_NSSAI *)(unsigned int)v77;
      v52 = v42;
      *((_DWORD *)v41 + 7) = HIDWORD(v81);
      *((_DWORD *)v41 + 6) = v42;
      v42 += v50;
      *(_DWORD *)((char *)v41 + v52 + 8) = (_DWORD)v51;
      mbbcx_p::ParseTlvNSSAI(v49, (struct _NDIS_WWAN_NETWORK_PARAMS_INFO *)((char *)v41 + v52 + 12), v51);
    }
  }
  v53 = v87;
  if ( v87 )
  {
    v54 = v82;
    if ( v82 )
    {
      v55 = (struct _WWAN_SINGLE_NSSAI *)HIDWORD(v77);
      v56 = v42;
      *((_DWORD *)v41 + 8) = v42;
      v42 += v54;
      *((_DWORD *)v41 + 9) = v54;
      *(_DWORD *)((char *)v41 + v56 + 8) = (_DWORD)v55;
      mbbcx_p::ParseTlvNSSAI(v53, (struct _NDIS_WWAN_NETWORK_PARAMS_INFO *)((char *)v41 + v56 + 12), v55);
    }
  }
  if ( v88 )
  {
    v57 = v83;
    if ( v83 )
    {
      v58 = v78;
      v59 = (char *)v88 + 8;
      v60 = v42;
      v61 = 0;
      *((_DWORD *)v41 + 10) = v42;
      v42 += v57;
      *((_DWORD *)v41 + 11) = v57;
      *(_DWORD *)((char *)v41 + v60 + 8) = v58;
      v62 = (char *)v41 + v60;
      if ( v58 )
      {
        do
        {
          *(_DWORD *)&v62[8 * v61 + 16] = 0xFFFFFF;
          v63 = v59 + 3;
          *(_WORD *)&v62[8 * v61 + 12] = (unsigned __int8)v59[1];
          *(_WORD *)&v62[8 * v61 + 14] = (unsigned __int8)v59[2];
          if ( *v59 >= 4u )
          {
            *(_WORD *)&v62[8 * v61 + 16] = *v63;
            v63 = v59 + 6;
            v62[8 * v61 + 18] = v59[5];
          }
          v61 = (unsigned int)(v61 + 1);
          v59 = v63;
        }
        while ( (unsigned int)v61 < v58 );
      }
    }
  }
  v64 = v80;
  if ( v80 )
  {
    v65 = v76;
    if ( v76 )
    {
      v66 = (struct _WWAN_SINGLE_NSSAI *)(unsigned int)v79;
      v67 = v42;
      *((_DWORD *)v41 + 12) = v42;
      v42 += v65;
      *((_DWORD *)v41 + 13) = v65;
      *(_DWORD *)((char *)v41 + v67 + 8) = (_DWORD)v66;
      mbbcx_p::ParseTlvNSSAI(v64, (struct _NDIS_WWAN_NETWORK_PARAMS_INFO *)((char *)v41 + v67 + 12), v66);
    }
  }
  v68 = v84;
  if ( v84 )
  {
    if ( HIDWORD(v79) )
    {
      *((_DWORD *)v41 + 15) = HIDWORD(v79);
      *((_DWORD *)v41 + 14) = v42;
      v80 = (mbbcx_p *)((char *)v68 + 8);
      v76 = 0;
      *(_DWORD *)((char *)v41 + v42 + 8) = v10;
      v69 = (char *)v41 + v42 + 12;
      for ( LODWORD(v91) = *((_DWORD *)v68 + 1); (_DWORD)v91; v69 = &v71[(unsigned int)a5] )
      {
        v70 = mbbcx_p::ExtractValidateNextTlv((mbbcx_p *)&v80, &v91, &v76, (enum mbbcx_p::MbbTlvError *)0xA);
        if ( !v70 )
          __int2c();
        memmove(v69, (char *)v70 + 8, *((unsigned int *)v70 + 1));
        v71 = v69 + 204;
        LODWORD(a5) = 0;
        v72 = v80;
        LODWORD(v90) = 0;
        mbbcx_p::ParseMbbSingleTaiListInfo(v80, &v90, v71, &a5);
        LODWORD(v91) = (_DWORD)v91 - (_DWORD)v90;
        v80 = (mbbcx_p *)((char *)v72 + (unsigned int)v90);
      }
    }
  }
  return v38;
}

```

## disassembly

```asm
0x14004041c  mov     rax, rsp
0x14004041f  mov     [rax+8], rbx
0x140040423  mov     [rax+20h], r9
0x140040427  mov     [rax+10h], rdx
0x14004042b  push    rbp
0x14004042c  push    rsi
0x14004042d  push    rdi
0x14004042e  push    r12
0x140040430  push    r13
0x140040432  push    r14
0x140040434  push    r15
0x140040436  lea     rbp, [rax-57h]
0x14004043a  sub     rsp, 0B0h
0x140040441  mov     r14, [rbp+4Fh+arg_20]
0x140040445  lea     rax, [rdx+8]
0x140040449  add     r8d, 0FFFFFFF8h
0x14004044d  mov     [rbp+4Fh+var_40], rax
0x140040451  mov     rbx, rcx
0x140040454  mov     dword ptr [rbp+4Fh+var_78], r8d
0x140040458  xor     ecx, ecx
0x14004045a  lea     r12, WPP_RECORDER_INITIALIZED
0x140040461  mov     dword ptr [r14], 44h ; 'D'
0x140040468  mov     rdi, r9
0x14004046b  mov     dword ptr [rbp+4Fh+arg_10], ecx
0x14004046e  mov     esi, ecx
0x140040470  mov     [rbp+4Fh+var_60], rcx
0x140040474  mov     r13d, ecx
0x140040477  mov     [rbp+4Fh+var_58], rcx
0x14004047b  mov     r15d, ecx
0x14004047e  mov     [rbp+4Fh+var_50], rcx
0x140040482  mov     [rbp+4Fh+var_48], rcx
0x140040486  mov     [rbp+4Fh+var_80], rcx
0x14004048a  mov     [rbp+4Fh+var_68], rcx
0x14004048e  mov     dword ptr [rbp+4Fh+arg_20], ecx
0x140040491  mov     dword ptr [rbp+4Fh+var_98], ecx
0x140040494  mov     dword ptr [rbp+4Fh+var_98+4], ecx
0x140040497  mov     [rbp+4Fh+var_90], ecx
0x14004049a  mov     dword ptr [rbp+4Fh+var_8C], ecx
0x14004049d  mov     [rbp+4Fh+var_A0], ecx
0x1400404a0  mov     dword ptr [rbp+4Fh+var_78+4], ecx
0x1400404a3  mov     [rbp+4Fh+var_70], ecx
0x1400404a6  mov     [rbp+4Fh+var_6C], ecx
0x1400404a9  mov     [rbp+4Fh+var_9C], ecx
0x1400404ac  mov     dword ptr [rbp+4Fh+var_8C+4], ecx
0x1400404af  test    r8d, r8d
0x1400404b2  jz      loc_1400409F2
0x1400404b8  mov     r13d, ecx
0x1400404bb  xor     r9d, r9d; enum mbbcx_p::MbbTlvError *
0x1400404be  lea     r8, [rbp+4Fh+arg_10]; unsigned int *
0x1400404c2  lea     rdx, [rbp+4Fh+var_78]; unsigned __int8 **
0x1400404c6  lea     rcx, [rbp+4Fh+var_40]; this
0x1400404ca  call    ?ExtractValidateNextTlv@mbbcx_p@@YAPEAU_MBB_TLV_IE@@AEAPEAEAEAKAEAW4MbbTlvError@1@G@Z; mbbcx_p::ExtractValidateNextTlv(uchar * &,ulong &,mbbcx_p::MbbTlvError &,ushort)
0x1400404cf  mov     rdi, rax
0x1400404d2  test    rax, rax
0x1400404d5  jz      loc_140040BA0
0x1400404db  movzx   ecx, word ptr [rax]
0x1400404de  cmp     ecx, 9
0x1400404e1  jnz     loc_140040618
0x1400404e7  test    r13, r13
0x1400404ea  jnz     loc_140040A7E
0x1400404f0  mov     r9d, [rax+4]
0x1400404f4  xor     r12d, r12d
0x1400404f7  xor     r15d, r15d
0x1400404fa  mov     dword ptr [rbp+4Fh+arg_20], r12d
0x1400404fe  test    r9d, r9d
0x140040501  jnz     short loc_140040509
0x140040503  mov     dword ptr [rbp+4Fh+arg_10], r12d
0x140040507  jmp     short loc_14004057D
0x140040509  cmp     r9d, 1
0x14004050d  jb      loc_140040A5A
0x140040513  lea     r11, [rax+8]
0x140040517  lea     r8, [rbp+4Fh+arg_20]
0x14004051b  mov     dword ptr [rbp+4Fh+arg_10], 0
0x140040522  lea     rdx, [rbp+4Fh+arg_10]
0x140040526  mov     dword ptr [rbp+4Fh+arg_20], 0
0x14004052d  mov     rcx, r11
0x140040530  call    mbbcx_p__ValidateAndCalculateBothMbbAndWwanSingleTaiListSize
0x140040535  mov     edx, eax
0x140040537  test    eax, eax
0x140040539  jnz     short loc_140040559
0x14004053b  or      ecx, 0FFFFFFFFh
0x14004053e  sub     ecx, dword ptr [rbp+4Fh+arg_10]
0x140040541  cmp     r15d, ecx
0x140040544  ja      short loc_140040559
0x140040546  mov     ecx, dword ptr [rbp+4Fh+arg_20]
0x140040549  inc     r12d
0x14004054c  add     r15d, dword ptr [rbp+4Fh+arg_10]
0x140040550  add     r11, rcx
0x140040553  sub     r9d, dword ptr [rbp+4Fh+arg_20]
0x140040557  jnz     short loc_140040517
0x140040559  xor     eax, eax
0x14004055b  mov     dword ptr [rbp+4Fh+arg_10], edx
0x14004055e  test    edx, edx
0x140040560  cmovz   eax, r15d
0x140040564  mov     r15d, eax
0x140040567  xor     eax, eax
0x140040569  test    edx, edx
0x14004056b  cmovz   eax, r12d
0x14004056f  mov     dword ptr [rbp+4Fh+arg_20], eax
0x140040572  jnz     loc_140040A5F
0x140040578  test    r15d, r15d
0x14004057b  jnz     short loc_1400405CA
0x14004057d  lea     r12, WPP_RECORDER_INITIALIZED
0x140040584  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14004058b  jz      loc_1400409E0
0x140040591  mov     r9d, 43h ; 'C'
0x140040597  mov     eax, [rbx+10h]
0x14004059a  mov     edi, 3
0x14004059f  mov     [rsp+0E0h+var_B8], eax
0x1400405a3  mov     r8d, edi
0x1400405a6  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x1400405ad  mov     dl, dil
0x1400405b0  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1400405b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400405bc  mov     rcx, [rcx+40h]
0x1400405c0  call    WPP_RECORDER_SF_d
0x1400405c5  jmp     loc_1400409E0
0x1400405ca  lea     r12, WPP_RECORDER_INITIALIZED
0x1400405d1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400405d8  jz      short loc_140040609
0x1400405da  mov     eax, [rbx+10h]
0x1400405dd  mov     r9d, 44h ; 'D'
0x1400405e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400405ea  mov     dl, 4
0x1400405ec  mov     [rsp+0E0h+var_B8], eax
0x1400405f0  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x1400405f7  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1400405fc  lea     r8d, [r9-41h]
0x140040600  mov     rcx, [rcx+40h]
0x140040604  call    WPP_RECORDER_SF_d
0x140040609  add     [r14], r15d
0x14004060c  mov     r13, rdi
0x14004060f  mov     [rbp+4Fh+var_60], rdi
0x140040613  jmp     loc_1400409E0
0x140040618  mov     edx, 3
0x14004061d  cmp     cx, dx
0x140040620  jnz     loc_1400406B2
0x140040626  cmp     [rbp+4Fh+var_58], 0
0x14004062b  jnz     loc_140040AA3
0x140040631  lea     rdx, [rbp+4Fh+var_98]
0x140040635  mov     rcx, rdi
0x140040638  call    ?GetSNSSAICountInTlv@mbbcx_p@@YA?AW4MbbTlvError@1@QEAU_MBB_TLV_IE@@AEAK@Z; mbbcx_p::GetSNSSAICountInTlv(_MBB_TLV_IE * const,ulong &)
0x14004063d  mov     dword ptr [rbp+4Fh+arg_10], eax
0x140040640  test    eax, eax
0x140040642  jnz     loc_140040A8F
0x140040648  mov     eax, dword ptr [rbp+4Fh+var_98]
0x14004064b  test    eax, eax
0x14004064d  jnz     short loc_140040665
0x14004064f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140040656  jz      loc_1400409E0
0x14004065c  lea     r9d, [rax+47h]
0x140040660  jmp     loc_140040597
0x140040665  shl     eax, 4
0x140040668  add     eax, 4
0x14004066b  add     [r14], eax
0x14004066e  mov     dword ptr [rbp+4Fh+var_78+4], eax
0x140040671  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140040678  jz      short loc_1400406A9
0x14004067a  mov     eax, [rbx+10h]
0x14004067d  mov     r9d, 48h ; 'H'
0x140040683  mov     rcx, cs:WPP_GLOBAL_Control
0x14004068a  mov     dl, 4
0x14004068c  mov     [rsp+0E0h+var_B8], eax
0x140040690  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x140040697  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14004069c  lea     r8d, [r9-45h]
0x1400406a0  mov     rcx, [rcx+40h]
0x1400406a4  call    WPP_RECORDER_SF_d
0x1400406a9  mov     [rbp+4Fh+var_58], rdi
0x1400406ad  jmp     loc_1400409E0
0x1400406b2  cmp     ecx, 4
0x1400406b5  jnz     loc_140040747
0x1400406bb  cmp     [rbp+4Fh+var_50], 0
0x1400406c0  jnz     loc_140040ACE
0x1400406c6  lea     rdx, [rbp+4Fh+var_98+4]
0x1400406ca  mov     rcx, rdi
0x1400406cd  call    ?GetSNSSAICountInTlv@mbbcx_p@@YA?AW4MbbTlvError@1@QEAU_MBB_TLV_IE@@AEAK@Z; mbbcx_p::GetSNSSAICountInTlv(_MBB_TLV_IE * const,ulong &)
0x1400406d2  mov     dword ptr [rbp+4Fh+arg_10], eax
0x1400406d5  test    eax, eax
0x1400406d7  jnz     loc_140040ABA
0x1400406dd  mov     eax, dword ptr [rbp+4Fh+var_98+4]
0x1400406e0  test    eax, eax
0x1400406e2  jnz     short loc_1400406FA
0x1400406e4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400406eb  jz      loc_1400409E0
0x1400406f1  lea     r9d, [rax+4Bh]
0x1400406f5  jmp     loc_140040597
0x1400406fa  shl     eax, 4
0x1400406fd  add     eax, 4
0x140040700  add     [r14], eax
0x140040703  mov     [rbp+4Fh+var_70], eax
0x140040706  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14004070d  jz      short loc_14004073E
0x14004070f  mov     eax, [rbx+10h]
0x140040712  mov     r9d, 4Ch ; 'L'
0x140040718  mov     rcx, cs:WPP_GLOBAL_Control
0x14004071f  mov     dl, 4
0x140040721  mov     [rsp+0E0h+var_B8], eax
0x140040725  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14004072c  mov     qword ptr [rsp+0E0h+var_C0], rax
0x140040731  lea     r8d, [r9-49h]
0x140040735  mov     rcx, [rcx+40h]
0x140040739  call    WPP_RECORDER_SF_d
0x14004073e  mov     [rbp+4Fh+var_50], rdi
0x140040742  jmp     loc_1400409E0
0x140040747  cmp     ecx, 7
0x14004074a  jnz     loc_140040859
0x140040750  cmp     [rbp+4Fh+var_48], 0
0x140040755  jnz     loc_140040AFF
0x14004075b  mov     r8d, [rax+4]
0x14004075f  lea     r9, [rax+8]
0x140040763  xor     ecx, ecx
0x140040765  xor     r10d, r10d
0x140040768  test    r8d, r8d
0x14004076b  jz      short loc_1400407B6
0x14004076d  test    ecx, ecx
0x14004076f  jnz     short loc_1400407B1
0x140040771  movzx   eax, byte ptr [r9]
0x140040775  cmp     al, 1
0x140040777  jz      short loc_140040784
0x140040779  cmp     al, 4
0x14004077b  jz      short loc_140040784
0x14004077d  mov     ecx, 0Dh
0x140040782  jmp     short loc_1400407AC
0x140040784  lea     edx, [rax+2]
0x140040787  cmp     r8d, edx
0x14004078a  jnb     short loc_140040793
0x14004078c  mov     ecx, 0Eh
0x140040791  jmp     short loc_1400407AC
0x140040793  cmp     byte ptr [r9+1], 2
0x140040798  jbe     short loc_1400407A1
0x14004079a  mov     ecx, 14h
0x14004079f  jmp     short loc_1400407AC
0x1400407a1  mov     eax, edx
0x1400407a3  sub     r8d, edx
0x1400407a6  add     r9, rax
0x1400407a9  inc     r10d
0x1400407ac  test    r8d, r8d
0x1400407af  jnz     short loc_14004076D
0x1400407b1  mov     edx, 3
0x1400407b6  xor     esi, esi
0x1400407b8  mov     dword ptr [rbp+4Fh+arg_10], ecx
0x1400407bb  test    ecx, ecx
0x1400407bd  cmovz   esi, r10d
0x1400407c1  mov     [rbp+4Fh+var_90], esi
0x1400407c4  jnz     loc_140040AE3
0x1400407ca  test    esi, esi
0x1400407cc  jnz     short loc_14004080F
0x1400407ce  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400407d5  jz      short loc_140040801
0x1400407d7  mov     eax, [rbx+10h]
0x1400407da  lea     r9d, [rsi+4Fh]
0x1400407de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400407e5  mov     r8d, edx
0x1400407e8  mov     [rsp+0E0h+var_B8], eax
0x1400407ec  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x1400407f3  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1400407f8  mov     rcx, [rcx+40h]
0x1400407fc  call    WPP_RECORDER_SF_d
0x140040801  xor     eax, eax
0x140040803  mov     [rbp+4Fh+var_90], eax
0x140040806  mov     rsi, [rbp+4Fh+var_68]
0x14004080a  jmp     loc_1400409E0
0x14004080f  lea     eax, ds:4[rsi*8]
0x140040816  add     [r14], eax
0x140040819  mov     [rbp+4Fh+var_6C], eax
0x14004081c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140040823  jz      short loc_140040853
0x140040825  mov     eax, [rbx+10h]
0x140040828  mov     r8d, edx
0x14004082b  mov     rcx, cs:WPP_GLOBAL_Control
0x140040832  mov     r9d, 50h ; 'P'
0x140040838  mov     [rsp+0E0h+var_B8], eax
0x14004083c  mov     dl, 4
0x14004083e  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x140040845  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14004084a  mov     rcx, [rcx+40h]
0x14004084e  call    WPP_RECORDER_SF_d
0x140040853  mov     [rbp+4Fh+var_48], rdi
0x140040857  jmp     short loc_140040806
0x140040859  cmp     ecx, 5
0x14004085c  jnz     loc_1400408EE
0x140040862  cmp     [rbp+4Fh+var_80], 0
0x140040867  jnz     loc_140040B29
0x14004086d  lea     rdx, [rbp+4Fh+var_8C]
0x140040871  mov     rcx, rdi
0x140040874  call    ?GetSNSSAICountInTlv@mbbcx_p@@YA?AW4MbbTlvError@1@QEAU_MBB_TLV_IE@@AEAK@Z; mbbcx_p::GetSNSSAICountInTlv(_MBB_TLV_IE * const,ulong &)
0x140040879  mov     dword ptr [rbp+4Fh+arg_10], eax
0x14004087c  test    eax, eax
0x14004087e  jnz     loc_140040B14
0x140040884  mov     eax, dword ptr [rbp+4Fh+var_8C]
0x140040887  test    eax, eax
0x140040889  jnz     short loc_1400408A1
0x14004088b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140040892  jz      loc_1400409E0
0x140040898  lea     r9d, [rax+53h]
0x14004089c  jmp     loc_140040597
0x1400408a1  shl     eax, 4
0x1400408a4  add     eax, 4
0x1400408a7  add     [r14], eax
  ... truncated ...
```
