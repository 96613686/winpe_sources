# CloudPrint::CloudPrintHelper::GetWebProviderError(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult> &,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IFindAllAccountsResult> &,ulong *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x1800179e8`
- end: `0x180017b8f`
- name: `?GetWebProviderError@CloudPrintHelper@CloudPrint@@KAJAEAV?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@UIFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@45@PEAKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, _DWORD *, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180013a2c`
- `0x180017b98`

## callees

- `0x1800067a4`
- `0x180009fc0`
- `0x18000c4cc`
- `0x18000e5e8`
- `0x180012700`
- `0x1800179e8`
- `0x18001bfe4`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017b3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017b3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017ae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017b27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017b5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017ae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017b27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017b5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CloudPrint::CloudPrintHelper::GetWebProviderError(__int64 *a1, __int64 *a2, _DWORD *a3, __int64 a4)
{
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v19; // rax
  __int64 v20; // rcx
  int v22[20]; // [rsp+20h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  __int64 v24; // [rsp+A0h] [rbp+30h] BYREF
  HSTRING string; // [rsp+B0h] [rbp+40h] BYREF

  CloudPrintHelperTelemetry::WatchCurrentThread(v22, "GetWebProviderError");
  *a3 = -2147467259;
  v24 = 0;
  v8 = *a1;
  if ( !*a1 )
  {
    v13 = *a2;
    if ( !*a2 )
      goto LABEL_14;
    v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v10 = v14(v13, &v24);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = 2314;
      goto LABEL_7;
    }
LABEL_8:
    if ( v24 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v24 + 48LL))(v24, a3);
      v11 = v10;
      if ( v10 < 0 )
      {
        v12 = 2320;
        goto LABEL_7;
      }
      string = 0;
      v15 = v24;
      v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 56LL);
      WindowsDeleteString(0);
      string = 0;
      v17 = v16(v15, &string);
      v11 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x913,
          (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
          (const char *)(unsigned int)v17,
          v22[0]);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_15;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v19 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
      std::wstring::_Assign<unsigned short>(a4, v20, v19);
      WindowsDeleteString(string);
    }
LABEL_14:
    v11 = 0;
    goto LABEL_15;
  }
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  v10 = v9(v8, &v24);
  v11 = v10;
  if ( v10 >= 0 )
    goto LABEL_8;
  v12 = 2310;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
    (const char *)(unsigned int)v10,
    v22[0]);
LABEL_15:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v22);
  return v11;
}

