# FSMergeCameraControlConfigurations

- ea: `0x180034a84`
- end: `0x180034f96`
- name: `FSMergeCameraControlConfigurations`
- size: `1298`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, LPVOID *, unsigned int *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033458`
- `0x180033ab0`
- `0x180034f9c`

## callees

- `0x180008cf0`
- `0x180009608`
- `0x180009cc0`
- `0x18000a460`
- `0x18000ad10`
- `0x18001807c`
- `0x18002da54`
- `0x18002db74`
- `0x18002dbc4`
- `0x18002dbf8`
- `0x180034a84`
- `0x1800367b0`
- `0x180039968`
- `0x1800e924c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034ec1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034f6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034f7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034ec1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034f6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034f7d`

## pseudocode

```c
__int64 __fastcall FSMergeCameraControlConfigurations(__int64 *a1, __int64 *a2, LPVOID *a3, unsigned int *a4)
{
  int v4; // r13d
  unsigned int v6; // ebx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r8
  unsigned int v13; // eax
  unsigned int v14; // edi
  int Instance; // eax
  unsigned int v16; // eax
  unsigned int v17; // esi
  int v18; // eax
  __int64 v19; // rdx
  __int64 unique_cotaskmem; // rax
  void *v21; // rcx
  char *v22; // rsi
  unsigned int v23; // r14d
  int v24; // eax
  unsigned int v25; // ecx
  __int64 v26; // rdx
  __int64 v27; // rdx
  unsigned int v28; // eax
  void *v29; // rcx
  void *v30; // rcx
  LPVOID v32; // [rsp+30h] [rbp-38h] BYREF
  LPVOID v33; // [rsp+38h] [rbp-30h] BYREF
  LPVOID i; // [rsp+40h] [rbp-28h] BYREF
  LPVOID *v35; // [rsp+48h] [rbp-20h] BYREF
  _BYTE v36[24]; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v37; // [rsp+B0h] [rbp+48h] BYREF
  unsigned int v38; // [rsp+B8h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp+58h] BYREF
  void *Src; // [rsp+C8h] [rbp+60h] BYREF

  v4 = 0;
  v6 = 0;
  v33 = 0;
  v37 = 0;
  v32 = 0;
  v38 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 27), 184, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, a1, a2);
  *a3 = 0;
  v35 = &v33;
  v10 = *a1;
  *a4 = 0;
  *(_QWORD *)v36 = 0;
  v36[8] = 1;
  (*(void (__fastcall **)(__int64 *, void *, _BYTE *, unsigned int *))(v10 + 128))(
    a1,
    &FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
    v36,
    &v37);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v35);
  *(_QWORD *)v36 = 0;
  v35 = &v32;
  v11 = *a2;
  v36[8] = 1;
  (*(void (__fastcall **)(__int64 *, void *, _BYTE *, unsigned int *))(v11 + 128))(
    a2,
    &FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
    v36,
    &v38);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v35);
  if ( !v33 )
  {
    if ( !v32 )
      goto LABEL_61;
    *a3 = v32;
    v28 = v38;
    v32 = 0;
LABEL_60:
    *a4 = v28;
LABEL_61:
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_Ddq(*((_QWORD *)WPP_GLOBAL_Control + 27), 197, v12, 0, *a4, *a3);
    goto LABEL_63;
  }
  if ( !v32 )
  {
    *a3 = v33;
    v28 = v37;
    v33 = 0;
    goto LABEL_60;
  }
  v13 = v38;
  v14 = 0;
  v35 = 0;
  *(_QWORD *)&v36[4] = 0;
  *(_DWORD *)v36 = 0;
  for ( i = 0; v14 < v38; v13 = v38 )
  {
    LODWORD(pv) = 0;
    Src = 0;
    Instance = FSConfigurationEntry::CreateInstance(
                 (unsigned __int8 *)v32 + v14,
                 v13 - v14,
                 (unsigned int *)&pv,
                 (struct IFSConfigurationEntry **)&Src);
    v6 = Instance;
    if ( Instance < 0 )
    {
      if ( g_wppLevels )
      {
        v19 = 185;
        goto LABEL_18;
      }
      goto LABEL_19;
    }
    if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add(&v35, Src) )
    {
      Instance = -2147024882;
      v6 = -2147024882;
      if ( g_wppLevels )
      {
        v19 = 186;
        goto LABEL_18;
      }
      goto LABEL_19;
    }
    if ( v14 + (unsigned int)pv < v14 )
    {
      Instance = -2147024362;
      v6 = -2147024362;
      if ( g_wppLevels )
      {
        v19 = 187;
        goto LABEL_18;
      }
      goto LABEL_19;
    }
    v14 += (unsigned int)pv;
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&Src);
  }
  v16 = v37;
  v17 = 0;
  if ( v37 )
  {
    while ( 1 )
    {
      LODWORD(pv) = 0;
      Src = 0;
      Instance = FSConfigurationEntry::CreateInstance(
                   (unsigned __int8 *)v33 + v17,
                   v16 - v17,
                   (unsigned int *)&pv,
                   (struct IFSConfigurationEntry **)&Src);
      v6 = Instance;
      if ( Instance < 0 )
        break;
      if ( (unsigned int)FSFindConfigurationEntryInArrayInternal(&v35, Src) == -1 )
      {
        if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add(&v35, Src) )
        {
          Instance = -2147024882;
          v6 = -2147024882;
          if ( g_wppLevels )
          {
            v19 = 189;
            goto LABEL_18;
          }
          goto LABEL_19;
        }
        v18 = (int)pv;
        if ( (unsigned int)pv + v14 < v14 )
        {
          Instance = -2147024362;
          v6 = -2147024362;
          if ( g_wppLevels )
          {
            v19 = 190;
            goto LABEL_18;
          }
          goto LABEL_19;
        }
        v14 += (unsigned int)pv;
      }
      else
      {
        v18 = (int)pv;
      }
      if ( v18 + v17 < v17 )
      {
        Instance = -2147024362;
        v6 = -2147024362;
        if ( g_wppLevels )
        {
          v19 = 191;
          goto LABEL_18;
        }
        goto LABEL_19;
      }
      v17 += v18;
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&Src);
      v16 = v37;
      if ( v17 >= v37 )
        goto LABEL_27;
    }
    if ( g_wppLevels )
    {
      v19 = 188;
LABEL_18:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, Instance);
    }
