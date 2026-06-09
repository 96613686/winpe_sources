# SensorGroupClassFactory::GetSensorGroupAttributesFromId(ushort const *,IMFAttributes * *)

- ea: `0x1800299e0`
- end: `0x18002a086`
- name: `?GetSensorGroupAttributesFromId@SensorGroupClassFactory@@UEAAJPEBGPEAPEAUIMFAttributes@@@Z`
- size: `1702`
- prototype: `int(SensorGroupClassFactory *__hidden this, const unsigned __int16 *, struct IMFAttributes **)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x18000c348`
- `0x180015e80`
- `0x1800299e0`
- `0x18002a530`
- `0x18002d02c`
- `0x180044f30`
- `0x180045900`
- `0x180077010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180029f5b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180029f76`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180029f5b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180029f76`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180029ce6`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180029ce6`
- `MFPlat!MFCreateAttributes` at `0x180029afd`
- `MFPlat!MFCreateAttributes` at `0x180029afd`

## pseudocode

```c
__int64 __fastcall SensorGroupClassFactory::GetSensorGroupAttributesFromId(
        SensorGroupClassFactory *this,
        const char *a2,
        struct IMFAttributes **a3)
{
  const char *v6; // r9
  int v7; // ebx
  __int64 v8; // rdx
  HRESULT v9; // eax
  __int64 v10; // rdx
  struct IMFSensorGroupIdManager *v11; // rcx
  __int64 (__fastcall ***v12)(__int64, GUID *, __int64 *); // rcx
  struct IMFSensorGroupIdManager *v13; // rbx
  __int64 v14; // rax
  __int64 (__fastcall *v15)(struct IMFSensorGroupIdManager *, _QWORD, _QWORD, __int64 *); // r14
  __int64 v16; // rcx
  __int64 (__fastcall ***v17)(__int64, GUID *, __int64 *); // rbx
  __int64 (__fastcall **v18)(__int64, GUID *, __int64 *); // rax
  __int64 (__fastcall *v19)(__int64, GUID *, __int64 *); // r14
  unsigned int v20; // r14d
  __int64 v21; // rdx
  IMFAttributes *ppMFAttributes; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v26)(__int64, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  ULONG PropertyBufferSize; // [rsp+60h] [rbp-A0h] BYREF
  struct IMFSensorGroupIdManager *v28; // [rsp+68h] [rbp-98h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+70h] [rbp-90h] BYREF
  BYTE PropertyBuffer[16]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v31; // [rsp+88h] [rbp-78h]
  _BYTE v32[40]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v33[264]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v34[528]; // [rsp+2D0h] [rbp+1D0h] BYREF

  memset_0(v34, 0, 0x208u);
  v28 = 0;
  v26 = 0;
  v24 = 0;
  ppMFAttributes = 0;
  *(_OWORD *)PropertyBuffer = 0;
  PropertyType = 0;
  v31 = 0;
  PropertyBufferSize = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v6 = a2;
    if ( !a2 )
      v6 = L"<nullptr>";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 91, &WPP_09150840c5f230171d137cf28cc6c946_Traceguids, v6);
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    if ( g_wppLevels )
    {
      v8 = 92;
LABEL_50:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        &WPP_09150840c5f230171d137cf28cc6c946_Traceguids,
        (char *)this - 8,
        v7);
      goto LABEL_51;
    }
    goto LABEL_51;
  }
  if ( !a3 )
  {
    v7 = -2147467261;
    if ( g_wppLevels )
    {
      v8 = 93;
      goto LABEL_50;
    }
LABEL_51:
    if ( !byte_18008D62D )
      goto LABEL_76;
    v21 = 109;
    goto LABEL_75;
  }
  *a3 = 0;
  ppMFAttributes = 0;
  v9 = MFCreateAttributes(&ppMFAttributes, 3u);
  v7 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 94;
