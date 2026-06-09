# GET_INTEGER_PROPERTY_VALUE(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>,int &)

- ea: `0x180005970`
- end: `0x180005b77`
- name: `?GET_INTEGER_PROPERTY_VALUE@@YAJV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@AEAH@Z`
- size: `519`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006940`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003d3c`
- `0x180005970`
- `0x18009fe1a`
- `0x18009fe26`
- `0x1800a031b`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005a4b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005a4b`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005ac6`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005ac6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180005a72`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180005a72`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GET_INTEGER_PROPERTY_VALUE(_QWORD *a1, int *a2)
{
  unsigned int v4; // edi
  PCWSTR StringRawBuffer_0; // rax
  unsigned __int64 v6; // r8
  _DWORD *v7; // rax
  _DWORD *v8; // r14
  const wchar_t *v9; // rbx
  int v10; // eax
  wchar_t *v11; // rcx
  HRESULT v12; // eax
  HSTRING v13; // rcx
  wchar_t *String[2]; // [rsp+20h] [rbp-50h] BYREF
  __int128 v16; // [rsp+30h] [rbp-40h]
  _QWORD *v17; // [rsp+40h] [rbp-30h]
  wchar_t *EndPtr; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+58h] [rbp-18h] BYREF
  __int64 v21; // [rsp+60h] [rbp-10h] BYREF

  v17 = a1;
  v21 = 0;
  v20 = 0;
  string = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 96LL))(*a1, &v21);
  if ( !v4 )
  {
    v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v21)(
           v21,
           &GUID_5cc5b382_e6dd_4991_abef_06d8d2e7bd0c,
           &v20);
    if ( !v4 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 56LL))(v20, &string);
      if ( !v4 )
      {
        StringRawBuffer_0 = WindowsGetStringRawBuffer_0(string, 0);
        *(_OWORD *)String = 0;
        v16 = 0;
        v6 = -1;
        do
          ++v6;
        while ( StringRawBuffer_0[v6] );
        std::wstring::_Construct<1,wchar_t const *>((char **)String, StringRawBuffer_0, v6);
        v7 = (_DWORD *)_o__errno();
        v8 = v7;
        v9 = (const wchar_t *)String;
        if ( *((_QWORD *)&v16 + 1) >= 8u )
          v9 = String[0];
        *v7 = 0;
        v10 = wcstol(v9, &EndPtr, 10);
        if ( v9 == EndPtr )
        {
          std::_Xinvalid_argument("invalid stoi argument");
          JUMPOUT(0x180005B76LL);
        }
        if ( *v8 == 34 )
        {
          std::_Xout_of_range("stoi argument out of range");
          __debugbreak();
        }
        *a2 = v10;
        if ( *((_QWORD *)&v16 + 1) >= 8u )
        {
          v11 = String[0];
          if ( (unsigned __int64)(2LL * *((_QWORD *)&v16 + 1) + 2) >= 0x1000 )
          {
            v11 = (wchar_t *)*((_QWORD *)String[0] - 1);
            if ( (unsigned __int64)((char *)String[0] - (char *)v11 - 8) > 0x1F )
            {
              _o__invalid_parameter_noinfo_noreturn(v11, 2LL * *((_QWORD *)&v16 + 1) + 41);
              __debugbreak();
            }
          }
          operator delete(v11);
        }
      }
    }
  }
  v12 = WindowsDeleteString_0(string);
  v13 = string;
  if ( !v12 )
    v13 = 0;
  string = v13;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v20 = 0;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v21 = 0;
  if ( *a1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
  *a1 = 0;
  return v4;
}

