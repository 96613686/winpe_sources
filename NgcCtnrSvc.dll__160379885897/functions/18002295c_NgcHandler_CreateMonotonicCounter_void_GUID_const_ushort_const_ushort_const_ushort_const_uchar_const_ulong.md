# NgcHandler::CreateMonotonicCounter(void *,_GUID const &,ushort const *,ushort const *,ushort const *,uchar const *,ulong)

- ea: `0x18002295c`
- end: `0x180022b68`
- name: `?CreateMonotonicCounter@NgcHandler@@QEAAJPEAXAEBU_GUID@@PEBG22PEBEK@Z`
- size: `524`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, void *, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *Src, const unsigned __int16 *, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004c3b8`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x18000b490`
- `0x1800134a0`
- `0x180014350`
- `0x18002295c`
- `0x180023278`
- `0x18002c640`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800229cd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022b32`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800229cd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022b32`

## string_xrefs

- `0x1800229b5`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x180022a23`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`
- `0x180022aae`: `onecore\ds\security\ngc\ctnrsvc\handlers\ngc\ngchandler.cpp`

## pseudocode

```c
__int64 __fastcall NgcHandler::CreateMonotonicCounter(
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
      (void *)0x1229,
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
    v16 = 4654;
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
    v16 = 4657;
    goto LABEL_8;
  }
  if ( !v23[0] )
  {
    v12 = -2147024809;
    v16 = 4658;
    goto LABEL_8;
  }
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v25);
  v12 = NgcUtils::NgcContainerKeyName::BuildKeyNameString(Src, a6, a4, (__int64)v25);
  if ( v12 < 0 )
  {
    v17 = 4665;
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
  v12 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _QWORD *, const unsigned __int8 *))(v18 + 360))(
          v22,
          &v24,
          v19,
          a7);
  if ( v12 < 0 )
  {
    v17 = 4671;
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
0x18002295c  mov     [rsp-8+arg_8], rbx
0x180022961  push    rbp
0x180022962  push    rsi
0x180022963  push    rdi
0x180022964  push    r12
0x180022966  push    r13
0x180022968  push    r14
0x18002296a  push    r15
0x18002296c  lea     rbp, [rsp-7]
0x180022971  sub     rsp, 90h
0x180022978  mov     rax, cs:__security_cookie
0x18002297f  xor     rax, rsp
0x180022982  mov     [rbp+37h+var_40], rax
0x180022986  mov     rdi, r9
0x180022989  mov     r12, r8
0x18002298c  mov     r15, rcx
0x18002298f  mov     rsi, [rbp+37h+Src]
0x180022993  mov     r14, [rbp+37h+arg_28]
0x180022997  mov     r13, [rbp+37h+arg_30]
0x18002299b  mov     [rbp+37h+var_90], 0
0x18002299f  lea     rcx, [rbp+37h+var_90]; this
0x1800229a3  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x1800229a8  mov     ebx, eax
0x1800229aa  test    eax, eax
0x1800229ac  jns     short loc_1800229E0
0x1800229ae  mov     rcx, [rbp+3Fh]; this
0x1800229b2  mov     r9d, eax; char *
0x1800229b5  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x1800229bc  mov     edx, 1229h; void *
0x1800229c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800229c6  nop
0x1800229c7  cmp     [rbp+37h+var_90], 0
0x1800229cb  jz      short loc_1800229D9
0x1800229cd  call    cs:__imp_CoUninitialize
0x1800229d4  nop     dword ptr [rax+rax+00h]
0x1800229d9  mov     eax, ebx
0x1800229db  jmp     loc_180022B40
0x1800229e0  mov     [rbp+37h+var_88], 0
0x1800229e8  mov     rbx, [r15]
0x1800229eb  lea     rcx, [rbp+37h+var_88]
0x1800229ef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800229f4  movups  xmm0, xmmword ptr [r12]
0x1800229f9  movdqu  [rbp+37h+var_70], xmm0
0x1800229fe  lea     rdx, [rbp+37h+var_88]
0x180022a02  lea     rcx, [rbp+37h+var_70]
0x180022a06  mov     rax, rbx
0x180022a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a0e  mov     ebx, eax
0x180022a10  xor     r15d, r15d
0x180022a13  test    eax, eax
0x180022a15  jns     short loc_180022A40
0x180022a17  mov     edx, 122Eh; void *
0x180022a1c  mov     rcx, [rbp+3Fh]; this
0x180022a20  mov     r9d, ebx; char *
0x180022a23  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180022a2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022a2f  nop
0x180022a30  lea     rcx, [rbp+37h+var_88]
0x180022a34  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022a39  nop
0x180022a3a  cmp     [rbp+37h+var_90], r15b
0x180022a3e  jmp     short loc_1800229CB
0x180022a40  mov     [rbp+37h+var_80], r15d
0x180022a44  mov     rcx, [rbp+37h+var_88]
0x180022a48  movups  xmm0, cs:xmmword_18008F2D8
0x180022a4f  movdqu  [rbp+37h+var_70], xmm0
0x180022a54  mov     rax, [rcx]
0x180022a57  lea     r8, [rbp+37h+var_80]
0x180022a5b  lea     rdx, [rbp+37h+var_70]
0x180022a5f  mov     rax, [rax+58h]
0x180022a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a68  mov     ebx, eax
0x180022a6a  test    eax, eax
0x180022a6c  jns     short loc_180022A75
0x180022a6e  mov     edx, 1231h
0x180022a73  jmp     short loc_180022A1C
0x180022a75  cmp     [rbp+37h+var_80], r15d
0x180022a79  jnz     short loc_180022A87
0x180022a7b  mov     ebx, 80070057h
0x180022a80  mov     edx, 1232h
0x180022a85  jmp     short loc_180022A1C
0x180022a87  lea     rcx, [rbp+37h+var_60]
0x180022a8b  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180022a90  nop
0x180022a91  lea     r9, [rbp+37h+var_60]
0x180022a95  mov     r8, rdi
0x180022a98  mov     rdx, r14
0x180022a9b  mov     rcx, rsi; Src
0x180022a9e  call    ?BuildKeyNameString@NgcContainerKeyName@NgcUtils@@YAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::NgcContainerKeyName::BuildKeyNameString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x180022aa3  mov     ebx, eax
0x180022aa5  test    eax, eax
0x180022aa7  jns     short loc_180022AD0
0x180022aa9  mov     edx, 1239h; void *
0x180022aae  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180022ab5  mov     r9d, ebx; char *
0x180022ab8  mov     rcx, [rbp+3Fh]; this
0x180022abc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022ac1  nop
0x180022ac2  lea     rcx, [rbp+37h+var_60]
0x180022ac6  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180022acb  jmp     loc_180022A30
0x180022ad0  mov     rcx, [rbp+37h+var_88]
0x180022ad4  mov     rax, [rcx]
0x180022ad7  lea     r8, [rbp+37h+var_60]
0x180022adb  cmp     [rbp+37h+var_48], 7
0x180022ae0  cmova   r8, [rbp+37h+var_60]
0x180022ae5  movups  xmm0, cs:xmmword_18008F2D8
0x180022aec  movdqu  [rbp+37h+var_70], xmm0
0x180022af1  mov     edx, [rbp+37h+arg_38]
0x180022af4  mov     [rsp+0C0h+var_A0], edx
0x180022af8  mov     r9, r13
0x180022afb  lea     rdx, [rbp+37h+var_70]
0x180022aff  mov     rax, [rax+168h]
0x180022b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b0b  mov     ebx, eax
0x180022b0d  test    eax, eax
0x180022b0f  jns     short loc_180022B18
0x180022b11  mov     edx, 123Fh
0x180022b16  jmp     short loc_180022AAE
0x180022b18  lea     rcx, [rbp+37h+var_60]
0x180022b1c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180022b21  nop
0x180022b22  lea     rcx, [rbp+37h+var_88]
0x180022b26  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022b2b  nop
0x180022b2c  cmp     [rbp+37h+var_90], r15b
0x180022b30  jz      short loc_180022B3E
0x180022b32  call    cs:__imp_CoUninitialize
0x180022b39  nop     dword ptr [rax+rax+00h]
0x180022b3e  xor     eax, eax
0x180022b40  mov     rcx, [rbp+37h+var_40]
0x180022b44  xor     rcx, rsp; StackCookie
0x180022b47  call    __security_check_cookie
0x180022b4c  mov     rbx, [rsp+0C0h+arg_8]
0x180022b54  add     rsp, 90h
0x180022b5b  pop     r15
0x180022b5d  pop     r14
0x180022b5f  pop     r13
0x180022b61  pop     r12
0x180022b63  pop     rdi
0x180022b64  pop     rsi
0x180022b65  pop     rbp
0x180022b66  retn
```
