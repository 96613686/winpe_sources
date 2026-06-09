# DetectLoopbackTappointProperty(IPropertyStore *)

- ea: `0x18002ae14`
- end: `0x18002b2a1`
- name: `?DetectLoopbackTappointProperty@@YAJPEAUIPropertyStore@@@Z`
- size: `1165`
- prototype: `__int64 __fastcall(struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004a344`

## callees

- `0x18000128c`
- `0x180006b0c`
- `0x180010da8`
- `0x18001f374`
- `0x18002ae14`
- `0x18003e920`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b254`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b275`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b280`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b254`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b275`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b280`

## string_xrefs

- `0x18002aea1`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002af54`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002b00c`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002b09d`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002b179`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002b1c1`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
__int64 __fastcall DetectLoopbackTappointProperty(struct IPropertyStore *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  struct IPropertyStoreVtbl *lpVtbl; // rax
  int v4; // eax
  struct IUnknown *v5; // r9
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, GUID *, __int64); // rdi
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  const struct _tlgProvider_t *v14; // rax
  int v15; // r8d
  int v16; // r9d
  int v18; // [rsp+20h] [rbp-E0h]
  struct IPropertyStore *v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+48h] [rbp-B8h] BYREF
  int v21; // [rsp+4Ch] [rbp-B4h]
  int v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+70h] [rbp-90h]
  int v26; // [rsp+78h] [rbp-88h] BYREF
  PROPVARIANT v27[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h]
  PROPVARIANT v29[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v30; // [rsp+A8h] [rbp-58h]
  GUID v31; // [rsp+B0h] [rbp-50h] BYREF
  int v32; // [rsp+C0h] [rbp-40h]
  int v33; // [rsp+C4h] [rbp-3Ch]
  int v34; // [rsp+C8h] [rbp-38h]
  int v35; // [rsp+CCh] [rbp-34h]
  struct IPropertyStore **v36; // [rsp+D0h] [rbp-30h]
  PROPVARIANT *v37; // [rsp+D8h] [rbp-28h]
  char v38; // [rsp+E0h] [rbp-20h]
  _DWORD v39[6]; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v19 = a1;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  v23 = 0;
  *(_QWORD *)v22 = 0;
  *(_OWORD *)pvar = 0;
  v25 = 0;
  LOWORD(pvar[0]) = 0;
  v36 = &v19;
  v37 = pvar;
  v38 = 1;
  v1 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int128 *, PROPVARIANT *))a1->lpVtbl->GetValue)(
         a1,
         &PKEY_Endpoint_HWAudioEngine_Loopback_ConnectorId,
         v27);
  v2 = v1;
  if ( v1 >= 0 )
  {
    if ( LOWORD(v27[0]) != 19 )
      goto LABEL_4;
    lpVtbl = v19->lpVtbl;
    v39[0] = 590439624;
    v39[1] = 1283267372;
    v39[2] = 1907779772;
    v39[3] = 1730509416;
    v39[4] = 1;
    v4 = ((__int64 (__fastcall *)(struct IPropertyStore *, _DWORD *, PROPVARIANT *))lpVtbl->GetValue)(v19, v39, v29);
    v2 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFCD,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v4,
        v18);
      ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v19->lpVtbl->SetValue)(
        v19,
        PKEY_Endpoint_Loopback_Tappoint_Capability,
        pvar);
      goto LABEL_25;
    }
    if ( LOWORD(v29[0]) == 31 )
    {
      v5 = g_DeviceEnumerator;
      Release = g_DeviceEnumerator->lpVtbl[1].Release;
      v7 = v23;
      v23 = 0;
      if ( v7 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        v5 = g_DeviceEnumerator;
      }
      v8 = ((__int64 (__fastcall *)(struct IUnknown *, PROPVARIANT, __int64 *))Release)(v5, v29[1], &v23);
      v2 = v8;
      if ( v8 >= 0 )
      {
        v9 = v23;
        v10 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v23 + 24LL);
        v11 = *(_QWORD *)v22;
        *(_QWORD *)v22 = 0;
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        v12 = v10(v9, &GUID_28f54685_06fd_11d2_b27a_00a0c9223196, 1);
        v2 = v12;
        if ( v12 >= 0 )
        {
          v35 = 0;
          v31 = GUID_b3648bc8_5b91_468a_b94d_f4641250917c;
          v32 = 0;
          v33 = 1;
          v34 = LOWORD(v27[1]);
          v20 = 0;
          v21 = 0;
          v13 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64, int *))(**(_QWORD **)v22 + 24LL))(
                  *(_QWORD *)v22,
                  &v31,
                  32,
                  &v20);
          v2 = v13;
          if ( v13 >= 0 )
          {
            if ( v21 == 4 )
            {
              LOWORD(pvar[0]) = 19;
              LODWORD(pvar[1]) = v20;
              v14 = AudioEndpointBuilderTelemetryProvider::Provider();
              if ( *(_DWORD *)v14 > 4u )
              {
                v26 = v20;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (_DWORD)v14,
                  (unsigned int)&unk_1800764E8,
                  v15,
                  v16,
                  (__int64)&v26);
              }
              ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v19->lpVtbl->SetValue)(
                v19,
                PKEY_Endpoint_Loopback_Tappoint_Capability,
                pvar);
              v2 = 0;
            }
            else
            {
              v2 = -2147467259;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xFDE,
                (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                (const char *)0x80004005LL,
                4);
              ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v19->lpVtbl->SetValue)(
                v19,
                PKEY_Endpoint_Loopback_Tappoint_Capability,
                pvar);
            }
          }
          else if ( v13 == -2147023726 )
          {
            ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v19->lpVtbl->SetValue)(
              v19,
              PKEY_Endpoint_Loopback_Tappoint_Capability,
              pvar);
            v2 = -2147023726;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xFDC,
              (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
              (const char *)(unsigned int)v13,
              4);
            ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v19->lpVtbl->SetValue)(
              v19,
              PKEY_Endpoint_Loopback_Tappoint_Capability,
              pvar);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFD1,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)(unsigned int)v12,
            (int)v22);
          ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v19->lpVtbl->SetValue)(
            v19,
            PKEY_Endpoint_Loopback_Tappoint_Capability,
            pvar);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFD0,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)(unsigned int)v8,
          v18);
        ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v19->lpVtbl->SetValue)(
          v19,
          PKEY_Endpoint_Loopback_Tappoint_Capability,
          pvar);
      }
    }
    else
    {
LABEL_4:
      ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v19->lpVtbl->SetValue)(
        v19,
        PKEY_Endpoint_Loopback_Tappoint_Capability,
        pvar);
      v2 = -2147023728;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFCA,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v1,
      v18);
    ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v19->lpVtbl->SetValue)(
      v19,
      PKEY_Endpoint_Loopback_Tappoint_Capability,
      pvar);
  }
LABEL_25:
  PropVariantClear(pvar);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v22);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  PropVariantClear(v27);
  PropVariantClear(v29);
  return v2;
}

```

