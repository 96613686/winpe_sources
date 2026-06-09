# PerformanceTraceHandler::GetFileToken(ushort const *,HSTRING__ * *)

- ea: `0x1800118d4`
- end: `0x180011a1e`
- name: `?GetFileToken@PerformanceTraceHandler@@AEAAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(PerformanceTraceHandler *__hidden this, const unsigned __int16 *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001124c`

## callees

- `0x180002c00`
- `0x180007f3c`
- `0x180010a6c`
- `0x1800118d4`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011975`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011975`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001195f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001195f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001198b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001198b`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller` at `0x180011912`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller` at `0x180011912`

## string_xrefs

- `0x180011958`: `Windows.ApplicationModel.DataTransfer.SharedStorageAccessManager`
- `0x180011925`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`
- `0x1800119c3`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`

## pseudocode

```c
__int64 __fastcall PerformanceTraceHandler::GetFileToken(
        PerformanceTraceHandler *this,
        const unsigned __int16 *a2,
        HSTRING *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  HRESULT v6; // eax
  int ActivationFactory; // eax
  __int64 v8; // rdx
  __int64 v10; // [rsp+20h] [rbp-40h] BYREF
  __int64 v11; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v11 = 0;
  v4 = CreateStorageItemFromPath_FullTrustCaller(a2, 0x2000, &GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea, &v11);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
      (const char *)(unsigned int)v4,
      v10);
LABEL_10:
    wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v11);
    return v5;
  }
  v10 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(
         L"Windows.ApplicationModel.DataTransfer.SharedStorageAccessManager",
         0x40u,
         &hstringHeader,
         &string);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_c6132ada_34b1_4849_bd5f_d09fee3158c5, &v10);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v8 = 210;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v10);
    wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v10);
    goto LABEL_10;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v10 + 48LL))(v10, v11, a3);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v8 = 211;
    goto LABEL_9;
  }
  wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v10);
  wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v11);
  return 0;
}

```

## disassembly

```asm
0x1800118d4  mov     [rsp-8+arg_0], rbx
0x1800118d9  mov     [rsp-8+arg_18], rdi
0x1800118de  push    rbp
0x1800118df  mov     rbp, rsp
0x1800118e2  sub     rsp, 60h
0x1800118e6  mov     rax, cs:__security_cookie
0x1800118ed  xor     rax, rsp
0x1800118f0  mov     [rbp+var_10], rax
0x1800118f4  mov     rdi, r8
0x1800118f7  mov     rcx, rdx
0x1800118fa  mov     [rbp+var_38], 0
0x180011902  lea     r9, [rbp+var_38]
0x180011906  lea     r8, _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea
0x18001190d  mov     edx, 2000h
0x180011912  call    cs:__imp_CreateStorageItemFromPath_FullTrustCaller
0x180011918  mov     ebx, eax
0x18001191a  test    eax, eax
0x18001191c  jns     short loc_18001193B
0x18001191e  mov     rcx, [rbp+8]; this
0x180011922  mov     r9d, eax; char *
0x180011925  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x18001192c  mov     edx, 0CFh; void *
0x180011931  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011936  jmp     loc_1800119DE
0x18001193b  mov     [rbp+var_40], 0
0x180011943  mov     [rbp+string], 0
0x18001194b  lea     r9, [rbp+string]; string
0x18001194f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180011953  mov     edx, 40h ; '@'; length
0x180011958  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_DataTransfer_SharedStorageAccessManager@@3QBGB; "Windows.ApplicationModel.DataTransfer.S"...
0x18001195f  call    cs:__imp_WindowsCreateStringReference
0x180011965  test    eax, eax
0x180011967  jns     short loc_18001197C
0x180011969  xor     r9d, r9d; lpArguments
0x18001196c  xor     r8d, r8d; nNumberOfArguments
0x18001196f  lea     edx, [r9+1]; dwExceptionFlags
0x180011973  mov     ecx, eax; dwExceptionCode
0x180011975  call    cs:__imp_RaiseException
0x18001197b  int     3; Trap to Debugger
0x18001197c  lea     r8, [rbp+var_40]
0x180011980  lea     rdx, _GUID_c6132ada_34b1_4849_bd5f_d09fee3158c5
0x180011987  mov     rcx, [rbp+string]
0x18001198b  call    cs:__imp_RoGetActivationFactory
0x180011991  mov     ebx, eax
0x180011993  test    eax, eax
0x180011995  jns     short loc_18001199E
0x180011997  mov     edx, 0D2h
0x18001199c  jmp     short loc_1800119C0
0x18001199e  mov     rcx, [rbp+var_40]
0x1800119a2  mov     rax, [rcx]
0x1800119a5  mov     r8, rdi
0x1800119a8  mov     rdx, [rbp+var_38]
0x1800119ac  mov     rax, [rax+30h]
0x1800119b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119b5  mov     ebx, eax
0x1800119b7  test    eax, eax
0x1800119b9  jns     short loc_1800119EB
0x1800119bb  mov     edx, 0D3h; void *
0x1800119c0  mov     r9d, eax; char *
0x1800119c3  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x1800119ca  mov     rcx, [rbp+8]; this
0x1800119ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800119d3  nop
0x1800119d4  lea     rcx, [rbp+var_40]
0x1800119d8  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x1800119dd  nop
0x1800119de  lea     rcx, [rbp+var_38]
0x1800119e2  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x1800119e7  mov     eax, ebx
0x1800119e9  jmp     short loc_180011A00
0x1800119eb  lea     rcx, [rbp+var_40]
0x1800119ef  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x1800119f4  nop
0x1800119f5  lea     rcx, [rbp+var_38]
0x1800119f9  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x1800119fe  xor     eax, eax
0x180011a00  mov     rcx, [rbp+var_10]
0x180011a04  xor     rcx, rsp; StackCookie
0x180011a07  call    __security_check_cookie
0x180011a0c  lea     r11, [rsp+60h+var_s0]
0x180011a11  mov     rbx, [r11+10h]
0x180011a15  mov     rdi, [r11+28h]
0x180011a19  mov     rsp, r11
0x180011a1c  pop     rbp
0x180011a1d  retn
```