```

## disassembly

```asm
0x1800179e8  mov     [rsp-28h+arg_8], rbx
0x1800179ed  push    rbp
0x1800179ee  push    rsi
0x1800179ef  push    rdi
0x1800179f0  push    r14
0x1800179f2  push    r15
0x1800179f4  mov     rbp, rsp
0x1800179f7  sub     rsp, 70h
0x1800179fb  mov     r15, r9
0x1800179fe  mov     r14, r8
0x180017a01  mov     rsi, rdx
0x180017a04  mov     rbx, rcx
0x180017a07  lea     rdx, aGetwebprovider; "GetWebProviderError"
0x180017a0e  lea     rcx, [rbp+var_50]
0x180017a12  call    ?WatchCurrentThread@CloudPrintHelperTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CloudPrintHelperTelemetry::WatchCurrentThread(char const *)
0x180017a17  nop
0x180017a18  mov     dword ptr [r14], 80004005h
0x180017a1f  mov     [rbp+arg_0], 0
0x180017a27  mov     rdi, [rbx]
0x180017a2a  test    rdi, rdi
0x180017a2d  jz      short loc_180017A5B
0x180017a2f  mov     rax, [rdi]
0x180017a32  mov     rbx, [rax+40h]
0x180017a36  lea     rcx, [rbp+arg_0]
0x180017a3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017a3f  lea     rdx, [rbp+arg_0]
0x180017a43  mov     rcx, rdi
0x180017a46  mov     rax, rbx
0x180017a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a4e  mov     ebx, eax
0x180017a50  test    eax, eax
0x180017a52  jns     short loc_180017AA9
0x180017a54  mov     edx, 906h
0x180017a59  jmp     short loc_180017A91
0x180017a5b  mov     rdi, [rsi]
0x180017a5e  test    rdi, rdi
0x180017a61  jz      loc_180017B64
0x180017a67  mov     rax, [rdi]
0x180017a6a  mov     rbx, [rax+40h]
0x180017a6e  lea     rcx, [rbp+arg_0]
0x180017a72  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017a77  lea     rdx, [rbp+arg_0]
0x180017a7b  mov     rcx, rdi
0x180017a7e  mov     rax, rbx
0x180017a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a86  mov     ebx, eax
0x180017a88  test    eax, eax
0x180017a8a  jns     short loc_180017AA9
0x180017a8c  mov     edx, 90Ah; void *
0x180017a91  mov     rcx, [rbp+28h]; this
0x180017a95  mov     r9d, eax; char *
0x180017a98  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180017a9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017aa4  jmp     loc_180017B66
0x180017aa9  mov     rcx, [rbp+arg_0]
0x180017aad  test    rcx, rcx
0x180017ab0  jz      loc_180017B64
0x180017ab6  mov     rax, [rcx]
0x180017ab9  mov     rdx, r14
0x180017abc  mov     rax, [rax+30h]
0x180017ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ac5  mov     ebx, eax
0x180017ac7  test    eax, eax
0x180017ac9  jns     short loc_180017AD2
0x180017acb  mov     edx, 910h
0x180017ad0  jmp     short loc_180017A91
0x180017ad2  mov     [rbp+string], 0
0x180017ada  mov     rdi, [rbp+arg_0]
0x180017ade  mov     rax, [rdi]
0x180017ae1  mov     rbx, [rax+38h]
0x180017ae5  xor     ecx, ecx; string
0x180017ae7  call    cs:__imp_WindowsDeleteString
0x180017aed  mov     [rbp+string], 0
0x180017af5  lea     rdx, [rbp+string]
0x180017af9  mov     rcx, rdi
0x180017afc  mov     rax, rbx
0x180017aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b04  mov     ebx, eax
0x180017b06  test    eax, eax
0x180017b08  jns     short loc_180017B37
0x180017b0a  mov     rcx, [rbp+28h]; this
0x180017b0e  mov     r9d, eax; char *
0x180017b11  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180017b18  mov     edx, 913h; void *
0x180017b1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b22  nop
0x180017b23  mov     rcx, [rbp+string]; string
0x180017b27  call    cs:__imp_WindowsDeleteString
0x180017b2d  mov     [rbp+string], 0
0x180017b35  jmp     short loc_180017B66
0x180017b37  xor     edx, edx; length
0x180017b39  mov     rcx, [rbp+string]; string
0x180017b3d  call    cs:__imp_WindowsGetStringRawBuffer
0x180017b43  mov     rcx, rax
0x180017b46  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180017b4b  mov     r8, rax
0x180017b4e  mov     rdx, rcx
0x180017b51  mov     rcx, r15
0x180017b54  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180017b59  nop
0x180017b5a  mov     rcx, [rbp+string]; string
0x180017b5e  call    cs:__imp_WindowsDeleteString
0x180017b64  xor     ebx, ebx
0x180017b66  lea     rcx, [rbp+arg_0]
0x180017b6a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b6f  nop
0x180017b70  lea     rcx, [rbp+var_50]; this
0x180017b74  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180017b79  mov     eax, ebx
0x180017b7b  mov     rbx, [rsp+70h+arg_8]
0x180017b83  add     rsp, 70h
0x180017b87  pop     r15
0x180017b89  pop     r14
0x180017b8b  pop     rdi
0x180017b8c  pop     rsi
0x180017b8d  pop     rbp
0x180017b8e  retn
```
