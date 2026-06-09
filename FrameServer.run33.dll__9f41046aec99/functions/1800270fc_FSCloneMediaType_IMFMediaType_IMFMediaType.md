# FSCloneMediaType(IMFMediaType *,IMFMediaType * *)

- ea: `0x1800270fc`
- end: `0x1800272db`
- name: `?FSCloneMediaType@@YAJPEAUIMFMediaType@@PEAPEAU1@@Z`
- size: `479`
- prototype: `__int64 __fastcall(struct IMFMediaType *, struct IMFMediaType **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800422b0`
- `0x180089208`

## callees

- `0x180008cf0`
- `0x180009608`
- `0x1800270fc`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateVideoMediaType` at `0x18002717e`
- `MFPlat!MFCreateVideoMediaType` at `0x18002717e`
- `MFPlat!MFCreateMediaType` at `0x180027227`
- `MFPlat!MFCreateMediaType` at `0x180027227`

## pseudocode

```c
__int64 __fastcall FSCloneMediaType(struct IMFMediaType *a1, struct IMFMediaType **a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  const MFVIDEOFORMAT *v6; // rax
  HRESULT v7; // eax
  __int64 v8; // rdx
  HRESULT v9; // eax
  __int64 v10; // rdx
  IMFVideoMediaType *ppIVideoMediaType; // [rsp+50h] [rbp+20h] BYREF
  __int64 v13; // [rsp+60h] [rbp+30h] BYREF

  v13 = 0;
  if ( a1 )
  {
    if ( !a2 )
    {
      v4 = -2147467261;
      goto LABEL_28;
    }
    *a2 = 0;
    v5 = ((__int64 (__fastcall *)(struct IMFMediaType *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
           a1,
           &GUID_b99f381f_a8f9_47a2_a5af_ca3a225a3890,
           &v13);
    ppIVideoMediaType = 0;
    if ( v5 >= 0 )
    {
      v6 = (const MFVIDEOFORMAT *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 304LL))(v13);
      v7 = MFCreateVideoMediaType(v6, &ppIVideoMediaType);
      v4 = v7;
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, IMFVideoMediaType *))(*(_QWORD *)v13 + 256LL))(v13, ppIVideoMediaType);
        v4 = v7;
        if ( v7 >= 0 )
        {
          v7 = ((__int64 (__fastcall *)(IMFVideoMediaType *, GUID *, struct IMFMediaType **))ppIVideoMediaType->lpVtbl->QueryInterface)(
                 ppIVideoMediaType,
                 &GUID_44ae0fa8_ea31_4109_8d2e_4cae4997c555,
                 a2);
          v4 = v7;
          if ( v7 >= 0 || !g_wppLevels )
            goto LABEL_27;
          v8 = 74;
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_27;
          v8 = 73;
        }
        goto LABEL_9;
      }
      if ( g_wppLevels )
      {
        v8 = 72;
LABEL_9:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v7);
      }
LABEL_27:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppIVideoMediaType);
      goto LABEL_28;
    }
    v9 = MFCreateMediaType((IMFMediaType **)&ppIVideoMediaType);
    v4 = v9;
    if ( v9 >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFVideoMediaType *))a1->lpVtbl->CopyAllItems)(
             a1,
             ppIVideoMediaType);
      v4 = v9;
      if ( v9 >= 0 )
      {
        v9 = ((__int64 (__fastcall *)(IMFVideoMediaType *, GUID *, struct IMFMediaType **))ppIVideoMediaType->lpVtbl->QueryInterface)(
               ppIVideoMediaType,
               &GUID_44ae0fa8_ea31_4109_8d2e_4cae4997c555,
               a2);
        v4 = v9;
        if ( v9 >= 0 || !g_wppLevels )
          goto LABEL_27;
        v10 = 77;
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_27;
        v10 = 76;
      }
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_27;
      v10 = 75;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v9);
    goto LABEL_27;
  }
  v4 = -2147024809;
LABEL_28:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v13);
  return v4;
}

