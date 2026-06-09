# FSStream::GetStreamAttributes(IMFAttributes * *)

- ea: `0x1800a981c`
- end: `0x1800a9b98`
- name: `?GetStreamAttributes@FSStream@@QEAAJPEAPEAUIMFAttributes@@@Z`
- size: `892`
- prototype: `__int64 __fastcall(FSStream *__hidden this, struct IMFAttributes **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180096cf0`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x18000a880`
- `0x180024200`
- `0x1800a981c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a9b77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a9b77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a983f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a983f`
- `MFPlat!MFCreateAttributes` at `0x1800a98e5`
- `MFPlat!MFCreateAttributes` at `0x1800a98e5`

## pseudocode

```c
__int64 __fastcall FSStream::GetStreamAttributes(FSStream *this, struct IMFAttributes **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  struct IMFAttributes **v6; // r12
  HRESULT v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall **v11)(_QWORD, GUID *, __int64 *); // rax
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  struct IMFAttributes *v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  __int64 v18; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+40h] [rbp-10h] BYREF
  int v20; // [rsp+90h] [rbp+40h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+98h] [rbp+48h] BYREF
  __int64 v22; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v23; // [rsp+A8h] [rbp+58h] BYREF

  v19 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( a2 )
  {
    *a2 = 0;
    if ( *((_DWORD *)this + 53) )
    {
      v4 = -1072873851;
      if ( !g_wppLevels )
        goto LABEL_38;
      v5 = 46;
      goto LABEL_4;
    }
    v6 = (struct IMFAttributes **)((char *)this + 152);
    if ( !*((_QWORD *)this + 19) )
    {
      v18 = 0;
      v23 = 0;
      ppMFAttributes = 0;
      v22 = 0;
      v17 = 0;
      v20 = 1;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
      v7 = MFCreateAttributes(&ppMFAttributes, 1u);
      v4 = v7;
      if ( v7 < 0 )
      {
        if ( !g_wppLevels )
        {
LABEL_13:
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v17);
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v22);
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v23);
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v18);
          goto LABEL_38;
        }
        v8 = 47;
LABEL_12:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids, this, v7);
        goto LABEL_13;
      }
      v9 = v23;
      v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 9);
      v11 = *v10;
      v23 = 0;
      v12 = *v11;
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      v7 = v12(v10, &GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8, &v23);
      v4 = v7;
      if ( v7 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_13;
        v8 = 48;
        goto LABEL_12;
      }
      v13 = v23;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v23 + 112LL);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v22);
      v7 = v14(v13, *((unsigned int *)this + 23), &v22);
      v4 = v7;
      if ( v7 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_13;
        v8 = 49;
        goto LABEL_12;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v22 + 256LL))(v22, ppMFAttributes);
      v4 = v7;
      if ( v7 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_13;
        v8 = 50;
        goto LABEL_12;
      }
      if ( (unsigned int)MFGetAttributeUINT32(v22, MF_DEVICESTREAM_ATTRIBUTE_PLUGIN_ENABLED, 0) )
      {
        v7 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
               ppMFAttributes,
               MF_DEVICESTREAM_ATTRIBUTE_PLUGIN_IN_FRAMESERVER,
               1);
        v4 = v7;
        if ( v7 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_13;
          v8 = 51;
          goto LABEL_12;
        }
      }
      ((void (__fastcall *)(IMFAttributes *, const IID *))ppMFAttributes->lpVtbl->DeleteItem)(
        ppMFAttributes,
        &MF_DEVICESTREAM_EXTENSION_PLUGIN_CLSID);
      ((void (__fastcall *)(IMFAttributes *, const IID *))ppMFAttributes->lpVtbl->DeleteItem)(
        ppMFAttributes,
        &MF_DEVICESTREAM_EXTENSION_PLUGIN_CONNECTION_POINT);
      ((void (__fastcall *)(IMFAttributes *, __int64 *))ppMFAttributes->lpVtbl->DeleteItem)(
        ppMFAttributes,
        MF_DEVICESTREAM_ATTRIBUTE_PLUGIN_ENABLED);
      if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, int *))ppMFAttributes->lpVtbl->GetUINT32)(
             ppMFAttributes,
             MF_DEVICESTREAM_ATTRIBUTE_FRAMESOURCE_TYPES,
             &v20) < 0 )
      {
        v7 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
               ppMFAttributes,
               MF_DEVICESTREAM_ATTRIBUTE_FRAMESOURCE_TYPES,
               1);
        v4 = v7;
        if ( v7 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_13;
          v8 = 52;
          goto LABEL_12;
        }
      }
      wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(
        (__int64 *)this + 19,
        (__int64)ppMFAttributes);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v17);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v22);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v23);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v18);
    }
    v15 = *v6;
    if ( *v6 )
    {
      *a2 = v15;
      ((void (__fastcall *)(struct IMFAttributes *))v15->lpVtbl->AddRef)(v15);
    }
    else
    {
      *a2 = 0;
    }
    v4 = 0;
    goto LABEL_38;
  }
  v4 = -2147467261;
  if ( g_wppLevels )
  {
    v5 = 45;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids, this, v4);
  }
