# SDK::Unit::TemporaryPolicy::ReadShortTermLicense(ABI::Windows::Storage::Streams::IRandomAccessStream *)

- ea: `0x180016ce0`
- end: `0x180016fba`
- name: `?ReadShortTermLicense@TemporaryPolicy@Unit@SDK@@UEAA?AV?$shared_ptr@VSmoothEntry@SDK@@@std@@PEAUIRandomAccessStream@Streams@Storage@Windows@ABI@@@Z`
- size: `730`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callees

- `0x180003180`
- `0x1800031a4`
- `0x180003580`
- `0x18000358c`
- `0x180003d30`
- `0x180003d3c`
- `0x180015e20`
- `0x180016ce0`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180016da7`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180016da7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016dc2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016dc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SDK::Unit::TemporaryPolicy::ReadShortTermLicense(__int64 a1, __int64 a2, __int64 a3)
{
  const WCHAR *v6; // rcx
  WCHAR *v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  _DWORD *v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rbx
  _DWORD *v14; // rax
  volatile signed __int32 *v15; // rbx
  HRESULT v16; // eax
  HSTRING v17; // rcx
  __int64 v19; // [rsp+28h] [rbp-41h] BYREF
  __int128 v20; // [rsp+30h] [rbp-39h] BYREF
  PCNZWCH sourceString[2]; // [rsp+40h] [rbp-29h] BYREF
  UINT32 length[4]; // [rsp+50h] [rbp-19h]
  _DWORD *v23; // [rsp+60h] [rbp-9h]
  __int128 *v24; // [rsp+68h] [rbp-1h]
  __int64 v25; // [rsp+70h] [rbp+7h]
  HSTRING string; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+80h] [rbp+17h] BYREF
  __int64 v28; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v29; // [rsp+90h] [rbp+27h] BYREF

  v25 = a2;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  v29 = 0;
  string = 0;
  *(_OWORD *)sourceString = 0;
  *(_OWORD *)length = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)sourceString, L"Windows.Data.Pdf.PdfDocument", 0x1Cu);
  string = 0;
  v6 = (const WCHAR *)sourceString;
  if ( *(_QWORD *)&length[2] >= 8u )
    v6 = sourceString[0];
  WindowsCreateString_0(v6, length[0], &string);
  if ( *(_QWORD *)&length[2] >= 8u )
  {
    v7 = (WCHAR *)sourceString[0];
    if ( (unsigned __int64)(2LL * *(_QWORD *)&length[2] + 2) >= 0x1000 )
    {
      v7 = (WCHAR *)*((_QWORD *)sourceString[0] - 1);
      if ( (unsigned __int64)((char *)sourceString[0] - (char *)v7 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v7, 2LL * *(_QWORD *)&length[2] + 41);
        __debugbreak();
      }
    }
    operator delete(v7);
  }
  if ( !(unsigned int)RoGetActivationFactory(string, &GUID_433a0b5f_c007_4788_90f2_08143d922599, &v29) && v29 )
  {
    v28 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v29 + 64LL))(v29, a3, &v28);
    v9 = v28;
    if ( !v8 && v28 )
    {
      v27 = 0;
      while ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 64LL))(v9, &v27) == -2147483634 )
        v9 = v28;
      v10 = v27;
      if ( v27 )
      {
        v11 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
        v23 = v11;
        if ( v11 )
        {
          v24 = &v20;
          v20 = 0;
          v12 = *(_QWORD *)(a1 + 16);
          if ( v12 )
            _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
          v20 = *(_OWORD *)(a1 + 8);
          v19 = v27;
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
          v13 = SDK::Unit::CoordinatedException::CoordinatedException((__int64)v11, &v19, &v20);
        }
        else
        {
          v13 = 0;
        }
        v24 = (__int128 *)v13;
        v14 = operator new(0x18u);
        v23 = v14;
        if ( v14 )
        {
          *(_OWORD *)v14 = 0;
          v14[2] = 1;
          v14[3] = 1;
          *(_QWORD *)v14 = &std::_Ref_count<SDK::Unit::CoordinatedException>::`vftable';
          *((_QWORD *)v14 + 2) = v13;
        }
        else
        {
          v14 = 0;
        }
        *(_QWORD *)a2 = v13;
        v15 = *(volatile signed __int32 **)(a2 + 8);
        *(_QWORD *)(a2 + 8) = v14;
        if ( v15 )
        {
          if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
            if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
          }
        }
        v10 = v27;
      }
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v9 = v28;
    }
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v16 = WindowsDeleteString_0(string);
  v17 = string;
  if ( !v16 )
    v17 = 0;
  string = v17;
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  return a2;
}

