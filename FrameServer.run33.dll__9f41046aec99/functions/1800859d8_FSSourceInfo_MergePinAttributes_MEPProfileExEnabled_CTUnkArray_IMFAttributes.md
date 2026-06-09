# FSSourceInfo::MergePinAttributes_MEPProfileExEnabled(CTUnkArray<IMFAttributes> &)

- ea: `0x1800859d8`
- end: `0x180085f87`
- name: `?MergePinAttributes_MEPProfileExEnabled@FSSourceInfo@@IEAAJAEAV?$CTUnkArray@UIMFAttributes@@@@@Z`
- size: `1455`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
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
- `0x1800859d8`
- `0x1800e9240`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180085bce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180085e8e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180085bce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180085e8e`
- `MFPlat!MFCreateAttributes` at `0x180085c17`
- `MFPlat!MFCreateAttributes` at `0x180085c17`

## pseudocode

```c
__int64 __fastcall FSSourceInfo::MergePinAttributes_MEPProfileExEnabled(__int64 a1, __int64 *a2)
{
  __int64 v3; // rcx
  unsigned int v4; // edi
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // r12d
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  HRESULT v10; // eax
  __int64 *v11; // rdi
  UINT32 v12; // r13d
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  int v17; // eax
  IMFAttributes *v18; // rcx
  UINT32 v19; // ebx
  int v20; // r13d
  int v21; // ebx
  int v22; // eax
  __int64 v24; // rdx
  IMFAttributes *ppMFAttributes; // [rsp+40h] [rbp-19h] BYREF
  __int64 v26; // [rsp+48h] [rbp-11h] BYREF
  UINT32 cInitialSize; // [rsp+50h] [rbp-9h] BYREF
  unsigned int v28; // [rsp+54h] [rbp-5h] BYREF
  unsigned int v29; // [rsp+58h] [rbp-1h] BYREF
  int v30; // [rsp+5Ch] [rbp+3h]
  __int64 *v31; // [rsp+60h] [rbp+7h]
  PROPVARIANT pvar[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v33; // [rsp+78h] [rbp+1Fh]

  v31 = a2;
  v3 = *(_QWORD *)(a1 + 96);
  v29 = 0;
  if ( !v3 )
  {
    v4 = -1072875850;
    if ( g_wppLevels )
    {
      v5 = 88;
      goto LABEL_41;
    }
    return v4;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v3 + 64LL))(v3, &v29);
  v4 = v6;
  if ( v6 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1, v6);
    return v4;
  }
  v7 = 0;
  v30 = -1;
  if ( !v29 )
    goto LABEL_39;
  do
  {
    v8 = *(_QWORD *)(a1 + 96);
    v26 = 0;
    ppMFAttributes = 0;
    v28 = 0;
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v8 + 72LL);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v26);
    v10 = v9(v8, v7, &v26);
    v4 = v10;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_67;
      v24 = 90;
      goto LABEL_66;
    }
    v10 = (*(__int64 (__fastcall **)(__int64, const IID *, unsigned int *))(*(_QWORD *)v26 + 56LL))(
            v26,
            &MF_DEVICESTREAM_STREAM_ID,
            &v28);
    v4 = v10;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_67;
      v24 = 91;
      goto LABEL_66;
    }
    v11 = v31;
    v12 = -1;
    v13 = 0;
    if ( *((_DWORD *)v31 + 2) )
    {
      while ( 1 )
      {
        v14 = MFGetAttributeUINT32(*(_QWORD *)(*v11 + 8 * v13), &MF_DEVICESTREAM_SENSORSTREAM_FSSTREAM_ID, 0xFFFFFFFFLL);
        if ( v28 == v14 )
          break;
        v13 = (unsigned int)(v13 + 1);
        if ( (unsigned int)v13 >= *((_DWORD *)v11 + 2) )
          goto LABEL_18;
      }
      v15 = *v11;
      *(_OWORD *)pvar = 0;
      v33 = 0;
      cInitialSize = MFGetAttributeUINT32(*(_QWORD *)(v15 + 8 * v13), &MF_DEVICESTREAM_SENSORSTREAM_ID, 0xFFFFFFFFLL);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
      v17 = FSMergeAttributes(*(_QWORD *)(*v11 + 8 * v13), v26, v16, &ppMFAttributes);
      v4 = v17;
      if ( v17 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1, v17);
        PropVariantClear(pvar);
        goto LABEL_67;
      }
      if ( (*(int (__fastcall **)(_QWORD, void *, PROPVARIANT *))(**(_QWORD **)(*v31 + 8 * v13) + 24LL))(
             *(_QWORD *)(*v31 + 8 * v13),
             &MF_DEVICESTREAM_SENSORSTREAM_TAGID,
             pvar) >= 0 )
        ((void (__fastcall *)(IMFAttributes *, void *, PROPVARIANT *))ppMFAttributes->lpVtbl->SetItem)(
          ppMFAttributes,
          &MF_DEVICESTREAM_SENSORSTREAM_TAGID,
          pvar);
      PropVariantClear(pvar);
      v12 = cInitialSize;
    }
