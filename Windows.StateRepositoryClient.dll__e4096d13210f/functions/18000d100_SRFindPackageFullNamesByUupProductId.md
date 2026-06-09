# SRFindPackageFullNamesByUupProductId

- ea: `0x18000d100`
- end: `0x18000d487`
- name: `SRFindPackageFullNamesByUupProductId`
- size: `903`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002980`
- `0x180003630`
- `0x1800075e4`
- `0x180008ab4`
- `0x180008b4c`
- `0x180008d28`
- `0x1800092b8`
- `0x180009350`
- `0x1800094f4`
- `0x18000b348`
- `0x18000c504`
- `0x18000d100`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d427`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d427`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d20d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d20d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d2dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d2dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d2b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d310`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d39c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d2b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d310`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d39c`

## pseudocode

```c
__int64 __fastcall SRFindPackageFullNamesByUupProductId(void *a1, unsigned __int16 *a2, HSTRING *a3)
{
  __int64 *v5; // rax
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64, __int64 *); // rbx
  __int64 v10; // rax
  int v11; // eax
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  HSTRING v15; // rax
  HSTRING v16; // rsi
  size_t v17; // rax
  unsigned int v18; // ecx
  unsigned int v19; // r14d
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rbx
  int v24; // eax
  char *StringRawBuffer; // rax
  __int64 v26; // r8
  const char *v27; // r9
  void *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v32; // rdx
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rcx
  int v37; // [rsp+20h] [rbp-49h]
  __int64 v38; // [rsp+30h] [rbp-39h] BYREF
  __int64 v39; // [rsp+38h] [rbp-31h] BYREF
  __int64 v40; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v41; // [rsp+48h] [rbp-21h] BYREF
  HSTRING string; // [rsp+50h] [rbp-19h] BYREF
  void *v43; // [rsp+58h] [rbp-11h] BYREF
  __int64 v44; // [rsp+60h] [rbp-9h] BYREF
  HSTRING v45[4]; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v43 = a1;
  v44 = 0;
  v5 = (__int64 *)Windows::Internal::StringReference::StringReference(v45, (const unsigned __int16 (*)[51])a2);
  v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUupProductPackageStatics>>(
         *v5,
         (__int64)&v44);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = v44;
    v39 = 0;
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v44 + 152LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v39);
    v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v45, &v43);
    v11 = v9(v8, *(_QWORD *)(v10 + 24), 1, &v39);
    v7 = v11;
    if ( v11 >= 0 )
    {
      v41 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v39 + 56LL))(v39, &v41);
      v7 = v14;
      if ( v14 >= 0 )
      {
        v43 = 0;
        if ( is_mul_ok(v41, 8u) )
        {
          v15 = (HSTRING)CoTaskMemAlloc(8LL * v41);
          v16 = v15;
          if ( v15 )
          {
            v17 = CTCoAllocPolicy::_CoTaskMemSize(v15);
            memset_0(v16, 0, v17);
            v7 = 0;
          }
          else
          {
            v7 = -2147024882;
          }
          if ( v7 >= 0 )
          {
            v18 = v41;
            v19 = 0;
            v45[0] = v16;
            v45[1] = (HSTRING)v41;
            if ( !v41 )
            {
LABEL_22:
              *a3 = v16;
              *(_DWORD *)a2 = v18;
              Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v39);
              Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v44);
              return 0;
            }
            while ( 1 )
            {
              v38 = 0;
              v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v39 + 48LL))(v39, v19, &v38);
              v7 = v20;
              if ( v20 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x210,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
                  (const char *)(unsigned int)v20,
                  v37);
                goto LABEL_30;
              }
              v40 = 0;
              v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 128LL))(v38, &v40);
              v7 = v21;
              if ( v21 < 0 )
                break;
              v22 = v40;
              string = 0;
              v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 80LL);
              WindowsDeleteString(0);
              string = 0;
              v24 = v23(v22, &string);
              v7 = v24;
              if ( v24 < 0 )
              {
                v33 = (unsigned int)v24;
                v32 = 534;
                goto LABEL_24;
              }
              StringRawBuffer = (char *)WindowsGetStringRawBuffer(string, 0);
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v43,
                StringRawBuffer,
                v26,
                v27);
              v28 = v43;
              v43 = 0;
              *((_QWORD *)v16 + v19) = v28;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
              if ( !*((_QWORD *)v16 + v19) )
              {
                v7 = -2147024882;
                v32 = 537;
                v33 = 2147942414LL;
LABEL_24:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v32,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
                  (const char *)v33,
                  v37);
                WindowsDeleteString(string);
                string = 0;
                goto LABEL_25;
              }
              WindowsDeleteString(string);
              v29 = v40;
              string = 0;
              if ( v40 )
              {
                v40 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
              }
              v30 = v38;
              if ( v38 )
              {
                v38 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              }
              v18 = v41;
              if ( ++v19 >= v41 )
                goto LABEL_22;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x213,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
              (const char *)(unsigned int)v21,
              v37);
LABEL_25:
            v35 = v40;
            if ( v40 )
            {
              v40 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
            }
LABEL_30:
            v36 = v38;
            if ( v38 )
            {
              v38 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            }
            if ( v16 )
            {
              wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::reset_array<wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
                (__int64)v45,
                v34);
              CoTaskMemFree(v16);
            }
            goto LABEL_37;
          }
        }
        else
        {
          v7 = -2147024362;
        }
        v12 = (unsigned int)v7;
        v13 = 522;
      }
      else
      {
        v12 = (unsigned int)v14;
        v13 = 519;
      }
    }
    else
    {
      v12 = (unsigned int)v11;
      v13 = 516;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)v12,
      v37);
LABEL_37:
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v39);
    goto LABEL_38;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x201,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
    (const char *)(unsigned int)v6,
    v37);
LABEL_38:
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v44);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d100  mov     [rsp-8+arg_18], rbx
0x18000d105  push    rbp
0x18000d106  push    rsi
0x18000d107  push    rdi
0x18000d108  push    r12
0x18000d10a  push    r13
0x18000d10c  push    r14
0x18000d10e  push    r15
0x18000d110  lea     rbp, [rsp-27h]
0x18000d115  sub     rsp, 90h
0x18000d11c  mov     rax, cs:__security_cookie
0x18000d123  xor     rax, rsp
0x18000d126  mov     [rbp+57h+var_38], rax
0x18000d12a  mov     [rbp+57h+var_68], rcx
0x18000d12e  xor     r13d, r13d
0x18000d131  lea     rcx, [rbp+57h+var_58]; string
0x18000d135  mov     [rbp+57h+var_60], r13
0x18000d139  mov     r12, r8
0x18000d13c  mov     r15, rdx
0x18000d13f  call    ??$?0$0DD@@StringReference@Internal@Windows@@QEAA@AEAY0DD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[51])
0x18000d144  lea     rdx, [rbp+57h+var_60]
0x18000d148  mov     rcx, [rax]
0x18000d14b  call    ??$GetActivationFactory@V?$ComPtr@UIUupProductPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUupProductPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUupProductPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUupProductPackageStatics>>)
0x18000d150  mov     ebx, eax
0x18000d152  test    eax, eax
0x18000d154  jns     short loc_18000D173
0x18000d156  mov     rcx, [rbp+5Fh]; this
0x18000d15a  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000d161  mov     r9d, eax; char *
0x18000d164  mov     edx, 201h; void *
0x18000d169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d16e  jmp     loc_18000D455
0x18000d173  mov     rdi, [rbp+57h+var_60]
0x18000d177  lea     rcx, [rbp+57h+var_88]
0x18000d17b  mov     [rbp+57h+var_88], r13
0x18000d17f  mov     rax, [rdi]
0x18000d182  mov     rbx, [rax+98h]
0x18000d189  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000d18e  lea     rdx, [rbp+57h+var_68]
0x18000d192  lea     rcx, [rbp+57h+var_58]
0x18000d196  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000d19b  lea     r9, [rbp+57h+var_88]
0x18000d19f  mov     r8d, 1
0x18000d1a5  mov     rcx, rdi
0x18000d1a8  mov     rdx, [rax+18h]
0x18000d1ac  mov     rax, rbx
0x18000d1af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1b4  mov     ebx, eax
0x18000d1b6  test    eax, eax
0x18000d1b8  jns     short loc_18000D1C7
0x18000d1ba  mov     r9d, eax
0x18000d1bd  mov     edx, 204h
0x18000d1c2  jmp     loc_18000D43C
0x18000d1c7  mov     rcx, [rbp+57h+var_88]
0x18000d1cb  lea     rdx, [rbp+57h+var_78]
0x18000d1cf  mov     [rbp+57h+var_78], r13d
0x18000d1d3  mov     rax, [rcx]
0x18000d1d6  mov     rax, [rax+38h]
0x18000d1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1df  mov     ebx, eax
0x18000d1e1  test    eax, eax
0x18000d1e3  jns     short loc_18000D1F2
0x18000d1e5  mov     r9d, eax
0x18000d1e8  mov     edx, 207h
0x18000d1ed  jmp     loc_18000D43C
0x18000d1f2  mov     ecx, [rbp+57h+var_78]
0x18000d1f5  mov     eax, 8
0x18000d1fa  mul     rcx
0x18000d1fd  mov     [rbp+57h+var_68], r13
0x18000d201  test    rdx, rdx
0x18000d204  jnz     loc_18000D42F
0x18000d20a  mov     rcx, rax; cb
0x18000d20d  call    cs:__imp_CoTaskMemAlloc
0x18000d213  mov     rsi, rax
0x18000d216  test    rax, rax
0x18000d219  jz      short loc_18000D235
0x18000d21b  mov     rcx, rax; void *
0x18000d21e  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000d223  mov     r8, rax; Size
0x18000d226  xor     edx, edx; Val
0x18000d228  mov     rcx, rsi; void *
0x18000d22b  call    memset_0
0x18000d230  mov     ebx, r13d
0x18000d233  jmp     short loc_18000D23A
0x18000d235  mov     ebx, 8007000Eh
0x18000d23a  test    ebx, ebx
0x18000d23c  js      loc_18000D434
0x18000d242  mov     ecx, [rbp+57h+var_78]
0x18000d245  mov     r14d, r13d
0x18000d248  mov     [rbp+57h+var_58], rsi
0x18000d24c  mov     [rbp+57h+var_50], rcx
0x18000d250  test    ecx, ecx
0x18000d252  jz      loc_18000D35B
0x18000d258  mov     rcx, [rbp+57h+var_88]
0x18000d25c  lea     r8, [rbp+57h+var_90]
0x18000d260  mov     [rbp+57h+var_90], r13
0x18000d264  mov     edx, r14d
0x18000d267  mov     rax, [rcx]
0x18000d26a  mov     rax, [rax+30h]
0x18000d26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d273  mov     ebx, eax
0x18000d275  test    eax, eax
0x18000d277  js      loc_18000D3E5
0x18000d27d  mov     rcx, [rbp+57h+var_90]
0x18000d281  lea     rdx, [rbp+57h+var_80]
0x18000d285  mov     [rbp+57h+var_80], r13
0x18000d289  mov     rax, [rcx]
0x18000d28c  mov     rax, [rax+80h]
0x18000d293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d298  mov     ebx, eax
0x18000d29a  test    eax, eax
0x18000d29c  js      loc_18000D3CB
0x18000d2a2  mov     rdi, [rbp+57h+var_80]
0x18000d2a6  xor     ecx, ecx; string
0x18000d2a8  mov     [rbp+57h+string], r13
0x18000d2ac  mov     rax, [rdi]
0x18000d2af  mov     rbx, [rax+50h]
0x18000d2b3  call    cs:__imp_WindowsDeleteString
0x18000d2b9  lea     rdx, [rbp+57h+string]
0x18000d2bd  mov     [rbp+57h+string], r13
0x18000d2c1  mov     rcx, rdi
0x18000d2c4  mov     rax, rbx
0x18000d2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2cc  mov     ebx, eax
0x18000d2ce  test    eax, eax
0x18000d2d0  js      loc_18000D3C1
0x18000d2d6  mov     rcx, [rbp+57h+string]; string
0x18000d2da  xor     edx, edx; length
0x18000d2dc  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d2e2  mov     rdx, rax
0x18000d2e5  lea     rcx, [rbp+57h+var_68]
0x18000d2e9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000d2ee  mov     rax, [rbp+57h+var_68]
0x18000d2f2  lea     rcx, [rbp+57h+var_68]
0x18000d2f6  mov     ebx, r14d
0x18000d2f9  mov     [rbp+57h+var_68], r13
0x18000d2fd  mov     [rsi+rbx*8], rax
0x18000d301  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000d306  cmp     [rsi+rbx*8], r13
0x18000d30a  jz      short loc_18000D37B
0x18000d30c  mov     rcx, [rbp+57h+string]; string
0x18000d310  call    cs:__imp_WindowsDeleteString
0x18000d316  mov     rcx, [rbp+57h+var_80]
0x18000d31a  mov     [rbp+57h+string], r13
0x18000d31e  test    rcx, rcx
0x18000d321  jz      short loc_18000D333
0x18000d323  mov     [rbp+57h+var_80], r13
0x18000d327  mov     rax, [rcx]
0x18000d32a  mov     rax, [rax+10h]
0x18000d32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d333  mov     rcx, [rbp+57h+var_90]
0x18000d337  test    rcx, rcx
0x18000d33a  jz      short loc_18000D34C
0x18000d33c  mov     [rbp+57h+var_90], r13
0x18000d340  mov     rax, [rcx]
0x18000d343  mov     rax, [rax+10h]
0x18000d347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d34c  mov     ecx, [rbp+57h+var_78]
0x18000d34f  inc     r14d
0x18000d352  cmp     r14d, ecx
0x18000d355  jb      loc_18000D258
0x18000d35b  mov     [r12], rsi
0x18000d35f  mov     [r15], ecx
0x18000d362  lea     rcx, [rbp+57h+var_88]
0x18000d366  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000d36b  lea     rcx, [rbp+57h+var_60]
0x18000d36f  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000d374  xor     eax, eax
0x18000d376  jmp     loc_18000D460
0x18000d37b  mov     ebx, 8007000Eh
0x18000d380  mov     edx, 219h; void *
0x18000d385  mov     r9d, ebx; char *
0x18000d388  mov     rcx, [rbp+5Fh]; this
0x18000d38c  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000d393  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d398  mov     rcx, [rbp+57h+string]; string
0x18000d39c  call    cs:__imp_WindowsDeleteString
0x18000d3a2  mov     [rbp+57h+string], r13
0x18000d3a6  mov     rcx, [rbp+57h+var_80]
0x18000d3aa  test    rcx, rcx
0x18000d3ad  jz      short loc_18000D3FD
0x18000d3af  mov     [rbp+57h+var_80], r13
0x18000d3b3  mov     rax, [rcx]
0x18000d3b6  mov     rax, [rax+10h]
0x18000d3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3bf  jmp     short loc_18000D3FD
0x18000d3c1  mov     r9d, eax
0x18000d3c4  mov     edx, 216h
0x18000d3c9  jmp     short loc_18000D388
0x18000d3cb  mov     rcx, [rbp+5Fh]; this
0x18000d3cf  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000d3d6  mov     r9d, eax; char *
0x18000d3d9  mov     edx, 213h; void *
0x18000d3de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d3e3  jmp     short loc_18000D3A6
0x18000d3e5  mov     rcx, [rbp+5Fh]; this
0x18000d3e9  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000d3f0  mov     r9d, eax; char *
0x18000d3f3  mov     edx, 210h; void *
0x18000d3f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d3fd  mov     rcx, [rbp+57h+var_90]
0x18000d401  test    rcx, rcx
0x18000d404  jz      short loc_18000D416
0x18000d406  mov     [rbp+57h+var_90], r13
0x18000d40a  mov     rax, [rcx]
0x18000d40d  mov     rax, [rax+10h]
0x18000d411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d416  test    rsi, rsi
0x18000d419  jz      short loc_18000D44C
0x18000d41b  lea     rcx, [rbp+57h+var_58]
0x18000d41f  call    ??$reset_array@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@AEAAXAEBU?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@1@@Z; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::reset_array<wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> const &)
0x18000d424  mov     rcx, rsi; pv
0x18000d427  call    cs:__imp_CoTaskMemFree
0x18000d42d  jmp     short loc_18000D44C
0x18000d42f  mov     ebx, 80070216h
0x18000d434  mov     r9d, ebx; char *
0x18000d437  mov     edx, 20Ah; void *
0x18000d43c  mov     rcx, [rbp+5Fh]; this
0x18000d440  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000d447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d44c  lea     rcx, [rbp+57h+var_88]
0x18000d450  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000d455  lea     rcx, [rbp+57h+var_60]
0x18000d459  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000d45e  mov     eax, ebx
0x18000d460  mov     rcx, [rbp+57h+var_38]
0x18000d464  xor     rcx, rsp; StackCookie
0x18000d467  call    __security_check_cookie
0x18000d46c  mov     rbx, [rsp+0C0h+arg_18]
0x18000d474  add     rsp, 90h
0x18000d47b  pop     r15
0x18000d47d  pop     r14
0x18000d47f  pop     r13
0x18000d481  pop     r12
0x18000d483  pop     rdi
0x18000d484  pop     rsi
0x18000d485  pop     rbp
0x18000d486  retn
```
