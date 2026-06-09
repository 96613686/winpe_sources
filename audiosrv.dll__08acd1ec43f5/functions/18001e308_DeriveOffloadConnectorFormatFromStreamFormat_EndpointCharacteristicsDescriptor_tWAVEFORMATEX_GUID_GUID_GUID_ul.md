# DeriveOffloadConnectorFormatFromStreamFormat(EndpointCharacteristicsDescriptor *,tWAVEFORMATEX *,_GUID,_GUID,_GUID,ulong,tWAVEFORMATEX * *)

- ea: `0x18001e308`
- end: `0x18001e72f`
- name: `?DeriveOffloadConnectorFormatFromStreamFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@PEAUtWAVEFORMATEX@@U_GUID@@22KPEAPEAU2@@Z`
- size: `1063`
- prototype: `int(struct EndpointCharacteristicsDescriptor *, struct tWAVEFORMATEX *, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, unsigned int, struct tWAVEFORMATEX **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ec9c`
- `0x180083df0`

## callees

- `0x180008a2c`
- `0x18001280c`
- `0x18001e308`
- `0x180021620`
- `0x180026514`
- `0x18002cbc4`
- `0x18003cf5c`
- `0x18003d040`
- `0x18006ad1c`
- `0x180143ce0`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e372`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e47b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e493`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e511`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e525`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e57f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e5ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e5de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e6e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e6fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e70f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e372`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e47b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e493`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e511`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e525`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e57f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e5ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e5de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e6e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e6fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e70f`

## string_xrefs

- `0x18001e383`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001e458`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001e4f2`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001e5ab`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001e613`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001e664`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DeriveOffloadConnectorFormatFromStreamFormat(
        CEndpointCharacteristics **a1,
        struct tWAVEFORMATEX *a2,
        struct tWAVEFORMATEX *a3,
        struct _GUID *a4,
        struct tWAVEFORMATEX *a5,
        unsigned int a6,
        struct tWAVEFORMATEX **pv)
{
  struct tWAVEFORMATEX **v10; // r12
  int OffloadDeviceFormat; // ebx
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 Data1; // r8d
  void *v13; // rcx
  struct tWAVEFORMATEX **v14; // rcx
  char v16; // si
  WORD v17; // cx
  bool v18; // bl
  int IsFormatSupportedByHwAudioEngine; // edi
  struct tWAVEFORMATEX *v20; // r9
  int v21; // esi
  struct tWAVEFORMATEX *v22; // rcx
  struct tWAVEFORMATEX **v23; // rcx
  struct tWAVEFORMATEX *v24; // rcx
  struct tWAVEFORMATEX *v25; // rcx
  DWORD nSamplesPerSec; // edx
  struct _GUID *v27; // rcx
  struct tWAVEFORMATEX *v28; // rcx
  struct tWAVEFORMATEX **v29; // rcx
  int v30; // eax
  __int64 v31; // rdx
  struct tWAVEFORMATEX *v32; // rax
  struct tWAVEFORMATEX *v33; // rcx
  struct tWAVEFORMATEX *v34; // rax
  struct tWAVEFORMATEX **v35; // rcx
  int v36; // [rsp+20h] [rbp-30h]
  int v37; // [rsp+20h] [rbp-30h]
  struct _GUID v38; // [rsp+30h] [rbp-20h] BYREF
  char v39; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  struct tWAVEFORMATEX *v41; // [rsp+90h] [rbp+40h] BYREF
  struct tWAVEFORMATEX *v42; // [rsp+A0h] [rbp+50h] BYREF