LABEL_18:
    v18 = ppMFAttributes;
    if ( !ppMFAttributes )
    {
      cInitialSize = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v26 + 240LL))(v26, &cInitialSize);
      v4 = v10;
      if ( v10 < 0 )
      {
        if ( g_wppLevels )
        {
          v24 = 93;
          goto LABEL_66;
        }
        goto LABEL_67;
      }
      v19 = cInitialSize;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
      v10 = MFCreateAttributes(&ppMFAttributes, v19);
      v4 = v10;
      if ( v10 < 0 )
      {
        if ( g_wppLevels )
        {
          v24 = 94;
          goto LABEL_66;
        }
        goto LABEL_67;
      }
      v10 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v26 + 256LL))(v26, ppMFAttributes);
      v4 = v10;
      if ( v10 < 0 )
      {
        if ( g_wppLevels )
        {
          v24 = 95;
          goto LABEL_66;
        }
        goto LABEL_67;
      }
      v18 = ppMFAttributes;
    }
    if ( v12 != -1 )
    {
      v10 = ((__int64 (__fastcall *)(IMFAttributes *, void *, _QWORD))v18->lpVtbl->SetUINT32)(
              v18,
              &MF_DEVICESTREAM_SENSORSTREAM_ID,
              v12);
      v4 = v10;
      if ( v10 < 0 )
      {
        if ( g_wppLevels )
        {
          v24 = 96;
          goto LABEL_66;
        }
        goto LABEL_67;
      }
      v18 = ppMFAttributes;
    }
    v10 = ((__int64 (__fastcall *)(IMFAttributes *, void *, _QWORD))v18->lpVtbl->SetUINT32)(
            v18,
            &MF_DEVICESTREAM_SENSORSTREAM_FSSTREAM_ID,
            v28);
    v4 = v10;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_67;
      v24 = 97;
      goto LABEL_66;
    }
    v20 = v30;
    if ( v30 != -1 || (unsigned int)MFGetAttributeUINT32(ppMFAttributes, &MF_DEVICESTREAM_FRAMESERVER_HIDDEN, 0) )
      goto LABEL_34;
    *(GUID *)pvar = GUID_00000000_0000_0000_0000_000000000000;
    v10 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, PROPVARIANT *))ppMFAttributes->lpVtbl->GetGUID)(
            ppMFAttributes,
            &MF_DEVICESTREAM_STREAM_CATEGORY,
            pvar);
    v4 = v10;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_67;
      v24 = 98;
LABEL_66:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1, v10);
      goto LABEL_67;
    }
    if ( memcmp_0(pvar, &GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba, 0x10u) )
      goto LABEL_34;
    v10 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            &MF_DEVICESTREAM_FRAMESERVER_SHARED,
            1);
    v4 = v10;
    if ( v10 < 0 )
    {
      if ( g_wppLevels )
      {
        v24 = 99;
        goto LABEL_66;
      }
LABEL_67:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v26);
      return v4;
    }
    v20 = v7;
    v30 = v7;
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 100, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1, v7);
LABEL_34:
    if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
    {
      v21 = MFGetAttributeUINT32(ppMFAttributes, &MF_DEVICESTREAM_FRAMESERVER_SHARED, 0);
      v22 = MFGetAttributeUINT32(ppMFAttributes, &MF_DEVICESTREAM_FRAMESERVER_HIDDEN, 0);
      WPP_SF_qddd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        101,
        &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
        a1,
        v7,
        v22,
        v21);
    }
    if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add(a1 + 224, ppMFAttributes) )
    {
      v4 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          102,
          &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
          a1,
          -2147024882);
      goto LABEL_67;
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v26);
    ++v7;
  }
  while ( v7 < v29 );
  if ( v20 != -1 )
    return v4;
