# Rdp::Avenc::Raw::CRawProcessor::OnChannelOfferEx(_GUID const &,_GUID const &,uint,Rdp::Avenc::IFileIoChannel *,Rdp::Avenc::IFileIoChannelEvents * *)

- ea: `0x18003a3e0`
- end: `0x18003a805`
- name: `?OnChannelOfferEx@CRawProcessor@Raw@Avenc@Rdp@@UEAAJAEBU_GUID@@0IPEAUIFileIoChannel@34@PEAPEAUIFileIoChannelEvents@34@@Z`
- size: `1061`
- prototype: `int(Rdp::Avenc::Raw::CRawProcessor *__hidden this, const struct _GUID *, const struct _GUID *, unsigned int, struct Rdp::Avenc::IFileIoChannel *, struct Rdp::Avenc::IFileIoChannelEvents **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800065a4`
- `0x1800080cc`
- `0x18000d3a4`
- `0x18000e848`
- `0x18000ec04`
- `0x1800199cc`
- `0x1800240b8`
- `0x180038e20`
- `0x180038eb4`
- `0x18003a3e0`
- `0x180089010`

## string_xrefs

- `0x18003a7de`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18003a43b`: `Failed to open property store`
- `0x18003a6bd`: `Failed to open property store`
- `0x18003a47a`: `Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length`
- `0x18003a6fc`: `Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length`
- `0x18003a4b2`: `Failed to set PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length`
- `0x18003a551`: `Failed to start FileIo graphics read channel`
- `0x18003a4f8`: `Failed to start FileIo graphics write channel`
- `0x18003a7f2`: `onecore\internal\sdk\inc\wil\opensource/wil/com.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Rdp::Avenc::Raw::CRawProcessor::OnChannelOfferEx(
        Rdp::Avenc::Raw::CRawProcessor *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const char *a4,
        struct Rdp::Avenc::IFileIoChannel *a5,
        struct Rdp::Avenc::IFileIoChannelEvents **a6)
{
  unsigned int v6; // r14d
  __int64 v8; // rax
  unsigned int v9; // eax
  unsigned int v10; // r9d
  unsigned int v11; // eax
  unsigned int v12; // r9d
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rdi
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  Rdp::Avenc::CFcWireEncoderWithBulkCompressor *v20; // rdi
  struct Rdp::Avenc::IIoPacketCompleteEvents *v21; // r8
  int v22; // eax
  __int64 v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // r9d
  unsigned int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // rdi
  __int64 result; // rax
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-48h]
  char *v33; // [rsp+28h] [rbp-40h]
  char *v34; // [rsp+28h] [rbp-40h]
  char *v35; // [rsp+28h] [rbp-40h]
  char *v36; // [rsp+28h] [rbp-40h]
  char *v37; // [rsp+28h] [rbp-40h]
  char *v38; // [rsp+28h] [rbp-40h]
  Rdp::Utils::Props *v39; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v40[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    v6 = (unsigned int)a4;
    if ( *(_OWORD *)a2 == *(_OWORD *)&GUID_AvencFileIoChannelGraphics )
    {
      v8 = *(_QWORD *)a5;
      v39 = 0;
      v9 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *, Rdp::Utils::Props **))(v8 + 24))(a5, &v39);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x19E,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
        (const char *)v9,
        (int)"Failed to open property store",
        v33);
      v11 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
              v39,
              (struct IPropertyStore *)&PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length,
              (const struct _tagpropertykey *)0x1000,
              v10);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1A8,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
        (const char *)v11,
        (int)"Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length",
        v34);
      v13 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
              v39,
              (struct IPropertyStore *)&PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length,
              (const struct _tagpropertykey *)8,
              v12);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1AF,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
        (const char *)v13,
        (int)"Failed to set PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length",
        v35);
      v14 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)a5 + 32LL))(a5);
      if ( v6 < 2 )
      {
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x1BC,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
          (const char *)v14,
          (int)"Failed to start FileIo graphics read channel",
          v36);
        v40[0] = 0;
        v16 = (**(__int64 (__fastcall ***)(struct Rdp::Avenc::IFileIoChannel *, GUID *, _QWORD *))a5)(
                a5,
                &GUID_ce09a263_f536_42c9_9acc_85b5652a904f,
                v40);
        if ( v16 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v16,
            v32);
        v17 = v40[0];
        v18 = 0;
        v40[0] = 0;
        v19 = *((_QWORD *)this + 49);
        *((_QWORD *)this + 49) = v17;
        if ( v19 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          v18 = v40[0];
        }
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        v20 = (Rdp::Avenc::CFcWireEncoderWithBulkCompressor *)operator new(0xC08u);
        v40[0] = v20;
        Rdp::Avenc::CFcWireEncoderWithBulkCompressor::CFcWireEncoderWithBulkCompressor(v20, a5, v21);
        *((_DWORD *)v20 + 768) = 0;
        v40[0] = v20;
        std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>::operator=<std::default_delete<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>,0>(
          (char *)this + 176,
          v40);
        std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>::~unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>(v40);
      }
      else
      {
        if ( v6 != 2 )
        {
          v31 = (const char *)(unsigned int)wil::verify_hresult<long>(2147549183LL);
          LODWORD(v36) = v6;
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x1CF,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
            v31,
            (int)"Unknown graphics channel instance id: %d",
            v36);
        }
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x1C8,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
          (const char *)v14,
          (int)"Failed to start FileIo graphics write channel",
          v36);
        v15 = *((_QWORD *)this + 48);
        *((_QWORD *)this + 48) = a5;
        (*(void (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)a5 + 8LL))(a5);
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      if ( this == (Rdp::Avenc::Raw::CRawProcessor *)88 )
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
            v32);
      }
    }
    else
    {
      if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_AvencFileIoChannelCursor.Data1
        || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_AvencFileIoChannelCursor.Data4 )
      {
        return 2147500037LL;
      }
      v24 = *(_QWORD *)a5;
      v39 = 0;
      v25 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *, Rdp::Utils::Props **))(v24 + 24))(a5, &v39);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
        (const char *)v25,
        (int)"Failed to open property store",
        v33);
      v27 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
              v39,
              (struct IPropertyStore *)&PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length,
              (const struct _tagpropertykey *)0x1000,
              v26);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1E2,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
        (const char *)v27,
        (int)"Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length",
        v37);
      v28 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)a5 + 32LL))(a5);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1E8,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
        (const char *)v28,
        (int)"Failed to start FileIo cursor channel",
        v38);
      v29 = *((_QWORD *)this + 50);
      *((_QWORD *)this + 50) = a5;
      (*(void (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)a5 + 8LL))(a5);
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    if ( v39 )
      (*(void (__fastcall **)(Rdp::Utils::Props *))(*(_QWORD *)v39 + 16LL))(v39);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1F4,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x18003a3e0  push    rbx
