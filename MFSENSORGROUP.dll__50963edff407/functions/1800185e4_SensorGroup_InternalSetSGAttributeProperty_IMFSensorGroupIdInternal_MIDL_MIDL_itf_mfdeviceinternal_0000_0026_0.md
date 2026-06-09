# SensorGroup::InternalSetSGAttributeProperty(IMFSensorGroupIdInternal *,__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0003 *)

- ea: `0x1800185e4`
- end: `0x180018b32`
- name: `?InternalSetSGAttributeProperty@SensorGroup@@IEAAJPEAUIMFSensorGroupIdInternal@@PEAU__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0003@@@Z`
- size: `1358`
- prototype: `__int64 __fastcall(SensorGroup *__hidden this, struct IMFSensorGroupIdInternal *, struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0003 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017b9c`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000c94c`
- `0x180015e80`
- `0x1800185e4`
- `0x1800199f4`
- `0x180019a4c`
- `0x18002f4e4`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018918`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018987`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018918`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018987`
- `MFPlat!MFGetAttributesAsBlob` at `0x180018aa9`
- `MFPlat!MFGetAttributesAsBlob` at `0x180018aa9`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x180018a3d`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x180018a3d`

## pseudocode

```c
__int64 __fastcall SensorGroup::InternalSetSGAttributeProperty(
        struct IMFAttributes **this,
        struct IMFSensorGroupIdInternal *a2,
        struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0003 *a3)
{
  char v6; // r15
  HRESULT v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  struct IMFAttributes *v10; // rcx
  struct IMFAttributesVtbl *lpVtbl; // rax
  unsigned int v12; // ebx
  __int64 v13; // r8
  const unsigned __int16 *v14; // r12
  __int64 v15; // rax
  char v16; // bl
  const wchar_t *v17; // rax
  __int64 v18; // rcx
  int v19; // r8d
  int v20; // eax
  __int64 v21; // rdx
  struct IMFAttributes *v22; // rcx
  IMFAttributes *v23; // rcx
  int v24; // eax
  LPVOID pv; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int16 *v27; // [rsp+38h] [rbp-38h] BYREF
  UINT8 *pBuf; // [rsp+40h] [rbp-30h] BYREF
  struct IMFAttributes *v29; // [rsp+48h] [rbp-28h] BYREF
  LPVOID *p_pv; // [rsp+50h] [rbp-20h] BYREF
  __int64 v31; // [rsp+58h] [rbp-18h] BYREF
  char v32; // [rsp+60h] [rbp-10h]
  int v33; // [rsp+B8h] [rbp+48h] BYREF
  __int64 pcbBufSize; // [rsp+C8h] [rbp+58h] BYREF

  v27 = 0;
  v29 = 0;
  v6 = 0;
  v33 = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    v8 = -2147024809;
    if ( !g_wppLevels )
      return v8;
    v9 = 406;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    v8 = -2147024809;
    if ( !g_wppLevels )
      return v8;
    v9 = 407;
    goto LABEL_4;
  }
  if ( (*(int (__fastcall **)(struct IMFSensorGroupIdInternal *, struct IMFAttributes **))(*(_QWORD *)a2 + 96LL))(
         a2,
         &v29) >= 0
    && ((int (__fastcall *)(struct IMFAttributes *, int *))v29->lpVtbl->GetCount)(v29, &v33) >= 0 )
  {
    if ( v33 )
    {
      v7 = MergeAttributes(v29, this[9], 0, 0);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( g_wppLevels )
        {
          v9 = 408;
LABEL_4:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v7);
          goto LABEL_74;
        }
        goto LABEL_74;
      }
    }
  }
  v7 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, unsigned __int16 **, _QWORD))(*(_QWORD *)a2 + 192LL))(
         a2,
         7,
         0,
         &v27,
         0);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( v27 )
      goto LABEL_54;
    v10 = this[9];
    pv = 0;
    LODWORD(pcbBufSize) = 0;
    lpVtbl = v10->lpVtbl;
    p_pv = &pv;
    v31 = 0;
    v32 = 1;
    v12 = ((unsigned int (__fastcall *)(struct IMFAttributes *, const IID *, __int64 *, __int64 *))lpVtbl->GetAllocatedString)(
            v10,
            &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
            &v31,
            &pcbBufSize) >> 31;
    if ( v32 )
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        p_pv,
        v31);
    v14 = L"Microsoft Camera Sensor Group";
    if ( (_BYTE)v12 )
    {
      pBuf = 0;
      if ( !*((_DWORD *)this + 26)
        || (*((int (__fastcall **)(struct IMFAttributesVtbl *, UINT8 **, __int64, _QWORD))this[12]->lpVtbl->QueryInterface
            + 7))(
             this[12]->lpVtbl,
             &pBuf,
             v13,
             0) < 0
        || (v6 = 1,
            v15 = *(_QWORD *)pBuf,
            p_pv = &pv,
            v31 = 0,
            v32 = 1,
            v16 = 0,
            (*(int (__fastcall **)(UINT8 *, const IID *, __int64 *, __int64 *))(v15 + 104))(
              pBuf,
              &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
              &v31,
              &pcbBufSize) < 0) )
      {
        v16 = 1;
      }
      if ( (v6 & 1) != 0 )
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&p_pv);
      if ( v16 )
      {
        v17 = L"Microsoft Camera Sensor Group";
        v18 = 0x7FFFFFFF;
        do
        {
          if ( !*v17 )
            break;
          ++v17;
          --v18;
        }
        while ( v18 );
        v8 = v18 == 0 ? 0x80070057 : 0;
        if ( !v18 )
        {
          pcbBufSize = 0;
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              410,
              &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
              this,
              -2147024809);
          if ( pBuf )
            (*(void (__fastcall **)(UINT8 *))(*(_QWORD *)pBuf + 16LL))(pBuf);
          goto LABEL_44;
        }
        pcbBufSize = 0x7FFFFFFF - v18;
      }
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pBuf);
    }
    v19 = pcbBufSize + 1;
    LODWORD(pcbBufSize) = pcbBufSize + 1;
    if ( pv )
      v14 = (const unsigned __int16 *)pv;
    v20 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, unsigned __int16 **, _QWORD))(*(_QWORD *)a2 + 192LL))(
            a2,
            7,
            (unsigned int)(2 * v19),
            &v27,
            0);
    v8 = v20;
    if ( v20 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_44;
      v21 = 411;
      goto LABEL_39;
    }
    v20 = StringCchCopyW(v27, (unsigned int)pcbBufSize, v14);
    v8 = v20;
    if ( v20 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_44:
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_74;
      }
      v21 = 412;
