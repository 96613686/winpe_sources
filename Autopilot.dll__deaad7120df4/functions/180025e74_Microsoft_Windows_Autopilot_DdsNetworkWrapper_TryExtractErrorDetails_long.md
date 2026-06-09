# Microsoft::Windows::Autopilot::DdsNetworkWrapper::TryExtractErrorDetails(long &)

- ea: `0x180025e74`
- end: `0x180025f8a`
- name: `?TryExtractErrorDetails@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJAEAJ@Z`
- size: `278`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::DdsNetworkWrapper *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025f90`

## callees

- `0x180013580`
- `0x1800232dc`
- `0x180025590`
- `0x180025e74`
- `0x1800261a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025f03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025f72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025f03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025f72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025f34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025f34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025eee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025f5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025eee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025f5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::TryExtractErrorDetails(
        Microsoft::Windows::Autopilot::DdsNetworkWrapper *this,
        unsigned int *a2)
{
  int Data; // ebx
  void *v5; // rbx
  int ErrorFromResponse; // edi
  PCWSTR StringRawBuffer; // rax
  __int64 v8; // rcx
  LPVOID pv; // [rsp+20h] [rbp-18h] BYREF
  int cbMultiByte[4]; // [rsp+28h] [rbp-10h]
  HSTRING string; // [rsp+70h] [rbp+38h] BYREF

  pv = 0;
  *(_QWORD *)cbMultiByte = 0;
  Data = Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData((__int64)this, (__int64)&pv);
  if ( Data < 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)Data;
  }
  string = 0;
  v5 = pv;
  ErrorFromResponse = Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(
                        0xFDE9u,
                        (LPCCH)pv,
                        cbMultiByte[0],
                        &string);
  if ( ErrorFromResponse < 0 )
    goto LABEL_6;
  ErrorFromResponse = Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractErrorFromResponse((__int64)&string, a2);
  if ( ErrorFromResponse < 0 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      McTemplateU0dz_EventWriteTransfer(
        v8,
        AutopilotDownloadExtractErrorFailed,
        (unsigned int)ErrorFromResponse,
        StringRawBuffer);
    }
LABEL_6:
    if ( string )
      WindowsDeleteString(string);
    if ( v5 )
      CoTaskMemFree(v5);
    return (unsigned int)ErrorFromResponse;
  }
  if ( string )
    WindowsDeleteString(string);
  if ( v5 )
    CoTaskMemFree(v5);
  return 0;
}

```

## disassembly

```asm
0x180025e74  push    rbp
0x180025e76  push    rbx
0x180025e77  push    rsi
0x180025e78  push    rdi
0x180025e79  mov     rbp, rsp
0x180025e7c  sub     rsp, 38h
0x180025e80  mov     rsi, rdx
0x180025e83  mov     [rbp+pv], 0
0x180025e8b  mov     qword ptr [rbp+cbMultiByte], 0
0x180025e93  lea     rdx, [rbp+pv]
0x180025e97  call    ?RetrieveData@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)
0x180025e9c  mov     ebx, eax
0x180025e9e  test    eax, eax
0x180025ea0  jns     short loc_180025EBE
0x180025ea2  mov     rcx, [rbp+pv]; pv
0x180025ea6  test    rcx, rcx
0x180025ea9  jz      short loc_180025EB7
0x180025eab  call    cs:__imp_CoTaskMemFree
0x180025eb2  nop     dword ptr [rax+rax+00h]
0x180025eb7  mov     eax, ebx
0x180025eb9  jmp     loc_180025F80
0x180025ebe  mov     [rbp+string], 0
0x180025ec6  lea     r9, [rbp+string]; string
0x180025eca  mov     r8d, [rbp+cbMultiByte]; cbMultiByte
0x180025ece  mov     rbx, [rbp+pv]
0x180025ed2  mov     rdx, rbx; lpMultiByteStr
0x180025ed5  mov     ecx, 0FDE9h; CodePage
0x180025eda  call    ?ConvertRawBytesToString@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJIPEBDHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(uint,char const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180025edf  mov     edi, eax
0x180025ee1  test    eax, eax
0x180025ee3  jns     short loc_180025F13
0x180025ee5  mov     rcx, [rbp+string]; string
0x180025ee9  test    rcx, rcx
0x180025eec  jz      short loc_180025EFB
0x180025eee  call    cs:__imp_WindowsDeleteString
0x180025ef5  nop     dword ptr [rax+rax+00h]
0x180025efa  nop
0x180025efb  test    rbx, rbx
0x180025efe  jz      short loc_180025F0F
0x180025f00  mov     rcx, rbx; pv
0x180025f03  call    cs:__imp_CoTaskMemFree
0x180025f0a  nop     dword ptr [rax+rax+00h]
0x180025f0f  mov     eax, edi
0x180025f11  jmp     short loc_180025F80
0x180025f13  mov     rdx, rsi
0x180025f16  lea     rcx, [rbp+string]
0x180025f1a  call    ?ExtractErrorFromResponse@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAJ@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractErrorFromResponse(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,long &)
0x180025f1f  mov     edi, eax
0x180025f21  test    eax, eax
0x180025f23  jns     short loc_180025F54
0x180025f25  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180025f2c  jz      short loc_180025EE5
0x180025f2e  xor     edx, edx; length
0x180025f30  mov     rcx, [rbp+string]; string
0x180025f34  call    cs:__imp_WindowsGetStringRawBuffer
0x180025f3b  nop     dword ptr [rax+rax+00h]
0x180025f40  mov     r9, rax
0x180025f43  mov     r8d, edi
0x180025f46  lea     rdx, AutopilotDownloadExtractErrorFailed
0x180025f4d  call    McTemplateU0dz_EventWriteTransfer
0x180025f52  jmp     short loc_180025EE5
0x180025f54  mov     rcx, [rbp+string]; string
0x180025f58  test    rcx, rcx
0x180025f5b  jz      short loc_180025F6A
0x180025f5d  call    cs:__imp_WindowsDeleteString
0x180025f64  nop     dword ptr [rax+rax+00h]
0x180025f69  nop
0x180025f6a  test    rbx, rbx
0x180025f6d  jz      short loc_180025F7E
0x180025f6f  mov     rcx, rbx; pv
0x180025f72  call    cs:__imp_CoTaskMemFree
0x180025f79  nop     dword ptr [rax+rax+00h]
0x180025f7e  xor     eax, eax
0x180025f80  add     rsp, 38h
0x180025f84  pop     rdi
0x180025f85  pop     rsi
0x180025f86  pop     rbx
0x180025f87  pop     rbp
0x180025f88  retn
```
