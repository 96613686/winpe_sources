# NgcHandler::QueryMonotonicCounter(void *,_GUID const &,ushort const *,ushort const *,ushort const *,uchar * *,ulong *)

- ea: `0x180022530`
- end: `0x180022741`
- name: `?QueryMonotonicCounter@NgcHandler@@QEAAJPEAXAEBU_GUID@@PEBG22PEAPEAEPEAK@Z`
- size: `529`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *Src, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004c778`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x18000b490`
- `0x1800134a0`
- `0x180014350`
- `0x180022530`
- `0x180023278`
- `0x18002c640`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800225a9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002270b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800225a9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002270b`

## string_xrefs

- `0x180022591`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x1800225fc`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x180022685`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcHandler::QueryMonotonicCounter(
        __int64 (__fastcall **this)(__int128 *, __int64 **),
        void *a2,
        const struct _GUID *a3,
        unsigned __int16 *a4,
        unsigned __int16 *Src,
        unsigned __int16 *a6,
        unsigned __int8 **a7,
        unsigned int *a8)
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
  unsigned int *v25; // [rsp+60h] [rbp-29h]
  _QWORD v26[4]; // [rsp+68h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+3Fh]

  v25 = a8;
  v21[0] = 0;
  v11 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v21, (unsigned int)a2);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1252,
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
    v16 = 4695;
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
    v16 = 4698;
    goto LABEL_8;
  }
  if ( !v23[0] )
  {
    v12 = -2147024809;
    v16 = 4699;
    goto LABEL_8;
  }
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v26);
  v12 = NgcUtils::NgcContainerKeyName::BuildKeyNameString(Src, a6, a4, (__int64)v26);
  if ( v12 < 0 )
  {
    v17 = 4706;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v12,
      v20);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v26);
    goto LABEL_9;
  }
  v18 = *v22;
  v19 = v26;
  if ( v26[3] > 7u )
    v19 = (_QWORD *)v26[0];
  v24 = xmmword_18008F2D8;
  v20 = (int)v25;
  v12 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _QWORD *, unsigned __int8 **))(v18 + 368))(v22, &v24, v19, a7);
  if ( v12 < 0 )
  {
    v17 = 4712;
    goto LABEL_16;
  }
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v26);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  if ( v21[0] )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180022530  mov     [rsp-8+arg_8], rbx
0x180022535  push    rbp
0x180022536  push    rsi
0x180022537  push    rdi
0x180022538  push    r12
0x18002253a  push    r13
0x18002253c  push    r14
0x18002253e  push    r15
0x180022540  lea     rbp, [rsp-7]
0x180022545  sub     rsp, 90h
0x18002254c  mov     rax, cs:__security_cookie
0x180022553  xor     rax, rsp
0x180022556  mov     [rbp+37h+var_38], rax
0x18002255a  mov     r14, r9
0x18002255d  mov     rsi, r8
0x180022560  mov     rdi, rcx
0x180022563  mov     r15, [rbp+37h+Src]
0x180022567  mov     r12, [rbp+37h+arg_28]
0x18002256b  mov     r13, [rbp+37h+arg_30]
0x18002256f  mov     rax, [rbp+37h+arg_38]
0x180022573  mov     [rbp+37h+var_60], rax
0x180022577  mov     [rbp+37h+var_90], 0
0x18002257b  lea     rcx, [rbp+37h+var_90]; this
0x18002257f  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x180022584  mov     ebx, eax
0x180022586  test    eax, eax
0x180022588  jns     short loc_1800225BC
0x18002258a  mov     rcx, [rbp+3Fh]; this
0x18002258e  mov     r9d, eax; char *
0x180022591  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180022598  mov     edx, 1252h; void *
0x18002259d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800225a2  nop
0x1800225a3  cmp     [rbp+37h+var_90], 0
0x1800225a7  jz      short loc_1800225B5
0x1800225a9  call    cs:__imp_CoUninitialize
0x1800225b0  nop     dword ptr [rax+rax+00h]
0x1800225b5  mov     eax, ebx
0x1800225b7  jmp     loc_180022719
0x1800225bc  mov     [rbp+37h+var_88], 0
0x1800225c4  mov     rbx, [rdi]
0x1800225c7  lea     rcx, [rbp+37h+var_88]
0x1800225cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800225d0  movups  xmm0, xmmword ptr [rsi]
0x1800225d3  movdqu  [rbp+37h+var_70], xmm0
0x1800225d8  lea     rdx, [rbp+37h+var_88]
0x1800225dc  lea     rcx, [rbp+37h+var_70]
0x1800225e0  mov     rax, rbx
0x1800225e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225e8  mov     ebx, eax
0x1800225ea  xor     edi, edi
0x1800225ec  test    eax, eax
0x1800225ee  jns     short loc_180022619
0x1800225f0  mov     edx, 1257h; void *
0x1800225f5  mov     rcx, [rbp+3Fh]; this
0x1800225f9  mov     r9d, ebx; char *
0x1800225fc  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180022603  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022608  nop
0x180022609  lea     rcx, [rbp+37h+var_88]
0x18002260d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022612  nop
0x180022613  cmp     [rbp+37h+var_90], dil
0x180022617  jmp     short loc_1800225A7
0x180022619  mov     [rbp+37h+var_80], edi
0x18002261c  mov     rcx, [rbp+37h+var_88]
0x180022620  movups  xmm0, cs:xmmword_18008F2D8
0x180022627  movdqu  [rbp+37h+var_70], xmm0
0x18002262c  mov     rax, [rcx]
0x18002262f  lea     r8, [rbp+37h+var_80]
0x180022633  lea     rdx, [rbp+37h+var_70]
0x180022637  mov     rax, [rax+58h]
0x18002263b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022640  mov     ebx, eax
0x180022642  test    eax, eax
0x180022644  jns     short loc_18002264D
0x180022646  mov     edx, 125Ah
0x18002264b  jmp     short loc_1800225F5
0x18002264d  cmp     [rbp+37h+var_80], edi
0x180022650  jnz     short loc_18002265E
0x180022652  mov     ebx, 80070057h
0x180022657  mov     edx, 125Bh
0x18002265c  jmp     short loc_1800225F5
0x18002265e  lea     rcx, [rbp+37h+var_58]
0x180022662  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180022667  nop
0x180022668  lea     r9, [rbp+37h+var_58]
0x18002266c  mov     r8, r14
0x18002266f  mov     rdx, r12
0x180022672  mov     rcx, r15; Src
0x180022675  call    ?BuildKeyNameString@NgcContainerKeyName@NgcUtils@@YAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::NgcContainerKeyName::BuildKeyNameString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x18002267a  mov     ebx, eax
0x18002267c  test    eax, eax
0x18002267e  jns     short loc_1800226A7
0x180022680  mov     edx, 1262h; void *
0x180022685  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x18002268c  mov     r9d, ebx; char *
0x18002268f  mov     rcx, [rbp+3Fh]; this
0x180022693  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022698  nop
0x180022699  lea     rcx, [rbp+37h+var_58]
0x18002269d  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x1800226a2  jmp     loc_180022609
0x1800226a7  mov     rcx, [rbp+37h+var_88]
0x1800226ab  mov     rax, [rcx]
0x1800226ae  lea     r8, [rbp+37h+var_58]
0x1800226b2  cmp     [rbp+37h+var_40], 7
0x1800226b7  cmova   r8, [rbp+37h+var_58]
0x1800226bc  movups  xmm0, cs:xmmword_18008F2D8
0x1800226c3  movdqu  [rbp+37h+var_70], xmm0
0x1800226c8  mov     rdx, [rbp+37h+var_60]
0x1800226cc  mov     qword ptr [rsp+0C0h+var_A0], rdx
0x1800226d1  mov     r9, r13
0x1800226d4  lea     rdx, [rbp+37h+var_70]
0x1800226d8  mov     rax, [rax+170h]
0x1800226df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226e4  mov     ebx, eax
0x1800226e6  test    eax, eax
0x1800226e8  jns     short loc_1800226F1
0x1800226ea  mov     edx, 1268h
0x1800226ef  jmp     short loc_180022685
0x1800226f1  lea     rcx, [rbp+37h+var_58]
0x1800226f5  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x1800226fa  nop
0x1800226fb  lea     rcx, [rbp+37h+var_88]
0x1800226ff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022704  nop
0x180022705  cmp     [rbp+37h+var_90], dil
0x180022709  jz      short loc_180022717
0x18002270b  call    cs:__imp_CoUninitialize
0x180022712  nop     dword ptr [rax+rax+00h]
0x180022717  xor     eax, eax
0x180022719  mov     rcx, [rbp+37h+var_38]
0x18002271d  xor     rcx, rsp; StackCookie
0x180022720  call    __security_check_cookie
0x180022725  mov     rbx, [rsp+0C0h+arg_8]
0x18002272d  add     rsp, 90h
0x180022734  pop     r15
0x180022736  pop     r14
0x180022738  pop     r13
0x18002273a  pop     r12
0x18002273c  pop     rdi
0x18002273d  pop     rsi
0x18002273e  pop     rbp
0x18002273f  retn
```
