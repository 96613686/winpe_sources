# SensorTransformFSSourceDMFTPin::Initialize(ulong,IFSSource *)

- ea: `0x1800c4cf0`
- end: `0x1800c52ca`
- name: `?Initialize@SensorTransformFSSourceDMFTPin@@MEAAJKPEAUIFSSource@@@Z`
- size: `1498`
- prototype: `__int64 __fastcall(SensorTransformFSSourceDMFTPin *__hidden this, unsigned int, struct IFSSource *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008cf0`
- `0x180009608`
- `0x18000ad10`
- `0x1800c4cf0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c526c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c526c`
- `MFPlat!MFCreateAttributes` at `0x1800c4ebc`
- `MFPlat!MFCreateAttributes` at `0x1800c4ee6`
- `MFPlat!MFCreateAttributes` at `0x1800c4ebc`
- `MFPlat!MFCreateAttributes` at `0x1800c4ee6`
- `MFPlat!MFCreateMediaType` at `0x1800c50d0`
- `MFPlat!MFCreateMediaType` at `0x1800c513b`
- `MFPlat!MFCreateMediaType` at `0x1800c50d0`
- `MFPlat!MFCreateMediaType` at `0x1800c513b`

## pseudocode

```c
__int64 __fastcall SensorTransformFSSourceDMFTPin::Initialize(
        IMFMediaType **this,
        unsigned int a2,
        struct IFSSource *a3)
{
  unsigned int v6; // edi
  HRESULT v7; // eax
  __int64 v8; // rdx
  unsigned int i; // esi
  HRESULT v10; // eax
  __int64 v11; // rdx
  IMFMediaType *v12; // rcx
  IMFMediaType *v13; // rcx
  _QWORD **v14; // rcx
  unsigned int j; // esi
  __int64 v16; // rbx
  IMFAttributes *ppMFAttributes; // [rsp+30h] [rbp-50h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  UINT32 cInitialSize; // [rsp+48h] [rbp-38h] BYREF
  IMFAttributes *v22; // [rsp+50h] [rbp-30h] BYREF
  __int64 v23; // [rsp+58h] [rbp-28h] BYREF
  __int64 v24; // [rsp+60h] [rbp-20h] BYREF
  __int64 v25; // [rsp+68h] [rbp-18h] BYREF
  __int64 v26; // [rsp+70h] [rbp-10h] BYREF
  __int64 v27; // [rsp+78h] [rbp-8h] BYREF
  unsigned int v28; // [rsp+C0h] [rbp+40h] BYREF
  int v29; // [rsp+C8h] [rbp+48h] BYREF

  v24 = 0;
  ppMFAttributes = 0;
  v23 = 0;
  v22 = 0;
  v27 = 0;
  v26 = 0;
  cInitialSize = 0;
  v29 = 0;
  pv = 0;
  v28 = 0;
  v25 = 0;
  if ( !a3 )
  {
    v6 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_82;
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids,
      this,
      -2147024809);
    goto LABEL_78;
  }
  v7 = (*(__int64 (__fastcall **)(struct IFSSource *, __int64 *))(*(_QWORD *)a3 + 288LL))(a3, &v23);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 22;
    goto LABEL_8;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v23 + 240LL))(v23, &cInitialSize);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 23;
    goto LABEL_8;
  }
  v7 = (*(__int64 (__fastcall **)(struct IFSSource *, GUID *, GUID *, __int64 *))(*(_QWORD *)a3 + 224LL))(
         a3,
         &GUID_00000000_0000_0000_0000_000000000000,
         &GUID_28f54685_06fd_11d2_b27a_00a0c9223196,
         &v26);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 24;
    goto LABEL_8;
  }
  (*(void (__fastcall **)(struct IFSSource *, _QWORD, GUID *, GUID *, __int64 *))(*(_QWORD *)a3 + 296LL))(
    a3,
    a2,
    &GUID_00000000_0000_0000_0000_000000000000,
    &GUID_28f54685_06fd_11d2_b27a_00a0c9223196,
    &v27);
  v7 = (*(__int64 (__fastcall **)(struct IFSSource *, _QWORD, __int64 *))(*(_QWORD *)a3 + 72LL))(a3, a2, &v24);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 25;
    goto LABEL_8;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 240LL))(v24, &v29);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 26;
    goto LABEL_8;
  }
  v7 = MFCreateAttributes(&ppMFAttributes, v29 + 3);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 27;
    goto LABEL_8;
  }
  v7 = MFCreateAttributes(&v22, cInitialSize);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 28;
    goto LABEL_8;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v24 + 256LL))(v24, ppMFAttributes);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 29;
    goto LABEL_8;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v23 + 256LL))(v23, v22);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 30;
    goto LABEL_8;
  }
  v7 = ((__int64 (__fastcall *)(IMFAttributes *, void *, __int64))ppMFAttributes->lpVtbl->SetUnknown)(
         ppMFAttributes,
         &MF_DEVICESTREAM_FILTER_KSCONTROL,
         v26);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 31;
    goto LABEL_8;
  }
  if ( v27 )
  {
    v7 = ((__int64 (__fastcall *)(IMFAttributes *, void *))ppMFAttributes->lpVtbl->SetUnknown)(
           ppMFAttributes,
           &MF_DEVICESTREAM_PIN_KSCONTROL);
    v6 = v7;
    if ( v7 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_78;
      v8 = 32;
      goto LABEL_8;
    }
  }
  v7 = ((__int64 (__fastcall *)(IMFAttributes *, void *, IMFAttributes *))ppMFAttributes->lpVtbl->SetUnknown)(
         ppMFAttributes,
         &MF_DEVICESTREAM_SOURCE_ATTRIBUTES,
         v22);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 33;
    goto LABEL_8;
  }
  v7 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
         ppMFAttributes,
         &MF_DEVICESTREAM_STREAM_ID,
         *((unsigned int *)this + 14));
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 34;
    goto LABEL_8;
  }
  v7 = (*(__int64 (__fastcall **)(struct IFSSource *, _QWORD, unsigned int *, LPVOID *))(*(_QWORD *)a3 + 80LL))(
         a3,
         a2,
         &v28,
         &pv);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 35;
    goto LABEL_8;
  }
  v7 = (*(__int64 (__fastcall **)(struct IFSSource *, _QWORD, __int64 *))(*(_QWORD *)a3 + 96LL))(a3, a2, &v25);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 36;
    goto LABEL_8;
  }
  v7 = MFCreateMediaType(this + 6);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v8 = 37;
LABEL_8:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids, this, v7);
    goto LABEL_78;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, IMFMediaType *))(*(_QWORD *)v25 + 256LL))(v25, this[6]);
  v6 = v7;
  if ( v7 >= 0 )
  {
    for ( i = 0; i < v28; ++i )
    {
      ppMFType = 0;
      v10 = MFCreateMediaType(&ppMFType);
      v6 = v10;
      if ( v10 < 0 )
      {
        if ( g_wppLevels )
        {
          v11 = 39;
LABEL_70:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v11,
            &WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids,
            this,
            v10);
        }
LABEL_71:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFType);
        goto LABEL_78;
      }
      v10 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaType *))(**((_QWORD **)pv + i) + 256LL))(
              *((_QWORD *)pv + i),
              ppMFType);
      v6 = v10;
      if ( v10 < 0 )
      {
        if ( g_wppLevels )
        {
          v11 = 40;
          goto LABEL_70;
        }
        goto LABEL_71;
      }
      if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add(this + 3, ppMFType) )
      {
        v6 = -2147024882;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            &WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids,
            this,
            -2147024882);
        goto LABEL_71;
      }
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFType);
    }
    if ( ppMFAttributes )
    {
      ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->AddRef)(ppMFAttributes);
      v13 = this[2];
      if ( v13 )
        ((void (__fastcall *)(IMFMediaType *))v13->lpVtbl->Release)(v13);
      this[2] = (IMFMediaType *)ppMFAttributes;
    }
    else
    {
      v12 = this[2];
      if ( v12 )
      {
        ((void (__fastcall *)(IMFMediaType *))v12->lpVtbl->Release)(v12);
        this[2] = 0;
      }
    }
    goto LABEL_78;
  }
  if ( g_wppLevels )
  {
    v8 = 38;
    goto LABEL_8;
  }
LABEL_78:
  v14 = (_QWORD **)pv;
  if ( pv )
  {
    for ( j = 0; j < v28; v14 = (_QWORD **)pv )
    {
      v16 = j;
      (*(void (__fastcall **)(_QWORD *))(*v14[j] + 16LL))(v14[j]);
      ++j;
      *((_QWORD *)pv + v16) = 0;
    }
    CoTaskMemFree(v14);
  }
LABEL_82:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v25);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v26);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v27);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v22);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v23);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v24);
  return v6;
}

```

