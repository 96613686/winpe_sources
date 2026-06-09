# FSMergeCameraControlConfigurations

- ea: `0x18003a48c`
- end: `0x18003a995`
- name: `FSMergeCameraControlConfigurations`
- size: `1289`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003896c`
- `0x180038f94`

## callees

- `0x180005f98`
- `0x180006a98`
- `0x180006f3c`
- `0x180007348`
- `0x18000d3d8`
- `0x18000d778`
- `0x18000e66c`
- `0x18003191c`
- `0x180031964`
- `0x180034e30`
- `0x18003a48c`
- `0x18003bda0`
- `0x18003ef58`
- `0x18004bf50`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a71c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a8c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a969`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a97c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a71c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a8c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a969`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a97c`

## pseudocode

```c
__int64 __fastcall FSMergeCameraControlConfigurations(__int64 *a1, __int64 *a2, LPVOID *a3, unsigned int *a4)
{
  int v4; // r13d
  unsigned int v6; // ebx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // eax
  unsigned int v15; // edi
  int Instance; // eax
  unsigned int v17; // eax
  unsigned int v18; // esi
  int v19; // eax
  __int64 v20; // rdx
  void **unique_cotaskmem; // rax
  void *v22; // rcx
  char *v23; // rsi
  unsigned int v24; // r14d
  int v25; // eax
  unsigned int v26; // ecx
  __int64 v27; // rdx
  __int64 v28; // rdx
  unsigned int v29; // eax
  void *v30; // rcx
  void *v31; // rcx
  LPVOID v33; // [rsp+30h] [rbp-38h] BYREF
  LPVOID v34; // [rsp+38h] [rbp-30h] BYREF
  LPVOID i; // [rsp+40h] [rbp-28h] BYREF
  LPVOID *v36; // [rsp+48h] [rbp-20h] BYREF
  _BYTE v37[24]; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v38; // [rsp+B0h] [rbp+48h] BYREF
  unsigned int v39; // [rsp+B8h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp+58h] BYREF
  void *Src; // [rsp+C8h] [rbp+60h] BYREF

  v4 = 0;
  v6 = 0;
  v34 = 0;
  v38 = 0;
  v33 = 0;
  v39 = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 27), 184, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, a1, a2);
  *a3 = 0;
  v36 = &v34;
  v10 = *a1;
  *a4 = 0;
  *(_QWORD *)v37 = 0;
  v37[8] = 1;
  (*(void (__fastcall **)(__int64 *, __int64 *, _BYTE *, unsigned int *))(v10 + 128))(
    a1,
    FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
    v37,
    &v38);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&v36);
  *(_QWORD *)v37 = 0;
  v36 = &v33;
  v11 = *a2;
  v37[8] = 1;
  (*(void (__fastcall **)(__int64 *, __int64 *, _BYTE *, unsigned int *))(v11 + 128))(
    a2,
    FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
    v37,
    &v39);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&v36);
  if ( !v34 )
  {
    if ( !v33 )
      goto LABEL_61;
    *a3 = v33;
    v29 = v39;
    v33 = 0;
LABEL_60:
    *a4 = v29;
LABEL_61:
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      WPP_SF_Ddq(*((_QWORD *)WPP_GLOBAL_Control + 27), v12, v13, 0, *a4, *a3);
    goto LABEL_63;
  }
  if ( !v33 )
  {
    *a3 = v34;
    v29 = v38;
    v34 = 0;
    goto LABEL_60;
  }
  v14 = v39;
  v15 = 0;
  v36 = 0;
  *(_QWORD *)&v37[4] = 0;
  *(_DWORD *)v37 = 0;
  for ( i = 0; v15 < v39; v14 = v39 )
  {
    LODWORD(pv) = 0;
    Src = 0;
    Instance = FSConfigurationEntry::CreateInstance(
                 (unsigned __int8 *)v33 + v15,
                 v14 - v15,
                 (unsigned int *)&pv,
                 (struct IFSConfigurationEntry **)&Src);
    v6 = Instance;
    if ( Instance < 0 )
    {
      if ( g_wppLevels )
      {
        v20 = 185;
        goto LABEL_18;
      }
      goto LABEL_19;
    }
    if ( !(unsigned int)CTUnkArray<IFSCameraControlState>::Add((__int64 *)&v36, (__int64)Src) )
    {
      Instance = -2147024882;
      v6 = -2147024882;
      if ( g_wppLevels )
      {
        v20 = 186;
        goto LABEL_18;
      }
      goto LABEL_19;
    }
    if ( v15 + (unsigned int)pv < v15 )
    {
      Instance = -2147024362;
      v6 = -2147024362;
      if ( g_wppLevels )
      {
        v20 = 187;
        goto LABEL_18;
      }
      goto LABEL_19;
    }
    v15 += (unsigned int)pv;
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&Src);
  }
  v17 = v38;
  v18 = 0;
  if ( v38 )
  {
    while ( 1 )
    {
      LODWORD(pv) = 0;
      Src = 0;
      Instance = FSConfigurationEntry::CreateInstance(
                   (unsigned __int8 *)v34 + v18,
                   v17 - v18,
                   (unsigned int *)&pv,
                   (struct IFSConfigurationEntry **)&Src);
      v6 = Instance;
      if ( Instance < 0 )
        break;
      if ( (unsigned int)FSFindConfigurationEntryInArrayInternal((__int64)&v36, (__int64)Src) == -1 )
      {
        if ( !(unsigned int)CTUnkArray<IFSCameraControlState>::Add((__int64 *)&v36, (__int64)Src) )
        {
          Instance = -2147024882;
          v6 = -2147024882;
          if ( g_wppLevels )
          {
            v20 = 189;
            goto LABEL_18;
          }
          goto LABEL_19;
        }
        v19 = (int)pv;
        if ( (unsigned int)pv + v15 < v15 )
        {
          Instance = -2147024362;
          v6 = -2147024362;
          if ( g_wppLevels )
          {
            v20 = 190;
            goto LABEL_18;
          }
          goto LABEL_19;
        }
        v15 += (unsigned int)pv;
      }
      else
      {
        v19 = (int)pv;
      }
      if ( v19 + v18 < v18 )
      {
        Instance = -2147024362;
        v6 = -2147024362;
        if ( g_wppLevels )
        {
          v20 = 191;
          goto LABEL_18;
        }
        goto LABEL_19;
      }
      v18 += v19;
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&Src);
      v17 = v38;
      if ( v18 >= v38 )
        goto LABEL_27;
    }
    if ( g_wppLevels )
    {
      v20 = 188;
LABEL_18:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, Instance);
    }
LABEL_19:
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&Src);
    goto LABEL_55;
  }
LABEL_27:
  unique_cotaskmem = (void **)wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(&pv, v15);
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    &i,
    unique_cotaskmem);
  v22 = pv;
  pv = 0;
  if ( v22 )
    CoTaskMemFree(v22);
  v23 = (char *)i;
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
  v24 = 0;
  if ( !*(_DWORD *)v37 )
  {
LABEL_45:
    *a3 = v23;
    *a4 = v15;
    CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>(&v36);
    v6 = 0;
    goto LABEL_61;
  }
  while ( 1 )
  {
    Src = 0;
    LODWORD(pv) = 0;
    v25 = (*(__int64 (__fastcall **)(LPVOID, void **, LPVOID *))(*(_QWORD *)v36[v4] + 48LL))(v36[v4], &Src, &pv);
    v6 = v25;
    if ( v25 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_53;
      v28 = 193;
      goto LABEL_52;
    }
    v26 = (_DWORD)pv + v24;
    if ( (unsigned int)pv + v24 < (unsigned int)pv )
    {
      v25 = -2147024362;
      v6 = -2147024362;
      if ( !g_wppLevels )
        goto LABEL_53;
      v28 = 194;
LABEL_52:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, 0, v25);
      goto LABEL_53;
    }
    v27 = v24;
    v24 += (unsigned int)pv;
    if ( v26 > v15 )
      break;
    memcpy_0(&v23[v27], Src, (unsigned int)pv);
    if ( (unsigned int)++v4 >= *(_DWORD *)v37 )
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
  if ( v23 )
    CoTaskMemFree(v23);
LABEL_55:
  CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>(&v36);
  if ( byte_18005E5A5 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 196, &WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids, v6);
LABEL_63:
  v30 = v33;
  v33 = 0;
  if ( v30 )
    CoTaskMemFree(v30);
  v31 = v34;
  v34 = 0;
  if ( v31 )
    CoTaskMemFree(v31);
  return v6;
}

```

