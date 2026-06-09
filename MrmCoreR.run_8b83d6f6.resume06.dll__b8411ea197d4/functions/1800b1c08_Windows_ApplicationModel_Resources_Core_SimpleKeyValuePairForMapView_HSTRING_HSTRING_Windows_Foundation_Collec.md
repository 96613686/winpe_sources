# Windows::ApplicationModel::Resources::Core::SimpleKeyValuePairForMapView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::Make(HSTRING__ * const &,HSTRING__ * const &,Windows::ApplicationModel::Resources::Core::SimpleKeyValuePairForMapView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>> * *)

- ea: `0x1800b1c08`
- end: `0x1800b1d17`
- name: `?Make@?$SimpleKeyValuePairForMapView@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@@Core@Resources@ApplicationModel@Windows@@SAJAEBQEAUHSTRING__@@0PEAPEAV12345@@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b30c0`

## callees

- `0x18000892c`
- `0x180054bc8`
- `0x18007a360`
- `0x1800867dc`
- `0x1800aeda0`
- `0x1800b1c08`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b1cd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b1ce3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b1cd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b1ce3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::SimpleKeyValuePairForMapView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::Make(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  void *v4; // rax
  __int64 v5; // rdi
  int v6; // ebx
  HSTRING v7; // rcx
  HSTRING v8; // rcx
  HSTRING newString; // [rsp+20h] [rbp-10h] BYREF
  __int64 v11; // [rsp+28h] [rbp-8h] BYREF
  void *v12; // [rsp+60h] [rbp+30h] BYREF
  HSTRING string; // [rsp+68h] [rbp+38h] BYREF

  *a3 = 0;
  v11 = 0;
  v4 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v4;
  v5 = 0;
  if ( v4 )
  {
    v5 = Windows::ApplicationModel::Resources::Core::SimpleKeyValuePairForMapView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::SimpleKeyValuePairForMapView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(v4);
    v11 = v5;
    v12 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v12);
  if ( v5 )
  {
    LODWORD(v12) = 0;
    XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(&newString);
    v6 = (int)v12;
    if ( (int)v12 >= 0 )
    {
      XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(&string);
      v6 = (int)v12;
      if ( (int)v12 < 0 )
      {
        v8 = string;
      }
      else
      {
        v7 = *(HSTRING *)(v5 + 64);
        *(_QWORD *)(v5 + 64) = newString;
        newString = v7;
        v8 = *(HSTRING *)(v5 + 72);
        *(_QWORD *)(v5 + 72) = string;
        string = v8;
      }
      WindowsDeleteString(v8);
    }
    WindowsDeleteString(newString);
    if ( v6 >= 0 )
    {
      v11 = 0;
      *a3 = v5;
    }
  }
  else
  {
    v6 = -2147024882;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800b1c08  mov     [rsp-18h+arg_0], rbx
0x1800b1c0d  mov     [rsp-18h+arg_8], rsi
0x1800b1c12  push    rbp
0x1800b1c13  push    rdi
0x1800b1c14  push    r14
0x1800b1c16  mov     rbp, rsp
0x1800b1c19  sub     rsp, 30h
0x1800b1c1d  mov     rsi, r8
0x1800b1c20  mov     r14, rdx
0x1800b1c23  mov     rbx, rcx
0x1800b1c26  mov     qword ptr [r8], 0
0x1800b1c2d  mov     [rbp+var_8], 0
0x1800b1c35  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b1c3c  mov     ecx, 50h ; 'P'; unsigned __int64
0x1800b1c41  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b1c46  mov     [rbp+arg_10], rax
0x1800b1c4a  xor     edi, edi
0x1800b1c4c  test    rax, rax
0x1800b1c4f  jz      short loc_1800B1C68
0x1800b1c51  mov     rcx, rax
0x1800b1c54  call    ??0?$SimpleKeyValuePairForMapView@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@@Core@Resources@ApplicationModel@Windows@@QEAA@Upermission@01234@@Z; Windows::ApplicationModel::Resources::Core::SimpleKeyValuePairForMapView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::SimpleKeyValuePairForMapView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(Windows::ApplicationModel::Resources::Core::SimpleKeyValuePairForMapView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::permission)
0x1800b1c59  mov     rdi, rax
0x1800b1c5c  mov     [rbp+var_8], rax
0x1800b1c60  mov     [rbp+arg_10], 0
0x1800b1c68  lea     rcx, [rbp+arg_10]
0x1800b1c6c  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x1800b1c71  test    rdi, rdi
0x1800b1c74  jnz     short loc_1800B1C7D
0x1800b1c76  mov     ebx, 8007000Eh
0x1800b1c7b  jmp     short loc_1800B1CF9
0x1800b1c7d  mov     dword ptr [rbp+arg_10], 0
0x1800b1c84  lea     r8, [rbp+arg_10]
0x1800b1c88  mov     rdx, rbx
0x1800b1c8b  lea     rcx, [rbp+newString]; newString
0x1800b1c8f  call    ??$?0PEAUHSTRING__@@@?$AutoValue@PEAUHSTRING__@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUHSTRING__@@PEAJ@Z; XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(HSTRING__ * const &,long *)
0x1800b1c94  mov     ebx, dword ptr [rbp+arg_10]
0x1800b1c97  test    ebx, ebx
0x1800b1c99  js      short loc_1800B1CDF
0x1800b1c9b  lea     r8, [rbp+arg_10]
0x1800b1c9f  mov     rdx, r14
0x1800b1ca2  lea     rcx, [rbp+string]; newString
0x1800b1ca6  call    ??$?0PEAUHSTRING__@@@?$AutoValue@PEAUHSTRING__@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUHSTRING__@@PEAJ@Z; XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(HSTRING__ * const &,long *)
0x1800b1cab  mov     ebx, dword ptr [rbp+arg_10]
0x1800b1cae  test    ebx, ebx
0x1800b1cb0  js      short loc_1800B1CD4
0x1800b1cb2  mov     rcx, [rdi+40h]
0x1800b1cb6  mov     rax, [rbp+newString]
0x1800b1cba  mov     [rdi+40h], rax
0x1800b1cbe  mov     [rbp+newString], rcx
0x1800b1cc2  mov     rcx, [rdi+48h]
0x1800b1cc6  mov     rax, [rbp+string]
0x1800b1cca  mov     [rdi+48h], rax
0x1800b1cce  mov     [rbp+string], rcx
0x1800b1cd2  jmp     short loc_1800B1CD8
0x1800b1cd4  mov     rcx, [rbp+string]; string
0x1800b1cd8  call    cs:__imp_WindowsDeleteString
0x1800b1cde  nop
0x1800b1cdf  mov     rcx, [rbp+newString]; string
0x1800b1ce3  call    cs:__imp_WindowsDeleteString
0x1800b1ce9  nop
0x1800b1cea  test    ebx, ebx
0x1800b1cec  js      short loc_1800B1CF9
0x1800b1cee  mov     [rbp+var_8], 0
0x1800b1cf6  mov     [rsi], rdi
0x1800b1cf9  lea     rcx, [rbp+var_8]
0x1800b1cfd  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800b1d02  mov     eax, ebx
0x1800b1d04  mov     rbx, [rsp+30h+arg_0]
0x1800b1d09  mov     rsi, [rsp+30h+arg_8]
0x1800b1d0e  add     rsp, 30h
0x1800b1d12  pop     r14
0x1800b1d14  pop     rdi
0x1800b1d15  pop     rbp
0x1800b1d16  retn
```
