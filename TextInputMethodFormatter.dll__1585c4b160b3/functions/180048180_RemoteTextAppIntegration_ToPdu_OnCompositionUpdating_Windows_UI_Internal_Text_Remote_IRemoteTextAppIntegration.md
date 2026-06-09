# RemoteTextAppIntegration_ToPdu::OnCompositionUpdating(Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs *)

- ea: `0x180048180`
- end: `0x1800486ab`
- name: `?OnCompositionUpdating@RemoteTextAppIntegration_ToPdu@@QEAAJPEAUIRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAUIRemoteTextCompositionUpdatingEventArgs@34567@@Z`
- size: `1323`
- prototype: `__int64 __fastcall(RemoteTextAppIntegration_ToPdu *__hidden this, struct Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *, struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs *)`
- caller_count: `0`
- callee_count: `18`
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
- `0x18003e85c`
- `0x18003e910`
- `0x18003e9c8`
- `0x180048180`
- `0x180055d34`
- `0x180056070`
- `0x1800562e4`
- `0x18005650c`
- `0x18005658c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004834f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048470`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004834f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048470`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RemoteTextAppIntegration_ToPdu::OnCompositionUpdating(
        RemoteTextAppIntegration_ToPdu *this,
        struct Windows::UI::Internal::Text::Remote::IRemoteTextAppIntegration *a2,
        struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs *a3)
{
  Gryps::FlexOBuffer *v5; // r14
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rcx
  UINT32 v14; // ebx
  unsigned int v15; // edi
  PCWSTR StringRawBuffer; // rax
  __int64 v17; // rax
  unsigned int v18; // r9d
  unsigned int i; // edi
  PCWSTR v20; // rax
  unsigned __int64 v21; // rbx
  unsigned __int64 j; // rsi
  __int128 *v23; // rax
  unsigned __int64 v24; // rax
  unsigned __int8 *v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  __int64 v28; // rdi
  void (__fastcall *v29)(__int64, unsigned __int64, unsigned __int8 *, _BYTE *); // rbx
  unsigned __int64 v30; // rax
  int v32; // [rsp+20h] [rbp-79h]
  _BYTE v33[4]; // [rsp+30h] [rbp-69h] BYREF
  UINT32 v34; // [rsp+34h] [rbp-65h] BYREF
  unsigned int v35; // [rsp+38h] [rbp-61h] BYREF
  UINT32 length[2]; // [rsp+40h] [rbp-59h] BYREF
  __int64 v37; // [rsp+48h] [rbp-51h] BYREF
  int v38; // [rsp+50h] [rbp-49h] BYREF
  int v39; // [rsp+54h] [rbp-45h] BYREF
  int v40; // [rsp+58h] [rbp-41h] BYREF
  int v41; // [rsp+5Ch] [rbp-3Dh] BYREF
  int v42; // [rsp+60h] [rbp-39h] BYREF
  __int64 v43; // [rsp+68h] [rbp-31h] BYREF
  HSTRING string[2]; // [rsp+70h] [rbp-29h] BYREF
  __int128 v45; // [rsp+80h] [rbp-19h] BYREF
  unsigned __int64 v46; // [rsp+90h] [rbp-9h]
  unsigned __int64 v47; // [rsp+98h] [rbp-1h]
  struct _EVENT_DATA_DESCRIPTOR v48; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v49; // [rsp+B0h] [rbp+17h]
  __int64 v50; // [rsp+B8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  *(_QWORD *)length = operator new(0x20u);
  v5 = (Gryps::FlexOBuffer *)Gryps::FlexOBuffer::FlexOBuffer(*(Gryps::FlexOBuffer **)length);
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180082080, (unsigned __int8 *)byte_180077809, 0, 0, 2u, &v48);
  }
  v38 = 0;
  v6 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs *, int *))(*(_QWORD *)a3 + 48LL))(
         a3,
         &v38);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x440,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v6,
      v32);
  v39 = 0;
  v7 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs *, int *))(*(_QWORD *)a3 + 56LL))(
         a3,
         &v39);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x442,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v7,
      v32);
  v40 = 0;
  v8 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs *, int *))(*(_QWORD *)a3 + 64LL))(
         a3,
         &v40);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x444,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v8,
      v32);
  v41 = 0;
  v9 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs *, int *))(*(_QWORD *)a3 + 72LL))(
         a3,
         &v41);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x446,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v9,
      v32);
  v42 = 0;
  v10 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs *, int *))(*(_QWORD *)a3 + 80LL))(
          a3,
          &v42);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x448,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v10,
      v32);
  v35 = 0;
  v11 = *(_QWORD *)a3;
  v37 = 0;
  v12 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs *, __int64 *))(v11 + 88))(
          a3,
          &v37);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x44B,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v12,
      v32);
  v13 = v37;
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v37 + 56LL))(v37, &v35);
    v13 = v37;
  }
  *(_OWORD *)string = 0;
  v14 = 23;
  length[0] = 23;
  v15 = 0;
  if ( v35 )
  {
    while ( 1 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v13 + 48LL))(v13, v15, string);
      length[0] = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string[0], length);
      v48 = 0;
      v49 = 0;
      v50 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v48, StringRawBuffer, length[0]);
      v14 += 2 * length[0] + 12;
      std::wstring::~wstring(&v48);
      if ( ++v15 >= v35 )
        break;
      v13 = v37;
    }
    length[0] = v14;
  }
  v34 = v14 + 4;
  v17 = Gryps::FlexOBuffer::begin(v5, &v45);
  Gryps::FlexOBuffer::iterator::reserveBlob(v17, &v48, v18 + 4LL);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(&v48, &v34);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(&v48, length);
  LOWORD(v34) = 516;
  Gryps::FlexOBuffer::inserter::injectLE<unsigned short>(&v48, &v34);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(&v48, &v38);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(&v48, &v39);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(&v48, &v40);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(&v48, &v41);
  LOBYTE(v34) = v42;
  Gryps::FlexOBuffer::inserter::injectLE<unsigned char>(&v48, &v34);
  Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(&v48, &v35);
  for ( i = 0; i < v35; ++i )
  {
    (*(void (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v37 + 48LL))(v37, i, string);
    length[0] = 0;
    v20 = WindowsGetStringRawBuffer(string[0], length);
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v45, v20, length[0]);
    Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(&v48, length);
    if ( length[0] )
    {
      v21 = 0;
      for ( j = v46; v21 < j; ++v21 )
      {
        v23 = &v45;
        if ( v47 > 7 )
          v23 = (__int128 *)v45;
        LOWORD(v34) = *((_WORD *)v23 + v21);
        Gryps::FlexOBuffer::inserter::injectLE<unsigned short>(&v48, &v34);
      }
    }
    Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(&v48, &string[1]);
    Gryps::FlexOBuffer::inserter::injectLE<unsigned int>(&v48, (char *)&string[1] + 4);
    std::wstring::~wstring(&v45);
  }
  v24 = Gryps::FlexOBuffer::size(v5);
  v25 = (unsigned __int8 *)operator new[](v24);
  Gryps::FlexOBuffer::flatten(v5, v25);
  v33[0] = 0;
  v43 = 0;
  v26 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**((_QWORD **)this + 32) + 24LL))(
          *((_QWORD *)this + 32),
          &GUID_099ffbc8_8bcb_41b5_b056_57e77021bf1b,
          &v43);
  v27 = v26;
  if ( v26 >= 0 )
  {
    v28 = v43;
    v29 = *(void (__fastcall **)(__int64, unsigned __int64, unsigned __int8 *, _BYTE *))(*(_QWORD *)v43 + 24LL);
    v30 = Gryps::FlexOBuffer::size(v5);
    v29(v28, v30, v25, v33);
    v27 = v33[0] == 0 ? 0x80004005 : 0;
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x486,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\tsfpduserializer\\remotetextappintegration_topdu.cpp",
      (const char *)(unsigned int)v26,
      v32);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  return v27;
}

```

