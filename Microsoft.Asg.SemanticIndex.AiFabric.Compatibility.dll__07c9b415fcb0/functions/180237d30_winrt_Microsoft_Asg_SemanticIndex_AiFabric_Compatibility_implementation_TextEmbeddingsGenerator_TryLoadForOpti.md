# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadForOptionsAsync$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions_

- ea: `0x180237d30`
- end: `0x180238348`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadForOptionsAsync$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions_`
- size: `1560`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180237d20`
- `0x180238360`

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
- `0x180062570`
- `0x1800680b0`
- `0x180078d00`
- `0x180078d10`
- `0x1801d1e70`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x180237d30`
- `0x180242120`

## string_xrefs

- `0x180237e45`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180237ed7`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18023806a`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180237dad`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\TextEmbeddingsGenerator.h`

## pseudocode

```c
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadForOptionsAsync__ResumeCoro_1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions_(
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
        *((_DWORD *)a1 + 40) = 107;
        *((_QWORD *)a1 + 21) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\TextEmbeddingsGenerator.h";
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
      *((_DWORD *)a1 + 116) = 3339;
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
      *((_DWORD *)a1 + 122) = 3357;
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
      CoreAsync = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadCoreAsync(
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
0x180237d30  mov     [rsp+Block], rcx
0x180237d35  push    rbx
0x180237d36  push    rsi
0x180237d37  push    rdi
0x180237d38  push    r12
0x180237d3a  push    r13
0x180237d3c  push    r14
0x180237d3e  push    r15
0x180237d40  sub     rsp, 120h
0x180237d47  mov     rbx, [rsp+158h+Block]
0x180237d4f  lea     r15, [rbx+98h]
0x180237d56  mov     [rsp+158h+arg_18], r15
0x180237d5e  movzx   eax, word ptr [r15]
0x180237d62  mov     [rsp+158h+var_138], ax
0x180237d67  inc     ax; switch 7 cases
0x180237d6a  cmp     ax, 6
0x180237d6e  ja      def_180237D89; jumptable 0000000180237D89 default case, case 0
0x180237d74  movsx   rax, ax
0x180237d78  lea     rdx, cs:180000000h
0x180237d7f  mov     ecx, ds:(jpt_180237D89 - 180000000h)[rdx+rax*4]
0x180237d86  add     rcx, rdx
0x180237d89  jmp     rcx; switch jump
0x180237d8b  mov     edi, 0FFFFFFFFh; jumptable 0000000180237D89 case 3
0x180237d90  jmp     loc_1802382A5
0x180237d95  xor     esi, esi; jumptable 0000000180237D89 case 2
0x180237d97  mov     rcx, [rbx+90h]
0x180237d9e  test    rcx, rcx
0x180237da1  jnz     short loc_180237DFE
0x180237da3  mov     dword ptr [rbx+0A0h], 6Bh ; 'k'
0x180237dad  lea     rax, aCW1SSrcSemanti_4; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180237db4  mov     [rbx+0A8h], rax
0x180237dbb  mov     [rbx+0B0h], rsi
0x180237dc2  lea     rdx, aOptions; "options"
0x180237dc9  lea     rcx, [rbx+0B8h]; this
0x180237dd0  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180237dd5  lea     r8, [rbx+0A0h]; struct winrt::impl::slim_source_location *
0x180237ddc  lea     rdx, [rbx+0B8h]; struct winrt::param::hstring *
0x180237de3  lea     rcx, [rsp+158h+pExceptionObject]; this
0x180237de8  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180237ded  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180237df4  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180237df9  call    _CxxThrowException
0x180237dfe  mov     [rbx+0D8h], rcx
0x180237e05  mov     rax, [rcx]
0x180237e08  mov     rax, [rax+8]
0x180237e0c  call    cs:__guard_dispatch_icall_fptr
0x180237e12  lea     rcx, [rbx+0E0h]
0x180237e19  lea     rdx, [rbx+0D8h]
0x180237e20  call    ?GetDbAesKeyStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUDbAesKeyStore@Sqlite@asg@@USemanticTextIndexStoreOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions)
0x180237e25  nop
0x180237e26  mov     byte ptr [rbx+120h], 0
0x180237e2d  mov     [rbx+1C8h], rsi
0x180237e34  mov     rcx, [rbx+90h]
0x180237e3b  mov     dword ptr [rbx+1D0h], 0D0Bh
0x180237e45  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180237e4c  mov     [rbx+1D8h], rax
0x180237e53  mov     [rbx+1E0h], rsi
0x180237e5a  mov     rax, [rcx]
0x180237e5d  lea     rdx, [rbx+1C8h]
0x180237e64  mov     rax, [rax+30h]
0x180237e68  call    cs:__guard_dispatch_icall_fptr
0x180237e6e  test    eax, eax
0x180237e70  jns     short loc_180237E83
0x180237e72  lfence
0x180237e75  lea     rdx, [rbx+1D0h]
0x180237e7c  mov     ecx, eax
0x180237e7e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180237e83  mov     rdi, [rbx+1C8h]
0x180237e8a  mov     [rbx+128h], rdi
0x180237e91  mov     rcx, [rbx+0E8h]
0x180237e98  mov     [rbx+130h], rcx
0x180237e9f  mov     rax, [rbx+0F0h]
0x180237ea6  mov     [rsp+158h+var_A0], rax
0x180237eae  mov     [rsp+158h+var_A8], rcx
0x180237eb6  sub     rax, rcx
0x180237eb9  mov     [rbx+138h], rax
0x180237ec0  mov     [rbx+1C0h], esi
0x180237ec6  mov     rcx, [rbx+90h]
0x180237ecd  mov     dword ptr [rbx+1E8h], 0D1Dh
0x180237ed7  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180237ede  mov     [rbx+1F0h], rax
0x180237ee5  mov     [rbx+1F8h], rsi
0x180237eec  mov     rax, [rcx]
0x180237eef  lea     rdx, [rbx+1C0h]
0x180237ef6  mov     rax, [rax+38h]
0x180237efa  call    cs:__guard_dispatch_icall_fptr
0x180237f00  test    eax, eax
0x180237f02  jns     short loc_180237F15
0x180237f04  lfence
0x180237f07  lea     rdx, [rbx+1E8h]
0x180237f0e  mov     ecx, eax
0x180237f10  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180237f15  mov     eax, [rbx+1C0h]
0x180237f1b  mov     [rbx+140h], eax
0x180237f21  cmp     byte ptr [rbx+120h], 0
0x180237f28  jz      short loc_180237F62
0x180237f2a  lea     rdx, [rbx+128h]
0x180237f31  lea     rcx, [rbx+100h]
0x180237f38  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x180237f3d  movups  xmm0, xmmword ptr [rbx+130h]
0x180237f44  movups  [rsp+158h+var_100], xmm0
0x180237f49  movups  xmmword ptr [rbx+108h], xmm0
0x180237f50  mov     eax, [rbx+140h]
0x180237f56  mov     [rsp+158h+var_F0], eax
0x180237f5a  mov     [rbx+118h], eax
0x180237f60  jmp     short loc_180237F9C
0x180237f62  mov     [rbx+128h], rsi
0x180237f69  mov     [rsp+158h+var_E8], rdi
0x180237f6e  mov     [rbx+100h], rdi
0x180237f75  movups  xmm0, xmmword ptr [rbx+130h]
0x180237f7c  movups  [rsp+158h+var_100], xmm0
0x180237f81  movups  xmmword ptr [rbx+108h], xmm0
0x180237f88  mov     [rsp+158h+arg_8], eax
0x180237f8f  mov     [rbx+118h], eax
0x180237f95  mov     byte ptr [rbx+120h], 1
0x180237f9c  mov     r14, [rbx+128h]
0x180237fa3  mov     edi, 0FFFFFFFFh
0x180237fa8  test    r14, r14
0x180237fab  jz      short loc_180237FE2
0x180237fad  mov     [rsp+158h+var_108], r14
0x180237fb2  mov     eax, edi
0x180237fb4  lock xadd [r14+18h], eax
0x180237fba  sub     eax, 1
0x180237fbd  jnz     short loc_180237FD8
0x180237fbf  mov     [rsp+158h+var_108], r14
0x180237fc4  call    WINRT_IMPL_GetProcessHeap
0x180237fc9  mov     rcx, rax; hHeap
0x180237fcc  mov     r8, r14; lpMem
0x180237fcf  xor     edx, edx; dwFlags
0x180237fd1  call    WINRT_IMPL_HeapFree
0x180237fd6  jmp     short loc_180237FE2
0x180237fd8  test    eax, eax
0x180237fda  jns     short loc_180237FE2
0x180237fdc  call    abort
0x180237fe2  lea     r14, [rbx+148h]
0x180237fe9  mov     [rbx+170h], r14
0x180237ff0  mov     byte ptr [rbx+168h], 0
0x180237ff7  cmp     byte ptr [rbx+120h], 0
0x180237ffe  jz      short loc_18023803E
0x180238000  mov     rcx, [rbx+100h]; this
0x180238007  mov     [rsp+158h+var_130], rcx
0x18023800c  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180238011  mov     [r14], rax
0x180238014  movups  xmm0, xmmword ptr [rbx+108h]
0x18023801b  movups  [rsp+158h+var_128], xmm0
0x180238020  movups  xmmword ptr [rbx+150h], xmm0
0x180238027  mov     eax, [rbx+118h]
0x18023802d  mov     [rsp+158h+var_118], eax
0x180238031  mov     [rbx+160h], eax
0x180238037  mov     byte ptr [rbx+168h], 1
0x18023803e  lea     rdx, [rbx+178h]
0x180238045  mov     r8, r14
0x180238048  mov     rcx, [rbx+88h]
0x18023804f  call    ?TryLoadCoreAsync@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AU?$IAsyncOperation@_N@Foundation@Windows@8@V?$optional@UVectorSpaceResolutionOptions@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadCoreAsync(std::optional<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::VectorSpaceResolutionOptions>)
0x180238054  nop
0x180238055  mov     ecx, [rbx+70h]
0x180238058  cmp     ecx, 2
0x18023805b  jnz     short loc_1802380A0
0x18023805d  lea     rdx, [rbx+200h]; struct winrt::impl::slim_source_location *
0x180238064  mov     dword ptr [rdx], 1628h
0x18023806a  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180238071  mov     [rbx+208h], rax
0x180238078  mov     [rbx+210h], rsi
0x18023807f  lea     rcx, [rsp+158h+var_C8]; this
0x180238087  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18023808c  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180238093  lea     rcx, [rsp+158h+var_C8]; pExceptionObject
0x18023809b  call    _CxxThrowException
0x1802380a0  lea     rcx, [rbx+180h]
0x1802380a7  mov     [rcx], rsi
0x1802380aa  mov     [rbx+188h], rax
0x1802380b1  mov     [rbx+190h], rsi
0x1802380b8  mov     byte ptr [rbx+198h], 1
0x1802380bf  mov     eax, 4
0x1802380c4  mov     [r15], ax
0x1802380c8  mov     rdx, rbx
0x1802380cb  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x1802380d0  test    al, al
0x1802380d2  jz      loc_1802381A5
0x1802380d8  jmp     loc_180238318
0x1802380dd  mov     rdi, [rbx+180h]; jumptable 0000000180237D89 case 5
0x1802380e4  xor     esi, esi
0x1802380e6  test    rdi, rdi
0x1802380e9  jz      short loc_180238111
0x1802380eb  mov     [rsp+158h+var_90], rdi
0x1802380f3  mov     eax, esi
0x1802380f5  xchg    rax, [rdi]
0x1802380f8  cmp     rax, 1
0x1802380fc  jnz     short loc_180238111
0x1802380fe  xchg    ax, ax
0x180238100  call    _Thrd_yield
0x180238105  mov     rax, rsi
0x180238108  xchg    rax, [rdi]
0x18023810b  cmp     rax, 1
0x18023810f  jz      short loc_180238100
0x180238111  lea     rcx, [rbx+178h]
0x180238118  mov     rax, [rcx]
0x18023811b  mov     [rsp+158h+arg_10], rax
0x180238123  test    rax, rax
0x180238126  jz      short loc_18023812E
0x180238128  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023812d  nop
0x18023812e  movzx   eax, byte ptr [rbx+120h]
0x180238135  mov     [rsp+158h+var_110], al
0x180238139  test    al, al
0x18023813b  jz      short loc_180238187
0x18023813d  mov     r14, [rbx+100h]
0x180238144  test    r14, r14
0x180238147  jz      short loc_180238187
0x180238149  mov     [rsp+158h+var_130], r14
0x18023814e  mov     edi, 0FFFFFFFFh
0x180238153  mov     eax, edi
0x180238155  lock xadd [r14+18h], eax
0x18023815b  sub     eax, 1
0x18023815e  jnz     short loc_180238174
0x180238160  call    WINRT_IMPL_GetProcessHeap
0x180238165  mov     rcx, rax; hHeap
0x180238168  mov     r8, r14; lpMem
0x18023816b  xor     edx, edx; dwFlags
0x18023816d  call    WINRT_IMPL_HeapFree
0x180238172  jmp     short loc_18023817E
0x180238174  test    eax, eax
0x180238176  jns     short loc_18023817E
0x180238178  call    abort
0x18023817e  mov     [rbx+100h], rsi
0x180238185  jmp     short loc_18023818C
0x180238187  mov     edi, 0FFFFFFFFh
0x18023818c  lea     rcx, [rbx+0E0h]
0x180238193  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x180238198  nop
0x180238199  jmp     loc_1802382A5
0x18023819e  xor     esi, esi; jumptable 0000000180237D89 case 4
0x1802381a0  mov     edi, 0FFFFFFFFh
0x1802381a5  lea     rcx, [rbx+180h]
0x1802381ac  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x1802381b1  mov     [rbx+78h], al
0x1802381b4  mov     r14, [rbx+180h]
0x1802381bb  test    r14, r14
0x1802381be  jz      short loc_1802381E5
0x1802381c0  mov     [rsp+158h+var_90], r14
0x1802381c8  mov     rax, rsi
0x1802381cb  xchg    rax, [r14]
0x1802381ce  cmp     rax, 1
0x1802381d2  jnz     short loc_1802381E5
0x1802381d4  call    _Thrd_yield
0x1802381d9  mov     rax, rsi
0x1802381dc  xchg    rax, [r14]
0x1802381df  cmp     rax, 1
0x1802381e3  jz      short loc_1802381D4
0x1802381e5  lea     rcx, [rbx+178h]
0x1802381ec  mov     rax, [rcx]
0x1802381ef  mov     [rsp+158h+arg_10], rax
0x1802381f7  test    rax, rax
0x1802381fa  jz      short loc_180238202
0x1802381fc  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180238201  nop
0x180238202  movzx   eax, byte ptr [rbx+120h]
0x180238209  mov     [rsp+158h+var_110], al
0x18023820d  test    al, al
0x18023820f  jz      short loc_180238254
0x180238211  mov     r14, [rbx+100h]
0x180238218  test    r14, r14
0x18023821b  jz      short loc_180238254
0x18023821d  mov     [rsp+158h+var_130], r14
0x180238222  mov     eax, edi
0x180238224  lock xadd [r14+18h], eax
0x18023822a  sub     eax, 1
0x18023822d  jnz     short loc_180238243
0x18023822f  call    WINRT_IMPL_GetProcessHeap
0x180238234  mov     rcx, rax; hHeap
0x180238237  mov     r8, r14; lpMem
0x18023823a  xor     edx, edx; dwFlags
0x18023823c  call    WINRT_IMPL_HeapFree
0x180238241  jmp     short loc_18023824D
0x180238243  test    eax, eax
0x180238245  jns     short loc_18023824D
0x180238247  call    abort
0x18023824d  mov     [rbx+100h], rsi
0x180238254  lea     rcx, [rbx+0E0h]
0x18023825b  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x180238260  nop
0x180238261  jmp     short loc_18023827A
0x180238263  xor     esi, esi
0x180238265  mov     edi, 0FFFFFFFFh
0x18023826a  mov     rbx, [rsp+158h+Block]
0x180238272  mov     r15, [rsp+158h+arg_18]
0x18023827a  lea     rax, [rbx+10h]
0x18023827e  lea     rcx, [rbx+1A0h]
0x180238285  mov     [rcx], rax
0x180238288  xor     eax, eax
0x18023828a  mov     [r15], ax
0x18023828e  mov     [rbx], rsi
0x180238291  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@AEBUQueryEmbeddings@789Asg@Microsoft@4@USemanticQueryOptions@789Asg@Microsoft@4@@std@@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x180238296  test    al, al
0x180238298  jz      short loc_1802382A5
0x18023829a  jmp     short loc_180238318
0x1802382a0  mov     edi, 0FFFFFFFFh; jumptable 0000000180237D89 cases -1,1
0x1802382a5  lea     rcx, [rbx+68h]
0x1802382a9  cmp     qword ptr [rcx], 0
0x1802382ad  jz      short loc_1802382B4
  ... truncated ...
```
