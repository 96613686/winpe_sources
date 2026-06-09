# GetMicArrayGeometryProperty(IMMDevice *,IConnector *,tagPROPVARIANT *)

- ea: `0x180013e14`
- end: `0x1800141de`
- name: `?GetMicArrayGeometryProperty@@YAJPEAUIMMDevice@@PEAUIConnector@@PEAUtagPROPVARIANT@@@Z`
- size: `970`
- prototype: `__int64 __fastcall(struct IMMDevice *, struct IConnector *, PROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a344`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x180013e14`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014123`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013ecb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013fb7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013ecb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013fb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013edb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013fcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800141a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013edb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013fcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800141a1`

## string_xrefs

- `0x180013eb5`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180013fa2`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall GetMicArrayGeometryProperty(struct IMMDevice *a1, struct IConnector *a2, PROPVARIANT *a3)
{
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, _QWORD *); // rdi
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, LPVOID *); // rbx
  struct IUnknown *v15; // r9
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, GUID *, __int64); // rdi
  __int64 v20; // rcx
  void *v21; // rax
  __int64 *v23; // [rsp+20h] [rbp-49h]
  LPVOID pv; // [rsp+40h] [rbp-29h] BYREF
  __int64 v25; // [rsp+48h] [rbp-21h] BYREF
  __int64 v26; // [rsp+50h] [rbp-19h] BYREF
  __int64 v27; // [rsp+58h] [rbp-11h] BYREF
  _QWORD v28[2]; // [rsp+60h] [rbp-9h] BYREF
  char v29; // [rsp+70h] [rbp+7h]
  _DWORD v30[18]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int v32; // [rsp+D8h] [rbp+6Fh] BYREF
  PROPVARIANT *pvar; // [rsp+E0h] [rbp+77h] BYREF
  int v34; // [rsp+E8h] [rbp+7Fh]

  pvar = a3;
  memset(v30, 0, 32);
  v32 = 0;
  v26 = 0;
  v25 = 0;
  v28[0] = 0;
  v27 = 0;
  pv = 0;
  *(_OWORD *)a3 = 0;
  a3[2] = 0;
  v28[1] = &pvar;
  v29 = 1;
  v4 = v26;
  v26 = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = ((__int64 (__fastcall *)(struct IConnector *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9,
         &v26);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 32LL))(v26, &v32);
    v6 = v7;
    if ( v7 >= 0 )
    {
      v9 = v26;
      v10 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v26 + 96LL);
      v11 = v28[0];
      v28[0] = 0;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      v7 = v10(v9, v28);
      v6 = v7;
      if ( v7 >= 0 )
      {
        v13 = v28[0];
        v14 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v28[0] + 64LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pv,
          0);
        v7 = v14(v13, &pv);
        v6 = v7;
        if ( v7 >= 0 )
        {
          v15 = g_DeviceEnumerator;
          Release = g_DeviceEnumerator->lpVtbl[1].Release;
          v17 = v27;
          v27 = 0;
          if ( v17 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            v15 = g_DeviceEnumerator;
          }
          v7 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, __int64 *))Release)(v15, pv, &v27);
          v6 = v7;
          if ( v7 >= 0 )
          {
            v18 = v27;
            v19 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v27 + 24LL);
            v20 = v25;
            v25 = 0;
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            v23 = &v25;
            v7 = v19(v18, &GUID_28f54685_06fd_11d2_b27a_00a0c9223196, 1);
            v6 = v7;
            if ( v7 >= 0 )
            {
              v30[7] = 0;
              v30[0] = 1174383264;
              *(_QWORD *)&v30[1] = *(_QWORD *)&GUID_45ffaaa0_6e1b_11d0_bcf2_444553540000.Data2;
              v30[3] = *(_DWORD *)&GUID_45ffaaa0_6e1b_11d0_bcf2_444553540000.Data4[4];
              v30[4] = 51;
              v30[5] = 1;
              v30[6] = (unsigned __int16)v32;
              LODWORD(v23) = 0;
              v7 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v25 + 24LL))(v25, v30, 32);
              v6 = v7;
              if ( v7 >= 0 )
              {
                v21 = CoTaskMemAlloc(0);
                if ( !v21 )
                {
                  v6 = -2147024882;
                  v12 = 2147942414LL;
                  v8 = 3615;
LABEL_22:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v8,
                    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                    (const char *)v12,
                    (int)v23);
                  PropVariantClear(pvar);
                  if ( pv )
                    CoTaskMemFree(pv);
LABEL_43:
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v28);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
                  return v6;
                }
                *(_WORD *)pvar = 4113;
                *((_DWORD *)pvar + 2) = 0;
                pvar[2] = v21;
                v34 = 0;
                LODWORD(v23) = 0;
                v7 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v25 + 24LL))(v25, v30, 32);
                v6 = v7;
                if ( v7 >= 0 )
                {
                  if ( pv )
                    CoTaskMemFree(pv);
                  v6 = 0;
                  goto LABEL_43;
                }
                v8 = 3625;
              }
              else
              {
                v8 = 3611;
              }
            }
            else
            {
              v8 = 3599;
            }
          }
          else
          {
            v8 = 3597;
          }
        }
        else
        {
          v8 = 3594;
        }
      }
      else
      {
        v8 = 3591;
      }
    }
    else
    {
      v8 = 3588;
    }
    v12 = (unsigned int)v7;
    goto LABEL_22;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE02,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v5,
    (int)v23);
  PropVariantClear(pvar);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v28[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v28[0] + 16LL))(v28[0]);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return v6;
}