## disassembly

```asm
0x180048180  mov     [rsp-8+arg_8], rbx
0x180048185  mov     [rsp-8+arg_18], rsi
0x18004818a  push    rbp
0x18004818b  push    rdi
0x18004818c  push    r12
0x18004818e  push    r14
0x180048190  push    r15
0x180048192  lea     rbp, [rsp-37h]
0x180048197  sub     rsp, 0D0h
0x18004819e  mov     rax, cs:__security_cookie
0x1800481a5  xor     rax, rsp
0x1800481a8  mov     [rbp+57h+var_30], rax
0x1800481ac  mov     rbx, r8
0x1800481af  mov     r15, rcx
0x1800481b2  mov     ecx, 20h ; ' '; Size
0x1800481b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800481bc  mov     qword ptr [rbp+57h+length], rax
0x1800481c0  mov     rcx, rax; this
0x1800481c3  call    ??0FlexOBuffer@Gryps@@QEAA@XZ; Gryps::FlexOBuffer::FlexOBuffer(void)
0x1800481c8  mov     r14, rax
0x1800481cb  mov     eax, cs:dword_180082080
0x1800481d1  cmp     eax, 5
0x1800481d4  jbe     short loc_180048223
0x1800481d6  mov     rcx, cs:qword_180082098
0x1800481dd  mov     rax, cs:qword_180082090
0x1800481e4  mov     edx, 400000h
0x1800481e9  test    rdx, rax
0x1800481ec  jz      short loc_180048223
0x1800481ee  mov     rax, rcx
0x1800481f1  and     rax, rdx
0x1800481f4  cmp     rax, rcx
0x1800481f7  jnz     short loc_180048223
0x1800481f9  lea     rax, [rbp+57h+var_50]
0x1800481fd  mov     [rsp+0F0h+var_C8], rax
0x180048202  mov     [rsp+0F0h+var_D0], 2; int
0x18004820a  xor     r9d, r9d
0x18004820d  xor     r8d, r8d
0x180048210  lea     rdx, byte_180077809
0x180048217  lea     rcx, dword_180082080
0x18004821e  call    _tlgWriteTransfer_EventWriteTransfer
0x180048223  xor     r12d, r12d
0x180048226  mov     [rbp+57h+var_A0], r12d
0x18004822a  mov     rax, [rbx]
0x18004822d  lea     rdx, [rbp+57h+var_A0]
0x180048231  mov     rcx, rbx
0x180048234  mov     rax, [rax+30h]
0x180048238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004823d  mov     rcx, [rbp+5Fh]; this
0x180048241  test    eax, eax
0x180048243  js      loc_180048642
0x180048249  mov     [rbp+57h+var_9C], r12d
0x18004824d  mov     rax, [rbx]
0x180048250  lea     rdx, [rbp+57h+var_9C]
0x180048254  mov     rcx, rbx
0x180048257  mov     rax, [rax+38h]
0x18004825b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048260  mov     rcx, [rbp+5Fh]; this
0x180048264  test    eax, eax
0x180048266  js      loc_180048657
0x18004826c  mov     [rbp+57h+var_98], r12d
0x180048270  mov     rax, [rbx]
0x180048273  lea     rdx, [rbp+57h+var_98]
0x180048277  mov     rcx, rbx
0x18004827a  mov     rax, [rax+40h]
0x18004827e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048283  mov     rcx, [rbp+5Fh]; this
0x180048287  test    eax, eax
0x180048289  js      loc_18004866C
0x18004828f  mov     [rbp+57h+var_94], r12d
0x180048293  mov     rax, [rbx]
0x180048296  lea     rdx, [rbp+57h+var_94]
0x18004829a  mov     rcx, rbx
0x18004829d  mov     rax, [rax+48h]
0x1800482a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482a6  mov     rcx, [rbp+5Fh]; this
0x1800482aa  test    eax, eax
0x1800482ac  js      loc_180048681
0x1800482b2  mov     [rbp+57h+var_90], r12d
0x1800482b6  mov     rax, [rbx]
0x1800482b9  lea     rdx, [rbp+57h+var_90]
0x1800482bd  mov     rcx, rbx
0x1800482c0  mov     rax, [rax+50h]
0x1800482c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482c9  mov     rcx, [rbp+5Fh]; this
0x1800482cd  test    eax, eax
0x1800482cf  js      loc_180048696
0x1800482d5  mov     [rbp+57h+var_B8], r12d
0x1800482d9  mov     rax, [rbx]
0x1800482dc  mov     [rbp+57h+var_A8], r12
0x1800482e0  lea     rdx, [rbp+57h+var_A8]
0x1800482e4  mov     rcx, rbx
0x1800482e7  mov     rax, [rax+58h]
0x1800482eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482f0  mov     rcx, [rbp+5Fh]; this
0x1800482f4  test    eax, eax
0x1800482f6  js      loc_18004862D
0x1800482fc  mov     rcx, [rbp+57h+var_A8]
0x180048300  test    rcx, rcx
0x180048303  jz      short loc_180048319
0x180048305  mov     rax, [rcx]
0x180048308  lea     rdx, [rbp+57h+var_B8]
0x18004830c  mov     rax, [rax+38h]
0x180048310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048315  mov     rcx, [rbp+57h+var_A8]
0x180048319  xorps   xmm0, xmm0
0x18004831c  movups  xmmword ptr [rbp+57h+string], xmm0
0x180048320  mov     ebx, 17h
0x180048325  mov     [rbp+57h+length], ebx
0x180048328  mov     edi, r12d
0x18004832b  cmp     [rbp+57h+var_B8], r12d
0x18004832f  jbe     short loc_180048396
0x180048331  mov     rax, [rcx]
0x180048334  lea     r8, [rbp+57h+string]
0x180048338  mov     edx, edi
0x18004833a  mov     rax, [rax+30h]
0x18004833e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048343  mov     [rbp+57h+length], r12d
0x180048347  lea     rdx, [rbp+57h+length]; length
0x18004834b  mov     rcx, [rbp+57h+string]; string
0x18004834f  call    cs:__imp_WindowsGetStringRawBuffer
0x180048355  xorps   xmm0, xmm0
0x180048358  movups  [rbp+57h+var_50], xmm0
0x18004835c  mov     [rbp+57h+var_40], r12
0x180048360  mov     [rbp+57h+var_38], r12
0x180048364  mov     r8d, [rbp+57h+length]
0x180048368  mov     rdx, rax
0x18004836b  lea     rcx, [rbp+57h+var_50]
0x18004836f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180048374  mov     eax, [rbp+57h+length]
0x180048377  lea     ebx, [rbx+rax*2]
0x18004837a  add     ebx, 0Ch
0x18004837d  lea     rcx, [rbp+57h+var_50]
0x180048381  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048386  inc     edi
0x180048388  cmp     edi, [rbp+57h+var_B8]
0x18004838b  jnb     short loc_180048393
0x18004838d  mov     rcx, [rbp+57h+var_A8]
0x180048391  jmp     short loc_180048331
0x180048393  mov     [rbp+57h+length], ebx
0x180048396  lea     r9d, [rbx+4]
0x18004839a  mov     [rbp+57h+var_BC], r9d
0x18004839e  lea     rdx, [rbp+57h+var_70]
0x1800483a2  mov     rcx, r14
0x1800483a5  call    ?begin@FlexOBuffer@Gryps@@QEAA?AViterator@12@XZ; Gryps::FlexOBuffer::begin(void)
0x1800483aa  mov     r8d, r9d
0x1800483ad  add     r8, 4
0x1800483b1  lea     rdx, [rbp+57h+var_50]
0x1800483b5  mov     rcx, rax
0x1800483b8  call    ?reserveBlob@iterator@FlexOBuffer@Gryps@@QEAA?AVinserter@23@_K@Z; Gryps::FlexOBuffer::iterator::reserveBlob(unsigned __int64)
0x1800483bd  lea     rdx, [rbp+57h+var_BC]
0x1800483c1  lea     rcx, [rbp+57h+var_50]
0x1800483c5  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x1800483ca  lea     rdx, [rbp+57h+length]
0x1800483ce  lea     rcx, [rbp+57h+var_50]
0x1800483d2  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x1800483d7  mov     eax, 204h
0x1800483dc  mov     word ptr [rbp+57h+var_BC], ax
0x1800483e0  lea     rdx, [rbp+57h+var_BC]
0x1800483e4  lea     rcx, [rbp+57h+var_50]
0x1800483e8  call    ??$injectLE@G@inserter@FlexOBuffer@Gryps@@QEAAXAEBG@Z; Gryps::FlexOBuffer::inserter::injectLE<ushort>(ushort const &)
0x1800483ed  lea     rdx, [rbp+57h+var_A0]
0x1800483f1  lea     rcx, [rbp+57h+var_50]
0x1800483f5  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x1800483fa  lea     rdx, [rbp+57h+var_9C]
0x1800483fe  lea     rcx, [rbp+57h+var_50]
0x180048402  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x180048407  lea     rdx, [rbp+57h+var_98]
0x18004840b  lea     rcx, [rbp+57h+var_50]
0x18004840f  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x180048414  lea     rdx, [rbp+57h+var_94]
0x180048418  lea     rcx, [rbp+57h+var_50]
0x18004841c  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x180048421  mov     al, byte ptr [rbp+57h+var_90]
0x180048424  mov     byte ptr [rbp+57h+var_BC], al
0x180048427  lea     rdx, [rbp+57h+var_BC]
0x18004842b  lea     rcx, [rbp+57h+var_50]
0x18004842f  call    ??$injectLE@E@inserter@FlexOBuffer@Gryps@@QEAAXAEBE@Z; Gryps::FlexOBuffer::inserter::injectLE<uchar>(uchar const &)
0x180048434  lea     rdx, [rbp+57h+var_B8]
0x180048438  lea     rcx, [rbp+57h+var_50]
0x18004843c  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x180048441  mov     edi, r12d
0x180048444  cmp     [rbp+57h+var_B8], r12d
0x180048448  jbe     loc_18004850F
0x18004844e  mov     rcx, [rbp+57h+var_A8]
0x180048452  mov     rax, [rcx]
0x180048455  lea     r8, [rbp+57h+string]
0x180048459  mov     edx, edi
0x18004845b  mov     rax, [rax+30h]
0x18004845f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048464  mov     [rbp+57h+length], r12d
0x180048468  lea     rdx, [rbp+57h+length]; length
0x18004846c  mov     rcx, [rbp+57h+string]; string
0x180048470  call    cs:__imp_WindowsGetStringRawBuffer
0x180048476  xorps   xmm0, xmm0
0x180048479  movups  [rbp+57h+var_70], xmm0
0x18004847d  mov     [rbp+57h+var_60], r12
0x180048481  mov     [rbp+57h+var_58], r12
0x180048485  mov     r8d, [rbp+57h+length]
0x180048489  mov     rdx, rax
0x18004848c  lea     rcx, [rbp+57h+var_70]
0x180048490  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180048495  nop
0x180048496  lea     rdx, [rbp+57h+length]
0x18004849a  lea     rcx, [rbp+57h+var_50]
0x18004849e  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x1800484a3  cmp     [rbp+57h+length], r12d
0x1800484a7  jbe     short loc_1800484E0
0x1800484a9  mov     rbx, r12
0x1800484ac  mov     rsi, [rbp+57h+var_60]
0x1800484b0  test    rsi, rsi
0x1800484b3  jz      short loc_1800484E0
0x1800484b5  lea     rax, [rbp+57h+var_70]
0x1800484b9  cmp     [rbp+57h+var_58], 7
0x1800484be  cmova   rax, qword ptr [rbp+57h+var_70]
0x1800484c3  movzx   eax, word ptr [rax+rbx*2]
0x1800484c7  mov     word ptr [rbp+57h+var_BC], ax
0x1800484cb  lea     rdx, [rbp+57h+var_BC]
0x1800484cf  lea     rcx, [rbp+57h+var_50]
0x1800484d3  call    ??$injectLE@G@inserter@FlexOBuffer@Gryps@@QEAAXAEBG@Z; Gryps::FlexOBuffer::inserter::injectLE<ushort>(ushort const &)
0x1800484d8  inc     rbx
0x1800484db  cmp     rbx, rsi
0x1800484de  jb      short loc_1800484B5
0x1800484e0  lea     rdx, [rbp+57h+string+8]
0x1800484e4  lea     rcx, [rbp+57h+var_50]
0x1800484e8  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x1800484ed  lea     rdx, [rbp+57h+string+0Ch]
0x1800484f1  lea     rcx, [rbp+57h+var_50]
0x1800484f5  call    ??$injectLE@I@inserter@FlexOBuffer@Gryps@@QEAAXAEBI@Z; Gryps::FlexOBuffer::inserter::injectLE<uint>(uint const &)
0x1800484fa  nop
0x1800484fb  lea     rcx, [rbp+57h+var_70]
0x1800484ff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048504  inc     edi
0x180048506  cmp     edi, [rbp+57h+var_B8]
0x180048509  jb      loc_18004844E
0x18004850f  mov     rcx, r14; this
0x180048512  call    ?size@FlexOBuffer@Gryps@@QEAA_KXZ; Gryps::FlexOBuffer::size(void)
0x180048517  mov     rcx, rax; unsigned __int64
0x18004851a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004851f  mov     rsi, rax
0x180048522  mov     rdx, rax; unsigned __int8 *
0x180048525  mov     rcx, r14; this
0x180048528  call    ?flatten@FlexOBuffer@Gryps@@QEAA_KPEAE@Z; Gryps::FlexOBuffer::flatten(uchar *)
0x18004852d  mov     [rbp+57h+var_C0], r12b
0x180048531  mov     [rbp+57h+var_88], r12
0x180048535  mov     rcx, [r15+100h]
0x18004853c  mov     rdx, [rcx]
0x18004853f  mov     rax, [rdx+18h]
0x180048543  lea     r8, [rbp+57h+var_88]
0x180048547  lea     rdx, _GUID_099ffbc8_8bcb_41b5_b056_57e77021bf1b
0x18004854e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048553  mov     ebx, eax
0x180048555  test    eax, eax
0x180048557  jns     short loc_1800485A0
0x180048559  mov     rcx, [rbp+5Fh]; this
0x18004855d  mov     r9d, eax; char *
0x180048560  lea     r8, aMincoreTextinp_15; "mincore\\textinput\\dev\\virtualization"...
0x180048567  mov     edx, 486h; void *
0x18004856c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048571  nop
0x180048572  mov     rcx, [rbp+57h+var_88]
0x180048576  test    rcx, rcx
0x180048579  jz      short loc_180048588
0x18004857b  mov     rax, [rcx]
0x18004857e  mov     rax, [rax+10h]
0x180048582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048587  nop
0x180048588  mov     rcx, [rbp+57h+var_A8]
0x18004858c  test    rcx, rcx
0x18004858f  jz      short loc_18004859E
0x180048591  mov     rax, [rcx]
0x180048594  mov     rax, [rax+10h]
0x180048598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004859d  nop
0x18004859e  jmp     short loc_180048603
0x1800485a0  mov     rdi, [rbp+57h+var_88]
0x1800485a4  mov     rax, [rdi]
0x1800485a7  mov     rbx, [rax+18h]
0x1800485ab  mov     rcx, r14; this
0x1800485ae  call    ?size@FlexOBuffer@Gryps@@QEAA_KXZ; Gryps::FlexOBuffer::size(void)
0x1800485b3  mov     rdx, rax
0x1800485b6  lea     r9, [rbp+57h+var_C0]
0x1800485ba  mov     r8, rsi
0x1800485bd  mov     rcx, rdi
0x1800485c0  mov     rax, rbx
0x1800485c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485c8  mov     al, [rbp+57h+var_C0]
0x1800485cb  neg     al
0x1800485cd  sbb     ebx, ebx
0x1800485cf  not     ebx
0x1800485d1  and     ebx, 80004005h
0x1800485d7  mov     rcx, [rbp+57h+var_88]
0x1800485db  test    rcx, rcx
0x1800485de  jz      short loc_1800485ED
0x1800485e0  mov     rax, [rcx]
0x1800485e3  mov     rax, [rax+10h]
0x1800485e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485ec  nop
0x1800485ed  mov     rcx, [rbp+57h+var_A8]
0x1800485f1  test    rcx, rcx
0x1800485f4  jz      short loc_180048603
  ... truncated ...
```
