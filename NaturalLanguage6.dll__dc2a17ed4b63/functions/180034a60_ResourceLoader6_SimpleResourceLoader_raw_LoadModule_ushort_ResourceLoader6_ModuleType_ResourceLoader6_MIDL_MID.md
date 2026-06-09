# ResourceLoader6::SimpleResourceLoader::raw_LoadModule(ushort,ResourceLoader6::ModuleType,ResourceLoader6::__MIDL___MIDL_itf_ILoadResources_0006_0001_0001 *,void * *)

- ea: `0x180034a60`
- end: `0x180034c9a`
- name: `?raw_LoadModule@SimpleResourceLoader@ResourceLoader6@@UEAAJGW4ModuleType@2@PEAU__MIDL___MIDL_itf_ILoadResources_0006_0001_0001@2@PEAPEAX@Z`
- size: `570`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64, unsigned int, __int64, HMODULE *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180031b60`
- `0x180031b9c`
- `0x180031c0c`
- `0x1800325e8`
- `0x180034a60`
- `0x18003757c`
- `0x18004bf10`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034bbe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034bbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034b6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034b6f`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180034b80`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180034b80`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180034bd1`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180034bd1`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180034ba3`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180034ba3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180034bf2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180034bf2`

## pseudocode

```c
__int64 __fastcall ResourceLoader6::SimpleResourceLoader::raw_LoadModule(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned int a3,
        __int64 a4,
        HMODULE *a5)
{
  __int64 v5; // r14
  unsigned int v7; // r15d
  NaturalLanguageTelemetry *v9; // rcx
  __int64 v11; // rcx
  NaturalLanguageTelemetry *v12; // rcx
  __int64 v13; // rdx
  const WCHAR *v14; // rdi
  HANDLE CurrentProcess; // rax
  HMODULE Library; // rdi
  char v17; // r14
  const WCHAR *v18; // rcx
  __int64 v19; // rax
  unsigned int v20; // ebx
  __int64 v21; // rdx
  __int16 v22; // [rsp+40h] [rbp-88h] BYREF
  PVOID OldValue; // [rsp+48h] [rbp-80h] BYREF
  __int64 v24; // [rsp+50h] [rbp-78h]
  __int64 v25; // [rsp+58h] [rbp-70h]
  LPCWSTR lpLibFileName[3]; // [rsp+68h] [rbp-60h] BYREF
  unsigned __int64 v27; // [rsp+80h] [rbp-48h]

  v25 = -2;
  v5 = a4;
  v24 = a4;
  v7 = (unsigned __int16)a2;
  if ( a3 - 512 <= 3 && NaturalLanguageTelemetry::IsEnabled((unsigned __int8)a1, a2) )
  {
    wil::details::static_lazy<NaturalLanguageTelemetry>::get(
      a1,
      _lambda_8b38532d7f8164044ce71ba0dfe7148a_::_lambda_invoker_cdecl_);
    NaturalLanguageTelemetry::ResourceLoaderLoadLegacyComponent_(v9, v7, a3);
  }
  if ( !a5 )
    return 2147942487LL;
  if ( (a3 == 256 || a3 == 259) && NaturalLanguageTelemetry::IsEnabled((unsigned __int8)a1, a2) )
  {
    wil::details::static_lazy<NaturalLanguageTelemetry>::get(
      v11,
      _lambda_8b38532d7f8164044ce71ba0dfe7148a_::_lambda_invoker_cdecl_);
    NaturalLanguageTelemetry::LogLexiconLoadAttempt_(v12, v7);
  }
  (*(void (__fastcall **)(_QWORD *, LPCWSTR *, _QWORD, _QWORD, unsigned int, __int64))(*a1 + 128LL))(
    a1,
    lpLibFileName,
    (unsigned __int16)v7,
    0,
    a3,
    v5);
  if ( !lpLibFileName[2] )
    goto LABEL_30;
  if ( a3 == 259 )
  {
    v14 = (const WCHAR *)lpLibFileName;
    if ( v27 >= 8 )
      v14 = lpLibFileName[0];
    v22 = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !(unsigned int)IsWow64Process2(CurrentProcess, &v22, 0) )
    {
      Library = 0;
      goto LABEL_26;
    }
    OldValue = 0;
    if ( v22 )
    {
      v17 = 1;
      if ( !Wow64DisableWow64FsRedirection(&OldValue) )
      {
        Library = 0;
LABEL_22:
        v5 = v24;
        goto LABEL_26;
      }
    }
    else
    {
      v17 = 0;
    }
    Library = LoadLibraryExW(v14, 0, 0x22u);
    if ( v17 )
      Wow64RevertWow64FsRedirection(OldValue);
    goto LABEL_22;
  }
  v18 = (const WCHAR *)lpLibFileName;
  if ( v27 >= 8 )
    v18 = lpLibFileName[0];
  Library = LoadLibraryW(v18);
LABEL_26:
  *a5 = Library;
  if ( Library )
  {
    LOBYTE(v13) = 1;
    std::wstring::_Tidy(lpLibFileName, v13, 0);
    return 0;
  }
  if ( a1[1] )
  {
    v19 = _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->();
    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, HMODULE *))(*(_QWORD *)v19 + 80LL))(
            v19,
            (unsigned __int16)v7,
            a3,
            v5,
            a5);
    LOBYTE(v21) = 1;
    std::wstring::_Tidy(lpLibFileName, v21, 0);
    return v20;
  }
LABEL_30:
  LOBYTE(v13) = 1;
  std::wstring::_Tidy(lpLibFileName, v13, 0);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180034a60  push    rbx
0x180034a62  push    rsi
0x180034a63  push    rdi
0x180034a64  push    r12
0x180034a66  push    r13
0x180034a68  push    r14
0x180034a6a  push    r15
0x180034a6c  sub     rsp, 90h
0x180034a73  mov     [rsp+0C8h+var_70], 0FFFFFFFFFFFFFFFEh
0x180034a7c  mov     rax, cs:__security_cookie
0x180034a83  xor     rax, rsp
0x180034a86  mov     [rsp+0C8h+var_40], rax
0x180034a8e  mov     r14, r9
0x180034a91  mov     [rsp+0C8h+var_78], r9
0x180034a96  mov     esi, r8d
0x180034a99  movzx   r15d, dx
0x180034a9d  mov     r12, rcx
0x180034aa0  mov     r13, [rsp+0C8h+arg_20]
0x180034aa8  lea     eax, [r8-200h]
0x180034aaf  cmp     eax, 3
0x180034ab2  ja      short loc_180034AD8
0x180034ab4  call    ?IsEnabled@NaturalLanguageTelemetry@@SA_NE_K@Z; NaturalLanguageTelemetry::IsEnabled(uchar,unsigned __int64)
0x180034ab9  xor     ebx, ebx
0x180034abb  test    al, al
0x180034abd  jz      short loc_180034ADA
0x180034abf  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8b38532d7f8164044ce71ba0dfe7148a_@@CA@XZ; _lambda_8b38532d7f8164044ce71ba0dfe7148a_::_lambda_invoker_cdecl_(void)
0x180034ac6  call    ?get@?$static_lazy@VNaturalLanguageTelemetry@@@details@wil@@QEAAPEAVNaturalLanguageTelemetry@@P6AXXZ@Z; wil::details::static_lazy<NaturalLanguageTelemetry>::get(void (*)(void))
0x180034acb  mov     edx, r15d; unsigned int
0x180034ace  mov     r8d, esi; unsigned int
0x180034ad1  call    ?ResourceLoaderLoadLegacyComponent_@NaturalLanguageTelemetry@@QEBAXKK@Z; NaturalLanguageTelemetry::ResourceLoaderLoadLegacyComponent_(ulong,ulong)
0x180034ad6  jmp     short loc_180034ADA
0x180034ad8  xor     ebx, ebx
0x180034ada  test    r13, r13
0x180034add  jnz     short loc_180034AE9
0x180034adf  mov     eax, 80070057h
0x180034ae4  jmp     loc_180034C71
0x180034ae9  cmp     esi, 100h
0x180034aef  jz      short loc_180034AF9
0x180034af1  cmp     esi, 103h
0x180034af7  jnz     short loc_180034B16
0x180034af9  call    ?IsEnabled@NaturalLanguageTelemetry@@SA_NE_K@Z; NaturalLanguageTelemetry::IsEnabled(uchar,unsigned __int64)
0x180034afe  test    al, al
0x180034b00  jz      short loc_180034B16
0x180034b02  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8b38532d7f8164044ce71ba0dfe7148a_@@CA@XZ; _lambda_8b38532d7f8164044ce71ba0dfe7148a_::_lambda_invoker_cdecl_(void)
0x180034b09  call    ?get@?$static_lazy@VNaturalLanguageTelemetry@@@details@wil@@QEAAPEAVNaturalLanguageTelemetry@@P6AXXZ@Z; wil::details::static_lazy<NaturalLanguageTelemetry>::get(void (*)(void))
0x180034b0e  mov     edx, r15d; unsigned int
0x180034b11  call    ?LogLexiconLoadAttempt_@NaturalLanguageTelemetry@@QEBAXK@Z; NaturalLanguageTelemetry::LogLexiconLoadAttempt_(ulong)
0x180034b16  mov     rax, [r12]
0x180034b1a  mov     [rsp+0C8h+var_A0], r14
0x180034b1f  mov     dword ptr [rsp+0C8h+var_A8], esi
0x180034b23  xor     r9d, r9d
0x180034b26  movzx   r8d, r15w
0x180034b2a  lea     rdx, [rsp+0C8h+lpLibFileName]
0x180034b2f  mov     rcx, r12
0x180034b32  mov     rax, [rax+80h]
0x180034b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b3e  nop
0x180034b3f  cmp     [rsp+0C8h+var_50], rbx
0x180034b44  jz      loc_180034C5C
0x180034b4a  cmp     esi, 103h
0x180034b50  jnz     loc_180034BDE
0x180034b56  lea     rdi, [rsp+0C8h+lpLibFileName]
0x180034b5b  cmp     [rsp+0C8h+var_48], 8
0x180034b64  cmovnb  rdi, [rsp+0C8h+lpLibFileName]
0x180034b6a  mov     [rsp+0C8h+var_88], bx
0x180034b6f  call    cs:__imp_GetCurrentProcess
0x180034b75  mov     rcx, rax
0x180034b78  xor     r8d, r8d
0x180034b7b  lea     rdx, [rsp+0C8h+var_88]
0x180034b80  call    cs:__imp_IsWow64Process2
0x180034b86  test    eax, eax
0x180034b88  jnz     short loc_180034B8F
0x180034b8a  mov     rdi, rbx
0x180034b8d  jmp     short loc_180034BFB
0x180034b8f  mov     [rsp+0C8h+OldValue], rbx
0x180034b94  cmp     [rsp+0C8h+var_88], bx
0x180034b99  jz      short loc_180034BB2
0x180034b9b  mov     r14b, 1
0x180034b9e  lea     rcx, [rsp+0C8h+OldValue]; OldValue
0x180034ba3  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180034ba9  test    eax, eax
0x180034bab  jnz     short loc_180034BB5
0x180034bad  mov     rdi, rbx
0x180034bb0  jmp     short loc_180034BD7
0x180034bb2  mov     r14b, bl
0x180034bb5  xor     edx, edx; hFile
0x180034bb7  lea     r8d, [rdx+22h]; dwFlags
0x180034bbb  mov     rcx, rdi; lpLibFileName
0x180034bbe  call    cs:__imp_LoadLibraryExW
0x180034bc4  mov     rdi, rax
0x180034bc7  test    r14b, r14b
0x180034bca  jz      short loc_180034BD7
0x180034bcc  mov     rcx, [rsp+0C8h+OldValue]; OlValue
0x180034bd1  call    cs:__imp_Wow64RevertWow64FsRedirection
0x180034bd7  mov     r14, [rsp+0C8h+var_78]
0x180034bdc  jmp     short loc_180034BFB
0x180034bde  lea     rcx, [rsp+0C8h+lpLibFileName]
0x180034be3  cmp     [rsp+0C8h+var_48], 8
0x180034bec  cmovnb  rcx, [rsp+0C8h+lpLibFileName]; lpLibFileName
0x180034bf2  call    cs:__imp_LoadLibraryW
0x180034bf8  mov     rdi, rax
0x180034bfb  mov     [r13+0], rdi
0x180034bff  test    rdi, rdi
0x180034c02  jz      short loc_180034C17
0x180034c04  xor     r8d, r8d
0x180034c07  mov     dl, 1
0x180034c09  lea     rcx, [rsp+0C8h+lpLibFileName]
0x180034c0e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180034c13  xor     eax, eax
0x180034c15  jmp     short loc_180034C71
0x180034c17  lea     rcx, [r12+8]
0x180034c1c  cmp     [rcx], rbx
0x180034c1f  jz      short loc_180034C5C
0x180034c21  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x180034c26  mov     r10, rax
0x180034c29  mov     rcx, [rax]
0x180034c2c  mov     rax, [rcx+50h]
0x180034c30  mov     [rsp+0C8h+var_A8], r13
0x180034c35  mov     r9, r14
0x180034c38  mov     r8d, esi
0x180034c3b  movzx   edx, r15w
0x180034c3f  mov     rcx, r10
0x180034c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c47  mov     ebx, eax
0x180034c49  xor     r8d, r8d
0x180034c4c  mov     dl, 1
0x180034c4e  lea     rcx, [rsp+0C8h+lpLibFileName]
0x180034c53  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180034c58  mov     eax, ebx
0x180034c5a  jmp     short loc_180034C71
0x180034c5c  xor     r8d, r8d
0x180034c5f  mov     dl, 1
0x180034c61  lea     rcx, [rsp+0C8h+lpLibFileName]
0x180034c66  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180034c6b  nop
0x180034c6c  mov     eax, 80004005h
0x180034c71  mov     rcx, [rsp+0C8h+var_40]
0x180034c79  xor     rcx, rsp; StackCookie
0x180034c7c  call    __security_check_cookie
0x180034c81  add     rsp, 90h
0x180034c88  pop     r15
0x180034c8a  pop     r14
0x180034c8c  pop     r13
0x180034c8e  pop     r12
0x180034c90  pop     rdi
0x180034c91  pop     rsi
0x180034c92  pop     rbx
0x180034c93  retn
0x180034c94  mov     eax, dword ptr [rsp+0C8h+var_88]
0x180034c98  jmp     short loc_180034C71
```
