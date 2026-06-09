# Rdp::Avenc::Hevc::CHevcProcessor::OnChannelOfferEx(_GUID const &,_GUID const &,uint,Rdp::Avenc::IFileIoChannel *,Rdp::Avenc::IFileIoChannelEvents * *)

- ea: `0x180024770`
- end: `0x180024bbc`
- name: `?OnChannelOfferEx@CHevcProcessor@Hevc@Avenc@Rdp@@UEAAJAEBU_GUID@@0IPEAUIFileIoChannel@34@PEAPEAUIFileIoChannelEvents@34@@Z`
- size: `1100`
- prototype: `__int64 __fastcall(Rdp::Avenc::Hevc::CHevcProcessor *this, const struct _GUID *, const struct _GUID *, const char *, struct Rdp::Avenc::IFileIoChannel *, struct Rdp::Avenc::IFileIoChannelEvents **)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800080cc`
- `0x18000d420`
- `0x18000e848`
- `0x18000ec04`
- `0x1800199cc`
- `0x180021ad0`
- `0x18002224c`
- `0x1800240b8`
- `0x180024770`
- `0x180089010`

## string_xrefs

- `0x180024b95`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800247cf`: `Failed to open property store`
- `0x180024a3a`: `Failed to open property store`
- `0x18002480e`: `Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length`
- `0x180024a79`: `Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length`
- `0x180024846`: `Failed to set PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length`
- `0x180024aae`: `Failed to set PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length`
- `0x1800248ea`: `Failed to start FileIo graphics read channel`
- `0x18002488c`: `Failed to start FileIo graphics write channel`
- `0x180024ba9`: `onecore\internal\sdk\inc\wil\opensource/wil/com.h`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Hevc::CHevcProcessor::OnChannelOfferEx(
        Rdp::Avenc::Hevc::CHevcProcessor *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const char *a4,
        struct Rdp::Avenc::IFileIoChannel *a5,
        struct Rdp::Avenc::IFileIoChannelEvents **a6)
{
  unsigned int v6; // r14d
  struct Rdp::Avenc::IFileIoChannel *v8; // rbx
  __int64 v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // r9d
  unsigned int v12; // eax
  unsigned int v13; // r9d
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rsi
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rax
  int v22; // eax
  struct Rdp::Avenc::IFileIoChannel *v23; // rbx
  __int64 v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // r9d
  unsigned int v27; // eax
  unsigned int v28; // r9d
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // rsi
  __int64 result; // rax
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-48h]
  char *v35; // [rsp+28h] [rbp-40h]
  char *v36; // [rsp+28h] [rbp-40h]
  char *v37; // [rsp+28h] [rbp-40h]
  char *v38; // [rsp+28h] [rbp-40h]
  char *v39; // [rsp+28h] [rbp-40h]
  char *v40; // [rsp+28h] [rbp-40h]
  char *v41; // [rsp+28h] [rbp-40h]
  Rdp::Utils::Props *v42; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v43[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    v6 = (unsigned int)a4;
    v42 = 0;
    if ( *(_OWORD *)a2 == *(_OWORD *)&GUID_AvencFileIoChannelGraphics )
    {
      v8 = a5;
      v9 = *(_QWORD *)a5;
      v42 = 0;
      v10 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *, Rdp::Utils::Props **))(v9 + 24))(a5, &v42);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x198,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
        (const char *)v10,
        (int)"Failed to open property store",
        v35);
      v12 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
              v42,
              (struct IPropertyStore *)&PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length,
              (const struct _tagpropertykey *)0x1000,
              v11);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
        (const char *)v12,
        (int)"Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length",
        v36);
      v14 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
              v42,
              (struct IPropertyStore *)&PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length,
              (const struct _tagpropertykey *)8,
              v13);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1A9,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
        (const char *)v14,
        (int)"Failed to set PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length",
        v37);
      v15 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)v8 + 32LL))(v8);
      if ( v6 < 2 )
      {
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x1B6,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
          (const char *)v15,
          (int)"Failed to start FileIo graphics read channel",
          v38);
        v43[0] = 0;
        v17 = (**(__int64 (__fastcall ***)(struct Rdp::Avenc::IFileIoChannel *, GUID *, _QWORD *))v8)(
                v8,
                &GUID_ce09a263_f536_42c9_9acc_85b5652a904f,
                v43);
        if ( v17 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v17,
            v34);
        v18 = v43[0];
        v19 = 0;
        v43[0] = 0;
        v20 = *((_QWORD *)this + 25);
        *((_QWORD *)this + 25) = v18;
        if ( v20 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          v19 = v43[0];
        }
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        v21 = std::make_unique<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>,Rdp::Avenc::IFileIoChannel * &,0>(
                v43,
                &a5);
        std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>::operator=<std::default_delete<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>,0>(
          (char *)this + 176,
          v21);
        std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>::~unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>(v43);
      }
      else
      {
        if ( v6 != 2 )
        {
          v33 = (const char *)(unsigned int)wil::verify_hresult<long>(2147549183LL);
          LODWORD(v38) = v6;
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x1C9,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
            v33,
            (int)"Unknown graphics channel instance id: %d",
            v38);
        }
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x1C2,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
          (const char *)v15,
          (int)"Failed to start FileIo graphics write channel",
          v38);
        v16 = *((_QWORD *)this + 24);
        *((_QWORD *)this + 24) = v8;
        if ( v8 )
          (*(void (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)v8 + 8LL))(v8);
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      if ( this == (Rdp::Avenc::Hevc::CHevcProcessor *)88 )
      {
        *a6 = 0;
      }
      else
      {
        v22 = (**((__int64 (__fastcall ***)(char *, GUID *, struct Rdp::Avenc::IFileIoChannelEvents **))this - 11))(
                (char *)this - 88,
                &GUID_0a6e23a0_618a_40d9_ad98_e1b064f18ccb,
                a6);
        if ( v22 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x61F,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/com.h",
            (const char *)(unsigned int)v22,
            v34);
      }
    }
    else
    {
      if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_AvencFileIoChannelCursor.Data1
        || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_AvencFileIoChannelCursor.Data4 )
      {
        return 2147500037LL;
      }
      v23 = a5;
      v24 = *(_QWORD *)a5;
      v42 = 0;
      v25 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *, Rdp::Utils::Props **))(v24 + 24))(a5, &v42);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1D2,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
        (const char *)v25,
        (int)"Failed to open property store",
        v35);
      v27 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
              v42,
              (struct IPropertyStore *)&PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length,
              (const struct _tagpropertykey *)0x1000,
              v26);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1DC,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
        (const char *)v27,
        (int)"Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length",
        v39);
      v29 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
              v42,
              (struct IPropertyStore *)&PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length,
              0,
              v28);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1E3,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
        (const char *)v29,
        (int)"Failed to set PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length",
        v40);
      v30 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)v23 + 32LL))(v23);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1E9,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
        (const char *)v30,
        (int)"Failed to start FileIo cursor channel",
        v41);
      v31 = *((_QWORD *)this + 26);
      *((_QWORD *)this + 26) = v23;
      if ( v23 )
        (*(void (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)v23 + 8LL))(v23);
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    if ( v42 )
      (*(void (__fastcall **)(Rdp::Utils::Props *))(*(_QWORD *)v42 + 16LL))(v42);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1F3,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x180024770  mov     r11, rsp
0x180024773  push    rbx
0x180024774  push    rsi
0x180024775  push    rdi
0x180024776  push    r14
0x180024778  sub     rsp, 48h
0x18002477c  mov     r14d, r9d
0x18002477f  mov     rdi, rcx
0x180024782  mov     qword ptr [r11-38h], 0
0x18002478a  mov     rax, [rdx]
0x18002478d  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelGraphics.Data1
0x180024794  jnz     loc_1800249EF
0x18002479a  mov     rax, [rdx+8]
0x18002479e  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelGraphics.Data4
0x1800247a5  jnz     loc_1800249EF
0x1800247ab  mov     rbx, [r11+28h]
0x1800247af  mov     rax, [rbx]
0x1800247b2  mov     qword ptr [r11-38h], 0
0x1800247ba  lea     rdx, [r11-38h]
0x1800247be  mov     rcx, rbx
0x1800247c1  mov     rax, [rax+18h]
0x1800247c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247ca  mov     rcx, [rsp+68h]; this
0x1800247cf  lea     rdx, aFailedToOpenPr_0; "Failed to open property store"
0x1800247d6  mov     qword ptr [rsp+68h+var_48], rdx; int
0x1800247db  mov     r9d, eax; char *
0x1800247de  lea     rsi, aOnecoreuapTerm_26; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800247e5  mov     r8, rsi; unsigned int
0x1800247e8  mov     edx, 198h; void *
0x1800247ed  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800247f2  mov     r8d, 1000h; struct _tagpropertykey *
0x1800247f8  lea     rdx, PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length; struct IPropertyStore *
0x1800247ff  mov     rcx, [rsp+68h+var_38]; this
0x180024804  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180024809  mov     rcx, [rsp+68h]; this
0x18002480e  lea     rdx, aFailedToSetPke_0; "Failed to set PKEY_Caps_FileIo_Read_Irp"...
0x180024815  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18002481a  mov     r9d, eax; char *
0x18002481d  mov     r8, rsi; unsigned int
0x180024820  mov     edx, 1A2h; void *
0x180024825  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002482a  mov     r8d, 8; struct _tagpropertykey *
0x180024830  lea     rdx, PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length; struct IPropertyStore *
0x180024837  mov     rcx, [rsp+68h+var_38]; this
0x18002483c  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180024841  mov     rcx, [rsp+68h]; this
0x180024846  lea     rdx, aFailedToSetPke_1; "Failed to set PKEY_Caps_FileIo_Write_Ir"...
0x18002484d  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180024852  mov     r9d, eax; char *
0x180024855  mov     r8, rsi; unsigned int
0x180024858  mov     edx, 1A9h; void *
0x18002485d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180024862  mov     rax, [rbx]
0x180024865  mov     rcx, rbx
0x180024868  mov     rax, [rax+20h]
0x18002486c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024871  mov     ecx, r14d
0x180024874  test    r14d, r14d
0x180024877  jz      short loc_1800248E5
0x180024879  sub     ecx, 1
0x18002487c  jz      short loc_1800248E5
0x18002487e  cmp     ecx, 1
0x180024881  jnz     loc_180024B62
0x180024887  mov     rcx, [rsp+68h]; this
0x18002488c  lea     rdx, aFailedToStartF; "Failed to start FileIo graphics write c"...
0x180024893  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180024898  mov     r9d, eax; char *
0x18002489b  mov     r8, rsi; unsigned int
0x18002489e  mov     edx, 1C2h; void *
0x1800248a3  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800248a8  nop
0x1800248a9  mov     rsi, [rdi+0C0h]
0x1800248b0  mov     [rdi+0C0h], rbx
0x1800248b7  test    rbx, rbx
0x1800248ba  jz      short loc_1800248CB
0x1800248bc  mov     rax, [rbx]
0x1800248bf  mov     rcx, rbx
0x1800248c2  mov     rax, [rax+8]
0x1800248c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248cb  test    rsi, rsi
0x1800248ce  jz      short loc_1800248E0
0x1800248d0  mov     rax, [rsi]
0x1800248d3  mov     rcx, rsi
0x1800248d6  mov     rax, [rax+10h]
0x1800248da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248df  nop
0x1800248e0  jmp     loc_1800249A6
0x1800248e5  mov     rcx, [rsp+68h]; this
0x1800248ea  lea     rdx, aFailedToStartF_1; "Failed to start FileIo graphics read ch"...
0x1800248f1  mov     qword ptr [rsp+68h+var_48], rdx; int
0x1800248f6  mov     r9d, eax; char *
0x1800248f9  mov     r8, rsi; unsigned int
0x1800248fc  mov     edx, 1B6h; void *
0x180024901  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180024906  mov     [rsp+68h+var_30], 0
0x18002490f  mov     rax, [rbx]
0x180024912  lea     r8, [rsp+68h+var_30]
0x180024917  lea     rdx, _GUID_ce09a263_f536_42c9_9acc_85b5652a904f
0x18002491e  mov     rcx, rbx
0x180024921  mov     rax, [rax]
0x180024924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024929  mov     rcx, [rsp+68h]; this
0x18002492e  test    eax, eax
0x180024930  js      loc_180024B92
0x180024936  mov     rax, [rsp+68h+var_30]
0x18002493b  xor     ecx, ecx
0x18002493d  mov     [rsp+68h+var_30], rcx
0x180024942  mov     rdx, [rdi+0C8h]
0x180024949  mov     [rdi+0C8h], rax
0x180024950  test    rdx, rdx
0x180024953  jz      short loc_180024969
0x180024955  mov     rax, [rdx]
0x180024958  mov     rcx, rdx
0x18002495b  mov     rax, [rax+10h]
0x18002495f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024964  mov     rcx, [rsp+68h+var_30]
0x180024969  test    rcx, rcx
0x18002496c  jz      short loc_18002497B
0x18002496e  mov     rax, [rcx]
0x180024971  mov     rax, [rax+10h]
0x180024975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002497a  nop
0x18002497b  lea     rdx, [rsp+68h+arg_20]
0x180024983  lea     rcx, [rsp+68h+var_30]
0x180024988  call    ??$make_unique@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@AEAPEAUIFileIoChannel@Avenc@3@$0A@@std@@YA?AV?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@0@AEAPEAUIFileIoChannel@Avenc@Rdp@@@Z; std::make_unique<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>,Rdp::Avenc::IFileIoChannel * &,0>(Rdp::Avenc::IFileIoChannel * &)
0x18002498d  lea     rcx, [rdi+0B0h]
0x180024994  mov     rdx, rax
0x180024997  call    ??$?4U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@$0A@@?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>::operator=<std::default_delete<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>,0>(std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>> &&)
0x18002499c  lea     rcx, [rsp+68h+var_30]
0x1800249a1  call    ??1?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>::~unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>(void)
0x1800249a6  lea     rcx, [rdi-58h]
0x1800249aa  test    rcx, rcx
0x1800249ad  jz      short loc_1800249DB
0x1800249af  mov     rax, [rcx]
0x1800249b2  mov     r8, [rsp+68h+arg_28]
0x1800249ba  lea     rdx, _GUID_0a6e23a0_618a_40d9_ad98_e1b064f18ccb
0x1800249c1  mov     rax, [rax]
0x1800249c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249c9  mov     rcx, [rsp+68h]; this
0x1800249ce  test    eax, eax
0x1800249d0  js      loc_180024BA6
0x1800249d6  jmp     loc_180024B32
0x1800249db  mov     rax, [rsp+68h+arg_28]
0x1800249e3  mov     qword ptr [rax], 0
0x1800249ea  jmp     loc_180024B32
0x1800249ef  mov     rax, [rdx]
0x1800249f2  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelCursor.Data1
0x1800249f9  jnz     loc_180024B4D
0x1800249ff  mov     rax, [rdx+8]
0x180024a03  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelCursor.Data4
0x180024a0a  jnz     loc_180024B4D
0x180024a10  mov     rbx, [rsp+68h+arg_20]
0x180024a18  mov     rax, [rbx]
0x180024a1b  mov     [rsp+68h+var_38], 0
0x180024a24  lea     rdx, [rsp+68h+var_38]
0x180024a29  mov     rcx, rbx
0x180024a2c  mov     rax, [rax+18h]
0x180024a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a35  mov     rcx, [rsp+68h]; this
0x180024a3a  lea     rdx, aFailedToOpenPr_0; "Failed to open property store"
0x180024a41  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180024a46  mov     r9d, eax; char *
0x180024a49  lea     rsi, aOnecoreuapTerm_26; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180024a50  mov     r8, rsi; unsigned int
0x180024a53  mov     edx, 1D2h; void *
0x180024a58  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180024a5d  mov     r8d, 1000h; struct _tagpropertykey *
0x180024a63  lea     rdx, PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length; struct IPropertyStore *
0x180024a6a  mov     rcx, [rsp+68h+var_38]; this
0x180024a6f  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180024a74  mov     rcx, [rsp+68h]; this
0x180024a79  lea     rdx, aFailedToSetPke_0; "Failed to set PKEY_Caps_FileIo_Read_Irp"...
0x180024a80  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180024a85  mov     r9d, eax; char *
0x180024a88  mov     r8, rsi; unsigned int
0x180024a8b  mov     edx, 1DCh; void *
0x180024a90  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180024a95  xor     r8d, r8d; struct _tagpropertykey *
0x180024a98  lea     rdx, PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length; struct IPropertyStore *
0x180024a9f  mov     rcx, [rsp+68h+var_38]; this
0x180024aa4  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180024aa9  mov     rcx, [rsp+68h]; this
0x180024aae  lea     rdx, aFailedToSetPke_1; "Failed to set PKEY_Caps_FileIo_Write_Ir"...
0x180024ab5  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180024aba  mov     r9d, eax; char *
0x180024abd  mov     r8, rsi; unsigned int
0x180024ac0  mov     edx, 1E3h; void *
0x180024ac5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180024aca  mov     rax, [rbx]
0x180024acd  mov     rcx, rbx
0x180024ad0  mov     rax, [rax+20h]
0x180024ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ad9  mov     rcx, [rsp+68h]; this
0x180024ade  lea     rdx, aFailedToStartF_2; "Failed to start FileIo cursor channel"
0x180024ae5  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180024aea  mov     r9d, eax; char *
0x180024aed  mov     r8, rsi; unsigned int
0x180024af0  mov     edx, 1E9h; void *
0x180024af5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180024afa  nop
0x180024afb  mov     rsi, [rdi+0D0h]
0x180024b02  mov     [rdi+0D0h], rbx
0x180024b09  test    rbx, rbx
0x180024b0c  jz      short loc_180024B1D
0x180024b0e  mov     rax, [rbx]
0x180024b11  mov     rcx, rbx
0x180024b14  mov     rax, [rax+8]
0x180024b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b1d  test    rsi, rsi
0x180024b20  jz      short loc_180024B32
0x180024b22  mov     rax, [rsi]
0x180024b25  mov     rcx, rsi
0x180024b28  mov     rax, [rax+10h]
0x180024b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b31  nop
0x180024b32  mov     rcx, [rsp+68h+var_38]
0x180024b37  test    rcx, rcx
0x180024b3a  jz      short loc_180024B49
0x180024b3c  mov     rax, [rcx]
0x180024b3f  mov     rax, [rax+10h]
0x180024b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b48  nop
0x180024b49  xor     eax, eax
0x180024b4b  jmp     short loc_180024B58
0x180024b4d  mov     eax, 80004005h
0x180024b52  jmp     short loc_180024B58
0x180024b54  mov     eax, dword ptr [rsp+68h+var_38]
0x180024b58  add     rsp, 48h
0x180024b5c  pop     r14
0x180024b5e  pop     rdi
0x180024b5f  pop     rsi
0x180024b60  pop     rbx
0x180024b61  retn
0x180024b62  mov     ecx, 8000FFFFh
0x180024b67  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180024b6c  mov     r9d, eax; char *
0x180024b6f  mov     rcx, [rsp+68h]; this
0x180024b74  mov     dword ptr [rsp+68h+var_40], r14d; char *
0x180024b79  lea     rax, aUnknownGraphic; "Unknown graphics channel instance id: %"...
0x180024b80  mov     qword ptr [rsp+68h+var_48], rax; int
0x180024b85  mov     r8, rsi; unsigned int
0x180024b88  mov     edx, 1C9h; void *
0x180024b8d  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024b92  mov     r9d, eax; char *
0x180024b95  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024b9c  mov     edx, 1CBEh; void *
0x180024ba1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180024ba6  mov     r9d, eax; char *
0x180024ba9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024bb0  mov     edx, 61Fh; void *
0x180024bb5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
