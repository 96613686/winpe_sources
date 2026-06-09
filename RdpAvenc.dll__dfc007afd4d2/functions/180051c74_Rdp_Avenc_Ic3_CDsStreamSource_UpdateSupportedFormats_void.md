# Rdp::Avenc::Ic3::CDsStreamSource::UpdateSupportedFormats(void)

- ea: `0x180051c74`
- end: `0x18005227e`
- name: `?UpdateSupportedFormats@CDsStreamSource@Ic3@Avenc@Rdp@@IEAA_NXZ`
- size: `1546`
- prototype: `bool __fastcall(Rdp::Avenc::Ic3::CDsStreamSource *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004f404`
- `0x180050758`

## callees

- `0x180001008`
- `0x180005260`
- `0x1800065a4`
- `0x18004cb8c`
- `0x18004cd1c`
- `0x180051c74`
- `0x1800544e8`
- `0x180089010`

## string_xrefs

- `0x180051d52`: `Rdp::Avenc::Ic3::CDsStreamSource::UpdateSupportedFormats`
- `0x180051e13`: `Rdp::Avenc::Ic3::CDsStreamSource::UpdateSupportedFormats`
- `0x180051f22`: `Rdp::Avenc::Ic3::CDsStreamSource::UpdateSupportedFormats`
- `0x1800520c0`: `Rdp::Avenc::Ic3::CDsStreamSource::UpdateSupportedFormats`
- `0x180052191`: `Rdp::Avenc::Ic3::CDsStreamSource::UpdateSupportedFormats`
- `0x180052186`: `CDsStreamSource::UpdateSupportedFormats - no device, early out`
- `0x180051d47`: `Skipping format update`
- `0x1800520b5`: `Supported formats updated`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Rdp::Avenc::Ic3::CDsStreamSource::UpdateSupportedFormats(
        Rdp::Avenc::Ic3::CDsStreamSource *this,
        __int64 a2,
        int a3,
        int a4)
{
  __int64 v5; // rcx
  int v6; // edx
  char v7; // r12
  __int64 v8; // rdx
  int v9; // r15d
  void ***v10; // r14
  _QWORD *v11; // rbx
  _QWORD *v12; // rdi
  __int64 v13; // rax
  void *v14; // rbx
  __int64 v15; // rdi
  __int64 v16; // rax
  void *v17; // r15
  _QWORD *v18; // rdx
  void *v19; // rcx
  __int64 v20; // rax
  int v21; // r8d
  int v22; // r9d
  void *v23; // r15
  _QWORD *v24; // rdx
  void *v25; // rcx
  void **v26; // r15
  void **v27; // rdi
  void *v28; // rax
  _QWORD *v29; // rdx
  __int64 v30; // rdx
  char *v31; // rbx
  __int64 v32; // rdx
  _QWORD *v33; // rdi
  _QWORD *v34; // r14
  __int64 v35; // rax
  const char *v37; // [rsp+68h] [rbp-9h] BYREF
  const char *v38; // [rsp+70h] [rbp-1h] BYREF
  const char *v39; // [rsp+78h] [rbp+7h] BYREF
  _QWORD v40[9]; // [rsp+80h] [rbp+Fh] BYREF
  void *v41; // [rsp+D8h] [rbp+67h] BYREF
  __int64 v42; // [rsp+E0h] [rbp+6Fh] BYREF
  const char *v43; // [rsp+E8h] [rbp+77h] BYREF
  const char *v44; // [rsp+F0h] [rbp+7Fh] BYREF

  if ( *((_QWORD *)this + 24) )
  {
    v5 = *((_QWORD *)this + 25);
    v6 = *(_DWORD *)(v5 + 144);
    LODWORD(v41) = *(_DWORD *)(v5 + 140);
    HIDWORD(v41) = v6;
    v42 = 0x10000003CLL;
    v7 = 1;
    if ( (_DWORD)v41 == *((_DWORD *)this + 72)
      && v6 == *((_DWORD *)this + 73)
      && *((_DWORD *)this + 74) == 60
      && *((_DWORD *)this + 75) == 1 )
    {
      v7 = 0;
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        LODWORD(v41) = (__int64)(*((_QWORD *)this + 29) - *((_QWORD *)this + 28)) >> 3;
        v8 = *((_QWORD *)this + 25);
        v37 = (const char *)(v8 + 112);
        LODWORD(v42) = *(_DWORD *)(*(_QWORD *)(v8 + 104) + 136LL);
        LODWORD(v43) = *(_DWORD *)(v8 + 128);
        v38 = "Skipping format update";
        v39 = "Rdp::Avenc::Ic3::CDsStreamSource::UpdateSupportedFormats";
        LODWORD(v44) = 536;
        v40[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&word_1800B25FE,
          a3,
          a4,
          (__int64)v40,
          (__int64)&v44,
          (__int64)&v39,
          (__int64)&v38,
          (__int64)&v43,
          (__int64)&v42,
          (__int64)&v37,
          (__int64)&v41);
      }
    }
    else
    {
      v9 = *(_DWORD *)(*(_QWORD *)(v5 + 104) + 284LL);
      v10 = (void ***)((char *)this + 224);
      v11 = (_QWORD *)*((_QWORD *)this + 28);
      v12 = (_QWORD *)*((_QWORD *)this + 29);
      if ( v11 != v12 )
      {
        do
        {
          if ( *v11 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
          ++v11;
        }
        while ( v11 != v12 );
        *((_QWORD *)this + 29) = *((_QWORD *)this + 28);
      }
      v13 = *((_QWORD *)this + 31);
      if ( v13 != *((_QWORD *)this + 32) )
        *((_QWORD *)this + 32) = v13;
      v14 = v41;
      v15 = v42;
      if ( v9 == 2 )
      {
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          v43 = "Supported format BGRA";
          v44 = "Rdp::Avenc::Ic3::CDsStreamSource::UpdateSupportedFormats";
          LODWORD(v41) = 502;
          v40[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)byte_1800B2721,
            a3,
            a4,
            (__int64)v40,
            (__int64)&v41,
            (__int64)&v44,
            (__int64)&v43);
        }
        v41 = operator new(0x70u);
        v16 = Rdp::Avenc::Ic3::CDsStreamFormat::CDsStreamFormat(v41, (char *)this + 208, v14, v15, 87);
        if ( v16 )
          v17 = (void *)(v16 + *(int *)(*(_QWORD *)v16 + 12LL));
        else
          v17 = 0;
        v41 = v17;
        if ( v17 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 8LL))(v17);
        v18 = (_QWORD *)*((_QWORD *)this + 29);
        if ( v18 == *((_QWORD **)this + 30) )
        {
          std::vector<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>(
            (char *)this + 224,
            v18,
            &v41);
          v19 = v41;
        }
        else
        {
          v19 = 0;
          *v18 = v17;
          *((_QWORD *)this + 29) += 8LL;
        }
        if ( v19 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
      }
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        v43 = "Supported format NV12";
        v44 = "Rdp::Avenc::Ic3::CDsStreamSource::UpdateSupportedFormats";
        LODWORD(v41) = 505;
        v40[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)qword_1800B2670,
          a3,
          a4,
          (__int64)v40,
          (__int64)&v41,
          (__int64)&v44,
          (__int64)&v43);
      }
      v41 = operator new(0x70u);
      v20 = Rdp::Avenc::Ic3::CDsStreamFormat::CDsStreamFormat(v41, (char *)this + 208, v14, v15, 103);
      if ( v20 )
        v23 = (void *)(v20 + *(int *)(*(_QWORD *)v20 + 12LL));
      else
        v23 = 0;
      v41 = v23;
      if ( v23 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 8LL))(v23);
      v24 = (_QWORD *)*((_QWORD *)this + 29);
      if ( v24 == *((_QWORD **)this + 30) )
      {
        std::vector<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>(
          (char *)this + 224,
          v24,
          &v41);
        v25 = v41;
      }
      else
      {
        v25 = 0;
        *v24 = v23;
        *((_QWORD *)this + 29) += 8LL;
      }
      if ( v25 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 16LL))(v25);
      v26 = *v10;
      if ( *v10 != *((void ***)this + 29) )
      {
        v27 = (void **)*((_QWORD *)this + 29);
        do
        {
          v28 = *v26;
          v41 = *v26;
          v29 = (_QWORD *)*((_QWORD *)this + 32);
          if ( v29 == *((_QWORD **)this + 33) )
          {
            std::vector<ds::nanocom::IStreamFormat *>::_Emplace_reallocate<ds::nanocom::IStreamFormat *>(
              (char *)this + 248,
              v29,
              &v41);
          }
          else
          {
            *v29 = v28;
            *((_QWORD *)this + 32) += 8LL;
          }
          ++v26;
        }
        while ( v26 != v27 );
        v15 = v42;
      }
      *((_QWORD *)this + 36) = v14;
      *((_QWORD *)this + 37) = v15;
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        LODWORD(v41) = (__int64)(*((_QWORD *)this + 29) - *((_QWORD *)this + 28)) >> 3;
        v30 = *((_QWORD *)this + 25);
        v40[0] = v30 + 112;
        LODWORD(v42) = *(_DWORD *)(*(_QWORD *)(v30 + 104) + 136LL);
        LODWORD(v43) = *(_DWORD *)(v30 + 128);
        v39 = "Supported formats updated";
        v38 = "Rdp::Avenc::Ic3::CDsStreamSource::UpdateSupportedFormats";
        LODWORD(v44) = 523;
        v37 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&byte_1800B26AF,
          v21,
          v22,
          (__int64)&v37,
          (__int64)&v44,
          (__int64)&v38,
          (__int64)&v39,
          (__int64)&v43,
          (__int64)&v42,
          (__int64)v40,
          (__int64)&v41);
      }
    }
  }
  else
  {
    v31 = (char *)this + 224;
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      LODWORD(v41) = (__int64)(*((_QWORD *)this + 29) - *((_QWORD *)this + 28)) >> 3;
      v32 = *((_QWORD *)this + 25);
      v40[0] = v32 + 112;
      LODWORD(v42) = *(_DWORD *)(*(_QWORD *)(v32 + 104) + 136LL);
      LODWORD(v43) = *(_DWORD *)(v32 + 128);
      v39 = "CDsStreamSource::UpdateSupportedFormats - no device, early out";
      v38 = "Rdp::Avenc::Ic3::CDsStreamSource::UpdateSupportedFormats";
      LODWORD(v44) = 465;
      v37 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\dsstreamsource.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)qword_1800B27C0,
        a3,
        a4,
        (__int64)&v37,
        (__int64)&v44,
        (__int64)&v38,
        (__int64)&v39,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)v40,
        (__int64)&v41);
    }
    *((_QWORD *)this + 36) = 0;
    v33 = *(_QWORD **)v31;
    v34 = (_QWORD *)*((_QWORD *)v31 + 1);
    if ( *(_QWORD **)v31 == v34 )
    {
      return 0;
    }
    else
    {
      do
      {
        if ( *v33 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v33 + 16LL))(*v33);
        ++v33;
      }
      while ( v33 != v34 );
      *((_QWORD *)v31 + 1) = *(_QWORD *)v31;
      v35 = *((_QWORD *)this + 31);
      if ( v35 != *((_QWORD *)this + 32) )
        *((_QWORD *)this + 32) = v35;
      return 1;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180051c74  mov     r11, rsp
