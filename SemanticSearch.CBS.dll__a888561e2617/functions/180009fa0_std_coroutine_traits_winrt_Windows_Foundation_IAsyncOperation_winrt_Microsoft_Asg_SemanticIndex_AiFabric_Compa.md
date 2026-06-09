# std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)

- ea: `0x180009fa0`
- end: `0x18000a00c`
- name: `??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ`
- size: `108`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `60`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a010`
- `0x180051770`
- `0x180051d80`
- `0x180052120`
- `0x1800524e0`
- `0x1800528b0`
- `0x180052c90`
- `0x180053610`
- `0x180053fa0`
- `0x180054370`
- `0x180054750`
- `0x180054b70`
- `0x180055d70`
- `0x180056180`
- `0x180056590`
- `0x180056980`
- `0x180056d90`
- `0x180057180`
- `0x180057590`
- `0x1800579e0`
- `0x180057e10`
- `0x1800583b0`
- `0x180058d60`
- `0x180059130`
- `0x180059520`
- `0x180059980`
- `0x180059df0`
- `0x18005a410`
- `0x18005a820`
- `0x18005ac10`
- `0x18005b020`
- `0x18005b450`
- `0x18005b870`
- `0x18005bc90`
- `0x18005d2c0`
- `0x18005d600`
- `0x18005d940`
- `0x18005dd60`
- `0x18005f7f5`
- `0x18005f925`
- `0x18005fb16`
- `0x18005fea5`
- `0x18005ff75`
- `0x180060666`
- `0x1800613d6`
- `0x1800614b6`
- `0x180061546`
- `0x1800615f5`
- `0x180061686`
- `0x180061716`

## callees

- `0x180002bb0`
- `0x1800051b0`
- `0x180009fa0`
- `0x18004ddc4`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a005`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000a005`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(
        _QWORD *a1)
{
  _QWORD *v2; // rcx
  __int64 result; // rax

  v2 = a1 + 13;
  if ( *v2 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v2);
  if ( a1[11] )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 11);
  if ( a1[10] )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 10);
  __ExceptionPtrDestroy(a1 + 7);
  winrt::impl::root_implements<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor>,winrt::guid>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor>,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(a1);
  result = (unsigned int)_InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock);
  if ( (int)result < 0 )
    abort();
  return result;
}

```

## disassembly

```asm
0x180009fa0  push    rbx
0x180009fa2  sub     rsp, 20h
0x180009fa6  mov     rbx, rcx
0x180009fa9  add     rcx, 68h ; 'h'
0x180009fad  cmp     qword ptr [rcx], 0
0x180009fb1  jz      short loc_180009FB8
0x180009fb3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180009fb8  cmp     qword ptr [rbx+58h], 0
0x180009fbd  lea     rcx, [rbx+58h]
0x180009fc1  jz      short loc_180009FC8
0x180009fc3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180009fc8  cmp     qword ptr [rbx+50h], 0
0x180009fcd  lea     rcx, [rbx+50h]
0x180009fd1  jz      short loc_180009FD8
0x180009fd3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180009fd8  lea     rcx, [rbx+38h]; void *
0x180009fdc  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180009fe1  mov     rcx, rbx
0x180009fe4  call    ?subtract_final_reference@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryProcessor@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@@std@@U?$IAsyncOperation@UQueryProcessor@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@567@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor>,winrt::guid>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor>,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(void)
0x180009fe9  mov     eax, 0FFFFFFFFh
0x180009fee  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180009ff6  sub     eax, 1
0x180009ff9  jnz     short loc_18000A001
0x180009ffb  add     rsp, 20h
0x180009fff  pop     rbx
0x18000a000  retn
0x18000a001  test    eax, eax
0x18000a003  jns     short loc_180009FFB
0x18000a005  call    cs:__imp_abort
```
