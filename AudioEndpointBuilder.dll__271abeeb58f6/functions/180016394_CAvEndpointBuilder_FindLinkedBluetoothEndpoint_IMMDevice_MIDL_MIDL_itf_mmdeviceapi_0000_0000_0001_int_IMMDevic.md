# CAvEndpointBuilder::FindLinkedBluetoothEndpoint(IMMDevice *,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,int,IMMDevice * *)

- ea: `0x180016394`
- end: `0x1800165e5`
- name: `?FindLinkedBluetoothEndpoint@CAvEndpointBuilder@@AEAAJPEAUIMMDevice@@W4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@HPEAPEAU2@@Z`
- size: `593`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *__hidden this, struct IMMDevice *, enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001, int, struct IMMDevice **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800152ec`

## callees

- `0x180006b0c`
- `0x180010da8`
- `0x180016394`
- `0x1800165ec`
- `0x18001707c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800164d2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016532`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800165b1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800164d2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016532`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800165b1`

## string_xrefs

- `0x1800163ec`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180016438`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800164a6`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180016512`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18001657f`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CAvEndpointBuilder::FindLinkedBluetoothEndpoint(
        CAvEndpointBuilder *this,
        struct IMMDevice *a2,
        unsigned int a3,
        int a4,
        struct IMMDevice **a5)
{
  struct IMMDevice **v7; // rdi
  struct IMMDeviceVtbl *lpVtbl; // rax
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  struct IUnknownVtbl *v14; // rax
  int v15; // eax
  int v16; // eax
  unsigned int i; // ebx
  int v19; // eax
  int v20; // [rsp+20h] [rbp-30h]
  int v21; // [rsp+20h] [rbp-30h]
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v23; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  CAvEndpointBuilder *v25; // [rsp+70h] [rbp+20h] BYREF
  __int64 v26; // [rsp+78h] [rbp+28h] BYREF

  v25 = this;
  v7 = a5;
  *a5 = 0;
  lpVtbl = a2->lpVtbl;
  v26 = 0;
  v9 = ((__int64 (__fastcall *)(struct IMMDevice *, __int64, __int64 *))lpVtbl->OpenPropertyStore)(a2, 2, &v26);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1585,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v9,
      v20);
LABEL_17:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
    return v10;
  }
  *(_OWORD *)pvar = 0;
  v23 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v26 + 40LL))(
          v26,
          &PKEY_Device_ContainerId,
          pvar);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = (unsigned int)v11;
    v13 = 5513;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)v12,
      v20);
LABEL_16:
    PropVariantClear(pvar);
    goto LABEL_17;
  }
  if ( LOWORD(pvar[0]) != 72 )
  {
    v10 = -2147024809;
    v12 = 2147942487LL;
    v13 = 5514;
    goto LABEL_5;
  }
  a5 = 0;
  LODWORD(v25) = 0;
  v14 = g_DeviceEnumerator->lpVtbl;
  a5 = 0;
  v15 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, __int64, struct IMMDevice ***))v14[1].QueryInterface)(
          g_DeviceEnumerator,
          a3,
          15,
          &a5);
  v10 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x158F,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v15,
      v20);
    if ( a5 )
      ((void (__fastcall *)(struct IMMDevice **))(*a5)[2].lpVtbl)(a5);
    PropVariantClear(pvar);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    return v10;
  }
  v16 = ((__int64 (__fastcall *)(struct IMMDevice **, CAvEndpointBuilder **))(*a5)[3].lpVtbl)(a5, &v25);
  v10 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1591,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v16,
      v20);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&a5);
    goto LABEL_16;
  }
  for ( i = 0; i < (unsigned int)v25; ++i )
  {
    if ( *v7 )
      break;
    v19 = CheckBluetoothEndpoint(i, a3, a4, (__int64)pvar, (__int64 *)a5, v7);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1596,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v19,
        v21);
  }
  if ( a5 )
    ((void (__fastcall *)(struct IMMDevice **))(*a5)[2].lpVtbl)(a5);
  PropVariantClear(pvar);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return 0;
}

```

## disassembly

