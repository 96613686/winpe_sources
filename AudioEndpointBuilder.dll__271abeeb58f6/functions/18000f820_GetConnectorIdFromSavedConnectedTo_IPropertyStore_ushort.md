# GetConnectorIdFromSavedConnectedTo(IPropertyStore *,ushort * *)

- ea: `0x18000f820`
- end: `0x18000fa79`
- name: `?GetConnectorIdFromSavedConnectedTo@@YAJPEAUIPropertyStore@@PEAPEAG@Z`
- size: `601`
- prototype: `__int64 __fastcall(struct IPropertyStore *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004f474`

## callees

- `0x18000f820`
- `0x18000fa80`
- `0x18000fb60`
- `0x180010da8`
- `0x18003f81c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f938`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f943`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f990`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f99b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f9c2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f9cd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f9f7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fa02`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fa5e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fa69`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f938`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f943`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f990`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f99b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f9c2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f9cd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f9f7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fa02`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fa5e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fa69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f90d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fa53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f90d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fa53`

## string_xrefs

- `0x18000f922`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18000f9ac`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18000f9e1`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18000fa1b`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18000fa3e`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetConnectorIdFromSavedConnectedTo(struct IPropertyStore *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rbx
  int v5; // eax
  unsigned int v6; // esi
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rax
  size_t v10; // rsi
  unsigned __int16 **cotaskmem_string_nothrow; // rdi
  __int64 v13; // rdx
  int v14; // [rsp+20h] [rbp-50h]
  int v15; // [rsp+20h] [rbp-50h]
  unsigned __int16 *v16; // [rsp+30h] [rbp-40h] BYREF
  PROPVARIANT v17[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+48h] [rbp-28h]
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  LPVOID pv; // [rsp+90h] [rbp+20h] BYREF

  *(_OWORD *)v17 = 0;
  v18 = 0;
  *(_OWORD *)pvar = 0;
  v20 = 0;
  v4 = 0;
  v16 = 0;
  v5 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a1->lpVtbl->GetValue)(
         a1,
         PKEY_Endpoint_DeviceIdSaveConnectedTo,
         v17);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23B2,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v5,
      v14);
    PropVariantClear(pvar);
    PropVariantClear(v17);
    return v6;
  }
  if ( LOWORD(v17[0]) == 31 )
  {
    v7 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a1->lpVtbl->GetValue)(
           a1,
           PKEY_Endpoint_LocalIdSaveConnectedTo,
           pvar);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23B5,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v7,
        v14);
      PropVariantClear(pvar);
      PropVariantClear(v17);
      return v8;
    }
    if ( LOWORD(pvar[0]) == 19 )
    {
      v9 = -1;
      do
        ++v9;
      while ( *((_WORD *)v17[1] + v9) );
      v10 = v9 + 10;
      cotaskmem_string_nothrow = (unsigned __int16 **)wil::make_cotaskmem_string_nothrow((wil *)&pv, 0, v9 + 10);
      if ( &v16 != cotaskmem_string_nothrow )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v16,
          *cotaskmem_string_nothrow);
        *cotaskmem_string_nothrow = 0;
        v4 = v16;
      }
      if ( pv )
        CoTaskMemFree(pv);
      if ( !v4 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x23BE,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)0x8007000ELL,
          v14);
        PropVariantClear(pvar);
        PropVariantClear(v17);
        return 2147942414LL;
      }
      v15 = (int)pvar[1];
      if ( swprintf_s(v4, v10, L"%s/%08x", v17[1]) != -1 )
      {
        *a2 = v4;
        PropVariantClear(pvar);
        PropVariantClear(v17);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23C1,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)0x80004005LL,
        v15);
      CoTaskMemFree(v4);
      goto LABEL_21;
    }
    v13 = 9142;
  }
  else
  {
    v13 = 9139;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)0x80004005LL,
    v14);
LABEL_21:
  PropVariantClear(pvar);
  PropVariantClear(v17);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000f820  mov     [rsp-18h+arg_8], rbx
0x18000f825  mov     [rsp-18h+arg_10], rsi
0x18000f82a  push    rbp
0x18000f82b  push    rdi
0x18000f82c  push    r14
0x18000f82e  mov     rbp, rsp
0x18000f831  sub     rsp, 70h
0x18000f835  mov     r14, rdx
0x18000f838  mov     rdi, rcx
0x18000f83b  xorps   xmm0, xmm0
0x18000f83e  xor     eax, eax
0x18000f840  movups  xmmword ptr [rbp+var_38], xmm0
0x18000f844  mov     [rbp+var_28], rax
0x18000f848  movups  xmmword ptr [rbp+pvar], xmm0
0x18000f84c  mov     [rbp+var_10], rax
0x18000f850  xor     ebx, ebx
0x18000f852  mov     [rbp+var_40], rbx
0x18000f856  mov     rax, [rcx]
0x18000f859  lea     r8, [rbp+var_38]
0x18000f85d  lea     rdx, PKEY_Endpoint_DeviceIdSaveConnectedTo
0x18000f864  mov     rax, [rax+28h]
0x18000f868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f86d  mov     esi, eax
0x18000f86f  test    eax, eax
0x18000f871  js      loc_18000F9A5
0x18000f877  mov     eax, 1Fh
0x18000f87c  cmp     ax, word ptr [rbp+var_38]
0x18000f880  jnz     loc_18000FA0F
0x18000f886  mov     rax, [rdi]
0x18000f889  lea     r8, [rbp+pvar]
0x18000f88d  lea     rdx, PKEY_Endpoint_LocalIdSaveConnectedTo
0x18000f894  mov     rcx, rdi
0x18000f897  mov     rax, [rax+28h]
0x18000f89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8a0  mov     edi, eax
0x18000f8a2  test    eax, eax
0x18000f8a4  js      loc_18000F9DA
0x18000f8aa  mov     eax, 13h
0x18000f8af  cmp     ax, word ptr [rbp+pvar]
0x18000f8b3  jnz     loc_18000FA16
0x18000f8b9  mov     rcx, [rbp+var_38+8]
0x18000f8bd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000f8c4  lea     rax, [rax+1]
0x18000f8c8  cmp     word ptr [rcx+rax*2], 0
0x18000f8cd  jnz     short loc_18000F8C4
0x18000f8cf  lea     rsi, [rax+0Ah]
0x18000f8d3  mov     r8, rsi; unsigned __int64
0x18000f8d6  xor     edx, edx; unsigned __int16 *
0x18000f8d8  lea     rcx, [rbp+pv]; this
0x18000f8dc  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18000f8e1  mov     rdi, rax
0x18000f8e4  lea     rax, [rbp+var_40]
0x18000f8e8  cmp     rax, rdi
0x18000f8eb  jz      short loc_18000F904
0x18000f8ed  mov     rdx, [rdi]
0x18000f8f0  lea     rcx, [rbp+var_40]
0x18000f8f4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000f8f9  mov     qword ptr [rdi], 0
0x18000f900  mov     rbx, [rbp+var_40]
0x18000f904  mov     rcx, [rbp+pv]; pv
0x18000f908  test    rcx, rcx
0x18000f90b  jz      short loc_18000F913
0x18000f90d  call    cs:__imp_CoTaskMemFree
0x18000f913  test    rbx, rbx
0x18000f916  jnz     short loc_18000F963
0x18000f918  mov     rcx, [rbp+18h]; this
0x18000f91c  mov     r9d, 8007000Eh; char *
0x18000f922  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18000f929  mov     edx, 23BEh; void *
0x18000f92e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f933  nop
0x18000f934  lea     rcx, [rbp+pvar]; pvar
0x18000f938  call    cs:__imp_PropVariantClear
0x18000f93e  nop
0x18000f93f  lea     rcx, [rbp+var_38]; pvar
0x18000f943  call    cs:__imp_PropVariantClear
0x18000f949  mov     eax, 8007000Eh
0x18000f94e  lea     r11, [rsp+70h+var_s0]
0x18000f953  mov     rbx, [r11+28h]
0x18000f957  mov     rsi, [r11+30h]
0x18000f95b  mov     rsp, r11
0x18000f95e  pop     r14
0x18000f960  pop     rdi
0x18000f961  pop     rbp
0x18000f962  retn
0x18000f963  mov     eax, dword ptr [rbp+pvar+8]
0x18000f966  mov     [rsp+70h+var_50], eax; int
0x18000f96a  mov     r9, [rbp+var_38+8]
0x18000f96e  lea     r8, aS08x; "%s/%08x"
0x18000f975  mov     rdx, rsi; BufferCount
0x18000f978  mov     rcx, rbx; Buffer
0x18000f97b  call    swprintf_s
0x18000f980  cmp     eax, 0FFFFFFFFh
0x18000f983  jz      loc_18000FA34
0x18000f989  mov     [r14], rbx
0x18000f98c  lea     rcx, [rbp+pvar]; pvar
0x18000f990  call    cs:__imp_PropVariantClear
0x18000f996  nop
0x18000f997  lea     rcx, [rbp+var_38]; pvar
0x18000f99b  call    cs:__imp_PropVariantClear
0x18000f9a1  xor     eax, eax
0x18000f9a3  jmp     short loc_18000F94E
0x18000f9a5  mov     rcx, [rbp+18h]; this
0x18000f9a9  mov     r9d, esi; char *
0x18000f9ac  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18000f9b3  mov     edx, 23B2h; void *
0x18000f9b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f9bd  nop
0x18000f9be  lea     rcx, [rbp+pvar]; pvar
0x18000f9c2  call    cs:__imp_PropVariantClear
0x18000f9c8  nop
0x18000f9c9  lea     rcx, [rbp+var_38]; pvar
0x18000f9cd  call    cs:__imp_PropVariantClear
0x18000f9d3  mov     eax, esi
0x18000f9d5  jmp     loc_18000F94E
0x18000f9da  mov     rcx, [rbp+18h]; this
0x18000f9de  mov     r9d, edi; char *
0x18000f9e1  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18000f9e8  mov     edx, 23B5h; void *
0x18000f9ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f9f2  nop
0x18000f9f3  lea     rcx, [rbp+pvar]; pvar
0x18000f9f7  call    cs:__imp_PropVariantClear
0x18000f9fd  nop
0x18000f9fe  lea     rcx, [rbp+var_38]; pvar
0x18000fa02  call    cs:__imp_PropVariantClear
0x18000fa08  mov     eax, edi
0x18000fa0a  jmp     loc_18000F94E
0x18000fa0f  mov     edx, 23B3h
0x18000fa14  jmp     short loc_18000FA1B
0x18000fa16  mov     edx, 23B6h; void *
0x18000fa1b  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18000fa22  mov     r9d, 80004005h; char *
0x18000fa28  mov     rcx, [rbp+18h]; this
0x18000fa2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fa31  nop
0x18000fa32  jmp     short loc_18000FA5A
0x18000fa34  mov     rcx, [rbp+18h]; this
0x18000fa38  mov     r9d, 80004005h; char *
0x18000fa3e  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18000fa45  mov     edx, 23C1h; void *
0x18000fa4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fa4f  nop
0x18000fa50  mov     rcx, rbx; pv
0x18000fa53  call    cs:__imp_CoTaskMemFree
0x18000fa59  nop
0x18000fa5a  lea     rcx, [rbp+pvar]; pvar
0x18000fa5e  call    cs:__imp_PropVariantClear
0x18000fa64  nop
0x18000fa65  lea     rcx, [rbp+var_38]; pvar
0x18000fa69  call    cs:__imp_PropVariantClear
0x18000fa6f  mov     eax, 80004005h
0x18000fa74  jmp     loc_18000F94E
```
