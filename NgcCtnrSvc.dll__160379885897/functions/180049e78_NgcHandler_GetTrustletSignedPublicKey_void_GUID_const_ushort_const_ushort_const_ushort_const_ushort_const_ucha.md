# NgcHandler::GetTrustletSignedPublicKey(void *,_GUID const &,ushort const *,ushort const *,ushort const *,ushort const *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180049e78`
- end: `0x18004a0f8`
- name: `?GetTrustletSignedPublicKey@NgcHandler@@QEAAJPEAXAEBU_GUID@@PEBG222PEBEKPEAPEAEPEAK@Z`
- size: `640`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *Src, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ca70`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x18000b490`
- `0x1800134a0`
- `0x180014350`
- `0x180018194`
- `0x180023278`
- `0x18002c640`
- `0x180049e78`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004a0c2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004a0c2`

## string_xrefs

- `0x180049f1f`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x180049f7a`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x18004a097`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcHandler::GetTrustletSignedPublicKey(
        __int64 (__fastcall **this)(__int128 *, __int64 **),
        void *a2,
        const struct _GUID *a3,
        unsigned __int16 *a4,
        unsigned __int16 *Src,
        unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const unsigned __int8 *a8,
        unsigned int a9,
        unsigned __int8 **a10,
        unsigned int *a11)
{
  int v14; // eax
  int v15; // ebx
  bool v16; // zf
  __int64 (__fastcall *v17)(__int128 *, __int64 **); // rbx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rax
  _QWORD *v21; // r8
  int v23; // [rsp+20h] [rbp-99h]
  _BYTE v24[8]; // [rsp+50h] [rbp-69h] BYREF
  __int64 *v25; // [rsp+58h] [rbp-61h] BYREF
  int v26; // [rsp+60h] [rbp-59h] BYREF
  int v27[2]; // [rsp+68h] [rbp-51h] BYREF
  __int128 v28; // [rsp+70h] [rbp-49h] BYREF
  unsigned __int8 **v29; // [rsp+80h] [rbp-39h]
  int v30[2]; // [rsp+88h] [rbp-31h]
  _QWORD v31[4]; // [rsp+90h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+3Fh]

  *(_QWORD *)v30 = a8;
  v29 = a10;
  *(_QWORD *)v27 = a11;
  v24[0] = 0;
  v14 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v24, (unsigned int)a2);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v25 = 0;
    v17 = *this;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    v28 = (__int128)*a3;
    v15 = v17(&v28, &v25);
    if ( v15 < 0 )
    {
      v18 = 4340;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
        (const char *)(unsigned int)v15,
        v23);
LABEL_22:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
      v16 = v24[0] == 0;
      goto LABEL_23;
    }
    v26 = 0;
    v28 = xmmword_18008F2D8;
    v15 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, int *))(*v25 + 88))(v25, &v28, &v26);
    if ( v15 < 0 )
    {
      v18 = 4344;
      goto LABEL_7;
    }
    if ( !v26 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v27[0] = -2147024809;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          (unsigned __int8 *)&word_1800AA006,
          0,
          0,
          (__int64)v27);
      }
      v15 = -2147024809;
      v18 = 4349;
      goto LABEL_7;
    }
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v31);
    v15 = NgcUtils::NgcContainerKeyName::BuildKeyNameString(Src, a6, a4, (__int64)v31);
    if ( v15 >= 0 )
    {
      v20 = *v25;
      v21 = v31;
      if ( v31[3] > 7u )
        v21 = (_QWORD *)v31[0];
      v28 = xmmword_18008F2D8;
      v23 = v30[0];
      v15 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _QWORD *, const unsigned __int16 *))(v20 + 336))(
              v25,
              &v28,
              v21,
              a7);
      if ( v15 >= 0 )
        goto LABEL_21;
      v19 = 4358;
    }
    else
    {
      v19 = 4354;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v15,
      v23);
LABEL_21:
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v31);
    goto LABEL_22;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v27[0] = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)byte_1800AA02D,
      0,
      0,
      (__int64)v27);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x10EF,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
    (const char *)(unsigned int)v15,
    v23);
  v16 = v24[0] == 0;
LABEL_23:
  if ( !v16 )
    CoUninitialize();
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180049e78  mov     [rsp-8+arg_8], rbx
0x180049e7d  push    rbp
0x180049e7e  push    rsi
0x180049e7f  push    rdi
0x180049e80  push    r12
0x180049e82  push    r13
0x180049e84  push    r14
0x180049e86  push    r15
0x180049e88  lea     rbp, [rsp-7]
0x180049e8d  sub     rsp, 0C0h
0x180049e94  mov     rax, cs:__security_cookie
0x180049e9b  xor     rax, rsp
0x180049e9e  mov     [rbp+37h+var_40], rax
0x180049ea2  mov     r14, r9
0x180049ea5  mov     rsi, r8
0x180049ea8  mov     rdi, rcx
0x180049eab  mov     r15, [rbp+37h+Src]
0x180049eaf  mov     r12, [rbp+37h+arg_28]
0x180049eb3  mov     r13, [rbp+37h+arg_30]
0x180049eb7  mov     rax, [rbp+37h+arg_38]
0x180049ebb  mov     qword ptr [rbp+37h+var_68], rax
0x180049ebf  mov     rax, [rbp+37h+arg_48]
0x180049ec6  mov     [rbp+37h+var_70], rax
0x180049eca  mov     rax, [rbp+37h+arg_50]
0x180049ed1  mov     qword ptr [rbp+37h+var_88], rax
0x180049ed5  mov     [rbp+37h+var_A0], 0
0x180049ed9  lea     rcx, [rbp+37h+var_A0]; this
0x180049edd  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x180049ee2  mov     ebx, eax
0x180049ee4  test    eax, eax
0x180049ee6  jns     short loc_180049F3A
0x180049ee8  mov     ecx, cs:dword_1800BE0B8
0x180049eee  cmp     ecx, 2
0x180049ef1  jbe     short loc_180049F18
0x180049ef3  mov     [rbp+37h+var_88], eax
0x180049ef6  lea     rax, [rbp+37h+var_88]
0x180049efa  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180049eff  xor     r9d, r9d
0x180049f02  xor     r8d, r8d
0x180049f05  lea     rdx, byte_1800AA02D
0x180049f0c  lea     rcx, dword_1800BE0B8
0x180049f13  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180049f18  mov     rcx, [rbp+3Fh]; this
0x180049f1c  mov     r9d, ebx; char *
0x180049f1f  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180049f26  mov     edx, 10EFh; void *
0x180049f2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049f30  nop
0x180049f31  cmp     [rbp+37h+var_A0], 0
0x180049f35  jmp     loc_18004A0C0
0x180049f3a  mov     [rbp+37h+var_98], 0
0x180049f42  mov     rbx, [rdi]
0x180049f45  lea     rcx, [rbp+37h+var_98]
0x180049f49  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049f4e  movups  xmm0, xmmword ptr [rsi]
0x180049f51  movdqu  [rbp+37h+var_80], xmm0
0x180049f56  lea     rdx, [rbp+37h+var_98]
0x180049f5a  lea     rcx, [rbp+37h+var_80]
0x180049f5e  mov     rax, rbx
0x180049f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f66  mov     ebx, eax
0x180049f68  xor     edi, edi
0x180049f6a  test    eax, eax
0x180049f6c  jns     short loc_180049F8B
0x180049f6e  mov     edx, 10F4h; void *
0x180049f73  mov     rcx, [rbp+3Fh]; this
0x180049f77  mov     r9d, ebx; char *
0x180049f7a  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180049f81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049f86  jmp     loc_18004A0B2
0x180049f8b  mov     [rbp+37h+var_90], edi
0x180049f8e  mov     rcx, [rbp+37h+var_98]
0x180049f92  movups  xmm0, cs:xmmword_18008F2D8
0x180049f99  movdqu  [rbp+37h+var_80], xmm0
0x180049f9e  mov     rax, [rcx]
0x180049fa1  lea     r8, [rbp+37h+var_90]
0x180049fa5  lea     rdx, [rbp+37h+var_80]
0x180049fa9  mov     rax, [rax+58h]
0x180049fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049fb2  mov     ebx, eax
0x180049fb4  test    eax, eax
0x180049fb6  jns     short loc_180049FBF
0x180049fb8  mov     edx, 10F8h
0x180049fbd  jmp     short loc_180049F73
0x180049fbf  cmp     [rbp+37h+var_90], edi
0x180049fc2  jnz     short loc_18004A007
0x180049fc4  mov     eax, cs:dword_1800BE0B8
0x180049fca  cmp     eax, 2
0x180049fcd  jbe     short loc_180049FF8
0x180049fcf  mov     [rbp+37h+var_88], 80070057h
0x180049fd6  lea     rax, [rbp+37h+var_88]
0x180049fda  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180049fdf  xor     r9d, r9d
0x180049fe2  xor     r8d, r8d
0x180049fe5  lea     rdx, word_1800AA006
0x180049fec  lea     rcx, dword_1800BE0B8
0x180049ff3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180049ff8  mov     ebx, 80070057h
0x180049ffd  mov     edx, 10FDh
0x18004a002  jmp     loc_180049F73
0x18004a007  lea     rcx, [rbp+37h+var_60]
0x18004a00b  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18004a010  nop
0x18004a011  lea     r9, [rbp+37h+var_60]
0x18004a015  mov     r8, r14
0x18004a018  mov     rdx, r12
0x18004a01b  mov     rcx, r15; Src
0x18004a01e  call    ?BuildKeyNameString@NgcContainerKeyName@NgcUtils@@YAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::NgcContainerKeyName::BuildKeyNameString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x18004a023  mov     ebx, eax
0x18004a025  test    eax, eax
0x18004a027  jns     short loc_18004A030
0x18004a029  mov     edx, 1102h
0x18004a02e  jmp     short loc_18004A094
0x18004a030  mov     rcx, [rbp+37h+var_98]
0x18004a034  mov     rax, [rcx]
0x18004a037  lea     r8, [rbp+37h+var_60]
0x18004a03b  cmp     [rbp+37h+var_48], 7
0x18004a040  cmova   r8, [rbp+37h+var_60]
0x18004a045  movups  xmm0, cs:xmmword_18008F2D8
0x18004a04c  movdqu  [rbp+37h+var_80], xmm0
0x18004a051  mov     rdx, qword ptr [rbp+37h+var_88]
0x18004a055  mov     [rsp+0F0h+var_B8], rdx
0x18004a05a  mov     rdx, [rbp+37h+var_70]
0x18004a05e  mov     [rsp+0F0h+var_C0], rdx
0x18004a063  mov     edx, [rbp+37h+arg_40]
0x18004a069  mov     [rsp+0F0h+var_C8], edx
0x18004a06d  mov     rdx, qword ptr [rbp+37h+var_68]
0x18004a071  mov     qword ptr [rsp+0F0h+var_D0], rdx; int
0x18004a076  mov     r9, r13
0x18004a079  lea     rdx, [rbp+37h+var_80]
0x18004a07d  mov     rax, [rax+150h]
0x18004a084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a089  mov     ebx, eax
0x18004a08b  test    eax, eax
0x18004a08d  jns     short loc_18004A0A8
0x18004a08f  mov     edx, 1106h; void *
0x18004a094  mov     r9d, ebx; char *
0x18004a097  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x18004a09e  mov     rcx, [rbp+3Fh]; this
0x18004a0a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a0a7  nop
0x18004a0a8  lea     rcx, [rbp+37h+var_60]
0x18004a0ac  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18004a0b1  nop
0x18004a0b2  lea     rcx, [rbp+37h+var_98]
0x18004a0b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a0bb  nop
0x18004a0bc  cmp     [rbp+37h+var_A0], dil
0x18004a0c0  jz      short loc_18004A0CE
0x18004a0c2  call    cs:__imp_CoUninitialize
0x18004a0c9  nop     dword ptr [rax+rax+00h]
0x18004a0ce  mov     eax, ebx
0x18004a0d0  mov     rcx, [rbp+37h+var_40]
0x18004a0d4  xor     rcx, rsp; StackCookie
0x18004a0d7  call    __security_check_cookie
0x18004a0dc  mov     rbx, [rsp+0F0h+arg_8]
0x18004a0e4  add     rsp, 0C0h
0x18004a0eb  pop     r15
0x18004a0ed  pop     r14
0x18004a0ef  pop     r13
0x18004a0f1  pop     r12
0x18004a0f3  pop     rdi
0x18004a0f4  pop     rsi
0x18004a0f5  pop     rbp
0x18004a0f6  retn
```