0x18003a3e2  push    rsi
0x18003a3e3  push    rdi
0x18003a3e4  push    r14
0x18003a3e6  sub     rsp, 48h
0x18003a3ea  mov     r14d, r9d
0x18003a3ed  mov     rsi, rcx
0x18003a3f0  mov     rax, [rdx]
0x18003a3f3  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelGraphics.Data1
0x18003a3fa  jnz     loc_18003A672
0x18003a400  mov     rax, [rdx+8]
0x18003a404  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelGraphics.Data4
0x18003a40b  jnz     loc_18003A672
0x18003a411  mov     rbx, [rsp+68h+arg_20]
0x18003a419  mov     rax, [rbx]
0x18003a41c  mov     [rsp+68h+var_38], 0
0x18003a425  lea     rdx, [rsp+68h+var_38]
0x18003a42a  mov     rcx, rbx
0x18003a42d  mov     rax, [rax+18h]
0x18003a431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a436  mov     rcx, [rsp+68h]; this
0x18003a43b  lea     rdx, aFailedToOpenPr_0; "Failed to open property store"
0x18003a442  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18003a447  mov     r9d, eax; char *
0x18003a44a  lea     rdi, aOnecoreuapTerm_42; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003a451  mov     r8, rdi; unsigned int
0x18003a454  mov     edx, 19Eh; void *
0x18003a459  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003a45e  mov     r8d, 1000h; struct _tagpropertykey *
0x18003a464  lea     rdx, PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length; struct IPropertyStore *
0x18003a46b  mov     rcx, [rsp+68h+var_38]; this
0x18003a470  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18003a475  mov     rcx, [rsp+68h]; this
0x18003a47a  lea     rdx, aFailedToSetPke_0; "Failed to set PKEY_Caps_FileIo_Read_Irp"...
0x18003a481  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18003a486  mov     r9d, eax; char *
0x18003a489  mov     r8, rdi; unsigned int
0x18003a48c  mov     edx, 1A8h; void *
0x18003a491  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003a496  mov     r8d, 8; struct _tagpropertykey *
0x18003a49c  lea     rdx, PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length; struct IPropertyStore *
0x18003a4a3  mov     rcx, [rsp+68h+var_38]; this
0x18003a4a8  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18003a4ad  mov     rcx, [rsp+68h]; this
0x18003a4b2  lea     rdx, aFailedToSetPke_1; "Failed to set PKEY_Caps_FileIo_Write_Ir"...
0x18003a4b9  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18003a4be  mov     r9d, eax; char *
0x18003a4c1  mov     r8, rdi; unsigned int
0x18003a4c4  mov     edx, 1AFh; void *
0x18003a4c9  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003a4ce  mov     rax, [rbx]
0x18003a4d1  mov     rcx, rbx
0x18003a4d4  mov     rax, [rax+20h]
0x18003a4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4dd  mov     ecx, r14d
0x18003a4e0  test    r14d, r14d
0x18003a4e3  jz      short loc_18003A54C
0x18003a4e5  sub     ecx, 1
0x18003a4e8  jz      short loc_18003A54C
0x18003a4ea  cmp     ecx, 1
0x18003a4ed  jnz     loc_18003A7AB
0x18003a4f3  mov     rcx, [rsp+68h]; this
0x18003a4f8  lea     rdx, aFailedToStartF; "Failed to start FileIo graphics write c"...
0x18003a4ff  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18003a504  mov     r9d, eax; char *
0x18003a507  mov     r8, rdi; unsigned int
0x18003a50a  mov     edx, 1C8h; void *
0x18003a50f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003a514  nop
0x18003a515  mov     rdi, [rsi+180h]
0x18003a51c  mov     [rsi+180h], rbx
0x18003a523  mov     rax, [rbx]
0x18003a526  mov     rcx, rbx
0x18003a529  mov     rax, [rax+8]
0x18003a52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a532  test    rdi, rdi
0x18003a535  jz      short loc_18003A547
0x18003a537  mov     rax, [rdi]
0x18003a53a  mov     rcx, rdi
0x18003a53d  mov     rax, [rax+10h]
0x18003a541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a546  nop
0x18003a547  jmp     loc_18003A629
0x18003a54c  mov     rcx, [rsp+68h]; this
0x18003a551  lea     rdx, aFailedToStartF_1; "Failed to start FileIo graphics read ch"...
0x18003a558  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18003a55d  mov     r9d, eax; char *
0x18003a560  mov     r8, rdi; unsigned int
0x18003a563  mov     edx, 1BCh; void *
0x18003a568  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003a56d  mov     [rsp+68h+var_30], 0
0x18003a576  mov     rax, [rbx]
0x18003a579  lea     r8, [rsp+68h+var_30]
0x18003a57e  lea     rdx, _GUID_ce09a263_f536_42c9_9acc_85b5652a904f
0x18003a585  mov     rcx, rbx
0x18003a588  mov     rax, [rax]
0x18003a58b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a590  mov     rcx, [rsp+68h]; this
0x18003a595  test    eax, eax
0x18003a597  js      loc_18003A7DB
0x18003a59d  mov     rax, [rsp+68h+var_30]
0x18003a5a2  xor     ecx, ecx
0x18003a5a4  mov     [rsp+68h+var_30], rcx
0x18003a5a9  mov     rdx, [rsi+188h]
0x18003a5b0  mov     [rsi+188h], rax
0x18003a5b7  test    rdx, rdx
0x18003a5ba  jz      short loc_18003A5D0
0x18003a5bc  mov     rax, [rdx]
0x18003a5bf  mov     rcx, rdx
0x18003a5c2  mov     rax, [rax+10h]
0x18003a5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5cb  mov     rcx, [rsp+68h+var_30]
0x18003a5d0  test    rcx, rcx
0x18003a5d3  jz      short loc_18003A5E2
0x18003a5d5  mov     rax, [rcx]
0x18003a5d8  mov     rax, [rax+10h]
0x18003a5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5e1  nop
0x18003a5e2  mov     ecx, 0C08h; Size
0x18003a5e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a5ec  mov     rdi, rax
0x18003a5ef  mov     [rsp+68h+var_30], rax
0x18003a5f4  mov     rdx, rbx; struct Rdp::Avenc::IFileIoChannel *
0x18003a5f7  mov     rcx, rax; this
0x18003a5fa  call    ??0CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAA@PEAUIFileIoChannel@12@PEAUIIoPacketCompleteEvents@12@@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::CFcWireEncoderWithBulkCompressor(Rdp::Avenc::IFileIoChannel *,Rdp::Avenc::IIoPacketCompleteEvents *)
0x18003a5ff  mov     dword ptr [rdi+0C00h], 0
0x18003a609  mov     [rsp+68h+var_30], rdi
0x18003a60e  lea     rcx, [rsi+0B0h]
0x18003a615  lea     rdx, [rsp+68h+var_30]
0x18003a61a  call    ??$?4U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@@std@@$0A@@?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>::operator=<std::default_delete<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>,0>(std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>> &&)
0x18003a61f  lea     rcx, [rsp+68h+var_30]
0x18003a624  call    ??1?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>::~unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>(void)
0x18003a629  lea     rcx, [rsi-58h]
0x18003a62d  test    rcx, rcx
0x18003a630  jz      short loc_18003A65E
0x18003a632  mov     rax, [rcx]
0x18003a635  mov     r8, [rsp+68h+arg_28]
0x18003a63d  lea     rdx, _GUID_0a6e23a0_618a_40d9_ad98_e1b064f18ccb
0x18003a644  mov     rax, [rax]
0x18003a647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a64c  mov     rcx, [rsp+68h]; this
0x18003a651  test    eax, eax
0x18003a653  js      loc_18003A7EF
0x18003a659  jmp     loc_18003A77B
0x18003a65e  mov     rax, [rsp+68h+arg_28]
0x18003a666  mov     qword ptr [rax], 0
0x18003a66d  jmp     loc_18003A77B
0x18003a672  mov     rax, [rdx]
0x18003a675  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelCursor.Data1
0x18003a67c  jnz     loc_18003A796
0x18003a682  mov     rax, [rdx+8]
0x18003a686  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelCursor.Data4
0x18003a68d  jnz     loc_18003A796
0x18003a693  mov     rbx, [rsp+68h+arg_20]
0x18003a69b  mov     rax, [rbx]
0x18003a69e  mov     [rsp+68h+var_38], 0
0x18003a6a7  lea     rdx, [rsp+68h+var_38]
0x18003a6ac  mov     rcx, rbx
0x18003a6af  mov     rax, [rax+18h]
0x18003a6b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6b8  mov     rcx, [rsp+68h]; this
0x18003a6bd  lea     rdx, aFailedToOpenPr_0; "Failed to open property store"
0x18003a6c4  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18003a6c9  mov     r9d, eax; char *
0x18003a6cc  lea     rdi, aOnecoreuapTerm_42; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003a6d3  mov     r8, rdi; unsigned int
0x18003a6d6  mov     edx, 1D8h; void *
0x18003a6db  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003a6e0  mov     r8d, 1000h; struct _tagpropertykey *
0x18003a6e6  lea     rdx, PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length; struct IPropertyStore *
0x18003a6ed  mov     rcx, [rsp+68h+var_38]; this
0x18003a6f2  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18003a6f7  mov     rcx, [rsp+68h]; this
0x18003a6fc  lea     rdx, aFailedToSetPke_0; "Failed to set PKEY_Caps_FileIo_Read_Irp"...
0x18003a703  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18003a708  mov     r9d, eax; char *
0x18003a70b  mov     r8, rdi; unsigned int
0x18003a70e  mov     edx, 1E2h; void *
0x18003a713  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003a718  mov     rax, [rbx]
0x18003a71b  mov     rcx, rbx
0x18003a71e  mov     rax, [rax+20h]
0x18003a722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a727  mov     rcx, [rsp+68h]; this
0x18003a72c  lea     rdx, aFailedToStartF_2; "Failed to start FileIo cursor channel"
0x18003a733  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18003a738  mov     r9d, eax; char *
0x18003a73b  mov     r8, rdi; unsigned int
0x18003a73e  mov     edx, 1E8h; void *
0x18003a743  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003a748  nop
0x18003a749  mov     rdi, [rsi+190h]
0x18003a750  mov     [rsi+190h], rbx
0x18003a757  mov     rax, [rbx]
0x18003a75a  mov     rcx, rbx
0x18003a75d  mov     rax, [rax+8]
0x18003a761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a766  test    rdi, rdi
0x18003a769  jz      short loc_18003A77B
0x18003a76b  mov     rax, [rdi]
0x18003a76e  mov     rcx, rdi
0x18003a771  mov     rax, [rax+10h]
0x18003a775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a77a  nop
0x18003a77b  mov     rcx, [rsp+68h+var_38]
0x18003a780  test    rcx, rcx
0x18003a783  jz      short loc_18003A792
0x18003a785  mov     rax, [rcx]
0x18003a788  mov     rax, [rax+10h]
0x18003a78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a791  nop
0x18003a792  xor     eax, eax
0x18003a794  jmp     short loc_18003A7A1
0x18003a796  mov     eax, 80004005h
0x18003a79b  jmp     short loc_18003A7A1
0x18003a79d  mov     eax, dword ptr [rsp+68h+var_38]
0x18003a7a1  add     rsp, 48h
0x18003a7a5  pop     r14
0x18003a7a7  pop     rdi
0x18003a7a8  pop     rsi
0x18003a7a9  pop     rbx
0x18003a7aa  retn
0x18003a7ab  mov     ecx, 8000FFFFh
0x18003a7b0  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003a7b5  mov     r9d, eax; char *
0x18003a7b8  mov     rcx, [rsp+68h]; this
0x18003a7bd  mov     dword ptr [rsp+68h+var_40], r14d; char *
0x18003a7c2  lea     rax, aUnknownGraphic; "Unknown graphics channel instance id: %"...
0x18003a7c9  mov     qword ptr [rsp+68h+var_48], rax; int
0x18003a7ce  mov     r8, rdi; unsigned int
0x18003a7d1  mov     edx, 1CFh; void *
0x18003a7d6  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a7db  mov     r9d, eax; char *
0x18003a7de  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003a7e5  mov     edx, 1CBEh; void *
0x18003a7ea  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003a7ef  mov     r9d, eax; char *
0x18003a7f2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003a7f9  mov     edx, 61Fh; void *
0x18003a7fe  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