```

## disassembly

```asm
0x180016ce0  push    rbp
0x180016ce2  push    rbx
0x180016ce3  push    rsi
0x180016ce4  push    rdi
0x180016ce5  push    r14
0x180016ce7  lea     rbp, [rsp-37h]
0x180016cec  sub     rsp, 0A0h
0x180016cf3  mov     rax, cs:__security_cookie
0x180016cfa  xor     rax, rsp
0x180016cfd  mov     [rbp+57h+var_28], rax
0x180016d01  mov     rbx, r8
0x180016d04  mov     rsi, rdx
0x180016d07  mov     rdi, rcx
0x180016d0a  mov     [rbp+57h+var_50], rdx
0x180016d0e  xor     r14d, r14d
0x180016d11  mov     [rbp+57h+var_A0], r14d
0x180016d15  xorps   xmm0, xmm0
0x180016d18  movups  xmmword ptr [rdx], xmm0
0x180016d1b  mov     [rdx], r14
0x180016d1e  mov     [rdx+8], r14
0x180016d22  mov     [rbp+57h+var_A0], 1
0x180016d29  mov     [rbp+57h+var_30], r14
0x180016d2d  mov     [rbp+57h+string], r14
0x180016d31  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180016d35  xorps   xmm1, xmm1
0x180016d38  movdqu  xmmword ptr [rbp+57h+length], xmm1
0x180016d3d  lea     r8d, [r14+1Ch]
0x180016d41  lea     rdx, ?RuntimeClass_Windows_Data_Pdf_PdfDocument@@3QB_WB; "Windows.Data.Pdf.PdfDocument"
0x180016d48  lea     rcx, [rbp+57h+sourceString]
0x180016d4c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180016d51  mov     [rbp+57h+string], r14
0x180016d55  lea     rcx, [rbp+57h+sourceString]
0x180016d59  cmp     qword ptr [rbp+57h+length+8], 8
0x180016d5e  cmovnb  rcx, [rbp+57h+sourceString]; sourceString
0x180016d63  lea     r8, [rbp+57h+string]; string
0x180016d67  mov     edx, [rbp+57h+length]; length
0x180016d6a  call    WindowsCreateString_0
0x180016d6f  nop
0x180016d70  mov     rdx, qword ptr [rbp+57h+length+8]
0x180016d74  cmp     rdx, 8
0x180016d78  jb      short loc_180016DB3
0x180016d7a  lea     rdx, ds:2[rdx*2]
0x180016d82  mov     rcx, [rbp+57h+sourceString]; Block
0x180016d86  mov     rax, rcx
0x180016d89  cmp     rdx, 1000h
0x180016d90  jb      short loc_180016DAE
0x180016d92  add     rdx, 27h ; '''
0x180016d96  mov     rcx, [rcx-8]
0x180016d9a  sub     rax, rcx
0x180016d9d  add     rax, 0FFFFFFFFFFFFFFF8h
0x180016da1  cmp     rax, 1Fh
0x180016da5  jbe     short loc_180016DAE
0x180016da7  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180016dad  int     3; Trap to Debugger
0x180016dae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016db3  lea     r8, [rbp+57h+var_30]
0x180016db7  lea     rdx, _GUID_433a0b5f_c007_4788_90f2_08143d922599
0x180016dbe  mov     rcx, [rbp+57h+string]
0x180016dc2  call    cs:__imp_RoGetActivationFactory
0x180016dc8  test    eax, eax
0x180016dca  jnz     loc_180016F6E
0x180016dd0  mov     rcx, [rbp+57h+var_30]
0x180016dd4  test    rcx, rcx
0x180016dd7  jz      loc_180016F6E
0x180016ddd  mov     [rbp+57h+var_38], r14
0x180016de1  mov     rax, [rcx]
0x180016de4  lea     r8, [rbp+57h+var_38]
0x180016de8  mov     rdx, rbx
0x180016deb  mov     rax, [rax+40h]
0x180016def  call    cs:__guard_dispatch_icall_fptr
0x180016df5  mov     rcx, [rbp+57h+var_38]
0x180016df9  test    eax, eax
0x180016dfb  jnz     loc_180016F5B
0x180016e01  test    rcx, rcx
0x180016e04  jz      loc_180016F5B
0x180016e0a  mov     [rbp+57h+var_40], r14
0x180016e0e  xchg    ax, ax
0x180016e10  mov     rax, [rcx]
0x180016e13  lea     rdx, [rbp+57h+var_40]
0x180016e17  mov     rax, [rax+40h]
0x180016e1b  call    cs:__guard_dispatch_icall_fptr
0x180016e21  cmp     eax, 8000000Eh
0x180016e26  jnz     short loc_180016E2E
0x180016e28  mov     rcx, [rbp+57h+var_38]
0x180016e2c  jmp     short loc_180016E10
0x180016e2e  mov     rcx, [rbp+57h+var_40]
0x180016e32  test    rcx, rcx
0x180016e35  jz      loc_180016F44
0x180016e3b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016e42  mov     ecx, 58h ; 'X'; unsigned __int64
0x180016e47  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016e4c  mov     rbx, rax
0x180016e4f  mov     [rbp+57h+var_60], rax
0x180016e53  test    rax, rax
0x180016e56  jz      short loc_180016EB5
0x180016e58  lea     rax, [rbp+57h+var_90]
0x180016e5c  mov     [rbp+57h+var_58], rax
0x180016e60  xorps   xmm0, xmm0
0x180016e63  movdqu  [rbp+57h+var_90], xmm0
0x180016e68  mov     rax, [rdi+10h]
0x180016e6c  test    rax, rax
0x180016e6f  jz      short loc_180016E75
0x180016e71  lock inc dword ptr [rax+8]
0x180016e75  mov     rax, [rdi+8]
0x180016e79  mov     qword ptr [rbp+57h+var_90], rax
0x180016e7d  mov     rax, [rdi+10h]
0x180016e81  mov     qword ptr [rbp+57h+var_90+8], rax
0x180016e85  mov     rcx, [rbp+57h+var_40]
0x180016e89  mov     [rbp+57h+var_98], rcx
0x180016e8d  test    rcx, rcx
0x180016e90  jz      short loc_180016EA0
0x180016e92  mov     rax, [rcx]
0x180016e95  mov     rax, [rax+8]
0x180016e99  call    cs:__guard_dispatch_icall_fptr
0x180016e9f  nop
0x180016ea0  lea     r8, [rbp+57h+var_90]
0x180016ea4  lea     rdx, [rbp+57h+var_98]
0x180016ea8  mov     rcx, rbx
0x180016eab  call    ??0CoordinatedException@Unit@SDK@@QEAA@V?$SmartComPtr@UIPdfDocument@Pdf@Data@Windows@ABI@@@@V?$shared_ptr@VGeneralTime@SDK@@@std@@@Z; SDK::Unit::CoordinatedException::CoordinatedException(SmartComPtr<ABI::Windows::Data::Pdf::IPdfDocument>,std::shared_ptr<SDK::GeneralTime>)
0x180016eb0  mov     rbx, rax
0x180016eb3  jmp     short loc_180016EB8
0x180016eb5  mov     rbx, r14
0x180016eb8  mov     [rbp+57h+var_58], rbx
0x180016ebc  mov     ecx, 18h; Size
0x180016ec1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016ec6  mov     [rbp+57h+var_60], rax
0x180016eca  test    rax, rax
0x180016ecd  jz      short loc_180016EF3
0x180016ecf  xorps   xmm0, xmm0
0x180016ed2  movups  xmmword ptr [rax], xmm0
0x180016ed5  mov     dword ptr [rax+8], 1
0x180016edc  mov     dword ptr [rax+0Ch], 1
0x180016ee3  lea     rcx, ??_7?$_Ref_count@VCoordinatedException@Unit@SDK@@@std@@6B@; const std::_Ref_count<SDK::Unit::CoordinatedException>::`vftable'
0x180016eea  mov     [rax], rcx
0x180016eed  mov     [rax+10h], rbx
0x180016ef1  jmp     short loc_180016EF6
0x180016ef3  mov     rax, r14
0x180016ef6  mov     [rsi], rbx
0x180016ef9  mov     rbx, [rsi+8]
0x180016efd  mov     [rsi+8], rax
0x180016f01  test    rbx, rbx
0x180016f04  jz      short loc_180016F40
0x180016f06  mov     edi, 0FFFFFFFFh
0x180016f0b  mov     eax, edi
0x180016f0d  lock xadd [rbx+8], eax
0x180016f12  cmp     eax, 1
0x180016f15  jnz     short loc_180016F40
0x180016f17  mov     rax, [rbx]
0x180016f1a  mov     rcx, rbx
0x180016f1d  mov     rax, [rax]
0x180016f20  call    cs:__guard_dispatch_icall_fptr
0x180016f26  lock xadd [rbx+0Ch], edi
0x180016f2b  cmp     edi, 1
0x180016f2e  jnz     short loc_180016F40
0x180016f30  mov     rax, [rbx]
0x180016f33  mov     rcx, rbx
0x180016f36  mov     rax, [rax+8]
0x180016f3a  call    cs:__guard_dispatch_icall_fptr
0x180016f40  mov     rcx, [rbp+57h+var_40]
0x180016f44  test    rcx, rcx
0x180016f47  jz      short loc_180016F57
0x180016f49  mov     rax, [rcx]
0x180016f4c  mov     rax, [rax+10h]
0x180016f50  call    cs:__guard_dispatch_icall_fptr
0x180016f56  nop
0x180016f57  mov     rcx, [rbp+57h+var_38]
0x180016f5b  test    rcx, rcx
0x180016f5e  jz      short loc_180016F6E
0x180016f60  mov     rax, [rcx]
0x180016f63  mov     rax, [rax+10h]
0x180016f67  call    cs:__guard_dispatch_icall_fptr
0x180016f6d  nop
0x180016f6e  mov     rcx, [rbp+57h+string]; string
0x180016f72  call    WindowsDeleteString_0
0x180016f77  mov     rcx, [rbp+57h+string]
0x180016f7b  test    eax, eax
0x180016f7d  cmovz   rcx, r14
0x180016f81  mov     [rbp+57h+string], rcx
0x180016f85  mov     rcx, [rbp+57h+var_30]
0x180016f89  test    rcx, rcx
0x180016f8c  jz      short loc_180016F9C
0x180016f8e  mov     rdx, [rcx]
0x180016f91  mov     rax, [rdx+10h]
0x180016f95  call    cs:__guard_dispatch_icall_fptr
0x180016f9b  nop
0x180016f9c  mov     rax, rsi
0x180016f9f  mov     rcx, [rbp+57h+var_28]
0x180016fa3  xor     rcx, rsp; StackCookie
0x180016fa6  call    __security_check_cookie
0x180016fab  add     rsp, 0A0h
0x180016fb2  pop     r14
0x180016fb4  pop     rdi
0x180016fb5  pop     rsi
0x180016fb6  pop     rbx
0x180016fb7  pop     rbp
0x180016fb8  retn
```
