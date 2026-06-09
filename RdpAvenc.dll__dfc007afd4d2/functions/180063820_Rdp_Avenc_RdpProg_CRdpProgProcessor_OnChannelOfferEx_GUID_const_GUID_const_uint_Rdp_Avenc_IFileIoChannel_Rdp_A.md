# Rdp::Avenc::RdpProg::CRdpProgProcessor::OnChannelOfferEx(_GUID const &,_GUID const &,uint,Rdp::Avenc::IFileIoChannel *,Rdp::Avenc::IFileIoChannelEvents * *)

- ea: `0x180063820`
- end: `0x180063c6c`
- name: `?OnChannelOfferEx@CRdpProgProcessor@RdpProg@Avenc@Rdp@@UEAAJAEBU_GUID@@0IPEAUIFileIoChannel@34@PEAPEAUIFileIoChannelEvents@34@@Z`
- size: `1100`
- prototype: `int(Rdp::Avenc::RdpProg::CRdpProgProcessor *__hidden this, const struct _GUID *, const struct _GUID *, unsigned int, struct Rdp::Avenc::IFileIoChannel *, struct Rdp::Avenc::IFileIoChannelEvents **)`
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
- `0x180063820`
- `0x180089010`

## string_xrefs

- `0x180063c45`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18006387f`: `Failed to open property store`
- `0x180063aea`: `Failed to open property store`
- `0x1800638be`: `Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length`
- `0x180063b29`: `Failed to set PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length`
- `0x1800638f6`: `Failed to set PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length`
- `0x180063b5e`: `Failed to set PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length`
- `0x18006399a`: `Failed to start FileIo graphics read channel`
- `0x18006393c`: `Failed to start FileIo graphics write channel`
- `0x180063c59`: `onecore\internal\sdk\inc\wil\opensource/wil/com.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Rdp::Avenc::RdpProg::CRdpProgProcessor::OnChannelOfferEx(
        Rdp::Avenc::RdpProg::CRdpProgProcessor *this,
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
        (void *)0x17D,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
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
        (void *)0x187,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
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
        (void *)0x18E,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
        (const char *)v14,
        (int)"Failed to set PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length",
        v37);
      v15 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)v8 + 32LL))(v8);
      if ( v6 < 2 )
      {
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x19B,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
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
            (void *)0x1AE,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
            v33,
            (int)"Unknown graphics channel instance id: %d",
            v38);
        }
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x1A7,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
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
      if ( this == (Rdp::Avenc::RdpProg::CRdpProgProcessor *)88 )
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
        (void *)0x1B7,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
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
        (void *)0x1C1,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
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
        (void *)0x1C8,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
        (const char *)v29,
        (int)"Failed to set PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length",
        v40);
      v30 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFileIoChannel *))(*(_QWORD *)v23 + 32LL))(v23);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x1CE,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
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
                           (void *)0x1D8,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x180063820  mov     r11, rsp
