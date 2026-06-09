# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::TryLoadForOptionsAsync$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions_

- ea: `0x18022c4c0`
- end: `0x18022cad8`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::TryLoadForOptionsAsync$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions_`
- size: `1560`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18022c4a0`
- `0x18022d130`

## callees

- `0x180003350`
- `0x180003bd0`
- `0x180003df0`
- `0x180004050`
- `0x18000d230`
- `0x180010400`
- `0x180010af0`
- `0x180010dd0`
- `0x18001bc40`
- `0x18001fd80`
- `0x180020e60`
- `0x180047520`
- `0x1800681e0`
- `0x18006df00`
- `0x180078d00`
- `0x180078d10`
- `0x1801d1e70`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x18022c4c0`
- `0x180242120`

## string_xrefs

- `0x18022c5d5`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18022c667`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18022c7fa`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18022c53d`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\ImageEmbeddingsGenerator.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::TryLoadForOptionsAsync__ResumeCoro_1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions_(
        _WORD *a1)
{
  _WORD *v2; // r15
  __int64 v3; // rcx
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // eax
  struct winrt::impl::hstring_header *v10; // rdx
  int v11; // eax
  volatile signed __int32 *v12; // r14
  int v13; // eax
  HANDLE ProcessHeap; // rax
  __int64 CoreAsync; // rax
  volatile __int64 *v16; // rdi
  volatile signed __int32 *v17; // r14
  int v18; // eax
  HANDLE v19; // rax
  volatile __int64 *v20; // r14
  volatile signed __int32 *v21; // r14
  int v22; // eax
  HANDLE v23; // rax
  _BYTE pExceptionObject[24]; // [rsp+78h] [rbp-E0h] BYREF
  _BYTE v25[32]; // [rsp+90h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+B0h] [rbp-A8h]
  __int64 v27; // [rsp+B8h] [rbp-A0h]
  __int64 v28; // [rsp+C8h] [rbp-90h]

  v2 = a1 + 76;
  switch ( a1[76] )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_48;
    case 2:
      v3 = *((_QWORD *)a1 + 18);
      if ( !v3 )
      {
        *((_DWORD *)a1 + 40) = 84;
        *((_QWORD *)a1 + 21) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\ImageEmbeddingsGenerator.h";
        *((_QWORD *)a1 + 22) = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)(a1 + 92), L"options");
        winrt::hresult_invalid_argument::hresult_invalid_argument(
          (winrt::hresult_invalid_argument *)pExceptionObject,
          (const struct winrt::param::hstring *)(a1 + 92),
          (const struct winrt::impl::slim_source_location *)(a1 + 80));
        throw (winrt::hresult_invalid_argument *)pExceptionObject;
      }
      *((_QWORD *)a1 + 27) = v3;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(
        a1 + 112,
        a1 + 108);
      *((_BYTE *)a1 + 288) = 0;
      *((_QWORD *)a1 + 57) = 0;
      v4 = *((_QWORD *)a1 + 18);
      *((_DWORD *)a1 + 116) = 1837;
      *((_QWORD *)a1 + 59) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated "
                             "Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *((_QWORD *)a1 + 60) = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v4 + 48LL))(v4, a1 + 228);
      if ( v5 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v5, a1 + 232);
      }
      v6 = *((_QWORD *)a1 + 57);
      *((_QWORD *)a1 + 37) = v6;
      v7 = *((_QWORD *)a1 + 29);
      *((_QWORD *)a1 + 38) = v7;
      v27 = *((_QWORD *)a1 + 30);
      v26 = v7;
      *((_QWORD *)a1 + 39) = v27 - v7;
      *((_DWORD *)a1 + 112) = 0;
      v8 = *((_QWORD *)a1 + 18);
      *((_DWORD *)a1 + 122) = 1855;
      *((_QWORD *)a1 + 62) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated "
                             "Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *((_QWORD *)a1 + 63) = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v8 + 56LL))(v8, a1 + 224);
      if ( v9 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v9, a1 + 244);
      }
      v11 = *((_DWORD *)a1 + 112);
      *((_DWORD *)a1 + 80) = v11;
      if ( *((_BYTE *)a1 + 288) )
      {
        winrt::hstring::operator=(a1 + 128, a1 + 148);
        *(_OWORD *)(a1 + 132) = *((_OWORD *)a1 + 19);
        *((_DWORD *)a1 + 70) = *((_DWORD *)a1 + 80);
      }
      else
      {
        *((_QWORD *)a1 + 37) = 0;
        *((_QWORD *)a1 + 32) = v6;
        *(_OWORD *)(a1 + 132) = *((_OWORD *)a1 + 19);
        *((_DWORD *)a1 + 70) = v11;
        *((_BYTE *)a1 + 288) = 1;
      }
      v12 = (volatile signed __int32 *)*((_QWORD *)a1 + 37);
      if ( v12 )
      {
        v13 = _InterlockedDecrement(v12 + 6);
        if ( v13 )
        {
          if ( v13 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v12);
        }
      }
      *((_QWORD *)a1 + 46) = a1 + 164;
      *((_BYTE *)a1 + 360) = 0;
      if ( *((_BYTE *)a1 + 288) )
      {
        *((_QWORD *)a1 + 41) = winrt::impl::duplicate_hstring(*((winrt::impl **)a1 + 32), v10);
        *((_OWORD *)a1 + 21) = *(_OWORD *)(a1 + 132);
        *((_DWORD *)a1 + 88) = *((_DWORD *)a1 + 70);
        *((_BYTE *)a1 + 360) = 1;
      }
      CoreAsync = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::TryLoadCoreAsync(
                    *((_QWORD *)a1 + 17),
                    a1 + 188,
                    a1 + 164);
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 128) = 5672;
        *((_QWORD *)a1 + 65) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generate"
                               "d Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)a1 + 66) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v25,
          (const struct winrt::impl::slim_source_location *)(a1 + 256));
        throw (winrt::hresult_canceled *)v25;
      }
      *((_QWORD *)a1 + 48) = 0;
      *((_QWORD *)a1 + 49) = CoreAsync;
      *((_QWORD *)a1 + 50) = 0;
      *((_BYTE *)a1 + 408) = 1;
      *v2 = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(
                              (_QWORD *)a1 + 48,
                              (__int64)a1) )
        return;
      goto LABEL_35;
    case 4:
