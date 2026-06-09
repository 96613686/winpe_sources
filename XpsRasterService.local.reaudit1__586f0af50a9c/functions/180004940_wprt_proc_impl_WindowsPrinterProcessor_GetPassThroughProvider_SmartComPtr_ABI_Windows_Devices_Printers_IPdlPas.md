# wprt::proc::impl::WindowsPrinterProcessor::GetPassThroughProvider(SmartComPtr<ABI::Windows::Devices::Printers::IPdlPassthroughProvider> &)

- ea: `0x180004940`
- end: `0x180004b0d`
- name: `?GetPassThroughProvider@WindowsPrinterProcessor@impl@proc@wprt@@AEBA_NAEAV?$SmartComPtr@UIPdlPassthroughProvider@Printers@Devices@Windows@ABI@@@@@Z`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005110`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003d30`
- `0x180003d3c`
- `0x180004940`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800049f1`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800049f1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180004a1e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180004a1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_BOOL8 __fastcall wprt::proc::impl::WindowsPrinterProcessor::GetPassThroughProvider(__int64 a1, __int64 a2)
{
  const WCHAR *v4; // rcx
  WCHAR *v5; // rcx
  int ActivationFactory; // ebx
  bool v7; // bl
  HRESULT v8; // eax
  HSTRING v9; // rcx
  PCNZWCH sourceString[2]; // [rsp+20h] [rbp-50h] BYREF
  UINT32 length[4]; // [rsp+30h] [rbp-40h]
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  __int64 v14; // [rsp+48h] [rbp-28h] BYREF
  __int64 v15; // [rsp+50h] [rbp-20h] BYREF
  __int64 v16; // [rsp+58h] [rbp-18h] BYREF

  v16 = 0;
  v14 = 0;
  string = 0;
  *(_OWORD *)sourceString = 0;
  *(_OWORD *)length = 0;
  std::wstring::_Construct<1,wchar_t const *>(sourceString, L"Windows.Devices.Printers.IppPrintDevice");
  string = 0;
  v4 = (const WCHAR *)sourceString;
  if ( *(_QWORD *)&length[2] >= 8u )
    v4 = sourceString[0];
  WindowsCreateString_0(v4, length[0], &string);
  if ( *(_QWORD *)&length[2] >= 8u )
  {
    v5 = (WCHAR *)sourceString[0];
    if ( (unsigned __int64)(2LL * *(_QWORD *)&length[2] + 2) >= 0x1000 )
    {
      v5 = (WCHAR *)*((_QWORD *)sourceString[0] - 1);
      if ( (unsigned __int64)((char *)sourceString[0] - (char *)v5 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v5, 2LL * *(_QWORD *)&length[2] + 41);
        __debugbreak();
      }
    }
    operator delete(v5);
  }
  *(__m128i *)length = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(sourceString[0]) = 0;
  ActivationFactory = RoGetActivationFactory(string, &GUID_7dc19f08_7f20_52ab_94a7_894b83b2a17e, &v16);
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 64LL))(
                          v16,
                          *(_QWORD *)(a1 + 8),
                          &v14);
    if ( ActivationFactory >= 0 )
    {
      v15 = 0;
      ActivationFactory = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v14)(
                            v14,
                            &GUID_f7c844c9_9d21_5c63_ac20_3676915be2d7,
                            &v15);
      if ( ActivationFactory >= 0 )
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 72LL))(v15, a2);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  v7 = ActivationFactory >= 0;
  v8 = WindowsDeleteString_0(string);
  v9 = string;
  if ( !v8 )
    v9 = 0;
  string = v9;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v14 = 0;
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return v7;
}

```

## disassembly