```

## disassembly

```asm
0x1800270fc  mov     [rsp-18h+arg_8], rbx
0x180027101  push    rbp
0x180027102  push    rsi
0x180027103  push    rdi
0x180027104  mov     rbp, rsp
0x180027107  sub     rsp, 30h
0x18002710b  mov     [rbp+arg_10], 0
0x180027113  mov     rsi, rdx
0x180027116  mov     rdi, rcx
0x180027119  test    rcx, rcx
0x18002711c  jnz     short loc_180027128
0x18002711e  mov     ebx, 80070057h
0x180027123  jmp     loc_1800272C3
0x180027128  test    rsi, rsi
0x18002712b  jnz     short loc_180027137
0x18002712d  mov     ebx, 80004003h
0x180027132  jmp     loc_1800272C3
0x180027137  mov     qword ptr [rdx], 0
0x18002713e  lea     r8, [rbp+arg_10]
0x180027142  mov     rax, [rcx]
0x180027145  lea     rdx, _GUID_b99f381f_a8f9_47a2_a5af_ca3a225a3890
0x18002714c  mov     rax, [rax]
0x18002714f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027154  mov     [rbp+ppIVideoMediaType], 0
0x18002715c  test    eax, eax
0x18002715e  js      loc_180027223
0x180027164  mov     rcx, [rbp+arg_10]
0x180027168  mov     rax, [rcx]
0x18002716b  mov     rax, [rax+130h]
0x180027172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027177  lea     rdx, [rbp+ppIVideoMediaType]; ppIVideoMediaType
0x18002717b  mov     rcx, rax; pVideoFormat
0x18002717e  call    cs:__imp_MFCreateVideoMediaType
0x180027184  mov     ebx, eax
0x180027186  test    eax, eax
0x180027188  jns     short loc_1800271C4
0x18002718a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027191  jb      short loc_1800271B6
0x180027193  mov     edx, 48h ; 'H'
0x180027198  mov     rcx, cs:WPP_GLOBAL_Control
0x18002719f  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x1800271a6  xor     r9d, r9d
0x1800271a9  mov     [rsp+30h+var_10], eax
0x1800271ad  mov     rcx, [rcx+10h]
0x1800271b1  call    WPP_SF_qD
0x1800271b6  lea     rcx, [rbp+ppIVideoMediaType]; void *
0x1800271ba  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800271bf  jmp     loc_1800272C3
0x1800271c4  mov     rcx, [rbp+arg_10]
0x1800271c8  mov     rdx, [rbp+ppIVideoMediaType]
0x1800271cc  mov     rax, [rcx]
0x1800271cf  mov     rax, [rax+100h]
0x1800271d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271db  mov     ebx, eax
0x1800271dd  test    eax, eax
0x1800271df  jns     short loc_1800271F1
0x1800271e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800271e8  jb      short loc_1800271B6
0x1800271ea  mov     edx, 49h ; 'I'
0x1800271ef  jmp     short loc_180027198
0x1800271f1  mov     rcx, [rbp+ppIVideoMediaType]
0x1800271f5  lea     rdx, _GUID_44ae0fa8_ea31_4109_8d2e_4cae4997c555
0x1800271fc  mov     r8, rsi
0x1800271ff  mov     rax, [rcx]
0x180027202  mov     rax, [rax]
0x180027205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002720a  mov     ebx, eax
0x18002720c  test    eax, eax
0x18002720e  jns     short loc_1800271B6
0x180027210  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027217  jb      short loc_1800271B6
0x180027219  mov     edx, 4Ah ; 'J'
0x18002721e  jmp     loc_180027198
0x180027223  lea     rcx, [rbp+ppIVideoMediaType]; ppMFType
0x180027227  call    cs:__imp_MFCreateMediaType
0x18002722d  mov     ebx, eax
0x18002722f  test    eax, eax
0x180027231  jns     short loc_180027243
0x180027233  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002723a  jb      short loc_1800272BA
0x18002723c  mov     edx, 4Bh ; 'K'
0x180027241  jmp     short loc_18002729C
0x180027243  mov     rax, [rdi]
0x180027246  mov     rcx, rdi
0x180027249  mov     rdx, [rbp+ppIVideoMediaType]
0x18002724d  mov     rax, [rax+100h]
0x180027254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027259  mov     ebx, eax
0x18002725b  test    eax, eax
0x18002725d  jns     short loc_18002726F
0x18002725f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027266  jb      short loc_1800272BA
0x180027268  mov     edx, 4Ch ; 'L'
0x18002726d  jmp     short loc_18002729C
0x18002726f  mov     rcx, [rbp+ppIVideoMediaType]
0x180027273  lea     rdx, _GUID_44ae0fa8_ea31_4109_8d2e_4cae4997c555
0x18002727a  mov     r8, rsi
0x18002727d  mov     rax, [rcx]
0x180027280  mov     rax, [rax]
0x180027283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027288  mov     ebx, eax
0x18002728a  test    eax, eax
0x18002728c  jns     short loc_1800272BA
0x18002728e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027295  jb      short loc_1800272BA
0x180027297  mov     edx, 4Dh ; 'M'
0x18002729c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800272a3  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x1800272aa  xor     r9d, r9d
0x1800272ad  mov     [rsp+30h+var_10], eax
0x1800272b1  mov     rcx, [rcx+10h]
0x1800272b5  call    WPP_SF_qD
0x1800272ba  lea     rcx, [rbp+ppIVideoMediaType]; void *
0x1800272be  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800272c3  lea     rcx, [rbp+arg_10]; void *
0x1800272c7  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800272cc  mov     eax, ebx
0x1800272ce  mov     rbx, [rsp+30h+arg_8]
0x1800272d3  add     rsp, 30h
0x1800272d7  pop     rdi
0x1800272d8  pop     rsi
0x1800272d9  pop     rbp
0x1800272da  retn
```
