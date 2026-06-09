# FSPinInfo::UpdateMuxPinInformation(IMFAttributes *)

- ea: `0x18008db58`
- end: `0x18008e24e`
- name: `?UpdateMuxPinInformation@FSPinInfo@@IEAAJPEAUIMFAttributes@@@Z`
- size: `1782`
- prototype: `__int64 __fastcall(struct IFSMemory **this, struct IMFAttributes *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008a734`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x18000a4a8`
- `0x18000ad10`
- `0x18004ee30`
- `0x1800627bc`
- `0x18006299c`
- `0x180062f0c`
- `0x180063098`
- `0x180064764`
- `0x1800648a4`
- `0x18006b99c`
- `0x18006d43c`
- `0x18008db58`
- `0x18008ec20`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateMuxStreamMediaType` at `0x18008e039`
- `MFPlat!MFCreateMuxStreamMediaType` at `0x18008e039`
- `MFPlat!MFCreateCollection` at `0x18008df7d`
- `MFPlat!MFCreateCollection` at `0x18008df7d`
- `MFPlat!MFCreateAttributes` at `0x18008dc9b`
- `MFPlat!MFCreateAttributes` at `0x18008dc9b`

## string_xrefs

- `0x18008e172`: `config(%u/%u),cfg=0x%I64X`

## pseudocode