LABEL_19:
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&Src);
    goto LABEL_55;
  }
LABEL_27:
  unique_cotaskmem = wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(&pv, v14);
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    &i,
    unique_cotaskmem);
  v21 = pv;
  pv = 0;
  if ( v21 )
    CoTaskMemFree(v21);
  v22 = (char *)i;
  if ( !i )
  {
    v6 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        192,
        &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
        0,
        -2147024882);
    goto LABEL_55;
  }
  v23 = 0;
  if ( !*(_DWORD *)v36 )
  {
LABEL_45:
    *a3 = v22;
    *a4 = v14;
    CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(&v35);
    v6 = 0;
    goto LABEL_61;
  }
  while ( 1 )
  {
    Src = 0;
    LODWORD(pv) = 0;
    v24 = (*(__int64 (__fastcall **)(LPVOID, void **, LPVOID *))(*(_QWORD *)v35[v4] + 48LL))(v35[v4], &Src, &pv);
    v6 = v24;
    if ( v24 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_53;
      v27 = 193;
      goto LABEL_52;
    }
    v25 = (_DWORD)pv + v23;
    if ( (unsigned int)pv + v23 < (unsigned int)pv )
    {
      v24 = -2147024362;
      v6 = -2147024362;
      if ( !g_wppLevels )
        goto LABEL_53;
      v27 = 194;
LABEL_52:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v24);
      goto LABEL_53;
    }
    v26 = v23;
    v23 += (unsigned int)pv;
    if ( v25 > v14 )
      break;
    memcpy_0(&v22[v26], Src, (unsigned int)pv);
    if ( (unsigned int)++v4 >= *(_DWORD *)v36 )
      goto LABEL_45;
  }
  v6 = -1072860816;
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      195,
      &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids,
      0,
      -1072860816);
