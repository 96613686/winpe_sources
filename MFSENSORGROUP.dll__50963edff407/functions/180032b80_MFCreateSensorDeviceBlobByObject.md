# MFCreateSensorDeviceBlobByObject

- ea: `0x180032b80`
- end: `0x180032ffb`
- name: `MFCreateSensorDeviceBlobByObject`
- size: `1147`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x180032b80`
- `0x180033004`
- `0x180076280`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032f9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032f9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032d21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032edd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032d21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032edd`

## pseudocode

```c
__int64 __fastcall MFCreateSensorDeviceBlobByObject(
        const struct _GUID *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        _DWORD *a5,
        _QWORD *a6,
        _DWORD *a7)
{
  int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rdx
  _DWORD *v14; // r12
  _DWORD *v15; // r14
  __int64 v16; // rsi
  _BYTE *v17; // rax
  void *v18; // rbx
  _BYTE *i; // rcx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdi
  __int64 v24; // rax
  __int64 (__fastcall *v25)(__int64, GUID *, GUID *, __int64 *); // rsi
  int v26; // eax
  __int64 v27; // r15
  _BYTE *v28; // rax
  void *v29; // rsi
  _BYTE *j; // rcx
  __int64 v31; // rcx
  int v32; // eax
  int v34; // [rsp+40h] [rbp-38h] BYREF
  int v35; // [rsp+44h] [rbp-34h] BYREF
  __int64 v36; // [rsp+48h] [rbp-30h] BYREF
  __int64 *v37; // [rsp+50h] [rbp-28h] BYREF
  void *Src; // [rsp+58h] [rbp-20h] BYREF
  void *v39; // [rsp+60h] [rbp-18h] BYREF
  SIZE_T cb; // [rsp+C0h] [rbp+48h] BYREF

  v39 = 0;
  v34 = 0;
  LODWORD(cb) = 0;
  v35 = 0;
  Src = 0;
  if ( !a1 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( !g_wppLevels )
      return v12;
    v13 = 119;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( !g_wppLevels )
      return v12;
    v13 = 120;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    v11 = -2147024809;
    v12 = -2147024809;
    if ( !g_wppLevels )
      return v12;
    v13 = 121;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v11 = -2147467261;
    v12 = -2147467261;
    if ( !g_wppLevels )
      return v12;
    v13 = 122;
    goto LABEL_4;
  }
  v14 = a5;
  *a4 = 0;
  if ( !v14 )
  {
    v11 = -2147467261;
    v12 = -2147467261;
    if ( !g_wppLevels )
      return v12;
    v13 = 123;
    goto LABEL_4;
  }
  v15 = a7;
  *v14 = 0;
  if ( v15 )
    *v15 = 0;
  v11 = SensorDevice::CreateSensorDevice(a1, &v39);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( g_wppLevels )
    {
      v13 = 124;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v11);
      goto LABEL_68;
    }
    goto LABEL_68;
  }
  v11 = (*(__int64 (__fastcall **)(void *, const struct _GUID *, __int64, __int64, _DWORD, _QWORD, int *))(*(_QWORD *)v39 + 24LL))(
          v39,
          a1,
          a2,
          a3,
          0,
          0,
          &v35);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(void *, void **, int *))(*(_QWORD *)v39 + 64LL))(v39, &Src, &v34);
    v12 = v11;
    if ( v11 < 0 )
    {
      if ( g_wppLevels )
      {
        v13 = 126;
        goto LABEL_4;
      }
      goto LABEL_68;
    }
    v16 = v34;
    v17 = CoTaskMemAlloc(v34);
    v18 = v17;
    if ( !v17 )
    {
      v12 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          127,
          &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
          0,
          -2147024882);
      goto LABEL_68;
    }
    for ( i = &v17[v16]; v17 != i; ++v17 )
      *v17 = 0;
    memcpy_0(v18, Src, v34);
    Src = 0;
    if ( a6 )
    {
      v37 = 0;
      v36 = 0;
      if ( !v15 )
      {
        v20 = -2147467261;
        v12 = -2147467261;
        if ( !g_wppLevels )
        {
LABEL_64:
          wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v36);
          wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v37);
LABEL_65:
          CoTaskMemFree(v18);
          goto LABEL_68;
        }
        v21 = 128;
LABEL_35:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v20);
        goto LABEL_64;
      }
      v20 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v39)(
              v39,
              &GUID_fa993888_4383_415a_a930_dd472a8cf6f7,
              (__int64 *)&v37);
      v12 = v20;
      if ( v20 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_64;
        v21 = 129;
        goto LABEL_35;
      }
      v22 = v36;
      v23 = (__int64)v37;
      v24 = *v37;
      v36 = 0;
      v25 = *(__int64 (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(v24 + 24);
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v20 = v25(v23, &GUID_00000000_0000_0000_0000_000000000000, &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3, &v36);
      v12 = v20;
      if ( v20 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_64;
        v21 = 130;
        goto LABEL_35;
      }
      v20 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 104LL))(v36, 1);
      v12 = v20;
      if ( v20 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_64;
        v21 = 131;
        goto LABEL_35;
      }
      v26 = (*(__int64 (__fastcall **)(__int64, void **, SIZE_T *))(*(_QWORD *)v36 + 112LL))(v36, &Src, &cb);
      v12 = v26;
      if ( v26 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v26);
        if ( v36 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        if ( v37 )
          (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
        goto LABEL_65;
      }
      v27 = (unsigned int)cb;
      v28 = CoTaskMemAlloc((unsigned int)cb);
      v29 = v28;
      if ( !v28 )
      {
        v12 = -2147024882;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            133,
            &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
            0,
            -2147024882);
        goto LABEL_64;
      }
      for ( j = &v28[v27]; v28 != j; ++v28 )
        *v28 = 0;
      memcpy_0(v29, Src, (unsigned int)cb);
      v31 = v36;
      *a6 = v29;
      *v15 = cb;
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      if ( v37 )
        (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
    }
    v32 = v34;
    *a4 = v18;
    *v14 = v32;
    goto LABEL_68;
  }
  if ( g_wppLevels )
  {
    v13 = 125;
    goto LABEL_4;
  }
LABEL_68:
  if ( v39 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v39 + 16LL))(v39);
  return v12;
}

```