LABEL_14:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      &WPP_09150840c5f230171d137cf28cc6c946_Traceguids,
      (char *)this - 8,
      v9);
    goto LABEL_51;
  }
  v11 = v28;
  v28 = 0;
  if ( v11 )
    (*(void (__fastcall **)(struct IMFSensorGroupIdManager *))(*(_QWORD *)v11 + 16LL))(v11);
  v9 = SensorGroupIdManager::CreateSensorGroupIdManager(&v28);
  v7 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 95;
    goto LABEL_14;
  }
  v12 = v26;
  v13 = v28;
  v14 = *(_QWORD *)v28;
  v26 = 0;
  v15 = *(__int64 (__fastcall **)(struct IMFSensorGroupIdManager *, _QWORD, _QWORD, __int64 *))(v14 + 32);
  if ( v12 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v12)[2])(v12);
  v9 = v15(v13, 0, 0, (__int64 *)&v26);
  v7 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 96;
    goto LABEL_14;
  }
  v16 = v24;
  v17 = v26;
  v18 = *v26;
  v24 = 0;
  v19 = *v18;
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  v9 = v19((__int64)v17, &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7, &v24);
  v7 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 97;
    goto LABEL_14;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)v24 + 64LL))(v24, a2);
  v7 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 98;
    goto LABEL_14;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, 0);
  v7 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 99;
    goto LABEL_14;
  }
  v9 = (*v26)[4]((__int64)v26, (GUID *)v32, (__int64 *)32);
  v7 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v10 = 100;
    goto LABEL_14;
  }
  PropertyBufferSize = 32;
  *(_OWORD *)PropertyBuffer = 0;
  v31 = 0;
  if ( CM_Get_Device_Interface_PropertyW(
         (LPCWSTR)a2,
         &DEVPKEY_DeviceInterface_FrameServerUniqueID,
         &PropertyType,
         PropertyBuffer,
         &PropertyBufferSize,
         0) )
  {
    memset_0(v33, 0, 0x208u);
    v25 = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, _BYTE *, int, int *))(*(_QWORD *)v24 + 200LL))(
           v24,
           0,
           4,
           v34,
           520,
           &v25) < 0 )
    {
      if ( wcsstr((const wchar_t *)a2, L"MF_DEVSOURCE_ATTRIBUTE_SOURCE_STREAM_URL")
        || (v20 = 0x8000, wcsstr((const wchar_t *)a2, L"MF_DEVSOURCE_ATTRIBUTE_SOURCE_XADDRESS")) )
      {
        v20 = 1;
        v9 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _BYTE *, __int64))ppMFAttributes->lpVtbl->SetBlob)(
               ppMFAttributes,
               MF_SENSORGROUPID_HASHBLOB,
               v32,
               32);
        v7 = v9;
        if ( v9 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_51;
          v10 = 107;
          goto LABEL_14;
        }
      }
    }
    else
    {
      v25 = 0;
      if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, unsigned __int16 *, int, int *))(*(_QWORD *)v24 + 200LL))(
             v24,
             0,
             7,
             v33,
             520,
             &v25) < 0 )
      {
        v9 = StringCchCopyW(v33, 0x104u, L"Unknown Device");
        v7 = v9;
        if ( v9 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_51;
          v10 = 103;
          goto LABEL_14;
        }
      }
      v9 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _BYTE *, __int64))ppMFAttributes->lpVtbl->SetBlob)(
             ppMFAttributes,
             MF_SENSORGROUPID_HASHBLOB,
             v32,
             32);
      v7 = v9;
      if ( v9 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_51;
        v10 = 104;
        goto LABEL_14;
      }
      v9 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, unsigned __int16 *))ppMFAttributes->lpVtbl->SetString)(
             ppMFAttributes,
             &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
             v33);
      v7 = v9;
      if ( v9 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_51;
        v10 = 105;
        goto LABEL_14;
      }
      v9 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, _BYTE *))ppMFAttributes->lpVtbl->SetString)(
             ppMFAttributes,
             &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
             v34);
      v7 = v9;
      if ( v9 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_51;
        v10 = 106;
        goto LABEL_14;
      }
      v20 = 0;
    }
  }
  else
  {
    v9 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, BYTE *, __int64))ppMFAttributes->lpVtbl->SetBlob)(
           ppMFAttributes,
           MF_SENSORGROUPID_HASHBLOB,
           PropertyBuffer,
           32);
    v7 = v9;
    if ( v9 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_51;
      v10 = 101;
      goto LABEL_14;
    }
    v9 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, const char *))ppMFAttributes->lpVtbl->SetString)(
           ppMFAttributes,
           &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
           a2);
    v7 = v9;
    if ( v9 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_51;
      v10 = 102;
      goto LABEL_14;
    }
    v20 = 1;
  }
  v7 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
         ppMFAttributes,
         MF_SENSORGROUPID_IDTYPE,
         v20);
  if ( v7 < 0 )
  {
    if ( g_wppLevels )
    {
      v8 = 108;
      goto LABEL_50;
    }
    goto LABEL_51;
  }
  *a3 = ppMFAttributes;
  ppMFAttributes = 0;
  if ( (unsigned __int8)byte_18008D62D < 8u )
    goto LABEL_76;
  v21 = 110;