LABEL_53:
  if ( v22 )
    CoTaskMemFree(v22);
LABEL_55:
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(&v35);
  if ( byte_18010EC4D )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 196, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, v6);
LABEL_63:
  v29 = v32;
  v32 = 0;
  if ( v29 )
    CoTaskMemFree(v29);
  v30 = v33;
  v33 = 0;
  if ( v30 )
    CoTaskMemFree(v30);
  return v6;
}

```

## disassembly

```asm
0x180034a84  push    rbp
0x180034a86  push    rbx
0x180034a87  push    rsi
0x180034a88  push    rdi
0x180034a89  push    r12
0x180034a8b  push    r13
0x180034a8d  push    r14
0x180034a8f  push    r15
0x180034a91  mov     rbp, rsp
0x180034a94  sub     rsp, 68h
0x180034a98  xor     r13d, r13d
0x180034a9b  mov     r15, r9
0x180034a9e  mov     ebx, r13d
0x180034aa1  mov     [rbp+var_30], r13
0x180034aa5  mov     [rbp+arg_0], r13d
0x180034aa9  mov     r12, r8
0x180034aac  mov     [rbp+var_38], r13
0x180034ab0  mov     rdi, rdx
0x180034ab3  mov     [rbp+arg_8], r13d
0x180034ab7  mov     rsi, rcx
0x180034aba  cmp     cs:byte_18010EC4D, 8
0x180034ac1  jb      short loc_180034AEA
0x180034ac3  mov     r9, rcx
0x180034ac6  mov     [rsp+68h+var_48], rdi
0x180034acb  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ad2  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180034ad9  mov     edx, 0B8h
0x180034ade  mov     rcx, [rcx+0D8h]
0x180034ae5  call    WPP_SF_qq
0x180034aea  lea     rax, [rbp+var_30]
0x180034aee  mov     [r12], r13
0x180034af2  mov     [rbp+var_20], rax
0x180034af6  lea     r9, [rbp+arg_0]
0x180034afa  mov     rax, [rsi]
0x180034afd  lea     r8, [rbp+var_18]
0x180034b01  lea     rdx, FRAMESERVER_DEVICECONFIGURATION_ENTRIES
0x180034b08  mov     [r15], r13d
0x180034b0b  mov     rcx, rsi
0x180034b0e  mov     [rbp+var_18], r13
0x180034b12  mov     [rbp+var_10], 1
0x180034b16  mov     rax, [rax+80h]
0x180034b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b22  lea     rcx, [rbp+var_20]
0x180034b26  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180034b2b  lea     rax, [rbp+var_38]
0x180034b2f  mov     [rbp+var_18], r13
0x180034b33  mov     [rbp+var_20], rax
0x180034b37  lea     r9, [rbp+arg_8]
0x180034b3b  mov     rax, [rdi]
0x180034b3e  lea     r8, [rbp+var_18]
0x180034b42  lea     rdx, FRAMESERVER_DEVICECONFIGURATION_ENTRIES
0x180034b49  mov     [rbp+var_10], 1
0x180034b4d  mov     rcx, rdi
0x180034b50  mov     rax, [rax+80h]
0x180034b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b5c  lea     rcx, [rbp+var_20]
0x180034b60  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180034b65  cmp     [rbp+var_30], r13
0x180034b69  jz      loc_180034F12
0x180034b6f  cmp     [rbp+var_38], r13
0x180034b73  jz      loc_180034F01
0x180034b79  mov     eax, [rbp+arg_8]
0x180034b7c  mov     edi, r13d
0x180034b7f  mov     [rbp+var_20], r13
0x180034b83  mov     [rbp+var_18+4], r13
0x180034b87  mov     dword ptr [rbp+var_18], r13d
0x180034b8b  mov     [rbp+var_28], r13
0x180034b8f  test    eax, eax
0x180034b91  jz      short loc_180034BF0
0x180034b93  sub     eax, edi
0x180034b95  mov     ecx, edi
0x180034b97  add     rcx, [rbp+var_38]; unsigned __int8 *
0x180034b9b  lea     r9, [rbp+Src]; struct IFSConfigurationEntry **
0x180034b9f  mov     edx, eax; unsigned int
0x180034ba1  mov     dword ptr [rbp+pv], r13d
0x180034ba5  lea     r8, [rbp+pv]; unsigned int *
0x180034ba9  mov     [rbp+Src], r13
0x180034bad  call    ?CreateInstance@FSConfigurationEntry@@SAJPEAEKPEAKPEAPEAUIFSConfigurationEntry@@@Z; FSConfigurationEntry::CreateInstance(uchar *,ulong,ulong *,IFSConfigurationEntry * *)
0x180034bb2  mov     ebx, eax
0x180034bb4  test    eax, eax
0x180034bb6  js      loc_180034CBC
0x180034bbc  mov     rdx, [rbp+Src]
0x180034bc0  lea     rcx, [rbp+var_20]
0x180034bc4  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x180034bc9  test    eax, eax
0x180034bcb  jz      loc_180034CA5
0x180034bd1  mov     ecx, dword ptr [rbp+pv]
0x180034bd4  add     ecx, edi
0x180034bd6  cmp     ecx, edi
0x180034bd8  jb      loc_180034C64
0x180034bde  mov     edi, ecx
0x180034be0  lea     rcx, [rbp+Src]; void *
0x180034be4  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180034be9  mov     eax, [rbp+arg_8]
0x180034bec  cmp     edi, eax
0x180034bee  jb      short loc_180034B93
0x180034bf0  mov     eax, [rbp+arg_0]
0x180034bf3  mov     esi, r13d
0x180034bf6  test    eax, eax
0x180034bf8  jz      loc_180034CF0
0x180034bfe  sub     eax, esi
0x180034c00  mov     ecx, esi
0x180034c02  add     rcx, [rbp+var_30]; unsigned __int8 *
0x180034c06  lea     r9, [rbp+Src]; struct IFSConfigurationEntry **
0x180034c0a  mov     edx, eax; unsigned int
0x180034c0c  mov     dword ptr [rbp+pv], r13d
0x180034c10  lea     r8, [rbp+pv]; unsigned int *
0x180034c14  mov     [rbp+Src], r13
0x180034c18  call    ?CreateInstance@FSConfigurationEntry@@SAJPEAEKPEAKPEAPEAUIFSConfigurationEntry@@@Z; FSConfigurationEntry::CreateInstance(uchar *,ulong,ulong *,IFSConfigurationEntry * *)
0x180034c1d  mov     ebx, eax
0x180034c1f  test    eax, eax
0x180034c21  js      loc_180034DBD
0x180034c27  mov     rdx, [rbp+Src]
0x180034c2b  lea     rcx, [rbp+var_20]
0x180034c2f  call    ?FSFindConfigurationEntryInArrayInternal@@YAKAEAV?$CTUnkArray@UIFSConfigurationEntry@@@@PEAUIFSConfigurationEntry@@@Z; FSFindConfigurationEntryInArrayInternal(CTUnkArray<IFSConfigurationEntry> &,IFSConfigurationEntry *)
0x180034c34  cmp     eax, 0FFFFFFFFh
0x180034c37  jnz     loc_180034CCC
0x180034c3d  mov     rdx, [rbp+Src]
0x180034c41  lea     rcx, [rbp+var_20]
0x180034c45  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x180034c4a  test    eax, eax
0x180034c4c  jz      loc_180034D81
0x180034c52  mov     eax, dword ptr [rbp+pv]
0x180034c55  lea     ecx, [rax+rdi]
0x180034c58  cmp     ecx, edi
0x180034c5a  jb      loc_180034D63
0x180034c60  mov     edi, ecx
0x180034c62  jmp     short loc_180034CCF
0x180034c64  mov     eax, 80070216h
0x180034c69  mov     ebx, eax
0x180034c6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034c72  jb      short loc_180034C97
0x180034c74  mov     edx, 0BBh
0x180034c79  mov     rcx, cs:WPP_GLOBAL_Control
0x180034c80  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180034c87  xor     r9d, r9d
0x180034c8a  mov     dword ptr [rsp+68h+var_48], eax
0x180034c8e  mov     rcx, [rcx+10h]
0x180034c92  call    WPP_SF_qD
0x180034c97  lea     rcx, [rbp+Src]; void *
0x180034c9b  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180034ca0  jmp     loc_180034EC7
0x180034ca5  mov     eax, 8007000Eh
0x180034caa  mov     ebx, eax
0x180034cac  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034cb3  jb      short loc_180034C97
0x180034cb5  mov     edx, 0BAh
0x180034cba  jmp     short loc_180034C79
0x180034cbc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034cc3  jb      short loc_180034C97
0x180034cc5  mov     edx, 0B9h
0x180034cca  jmp     short loc_180034C79
0x180034ccc  mov     eax, dword ptr [rbp+pv]
0x180034ccf  lea     ecx, [rax+rsi]
0x180034cd2  cmp     ecx, esi
0x180034cd4  jb      loc_180034D9F
0x180034cda  mov     esi, ecx
0x180034cdc  lea     rcx, [rbp+Src]; void *
0x180034ce0  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180034ce5  mov     eax, [rbp+arg_0]
0x180034ce8  cmp     esi, eax
0x180034cea  jb      loc_180034BFE
0x180034cf0  mov     edx, edi
0x180034cf2  lea     rcx, [rbp+pv]
0x180034cf6  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x180034cfb  mov     rdx, rax
0x180034cfe  lea     rcx, [rbp+var_28]
0x180034d02  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180034d07  mov     rcx, [rbp+pv]; pv
0x180034d0b  mov     [rbp+pv], r13
0x180034d0f  test    rcx, rcx
0x180034d12  jz      short loc_180034D1A
0x180034d14  call    cs:__imp_CoTaskMemFree
0x180034d1a  mov     rsi, [rbp+var_28]
0x180034d1e  test    rsi, rsi
0x180034d21  jnz     loc_180034DD4
0x180034d27  mov     eax, 8007000Eh
0x180034d2c  mov     ebx, eax
0x180034d2e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034d35  jb      loc_180034EC7
0x180034d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d42  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180034d49  mov     edx, 0C0h
0x180034d4e  mov     dword ptr [rsp+68h+var_48], eax
0x180034d52  xor     r9d, r9d
0x180034d55  mov     rcx, [rcx+10h]
0x180034d59  call    WPP_SF_qD
0x180034d5e  jmp     loc_180034EC7
0x180034d63  mov     eax, 80070216h
0x180034d68  mov     ebx, eax
0x180034d6a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034d71  jb      loc_180034C97
0x180034d77  mov     edx, 0BEh
0x180034d7c  jmp     loc_180034C79
0x180034d81  mov     eax, 8007000Eh
0x180034d86  mov     ebx, eax
0x180034d88  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034d8f  jb      loc_180034C97
0x180034d95  mov     edx, 0BDh
0x180034d9a  jmp     loc_180034C79
0x180034d9f  mov     eax, 80070216h
0x180034da4  mov     ebx, eax
0x180034da6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034dad  jb      loc_180034C97
0x180034db3  mov     edx, 0BFh
0x180034db8  jmp     loc_180034C79
0x180034dbd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034dc4  jb      loc_180034C97
0x180034dca  mov     edx, 0BCh
0x180034dcf  jmp     loc_180034C79
0x180034dd4  mov     r14d, r13d
0x180034dd7  cmp     dword ptr [rbp+var_18], r13d
0x180034ddb  jbe     short loc_180034E3F
0x180034ddd  mov     rax, [rbp+var_20]
0x180034de1  lea     r8, [rbp+pv]
0x180034de5  mov     [rbp+Src], 0
0x180034ded  lea     rdx, [rbp+Src]
0x180034df1  mov     dword ptr [rbp+pv], 0
0x180034df8  mov     ecx, r13d
0x180034dfb  mov     rcx, [rax+rcx*8]
0x180034dff  mov     rax, [rcx]
0x180034e02  mov     rax, [rax+30h]
0x180034e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e0b  mov     ebx, eax
0x180034e0d  test    eax, eax
0x180034e0f  js      short loc_180034E8A
0x180034e11  mov     eax, dword ptr [rbp+pv]
0x180034e14  lea     ecx, [rax+r14]
0x180034e18  cmp     ecx, eax
0x180034e1a  jb      short loc_180034E73
0x180034e1c  mov     edx, r14d
0x180034e1f  mov     r14d, ecx
0x180034e22  cmp     ecx, edi
0x180034e24  ja      short loc_180034E5A
0x180034e26  lea     rcx, [rsi+rdx]; void *
0x180034e2a  mov     r8d, eax; Size
0x180034e2d  mov     rdx, [rbp+Src]; Src
0x180034e31  call    memcpy_0
0x180034e36  inc     r13d
0x180034e39  cmp     r13d, dword ptr [rbp+var_18]
0x180034e3d  jb      short loc_180034DDD
0x180034e3f  lea     rcx, [rbp+var_20]; void *
0x180034e43  mov     [r12], rsi
0x180034e47  mov     [r15], edi
0x180034e4a  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x180034e4f  xor     r13d, r13d
0x180034e52  mov     ebx, r13d
0x180034e55  jmp     loc_180034F29
0x180034e5a  mov     ebx, 0C00D7170h
0x180034e5f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034e66  jb      short loc_180034EB6
0x180034e68  mov     edx, 0C3h
0x180034e6d  mov     dword ptr [rsp+68h+var_48], ebx
0x180034e71  jmp     short loc_180034E9C
0x180034e73  mov     eax, 80070216h
0x180034e78  mov     ebx, eax
0x180034e7a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034e81  jb      short loc_180034EB6
0x180034e83  mov     edx, 0C2h
0x180034e88  jmp     short loc_180034E98
0x180034e8a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180034e91  jb      short loc_180034EB6
0x180034e93  mov     edx, 0C1h
0x180034e98  mov     dword ptr [rsp+68h+var_48], eax
0x180034e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ea3  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180034eaa  xor     r9d, r9d
0x180034ead  mov     rcx, [rcx+10h]
0x180034eb1  call    WPP_SF_qD
0x180034eb6  xor     r13d, r13d
0x180034eb9  test    rsi, rsi
0x180034ebc  jz      short loc_180034EC7
0x180034ebe  mov     rcx, rsi; pv
0x180034ec1  call    cs:__imp_CoTaskMemFree
0x180034ec7  lea     rcx, [rbp+var_20]; void *
0x180034ecb  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x180034ed0  cmp     cs:byte_18010EC4D, 1
0x180034ed7  jb      loc_180034F5D
0x180034edd  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ee4  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x180034eeb  mov     edx, 0C4h
0x180034ef0  mov     r9d, ebx
0x180034ef3  mov     rcx, [rcx+0D8h]
0x180034efa  call    WPP_SF_d
0x180034eff  jmp     short loc_180034F5D
0x180034f01  mov     rax, [rbp+var_30]
0x180034f05  mov     [r12], rax
0x180034f09  mov     eax, [rbp+arg_0]
0x180034f0c  mov     [rbp+var_30], r13
0x180034f10  jmp     short loc_180034F26
0x180034f12  mov     rax, [rbp+var_38]
0x180034f16  test    rax, rax
0x180034f19  jz      short loc_180034F29
0x180034f1b  mov     [r12], rax
0x180034f1f  mov     eax, [rbp+arg_8]
0x180034f22  mov     [rbp+var_38], r13
0x180034f26  mov     [r15], eax
0x180034f29  cmp     cs:byte_18010EC4D, 8
0x180034f30  jb      short loc_180034F5D
0x180034f32  mov     rax, [r12]
  ... truncated ...
```
