# FSSourceInfo::MergePinAttributes_MEPProfileExDisabled(CTUnkArray<IMFAttributes> &)

- ea: `0x1800852c4`
- end: `0x1800859d0`
- name: `?MergePinAttributes_MEPProfileExDisabled@FSSourceInfo@@IEAAJAEAV?$CTUnkArray@UIMFAttributes@@@@@Z`
- size: `1804`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180083780`

## callees

- `0x180003e20`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x18000ad10`
- `0x180017ccc`
- `0x180024200`
- `0x1800643d4`
- `0x1800852c4`
- `0x1800e9240`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800854d1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800857a0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800854d1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800857a0`
- `MFPlat!MFCreateAttributes` at `0x180085516`
- `MFPlat!MFCreateAttributes` at `0x180085516`

## pseudocode

```c
__int64 __fastcall FSSourceInfo::MergePinAttributes_MEPProfileExDisabled(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rcx
  unsigned int v4; // edi
  int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // r13d
  unsigned int v8; // r12d
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  HRESULT v11; // eax
  _QWORD *v12; // rdi
  unsigned int v13; // r13d
  __int64 i; // rbx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // eax
  IMFAttributes *v19; // rcx
  UINT32 v20; // ebx
  unsigned __int8 v21; // bl
  int v22; // eax
  int v23; // ebx
  int v24; // eax
  unsigned int v25; // r13d
  __int64 v26; // rdx
  __int64 v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rcx
  bool v31; // [rsp+40h] [rbp-49h]
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-41h] BYREF
  __int64 v33; // [rsp+50h] [rbp-39h] BYREF
  int v34; // [rsp+58h] [rbp-31h]
  unsigned int v35; // [rsp+5Ch] [rbp-2Dh]
  UINT32 cInitialSize; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v37; // [rsp+64h] [rbp-25h] BYREF
  unsigned int v38; // [rsp+68h] [rbp-21h]
  unsigned int v39; // [rsp+6Ch] [rbp-1Dh] BYREF
  _QWORD *v40; // [rsp+70h] [rbp-19h]
  PROPVARIANT pvar[2]; // [rsp+78h] [rbp-11h] BYREF
  __int64 v42; // [rsp+88h] [rbp-1h]
  GUID Buf1; // [rsp+90h] [rbp+7h] BYREF

  v40 = a2;
  v3 = *(_QWORD *)(a1 + 96);
  v39 = 0;
  if ( !v3 )
  {
    v4 = -1072875850;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        104,
        &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
        a1,
        -1072875850);
    return v4;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v3 + 64LL))(v3, &v39);
  v4 = v5;
  if ( v5 < 0 )
  {
    if ( !g_wppLevels )
      return v4;
    v6 = 105;
LABEL_89:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1, v5);
    return v4;
  }
  v31 = 0;
  v7 = 0;
  v38 = -1;
  v8 = -1;
  v34 = -1;
  while ( 2 )
  {
    v35 = v7;
    if ( v7 < v39 )
    {
      v9 = *(_QWORD *)(a1 + 96);
      v33 = 0;
      ppMFAttributes = 0;
      Buf1 = GUID_00000000_0000_0000_0000_000000000000;
      v37 = 0;
      v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v9 + 72LL);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v33);
      v11 = v10(v9, v7, &v33);
      v4 = v11;
      if ( v11 < 0 )
      {
        if ( g_wppLevels )
        {
          v26 = 106;
          goto LABEL_74;
        }
      }
      else
      {
        v11 = (*(__int64 (__fastcall **)(__int64, const IID *, unsigned int *))(*(_QWORD *)v33 + 56LL))(
                v33,
                &MF_DEVICESTREAM_STREAM_ID,
                &v37);
        v4 = v11;
        if ( v11 >= 0 )
        {
          v12 = v40;
          v13 = -1;
          for ( i = 0; (unsigned int)i < *((_DWORD *)v12 + 2); i = (unsigned int)(i + 1) )
          {
            v15 = MFGetAttributeUINT32(
                    *(_QWORD *)(*v12 + 8 * i),
                    MF_DEVICESTREAM_SENSORSTREAM_FSSTREAM_ID,
                    0xFFFFFFFFLL);
            if ( v37 == v15 )
            {
              v16 = *v12;
              *(_OWORD *)pvar = 0;
              v42 = 0;
              v13 = MFGetAttributeUINT32(*(_QWORD *)(v16 + 8 * i), MF_DEVICESTREAM_SENSORSTREAM_ID, 0xFFFFFFFFLL);
              wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
              v18 = FSMergeAttributes(*(_QWORD *)(*v12 + 8 * i), v33, v17, &ppMFAttributes);
              v4 = v18;
              if ( v18 < 0 )
              {
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    108,
                    &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
                    a1,
                    v18);
                PropVariantClear(pvar);
                goto LABEL_75;
              }
              if ( (*(int (__fastcall **)(_QWORD, __int64 *, PROPVARIANT *))(**(_QWORD **)(*v40 + 8 * i) + 24LL))(
                     *(_QWORD *)(*v40 + 8 * i),
                     MF_DEVICESTREAM_SENSORSTREAM_TAGID,
                     pvar) >= 0 )
                ((void (__fastcall *)(IMFAttributes *, __int64 *, PROPVARIANT *))ppMFAttributes->lpVtbl->SetItem)(
                  ppMFAttributes,
                  MF_DEVICESTREAM_SENSORSTREAM_TAGID,
                  pvar);
              PropVariantClear(pvar);
              break;
            }
          }
          v19 = ppMFAttributes;
          if ( !ppMFAttributes )
          {
            cInitialSize = 0;
            v11 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v33 + 240LL))(v33, &cInitialSize);
            v4 = v11;
            if ( v11 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_75;
              v26 = 109;
              goto LABEL_74;
            }
            v20 = cInitialSize;
            wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
            v11 = MFCreateAttributes(&ppMFAttributes, v20);
            v4 = v11;
            if ( v11 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_75;
              v26 = 110;
              goto LABEL_74;
            }
            v11 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v33 + 256LL))(v33, ppMFAttributes);
            v4 = v11;
            if ( v11 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_75;
              v26 = 111;
              goto LABEL_74;
            }
            v19 = ppMFAttributes;
          }
          if ( v13 == -1 )
            goto LABEL_27;
          v11 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))v19->lpVtbl->SetUINT32)(
                  v19,
                  MF_DEVICESTREAM_SENSORSTREAM_ID,
                  v13);
          v4 = v11;
          if ( v11 >= 0 )
          {
            v19 = ppMFAttributes;
LABEL_27:
            v11 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))v19->lpVtbl->SetUINT32)(
                    v19,
                    MF_DEVICESTREAM_SENSORSTREAM_FSSTREAM_ID,
                    v37);
            v4 = v11;
            if ( v11 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_75;
              v26 = 113;
            }
            else
            {
              if ( (unsigned int)MFGetAttributeUINT32(ppMFAttributes, MF_DEVICESTREAM_FRAMESERVER_HIDDEN, 0) )
              {
                v8 = v34;
LABEL_46:
                if ( (unsigned __int8)byte_18010EC4D < 0x10u )
                {
                  v25 = v35;
                }
                else
                {
                  v23 = MFGetAttributeUINT32(ppMFAttributes, &MF_DEVICESTREAM_FRAMESERVER_SHARED, 0);
                  v24 = MFGetAttributeUINT32(ppMFAttributes, MF_DEVICESTREAM_FRAMESERVER_HIDDEN, 0);
                  v25 = v35;
                  WPP_SF_qddd(
                    *((_QWORD *)WPP_GLOBAL_Control + 27),
                    116,
                    &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
                    a1,
                    v35,
                    v24,
                    v23);
                }
                if ( (unsigned int)CTUnkArray<IMFMediaType>::Add(a1 + 224, ppMFAttributes) )
                {
                  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
                  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v33);
                  v7 = v25 + 1;
                  continue;
                }
                v4 = -2147024882;
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    117,
                    &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
                    a1,
                    -2147024882);
                goto LABEL_75;
              }
              cInitialSize = 0;
              v11 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, GUID *))ppMFAttributes->lpVtbl->GetGUID)(
                      ppMFAttributes,
                      &MF_DEVICESTREAM_STREAM_CATEGORY,
                      &Buf1);
              v4 = v11;
              if ( v11 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_75;
                v26 = 114;
              }
              else
              {
                v21 = 0;
                if ( !memcmp_0(&Buf1, &GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba, 0x10u) )
                {
                  v22 = MFGetAttributeUINT32(ppMFAttributes, MF_STREAM_ALL_ENCODEDMEDIATYPE_STREAM, 0);
                  v8 = v34;
                  if ( !v22 && v34 == -1 )
                  {
                    v8 = v35;
                    v34 = v35;
                  }
                }
                else if ( memcmp_0(&Buf1, &GUID_fb6c4282_0353_11d1_905f_0000c0cc16ba, 0x10u)
                       || (unsigned int)MFGetAttributeUINT32(ppMFAttributes, MF_STREAM_ALL_ENCODEDMEDIATYPE_STREAM, 0) )
                {
                  v8 = v34;
                }
                else
                {
                  v21 = 1;
                  v8 = v34;
                  if ( v38 == -1 )
                    v38 = v35;
                }
                if ( ((int (__fastcall *)(IMFAttributes *, const IID *, UINT32 *))ppMFAttributes->lpVtbl->GetUINT32)(
                       ppMFAttributes,
                       &MF_DEVICESTREAM_FRAMESERVER_SHARED,
                       &cInitialSize) >= 0 )
                {
                  if ( !v31 )
                    v31 = cInitialSize != 0;
                  goto LABEL_46;
                }
                v11 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
                        ppMFAttributes,
                        &MF_DEVICESTREAM_FRAMESERVER_SHARED,
                        v21);
                v4 = v11;
                if ( v11 >= 0 )
                {
                  if ( !v31 )
                    v31 = v21;
                  goto LABEL_46;
                }
                if ( !g_wppLevels )
                  goto LABEL_75;
                v26 = 115;
              }
            }
            goto LABEL_74;
          }
          if ( !g_wppLevels )
            goto LABEL_75;
          v26 = 112;