LABEL_39:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v20);
      goto LABEL_44;
    }
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        413,
        (unsigned int)&WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
        (_DWORD)this,
        (__int64)v27);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v27 )
    {
LABEL_54:
      v7 = ((__int64 (__fastcall *)(struct IMFAttributes *, const IID *))this[9]->lpVtbl->SetString)(
             this[9],
             &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( g_wppLevels )
        {
          v9 = 414;
          goto LABEL_4;
        }
        goto LABEL_74;
      }
      if ( (unsigned __int8)byte_18008D62D >= 8u )
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          415,
          (unsigned int)&WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
          (_DWORD)this,
          (__int64)v27);
    }
    v22 = this[9];
    v33 = 0;
    if ( ((int (__fastcall *)(struct IMFAttributes *, int *))v22->lpVtbl->GetCount)(v22, &v33) >= 0 && v33 )
    {
      v23 = this[9];
      LODWORD(pcbBufSize) = 0;
      pBuf = 0;
      v7 = MFGetAttributesAsBlobSize(v23, (UINT32 *)&pcbBufSize);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( g_wppLevels )
        {
          v9 = 416;
          goto LABEL_4;
        }
        goto LABEL_74;
      }
      v7 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, UINT8 **, _QWORD))(*(_QWORD *)a2 + 192LL))(
             a2,
             5,
             (unsigned int)pcbBufSize,
             &pBuf,
             0);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( g_wppLevels )
        {
          v9 = 417;
          goto LABEL_4;
        }
        goto LABEL_74;
      }
      v7 = MFGetAttributesAsBlob(this[9], pBuf, pcbBufSize);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( g_wppLevels )
        {
          v9 = 418;
          goto LABEL_4;
        }
        goto LABEL_74;
      }
      v24 = pcbBufSize;
      *((_DWORD *)a3 + 20) = pcbBufSize;
    }
    else
    {
      *((_DWORD *)a3 + 20) = 0;
      v24 = 0;
    }
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 419, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v24);
    goto LABEL_74;
  }
  if ( g_wppLevels )
  {
    v9 = 409;
    goto LABEL_4;
  }