LABEL_35:
      *((_BYTE *)a1 + 120) = winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(a1 + 192);
      v20 = (volatile __int64 *)*((_QWORD *)a1 + 48);
      if ( v20 )
      {
        v28 = *((_QWORD *)a1 + 48);
        while ( _InterlockedExchange64(v20, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 47) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 188);
      if ( *((_BYTE *)a1 + 288) )
      {
        v21 = (volatile signed __int32 *)*((_QWORD *)a1 + 32);
        if ( v21 )
        {
          v22 = _InterlockedDecrement(v21 + 6);
          if ( v22 )
          {
            if ( v22 < 0 )
              abort();
          }
          else
          {
            v23 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v23, 0, (LPVOID)v21);
          }
          *((_QWORD *)a1 + 32) = 0;
        }
      }
      std::vector<unsigned char,asg::secure_allocator<unsigned char>>::_Tidy(a1 + 112);
      *((_QWORD *)a1 + 52) = a1 + 8;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(a1 + 208) )
        goto LABEL_48;
      return;
    case 5:
      v16 = (volatile __int64 *)*((_QWORD *)a1 + 48);
      if ( v16 )
      {
        v28 = *((_QWORD *)a1 + 48);
        while ( _InterlockedExchange64(v16, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 47) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 188);
      if ( *((_BYTE *)a1 + 288) )
      {
        v17 = (volatile signed __int32 *)*((_QWORD *)a1 + 32);
        if ( v17 )
        {
          v18 = _InterlockedDecrement(v17 + 6);
          if ( v18 )
          {
            if ( v18 < 0 )
              abort();
          }
          else
          {
            v19 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v19, 0, (LPVOID)v17);
          }
          *((_QWORD *)a1 + 32) = 0;
        }
      }
      std::vector<unsigned char,asg::secure_allocator<unsigned char>>::_Tidy(a1 + 112);
LABEL_48:
      if ( *((_QWORD *)a1 + 13) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 52);
      if ( *((_QWORD *)a1 + 12) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 48);
      __ExceptionPtrDestroy(a1 + 36);
      winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::hstring,std::map<winrt::hstring,winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>>::subtract_final_reference(a1 + 8);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      if ( *((_QWORD *)a1 + 18) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 72);
      if ( a1[77] )
        operator delete(a1);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18022c4c0  mov     [rsp+Block], rcx
