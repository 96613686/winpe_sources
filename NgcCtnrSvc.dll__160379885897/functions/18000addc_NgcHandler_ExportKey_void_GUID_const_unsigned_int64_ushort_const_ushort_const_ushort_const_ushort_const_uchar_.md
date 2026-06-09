# NgcHandler::ExportKey(void *,_GUID const &,unsigned __int64,ushort const *,ushort const *,ushort const *,ushort const *,uchar * *,ulong *)

- ea: `0x18000addc`
- end: `0x18000b178`
- name: `?ExportKey@NgcHandler@@QEAAJPEAXAEBU_GUID@@_KPEBG333PEAPEAEPEAK@Z`
- size: `924`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, const struct _GUID *, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004c628`

## callees

- `0x18000a8e0`
- `0x18000addc`
- `0x18000b470`
- `0x18000b490`
- `0x18000c688`
- `0x18000c6b0`
- `0x18000c740`
- `0x18000c7e0`
- `0x180023278`
- `0x18002c640`
- `0x18002d500`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000ae44`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000ae44`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ae84`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000aeec`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b142`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ae84`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000aeec`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b142`

## string_xrefs

- `0x18000ae6d`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x18000aecf`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x18000af80`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x18000b039`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x18000b0ad`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall NgcHandler::ExportKey(
        __int64 (__fastcall **this)(__int128 *, __int64 *),
        void *a2,
        const struct _GUID *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8,
        unsigned __int8 **a9,
        unsigned int *a10)
{
  HRESULT v12; // esi
  bool v13; // di
  int v15; // ebx
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rax
  __int128 *v19; // r9
  __int64 v20; // rcx
  _BYTE *v21; // rdx
  __int64 v22; // rcx
  _BYTE *v23; // rdx
  __int64 v24; // rbx
  unsigned __int8 *v25; // rax
  unsigned __int8 *v26; // rsi
  __int64 v27; // rcx
  _BYTE *v28; // rdx
  __int64 v29; // rcx
  _BYTE *v30; // rdx
  int v31; // [rsp+20h] [rbp-B9h]
  int v32; // [rsp+20h] [rbp-B9h]
  __int64 *v33; // [rsp+40h] [rbp-99h] BYREF
  size_t size; // [rsp+48h] [rbp-91h]
  void *Src; // [rsp+50h] [rbp-89h] BYREF
  bool v36; // [rsp+58h] [rbp-81h]
  int v37; // [rsp+5Ch] [rbp-7Dh] BYREF
  __int64 v38; // [rsp+60h] [rbp-79h] BYREF
  unsigned __int8 *v39; // [rsp+68h] [rbp-71h]
  __int128 v40; // [rsp+70h] [rbp-69h] BYREF
  void **p_Src; // [rsp+80h] [rbp-59h]
  void *v42; // [rsp+88h] [rbp-51h]
  char v43; // [rsp+90h] [rbp-49h]
  void *v44; // [rsp+98h] [rbp-41h]
  int v45[2]; // [rsp+A0h] [rbp-39h]
  unsigned __int8 **v46; // [rsp+A8h] [rbp-31h]
  unsigned int *v47; // [rsp+B0h] [rbp-29h]
  __int128 v48; // [rsp+B8h] [rbp-21h] BYREF
  __int128 v49; // [rsp+C8h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+3Fh]

  v38 = a4;
  v44 = (void *)a7;
  *(_QWORD *)v45 = a8;
  v46 = a9;
  v47 = a10;
  v12 = CoInitializeEx(0, 0);
  v13 = v12 >= 0;
  v36 = v12 >= 0;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9DB,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v12,
      v31);
    return (unsigned int)v12;
  }
  v33 = 0;
  v40 = (__int128)*a3;
  v15 = (*this)(&v40, (__int64 *)&v33);
  if ( v15 < 0 )
  {
    v16 = 2528;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v15,
      v31);
LABEL_6:
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&v33);
LABEL_7:
    if ( v13 )
      CoUninitialize();
    return (unsigned int)v15;
  }
  v37 = 0;
  v40 = xmmword_18008F2D8;
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, int *))(*v33 + 88))(v33, &v40, &v37);
  if ( v15 < 0 )
  {
    v16 = 2534;
    goto LABEL_5;
  }
  if ( !v37 )
  {
    v15 = -2147024809;
    v16 = 2536;
    goto LABEL_5;
  }
  v48 = 0;
  v49 = 0;
  std::wstring::_Construct_empty(&v48);
  v17 = NgcUtils::NgcContainerKeyName::BuildKeyNameString(a6, v44, a5, (__int64)&v48);
  v15 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F0,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v17,
      v31);
LABEL_16:
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v48);
    goto LABEL_6;
  }
  Src = 0;
  LODWORD(size) = 0;
  v18 = *v33;
  p_Src = &Src;
  v42 = 0;
  v43 = 1;
  v19 = &v48;
  if ( *((_QWORD *)&v49 + 1) > 7u )
    v19 = (__int128 *)v48;
  v40 = xmmword_18008F2D8;
  v32 = v45[0];
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64, __int128 *))(v18 + 272))(v33, &v40, v38, v19);
  if ( v43 )
  {
    v20 = (__int64)p_Src;
    v21 = *p_Src;
    *p_Src = v42;
    if ( v21 )
      wil::cotaskmem_secure_deleter::operator()<unsigned char>(v20, v21);
  }
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9FA,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v15,
      v32);
    v23 = Src;
    Src = 0;
    if ( v23 )
      wil::cotaskmem_secure_deleter::operator()<unsigned char>(v22, v23);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v48);
    if ( v33 )
      (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
    goto LABEL_7;
  }
  v24 = (unsigned int)size;
  v25 = (unsigned __int8 *)MIDL_user_allocate((unsigned int)size);
  v26 = v25;
  v38 = v24;
  v39 = v25;
  if ( !v25 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA01,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)0x8007000ELL,
      v32);
    std::unique_ptr<unsigned char,rpcmem_secure_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_secure_delete<unsigned char>>(&v38);
    v28 = Src;
    Src = 0;
    if ( v28 )
      wil::cotaskmem_secure_deleter::operator()<unsigned char>(v27, v28);
    goto LABEL_16;
  }
  memcpy_0(v25, Src, (unsigned int)size);
  v39 = 0;
  *v46 = v26;
  *v47 = size;
  std::unique_ptr<unsigned char,rpcmem_secure_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_secure_delete<unsigned char>>(&v38);
  v30 = Src;
  Src = 0;
  if ( v30 )
    wil::cotaskmem_secure_deleter::operator()<unsigned char>(v29, v30);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v48);
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&v33);
  if ( v13 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18000addc  mov     [rsp-8+arg_8], rbx
0x18000ade1  push    rbp
0x18000ade2  push    rsi
0x18000ade3  push    rdi
0x18000ade4  push    r12
0x18000ade6  push    r13
0x18000ade8  push    r14
0x18000adea  push    r15
0x18000adec  lea     rbp, [rsp-7]
0x18000adf1  sub     rsp, 0E0h
0x18000adf8  mov     rax, cs:__security_cookie
0x18000adff  xor     rax, rsp
0x18000ae02  mov     [rbp+37h+var_38], rax
0x18000ae06  mov     [rbp+37h+var_B0], r9
0x18000ae0a  mov     r15, r8
0x18000ae0d  mov     r14, rcx
0x18000ae10  mov     r12, [rbp+37h+arg_20]
0x18000ae14  mov     r13, [rbp+37h+arg_28]
0x18000ae18  mov     rax, [rbp+37h+arg_30]
0x18000ae1c  mov     [rbp+37h+var_78], rax
0x18000ae20  mov     rax, [rbp+37h+arg_38]
0x18000ae24  mov     qword ptr [rbp+37h+var_70], rax
0x18000ae28  mov     rax, [rbp+37h+arg_40]
0x18000ae2f  mov     [rbp+37h+var_68], rax
0x18000ae33  mov     rax, [rbp+37h+arg_48]
0x18000ae3a  mov     [rbp+37h+var_60], rax
0x18000ae3e  xor     bl, bl
0x18000ae40  xor     edx, edx; dwCoInit
0x18000ae42  xor     ecx, ecx; pvReserved
0x18000ae44  call    cs:__imp_CoInitializeEx
0x18000ae4b  nop     dword ptr [rax+rax+00h]
0x18000ae50  mov     esi, eax
0x18000ae52  movzx   edi, bl
0x18000ae55  mov     eax, 1
0x18000ae5a  test    esi, esi
0x18000ae5c  cmovns  edi, eax
0x18000ae5f  mov     [rsp+110h+var_B8], dil
0x18000ae64  jns     short loc_18000AE97
0x18000ae66  mov     rcx, [rbp+3Fh]; this
0x18000ae6a  mov     r9d, esi; char *
0x18000ae6d  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x18000ae74  mov     edx, 9DBh; void *
0x18000ae79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae7e  nop
0x18000ae7f  test    dil, dil
0x18000ae82  jz      short loc_18000AE90
0x18000ae84  call    cs:__imp_CoUninitialize
0x18000ae8b  nop     dword ptr [rax+rax+00h]
0x18000ae90  mov     eax, esi
0x18000ae92  jmp     loc_18000B150
0x18000ae97  mov     [rsp+110h+var_D0], 0
0x18000aea0  movups  xmm0, xmmword ptr [r15]
0x18000aea4  movdqu  [rbp+37h+var_A0], xmm0
0x18000aea9  lea     rdx, [rsp+110h+var_D0]
0x18000aeae  lea     rcx, [rbp+37h+var_A0]
0x18000aeb2  mov     rax, [r14]
0x18000aeb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeba  mov     ebx, eax
0x18000aebc  xor     r14d, r14d
0x18000aebf  test    eax, eax
0x18000aec1  jns     short loc_18000AEFF
0x18000aec3  mov     edx, 9E0h; void *
0x18000aec8  mov     rcx, [rbp+3Fh]; this
0x18000aecc  mov     r9d, ebx; char *
0x18000aecf  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x18000aed6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aedb  nop
0x18000aedc  lea     rcx, [rsp+110h+var_D0]
0x18000aee1  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18000aee6  nop
0x18000aee7  test    dil, dil
0x18000aeea  jz      short loc_18000AEF8
0x18000aeec  call    cs:__imp_CoUninitialize
0x18000aef3  nop     dword ptr [rax+rax+00h]
0x18000aef8  mov     eax, ebx
0x18000aefa  jmp     loc_18000B150
0x18000aeff  mov     [rbp+37h+var_B4], r14d
0x18000af03  mov     rcx, [rsp+110h+var_D0]
0x18000af08  movups  xmm0, cs:xmmword_18008F2D8
0x18000af0f  movdqu  [rbp+37h+var_A0], xmm0
0x18000af14  mov     rax, [rcx]
0x18000af17  lea     r8, [rbp+37h+var_B4]
0x18000af1b  lea     rdx, [rbp+37h+var_A0]
0x18000af1f  mov     rax, [rax+58h]
0x18000af23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af28  mov     ebx, eax
0x18000af2a  test    eax, eax
0x18000af2c  jns     short loc_18000AF35
0x18000af2e  mov     edx, 9E6h
0x18000af33  jmp     short loc_18000AEC8
0x18000af35  cmp     [rbp+37h+var_B4], r14d
0x18000af39  jnz     short loc_18000AF47
0x18000af3b  mov     ebx, 80070057h
0x18000af40  mov     edx, 9E8h
0x18000af45  jmp     short loc_18000AEC8
0x18000af47  xorps   xmm0, xmm0
0x18000af4a  movups  [rbp+37h+var_58], xmm0
0x18000af4e  xorps   xmm1, xmm1
0x18000af51  movdqu  [rbp+37h+var_48], xmm1
0x18000af56  lea     rcx, [rbp+37h+var_58]
0x18000af5a  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000af5f  nop
0x18000af60  lea     r9, [rbp+37h+var_58]
0x18000af64  mov     r8, r12
0x18000af67  mov     rdx, [rbp+37h+var_78]
0x18000af6b  mov     rcx, r13; Src
0x18000af6e  call    ?BuildKeyNameString@NgcContainerKeyName@NgcUtils@@YAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::NgcContainerKeyName::BuildKeyNameString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x18000af73  mov     ebx, eax
0x18000af75  test    eax, eax
0x18000af77  jns     short loc_18000AFA0
0x18000af79  mov     rcx, [rbp+3Fh]; this
0x18000af7d  mov     r9d, eax; char *
0x18000af80  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x18000af87  mov     edx, 9F0h; void *
0x18000af8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000af91  nop
0x18000af92  lea     rcx, [rbp+37h+var_58]
0x18000af96  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18000af9b  jmp     loc_18000AEDC
0x18000afa0  mov     [rsp+110h+Src], r14
0x18000afa5  mov     dword ptr [rsp+110h+size], r14d
0x18000afaa  mov     rcx, [rsp+110h+var_D0]
0x18000afaf  mov     rax, [rcx]
0x18000afb2  lea     rdx, [rsp+110h+Src]
0x18000afb7  mov     [rbp+37h+var_90], rdx
0x18000afbb  mov     [rbp+37h+var_88], r14
0x18000afbf  mov     [rbp+37h+var_80], 1
0x18000afc3  lea     r9, [rbp+37h+var_58]
0x18000afc7  cmp     qword ptr [rbp+37h+var_48+8], 7
0x18000afcc  cmova   r9, qword ptr [rbp+37h+var_58]
0x18000afd1  movups  xmm0, cs:xmmword_18008F2D8
0x18000afd8  movdqu  [rbp+37h+var_A0], xmm0
0x18000afdd  lea     rdx, [rsp+110h+size]
0x18000afe2  mov     [rsp+110h+var_E0], rdx
0x18000afe7  lea     rdx, [rbp+37h+var_88]
0x18000afeb  mov     [rsp+110h+var_E8], rdx
0x18000aff0  mov     rdx, qword ptr [rbp+37h+var_70]
0x18000aff4  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x18000aff9  mov     r8, [rbp+37h+var_B0]
0x18000affd  lea     rdx, [rbp+37h+var_A0]
0x18000b001  mov     rax, [rax+110h]
0x18000b008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b00d  mov     ebx, eax
0x18000b00f  cmp     [rbp+37h+var_80], r14b
0x18000b013  jz      short loc_18000B02E
0x18000b015  mov     r8, [rbp+37h+var_88]
0x18000b019  mov     rcx, [rbp+37h+var_90]
0x18000b01d  mov     rdx, [rcx]
0x18000b020  mov     [rcx], r8
0x18000b023  test    rdx, rdx
0x18000b026  jz      short loc_18000B02E
0x18000b028  call    ??$?RE@cotaskmem_secure_deleter@wil@@QEBAXPEAE@Z; wil::cotaskmem_secure_deleter::operator()<uchar>(uchar *)
0x18000b02d  nop
0x18000b02e  test    ebx, ebx
0x18000b030  jns     short loc_18000B086
0x18000b032  mov     rcx, [rbp+3Fh]; this
0x18000b036  mov     r9d, ebx; char *
0x18000b039  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x18000b040  mov     edx, 9FAh; void *
0x18000b045  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b04a  nop
0x18000b04b  mov     rdx, [rsp+110h+Src]
0x18000b050  mov     [rsp+110h+Src], r14
0x18000b055  test    rdx, rdx
0x18000b058  jz      short loc_18000B060
0x18000b05a  call    ??$?RE@cotaskmem_secure_deleter@wil@@QEBAXPEAE@Z; wil::cotaskmem_secure_deleter::operator()<uchar>(uchar *)
0x18000b05f  nop
0x18000b060  lea     rcx, [rbp+37h+var_58]
0x18000b064  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18000b069  nop
0x18000b06a  mov     rcx, [rsp+110h+var_D0]
0x18000b06f  test    rcx, rcx
0x18000b072  jz      short loc_18000B081
0x18000b074  mov     rax, [rcx]
0x18000b077  mov     rax, [rax+10h]
0x18000b07b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b080  nop
0x18000b081  jmp     loc_18000AEE7
0x18000b086  mov     ebx, dword ptr [rsp+110h+size]
0x18000b08a  mov     ecx, ebx; size
0x18000b08c  call    MIDL_user_allocate
0x18000b091  mov     rsi, rax
0x18000b094  mov     [rbp+37h+var_B0], rbx
0x18000b098  mov     [rbp+37h+var_A8], rax
0x18000b09c  test    rax, rax
0x18000b09f  jnz     short loc_18000B0E2
0x18000b0a1  mov     rcx, [rbp+3Fh]; this
0x18000b0a5  mov     ebx, 8007000Eh
0x18000b0aa  mov     r9d, ebx; char *
0x18000b0ad  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x18000b0b4  mov     edx, 0A01h; void *
0x18000b0b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b0be  lea     rcx, [rbp+37h+var_B0]
0x18000b0c2  call    ??1?$unique_ptr@EU?$rpcmem_secure_delete@E@@@std@@QEAA@XZ; std::unique_ptr<uchar,rpcmem_secure_delete<uchar>>::~unique_ptr<uchar,rpcmem_secure_delete<uchar>>(void)
0x18000b0c7  nop
0x18000b0c8  mov     rdx, [rsp+110h+Src]
0x18000b0cd  mov     [rsp+110h+Src], r14
0x18000b0d2  test    rdx, rdx
0x18000b0d5  jz      short loc_18000B0DD
0x18000b0d7  call    ??$?RE@cotaskmem_secure_deleter@wil@@QEBAXPEAE@Z; wil::cotaskmem_secure_deleter::operator()<uchar>(uchar *)
0x18000b0dc  nop
0x18000b0dd  jmp     loc_18000AF92
0x18000b0e2  mov     r8d, dword ptr [rsp+110h+size]; Size
0x18000b0e7  mov     rdx, [rsp+110h+Src]; Src
0x18000b0ec  mov     rcx, rsi; void *
0x18000b0ef  call    memcpy_0
0x18000b0f4  mov     [rbp+37h+var_A8], r14
0x18000b0f8  mov     rax, [rbp+37h+var_68]
0x18000b0fc  mov     [rax], rsi
0x18000b0ff  mov     eax, dword ptr [rsp+110h+size]
0x18000b103  mov     rcx, [rbp+37h+var_60]
0x18000b107  mov     [rcx], eax
0x18000b109  lea     rcx, [rbp+37h+var_B0]
0x18000b10d  call    ??1?$unique_ptr@EU?$rpcmem_secure_delete@E@@@std@@QEAA@XZ; std::unique_ptr<uchar,rpcmem_secure_delete<uchar>>::~unique_ptr<uchar,rpcmem_secure_delete<uchar>>(void)
0x18000b112  nop
0x18000b113  mov     rdx, [rsp+110h+Src]
0x18000b118  mov     [rsp+110h+Src], r14
0x18000b11d  test    rdx, rdx
0x18000b120  jz      short loc_18000B128
0x18000b122  call    ??$?RE@cotaskmem_secure_deleter@wil@@QEBAXPEAE@Z; wil::cotaskmem_secure_deleter::operator()<uchar>(uchar *)
0x18000b127  nop
0x18000b128  lea     rcx, [rbp+37h+var_58]
0x18000b12c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18000b131  nop
0x18000b132  lea     rcx, [rsp+110h+var_D0]
0x18000b137  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18000b13c  nop
0x18000b13d  test    dil, dil
0x18000b140  jz      short loc_18000B14E
0x18000b142  call    cs:__imp_CoUninitialize
0x18000b149  nop     dword ptr [rax+rax+00h]
0x18000b14e  xor     eax, eax
0x18000b150  mov     rcx, [rbp+37h+var_38]
0x18000b154  xor     rcx, rsp; StackCookie
0x18000b157  call    __security_check_cookie
0x18000b15c  mov     rbx, [rsp+110h+arg_8]
0x18000b164  add     rsp, 0E0h
0x18000b16b  pop     r15
0x18000b16d  pop     r14
0x18000b16f  pop     r13
0x18000b171  pop     r12
0x18000b173  pop     rdi
0x18000b174  pop     rsi
0x18000b175  pop     rbp
0x18000b176  retn
```
