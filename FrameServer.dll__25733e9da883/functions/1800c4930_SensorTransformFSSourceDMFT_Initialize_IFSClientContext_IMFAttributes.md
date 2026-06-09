# SensorTransformFSSourceDMFT::Initialize(IFSClientContext *,IMFAttributes *)

- ea: `0x1800c4930`
- end: `0x1800c4ce1`
- name: `?Initialize@SensorTransformFSSourceDMFT@@MEAAJPEAUIFSClientContext@@PEAUIMFAttributes@@@Z`
- size: `945`
- prototype: `__int64 __fastcall(SensorTransformFSSourceDMFT *__hidden this, struct IFSClientContext *, struct IMFAttributes *)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, registry_config, broker_com_uri`

## callees

- `0x180008cf0`
- `0x180009608`
- `0x180016790`
- `0x1800180c8`
- `0x1800c41b4`
- `0x1800c4930`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x1800c49e5`
- `MFPlat!MFCreateAttributes` at `0x1800c4a3e`
- `MFPlat!MFCreateAttributes` at `0x1800c49e5`
- `MFPlat!MFCreateAttributes` at `0x1800c4a3e`

## pseudocode

```c
__int64 __fastcall SensorTransformFSSourceDMFT::Initialize(
        SensorTransformFSSourceDMFT *this,
        struct IFSClientContext *a2,
        struct IMFAttributes *a3)
{
  unsigned int v6; // edi
  struct IMFAttributesVtbl *lpVtbl; // rax
  HRESULT v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rax
  unsigned int v12; // r15d
  __int64 v13; // rax
  int v14; // eax
  UINT32 i; // ebx
  unsigned int v16; // ecx
  int v17; // eax
  __int64 v18; // r13
  struct SensorTransformFSSourceDMFTPin *v19; // rcx
  __int64 v20; // rdx
  struct IFSSource *v22; // [rsp+30h] [rbp-20h] BYREF
  struct SensorTransformFSSourceDMFTPin *v23; // [rsp+38h] [rbp-18h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+40h] [rbp-10h] BYREF
  __int64 v25; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v26; // [rsp+98h] [rbp+48h] BYREF
  UINT32 cInitialSize; // [rsp+A8h] [rbp+58h] BYREF

  ppMFAttributes = 0;
  v26 = 0;
  v25 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids,
        this,
        -2147024809);
    goto LABEL_53;
  }
  if ( a3 )
  {
    lpVtbl = a3->lpVtbl;
    cInitialSize = 0;
    v8 = ((__int64 (__fastcall *)(struct IMFAttributes *, UINT32 *))lpVtbl->GetCount)(a3, &cInitialSize);
    v6 = v8;
    if ( v8 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_53;
      v9 = 64;
LABEL_9:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids, this, v8);
      goto LABEL_53;
    }
    v8 = MFCreateAttributes(&ppMFAttributes, cInitialSize);
    v6 = v8;
    if ( v8 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_53;
      v9 = 65;
      goto LABEL_9;
    }
    v8 = ((__int64 (__fastcall *)(struct IMFAttributes *, IMFAttributes *))a3->lpVtbl->CopyAllItems)(a3, ppMFAttributes);
    v6 = v8;
    if ( v8 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_53;
      v9 = 66;
      goto LABEL_9;
    }
  }
  else
  {
    v8 = MFCreateAttributes(&ppMFAttributes, 2u);
    v6 = v8;
    if ( v8 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_53;
      v9 = 67;
      goto LABEL_9;
    }
    v8 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, const wchar_t *))ppMFAttributes->lpVtbl->SetString)(
           ppMFAttributes,
           &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
           L"Frame Server MFT");
    v6 = v8;
    if ( v8 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_53;
      v9 = 68;
      goto LABEL_9;
    }
  }
  v8 = (*(__int64 (__fastcall **)(struct IFSClientContext *, __int64 *))(*(_QWORD *)a2 + 168LL))(a2, &v25);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_53;
    v9 = 69;
    goto LABEL_9;
  }
  v8 = (*(__int64 (__fastcall **)(struct IFSClientContext *, unsigned int *))(*(_QWORD *)a2 + 152LL))(a2, &v26);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_53;
    v9 = 70;
    goto LABEL_9;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v10 = v26;
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 128LL))(v25);
    WPP_SF_qqD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      71,
      WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids,
      this,
      v11,
      v10);
  }
  v12 = 0;
