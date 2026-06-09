# CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(_GUID const &,IUnknown *,MARSHAL_KIND)

- ea: `0x180027fc8`
- end: `0x180028072`
- name: `?RuntimeClassInitialize@CMarshalStream@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z`
- size: `170`
- prototype: `int __high(const struct _GUID *, struct IUnknown *, enum MARSHAL_KIND)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026bac`

## callees

- `0x180007b3c`
- `0x180027fc8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027fdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027fdd`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18002805f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18002805f`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180028013`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180028013`

## pseudocode

```c
__int64 __fastcall CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(
        __int64 a1,
        const IID *a2,
        IUnknown *a3,
        int a4)
{
  DWORD CurrentThreadId; // eax
  __int64 v9; // rax
  unsigned int AgileReference; // ebx
  _QWORD v12[7]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 24) = a4;
  *(_DWORD *)(a1 + 40) = CurrentThreadId;
  if ( a4 == 2 )
  {
    v9 = 0;
    AgileReference = 0;
    v13 = 0;
    if ( a3 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v13);
      AgileReference = RoGetAgileReference(0, a2, a3, &v13);
      v9 = v13;
    }
    v12[0] = *(_QWORD *)(a1 + 32);
    v13 = 0;
    *(_QWORD *)(a1 + 32) = v9;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(v12);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v13);
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(a1 + 16);
    return (unsigned int)CoMarshalInterThreadInterfaceInStream(a2, a3, (LPSTREAM *)(a1 + 16));
  }
  return AgileReference;
}

```

## disassembly

```asm
0x180027fc8  push    rbx
0x180027fca  push    rbp
0x180027fcb  push    rsi
0x180027fcc  push    rdi
0x180027fcd  sub     rsp, 38h
0x180027fd1  mov     ebx, r9d
0x180027fd4  mov     rsi, r8
0x180027fd7  mov     rbp, rdx
0x180027fda  mov     rdi, rcx
0x180027fdd  call    cs:__imp_GetCurrentThreadId
0x180027fe3  mov     [rdi+18h], ebx
0x180027fe6  mov     [rdi+28h], eax
0x180027fe9  cmp     ebx, 2
0x180027fec  jnz     short loc_18002804C
0x180027fee  xor     eax, eax
0x180027ff0  xor     ebx, ebx
0x180027ff2  mov     [rsp+58h+arg_0], rax
0x180027ff7  test    rsi, rsi
0x180027ffa  jz      short loc_180028020
0x180027ffc  lea     rcx, [rsp+58h+arg_0]
0x180028001  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180028006  lea     r9, [rsp+58h+arg_0]
0x18002800b  mov     r8, rsi
0x18002800e  mov     rdx, rbp
0x180028011  xor     ecx, ecx
0x180028013  call    cs:__imp_RoGetAgileReference
0x180028019  mov     ebx, eax
0x18002801b  mov     rax, [rsp+58h+arg_0]
0x180028020  mov     rcx, [rdi+20h]
0x180028024  mov     [rsp+58h+var_38], rcx
0x180028029  lea     rcx, [rsp+58h+var_38]
0x18002802e  mov     [rsp+58h+arg_0], 0
0x180028037  mov     [rdi+20h], rax
0x18002803b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180028040  lea     rcx, [rsp+58h+arg_0]
0x180028045  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002804a  jmp     short loc_180028067
0x18002804c  lea     rcx, [rdi+10h]
0x180028050  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180028055  lea     r8, [rdi+10h]; ppStm
0x180028059  mov     rdx, rsi; pUnk
0x18002805c  mov     rcx, rbp; riid
0x18002805f  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180028065  mov     ebx, eax
0x180028067  mov     eax, ebx
0x180028069  add     rsp, 38h
0x18002806d  pop     rdi
0x18002806e  pop     rsi
0x18002806f  pop     rbp
0x180028070  pop     rbx
0x180028071  retn
```