## disassembly

```asm
0x18002ae14  push    rbp
0x18002ae16  push    rbx
0x18002ae17  push    rdi
0x18002ae18  push    r14
0x18002ae1a  lea     rbp, [rsp-18h]
0x18002ae1f  sub     rsp, 118h
0x18002ae26  mov     rax, cs:__security_cookie
0x18002ae2d  xor     rax, rsp
0x18002ae30  mov     [rbp+30h+var_30], rax
0x18002ae34  mov     [rsp+130h+var_F0], rcx
0x18002ae39  xorps   xmm0, xmm0
0x18002ae3c  xor     eax, eax
0x18002ae3e  movups  xmmword ptr [rbp+30h+var_98], xmm0
0x18002ae42  mov     [rbp+30h+var_88], rax
0x18002ae46  movups  xmmword ptr [rbp+30h+var_B0], xmm0
0x18002ae4a  mov     [rbp+30h+var_A0], rax
0x18002ae4e  mov     [rsp+130h+var_D8], rax
0x18002ae53  mov     qword ptr [rsp+130h+var_E0], rax
0x18002ae58  movups  xmmword ptr [rsp+130h+pvar], xmm0
0x18002ae5d  mov     [rsp+130h+var_C0], rax
0x18002ae62  mov     word ptr [rsp+130h+pvar], ax
0x18002ae67  lea     rax, [rsp+130h+var_F0]
0x18002ae6c  mov     [rbp+30h+var_60], rax
0x18002ae70  lea     rax, [rsp+130h+pvar]
0x18002ae75  mov     [rbp+30h+var_58], rax
0x18002ae79  mov     [rbp+30h+var_50], 1
0x18002ae7d  mov     rax, [rcx]
0x18002ae80  lea     r8, [rbp+30h+var_B0]
0x18002ae84  lea     rdx, PKEY_Endpoint_HWAudioEngine_Loopback_ConnectorId
0x18002ae8b  mov     rax, [rax+28h]
0x18002ae8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae94  mov     ebx, eax
0x18002ae96  test    eax, eax
0x18002ae98  jns     short loc_18002AED6
0x18002ae9a  mov     rcx, [rbp+38h]; this
0x18002ae9e  mov     r9d, eax; char *
0x18002aea1  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002aea8  mov     edx, 0FCAh; void *
0x18002aead  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aeb2  nop
0x18002aeb3  mov     rcx, [rsp+130h+var_F0]
0x18002aeb8  mov     rdx, [rcx]
0x18002aebb  mov     rax, [rdx+30h]
0x18002aebf  lea     r8, [rsp+130h+pvar]
0x18002aec4  lea     rdx, PKEY_Endpoint_Loopback_Tappoint_Capability
0x18002aecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aed0  nop
0x18002aed1  jmp     loc_18002B24F
0x18002aed6  mov     r14d, 13h
0x18002aedc  cmp     r14w, word ptr [rbp+30h+var_B0]
0x18002aee1  jz      short loc_18002AF0B
0x18002aee3  mov     rcx, [rsp+130h+var_F0]
0x18002aee8  mov     rax, [rcx]
0x18002aeeb  lea     r8, [rsp+130h+pvar]
0x18002aef0  lea     rdx, PKEY_Endpoint_Loopback_Tappoint_Capability
0x18002aef7  mov     rax, [rax+30h]
0x18002aefb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af00  nop
0x18002af01  mov     ebx, 80070490h
0x18002af06  jmp     loc_18002B24F
0x18002af0b  mov     rcx, [rsp+130h+var_F0]
0x18002af10  mov     rax, [rcx]
0x18002af13  mov     [rbp+30h+var_48], 233164C8h
0x18002af1a  mov     [rbp+30h+var_44], 4C7D1B2Ch
0x18002af21  mov     [rbp+30h+var_40], 71B668BCh
0x18002af28  mov     [rbp+30h+var_3C], 67257A68h
0x18002af2f  mov     [rbp+30h+var_38], 1
0x18002af36  lea     r8, [rbp+30h+var_98]
0x18002af3a  lea     rdx, [rbp+30h+var_48]
0x18002af3e  mov     rax, [rax+28h]
0x18002af42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af47  mov     ebx, eax
0x18002af49  test    eax, eax
0x18002af4b  jns     short loc_18002AF89
0x18002af4d  mov     rcx, [rbp+38h]; this
0x18002af51  mov     r9d, eax; char *
0x18002af54  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002af5b  mov     edx, 0FCDh; void *
0x18002af60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002af65  nop
0x18002af66  mov     rcx, [rsp+130h+var_F0]
0x18002af6b  mov     rdx, [rcx]
0x18002af6e  mov     rax, [rdx+30h]
0x18002af72  lea     r8, [rsp+130h+pvar]
0x18002af77  lea     rdx, PKEY_Endpoint_Loopback_Tappoint_Capability
0x18002af7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af83  nop
0x18002af84  jmp     loc_18002B24F
0x18002af89  mov     eax, 1Fh
0x18002af8e  cmp     ax, word ptr [rbp+30h+var_98]
0x18002af92  jz      short loc_18002AFB7
0x18002af94  mov     rcx, [rsp+130h+var_F0]
0x18002af99  mov     rax, [rcx]
0x18002af9c  lea     r8, [rsp+130h+pvar]
0x18002afa1  lea     rdx, PKEY_Endpoint_Loopback_Tappoint_Capability
0x18002afa8  mov     rax, [rax+30h]
0x18002afac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afb1  nop
0x18002afb2  jmp     loc_18002AF01
0x18002afb7  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18002afbe  mov     rax, [r9]
0x18002afc1  mov     rbx, [rax+28h]
0x18002afc5  mov     rcx, [rsp+130h+var_D8]
0x18002afca  mov     [rsp+130h+var_D8], 0
0x18002afd3  test    rcx, rcx
0x18002afd6  jz      short loc_18002AFEB
0x18002afd8  mov     rdx, [rcx]
0x18002afdb  mov     rax, [rdx+10h]
0x18002afdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afe4  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18002afeb  lea     r8, [rsp+130h+var_D8]
0x18002aff0  mov     rdx, [rbp+30h+var_98+8]
0x18002aff4  mov     rcx, r9
0x18002aff7  mov     rax, rbx
0x18002affa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afff  mov     ebx, eax
0x18002b001  test    eax, eax
0x18002b003  jns     short loc_18002B041
0x18002b005  mov     rcx, [rbp+38h]; this
0x18002b009  mov     r9d, eax; char *
0x18002b00c  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002b013  mov     edx, 0FD0h; void *
0x18002b018  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b01d  nop
0x18002b01e  mov     rcx, [rsp+130h+var_F0]
0x18002b023  mov     rdx, [rcx]
0x18002b026  mov     rax, [rdx+30h]
0x18002b02a  lea     r8, [rsp+130h+pvar]
0x18002b02f  lea     rdx, PKEY_Endpoint_Loopback_Tappoint_Capability
0x18002b036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b03b  nop
0x18002b03c  jmp     loc_18002B24F
0x18002b041  mov     rbx, [rsp+130h+var_D8]
0x18002b046  mov     rax, [rbx]
0x18002b049  mov     rdi, [rax+18h]
0x18002b04d  mov     rcx, qword ptr [rsp+130h+var_E0]
0x18002b052  mov     qword ptr [rsp+130h+var_E0], 0
0x18002b05b  test    rcx, rcx
0x18002b05e  jz      short loc_18002B06D
0x18002b060  mov     rax, [rcx]
0x18002b063  mov     rax, [rax+10h]
0x18002b067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b06c  nop
0x18002b06d  lea     rax, [rsp+130h+var_E0]
0x18002b072  mov     qword ptr [rsp+130h+var_110], rax; int
0x18002b077  xor     r9d, r9d
0x18002b07a  lea     r8d, [r9+1]
0x18002b07e  lea     rdx, _GUID_28f54685_06fd_11d2_b27a_00a0c9223196
0x18002b085  mov     rcx, rbx
0x18002b088  mov     rax, rdi
0x18002b08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b090  mov     ebx, eax
0x18002b092  test    eax, eax
0x18002b094  jns     short loc_18002B0D2
0x18002b096  mov     rcx, [rbp+38h]; this
0x18002b09a  mov     r9d, eax; char *
0x18002b09d  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002b0a4  mov     edx, 0FD1h; void *
0x18002b0a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b0ae  nop
0x18002b0af  mov     rcx, [rsp+130h+var_F0]
0x18002b0b4  mov     rdx, [rcx]
0x18002b0b7  mov     rax, [rdx+30h]
0x18002b0bb  lea     r8, [rsp+130h+pvar]
0x18002b0c0  lea     rdx, PKEY_Endpoint_Loopback_Tappoint_Capability
0x18002b0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0cc  nop
0x18002b0cd  jmp     loc_18002B24F
0x18002b0d2  xorps   xmm0, xmm0
0x18002b0d5  xor     eax, eax
0x18002b0d7  movups  [rbp+30h+var_7C], xmm0
0x18002b0db  movups  [rbp+30h+var_7C+0Ch], xmm0
0x18002b0df  movups  xmm0, xmmword ptr cs:_GUID_b3648bc8_5b91_468a_b94d_f4641250917c.Data1
0x18002b0e6  movdqu  xmmword ptr [rbp-50h], xmm0
0x18002b0eb  mov     dword ptr [rbp+30h+var_7C+0Ch], eax
0x18002b0ee  mov     [rbp+30h+var_6C], 1
0x18002b0f5  movzx   eax, word ptr [rbp+30h+var_B0+8]
0x18002b0f9  mov     [rbp+30h+var_68], eax
0x18002b0fc  mov     [rsp+130h+var_E8], 0
0x18002b104  mov     [rsp+130h+var_E4], 0
0x18002b10c  mov     rcx, qword ptr [rsp+130h+var_E0]
0x18002b111  mov     rax, [rcx]
0x18002b114  lea     rdx, [rsp+130h+var_E4]
0x18002b119  mov     [rsp+130h+var_108], rdx
0x18002b11e  mov     [rsp+130h+var_110], 4; int
0x18002b126  lea     r9, [rsp+130h+var_E8]
0x18002b12b  mov     r8d, 20h ; ' '
0x18002b131  lea     rdx, [rbp+30h+var_80]
0x18002b135  mov     rax, [rax+18h]
0x18002b139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b13e  mov     ebx, eax
0x18002b140  test    eax, eax
0x18002b142  jns     short loc_18002B1AE
0x18002b144  mov     edi, 80070492h
0x18002b149  cmp     eax, edi
0x18002b14b  jnz     short loc_18002B172
0x18002b14d  mov     rcx, [rsp+130h+var_F0]
0x18002b152  mov     rax, [rcx]
0x18002b155  lea     r8, [rsp+130h+pvar]
0x18002b15a  lea     rdx, PKEY_Endpoint_Loopback_Tappoint_Capability
0x18002b161  mov     rax, [rax+30h]
0x18002b165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b16a  nop
0x18002b16b  mov     ebx, edi
0x18002b16d  jmp     loc_18002B24F
0x18002b172  mov     rcx, [rbp+38h]; this
0x18002b176  mov     r9d, eax; char *
0x18002b179  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002b180  mov     edx, 0FDCh; void *
0x18002b185  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b18a  nop
0x18002b18b  mov     rcx, [rsp+130h+var_F0]
0x18002b190  mov     rax, [rcx]
0x18002b193  lea     r8, [rsp+130h+pvar]
0x18002b198  lea     rdx, PKEY_Endpoint_Loopback_Tappoint_Capability
0x18002b19f  mov     rax, [rax+30h]
0x18002b1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1a8  nop
0x18002b1a9  jmp     loc_18002B24F
0x18002b1ae  cmp     [rsp+130h+var_E4], 4
0x18002b1b3  jz      short loc_18002B1F3
0x18002b1b5  mov     rcx, [rbp+38h]; this
0x18002b1b9  mov     ebx, 80004005h
0x18002b1be  mov     r9d, ebx; char *
0x18002b1c1  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002b1c8  mov     edx, 0FDEh; void *
0x18002b1cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b1d2  nop
0x18002b1d3  mov     rcx, [rsp+130h+var_F0]
0x18002b1d8  mov     rax, [rcx]
0x18002b1db  lea     r8, [rsp+130h+pvar]
0x18002b1e0  lea     rdx, PKEY_Endpoint_Loopback_Tappoint_Capability
0x18002b1e7  mov     rax, [rax+30h]
0x18002b1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1f0  nop
0x18002b1f1  jmp     short loc_18002B24F
0x18002b1f3  mov     word ptr [rsp+130h+pvar], r14w
0x18002b1f9  mov     eax, [rsp+130h+var_E8]
0x18002b1fd  mov     dword ptr [rsp+130h+pvar+8], eax
0x18002b201  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002b206  mov     ecx, [rax]
0x18002b208  cmp     ecx, 4
0x18002b20b  jbe     short loc_18002B22F
0x18002b20d  mov     ecx, [rsp+130h+var_E8]
0x18002b211  mov     [rsp+130h+var_B8], ecx
0x18002b215  lea     rcx, [rsp+130h+var_B8]
0x18002b21a  mov     qword ptr [rsp+130h+var_110], rcx
0x18002b21f  lea     rdx, unk_1800764E8
0x18002b226  mov     rcx, rax
0x18002b229  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002b22e  nop
0x18002b22f  mov     rcx, [rsp+130h+var_F0]
0x18002b234  mov     rax, [rcx]
0x18002b237  lea     r8, [rsp+130h+pvar]
0x18002b23c  lea     rdx, PKEY_Endpoint_Loopback_Tappoint_Capability
0x18002b243  mov     rax, [rax+30h]
0x18002b247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b24c  nop
0x18002b24d  xor     ebx, ebx
0x18002b24f  lea     rcx, [rsp+130h+pvar]; pvar
0x18002b254  call    cs:__imp_PropVariantClear
0x18002b25a  nop
0x18002b25b  lea     rcx, [rsp+130h+var_E0]
0x18002b260  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002b265  nop
0x18002b266  lea     rcx, [rsp+130h+var_D8]
0x18002b26b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002b270  nop
0x18002b271  lea     rcx, [rbp+30h+var_B0]; pvar
0x18002b275  call    cs:__imp_PropVariantClear
0x18002b27b  nop
0x18002b27c  lea     rcx, [rbp+30h+var_98]; pvar
0x18002b280  call    cs:__imp_PropVariantClear
0x18002b286  mov     eax, ebx
0x18002b288  mov     rcx, [rbp+30h+var_30]
0x18002b28c  xor     rcx, rsp; StackCookie
0x18002b28f  call    __security_check_cookie
0x18002b294  add     rsp, 118h
0x18002b29b  pop     r14
0x18002b29d  pop     rdi
0x18002b29e  pop     rbx
0x18002b29f  pop     rbp
0x18002b2a0  retn
```