  v42 = a3;
  v10 = pv;
  *pv = 0;
  pv = 0;
  *(_QWORD *)&v38.Data1 = &pv;
  *(_QWORD *)v38.Data4 = 0;
  v39 = 1;
  OffloadDeviceFormat = CEndpointCharacteristics::GetOffloadDeviceFormat(*a1, (struct tWAVEFORMATEX **)v38.Data4);
  if ( v39 )
  {
    Data1 = v38.Data1;
    v13 = **(void ***)&v38.Data1;
    **(_QWORD **)&v38.Data1 = *(_QWORD *)v38.Data4;
    if ( v13 )
      CoTaskMemFree(v13);
  }
  if ( OffloadDeviceFormat < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)(unsigned int)OffloadDeviceFormat,
      v36);
    v14 = pv;
    pv = 0;
LABEL_6:
    if ( v14 )
      CoTaskMemFree(v14);
    return (unsigned int)OffloadDeviceFormat;
  }
  v16 = 1;
  v17 = *((_WORD *)pv + 1);
  v18 = v17 != a2->nChannels;
  if ( v17 < a2->nChannels
    && v17 >= 2u
    && *((_DWORD *)qword_180187300 + a6)
    && !(*(unsigned int (__fastcall **)(CEndpointCharacteristics *))(*(_QWORD *)*a1 + 56LL))(*a1)
    && CEndpointCharacteristics::GetVirtualSurroundEffectMode(*a1) == 1 )
  {
    v16 = 0;
    v18 = 1;
  }
  IsFormatSupportedByHwAudioEngine = -2147023728;
  v20 = 0;
  v42 = 0;
  if ( !v16 )
    goto LABEL_24;
  IsFormatSupportedByHwAudioEngine = CEndpointCharacteristics::IsFormatSupportedByHwAudioEngine(*a1, a2);
  if ( !IsFormatSupportedByHwAudioEngine )
  {
    *(_QWORD *)&v38.Data1 = &v42;
    *(_QWORD *)v38.Data4 = 0;
    v39 = 1;
    v21 = CloneWaveFormat(a2, (struct tWAVEFORMATEX **)v38.Data4);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v38);
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x180,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
        (const char *)(unsigned int)v21,
        v36);
      v22 = v42;
      v42 = 0;
      if ( v22 )
        CoTaskMemFree(v22);
      v23 = pv;
      pv = 0;
      if ( v23 )
        CoTaskMemFree(v23);
      return (unsigned int)v21;
    }
  }
  v20 = v42;
  if ( !v42 )
  {
LABEL_24:
    if ( v18 )
    {
      a5 = 0;
      *(_QWORD *)&v38.Data1 = &a5;
      *(_QWORD *)v38.Data4 = 0;
      v39 = 1;
      OffloadDeviceFormat = CloneWaveFormat((const struct tWAVEFORMATEX *)pv, (struct tWAVEFORMATEX **)v38.Data4);
      wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v38);
      if ( OffloadDeviceFormat < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x187,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
          (const char *)(unsigned int)OffloadDeviceFormat,
          v36);
        v24 = a5;
        a5 = 0;
        goto LABEL_27;
      }
      nSamplesPerSec = a2->nSamplesPerSec;
      a5->nSamplesPerSec = nSamplesPerSec;
      a5->nAvgBytesPerSec = nSamplesPerSec * a5->nBlockAlign;
      IsFormatSupportedByHwAudioEngine = CEndpointCharacteristics::IsFormatSupportedByHwAudioEngine(*a1, a5);
      if ( !IsFormatSupportedByHwAudioEngine )
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
          &v42,
          &a5);
      v27 = (struct _GUID *)a5;
      a5 = 0;
      if ( v27 )
        CoTaskMemFree(v27);
      v20 = v42;
    }
  }
  if ( IsFormatSupportedByHwAudioEngine >= 0 )
  {
    v38 = *a4;
    v30 = IsOffloadConnectorFormatSupportedForMixFormat(
            (struct EndpointCharacteristicsDescriptor *)a1,
            &v38,
            Data1,
            v20,
            v20);
    OffloadDeviceFormat = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x198,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
        (const char *)(unsigned int)v30,
        v37);
      goto LABEL_29;
    }
    v41 = 0;
    *(_QWORD *)&v38.Data1 = &v41;
    *(_QWORD *)v38.Data4 = 0;
    v39 = 1;
    OffloadDeviceFormat = CloneWaveFormat(a2, (struct tWAVEFORMATEX **)v38.Data4);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v38);
    if ( OffloadDeviceFormat >= 0 )
    {
      v38 = *a4;
      OffloadDeviceFormat = IsStreamFormatSupportedForMixFormat(
                              (struct EndpointCharacteristicsDescriptor *)a1,
                              &v38,
                              eOffloadConnector,
                              v42,
                              v41,
                              0);
      if ( OffloadDeviceFormat >= 0 )
      {
        if ( !OffloadDeviceFormat )
        {
          v32 = v42;
          v33 = 0;
          v42 = 0;
          *v10 = v32;
          v34 = v41;
          v41 = 0;
          if ( v34 )
          {
            CoTaskMemFree(v34);
            v33 = v42;
          }
          v42 = 0;
          if ( v33 )
            CoTaskMemFree(v33);
          v35 = pv;
          pv = 0;
          if ( v35 )
            CoTaskMemFree(v35);
          return 0;
        }
        OffloadDeviceFormat = -2005073917;
        v31 = 416;
      }
      else
      {
        v31 = 415;
      }
    }
    else
    {
      v31 = 411;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)(unsigned int)OffloadDeviceFormat,
      v37);
    v24 = v41;
    v41 = 0;