## disassembly

```asm
0x180032b80  push    rbp
0x180032b82  push    rbx
0x180032b83  push    rsi
0x180032b84  push    rdi
0x180032b85  push    r12
0x180032b87  push    r13
0x180032b89  push    r14
0x180032b8b  push    r15
0x180032b8d  mov     rbp, rsp
0x180032b90  sub     rsp, 78h
0x180032b94  xor     eax, eax
0x180032b96  mov     r13, r9
0x180032b99  mov     [rbp+var_18], rax
0x180032b9d  mov     rbx, r8
0x180032ba0  mov     [rbp+var_38], eax
0x180032ba3  mov     rsi, rdx
0x180032ba6  mov     dword ptr [rbp+cb], eax
0x180032ba9  mov     r15, rcx
0x180032bac  mov     [rbp+var_34], eax
0x180032baf  mov     [rbp+Src], rax
0x180032bb3  test    rcx, rcx
0x180032bb6  jnz     short loc_180032BD8
0x180032bb8  mov     eax, 80070057h
0x180032bbd  mov     edi, eax
0x180032bbf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032bc6  jb      loc_180032FE8
0x180032bcc  lea     edx, [rcx+77h]
0x180032bcf  mov     [rsp+78h+var_58], eax
0x180032bd3  jmp     loc_180032FB9
0x180032bd8  test    rsi, rsi
0x180032bdb  jnz     short loc_180032BF6
0x180032bdd  mov     eax, 80070057h
0x180032be2  mov     edi, eax
0x180032be4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032beb  jb      loc_180032FE8
0x180032bf1  lea     edx, [rsi+78h]
0x180032bf4  jmp     short loc_180032BCF
0x180032bf6  test    rbx, rbx
0x180032bf9  jnz     short loc_180032C14
0x180032bfb  mov     eax, 80070057h
0x180032c00  mov     edi, eax
0x180032c02  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032c09  jb      loc_180032FE8
0x180032c0f  lea     edx, [rbx+79h]
0x180032c12  jmp     short loc_180032BCF
0x180032c14  test    r13, r13
0x180032c17  jnz     short loc_180032C33
0x180032c19  mov     eax, 80004003h
0x180032c1e  mov     edi, eax
0x180032c20  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032c27  jb      loc_180032FE8
0x180032c2d  lea     edx, [r13+7Ah]
0x180032c31  jmp     short loc_180032BCF
0x180032c33  mov     r12, [rbp+arg_20]
0x180032c37  mov     [r9], rax
0x180032c3a  test    r12, r12
0x180032c3d  jnz     short loc_180032C5D
0x180032c3f  mov     eax, 80004003h
0x180032c44  mov     edi, eax
0x180032c46  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032c4d  jb      loc_180032FE8
0x180032c53  lea     edx, [r12+7Bh]
0x180032c58  jmp     loc_180032BCF
0x180032c5d  mov     r14, [rbp+arg_30]
0x180032c61  mov     [r12], eax
0x180032c65  test    r14, r14
0x180032c68  jz      short loc_180032C6D
0x180032c6a  mov     [r14], eax
0x180032c6d  lea     rdx, [rbp+var_18]; void **
0x180032c71  call    ?CreateSensorDevice@SensorDevice@@SAJAEBU_GUID@@PEAPEAX@Z; SensorDevice::CreateSensorDevice(_GUID const &,void * *)
0x180032c76  mov     edi, eax
0x180032c78  test    eax, eax
0x180032c7a  jns     short loc_180032C93
0x180032c7c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032c83  jb      loc_180032FD3
0x180032c89  mov     edx, 7Ch ; '|'
0x180032c8e  jmp     loc_180032BCF
0x180032c93  mov     rcx, [rbp+var_18]
0x180032c97  lea     rdx, [rbp+var_34]
0x180032c9b  mov     [rsp+78h+var_48], rdx
0x180032ca0  mov     r9, rbx
0x180032ca3  mov     [rsp+78h+var_50], 0
0x180032cac  mov     r8, rsi
0x180032caf  mov     rdx, r15
0x180032cb2  mov     [rsp+78h+var_58], 0
0x180032cba  mov     rax, [rcx]
0x180032cbd  mov     rax, [rax+18h]
0x180032cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cc6  xor     r15d, r15d
0x180032cc9  mov     edi, eax
0x180032ccb  test    eax, eax
0x180032ccd  jns     short loc_180032CE5
0x180032ccf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032cd6  jb      loc_180032FD3
0x180032cdc  lea     edx, [r15+7Dh]
0x180032ce0  jmp     loc_180032BCF
0x180032ce5  mov     rcx, [rbp+var_18]
0x180032ce9  lea     r8, [rbp+var_38]
0x180032ced  lea     rdx, [rbp+Src]
0x180032cf1  mov     rax, [rcx]
0x180032cf4  mov     rax, [rax+40h]
0x180032cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cfd  mov     edi, eax
0x180032cff  test    eax, eax
0x180032d01  jns     short loc_180032D1A
0x180032d03  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032d0a  jb      loc_180032FD3
0x180032d10  mov     edx, 7Eh ; '~'
0x180032d15  jmp     loc_180032BCF
0x180032d1a  movsxd  rsi, [rbp+var_38]
0x180032d1e  mov     rcx, rsi; cb
0x180032d21  call    cs:__imp_CoTaskMemAlloc
0x180032d27  mov     rbx, rax
0x180032d2a  test    rax, rax
0x180032d2d  jz      loc_180032FA2
0x180032d33  lea     rcx, [rax+rsi]
0x180032d37  cmp     rax, rcx
0x180032d3a  jz      short loc_180032D48
0x180032d3c  xor     edx, edx
0x180032d3e  mov     [rax], dl
0x180032d40  inc     rax
0x180032d43  cmp     rax, rcx
0x180032d46  jnz     short loc_180032D3C
0x180032d48  movsxd  r8, [rbp+var_38]; Size
0x180032d4c  mov     rcx, rbx; void *
0x180032d4f  mov     rdx, [rbp+Src]; Src
0x180032d53  call    memcpy_0
0x180032d58  mov     [rbp+Src], r15
0x180032d5c  cmp     [rbp+arg_28], r15
0x180032d60  jz      loc_180032F47
0x180032d66  mov     [rbp+var_28], r15
0x180032d6a  mov     [rbp+var_30], r15
0x180032d6e  test    r14, r14
0x180032d71  jnz     short loc_180032D95
0x180032d73  mov     eax, 80004003h
0x180032d78  mov     edi, eax
0x180032d7a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032d81  jb      loc_180032F85
0x180032d87  mov     edx, 80h
0x180032d8c  mov     [rsp+78h+var_58], eax
0x180032d90  jmp     loc_180032F6B
0x180032d95  mov     rcx, [rbp+var_18]
0x180032d99  lea     r8, [rbp+var_28]
0x180032d9d  lea     rdx, _GUID_fa993888_4383_415a_a930_dd472a8cf6f7
0x180032da4  mov     rax, [rcx]
0x180032da7  mov     rax, [rax]
0x180032daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032daf  mov     edi, eax
0x180032db1  test    eax, eax
0x180032db3  jns     short loc_180032DC9
0x180032db5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032dbc  jb      loc_180032F85
0x180032dc2  mov     edx, 81h
0x180032dc7  jmp     short loc_180032D8C
0x180032dc9  mov     rcx, [rbp+var_30]
0x180032dcd  mov     rdi, [rbp+var_28]
0x180032dd1  mov     rax, [rdi]
0x180032dd4  mov     [rbp+var_30], r15
0x180032dd8  mov     rsi, [rax+18h]
0x180032ddc  test    rcx, rcx
0x180032ddf  jz      short loc_180032DED
0x180032de1  mov     rdx, [rcx]
0x180032de4  mov     rax, [rdx+10h]
0x180032de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ded  lea     r9, [rbp+var_30]
0x180032df1  mov     rcx, rdi
0x180032df4  lea     r8, _GUID_9a9daaaa_9774_4732_848e_8739655f2ba3
0x180032dfb  mov     rax, rsi
0x180032dfe  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x180032e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e0a  mov     edi, eax
0x180032e0c  test    eax, eax
0x180032e0e  jns     short loc_180032E27
0x180032e10  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032e17  jb      loc_180032F85
0x180032e1d  mov     edx, 82h
0x180032e22  jmp     loc_180032D8C
0x180032e27  mov     rcx, [rbp+var_30]
0x180032e2b  mov     edx, 1
0x180032e30  mov     rax, [rcx]
0x180032e33  mov     rax, [rax+68h]
0x180032e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e3c  mov     edi, eax
0x180032e3e  test    eax, eax
0x180032e40  jns     short loc_180032E59
0x180032e42  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032e49  jb      loc_180032F85
0x180032e4f  mov     edx, 83h
0x180032e54  jmp     loc_180032D8C
0x180032e59  mov     rcx, [rbp+var_30]
0x180032e5d  lea     r8, [rbp+cb]
0x180032e61  lea     rdx, [rbp+Src]
0x180032e65  mov     rax, [rcx]
0x180032e68  mov     rax, [rax+70h]
0x180032e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e71  mov     edi, eax
0x180032e73  test    eax, eax
0x180032e75  jns     short loc_180032ED6
0x180032e77  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032e7e  jb      short loc_180032EA3
0x180032e80  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e87  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x180032e8e  mov     edx, 84h
0x180032e93  mov     [rsp+78h+var_58], eax
0x180032e97  xor     r9d, r9d
0x180032e9a  mov     rcx, [rcx+10h]
0x180032e9e  call    WPP_SF_qD
0x180032ea3  mov     rcx, [rbp+var_30]
0x180032ea7  test    rcx, rcx
0x180032eaa  jz      short loc_180032EB8
0x180032eac  mov     rax, [rcx]
0x180032eaf  mov     rax, [rax+10h]
0x180032eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032eb8  mov     rcx, [rbp+var_28]
0x180032ebc  test    rcx, rcx
0x180032ebf  jz      loc_180032F97
0x180032ec5  mov     rax, [rcx]
0x180032ec8  mov     rax, [rax+10h]
0x180032ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ed1  jmp     loc_180032F97
0x180032ed6  mov     r15d, dword ptr [rbp+cb]
0x180032eda  mov     ecx, r15d; cb
0x180032edd  call    cs:__imp_CoTaskMemAlloc
0x180032ee3  mov     rsi, rax
0x180032ee6  test    rax, rax
0x180032ee9  jz      short loc_180032F54
0x180032eeb  lea     rcx, [rax+r15]
0x180032eef  cmp     rax, rcx
0x180032ef2  jz      short loc_180032F00
0x180032ef4  xor     edx, edx
0x180032ef6  mov     [rax], dl
0x180032ef8  inc     rax
0x180032efb  cmp     rax, rcx
0x180032efe  jnz     short loc_180032EF4
0x180032f00  mov     r8d, dword ptr [rbp+cb]; Size
0x180032f04  mov     rcx, rsi; void *
0x180032f07  mov     rdx, [rbp+Src]; Src
0x180032f0b  call    memcpy_0
0x180032f10  mov     rax, [rbp+arg_28]
0x180032f14  mov     rcx, [rbp+var_30]
0x180032f18  mov     [rax], rsi
0x180032f1b  mov     eax, dword ptr [rbp+cb]
0x180032f1e  mov     [r14], eax
0x180032f21  test    rcx, rcx
0x180032f24  jz      short loc_180032F32
0x180032f26  mov     rax, [rcx]
0x180032f29  mov     rax, [rax+10h]
0x180032f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f32  mov     rcx, [rbp+var_28]
0x180032f36  test    rcx, rcx
0x180032f39  jz      short loc_180032F47
0x180032f3b  mov     rax, [rcx]
0x180032f3e  mov     rax, [rax+10h]
0x180032f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f47  mov     eax, [rbp+var_38]
0x180032f4a  mov     [r13+0], rbx
0x180032f4e  mov     [r12], eax
0x180032f52  jmp     short loc_180032FD3
0x180032f54  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032f5b  mov     edi, 8007000Eh
0x180032f60  jb      short loc_180032F85
0x180032f62  mov     edx, 85h
0x180032f67  mov     [rsp+78h+var_58], edi
0x180032f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f72  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x180032f79  xor     r9d, r9d
0x180032f7c  mov     rcx, [rcx+10h]
0x180032f80  call    WPP_SF_qD
0x180032f85  lea     rcx, [rbp+var_30]
0x180032f89  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180032f8e  lea     rcx, [rbp+var_28]
0x180032f92  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180032f97  mov     rcx, rbx; pv
0x180032f9a  call    cs:__imp_CoTaskMemFree
0x180032fa0  jmp     short loc_180032FD3
0x180032fa2  mov     edi, 8007000Eh
0x180032fa7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032fae  jb      short loc_180032FD3
0x180032fb0  mov     edx, 7Fh
0x180032fb5  mov     [rsp+78h+var_58], edi
0x180032fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180032fc0  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x180032fc7  xor     r9d, r9d
0x180032fca  mov     rcx, [rcx+10h]
0x180032fce  call    WPP_SF_qD
0x180032fd3  mov     rcx, [rbp+var_18]
0x180032fd7  test    rcx, rcx
0x180032fda  jz      short loc_180032FE8
0x180032fdc  mov     rax, [rcx]
0x180032fdf  mov     rax, [rax+10h]
0x180032fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fe8  mov     eax, edi
0x180032fea  add     rsp, 78h
0x180032fee  pop     r15
0x180032ff0  pop     r14
0x180032ff2  pop     r13
0x180032ff4  pop     r12
0x180032ff6  pop     rdi
0x180032ff7  pop     rsi
0x180032ff8  pop     rbx
  ... truncated ...
```