```asm
0x180016394  mov     [rsp-18h+arg_10], rbx
0x180016399  mov     [rsp-18h+arg_18], rsi
0x18001639e  mov     [rsp-18h+arg_0], rcx
0x1800163a3  push    rbp
0x1800163a4  push    rdi
0x1800163a5  push    r14
0x1800163a7  mov     rbp, rsp
0x1800163aa  sub     rsp, 50h
0x1800163ae  mov     r14d, r9d
0x1800163b1  mov     esi, r8d
0x1800163b4  mov     rcx, rdx
0x1800163b7  mov     rdi, [rbp+arg_20]
0x1800163bb  mov     qword ptr [rdi], 0
0x1800163c2  mov     rax, [rdx]
0x1800163c5  mov     [rbp+arg_8], 0
0x1800163cd  lea     r8, [rbp+arg_8]
0x1800163d1  mov     edx, 2
0x1800163d6  mov     rax, [rax+20h]
0x1800163da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163df  mov     ebx, eax
0x1800163e1  test    eax, eax
0x1800163e3  jns     short loc_180016402
0x1800163e5  mov     rcx, [rbp+18h]; this
0x1800163e9  mov     r9d, eax; char *
0x1800163ec  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800163f3  mov     edx, 1585h; void *
0x1800163f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800163fd  jmp     loc_180016539
0x180016402  xorps   xmm0, xmm0
0x180016405  xor     eax, eax
0x180016407  movups  xmmword ptr [rbp+pvar], xmm0
0x18001640b  mov     [rbp+var_10], rax
0x18001640f  mov     rcx, [rbp+arg_8]
0x180016413  mov     rax, [rcx]
0x180016416  lea     r8, [rbp+pvar]
0x18001641a  lea     rdx, PKEY_Device_ContainerId
0x180016421  mov     rax, [rax+28h]
0x180016425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001642a  mov     ebx, eax
0x18001642c  test    eax, eax
0x18001642e  jns     short loc_18001644D
0x180016430  mov     r9d, eax; char *
0x180016433  mov     edx, 1589h; void *
0x180016438  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18001643f  mov     rcx, [rbp+18h]; this
0x180016443  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016448  jmp     loc_18001652E
0x18001644d  cmp     word ptr [rbp+pvar], 48h ; 'H'
0x180016452  jz      short loc_180016463
0x180016454  mov     ebx, 80070057h
0x180016459  mov     r9d, ebx
0x18001645c  mov     edx, 158Ah
0x180016461  jmp     short loc_180016438
0x180016463  mov     [rbp+arg_20], 0
0x18001646b  mov     dword ptr [rbp+arg_0], 0
0x180016472  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180016479  mov     rax, [rcx]
0x18001647c  mov     [rbp+arg_20], 0
0x180016484  lea     r9, [rbp+arg_20]
0x180016488  mov     r8d, 0Fh
0x18001648e  mov     edx, esi
0x180016490  mov     rax, [rax+18h]
0x180016494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016499  mov     ebx, eax
0x18001649b  test    eax, eax
0x18001649d  jns     short loc_1800164F1
0x18001649f  mov     rcx, [rbp+18h]; this
0x1800164a3  mov     r9d, eax; char *
0x1800164a6  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800164ad  mov     edx, 158Fh; void *
0x1800164b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800164b7  nop
0x1800164b8  mov     rcx, [rbp+arg_20]
0x1800164bc  test    rcx, rcx
0x1800164bf  jz      short loc_1800164CE
0x1800164c1  mov     rax, [rcx]
0x1800164c4  mov     rax, [rax+10h]
0x1800164c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164cd  nop
0x1800164ce  lea     rcx, [rbp+pvar]; pvar
0x1800164d2  call    cs:__imp_PropVariantClear
0x1800164d8  nop
0x1800164d9  mov     rcx, [rbp+arg_8]
0x1800164dd  test    rcx, rcx
0x1800164e0  jz      short loc_1800164EF
0x1800164e2  mov     rax, [rcx]
0x1800164e5  mov     rax, [rax+10h]
0x1800164e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164ee  nop
0x1800164ef  jmp     short loc_180016542
0x1800164f1  mov     rcx, [rbp+arg_20]
0x1800164f5  mov     rax, [rcx]
0x1800164f8  lea     rdx, [rbp+arg_0]
0x1800164fc  mov     rax, [rax+18h]
0x180016500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016505  mov     ebx, eax
0x180016507  test    eax, eax
0x180016509  jns     short loc_180016549
0x18001650b  mov     rcx, [rbp+18h]; this
0x18001650f  mov     r9d, eax; char *
0x180016512  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180016519  mov     edx, 1591h; void *
0x18001651e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016523  nop
0x180016524  lea     rcx, [rbp+arg_20]
0x180016528  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001652d  nop
0x18001652e  lea     rcx, [rbp+pvar]; pvar
0x180016532  call    cs:__imp_PropVariantClear
0x180016538  nop
0x180016539  lea     rcx, [rbp+arg_8]
0x18001653d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180016542  mov     eax, ebx
0x180016544  jmp     loc_1800165D0
0x180016549  xor     ebx, ebx
0x18001654b  cmp     dword ptr [rbp+arg_0], ebx
0x18001654e  jbe     short loc_180016597
0x180016550  cmp     qword ptr [rdi], 0
0x180016554  jnz     short loc_180016597
0x180016556  mov     [rsp+50h+var_28], rdi
0x18001655b  mov     rax, [rbp+arg_20]
0x18001655f  mov     qword ptr [rsp+50h+var_30], rax; int
0x180016564  lea     r9, [rbp+pvar]
0x180016568  mov     r8d, r14d
0x18001656b  mov     edx, esi
0x18001656d  mov     ecx, ebx
0x18001656f  call    ?CheckBluetoothEndpoint@@YAJHW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@HAEAV?$unique_struct@UtagPROPVARIANT@@P6AJPEAU1@@Z$1?PropVariantClear@@YAJ0@ZP6AX0@Z$1?PropVariantInit@@YAX0@Z@wil@@PEAUIMMDeviceCollection@@PEAPEAUIMMDevice@@@Z; CheckBluetoothEndpoint(int,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,int,wil::unique_struct<tagPROPVARIANT,long (*)(tagPROPVARIANT *),&PropVariantClear(tagPROPVARIANT *),void (*)(tagPROPVARIANT *),&PropVariantInit(tagPROPVARIANT *)> &,IMMDeviceCollection *,IMMDevice * *)
0x180016574  mov     rcx, [rbp+18h]; this
0x180016578  test    eax, eax
0x18001657a  jns     short loc_180016590
0x18001657c  mov     r9d, eax; char *
0x18001657f  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180016586  mov     edx, 1596h; void *
0x18001658b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016590  inc     ebx
0x180016592  cmp     ebx, dword ptr [rbp+arg_0]
0x180016595  jb      short loc_180016550
0x180016597  mov     rcx, [rbp+arg_20]
0x18001659b  test    rcx, rcx
0x18001659e  jz      short loc_1800165AD
0x1800165a0  mov     rax, [rcx]
0x1800165a3  mov     rax, [rax+10h]
0x1800165a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165ac  nop
0x1800165ad  lea     rcx, [rbp+pvar]; pvar
0x1800165b1  call    cs:__imp_PropVariantClear
0x1800165b7  nop
0x1800165b8  mov     rcx, [rbp+arg_8]
0x1800165bc  test    rcx, rcx
0x1800165bf  jz      short loc_1800165CE
0x1800165c1  mov     rax, [rcx]
0x1800165c4  mov     rax, [rax+10h]
0x1800165c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165cd  nop
0x1800165ce  xor     eax, eax
0x1800165d0  lea     r11, [rsp+50h+var_s0]
0x1800165d5  mov     rbx, [r11+30h]
0x1800165d9  mov     rsi, [r11+38h]
0x1800165dd  mov     rsp, r11
0x1800165e0  pop     r14
0x1800165e2  pop     rdi
0x1800165e3  pop     rbp
0x1800165e4  retn
```
