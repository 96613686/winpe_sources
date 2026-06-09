# DeriveOffloadConnectorFormatFromStreamFormat(EndpointCharacteristicsDescriptor *,tWAVEFORMATEX *,_GUID,_GUID,_GUID,ulong,tWAVEFORMATEX * *)

- ea: `0x18001e1b8`
- end: `0x18001e5df`
- name: `?DeriveOffloadConnectorFormatFromStreamFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@PEAUtWAVEFORMATEX@@U_GUID@@22KPEAPEAU2@@Z`
- size: `1063`
- prototype: `int(struct EndpointCharacteristicsDescriptor *, struct tWAVEFORMATEX *, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, unsigned int, struct tWAVEFORMATEX **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001eb4c`
- `0x1800842f0`

## callees

- `0x1800088dc`
- `0x1800126bc`
- `0x18001e1b8`
- `0x1800214d0`
- `0x1800263c4`
- `0x18002ca64`
- `0x18003cdfc`
- `0x18003cee0`
- `0x18006b1ac`
- `0x1801433d0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e222`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e32b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e3c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e3d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e42f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e47a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e48e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e5ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e5bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e222`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e32b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e3c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e3d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e42f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e47a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e48e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e5ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e5bf`

## string_xrefs

- `0x18001e233`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001e308`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001e3a2`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001e45b`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001e4c3`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001e514`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`

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
    && dword_1801862A0[a6]
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
0x18001e1b8  mov     [rsp-38h+arg_8], rbx
0x18001e1bd  mov     [rsp-38h+arg_10], r8
0x18001e1c2  push    rbp
0x18001e1c3  push    rsi
0x18001e1c4  push    rdi
0x18001e1c5  push    r12
0x18001e1c7  push    r13
0x18001e1c9  push    r14
0x18001e1cb  push    r15
0x18001e1cd  mov     rbp, rsp
0x18001e1d0  sub     rsp, 50h
0x18001e1d4  mov     r13, r9
0x18001e1d7  mov     r15, rdx
0x18001e1da  mov     r14, rcx
0x18001e1dd  xor     edi, edi
0x18001e1df  mov     r12, [rbp+pv]
0x18001e1e3  mov     [r12], rdi
0x18001e1e7  mov     [rbp+pv], rdi
0x18001e1eb  lea     rax, [rbp+pv]
0x18001e1ef  mov     qword ptr [rbp+var_20.Data1], rax
0x18001e1f3  mov     qword ptr [rbp+var_20.Data4], rdi
0x18001e1f7  mov     [rbp+var_10], 1
0x18001e1fb  lea     rdx, [rbp+var_20.Data4]; struct tWAVEFORMATEX **
0x18001e1ff  mov     rcx, [rcx]; this
0x18001e202  call    ?GetOffloadDeviceFormat@CEndpointCharacteristics@@QEAAJPEAPEAUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::GetOffloadDeviceFormat(tWAVEFORMATEX * *)
0x18001e207  mov     ebx, eax
0x18001e209  cmp     [rbp+var_10], dil
0x18001e20d  jz      short loc_18001E228
0x18001e20f  mov     r8, qword ptr [rbp+var_20.Data1]
0x18001e213  mov     rcx, [r8]; pv
0x18001e216  mov     rdx, qword ptr [rbp+var_20.Data4]
0x18001e21a  mov     [r8], rdx
0x18001e21d  test    rcx, rcx
0x18001e220  jz      short loc_18001E228
0x18001e222  call    cs:__imp_CoTaskMemFree
0x18001e228  test    ebx, ebx
0x18001e22a  jns     short loc_18001E25F
0x18001e22c  mov     rcx, [rbp+38h]; this
0x18001e230  mov     r9d, ebx; char *
0x18001e233  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001e23a  mov     edx, 15Dh; void *
0x18001e23f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e244  nop
0x18001e245  mov     rcx, [rbp+pv]; pv
0x18001e249  mov     [rbp+pv], rdi
0x18001e24d  test    rcx, rcx
0x18001e250  jz      short loc_18001E258
0x18001e252  call    cs:__imp_CoTaskMemFree
0x18001e258  mov     eax, ebx
0x18001e25a  jmp     loc_18001E5C7
0x18001e25f  mov     sil, 1
0x18001e262  mov     rax, [rbp+pv]
0x18001e266  movzx   ecx, word ptr [rax+2]
0x18001e26a  cmp     cx, [r15+2]
0x18001e26f  setnz   bl
0x18001e272  jnb     short loc_18001E2AE
0x18001e274  cmp     cx, 2
0x18001e278  jb      short loc_18001E2AE
0x18001e27a  mov     eax, [rbp+arg_28]
0x18001e27d  lea     rcx, dword_1801862A0
0x18001e284  cmp     [rcx+rax*4], edi
0x18001e287  jz      short loc_18001E2AE
0x18001e289  mov     rcx, [r14]
0x18001e28c  mov     rax, [rcx]
0x18001e28f  mov     rax, [rax+38h]
0x18001e293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e298  test    eax, eax
0x18001e29a  jnz     short loc_18001E2AE
0x18001e29c  mov     rcx, [r14]; this
0x18001e29f  call    ?GetVirtualSurroundEffectMode@CEndpointCharacteristics@@QEAAIXZ; CEndpointCharacteristics::GetVirtualSurroundEffectMode(void)
0x18001e2a4  cmp     eax, 1
0x18001e2a7  jnz     short loc_18001E2AE
0x18001e2a9  mov     sil, dil
0x18001e2ac  mov     bl, al
0x18001e2ae  mov     edi, 80070490h
0x18001e2b3  xor     r9d, r9d
0x18001e2b6  mov     [rbp+arg_10], r9
0x18001e2ba  test    sil, sil
0x18001e2bd  jz      loc_18001E361
0x18001e2c3  mov     rdx, r15; struct tWAVEFORMATEX *
0x18001e2c6  mov     rcx, [r14]; this
0x18001e2c9  call    ?IsFormatSupportedByHwAudioEngine@CEndpointCharacteristics@@QEAAJPEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::IsFormatSupportedByHwAudioEngine(tWAVEFORMATEX const *)
0x18001e2ce  mov     edi, eax
0x18001e2d0  xor     esi, esi
0x18001e2d2  test    eax, eax
0x18001e2d4  jnz     short loc_18001E352
0x18001e2d6  lea     rax, [rbp+arg_10]
0x18001e2da  mov     qword ptr [rbp+var_20.Data1], rax
0x18001e2de  mov     qword ptr [rbp+var_20.Data4], rsi
0x18001e2e2  mov     [rbp+var_10], 1
0x18001e2e6  lea     rdx, [rbp+var_20.Data4]; struct tWAVEFORMATEX **
0x18001e2ea  mov     rcx, r15; Src
0x18001e2ed  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001e2f2  mov     esi, eax
0x18001e2f4  lea     rcx, [rbp+var_20]
0x18001e2f8  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001e2fd  test    esi, esi
0x18001e2ff  jns     short loc_18001E350
0x18001e301  mov     rcx, [rbp+38h]; this
0x18001e305  mov     r9d, esi; char *
0x18001e308  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001e30f  mov     edx, 180h; void *
0x18001e314  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e319  nop
0x18001e31a  mov     rcx, [rbp+arg_10]; pv
0x18001e31e  mov     [rbp+arg_10], 0
0x18001e326  test    rcx, rcx
0x18001e329  jz      short loc_18001E332
0x18001e32b  call    cs:__imp_CoTaskMemFree
0x18001e331  nop
0x18001e332  mov     rcx, [rbp+pv]; pv
0x18001e336  mov     [rbp+pv], 0
0x18001e33e  test    rcx, rcx
0x18001e341  jz      short loc_18001E349
0x18001e343  call    cs:__imp_CoTaskMemFree
0x18001e349  mov     eax, esi
0x18001e34b  jmp     loc_18001E5C7
0x18001e350  xor     esi, esi
0x18001e352  mov     r9, [rbp+arg_10]
0x18001e356  test    r9, r9
0x18001e359  jnz     loc_18001E439
0x18001e35f  jmp     short loc_18001E363
0x18001e361  xor     esi, esi
0x18001e363  test    bl, bl
0x18001e365  jz      loc_18001E439
0x18001e36b  mov     [rbp+arg_20], rsi
0x18001e36f  lea     rax, [rbp+arg_20]
0x18001e373  mov     qword ptr [rbp+var_20.Data1], rax
0x18001e377  mov     qword ptr [rbp+var_20.Data4], rsi
0x18001e37b  mov     [rbp+var_10], 1
0x18001e37f  lea     rdx, [rbp+var_20.Data4]; struct tWAVEFORMATEX **
0x18001e383  mov     rcx, [rbp+pv]; Src
0x18001e387  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001e38c  mov     ebx, eax
0x18001e38e  lea     rcx, [rbp+var_20]
0x18001e392  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001e397  test    ebx, ebx
0x18001e399  jns     short loc_18001E3E9
0x18001e39b  mov     rcx, [rbp+38h]; this
0x18001e39f  mov     r9d, ebx; char *
0x18001e3a2  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001e3a9  mov     edx, 187h; void *
0x18001e3ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e3b3  nop
0x18001e3b4  mov     rcx, [rbp+arg_20]; pv
0x18001e3b8  mov     [rbp+arg_20], rsi
0x18001e3bc  test    rcx, rcx
0x18001e3bf  jz      short loc_18001E3C8
0x18001e3c1  call    cs:__imp_CoTaskMemFree
0x18001e3c7  nop
0x18001e3c8  mov     rcx, [rbp+arg_10]; pv
0x18001e3cc  mov     [rbp+arg_10], rsi
0x18001e3d0  test    rcx, rcx
0x18001e3d3  jz      short loc_18001E3DC
0x18001e3d5  call    cs:__imp_CoTaskMemFree
0x18001e3db  nop
0x18001e3dc  mov     rcx, [rbp+pv]
0x18001e3e0  mov     [rbp+pv], rsi
0x18001e3e4  jmp     loc_18001E24D
0x18001e3e9  mov     edx, [r15+4]
0x18001e3ed  mov     rax, [rbp+arg_20]
0x18001e3f1  mov     [rax+4], edx
0x18001e3f4  mov     rax, [rbp+arg_20]
0x18001e3f8  movzx   ecx, word ptr [rax+0Ch]
0x18001e3fc  imul    ecx, edx
0x18001e3ff  mov     [rax+8], ecx
0x18001e402  mov     rdx, [rbp+arg_20]; struct tWAVEFORMATEX *
0x18001e406  mov     rcx, [r14]; this
0x18001e409  call    ?IsFormatSupportedByHwAudioEngine@CEndpointCharacteristics@@QEAAJPEBUtWAVEFORMATEX@@@Z; CEndpointCharacteristics::IsFormatSupportedByHwAudioEngine(tWAVEFORMATEX const *)
0x18001e40e  mov     edi, eax
0x18001e410  test    eax, eax
0x18001e412  jnz     short loc_18001E422
0x18001e414  lea     rdx, [rbp+arg_20]
0x18001e418  lea     rcx, [rbp+arg_10]
0x18001e41c  call    ??4?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18001e421  nop
0x18001e422  mov     rcx, [rbp+arg_20]; pv
0x18001e426  mov     [rbp+arg_20], rsi
0x18001e42a  test    rcx, rcx
0x18001e42d  jz      short loc_18001E435
0x18001e42f  call    cs:__imp_CoTaskMemFree
0x18001e435  mov     r9, [rbp+arg_10]; struct tWAVEFORMATEX *
0x18001e439  test    edi, edi
0x18001e43b  jns     short loc_18001E49B
0x18001e43d  mov     ebx, 887C007Bh
0x18001e442  cmp     edi, ebx
0x18001e444  jnz     short loc_18001E454
0x18001e446  mov     [rbp+arg_10], rsi
0x18001e44a  test    r9, r9
0x18001e44d  jz      short loc_18001E3DC
0x18001e44f  mov     rcx, r9
0x18001e452  jmp     short loc_18001E3D5
0x18001e454  mov     rcx, [rbp+38h]; this
0x18001e458  mov     r9d, edi; char *
0x18001e45b  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001e462  mov     edx, 194h; void *
0x18001e467  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e46c  nop
0x18001e46d  mov     rcx, [rbp+arg_10]; pv
0x18001e471  mov     [rbp+arg_10], rsi
0x18001e475  test    rcx, rcx
0x18001e478  jz      short loc_18001E481
0x18001e47a  call    cs:__imp_CoTaskMemFree
0x18001e480  nop
0x18001e481  mov     rcx, [rbp+pv]; pv
0x18001e485  mov     [rbp+pv], rsi
0x18001e489  test    rcx, rcx
0x18001e48c  jz      short loc_18001E494
0x18001e48e  call    cs:__imp_CoTaskMemFree
0x18001e494  mov     eax, edi
0x18001e496  jmp     loc_18001E5C7
0x18001e49b  movaps  xmm0, xmmword ptr [r13+0]
0x18001e4a0  movdqa  xmmword ptr [rbp+var_20.Data1], xmm0
0x18001e4a5  mov     [rsp+50h+var_30], r9; int
0x18001e4aa  lea     rdx, [rbp+var_20]; struct _GUID
0x18001e4ae  mov     rcx, r14; struct EndpointCharacteristicsDescriptor *
0x18001e4b1  call    ?IsOffloadConnectorFormatSupportedForMixFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@3@Z; IsOffloadConnectorFormatSupportedForMixFormat(EndpointCharacteristicsDescriptor *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,tWAVEFORMATEX const *)
0x18001e4b6  mov     ebx, eax
0x18001e4b8  test    eax, eax
0x18001e4ba  jns     short loc_18001E4D9
0x18001e4bc  mov     rcx, [rbp+38h]; this
0x18001e4c0  mov     r9d, eax; char *
0x18001e4c3  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001e4ca  mov     edx, 198h; void *
0x18001e4cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e4d4  jmp     loc_18001E3C8
0x18001e4d9  mov     [rbp+arg_0], rsi
0x18001e4dd  lea     rax, [rbp+arg_0]
0x18001e4e1  mov     qword ptr [rbp+var_20.Data1], rax
0x18001e4e5  mov     qword ptr [rbp+var_20.Data4], rsi
0x18001e4e9  mov     [rbp+var_10], 1
0x18001e4ed  lea     rdx, [rbp+var_20.Data4]; struct tWAVEFORMATEX **
0x18001e4f1  mov     rcx, r15; Src
0x18001e4f4  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001e4f9  mov     ebx, eax
0x18001e4fb  lea     rcx, [rbp+var_20]
0x18001e4ff  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001e504  test    ebx, ebx
0x18001e506  jns     short loc_18001E52E
0x18001e508  mov     edx, 19Bh; void *
0x18001e50d  mov     rcx, [rbp+38h]; this
0x18001e511  mov     r9d, ebx; char *
0x18001e514  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001e51b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e520  nop
0x18001e521  mov     rcx, [rbp+arg_0]
0x18001e525  mov     [rbp+arg_0], rsi
0x18001e529  jmp     loc_18001E3BC
0x18001e52e  mov     rax, [rbp+arg_0]
0x18001e532  movaps  xmm0, xmmword ptr [r13+0]
0x18001e537  movdqa  xmmword ptr [rbp+var_20.Data1], xmm0
0x18001e53c  mov     [rsp+50h+var_28], rsi; struct tWAVEFORMATEX **
0x18001e541  mov     [rsp+50h+var_30], rax; struct tWAVEFORMATEX *
0x18001e546  mov     r9, [rbp+arg_10]; struct tWAVEFORMATEX *
0x18001e54a  mov     r8d, 1; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001e550  lea     rdx, [rbp+var_20]; struct _GUID
0x18001e554  mov     rcx, r14; struct EndpointCharacteristicsDescriptor *
0x18001e557  call    ?IsStreamFormatSupportedForMixFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@3PEAPEAU4@@Z; IsStreamFormatSupportedForMixFormat(EndpointCharacteristicsDescriptor *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001e55c  mov     ebx, eax
0x18001e55e  test    eax, eax
0x18001e560  jns     short loc_18001E569
0x18001e562  mov     edx, 19Fh
0x18001e567  jmp     short loc_18001E50D
0x18001e569  test    ebx, ebx
0x18001e56b  jz      short loc_18001E579
0x18001e56d  mov     ebx, 887D0003h
0x18001e572  mov     edx, 1A0h
0x18001e577  jmp     short loc_18001E50D
0x18001e579  mov     rax, [rbp+arg_10]
0x18001e57d  mov     rcx, rsi
0x18001e580  mov     [rbp+arg_10], rcx
0x18001e584  mov     [r12], rax
0x18001e588  mov     rax, [rbp+arg_0]
0x18001e58c  mov     [rbp+arg_0], rsi
0x18001e590  test    rax, rax
0x18001e593  jz      short loc_18001E5A2
0x18001e595  mov     rcx, rax; pv
0x18001e598  call    cs:__imp_CoTaskMemFree
0x18001e59e  mov     rcx, [rbp+arg_10]; pv
0x18001e5a2  mov     [rbp+arg_10], rsi
0x18001e5a6  test    rcx, rcx
0x18001e5a9  jz      short loc_18001E5B2
0x18001e5ab  call    cs:__imp_CoTaskMemFree
0x18001e5b1  nop
0x18001e5b2  mov     rcx, [rbp+pv]; pv
0x18001e5b6  mov     [rbp+pv], rsi
0x18001e5ba  test    rcx, rcx
0x18001e5bd  jz      short loc_18001E5C5
0x18001e5bf  call    cs:__imp_CoTaskMemFree
0x18001e5c5  xor     eax, eax
0x18001e5c7  mov     rbx, [rsp+50h+arg_8]
0x18001e5cf  add     rsp, 50h
0x18001e5d3  pop     r15
0x18001e5d5  pop     r14
0x18001e5d7  pop     r13
0x18001e5d9  pop     r12
0x18001e5db  pop     rdi
0x18001e5dc  pop     rsi
0x18001e5dd  pop     rbp
0x18001e5de  retn
  ... truncated ...
```
