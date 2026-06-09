# Mso::SVG::SVGImage::Init(wchar_t * const &,bool)

- ea: `0x180004c38`
- end: `0x180004ffa`
- name: `?Init@SVGImage@SVG@Mso@@AEAAXAEBQEA_W_N@Z`
- size: `962`
- prototype: `void __fastcall(Mso::SVG::SVGImage *__hidden this, wchar_t *const *, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180003374`

## callees

- `0x180002fcc`
- `0x1800044c8`
- `0x180004c38`
- `0x180009068`
- `0x180010c3c`
- `0x18005fee4`
- `0x1800f5e48`
- `0x18010d754`
- `0x18013b4f8`
- `0x18013b97c`
- `0x18013d650`
- `0x18013f690`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180004fbd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180004fe6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180004fbd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180004fe6`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180004dd9`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180004dd9`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180004e1b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180004e1b`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180004de4`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180004de4`
- `Mso20Win32Client!__imp_?Load@XMLDOMDocument@Dom@Xml@Mso@@SAJAEBUDocumentIdentifier@234@AEBUDocumentLoadSettings@234@PEAPEAV1234@@Z` at `0x180004e56`
- `Mso20Win32Client!__imp_?Load@XMLDOMDocument@Dom@Xml@Mso@@SAJAEBUDocumentIdentifier@234@AEBUDocumentLoadSettings@234@PEAPEAV1234@@Z` at `0x180004e56`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004db0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180004db0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004da9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180004da9`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall Mso::SVG::SVGImage::Init(Mso::SVG::SVGImage *this, wchar_t *const *a2, char a3)
{
  __int64 v6; // rcx
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // r9
  int v8; // eax
  __int64 v9; // r8
  __int64 *v10; // rax
  __int64 v11; // rcx
  void *v12; // rcx
  void *v13; // rax
  __int64 v14; // rax
  Mso::SVG::Environment *v15; // rbx
  void *v16; // rdx
  int v17; // eax
  int v18; // eax
  struct Mso::Xml::Dom::XMLDOMNode *v19; // rax
  struct Mso::Xml::Dom::XMLDOMNode *v20; // rbx
  __int64 v21; // rcx
  struct Mso::Xml::Dom::XMLDOMDocument *v22; // rcx
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  struct Mso::Xml::Dom::XMLDOMDocument *v25; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v26[2]; // [rsp+48h] [rbp-B8h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v28; // [rsp+68h] [rbp-98h]
  _WORD v29[2088]; // [rsp+80h] [rbp-80h] BYREF

  v26[0] = 0;
  v6 = 0;
  v23 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 18);
  if ( v7 )
  {
    v8 = (**v7)(*((_QWORD *)this + 18), &GUID_a6e68895_4a20_4e02_89ed_b78019f5aa73, &v23);
    v6 = v23;
    if ( v8 < 0 )
    {
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        v6 = v23;
      }
    }
  }
  if ( v6 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(__int64, _WORD *, __int64))(*(_QWORD *)v6 + 24LL))(v6, v29, 2084) )
    {
      *(_OWORD *)Block = 0;
      v28 = 0;
      v9 = -1;
      do
        ++v9;
      while ( v29[v9] );
      std::wstring::_Construct<1,wchar_t *>(Block, v29, v9);
      v10 = (__int64 *)Mso::SVG::CreateExternalResourceLoader(&v24, Block);
      v11 = *v10;
      *v10 = 0;
      v26[0] = v11;
      if ( v24 )
        (**(void (__fastcall ***)(__int64, __int64))v24)(v24, 1);
      v24 = 19937;
      if ( *((_QWORD *)&v28 + 1) > 7u )
      {
        v12 = Block[0];
        if ( (unsigned __int64)(2LL * *((_QWORD *)&v28 + 1) + 2) >= 0x1000 )
        {
          v12 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v12 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v12);
      }
    }
    v6 = v23;
  }
  if ( v6 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v13 = Mso::Memory::AllocateEx((Mso::Memory *)0x2E0, 0, a3);
  if ( !v13 )
  {
    ThrowOOM();
    __debugbreak();
  }
  v24 = (__int64)v13;
  v14 = Mso::SVG::Environment::Environment(v13, v26);
  v15 = (Mso::SVG::Environment *)*((_QWORD *)this + 16);
  *((_QWORD *)this + 16) = v14;
  if ( v15 )
  {
    Mso::SVG::Environment::~Environment(v15);
    Mso::Memory::Free(v15, v16);
  }
  Block[0] = (void *)1;
  Block[1] = *(void **)a2;
  v23 = 0x100000000000100LL;
  v25 = 0;
  v17 = Mso::Xml::Dom::XMLDOMDocument::Load(
          (const struct Mso::Xml::Dom::DocumentIdentifier *)Block,
          (const struct Mso::Xml::Dom::DocumentLoadSettings *)&v23,
          &v25);
  if ( v17 == -2147217376 || v17 == 1 )
  {
LABEL_45:
    Ofc::CInvalidParamException::ThrowTag(0x138D85Eu);
    __debugbreak();
  }
  if ( v17 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v17, 0x138D85Fu);
LABEL_47:
    CrashWithRecovery(0x1E3C3840u, 0);
LABEL_48:
    Ofc::CHResultException::ThrowTag(v18, 0x138D860u);
    __debugbreak();
  }
  if ( a3 )
    sub_1800044C8(v25, *((_QWORD *)this + 16) + 552LL);
  v24 = 0;
  if ( !v25 )
    goto LABEL_47;
  v18 = (*(__int64 (__fastcall **)(struct Mso::Xml::Dom::XMLDOMDocument *, __int64 *))(*(_QWORD *)v25 + 24LL))(
          v25,
          &v24);
  if ( v18 < 0 )
    goto LABEL_48;
  if ( !v24 )
  {
    CrashWithRecovery(0x1E3C3840u, 0);
    goto LABEL_45;
  }
  v19 = (struct Mso::Xml::Dom::XMLDOMNode *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 72LL))(v24);
  v20 = v19;
  v26[1] = v19;
  if ( v19 )
    (**(void (__fastcall ***)(struct Mso::Xml::Dom::XMLDOMNode *))v19)(v19);
  v21 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
  }
  v22 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(struct Mso::Xml::Dom::XMLDOMDocument *))(*(_QWORD *)v22 + 8LL))(v22);
  }
  Mso::SVG::Environment::Traverse(*((Mso::SVG::Environment **)this + 16), v20, a3);
  if ( a3 )
    Mso::SVG::Stats::Log((Mso::SVG::Stats *)(*((_QWORD *)this + 16) + 552LL));
  if ( v20 )
    (*(void (__fastcall **)(struct Mso::Xml::Dom::XMLDOMNode *))(*(_QWORD *)v20 + 8LL))(v20);
  if ( v26[0] )
    (**(void (__fastcall ***)(_QWORD, __int64))v26[0])(v26[0], 1);
}

```

