# wprt::proc::impl::WindowsPrinterProcessor::SubmitJob(HSTRING__ *,ABI::Windows::Storage::Streams::IRandomAccessStream *,ABI::Windows::Storage::Streams::IRandomAccessStream *)

- ea: `0x180005110`
- end: `0x180005503`
- name: `?SubmitJob@WindowsPrinterProcessor@impl@proc@wprt@@UEAAXPEAUHSTRING__@@PEAUIRandomAccessStream@Streams@Storage@Windows@ABI@@1@Z`
- size: `1011`
- prototype: `void __fastcall(wprt::proc::impl::WindowsPrinterProcessor *__hidden this, HSTRING, struct ABI::Windows::Storage::Streams::IRandomAccessStream *, struct ABI::Windows::Storage::Streams::IRandomAccessStream *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003d30`
- `0x180003d3c`
- `0x180004940`
- `0x180004f80`
- `0x180005110`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800051e0`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800052ec`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800051e0`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800052ec`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180005318`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180005318`

## string_xrefs

- `0x180005286`: `Windows.Storage.Streams.RandomAccessStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall wprt::proc::impl::WindowsPrinterProcessor::SubmitJob(
        wprt::proc::impl::WindowsPrinterProcessor *this,
        HSTRING a2,
        struct ABI::Windows::Storage::Streams::IRandomAccessStream *a3,
        struct ABI::Windows::Storage::Streams::IRandomAccessStream *a4)
{
  __int64 v7; // rbx
  const WCHAR *v8; // rcx
  WCHAR *v9; // rcx
  const WCHAR *v10; // rcx
  WCHAR *v11; // rcx
  PCNZWCH sourceString[2]; // [rsp+40h] [rbp-59h] BYREF
  UINT32 length[4]; // [rsp+50h] [rbp-49h]
  __int64 v14; // [rsp+60h] [rbp-39h] BYREF
  HSTRING v15; // [rsp+68h] [rbp-31h] BYREF
  __int64 v16; // [rsp+70h] [rbp-29h] BYREF
  __int64 v17; // [rsp+78h] [rbp-21h] BYREF
  __int64 v18; // [rsp+80h] [rbp-19h] BYREF
  __int64 v19; // [rsp+88h] [rbp-11h] BYREF
  __int64 v20; // [rsp+90h] [rbp-9h] BYREF
  HSTRING string; // [rsp+98h] [rbp-1h] BYREF
  __int64 v22; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v23; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v24; // [rsp+B0h] [rbp+17h] BYREF
  _BYTE v25[8]; // [rsp+B8h] [rbp+1Fh] BYREF

  v7 = 0;
  v22 = 0;
  if ( a3 && a4 )
  {
    if ( (unsigned __int8)wprt::proc::impl::WindowsPrinterProcessor::GetPassThroughProvider(this, &v22) )
    {
      string = 0;
      *(_OWORD *)sourceString = 0;
      *(_OWORD *)length = 0;
      std::wstring::_Construct<1,wchar_t const *>(sourceString, L"Job Name");
      string = 0;
      v8 = (const WCHAR *)sourceString;
      if ( *(_QWORD *)&length[2] >= 8u )
        v8 = sourceString[0];
      WindowsCreateString_0(v8, length[0], &string);
      if ( *(_QWORD *)&length[2] >= 8u )
      {
        v9 = (WCHAR *)sourceString[0];
        if ( (unsigned __int64)(2LL * *(_QWORD *)&length[2] + 2) >= 0x1000 )
        {
          v9 = (WCHAR *)*((_QWORD *)sourceString[0] - 1);
          if ( (unsigned __int64)((char *)sourceString[0] - (char *)v9 - 8) > 0x1F )
          {
            _o__invalid_parameter_noinfo_noreturn(v9, 2LL * *(_QWORD *)&length[2] + 41);
            __debugbreak();
          }
        }
        operator delete(v9);
      }
      v20 = 0;
      v19 = 0;
      v18 = 0;
      v17 = 0;
      v14 = 0;
      v16 = 0;
      if ( (int)SetPageConfiguration(&v17) >= 0
        && (**(int (__fastcall ***)(struct ABI::Windows::Storage::Streams::IRandomAccessStream *, GUID *, __int64 *))a3)(
             a3,
             &GUID_905a0fe2_bc53_11df_8c49_001e4fc686da,
             &v20) >= 0
        && (*(int (__fastcall **)(__int64, HSTRING, HSTRING, __int64, __int64, __int64 *))(*(_QWORD *)v22 + 64LL))(
             v22,
             string,
             a2,
             v20,
             v17,
             &v14) >= 0 )
      {
        v15 = 0;
        *(_OWORD *)sourceString = 0;
        *(_OWORD *)length = 0;
        std::wstring::_Construct<1,wchar_t const *>(sourceString, L"Windows.Storage.Streams.RandomAccessStream");
        v15 = 0;
        v10 = (const WCHAR *)sourceString;
        if ( *(_QWORD *)&length[2] >= 8u )
          v10 = sourceString[0];
        WindowsCreateString_0(v10, length[0], &v15);
        if ( *(_QWORD *)&length[2] >= 8u )
        {
          v11 = (WCHAR *)sourceString[0];
          if ( (unsigned __int64)(2LL * *(_QWORD *)&length[2] + 2) >= 0x1000 )
          {
            v11 = (WCHAR *)*((_QWORD *)sourceString[0] - 1);
            if ( (unsigned __int64)((char *)sourceString[0] - (char *)v11 - 8) > 0x1F )
            {
              _o__invalid_parameter_noinfo_noreturn(v11, 2LL * *(_QWORD *)&length[2] + 41);
              __debugbreak();
            }
          }
          operator delete(v11);
        }
        *(__m128i *)length = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(sourceString[0]) = 0;
        if ( (int)RoGetActivationFactory(v15, &GUID_524cedcf_6e29_4ce5_9573_6b753db66c3a, &v16) >= 0
          && (**(int (__fastcall ***)(struct ABI::Windows::Storage::Streams::IRandomAccessStream *, GUID *, __int64 *))a4)(
               a4,
               &GUID_905a0fe2_bc53_11df_8c49_001e4fc686da,
               &v19) >= 0
          && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 56LL))(v14, &v18) >= 0 )
        {
          v24 = 0;
          if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v16 + 48LL))(
                 v16,
                 v19,
                 v18,
                 &v24) >= 0 )
          {
            while ( (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v24 + 80LL))(v24, v25) == -2147483634 )
              ;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 64LL))(v14);
            v23 = 0;
            if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v14)(
                   v14,
                   &GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e,
                   &v23) >= 0 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 48LL))(v23);
            if ( v23 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          }
          if ( v24 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        WindowsDeleteString_0(v15);
      }
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v16 = 0;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v14 = 0;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v17 = 0;
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v18 = 0;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v20 = 0;
      WindowsDeleteString_0(string);
    }
    v7 = v22;
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
}

```

