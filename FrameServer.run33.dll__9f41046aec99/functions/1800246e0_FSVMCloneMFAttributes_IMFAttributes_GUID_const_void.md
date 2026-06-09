# FSVMCloneMFAttributes(IMFAttributes *,_GUID const &,void * *)

- ea: `0x1800246e0`
- end: `0x180024a38`
- name: `?FSVMCloneMFAttributes@@YAJPEAUIMFAttributes@@AEBU_GUID@@PEAPEAX@Z`
- size: `856`
- prototype: `__int64 __fastcall(struct IMFAttributes *, const struct _GUID *, void **)`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d6d30`
- `0x1800d8350`
- `0x1800d8450`
- `0x1800d85c0`
- `0x1800d8e60`
- `0x1800dc150`
- `0x1800dc470`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x1800246e0`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180024979`
- `MFPlat!MFCreateAttributes` at `0x180024979`
- `MFPlat!MFCreateVideoMediaType` at `0x180024796`
- `MFPlat!MFCreateVideoMediaType` at `0x180024796`
- `MFPlat!MFCreateMediaType` at `0x180024884`
- `MFPlat!MFCreateMediaType` at `0x180024884`

## pseudocode

```c
__int64 __fastcall FSVMCloneMFAttributes(struct IMFAttributes *a1, const struct _GUID *a2, void **a3)
{
  unsigned int v6; // ebx
  const MFVIDEOFORMAT *v7; // rax
  HRESULT v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  struct IMFAttributesVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IMFAttributes *, const IID *const, void **); // rbx
  HRESULT v13; // eax
  __int64 v14; // rdx
  struct IMFAttributesVtbl *v15; // rax
  HRESULT v16; // eax
  __int64 v17; // rdx
  UINT32 v18; // ebx
  __int64 v20; // [rsp+30h] [rbp-10h] BYREF
  __int64 v21; // [rsp+38h] [rbp-8h] BYREF
  IMFVideoMediaType *ppIVideoMediaType; // [rsp+70h] [rbp+30h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+78h] [rbp+38h] BYREF

  v21 = 0;
  v20 = 0;
  if ( a3 )
  {
    v6 = 0;
    *a3 = 0;
    if ( !a1 )
      goto LABEL_45;
    if ( ((__int64 (__fastcall *)(struct IMFAttributes *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
           a1,
           &GUID_b99f381f_a8f9_47a2_a5af_ca3a225a3890,
           &v21) >= 0 )
    {
      ppIVideoMediaType = 0;
      v7 = (const MFVIDEOFORMAT *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 304LL))(v21);
      v8 = MFCreateVideoMediaType(v7, &ppIVideoMediaType);
      v6 = v8;
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, IMFVideoMediaType *))(*(_QWORD *)v21 + 256LL))(v21, ppIVideoMediaType);
        v6 = v8;
        if ( v8 >= 0 )
        {
          v8 = ((__int64 (__fastcall *)(IMFVideoMediaType *, const struct _GUID *, void **))ppIVideoMediaType->lpVtbl->QueryInterface)(
                 ppIVideoMediaType,
                 a2,
                 a3);
          v6 = v8;
          if ( v8 >= 0 || !g_wppLevels )
            goto LABEL_10;
          v9 = 77;
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_10;
          v9 = 76;
        }
      }
      else
      {
        if ( !g_wppLevels )
        {
LABEL_10:
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppIVideoMediaType);
          goto LABEL_45;
        }
        v9 = 75;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v8);
      goto LABEL_10;
    }
    v10 = v20;
    lpVtbl = a1->lpVtbl;
    v20 = 0;
    QueryInterface = lpVtbl->QueryInterface;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    if ( ((int (__fastcall *)(struct IMFAttributes *, GUID *, __int64 *))QueryInterface)(
           a1,
           &GUID_44ae0fa8_ea31_4109_8d2e_4cae4997c555,
           &v20) >= 0 )
    {
      ppIVideoMediaType = 0;
      v13 = MFCreateMediaType((IMFMediaType **)&ppIVideoMediaType);
      v6 = v13;
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, IMFVideoMediaType *))(*(_QWORD *)v20 + 256LL))(v20, ppIVideoMediaType);
        v6 = v13;
        if ( v13 >= 0 )
        {
          v13 = ((__int64 (__fastcall *)(IMFVideoMediaType *, const struct _GUID *, void **))ppIVideoMediaType->lpVtbl->QueryInterface)(
                  ppIVideoMediaType,
                  a2,
                  a3);
          v6 = v13;
          if ( v13 >= 0 || !g_wppLevels )
            goto LABEL_24;
          v14 = 80;
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_24;
          v14 = 79;
        }
      }
      else
      {
        if ( !g_wppLevels )
        {
LABEL_24:
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppIVideoMediaType);
          goto LABEL_45;
        }
        v14 = 78;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v13);
      goto LABEL_24;
    }
    v15 = a1->lpVtbl;
    ppMFAttributes = 0;
    LODWORD(ppIVideoMediaType) = 0;
    v16 = ((__int64 (__fastcall *)(struct IMFAttributes *, IMFVideoMediaType **))v15->GetCount)(a1, &ppIVideoMediaType);
    v6 = v16;
    if ( v16 >= 0 )
    {
      v18 = (unsigned int)ppIVideoMediaType;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
      v16 = MFCreateAttributes(&ppMFAttributes, v18);
      v6 = v16;
      if ( v16 >= 0 )
      {
        v16 = ((__int64 (__fastcall *)(struct IMFAttributes *, IMFAttributes *))a1->lpVtbl->CopyAllItems)(
                a1,
                ppMFAttributes);
        v6 = v16;
        if ( v16 >= 0 )
        {
          v16 = ((__int64 (__fastcall *)(IMFAttributes *, const struct _GUID *, void **))ppMFAttributes->lpVtbl->QueryInterface)(
                  ppMFAttributes,
                  a2,
                  a3);
          v6 = v16;
          if ( v16 >= 0 || !g_wppLevels )
            goto LABEL_44;
          v17 = 84;
          goto LABEL_43;
        }
        if ( g_wppLevels )
        {
          v17 = 83;
          goto LABEL_43;
        }
      }
      else if ( g_wppLevels )
      {
        v17 = 82;
        goto LABEL_43;
      }
    }
    else if ( g_wppLevels )
    {
      v17 = 81;
LABEL_43:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v16);
    }
