# RemoteTextAppIntegration_ToPdu::OnCompositionInfoUpdating(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs *)

- ea: `0x180047d50`
- end: `0x18004816f`
- name: `?OnCompositionInfoUpdating@RemoteTextAppIntegration_ToPdu@@QEAAJPEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextCompositionInfoUpdatingEventArgs@34567@@Z`
- size: `1055`
- prototype: `__int64 __fastcall(RemoteTextAppIntegration_ToPdu *__hidden this, struct Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *, struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs *)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x18000275c`
- `0x180002f2c`
- `0x180006a14`
- `0x180012074`
- `0x1800396e0`
- `0x18003e750`
- `0x18003e910`
- `0x18003e9c8`
- `0x180047d50`
- `0x180055d34`
- `0x180056070`
- `0x1800562e4`
- `0x18005650c`
- `0x18005658c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047ed4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047ed4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RemoteTextAppIntegration_ToPdu::OnCompositionInfoUpdating(
        RemoteTextAppIntegration_ToPdu *this,
        struct Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *a2,
        struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs *a3)
{
  Gryps::FlexOBuffer *v5; // rsi
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // rax
  unsigned int v14; // r9d
  unsigned __int64 v15; // rbx
  unsigned __int64 i; // rdi
  struct _EVENT_DATA_DESCRIPTOR *Ptr; // rax
  unsigned __int64 v18; // rax
  unsigned __int8 *v19; // r14
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rdi
  void (__fastcall *v23)(__int64, unsigned __int64, unsigned __int8 *, _BYTE *); // rbx
  unsigned __int64 v24; // rax
  int v26; // [rsp+20h] [rbp-79h]
  _BYTE v27[4]; // [rsp+30h] [rbp-69h] BYREF
  UINT32 v28; // [rsp+34h] [rbp-65h] BYREF
  UINT32 length; // [rsp+38h] [rbp-61h] BYREF
  int v30; // [rsp+3Ch] [rbp-5Dh] BYREF
  int v31; // [rsp+40h] [rbp-59h] BYREF
  int v32; // [rsp+44h] [rbp-55h] BYREF
  int v33; // [rsp+48h] [rbp-51h] BYREF
  __int64 v34; // [rsp+50h] [rbp-49h] BYREF
  __int64 v35; // [rsp+58h] [rbp-41h] BYREF
  Gryps::FlexOBuffer *v36; // [rsp+60h] [rbp-39h] BYREF
  HSTRING string; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v38[32]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v39[24]; // [rsp+90h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v40; // [rsp+A8h] [rbp+Fh] BYREF
  unsigned __int64 v41; // [rsp+B8h] [rbp+1Fh]
  unsigned __int64 v42; // [rsp+C0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v36 = (Gryps::FlexOBuffer *)operator new(0x20u);
  v5 = (Gryps::FlexOBuffer *)Gryps::FlexOBuffer::FlexOBuffer(v36);
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180082080, (unsigned __int8 *)byte_1800777A7, 0, 0, 2u, &v40);
  }
  v30 = 0;
  v6 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs *, int *))(*(_QWORD *)a3 + 48LL))(
         a3,
         &v30);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x496,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v6,
      v26);
  v31 = 0;
  v7 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs *, int *))(*(_QWORD *)a3 + 56LL))(
         a3,
         &v31);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x498,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v7,
      v26);
  v32 = 0;
  v8 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs *, int *))(*(_QWORD *)a3 + 64LL))(
         a3,
         &v32);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x49A,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v8,
      v26);
  v33 = 0;
  v9 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs *, int *))(*(_QWORD *)a3 + 72LL))(
         a3,
         &v33);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x49C,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v9,
      v26);
  v35 = 0;
  v10 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs *, __int64 *))(*(_QWORD *)a3 + 80LL))(
          a3,
          &v35);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x49E,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v10,
      v26);
  length = 0;
  string = 0;
  v11 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionInfoUpdatingEventArgs *, HSTRING *))(*(_QWORD *)a3 + 88LL))(
          a3,
          &string);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4A1,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v11,
      v26);
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  v40 = 0;
  v41 = 0;
  v42 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v40, StringRawBuffer, length);
  LODWORD(v36) = 2 * length + 30;
  v28 = 2 * length + 34;
  v13 = Gryps::FlexOBuffer::begin(v5, v39);
  Gryps::FlexOBuffer::iterator::reserveBlob(v13, v38, v14 + 4LL);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(v38, &v28);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(v38, &v36);
  LOWORD(v28) = 517;
  Gryps::FlexOBuffer::inserter::injectLE<unsigned short>(v38, &v28);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(v38, &v30);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(v38, &v31);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(v38, &v32);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(v38, &v33);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(v38, &v35);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(v38, (char *)&v35 + 4);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(v38, &length);
  if ( length )
  {
    v15 = 0;
    for ( i = v41; v15 < i; ++v15 )
    {
      Ptr = &v40;
      if ( v42 > 7 )
        Ptr = (struct _EVENT_DATA_DESCRIPTOR *)v40.Ptr;
      LOWORD(v28) = *((_WORD *)&Ptr->Ptr + v15);
      Gryps::FlexOBuffer::inserter::injectLE<unsigned short>(v38, &v28);
    }
  }
  v18 = Gryps::FlexOBuffer::size(v5);
  v19 = (unsigned __int8 *)operator new[](v18);
  Gryps::FlexOBuffer::flatten(v5, v19);
  v27[0] = 0;
  v34 = 0;
  v20 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**((_QWORD **)this + 32) + 24LL))(
          *((_QWORD *)this + 32),
          &GUID_099ffbc8_8bcb_41b5_b056_57e77021bf1b,
          &v34);
  v21 = v20;
  if ( v20 >= 0 )
  {
    v22 = v34;
    v23 = *(void (__fastcall **)(__int64, unsigned __int64, unsigned __int8 *, _BYTE *))(*(_QWORD *)v34 + 24LL);
    v24 = Gryps::FlexOBuffer::size(v5);
    v23(v22, v24, v19, v27);
    v21 = v27[0] == 0 ? 0x80004005 : 0;
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C5,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v20,
      v26);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  std::wstring::~wstring(&v40);
  return v21;
}

```

