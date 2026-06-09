# CRdpIdAdapter::ProcessConfigFileIoChannel(_RDPIDD_OPCODE_CONFIG_FILEIO_CHANNEL * const,RDPIDD_FILEOBJECT_CONTEXT *)

- ea: `0x18001818c`
- end: `0x1800184ae`
- name: `?ProcessConfigFileIoChannel@CRdpIdAdapter@@AEAAXQEAU_RDPIDD_OPCODE_CONFIG_FILEIO_CHANNEL@@PEAURDPIDD_FILEOBJECT_CONTEXT@@@Z`
- size: `802`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this, struct _RDPIDD_OPCODE_CONFIG_FILEIO_CHANNEL *const, struct RDPIDD_FILEOBJECT_CONTEXT *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800185bc`

## callees

- `0x180006f60`
- `0x180006f84`
- `0x18000ead8`
- `0x18000eb00`
- `0x180013520`
- `0x180013854`
- `0x180013ad0`
- `0x180013b38`
- `0x180013db8`
- `0x18001818c`
- `0x18001dd70`
- `0x18001ddf4`
- `0x180021750`
- `0x18003f010`

## string_xrefs

- `0x18001821f`: `FileIo channel has already been created`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CRdpIdAdapter::ProcessConfigFileIoChannel(
        CRdpIdAdapter *this,
        struct _RDPIDD_OPCODE_CONFIG_FILEIO_CHANNEL *const a2,
        struct RDPIDD_FILEOBJECT_CONTEXT *a3)
{
  char *v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdi
  _QWORD *v11; // rbx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, char *, char *, _QWORD, _QWORD *, char *); // rsi
  unsigned int v14; // eax
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, char *, _QWORD *, char *); // rdi
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rdi
  char *v20; // [rsp+28h] [rbp-51h]
  char *v21; // [rsp+28h] [rbp-51h]
  const char *v22; // [rsp+30h] [rbp-49h]
  const char *v23; // [rsp+30h] [rbp-49h]
  const char *v24; // [rsp+30h] [rbp-49h]
  char v25[8]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v26; // [rsp+48h] [rbp-31h] BYREF
  _QWORD *v27; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v28[2]; // [rsp+58h] [rbp-21h] BYREF
  __int128 v29; // [rsp+68h] [rbp-11h] BYREF
  __int128 v30; // [rsp+78h] [rbp-1h]
  __int64 v31; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v6 = (char *)this + 560;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xDD3,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)0x80070057LL,
    *((_QWORD *)this + 70) == 0,
    (bool)"Encoding processor has not been started",
    v22);
  v7 = -*(_QWORD *)a3;
  if ( !*(_QWORD *)a3 )
    v7 = -*((_QWORD *)a3 + 1);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xDDC,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)0x80070057LL,
    v7 != 0,
    (bool)"FileIo channel has already been created",
    v23);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xDE3,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)0x80070057LL,
    (unsigned int)(*((_DWORD *)a2 + 7) - 1) > 1,
    (bool)"Invalid FileIo mode is specified",
    v24);
  v29 = *(_OWORD *)((char *)a2 + 12);
  v30 = *(_OWORD *)((char *)a2 + 44);
  v31 = *((unsigned int *)a2 + 15);
  v27 = operator new(0x1B8u);
  v8 = CFileIoChannel::CFileIoChannel(
         v27,
         *((_QWORD *)this + 57),
         &v29,
         *((unsigned int *)a2 + 7),
         *((_DWORD *)a2 + 9),
         *((_DWORD *)a2 + 10),
         *((_DWORD *)a2 + 8));
  wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(&v27, v8);
  v9 = std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Try_emplace<FileIoChannelId const &,>(
         (char *)this + 280,
         v28,
         &v29);
  v10 = *(_QWORD *)(*(_QWORD *)v9 + 56LL);
  v11 = v27;
  *(_QWORD *)(*(_QWORD *)v9 + 56LL) = v27;
  if ( v11 )
    (*(void (__fastcall **)(_QWORD *))(*v11 + 8LL))(v11);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  *(_QWORD *)v25 = 0;
  v26 = 0;
  wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>::try_query_to<Rdp::Avenc::IFileIoControlEvents1>(
    v6,
    &v26);
  v12 = v26;
  if ( v26 )
  {
    v13 = *(__int64 (__fastcall **)(__int64, char *, char *, _QWORD, _QWORD *, char *))(*(_QWORD *)v26 + 24LL);
    wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset(v25);
    v14 = v13(v12, (char *)a2 + 12, (char *)a2 + 44, *((unsigned int *)a2 + 15), v11, v25);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xE08,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)v14,
      (int)"Failed to offer channel",
      v21);
  }
  else
  {
    v28[0] = 0;
    wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::IFileIoControlEvents>(
      v6,
      v28);
    v15 = v28[0];
    v16 = *(__int64 (__fastcall **)(__int64, char *, _QWORD *, char *))(*(_QWORD *)v28[0] + 24LL);
    wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset(v25);
    v17 = v16(v15, (char *)a2 + 12, v11, v25);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xE14,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)v17,
      (int)"Failed to offer channel",
      v20);
    wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(v28);
  }
  v18 = *(_QWORD *)v25;
  v19 = v11[53];
  v11[53] = *(_QWORD *)v25;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  *(_OWORD *)a3 = v29;
  *((_OWORD *)a3 + 1) = v30;
  *((_QWORD *)a3 + 4) = v31;
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v26);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(v25);
  wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(&v27);
}

```