## disassembly

```asm
0x18003a48c  push    rbp
0x18003a48e  push    rbx
0x18003a48f  push    rsi
0x18003a490  push    rdi
0x18003a491  push    r12
0x18003a493  push    r13
0x18003a495  push    r14
0x18003a497  push    r15
0x18003a499  mov     rbp, rsp
0x18003a49c  sub     rsp, 68h
0x18003a4a0  xor     r13d, r13d
0x18003a4a3  mov     r15, r9
0x18003a4a6  mov     ebx, r13d
0x18003a4a9  mov     [rbp+var_30], r13
0x18003a4ad  mov     [rbp+arg_0], r13d
0x18003a4b1  mov     r12, r8
0x18003a4b4  mov     [rbp+var_38], r13
0x18003a4b8  mov     rdi, rdx
0x18003a4bb  mov     [rbp+arg_8], r13d
0x18003a4bf  mov     rsi, rcx
0x18003a4c2  cmp     cs:byte_18005E5A5, 8
0x18003a4c9  jb      short loc_18003A4F2
0x18003a4cb  mov     r9, rcx
0x18003a4ce  mov     [rsp+68h+var_48], rdi
0x18003a4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4da  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003a4e1  mov     edx, 0B8h
0x18003a4e6  mov     rcx, [rcx+0D8h]
0x18003a4ed  call    WPP_SF_qq
0x18003a4f2  lea     rax, [rbp+var_30]
0x18003a4f6  mov     [r12], r13
0x18003a4fa  mov     [rbp+var_20], rax
0x18003a4fe  lea     r9, [rbp+arg_0]
0x18003a502  mov     rax, [rsi]
0x18003a505  lea     r8, [rbp+var_18]
0x18003a509  lea     rdx, FRAMESERVER_DEVICECONFIGURATION_ENTRIES
0x18003a510  mov     [r15], r13d
0x18003a513  mov     rcx, rsi
0x18003a516  mov     [rbp+var_18], r13
0x18003a51a  mov     [rbp+var_10], 1
0x18003a51e  mov     rax, [rax+80h]
0x18003a525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a52a  lea     rcx, [rbp+var_20]
0x18003a52e  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003a533  lea     rax, [rbp+var_38]
0x18003a537  mov     [rbp+var_18], r13
0x18003a53b  mov     [rbp+var_20], rax
0x18003a53f  lea     r9, [rbp+arg_8]
0x18003a543  mov     rax, [rdi]
0x18003a546  lea     r8, [rbp+var_18]
0x18003a54a  lea     rdx, FRAMESERVER_DEVICECONFIGURATION_ENTRIES
0x18003a551  mov     [rbp+var_10], 1
0x18003a555  mov     rcx, rdi
0x18003a558  mov     rax, [rax+80h]
0x18003a55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a564  lea     rcx, [rbp+var_20]
0x18003a568  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003a56d  cmp     [rbp+var_30], r13
0x18003a571  jz      loc_18003A916
0x18003a577  cmp     [rbp+var_38], r13
0x18003a57b  jz      loc_18003A905
0x18003a581  mov     eax, [rbp+arg_8]
0x18003a584  mov     edi, r13d
0x18003a587  mov     [rbp+var_20], r13
0x18003a58b  mov     [rbp+var_18+4], r13
0x18003a58f  mov     dword ptr [rbp+var_18], r13d
0x18003a593  mov     [rbp+var_28], r13
0x18003a597  test    eax, eax
0x18003a599  jz      short loc_18003A5F8
0x18003a59b  sub     eax, edi
0x18003a59d  mov     ecx, edi
0x18003a59f  add     rcx, [rbp+var_38]; unsigned __int8 *
0x18003a5a3  lea     r9, [rbp+Src]; struct IFSConfigurationEntry **
0x18003a5a7  mov     edx, eax; unsigned int
0x18003a5a9  mov     dword ptr [rbp+pv], r13d
0x18003a5ad  lea     r8, [rbp+pv]; unsigned int *
0x18003a5b1  mov     [rbp+Src], r13
0x18003a5b5  call    ?CreateInstance@FSConfigurationEntry@@SAJPEAEKPEAKPEAPEAUIFSConfigurationEntry@@@Z; FSConfigurationEntry::CreateInstance(uchar *,ulong,ulong *,IFSConfigurationEntry * *)
0x18003a5ba  mov     ebx, eax
0x18003a5bc  test    eax, eax
0x18003a5be  js      loc_18003A6C4
0x18003a5c4  mov     rdx, [rbp+Src]
0x18003a5c8  lea     rcx, [rbp+var_20]
0x18003a5cc  call    ?Add@?$CTUnkArray@UIFSCameraControlState@@@@QEAAHPEAUIFSCameraControlState@@@Z; CTUnkArray<IFSCameraControlState>::Add(IFSCameraControlState *)
0x18003a5d1  test    eax, eax
0x18003a5d3  jz      loc_18003A6AD
0x18003a5d9  mov     ecx, dword ptr [rbp+pv]
0x18003a5dc  add     ecx, edi
0x18003a5de  cmp     ecx, edi
0x18003a5e0  jb      loc_18003A66C
0x18003a5e6  mov     edi, ecx
0x18003a5e8  lea     rcx, [rbp+Src]
0x18003a5ec  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003a5f1  mov     eax, [rbp+arg_8]
0x18003a5f4  cmp     edi, eax
0x18003a5f6  jb      short loc_18003A59B
0x18003a5f8  mov     eax, [rbp+arg_0]
0x18003a5fb  mov     esi, r13d
0x18003a5fe  test    eax, eax
0x18003a600  jz      loc_18003A6F8
0x18003a606  sub     eax, esi
0x18003a608  mov     ecx, esi
0x18003a60a  add     rcx, [rbp+var_30]; unsigned __int8 *
0x18003a60e  lea     r9, [rbp+Src]; struct IFSConfigurationEntry **
0x18003a612  mov     edx, eax; unsigned int
0x18003a614  mov     dword ptr [rbp+pv], r13d
0x18003a618  lea     r8, [rbp+pv]; unsigned int *
0x18003a61c  mov     [rbp+Src], r13
0x18003a620  call    ?CreateInstance@FSConfigurationEntry@@SAJPEAEKPEAKPEAPEAUIFSConfigurationEntry@@@Z; FSConfigurationEntry::CreateInstance(uchar *,ulong,ulong *,IFSConfigurationEntry * *)
0x18003a625  mov     ebx, eax
0x18003a627  test    eax, eax
0x18003a629  js      loc_18003A7C5
0x18003a62f  mov     rdx, [rbp+Src]
0x18003a633  lea     rcx, [rbp+var_20]
0x18003a637  call    ?FSFindConfigurationEntryInArrayInternal@@YAKAEAV?$CTUnkArray@UIFSConfigurationEntry@@@@PEAUIFSConfigurationEntry@@@Z; FSFindConfigurationEntryInArrayInternal(CTUnkArray<IFSConfigurationEntry> &,IFSConfigurationEntry *)
0x18003a63c  cmp     eax, 0FFFFFFFFh
0x18003a63f  jnz     loc_18003A6D4
0x18003a645  mov     rdx, [rbp+Src]
0x18003a649  lea     rcx, [rbp+var_20]
0x18003a64d  call    ?Add@?$CTUnkArray@UIFSCameraControlState@@@@QEAAHPEAUIFSCameraControlState@@@Z; CTUnkArray<IFSCameraControlState>::Add(IFSCameraControlState *)
0x18003a652  test    eax, eax
0x18003a654  jz      loc_18003A789
0x18003a65a  mov     eax, dword ptr [rbp+pv]
0x18003a65d  lea     ecx, [rax+rdi]
0x18003a660  cmp     ecx, edi
0x18003a662  jb      loc_18003A76B
0x18003a668  mov     edi, ecx
0x18003a66a  jmp     short loc_18003A6D7
0x18003a66c  mov     eax, 80070216h
0x18003a671  mov     ebx, eax
0x18003a673  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a67a  jb      short loc_18003A69F
0x18003a67c  mov     edx, 0BBh
0x18003a681  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a688  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003a68f  xor     r9d, r9d
0x18003a692  mov     dword ptr [rsp+68h+var_48], eax
0x18003a696  mov     rcx, [rcx+10h]
0x18003a69a  call    WPP_SF_qD
0x18003a69f  lea     rcx, [rbp+Src]
0x18003a6a3  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003a6a8  jmp     loc_18003A8CF
0x18003a6ad  mov     eax, 8007000Eh
0x18003a6b2  mov     ebx, eax
0x18003a6b4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a6bb  jb      short loc_18003A69F
0x18003a6bd  mov     edx, 0BAh
0x18003a6c2  jmp     short loc_18003A681
0x18003a6c4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a6cb  jb      short loc_18003A69F
0x18003a6cd  mov     edx, 0B9h
0x18003a6d2  jmp     short loc_18003A681
0x18003a6d4  mov     eax, dword ptr [rbp+pv]
0x18003a6d7  lea     ecx, [rax+rsi]
0x18003a6da  cmp     ecx, esi
0x18003a6dc  jb      loc_18003A7A7
0x18003a6e2  mov     esi, ecx
0x18003a6e4  lea     rcx, [rbp+Src]
0x18003a6e8  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003a6ed  mov     eax, [rbp+arg_0]
0x18003a6f0  cmp     esi, eax
0x18003a6f2  jb      loc_18003A606
0x18003a6f8  mov     edx, edi
0x18003a6fa  lea     rcx, [rbp+pv]
0x18003a6fe  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x18003a703  mov     rdx, rax
0x18003a706  lea     rcx, [rbp+var_28]
0x18003a70a  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18003a70f  mov     rcx, [rbp+pv]; pv
0x18003a713  mov     [rbp+pv], r13
0x18003a717  test    rcx, rcx
0x18003a71a  jz      short loc_18003A722
0x18003a71c  call    cs:__imp_CoTaskMemFree
0x18003a722  mov     rsi, [rbp+var_28]
0x18003a726  test    rsi, rsi
0x18003a729  jnz     loc_18003A7DC
0x18003a72f  mov     eax, 8007000Eh
0x18003a734  mov     ebx, eax
0x18003a736  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a73d  jb      loc_18003A8CF
0x18003a743  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a74a  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003a751  mov     edx, 0C0h
0x18003a756  mov     dword ptr [rsp+68h+var_48], eax
0x18003a75a  xor     r9d, r9d
0x18003a75d  mov     rcx, [rcx+10h]
0x18003a761  call    WPP_SF_qD
0x18003a766  jmp     loc_18003A8CF
0x18003a76b  mov     eax, 80070216h
0x18003a770  mov     ebx, eax
0x18003a772  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a779  jb      loc_18003A69F
0x18003a77f  mov     edx, 0BEh
0x18003a784  jmp     loc_18003A681
0x18003a789  mov     eax, 8007000Eh
0x18003a78e  mov     ebx, eax
0x18003a790  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a797  jb      loc_18003A69F
0x18003a79d  mov     edx, 0BDh
0x18003a7a2  jmp     loc_18003A681
0x18003a7a7  mov     eax, 80070216h
0x18003a7ac  mov     ebx, eax
0x18003a7ae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a7b5  jb      loc_18003A69F
0x18003a7bb  mov     edx, 0BFh
0x18003a7c0  jmp     loc_18003A681
0x18003a7c5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a7cc  jb      loc_18003A69F
0x18003a7d2  mov     edx, 0BCh
0x18003a7d7  jmp     loc_18003A681
0x18003a7dc  mov     r14d, r13d
0x18003a7df  cmp     dword ptr [rbp+var_18], r13d
0x18003a7e3  jbe     short loc_18003A847
0x18003a7e5  mov     rax, [rbp+var_20]
0x18003a7e9  lea     r8, [rbp+pv]
0x18003a7ed  mov     [rbp+Src], 0
0x18003a7f5  lea     rdx, [rbp+Src]
0x18003a7f9  mov     dword ptr [rbp+pv], 0
0x18003a800  mov     ecx, r13d
0x18003a803  mov     rcx, [rax+rcx*8]
0x18003a807  mov     rax, [rcx]
0x18003a80a  mov     rax, [rax+30h]
0x18003a80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a813  mov     ebx, eax
0x18003a815  test    eax, eax
0x18003a817  js      short loc_18003A892
0x18003a819  mov     eax, dword ptr [rbp+pv]
0x18003a81c  lea     ecx, [rax+r14]
0x18003a820  cmp     ecx, eax
0x18003a822  jb      short loc_18003A87B
0x18003a824  mov     edx, r14d
0x18003a827  mov     r14d, ecx
0x18003a82a  cmp     ecx, edi
0x18003a82c  ja      short loc_18003A862
0x18003a82e  lea     rcx, [rsi+rdx]; void *
0x18003a832  mov     r8d, eax; Size
0x18003a835  mov     rdx, [rbp+Src]; Src
0x18003a839  call    memcpy_0
0x18003a83e  inc     r13d
0x18003a841  cmp     r13d, dword ptr [rbp+var_18]
0x18003a845  jb      short loc_18003A7E5
0x18003a847  lea     rcx, [rbp+var_20]
0x18003a84b  mov     [r12], rsi
0x18003a84f  mov     [r15], edi
0x18003a852  call    ??1?$CTUnkArray@UIMFSensorDeviceIdInternal@@@@QEAA@XZ; CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>(void)
0x18003a857  xor     r13d, r13d
0x18003a85a  mov     ebx, r13d
0x18003a85d  jmp     loc_18003A92D
0x18003a862  mov     ebx, 0C00D7170h
0x18003a867  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a86e  jb      short loc_18003A8BE
0x18003a870  mov     edx, 0C3h
0x18003a875  mov     dword ptr [rsp+68h+var_48], ebx
0x18003a879  jmp     short loc_18003A8A4
0x18003a87b  mov     eax, 80070216h
0x18003a880  mov     ebx, eax
0x18003a882  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a889  jb      short loc_18003A8BE
0x18003a88b  mov     edx, 0C2h
0x18003a890  jmp     short loc_18003A8A0
0x18003a892  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003a899  jb      short loc_18003A8BE
0x18003a89b  mov     edx, 0C1h
0x18003a8a0  mov     dword ptr [rsp+68h+var_48], eax
0x18003a8a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a8ab  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003a8b2  xor     r9d, r9d
0x18003a8b5  mov     rcx, [rcx+10h]
0x18003a8b9  call    WPP_SF_qD
0x18003a8be  xor     r13d, r13d
0x18003a8c1  test    rsi, rsi
0x18003a8c4  jz      short loc_18003A8CF
0x18003a8c6  mov     rcx, rsi; pv
0x18003a8c9  call    cs:__imp_CoTaskMemFree
0x18003a8cf  lea     rcx, [rbp+var_20]
0x18003a8d3  call    ??1?$CTUnkArray@UIMFSensorDeviceIdInternal@@@@QEAA@XZ; CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>(void)
0x18003a8d8  cmp     cs:byte_18005E5A5, 1
0x18003a8df  jb      short loc_18003A95C
0x18003a8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a8e8  lea     r8, WPP_376655425d2f3a200f8fa7e330fe4e70_Traceguids
0x18003a8ef  mov     edx, 0C4h
0x18003a8f4  mov     r9d, ebx
0x18003a8f7  mov     rcx, [rcx+0D8h]
0x18003a8fe  call    WPP_SF_d
0x18003a903  jmp     short loc_18003A95C
0x18003a905  mov     rax, [rbp+var_30]
0x18003a909  mov     [r12], rax
0x18003a90d  mov     eax, [rbp+arg_0]
0x18003a910  mov     [rbp+var_30], r13
0x18003a914  jmp     short loc_18003A92A
0x18003a916  mov     rax, [rbp+var_38]
0x18003a91a  test    rax, rax
0x18003a91d  jz      short loc_18003A92D
0x18003a91f  mov     [r12], rax
0x18003a923  mov     eax, [rbp+arg_8]
0x18003a926  mov     [rbp+var_38], r13
0x18003a92a  mov     [r15], eax
0x18003a92d  cmp     cs:byte_18005E5A5, 8
0x18003a934  jb      short loc_18003A95C
0x18003a936  mov     rax, [r12]
  ... truncated ...
```