LABEL_44:
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
    goto LABEL_45;
  }
  v6 = -2147467261;
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, -2147467261);
LABEL_45:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v20);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v21);
  return v6;
}

```

## disassembly

```asm
0x1800246e0  mov     [rsp-18h+arg_0], rbx
0x1800246e5  mov     [rsp-18h+arg_8], rsi
0x1800246ea  push    rbp
0x1800246eb  push    rdi
0x1800246ec  push    r14
0x1800246ee  mov     rbp, rsp
0x1800246f1  sub     rsp, 40h
0x1800246f5  mov     [rbp+var_8], 0
0x1800246fd  mov     rsi, r8
0x180024700  mov     [rbp+var_10], 0
0x180024708  mov     r14, rdx
0x18002470b  mov     rdi, rcx
0x18002470e  test    r8, r8
0x180024711  jnz     short loc_18002474C
0x180024713  mov     ebx, 80004003h
0x180024718  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002471f  jb      loc_180024A11
0x180024725  mov     rcx, cs:WPP_GLOBAL_Control
0x18002472c  lea     edx, [r8+4Ah]
0x180024730  xor     r9d, r9d
0x180024733  mov     [rsp+40h+var_20], ebx
0x180024737  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x18002473e  mov     rcx, [rcx+10h]
0x180024742  call    WPP_SF_qD
0x180024747  jmp     loc_180024A11
0x18002474c  xor     ebx, ebx
0x18002474e  mov     [r8], rbx
0x180024751  test    rdi, rdi
0x180024754  jz      loc_180024A11
0x18002475a  mov     rax, [rcx]
0x18002475d  lea     r8, [rbp+var_8]
0x180024761  lea     rdx, _GUID_b99f381f_a8f9_47a2_a5af_ca3a225a3890
0x180024768  mov     rax, [rax]
0x18002476b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024770  test    eax, eax
0x180024772  js      loc_180024837
0x180024778  mov     rcx, [rbp+var_8]
0x18002477c  mov     [rbp+ppIVideoMediaType], rbx
0x180024780  mov     rax, [rcx]
0x180024783  mov     rax, [rax+130h]
0x18002478a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002478f  lea     rdx, [rbp+ppIVideoMediaType]; ppIVideoMediaType
0x180024793  mov     rcx, rax; pVideoFormat
0x180024796  call    cs:__imp_MFCreateVideoMediaType
0x18002479c  mov     ebx, eax
0x18002479e  test    eax, eax
0x1800247a0  jns     short loc_1800247DC
0x1800247a2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800247a9  jb      short loc_1800247CE
0x1800247ab  mov     edx, 4Bh ; 'K'
0x1800247b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247b7  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x1800247be  xor     r9d, r9d
0x1800247c1  mov     [rsp+40h+var_20], eax
0x1800247c5  mov     rcx, [rcx+10h]
0x1800247c9  call    WPP_SF_qD
0x1800247ce  lea     rcx, [rbp+ppIVideoMediaType]; void *
0x1800247d2  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800247d7  jmp     loc_180024A11
0x1800247dc  mov     rcx, [rbp+var_8]
0x1800247e0  mov     rdx, [rbp+ppIVideoMediaType]
0x1800247e4  mov     rax, [rcx]
0x1800247e7  mov     rax, [rax+100h]
0x1800247ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247f3  mov     ebx, eax
0x1800247f5  test    eax, eax
0x1800247f7  jns     short loc_180024809
0x1800247f9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024800  jb      short loc_1800247CE
0x180024802  mov     edx, 4Ch ; 'L'
0x180024807  jmp     short loc_1800247B0
0x180024809  mov     rcx, [rbp+ppIVideoMediaType]
0x18002480d  mov     r8, rsi
0x180024810  mov     rdx, r14
0x180024813  mov     rax, [rcx]
0x180024816  mov     rax, [rax]
0x180024819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002481e  mov     ebx, eax
0x180024820  test    eax, eax
0x180024822  jns     short loc_1800247CE
0x180024824  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002482b  jb      short loc_1800247CE
0x18002482d  mov     edx, 4Dh ; 'M'
0x180024832  jmp     loc_1800247B0
0x180024837  mov     rcx, [rbp+var_10]
0x18002483b  mov     rax, [rdi]
0x18002483e  mov     [rbp+var_10], 0
0x180024846  mov     rbx, [rax]
0x180024849  test    rcx, rcx
0x18002484c  jz      short loc_18002485A
0x18002484e  mov     rdx, [rcx]
0x180024851  mov     rax, [rdx+10h]
0x180024855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002485a  lea     r8, [rbp+var_10]
0x18002485e  mov     rcx, rdi
0x180024861  lea     rdx, _GUID_44ae0fa8_ea31_4109_8d2e_4cae4997c555
0x180024868  mov     rax, rbx
0x18002486b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024870  test    eax, eax
0x180024872  js      loc_180024925
0x180024878  lea     rcx, [rbp+ppIVideoMediaType]; ppMFType
0x18002487c  mov     [rbp+ppIVideoMediaType], 0
0x180024884  call    cs:__imp_MFCreateMediaType
0x18002488a  mov     ebx, eax
0x18002488c  test    eax, eax
0x18002488e  jns     short loc_1800248CA
0x180024890  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024897  jb      short loc_1800248BC
0x180024899  mov     edx, 4Eh ; 'N'
0x18002489e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248a5  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x1800248ac  xor     r9d, r9d
0x1800248af  mov     [rsp+40h+var_20], eax
0x1800248b3  mov     rcx, [rcx+10h]
0x1800248b7  call    WPP_SF_qD
0x1800248bc  lea     rcx, [rbp+ppIVideoMediaType]; void *
0x1800248c0  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800248c5  jmp     loc_180024A11
0x1800248ca  mov     rcx, [rbp+var_10]
0x1800248ce  mov     rdx, [rbp+ppIVideoMediaType]
0x1800248d2  mov     rax, [rcx]
0x1800248d5  mov     rax, [rax+100h]
0x1800248dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248e1  mov     ebx, eax
0x1800248e3  test    eax, eax
0x1800248e5  jns     short loc_1800248F7
0x1800248e7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800248ee  jb      short loc_1800248BC
0x1800248f0  mov     edx, 4Fh ; 'O'
0x1800248f5  jmp     short loc_18002489E
0x1800248f7  mov     rcx, [rbp+ppIVideoMediaType]
0x1800248fb  mov     r8, rsi
0x1800248fe  mov     rdx, r14
0x180024901  mov     rax, [rcx]
0x180024904  mov     rax, [rax]
0x180024907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002490c  mov     ebx, eax
0x18002490e  test    eax, eax
0x180024910  jns     short loc_1800248BC
0x180024912  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024919  jb      short loc_1800248BC
0x18002491b  mov     edx, 50h ; 'P'
0x180024920  jmp     loc_18002489E
0x180024925  mov     rax, [rdi]
0x180024928  lea     rdx, [rbp+ppIVideoMediaType]
0x18002492c  mov     rcx, rdi
0x18002492f  mov     [rbp+ppMFAttributes], 0
0x180024937  mov     dword ptr [rbp+ppIVideoMediaType], 0
0x18002493e  mov     rax, [rax+0F0h]
0x180024945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002494a  mov     ebx, eax
0x18002494c  test    eax, eax
0x18002494e  jns     short loc_180024967
0x180024950  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024957  jb      loc_180024A08
0x18002495d  mov     edx, 51h ; 'Q'
0x180024962  jmp     loc_1800249EA
0x180024967  mov     ebx, dword ptr [rbp+ppIVideoMediaType]
0x18002496a  lea     rcx, [rbp+ppMFAttributes]
0x18002496e  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180024973  mov     edx, ebx; cInitialSize
0x180024975  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x180024979  call    cs:__imp_MFCreateAttributes
0x18002497f  mov     ebx, eax
0x180024981  test    eax, eax
0x180024983  jns     short loc_180024995
0x180024985  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002498c  jb      short loc_180024A08
0x18002498e  mov     edx, 52h ; 'R'
0x180024993  jmp     short loc_1800249EA
0x180024995  mov     rax, [rdi]
0x180024998  mov     rcx, rdi
0x18002499b  mov     rdx, [rbp+ppMFAttributes]
0x18002499f  mov     rax, [rax+100h]
0x1800249a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249ab  mov     ebx, eax
0x1800249ad  test    eax, eax
0x1800249af  jns     short loc_1800249C1
0x1800249b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800249b8  jb      short loc_180024A08
0x1800249ba  mov     edx, 53h ; 'S'
0x1800249bf  jmp     short loc_1800249EA
0x1800249c1  mov     rcx, [rbp+ppMFAttributes]
0x1800249c5  mov     r8, rsi
0x1800249c8  mov     rdx, r14
0x1800249cb  mov     rax, [rcx]
0x1800249ce  mov     rax, [rax]
0x1800249d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249d6  mov     ebx, eax
0x1800249d8  test    eax, eax
0x1800249da  jns     short loc_180024A08
0x1800249dc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800249e3  jb      short loc_180024A08
0x1800249e5  mov     edx, 54h ; 'T'
0x1800249ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249f1  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x1800249f8  xor     r9d, r9d
0x1800249fb  mov     [rsp+40h+var_20], eax
0x1800249ff  mov     rcx, [rcx+10h]
0x180024a03  call    WPP_SF_qD
0x180024a08  lea     rcx, [rbp+ppMFAttributes]; void *
0x180024a0c  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180024a11  lea     rcx, [rbp+var_10]; void *
0x180024a15  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180024a1a  lea     rcx, [rbp+var_8]; void *
0x180024a1e  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180024a23  mov     rsi, [rsp+40h+arg_8]
0x180024a28  mov     eax, ebx
0x180024a2a  mov     rbx, [rsp+40h+arg_0]
0x180024a2f  add     rsp, 40h
0x180024a33  pop     r14
0x180024a35  pop     rdi
0x180024a36  pop     rbp
0x180024a37  retn
```
