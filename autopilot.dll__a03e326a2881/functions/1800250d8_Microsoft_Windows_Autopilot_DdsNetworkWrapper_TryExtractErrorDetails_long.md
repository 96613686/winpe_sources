# Microsoft::Windows::Autopilot::DdsNetworkWrapper::TryExtractErrorDetails(long &)

- ea: `0x1800250d8`
- end: `0x1800251c9`
- name: `?TryExtractErrorDetails@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJAEAJ@Z`
- size: `241`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::DdsNetworkWrapper *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800251d0`

## callees

- `0x1800132d8`
- `0x1800227dc`
- `0x1800248b0`
- `0x1800250d8`
- `0x1800253d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002510f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002515b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800251b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002510f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002515b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800251b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025186`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025186`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002514c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800251a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002514c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800251a9`

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
0x1800250d8  push    rbp
0x1800250da  push    rbx
0x1800250db  push    rsi
0x1800250dc  push    rdi
0x1800250dd  mov     rbp, rsp
0x1800250e0  sub     rsp, 38h
0x1800250e4  mov     rsi, rdx
0x1800250e7  mov     [rbp+pv], 0
0x1800250ef  mov     qword ptr [rbp+cbMultiByte], 0
0x1800250f7  lea     rdx, [rbp+pv]
0x1800250fb  call    ?RetrieveData@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJAEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &)
0x180025100  mov     ebx, eax
0x180025102  test    eax, eax
0x180025104  jns     short loc_18002511C
0x180025106  mov     rcx, [rbp+pv]; pv
0x18002510a  test    rcx, rcx
0x18002510d  jz      short loc_180025115
0x18002510f  call    cs:__imp_CoTaskMemFree
0x180025115  mov     eax, ebx
0x180025117  jmp     loc_1800251C0
0x18002511c  mov     [rbp+string], 0
0x180025124  lea     r9, [rbp+string]; string
0x180025128  mov     r8d, [rbp+cbMultiByte]; cbMultiByte
0x18002512c  mov     rbx, [rbp+pv]
0x180025130  mov     rdx, rbx; lpMultiByteStr
0x180025133  mov     ecx, 0FDE9h; CodePage
0x180025138  call    ?ConvertRawBytesToString@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJIPEBDHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(uint,char const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x18002513d  mov     edi, eax
0x18002513f  test    eax, eax
0x180025141  jns     short loc_180025165
0x180025143  mov     rcx, [rbp+string]; string
0x180025147  test    rcx, rcx
0x18002514a  jz      short loc_180025153
0x18002514c  call    cs:__imp_WindowsDeleteString
0x180025152  nop
0x180025153  test    rbx, rbx
0x180025156  jz      short loc_180025161
0x180025158  mov     rcx, rbx; pv
0x18002515b  call    cs:__imp_CoTaskMemFree
0x180025161  mov     eax, edi
0x180025163  jmp     short loc_1800251C0
0x180025165  mov     rdx, rsi
0x180025168  lea     rcx, [rbp+string]
0x18002516c  call    ?ExtractErrorFromResponse@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAJ@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractErrorFromResponse(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,long &)
0x180025171  mov     edi, eax
0x180025173  test    eax, eax
0x180025175  jns     short loc_1800251A0
0x180025177  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18002517e  jz      short loc_180025143
0x180025180  xor     edx, edx; length
0x180025182  mov     rcx, [rbp+string]; string
0x180025186  call    cs:__imp_WindowsGetStringRawBuffer
0x18002518c  mov     r9, rax
0x18002518f  mov     r8d, edi
0x180025192  lea     rdx, AutopilotDownloadExtractErrorFailed
0x180025199  call    McTemplateU0dz_EventWriteTransfer
0x18002519e  jmp     short loc_180025143
0x1800251a0  mov     rcx, [rbp+string]; string
0x1800251a4  test    rcx, rcx
0x1800251a7  jz      short loc_1800251B0
0x1800251a9  call    cs:__imp_WindowsDeleteString
0x1800251af  nop
0x1800251b0  test    rbx, rbx
0x1800251b3  jz      short loc_1800251BE
0x1800251b5  mov     rcx, rbx; pv
0x1800251b8  call    cs:__imp_CoTaskMemFree
0x1800251be  xor     eax, eax
0x1800251c0  add     rsp, 38h
0x1800251c4  pop     rdi
0x1800251c5  pop     rsi
0x1800251c6  pop     rbx
0x1800251c7  pop     rbp
0x1800251c8  retn
```