## disassembly

```asm
0x180047d50  mov     [rsp-8+arg_8], rbx
0x180047d55  mov     [rsp-8+arg_18], rsi
0x180047d5a  push    rbp
0x180047d5b  push    rdi
0x180047d5c  push    r12
0x180047d5e  push    r14
0x180047d60  push    r15
0x180047d62  lea     rbp, [rsp-37h]
0x180047d67  sub     rsp, 0D0h
0x180047d6e  mov     rax, cs:__security_cookie
0x180047d75  xor     rax, rsp
0x180047d78  mov     [rbp+57h+var_28], rax
0x180047d7c  mov     rbx, r8
0x180047d7f  mov     r15, rcx
0x180047d82  mov     ecx, 20h ; ' '; Size
0x180047d87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180047d8c  mov     [rbp+57h+var_90], rax
0x180047d90  mov     rcx, rax; this
0x180047d93  call    ??0FlexOBuffer@Gryps@@QEAA@XZ; Gryps::FlexOBuffer::FlexOBuffer(void)
0x180047d98  mov     rsi, rax
0x180047d9b  mov     eax, cs:dword_180082080
0x180047da1  cmp     eax, 5
0x180047da4  jbe     short loc_180047DF3
0x180047da6  mov     rcx, cs:qword_180082098
0x180047dad  mov     rax, cs:qword_180082090
0x180047db4  mov     edx, 400000h
0x180047db9  test    rdx, rax
0x180047dbc  jz      short loc_180047DF3
0x180047dbe  mov     rax, rcx
0x180047dc1  and     rax, rdx
0x180047dc4  cmp     rax, rcx
0x180047dc7  jnz     short loc_180047DF3
0x180047dc9  lea     rax, [rbp+57h+var_48]
0x180047dcd  mov     [rsp+0F0h+var_C8], rax
0x180047dd2  mov     [rsp+0F0h+var_D0], 2; int
0x180047dda  xor     r9d, r9d
0x180047ddd  xor     r8d, r8d
0x180047de0  lea     rdx, byte_1800777A7
0x180047de7  lea     rcx, dword_180082080
0x180047dee  call    _tlgWriteTransfer_EventWriteTransfer
0x180047df3  xor     r12d, r12d
0x180047df6  mov     [rbp+57h+var_B4], r12d
0x180047dfa  mov     rax, [rbx]
0x180047dfd  lea     rdx, [rbp+57h+var_B4]
0x180047e01  mov     rcx, rbx
0x180047e04  mov     rax, [rax+30h]
0x180047e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e0d  mov     rcx, [rbp+5Fh]; this
0x180047e11  test    eax, eax
0x180047e13  js      loc_180048106
0x180047e19  mov     [rbp+57h+var_B0], r12d
0x180047e1d  mov     rax, [rbx]
0x180047e20  lea     rdx, [rbp+57h+var_B0]
0x180047e24  mov     rcx, rbx
0x180047e27  mov     rax, [rax+38h]
0x180047e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e30  mov     rcx, [rbp+5Fh]; this
0x180047e34  test    eax, eax
0x180047e36  js      loc_18004811B
0x180047e3c  mov     [rbp+57h+var_AC], r12d
0x180047e40  mov     rax, [rbx]
0x180047e43  lea     rdx, [rbp+57h+var_AC]
0x180047e47  mov     rcx, rbx
0x180047e4a  mov     rax, [rax+40h]
0x180047e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e53  mov     rcx, [rbp+5Fh]; this
0x180047e57  test    eax, eax
0x180047e59  js      loc_180048130
0x180047e5f  mov     [rbp+57h+var_A8], r12d
0x180047e63  mov     rax, [rbx]
0x180047e66  lea     rdx, [rbp+57h+var_A8]
0x180047e6a  mov     rcx, rbx
0x180047e6d  mov     rax, [rax+48h]
0x180047e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e76  mov     rcx, [rbp+5Fh]; this
0x180047e7a  test    eax, eax
0x180047e7c  js      loc_180048145
0x180047e82  mov     [rbp+57h+var_98], r12
0x180047e86  mov     rax, [rbx]
0x180047e89  lea     rdx, [rbp+57h+var_98]
0x180047e8d  mov     rcx, rbx
0x180047e90  mov     rax, [rax+50h]
0x180047e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e99  mov     rcx, [rbp+5Fh]; this
0x180047e9d  test    eax, eax
0x180047e9f  js      loc_18004815A
0x180047ea5  mov     [rbp+57h+length], r12d
0x180047ea9  mov     [rbp+57h+string], r12
0x180047ead  mov     rax, [rbx]
0x180047eb0  lea     rdx, [rbp+57h+string]
0x180047eb4  mov     rcx, rbx
0x180047eb7  mov     rax, [rax+58h]
0x180047ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ec0  mov     rcx, [rbp+5Fh]; this
0x180047ec4  test    eax, eax
0x180047ec6  js      loc_1800480F1
0x180047ecc  lea     rdx, [rbp+57h+length]; length
0x180047ed0  mov     rcx, [rbp+57h+string]; string
0x180047ed4  call    cs:__imp_WindowsGetStringRawBuffer
0x180047eda  xorps   xmm0, xmm0
0x180047edd  movups  [rbp+57h+var_48], xmm0
0x180047ee1  mov     [rbp+57h+var_38], r12
0x180047ee5  mov     [rbp+57h+var_30], r12
0x180047ee9  mov     r8d, [rbp+57h+length]
0x180047eed  mov     rdx, rax
0x180047ef0  lea     rcx, [rbp+57h+var_48]
0x180047ef4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180047ef9  nop
0x180047efa  mov     eax, [rbp+57h+length]
0x180047efd  lea     eax, ds:1Eh[rax*2]
0x180047f04  mov     dword ptr [rbp+57h+var_90], eax
0x180047f07  lea     r9d, [rax+4]
0x180047f0b  mov     [rbp+57h+var_BC], r9d
0x180047f0f  lea     rdx, [rbp+57h+var_60]
0x180047f13  mov     rcx, rsi
0x180047f16  call    ?begin@FlexOBuffer@Gryps@@QEAA?AViterator@12@XZ; Gryps::FlexOBuffer::begin(void)
0x180047f1b  mov     r8d, r9d
0x180047f1e  add     r8, 4
0x180047f22  lea     rdx, [rbp+57h+var_80]
0x180047f26  mov     rcx, rax
0x180047f29  call    ?reserveBlob@iterator@FlexOBuffer@Gryps@@QEAA?AVinserter@23@_K@Z; Gryps::FlexOBuffer::iterator::reserveBlob(unsigned __int64)
0x180047f2e  lea     rdx, [rbp+57h+var_BC]
0x180047f32  lea     rcx, [rbp+57h+var_80]
0x180047f36  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x180047f3b  lea     rdx, [rbp+57h+var_90]
0x180047f3f  lea     rcx, [rbp+57h+var_80]
0x180047f43  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x180047f48  mov     eax, 205h
0x180047f4d  mov     word ptr [rbp+57h+var_BC], ax
0x180047f51  lea     rdx, [rbp+57h+var_BC]
0x180047f55  lea     rcx, [rbp+57h+var_80]
0x180047f59  call    ??$injectLE@G@inserter@FlexOBuffer@Gryps@@QEAAXAEBG@Z; Gryps::FlexOBuffer::inserter::injectLE<ushort>(ushort const &)
0x180047f5e  lea     rdx, [rbp+57h+var_B4]
0x180047f62  lea     rcx, [rbp+57h+var_80]
0x180047f66  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x180047f6b  lea     rdx, [rbp+57h+var_B0]
0x180047f6f  lea     rcx, [rbp+57h+var_80]
0x180047f73  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x180047f78  lea     rdx, [rbp+57h+var_AC]
0x180047f7c  lea     rcx, [rbp+57h+var_80]
0x180047f80  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x180047f85  lea     rdx, [rbp+57h+var_A8]
0x180047f89  lea     rcx, [rbp+57h+var_80]
0x180047f8d  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x180047f92  lea     rdx, [rbp+57h+var_98]
0x180047f96  lea     rcx, [rbp+57h+var_80]
0x180047f9a  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x180047f9f  lea     rdx, [rbp+57h+var_98+4]
0x180047fa3  lea     rcx, [rbp+57h+var_80]
0x180047fa7  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x180047fac  lea     rdx, [rbp+57h+length]
0x180047fb0  lea     rcx, [rbp+57h+var_80]
0x180047fb4  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x180047fb9  cmp     [rbp+57h+length], r12d
0x180047fbd  jbe     short loc_180047FF6
0x180047fbf  mov     ebx, r12d
0x180047fc2  mov     rdi, [rbp+57h+var_38]
0x180047fc6  test    rdi, rdi
0x180047fc9  jz      short loc_180047FF6
0x180047fcb  lea     rax, [rbp+57h+var_48]
0x180047fcf  cmp     [rbp+57h+var_30], 7
0x180047fd4  cmova   rax, qword ptr [rbp+57h+var_48]
0x180047fd9  movzx   eax, word ptr [rax+rbx*2]
0x180047fdd  mov     word ptr [rbp+57h+var_BC], ax
0x180047fe1  lea     rdx, [rbp+57h+var_BC]
0x180047fe5  lea     rcx, [rbp+57h+var_80]
0x180047fe9  call    ??$injectLE@G@inserter@FlexOBuffer@Gryps@@QEAAXAEBG@Z; Gryps::FlexOBuffer::inserter::injectLE<ushort>(ushort const &)
0x180047fee  inc     rbx
0x180047ff1  cmp     rbx, rdi
0x180047ff4  jb      short loc_180047FCB
0x180047ff6  mov     rcx, rsi; this
0x180047ff9  call    ?size@FlexOBuffer@Gryps@@QEAA_KXZ; Gryps::FlexOBuffer::size(void)
0x180047ffe  mov     rcx, rax; unsigned __int64
0x180048001  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180048006  mov     r14, rax
0x180048009  mov     rdx, rax; unsigned __int8 *
0x18004800c  mov     rcx, rsi; this
0x18004800f  call    ?flatten@FlexOBuffer@Gryps@@QEAA_KPEAE@Z; Gryps::FlexOBuffer::flatten(uchar *)
0x180048014  mov     [rbp+57h+var_C0], r12b
0x180048018  mov     [rbp+57h+var_A0], r12
0x18004801c  mov     rcx, [r15+100h]
0x180048023  mov     rdx, [rcx]
0x180048026  mov     rax, [rdx+18h]
0x18004802a  lea     r8, [rbp+57h+var_A0]
0x18004802e  lea     rdx, _GUID_099ffbc8_8bcb_41b5_b056_57e77021bf1b
0x180048035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004803a  mov     ebx, eax
0x18004803c  test    eax, eax
0x18004803e  jns     short loc_180048071
0x180048040  mov     rcx, [rbp+5Fh]; this
0x180048044  mov     r9d, eax; char *
0x180048047  lea     r8, aMincoreTextinp_15; "mincore\\textinput\\dev\\virtualization"...
0x18004804e  mov     edx, 4C5h; void *
0x180048053  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048058  nop
0x180048059  mov     rcx, [rbp+57h+var_A0]
0x18004805d  test    rcx, rcx
0x180048060  jz      short loc_18004806F
0x180048062  mov     rax, [rcx]
0x180048065  mov     rax, [rax+10h]
0x180048069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004806e  nop
0x18004806f  jmp     short loc_1800480BE
0x180048071  mov     rdi, [rbp+57h+var_A0]
0x180048075  mov     rax, [rdi]
0x180048078  mov     rbx, [rax+18h]
0x18004807c  mov     rcx, rsi; this
0x18004807f  call    ?size@FlexOBuffer@Gryps@@QEAA_KXZ; Gryps::FlexOBuffer::size(void)
0x180048084  mov     rdx, rax
0x180048087  lea     r9, [rbp+57h+var_C0]
0x18004808b  mov     r8, r14
0x18004808e  mov     rcx, rdi
0x180048091  mov     rax, rbx
0x180048094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048099  mov     al, [rbp+57h+var_C0]
0x18004809c  neg     al
0x18004809e  sbb     ebx, ebx
0x1800480a0  not     ebx
0x1800480a2  and     ebx, 80004005h
0x1800480a8  mov     rcx, [rbp+57h+var_A0]
0x1800480ac  test    rcx, rcx
0x1800480af  jz      short loc_1800480BE
0x1800480b1  mov     rdx, [rcx]
0x1800480b4  mov     rax, [rdx+10h]
0x1800480b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480bd  nop
0x1800480be  lea     rcx, [rbp+57h+var_48]
0x1800480c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800480c7  mov     eax, ebx
0x1800480c9  mov     rcx, [rbp+57h+var_28]
0x1800480cd  xor     rcx, rsp; StackCookie
0x1800480d0  call    __security_check_cookie
0x1800480d5  lea     r11, [rsp+0F0h+var_20]
0x1800480dd  mov     rbx, [r11+38h]
0x1800480e1  mov     rsi, [r11+48h]
0x1800480e5  mov     rsp, r11
0x1800480e8  pop     r15
0x1800480ea  pop     r14
0x1800480ec  pop     r12
0x1800480ee  pop     rdi
0x1800480ef  pop     rbp
0x1800480f0  retn
0x1800480f1  mov     r9d, eax; char *
0x1800480f4  lea     r8, aMincoreTextinp_15; "mincore\\textinput\\dev\\virtualization"...
0x1800480fb  mov     edx, 4A1h; void *
0x180048100  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180048106  mov     r9d, eax; char *
0x180048109  lea     r8, aMincoreTextinp_15; "mincore\\textinput\\dev\\virtualization"...
0x180048110  mov     edx, 496h; void *
0x180048115  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004811b  mov     r9d, eax; char *
0x18004811e  lea     r8, aMincoreTextinp_15; "mincore\\textinput\\dev\\virtualization"...
0x180048125  mov     edx, 498h; void *
0x18004812a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180048130  mov     r9d, eax; char *
0x180048133  lea     r8, aMincoreTextinp_15; "mincore\\textinput\\dev\\virtualization"...
0x18004813a  mov     edx, 49Ah; void *
0x18004813f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180048145  mov     r9d, eax; char *
0x180048148  lea     r8, aMincoreTextinp_15; "mincore\\textinput\\dev\\virtualization"...
0x18004814f  mov     edx, 49Ch; void *
0x180048154  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004815a  mov     r9d, eax; char *
0x18004815d  lea     r8, aMincoreTextinp_15; "mincore\\textinput\\dev\\virtualization"...
0x180048164  mov     edx, 49Eh; void *
0x180048169  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
