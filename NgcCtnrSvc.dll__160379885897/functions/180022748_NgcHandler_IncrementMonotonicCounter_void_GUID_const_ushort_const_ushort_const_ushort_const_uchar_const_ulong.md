# NgcHandler::IncrementMonotonicCounter(void *,_GUID const &,ushort const *,ushort const *,ushort const *,uchar const *,ulong)

- ea: `0x180022748`
- end: `0x180022954`
- name: `?IncrementMonotonicCounter@NgcHandler@@QEAAJPEAXAEBU_GUID@@PEBG22PEBEK@Z`
- size: `524`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *Src, const unsigned __int16 *, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004c578`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x18000b490`
- `0x1800134a0`
- `0x180014350`
- `0x180022748`
- `0x180023278`
- `0x18002c640`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800227b9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002291e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800227b9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002291e`

## string_xrefs

- `0x1800227a1`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x18002280f`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x18002289a`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcHandler::IncrementMonotonicCounter(
        __int64 (__fastcall **this)(__int128 *, __int64 **),
        void *a2,
        const struct _GUID *a3,
        unsigned __int16 *a4,
        unsigned __int16 *Src,
        unsigned __int16 *a6,
        const unsigned __int8 *a7,
        unsigned int a8)
{
  int v11; // eax
  int v12; // ebx
  bool v13; // zf
  __int64 (__fastcall *v15)(__int128 *, __int64 **); // rbx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rax
  _QWORD *v19; // r8
  int v20; // [rsp+20h] [rbp-69h]
  _BYTE v21[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 *v22; // [rsp+38h] [rbp-51h] BYREF
  _DWORD v23[4]; // [rsp+40h] [rbp-49h] BYREF
  __int128 v24; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v25[4]; // [rsp+60h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+3Fh]

  v21[0] = 0;
  v11 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v21, (unsigned int)a2);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x127B,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v11,
      v20);
    v13 = v21[0] == 0;
LABEL_3:
    if ( !v13 )
      CoUninitialize();
    return (unsigned int)v12;
  }
  v22 = 0;
  v15 = *this;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  v24 = (__int128)*a3;
  v12 = v15(&v24, &v22);
  if ( v12 < 0 )
  {
    v16 = 4736;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v12,
      v20);
LABEL_9:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    v13 = v21[0] == 0;
    goto LABEL_3;
  }
  v23[0] = 0;
  v24 = xmmword_18008F2D8;
  v12 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _DWORD *))(*v22 + 88))(v22, &v24, v23);
  if ( v12 < 0 )
  {
    v16 = 4739;
    goto LABEL_8;
  }
  if ( !v23[0] )
  {
    v12 = -2147024809;
    v16 = 4740;
    goto LABEL_8;
  }
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v25);
  v12 = NgcUtils::NgcContainerKeyName::BuildKeyNameString(Src, a6, a4, (__int64)v25);
  if ( v12 < 0 )
  {
    v17 = 4747;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v12,
      v20);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v25);
    goto LABEL_9;
  }
  v18 = *v22;
  v19 = v25;
  if ( v25[3] > 7u )
    v19 = (_QWORD *)v25[0];
  v24 = xmmword_18008F2D8;
  v20 = a8;
  v12 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _QWORD *, const unsigned __int8 *))(v18 + 376))(
          v22,
          &v24,
          v19,
          a7);
  if ( v12 < 0 )
  {
    v17 = 4753;
    goto LABEL_16;
  }
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  if ( v21[0] )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180022748  mov     [rsp-8+arg_8], rbx
0x18002274d  push    rbp
0x18002274e  push    rsi
0x18002274f  push    rdi
0x180022750  push    r12
0x180022752  push    r13
0x180022754  push    r14
0x180022756  push    r15
0x180022758  lea     rbp, [rsp-7]
0x18002275d  sub     rsp, 90h
0x180022764  mov     rax, cs:__security_cookie
0x18002276b  xor     rax, rsp
0x18002276e  mov     [rbp+37h+var_40], rax
0x180022772  mov     rdi, r9
0x180022775  mov     r12, r8
0x180022778  mov     r15, rcx
0x18002277b  mov     rsi, [rbp+37h+Src]
0x18002277f  mov     r14, [rbp+37h+arg_28]
0x180022783  mov     r13, [rbp+37h+arg_30]
0x180022787  mov     [rbp+37h+var_90], 0
0x18002278b  lea     rcx, [rbp+37h+var_90]; this
0x18002278f  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x180022794  mov     ebx, eax
0x180022796  test    eax, eax
0x180022798  jns     short loc_1800227CC
0x18002279a  mov     rcx, [rbp+3Fh]; this
0x18002279e  mov     r9d, eax; char *
0x1800227a1  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x1800227a8  mov     edx, 127Bh; void *
0x1800227ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800227b2  nop
0x1800227b3  cmp     [rbp+37h+var_90], 0
0x1800227b7  jz      short loc_1800227C5
0x1800227b9  call    cs:__imp_CoUninitialize
0x1800227c0  nop     dword ptr [rax+rax+00h]
0x1800227c5  mov     eax, ebx
0x1800227c7  jmp     loc_18002292C
0x1800227cc  mov     [rbp+37h+var_88], 0
0x1800227d4  mov     rbx, [r15]
0x1800227d7  lea     rcx, [rbp+37h+var_88]
0x1800227db  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800227e0  movups  xmm0, xmmword ptr [r12]
0x1800227e5  movdqu  [rbp+37h+var_70], xmm0
0x1800227ea  lea     rdx, [rbp+37h+var_88]
0x1800227ee  lea     rcx, [rbp+37h+var_70]
0x1800227f2  mov     rax, rbx
0x1800227f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227fa  mov     ebx, eax
0x1800227fc  xor     r15d, r15d
0x1800227ff  test    eax, eax
0x180022801  jns     short loc_18002282C
0x180022803  mov     edx, 1280h; void *
0x180022808  mov     rcx, [rbp+3Fh]; this
0x18002280c  mov     r9d, ebx; char *
0x18002280f  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180022816  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002281b  nop
0x18002281c  lea     rcx, [rbp+37h+var_88]
0x180022820  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022825  nop
0x180022826  cmp     [rbp+37h+var_90], r15b
0x18002282a  jmp     short loc_1800227B7
0x18002282c  mov     [rbp+37h+var_80], r15d
0x180022830  mov     rcx, [rbp+37h+var_88]
0x180022834  movups  xmm0, cs:xmmword_18008F2D8
0x18002283b  movdqu  [rbp+37h+var_70], xmm0
0x180022840  mov     rax, [rcx]
0x180022843  lea     r8, [rbp+37h+var_80]
0x180022847  lea     rdx, [rbp+37h+var_70]
0x18002284b  mov     rax, [rax+58h]
0x18002284f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022854  mov     ebx, eax
0x180022856  test    eax, eax
0x180022858  jns     short loc_180022861
0x18002285a  mov     edx, 1283h
0x18002285f  jmp     short loc_180022808
0x180022861  cmp     [rbp+37h+var_80], r15d
0x180022865  jnz     short loc_180022873
0x180022867  mov     ebx, 80070057h
0x18002286c  mov     edx, 1284h
0x180022871  jmp     short loc_180022808
0x180022873  lea     rcx, [rbp+37h+var_60]
0x180022877  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18002287c  nop
0x18002287d  lea     r9, [rbp+37h+var_60]
0x180022881  mov     r8, rdi
0x180022884  mov     rdx, r14
0x180022887  mov     rcx, rsi; Src
0x18002288a  call    ?BuildKeyNameString@NgcContainerKeyName@NgcUtils@@YAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::NgcContainerKeyName::BuildKeyNameString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x18002288f  mov     ebx, eax
0x180022891  test    eax, eax
0x180022893  jns     short loc_1800228BC
0x180022895  mov     edx, 128Bh; void *
0x18002289a  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x1800228a1  mov     r9d, ebx; char *
0x1800228a4  mov     rcx, [rbp+3Fh]; this
0x1800228a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800228ad  nop
0x1800228ae  lea     rcx, [rbp+37h+var_60]
0x1800228b2  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x1800228b7  jmp     loc_18002281C
0x1800228bc  mov     rcx, [rbp+37h+var_88]
0x1800228c0  mov     rax, [rcx]
0x1800228c3  lea     r8, [rbp+37h+var_60]
0x1800228c7  cmp     [rbp+37h+var_48], 7
0x1800228cc  cmova   r8, [rbp+37h+var_60]
0x1800228d1  movups  xmm0, cs:xmmword_18008F2D8
0x1800228d8  movdqu  [rbp+37h+var_70], xmm0
0x1800228dd  mov     edx, [rbp+37h+arg_38]
0x1800228e0  mov     [rsp+0C0h+var_A0], edx
0x1800228e4  mov     r9, r13
0x1800228e7  lea     rdx, [rbp+37h+var_70]
0x1800228eb  mov     rax, [rax+178h]
0x1800228f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228f7  mov     ebx, eax
0x1800228f9  test    eax, eax
0x1800228fb  jns     short loc_180022904
0x1800228fd  mov     edx, 1291h
0x180022902  jmp     short loc_18002289A
0x180022904  lea     rcx, [rbp+37h+var_60]
0x180022908  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18002290d  nop
0x18002290e  lea     rcx, [rbp+37h+var_88]
0x180022912  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022917  nop
0x180022918  cmp     [rbp+37h+var_90], r15b
0x18002291c  jz      short loc_18002292A
0x18002291e  call    cs:__imp_CoUninitialize
0x180022925  nop     dword ptr [rax+rax+00h]
0x18002292a  xor     eax, eax
0x18002292c  mov     rcx, [rbp+37h+var_40]
0x180022930  xor     rcx, rsp; StackCookie
0x180022933  call    __security_check_cookie
0x180022938  mov     rbx, [rsp+0C0h+arg_8]
0x180022940  add     rsp, 90h
0x180022947  pop     r15
0x180022949  pop     r14
0x18002294b  pop     r13
0x18002294d  pop     r12
0x18002294f  pop     rdi
0x180022950  pop     rsi
0x180022951  pop     rbp
0x180022952  retn
```