LABEL_27:
    if ( v24 )
      CoTaskMemFree(v24);
LABEL_29:
    v25 = v42;
    v42 = 0;
    if ( !v25 )
    {
LABEL_31:
      v14 = pv;
      pv = 0;
      goto LABEL_6;
    }
LABEL_30:
    CoTaskMemFree(v25);
    goto LABEL_31;
  }
  OffloadDeviceFormat = -2005139333;
  if ( IsFormatSupportedByHwAudioEngine == -2005139333 )
  {
    v42 = 0;
    if ( !v20 )
      goto LABEL_31;
    v25 = v20;
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x194,
    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
    (const char *)(unsigned int)IsFormatSupportedByHwAudioEngine,
    v36);
  v28 = v42;
  v42 = 0;
  if ( v28 )
    CoTaskMemFree(v28);
  v29 = pv;
  pv = 0;
  if ( v29 )
    CoTaskMemFree(v29);
  return (unsigned int)IsFormatSupportedByHwAudioEngine;
}

```

## disassembly

```asm
0x18001e308  mov     [rsp-38h+arg_8], rbx
0x18001e30d  mov     [rsp-38h+arg_10], r8
0x18001e312  push    rbp
0x18001e313  push    rsi
0x18001e314  push    rdi
0x18001e315  push    r12
0x18001e317  push    r13
0x18001e319  push    r14
0x18001e31b  push    r15
0x18001e31d  mov     rbp, rsp
0x18001e320  sub     rsp, 50h
0x18001e324  mov     r13, r9
0x18001e327  mov     r15, rdx
0x18001e32a  mov     r14, rcx
0x18001e32d  xor     edi, edi
0x18001e32f  mov     r12, [rbp+pv]
0x18001e333  mov     [r12], rdi
0x18001e337  mov     [rbp+pv], rdi
0x18001e33b  lea     rax, [rbp+pv]
0x18001e33f  mov     qword ptr [rbp+var_20.Data1], rax
0x18001e343  mov     qword ptr [rbp+var_20.Data4], rdi
0x18001e347  mov     [rbp+var_10], 1
0x18001e34b  lea     rdx, [rbp+var_20.Data4]; struct tWAVEFORMATEX **
0x18001e34f  mov     rcx, [rcx]; this
0x18001e352  call    ?GetOffloadDeviceFormat@CEndpointCharacteristics@@QEAAJPEAPEAUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::GetOffloadDeviceFormat(tWAVEFORMATEX * *)
0x18001e357  mov     ebx, eax
0x18001e359  cmp     [rbp+var_10], dil
0x18001e35d  jz      short loc_18001E378
0x18001e35f  mov     r8, qword ptr [rbp+var_20.Data1]
0x18001e363  mov     rcx, [r8]; pv
0x18001e366  mov     rdx, qword ptr [rbp+var_20.Data4]
0x18001e36a  mov     [r8], rdx
0x18001e36d  test    rcx, rcx
0x18001e370  jz      short loc_18001E378
0x18001e372  call    cs:__imp_CoTaskMemFree
0x18001e378  test    ebx, ebx
0x18001e37a  jns     short loc_18001E3AF
0x18001e37c  mov     rcx, [rbp+38h]; this
0x18001e380  mov     r9d, ebx; char *
0x18001e383  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001e38a  mov     edx, 15Dh; void *
0x18001e38f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e394  nop
0x18001e395  mov     rcx, [rbp+pv]; pv
0x18001e399  mov     [rbp+pv], rdi
0x18001e39d  test    rcx, rcx
0x18001e3a0  jz      short loc_18001E3A8
0x18001e3a2  call    cs:__imp_CoTaskMemFree
0x18001e3a8  mov     eax, ebx
0x18001e3aa  jmp     loc_18001E717
0x18001e3af  mov     sil, 1
0x18001e3b2  mov     rax, [rbp+pv]
0x18001e3b6  movzx   ecx, word ptr [rax+2]
0x18001e3ba  cmp     cx, [r15+2]
0x18001e3bf  setnz   bl
0x18001e3c2  jnb     short loc_18001E3FE
0x18001e3c4  cmp     cx, 2
0x18001e3c8  jb      short loc_18001E3FE
0x18001e3ca  mov     eax, [rbp+arg_28]
0x18001e3cd  lea     rcx, qword_180187300
0x18001e3d4  cmp     [rcx+rax*4], edi
0x18001e3d7  jz      short loc_18001E3FE
0x18001e3d9  mov     rcx, [r14]
0x18001e3dc  mov     rax, [rcx]
0x18001e3df  mov     rax, [rax+38h]
0x18001e3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3e8  test    eax, eax
0x18001e3ea  jnz     short loc_18001E3FE
0x18001e3ec  mov     rcx, [r14]; this
0x18001e3ef  call    ?GetVirtualSurroundEffectMode@CEndpointCharacteristics@@QEAAIXZ; CEndpointCharacteristics::GetVirtualSurroundEffectMode(void)
0x18001e3f4  cmp     eax, 1
0x18001e3f7  jnz     short loc_18001E3FE
0x18001e3f9  mov     sil, dil
0x18001e3fc  mov     bl, al
0x18001e3fe  mov     edi, 80070490h
0x18001e403  xor     r9d, r9d
0x18001e406  mov     [rbp+arg_10], r9
0x18001e40a  test    sil, sil
0x18001e40d  jz      loc_18001E4B1
0x18001e413  mov     rdx, r15; struct tWAVEFORMATEX *
0x18001e416  mov     rcx, [r14]; this
0x18001e419  call    ?IsFormatSupportedByHwAudioEngine@CEndpointCharacteristics@@QEAAJPEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::IsFormatSupportedByHwAudioEngine(tWAVEFORMATEX const *)
0x18001e41e  mov     edi, eax
0x18001e420  xor     esi, esi
0x18001e422  test    eax, eax
0x18001e424  jnz     short loc_18001E4A2
0x18001e426  lea     rax, [rbp+arg_10]
0x18001e42a  mov     qword ptr [rbp+var_20.Data1], rax
0x18001e42e  mov     qword ptr [rbp+var_20.Data4], rsi
0x18001e432  mov     [rbp+var_10], 1
0x18001e436  lea     rdx, [rbp+var_20.Data4]; struct tWAVEFORMATEX **
0x18001e43a  mov     rcx, r15; Src
0x18001e43d  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001e442  mov     esi, eax
0x18001e444  lea     rcx, [rbp+var_20]
0x18001e448  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001e44d  test    esi, esi
0x18001e44f  jns     short loc_18001E4A0
0x18001e451  mov     rcx, [rbp+38h]; this
0x18001e455  mov     r9d, esi; char *
0x18001e458  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001e45f  mov     edx, 180h; void *
0x18001e464  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e469  nop
0x18001e46a  mov     rcx, [rbp+arg_10]; pv
0x18001e46e  mov     [rbp+arg_10], 0
0x18001e476  test    rcx, rcx
0x18001e479  jz      short loc_18001E482
0x18001e47b  call    cs:__imp_CoTaskMemFree
0x18001e481  nop
0x18001e482  mov     rcx, [rbp+pv]; pv
0x18001e486  mov     [rbp+pv], 0
0x18001e48e  test    rcx, rcx
0x18001e491  jz      short loc_18001E499
0x18001e493  call    cs:__imp_CoTaskMemFree
0x18001e499  mov     eax, esi
0x18001e49b  jmp     loc_18001E717
0x18001e4a0  xor     esi, esi
0x18001e4a2  mov     r9, [rbp+arg_10]
0x18001e4a6  test    r9, r9
0x18001e4a9  jnz     loc_18001E589
0x18001e4af  jmp     short loc_18001E4B3
0x18001e4b1  xor     esi, esi
0x18001e4b3  test    bl, bl
0x18001e4b5  jz      loc_18001E589
0x18001e4bb  mov     [rbp+arg_20], rsi
0x18001e4bf  lea     rax, [rbp+arg_20]
0x18001e4c3  mov     qword ptr [rbp+var_20.Data1], rax
0x18001e4c7  mov     qword ptr [rbp+var_20.Data4], rsi
0x18001e4cb  mov     [rbp+var_10], 1
0x18001e4cf  lea     rdx, [rbp+var_20.Data4]; struct tWAVEFORMATEX **
0x18001e4d3  mov     rcx, [rbp+pv]; Src
0x18001e4d7  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001e4dc  mov     ebx, eax
0x18001e4de  lea     rcx, [rbp+var_20]
0x18001e4e2  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001e4e7  test    ebx, ebx
0x18001e4e9  jns     short loc_18001E539
0x18001e4eb  mov     rcx, [rbp+38h]; this
0x18001e4ef  mov     r9d, ebx; char *
0x18001e4f2  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001e4f9  mov     edx, 187h; void *
0x18001e4fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e503  nop
0x18001e504  mov     rcx, [rbp+arg_20]; pv
0x18001e508  mov     [rbp+arg_20], rsi
0x18001e50c  test    rcx, rcx
0x18001e50f  jz      short loc_18001E518
0x18001e511  call    cs:__imp_CoTaskMemFree
0x18001e517  nop
0x18001e518  mov     rcx, [rbp+arg_10]; pv
0x18001e51c  mov     [rbp+arg_10], rsi
0x18001e520  test    rcx, rcx
0x18001e523  jz      short loc_18001E52C
0x18001e525  call    cs:__imp_CoTaskMemFree
0x18001e52b  nop
0x18001e52c  mov     rcx, [rbp+pv]
0x18001e530  mov     [rbp+pv], rsi
0x18001e534  jmp     loc_18001E39D
0x18001e539  mov     edx, [r15+4]
0x18001e53d  mov     rax, [rbp+arg_20]
0x18001e541  mov     [rax+4], edx
0x18001e544  mov     rax, [rbp+arg_20]
0x18001e548  movzx   ecx, word ptr [rax+0Ch]
0x18001e54c  imul    ecx, edx
0x18001e54f  mov     [rax+8], ecx
0x18001e552  mov     rdx, [rbp+arg_20]; struct tWAVEFORMATEX *
0x18001e556  mov     rcx, [r14]; this
0x18001e559  call    ?IsFormatSupportedByHwAudioEngine@CEndpointCharacteristics@@QEAAJPEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::IsFormatSupportedByHwAudioEngine(tWAVEFORMATEX const *)
0x18001e55e  mov     edi, eax
0x18001e560  test    eax, eax
0x18001e562  jnz     short loc_18001E572
0x18001e564  lea     rdx, [rbp+arg_20]
0x18001e568  lea     rcx, [rbp+arg_10]
0x18001e56c  call    ??4?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18001e571  nop
0x18001e572  mov     rcx, [rbp+arg_20]; pv
0x18001e576  mov     [rbp+arg_20], rsi
0x18001e57a  test    rcx, rcx
0x18001e57d  jz      short loc_18001E585
0x18001e57f  call    cs:__imp_CoTaskMemFree
0x18001e585  mov     r9, [rbp+arg_10]; struct tWAVEFORMATEX *
0x18001e589  test    edi, edi
0x18001e58b  jns     short loc_18001E5EB
0x18001e58d  mov     ebx, 887C007Bh
0x18001e592  cmp     edi, ebx
0x18001e594  jnz     short loc_18001E5A4
0x18001e596  mov     [rbp+arg_10], rsi
0x18001e59a  test    r9, r9
0x18001e59d  jz      short loc_18001E52C
0x18001e59f  mov     rcx, r9
0x18001e5a2  jmp     short loc_18001E525
0x18001e5a4  mov     rcx, [rbp+38h]; this
0x18001e5a8  mov     r9d, edi; char *
0x18001e5ab  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001e5b2  mov     edx, 194h; void *
0x18001e5b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e5bc  nop
0x18001e5bd  mov     rcx, [rbp+arg_10]; pv
0x18001e5c1  mov     [rbp+arg_10], rsi
0x18001e5c5  test    rcx, rcx
0x18001e5c8  jz      short loc_18001E5D1
0x18001e5ca  call    cs:__imp_CoTaskMemFree
0x18001e5d0  nop
0x18001e5d1  mov     rcx, [rbp+pv]; pv
0x18001e5d5  mov     [rbp+pv], rsi
0x18001e5d9  test    rcx, rcx
0x18001e5dc  jz      short loc_18001E5E4
0x18001e5de  call    cs:__imp_CoTaskMemFree
0x18001e5e4  mov     eax, edi
0x18001e5e6  jmp     loc_18001E717
0x18001e5eb  movaps  xmm0, xmmword ptr [r13+0]
0x18001e5f0  movdqa  xmmword ptr [rbp+var_20.Data1], xmm0
0x18001e5f5  mov     [rsp+50h+var_30], r9; int
0x18001e5fa  lea     rdx, [rbp+var_20]; struct _GUID
0x18001e5fe  mov     rcx, r14; struct EndpointCharacteristicsDescriptor *
0x18001e601  call    ?IsOffloadConnectorFormatSupportedForMixFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@3@Z; IsOffloadConnectorFormatSupportedForMixFormat(EndpointCharacteristicsDescriptor *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,tWAVEFORMATEX const *)
0x18001e606  mov     ebx, eax
0x18001e608  test    eax, eax
0x18001e60a  jns     short loc_18001E629
0x18001e60c  mov     rcx, [rbp+38h]; this
0x18001e610  mov     r9d, eax; char *
0x18001e613  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001e61a  mov     edx, 198h; void *
0x18001e61f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e624  jmp     loc_18001E518
0x18001e629  mov     [rbp+arg_0], rsi
0x18001e62d  lea     rax, [rbp+arg_0]
0x18001e631  mov     qword ptr [rbp+var_20.Data1], rax
0x18001e635  mov     qword ptr [rbp+var_20.Data4], rsi
0x18001e639  mov     [rbp+var_10], 1
0x18001e63d  lea     rdx, [rbp+var_20.Data4]; struct tWAVEFORMATEX **
0x18001e641  mov     rcx, r15; Src
0x18001e644  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001e649  mov     ebx, eax
0x18001e64b  lea     rcx, [rbp+var_20]
0x18001e64f  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001e654  test    ebx, ebx
0x18001e656  jns     short loc_18001E67E
0x18001e658  mov     edx, 19Bh; void *
0x18001e65d  mov     rcx, [rbp+38h]; this
0x18001e661  mov     r9d, ebx; char *
0x18001e664  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001e66b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e670  nop
0x18001e671  mov     rcx, [rbp+arg_0]
0x18001e675  mov     [rbp+arg_0], rsi
0x18001e679  jmp     loc_18001E50C
0x18001e67e  mov     rax, [rbp+arg_0]
0x18001e682  movaps  xmm0, xmmword ptr [r13+0]
0x18001e687  movdqa  xmmword ptr [rbp+var_20.Data1], xmm0
0x18001e68c  mov     [rsp+50h+var_28], rsi; struct tWAVEFORMATEX **
0x18001e691  mov     [rsp+50h+var_30], rax; struct tWAVEFORMATEX *
0x18001e696  mov     r9, [rbp+arg_10]; struct tWAVEFORMATEX *
0x18001e69a  mov     r8d, 1; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001e6a0  lea     rdx, [rbp+var_20]; struct _GUID
0x18001e6a4  mov     rcx, r14; struct EndpointCharacteristicsDescriptor *
0x18001e6a7  call    ?IsStreamFormatSupportedForMixFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@3PEAPEAU4@@Z; IsStreamFormatSupportedForMixFormat(EndpointCharacteristicsDescriptor *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001e6ac  mov     ebx, eax
0x18001e6ae  test    eax, eax
0x18001e6b0  jns     short loc_18001E6B9
0x18001e6b2  mov     edx, 19Fh
0x18001e6b7  jmp     short loc_18001E65D
0x18001e6b9  test    ebx, ebx
0x18001e6bb  jz      short loc_18001E6C9
0x18001e6bd  mov     ebx, 887D0003h
0x18001e6c2  mov     edx, 1A0h
0x18001e6c7  jmp     short loc_18001E65D
0x18001e6c9  mov     rax, [rbp+arg_10]
0x18001e6cd  mov     rcx, rsi
0x18001e6d0  mov     [rbp+arg_10], rcx
0x18001e6d4  mov     [r12], rax
0x18001e6d8  mov     rax, [rbp+arg_0]
0x18001e6dc  mov     [rbp+arg_0], rsi
0x18001e6e0  test    rax, rax
0x18001e6e3  jz      short loc_18001E6F2
0x18001e6e5  mov     rcx, rax; pv
0x18001e6e8  call    cs:__imp_CoTaskMemFree
0x18001e6ee  mov     rcx, [rbp+arg_10]; pv
0x18001e6f2  mov     [rbp+arg_10], rsi
0x18001e6f6  test    rcx, rcx
0x18001e6f9  jz      short loc_18001E702
0x18001e6fb  call    cs:__imp_CoTaskMemFree
0x18001e701  nop
0x18001e702  mov     rcx, [rbp+pv]; pv
0x18001e706  mov     [rbp+pv], rsi
0x18001e70a  test    rcx, rcx
0x18001e70d  jz      short loc_18001E715
0x18001e70f  call    cs:__imp_CoTaskMemFree
0x18001e715  xor     eax, eax
0x18001e717  mov     rbx, [rsp+50h+arg_8]
0x18001e71f  add     rsp, 50h
0x18001e723  pop     r15
0x18001e725  pop     r14
0x18001e727  pop     r13
0x18001e729  pop     r12
0x18001e72b  pop     rdi
0x18001e72c  pop     rsi
0x18001e72d  pop     rbp
0x18001e72e  retn
  ... truncated ...
```
