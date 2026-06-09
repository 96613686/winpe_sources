# CRemoteTextConnection::RuntimeClassInitialize(_GUID,Windows::System::RemoteDesktop::Input::IRemoteTextConnectionDataHandler *,Windows::System::RemoteDesktop::Input::RemoteTextConnectionOptions)

- ea: `0x180036a80`
- end: `0x180036e5c`
- name: `?RuntimeClassInitialize@CRemoteTextConnection@@QEAAJU_GUID@@PEAUIRemoteTextConnectionDataHandler@Input@RemoteDesktop@System@Windows@@W4RemoteTextConnectionOptions@4567@@Z`
- size: `988`
- prototype: `int __high(struct _GUID, struct Windows::System::RemoteDesktop::Input::IRemoteTextConnectionDataHandler *, enum Windows::System::RemoteDesktop::Input::RemoteTextConnectionOptions)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180035f00`
- `0x180036050`

## callees

- `0x180002240`
- `0x180002270`
- `0x18000275c`
- `0x180002db8`
- `0x180012030`
- `0x180012074`
- `0x180017a2c`
- `0x1800183d0`
- `0x18002879c`
- `0x180036a80`
- `0x180045f84`
- `0x18004f32c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180036c1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180036c1e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180036c3d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180036c3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CRemoteTextConnection::RuntimeClassInitialize(
        __int64 a1,
        _OWORD *a2,
        struct Windows::System::RemoteDesktop::Input::IRemoteTextConnectionDataHandler *a3,
        unsigned int a4)
{
  _DWORD *v8; // rax
  volatile signed __int32 *v9; // rbx
  _DWORD *v10; // rax
  volatile signed __int32 *v11; // rbx
  _QWORD *v12; // rbx
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v17; // rcx
  __int64 v18; // r14
  void (__fastcall *v19)(__int64, HSTRING_HEADER *, _QWORD *); // r15
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  volatile signed __int32 *v23; // rcx
  unsigned int v24; // r8d
  __int64 v25; // rcx
  MessageProxyReconnectAdapter *v26; // rax
  int v27; // esi
  MessageProxyReconnectAdapter *v28; // rbx
  int v30[4]; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v33[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v8 = operator new(0x128u);
  *(_QWORD *)v30 = v8;
  *(_OWORD *)v8 = 0;
  v8[2] = 1;
  v8[3] = 1;
  *(_QWORD *)v8 = &std::_Ref_count_obj2<RemoteTextAppIntegration_ToPdu>::`vftable';
  v8[66] = 0;
  *((_QWORD *)v8 + 34) = 0;
  *((_QWORD *)v8 + 35) = 0;
  *((_QWORD *)v8 + 36) = 0;
  *(_QWORD *)(a1 + 72) = v8 + 4;
  v9 = *(volatile signed __int32 **)(a1 + 80);
  *(_QWORD *)(a1 + 80) = v8;
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *a2;
  RemoteTextAppIntegration_ToPdu::Initialize(
    *(RemoteTextAppIntegration_ToPdu **)(a1 + 72),
    a3,
    (struct _GUID *)&hstringHeader);
  v10 = operator new(0x38u);
  *(_QWORD *)v30 = v10;
  *(_OWORD *)v10 = 0;
  v10[2] = 1;
  v10[3] = 1;
  *(_QWORD *)v10 = &std::_Ref_count_obj2<PduRecv_ToRemoteTextAppIntegration>::`vftable';
  *((_QWORD *)v10 + 2) = &PduRecv_ToRemoteTextAppIntegration::`vftable';
  *((_QWORD *)v10 + 3) = 0;
  *((_QWORD *)v10 + 4) = 0;
  *((_QWORD *)v10 + 5) = 0;
  *((_QWORD *)v10 + 6) = 0;
  *(_QWORD *)(a1 + 88) = v10 + 4;
  v11 = *(volatile signed __int32 **)(a1 + 96);
  *(_QWORD *)(a1 + 96) = v10;
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  v12 = *(_QWORD **)(a1 + 88);
  *(_QWORD *)v30 = 0;
  string = 0;
  v13 = WindowsCreateStringReference(
          L"Windows.UI.Internal.Text.Remote.RemoteTextAppIntegration",
          0x38u,
          &hstringHeader,
          &string);
  if ( v13 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
LABEL_35:
    wil::details::in1diag3::_Throw_Hr(
      v17,
      (void *)0x27,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\pdurecv_toremotetextappintegration.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v30[0]);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_e43158d1_8fc2_4ddc_9b23_7dcd37aeec1f, v30);
  v17 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_35;
  v18 = *(_QWORD *)v30;
  v19 = *(void (__fastcall **)(__int64, HSTRING_HEADER *, _QWORD *))(**(_QWORD **)v30 + 48LL);
  v20 = v12[1];
  v12[1] = 0;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *a2;
  v19(v18, &hstringHeader, v12 + 1);
  v21 = *(_QWORD *)(a1 + 80);
  if ( v21 )
  {
    v22 = *(_QWORD *)(a1 + 72);
    _InterlockedIncrement((volatile signed __int32 *)(v21 + 12));
  }
  else
  {
    v22 = 0;
    v21 = 0;
  }
  v12[2] = v22;
  v23 = (volatile signed __int32 *)v12[3];
  v12[3] = v21;
  if ( v23 && _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
  if ( *(_QWORD *)v30 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v30 + 16LL))(*(_QWORD *)v30);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 88) + 8LL) + 584LL))(
    *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8LL),
    a4);
  *(_OWORD *)(a1 + 376) = *a2;
  memset_0(v33, 0, 0x208u);
  GetDesktopUniqueName(L"System\\RemoteTextInputProcessor", v33, v24);
  v25 = *(_QWORD *)(a1 + 104);
  *(_QWORD *)(a1 + 104) = 0;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  *(_QWORD *)(a1 + 104) = 0;
  v26 = (MessageProxyReconnectAdapter *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)v30 = v26;
  if ( !v26 )
  {
    v27 = -2147024882;
    goto LABEL_33;
  }
  v28 = MessageProxyReconnectAdapter::MessageProxyReconnectAdapter(v26);
  hstringHeader.Reserved.Reserved1 = v28;
  *(_QWORD *)v30 = 0;
  v27 = MessageProxyReconnectAdapter::RuntimeClassInitialize(
          v28,
          &GUID_b30e303e_7340_4446_bd7b_c37fdee42abc,
          v33,
          (struct IMessageProxyReconnectAdapterOwner *)(a1 + 24));
  if ( v27 < 0 )
  {
    if ( v28 )
      (*(void (__fastcall **)(MessageProxyReconnectAdapter *))(*(_QWORD *)v28 + 16LL))(v28);
LABEL_33:
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextconnection\\remotetextconnection.cpp",
      (const char *)(unsigned int)v27,
      v30[0]);
  }
  if ( v28 )
    (*(void (__fastcall **)(MessageProxyReconnectAdapter *))(*(_QWORD *)v28 + 8LL))(v28);
  *(_QWORD *)(a1 + 104) = v28;
  if ( v28 )
    (*(void (__fastcall **)(MessageProxyReconnectAdapter *))(*(_QWORD *)v28 + 16LL))(v28);
  return 0;
}