LABEL_39:
  v4 = -2147024865;
  if ( g_wppLevels )
  {
    v5 = 103;
LABEL_41:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, a1, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x1800859d8  mov     [rsp-8+arg_10], rbx
0x1800859dd  mov     [rsp-8+arg_18], rdi
0x1800859e2  push    rbp
0x1800859e3  push    r12
0x1800859e5  push    r13
0x1800859e7  push    r14
0x1800859e9  push    r15
0x1800859eb  lea     rbp, [rsp-37h]
0x1800859f0  sub     rsp, 90h
0x1800859f7  mov     rax, cs:__security_cookie
0x1800859fe  xor     rax, rsp
0x180085a01  mov     [rbp+57h+var_30], rax
0x180085a05  mov     r15, rcx
0x180085a08  mov     [rbp+57h+var_50], rdx
0x180085a0c  mov     rcx, [rcx+60h]
0x180085a10  mov     [rbp+57h+var_58], 0
0x180085a17  test    rcx, rcx
0x180085a1a  jnz     short loc_180085A3D
0x180085a1c  mov     edi, 0C00D36B6h
0x180085a21  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085a28  jb      loc_180085E37
0x180085a2e  lea     edx, [rcx+58h]
0x180085a31  lea     r8, WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids
0x180085a38  jmp     loc_180085E20
0x180085a3d  mov     rax, [rcx]
0x180085a40  lea     rdx, [rbp+57h+var_58]
0x180085a44  mov     rax, [rax+40h]
0x180085a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085a4d  mov     edi, eax
0x180085a4f  test    eax, eax
0x180085a51  jns     short loc_180085A75
0x180085a53  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085a5a  jb      loc_180085E37
0x180085a60  mov     edx, 59h ; 'Y'
0x180085a65  mov     [rsp+0B0h+var_90], eax
0x180085a69  lea     r8, WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids
0x180085a70  jmp     loc_180085E24
0x180085a75  or      r13d, 0FFFFFFFFh
0x180085a79  lea     r14, WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids
0x180085a80  xor     r12d, r12d
0x180085a83  mov     [rbp+57h+var_54], r13d
0x180085a87  cmp     [rbp+57h+var_58], r12d
0x180085a8b  jbe     loc_180085E0A
0x180085a91  mov     rdi, [r15+60h]
0x180085a95  lea     rcx, [rbp+57h+var_68]
0x180085a99  mov     [rbp+57h+var_68], 0
0x180085aa1  mov     [rbp+57h+ppMFAttributes], 0
0x180085aa9  mov     [rbp+57h+var_5C], 0
0x180085ab0  mov     rax, [rdi]
0x180085ab3  mov     rbx, [rax+48h]
0x180085ab7  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180085abc  lea     r8, [rbp+57h+var_68]
0x180085ac0  mov     edx, r12d
0x180085ac3  mov     rcx, rdi
0x180085ac6  mov     rax, rbx
0x180085ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085ace  mov     edi, eax
0x180085ad0  test    eax, eax
0x180085ad2  js      loc_180085F48
0x180085ad8  mov     rcx, [rbp+57h+var_68]
0x180085adc  lea     r8, [rbp+57h+var_5C]
0x180085ae0  lea     rdx, MF_DEVICESTREAM_STREAM_ID
0x180085ae7  mov     rax, [rcx]
0x180085aea  mov     rax, [rax+38h]
0x180085aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085af3  mov     edi, eax
0x180085af5  test    eax, eax
0x180085af7  js      loc_180085F38
0x180085afd  mov     rdi, [rbp+57h+var_50]
0x180085b01  or      r13d, 0FFFFFFFFh
0x180085b05  xor     ebx, ebx
0x180085b07  cmp     [rdi+8], ebx
0x180085b0a  jbe     loc_180085BD8
0x180085b10  mov     rcx, [rdi]
0x180085b13  lea     rdx, MF_DEVICESTREAM_SENSORSTREAM_FSSTREAM_ID
0x180085b1a  or      r8d, 0FFFFFFFFh
0x180085b1e  mov     rcx, [rcx+rbx*8]
0x180085b22  call    MFGetAttributeUINT32
0x180085b27  cmp     [rbp+57h+var_5C], eax
0x180085b2a  jz      short loc_180085B38
0x180085b2c  inc     ebx
0x180085b2e  cmp     ebx, [rdi+8]
0x180085b31  jb      short loc_180085B10
0x180085b33  jmp     loc_180085BD8
0x180085b38  mov     rcx, [rdi]
0x180085b3b  lea     rdx, MF_DEVICESTREAM_SENSORSTREAM_ID
0x180085b42  xorps   xmm0, xmm0
0x180085b45  xor     eax, eax
0x180085b47  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180085b4b  mov     [rbp+57h+var_38], rax
0x180085b4f  or      r8d, 0FFFFFFFFh
0x180085b53  mov     rcx, [rcx+rbx*8]
0x180085b57  call    MFGetAttributeUINT32
0x180085b5c  lea     rcx, [rbp+57h+ppMFAttributes]
0x180085b60  mov     [rbp+57h+cInitialSize], eax
0x180085b63  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180085b68  mov     rcx, [rdi]
0x180085b6b  lea     r9, [rbp+57h+ppMFAttributes]
0x180085b6f  mov     rdx, [rbp+57h+var_68]
0x180085b73  mov     rcx, [rcx+rbx*8]
0x180085b77  call    ?FSMergeAttributes@@YAJPEAUIMFAttributes@@0W4FSMergeAttribCollisionFlag@@PEAPEAU1@@Z; FSMergeAttributes(IMFAttributes *,IMFAttributes *,FSMergeAttribCollisionFlag,IMFAttributes * *)
0x180085b7c  mov     edi, eax
0x180085b7e  test    eax, eax
0x180085b80  js      loc_180085E62
0x180085b86  mov     rdx, [rbp+57h+var_50]
0x180085b8a  lea     r8, [rbp+57h+pvar]
0x180085b8e  mov     rax, [rdx]
0x180085b91  lea     rdx, MF_DEVICESTREAM_SENSORSTREAM_TAGID
0x180085b98  mov     rcx, [rax+rbx*8]
0x180085b9c  mov     rax, [rcx]
0x180085b9f  mov     rax, [rax+18h]
0x180085ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085ba8  test    eax, eax
0x180085baa  js      short loc_180085BCA
0x180085bac  mov     rcx, [rbp+57h+ppMFAttributes]
0x180085bb0  lea     r8, [rbp+57h+pvar]
0x180085bb4  lea     rdx, MF_DEVICESTREAM_SENSORSTREAM_TAGID
0x180085bbb  mov     rax, [rcx]
0x180085bbe  mov     rax, [rax+90h]
0x180085bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085bca  lea     rcx, [rbp+57h+pvar]; pvar
0x180085bce  call    cs:__imp_PropVariantClear
0x180085bd4  mov     r13d, [rbp+57h+cInitialSize]
0x180085bd8  mov     rcx, [rbp+57h+ppMFAttributes]
0x180085bdc  test    rcx, rcx
0x180085bdf  jnz     short loc_180085C4C
0x180085be1  mov     [rbp+57h+cInitialSize], ecx
0x180085be4  lea     rdx, [rbp+57h+cInitialSize]
0x180085be8  mov     rcx, [rbp+57h+var_68]
0x180085bec  mov     rax, [rcx]
0x180085bef  mov     rax, [rax+0F0h]
0x180085bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085bfb  mov     edi, eax
0x180085bfd  test    eax, eax
0x180085bff  js      loc_180085EC7
0x180085c05  mov     ebx, [rbp+57h+cInitialSize]
0x180085c08  lea     rcx, [rbp+57h+ppMFAttributes]
0x180085c0c  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180085c11  mov     edx, ebx; cInitialSize
0x180085c13  lea     rcx, [rbp+57h+ppMFAttributes]; ppMFAttributes
0x180085c17  call    cs:__imp_MFCreateAttributes
0x180085c1d  mov     edi, eax
0x180085c1f  test    eax, eax
0x180085c21  js      loc_180085EB0
0x180085c27  mov     rcx, [rbp+57h+var_68]
0x180085c2b  mov     rdx, [rbp+57h+ppMFAttributes]
0x180085c2f  mov     rax, [rcx]
0x180085c32  mov     rax, [rax+100h]
0x180085c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c3e  mov     edi, eax
0x180085c40  test    eax, eax
0x180085c42  js      loc_180085E99
0x180085c48  mov     rcx, [rbp+57h+ppMFAttributes]
0x180085c4c  or      ebx, 0FFFFFFFFh
0x180085c4f  cmp     r13d, ebx
0x180085c52  jz      short loc_180085C7B
0x180085c54  mov     rax, [rcx]
0x180085c57  lea     rdx, MF_DEVICESTREAM_SENSORSTREAM_ID
0x180085c5e  mov     r8d, r13d
0x180085c61  mov     rax, [rax+0A8h]
0x180085c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c6d  mov     edi, eax
0x180085c6f  test    eax, eax
0x180085c71  js      loc_180085EDB
0x180085c77  mov     rcx, [rbp+57h+ppMFAttributes]
0x180085c7b  mov     rax, [rcx]
0x180085c7e  lea     rdx, MF_DEVICESTREAM_SENSORSTREAM_FSSTREAM_ID
0x180085c85  mov     r8d, [rbp+57h+var_5C]
0x180085c89  mov     rax, [rax+0A8h]
0x180085c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c95  mov     edi, eax
0x180085c97  test    eax, eax
0x180085c99  js      loc_180085F28
0x180085c9f  mov     r13d, [rbp+57h+var_54]
0x180085ca3  cmp     r13d, ebx
0x180085ca6  jnz     loc_180085D6F
0x180085cac  mov     rcx, [rbp+57h+ppMFAttributes]
0x180085cb0  lea     rdx, MF_DEVICESTREAM_FRAMESERVER_HIDDEN
0x180085cb7  xor     r8d, r8d
0x180085cba  call    MFGetAttributeUINT32
0x180085cbf  test    eax, eax
0x180085cc1  jnz     loc_180085D6F
0x180085cc7  mov     rcx, [rbp+57h+ppMFAttributes]
0x180085ccb  lea     r8, [rbp+57h+pvar]
0x180085ccf  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180085cd6  lea     rdx, MF_DEVICESTREAM_STREAM_CATEGORY
0x180085cdd  movdqu  xmmword ptr [rbp+57h+pvar], xmm0
0x180085ce2  mov     rax, [rcx]
0x180085ce5  mov     rax, [rax+50h]
0x180085ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085cee  mov     edi, eax
0x180085cf0  test    eax, eax
0x180085cf2  js      loc_180085EFF
0x180085cf8  mov     r8d, 10h; Size
0x180085cfe  lea     rdx, _GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba; Buf2
0x180085d05  lea     rcx, [rbp+57h+pvar]; Buf1
0x180085d09  call    memcmp_0
0x180085d0e  test    eax, eax
0x180085d10  jnz     short loc_180085D6F
0x180085d12  mov     rcx, [rbp+57h+ppMFAttributes]
0x180085d16  lea     rdx, MF_DEVICESTREAM_FRAMESERVER_SHARED
0x180085d1d  mov     r8d, 1
0x180085d23  mov     rax, [rcx]
0x180085d26  mov     rax, [rax+0A8h]
0x180085d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085d32  mov     edi, eax
0x180085d34  test    eax, eax
0x180085d36  js      loc_180085EEF
0x180085d3c  mov     r13d, r12d
0x180085d3f  mov     [rbp+57h+var_54], r12d
0x180085d43  cmp     cs:byte_18010EC4D, 8
0x180085d4a  jb      short loc_180085D6F
0x180085d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180085d53  mov     edx, 64h ; 'd'
0x180085d58  mov     r9, r15
0x180085d5b  mov     [rsp+0B0h+var_90], r12d
0x180085d60  mov     r8, r14
0x180085d63  mov     rcx, [rcx+0D8h]
0x180085d6a  call    WPP_SF_qD
0x180085d6f  cmp     cs:byte_18010EC4D, 10h
0x180085d76  jb      short loc_180085DCE
0x180085d78  mov     rcx, [rbp+57h+ppMFAttributes]
0x180085d7c  lea     rdx, MF_DEVICESTREAM_FRAMESERVER_SHARED
0x180085d83  xor     r8d, r8d
0x180085d86  call    MFGetAttributeUINT32
0x180085d8b  mov     rcx, [rbp+57h+ppMFAttributes]
0x180085d8f  lea     rdx, MF_DEVICESTREAM_FRAMESERVER_HIDDEN
0x180085d96  xor     r8d, r8d
0x180085d99  mov     ebx, eax
0x180085d9b  call    MFGetAttributeUINT32
0x180085da0  mov     rcx, cs:WPP_GLOBAL_Control
0x180085da7  mov     edx, 65h ; 'e'
0x180085dac  mov     [rsp+0B0h+var_80], ebx
0x180085db0  mov     r9, r15
0x180085db3  mov     [rsp+0B0h+var_88], eax
0x180085db7  mov     r8, r14
0x180085dba  mov     [rsp+0B0h+var_90], r12d
0x180085dbf  mov     rcx, [rcx+0D8h]
0x180085dc6  call    WPP_SF_qddd
0x180085dcb  or      ebx, 0FFFFFFFFh
0x180085dce  mov     rdx, [rbp+57h+ppMFAttributes]
0x180085dd2  lea     rcx, [r15+0E0h]
0x180085dd9  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x180085dde  test    eax, eax
0x180085de0  jz      loc_180085F0F
0x180085de6  lea     rcx, [rbp+57h+ppMFAttributes]; void *
0x180085dea  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180085def  lea     rcx, [rbp+57h+var_68]; void *
0x180085df3  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180085df8  inc     r12d
0x180085dfb  cmp     r12d, [rbp+57h+var_58]
0x180085dff  jb      loc_180085A91
0x180085e05  cmp     r13d, ebx
0x180085e08  jnz     short loc_180085E37
0x180085e0a  mov     edi, 8007001Fh
0x180085e0f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085e16  jb      short loc_180085E37
0x180085e18  mov     edx, 67h ; 'g'
0x180085e1d  mov     r8, r14
0x180085e20  mov     [rsp+0B0h+var_90], edi
0x180085e24  mov     rcx, cs:WPP_GLOBAL_Control
0x180085e2b  mov     r9, r15
0x180085e2e  mov     rcx, [rcx+10h]
0x180085e32  call    WPP_SF_qD
0x180085e37  mov     eax, edi
0x180085e39  mov     rcx, [rbp+57h+var_30]
0x180085e3d  xor     rcx, rsp; StackCookie
0x180085e40  call    __security_check_cookie
0x180085e45  lea     r11, [rsp+0B0h+var_20]
0x180085e4d  mov     rbx, [r11+40h]
0x180085e51  mov     rdi, [r11+48h]
0x180085e55  mov     rsp, r11
0x180085e58  pop     r15
0x180085e5a  pop     r14
0x180085e5c  pop     r13
0x180085e5e  pop     r12
0x180085e60  pop     rbp
0x180085e61  retn
0x180085e62  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085e69  jb      short loc_180085E8A
0x180085e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180085e72  mov     edx, 5Ch ; '\'
0x180085e77  mov     r9, r15
0x180085e7a  mov     [rsp+0B0h+var_90], eax
0x180085e7e  mov     r8, r14
0x180085e81  mov     rcx, [rcx+10h]
0x180085e85  call    WPP_SF_qD
0x180085e8a  lea     rcx, [rbp+57h+pvar]; pvar
0x180085e8e  call    cs:__imp_PropVariantClear
0x180085e94  jmp     loc_180085F70
0x180085e99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085ea0  jb      loc_180085F70
0x180085ea6  mov     edx, 5Fh ; '_'
0x180085eab  jmp     loc_180085F56
0x180085eb0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085eb7  jb      loc_180085F70
0x180085ebd  mov     edx, 5Eh ; '^'
0x180085ec2  jmp     loc_180085F56
0x180085ec7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085ece  jb      loc_180085F70
  ... truncated ...
```