```asm
0x180004940  mov     [rsp-18h+arg_10], rbx
0x180004945  mov     [rsp-18h+arg_18], rsi
0x18000494a  push    rbp
0x18000494b  push    rdi
0x18000494c  push    r14
0x18000494e  mov     rbp, rsp
0x180004951  sub     rsp, 70h
0x180004955  mov     rax, cs:__security_cookie
0x18000495c  xor     rax, rsp
0x18000495f  mov     [rbp+var_10], rax
0x180004963  mov     rsi, rdx
0x180004966  mov     rdi, rcx
0x180004969  xor     r14d, r14d
0x18000496c  mov     [rbp+var_18], r14
0x180004970  mov     [rbp+var_28], r14
0x180004974  mov     [rbp+string], r14
0x180004978  xorps   xmm0, xmm0
0x18000497b  movups  xmmword ptr [rbp+sourceString], xmm0
0x18000497f  xorps   xmm1, xmm1
0x180004982  movdqu  xmmword ptr [rbp+length], xmm1
0x180004987  lea     r8d, [r14+27h]
0x18000498b  lea     rdx, ?RuntimeClass_Windows_Devices_Printers_IppPrintDevice@@3QB_WB; "Windows.Devices.Printers.IppPrintDevice"
0x180004992  lea     rcx, [rbp+sourceString]
0x180004996  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000499b  mov     [rbp+string], r14
0x18000499f  lea     rcx, [rbp+sourceString]
0x1800049a3  cmp     qword ptr [rbp+length+8], 8
0x1800049a8  cmovnb  rcx, [rbp+sourceString]; sourceString
0x1800049ad  lea     r8, [rbp+string]; string
0x1800049b1  mov     edx, [rbp+length]; length
0x1800049b4  call    WindowsCreateString_0
0x1800049b9  nop
0x1800049ba  mov     rdx, qword ptr [rbp+length+8]
0x1800049be  cmp     rdx, 8
0x1800049c2  jb      short loc_1800049FD
0x1800049c4  lea     rdx, ds:2[rdx*2]
0x1800049cc  mov     rcx, [rbp+sourceString]; Block
0x1800049d0  mov     rax, rcx
0x1800049d3  cmp     rdx, 1000h
0x1800049da  jb      short loc_1800049F8
0x1800049dc  add     rdx, 27h ; '''
0x1800049e0  mov     rcx, [rcx-8]
0x1800049e4  sub     rax, rcx
0x1800049e7  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800049eb  cmp     rax, 1Fh
0x1800049ef  jbe     short loc_1800049F8
0x1800049f1  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x1800049f7  int     3; Trap to Debugger
0x1800049f8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800049fd  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180004a05  movdqu  xmmword ptr [rbp+length], xmm0
0x180004a0a  mov     word ptr [rbp+sourceString], r14w
0x180004a0f  lea     r8, [rbp+var_18]
0x180004a13  lea     rdx, _GUID_7dc19f08_7f20_52ab_94a7_894b83b2a17e
0x180004a1a  mov     rcx, [rbp+string]
0x180004a1e  call    cs:__imp_RoGetActivationFactory
0x180004a24  mov     ebx, eax
0x180004a26  test    eax, eax
0x180004a28  js      short loc_180004A9B
0x180004a2a  mov     rcx, [rbp+var_18]
0x180004a2e  mov     rax, [rcx]
0x180004a31  lea     r8, [rbp+var_28]
0x180004a35  mov     rdx, [rdi+8]
0x180004a39  mov     rax, [rax+40h]
0x180004a3d  call    cs:__guard_dispatch_icall_fptr
0x180004a43  mov     ebx, eax
0x180004a45  test    eax, eax
0x180004a47  js      short loc_180004A9B
0x180004a49  mov     [rbp+var_20], r14
0x180004a4d  mov     rcx, [rbp+var_28]
0x180004a51  mov     rax, [rcx]
0x180004a54  lea     r8, [rbp+var_20]
0x180004a58  lea     rdx, _GUID_f7c844c9_9d21_5c63_ac20_3676915be2d7
0x180004a5f  mov     rax, [rax]
0x180004a62  call    cs:__guard_dispatch_icall_fptr
0x180004a68  mov     ebx, eax
0x180004a6a  test    eax, eax
0x180004a6c  js      short loc_180004A84
0x180004a6e  mov     rcx, [rbp+var_20]
0x180004a72  mov     rax, [rcx]
0x180004a75  mov     rdx, rsi
0x180004a78  mov     rax, [rax+48h]
0x180004a7c  call    cs:__guard_dispatch_icall_fptr
0x180004a82  mov     ebx, eax
0x180004a84  mov     rcx, [rbp+var_20]
0x180004a88  test    rcx, rcx
0x180004a8b  jz      short loc_180004A9B
0x180004a8d  mov     rax, [rcx]
0x180004a90  mov     rax, [rax+10h]
0x180004a94  call    cs:__guard_dispatch_icall_fptr
0x180004a9a  nop
0x180004a9b  shr     ebx, 1Fh
0x180004a9e  xor     bl, 1
0x180004aa1  mov     rcx, [rbp+string]; string
0x180004aa5  call    WindowsDeleteString_0
0x180004aaa  mov     rcx, [rbp+string]
0x180004aae  test    eax, eax
0x180004ab0  cmovz   rcx, r14
0x180004ab4  mov     [rbp+string], rcx
0x180004ab8  mov     rcx, [rbp+var_28]
0x180004abc  test    rcx, rcx
0x180004abf  jz      short loc_180004ACE
0x180004ac1  mov     rax, [rcx]
0x180004ac4  mov     rax, [rax+10h]
0x180004ac8  call    cs:__guard_dispatch_icall_fptr
0x180004ace  mov     [rbp+var_28], r14
0x180004ad2  mov     rcx, [rbp+var_18]
0x180004ad6  test    rcx, rcx
0x180004ad9  jz      short loc_180004AE9
0x180004adb  mov     rax, [rcx]
0x180004ade  mov     rax, [rax+10h]
0x180004ae2  call    cs:__guard_dispatch_icall_fptr
0x180004ae8  nop
0x180004ae9  movzx   eax, bl
0x180004aec  mov     rcx, [rbp+var_10]
0x180004af0  xor     rcx, rsp; StackCookie
0x180004af3  call    __security_check_cookie
0x180004af8  lea     r11, [rsp+70h+var_s0]
0x180004afd  mov     rbx, [r11+30h]
0x180004b01  mov     rsi, [r11+38h]
0x180004b05  mov     rsp, r11
0x180004b08  pop     r14
0x180004b0a  pop     rdi
0x180004b0b  pop     rbp
0x180004b0c  retn
```