0x180063823  push    rbx
0x180063824  push    rsi
0x180063825  push    rdi
0x180063826  push    r14
0x180063828  sub     rsp, 48h
0x18006382c  mov     r14d, r9d
0x18006382f  mov     rdi, rcx
0x180063832  mov     qword ptr [r11-38h], 0
0x18006383a  mov     rax, [rdx]
0x18006383d  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelGraphics.Data1
0x180063844  jnz     loc_180063A9F
0x18006384a  mov     rax, [rdx+8]
0x18006384e  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelGraphics.Data4
0x180063855  jnz     loc_180063A9F
0x18006385b  mov     rbx, [r11+28h]
0x18006385f  mov     rax, [rbx]
0x180063862  mov     qword ptr [r11-38h], 0
0x18006386a  lea     rdx, [r11-38h]
0x18006386e  mov     rcx, rbx
0x180063871  mov     rax, [rax+18h]
0x180063875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006387a  mov     rcx, [rsp+68h]; this
0x18006387f  lea     rdx, aFailedToOpenPr_0; "Failed to open property store"
0x180063886  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18006388b  mov     r9d, eax; char *
0x18006388e  lea     rsi, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180063895  mov     r8, rsi; unsigned int
0x180063898  mov     edx, 17Dh; void *
0x18006389d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800638a2  mov     r8d, 1000h; struct _tagpropertykey *
0x1800638a8  lea     rdx, PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length; struct IPropertyStore *
0x1800638af  mov     rcx, [rsp+68h+var_38]; this
0x1800638b4  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x1800638b9  mov     rcx, [rsp+68h]; this
0x1800638be  lea     rdx, aFailedToSetPke_0; "Failed to set PKEY_Caps_FileIo_Read_Irp"...
0x1800638c5  mov     qword ptr [rsp+68h+var_48], rdx; int
0x1800638ca  mov     r9d, eax; char *
0x1800638cd  mov     r8, rsi; unsigned int
0x1800638d0  mov     edx, 187h; void *
0x1800638d5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800638da  mov     r8d, 8; struct _tagpropertykey *
0x1800638e0  lea     rdx, PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length; struct IPropertyStore *
0x1800638e7  mov     rcx, [rsp+68h+var_38]; this
0x1800638ec  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x1800638f1  mov     rcx, [rsp+68h]; this
0x1800638f6  lea     rdx, aFailedToSetPke_1; "Failed to set PKEY_Caps_FileIo_Write_Ir"...
0x1800638fd  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180063902  mov     r9d, eax; char *
0x180063905  mov     r8, rsi; unsigned int
0x180063908  mov     edx, 18Eh; void *
0x18006390d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180063912  mov     rax, [rbx]
0x180063915  mov     rcx, rbx
0x180063918  mov     rax, [rax+20h]
0x18006391c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063921  mov     ecx, r14d
0x180063924  test    r14d, r14d
0x180063927  jz      short loc_180063995
0x180063929  sub     ecx, 1
0x18006392c  jz      short loc_180063995
0x18006392e  cmp     ecx, 1
0x180063931  jnz     loc_180063C12
0x180063937  mov     rcx, [rsp+68h]; this
0x18006393c  lea     rdx, aFailedToStartF; "Failed to start FileIo graphics write c"...
0x180063943  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180063948  mov     r9d, eax; char *
0x18006394b  mov     r8, rsi; unsigned int
0x18006394e  mov     edx, 1A7h; void *
0x180063953  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180063958  nop
0x180063959  mov     rsi, [rdi+0C0h]
0x180063960  mov     [rdi+0C0h], rbx
0x180063967  test    rbx, rbx
0x18006396a  jz      short loc_18006397B
0x18006396c  mov     rax, [rbx]
0x18006396f  mov     rcx, rbx
0x180063972  mov     rax, [rax+8]
0x180063976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006397b  test    rsi, rsi
0x18006397e  jz      short loc_180063990
0x180063980  mov     rax, [rsi]
0x180063983  mov     rcx, rsi
0x180063986  mov     rax, [rax+10h]
0x18006398a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006398f  nop
0x180063990  jmp     loc_180063A56
0x180063995  mov     rcx, [rsp+68h]; this
0x18006399a  lea     rdx, aFailedToStartF_1; "Failed to start FileIo graphics read ch"...
0x1800639a1  mov     qword ptr [rsp+68h+var_48], rdx; int
0x1800639a6  mov     r9d, eax; char *
0x1800639a9  mov     r8, rsi; unsigned int
0x1800639ac  mov     edx, 19Bh; void *
0x1800639b1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800639b6  mov     [rsp+68h+var_30], 0
0x1800639bf  mov     rax, [rbx]
0x1800639c2  lea     r8, [rsp+68h+var_30]
0x1800639c7  lea     rdx, _GUID_ce09a263_f536_42c9_9acc_85b5652a904f
0x1800639ce  mov     rcx, rbx
0x1800639d1  mov     rax, [rax]
0x1800639d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639d9  mov     rcx, [rsp+68h]; this
0x1800639de  test    eax, eax
0x1800639e0  js      loc_180063C42
0x1800639e6  mov     rax, [rsp+68h+var_30]
0x1800639eb  xor     ecx, ecx
0x1800639ed  mov     [rsp+68h+var_30], rcx
0x1800639f2  mov     rdx, [rdi+0C8h]
0x1800639f9  mov     [rdi+0C8h], rax
0x180063a00  test    rdx, rdx
0x180063a03  jz      short loc_180063A19
0x180063a05  mov     rax, [rdx]
0x180063a08  mov     rcx, rdx
0x180063a0b  mov     rax, [rax+10h]
0x180063a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a14  mov     rcx, [rsp+68h+var_30]
0x180063a19  test    rcx, rcx
0x180063a1c  jz      short loc_180063A2B
0x180063a1e  mov     rax, [rcx]
0x180063a21  mov     rax, [rax+10h]
0x180063a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a2a  nop
0x180063a2b  lea     rdx, [rsp+68h+arg_20]
0x180063a33  lea     rcx, [rsp+68h+var_30]
0x180063a38  call    ??$make_unique@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@AEAPEAUIFileIoChannel@Avenc@3@$0A@@std@@YA?AV?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@0@AEAPEAUIFileIoChannel@Avenc@Rdp@@@Z; std::make_unique<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>,Rdp::Avenc::IFileIoChannel * &,0>(Rdp::Avenc::IFileIoChannel * &)
0x180063a3d  lea     rcx, [rdi+0B0h]
0x180063a44  mov     rdx, rax
0x180063a47  call    ??$?4U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@$0A@@?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>::operator=<std::default_delete<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>,0>(std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>> &&)
0x180063a4c  lea     rcx, [rsp+68h+var_30]
0x180063a51  call    ??1?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>::~unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>(void)
0x180063a56  lea     rcx, [rdi-58h]
0x180063a5a  test    rcx, rcx
0x180063a5d  jz      short loc_180063A8B
0x180063a5f  mov     rax, [rcx]
0x180063a62  mov     r8, [rsp+68h+arg_28]
0x180063a6a  lea     rdx, _GUID_0a6e23a0_618a_40d9_ad98_e1b064f18ccb
0x180063a71  mov     rax, [rax]
0x180063a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a79  mov     rcx, [rsp+68h]; this
0x180063a7e  test    eax, eax
0x180063a80  js      loc_180063C56
0x180063a86  jmp     loc_180063BE2
0x180063a8b  mov     rax, [rsp+68h+arg_28]
0x180063a93  mov     qword ptr [rax], 0
0x180063a9a  jmp     loc_180063BE2
0x180063a9f  mov     rax, [rdx]
0x180063aa2  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelCursor.Data1
0x180063aa9  jnz     loc_180063BFD
0x180063aaf  mov     rax, [rdx+8]
0x180063ab3  cmp     rax, qword ptr cs:GUID_AvencFileIoChannelCursor.Data4
0x180063aba  jnz     loc_180063BFD
0x180063ac0  mov     rbx, [rsp+68h+arg_20]
0x180063ac8  mov     rax, [rbx]
0x180063acb  mov     [rsp+68h+var_38], 0
0x180063ad4  lea     rdx, [rsp+68h+var_38]
0x180063ad9  mov     rcx, rbx
0x180063adc  mov     rax, [rax+18h]
0x180063ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063ae5  mov     rcx, [rsp+68h]; this
0x180063aea  lea     rdx, aFailedToOpenPr_0; "Failed to open property store"
0x180063af1  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180063af6  mov     r9d, eax; char *
0x180063af9  lea     rsi, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180063b00  mov     r8, rsi; unsigned int
0x180063b03  mov     edx, 1B7h; void *
0x180063b08  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180063b0d  mov     r8d, 1000h; struct _tagpropertykey *
0x180063b13  lea     rdx, PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length; struct IPropertyStore *
0x180063b1a  mov     rcx, [rsp+68h+var_38]; this
0x180063b1f  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180063b24  mov     rcx, [rsp+68h]; this
0x180063b29  lea     rdx, aFailedToSetPke_0; "Failed to set PKEY_Caps_FileIo_Read_Irp"...
0x180063b30  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180063b35  mov     r9d, eax; char *
0x180063b38  mov     r8, rsi; unsigned int
0x180063b3b  mov     edx, 1C1h; void *
0x180063b40  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180063b45  xor     r8d, r8d; struct _tagpropertykey *
0x180063b48  lea     rdx, PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length; struct IPropertyStore *
0x180063b4f  mov     rcx, [rsp+68h+var_38]; this
0x180063b54  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x180063b59  mov     rcx, [rsp+68h]; this
0x180063b5e  lea     rdx, aFailedToSetPke_1; "Failed to set PKEY_Caps_FileIo_Write_Ir"...
0x180063b65  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180063b6a  mov     r9d, eax; char *
0x180063b6d  mov     r8, rsi; unsigned int
0x180063b70  mov     edx, 1C8h; void *
0x180063b75  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180063b7a  mov     rax, [rbx]
0x180063b7d  mov     rcx, rbx
0x180063b80  mov     rax, [rax+20h]
0x180063b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b89  mov     rcx, [rsp+68h]; this
0x180063b8e  lea     rdx, aFailedToStartF_2; "Failed to start FileIo cursor channel"
0x180063b95  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180063b9a  mov     r9d, eax; char *
0x180063b9d  mov     r8, rsi; unsigned int
0x180063ba0  mov     edx, 1CEh; void *
0x180063ba5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180063baa  nop
0x180063bab  mov     rsi, [rdi+0D0h]
0x180063bb2  mov     [rdi+0D0h], rbx
0x180063bb9  test    rbx, rbx
0x180063bbc  jz      short loc_180063BCD
0x180063bbe  mov     rax, [rbx]
0x180063bc1  mov     rcx, rbx
0x180063bc4  mov     rax, [rax+8]
0x180063bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063bcd  test    rsi, rsi
0x180063bd0  jz      short loc_180063BE2
0x180063bd2  mov     rax, [rsi]
0x180063bd5  mov     rcx, rsi
0x180063bd8  mov     rax, [rax+10h]
0x180063bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063be1  nop
0x180063be2  mov     rcx, [rsp+68h+var_38]
0x180063be7  test    rcx, rcx
0x180063bea  jz      short loc_180063BF9
0x180063bec  mov     rax, [rcx]
0x180063bef  mov     rax, [rax+10h]
0x180063bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063bf8  nop
0x180063bf9  xor     eax, eax
0x180063bfb  jmp     short loc_180063C08
0x180063bfd  mov     eax, 80004005h
0x180063c02  jmp     short loc_180063C08
0x180063c04  mov     eax, dword ptr [rsp+68h+var_38]
0x180063c08  add     rsp, 48h
0x180063c0c  pop     r14
0x180063c0e  pop     rdi
0x180063c0f  pop     rsi
0x180063c10  pop     rbx
0x180063c11  retn
0x180063c12  mov     ecx, 8000FFFFh
0x180063c17  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180063c1c  mov     r9d, eax; char *
0x180063c1f  mov     rcx, [rsp+68h]; this
0x180063c24  mov     dword ptr [rsp+68h+var_40], r14d; char *
0x180063c29  lea     rax, aUnknownGraphic; "Unknown graphics channel instance id: %"...
0x180063c30  mov     qword ptr [rsp+68h+var_48], rax; int
0x180063c35  mov     r8, rsi; unsigned int
0x180063c38  mov     edx, 1AEh; void *
0x180063c3d  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180063c42  mov     r9d, eax; char *
0x180063c45  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180063c4c  mov     edx, 1CBEh; void *
0x180063c51  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180063c56  mov     r9d, eax; char *
0x180063c59  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180063c60  mov     edx, 61Fh; void *
0x180063c65  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