## disassembly

```asm
0x18001818c  mov     [rsp-8+arg_18], rbx
0x180018191  push    rbp
0x180018192  push    rsi
0x180018193  push    rdi
0x180018194  push    r12
0x180018196  push    r13
0x180018198  push    r14
0x18001819a  push    r15
0x18001819c  lea     rbp, [rsp-27h]
0x1800181a1  sub     rsp, 0A0h
0x1800181a8  mov     rax, cs:__security_cookie
0x1800181af  xor     rax, rsp
0x1800181b2  mov     [rbp+57h+var_40], rax
0x1800181b6  mov     r14, r8
0x1800181b9  mov     r15, rdx
0x1800181bc  mov     rbx, rcx
0x1800181bf  lea     rsi, [rcx+230h]
0x1800181c6  cmp     qword ptr [rsi], 0
0x1800181ca  setz    al
0x1800181cd  mov     rcx, [rbp+5Fh]; this
0x1800181d1  lea     rdx, aEncodingProces; "Encoding processor has not been started"
0x1800181d8  mov     [rsp+0D0h+var_A8], rdx; bool
0x1800181dd  mov     [rsp+0D0h+var_B0], al; char
0x1800181e1  mov     r12d, 80070057h
0x1800181e7  mov     r9d, r12d; char *
0x1800181ea  lea     rdi, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800181f1  mov     r8, rdi; unsigned int
0x1800181f4  mov     edx, 0DD3h; void *
0x1800181f9  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800181fe  mov     rax, qword ptr cs:xmmword_180046C80
0x180018205  sub     rax, [r14]
0x180018208  jnz     short loc_180018215
0x18001820a  mov     rax, qword ptr cs:xmmword_180046C80+8
0x180018211  sub     rax, [r14+8]
0x180018215  test    rax, rax
0x180018218  setnz   al
0x18001821b  mov     rcx, [rbp+5Fh]; this
0x18001821f  lea     rdx, aFileioChannelH_0; "FileIo channel has already been created"
0x180018226  mov     [rsp+0D0h+var_A8], rdx; bool
0x18001822b  mov     [rsp+0D0h+var_B0], al; char
0x18001822f  mov     r9d, r12d; char *
0x180018232  mov     r8, rdi; unsigned int
0x180018235  mov     edx, 0DDCh; void *
0x18001823a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001823f  mov     eax, [r15+1Ch]
0x180018243  dec     eax
0x180018245  cmp     eax, 1
0x180018248  setnbe  al
0x18001824b  mov     rcx, [rbp+5Fh]; this
0x18001824f  lea     rdx, aInvalidFileioM; "Invalid FileIo mode is specified"
0x180018256  mov     [rsp+0D0h+var_A8], rdx; bool
0x18001825b  mov     [rsp+0D0h+var_B0], al; char
0x18001825f  mov     r9d, r12d; char *
0x180018262  mov     r8, rdi; unsigned int
0x180018265  mov     edx, 0DE3h; void *
0x18001826a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001826f  lea     r12, [r15+0Ch]
0x180018273  movups  xmm0, xmmword ptr [r12]
0x180018278  movdqu  [rbp+57h+var_68], xmm0
0x18001827d  movups  xmm1, xmmword ptr [r15+2Ch]
0x180018282  movdqu  [rbp+57h+var_58], xmm1
0x180018287  mov     eax, [r15+3Ch]
0x18001828b  mov     dword ptr [rbp+57h+var_48], eax
0x18001828e  mov     dword ptr [rbp+57h+var_48+4], 0
0x180018295  mov     ecx, 1B8h; Size
0x18001829a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001829f  mov     [rbp+57h+var_80], rax
0x1800182a3  mov     ecx, [r15+20h]
0x1800182a7  mov     [rsp+0D0h+var_A0], ecx
0x1800182ab  mov     ecx, [r15+28h]
0x1800182af  mov     dword ptr [rsp+0D0h+var_A8], ecx; char *
0x1800182b3  mov     ecx, [r15+24h]
0x1800182b7  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x1800182bb  mov     r9d, [r15+1Ch]
0x1800182bf  lea     r8, [rbp+57h+var_68]
0x1800182c3  mov     rdx, [rbx+1C8h]
0x1800182ca  mov     rcx, rax
0x1800182cd  call    ??0CFileIoChannel@@QEAA@PEAUWDFDEVICE__@@AEBUFileIoChannelId@@W4RDPIDD_FILEIO_MODE@@III@Z; CFileIoChannel::CFileIoChannel(WDFDEVICE__ *,FileIoChannelId const &,RDPIDD_FILEIO_MODE,uint,uint,uint)
0x1800182d2  nop
0x1800182d3  mov     rdx, rax
0x1800182d6  lea     rcx, [rbp+57h+var_80]
0x1800182da  call    ??0?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCIoPacket@@@Z; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(CIoPacket *)
0x1800182df  nop
0x1800182e0  lea     rcx, [rbx+118h]
0x1800182e7  lea     r8, [rbp+57h+var_68]
0x1800182eb  lea     rdx, [rbp+57h+var_78]
0x1800182ef  call    ??$_Try_emplace@AEBUFileIoChannelId@@$$V@?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBUFileIoChannelId@@@Z; std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Try_emplace<FileIoChannelId const &,>(FileIoChannelId const &)
0x1800182f4  mov     rcx, [rax]
0x1800182f7  mov     rdi, [rcx+38h]
0x1800182fb  mov     rbx, [rbp+57h+var_80]
0x1800182ff  mov     [rcx+38h], rbx
0x180018303  test    rbx, rbx
0x180018306  jz      short loc_180018317
0x180018308  mov     rax, [rbx]
0x18001830b  mov     rcx, rbx
0x18001830e  mov     rax, [rax+8]
0x180018312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018317  test    rdi, rdi
0x18001831a  jz      short loc_18001832B
0x18001831c  mov     rax, [rdi]
0x18001831f  mov     rcx, rdi
0x180018322  mov     rax, [rax+10h]
0x180018326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001832b  mov     qword ptr [rbp+57h+var_90], 0
0x180018333  mov     [rbp+57h+var_88], 0
0x18001833b  lea     rdx, [rbp+57h+var_88]
0x18001833f  mov     rcx, rsi
0x180018342  call    ??$try_query_to@UIFileIoControlEvents1@Avenc@Rdp@@@?$com_ptr_t@UIEncodingProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEBA_NPEAPEAUIFileIoControlEvents1@Avenc@Rdp@@@Z; wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>::try_query_to<Rdp::Avenc::IFileIoControlEvents1>(Rdp::Avenc::IFileIoControlEvents1 * *)
0x180018347  mov     rdi, [rbp+57h+var_88]
0x18001834b  test    rdi, rdi
0x18001834e  jz      short loc_1800183AA
0x180018350  mov     rax, [rdi]
0x180018353  mov     rsi, [rax+18h]
0x180018357  lea     rcx, [rbp+57h+var_90]
0x18001835b  call    ?reset@?$com_ptr_t@UIFileIoChannelEvents@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset(void)
0x180018360  lea     rax, [rbp+57h+var_90]
0x180018364  mov     [rsp+0D0h+var_A8], rax; char *
0x180018369  mov     qword ptr [rsp+0D0h+var_B0], rbx
0x18001836e  mov     r9d, [r15+3Ch]
0x180018372  lea     r8, [r15+2Ch]
0x180018376  mov     rdx, r12
0x180018379  mov     rcx, rdi
0x18001837c  mov     rax, rsi
0x18001837f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018384  mov     rcx, [rbp+5Fh]; this
0x180018388  lea     rdx, aFailedToOfferC; "Failed to offer channel"
0x18001838f  mov     qword ptr [rsp+0D0h+var_B0], rdx; int
0x180018394  mov     r9d, eax; char *
0x180018397  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001839e  mov     edx, 0E08h; void *
0x1800183a3  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800183a8  jmp     short loc_180018415
0x1800183aa  mov     [rbp+57h+var_78], 0
0x1800183b2  lea     rdx, [rbp+57h+var_78]
0x1800183b6  mov     rcx, rsi
0x1800183b9  call    ??$copy_to@UIFileIoControlEvents@Avenc@Rdp@@@?$com_ptr_t@UIEncodingProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIFileIoControlEvents@Avenc@Rdp@@@Z; wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::IFileIoControlEvents>(Rdp::Avenc::IFileIoControlEvents * *)
0x1800183be  mov     rsi, [rbp+57h+var_78]
0x1800183c2  mov     rax, [rsi]
0x1800183c5  mov     rdi, [rax+18h]
0x1800183c9  lea     rcx, [rbp+57h+var_90]
0x1800183cd  call    ?reset@?$com_ptr_t@UIFileIoChannelEvents@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset(void)
0x1800183d2  lea     r9, [rbp+57h+var_90]
0x1800183d6  mov     r8, rbx
0x1800183d9  mov     rdx, r12
0x1800183dc  mov     rcx, rsi
0x1800183df  mov     rax, rdi
0x1800183e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183e7  mov     rcx, [rbp+5Fh]; this
0x1800183eb  lea     rdx, aFailedToOfferC; "Failed to offer channel"
0x1800183f2  mov     qword ptr [rsp+0D0h+var_B0], rdx; int
0x1800183f7  mov     r9d, eax; char *
0x1800183fa  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180018401  mov     edx, 0E14h; void *
0x180018406  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001840b  nop
0x18001840c  lea     rcx, [rbp+57h+var_78]
0x180018410  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x180018415  mov     rcx, qword ptr [rbp+57h+var_90]
0x180018419  mov     rdi, [rbx+1A8h]
0x180018420  mov     [rbx+1A8h], rcx
0x180018427  test    rcx, rcx
0x18001842a  jz      short loc_180018438
0x18001842c  mov     rax, [rcx]
0x18001842f  mov     rax, [rax+8]
0x180018433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018438  test    rdi, rdi
0x18001843b  jz      short loc_18001844D
0x18001843d  mov     rax, [rdi]
0x180018440  mov     rcx, rdi
0x180018443  mov     rax, [rax+10h]
0x180018447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001844c  nop
0x18001844d  movups  xmm0, [rbp+57h+var_68]
0x180018451  movups  xmmword ptr [r14], xmm0
0x180018455  movups  xmm1, [rbp+57h+var_58]
0x180018459  movups  xmmword ptr [r14+10h], xmm1
0x18001845e  movsd   xmm0, [rbp+57h+var_48]
0x180018463  movsd   qword ptr [r14+20h], xmm0
0x180018469  lea     rcx, [rbp+57h+var_88]
0x18001846d  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x180018472  nop
0x180018473  lea     rcx, [rbp+57h+var_90]
0x180018477  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18001847c  nop
0x18001847d  lea     rcx, [rbp+57h+var_80]
0x180018481  call    ??1?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(void)
0x180018486  mov     rcx, [rbp+57h+var_40]
0x18001848a  xor     rcx, rsp; StackCookie
0x18001848d  call    __security_check_cookie
0x180018492  mov     rbx, [rsp+0D0h+arg_18]
0x18001849a  add     rsp, 0A0h
0x1800184a1  pop     r15
0x1800184a3  pop     r14
0x1800184a5  pop     r13
0x1800184a7  pop     r12
0x1800184a9  pop     rdi
0x1800184aa  pop     rsi
0x1800184ab  pop     rbp
0x1800184ac  retn
```