LABEL_31:
  if ( v12 < v26 )
  {
    v13 = *(_QWORD *)a2;
    v22 = 0;
    cInitialSize = 0;
    v14 = (*(__int64 (__fastcall **)(struct IFSClientContext *, _QWORD, struct IFSSource **))(v13 + 160))(a2, v12, &v22);
    v6 = v14;
    if ( v14 < 0 )
    {
      if ( g_wppLevels )
      {
        v20 = 72;
        goto LABEL_51;
      }
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(struct IFSSource *, UINT32 *))(*(_QWORD *)v22 + 64LL))(v22, &cInitialSize);
      v6 = v14;
      if ( v14 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= cInitialSize )
          {
            wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v22);
            ++v12;
            goto LABEL_31;
          }
          v16 = *((_DWORD *)this + 10);
          v23 = 0;
          v17 = SensorTransformFSSourceDMFTPin::CreateInstance(v16, i, v22, &v23);
          v6 = v17;
          if ( v17 < 0 )
            break;
          v18 = *((unsigned int *)this + 10);
          if ( !(unsigned int)CTEntryArray<FSCallback<IFSSourceFrameCallback,void *,int> *>::SetSize(
                                (char **)this + 4,
                                (const struct std::nothrow_t *)(unsigned int)(v18 + 1)) )
          {
            v6 = -2147024882;
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                75,
                WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids,
                this,
                -2147024882);
            goto LABEL_44;
          }
          v19 = v23;
          *(_QWORD *)(*((_QWORD *)this + 4) + 8 * v18) = v23;
          if ( v19 )
            (*(void (__fastcall **)(struct SensorTransformFSSourceDMFTPin *))(*(_QWORD *)v19 + 8LL))(v19);
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v23);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids, this, v17);
LABEL_44:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v23);
        goto LABEL_52;
      }
      if ( g_wppLevels )
      {
        v20 = 73;
LABEL_51:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids, this, v14);
      }
    }
LABEL_52:
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v22);
  }
LABEL_53:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v25);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  return v6;
}