LABEL_38:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v19);
  return v4;
}

```

## disassembly

```asm
0x1800a981c  push    rbp
0x1800a981e  push    rbx
0x1800a981f  push    rdi
0x1800a9820  push    r12
0x1800a9822  push    r13
0x1800a9824  push    r14
0x1800a9826  push    r15
0x1800a9828  mov     rbp, rsp
0x1800a982b  sub     rsp, 50h
0x1800a982f  mov     r14, rcx
0x1800a9832  xor     edi, edi
0x1800a9834  add     rcx, 18h; lpCriticalSection
0x1800a9838  mov     [rbp+var_10], rdi
0x1800a983c  mov     r15, rdx
0x1800a983f  call    cs:__imp_EnterCriticalSection
0x1800a9845  test    r15, r15
0x1800a9848  jnz     short loc_1800A9882
0x1800a984a  mov     ebx, 80004003h
0x1800a984f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9856  jb      loc_1800A9B73
0x1800a985c  lea     edx, [rdi+2Dh]
0x1800a985f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9866  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800a986d  mov     r9, r14
0x1800a9870  mov     [rsp+50h+var_30], ebx
0x1800a9874  mov     rcx, [rcx+10h]
0x1800a9878  call    WPP_SF_qD
0x1800a987d  jmp     loc_1800A9B73
0x1800a9882  mov     [r15], rdi
0x1800a9885  cmp     [r14+0D4h], edi
0x1800a988c  jz      short loc_1800A98A7
0x1800a988e  mov     ebx, 0C00D3E85h
0x1800a9893  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a989a  jb      loc_1800A9B73
0x1800a98a0  mov     edx, 2Eh ; '.'
0x1800a98a5  jmp     short loc_1800A985F
0x1800a98a7  lea     r12, [r14+98h]
0x1800a98ae  cmp     [r12], rdi
0x1800a98b2  jnz     loc_1800A9B54
0x1800a98b8  lea     rcx, [rbp+ppMFAttributes]
0x1800a98bc  mov     [rbp+var_18], rdi
0x1800a98c0  mov     [rbp+arg_18], rdi
0x1800a98c4  mov     [rbp+ppMFAttributes], rdi
0x1800a98c8  mov     [rbp+arg_10], rdi
0x1800a98cc  mov     [rbp+var_20], rdi
0x1800a98d0  mov     [rbp+arg_0], 1
0x1800a98d7  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800a98dc  mov     edx, 1; cInitialSize
0x1800a98e1  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x1800a98e5  call    cs:__imp_MFCreateAttributes
0x1800a98eb  mov     ebx, eax
0x1800a98ed  test    eax, eax
0x1800a98ef  jns     short loc_1800A994F
0x1800a98f1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a98f8  jb      short loc_1800A991D
0x1800a98fa  mov     edx, 2Fh ; '/'
0x1800a98ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9906  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800a990d  mov     r9, r14
0x1800a9910  mov     [rsp+50h+var_30], eax
0x1800a9914  mov     rcx, [rcx+10h]
0x1800a9918  call    WPP_SF_qD
0x1800a991d  lea     rcx, [rbp+var_20]; void *
0x1800a9921  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a9926  lea     rcx, [rbp+arg_10]; void *
0x1800a992a  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a992f  lea     rcx, [rbp+ppMFAttributes]; void *
0x1800a9933  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a9938  lea     rcx, [rbp+arg_18]; void *
0x1800a993c  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a9941  lea     rcx, [rbp+var_18]; void *
0x1800a9945  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a994a  jmp     loc_1800A9B73
0x1800a994f  mov     rcx, [rbp+arg_18]
0x1800a9953  mov     rbx, [r14+48h]
0x1800a9957  mov     rax, [rbx]
0x1800a995a  mov     [rbp+arg_18], 0
0x1800a9962  mov     rdi, [rax]
0x1800a9965  test    rcx, rcx
0x1800a9968  jz      short loc_1800A9976
0x1800a996a  mov     rdx, [rcx]
0x1800a996d  mov     rax, [rdx+10h]
0x1800a9971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9976  lea     r8, [rbp+arg_18]
0x1800a997a  mov     rcx, rbx
0x1800a997d  lea     rdx, _GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8
0x1800a9984  mov     rax, rdi
0x1800a9987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a998c  mov     ebx, eax
0x1800a998e  test    eax, eax
0x1800a9990  jns     short loc_1800A99A5
0x1800a9992  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9999  jb      short loc_1800A991D
0x1800a999b  mov     edx, 30h ; '0'
0x1800a99a0  jmp     loc_1800A98FF
0x1800a99a5  mov     rdi, [rbp+arg_18]
0x1800a99a9  lea     rcx, [rbp+arg_10]
0x1800a99ad  mov     rax, [rdi]
0x1800a99b0  mov     rbx, [rax+70h]
0x1800a99b4  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800a99b9  mov     edx, [r14+5Ch]
0x1800a99bd  lea     r8, [rbp+arg_10]
0x1800a99c1  mov     rcx, rdi
0x1800a99c4  mov     rax, rbx
0x1800a99c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a99cc  xor     edi, edi
0x1800a99ce  mov     ebx, eax
0x1800a99d0  test    eax, eax
0x1800a99d2  jns     short loc_1800A99E9
0x1800a99d4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a99db  jb      loc_1800A991D
0x1800a99e1  lea     edx, [rdi+31h]
0x1800a99e4  jmp     loc_1800A98FF
0x1800a99e9  mov     rcx, [rbp+arg_10]
0x1800a99ed  mov     rdx, [rbp+ppMFAttributes]
0x1800a99f1  mov     rax, [rcx]
0x1800a99f4  mov     rax, [rax+100h]
0x1800a99fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9a00  mov     ebx, eax
0x1800a9a02  test    eax, eax
0x1800a9a04  jns     short loc_1800A9A1D
0x1800a9a06  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9a0d  jb      loc_1800A991D
0x1800a9a13  mov     edx, 32h ; '2'
0x1800a9a18  jmp     loc_1800A98FF
0x1800a9a1d  mov     rcx, [rbp+arg_10]
0x1800a9a21  lea     rdx, MF_DEVICESTREAM_ATTRIBUTE_PLUGIN_ENABLED
0x1800a9a28  xor     r8d, r8d
0x1800a9a2b  call    MFGetAttributeUINT32
0x1800a9a30  test    eax, eax
0x1800a9a32  jz      short loc_1800A9A71
0x1800a9a34  mov     rcx, [rbp+ppMFAttributes]
0x1800a9a38  lea     rdx, MF_DEVICESTREAM_ATTRIBUTE_PLUGIN_IN_FRAMESERVER
0x1800a9a3f  mov     r8d, 1
0x1800a9a45  mov     rax, [rcx]
0x1800a9a48  mov     rax, [rax+0A8h]
0x1800a9a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9a54  mov     ebx, eax
0x1800a9a56  test    eax, eax
0x1800a9a58  jns     short loc_1800A9A71
0x1800a9a5a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9a61  jb      loc_1800A991D
0x1800a9a67  mov     edx, 33h ; '3'
0x1800a9a6c  jmp     loc_1800A98FF
0x1800a9a71  mov     rcx, [rbp+ppMFAttributes]
0x1800a9a75  lea     rdx, MF_DEVICESTREAM_EXTENSION_PLUGIN_CLSID
0x1800a9a7c  mov     rax, [rcx]
0x1800a9a7f  mov     rax, [rax+98h]
0x1800a9a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9a8b  mov     rcx, [rbp+ppMFAttributes]
0x1800a9a8f  lea     rdx, MF_DEVICESTREAM_EXTENSION_PLUGIN_CONNECTION_POINT
0x1800a9a96  mov     rax, [rcx]
0x1800a9a99  mov     rax, [rax+98h]
0x1800a9aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9aa5  mov     rcx, [rbp+ppMFAttributes]
0x1800a9aa9  lea     rdx, MF_DEVICESTREAM_ATTRIBUTE_PLUGIN_ENABLED
0x1800a9ab0  mov     rax, [rcx]
0x1800a9ab3  mov     rax, [rax+98h]
0x1800a9aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9abf  mov     rcx, [rbp+ppMFAttributes]
0x1800a9ac3  lea     r8, [rbp+arg_0]
0x1800a9ac7  lea     rdx, MF_DEVICESTREAM_ATTRIBUTE_FRAMESOURCE_TYPES
0x1800a9ace  mov     rax, [rcx]
0x1800a9ad1  mov     rax, [rax+38h]
0x1800a9ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9ada  test    eax, eax
0x1800a9adc  jns     short loc_1800A9B1B
0x1800a9ade  mov     rcx, [rbp+ppMFAttributes]
0x1800a9ae2  lea     rdx, MF_DEVICESTREAM_ATTRIBUTE_FRAMESOURCE_TYPES
0x1800a9ae9  mov     r8d, 1
0x1800a9aef  mov     rax, [rcx]
0x1800a9af2  mov     rax, [rax+0A8h]
0x1800a9af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9afe  mov     ebx, eax
0x1800a9b00  test    eax, eax
0x1800a9b02  jns     short loc_1800A9B1B
0x1800a9b04  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9b0b  jb      loc_1800A991D
0x1800a9b11  mov     edx, 34h ; '4'
0x1800a9b16  jmp     loc_1800A98FF
0x1800a9b1b  mov     rdx, [rbp+ppMFAttributes]
0x1800a9b1f  mov     rcx, r12
0x1800a9b22  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x1800a9b27  lea     rcx, [rbp+var_20]; void *
0x1800a9b2b  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a9b30  lea     rcx, [rbp+arg_10]; void *
0x1800a9b34  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a9b39  lea     rcx, [rbp+ppMFAttributes]; void *
0x1800a9b3d  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a9b42  lea     rcx, [rbp+arg_18]; void *
0x1800a9b46  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a9b4b  lea     rcx, [rbp+var_18]; void *
0x1800a9b4f  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a9b54  mov     rcx, [r12]
0x1800a9b58  test    rcx, rcx
0x1800a9b5b  jz      short loc_1800A9B6E
0x1800a9b5d  mov     [r15], rcx
0x1800a9b60  mov     rax, [rcx]
0x1800a9b63  mov     rax, [rax+8]
0x1800a9b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9b6c  jmp     short loc_1800A9B71
0x1800a9b6e  mov     [r15], rdi
0x1800a9b71  mov     ebx, edi
0x1800a9b73  lea     rcx, [r14+18h]; lpCriticalSection
0x1800a9b77  call    cs:__imp_LeaveCriticalSection
0x1800a9b7d  lea     rcx, [rbp+var_10]; void *
0x1800a9b81  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a9b86  mov     eax, ebx
0x1800a9b88  add     rsp, 50h
0x1800a9b8c  pop     r15
0x1800a9b8e  pop     r14
0x1800a9b90  pop     r13
0x1800a9b92  pop     r12
0x1800a9b94  pop     rdi
0x1800a9b95  pop     rbx
0x1800a9b96  pop     rbp
0x1800a9b97  retn
```