## disassembly

```asm
0x180004c38  mov     [rsp-8+arg_10], rbx
0x180004c3d  push    rbp
0x180004c3e  push    rsi
0x180004c3f  push    rdi
0x180004c40  push    r14
0x180004c42  push    r15
0x180004c44  lea     rbp, [rsp-0FE0h]
0x180004c4c  mov     eax, 10E0h
0x180004c51  call    _alloca_probe
0x180004c56  sub     rsp, rax
0x180004c59  mov     rax, cs:__security_cookie
0x180004c60  xor     rax, rsp
0x180004c63  mov     [rbp+1000h+var_30], rax
0x180004c6a  mov     sil, r8b
0x180004c6d  mov     r14, rdx
0x180004c70  mov     rdi, rcx
0x180004c73  xor     r15d, r15d
0x180004c76  mov     [rsp+1100h+var_10B8], r15
0x180004c7b  mov     ecx, r15d
0x180004c7e  mov     [rsp+1100h+var_10D0], rcx
0x180004c83  mov     r9, [rdi+90h]
0x180004c8a  test    r9, r9
0x180004c8d  jz      short loc_180004CCF
0x180004c8f  mov     rax, [r9]
0x180004c92  lea     r8, [rsp+1100h+var_10D0]
0x180004c97  lea     rdx, _GUID_a6e68895_4a20_4e02_89ed_b78019f5aa73
0x180004c9e  mov     rcx, r9
0x180004ca1  mov     rax, [rax]
0x180004ca4  call    cs:__guard_dispatch_icall_fptr
0x180004caa  mov     rcx, [rsp+1100h+var_10D0]
0x180004caf  test    eax, eax
0x180004cb1  jns     short loc_180004CCF
0x180004cb3  test    rcx, rcx
0x180004cb6  jz      short loc_180004CCF
0x180004cb8  mov     [rsp+1100h+var_10D0], r15
0x180004cbd  mov     rax, [rcx]
0x180004cc0  mov     rax, [rax+10h]
0x180004cc4  call    cs:__guard_dispatch_icall_fptr
0x180004cca  mov     rcx, [rsp+1100h+var_10D0]
0x180004ccf  test    rcx, rcx
0x180004cd2  jz      loc_180004DBB
0x180004cd8  mov     rax, [rcx]
0x180004cdb  mov     r8d, 824h
0x180004ce1  lea     rdx, [rbp+1000h+var_1080]
0x180004ce5  mov     rax, [rax+18h]
0x180004ce9  call    cs:__guard_dispatch_icall_fptr
0x180004cef  test    al, al
0x180004cf1  jz      loc_180004DB6
0x180004cf7  xorps   xmm0, xmm0
0x180004cfa  movups  xmmword ptr [rsp+1100h+Block], xmm0
0x180004cff  xorps   xmm1, xmm1
0x180004d02  movdqu  [rsp+1100h+var_1098], xmm1
0x180004d08  lea     rax, [rbp+1000h+var_1080]
0x180004d0c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004d10  inc     r8
0x180004d13  cmp     [rax+r8*2], r15w
0x180004d18  jnz     short loc_180004D10
0x180004d1a  lea     rdx, [rbp+1000h+var_1080]
0x180004d1e  lea     rcx, [rsp+1100h+Block]
0x180004d23  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180004d28  lea     rdx, [rsp+1100h+Block]
0x180004d2d  lea     rcx, [rsp+1100h+var_10C8]
0x180004d32  call    ?CreateExternalResourceLoader@SVG@Mso@@YA?AV?$unique_ptr@UIExternalResourceLoader@SVG@Mso@@U?$default_delete@UIExternalResourceLoader@SVG@Mso@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Mso::SVG::CreateExternalResourceLoader(std::wstring const &)
0x180004d37  mov     rcx, [rax]
0x180004d3a  mov     [rax], r15
0x180004d3d  mov     [rsp+1100h+var_10B8], rcx
0x180004d42  mov     rcx, [rsp+1100h+var_10C8]
0x180004d47  test    rcx, rcx
0x180004d4a  jz      short loc_180004D5D
0x180004d4c  mov     rax, [rcx]
0x180004d4f  mov     edx, 1
0x180004d54  mov     rax, [rax]
0x180004d57  call    cs:__guard_dispatch_icall_fptr
0x180004d5d  mov     [rsp+1100h+var_10C8], 4DE1h
0x180004d66  mov     rax, qword ptr [rsp+1100h+var_1098+8]
0x180004d6b  cmp     rax, 7
0x180004d6f  jbe     short loc_180004DB6
0x180004d71  mov     rcx, [rsp+1100h+Block]; Block
0x180004d76  mov     rdx, rcx
0x180004d79  lea     rax, ds:2[rax*2]
0x180004d81  cmp     rax, 1000h
0x180004d87  jb      short loc_180004DB0
0x180004d89  mov     rcx, [rcx-8]
0x180004d8d  sub     rdx, rcx
0x180004d90  lea     rax, [rdx-8]
0x180004d94  cmp     rax, 1Fh
0x180004d98  jbe     short loc_180004DB0
0x180004d9a  mov     [rsp+1100h+Reserved], r15; Reserved
0x180004d9f  xor     r9d, r9d; LineNo
0x180004da2  xor     r8d, r8d; FileName
0x180004da5  xor     edx, edx; FunctionName
0x180004da7  xor     ecx, ecx; Expression
0x180004da9  call    cs:__imp__invoke_watson
0x180004db0  call    cs:__imp_free
0x180004db6  mov     rcx, [rsp+1100h+var_10D0]
0x180004dbb  test    rcx, rcx
0x180004dbe  jz      short loc_180004DD2
0x180004dc0  mov     [rsp+1100h+var_10D0], r15
0x180004dc5  mov     rax, [rcx]
0x180004dc8  mov     rax, [rax+10h]
0x180004dcc  call    cs:__guard_dispatch_icall_fptr
0x180004dd2  xor     edx, edx
0x180004dd4  mov     ecx, 2E0h
0x180004dd9  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x180004ddf  test    rax, rax
0x180004de2  jnz     short loc_180004DEB
0x180004de4  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x180004dea  int     3; Trap to Debugger
0x180004deb  mov     [rsp+1100h+var_10C8], rax
0x180004df0  lea     rdx, [rsp+1100h+var_10B8]
0x180004df5  mov     rcx, rax
0x180004df8  call    ??0Environment@SVG@Mso@@QEAA@$$QEAV?$unique_ptr@UIExternalResourceLoader@SVG@Mso@@U?$default_delete@UIExternalResourceLoader@SVG@Mso@@@std@@@std@@@Z; Mso::SVG::Environment::Environment(std::unique_ptr<Mso::SVG::IExternalResourceLoader> &&)
0x180004dfd  mov     rbx, [rdi+80h]
0x180004e04  mov     [rdi+80h], rax
0x180004e0b  test    rbx, rbx
0x180004e0e  jz      short loc_180004E21
0x180004e10  mov     rcx, rbx; this
0x180004e13  call    ??1Environment@SVG@Mso@@QEAA@XZ; Mso::SVG::Environment::~Environment(void)
0x180004e18  mov     rcx, rbx
0x180004e1b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180004e21  mov     [rsp+1100h+Block], 1
0x180004e2a  mov     rax, [r14]
0x180004e2d  mov     [rsp+1100h+Block+8], rax
0x180004e32  mov     dword ptr [rsp+1100h+var_10D0], 100h
0x180004e3a  mov     dword ptr [rsp+1100h+var_10D0+4], 1000000h
0x180004e42  mov     [rsp+1100h+var_10C0], r15
0x180004e47  lea     r8, [rsp+1100h+var_10C0]
0x180004e4c  lea     rdx, [rsp+1100h+var_10D0]
0x180004e51  lea     rcx, [rsp+1100h+Block]
0x180004e56  call    cs:__imp_?Load@XMLDOMDocument@Dom@Xml@Mso@@SAJAEBUDocumentIdentifier@234@AEBUDocumentLoadSettings@234@PEAPEAV1234@@Z; Mso::Xml::Dom::XMLDOMDocument::Load(Mso::Xml::Dom::DocumentIdentifier const &,Mso::Xml::Dom::DocumentLoadSettings const &,Mso::Xml::Dom::XMLDOMDocument * *)
0x180004e5c  cmp     eax, 80041020h
0x180004e61  jz      loc_180004FC4
0x180004e67  cmp     eax, 1
0x180004e6a  jz      loc_180004FC4
0x180004e70  test    eax, eax
0x180004e72  js      loc_180004FCF
0x180004e78  test    sil, sil
0x180004e7b  jz      short loc_180004E95
0x180004e7d  mov     rdx, [rdi+80h]
0x180004e84  add     rdx, 228h
0x180004e8b  mov     rcx, [rsp+1100h+var_10C0]
0x180004e90  call    sub_1800044C8
0x180004e95  mov     [rsp+1100h+var_10C8], r15
0x180004e9a  mov     rcx, [rsp+1100h+var_10C0]
0x180004e9f  test    rcx, rcx
0x180004ea2  jz      loc_180004FDF
0x180004ea8  mov     rax, [rcx]
0x180004eab  lea     rdx, [rsp+1100h+var_10C8]
0x180004eb0  mov     rax, [rax+18h]
0x180004eb4  call    cs:__guard_dispatch_icall_fptr
0x180004eba  test    eax, eax
0x180004ebc  js      loc_180004FED
0x180004ec2  mov     rcx, [rsp+1100h+var_10C8]
0x180004ec7  test    rcx, rcx
0x180004eca  jz      loc_180004FB6
0x180004ed0  mov     rax, [rcx]
0x180004ed3  mov     rax, [rax+48h]
0x180004ed7  call    cs:__guard_dispatch_icall_fptr
0x180004edd  mov     rbx, rax
0x180004ee0  mov     [rsp+1100h+var_10B0], rax
0x180004ee5  test    rax, rax
0x180004ee8  jz      short loc_180004EFA
0x180004eea  mov     rax, [rax]
0x180004eed  mov     rcx, rbx
0x180004ef0  mov     rax, [rax]
0x180004ef3  call    cs:__guard_dispatch_icall_fptr
0x180004ef9  nop
0x180004efa  mov     rcx, [rsp+1100h+var_10C8]
0x180004eff  test    rcx, rcx
0x180004f02  jz      short loc_180004F17
0x180004f04  mov     [rsp+1100h+var_10C8], r15
0x180004f09  mov     rax, [rcx]
0x180004f0c  mov     rax, [rax+8]
0x180004f10  call    cs:__guard_dispatch_icall_fptr
0x180004f16  nop
0x180004f17  mov     rcx, [rsp+1100h+var_10C0]
0x180004f1c  test    rcx, rcx
0x180004f1f  jz      short loc_180004F34
0x180004f21  mov     [rsp+1100h+var_10C0], r15
0x180004f26  mov     rax, [rcx]
0x180004f29  mov     rax, [rax+8]
0x180004f2d  call    cs:__guard_dispatch_icall_fptr
0x180004f33  nop
0x180004f34  mov     r8b, sil; bool
0x180004f37  mov     rdx, rbx; struct Mso::Xml::Dom::XMLDOMNode *
0x180004f3a  mov     rcx, [rdi+80h]; this
0x180004f41  call    ?Traverse@Environment@SVG@Mso@@QEAAXPEAVXMLDOMNode@Dom@Xml@3@_N@Z; Mso::SVG::Environment::Traverse(Mso::Xml::Dom::XMLDOMNode *,bool)
0x180004f46  test    sil, sil
0x180004f49  jz      short loc_180004F5F
0x180004f4b  mov     rcx, [rdi+80h]
0x180004f52  add     rcx, 228h; this
0x180004f59  call    ?Log@Stats@SVG@Mso@@QEBAXXZ; Mso::SVG::Stats::Log(void)
0x180004f5e  nop
0x180004f5f  test    rbx, rbx
0x180004f62  jz      short loc_180004F75
0x180004f64  mov     rax, [rbx]
0x180004f67  mov     rcx, rbx
0x180004f6a  mov     rax, [rax+8]
0x180004f6e  call    cs:__guard_dispatch_icall_fptr
0x180004f74  nop
0x180004f75  mov     rcx, [rsp+1100h+var_10B8]
0x180004f7a  test    rcx, rcx
0x180004f7d  jz      short loc_180004F90
0x180004f7f  mov     rax, [rcx]
0x180004f82  mov     edx, 1
0x180004f87  mov     rax, [rax]
0x180004f8a  call    cs:__guard_dispatch_icall_fptr
0x180004f90  mov     rcx, [rbp+1000h+var_30]
0x180004f97  xor     rcx, rsp; StackCookie
0x180004f9a  call    __security_check_cookie
0x180004f9f  mov     rbx, [rsp+1100h+arg_10]
0x180004fa7  add     rsp, 10E0h
0x180004fae  pop     r15
0x180004fb0  pop     r14
0x180004fb2  pop     rdi
0x180004fb3  pop     rsi
0x180004fb4  pop     rbp
0x180004fb5  retn
0x180004fb6  xor     edx, edx
0x180004fb8  mov     ecx, 1E3C3840h
0x180004fbd  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180004fc3  nop
0x180004fc4  mov     ecx, 138D85Eh; unsigned int
0x180004fc9  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x180004fce  int     3; Trap to Debugger
0x180004fcf  mov     edx, 138D85Fh; unsigned int
0x180004fd4  mov     ecx, eax; int
0x180004fd6  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180004fdb  nop
0x180004fdc  jmp     short $+2
0x180004fde  nop
0x180004fdf  xor     edx, edx
0x180004fe1  mov     ecx, 1E3C3840h
0x180004fe6  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180004fec  nop
0x180004fed  mov     edx, 138D860h; unsigned int
0x180004ff2  mov     ecx, eax; int
0x180004ff4  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180004ff9  int     3; Trap to Debugger
```
