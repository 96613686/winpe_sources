# CSyncRootManagerCache::GetCustomStatesAndStateHandler(ushort const *,_GUID const &,Microsoft::WRL::ComPtr<Windows::Storage::Provider::IStorageProviderItemPropertySource> &,bool *,Windows::Foundation::Collections::IIterable<Windows::Storage::Provider::StorageProviderItemProperty *> * *)

- ea: `0x180005708`
- end: `0x180005936`
- name: `?GetCustomStatesAndStateHandler@CSyncRootManagerCache@@AEAAJPEBGAEBU_GUID@@AEAV?$ComPtr@UIStorageProviderItemPropertySource@Provider@Storage@Windows@@@WRL@Microsoft@@PEA_NPEAPEAU?$IIterable@PEAVStorageProviderItemProperty@Provider@Storage@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800046ec`

## callees

- `0x1800049a0`
- `0x180004a54`
- `0x180005708`
- `0x180006c54`
- `0x1800077c8`
- `0x1800192a0`
- `0x180037780`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005820`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005879`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005820`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005879`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800057a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800057a8`

## string_xrefs

- `0x180005858`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180005917`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSyncRootManagerCache::GetCustomStatesAndStateHandler(
        __int64 a1,
        const WCHAR *a2,
        const struct _GUID *a3,
        struct Windows::Storage::Provider::IStorageProviderItemPropertySource **a4,
        _BYTE *a5,
        struct Windows::Storage::Provider::IStorageProviderItemPropertySource **a6)
{
  struct Windows::Storage::Provider::IStorageProviderItemPropertySource *v9; // r12
  unsigned __int64 v10; // rbx
  unsigned int v11; // eax
  UINT32 v12; // edx
  HRESULT v13; // eax
  int v14; // ebx
  __int64 result; // rax
  CSyncRootManagerCache *v16; // rcx
  CSyncRootManagerCache *v17; // rcx
  int ReinitializedCustomStateHandler; // eax
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  struct Windows::Storage::Provider::IStorageProviderItemPropertySource *v21; // rdi
  __int64 (__fastcall *v22)(struct Windows::Storage::Provider::IStorageProviderItemPropertySource *, _QWORD, struct Windows::Storage::Provider::IStorageProviderItemPropertySource **); // rbx
  __int64 v23; // rax
  int v24; // eax
  struct Windows::Storage::Provider::IStorageProviderItemPropertySource *v25; // [rsp+20h] [rbp-40h] BYREF
  __int64 v26; // [rsp+28h] [rbp-38h]
  const WCHAR *v27; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v27 = a2;
  v9 = 0;
  *a6 = 0;
  *a5 = 0;
  if ( !*a4 )
    goto LABEL_13;
  while ( 1 )
  {
    v25 = v9;
    v9 = *a4;
    v26 = *(_QWORD *)*a4;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v25);
    string = 0;
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    if ( v10 <= 0xFFFFFFFF )
    {
      v11 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v10);
      v12 = v11 - 1;
      if ( (unsigned int)v10 < v11 )
        v12 = v10;
      v13 = WindowsCreateStringReference(a2, v12, &hstringHeader, &string);
      if ( v13 < 0 )
      {
        RaiseException(v13, 1u, 0, 0);
        __debugbreak();
      }
      v14 = (*(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderItemPropertySource *, HSTRING, struct Windows::Storage::Provider::IStorageProviderItemPropertySource **))(v26 + 48))(
              v9,
              string,
              &v25);
      if ( *a5 || v14 != -2147023174 )
      {
        if ( v14 < 0 )
        {
          if ( v14 == -2147221021 )
          {
            v14 = -2147221021;
            goto LABEL_28;
          }
          v19 = (unsigned int)v14;
          v20 = 4628;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
            (const char *)v19,
            (int)v25);
LABEL_28:
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v25);
          return (unsigned int)v14;
        }
      }
      else
      {
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(a4);
        *a5 = 1;
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(a4);
        ReinitializedCustomStateHandler = CSyncRootManagerCache::GetReinitializedCustomStateHandler(v17, a3, a4);
        v14 = ReinitializedCustomStateHandler;
        if ( ReinitializedCustomStateHandler < 0 )
        {
          v19 = (unsigned int)ReinitializedCustomStateHandler;
          v20 = 4622;
          goto LABEL_27;
        }
        v21 = *a4;
        v22 = *(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderItemPropertySource *, _QWORD, struct Windows::Storage::Provider::IStorageProviderItemPropertySource **))(*(_QWORD *)v21 + 48LL);
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v25);
        v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v27);
        v24 = v22(v21, *(_QWORD *)(v23 + 24), &v25);
        v14 = v24;
        if ( v24 < 0 )
        {
          v19 = (unsigned int)v24;
          v20 = 4623;
          goto LABEL_27;
        }
      }
      *a6 = v25;
      return 0;
    }
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_13:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(a4);
    v14 = CSyncRootManagerCache::GetReinitializedCustomStateHandler(v16, a3, a4);
    if ( v14 < 0 )
      break;
    *a5 = 1;
  }
  result = 2147746132LL;
  if ( v14 != -2147221164 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1202,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v14,
      (int)v25);
    return (unsigned int)v14;
  }
  return result;
}