LABEL_74:
  if ( v29 )
    ((void (__fastcall *)(struct IMFAttributes *))v29->lpVtbl->Release)(v29);
  return v8;
}

```

## disassembly

```asm
0x1800185e4  mov     [rsp-38h+arg_0], rbx
0x1800185e9  push    rbp
0x1800185ea  push    rsi
0x1800185eb  push    rdi
0x1800185ec  push    r12
0x1800185ee  push    r13
0x1800185f0  push    r14
0x1800185f2  push    r15
0x1800185f4  mov     rbp, rsp
0x1800185f7  sub     rsp, 70h
0x1800185fb  xor     r12d, r12d
0x1800185fe  mov     r13, r8
0x180018601  mov     [rbp+arg_8], r12d
0x180018605  mov     r14, rdx
0x180018608  mov     [rbp+var_38], r12
0x18001860c  mov     rdi, rcx
0x18001860f  mov     [rbp+var_28], r12
0x180018613  mov     r15d, r12d
0x180018616  mov     [rbp+arg_8], r12d
0x18001861a  test    rdx, rdx
0x18001861d  jnz     short loc_18001865B
0x18001861f  mov     eax, 80070057h
0x180018624  mov     ebx, eax
0x180018626  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001862d  jb      loc_180018B18
0x180018633  mov     edx, 196h
0x180018638  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x18001863f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018646  mov     r9, rdi
0x180018649  mov     dword ptr [rsp+70h+var_50], eax
0x18001864d  mov     rcx, [rcx+10h]
0x180018651  call    WPP_SF_qD
0x180018656  jmp     loc_180018B03
0x18001865b  test    r13, r13
0x18001865e  jnz     short loc_18001867B
0x180018660  mov     eax, 80070057h
0x180018665  mov     ebx, eax
0x180018667  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001866e  jb      loc_180018B18
0x180018674  mov     edx, 197h
0x180018679  jmp     short loc_180018638
0x18001867b  mov     rax, [rdx]
0x18001867e  mov     rcx, r14
0x180018681  lea     rdx, [rbp+var_28]
0x180018685  mov     rax, [rax+60h]
0x180018689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001868e  test    eax, eax
0x180018690  js      short loc_1800186E3
0x180018692  mov     rcx, [rbp+var_28]
0x180018696  lea     rdx, [rbp+arg_8]
0x18001869a  mov     rax, [rcx]
0x18001869d  mov     rax, [rax+0F0h]
0x1800186a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186a9  test    eax, eax
0x1800186ab  js      short loc_1800186E3
0x1800186ad  cmp     [rbp+arg_8], r12d
0x1800186b1  jbe     short loc_1800186E3
0x1800186b3  mov     rdx, [rdi+48h]; struct IMFAttributes *
0x1800186b7  xor     r9d, r9d; struct IMFAttributes **
0x1800186ba  mov     rcx, [rbp+var_28]; struct IMFAttributes *
0x1800186be  xor     r8d, r8d; bool
0x1800186c1  call    ?MergeAttributes@@YAJPEAUIMFAttributes@@0_NPEAPEAU1@@Z; MergeAttributes(IMFAttributes *,IMFAttributes *,bool,IMFAttributes * *)
0x1800186c6  mov     ebx, eax
0x1800186c8  test    eax, eax
0x1800186ca  jns     short loc_1800186E3
0x1800186cc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800186d3  jb      loc_180018B03
0x1800186d9  mov     edx, 198h
0x1800186de  jmp     loc_180018638
0x1800186e3  mov     rax, [r14]
0x1800186e6  lea     r9, [rbp+var_38]
0x1800186ea  xor     r8d, r8d
0x1800186ed  mov     [rsp+70h+var_50], r12
0x1800186f2  mov     rcx, r14
0x1800186f5  mov     rax, [rax+0C0h]
0x1800186fc  lea     edx, [r8+7]
0x180018700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018705  mov     ebx, eax
0x180018707  test    eax, eax
0x180018709  jns     short loc_180018722
0x18001870b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018712  jb      loc_180018B03
0x180018718  mov     edx, 199h
0x18001871d  jmp     loc_180018638
0x180018722  mov     r8, [rbp+var_38]
0x180018726  lea     rsi, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x18001872d  test    r8, r8
0x180018730  jnz     loc_180018996
0x180018736  mov     rcx, [rdi+48h]
0x18001873a  lea     rdx, [rbp+pv]
0x18001873e  mov     [rbp+pv], r12
0x180018742  lea     r9, [rbp+pcbBufSize]
0x180018746  mov     dword ptr [rbp+pcbBufSize], r12d
0x18001874a  lea     r8, [rbp+var_18]
0x18001874e  mov     rax, [rcx]
0x180018751  mov     [rbp+var_20], rdx
0x180018755  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME
0x18001875c  mov     [rbp+var_18], r12
0x180018760  mov     [rbp+var_10], 1
0x180018764  mov     rax, [rax+68h]
0x180018768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001876d  mov     ebx, eax
0x18001876f  shr     ebx, 1Fh
0x180018772  cmp     [rbp+var_10], r12b
0x180018776  jz      short loc_180018785
0x180018778  mov     rdx, [rbp+var_18]
0x18001877c  mov     rcx, [rbp+var_20]
0x180018780  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180018785  xor     r9d, r9d
0x180018788  lea     r12, aMicrosoftCamer; "Microsoft Camera Sensor Group"
0x18001878f  test    bl, bl
0x180018791  jz      loc_18001885A
0x180018797  mov     [rbp+pBuf], r9
0x18001879b  cmp     [rdi+68h], r9d
0x18001879f  jz      short loc_1800187FC
0x1800187a1  mov     rax, [rdi+60h]
0x1800187a5  lea     rdx, [rbp+pBuf]
0x1800187a9  mov     rcx, [rax]
0x1800187ac  mov     rax, [rcx]
0x1800187af  mov     rax, [rax+38h]
0x1800187b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187b8  xor     r9d, r9d
0x1800187bb  test    eax, eax
0x1800187bd  js      short loc_1800187FC
0x1800187bf  mov     rcx, [rbp+pBuf]
0x1800187c3  lea     rdx, [rbp+pv]
0x1800187c7  lea     r15d, [r9+1]
0x1800187cb  lea     r8, [rbp+var_18]
0x1800187cf  mov     rax, [rcx]
0x1800187d2  mov     [rbp+var_20], rdx
0x1800187d6  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME
0x1800187dd  mov     [rbp+var_18], r9
0x1800187e1  lea     r9, [rbp+pcbBufSize]
0x1800187e5  mov     [rbp+var_10], 1
0x1800187e9  mov     rax, [rax+68h]
0x1800187ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187f2  xor     r9d, r9d
0x1800187f5  mov     bl, r9b
0x1800187f8  test    eax, eax
0x1800187fa  jns     short loc_1800187FE
0x1800187fc  mov     bl, 1
0x1800187fe  test    r15b, 1
0x180018802  jz      short loc_18001880D
0x180018804  lea     rcx, [rbp+var_20]
0x180018808  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18001880d  xor     r8d, r8d
0x180018810  test    bl, bl
0x180018812  jz      short loc_18001884E
0x180018814  mov     edx, 7FFFFFFFh
0x180018819  mov     rax, r12
0x18001881c  mov     ecx, edx
0x18001881e  cmp     [rax], r8w
0x180018822  jz      short loc_18001882E
0x180018824  add     rax, 2
0x180018828  sub     rcx, 1
0x18001882c  jnz     short loc_18001881E
0x18001882e  mov     rax, rcx
0x180018831  neg     rax
0x180018834  sbb     ebx, ebx
0x180018836  not     ebx
0x180018838  and     ebx, 80070057h
0x18001883e  test    rcx, rcx
0x180018841  jz      loc_1800188C7
0x180018847  sub     rdx, rcx
0x18001884a  mov     [rbp+pcbBufSize], rdx
0x18001884e  lea     rcx, [rbp+pBuf]
0x180018852  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180018857  xor     r9d, r9d
0x18001885a  mov     rax, [rbp+pv]
0x18001885e  mov     edx, 7
0x180018863  mov     r8d, dword ptr [rbp+pcbBufSize]
0x180018867  mov     rcx, r14
0x18001886a  inc     r8d
0x18001886d  mov     [rsp+70h+var_50], r9
0x180018872  test    rax, rax
0x180018875  mov     dword ptr [rbp+pcbBufSize], r8d
0x180018879  lea     r9, [rbp+var_38]
0x18001887d  cmovnz  r12, rax
0x180018881  mov     rax, [r14]
0x180018884  add     r8d, r8d
0x180018887  mov     rax, [rax+0C0h]
0x18001888e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018893  mov     ebx, eax
0x180018895  test    eax, eax
0x180018897  jns     loc_180018923
0x18001889d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800188a4  jb      short loc_18001890B
0x1800188a6  mov     edx, 19Bh
0x1800188ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800188b2  mov     r9, rdi
0x1800188b5  mov     r8, rsi
0x1800188b8  mov     dword ptr [rsp+70h+var_50], eax
0x1800188bc  mov     rcx, [rcx+10h]
0x1800188c0  call    WPP_SF_qD
0x1800188c5  jmp     short loc_18001890B
0x1800188c7  xor     r12d, r12d
0x1800188ca  mov     [rbp+pcbBufSize], r12
0x1800188ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800188d5  jb      short loc_1800188F6
0x1800188d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800188de  mov     edx, 19Ah
0x1800188e3  mov     r9, rdi
0x1800188e6  mov     dword ptr [rsp+70h+var_50], ebx
0x1800188ea  mov     r8, rsi
0x1800188ed  mov     rcx, [rcx+10h]
0x1800188f1  call    WPP_SF_qD
0x1800188f6  mov     rcx, [rbp+pBuf]
0x1800188fa  test    rcx, rcx
0x1800188fd  jz      short loc_18001890B
0x1800188ff  mov     rax, [rcx]
0x180018902  mov     rax, [rax+10h]
0x180018906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001890b  mov     rcx, [rbp+pv]; pv
0x18001890f  test    rcx, rcx
0x180018912  jz      loc_180018B03
0x180018918  call    cs:__imp_CoTaskMemFree
0x18001891e  jmp     loc_180018B03
0x180018923  mov     edx, dword ptr [rbp+pcbBufSize]; unsigned __int64
0x180018926  mov     r8, r12; unsigned __int16 *
0x180018929  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x18001892d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018932  xor     r12d, r12d
0x180018935  mov     ebx, eax
0x180018937  test    eax, eax
0x180018939  jns     short loc_18001894E
0x18001893b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018942  jb      short loc_18001890B
0x180018944  mov     edx, 19Ch
0x180018949  jmp     loc_1800188AB
0x18001894e  cmp     cs:byte_18008D62D, 8
0x180018955  jb      short loc_18001897E
0x180018957  mov     rcx, cs:WPP_GLOBAL_Control
0x18001895e  mov     edx, 19Dh
0x180018963  mov     rax, [rbp+var_38]
0x180018967  mov     r9, rdi
0x18001896a  mov     r8, rsi
0x18001896d  mov     [rsp+70h+var_50], rax
0x180018972  mov     rcx, [rcx+0D8h]
0x180018979  call    WPP_SF_qS
0x18001897e  mov     rcx, [rbp+pv]; pv
0x180018982  test    rcx, rcx
0x180018985  jz      short loc_18001898D
0x180018987  call    cs:__imp_CoTaskMemFree
0x18001898d  mov     r8, [rbp+var_38]
0x180018991  test    r8, r8
0x180018994  jz      short loc_180018A00
0x180018996  mov     rcx, [rdi+48h]
0x18001899a  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME
0x1800189a1  mov     rax, [rcx]
0x1800189a4  mov     rax, [rax+0C8h]
0x1800189ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189b0  mov     ebx, eax
0x1800189b2  test    eax, eax
0x1800189b4  jns     short loc_1800189D0
0x1800189b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800189bd  jb      loc_180018B03
0x1800189c3  mov     edx, 19Eh
0x1800189c8  mov     r8, rsi
0x1800189cb  jmp     loc_18001863F
0x1800189d0  cmp     cs:byte_18008D62D, 8
0x1800189d7  jb      short loc_180018A00
0x1800189d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189e0  mov     edx, 19Fh
0x1800189e5  mov     rax, [rbp+var_38]
0x1800189e9  mov     r9, rdi
0x1800189ec  mov     r8, rsi
0x1800189ef  mov     [rsp+70h+var_50], rax
0x1800189f4  mov     rcx, [rcx+0D8h]
0x1800189fb  call    WPP_SF_qS
0x180018a00  mov     rcx, [rdi+48h]
0x180018a04  lea     rdx, [rbp+arg_8]
0x180018a08  mov     [rbp+arg_8], r12d
0x180018a0c  mov     rax, [rcx]
0x180018a0f  mov     rax, [rax+0F0h]
0x180018a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a1b  test    eax, eax
0x180018a1d  js      loc_180018AD1
0x180018a23  cmp     [rbp+arg_8], r12d
0x180018a27  jbe     loc_180018AD1
0x180018a2d  mov     rcx, [rdi+48h]; pAttributes
0x180018a31  lea     rdx, [rbp+pcbBufSize]; pcbBufSize
0x180018a35  mov     dword ptr [rbp+pcbBufSize], r12d
0x180018a39  mov     [rbp+pBuf], r12
0x180018a3d  call    cs:__imp_MFGetAttributesAsBlobSize
0x180018a43  mov     ebx, eax
0x180018a45  test    eax, eax
0x180018a47  jns     short loc_180018A60
0x180018a49  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018a50  jb      loc_180018B03
0x180018a56  mov     edx, 1A0h
0x180018a5b  jmp     loc_1800189C8
0x180018a60  mov     rax, [r14]
0x180018a63  lea     r9, [rbp+pBuf]
0x180018a67  mov     r8d, dword ptr [rbp+pcbBufSize]
0x180018a6b  mov     edx, 5
0x180018a70  mov     rcx, r14
0x180018a73  mov     [rsp+70h+var_50], r12
0x180018a78  mov     rax, [rax+0C0h]
0x180018a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a84  mov     ebx, eax
  ... truncated ...
```