```

## disassembly

```asm
0x1800c4930  mov     [rsp-38h+arg_0], rbx
0x1800c4935  push    rbp
0x1800c4936  push    rsi
0x1800c4937  push    rdi
0x1800c4938  push    r12
0x1800c493a  push    r13
0x1800c493c  push    r14
0x1800c493e  push    r15
0x1800c4940  mov     rbp, rsp
0x1800c4943  sub     rsp, 50h
0x1800c4947  xor     r12d, r12d
0x1800c494a  mov     rbx, r8
0x1800c494d  mov     [rbp+ppMFAttributes], r12
0x1800c4951  mov     r14, rdx
0x1800c4954  mov     [rbp+arg_8], r12d
0x1800c4958  mov     rsi, rcx
0x1800c495b  mov     [rbp+var_8], r12
0x1800c495f  test    rdx, rdx
0x1800c4962  jnz     short loc_1800C499D
0x1800c4964  mov     edi, 80070057h
0x1800c4969  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4970  jb      loc_1800C4CB5
0x1800c4976  lea     edx, [r14+3Fh]
0x1800c497a  mov     dword ptr [rsp+50h+var_30], edi
0x1800c497e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4985  lea     r8, WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids
0x1800c498c  mov     r9, rsi
0x1800c498f  mov     rcx, [rcx+10h]
0x1800c4993  call    WPP_SF_qD
0x1800c4998  jmp     loc_1800C4CB5
0x1800c499d  test    rbx, rbx
0x1800c49a0  jz      loc_1800C4A35
0x1800c49a6  mov     rax, [r8]
0x1800c49a9  lea     rdx, [rbp+cInitialSize]
0x1800c49ad  mov     rcx, rbx
0x1800c49b0  mov     [rbp+cInitialSize], r12d
0x1800c49b4  mov     rax, [rax+0F0h]
0x1800c49bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c49c0  mov     edi, eax
0x1800c49c2  test    eax, eax
0x1800c49c4  jns     short loc_1800C49DE
0x1800c49c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c49cd  jb      loc_1800C4CB5
0x1800c49d3  mov     edx, 40h ; '@'
0x1800c49d8  mov     dword ptr [rsp+50h+var_30], eax
0x1800c49dc  jmp     short loc_1800C497E
0x1800c49de  mov     edx, [rbp+cInitialSize]; cInitialSize
0x1800c49e1  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x1800c49e5  call    cs:__imp_MFCreateAttributes
0x1800c49eb  mov     edi, eax
0x1800c49ed  test    eax, eax
0x1800c49ef  jns     short loc_1800C4A05
0x1800c49f1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c49f8  jb      loc_1800C4CB5
0x1800c49fe  mov     edx, 41h ; 'A'
0x1800c4a03  jmp     short loc_1800C49D8
0x1800c4a05  mov     rax, [rbx]
0x1800c4a08  mov     rcx, rbx
0x1800c4a0b  mov     rdx, [rbp+ppMFAttributes]
0x1800c4a0f  mov     rax, [rax+100h]
0x1800c4a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4a1b  mov     edi, eax
0x1800c4a1d  test    eax, eax
0x1800c4a1f  jns     short loc_1800C4A9F
0x1800c4a21  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4a28  jb      loc_1800C4CB5
0x1800c4a2e  mov     edx, 42h ; 'B'
0x1800c4a33  jmp     short loc_1800C49D8
0x1800c4a35  mov     edx, 2; cInitialSize
0x1800c4a3a  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x1800c4a3e  call    cs:__imp_MFCreateAttributes
0x1800c4a44  mov     edi, eax
0x1800c4a46  test    eax, eax
0x1800c4a48  jns     short loc_1800C4A61
0x1800c4a4a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4a51  jb      loc_1800C4CB5
0x1800c4a57  mov     edx, 43h ; 'C'
0x1800c4a5c  jmp     loc_1800C49D8
0x1800c4a61  mov     rcx, [rbp+ppMFAttributes]
0x1800c4a65  lea     r8, aFrameServerMft; "Frame Server MFT"
0x1800c4a6c  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x1800c4a73  mov     rax, [rcx]
0x1800c4a76  mov     rax, [rax+0C8h]
0x1800c4a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4a82  mov     edi, eax
0x1800c4a84  test    eax, eax
0x1800c4a86  jns     short loc_1800C4A9F
0x1800c4a88  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4a8f  jb      loc_1800C4CB5
0x1800c4a95  mov     edx, 44h ; 'D'
0x1800c4a9a  jmp     loc_1800C49D8
0x1800c4a9f  mov     rax, [r14]
0x1800c4aa2  lea     rdx, [rbp+var_8]
0x1800c4aa6  mov     rcx, r14
0x1800c4aa9  mov     rax, [rax+0A8h]
0x1800c4ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4ab5  mov     edi, eax
0x1800c4ab7  test    eax, eax
0x1800c4ab9  jns     short loc_1800C4AD2
0x1800c4abb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4ac2  jb      loc_1800C4CB5
0x1800c4ac8  mov     edx, 45h ; 'E'
0x1800c4acd  jmp     loc_1800C49D8
0x1800c4ad2  mov     rax, [r14]
0x1800c4ad5  lea     rdx, [rbp+arg_8]
0x1800c4ad9  mov     rcx, r14
0x1800c4adc  mov     rax, [rax+98h]
0x1800c4ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4ae8  mov     edi, eax
0x1800c4aea  test    eax, eax
0x1800c4aec  jns     short loc_1800C4B05
0x1800c4aee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4af5  jb      loc_1800C4CB5
0x1800c4afb  mov     edx, 46h ; 'F'
0x1800c4b00  jmp     loc_1800C49D8
0x1800c4b05  cmp     cs:byte_18010EC4D, 8
0x1800c4b0c  jb      short loc_1800C4B4F
0x1800c4b0e  mov     rcx, [rbp+var_8]
0x1800c4b12  mov     ebx, [rbp+arg_8]
0x1800c4b15  mov     rax, [rcx]
0x1800c4b18  mov     rax, [rax+80h]
0x1800c4b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b24  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4b2b  lea     r8, WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids
0x1800c4b32  mov     edx, 47h ; 'G'
0x1800c4b37  mov     [rsp+50h+var_28], ebx
0x1800c4b3b  mov     r9, rsi
0x1800c4b3e  mov     [rsp+50h+var_30], rax
0x1800c4b43  mov     rcx, [rcx+0D8h]
0x1800c4b4a  call    WPP_SF_qqD
0x1800c4b4f  mov     r15d, r12d
0x1800c4b52  cmp     r15d, [rbp+arg_8]
0x1800c4b56  jnb     loc_1800C4CB5
0x1800c4b5c  mov     rax, [r14]
0x1800c4b5f  lea     r8, [rbp+var_20]
0x1800c4b63  mov     edx, r15d
0x1800c4b66  mov     [rbp+var_20], r12
0x1800c4b6a  mov     rcx, r14
0x1800c4b6d  mov     [rbp+cInitialSize], r12d
0x1800c4b71  mov     rax, [rax+0A0h]
0x1800c4b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b7d  mov     edi, eax
0x1800c4b7f  test    eax, eax
0x1800c4b81  js      loc_1800C4C80
0x1800c4b87  mov     rcx, [rbp+var_20]
0x1800c4b8b  lea     rdx, [rbp+cInitialSize]
0x1800c4b8f  mov     rax, [rcx]
0x1800c4b92  mov     rax, [rax+40h]
0x1800c4b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b9b  mov     edi, eax
0x1800c4b9d  test    eax, eax
0x1800c4b9f  js      loc_1800C4C70
0x1800c4ba5  mov     ebx, r12d
0x1800c4ba8  cmp     ebx, [rbp+cInitialSize]
0x1800c4bab  jnb     short loc_1800C4C0F
0x1800c4bad  mov     r8, [rbp+var_20]; struct IFSSource *
0x1800c4bb1  lea     r9, [rbp+var_18]; struct SensorTransformFSSourceDMFTPin **
0x1800c4bb5  mov     ecx, [rsi+28h]; unsigned int
0x1800c4bb8  mov     edx, ebx; unsigned int
0x1800c4bba  mov     [rbp+var_18], r12
0x1800c4bbe  call    ?CreateInstance@SensorTransformFSSourceDMFTPin@@SAJKKPEAUIFSSource@@PEAPEAV1@@Z; SensorTransformFSSourceDMFTPin::CreateInstance(ulong,ulong,IFSSource *,SensorTransformFSSourceDMFTPin * *)
0x1800c4bc3  mov     edi, eax
0x1800c4bc5  test    eax, eax
0x1800c4bc7  js      loc_1800C4C5C
0x1800c4bcd  mov     r13d, [rsi+28h]
0x1800c4bd1  lea     rcx, [rsi+20h]
0x1800c4bd5  lea     edx, [r13+1]
0x1800c4bd9  call    ?SetSize@?$CTEntryArray@PEAV?$FSCallback@UIFSSourceFrameCallback@@PEAXH@@@@QEAAHKK@Z; CTEntryArray<FSCallback<IFSSourceFrameCallback,void *,int> *>::SetSize(ulong,ulong)
0x1800c4bde  test    eax, eax
0x1800c4be0  jz      short loc_1800C4C20
0x1800c4be2  mov     rcx, [rbp+var_18]
0x1800c4be6  xor     r12d, r12d
0x1800c4be9  mov     rax, [rsi+20h]
0x1800c4bed  mov     [rax+r13*8], rcx
0x1800c4bf1  test    rcx, rcx
0x1800c4bf4  jz      short loc_1800C4C02
0x1800c4bf6  mov     rax, [rcx]
0x1800c4bf9  mov     rax, [rax+8]
0x1800c4bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4c02  lea     rcx, [rbp+var_18]; void *
0x1800c4c06  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800c4c0b  inc     ebx
0x1800c4c0d  jmp     short loc_1800C4BA8
0x1800c4c0f  lea     rcx, [rbp+var_20]; void *
0x1800c4c13  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800c4c18  inc     r15d
0x1800c4c1b  jmp     loc_1800C4B52
0x1800c4c20  mov     edi, 8007000Eh
0x1800c4c25  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4c2c  jb      short loc_1800C4C51
0x1800c4c2e  mov     edx, 4Bh ; 'K'
0x1800c4c33  mov     dword ptr [rsp+50h+var_30], edi
0x1800c4c37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4c3e  lea     r8, WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids
0x1800c4c45  mov     r9, rsi
0x1800c4c48  mov     rcx, [rcx+10h]
0x1800c4c4c  call    WPP_SF_qD
0x1800c4c51  lea     rcx, [rbp+var_18]; void *
0x1800c4c55  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800c4c5a  jmp     short loc_1800C4CAC
0x1800c4c5c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4c63  jb      short loc_1800C4C51
0x1800c4c65  mov     edx, 4Ah ; 'J'
0x1800c4c6a  mov     dword ptr [rsp+50h+var_30], eax
0x1800c4c6e  jmp     short loc_1800C4C37
0x1800c4c70  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4c77  jb      short loc_1800C4CAC
0x1800c4c79  mov     edx, 49h ; 'I'
0x1800c4c7e  jmp     short loc_1800C4C8E
0x1800c4c80  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4c87  jb      short loc_1800C4CAC
0x1800c4c89  mov     edx, 48h ; 'H'
0x1800c4c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4c95  lea     r8, WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids
0x1800c4c9c  mov     r9, rsi
0x1800c4c9f  mov     dword ptr [rsp+50h+var_30], eax
0x1800c4ca3  mov     rcx, [rcx+10h]
0x1800c4ca7  call    WPP_SF_qD
0x1800c4cac  lea     rcx, [rbp+var_20]; void *
0x1800c4cb0  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800c4cb5  lea     rcx, [rbp+var_8]; void *
0x1800c4cb9  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800c4cbe  lea     rcx, [rbp+ppMFAttributes]; void *
0x1800c4cc2  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800c4cc7  mov     rbx, [rsp+50h+arg_0]
0x1800c4ccf  mov     eax, edi
0x1800c4cd1  add     rsp, 50h
0x1800c4cd5  pop     r15
0x1800c4cd7  pop     r14
0x1800c4cd9  pop     r13
0x1800c4cdb  pop     r12
0x1800c4cdd  pop     rdi
0x1800c4cde  pop     rsi
0x1800c4cdf  pop     rbp
0x1800c4ce0  retn
```
