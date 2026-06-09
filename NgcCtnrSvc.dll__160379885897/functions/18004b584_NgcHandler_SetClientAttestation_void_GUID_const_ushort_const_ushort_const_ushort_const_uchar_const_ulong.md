# NgcHandler::SetClientAttestation(void *,_GUID const &,ushort const *,ushort const *,ushort const *,uchar const *,ulong)

- ea: `0x18004b584`
- end: `0x18004b7cd`
- name: `?SetClientAttestation@NgcHandler@@QEAAJPEAXAEBU_GUID@@PEBG22PEBEK@Z`
- size: `585`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *Src, const unsigned __int16 *, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004c0cc`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x18000b490`
- `0x1800134a0`
- `0x180014350`
- `0x180018194`
- `0x180023278`
- `0x18002c640`
- `0x18004b584`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004b797`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004b797`

## string_xrefs

- `0x18004b60d`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x18004b66b`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x18004b76c`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcHandler::SetClientAttestation(
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
  __int64 (__fastcall *v14)(__int128 *, __int64 **); // rbx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rax
  _QWORD *v18; // r8
  int v20; // [rsp+20h] [rbp-69h]
  _BYTE v21[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 *v22; // [rsp+38h] [rbp-51h] BYREF
  int v23; // [rsp+40h] [rbp-49h] BYREF
  _DWORD v24[3]; // [rsp+44h] [rbp-45h] BYREF
  __int128 v25; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v26[4]; // [rsp+60h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+3Fh]

  v21[0] = 0;
  v11 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v21, (unsigned int)a2);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v22 = 0;
    v14 = *this;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    v25 = (__int128)*a3;
    v12 = v14(&v25, &v22);
    if ( v12 < 0 )
    {
      v15 = 4434;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
        (const char *)(unsigned int)v12,
        v20);
LABEL_22:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
      v13 = v21[0] == 0;
      goto LABEL_23;
    }
    v24[0] = 0;
    v25 = xmmword_18008F2D8;
    v12 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _DWORD *))(*v22 + 88))(v22, &v25, v24);
    if ( v12 < 0 )
    {
      v15 = 4438;
      goto LABEL_7;
    }
    if ( !v24[0] )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v23 = -2147024809;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          (unsigned __int8 *)byte_1800A9EA9,
          0,
          0,
          (__int64)&v23);
      }
      v12 = -2147024809;
      v15 = 4443;
      goto LABEL_7;
    }
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v26);
    v12 = NgcUtils::NgcContainerKeyName::BuildKeyNameString(Src, a6, a4, (__int64)v26);
    if ( v12 >= 0 )
    {
      v17 = *v22;
      v18 = v26;
      if ( v26[3] > 7u )
        v18 = (_QWORD *)v26[0];
      v25 = xmmword_18008F2D8;
      v20 = a8;
      v12 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _QWORD *, const unsigned __int8 *))(v17 + 352))(
              v22,
              &v25,
              v18,
              a7);
      if ( v12 >= 0 )
        goto LABEL_21;
      v16 = 4452;
    }
    else
    {
      v16 = 4448;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v12,
      v20);
LABEL_21:
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v26);
    goto LABEL_22;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v23 = v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)byte_1800A9F59,
      0,
      0,
      (__int64)&v23);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x114D,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
    (const char *)(unsigned int)v12,
    v20);
  v13 = v21[0] == 0;
LABEL_23:
  if ( !v13 )
    CoUninitialize();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004b584  mov     [rsp-8+arg_8], rbx