```

## disassembly

```asm
0x180005970  mov     [rsp-28h+arg_10], rbx
0x180005975  mov     [rsp-28h+arg_18], rsi
0x18000597a  push    rbp
0x18000597b  push    rdi
0x18000597c  push    r12
0x18000597e  push    r14
0x180005980  push    r15
0x180005982  mov     rbp, rsp
0x180005985  sub     rsp, 70h
0x180005989  mov     rax, cs:__security_cookie
0x180005990  xor     rax, rsp
0x180005993  mov     [rbp+var_8], rax
0x180005997  mov     r15, rdx
0x18000599a  mov     rsi, rcx
0x18000599d  mov     [rbp+var_30], rcx
0x1800059a1  xor     r12d, r12d
0x1800059a4  mov     [rbp+var_10], r12
0x1800059a8  mov     [rbp+var_18], r12
0x1800059ac  mov     [rbp+string], r12
0x1800059b0  mov     rcx, [rcx]
0x1800059b3  mov     rax, [rcx]
0x1800059b6  lea     rdx, [rbp+var_10]
0x1800059ba  mov     rax, [rax+60h]
0x1800059be  call    cs:__guard_dispatch_icall_fptr
0x1800059c4  mov     edi, eax
0x1800059c6  test    eax, eax
0x1800059c8  jnz     loc_180005AD3
0x1800059ce  mov     rcx, [rbp+var_10]
0x1800059d2  mov     rax, [rcx]
0x1800059d5  lea     r8, [rbp+var_18]
0x1800059d9  lea     rdx, _GUID_5cc5b382_e6dd_4991_abef_06d8d2e7bd0c
0x1800059e0  mov     rax, [rax]
0x1800059e3  call    cs:__guard_dispatch_icall_fptr
0x1800059e9  mov     edi, eax
0x1800059eb  test    eax, eax
0x1800059ed  jnz     loc_180005AD3
0x1800059f3  mov     rcx, [rbp+var_18]
0x1800059f7  mov     rax, [rcx]
0x1800059fa  lea     rdx, [rbp+string]
0x1800059fe  mov     rax, [rax+38h]
0x180005a02  call    cs:__guard_dispatch_icall_fptr
0x180005a08  mov     edi, eax
0x180005a0a  test    eax, eax
0x180005a0c  jnz     loc_180005AD3
0x180005a12  xor     edx, edx; length
0x180005a14  mov     rcx, [rbp+string]; string
0x180005a18  call    WindowsGetStringRawBuffer_0
0x180005a1d  xorps   xmm0, xmm0
0x180005a20  movups  xmmword ptr [rbp+String], xmm0
0x180005a24  xorps   xmm1, xmm1
0x180005a27  movdqu  [rbp+var_40], xmm1
0x180005a2c  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180005a33  inc     r8
0x180005a36  cmp     word ptr [rax+r8*2], 0
0x180005a3c  jnz     short loc_180005A33
0x180005a3e  mov     rdx, rax
0x180005a41  lea     rcx, [rbp+String]
0x180005a45  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005a4a  nop
0x180005a4b  call    cs:__imp__o__errno
0x180005a51  mov     r14, rax
0x180005a54  lea     rbx, [rbp+String]
0x180005a58  cmp     qword ptr [rbp+var_40+8], 8
0x180005a5d  cmovnb  rbx, [rbp+String]
0x180005a62  mov     [rax], r12d
0x180005a65  mov     r8d, 0Ah; Radix
0x180005a6b  lea     rdx, [rbp+EndPtr]; EndPtr
0x180005a6f  mov     rcx, rbx; String
0x180005a72  call    cs:__imp_wcstol
0x180005a78  cmp     rbx, [rbp+EndPtr]
0x180005a7c  jz      loc_180005B6A
0x180005a82  cmp     dword ptr [r14], 22h ; '"'
0x180005a86  jz      loc_180005B5D
0x180005a8c  mov     [r15], eax
0x180005a8f  mov     rdx, qword ptr [rbp+var_40+8]
0x180005a93  cmp     rdx, 8
0x180005a97  jb      short loc_180005AD3
0x180005a99  lea     rdx, ds:2[rdx*2]
0x180005aa1  mov     rcx, [rbp+String]; Block
0x180005aa5  mov     rax, rcx
0x180005aa8  cmp     rdx, 1000h
0x180005aaf  jb      short loc_180005ACD
0x180005ab1  add     rdx, 27h ; '''
0x180005ab5  mov     rcx, [rcx-8]
0x180005ab9  sub     rax, rcx
0x180005abc  add     rax, 0FFFFFFFFFFFFFFF8h
0x180005ac0  cmp     rax, 1Fh
0x180005ac4  jbe     short loc_180005ACD
0x180005ac6  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180005acc  int     3; Trap to Debugger
0x180005acd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005ad2  nop
0x180005ad3  mov     rcx, [rbp+string]; string
0x180005ad7  call    WindowsDeleteString_0
0x180005adc  mov     rcx, [rbp+string]
0x180005ae0  test    eax, eax
0x180005ae2  cmovz   rcx, r12
0x180005ae6  mov     [rbp+string], rcx
0x180005aea  mov     rcx, [rbp+var_18]
0x180005aee  test    rcx, rcx
0x180005af1  jz      short loc_180005B00
0x180005af3  mov     rax, [rcx]
0x180005af6  mov     rax, [rax+10h]
0x180005afa  call    cs:__guard_dispatch_icall_fptr
0x180005b00  mov     [rbp+var_18], r12
0x180005b04  mov     rcx, [rbp+var_10]
0x180005b08  test    rcx, rcx
0x180005b0b  jz      short loc_180005B1A
0x180005b0d  mov     rax, [rcx]
0x180005b10  mov     rax, [rax+10h]
0x180005b14  call    cs:__guard_dispatch_icall_fptr
0x180005b1a  mov     [rbp+var_10], r12
0x180005b1e  mov     rcx, [rsi]
0x180005b21  test    rcx, rcx
0x180005b24  jz      short loc_180005B33
0x180005b26  mov     rax, [rcx]
0x180005b29  mov     rax, [rax+10h]
0x180005b2d  call    cs:__guard_dispatch_icall_fptr
0x180005b33  mov     [rsi], r12
0x180005b36  mov     eax, edi
0x180005b38  mov     rcx, [rbp+var_8]
0x180005b3c  xor     rcx, rsp; StackCookie
0x180005b3f  call    __security_check_cookie
0x180005b44  lea     r11, [rsp+70h+var_s0]
0x180005b49  mov     rbx, [r11+40h]
0x180005b4d  mov     rsi, [r11+48h]
0x180005b51  mov     rsp, r11
0x180005b54  pop     r15
0x180005b56  pop     r14
0x180005b58  pop     r12
0x180005b5a  pop     rdi
0x180005b5b  pop     rbp
0x180005b5c  retn
0x180005b5d  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x180005b64  call    ?_Xout_of_range@std@@YAXPEBD@Z_0; std::_Xout_of_range(char const *)
0x180005b69  int     3; Trap to Debugger
0x180005b6a  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x180005b71  call    ?_Xinvalid_argument@std@@YAXPEBD@Z_0; std::_Xinvalid_argument(char const *)
```