LABEL_74:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1, v11);
          goto LABEL_75;
        }
        if ( g_wppLevels )
        {
          v26 = 107;
          goto LABEL_74;
        }
      }
LABEL_75:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v33);
      return v4;
    }
    break;
  }
  if ( v31 )
    return v4;
  v27 = v38;
  if ( v38 == -1 )
  {
    if ( v8 != -1 )
    {
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 120, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1, v8);
      v29 = *(_QWORD *)(*(_QWORD *)(a1 + 224) + 8LL * v8);
      v5 = (*(__int64 (__fastcall **)(__int64, const IID *, __int64))(*(_QWORD *)v29 + 168LL))(
             v29,
             &MF_DEVICESTREAM_FRAMESERVER_SHARED,
             1);
      v4 = v5;
      if ( v5 < 0 )
      {
        if ( g_wppLevels )
        {
          v6 = 121;
          goto LABEL_89;
        }
      }
    }
  }
  else
  {
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 118, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1, v38);
    v28 = *(_QWORD *)(*(_QWORD *)(a1 + 224) + 8 * v27);
    v5 = (*(__int64 (__fastcall **)(__int64, const IID *, __int64))(*(_QWORD *)v28 + 168LL))(
           v28,
           &MF_DEVICESTREAM_FRAMESERVER_SHARED,
           1);
    v4 = v5;
    if ( v5 < 0 && g_wppLevels )
    {
      v6 = 119;
      goto LABEL_89;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800852c4  mov     [rsp-8+arg_10], rbx
0x1800852c9  push    rbp
0x1800852ca  push    rsi
0x1800852cb  push    rdi
0x1800852cc  push    r12
0x1800852ce  push    r13
0x1800852d0  push    r14
0x1800852d2  push    r15
0x1800852d4  lea     rbp, [rsp-27h]
0x1800852d9  sub     rsp, 0B0h
0x1800852e0  mov     rax, cs:__security_cookie
0x1800852e7  xor     rax, rsp
0x1800852ea  mov     [rbp+57h+var_40], rax
0x1800852ee  mov     r14, rcx
0x1800852f1  mov     [rbp+57h+var_70], rdx
0x1800852f5  mov     rcx, [rcx+60h]
0x1800852f9  mov     [rbp+57h+var_74], 0
0x180085300  test    rcx, rcx
0x180085303  jnz     short loc_18008532D
0x180085305  mov     edi, 0C00D36B6h
0x18008530a  lea     esi, [rcx+1]
0x18008530d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180085314  jb      loc_1800859A7
0x18008531a  lea     edx, [rcx+68h]
0x18008531d  mov     [rsp+0E0h+var_C0], edi
0x180085321  lea     r8, WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids
0x180085328  jmp     loc_180085994
0x18008532d  mov     rax, [rcx]
0x180085330  lea     rdx, [rbp+57h+var_74]
0x180085334  mov     rax, [rax+40h]
0x180085338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008533d  mov     edi, eax
0x18008533f  test    eax, eax
0x180085341  jns     short loc_180085364
0x180085343  mov     esi, 1
0x180085348  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18008534f  jb      loc_1800859A7
0x180085355  lea     edx, [rsi+68h]
0x180085358  lea     r8, WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids
0x18008535f  jmp     loc_180085990
0x180085364  or      eax, 0FFFFFFFFh
0x180085367  mov     [rbp+57h+var_A0], 0
0x18008536b  xor     r13d, r13d
0x18008536e  mov     [rbp+57h+var_78], eax
0x180085371  mov     r12d, eax
0x180085374  mov     [rbp+57h+var_88], eax
0x180085377  lea     r15, WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids
0x18008537e  lea     esi, [r13+1]
0x180085382  mov     [rbp+57h+var_84], r13d
0x180085386  cmp     r13d, [rbp+57h+var_74]
0x18008538a  jnb     loc_180085899
0x180085390  mov     rdi, [r14+60h]
0x180085394  lea     rcx, [rbp+57h+var_90]
0x180085398  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18008539f  mov     [rbp+57h+var_90], 0
0x1800853a7  mov     [rbp+57h+ppMFAttributes], 0
0x1800853af  movdqu  [rbp+57h+Buf1], xmm0
0x1800853b4  mov     [rbp+57h+var_7C], 0
0x1800853bb  mov     rax, [rdi]
0x1800853be  mov     rbx, [rax+48h]
0x1800853c2  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800853c7  lea     r8, [rbp+57h+var_90]
0x1800853cb  mov     edx, r13d
0x1800853ce  mov     rcx, rdi
0x1800853d1  mov     rax, rbx
0x1800853d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800853d9  mov     edi, eax
0x1800853db  test    eax, eax
0x1800853dd  js      loc_18008585A
0x1800853e3  mov     rcx, [rbp+57h+var_90]
0x1800853e7  lea     r8, [rbp+57h+var_7C]
0x1800853eb  lea     rdx, MF_DEVICESTREAM_STREAM_ID
0x1800853f2  mov     rax, [rcx]
0x1800853f5  mov     rax, [rax+38h]
0x1800853f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800853fe  mov     edi, eax
0x180085400  test    eax, eax
0x180085402  js      loc_18008584A
0x180085408  mov     rdi, [rbp+57h+var_70]
0x18008540c  or      r13d, 0FFFFFFFFh
0x180085410  xor     ebx, ebx
0x180085412  cmp     ebx, [rdi+8]
0x180085415  jnb     loc_1800854D7
0x18008541b  mov     rcx, [rdi]
0x18008541e  lea     rdx, MF_DEVICESTREAM_SENSORSTREAM_FSSTREAM_ID
0x180085425  or      r8d, 0FFFFFFFFh
0x180085429  mov     rcx, [rcx+rbx*8]
0x18008542d  call    MFGetAttributeUINT32
0x180085432  cmp     [rbp+57h+var_7C], eax
0x180085435  jz      short loc_18008543B
0x180085437  add     ebx, esi
0x180085439  jmp     short loc_180085412
0x18008543b  mov     rcx, [rdi]
0x18008543e  lea     rdx, MF_DEVICESTREAM_SENSORSTREAM_ID
0x180085445  xorps   xmm0, xmm0
0x180085448  xor     eax, eax
0x18008544a  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18008544e  mov     [rbp+57h+var_58], rax
0x180085452  or      r8d, 0FFFFFFFFh
0x180085456  mov     rcx, [rcx+rbx*8]
0x18008545a  call    MFGetAttributeUINT32
0x18008545f  lea     rcx, [rbp+57h+ppMFAttributes]
0x180085463  mov     r13d, eax
0x180085466  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18008546b  mov     rcx, [rdi]
0x18008546e  lea     r9, [rbp+57h+ppMFAttributes]
0x180085472  mov     rdx, [rbp+57h+var_90]
0x180085476  mov     rcx, [rcx+rbx*8]
0x18008547a  call    ?FSMergeAttributes@@YAJPEAUIMFAttributes@@0W4FSMergeAttribCollisionFlag@@PEAPEAU1@@Z; FSMergeAttributes(IMFAttributes *,IMFAttributes *,FSMergeAttribCollisionFlag,IMFAttributes * *)
0x18008547f  mov     edi, eax
0x180085481  test    eax, eax
0x180085483  js      loc_180085774
0x180085489  mov     rdx, [rbp+57h+var_70]
0x18008548d  lea     r8, [rbp+57h+pvar]
0x180085491  mov     rax, [rdx]
0x180085494  lea     rdx, MF_DEVICESTREAM_SENSORSTREAM_TAGID
0x18008549b  mov     rcx, [rax+rbx*8]
0x18008549f  mov     rax, [rcx]
0x1800854a2  mov     rax, [rax+18h]
0x1800854a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800854ab  test    eax, eax
0x1800854ad  js      short loc_1800854CD
0x1800854af  mov     rcx, [rbp+57h+ppMFAttributes]
0x1800854b3  lea     r8, [rbp+57h+pvar]
0x1800854b7  lea     rdx, MF_DEVICESTREAM_SENSORSTREAM_TAGID
0x1800854be  mov     rax, [rcx]
0x1800854c1  mov     rax, [rax+90h]
0x1800854c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800854cd  lea     rcx, [rbp+57h+pvar]; pvar
0x1800854d1  call    cs:__imp_PropVariantClear
0x1800854d7  mov     rcx, [rbp+57h+ppMFAttributes]
0x1800854db  test    rcx, rcx
0x1800854de  jnz     short loc_18008554B
0x1800854e0  mov     [rbp+57h+cInitialSize], ecx
0x1800854e3  lea     rdx, [rbp+57h+cInitialSize]
0x1800854e7  mov     rcx, [rbp+57h+var_90]
0x1800854eb  mov     rax, [rcx]
0x1800854ee  mov     rax, [rax+0F0h]
0x1800854f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800854fa  mov     edi, eax
0x1800854fc  test    eax, eax
0x1800854fe  js      loc_1800857D9
0x180085504  mov     ebx, [rbp+57h+cInitialSize]
0x180085507  lea     rcx, [rbp+57h+ppMFAttributes]
0x18008550b  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180085510  mov     edx, ebx; cInitialSize
0x180085512  lea     rcx, [rbp+57h+ppMFAttributes]; ppMFAttributes
0x180085516  call    cs:__imp_MFCreateAttributes
0x18008551c  mov     edi, eax
0x18008551e  test    eax, eax
0x180085520  js      loc_1800857C2
0x180085526  mov     rcx, [rbp+57h+var_90]
0x18008552a  mov     rdx, [rbp+57h+ppMFAttributes]
0x18008552e  mov     rax, [rcx]
0x180085531  mov     rax, [rax+100h]
0x180085538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008553d  mov     edi, eax
0x18008553f  test    eax, eax
0x180085541  js      loc_1800857AB
0x180085547  mov     rcx, [rbp+57h+ppMFAttributes]
0x18008554b  or      r12d, 0FFFFFFFFh
0x18008554f  cmp     r13d, r12d
0x180085552  jz      short loc_18008557B
0x180085554  mov     rax, [rcx]
0x180085557  lea     rdx, MF_DEVICESTREAM_SENSORSTREAM_ID
0x18008555e  mov     r8d, r13d
0x180085561  mov     rax, [rax+0A8h]
0x180085568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008556d  mov     edi, eax
0x18008556f  test    eax, eax
0x180085571  js      loc_1800857ED
0x180085577  mov     rcx, [rbp+57h+ppMFAttributes]
0x18008557b  mov     rax, [rcx]
0x18008557e  lea     rdx, MF_DEVICESTREAM_SENSORSTREAM_FSSTREAM_ID
0x180085585  mov     r8d, [rbp+57h+var_7C]
0x180085589  mov     rax, [rax+0A8h]
0x180085590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085595  mov     edi, eax
0x180085597  test    eax, eax
0x180085599  js      loc_18008583A
0x18008559f  mov     rcx, [rbp+57h+ppMFAttributes]
0x1800855a3  lea     rdx, MF_DEVICESTREAM_FRAMESERVER_HIDDEN
0x1800855aa  xor     r8d, r8d
0x1800855ad  call    MFGetAttributeUINT32
0x1800855b2  test    eax, eax
0x1800855b4  jnz     loc_1800856D8
0x1800855ba  mov     rcx, [rbp+57h+ppMFAttributes]
0x1800855be  lea     r8, [rbp+57h+Buf1]
0x1800855c2  mov     [rbp+57h+cInitialSize], eax
0x1800855c5  lea     rdx, MF_DEVICESTREAM_STREAM_CATEGORY
0x1800855cc  mov     rax, [rcx]
0x1800855cf  mov     rax, [rax+50h]
0x1800855d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800855d8  mov     edi, eax
0x1800855da  test    eax, eax
0x1800855dc  js      loc_180085811
0x1800855e2  mov     r13d, 10h
0x1800855e8  lea     rdx, _GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba; Buf2
0x1800855ef  mov     r8d, r13d; Size
0x1800855f2  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800855f6  xor     bl, bl
0x1800855f8  call    memcmp_0
0x1800855fd  test    eax, eax
0x1800855ff  jnz     short loc_18008562C
0x180085601  mov     rcx, [rbp+57h+ppMFAttributes]
0x180085605  lea     rdx, MF_STREAM_ALL_ENCODEDMEDIATYPE_STREAM
0x18008560c  xor     r8d, r8d
0x18008560f  call    MFGetAttributeUINT32
0x180085614  mov     r12d, [rbp+57h+var_88]
0x180085618  test    eax, eax
0x18008561a  jnz     short loc_180085673
0x18008561c  cmp     r12d, 0FFFFFFFFh
0x180085620  jnz     short loc_180085673
0x180085622  mov     r12d, [rbp+57h+var_84]
0x180085626  mov     [rbp+57h+var_88], r12d
0x18008562a  jmp     short loc_180085673
0x18008562c  mov     r8, r13; Size
0x18008562f  lea     rdx, _GUID_fb6c4282_0353_11d1_905f_0000c0cc16ba; Buf2
0x180085636  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18008563a  call    memcmp_0
0x18008563f  test    eax, eax
0x180085641  jnz     short loc_18008566F
0x180085643  mov     rcx, [rbp+57h+ppMFAttributes]
0x180085647  lea     rdx, MF_STREAM_ALL_ENCODEDMEDIATYPE_STREAM
0x18008564e  xor     r8d, r8d
0x180085651  call    MFGetAttributeUINT32
0x180085656  test    eax, eax
0x180085658  jnz     short loc_18008566F
0x18008565a  cmp     [rbp+57h+var_78], r12d
0x18008565e  mov     bl, sil
0x180085661  mov     r12d, [rbp+57h+var_88]
0x180085665  jnz     short loc_180085673
0x180085667  mov     eax, [rbp+57h+var_84]
0x18008566a  mov     [rbp+57h+var_78], eax
0x18008566d  jmp     short loc_180085673
0x18008566f  mov     r12d, [rbp+57h+var_88]
0x180085673  mov     rcx, [rbp+57h+ppMFAttributes]
0x180085677  lea     r8, [rbp+57h+cInitialSize]
0x18008567b  lea     rdx, MF_DEVICESTREAM_FRAMESERVER_SHARED
0x180085682  mov     rax, [rcx]
0x180085685  mov     rax, [rax+38h]
0x180085689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008568e  xor     r13d, r13d
0x180085691  test    eax, eax
0x180085693  jns     short loc_1800856C8
0x180085695  mov     rcx, [rbp+57h+ppMFAttributes]
0x180085699  lea     rdx, MF_DEVICESTREAM_FRAMESERVER_SHARED
0x1800856a0  movzx   r8d, bl
0x1800856a4  mov     rax, [rcx]
0x1800856a7  mov     rax, [rax+0A8h]
0x1800856ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800856b3  mov     edi, eax
0x1800856b5  test    eax, eax
0x1800856b7  js      loc_180085801
0x1800856bd  cmp     [rbp+57h+var_A0], r13b
0x1800856c1  jnz     short loc_1800856DC
0x1800856c3  mov     [rbp+57h+var_A0], bl
0x1800856c6  jmp     short loc_1800856DC
0x1800856c8  cmp     [rbp+57h+var_A0], r13b
0x1800856cc  jnz     short loc_1800856DC
0x1800856ce  cmp     [rbp+57h+cInitialSize], r13d
0x1800856d2  setnz   [rbp+57h+var_A0]
0x1800856d6  jmp     short loc_1800856DC
0x1800856d8  mov     r12d, [rbp+57h+var_88]
0x1800856dc  cmp     cs:byte_18010EC4D, 10h
0x1800856e3  jb      short loc_18008573E
0x1800856e5  mov     rcx, [rbp+57h+ppMFAttributes]
0x1800856e9  lea     rdx, MF_DEVICESTREAM_FRAMESERVER_SHARED
0x1800856f0  xor     r8d, r8d
0x1800856f3  call    MFGetAttributeUINT32
0x1800856f8  mov     rcx, [rbp+57h+ppMFAttributes]
0x1800856fc  lea     rdx, MF_DEVICESTREAM_FRAMESERVER_HIDDEN
0x180085703  xor     r8d, r8d
0x180085706  mov     ebx, eax
0x180085708  call    MFGetAttributeUINT32
0x18008570d  mov     rcx, cs:WPP_GLOBAL_Control
0x180085714  mov     edx, 74h ; 't'
0x180085719  mov     r13d, [rbp+57h+var_84]
0x18008571d  mov     r9, r14
0x180085720  mov     [rsp+0E0h+var_B0], ebx
0x180085724  mov     r8, r15
0x180085727  mov     [rsp+0E0h+var_B8], eax
0x18008572b  mov     rcx, [rcx+0D8h]
0x180085732  mov     [rsp+0E0h+var_C0], r13d
0x180085737  call    WPP_SF_qddd
0x18008573c  jmp     short loc_180085742
0x18008573e  mov     r13d, [rbp+57h+var_84]
0x180085742  mov     rdx, [rbp+57h+ppMFAttributes]
0x180085746  lea     rcx, [r14+0E0h]
0x18008574d  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x180085752  test    eax, eax
0x180085754  jz      loc_180085821
0x18008575a  lea     rcx, [rbp+57h+ppMFAttributes]; void *
0x18008575e  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180085763  lea     rcx, [rbp+57h+var_90]; void *
0x180085767  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18008576c  add     r13d, esi
0x18008576f  jmp     loc_180085382
0x180085774  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18008577b  jb      short loc_18008579C
  ... truncated ...
```