```

## disassembly

```asm
0x180013e14  mov     [rsp-8+pvar], r8
0x180013e19  mov     [rsp-8+cb], rcx
0x180013e1e  push    rbp
0x180013e1f  push    rbx
0x180013e20  push    rsi
0x180013e21  push    rdi
0x180013e22  lea     rbp, [rsp-3Fh]
0x180013e27  sub     rsp, 0A8h
0x180013e2e  mov     rbx, rdx
0x180013e31  xor     esi, esi
0x180013e33  mov     [rbp+57h+var_48], esi
0x180013e36  xorps   xmm0, xmm0
0x180013e39  movups  [rbp+57h+var_44], xmm0
0x180013e3d  movups  [rbp+57h+var_44+0Ch], xmm0
0x180013e41  mov     dword ptr [rbp+57h+cb], esi
0x180013e44  mov     [rbp+57h+arg_8], esi
0x180013e47  mov     [rbp+57h+var_70], rsi
0x180013e4b  mov     [rbp+57h+var_78], rsi
0x180013e4f  mov     [rbp+57h+var_60], rsi
0x180013e53  mov     [rbp+57h+var_68], rsi
0x180013e57  mov     [rbp+57h+pv], rsi
0x180013e5b  xor     eax, eax
0x180013e5d  movups  xmmword ptr [r8], xmm0
0x180013e61  mov     [r8+10h], rax
0x180013e65  lea     rax, [rbp+57h+pvar]
0x180013e69  mov     [rbp+57h+var_58], rax
0x180013e6d  mov     [rbp+57h+var_50], 1
0x180013e71  mov     rcx, [rbp+57h+var_70]
0x180013e75  mov     [rbp+57h+var_70], rsi
0x180013e79  test    rcx, rcx
0x180013e7c  jz      short loc_180013E8B
0x180013e7e  mov     rax, [rcx]
0x180013e81  mov     rax, [rax+10h]
0x180013e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e8a  nop
0x180013e8b  mov     rax, [rbx]
0x180013e8e  lea     r8, [rbp+57h+var_70]
0x180013e92  lea     rdx, _GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9
0x180013e99  mov     rcx, rbx
0x180013e9c  mov     rax, [rax]
0x180013e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ea4  mov     ebx, eax
0x180013ea6  test    eax, eax
0x180013ea8  jns     loc_180013F3F
0x180013eae  mov     rcx, [rbp+5Fh]; this
0x180013eb2  mov     r9d, eax; char *
0x180013eb5  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180013ebc  mov     edx, 0E02h; void *
0x180013ec1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ec6  nop
0x180013ec7  mov     rcx, [rbp+57h+pvar]; pvar
0x180013ecb  call    cs:__imp_PropVariantClear
0x180013ed1  nop
0x180013ed2  mov     rcx, [rbp+57h+pv]; pv
0x180013ed6  test    rcx, rcx
0x180013ed9  jz      short loc_180013EE2
0x180013edb  call    cs:__imp_CoTaskMemFree
0x180013ee1  nop
0x180013ee2  mov     rcx, [rbp+57h+var_68]
0x180013ee6  test    rcx, rcx
0x180013ee9  jz      short loc_180013EF8
0x180013eeb  mov     rax, [rcx]
0x180013eee  mov     rax, [rax+10h]
0x180013ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ef7  nop
0x180013ef8  mov     rcx, [rbp+57h+var_60]
0x180013efc  test    rcx, rcx
0x180013eff  jz      short loc_180013F0E
0x180013f01  mov     rax, [rcx]
0x180013f04  mov     rax, [rax+10h]
0x180013f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f0d  nop
0x180013f0e  mov     rcx, [rbp+57h+var_78]
0x180013f12  test    rcx, rcx
0x180013f15  jz      short loc_180013F24
0x180013f17  mov     rax, [rcx]
0x180013f1a  mov     rax, [rax+10h]
0x180013f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f23  nop
0x180013f24  mov     rcx, [rbp+57h+var_70]
0x180013f28  test    rcx, rcx
0x180013f2b  jz      short loc_180013F3A
0x180013f2d  mov     rax, [rcx]
0x180013f30  mov     rax, [rax+10h]
0x180013f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f39  nop
0x180013f3a  jmp     loc_1800141D0
0x180013f3f  mov     rcx, [rbp+57h+var_70]
0x180013f43  mov     rax, [rcx]
0x180013f46  lea     rdx, [rbp+57h+arg_8]
0x180013f4a  mov     rax, [rax+20h]
0x180013f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f53  mov     ebx, eax
0x180013f55  test    eax, eax
0x180013f57  jns     short loc_180013F60
0x180013f59  mov     edx, 0E04h
0x180013f5e  jmp     short loc_180013F9F
0x180013f60  mov     rbx, [rbp+57h+var_70]
0x180013f64  mov     rax, [rbx]
0x180013f67  mov     rdi, [rax+60h]
0x180013f6b  mov     rcx, [rbp+57h+var_60]
0x180013f6f  mov     [rbp+57h+var_60], rsi
0x180013f73  test    rcx, rcx
0x180013f76  jz      short loc_180013F85
0x180013f78  mov     rdx, [rcx]
0x180013f7b  mov     rax, [rdx+10h]
0x180013f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f84  nop
0x180013f85  lea     rdx, [rbp+57h+var_60]
0x180013f89  mov     rcx, rbx
0x180013f8c  mov     rax, rdi
0x180013f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f94  mov     ebx, eax
0x180013f96  test    eax, eax
0x180013f98  jns     short loc_180013FD6
0x180013f9a  mov     edx, 0E07h; void *
0x180013f9f  mov     r9d, eax; char *
0x180013fa2  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180013fa9  mov     rcx, [rbp+5Fh]; this
0x180013fad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013fb2  nop
0x180013fb3  mov     rcx, [rbp+57h+pvar]; pvar
0x180013fb7  call    cs:__imp_PropVariantClear
0x180013fbd  nop
0x180013fbe  mov     rcx, [rbp+57h+pv]; pv
0x180013fc2  test    rcx, rcx
0x180013fc5  jz      loc_1800141A9
0x180013fcb  call    cs:__imp_CoTaskMemFree
0x180013fd1  jmp     loc_1800141A9
0x180013fd6  mov     rdi, [rbp+57h+var_60]
0x180013fda  mov     rax, [rdi]
0x180013fdd  mov     rbx, [rax+40h]
0x180013fe1  xor     edx, edx
0x180013fe3  lea     rcx, [rbp+57h+pv]
0x180013fe7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180013fec  lea     rdx, [rbp+57h+pv]
0x180013ff0  mov     rcx, rdi
0x180013ff3  mov     rax, rbx
0x180013ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ffb  mov     ebx, eax
0x180013ffd  test    eax, eax
0x180013fff  jns     short loc_180014008
0x180014001  mov     edx, 0E0Ah
0x180014006  jmp     short loc_180013F9F
0x180014008  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18001400f  mov     rax, [r9]
0x180014012  mov     rbx, [rax+28h]
0x180014016  mov     rcx, [rbp+57h+var_68]
0x18001401a  mov     [rbp+57h+var_68], rsi
0x18001401e  test    rcx, rcx
0x180014021  jz      short loc_180014036
0x180014023  mov     rax, [rcx]
0x180014026  mov     rax, [rax+10h]
0x18001402a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001402f  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180014036  lea     r8, [rbp+57h+var_68]
0x18001403a  mov     rdx, [rbp+57h+pv]
0x18001403e  mov     rcx, r9
0x180014041  mov     rax, rbx
0x180014044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014049  mov     ebx, eax
0x18001404b  test    eax, eax
0x18001404d  jns     short loc_180014059
0x18001404f  mov     edx, 0E0Dh
0x180014054  jmp     loc_180013F9F
0x180014059  mov     rbx, [rbp+57h+var_68]
0x18001405d  mov     rax, [rbx]
0x180014060  mov     rdi, [rax+18h]
0x180014064  mov     rcx, [rbp+57h+var_78]
0x180014068  mov     [rbp+57h+var_78], rsi
0x18001406c  test    rcx, rcx
0x18001406f  jz      short loc_18001407E
0x180014071  mov     rax, [rcx]
0x180014074  mov     rax, [rax+10h]
0x180014078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001407d  nop
0x18001407e  lea     rax, [rbp+57h+var_78]
0x180014082  mov     [rsp+0C0h+var_A0], rax
0x180014087  xor     r9d, r9d
0x18001408a  lea     r8d, [r9+1]
0x18001408e  lea     rdx, _GUID_28f54685_06fd_11d2_b27a_00a0c9223196
0x180014095  mov     rcx, rbx
0x180014098  mov     rax, rdi
0x18001409b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140a0  mov     ebx, eax
0x1800140a2  test    eax, eax
0x1800140a4  jns     short loc_1800140B0
0x1800140a6  mov     edx, 0E0Fh
0x1800140ab  jmp     loc_180013F9F
0x1800140b0  mov     [rbp+57h+var_2C], esi
0x1800140b3  mov     [rbp+57h+var_48], 45FFAAA0h
0x1800140ba  movsd   xmm0, qword ptr cs:_GUID_45ffaaa0_6e1b_11d0_bcf2_444553540000.Data2
0x1800140c2  movsd   qword ptr [rbp+57h+var_44], xmm0
0x1800140c7  mov     eax, dword ptr cs:_GUID_45ffaaa0_6e1b_11d0_bcf2_444553540000.Data4+4
0x1800140cd  mov     dword ptr [rbp+57h+var_44+8], eax
0x1800140d0  mov     dword ptr [rbp+57h+var_44+0Ch], 33h ; '3'
0x1800140d7  mov     [rbp+57h+var_34], 1
0x1800140de  movzx   eax, word ptr [rbp+57h+arg_8]
0x1800140e2  mov     [rbp+57h+var_30], eax
0x1800140e5  mov     rcx, [rbp+57h+var_78]
0x1800140e9  mov     rax, [rcx]
0x1800140ec  lea     rdx, [rbp+57h+cb]
0x1800140f0  mov     [rsp+0C0h+var_98], rdx
0x1800140f5  mov     dword ptr [rsp+0C0h+var_A0], esi
0x1800140f9  xor     r9d, r9d
0x1800140fc  lea     edi, [r9+20h]
0x180014100  mov     r8d, edi
0x180014103  lea     rdx, [rbp+57h+var_48]
0x180014107  mov     rax, [rax+18h]
0x18001410b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014110  mov     ebx, eax
0x180014112  test    eax, eax
0x180014114  jns     short loc_180014120
0x180014116  mov     edx, 0E1Bh
0x18001411b  jmp     loc_180013F9F
0x180014120  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180014123  call    cs:__imp_CoTaskMemAlloc
0x180014129  mov     r9, rax
0x18001412c  test    rax, rax
0x18001412f  jnz     short loc_180014143
0x180014131  mov     ebx, 8007000Eh
0x180014136  mov     r9d, ebx
0x180014139  mov     edx, 0E1Fh
0x18001413e  jmp     loc_180013FA2
0x180014143  mov     rax, [rbp+57h+pvar]
0x180014147  mov     word ptr [rax], 1011h
0x18001414c  mov     rcx, [rbp+57h+pvar]
0x180014150  mov     eax, dword ptr [rbp+57h+cb]
0x180014153  mov     [rcx+8], eax
0x180014156  mov     rax, [rbp+57h+pvar]
0x18001415a  mov     [rax+10h], r9
0x18001415e  mov     [rbp+57h+arg_18], esi
0x180014161  mov     rcx, [rbp+57h+var_78]
0x180014165  mov     edx, dword ptr [rbp+57h+cb]
0x180014168  mov     rax, [rcx]
0x18001416b  lea     r10, [rbp+57h+arg_18]
0x18001416f  mov     [rsp+0C0h+var_98], r10
0x180014174  mov     dword ptr [rsp+0C0h+var_A0], edx
0x180014178  mov     r8d, edi
0x18001417b  lea     rdx, [rbp+57h+var_48]
0x18001417f  mov     rax, [rax+18h]
0x180014183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014188  mov     ebx, eax
0x18001418a  test    eax, eax
0x18001418c  jns     short loc_180014198
0x18001418e  mov     edx, 0E29h
0x180014193  jmp     loc_180013F9F
0x180014198  mov     rcx, [rbp+57h+pv]; pv
0x18001419c  test    rcx, rcx
0x18001419f  jz      short loc_1800141A7
0x1800141a1  call    cs:__imp_CoTaskMemFree
0x1800141a7  mov     ebx, esi
0x1800141a9  lea     rcx, [rbp+57h+var_68]
0x1800141ad  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800141b2  nop
0x1800141b3  lea     rcx, [rbp+57h+var_60]
0x1800141b7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800141bc  nop
0x1800141bd  lea     rcx, [rbp+57h+var_78]
0x1800141c1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800141c6  nop
0x1800141c7  lea     rcx, [rbp+57h+var_70]
0x1800141cb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800141d0  mov     eax, ebx
0x1800141d2  add     rsp, 0A8h
0x1800141d9  pop     rdi
0x1800141da  pop     rsi
0x1800141db  pop     rbx
0x1800141dc  pop     rbp
0x1800141dd  retn
```