0x180051c77  push    rbp
0x180051c78  push    rbx
0x180051c79  push    rsi
0x180051c7a  push    rdi
0x180051c7b  push    r12
0x180051c7d  push    r13
0x180051c7f  push    r14
0x180051c81  push    r15
0x180051c83  lea     rbp, [r11-5Fh]
0x180051c87  sub     rsp, 88h
0x180051c8e  mov     rsi, rcx
0x180051c91  cmp     qword ptr [rcx+0C0h], 0
0x180051c99  jz      loc_18005213D
0x180051c9f  mov     rcx, [rcx+0C8h]
0x180051ca6  mov     eax, [rcx+8Ch]
0x180051cac  mov     edx, [rcx+90h]
0x180051cb2  mov     dword ptr [rbp+57h+arg_0], eax
0x180051cb5  mov     dword ptr [rbp+57h+arg_0+4], edx
0x180051cb8  mov     dword ptr [rbp+57h+arg_8], 3Ch ; '<'
0x180051cbf  mov     r12d, 1
0x180051cc5  mov     dword ptr [rbp+57h+arg_8+4], r12d
0x180051cc9  cmp     eax, [rsi+120h]
0x180051ccf  jnz     loc_180051DBB
0x180051cd5  cmp     edx, [rsi+124h]
0x180051cdb  jnz     loc_180051DBB
0x180051ce1  cmp     dword ptr [rsi+128h], 3Ch ; '<'
0x180051ce8  jnz     loc_180051DBB
0x180051cee  cmp     [rsi+12Ch], r12d
0x180051cf5  jnz     loc_180051DBB
0x180051cfb  xor     r12b, r12b
0x180051cfe  mov     eax, cs:dword_1800C1058
0x180051d04  cmp     eax, 5
0x180051d07  jbe     loc_180052267
0x180051d0d  mov     rax, [rsi+0E8h]
0x180051d14  sub     rax, [rsi+0E0h]
0x180051d1b  sar     rax, 3
0x180051d1f  mov     dword ptr [rbp+57h+arg_0], eax
0x180051d22  mov     rdx, [rsi+0C8h]
0x180051d29  lea     rax, [rdx+70h]
0x180051d2d  mov     [rbp+57h+var_60], rax
0x180051d31  mov     rax, [rdx+68h]
0x180051d35  mov     ecx, [rax+88h]
0x180051d3b  mov     dword ptr [rbp+57h+arg_8], ecx
0x180051d3e  mov     eax, [rdx+80h]
0x180051d44  mov     dword ptr [rbp+57h+arg_10], eax
0x180051d47  lea     rax, aSkippingFormat; "Skipping format update"
0x180051d4e  mov     [rbp+57h+var_58], rax
0x180051d52  lea     rax, aRdpAvencIc3Cds_32; "Rdp::Avenc::Ic3::CDsStreamSource::Updat"...
0x180051d59  mov     [rbp+57h+var_50], rax
0x180051d5d  mov     dword ptr [rbp+57h+arg_18], 218h
0x180051d64  lea     rax, aOnecoreuapTerm_34; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180051d6b  mov     [rbp+57h+var_48], rax
0x180051d6f  lea     rax, [rbp+57h+arg_0]
0x180051d73  mov     [r11-70h], rax
0x180051d77  lea     rax, [rbp+57h+var_60]
0x180051d7b  mov     [r11-78h], rax
0x180051d7f  lea     rax, [rbp+57h+arg_8]
0x180051d83  mov     [r11-80h], rax
0x180051d87  lea     rax, [rbp+57h+arg_10]
0x180051d8b  mov     [rsp+0C0h+var_80], rax
0x180051d90  lea     rax, [rbp+57h+var_58]
0x180051d94  mov     [rsp+0C0h+var_88], rax
0x180051d99  lea     rax, [rbp+57h+var_50]
0x180051d9d  mov     [rsp+0C0h+var_90], rax
0x180051da2  lea     rax, [rbp+57h+arg_18]
0x180051da6  mov     [rsp+0C0h+var_98], rax
0x180051dab  lea     rax, [rbp+57h+var_48]
0x180051daf  lea     rdx, word_1800B25FE
0x180051db6  jmp     loc_180052127
0x180051dbb  mov     rax, [rcx+68h]
0x180051dbf  mov     r15d, [rax+11Ch]
0x180051dc6  lea     r14, [rsi+0E0h]
0x180051dcd  mov     rbx, [r14]
0x180051dd0  mov     rdi, [r14+8]
0x180051dd4  cmp     rbx, rdi
0x180051dd7  jz      short loc_180051DFE
0x180051dd9  mov     rcx, [rbx]
0x180051ddc  test    rcx, rcx
0x180051ddf  jz      short loc_180051DEE
0x180051de1  mov     rax, [rcx]
0x180051de4  mov     rax, [rax+10h]
0x180051de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ded  nop
0x180051dee  add     rbx, 8
0x180051df2  cmp     rbx, rdi
0x180051df5  jnz     short loc_180051DD9
0x180051df7  mov     rax, [r14]
0x180051dfa  mov     [r14+8], rax
0x180051dfe  lea     r13, [rsi+0F8h]
0x180051e05  mov     rax, [r13+0]
0x180051e09  cmp     rax, [r13+8]
0x180051e0d  jz      short loc_180051E13
0x180051e0f  mov     [r13+8], rax
0x180051e13  lea     rcx, aRdpAvencIc3Cds_32; "Rdp::Avenc::Ic3::CDsStreamSource::Updat"...
0x180051e1a  lea     rdx, aOnecoreuapTerm_34; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180051e21  mov     rbx, [rbp+57h+arg_0]
0x180051e25  mov     rdi, [rbp+57h+arg_8]
0x180051e29  cmp     r15d, 2
0x180051e2d  jnz     loc_180051F30
0x180051e33  mov     eax, cs:dword_1800C1058
0x180051e39  cmp     eax, 5
0x180051e3c  jbe     short loc_180051E8F
0x180051e3e  lea     rax, aSupportedForma_2; "Supported format BGRA"
0x180051e45  mov     [rbp+57h+arg_10], rax
0x180051e49  mov     [rbp+57h+arg_18], rcx
0x180051e4d  mov     dword ptr [rbp+57h+arg_0], 1F6h
0x180051e54  mov     [rbp+57h+var_48], rdx
0x180051e58  lea     rax, [rbp+57h+arg_10]
0x180051e5c  mov     [rsp+0C0h+var_88], rax
0x180051e61  lea     rax, [rbp+57h+arg_18]
0x180051e65  mov     [rsp+0C0h+var_90], rax
0x180051e6a  lea     rax, [rbp+57h+arg_0]
0x180051e6e  mov     [rsp+0C0h+var_98], rax
0x180051e73  lea     rax, [rbp+57h+var_48]
0x180051e77  mov     [rsp+0C0h+var_A0], rax
0x180051e7c  lea     rdx, byte_1800B2721
0x180051e83  lea     rcx, dword_1800C1058
0x180051e8a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180051e8f  mov     ecx, 70h ; 'p'; Size
0x180051e94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051e99  mov     [rbp+57h+arg_0], rax
0x180051e9d  lea     rdx, [rsi+0D0h]
0x180051ea4  mov     dword ptr [rsp+0C0h+var_A0], 57h ; 'W'
0x180051eac  mov     r9, rdi
0x180051eaf  mov     r8, rbx
0x180051eb2  mov     rcx, rax
0x180051eb5  call    ??0CDsStreamFormat@Ic3@Avenc@Rdp@@QEAA@AEBU_LUID@@UResolution@nanocom@ds@@USampleRate@67@W4DXGI_FORMAT@@@Z; Rdp::Avenc::Ic3::CDsStreamFormat::CDsStreamFormat(_LUID const &,ds::nanocom::Resolution,ds::nanocom::SampleRate,DXGI_FORMAT)
0x180051eba  mov     rcx, rax
0x180051ebd  test    rax, rax
0x180051ec0  jnz     short loc_180051EC7
0x180051ec2  xor     r15d, r15d
0x180051ec5  jmp     short loc_180051ED1
0x180051ec7  mov     rax, [rax]
0x180051eca  movsxd  r15, dword ptr [rax+0Ch]
0x180051ece  add     r15, rcx
0x180051ed1  mov     [rbp+57h+arg_0], r15
0x180051ed5  test    r15, r15
0x180051ed8  jz      short loc_180051EEA
0x180051eda  mov     rax, [r15]
0x180051edd  mov     rcx, r15
0x180051ee0  mov     rax, [rax+8]
0x180051ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ee9  nop
0x180051eea  mov     rdx, [r14+8]
0x180051eee  cmp     rdx, [r14+10h]
0x180051ef2  jz      short loc_180051F00
0x180051ef4  xor     ecx, ecx
0x180051ef6  mov     [rdx], r15
0x180051ef9  add     qword ptr [r14+8], 8
0x180051efe  jmp     short loc_180051F10
0x180051f00  lea     r8, [rbp+57h+arg_0]
0x180051f04  mov     rcx, r14
0x180051f07  call    ??$_Emplace_reallocate@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>(wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy> * const,wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy> &&)
0x180051f0c  mov     rcx, [rbp+57h+arg_0]
0x180051f10  test    rcx, rcx
0x180051f13  jz      short loc_180051F22
0x180051f15  mov     rax, [rcx]
0x180051f18  mov     rax, [rax+10h]
0x180051f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f21  nop
0x180051f22  lea     rcx, aRdpAvencIc3Cds_32; "Rdp::Avenc::Ic3::CDsStreamSource::Updat"...
0x180051f29  lea     rdx, aOnecoreuapTerm_34; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180051f30  lea     r15, [rsi+0D0h]
0x180051f37  mov     eax, cs:dword_1800C1058
0x180051f3d  cmp     eax, 5
0x180051f40  jbe     short loc_180051F93
0x180051f42  lea     rax, aSupportedForma_1; "Supported format NV12"
0x180051f49  mov     [rbp+57h+arg_10], rax
0x180051f4d  mov     [rbp+57h+arg_18], rcx
0x180051f51  mov     dword ptr [rbp+57h+arg_0], 1F9h
0x180051f58  mov     [rbp+57h+var_48], rdx
0x180051f5c  lea     rax, [rbp+57h+arg_10]
0x180051f60  mov     [rsp+0C0h+var_88], rax
0x180051f65  lea     rax, [rbp+57h+arg_18]
0x180051f69  mov     [rsp+0C0h+var_90], rax
0x180051f6e  lea     rax, [rbp+57h+arg_0]
0x180051f72  mov     [rsp+0C0h+var_98], rax
0x180051f77  lea     rax, [rbp+57h+var_48]
0x180051f7b  mov     [rsp+0C0h+var_A0], rax
0x180051f80  lea     rdx, qword_1800B2670
0x180051f87  lea     rcx, dword_1800C1058
0x180051f8e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180051f93  mov     ecx, 70h ; 'p'; Size
0x180051f98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051f9d  mov     [rbp+57h+arg_0], rax
0x180051fa1  mov     dword ptr [rsp+0C0h+var_A0], 67h ; 'g'
0x180051fa9  mov     r9, rdi
0x180051fac  mov     r8, rbx
0x180051faf  mov     rdx, r15
0x180051fb2  mov     rcx, rax
0x180051fb5  call    ??0CDsStreamFormat@Ic3@Avenc@Rdp@@QEAA@AEBU_LUID@@UResolution@nanocom@ds@@USampleRate@67@W4DXGI_FORMAT@@@Z; Rdp::Avenc::Ic3::CDsStreamFormat::CDsStreamFormat(_LUID const &,ds::nanocom::Resolution,ds::nanocom::SampleRate,DXGI_FORMAT)
0x180051fba  mov     rcx, rax
0x180051fbd  test    rax, rax
0x180051fc0  jnz     short loc_180051FC7
0x180051fc2  xor     r15d, r15d
0x180051fc5  jmp     short loc_180051FD1
0x180051fc7  mov     rax, [rax]
0x180051fca  movsxd  r15, dword ptr [rax+0Ch]
0x180051fce  add     r15, rcx
0x180051fd1  mov     [rbp+57h+arg_0], r15
0x180051fd5  test    r15, r15
0x180051fd8  jz      short loc_180051FEA
0x180051fda  mov     rax, [r15]
0x180051fdd  mov     rcx, r15
0x180051fe0  mov     rax, [rax+8]
0x180051fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fe9  nop
0x180051fea  mov     rdx, [r14+8]
0x180051fee  cmp     rdx, [r14+10h]
0x180051ff2  jz      short loc_180052000
0x180051ff4  xor     ecx, ecx
0x180051ff6  mov     [rdx], r15
0x180051ff9  add     qword ptr [r14+8], 8
0x180051ffe  jmp     short loc_180052010
0x180052000  lea     r8, [rbp+57h+arg_0]
0x180052004  mov     rcx, r14
0x180052007  call    ??$_Emplace_reallocate@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>(wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy> * const,wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy> &&)
0x18005200c  mov     rcx, [rbp+57h+arg_0]
0x180052010  test    rcx, rcx
0x180052013  jz      short loc_180052022
0x180052015  mov     rax, [rcx]
0x180052018  mov     rax, [rax+10h]
0x18005201c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052021  nop
0x180052022  mov     rax, [r14+8]
0x180052026  mov     r15, [r14]
0x180052029  cmp     r15, rax
0x18005202c  jz      short loc_180052065
0x18005202e  mov     rdi, rax
0x180052031  mov     rax, [r15]
0x180052034  mov     [rbp+57h+arg_0], rax
0x180052038  mov     rdx, [r13+8]
0x18005203c  cmp     rdx, [r13+10h]
0x180052040  jz      short loc_18005204C
0x180052042  mov     [rdx], rax
0x180052045  add     qword ptr [r13+8], 8
0x18005204a  jmp     short loc_180052058
0x18005204c  lea     r8, [rbp+57h+arg_0]
0x180052050  mov     rcx, r13
0x180052053  call    ??$_Emplace_reallocate@PEAUIStreamFormat@nanocom@ds@@@?$vector@PEAUIStreamFormat@nanocom@ds@@V?$allocator@PEAUIStreamFormat@nanocom@ds@@@std@@@std@@AEAAPEAPEAUIStreamFormat@nanocom@ds@@QEAPEAU234@$$QEAPEAU234@@Z; std::vector<ds::nanocom::IStreamFormat *>::_Emplace_reallocate<ds::nanocom::IStreamFormat *>(ds::nanocom::IStreamFormat * * const,ds::nanocom::IStreamFormat * &&)
0x180052058  add     r15, 8
0x18005205c  cmp     r15, rdi
0x18005205f  jnz     short loc_180052031
0x180052061  mov     rdi, [rbp+57h+arg_8]
0x180052065  mov     [rsi+120h], rbx
0x18005206c  mov     [rsi+128h], rdi
0x180052073  mov     eax, cs:dword_1800C1058
0x180052079  cmp     eax, 5
0x18005207c  jbe     loc_180052267
0x180052082  mov     rax, [r14+8]
0x180052086  sub     rax, [r14]
0x180052089  sar     rax, 3
0x18005208d  mov     dword ptr [rbp+57h+arg_0], eax
0x180052090  mov     rdx, [rsi+0C8h]
0x180052097  lea     rax, [rdx+70h]
0x18005209b  mov     [rbp+57h+var_48], rax
0x18005209f  mov     rax, [rdx+68h]
0x1800520a3  mov     ecx, [rax+88h]
0x1800520a9  mov     dword ptr [rbp+57h+arg_8], ecx
0x1800520ac  mov     eax, [rdx+80h]
0x1800520b2  mov     dword ptr [rbp+57h+arg_10], eax
0x1800520b5  lea     rax, aSupportedForma; "Supported formats updated"
0x1800520bc  mov     [rbp+57h+var_50], rax
0x1800520c0  lea     rax, aRdpAvencIc3Cds_32; "Rdp::Avenc::Ic3::CDsStreamSource::Updat"...
0x1800520c7  mov     [rbp+57h+var_58], rax
0x1800520cb  mov     dword ptr [rbp+57h+arg_18], 20Bh
0x1800520d2  lea     rax, aOnecoreuapTerm_34; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800520d9  mov     [rbp+57h+var_60], rax
0x1800520dd  lea     rax, [rbp+57h+arg_0]
0x1800520e1  mov     [rsp+58h], rax
0x1800520e6  lea     rax, [rbp+57h+var_48]
0x1800520ea  mov     [rsp+0C0h+var_70], rax
0x1800520ef  lea     rax, [rbp+57h+arg_8]
0x1800520f3  mov     [rsp+0C0h+var_78], rax
0x1800520f8  lea     rax, [rbp+57h+arg_10]
0x1800520fc  mov     [rsp+0C0h+var_80], rax
0x180052101  lea     rax, [rbp+57h+var_50]
0x180052105  mov     [rsp+0C0h+var_88], rax
0x18005210a  lea     rax, [rbp+57h+var_58]
0x18005210e  mov     [rsp+0C0h+var_90], rax
0x180052113  lea     rax, [rbp+57h+arg_18]
0x180052117  mov     [rsp+0C0h+var_98], rax
0x18005211c  lea     rax, [rbp+57h+var_60]
0x180052120  lea     rdx, byte_1800B26AF
0x180052127  mov     [rsp+0C0h+var_A0], rax
0x18005212c  lea     rcx, dword_1800C1058
0x180052133  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180052138  jmp     loc_180052267
0x18005213d  mov     eax, cs:dword_1800C1058
0x180052143  lea     rbx, [rcx+0E0h]
0x18005214a  cmp     eax, 5
0x18005214d  jbe     loc_180052209
0x180052153  mov     rax, [rbx+8]
0x180052157  sub     rax, [rbx]
0x18005215a  sar     rax, 3
0x18005215e  mov     dword ptr [rbp+57h+arg_0], eax
0x180052161  mov     rdx, [rcx+0C8h]
0x180052168  lea     rax, [rdx+70h]
0x18005216c  mov     [rbp+57h+var_48], rax
  ... truncated ...
```