0x18004b589  push    rbp
0x18004b58a  push    rsi
0x18004b58b  push    rdi
0x18004b58c  push    r12
0x18004b58e  push    r13
0x18004b590  push    r14
0x18004b592  push    r15
0x18004b594  lea     rbp, [rsp-7]
0x18004b599  sub     rsp, 90h
0x18004b5a0  mov     rax, cs:__security_cookie
0x18004b5a7  xor     rax, rsp
0x18004b5aa  mov     [rbp+37h+var_40], rax
0x18004b5ae  mov     rdi, r9
0x18004b5b1  mov     r12, r8
0x18004b5b4  mov     r15, rcx
0x18004b5b7  mov     rsi, [rbp+37h+Src]
0x18004b5bb  mov     r14, [rbp+37h+arg_28]
0x18004b5bf  mov     r13, [rbp+37h+arg_30]
0x18004b5c3  mov     [rbp+37h+var_90], 0
0x18004b5c7  lea     rcx, [rbp+37h+var_90]; this
0x18004b5cb  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x18004b5d0  mov     ebx, eax
0x18004b5d2  test    eax, eax
0x18004b5d4  jns     short loc_18004B628
0x18004b5d6  mov     ecx, cs:dword_1800BE0B8
0x18004b5dc  cmp     ecx, 2
0x18004b5df  jbe     short loc_18004B606
0x18004b5e1  mov     [rbp+37h+var_80], eax
0x18004b5e4  lea     rax, [rbp+37h+var_80]
0x18004b5e8  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004b5ed  xor     r9d, r9d
0x18004b5f0  xor     r8d, r8d
0x18004b5f3  lea     rdx, byte_1800A9F59
0x18004b5fa  lea     rcx, dword_1800BE0B8
0x18004b601  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004b606  mov     rcx, [rbp+3Fh]; this
0x18004b60a  mov     r9d, ebx; char *
0x18004b60d  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x18004b614  mov     edx, 114Dh; void *
0x18004b619  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b61e  nop
0x18004b61f  cmp     [rbp+37h+var_90], 0
0x18004b623  jmp     loc_18004B795
0x18004b628  mov     [rbp+37h+var_88], 0
0x18004b630  mov     rbx, [r15]
0x18004b633  lea     rcx, [rbp+37h+var_88]
0x18004b637  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b63c  movups  xmm0, xmmword ptr [r12]
0x18004b641  movdqu  [rbp+37h+var_70], xmm0
0x18004b646  lea     rdx, [rbp+37h+var_88]
0x18004b64a  lea     rcx, [rbp+37h+var_70]
0x18004b64e  mov     rax, rbx
0x18004b651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b656  mov     ebx, eax
0x18004b658  xor     r15d, r15d
0x18004b65b  test    eax, eax
0x18004b65d  jns     short loc_18004B67C
0x18004b65f  mov     edx, 1152h; void *
0x18004b664  mov     rcx, [rbp+3Fh]; this
0x18004b668  mov     r9d, ebx; char *
0x18004b66b  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x18004b672  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b677  jmp     loc_18004B787
0x18004b67c  mov     [rbp+37h+var_7C], r15d
0x18004b680  mov     rcx, [rbp+37h+var_88]
0x18004b684  movups  xmm0, cs:xmmword_18008F2D8
0x18004b68b  movdqu  [rbp+37h+var_70], xmm0
0x18004b690  mov     rax, [rcx]
0x18004b693  lea     r8, [rbp+37h+var_7C]
0x18004b697  lea     rdx, [rbp+37h+var_70]
0x18004b69b  mov     rax, [rax+58h]
0x18004b69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6a4  mov     ebx, eax
0x18004b6a6  test    eax, eax
0x18004b6a8  jns     short loc_18004B6B1
0x18004b6aa  mov     edx, 1156h
0x18004b6af  jmp     short loc_18004B664
0x18004b6b1  cmp     [rbp+37h+var_7C], r15d
0x18004b6b5  jnz     short loc_18004B6FA
0x18004b6b7  mov     eax, cs:dword_1800BE0B8
0x18004b6bd  cmp     eax, 2
0x18004b6c0  jbe     short loc_18004B6EB
0x18004b6c2  mov     [rbp+37h+var_80], 80070057h
0x18004b6c9  lea     rax, [rbp+37h+var_80]
0x18004b6cd  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18004b6d2  xor     r9d, r9d
0x18004b6d5  xor     r8d, r8d
0x18004b6d8  lea     rdx, byte_1800A9EA9
0x18004b6df  lea     rcx, dword_1800BE0B8
0x18004b6e6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004b6eb  mov     ebx, 80070057h
0x18004b6f0  mov     edx, 115Bh
0x18004b6f5  jmp     loc_18004B664
0x18004b6fa  lea     rcx, [rbp+37h+var_60]
0x18004b6fe  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18004b703  nop
0x18004b704  lea     r9, [rbp+37h+var_60]
0x18004b708  mov     r8, rdi
0x18004b70b  mov     rdx, r14
0x18004b70e  mov     rcx, rsi; Src
0x18004b711  call    ?BuildKeyNameString@NgcContainerKeyName@NgcUtils@@YAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::NgcContainerKeyName::BuildKeyNameString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x18004b716  mov     ebx, eax
0x18004b718  test    eax, eax
0x18004b71a  jns     short loc_18004B723
0x18004b71c  mov     edx, 1160h
0x18004b721  jmp     short loc_18004B769
0x18004b723  mov     rcx, [rbp+37h+var_88]
0x18004b727  mov     rax, [rcx]
0x18004b72a  lea     r8, [rbp+37h+var_60]
0x18004b72e  cmp     [rbp+37h+var_48], 7
0x18004b733  cmova   r8, [rbp+37h+var_60]
0x18004b738  movups  xmm0, cs:xmmword_18008F2D8
0x18004b73f  movdqu  [rbp+37h+var_70], xmm0
0x18004b744  mov     edx, [rbp+37h+arg_38]
0x18004b747  mov     [rsp+0C0h+var_A0], edx; int
0x18004b74b  mov     r9, r13
0x18004b74e  lea     rdx, [rbp+37h+var_70]
0x18004b752  mov     rax, [rax+160h]
0x18004b759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b75e  mov     ebx, eax
0x18004b760  test    eax, eax
0x18004b762  jns     short loc_18004B77D
0x18004b764  mov     edx, 1164h; void *
0x18004b769  mov     r9d, ebx; char *
0x18004b76c  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x18004b773  mov     rcx, [rbp+3Fh]; this
0x18004b777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b77c  nop
0x18004b77d  lea     rcx, [rbp+37h+var_60]
0x18004b781  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18004b786  nop
0x18004b787  lea     rcx, [rbp+37h+var_88]
0x18004b78b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b790  nop
0x18004b791  cmp     [rbp+37h+var_90], r15b
0x18004b795  jz      short loc_18004B7A3
0x18004b797  call    cs:__imp_CoUninitialize
0x18004b79e  nop     dword ptr [rax+rax+00h]
0x18004b7a3  mov     eax, ebx
0x18004b7a5  mov     rcx, [rbp+37h+var_40]
0x18004b7a9  xor     rcx, rsp; StackCookie
0x18004b7ac  call    __security_check_cookie
0x18004b7b1  mov     rbx, [rsp+0C0h+arg_8]
0x18004b7b9  add     rsp, 90h
0x18004b7c0  pop     r15
0x18004b7c2  pop     r14
0x18004b7c4  pop     r13
0x18004b7c6  pop     r12
0x18004b7c8  pop     rdi
0x18004b7c9  pop     rsi
0x18004b7ca  pop     rbp
0x18004b7cb  retn
```