```c
__int64 __fastcall FSPinInfo::UpdateMuxPinInformation(struct IFSMemory **this, struct IMFAttributes *a2)
{
  struct IMFAttributesVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetUnknown)(IMFAttributes *, const GUID *const, const IID *const, LPVOID *); // rax
  unsigned int v6; // ebx
  int FSMemory; // eax
  __int64 v8; // rdx
  unsigned int i; // r15d
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, _QWORD, IMFAttributes **); // rbx
  HRESULT v12; // eax
  struct IFSMemory **v13; // rdi
  unsigned int *v14; // rbx
  int v15; // eax
  struct IFSMemory *v16; // rbx
  unsigned int ShareMode; // eax
  struct IFSMemory **v18; // rdi
  __int64 v19; // rbx
  unsigned int v20; // eax
  __int64 v21; // rcx
  unsigned int v22; // r12d
  unsigned int j; // edi
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  bool v29; // cf
  int v30; // edx
  int v31; // r8d
  struct IFSMemory *v32; // r14
  __int64 v33; // rcx
  unsigned int v34; // edi
  unsigned int v35; // r15d
  __int64 v36; // r8
  __int64 v37; // r9
  unsigned int v38; // edi
  unsigned int v39; // eax
  unsigned int v40; // r15d
  __int64 v41; // r8
  __int64 v42; // rax
  IMFAttributes *ppMFAttributes; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v45; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v46; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v47; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+68h] [rbp-98h] BYREF
  __int64 v49; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+78h] [rbp-88h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h] BYREF
  int v52; // [rsp+88h] [rbp-78h]
  __int64 v53; // [rsp+8Ch] [rbp-74h]
  char v54[272]; // [rsp+A0h] [rbp-60h] BYREF

  lpVtbl = a2->lpVtbl;
  v47 = 0;
  v45 = 0;
  GetUnknown = lpVtbl->GetUnknown;
  v51 = 0;
  v6 = 0;
  v53 = 0;
  v52 = 0;
  v49 = 0;
  v48 = 0;
  v50 = 0;
  if ( ((int (__fastcall *)(struct IMFAttributes *, void *, GUID *, __int64 *))GetUnknown)(
         a2,
         &MF_DEVICESTREAM_MULTIPLEXED_MANAGER,
         &GUID_ce8bd576_e440_43b3_be34_1e53f565f7e8,
         &v50) >= 0 )
  {
    v46 = 0;
    FSMemory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v50 + 24LL))(v50, &v47);
    v6 = FSMemory;
    if ( FSMemory >= 0 )
    {
      for ( i = 0; i < v47; ++i )
      {
        v10 = v50;
        ppMFAttributes = 0;
        v11 = *(int (__fastcall **)(__int64, _QWORD, IMFAttributes **))(*(_QWORD *)v50 + 32LL);
        wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
        if ( v11(v10, i, &ppMFAttributes) >= 0 )
        {
          ((void (__fastcall *)(IMFAttributes *, const IID *))ppMFAttributes->lpVtbl->DeleteItem)(
            ppMFAttributes,
            &MF_DEVICESTREAM_EXTENSION_PLUGIN_CLSID);
          ((void (__fastcall *)(IMFAttributes *, const IID *))ppMFAttributes->lpVtbl->DeleteItem)(
            ppMFAttributes,
            &MF_DEVICESTREAM_EXTENSION_PLUGIN_CONNECTION_POINT);
          ((void (__fastcall *)(IMFAttributes *, void *))ppMFAttributes->lpVtbl->DeleteItem)(
            ppMFAttributes,
            &MF_DEVICESTREAM_ATTRIBUTE_PLUGIN_ENABLED);
        }
        else
        {
          wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
          v12 = MFCreateAttributes(&ppMFAttributes, 1u);
          v6 = v12;
          if ( v12 < 0 )
          {
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                177,
                &WPP_d3b387ac0f4739244cd24a2364c9c9a7_Traceguids,
                this,
                v12);
LABEL_12:
            wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
            goto LABEL_74;
          }
        }
        if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add(&v51, ppMFAttributes) )
        {
          v6 = -2147024882;
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              178,
              &WPP_d3b387ac0f4739244cd24a2364c9c9a7_Traceguids,
              this,
              -2147024882);
          goto LABEL_12;
        }
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
      }
      FSMemory = ((__int64 (__fastcall *)(struct IMFAttributes *, void *))a2->lpVtbl->SetUINT32)(
                   a2,
                   &MF_DEVICESTREAM_FSATTRIB_MUXEDSTREAM);
      v6 = FSMemory;
      if ( FSMemory >= 0 )
      {
        FSMemory = FSSerializeAttributeArraySize(&v51, (int *)&v45);
        v6 = FSMemory;
        if ( FSMemory >= 0 )
        {
          v13 = this + 45;
          wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(this + 45);
          FSMemory = FSMemory::CreateFSMemory(v45, 0, this + 45);
          v6 = FSMemory;
          if ( FSMemory >= 0 )
          {
            v14 = (unsigned int *)(*(__int64 (__fastcall **)(struct IFSMemory *))(*(_QWORD *)*v13 + 24LL))(*v13);
            v15 = (*(__int64 (__fastcall **)(struct IFSMemory *))(*(_QWORD *)*v13 + 32LL))(*v13);
            FSMemory = FSSerializeAttributeArray(&v51, v15, v14, &v45);
            v6 = FSMemory;
            if ( FSMemory >= 0 )
            {
              v16 = this[9];
              ShareMode = FSSourceInfo::GetShareMode(this[22]);
              FSMemory = FSClientContext::InternalGetAllPinMediaTypes(v16, ShareMode, this + 46);
              v6 = FSMemory;
              if ( FSMemory >= 0 )
              {
                FSMemory = FSSerializeArrayOfMediaTypeArrayGetSize(this + 46, &v46);
                v6 = FSMemory;
                if ( FSMemory >= 0 )
                {
                  v18 = this + 50;
                  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(this + 50);
                  FSMemory = FSMemory::CreateFSMemory(v46, 0, this + 50);
                  v6 = FSMemory;
                  if ( FSMemory >= 0 )
                  {
                    v19 = (*(__int64 (__fastcall **)(struct IFSMemory *))(*(_QWORD *)*v18 + 24LL))(*v18);
                    v20 = (*(__int64 (__fastcall **)(struct IFSMemory *))(*(_QWORD *)*v18 + 32LL))(*v18);
                    FSMemory = FSSerializeArrayOfMediaTypeArray(this + 46, v20, v19, &v46);
                    v6 = FSMemory;
                    if ( FSMemory >= 0 )
                    {
                      v21 = v48;
                      v48 = 0;
                      if ( v21 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
                      FSMemory = MFCreateCollection(&v48);
                      v6 = FSMemory;
                      if ( FSMemory >= 0 )
                      {
                        v22 = *((_DWORD *)this + 94);
                        for ( j = 0; j < v22; ++j )
                        {
                          v24 = *((_QWORD *)this[46] + j);
                          v25 = *(unsigned int *)(v24 + 40);
                          if ( (unsigned int)v25 < *(_DWORD *)(v24 + 24) )
                          {
                            v26 = *(_QWORD *)(*(_QWORD *)(v24 + 16) + 8 * v25);
                            v27 = 1;
                          }
                          else
                          {
                            v26 = 0;
                            v27 = 0;
                          }
                          FSMemory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 40LL))(
                                       v48,
                                       v26 & -(__int64)(v27 != 0));
                          v6 = FSMemory;
                          if ( FSMemory < 0 )
                          {
                            if ( !g_wppLevels )
                              goto LABEL_74;
                            v8 = 188;
                            goto LABEL_5;
                          }
                        }
                        v28 = v49;
                        v49 = 0;
                        if ( v28 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                        FSMemory = MFCreateMuxStreamMediaType(v48, &v49);
                        v6 = FSMemory;
                        if ( FSMemory >= 0 )
                        {
                          wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(this + 49);
                          FSMemory = FSMuxMediaType::CreateMuxMediaType(this + 46, v49, this + 49);
                          v6 = FSMemory;
                          if ( FSMemory >= 0 )
                          {
                            v29 = (unsigned __int8)byte_18010EC4D < 0x10u;
                            *((_DWORD *)this + 88) = v47;
                            if ( !v29 )
                            {
                              memset_0(v54, 0, 0x104u);
                              v32 = this[49];
                              v33 = 0;
                              v34 = 0;
                              v35 = *((_DWORD *)v32 + 18);
                              while ( v34 < v35 )
                              {
                                v36 = *((_QWORD *)v32 + 10);
                                v37 = 2LL * v34;
                                ppMFAttributes = 0;
                                if ( (int)StringCchPrintfExA(
                                            &v54[v33],
                                            260 - v33,
                                            0,
                                            (unsigned __int64 *)&ppMFAttributes,
                                            0,
                                            "curmt(%u/%u),strmid=%u,mtidx=%u",
                                            ++v34,
                                            v35,
                                            *(_DWORD *)(v36 + 8 * v37),
                                            *(_DWORD *)(v36 + 8 * v37 + 4)) < 0 )
                                  goto LABEL_72;
                                v33 = 260LL - (_QWORD)ppMFAttributes;
                              }
                              v38 = *((_DWORD *)v32 + 8);
                              v39 = 0;
                              if ( v38 )
                              {
                                do
                                {
                                  v40 = v39 + 1;
                                  v41 = v39;
                                  v42 = *((_QWORD *)v32 + 5);
                                  ppMFAttributes = 0;
                                  if ( (int)StringCchPrintfExA(
                                              &v54[v33],
                                              260 - v33,
                                              0,
                                              (unsigned __int64 *)&ppMFAttributes,
                                              0,
                                              "config(%u/%u),cfg=0x%I64X",
                                              v40,
                                              v38,
                                              *(_QWORD *)(v42 + 8 * v41)) < 0 )
                                    break;
                                  v39 = v40;
                                  v33 = 260LL - (_QWORD)ppMFAttributes;
                                }
                                while ( v40 < v38 );
                              }
LABEL_72:
                              if ( (unsigned __int8)byte_18010EC4D >= 8u )
                                WPP_SF_qqDDDDs(
                                  *((_QWORD *)WPP_GLOBAL_Control + 27),
                                  v30,
                                  v31,
                                  (_DWORD)this,
                                  (char)this[26],
                                  *((_DWORD *)this + 88),
                                  *((_DWORD *)this + 30),
                                  *((_DWORD *)this + 22),
                                  *((_DWORD *)this + 56),
                                  (__int64)v54);
                            }
                            goto LABEL_74;
                          }
                          if ( !g_wppLevels )
                            goto LABEL_74;
                          v8 = 190;
                        }
                        else
                        {
                          if ( !g_wppLevels )
                            goto LABEL_74;
                          v8 = 189;
                        }
                      }
                      else
                      {
                        if ( !g_wppLevels )
                          goto LABEL_74;
                        v8 = 187;
                      }
                    }
                    else
                    {
                      if ( !g_wppLevels )
                        goto LABEL_74;
                      v8 = 186;
                    }
                  }
                  else
                  {
                    if ( !g_wppLevels )
                      goto LABEL_74;
                    v8 = 185;
                  }
                }
                else
                {
                  if ( !g_wppLevels )
                    goto LABEL_74;
                  v8 = 184;
                }
              }
              else
              {
                if ( !g_wppLevels )
                  goto LABEL_74;
                v8 = 183;
              }
            }
            else
            {
              if ( !g_wppLevels )
                goto LABEL_74;
              v8 = 182;
            }
          }
          else
          {
            if ( !g_wppLevels )
              goto LABEL_74;
            v8 = 181;
          }
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_74;
          v8 = 180;
        }
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_74;
        v8 = 179;
      }
      goto LABEL_5;
    }
    if ( g_wppLevels )
    {
      v8 = 176;
LABEL_5:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        &WPP_d3b387ac0f4739244cd24a2364c9c9a7_Traceguids,
        this,
        FSMemory);
    }
  }
LABEL_74:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v48);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v49);
  CTUnkArray<IFSProcessActivity>::~CTUnkArray<IFSProcessActivity>(&v51);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v50);
  return v6;
}

```

