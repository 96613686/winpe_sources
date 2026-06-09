# NgcHandler::GetSessionChallenge(void *,_GUID const &,ushort const *,ushort const *,ushort const *,uchar * *,ulong *)

- ea: `0x180049c30`
- end: `0x180049e71`
- name: `?GetSessionChallenge@NgcHandler@@QEAAJPEAXAEBU_GUID@@PEBG22PEAPEAEPEAK@Z`
- size: `577`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *Src, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004c968`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x18000b490`
- `0x1800134a0`
- `0x180014350`
- `0x180018194`
- `0x180023278`
- `0x18002c640`
- `0x180049c30`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180049e3b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180049e3b`

## string_xrefs

- `0x180049cc1`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x180049d1c`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x180049e0f`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcHandler::GetSessionChallenge(
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
  __int64 (__fastcall *v14)(__int128 *, __int64 **); // rbx
  __int64 v15; // rdx
  __int64 v16; // rax
  _QWORD *v17; // r8
  int v18; // eax
  int v20; // [rsp+20h] [rbp-69h]
  int v21; // [rsp+20h] [rbp-69h]
  _BYTE v22[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 *v23; // [rsp+38h] [rbp-51h] BYREF
  int v24; // [rsp+40h] [rbp-49h] BYREF
  int v25[2]; // [rsp+48h] [rbp-41h] BYREF
  __int128 v26; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v27[4]; // [rsp+60h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+3Fh]

  *(_QWORD *)v25 = a8;
  v22[0] = 0;
  v11 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v22, (unsigned int)a2);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v23 = 0;
    v14 = *this;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    v26 = (__int128)*a3;
    v12 = v14(&v26, &v23);
    if ( v12 >= 0 )
    {
      v24 = 0;
      v26 = xmmword_18008F2D8;
      v12 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, int *))(*v23 + 88))(v23, &v26, &v24);
      if ( v12 >= 0 )
      {
        if ( v24 )
        {
          std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v27);
          NgcUtils::NgcContainerKeyName::BuildKeyNameString(Src, a6, a4, (__int64)v27);
          v16 = *v23;
          v17 = v27;
          if ( v27[3] > 7u )
            v17 = (_QWORD *)v27[0];
          v26 = xmmword_18008F2D8;
          v21 = v25[0];
          v18 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _QWORD *, unsigned __int8 **))(v16 + 344))(
                  v23,
                  &v26,
                  v17,
                  a7);
          v12 = v18;
          if ( v18 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1135,
              (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
              (const char *)(unsigned int)v18,
              v21);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v27);
          goto LABEL_19;
        }
        if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          v25[0] = -2147024809;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_1800BE0B8,
            (unsigned __int8 *)&byte_1800A9EF7,
            0,
            0,
            (__int64)v25);
        }
        v12 = -2147024809;
        v15 = 4396;
      }
      else
      {
        v15 = 4391;
      }
    }
    else
    {
      v15 = 4387;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
      (const char *)(unsigned int)v12,
      v20);
LABEL_19:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    v13 = v22[0] == 0;
    goto LABEL_20;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v25[0] = v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)&word_1800A9F1E,
      0,
      0,
      (__int64)v25);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x111E,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\ngc\\ngchandler.cpp",
    (const char *)(unsigned int)v12,
    v20);
  v13 = v22[0] == 0;
LABEL_20:
  if ( !v13 )
    CoUninitialize();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180049c30  mov     [rsp-8+arg_8], rbx
0x180049c35  push    rbp
0x180049c36  push    rsi
0x180049c37  push    rdi
0x180049c38  push    r12
0x180049c3a  push    r13
0x180049c3c  push    r14
0x180049c3e  push    r15
0x180049c40  lea     rbp, [rsp-7]
0x180049c45  sub     rsp, 90h
0x180049c4c  mov     rax, cs:__security_cookie
0x180049c53  xor     rax, rsp
0x180049c56  mov     [rbp+37h+var_40], rax
0x180049c5a  mov     r14, r9
0x180049c5d  mov     rsi, r8
0x180049c60  mov     rdi, rcx
0x180049c63  mov     r15, [rbp+37h+Src]
0x180049c67  mov     r12, [rbp+37h+arg_28]
0x180049c6b  mov     r13, [rbp+37h+arg_30]
0x180049c6f  mov     rax, [rbp+37h+arg_38]
0x180049c73  mov     qword ptr [rbp+37h+var_78], rax
0x180049c77  mov     [rbp+37h+var_90], 0
0x180049c7b  lea     rcx, [rbp+37h+var_90]; this
0x180049c7f  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x180049c84  mov     ebx, eax
0x180049c86  test    eax, eax
0x180049c88  jns     short loc_180049CDC
0x180049c8a  mov     ecx, cs:dword_1800BE0B8
0x180049c90  cmp     ecx, 2
0x180049c93  jbe     short loc_180049CBA
0x180049c95  mov     [rbp+37h+var_78], eax
0x180049c98  lea     rax, [rbp+37h+var_78]
0x180049c9c  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180049ca1  xor     r9d, r9d
0x180049ca4  xor     r8d, r8d
0x180049ca7  lea     rdx, word_1800A9F1E
0x180049cae  lea     rcx, dword_1800BE0B8
0x180049cb5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180049cba  mov     rcx, [rbp+3Fh]; this
0x180049cbe  mov     r9d, ebx; char *
0x180049cc1  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180049cc8  mov     edx, 111Eh; void *
0x180049ccd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049cd2  nop
0x180049cd3  cmp     [rbp+37h+var_90], 0
0x180049cd7  jmp     loc_180049E39
0x180049cdc  mov     [rbp+37h+var_88], 0
0x180049ce4  mov     rbx, [rdi]
0x180049ce7  lea     rcx, [rbp+37h+var_88]
0x180049ceb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049cf0  movups  xmm0, xmmword ptr [rsi]
0x180049cf3  movdqu  [rbp+37h+var_70], xmm0
0x180049cf8  lea     rdx, [rbp+37h+var_88]
0x180049cfc  lea     rcx, [rbp+37h+var_70]
0x180049d00  mov     rax, rbx
0x180049d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d08  mov     ebx, eax
0x180049d0a  xor     edi, edi
0x180049d0c  test    eax, eax
0x180049d0e  jns     short loc_180049D2D
0x180049d10  mov     edx, 1123h; void *
0x180049d15  mov     rcx, [rbp+3Fh]; this
0x180049d19  mov     r9d, ebx; char *
0x180049d1c  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180049d23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049d28  jmp     loc_180049E2B
0x180049d2d  mov     [rbp+37h+var_80], edi
0x180049d30  mov     rcx, [rbp+37h+var_88]
0x180049d34  movups  xmm0, cs:xmmword_18008F2D8
0x180049d3b  movdqu  [rbp+37h+var_70], xmm0
0x180049d40  mov     rax, [rcx]
0x180049d43  lea     r8, [rbp+37h+var_80]
0x180049d47  lea     rdx, [rbp+37h+var_70]
0x180049d4b  mov     rax, [rax+58h]
0x180049d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d54  mov     ebx, eax
0x180049d56  test    eax, eax
0x180049d58  jns     short loc_180049D61
0x180049d5a  mov     edx, 1127h
0x180049d5f  jmp     short loc_180049D15
0x180049d61  cmp     [rbp+37h+var_80], edi
0x180049d64  jnz     short loc_180049DA9
0x180049d66  mov     eax, cs:dword_1800BE0B8
0x180049d6c  cmp     eax, 2
0x180049d6f  jbe     short loc_180049D9A
0x180049d71  mov     [rbp+37h+var_78], 80070057h
0x180049d78  lea     rax, [rbp+37h+var_78]
0x180049d7c  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180049d81  xor     r9d, r9d
0x180049d84  xor     r8d, r8d
0x180049d87  lea     rdx, byte_1800A9EF7
0x180049d8e  lea     rcx, dword_1800BE0B8
0x180049d95  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180049d9a  mov     ebx, 80070057h
0x180049d9f  mov     edx, 112Ch
0x180049da4  jmp     loc_180049D15
0x180049da9  lea     rcx, [rbp+37h+var_60]
0x180049dad  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180049db2  nop
0x180049db3  lea     r9, [rbp+37h+var_60]
0x180049db7  mov     r8, r14
0x180049dba  mov     rdx, r12
0x180049dbd  mov     rcx, r15; Src
0x180049dc0  call    ?BuildKeyNameString@NgcContainerKeyName@NgcUtils@@YAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::NgcContainerKeyName::BuildKeyNameString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x180049dc5  mov     rcx, [rbp+37h+var_88]
0x180049dc9  mov     rax, [rcx]
0x180049dcc  lea     r8, [rbp+37h+var_60]
0x180049dd0  cmp     [rbp+37h+var_48], 7
0x180049dd5  cmova   r8, [rbp+37h+var_60]
0x180049dda  movups  xmm0, cs:xmmword_18008F2D8
0x180049de1  movdqu  [rbp+37h+var_70], xmm0
0x180049de6  mov     rdx, qword ptr [rbp+37h+var_78]
0x180049dea  mov     qword ptr [rsp+0C0h+var_A0], rdx; int
0x180049def  mov     r9, r13
0x180049df2  lea     rdx, [rbp+37h+var_70]
0x180049df6  mov     rax, [rax+158h]
0x180049dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e02  mov     ebx, eax
0x180049e04  test    eax, eax
0x180049e06  jns     short loc_180049E21
0x180049e08  mov     rcx, [rbp+3Fh]; this
0x180049e0c  mov     r9d, eax; char *
0x180049e0f  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180049e16  mov     edx, 1135h; void *
0x180049e1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049e20  nop
0x180049e21  lea     rcx, [rbp+37h+var_60]
0x180049e25  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180049e2a  nop
0x180049e2b  lea     rcx, [rbp+37h+var_88]
0x180049e2f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049e34  nop
0x180049e35  cmp     [rbp+37h+var_90], dil
0x180049e39  jz      short loc_180049E47
0x180049e3b  call    cs:__imp_CoUninitialize
0x180049e42  nop     dword ptr [rax+rax+00h]
0x180049e47  mov     eax, ebx
0x180049e49  mov     rcx, [rbp+37h+var_40]
0x180049e4d  xor     rcx, rsp; StackCookie
0x180049e50  call    __security_check_cookie
0x180049e55  mov     rbx, [rsp+0C0h+arg_8]
0x180049e5d  add     rsp, 90h
0x180049e64  pop     r15
0x180049e66  pop     r14
0x180049e68  pop     r13
0x180049e6a  pop     r12
0x180049e6c  pop     rdi
0x180049e6d  pop     rsi
0x180049e6e  pop     rbp
0x180049e6f  retn
```