LABEL_75:
  WPP_SF_d(
    *((_QWORD *)WPP_GLOBAL_Control + 27),
    v21,
    &WPP_09150840c5f230171d137cf28cc6c946_Traceguids,
    (unsigned int)v7);
LABEL_76:
  if ( ppMFAttributes )
    ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v26 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v26)[2])(v26);
  if ( v28 )
    (*(void (__fastcall **)(struct IMFSensorGroupIdManager *))(*(_QWORD *)v28 + 16LL))(v28);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800299e0  mov     [rsp-8+arg_18], rbx
0x1800299e5  push    rbp
0x1800299e6  push    rsi
0x1800299e7  push    rdi
0x1800299e8  push    r12
0x1800299ea  push    r13
0x1800299ec  push    r14
0x1800299ee  push    r15
0x1800299f0  lea     rbp, [rsp-3F0h]
0x1800299f8  sub     rsp, 4F0h
0x1800299ff  mov     rax, cs:__security_cookie
0x180029a06  xor     rax, rsp
0x180029a09  mov     [rbp+420h+var_40], rax
0x180029a10  mov     r15, r8
0x180029a13  mov     rsi, rdx
0x180029a16  mov     rdi, rcx
0x180029a19  xor     edx, edx; Val
0x180029a1b  mov     r8d, 208h; Size
0x180029a21  lea     rcx, [rbp+420h+var_250]; void *
0x180029a28  call    memset_0
0x180029a2d  xor     r12d, r12d
0x180029a30  xorps   xmm0, xmm0
0x180029a33  mov     [rsp+520h+var_4B8], r12
0x180029a38  mov     [rsp+520h+var_4C8], r12
0x180029a3d  mov     [rsp+520h+var_4D8], r12
0x180029a42  mov     [rsp+520h+ppMFAttributes], r12
0x180029a47  movups  xmmword ptr [rsp+520h+PropertyBuffer], xmm0
0x180029a4c  mov     [rsp+520h+PropertyType], r12d
0x180029a51  movups  [rbp+420h+var_498], xmm0
0x180029a55  mov     [rsp+520h+var_4C0], r12d
0x180029a5a  cmp     cs:byte_18008D62D, 8
0x180029a61  lea     r13, WPP_09150840c5f230171d137cf28cc6c946_Traceguids
0x180029a68  jb      short loc_180029A96
0x180029a6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a71  lea     rax, aNullptr; "<nullptr>"
0x180029a78  test    rsi, rsi
0x180029a7b  lea     edx, [r12+5Bh]
0x180029a80  mov     r9, rsi
0x180029a83  mov     r8, r13
0x180029a86  cmovz   r9, rax
0x180029a8a  mov     rcx, [rcx+0D8h]
0x180029a91  call    WPP_SF_S
0x180029a96  test    rsi, rsi
0x180029a99  jnz     short loc_180029AB5
0x180029a9b  mov     ebx, 80070057h
0x180029aa0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029aa7  jb      loc_180029DC2
0x180029aad  lea     edx, [rsi+5Ch]
0x180029ab0  jmp     loc_180029DA7
0x180029ab5  test    r15, r15
0x180029ab8  jnz     short loc_180029AD5
0x180029aba  mov     ebx, 80004003h
0x180029abf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029ac6  jb      loc_180029DC2
0x180029acc  lea     edx, [r15+5Dh]
0x180029ad0  jmp     loc_180029DA7
0x180029ad5  mov     rcx, [rsp+520h+ppMFAttributes]
0x180029ada  mov     [r15], r12
0x180029add  mov     [rsp+520h+ppMFAttributes], r12
0x180029ae2  test    rcx, rcx
0x180029ae5  jz      short loc_180029AF3
0x180029ae7  mov     rax, [rcx]
0x180029aea  mov     rax, [rax+10h]
0x180029aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029af3  mov     edx, 3; cInitialSize
0x180029af8  lea     rcx, [rsp+520h+ppMFAttributes]; ppMFAttributes
0x180029afd  call    cs:__imp_MFCreateAttributes
0x180029b03  mov     ebx, eax
0x180029b05  test    eax, eax
0x180029b07  jns     short loc_180029B24
0x180029b09  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029b10  jb      loc_180029DC2
0x180029b16  mov     edx, 5Eh ; '^'
0x180029b1b  mov     dword ptr [rsp+520h+PropertyBufferSize], eax
0x180029b1f  jmp     loc_180029DAB
0x180029b24  mov     rcx, [rsp+520h+var_4B8]
0x180029b29  mov     [rsp+520h+var_4B8], r12
0x180029b2e  test    rcx, rcx
0x180029b31  jz      short loc_180029B3F
0x180029b33  mov     rax, [rcx]
0x180029b36  mov     rax, [rax+10h]
0x180029b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b3f  lea     rcx, [rsp+520h+var_4B8]; struct IMFSensorGroupIdManager **
0x180029b44  call    ?CreateSensorGroupIdManager@SensorGroupIdManager@@SAJPEAPEAUIMFSensorGroupIdManager@@@Z; SensorGroupIdManager::CreateSensorGroupIdManager(IMFSensorGroupIdManager * *)
0x180029b49  mov     ebx, eax
0x180029b4b  test    eax, eax
0x180029b4d  jns     short loc_180029B63
0x180029b4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029b56  jb      loc_180029DC2
0x180029b5c  mov     edx, 5Fh ; '_'
0x180029b61  jmp     short loc_180029B1B
0x180029b63  mov     rcx, [rsp+520h+var_4C8]
0x180029b68  mov     rbx, [rsp+520h+var_4B8]
0x180029b6d  mov     rax, [rbx]
0x180029b70  mov     [rsp+520h+var_4C8], r12
0x180029b75  mov     r14, [rax+20h]
0x180029b79  test    rcx, rcx
0x180029b7c  jz      short loc_180029B8A
0x180029b7e  mov     rdx, [rcx]
0x180029b81  mov     rax, [rdx+10h]
0x180029b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b8a  lea     r9, [rsp+520h+var_4C8]
0x180029b8f  xor     r8d, r8d
0x180029b92  xor     edx, edx
0x180029b94  mov     rcx, rbx
0x180029b97  mov     rax, r14
0x180029b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b9f  mov     ebx, eax
0x180029ba1  test    eax, eax
0x180029ba3  jns     short loc_180029BBC
0x180029ba5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029bac  jb      loc_180029DC2
0x180029bb2  mov     edx, 60h ; '`'
0x180029bb7  jmp     loc_180029B1B
0x180029bbc  mov     rcx, [rsp+520h+var_4D8]
0x180029bc1  mov     rbx, [rsp+520h+var_4C8]
0x180029bc6  mov     rax, [rbx]
0x180029bc9  mov     [rsp+520h+var_4D8], r12
0x180029bce  mov     r14, [rax]
0x180029bd1  test    rcx, rcx
0x180029bd4  jz      short loc_180029BE2
0x180029bd6  mov     rdx, [rcx]
0x180029bd9  mov     rax, [rdx+10h]
0x180029bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029be2  lea     r8, [rsp+520h+var_4D8]
0x180029be7  mov     rcx, rbx
0x180029bea  lea     rdx, _GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7
0x180029bf1  mov     rax, r14
0x180029bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bf9  mov     ebx, eax
0x180029bfb  test    eax, eax
0x180029bfd  jns     short loc_180029C16
0x180029bff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029c06  jb      loc_180029DC2
0x180029c0c  mov     edx, 61h ; 'a'
0x180029c11  jmp     loc_180029B1B
0x180029c16  mov     rcx, [rsp+520h+var_4D8]
0x180029c1b  mov     rdx, rsi
0x180029c1e  mov     rax, [rcx]
0x180029c21  mov     rax, [rax+40h]
0x180029c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c2a  mov     ebx, eax
0x180029c2c  test    eax, eax
0x180029c2e  jns     short loc_180029C47
0x180029c30  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029c37  jb      loc_180029DC2
0x180029c3d  mov     edx, 62h ; 'b'
0x180029c42  jmp     loc_180029B1B
0x180029c47  mov     rcx, [rsp+520h+var_4D8]
0x180029c4c  xor     edx, edx
0x180029c4e  mov     rax, [rcx]
0x180029c51  mov     rax, [rax+48h]
0x180029c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c5a  mov     ebx, eax
0x180029c5c  test    eax, eax
0x180029c5e  jns     short loc_180029C77
0x180029c60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029c67  jb      loc_180029DC2
0x180029c6d  mov     edx, 63h ; 'c'
0x180029c72  jmp     loc_180029B1B
0x180029c77  mov     rcx, [rsp+520h+var_4C8]
0x180029c7c  lea     rdx, [rbp+420h+var_488]
0x180029c80  xor     r9d, r9d
0x180029c83  mov     rax, [rcx]
0x180029c86  lea     r14d, [r9+20h]
0x180029c8a  mov     r8d, r14d
0x180029c8d  mov     rax, [rax+20h]
0x180029c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c96  mov     ebx, eax
0x180029c98  test    eax, eax
0x180029c9a  jns     short loc_180029CB2
0x180029c9c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029ca3  jb      loc_180029DC2
0x180029ca9  lea     edx, [r14+44h]
0x180029cad  jmp     loc_180029B1B
0x180029cb2  xorps   xmm0, xmm0
0x180029cb5  mov     [rsp+520h+ulFlags], r12d; ulFlags
0x180029cba  lea     rax, [rsp+520h+var_4C0]
0x180029cbf  mov     [rsp+520h+var_4C0], r14d
0x180029cc4  lea     r9, [rsp+520h+PropertyBuffer]; PropertyBuffer
0x180029cc9  mov     [rsp+520h+PropertyBufferSize], rax; PropertyBufferSize
0x180029cce  lea     r8, [rsp+520h+PropertyType]; PropertyType
0x180029cd3  mov     rcx, rsi; pszDeviceInterface
0x180029cd6  lea     rdx, DEVPKEY_DeviceInterface_FrameServerUniqueID; PropertyKey
0x180029cdd  movups  xmmword ptr [rsp+520h+PropertyBuffer], xmm0
0x180029ce2  movups  [rbp+420h+var_498], xmm0
0x180029ce6  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x180029cec  test    eax, eax
0x180029cee  jnz     loc_180029DD9
0x180029cf4  mov     rcx, [rsp+520h+ppMFAttributes]
0x180029cf9  lea     r8, [rsp+520h+PropertyBuffer]
0x180029cfe  mov     r9d, r14d
0x180029d01  lea     rdx, MF_SENSORGROUPID_HASHBLOB
0x180029d08  mov     rax, [rcx]
0x180029d0b  mov     rax, [rax+0D0h]
0x180029d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d17  mov     ebx, eax
0x180029d19  test    eax, eax
0x180029d1b  jns     short loc_180029D34
0x180029d1d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029d24  jb      loc_180029DC2
0x180029d2a  mov     edx, 65h ; 'e'
0x180029d2f  jmp     loc_180029B1B
0x180029d34  mov     rcx, [rsp+520h+ppMFAttributes]
0x180029d39  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x180029d40  mov     r8, rsi
0x180029d43  mov     rax, [rcx]
0x180029d46  mov     rax, [rax+0C8h]
0x180029d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d52  mov     ebx, eax
0x180029d54  test    eax, eax
0x180029d56  jns     short loc_180029D6B
0x180029d58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029d5f  jb      short loc_180029DC2
0x180029d61  mov     edx, 66h ; 'f'
0x180029d66  jmp     loc_180029B1B
0x180029d6b  mov     r14d, 1
0x180029d71  mov     rcx, [rsp+520h+ppMFAttributes]
0x180029d76  lea     rdx, MF_SENSORGROUPID_IDTYPE
0x180029d7d  mov     r8d, r14d
0x180029d80  mov     rax, [rcx]
0x180029d83  mov     rax, [rax+0A8h]
0x180029d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d8f  mov     ebx, eax
0x180029d91  test    eax, eax
0x180029d93  jns     loc_180029FCE
0x180029d99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029da0  jb      short loc_180029DC2
0x180029da2  mov     edx, 6Ch ; 'l'
0x180029da7  mov     dword ptr [rsp+520h+PropertyBufferSize], ebx
0x180029dab  mov     rcx, cs:WPP_GLOBAL_Control
0x180029db2  lea     r9, [rdi-8]
0x180029db6  mov     r8, r13
0x180029db9  mov     rcx, [rcx+10h]
0x180029dbd  call    WPP_SF_qD
0x180029dc2  cmp     cs:byte_18008D62D, 1
0x180029dc9  jb      loc_18002A002
0x180029dcf  mov     edx, 6Dh ; 'm'
0x180029dd4  jmp     loc_180029FE9
0x180029dd9  mov     ebx, 208h
0x180029dde  lea     rcx, [rbp+420h+var_460]; void *
0x180029de2  mov     r8d, ebx; Size
0x180029de5  xor     edx, edx; Val
0x180029de7  call    memset_0
0x180029dec  mov     rcx, [rsp+520h+var_4D8]
0x180029df1  lea     rdx, [rsp+520h+var_4D0]
0x180029df6  mov     qword ptr [rsp+520h+ulFlags], rdx
0x180029dfb  lea     r9, [rbp+420h+var_250]
0x180029e02  mov     [rsp+520h+var_4D0], r12d
0x180029e07  xor     edx, edx
0x180029e09  mov     dword ptr [rsp+520h+PropertyBufferSize], ebx
0x180029e0d  mov     rax, [rcx]
0x180029e10  lea     r8d, [rdx+4]
0x180029e14  mov     rax, [rax+0C8h]
0x180029e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e20  test    eax, eax
0x180029e22  js      loc_180029F51
0x180029e28  mov     rcx, [rsp+520h+var_4D8]
0x180029e2d  lea     rdx, [rsp+520h+var_4D0]
0x180029e32  mov     qword ptr [rsp+520h+ulFlags], rdx
0x180029e37  lea     r9, [rbp+420h+var_460]
0x180029e3b  mov     [rsp+520h+var_4D0], r12d
0x180029e40  xor     edx, edx
0x180029e42  mov     dword ptr [rsp+520h+PropertyBufferSize], ebx
0x180029e46  mov     rax, [rcx]
0x180029e49  lea     r8d, [rdx+7]
0x180029e4d  mov     rax, [rax+0C8h]
0x180029e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e59  test    eax, eax
0x180029e5b  jns     short loc_180029E8F
0x180029e5d  lea     r8, aUnknownDevice; "Unknown Device"
0x180029e64  mov     edx, 104h; unsigned __int64
0x180029e69  lea     rcx, [rbp+420h+var_460]; unsigned __int16 *
0x180029e6d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029e72  mov     ebx, eax
0x180029e74  test    eax, eax
0x180029e76  jns     short loc_180029E8F
0x180029e78  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029e7f  jb      loc_180029DC2
0x180029e85  mov     edx, 67h ; 'g'
0x180029e8a  jmp     loc_180029B1B
0x180029e8f  mov     rcx, [rsp+520h+ppMFAttributes]
0x180029e94  lea     r8, [rbp+420h+var_488]
0x180029e98  mov     r9d, r14d
0x180029e9b  lea     rdx, MF_SENSORGROUPID_HASHBLOB
0x180029ea2  mov     rax, [rcx]
0x180029ea5  mov     rax, [rax+0D0h]
0x180029eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029eb1  mov     ebx, eax
0x180029eb3  test    eax, eax
0x180029eb5  jns     short loc_180029ECE
0x180029eb7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029ebe  jb      loc_180029DC2
0x180029ec4  mov     edx, 68h ; 'h'
0x180029ec9  jmp     loc_180029B1B
0x180029ece  mov     rcx, [rsp+520h+ppMFAttributes]
0x180029ed3  lea     r8, [rbp+420h+var_460]
0x180029ed7  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME
0x180029ede  mov     rax, [rcx]
0x180029ee1  mov     rax, [rax+0C8h]
  ... truncated ...
```