## disassembly

```asm
0x180005110  push    rbp
0x180005112  push    rbx
0x180005113  push    rsi
0x180005114  push    rdi
0x180005115  push    r14
0x180005117  lea     rbp, [rsp-37h]
0x18000511c  sub     rsp, 0D0h
0x180005123  mov     rax, cs:__security_cookie
0x18000512a  xor     rax, rsp
0x18000512d  mov     [rbp+57h+var_30], rax
0x180005131  mov     rdi, r9
0x180005134  mov     rsi, r8
0x180005137  mov     r14, rdx
0x18000513a  xor     ebx, ebx
0x18000513c  mov     [rbp+57h+var_50], rbx
0x180005140  test    r8, r8
0x180005143  jz      loc_1800054D3
0x180005149  test    r9, r9
0x18000514c  jz      loc_1800054D3
0x180005152  lea     rdx, [rbp+57h+var_50]
0x180005156  call    ?GetPassThroughProvider@WindowsPrinterProcessor@impl@proc@wprt@@AEBA_NAEAV?$SmartComPtr@UIPdlPassthroughProvider@Printers@Devices@Windows@ABI@@@@@Z; wprt::proc::impl::WindowsPrinterProcessor::GetPassThroughProvider(SmartComPtr<ABI::Windows::Devices::Printers::IPdlPassthroughProvider> &)
0x18000515b  test    al, al
0x18000515d  jz      loc_1800054CF
0x180005163  mov     [rbp+57h+string], rbx
0x180005167  xorps   xmm0, xmm0
0x18000516a  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x18000516e  xorps   xmm1, xmm1
0x180005171  movdqu  xmmword ptr [rbp+57h+length], xmm1
0x180005176  lea     r8d, [rbx+8]
0x18000517a  lea     rdx, aJobName; "Job Name"
0x180005181  lea     rcx, [rbp+57h+sourceString]
0x180005185  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000518a  mov     [rbp+57h+string], rbx
0x18000518e  lea     rcx, [rbp+57h+sourceString]
0x180005192  cmp     qword ptr [rbp+57h+length+8], 8
0x180005197  cmovnb  rcx, [rbp+57h+sourceString]; sourceString
0x18000519c  lea     r8, [rbp+57h+string]; string
0x1800051a0  mov     edx, [rbp+57h+length]; length
0x1800051a3  call    WindowsCreateString_0
0x1800051a8  nop
0x1800051a9  mov     rdx, qword ptr [rbp+57h+length+8]
0x1800051ad  cmp     rdx, 8
0x1800051b1  jb      short loc_1800051EC
0x1800051b3  lea     rdx, ds:2[rdx*2]
0x1800051bb  mov     rcx, [rbp+57h+sourceString]; Block
0x1800051bf  mov     rax, rcx
0x1800051c2  cmp     rdx, 1000h
0x1800051c9  jb      short loc_1800051E7
0x1800051cb  add     rdx, 27h ; '''
0x1800051cf  mov     rcx, [rcx-8]
0x1800051d3  sub     rax, rcx
0x1800051d6  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800051da  cmp     rax, 1Fh
0x1800051de  jbe     short loc_1800051E7
0x1800051e0  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x1800051e6  int     3; Trap to Debugger
0x1800051e7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800051ec  mov     [rbp+57h+var_60], rbx
0x1800051f0  mov     [rbp+57h+var_68], rbx
0x1800051f4  mov     [rbp+57h+var_70], rbx
0x1800051f8  mov     [rbp+57h+var_78], rbx
0x1800051fc  mov     [rbp+57h+var_90], rbx
0x180005200  mov     [rbp+57h+var_80], rbx
0x180005204  lea     rcx, [rbp+57h+var_78]
0x180005208  call    ?SetPageConfiguration@@YAJAEAV?$SmartComPtr@UIPageConfigurationSettings@Printers@Devices@Windows@ABI@@@@@Z; SetPageConfiguration(SmartComPtr<ABI::Windows::Devices::Printers::IPageConfigurationSettings> &)
0x18000520d  test    eax, eax
0x18000520f  js      loc_18000542A
0x180005215  mov     rax, [rsi]
0x180005218  lea     r8, [rbp+57h+var_60]
0x18000521c  lea     rdx, _GUID_905a0fe2_bc53_11df_8c49_001e4fc686da
0x180005223  mov     rcx, rsi
0x180005226  mov     rax, [rax]
0x180005229  call    cs:__guard_dispatch_icall_fptr
0x18000522f  test    eax, eax
0x180005231  js      loc_18000542A
0x180005237  mov     rcx, [rbp+57h+var_50]
0x18000523b  mov     rax, [rcx]
0x18000523e  lea     rdx, [rbp+57h+var_90]
0x180005242  mov     [rsp+0F0h+var_C8], rdx
0x180005247  mov     rdx, [rbp+57h+var_78]
0x18000524b  mov     [rsp+0F0h+var_D0], rdx
0x180005250  mov     r9, [rbp+57h+var_60]
0x180005254  mov     r8, r14
0x180005257  mov     rdx, [rbp+57h+string]
0x18000525b  mov     rax, [rax+40h]
0x18000525f  call    cs:__guard_dispatch_icall_fptr
0x180005265  test    eax, eax
0x180005267  js      loc_18000542A
0x18000526d  mov     [rbp+57h+var_88], rbx
0x180005271  xorps   xmm0, xmm0
0x180005274  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180005278  xorps   xmm1, xmm1
0x18000527b  movdqu  xmmword ptr [rbp+57h+length], xmm1
0x180005280  mov     r8d, 2Ah ; '*'
0x180005286  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_RandomAccessStream@@3QB_WB; "Windows.Storage.Streams.RandomAccessStr"...
0x18000528d  lea     rcx, [rbp+57h+sourceString]
0x180005291  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005296  mov     [rbp+57h+var_88], rbx
0x18000529a  lea     rcx, [rbp+57h+sourceString]
0x18000529e  cmp     qword ptr [rbp+57h+length+8], 8
0x1800052a3  cmovnb  rcx, [rbp+57h+sourceString]; sourceString
0x1800052a8  lea     r8, [rbp+57h+var_88]; string
0x1800052ac  mov     edx, [rbp+57h+length]; length
0x1800052af  call    WindowsCreateString_0
0x1800052b4  nop
0x1800052b5  mov     rdx, qword ptr [rbp+57h+length+8]
0x1800052b9  cmp     rdx, 8
0x1800052bd  jb      short loc_1800052F8
0x1800052bf  lea     rdx, ds:2[rdx*2]
0x1800052c7  mov     rcx, [rbp+57h+sourceString]; Block
0x1800052cb  mov     rax, rcx
0x1800052ce  cmp     rdx, 1000h
0x1800052d5  jb      short loc_1800052F3
0x1800052d7  add     rdx, 27h ; '''
0x1800052db  mov     rcx, [rcx-8]
0x1800052df  sub     rax, rcx
0x1800052e2  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800052e6  cmp     rax, 1Fh
0x1800052ea  jbe     short loc_1800052F3
0x1800052ec  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x1800052f2  int     3; Trap to Debugger
0x1800052f3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800052f8  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180005300  movdqu  xmmword ptr [rbp+57h+length], xmm0
0x180005305  mov     word ptr [rbp+57h+sourceString], bx
0x180005309  lea     r8, [rbp+57h+var_80]
0x18000530d  lea     rdx, _GUID_524cedcf_6e29_4ce5_9573_6b753db66c3a
0x180005314  mov     rcx, [rbp+57h+var_88]
0x180005318  call    cs:__imp_RoGetActivationFactory
0x18000531e  test    eax, eax
0x180005320  js      loc_180005420
0x180005326  mov     rax, [rdi]
0x180005329  lea     r8, [rbp+57h+var_68]
0x18000532d  lea     rdx, _GUID_905a0fe2_bc53_11df_8c49_001e4fc686da
0x180005334  mov     rcx, rdi
0x180005337  mov     rax, [rax]
0x18000533a  call    cs:__guard_dispatch_icall_fptr
0x180005340  test    eax, eax
0x180005342  js      loc_180005420
0x180005348  mov     rcx, [rbp+57h+var_90]
0x18000534c  mov     rax, [rcx]
0x18000534f  lea     rdx, [rbp+57h+var_70]
0x180005353  mov     rax, [rax+38h]
0x180005357  call    cs:__guard_dispatch_icall_fptr
0x18000535d  test    eax, eax
0x18000535f  js      loc_180005420
0x180005365  mov     [rbp+57h+var_40], rbx
0x180005369  mov     rcx, [rbp+57h+var_80]
0x18000536d  mov     rax, [rcx]
0x180005370  lea     r9, [rbp+57h+var_40]
0x180005374  mov     r8, [rbp+57h+var_70]
0x180005378  mov     rdx, [rbp+57h+var_68]
0x18000537c  mov     rax, [rax+30h]
0x180005380  call    cs:__guard_dispatch_icall_fptr
0x180005386  test    eax, eax
0x180005388  js      loc_180005409
0x18000538e  xchg    ax, ax
0x180005390  mov     rcx, [rbp+57h+var_40]
0x180005394  mov     rax, [rcx]
0x180005397  lea     rdx, [rbp+57h+var_38]
0x18000539b  mov     rax, [rax+50h]
0x18000539f  call    cs:__guard_dispatch_icall_fptr
0x1800053a5  cmp     eax, 8000000Eh
0x1800053aa  jz      short loc_180005390
0x1800053ac  mov     rcx, [rbp+57h+var_90]
0x1800053b0  mov     rax, [rcx]
0x1800053b3  mov     rax, [rax+40h]
0x1800053b7  call    cs:__guard_dispatch_icall_fptr
0x1800053bd  mov     [rbp+57h+var_48], rbx
0x1800053c1  mov     rcx, [rbp+57h+var_90]
0x1800053c5  mov     rax, [rcx]
0x1800053c8  lea     r8, [rbp+57h+var_48]
0x1800053cc  lea     rdx, _GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e
0x1800053d3  mov     rax, [rax]
0x1800053d6  call    cs:__guard_dispatch_icall_fptr
0x1800053dc  test    eax, eax
0x1800053de  js      short loc_1800053F2
0x1800053e0  mov     rcx, [rbp+57h+var_48]
0x1800053e4  mov     rax, [rcx]
0x1800053e7  mov     rax, [rax+30h]
0x1800053eb  call    cs:__guard_dispatch_icall_fptr
0x1800053f1  nop
0x1800053f2  mov     rcx, [rbp+57h+var_48]
0x1800053f6  test    rcx, rcx
0x1800053f9  jz      short loc_180005409
0x1800053fb  mov     rax, [rcx]
0x1800053fe  mov     rax, [rax+10h]
0x180005402  call    cs:__guard_dispatch_icall_fptr
0x180005408  nop
0x180005409  mov     rcx, [rbp+57h+var_40]
0x18000540d  test    rcx, rcx
0x180005410  jz      short loc_180005420
0x180005412  mov     rax, [rcx]
0x180005415  mov     rax, [rax+10h]
0x180005419  call    cs:__guard_dispatch_icall_fptr
0x18000541f  nop
0x180005420  mov     rcx, [rbp+57h+var_88]; string
0x180005424  call    WindowsDeleteString_0
0x180005429  nop
0x18000542a  mov     rcx, [rbp+57h+var_80]
0x18000542e  test    rcx, rcx
0x180005431  jz      short loc_180005440
0x180005433  mov     rax, [rcx]
0x180005436  mov     rax, [rax+10h]
0x18000543a  call    cs:__guard_dispatch_icall_fptr
0x180005440  mov     [rbp+57h+var_80], rbx
0x180005444  mov     rcx, [rbp+57h+var_90]
0x180005448  test    rcx, rcx
0x18000544b  jz      short loc_18000545A
0x18000544d  mov     rax, [rcx]
0x180005450  mov     rax, [rax+10h]
0x180005454  call    cs:__guard_dispatch_icall_fptr
0x18000545a  mov     [rbp+57h+var_90], rbx
0x18000545e  mov     rcx, [rbp+57h+var_78]
0x180005462  test    rcx, rcx
0x180005465  jz      short loc_180005474
0x180005467  mov     rax, [rcx]
0x18000546a  mov     rax, [rax+10h]
0x18000546e  call    cs:__guard_dispatch_icall_fptr
0x180005474  mov     [rbp+57h+var_78], rbx
0x180005478  mov     rcx, [rbp+57h+var_70]
0x18000547c  test    rcx, rcx
0x18000547f  jz      short loc_18000548E
0x180005481  mov     rax, [rcx]
0x180005484  mov     rax, [rax+10h]
0x180005488  call    cs:__guard_dispatch_icall_fptr
0x18000548e  mov     [rbp+57h+var_70], rbx
0x180005492  mov     rcx, [rbp+57h+var_68]
0x180005496  test    rcx, rcx
0x180005499  jz      short loc_1800054A8
0x18000549b  mov     rax, [rcx]
0x18000549e  mov     rax, [rax+10h]
0x1800054a2  call    cs:__guard_dispatch_icall_fptr
0x1800054a8  mov     [rbp+57h+var_68], rbx
0x1800054ac  mov     rcx, [rbp+57h+var_60]
0x1800054b0  test    rcx, rcx
0x1800054b3  jz      short loc_1800054C2
0x1800054b5  mov     rax, [rcx]
0x1800054b8  mov     rax, [rax+10h]
0x1800054bc  call    cs:__guard_dispatch_icall_fptr
0x1800054c2  mov     [rbp+57h+var_60], rbx
0x1800054c6  mov     rcx, [rbp+57h+string]; string
0x1800054ca  call    WindowsDeleteString_0
0x1800054cf  mov     rbx, [rbp+57h+var_50]
0x1800054d3  test    rbx, rbx
0x1800054d6  jz      short loc_1800054E9
0x1800054d8  mov     rax, [rbx]
0x1800054db  mov     rcx, rbx
0x1800054de  mov     rax, [rax+10h]
0x1800054e2  call    cs:__guard_dispatch_icall_fptr
0x1800054e8  nop
0x1800054e9  mov     rcx, [rbp+57h+var_30]
0x1800054ed  xor     rcx, rsp; StackCookie
0x1800054f0  call    __security_check_cookie
0x1800054f5  add     rsp, 0D0h
0x1800054fc  pop     r14
0x1800054fe  pop     rdi
0x1800054ff  pop     rsi
0x180005500  pop     rbx
0x180005501  pop     rbp
0x180005502  retn
```