## disassembly

```asm
0x18008db58  mov     [rsp-8+arg_10], rbx
0x18008db5d  push    rbp
0x18008db5e  push    rsi
0x18008db5f  push    rdi
0x18008db60  push    r12
0x18008db62  push    r13
0x18008db64  push    r14
0x18008db66  push    r15
0x18008db68  lea     rbp, [rsp-0C0h]
0x18008db70  sub     rsp, 1C0h
0x18008db77  mov     rax, cs:__security_cookie
0x18008db7e  xor     rax, rsp
0x18008db81  mov     [rbp+0F0h+var_40], rax
0x18008db88  mov     rax, [rdx]
0x18008db8b  lea     r9, [rsp+1F0h+var_178]
0x18008db90  xor     r13d, r13d
0x18008db93  lea     r8, _GUID_ce8bd576_e440_43b3_be34_1e53f565f7e8
0x18008db9a  mov     r12, rdx
0x18008db9d  mov     [rsp+1F0h+var_190], r13d
0x18008dba2  mov     rsi, rcx
0x18008dba5  mov     [rsp+1F0h+var_198], r13d
0x18008dbaa  mov     rax, [rax+88h]
0x18008dbb1  lea     rdx, MF_DEVICESTREAM_MULTIPLEXED_MANAGER
0x18008dbb8  mov     rcx, r12
0x18008dbbb  mov     [rbp+0F0h+var_170], r13
0x18008dbbf  mov     ebx, r13d
0x18008dbc2  mov     [rbp+0F0h+var_164], r13
0x18008dbc6  mov     [rbp+0F0h+var_168], r13d
0x18008dbca  mov     [rsp+1F0h+var_180], r13
0x18008dbcf  mov     [rsp+1F0h+var_188], r13
0x18008dbd4  mov     [rsp+1F0h+var_178], r13
0x18008dbd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dbde  test    eax, eax
0x18008dbe0  js      loc_18008E1FB
0x18008dbe6  mov     rcx, [rsp+1F0h+var_178]
0x18008dbeb  lea     rdx, [rsp+1F0h+var_190]
0x18008dbf0  mov     [rsp+1F0h+var_194], r13d
0x18008dbf5  mov     rax, [rcx]
0x18008dbf8  mov     rax, [rax+18h]
0x18008dbfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dc01  mov     ebx, eax
0x18008dc03  test    eax, eax
0x18008dc05  jns     short loc_18008DC40
0x18008dc07  lea     r14d, [r13+1]
0x18008dc0b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18008dc12  jb      loc_18008E1FB
0x18008dc18  mov     edx, 0B0h
0x18008dc1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008dc24  lea     r8, WPP_d3b387ac0f4739244cd24a2364c9c9a7_Traceguids
0x18008dc2b  mov     r9, rsi
0x18008dc2e  mov     [rsp+1F0h+dwFlags], eax
0x18008dc32  mov     rcx, [rcx+10h]
0x18008dc36  call    WPP_SF_qD
0x18008dc3b  jmp     loc_18008E1FB
0x18008dc40  mov     r15d, r13d
0x18008dc43  mov     r14d, 1
0x18008dc49  mov     r8d, [rsp+1F0h+var_190]
0x18008dc4e  cmp     r15d, r8d
0x18008dc51  jnb     loc_18008DD7B
0x18008dc57  mov     rdi, [rsp+1F0h+var_178]
0x18008dc5c  lea     rcx, [rsp+1F0h+ppMFAttributes]
0x18008dc61  mov     [rsp+1F0h+ppMFAttributes], r13
0x18008dc66  mov     rax, [rdi]
0x18008dc69  mov     rbx, [rax+20h]
0x18008dc6d  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18008dc72  lea     r8, [rsp+1F0h+ppMFAttributes]
0x18008dc77  mov     edx, r15d
0x18008dc7a  mov     rcx, rdi
0x18008dc7d  mov     rax, rbx
0x18008dc80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dc85  test    eax, eax
0x18008dc87  jns     short loc_18008DCE6
0x18008dc89  lea     rcx, [rsp+1F0h+ppMFAttributes]
0x18008dc8e  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18008dc93  mov     edx, r14d; cInitialSize
0x18008dc96  lea     rcx, [rsp+1F0h+ppMFAttributes]; ppMFAttributes
0x18008dc9b  call    cs:__imp_MFCreateAttributes
0x18008dca1  mov     ebx, eax
0x18008dca3  test    eax, eax
0x18008dca5  jns     loc_18008DD37
0x18008dcab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18008dcb2  jb      short loc_18008DCD7
0x18008dcb4  mov     edx, 0B1h
0x18008dcb9  mov     [rsp+1F0h+dwFlags], eax
0x18008dcbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18008dcc4  lea     r8, WPP_d3b387ac0f4739244cd24a2364c9c9a7_Traceguids
0x18008dccb  mov     r9, rsi
0x18008dcce  mov     rcx, [rcx+10h]
0x18008dcd2  call    WPP_SF_qD
0x18008dcd7  lea     rcx, [rsp+1F0h+ppMFAttributes]; void *
0x18008dcdc  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18008dce1  jmp     loc_18008E1FB
0x18008dce6  mov     rcx, [rsp+1F0h+ppMFAttributes]
0x18008dceb  lea     rdx, MF_DEVICESTREAM_EXTENSION_PLUGIN_CLSID
0x18008dcf2  mov     rax, [rcx]
0x18008dcf5  mov     rax, [rax+98h]
0x18008dcfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dd01  mov     rcx, [rsp+1F0h+ppMFAttributes]
0x18008dd06  lea     rdx, MF_DEVICESTREAM_EXTENSION_PLUGIN_CONNECTION_POINT
0x18008dd0d  mov     rax, [rcx]
0x18008dd10  mov     rax, [rax+98h]
0x18008dd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dd1c  mov     rcx, [rsp+1F0h+ppMFAttributes]
0x18008dd21  lea     rdx, MF_DEVICESTREAM_ATTRIBUTE_PLUGIN_ENABLED
0x18008dd28  mov     rax, [rcx]
0x18008dd2b  mov     rax, [rax+98h]
0x18008dd32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dd37  mov     rdx, [rsp+1F0h+ppMFAttributes]
0x18008dd3c  lea     rcx, [rbp+0F0h+var_170]
0x18008dd40  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x18008dd45  test    eax, eax
0x18008dd47  jz      short loc_18008DD5B
0x18008dd49  lea     rcx, [rsp+1F0h+ppMFAttributes]; void *
0x18008dd4e  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18008dd53  add     r15d, r14d
0x18008dd56  jmp     loc_18008DC49
0x18008dd5b  mov     ebx, 8007000Eh
0x18008dd60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18008dd67  jb      loc_18008DCD7
0x18008dd6d  mov     edx, 0B2h
0x18008dd72  mov     [rsp+1F0h+dwFlags], ebx
0x18008dd76  jmp     loc_18008DCBD
0x18008dd7b  mov     rax, [r12]
0x18008dd7f  lea     rdx, MF_DEVICESTREAM_FSATTRIB_MUXEDSTREAM
0x18008dd86  mov     rcx, r12
0x18008dd89  mov     rax, [rax+0A8h]
0x18008dd90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dd95  mov     ebx, eax
0x18008dd97  test    eax, eax
0x18008dd99  jns     short loc_18008DDB2
0x18008dd9b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18008dda2  jb      loc_18008E1FB
0x18008dda8  mov     edx, 0B3h
0x18008ddad  jmp     loc_18008DC1D
0x18008ddb2  lea     rdx, [rsp+1F0h+var_198]
0x18008ddb7  lea     rcx, [rbp+0F0h+var_170]
0x18008ddbb  call    ?FSSerializeAttributeArraySize@@YAJAEAV?$CTUnkArray@UIMFAttributes@@@@PEAK@Z; FSSerializeAttributeArraySize(CTUnkArray<IMFAttributes> &,ulong *)
0x18008ddc0  mov     ebx, eax
0x18008ddc2  test    eax, eax
0x18008ddc4  jns     short loc_18008DDDD
0x18008ddc6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18008ddcd  jb      loc_18008E1FB
0x18008ddd3  mov     edx, 0B4h
0x18008ddd8  jmp     loc_18008DC1D
0x18008dddd  lea     rdi, [rsi+168h]
0x18008dde4  mov     rcx, rdi
0x18008dde7  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18008ddec  mov     ecx, [rsp+1F0h+var_198]; unsigned int
0x18008ddf0  mov     r8, rdi; struct IFSMemory **
0x18008ddf3  xor     edx, edx; unsigned __int8 *
0x18008ddf5  call    ?CreateFSMemory@FSMemory@@SAJKPEAEPEAPEAUIFSMemory@@@Z; FSMemory::CreateFSMemory(ulong,uchar *,IFSMemory * *)
0x18008ddfa  mov     ebx, eax
0x18008ddfc  test    eax, eax
0x18008ddfe  jns     short loc_18008DE17
0x18008de00  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18008de07  jb      loc_18008E1FB
0x18008de0d  mov     edx, 0B5h
0x18008de12  jmp     loc_18008DC1D
0x18008de17  mov     rcx, [rdi]
0x18008de1a  mov     rax, [rcx]
0x18008de1d  mov     rax, [rax+18h]
0x18008de21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008de26  mov     rcx, [rdi]
0x18008de29  mov     rbx, rax
0x18008de2c  mov     rdx, [rcx]
0x18008de2f  mov     rax, [rdx+20h]
0x18008de33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008de38  lea     r9, [rsp+1F0h+var_198]
0x18008de3d  mov     r8, rbx
0x18008de40  mov     edx, eax
0x18008de42  lea     rcx, [rbp+0F0h+var_170]
0x18008de46  call    ?FSSerializeAttributeArray@@YAJAEAV?$CTUnkArray@UIMFAttributes@@@@KPEAEPEAK@Z; FSSerializeAttributeArray(CTUnkArray<IMFAttributes> &,ulong,uchar *,ulong *)
0x18008de4b  mov     ebx, eax
0x18008de4d  test    eax, eax
0x18008de4f  jns     short loc_18008DE68
0x18008de51  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18008de58  jb      loc_18008E1FB
0x18008de5e  mov     edx, 0B6h
0x18008de63  jmp     loc_18008DC1D
0x18008de68  mov     rcx, [rsi+0B0h]
0x18008de6f  mov     rbx, [rsi+48h]
0x18008de73  call    ?GetShareMode@FSSourceInfo@@QEBA?AW4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@XZ; FSSourceInfo::GetShareMode(void)
0x18008de78  lea     r15, [rsi+170h]
0x18008de7f  mov     edx, eax
0x18008de81  mov     r8, r15
0x18008de84  mov     rcx, rbx
0x18008de87  call    ?InternalGetAllPinMediaTypes@FSClientContext@@IEAAJW4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@AEAV?$CTUnkArray@VFSMediaTypeArray@@@@@Z; FSClientContext::InternalGetAllPinMediaTypes(__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001,CTUnkArray<FSMediaTypeArray> &)
0x18008de8c  mov     ebx, eax
0x18008de8e  test    eax, eax
0x18008de90  jns     short loc_18008DEA9
0x18008de92  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18008de99  jb      loc_18008E1FB
0x18008de9f  mov     edx, 0B7h
0x18008dea4  jmp     loc_18008DC1D
0x18008dea9  lea     rdx, [rsp+1F0h+var_194]
0x18008deae  mov     rcx, r15
0x18008deb1  call    ?FSSerializeArrayOfMediaTypeArrayGetSize@@YAJAEAV?$CTUnkArray@VFSMediaTypeArray@@@@PEAK@Z; FSSerializeArrayOfMediaTypeArrayGetSize(CTUnkArray<FSMediaTypeArray> &,ulong *)
0x18008deb6  mov     ebx, eax
0x18008deb8  test    eax, eax
0x18008deba  jns     short loc_18008DED3
0x18008debc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18008dec3  jb      loc_18008E1FB
0x18008dec9  mov     edx, 0B8h
0x18008dece  jmp     loc_18008DC1D
0x18008ded3  lea     rdi, [rsi+190h]
0x18008deda  mov     rcx, rdi
0x18008dedd  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18008dee2  mov     ecx, [rsp+1F0h+var_194]; unsigned int
0x18008dee6  mov     r8, rdi; struct IFSMemory **
0x18008dee9  xor     edx, edx; unsigned __int8 *
0x18008deeb  call    ?CreateFSMemory@FSMemory@@SAJKPEAEPEAPEAUIFSMemory@@@Z; FSMemory::CreateFSMemory(ulong,uchar *,IFSMemory * *)
0x18008def0  mov     ebx, eax
0x18008def2  test    eax, eax
0x18008def4  jns     short loc_18008DF0D
0x18008def6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18008defd  jb      loc_18008E1FB
0x18008df03  mov     edx, 0B9h
0x18008df08  jmp     loc_18008DC1D
0x18008df0d  mov     rcx, [rdi]
0x18008df10  mov     rax, [rcx]
0x18008df13  mov     rax, [rax+18h]
0x18008df17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008df1c  mov     rcx, [rdi]
0x18008df1f  mov     rbx, rax
0x18008df22  mov     rdx, [rcx]
0x18008df25  mov     rax, [rdx+20h]
0x18008df29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008df2e  lea     r9, [rsp+1F0h+var_194]
0x18008df33  mov     r8, rbx
0x18008df36  mov     edx, eax
0x18008df38  mov     rcx, r15
0x18008df3b  call    ?FSSerializeArrayOfMediaTypeArray@@YAJAEAV?$CTUnkArray@VFSMediaTypeArray@@@@KPEAEPEAK@Z; FSSerializeArrayOfMediaTypeArray(CTUnkArray<FSMediaTypeArray> &,ulong,uchar *,ulong *)
0x18008df40  mov     ebx, eax
0x18008df42  test    eax, eax
0x18008df44  jns     short loc_18008DF5D
0x18008df46  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18008df4d  jb      loc_18008E1FB
0x18008df53  mov     edx, 0BAh
0x18008df58  jmp     loc_18008DC1D
0x18008df5d  mov     rcx, [rsp+1F0h+var_188]
0x18008df62  mov     [rsp+1F0h+var_188], r13
0x18008df67  test    rcx, rcx
0x18008df6a  jz      short loc_18008DF78
0x18008df6c  mov     rax, [rcx]
0x18008df6f  mov     rax, [rax+10h]
0x18008df73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008df78  lea     rcx, [rsp+1F0h+var_188]
0x18008df7d  call    cs:__imp_MFCreateCollection
0x18008df83  mov     ebx, eax
0x18008df85  test    eax, eax
0x18008df87  jns     short loc_18008DFA0
0x18008df89  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18008df90  jb      loc_18008E1FB
0x18008df96  mov     edx, 0BBh
0x18008df9b  jmp     loc_18008DC1D
0x18008dfa0  mov     r12d, [rsi+178h]
0x18008dfa7  mov     edi, r13d
0x18008dfaa  cmp     edi, r12d
0x18008dfad  jnb     short loc_18008E014
0x18008dfaf  mov     r9, [rsp+1F0h+var_188]
0x18008dfb4  mov     ecx, edi
0x18008dfb6  mov     rax, [r9]
0x18008dfb9  mov     r10, [rax+28h]
0x18008dfbd  mov     rax, [r15]
0x18008dfc0  mov     rdx, [rax+rcx*8]
0x18008dfc4  mov     eax, [rdx+28h]
0x18008dfc7  cmp     eax, [rdx+18h]
0x18008dfca  jb      short loc_18008DFD4
0x18008dfcc  mov     rcx, r13
0x18008dfcf  mov     eax, r13d
0x18008dfd2  jmp     short loc_18008DFDF
0x18008dfd4  mov     rdx, [rdx+10h]
0x18008dfd8  mov     rcx, [rdx+rax*8]
0x18008dfdc  mov     eax, r14d
0x18008dfdf  neg     eax
0x18008dfe1  mov     rax, r10
0x18008dfe4  sbb     rdx, rdx
0x18008dfe7  and     rdx, rcx
0x18008dfea  mov     rcx, r9
0x18008dfed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dff2  mov     ebx, eax
0x18008dff4  test    eax, eax
0x18008dff6  js      short loc_18008DFFD
0x18008dff8  add     edi, r14d
0x18008dffb  jmp     short loc_18008DFAA
0x18008dffd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18008e004  jb      loc_18008E1FB
0x18008e00a  mov     edx, 0BCh
0x18008e00f  jmp     loc_18008DC1D
0x18008e014  mov     rcx, [rsp+1F0h+var_180]
0x18008e019  mov     [rsp+1F0h+var_180], r13
0x18008e01e  test    rcx, rcx
0x18008e021  jz      short loc_18008E02F
0x18008e023  mov     rax, [rcx]
0x18008e026  mov     rax, [rax+10h]
0x18008e02a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e02f  mov     rcx, [rsp+1F0h+var_188]
0x18008e034  lea     rdx, [rsp+1F0h+var_180]
0x18008e039  call    cs:__imp_MFCreateMuxStreamMediaType
0x18008e03f  mov     ebx, eax
  ... truncated ...
```
