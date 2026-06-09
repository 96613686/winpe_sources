# CSearchScopeSelectorService::_GetApplicationDisplayName(ushort const *,ushort * *)

- ea: `0x180025194`
- end: `0x180025286`
- name: `?_GetApplicationDisplayName@CSearchScopeSelectorService@@AEAAJPEBGPEAPEAG@Z`
- size: `242`
- prototype: `int(CSearchScopeSelectorService *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800245c0`

## callees

- `0x180007b3c`
- `0x18001f424`
- `0x180025194`
- `0x1800263d8`
- `0x180026454`
- `0x180039e6c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025254`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025254`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002522c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002522c`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800251f2`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800251f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSearchScopeSelectorService::_GetApplicationDisplayName(
        CSearchScopeSelectorService *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HRESULT DisplayNameProperty; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r9
  HSTRING string; // [rsp+40h] [rbp+8h] BYREF
  void *ppv; // [rsp+50h] [rbp+18h] BYREF

  string = (HSTRING)this;
  *a3 = 0;
  if ( (unsigned int)IsAppScope(a2) )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
    DisplayNameProperty = SHCreateItemInKnownFolder(
                            &FOLDERID_AppsFolder,
                            0x4000u,
                            a2,
                            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                            &ppv);
    if ( DisplayNameProperty >= 0 )
    {
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      DisplayNameProperty = GetDisplayNameProperty(ppv, &string);
      if ( DisplayNameProperty >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v9 = -1;
        do
          ++v9;
        while ( StringRawBuffer[v9] );
        DisplayNameProperty = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, StringRawBuffer);
      }
      WindowsDeleteString(string);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
  }
  else
  {
    return (unsigned int)GetDisplayNameForBuiltinAppId(a2, (unsigned __int16 *)a3);
  }
  return (unsigned int)DisplayNameProperty;
}

```

## disassembly

```asm
0x180025194  mov     [rsp+arg_8], rbx
0x180025199  mov     [rsp+arg_18], rsi
0x18002519e  mov     [rsp+string], rcx
0x1800251a3  push    rdi
0x1800251a4  sub     rsp, 30h
0x1800251a8  mov     rdi, r8
0x1800251ab  mov     rbx, rdx
0x1800251ae  xor     esi, esi
0x1800251b0  mov     [r8], rsi
0x1800251b3  mov     rcx, rdx; lpString1
0x1800251b6  call    IsAppScope
0x1800251bb  test    eax, eax
0x1800251bd  jz      loc_180025267
0x1800251c3  mov     [rsp+38h+arg_10], rsi
0x1800251c8  lea     rcx, [rsp+38h+arg_10]
0x1800251cd  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800251d2  lea     rax, [rsp+38h+arg_10]
0x1800251d7  mov     [rsp+38h+ppv], rax; ppv
0x1800251dc  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800251e3  mov     r8, rbx; pszItem
0x1800251e6  mov     edx, 4000h; dwKFFlags
0x1800251eb  lea     rcx, FOLDERID_AppsFolder; kfid
0x1800251f2  call    cs:__imp_SHCreateItemInKnownFolder
0x1800251f8  mov     ebx, eax
0x1800251fa  test    eax, eax
0x1800251fc  js      short loc_18002525B
0x1800251fe  mov     [rsp+38h+string], rsi
0x180025203  xor     ecx, ecx; string
0x180025205  call    cs:__imp_WindowsDeleteString
0x18002520b  mov     [rsp+38h+string], rsi
0x180025210  lea     rdx, [rsp+38h+string]
0x180025215  mov     rcx, [rsp+38h+arg_10]
0x18002521a  call    GetDisplayNameProperty
0x18002521f  mov     ebx, eax
0x180025221  test    eax, eax
0x180025223  js      short loc_18002524F
0x180025225  xor     edx, edx; length
0x180025227  mov     rcx, [rsp+38h+string]; string
0x18002522c  call    cs:__imp_WindowsGetStringRawBuffer
0x180025232  or      r9, 0FFFFFFFFFFFFFFFFh
0x180025236  inc     r9
0x180025239  cmp     [rax+r9*2], si
0x18002523e  jnz     short loc_180025236
0x180025240  mov     [rsp+38h+var_10], rdi
0x180025245  mov     r8, rax
0x180025248  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002524d  mov     ebx, eax
0x18002524f  mov     rcx, [rsp+38h+string]; string
0x180025254  call    cs:__imp_WindowsDeleteString
0x18002525a  nop
0x18002525b  lea     rcx, [rsp+38h+arg_10]
0x180025260  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180025265  jmp     short loc_180025274
0x180025267  mov     rdx, rdi; unsigned __int16 *
0x18002526a  mov     rcx, rbx; lpString2
0x18002526d  call    GetDisplayNameForBuiltinAppId
0x180025272  mov     ebx, eax
0x180025274  mov     eax, ebx
0x180025276  mov     rbx, [rsp+38h+arg_8]
0x18002527b  mov     rsi, [rsp+38h+arg_18]
0x180025280  add     rsp, 30h
0x180025284  pop     rdi
0x180025285  retn
```