## disassembly

```asm
0x1800c4cf0  mov     [rsp-28h+arg_0], rbx
0x1800c4cf5  push    rbp
0x1800c4cf6  push    rsi
0x1800c4cf7  push    rdi
0x1800c4cf8  push    r14
0x1800c4cfa  push    r15
0x1800c4cfc  mov     rbp, rsp
0x1800c4cff  sub     rsp, 80h
0x1800c4d06  xor     r15d, r15d
0x1800c4d09  mov     rsi, r8
0x1800c4d0c  mov     [rbp+var_20], r15
0x1800c4d10  mov     r14d, edx
0x1800c4d13  mov     [rbp+ppMFAttributes], r15
0x1800c4d17  mov     rbx, rcx
0x1800c4d1a  mov     [rbp+var_28], r15
0x1800c4d1e  mov     [rbp+var_30], r15
0x1800c4d22  mov     [rbp+var_8], r15
0x1800c4d26  mov     [rbp+var_10], r15
0x1800c4d2a  mov     [rbp+cInitialSize], r15d
0x1800c4d2e  mov     [rbp+arg_18], r15d
0x1800c4d32  mov     [rbp+pv], r15
0x1800c4d36  mov     [rbp+arg_10], r15d
0x1800c4d3a  mov     [rbp+var_18], r15
0x1800c4d3e  test    r8, r8
0x1800c4d41  jnz     short loc_1800C4D7C
0x1800c4d43  mov     edi, 80070057h
0x1800c4d48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4d4f  jb      loc_1800C5272
0x1800c4d55  lea     edx, [r8+15h]
0x1800c4d59  mov     dword ptr [rsp+80h+var_60], edi
0x1800c4d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4d64  lea     r8, WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids
0x1800c4d6b  mov     r9, rbx
0x1800c4d6e  mov     rcx, [rcx+10h]
0x1800c4d72  call    WPP_SF_qD
0x1800c4d77  jmp     loc_1800C5235
0x1800c4d7c  mov     rax, [r8]
0x1800c4d7f  lea     rdx, [rbp+var_28]
0x1800c4d83  mov     rcx, rsi
0x1800c4d86  mov     rax, [rax+120h]
0x1800c4d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4d92  mov     edi, eax
0x1800c4d94  test    eax, eax
0x1800c4d96  jns     short loc_1800C4DB0
0x1800c4d98  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4d9f  jb      loc_1800C5235
0x1800c4da5  mov     edx, 16h
0x1800c4daa  mov     dword ptr [rsp+80h+var_60], eax
0x1800c4dae  jmp     short loc_1800C4D5D
0x1800c4db0  mov     rcx, [rbp+var_28]
0x1800c4db4  lea     rdx, [rbp+cInitialSize]
0x1800c4db8  mov     rax, [rcx]
0x1800c4dbb  mov     rax, [rax+0F0h]
0x1800c4dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4dc7  mov     edi, eax
0x1800c4dc9  test    eax, eax
0x1800c4dcb  jns     short loc_1800C4DE1
0x1800c4dcd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4dd4  jb      loc_1800C5235
0x1800c4dda  mov     edx, 17h
0x1800c4ddf  jmp     short loc_1800C4DAA
0x1800c4de1  mov     rax, [rsi]
0x1800c4de4  lea     r9, [rbp+var_10]
0x1800c4de8  lea     r8, _GUID_28f54685_06fd_11d2_b27a_00a0c9223196
0x1800c4def  mov     rcx, rsi
0x1800c4df2  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x1800c4df9  mov     rax, [rax+0E0h]
0x1800c4e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4e05  mov     edi, eax
0x1800c4e07  test    eax, eax
0x1800c4e09  jns     short loc_1800C4E1F
0x1800c4e0b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4e12  jb      loc_1800C5235
0x1800c4e18  mov     edx, 18h
0x1800c4e1d  jmp     short loc_1800C4DAA
0x1800c4e1f  mov     rax, [rsi]
0x1800c4e22  lea     rcx, [rbp+var_8]
0x1800c4e26  mov     [rsp+80h+var_60], rcx
0x1800c4e2b  lea     r9, _GUID_28f54685_06fd_11d2_b27a_00a0c9223196
0x1800c4e32  lea     r8, _GUID_00000000_0000_0000_0000_000000000000
0x1800c4e39  mov     edx, r14d
0x1800c4e3c  mov     rcx, rsi
0x1800c4e3f  mov     rax, [rax+128h]
0x1800c4e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4e4b  mov     rax, [rsi]
0x1800c4e4e  lea     r8, [rbp+var_20]
0x1800c4e52  mov     edx, r14d
0x1800c4e55  mov     rcx, rsi
0x1800c4e58  mov     rax, [rax+48h]
0x1800c4e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4e61  mov     edi, eax
0x1800c4e63  test    eax, eax
0x1800c4e65  jns     short loc_1800C4E7E
0x1800c4e67  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4e6e  jb      loc_1800C5235
0x1800c4e74  mov     edx, 19h
0x1800c4e79  jmp     loc_1800C4DAA
0x1800c4e7e  mov     rcx, [rbp+var_20]
0x1800c4e82  lea     rdx, [rbp+arg_18]
0x1800c4e86  mov     rax, [rcx]
0x1800c4e89  mov     rax, [rax+0F0h]
0x1800c4e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4e95  mov     edi, eax
0x1800c4e97  test    eax, eax
0x1800c4e99  jns     short loc_1800C4EB2
0x1800c4e9b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4ea2  jb      loc_1800C5235
0x1800c4ea8  mov     edx, 1Ah
0x1800c4ead  jmp     loc_1800C4DAA
0x1800c4eb2  mov     edx, [rbp+arg_18]
0x1800c4eb5  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x1800c4eb9  add     edx, 3; cInitialSize
0x1800c4ebc  call    cs:__imp_MFCreateAttributes
0x1800c4ec2  mov     edi, eax
0x1800c4ec4  test    eax, eax
0x1800c4ec6  jns     short loc_1800C4EDF
0x1800c4ec8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4ecf  jb      loc_1800C5235
0x1800c4ed5  mov     edx, 1Bh
0x1800c4eda  jmp     loc_1800C4DAA
0x1800c4edf  mov     edx, [rbp+cInitialSize]; cInitialSize
0x1800c4ee2  lea     rcx, [rbp+var_30]; ppMFAttributes
0x1800c4ee6  call    cs:__imp_MFCreateAttributes
0x1800c4eec  mov     edi, eax
0x1800c4eee  test    eax, eax
0x1800c4ef0  jns     short loc_1800C4F09
0x1800c4ef2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4ef9  jb      loc_1800C5235
0x1800c4eff  mov     edx, 1Ch
0x1800c4f04  jmp     loc_1800C4DAA
0x1800c4f09  mov     rcx, [rbp+var_20]
0x1800c4f0d  mov     rdx, [rbp+ppMFAttributes]
0x1800c4f11  mov     rax, [rcx]
0x1800c4f14  mov     rax, [rax+100h]
0x1800c4f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4f20  mov     edi, eax
0x1800c4f22  test    eax, eax
0x1800c4f24  jns     short loc_1800C4F3D
0x1800c4f26  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4f2d  jb      loc_1800C5235
0x1800c4f33  mov     edx, 1Dh
0x1800c4f38  jmp     loc_1800C4DAA
0x1800c4f3d  mov     rcx, [rbp+var_28]
0x1800c4f41  mov     rdx, [rbp+var_30]
0x1800c4f45  mov     rax, [rcx]
0x1800c4f48  mov     rax, [rax+100h]
0x1800c4f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4f54  mov     edi, eax
0x1800c4f56  test    eax, eax
0x1800c4f58  jns     short loc_1800C4F71
0x1800c4f5a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4f61  jb      loc_1800C5235
0x1800c4f67  mov     edx, 1Eh
0x1800c4f6c  jmp     loc_1800C4DAA
0x1800c4f71  mov     rcx, [rbp+ppMFAttributes]
0x1800c4f75  lea     rdx, MF_DEVICESTREAM_FILTER_KSCONTROL
0x1800c4f7c  mov     r8, [rbp+var_10]
0x1800c4f80  mov     rax, [rcx]
0x1800c4f83  mov     rax, [rax+0D8h]
0x1800c4f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4f8f  mov     edi, eax
0x1800c4f91  test    eax, eax
0x1800c4f93  jns     short loc_1800C4FAC
0x1800c4f95  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4f9c  jb      loc_1800C5235
0x1800c4fa2  mov     edx, 1Fh
0x1800c4fa7  jmp     loc_1800C4DAA
0x1800c4fac  mov     r8, [rbp+var_8]
0x1800c4fb0  test    r8, r8
0x1800c4fb3  jz      short loc_1800C4FEC
0x1800c4fb5  mov     rcx, [rbp+ppMFAttributes]
0x1800c4fb9  lea     rdx, MF_DEVICESTREAM_PIN_KSCONTROL
0x1800c4fc0  mov     rax, [rcx]
0x1800c4fc3  mov     rax, [rax+0D8h]
0x1800c4fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4fcf  mov     edi, eax
0x1800c4fd1  test    eax, eax
0x1800c4fd3  jns     short loc_1800C4FEC
0x1800c4fd5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4fdc  jb      loc_1800C5235
0x1800c4fe2  mov     edx, 20h ; ' '
0x1800c4fe7  jmp     loc_1800C4DAA
0x1800c4fec  mov     rcx, [rbp+ppMFAttributes]
0x1800c4ff0  lea     rdx, MF_DEVICESTREAM_SOURCE_ATTRIBUTES
0x1800c4ff7  mov     r8, [rbp+var_30]
0x1800c4ffb  mov     rax, [rcx]
0x1800c4ffe  mov     rax, [rax+0D8h]
0x1800c5005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c500a  mov     edi, eax
0x1800c500c  test    eax, eax
0x1800c500e  jns     short loc_1800C5027
0x1800c5010  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c5017  jb      loc_1800C5235
0x1800c501d  mov     edx, 21h ; '!'
0x1800c5022  jmp     loc_1800C4DAA
0x1800c5027  mov     rcx, [rbp+ppMFAttributes]
0x1800c502b  lea     rdx, MF_DEVICESTREAM_STREAM_ID
0x1800c5032  mov     r8d, [rbx+38h]
0x1800c5036  mov     rax, [rcx]
0x1800c5039  mov     rax, [rax+0A8h]
0x1800c5040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5045  mov     edi, eax
0x1800c5047  test    eax, eax
0x1800c5049  jns     short loc_1800C5062
0x1800c504b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c5052  jb      loc_1800C5235
0x1800c5058  mov     edx, 22h ; '"'
0x1800c505d  jmp     loc_1800C4DAA
0x1800c5062  mov     rax, [rsi]
0x1800c5065  lea     r9, [rbp+pv]
0x1800c5069  lea     r8, [rbp+arg_10]
0x1800c506d  mov     edx, r14d
0x1800c5070  mov     rcx, rsi
0x1800c5073  mov     rax, [rax+50h]
0x1800c5077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c507c  mov     edi, eax
0x1800c507e  test    eax, eax
0x1800c5080  jns     short loc_1800C5099
0x1800c5082  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c5089  jb      loc_1800C5235
0x1800c508f  mov     edx, 23h ; '#'
0x1800c5094  jmp     loc_1800C4DAA
0x1800c5099  mov     rax, [rsi]
0x1800c509c  lea     r8, [rbp+var_18]
0x1800c50a0  mov     edx, r14d
0x1800c50a3  mov     rcx, rsi
0x1800c50a6  mov     rax, [rax+60h]
0x1800c50aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c50af  mov     edi, eax
0x1800c50b1  test    eax, eax
0x1800c50b3  jns     short loc_1800C50CC
0x1800c50b5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c50bc  jb      loc_1800C5235
0x1800c50c2  mov     edx, 24h ; '$'
0x1800c50c7  jmp     loc_1800C4DAA
0x1800c50cc  lea     rcx, [rbx+30h]; ppMFType
0x1800c50d0  call    cs:__imp_MFCreateMediaType
0x1800c50d6  mov     edi, eax
0x1800c50d8  test    eax, eax
0x1800c50da  jns     short loc_1800C50F3
0x1800c50dc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c50e3  jb      loc_1800C5235
0x1800c50e9  mov     edx, 25h ; '%'
0x1800c50ee  jmp     loc_1800C4DAA
0x1800c50f3  mov     rcx, [rbp+var_18]
0x1800c50f7  mov     rdx, [rbx+30h]
0x1800c50fb  mov     rax, [rcx]
0x1800c50fe  mov     rax, [rax+100h]
0x1800c5105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c510a  mov     edi, eax
0x1800c510c  test    eax, eax
0x1800c510e  jns     short loc_1800C5127
0x1800c5110  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c5117  jb      loc_1800C5235
0x1800c511d  mov     edx, 26h ; '&'
0x1800c5122  jmp     loc_1800C4DAA
0x1800c5127  mov     esi, r15d
0x1800c512a  cmp     esi, [rbp+arg_10]
0x1800c512d  jnb     loc_1800C51E8
0x1800c5133  lea     rcx, [rbp+ppMFType]; ppMFType
0x1800c5137  mov     [rbp+ppMFType], r15
0x1800c513b  call    cs:__imp_MFCreateMediaType
0x1800c5141  mov     edi, eax
0x1800c5143  test    eax, eax
0x1800c5145  js      short loc_1800C51B1
0x1800c5147  mov     rax, [rbp+pv]
0x1800c514b  mov     rdx, [rbp+ppMFType]
0x1800c514f  mov     ecx, esi
0x1800c5151  mov     rcx, [rax+rcx*8]
0x1800c5155  mov     rax, [rcx]
0x1800c5158  mov     rax, [rax+100h]
0x1800c515f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5164  mov     edi, eax
0x1800c5166  test    eax, eax
0x1800c5168  js      short loc_1800C51A1
0x1800c516a  mov     rdx, [rbp+ppMFType]
0x1800c516e  lea     rcx, [rbx+18h]
0x1800c5172  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x1800c5177  test    eax, eax
0x1800c5179  jz      short loc_1800C5188
0x1800c517b  lea     rcx, [rbp+ppMFType]; void *
0x1800c517f  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800c5184  inc     esi
0x1800c5186  jmp     short loc_1800C512A
0x1800c5188  mov     edi, 8007000Eh
0x1800c518d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c5194  jb      short loc_1800C51DD
0x1800c5196  mov     edx, 29h ; ')'
0x1800c519b  mov     dword ptr [rsp+80h+var_60], edi
0x1800c519f  jmp     short loc_1800C51C3
0x1800c51a1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c51a8  jb      short loc_1800C51DD
0x1800c51aa  mov     edx, 28h ; '('
0x1800c51af  jmp     short loc_1800C51BF
0x1800c51b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c51b8  jb      short loc_1800C51DD
0x1800c51ba  mov     edx, 27h ; '''
0x1800c51bf  mov     dword ptr [rsp+80h+var_60], eax
0x1800c51c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c51ca  lea     r8, WPP_ae6d943f78d63f0fc67385511c76e394_Traceguids
  ... truncated ...
```