```

## disassembly

```asm
0x180036a80  push    rbp
0x180036a82  push    rbx
0x180036a83  push    rsi
0x180036a84  push    rdi
0x180036a85  push    r12
0x180036a87  push    r13
0x180036a89  push    r14
0x180036a8b  push    r15
0x180036a8d  lea     rbp, [rsp-178h]
0x180036a95  sub     rsp, 278h
0x180036a9c  mov     rax, cs:__security_cookie
0x180036aa3  xor     rax, rsp
0x180036aa6  mov     [rbp+1B0h+var_50], rax
0x180036aad  mov     r13d, r9d
0x180036ab0  mov     rsi, r8
0x180036ab3  mov     r12, rdx
0x180036ab6  mov     rdi, rcx
0x180036ab9  xor     r14d, r14d
0x180036abc  mov     ecx, 128h; Size
0x180036ac1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036ac6  mov     qword ptr [rsp+2B0h+var_290], rax
0x180036acb  xorps   xmm0, xmm0
0x180036ace  movups  xmmword ptr [rax], xmm0
0x180036ad1  lea     ecx, [r14+1]
0x180036ad5  mov     [rax+8], ecx
0x180036ad8  mov     [rax+0Ch], ecx
0x180036adb  lea     rcx, ??_7?$_Ref_count_obj2@VRemoteTextAppIntegration_ToPdu@@@std@@6B@; const std::_Ref_count_obj2<RemoteTextAppIntegration_ToPdu>::`vftable'
0x180036ae2  mov     [rax], rcx
0x180036ae5  lea     rcx, [rax+10h]
0x180036ae9  mov     [rcx+0F8h], r14d
0x180036af0  mov     [rcx+100h], r14
0x180036af7  mov     [rcx+108h], r14
0x180036afe  mov     [rcx+110h], r14
0x180036b05  mov     [rdi+48h], rcx
0x180036b09  mov     rbx, [rdi+50h]
0x180036b0d  mov     [rdi+50h], rax
0x180036b11  or      r15d, 0FFFFFFFFh
0x180036b15  test    rbx, rbx
0x180036b18  jz      short loc_180036B51
0x180036b1a  mov     eax, r15d
0x180036b1d  lock xadd [rbx+8], eax
0x180036b22  add     eax, r15d
0x180036b25  jnz     short loc_180036B51
0x180036b27  mov     rax, [rbx]
0x180036b2a  mov     rcx, rbx
0x180036b2d  mov     rax, [rax]
0x180036b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b35  mov     eax, r15d
0x180036b38  lock xadd [rbx+0Ch], eax
0x180036b3d  add     eax, r15d
0x180036b40  jnz     short loc_180036B51
0x180036b42  mov     rax, [rbx]
0x180036b45  mov     rcx, rbx
0x180036b48  mov     rax, [rax+8]
0x180036b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b51  movaps  xmm0, xmmword ptr [r12]
0x180036b56  movdqa  xmmword ptr [rsp+2B0h+hstringHeader.Reserved], xmm0
0x180036b5c  lea     r8, [rsp+2B0h+hstringHeader]; struct _GUID
0x180036b61  mov     rdx, rsi; struct Windows::System::RemoteDesktop::Input::IRemoteTextConnectionDataHandler *
0x180036b64  mov     rcx, [rdi+48h]; this
0x180036b68  call    ?Initialize@RemoteTextAppIntegration_ToPdu@@QEAAXPEAUIRemoteTextConnectionDataHandler@Input@RemoteDesktop@System@Windows@@U_GUID@@@Z; RemoteTextAppIntegration_ToPdu::Initialize(Windows::System::RemoteDesktop::Input::IRemoteTextConnectionDataHandler *,_GUID)
0x180036b6d  mov     esi, 38h ; '8'
0x180036b72  mov     ecx, esi; Size
0x180036b74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036b79  mov     qword ptr [rsp+2B0h+var_290], rax
0x180036b7e  xorps   xmm0, xmm0
0x180036b81  movups  xmmword ptr [rax], xmm0
0x180036b84  lea     ecx, [rsi-37h]
0x180036b87  mov     [rax+8], ecx
0x180036b8a  mov     [rax+0Ch], ecx
0x180036b8d  lea     rcx, ??_7?$_Ref_count_obj2@VPduRecv_ToRemoteTextAppIntegration@@@std@@6B@; const std::_Ref_count_obj2<PduRecv_ToRemoteTextAppIntegration>::`vftable'
0x180036b94  mov     [rax], rcx
0x180036b97  lea     rcx, [rax+10h]
0x180036b9b  lea     rdx, ??_7PduRecv_ToRemoteTextAppIntegration@@6B@; const PduRecv_ToRemoteTextAppIntegration::`vftable'
0x180036ba2  mov     [rcx], rdx
0x180036ba5  mov     [rcx+8], r14
0x180036ba9  mov     [rcx+10h], r14
0x180036bad  mov     [rcx+18h], r14
0x180036bb1  mov     [rcx+20h], r14
0x180036bb5  mov     [rdi+58h], rcx
0x180036bb9  mov     rbx, [rdi+60h]
0x180036bbd  mov     [rdi+60h], rax
0x180036bc1  test    rbx, rbx
0x180036bc4  jz      short loc_180036BFD
0x180036bc6  mov     eax, r15d
0x180036bc9  lock xadd [rbx+8], eax
0x180036bce  add     eax, r15d
0x180036bd1  jnz     short loc_180036BFD
0x180036bd3  mov     rax, [rbx]
0x180036bd6  mov     rcx, rbx
0x180036bd9  mov     rax, [rax]
0x180036bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036be1  mov     eax, r15d
0x180036be4  lock xadd [rbx+0Ch], eax
0x180036be9  add     eax, r15d
0x180036bec  jnz     short loc_180036BFD
0x180036bee  mov     rax, [rbx]
0x180036bf1  mov     rcx, rbx
0x180036bf4  mov     rax, [rax+8]
0x180036bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036bfd  mov     rbx, [rdi+58h]
0x180036c01  mov     qword ptr [rsp+2B0h+var_290], r14; int
0x180036c06  mov     [rsp+2B0h+string], r14
0x180036c0b  lea     r9, [rsp+2B0h+string]; string
0x180036c10  lea     r8, [rsp+2B0h+hstringHeader]; hstringHeader
0x180036c15  mov     edx, esi; length
0x180036c17  lea     rcx, ?RuntimeClass_Windows_UI_Internal_Text_Remote_RemoteTextAppIntegration@@3QBGB; "Windows.UI.Internal.Text.Remote.RemoteT"...
0x180036c1e  call    cs:__imp_WindowsCreateStringReference
0x180036c24  test    eax, eax
0x180036c26  js      loc_180036E3F
0x180036c2c  lea     r8, [rsp+2B0h+var_290]
0x180036c31  lea     rdx, _GUID_e43158d1_8fc2_4ddc_9b23_7dcd37aeec1f
0x180036c38  mov     rcx, [rsp+2B0h+string]
0x180036c3d  call    cs:__imp_RoGetActivationFactory
0x180036c43  mov     rcx, [rbp+1B8h]
0x180036c4a  test    eax, eax
0x180036c4c  js      loc_180036E47
0x180036c52  mov     r14, qword ptr [rsp+2B0h+var_290]
0x180036c57  mov     rax, [r14]
0x180036c5a  mov     r15, [rax+30h]
0x180036c5e  lea     rsi, [rbx+8]
0x180036c62  mov     rcx, [rsi]
0x180036c65  mov     qword ptr [rsi], 0
0x180036c6c  test    rcx, rcx
0x180036c6f  jz      short loc_180036C7E
0x180036c71  mov     rax, [rcx]
0x180036c74  mov     rax, [rax+10h]
0x180036c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c7d  nop
0x180036c7e  movaps  xmm0, xmmword ptr [r12]
0x180036c83  movdqa  xmmword ptr [rsp+2B0h+hstringHeader.Reserved], xmm0
0x180036c89  mov     r8, rsi
0x180036c8c  lea     rdx, [rsp+2B0h+hstringHeader]
0x180036c91  mov     rcx, r14
0x180036c94  mov     rax, r15
0x180036c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c9c  mov     rax, [rdi+50h]
0x180036ca0  xor     r14d, r14d
0x180036ca3  test    rax, rax
0x180036ca6  jz      short loc_180036CB2
0x180036ca8  mov     rcx, [rdi+48h]
0x180036cac  lock inc dword ptr [rax+0Ch]
0x180036cb0  jmp     short loc_180036CB8
0x180036cb2  mov     rcx, r14
0x180036cb5  mov     rax, r14
0x180036cb8  mov     [rbx+10h], rcx
0x180036cbc  mov     rcx, [rbx+18h]
0x180036cc0  mov     [rbx+18h], rax
0x180036cc4  test    rcx, rcx
0x180036cc7  jz      short loc_180036CE3
0x180036cc9  or      eax, 0FFFFFFFFh
0x180036ccc  lock xadd [rcx+0Ch], eax
0x180036cd1  cmp     eax, 1
0x180036cd4  jnz     short loc_180036CE3
0x180036cd6  mov     rax, [rcx]
0x180036cd9  mov     rax, [rax+8]
0x180036cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ce2  nop
0x180036ce3  mov     rcx, qword ptr [rsp+2B0h+var_290]
0x180036ce8  test    rcx, rcx
0x180036ceb  jz      short loc_180036CFA
0x180036ced  mov     rax, [rcx]
0x180036cf0  mov     rax, [rax+10h]
0x180036cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cf9  nop
0x180036cfa  mov     rax, [rdi+58h]
0x180036cfe  mov     rcx, [rax+8]
0x180036d02  mov     rax, [rcx]
0x180036d05  mov     edx, r13d
0x180036d08  mov     rax, [rax+248h]
0x180036d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d14  movaps  xmm0, xmmword ptr [r12]
0x180036d19  movdqu  xmmword ptr [rdi+178h], xmm0
0x180036d21  xor     edx, edx; Val
0x180036d23  mov     r8d, 208h; Size
0x180036d29  lea     rcx, [rsp+2B0h+var_260]; void *
0x180036d2e  call    memset_0
0x180036d33  lea     rdx, [rsp+2B0h+var_260]; unsigned __int16 *
0x180036d38  lea     rcx, aSystemRemotete; "System\\RemoteTextInputProcessor"
0x180036d3f  call    ?GetDesktopUniqueName@@YAXPEBGPEAGK@Z; GetDesktopUniqueName(ushort const *,ushort *,ulong)
0x180036d44  nop
0x180036d45  mov     rcx, [rdi+68h]
0x180036d49  mov     [rdi+68h], r14
0x180036d4d  test    rcx, rcx
0x180036d50  jz      short loc_180036D5F
0x180036d52  mov     rax, [rcx]
0x180036d55  mov     rax, [rax+10h]
0x180036d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d5e  nop
0x180036d5f  mov     [rdi+68h], r14
0x180036d63  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180036d6a  mov     ecx, 70h ; 'p'; unsigned __int64
0x180036d6f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180036d74  mov     qword ptr [rsp+2B0h+var_290], rax
0x180036d79  test    rax, rax
0x180036d7c  jnz     short loc_180036D88
0x180036d7e  mov     esi, 8007000Eh
0x180036d83  jmp     loc_180036E23
0x180036d88  mov     rcx, rax; this
0x180036d8b  call    ??0MessageProxyReconnectAdapter@@QEAA@XZ; MessageProxyReconnectAdapter::MessageProxyReconnectAdapter(void)
0x180036d90  mov     rbx, rax
0x180036d93  mov     qword ptr [rsp+2B0h+hstringHeader.Reserved], rax
0x180036d98  mov     qword ptr [rsp+2B0h+var_290], r14; int
0x180036d9d  lea     r9, [rdi+18h]; struct IMessageProxyReconnectAdapterOwner *
0x180036da1  lea     r8, [rsp+2B0h+var_260]; unsigned __int16 *
0x180036da6  lea     rdx, _GUID_b30e303e_7340_4446_bd7b_c37fdee42abc; struct _GUID *
0x180036dad  mov     rcx, rax; this
0x180036db0  call    ?RuntimeClassInitialize@MessageProxyReconnectAdapter@@QEAAJAEBU_GUID@@PEBGPEAUIMessageProxyReconnectAdapterOwner@@@Z; MessageProxyReconnectAdapter::RuntimeClassInitialize(_GUID const &,ushort const *,IMessageProxyReconnectAdapterOwner *)
0x180036db5  mov     esi, eax
0x180036db7  test    eax, eax
0x180036db9  js      short loc_180036E0E
0x180036dbb  test    rbx, rbx
0x180036dbe  jz      short loc_180036DD0
0x180036dc0  mov     rax, [rbx]
0x180036dc3  mov     rcx, rbx
0x180036dc6  mov     rax, [rax+8]
0x180036dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036dcf  nop
0x180036dd0  mov     [rdi+68h], rbx
0x180036dd4  test    rbx, rbx
0x180036dd7  jz      short loc_180036DE9
0x180036dd9  mov     rax, [rbx]
0x180036ddc  mov     rcx, rbx
0x180036ddf  mov     rax, [rax+10h]
0x180036de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036de8  nop
0x180036de9  xor     eax, eax
0x180036deb  mov     rcx, [rbp+1B0h+var_50]
0x180036df2  xor     rcx, rsp; StackCookie
0x180036df5  call    __security_check_cookie
0x180036dfa  add     rsp, 278h
0x180036e01  pop     r15
0x180036e03  pop     r14
0x180036e05  pop     r13
0x180036e07  pop     r12
0x180036e09  pop     rdi
0x180036e0a  pop     rsi
0x180036e0b  pop     rbx
0x180036e0c  pop     rbp
0x180036e0d  retn
0x180036e0e  test    rbx, rbx
0x180036e11  jz      short loc_180036E23
0x180036e13  mov     rax, [rbx]
0x180036e16  mov     rcx, rbx
0x180036e19  mov     rax, [rax+10h]
0x180036e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e22  nop
0x180036e23  mov     rcx, [rbp+1B8h]; this
0x180036e2a  mov     r9d, esi; char *
0x180036e2d  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\virtualization"...
0x180036e34  mov     edx, 3Dh ; '='; void *
0x180036e39  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180036e3f  mov     ecx, eax; this
0x180036e41  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180036e46  nop
0x180036e47  mov     r9d, eax; char *
0x180036e4a  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\virtualization"...
0x180036e51  mov     edx, 27h ; '''; void *
0x180036e56  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