0x18022c4c5  push    rbx
0x18022c4c6  push    rsi
0x18022c4c7  push    rdi
0x18022c4c8  push    r12
0x18022c4ca  push    r13
0x18022c4cc  push    r14
0x18022c4ce  push    r15
0x18022c4d0  sub     rsp, 120h
0x18022c4d7  mov     rbx, [rsp+158h+Block]
0x18022c4df  lea     r15, [rbx+98h]
0x18022c4e6  mov     [rsp+158h+arg_18], r15
0x18022c4ee  movzx   eax, word ptr [r15]
0x18022c4f2  mov     [rsp+158h+var_138], ax
0x18022c4f7  inc     ax; switch 7 cases
0x18022c4fa  cmp     ax, 6
0x18022c4fe  ja      def_18022C519; jumptable 000000018022C519 default case, case 0
0x18022c504  movsx   rax, ax
0x18022c508  lea     rdx, cs:180000000h
0x18022c50f  mov     ecx, ds:(jpt_18022C519 - 180000000h)[rdx+rax*4]
0x18022c516  add     rcx, rdx
0x18022c519  jmp     rcx; switch jump
0x18022c51b  mov     edi, 0FFFFFFFFh; jumptable 000000018022C519 case 3
0x18022c520  jmp     loc_18022CA35
0x18022c525  xor     esi, esi; jumptable 000000018022C519 case 2
0x18022c527  mov     rcx, [rbx+90h]
0x18022c52e  test    rcx, rcx
0x18022c531  jnz     short loc_18022C58E
0x18022c533  mov     dword ptr [rbx+0A0h], 54h ; 'T'
0x18022c53d  lea     rax, aCW1SSrcSemanti_19; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18022c544  mov     [rbx+0A8h], rax
0x18022c54b  mov     [rbx+0B0h], rsi
0x18022c552  lea     rdx, aOptions; "options"
0x18022c559  lea     rcx, [rbx+0B8h]; this
0x18022c560  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18022c565  lea     r8, [rbx+0A0h]; struct winrt::impl::slim_source_location *
0x18022c56c  lea     rdx, [rbx+0B8h]; struct winrt::param::hstring *
0x18022c573  lea     rcx, [rsp+158h+pExceptionObject]; this
0x18022c578  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18022c57d  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18022c584  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x18022c589  call    _CxxThrowException
0x18022c58e  mov     [rbx+0D8h], rcx
0x18022c595  mov     rax, [rcx]
0x18022c598  mov     rax, [rax+8]
0x18022c59c  call    cs:__guard_dispatch_icall_fptr
0x18022c5a2  lea     rcx, [rbx+0E0h]
0x18022c5a9  lea     rdx, [rbx+0D8h]
0x18022c5b0  call    ?GetDbAesKeyStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUDbAesKeyStore@Sqlite@asg@@USemanticImageIndexStoreOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions)
0x18022c5b5  nop
0x18022c5b6  mov     byte ptr [rbx+120h], 0
0x18022c5bd  mov     [rbx+1C8h], rsi
0x18022c5c4  mov     rcx, [rbx+90h]
0x18022c5cb  mov     dword ptr [rbx+1D0h], 72Dh
0x18022c5d5  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022c5dc  mov     [rbx+1D8h], rax
0x18022c5e3  mov     [rbx+1E0h], rsi
0x18022c5ea  mov     rax, [rcx]
0x18022c5ed  lea     rdx, [rbx+1C8h]
0x18022c5f4  mov     rax, [rax+30h]
0x18022c5f8  call    cs:__guard_dispatch_icall_fptr
0x18022c5fe  test    eax, eax
0x18022c600  jns     short loc_18022C613
0x18022c602  lfence
0x18022c605  lea     rdx, [rbx+1D0h]
0x18022c60c  mov     ecx, eax
0x18022c60e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18022c613  mov     rdi, [rbx+1C8h]
0x18022c61a  mov     [rbx+128h], rdi
0x18022c621  mov     rcx, [rbx+0E8h]
0x18022c628  mov     [rbx+130h], rcx
0x18022c62f  mov     rax, [rbx+0F0h]
0x18022c636  mov     [rsp+158h+var_A0], rax
0x18022c63e  mov     [rsp+158h+var_A8], rcx
0x18022c646  sub     rax, rcx
0x18022c649  mov     [rbx+138h], rax
0x18022c650  mov     [rbx+1C0h], esi
0x18022c656  mov     rcx, [rbx+90h]
0x18022c65d  mov     dword ptr [rbx+1E8h], 73Fh
0x18022c667  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022c66e  mov     [rbx+1F0h], rax
0x18022c675  mov     [rbx+1F8h], rsi
0x18022c67c  mov     rax, [rcx]
0x18022c67f  lea     rdx, [rbx+1C0h]
0x18022c686  mov     rax, [rax+38h]
0x18022c68a  call    cs:__guard_dispatch_icall_fptr
0x18022c690  test    eax, eax
0x18022c692  jns     short loc_18022C6A5
0x18022c694  lfence
0x18022c697  lea     rdx, [rbx+1E8h]
0x18022c69e  mov     ecx, eax
0x18022c6a0  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18022c6a5  mov     eax, [rbx+1C0h]
0x18022c6ab  mov     [rbx+140h], eax
0x18022c6b1  cmp     byte ptr [rbx+120h], 0
0x18022c6b8  jz      short loc_18022C6F2
0x18022c6ba  lea     rdx, [rbx+128h]
0x18022c6c1  lea     rcx, [rbx+100h]
0x18022c6c8  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18022c6cd  movups  xmm0, xmmword ptr [rbx+130h]
0x18022c6d4  movups  [rsp+158h+var_100], xmm0
0x18022c6d9  movups  xmmword ptr [rbx+108h], xmm0
0x18022c6e0  mov     eax, [rbx+140h]
0x18022c6e6  mov     [rsp+158h+var_F0], eax
0x18022c6ea  mov     [rbx+118h], eax
0x18022c6f0  jmp     short loc_18022C72C
0x18022c6f2  mov     [rbx+128h], rsi
0x18022c6f9  mov     [rsp+158h+var_E8], rdi
0x18022c6fe  mov     [rbx+100h], rdi
0x18022c705  movups  xmm0, xmmword ptr [rbx+130h]
0x18022c70c  movups  [rsp+158h+var_100], xmm0
0x18022c711  movups  xmmword ptr [rbx+108h], xmm0
0x18022c718  mov     [rsp+158h+arg_8], eax
0x18022c71f  mov     [rbx+118h], eax
0x18022c725  mov     byte ptr [rbx+120h], 1
0x18022c72c  mov     r14, [rbx+128h]
0x18022c733  mov     edi, 0FFFFFFFFh
0x18022c738  test    r14, r14
0x18022c73b  jz      short loc_18022C772
0x18022c73d  mov     [rsp+158h+var_108], r14
0x18022c742  mov     eax, edi
0x18022c744  lock xadd [r14+18h], eax
0x18022c74a  sub     eax, 1
0x18022c74d  jnz     short loc_18022C768
0x18022c74f  mov     [rsp+158h+var_108], r14
0x18022c754  call    WINRT_IMPL_GetProcessHeap
0x18022c759  mov     rcx, rax; hHeap
0x18022c75c  mov     r8, r14; lpMem
0x18022c75f  xor     edx, edx; dwFlags
0x18022c761  call    WINRT_IMPL_HeapFree
0x18022c766  jmp     short loc_18022C772
0x18022c768  test    eax, eax
0x18022c76a  jns     short loc_18022C772
0x18022c76c  call    abort
0x18022c772  lea     r14, [rbx+148h]
0x18022c779  mov     [rbx+170h], r14
0x18022c780  mov     byte ptr [rbx+168h], 0
0x18022c787  cmp     byte ptr [rbx+120h], 0
0x18022c78e  jz      short loc_18022C7CE
0x18022c790  mov     rcx, [rbx+100h]; this
0x18022c797  mov     [rsp+158h+var_130], rcx
0x18022c79c  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18022c7a1  mov     [r14], rax
0x18022c7a4  movups  xmm0, xmmword ptr [rbx+108h]
0x18022c7ab  movups  [rsp+158h+var_128], xmm0
0x18022c7b0  movups  xmmword ptr [rbx+150h], xmm0
0x18022c7b7  mov     eax, [rbx+118h]
0x18022c7bd  mov     [rsp+158h+var_118], eax
0x18022c7c1  mov     [rbx+160h], eax
0x18022c7c7  mov     byte ptr [rbx+168h], 1
0x18022c7ce  lea     rdx, [rbx+178h]
0x18022c7d5  mov     r8, r14
0x18022c7d8  mov     rcx, [rbx+88h]
0x18022c7df  call    ?TryLoadCoreAsync@ImageEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AU?$IAsyncOperation@_N@Foundation@Windows@8@V?$optional@UVectorSpaceResolutionOptions@ImageEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::TryLoadCoreAsync(std::optional<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::VectorSpaceResolutionOptions>)
0x18022c7e4  nop
0x18022c7e5  mov     ecx, [rbx+70h]
0x18022c7e8  cmp     ecx, 2
0x18022c7eb  jnz     short loc_18022C830
0x18022c7ed  lea     rdx, [rbx+200h]; struct winrt::impl::slim_source_location *
0x18022c7f4  mov     dword ptr [rdx], 1628h
0x18022c7fa  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022c801  mov     [rbx+208h], rax
0x18022c808  mov     [rbx+210h], rsi
0x18022c80f  lea     rcx, [rsp+158h+var_C8]; this
0x18022c817  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022c81c  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022c823  lea     rcx, [rsp+158h+var_C8]; pExceptionObject
0x18022c82b  call    _CxxThrowException
0x18022c830  lea     rcx, [rbx+180h]
0x18022c837  mov     [rcx], rsi
0x18022c83a  mov     [rbx+188h], rax
0x18022c841  mov     [rbx+190h], rsi
0x18022c848  mov     byte ptr [rbx+198h], 1
0x18022c84f  mov     eax, 4
0x18022c854  mov     [r15], ax
0x18022c858  mov     rdx, rbx
0x18022c85b  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x18022c860  test    al, al
0x18022c862  jz      loc_18022C935
0x18022c868  jmp     loc_18022CAA8
0x18022c86d  mov     rdi, [rbx+180h]; jumptable 000000018022C519 case 5
0x18022c874  xor     esi, esi
0x18022c876  test    rdi, rdi
0x18022c879  jz      short loc_18022C8A1
0x18022c87b  mov     [rsp+158h+var_90], rdi
0x18022c883  mov     eax, esi
0x18022c885  xchg    rax, [rdi]
0x18022c888  cmp     rax, 1
0x18022c88c  jnz     short loc_18022C8A1
0x18022c88e  xchg    ax, ax
0x18022c890  call    _Thrd_yield
0x18022c895  mov     rax, rsi
0x18022c898  xchg    rax, [rdi]
0x18022c89b  cmp     rax, 1
0x18022c89f  jz      short loc_18022C890
0x18022c8a1  lea     rcx, [rbx+178h]
0x18022c8a8  mov     rax, [rcx]
0x18022c8ab  mov     [rsp+158h+arg_10], rax
0x18022c8b3  test    rax, rax
0x18022c8b6  jz      short loc_18022C8BE
0x18022c8b8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022c8bd  nop
0x18022c8be  movzx   eax, byte ptr [rbx+120h]
0x18022c8c5  mov     [rsp+158h+var_110], al
0x18022c8c9  test    al, al
0x18022c8cb  jz      short loc_18022C917
0x18022c8cd  mov     r14, [rbx+100h]
0x18022c8d4  test    r14, r14
0x18022c8d7  jz      short loc_18022C917
0x18022c8d9  mov     [rsp+158h+var_130], r14
0x18022c8de  mov     edi, 0FFFFFFFFh
0x18022c8e3  mov     eax, edi
0x18022c8e5  lock xadd [r14+18h], eax
0x18022c8eb  sub     eax, 1
0x18022c8ee  jnz     short loc_18022C904
0x18022c8f0  call    WINRT_IMPL_GetProcessHeap
0x18022c8f5  mov     rcx, rax; hHeap
0x18022c8f8  mov     r8, r14; lpMem
0x18022c8fb  xor     edx, edx; dwFlags
0x18022c8fd  call    WINRT_IMPL_HeapFree
0x18022c902  jmp     short loc_18022C90E
0x18022c904  test    eax, eax
0x18022c906  jns     short loc_18022C90E
0x18022c908  call    abort
0x18022c90e  mov     [rbx+100h], rsi
0x18022c915  jmp     short loc_18022C91C
0x18022c917  mov     edi, 0FFFFFFFFh
0x18022c91c  lea     rcx, [rbx+0E0h]
0x18022c923  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x18022c928  nop
0x18022c929  jmp     loc_18022CA35
0x18022c92e  xor     esi, esi; jumptable 000000018022C519 case 4
0x18022c930  mov     edi, 0FFFFFFFFh
0x18022c935  lea     rcx, [rbx+180h]
0x18022c93c  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x18022c941  mov     [rbx+78h], al
0x18022c944  mov     r14, [rbx+180h]
0x18022c94b  test    r14, r14
0x18022c94e  jz      short loc_18022C975
0x18022c950  mov     [rsp+158h+var_90], r14
0x18022c958  mov     rax, rsi
0x18022c95b  xchg    rax, [r14]
0x18022c95e  cmp     rax, 1
0x18022c962  jnz     short loc_18022C975
0x18022c964  call    _Thrd_yield
0x18022c969  mov     rax, rsi
0x18022c96c  xchg    rax, [r14]
0x18022c96f  cmp     rax, 1
0x18022c973  jz      short loc_18022C964
0x18022c975  lea     rcx, [rbx+178h]
0x18022c97c  mov     rax, [rcx]
0x18022c97f  mov     [rsp+158h+arg_10], rax
0x18022c987  test    rax, rax
0x18022c98a  jz      short loc_18022C992
0x18022c98c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022c991  nop
0x18022c992  movzx   eax, byte ptr [rbx+120h]
0x18022c999  mov     [rsp+158h+var_110], al
0x18022c99d  test    al, al
0x18022c99f  jz      short loc_18022C9E4
0x18022c9a1  mov     r14, [rbx+100h]
0x18022c9a8  test    r14, r14
0x18022c9ab  jz      short loc_18022C9E4
0x18022c9ad  mov     [rsp+158h+var_130], r14
0x18022c9b2  mov     eax, edi
0x18022c9b4  lock xadd [r14+18h], eax
0x18022c9ba  sub     eax, 1
0x18022c9bd  jnz     short loc_18022C9D3
0x18022c9bf  call    WINRT_IMPL_GetProcessHeap
0x18022c9c4  mov     rcx, rax; hHeap
0x18022c9c7  mov     r8, r14; lpMem
0x18022c9ca  xor     edx, edx; dwFlags
0x18022c9cc  call    WINRT_IMPL_HeapFree
0x18022c9d1  jmp     short loc_18022C9DD
0x18022c9d3  test    eax, eax
0x18022c9d5  jns     short loc_18022C9DD
0x18022c9d7  call    abort
0x18022c9dd  mov     [rbx+100h], rsi
0x18022c9e4  lea     rcx, [rbx+0E0h]
0x18022c9eb  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x18022c9f0  nop
0x18022c9f1  jmp     short loc_18022CA0A
0x18022c9f3  xor     esi, esi
0x18022c9f5  mov     edi, 0FFFFFFFFh
0x18022c9fa  mov     rbx, [rsp+158h+Block]
0x18022ca02  mov     r15, [rsp+158h+arg_18]
0x18022ca0a  lea     rax, [rbx+10h]
0x18022ca0e  lea     rcx, [rbx+1A0h]
0x18022ca15  mov     [rcx], rax
0x18022ca18  xor     eax, eax
0x18022ca1a  mov     [r15], ax
0x18022ca1e  mov     [rbx], rsi
0x18022ca21  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@AEBUQueryEmbeddings@789Asg@Microsoft@4@USemanticQueryOptions@789Asg@Microsoft@4@@std@@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18022ca26  test    al, al
0x18022ca28  jz      short loc_18022CA35
0x18022ca2a  jmp     short loc_18022CAA8
0x18022ca30  mov     edi, 0FFFFFFFFh; jumptable 000000018022C519 cases -1,1
0x18022ca35  lea     rcx, [rbx+68h]
0x18022ca39  cmp     qword ptr [rcx], 0
0x18022ca3d  jz      short loc_18022CA44
  ... truncated ...
```
