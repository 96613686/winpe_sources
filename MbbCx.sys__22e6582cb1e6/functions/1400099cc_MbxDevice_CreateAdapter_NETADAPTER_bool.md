# MbxDevice::CreateAdapter(NETADAPTER__ * *,bool)

- ea: `0x1400099cc`
- end: `0x140009e09`
- name: `?CreateAdapter@MbxDevice@@QEAAJPEAPEAUNETADAPTER__@@_N@Z`
- size: `1085`
- prototype: `__int64 __fastcall(MbxDevice *__hidden this, struct NETADAPTER__ **, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x14000bb48`
- `0x140020ed8`

## callees

- `0x140001b34`
- `0x140001cf8`
- `0x140009104`
- `0x1400099cc`
- `0x14000e2d8`
- `0x14000e560`
- `0x140047e50`
- `0x140047e90`

## string_xrefs

- `0x140009aac`: `adapterExtensionInit`

## pseudocode

```c
__int64 __fastcall MbxDevice::CreateAdapter(MbxDevice *this, struct NETADAPTER__ **a2, char a3)
{
  NETFUNC v3; // rax
  int v7; // edx
  __int64 v8; // rbx
  __int64 v10; // rax
  int v11; // edx
  __int64 v12; // rdi
  char v13; // dl
  int v14; // ecx
  bool v15; // cf
  char v16; // dl
  int v17; // eax
  int v18; // ecx
  int v19; // eax
  unsigned int v20; // r15d
  __int64 v21; // rax
  int v22; // edx
  int v23; // r8d
  int v24; // r9d
  struct NETADAPTER__ *v25; // rsi
  int v26; // eax
  int v27; // edx
  unsigned int v28; // r14d
  __int64 v29; // rax
  void (__fastcall *v30)(PNET_DRIVER_GLOBALS, __int64); // rax
  PNET_DRIVER_GLOBALS v31; // rcx
  int v32; // edx
  __int64 v33; // rax
  _QWORD v34[2]; // [rsp+40h] [rbp-30h] BYREF
  int v35; // [rsp+50h] [rbp-20h] BYREF
  __int64 v36; // [rsp+54h] [rbp-1Ch]

  v3 = NetFunctions[0];
  *a2 = 0;
  v8 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, _QWORD))v3)(NetDriverGlobals, *((_QWORD *)this + 1));
  if ( !v8 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_qs(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        11,
        56,
        (__int64)WPP_87eee639879b3392f87380bbab0baecf_Traceguids,
        *((_QWORD *)this + 1),
        (__int64)"adapterInit.get()");
    }
    return 3221225626LL;
  }
  v10 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, __int64))qword_14005F5F8)(NetDriverGlobals, v8);
  v12 = v10;
  if ( !v10 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_qs(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        11,
        57,
        (__int64)WPP_87eee639879b3392f87380bbab0baecf_Traceguids,
        *((_QWORD *)this + 1),
        (__int64)"adapterExtensionInit");
    }
    ((void (__fastcall *)(PNET_DRIVER_GLOBALS, __int64))qword_14005F528)(NetDriverGlobals, v8);
    return 3221225626LL;
  }
  ((void (__fastcall *)(PNET_DRIVER_GLOBALS, __int64, _QWORD))qword_14005F600)(
    NetDriverGlobals,
    v10,
    EvtAdapterPreProcessOidRequest);
  v34[1] = EvtAdapterUpdateNdisPmParameters;
  v34[0] = 16;
  ((void (__fastcall *)(PNET_DRIVER_GLOBALS, __int64, _QWORD *))qword_14005F8F0)(NetDriverGlobals, v12, v34);
  v13 = *((_BYTE *)this + 1651);
  v36 = 0;
  v14 = 0;
  v35 = 12;
  if ( v13 )
    v14 = 8;
  v15 = v13 != 0;
  v16 = *((_BYTE *)this + 1648);
  LODWORD(v36) = v14;
  v17 = (v15 ? 8 : 0) | 1;
  if ( v16 )
    LODWORD(v36) = (v15 ? 8 : 0) | 1;
  else
    v17 = v15 ? 8 : 0;
  v18 = v17 | 2;
  if ( *((_BYTE *)this + 1649) )
    LODWORD(v36) = v17 | 2;
  else
    v18 = v17;
  v19 = v18 | 0x10;
  if ( *((_BYTE *)this + 1652) )
    LODWORD(v36) = v18 | 0x10;
  else
    v19 = v18;
  if ( *((_BYTE *)this + 1650) )
    LODWORD(v36) = v19 | 4;
  ((void (__fastcall *)(PNET_DRIVER_GLOBALS, __int64, int *))qword_14005F620)(NetDriverGlobals, v12, &v35);
  v20 = (*((__int64 (__fastcall **)(_QWORD, __int64))this + 7))(*((_QWORD *)this + 1), v8);
  v21 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, __int64))qword_14005F5F0)(NetDriverGlobals, v8);
  v25 = (struct NETADAPTER__ *)v21;
  if ( v20 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dq(WPP_GLOBAL_Control->DeviceExtension, v22, v23, v24);
    if ( v25 && !a3 )
    {
      if ( (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct NETADAPTER__ *, __int64 *))(WdfFunctions_01031 + 1616))(
             WdfDriverGlobals,
             v25,
             off_14005DF38) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v32) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v32,
            11,
            59,
            (__int64)WPP_87eee639879b3392f87380bbab0baecf_Traceguids);
        }
        v33 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct NETADAPTER__ *, __int64 *))(WdfFunctions_01031
                                                                                               + 1616))(
                WdfDriverGlobals,
                v25,
                off_14005DF38);
        MbbWwanRemoveSessionFromAdapterList((PKSPIN_LOCK)this + 8, (struct _MINIPORT_INTERFACE_CONTEXT *)(v33 + 24));
      }
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct NETADAPTER__ *))(WdfFunctions_01031 + 1664))(
        WdfDriverGlobals,
        v25);
    }
    ((void (__fastcall *)(PNET_DRIVER_GLOBALS, __int64))qword_14005F528)(NetDriverGlobals, v8);
    return v20;
  }
  else
  {
    if ( !v21 )
      __int2c();
    if ( a3
      || (v26 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, __int64))qword_14005F540)(NetDriverGlobals, v21),
          v28 = v26,
          v26 >= 0) )
    {
      v29 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct NETADAPTER__ *, __int64 *))(WdfFunctions_01031 + 1616))(
              WdfDriverGlobals,
              v25,
              off_14005DF38);
      if ( !v29 )
        __int2c();
      if ( !*(_BYTE *)(v29 + 144) )
        __int2c();
      v30 = (void (__fastcall *)(PNET_DRIVER_GLOBALS, __int64))qword_14005F528;
      v31 = NetDriverGlobals;
      *a2 = v25;
      v30(v31, v8);
      return 0;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = 2;
        WPP_RECORDER_SF_qd(
          WPP_GLOBAL_Control->DeviceExtension,
          v27,
          11,
          60,
          (__int64)WPP_87eee639879b3392f87380bbab0baecf_Traceguids,
          (char)v25,
          v26);
      }
      ((void (__fastcall *)(PNET_DRIVER_GLOBALS, __int64))qword_14005F528)(NetDriverGlobals, v8);
      return v28;
    }
  }
}

```