```

## disassembly

```asm
0x180005708  mov     [rsp-38h+arg_0], rbx
0x18000570d  push    rbp
0x18000570e  push    rsi
0x18000570f  push    rdi
0x180005710  push    r12
0x180005712  push    r13
0x180005714  push    r14
0x180005716  push    r15
0x180005718  mov     rbp, rsp
0x18000571b  sub     rsp, 60h
0x18000571f  mov     rax, cs:__security_cookie
0x180005726  xor     rax, rsp
0x180005729  mov     [rbp+var_8], rax
0x18000572d  mov     rdi, r9
0x180005730  mov     r13, r8
0x180005733  mov     r14, rdx
0x180005736  mov     [rbp+var_30], rdx
0x18000573a  mov     rsi, [rbp+arg_20]
0x18000573e  mov     r15, [rbp+arg_28]
0x180005742  xor     r12d, r12d
0x180005745  mov     [r15], r12
0x180005748  mov     [rsi], r12b
0x18000574b  cmp     [r9], r12
0x18000574e  jz      loc_180005827
0x180005754  mov     [rbp+var_40], r12
0x180005758  mov     r12, [rdi]
0x18000575b  mov     rax, [r12]
0x18000575f  mov     [rbp+var_38], rax
0x180005763  lea     rcx, [rbp+var_40]
0x180005767  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18000576c  xor     eax, eax
0x18000576e  mov     [rbp+string], rax
0x180005772  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005776  inc     rbx
0x180005779  cmp     [r14+rbx*2], ax
0x18000577e  jnz     short loc_180005776
0x180005780  mov     eax, 0FFFFFFFFh
0x180005785  cmp     rbx, rax
0x180005788  ja      loc_180005811
0x18000578e  mov     ecx, ebx; unsigned int
0x180005790  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180005795  lea     edx, [rax-1]
0x180005798  cmp     ebx, eax
0x18000579a  cmovb   edx, ebx; length
0x18000579d  lea     r9, [rbp+string]; string
0x1800057a1  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800057a5  mov     rcx, r14; sourceString
0x1800057a8  call    cs:__imp_WindowsCreateStringReference
0x1800057ae  xor     r14d, r14d
0x1800057b1  test    eax, eax
0x1800057b3  js      loc_18000586D
0x1800057b9  lea     r8, [rbp+var_40]
0x1800057bd  mov     rdx, [rbp+string]
0x1800057c1  mov     rcx, r12
0x1800057c4  mov     rax, [rbp+var_38]
0x1800057c8  mov     rax, [rax+30h]
0x1800057cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057d1  mov     ebx, eax
0x1800057d3  cmp     [rsi], r14b
0x1800057d6  jz      loc_180005880
0x1800057dc  test    ebx, ebx
0x1800057de  js      loc_180005902
0x1800057e4  mov     rax, [rbp+var_40]
0x1800057e8  mov     [r15], rax
0x1800057eb  xor     eax, eax
0x1800057ed  mov     rcx, [rbp+var_8]
0x1800057f1  xor     rcx, rsp; StackCookie
0x1800057f4  call    __security_check_cookie
0x1800057f9  mov     rbx, [rsp+60h+arg_0]
0x180005801  add     rsp, 60h
0x180005805  pop     r15
0x180005807  pop     r14
0x180005809  pop     r13
0x18000580b  pop     r12
0x18000580d  pop     rdi
0x18000580e  pop     rsi
0x18000580f  pop     rbp
0x180005810  retn
0x180005811  xor     r9d, r9d; lpArguments
0x180005814  xor     r8d, r8d; nNumberOfArguments
0x180005817  lea     edx, [r9+1]; dwExceptionFlags
0x18000581b  mov     ecx, 80070216h; dwExceptionCode
0x180005820  call    cs:__imp_RaiseException
0x180005826  nop
0x180005827  mov     rcx, rdi
0x18000582a  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18000582f  mov     r8, rdi; struct Windows::Storage::Provider::IStorageProviderItemPropertySource **
0x180005832  mov     rdx, r13; struct _GUID *
0x180005835  call    ?GetReinitializedCustomStateHandler@CSyncRootManagerCache@@AEAAJAEBU_GUID@@PEAPEAUIStorageProviderItemPropertySource@Provider@Storage@Windows@@@Z; CSyncRootManagerCache::GetReinitializedCustomStateHandler(_GUID const &,Windows::Storage::Provider::IStorageProviderItemPropertySource * *)
0x18000583a  mov     ebx, eax
0x18000583c  test    eax, eax
0x18000583e  js      short loc_180005848
0x180005840  mov     byte ptr [rsi], 1
0x180005843  jmp     loc_180005754
0x180005848  mov     eax, 80040154h
0x18000584d  cmp     ebx, eax
0x18000584f  jz      short loc_1800057ED
0x180005851  mov     rcx, [rbp+38h]; this
0x180005855  mov     r9d, ebx; char *
0x180005858  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000585f  mov     edx, 1202h; void *
0x180005864  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005869  mov     eax, ebx
0x18000586b  jmp     short loc_1800057ED
0x18000586d  xor     r9d, r9d; lpArguments
0x180005870  xor     r8d, r8d; nNumberOfArguments
0x180005873  lea     edx, [r9+1]; dwExceptionFlags
0x180005877  mov     ecx, eax; dwExceptionCode
0x180005879  call    cs:__imp_RaiseException
0x18000587f  int     3; Trap to Debugger
0x180005880  cmp     ebx, 800706BAh
0x180005886  jnz     loc_1800057DC
0x18000588c  mov     rcx, rdi
0x18000588f  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180005894  mov     byte ptr [rsi], 1
0x180005897  mov     rcx, rdi
0x18000589a  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18000589f  mov     r8, rdi; struct Windows::Storage::Provider::IStorageProviderItemPropertySource **
0x1800058a2  mov     rdx, r13; struct _GUID *
0x1800058a5  call    ?GetReinitializedCustomStateHandler@CSyncRootManagerCache@@AEAAJAEBU_GUID@@PEAPEAUIStorageProviderItemPropertySource@Provider@Storage@Windows@@@Z; CSyncRootManagerCache::GetReinitializedCustomStateHandler(_GUID const &,Windows::Storage::Provider::IStorageProviderItemPropertySource * *)
0x1800058aa  mov     ebx, eax
0x1800058ac  test    eax, eax
0x1800058ae  jns     short loc_1800058BA
0x1800058b0  mov     r9d, eax
0x1800058b3  mov     edx, 120Eh
0x1800058b8  jmp     short loc_180005917
0x1800058ba  mov     rdi, [rdi]
0x1800058bd  mov     rax, [rdi]
0x1800058c0  mov     rbx, [rax+30h]
0x1800058c4  lea     rcx, [rbp+var_40]
0x1800058c8  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800058cd  lea     rdx, [rbp+var_30]
0x1800058d1  lea     rcx, [rbp+hstringHeader]
0x1800058d5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800058da  nop
0x1800058db  lea     r8, [rbp+var_40]
0x1800058df  mov     rdx, [rax+18h]
0x1800058e3  mov     rcx, rdi
0x1800058e6  mov     rax, rbx
0x1800058e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ee  mov     ebx, eax
0x1800058f0  test    eax, eax
0x1800058f2  jns     loc_1800057E4
0x1800058f8  mov     r9d, eax
0x1800058fb  mov     edx, 120Fh
0x180005900  jmp     short loc_180005917
0x180005902  mov     eax, 800401E3h
0x180005907  cmp     ebx, eax
0x180005909  jnz     short loc_18000590F
0x18000590b  mov     ebx, eax
0x18000590d  jmp     short loc_180005928
0x18000590f  mov     r9d, ebx; char *
0x180005912  mov     edx, 1214h; void *
0x180005917  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000591e  mov     rcx, [rbp+38h]; this
0x180005922  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005927  nop
0x180005928  lea     rcx, [rbp+var_40]
0x18000592c  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180005931  jmp     loc_180005869
```
