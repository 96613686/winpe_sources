# ActivateAppWithQuery(HSTRING__ *,HSTRING__ *,HSTRING__ *,IInspectable *)

- ea: `0x18003b098`
- end: `0x18003b2be`
- name: `?ActivateAppWithQuery@@YAJPEAUHSTRING__@@00PEAUIInspectable@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING, HSTRING, struct IInspectable *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180039ab0`

## callees

- `0x180007b3c`
- `0x180010a10`
- `0x180013db4`
- `0x180015084`
- `0x18003a3ac`
- `0x18003a578`
- `0x18003ac08`
- `0x18003b098`
- `0x18003b550`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b0d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b151`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b0d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b151`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b205`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b205`
- `SHCORE!SHTaskPoolQueueTask` at `0x18003b224`
- `SHCORE!SHTaskPoolQueueTask` at `0x18003b224`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ActivateAppWithQuery(HSTRING string, HSTRING a2, HSTRING a3, struct IInspectable *a4)
{
  __int64 v8; // r14
  PCWSTR StringRawBuffer; // rax
  int v10; // ebx
  __int64 v11; // rsi
  PCWSTR v12; // rax
  __int64 v13; // rdi
  PCWSTR v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 *v19; // rax
  __int64 v20; // r15
  __int64 v21; // rcx
  DWORD CurrentThreadId; // eax
  struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails *v24; // [rsp+30h] [rbp-39h] BYREF
  __int64 v25; // [rsp+38h] [rbp-31h] BYREF
  __int64 v26; // [rsp+40h] [rbp-29h] BYREF
  __int64 v27; // [rsp+48h] [rbp-21h] BYREF
  __int64 v28; // [rsp+50h] [rbp-19h] BYREF
  __int64 v29; // [rsp+58h] [rbp-11h] BYREF
  __int64 v30; // [rsp+60h] [rbp-9h] BYREF
  __int64 v31; // [rsp+68h] [rbp-1h] BYREF
  struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails *v32; // [rsp+70h] [rbp+7h] BYREF

  CreateRefCountedObj<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,>(&v26);
  v8 = v26;
  if ( v26 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            v8 + 8,
            StringRawBuffer,
            -1);
    if ( v10 >= 0 )
    {
      CreateRefCountedObj<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,>(&v27);
      v11 = v27;
      if ( v27 )
      {
        v12 = WindowsGetStringRawBuffer(a3, 0);
        v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                v11 + 8,
                v12,
                -1);
        if ( v10 >= 0 )
        {
          CreateRefCountedObj<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,>(&v28);
          v13 = v28;
          if ( v28 )
          {
            v14 = WindowsGetStringRawBuffer(string, 0);
            v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                    v13 + 8,
                    v14,
                    -1);
            if ( v10 >= 0 )
            {
              v24 = 0;
              if ( a4 )
              {
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v24);
                v10 = ConvertToSearchPaneQueryLinguisticDetails(a2, a4, &v24);
              }
              if ( v10 >= 0 )
              {
                v29 = v13;
                Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v29, v15);
                v30 = v8;
                Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v30, v16);
                v31 = v11;
                Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v31, v17);
                v32 = v24;
                Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v32, v18);
                v19 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_f1004ae5ab24418310f18333093cde63_____lambda_f1004ae5ab24418310f18333093cde63___(
                                   &v25,
                                   &v29);
                v20 = *v19;
                *v19 = 0;
                v21 = v25;
                if ( v25 )
                {
                  v25 = 0;
                  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Xaml::IRoutedEventHandler>::Release(v21);
                }
                CurrentThreadId = GetCurrentThreadId();
                v10 = SHTaskPoolQueueTask(3, 0, CurrentThreadId);
                if ( v20 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
                lambda_f1004ae5ab24418310f18333093cde63_::__lambda_f1004ae5ab24418310f18333093cde63_(&v29);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v24);
            }
          }
          else
          {
            v10 = -2147024882;
          }
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
      }
      else
      {
        v10 = -2147024882;
      }
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  else
  {
    v10 = -2147024882;
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003b098  push    rbp
0x18003b09a  push    rbx
0x18003b09b  push    rsi
0x18003b09c  push    rdi
0x18003b09d  push    r12
0x18003b09f  push    r13
0x18003b0a1  push    r14
0x18003b0a3  push    r15
0x18003b0a5  lea     rbp, [rsp-1Fh]
0x18003b0aa  sub     rsp, 88h
0x18003b0b1  mov     r15, r9
0x18003b0b4  mov     rdi, r8
0x18003b0b7  mov     r12, rdx
0x18003b0ba  mov     r13, rcx
0x18003b0bd  lea     rcx, [rbp+57h+var_80]
0x18003b0c1  call    ??$CreateRefCountedObj@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,>(void)
0x18003b0c6  nop
0x18003b0c7  mov     r14, [rbp+57h+var_80]
0x18003b0cb  test    r14, r14
0x18003b0ce  jz      loc_18003B28E
0x18003b0d4  xor     edx, edx; length
0x18003b0d6  mov     rcx, r12; string
0x18003b0d9  call    cs:__imp_WindowsGetStringRawBuffer
0x18003b0df  lea     rcx, [r14+8]
0x18003b0e3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003b0e7  mov     rdx, rax
0x18003b0ea  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003b0ef  mov     ebx, eax
0x18003b0f1  test    eax, eax
0x18003b0f3  js      loc_18003B293
0x18003b0f9  lea     rcx, [rbp+57h+var_78]
0x18003b0fd  call    ??$CreateRefCountedObj@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,>(void)
0x18003b102  nop
0x18003b103  mov     rsi, [rbp+57h+var_78]
0x18003b107  test    rsi, rsi
0x18003b10a  jz      loc_18003B272
0x18003b110  xor     edx, edx; length
0x18003b112  mov     rcx, rdi; string
0x18003b115  call    cs:__imp_WindowsGetStringRawBuffer
0x18003b11b  lea     rcx, [rsi+8]
0x18003b11f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003b123  mov     rdx, rax
0x18003b126  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003b12b  mov     ebx, eax
0x18003b12d  test    eax, eax
0x18003b12f  js      loc_18003B277
0x18003b135  lea     rcx, [rbp+57h+var_70]
0x18003b139  call    ??$CreateRefCountedObj@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,>(void)
0x18003b13e  nop
0x18003b13f  mov     rdi, [rbp+57h+var_70]
0x18003b143  test    rdi, rdi
0x18003b146  jz      loc_18003B256
0x18003b14c  xor     edx, edx; length
0x18003b14e  mov     rcx, r13; string
0x18003b151  call    cs:__imp_WindowsGetStringRawBuffer
0x18003b157  lea     rcx, [rdi+8]
0x18003b15b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003b15f  mov     rdx, rax
0x18003b162  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003b167  mov     ebx, eax
0x18003b169  test    eax, eax
0x18003b16b  js      loc_18003B25B
0x18003b171  mov     [rbp+57h+var_90], 0
0x18003b179  test    r15, r15
0x18003b17c  jz      short loc_18003B198
0x18003b17e  lea     rcx, [rbp+57h+var_90]
0x18003b182  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003b187  lea     r8, [rbp+57h+var_90]; struct Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails **
0x18003b18b  mov     rdx, r15; struct IInspectable *
0x18003b18e  mov     rcx, r12; HSTRING
0x18003b191  call    ?ConvertToSearchPaneQueryLinguisticDetails@@YAJPEAUHSTRING__@@PEAUIInspectable@@PEAPEAUISearchPaneQueryLinguisticDetails@Search@ApplicationModel@Windows@@@Z; ConvertToSearchPaneQueryLinguisticDetails(HSTRING__ *,IInspectable *,Windows::ApplicationModel::Search::ISearchPaneQueryLinguisticDetails * *)
0x18003b196  mov     ebx, eax
0x18003b198  test    ebx, ebx
0x18003b19a  js      loc_18003B24B
0x18003b1a0  mov     [rbp+57h+var_68], rdi
0x18003b1a4  lea     rcx, [rbp+57h+var_68]
0x18003b1a8  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18003b1ad  mov     [rbp+57h+var_60], r14
0x18003b1b1  lea     rcx, [rbp+57h+var_60]
0x18003b1b5  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18003b1ba  mov     [rbp+57h+var_58], rsi
0x18003b1be  lea     rcx, [rbp+57h+var_58]
0x18003b1c2  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18003b1c7  mov     rax, [rbp+57h+var_90]
0x18003b1cb  mov     [rbp+57h+var_50], rax
0x18003b1cf  lea     rcx, [rbp+57h+var_50]
0x18003b1d3  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18003b1d8  lea     rdx, [rbp+57h+var_68]
0x18003b1dc  lea     rcx, [rbp+57h+var_88]
0x18003b1e0  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_f1004ae5ab24418310f18333093cde63_____lambda_f1004ae5ab24418310f18333093cde63___
0x18003b1e5  mov     r15, [rax]
0x18003b1e8  mov     qword ptr [rax], 0
0x18003b1ef  mov     rcx, [rbp+57h+var_88]
0x18003b1f3  test    rcx, rcx
0x18003b1f6  jz      short loc_18003B205
0x18003b1f8  mov     [rbp+57h+var_88], 0
0x18003b200  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIRoutedEventHandler@Xaml@UI@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Xaml::IRoutedEventHandler>::Release(void)
0x18003b205  call    cs:__imp_GetCurrentThreadId
0x18003b20b  mov     [rsp+0C0h+var_98], 0
0x18003b214  mov     [rsp+0C0h+var_A0], r15
0x18003b219  xor     r9d, r9d
0x18003b21c  mov     r8d, eax
0x18003b21f  xor     edx, edx
0x18003b221  lea     ecx, [rdx+3]
0x18003b224  call    cs:__imp_SHTaskPoolQueueTask
0x18003b22a  mov     ebx, eax
0x18003b22c  test    r15, r15
0x18003b22f  jz      short loc_18003B241
0x18003b231  mov     rax, [r15]
0x18003b234  mov     rcx, r15
0x18003b237  mov     rax, [rax+10h]
0x18003b23b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b240  nop
0x18003b241  lea     rcx, [rbp+57h+var_68]
0x18003b245  call    _lambda_f1004ae5ab24418310f18333093cde63_____lambda_f1004ae5ab24418310f18333093cde63_
0x18003b24a  nop
0x18003b24b  lea     rcx, [rbp+57h+var_90]
0x18003b24f  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003b254  jmp     short loc_18003B25B
0x18003b256  mov     ebx, 8007000Eh
0x18003b25b  test    rdi, rdi
0x18003b25e  jz      short loc_18003B270
0x18003b260  mov     rax, [rdi]
0x18003b263  mov     rcx, rdi
0x18003b266  mov     rax, [rax+10h]
0x18003b26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b26f  nop
0x18003b270  jmp     short loc_18003B277
0x18003b272  mov     ebx, 8007000Eh
0x18003b277  test    rsi, rsi
0x18003b27a  jz      short loc_18003B28C
0x18003b27c  mov     rax, [rsi]
0x18003b27f  mov     rcx, rsi
0x18003b282  mov     rax, [rax+10h]
0x18003b286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b28b  nop
0x18003b28c  jmp     short loc_18003B293
0x18003b28e  mov     ebx, 8007000Eh
0x18003b293  test    r14, r14
0x18003b296  jz      short loc_18003B2A8
0x18003b298  mov     rax, [r14]
0x18003b29b  mov     rcx, r14
0x18003b29e  mov     rax, [rax+10h]
0x18003b2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2a7  nop
0x18003b2a8  mov     eax, ebx
0x18003b2aa  add     rsp, 88h
0x18003b2b1  pop     r15
0x18003b2b3  pop     r14
0x18003b2b5  pop     r13
0x18003b2b7  pop     r12
0x18003b2b9  pop     rdi
0x18003b2ba  pop     rsi
0x18003b2bb  pop     rbx
0x18003b2bc  pop     rbp
0x18003b2bd  retn
```