## disassembly

```asm
0x1400099cc  mov     [rsp-38h+arg_10], rbx
0x1400099d1  push    rbp
0x1400099d2  push    rsi
0x1400099d3  push    rdi
0x1400099d4  push    r12
0x1400099d6  push    r13
0x1400099d8  push    r14
0x1400099da  push    r15
0x1400099dc  mov     rbp, rsp
0x1400099df  sub     rsp, 70h
0x1400099e3  mov     rax, cs:__security_cookie
0x1400099ea  xor     rax, rsp
0x1400099ed  mov     [rbp+var_10], rax
0x1400099f1  mov     rax, cs:NetFunctions
0x1400099f8  mov     r13, rdx
0x1400099fb  mov     r14, rcx
0x1400099fe  xor     esi, esi
0x140009a00  mov     [rdx], rsi
0x140009a03  mov     r12b, r8b
0x140009a06  mov     rdx, [rcx+8]
0x140009a0a  mov     rcx, cs:NetDriverGlobals
0x140009a11  call    _guard_dispatch_icall
0x140009a16  mov     rbx, rax
0x140009a19  test    rax, rax
0x140009a1c  jnz     short loc_140009A73
0x140009a1e  lea     rdi, WPP_RECORDER_INITIALIZED
0x140009a25  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140009a2c  jz      short loc_140009A69
0x140009a2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140009a35  lea     rax, aAdapterinitGet; "adapterInit.get()"
0x140009a3c  mov     [rsp+70h+var_40], rax
0x140009a41  lea     r9d, [rsi+38h]
0x140009a45  mov     rax, [r14+8]
0x140009a49  lea     r8d, [rsi+0Bh]
0x140009a4d  mov     [rsp+70h+var_48], rax
0x140009a52  mov     dl, 2
0x140009a54  mov     rcx, [rcx+40h]
0x140009a58  lea     rax, WPP_87eee639879b3392f87380bbab0baecf_Traceguids
0x140009a5f  mov     [rsp+70h+var_50], rax
0x140009a64  call    WPP_RECORDER_SF_qs
0x140009a69  mov     eax, 0C000009Ah
0x140009a6e  jmp     loc_140009DE4
0x140009a73  mov     rax, cs:qword_14005F5F8
0x140009a7a  mov     rdx, rbx
0x140009a7d  mov     rcx, cs:NetDriverGlobals
0x140009a84  call    _guard_dispatch_icall
0x140009a89  mov     rdi, rax
0x140009a8c  test    rax, rax
0x140009a8f  jnz     short loc_140009AF7
0x140009a91  lea     rdi, WPP_RECORDER_INITIALIZED
0x140009a98  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140009a9f  jz      short loc_140009ADC
0x140009aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140009aa8  lea     r9d, [rax+39h]
0x140009aac  lea     rax, aAdapterextensi; "adapterExtensionInit"
0x140009ab3  mov     dl, 2
0x140009ab5  mov     [rsp+70h+var_40], rax
0x140009aba  lea     r8d, [r9-2Eh]
0x140009abe  mov     rax, [r14+8]
0x140009ac2  mov     rcx, [rcx+40h]
0x140009ac6  mov     [rsp+70h+var_48], rax
0x140009acb  lea     rax, WPP_87eee639879b3392f87380bbab0baecf_Traceguids
0x140009ad2  mov     [rsp+70h+var_50], rax
0x140009ad7  call    WPP_RECORDER_SF_qs
0x140009adc  mov     rax, cs:qword_14005F528
0x140009ae3  mov     rdx, rbx
0x140009ae6  mov     rcx, cs:NetDriverGlobals
0x140009aed  call    _guard_dispatch_icall
0x140009af2  jmp     loc_140009A69
0x140009af7  mov     rax, cs:qword_14005F600
0x140009afe  lea     r8, EvtAdapterPreProcessOidRequest
0x140009b05  mov     rcx, cs:NetDriverGlobals
0x140009b0c  mov     rdx, rdi
0x140009b0f  call    _guard_dispatch_icall
0x140009b14  mov     rcx, cs:NetDriverGlobals
0x140009b1b  lea     rax, EvtAdapterUpdateNdisPmParameters
0x140009b22  mov     [rbp+var_28], rax
0x140009b26  lea     r8, [rbp+var_30]
0x140009b2a  mov     rax, cs:qword_14005F8F0
0x140009b31  mov     rdx, rdi
0x140009b34  mov     [rbp+var_30], 10h
0x140009b3c  call    _guard_dispatch_icall
0x140009b41  mov     dl, [r14+673h]
0x140009b48  mov     eax, 8
0x140009b4d  test    dl, dl
0x140009b4f  mov     [rbp+var_1C], rsi
0x140009b53  mov     ecx, esi
0x140009b55  mov     [rbp+var_20], 0Ch
0x140009b5c  cmovnz  ecx, eax
0x140009b5f  neg     dl
0x140009b61  mov     dl, [r14+670h]
0x140009b68  mov     dword ptr [rbp+var_1C], ecx
0x140009b6b  sbb     ecx, ecx
0x140009b6d  and     ecx, eax
0x140009b6f  mov     eax, ecx
0x140009b71  or      eax, 1
0x140009b74  test    dl, dl
0x140009b76  jz      short loc_140009B7B
0x140009b78  mov     dword ptr [rbp+var_1C], eax
0x140009b7b  mov     dl, [r14+671h]
0x140009b82  cmovz   eax, ecx
0x140009b85  mov     ecx, eax
0x140009b87  or      ecx, 2
0x140009b8a  test    dl, dl
0x140009b8c  jz      short loc_140009B91
0x140009b8e  mov     dword ptr [rbp+var_1C], ecx
0x140009b91  mov     dl, [r14+674h]
0x140009b98  cmovz   ecx, eax
0x140009b9b  mov     eax, ecx
0x140009b9d  or      eax, 10h
0x140009ba0  test    dl, dl
0x140009ba2  jz      short loc_140009BA7
0x140009ba4  mov     dword ptr [rbp+var_1C], eax
0x140009ba7  cmovz   eax, ecx
0x140009baa  cmp     [r14+672h], sil
0x140009bb1  jz      short loc_140009BB9
0x140009bb3  or      eax, 4
0x140009bb6  mov     dword ptr [rbp+var_1C], eax
0x140009bb9  mov     rax, cs:qword_14005F620
0x140009bc0  lea     r8, [rbp+var_20]
0x140009bc4  mov     rcx, cs:NetDriverGlobals
0x140009bcb  mov     rdx, rdi
0x140009bce  call    _guard_dispatch_icall
0x140009bd3  mov     rax, [r14+38h]
0x140009bd7  mov     rdx, rbx
0x140009bda  mov     rcx, [r14+8]
0x140009bde  call    _guard_dispatch_icall
0x140009be3  mov     rcx, cs:NetDriverGlobals
0x140009bea  mov     r15d, eax
0x140009bed  mov     rax, cs:qword_14005F5F0
0x140009bf4  mov     rdx, rbx
0x140009bf7  call    _guard_dispatch_icall
0x140009bfc  mov     rsi, rax
0x140009bff  test    r15d, r15d
0x140009c02  jnz     loc_140009CE7
0x140009c08  test    rax, rax
0x140009c0b  jnz     short loc_140009C0F
0x140009c0d  int     2Ch; Windows NT - assertion failure
0x140009c0f  test    r12b, r12b
0x140009c12  jnz     short loc_140009C90
0x140009c14  mov     rax, cs:qword_14005F540
0x140009c1b  mov     rdx, rsi
0x140009c1e  mov     rcx, cs:NetDriverGlobals
0x140009c25  call    _guard_dispatch_icall
0x140009c2a  mov     r14d, eax
0x140009c2d  test    eax, eax
0x140009c2f  jns     short loc_140009C90
0x140009c31  lea     rdi, WPP_RECORDER_INITIALIZED
0x140009c38  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140009c3f  jz      short loc_140009C72
0x140009c41  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c48  mov     r9d, 3Ch ; '<'
0x140009c4e  mov     dword ptr [rsp+70h+var_40], eax
0x140009c52  mov     dl, 2
0x140009c54  lea     rax, WPP_87eee639879b3392f87380bbab0baecf_Traceguids
0x140009c5b  mov     [rsp+70h+var_48], rsi
0x140009c60  mov     [rsp+70h+var_50], rax
0x140009c65  mov     rcx, [rcx+40h]
0x140009c69  lea     r8d, [r9-31h]
0x140009c6d  call    WPP_RECORDER_SF_qd
0x140009c72  mov     rax, cs:qword_14005F528
0x140009c79  mov     rdx, rbx
0x140009c7c  mov     rcx, cs:NetDriverGlobals
0x140009c83  call    _guard_dispatch_icall
0x140009c88  mov     eax, r14d
0x140009c8b  jmp     loc_140009DE4
0x140009c90  mov     rax, cs:WdfFunctions_01031
0x140009c97  mov     rdx, rsi
0x140009c9a  mov     r8, cs:off_14005DF38
0x140009ca1  mov     rcx, cs:WdfDriverGlobals
0x140009ca8  mov     rax, [rax+650h]
0x140009caf  call    _guard_dispatch_icall
0x140009cb4  test    rax, rax
0x140009cb7  jnz     short loc_140009CBB
0x140009cb9  int     2Ch; Windows NT - assertion failure
0x140009cbb  cmp     byte ptr [rax+90h], 0
0x140009cc2  jnz     short loc_140009CC6
0x140009cc4  int     2Ch; Windows NT - assertion failure
0x140009cc6  mov     rax, cs:qword_14005F528
0x140009ccd  mov     rdx, rbx
0x140009cd0  mov     rcx, cs:NetDriverGlobals
0x140009cd7  mov     [r13+0], rsi
0x140009cdb  call    _guard_dispatch_icall
0x140009ce0  xor     eax, eax
0x140009ce2  jmp     loc_140009DE4
0x140009ce7  lea     rdi, WPP_RECORDER_INITIALIZED
0x140009cee  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140009cf5  jz      short loc_140009D11
0x140009cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x140009cfe  mov     [rsp+70h+var_40], rsi
0x140009d03  mov     dword ptr [rsp+70h+var_48], r15d
0x140009d08  mov     rcx, [rcx+40h]
0x140009d0c  call    WPP_RECORDER_SF_dq
0x140009d11  test    rsi, rsi
0x140009d14  jz      loc_140009DCB
0x140009d1a  test    r12b, r12b
0x140009d1d  jnz     loc_140009DCB
0x140009d23  mov     rax, cs:WdfFunctions_01031
0x140009d2a  mov     rdx, rsi
0x140009d2d  mov     r8, cs:off_14005DF38
0x140009d34  mov     rcx, cs:WdfDriverGlobals
0x140009d3b  mov     rax, [rax+650h]
0x140009d42  call    _guard_dispatch_icall
0x140009d47  test    rax, rax
0x140009d4a  jz      short loc_140009DAE
0x140009d4c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140009d53  jz      short loc_140009D7D
0x140009d55  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d5c  lea     rax, WPP_87eee639879b3392f87380bbab0baecf_Traceguids
0x140009d63  mov     r9d, 3Bh ; ';'
0x140009d69  mov     [rsp+70h+var_50], rax
0x140009d6e  mov     dl, 2
0x140009d70  mov     rcx, [rcx+40h]
0x140009d74  lea     r8d, [r9-30h]
0x140009d78  call    WPP_RECORDER_SF_
0x140009d7d  mov     rax, cs:WdfFunctions_01031
0x140009d84  mov     rdx, rsi
0x140009d87  mov     r8, cs:off_14005DF38
0x140009d8e  mov     rcx, cs:WdfDriverGlobals
0x140009d95  mov     rax, [rax+650h]
0x140009d9c  call    _guard_dispatch_icall
0x140009da1  lea     rcx, [r14+40h]; SpinLock
0x140009da5  lea     rdx, [rax+18h]; struct _MINIPORT_INTERFACE_CONTEXT *
0x140009da9  call    ?MbbWwanRemoveSessionFromAdapterList@@YA_NPEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_MINIPORT_INTERFACE_CONTEXT@@@Z; MbbWwanRemoveSessionFromAdapterList(_MINIPORT_ADAPTER_CONTEXT *,_MINIPORT_INTERFACE_CONTEXT *)
0x140009dae  mov     rax, cs:WdfFunctions_01031
0x140009db5  mov     rdx, rsi
0x140009db8  mov     rcx, cs:WdfDriverGlobals
0x140009dbf  mov     rax, [rax+680h]
0x140009dc6  call    _guard_dispatch_icall
0x140009dcb  mov     rax, cs:qword_14005F528
0x140009dd2  mov     rdx, rbx
0x140009dd5  mov     rcx, cs:NetDriverGlobals
0x140009ddc  call    _guard_dispatch_icall
0x140009de1  mov     eax, r15d
0x140009de4  mov     rcx, [rbp+var_10]
0x140009de8  xor     rcx, rsp; StackCookie
0x140009deb  call    __security_check_cookie
0x140009df0  mov     rbx, [rsp+70h+arg_10]
0x140009df8  add     rsp, 70h
0x140009dfc  pop     r15
0x140009dfe  pop     r14
0x140009e00  pop     r13
0x140009e02  pop     r12
0x140009e04  pop     rdi
0x140009e05  pop     rsi
0x140009e06  pop     rbp
0x140009e07  retn
```
