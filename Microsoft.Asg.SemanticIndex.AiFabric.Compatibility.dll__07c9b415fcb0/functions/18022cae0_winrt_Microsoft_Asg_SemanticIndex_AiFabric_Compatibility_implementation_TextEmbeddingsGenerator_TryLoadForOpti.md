# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadForOptionsAsync$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions_

- ea: `0x18022cae0`
- end: `0x18022d0f8`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadForOptionsAsync$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions_`
- size: `1560`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18022c4b0`
- `0x18022d5b0`

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
- `0x1800681e0`
- `0x180078d00`
- `0x180078d10`
- `0x1801d1e70`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x18022cae0`
- `0x180242120`

## string_xrefs

- `0x18022cbf5`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18022cc87`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18022ce1a`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18022cb5d`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\TextEmbeddingsGenerator.h`

## pseudocode

```c
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadForOptionsAsync__ResumeCoro_1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions_(
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
0x18022cae0  mov     [rsp+Block], rcx
0x18022cae5  push    rbx
0x18022cae6  push    rsi
0x18022cae7  push    rdi
0x18022cae8  push    r12
0x18022caea  push    r13
0x18022caec  push    r14
0x18022caee  push    r15
0x18022caf0  sub     rsp, 120h
0x18022caf7  mov     rbx, [rsp+158h+Block]
0x18022caff  lea     r15, [rbx+98h]
0x18022cb06  mov     [rsp+158h+arg_18], r15
0x18022cb0e  movzx   eax, word ptr [r15]
0x18022cb12  mov     [rsp+158h+var_138], ax
0x18022cb17  inc     ax; switch 7 cases
0x18022cb1a  cmp     ax, 6
0x18022cb1e  ja      def_18022CB39; jumptable 000000018022CB39 default case, case 0
0x18022cb24  movsx   rax, ax
0x18022cb28  lea     rdx, cs:180000000h
0x18022cb2f  mov     ecx, ds:(jpt_18022CB39 - 180000000h)[rdx+rax*4]
0x18022cb36  add     rcx, rdx
0x18022cb39  jmp     rcx; switch jump
0x18022cb3b  mov     edi, 0FFFFFFFFh; jumptable 000000018022CB39 case 3
0x18022cb40  jmp     loc_18022D055
0x18022cb45  xor     esi, esi; jumptable 000000018022CB39 case 2
0x18022cb47  mov     rcx, [rbx+90h]
0x18022cb4e  test    rcx, rcx
0x18022cb51  jnz     short loc_18022CBAE
0x18022cb53  mov     dword ptr [rbx+0A0h], 6Bh ; 'k'
0x18022cb5d  lea     rax, aCW1SSrcSemanti_4; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18022cb64  mov     [rbx+0A8h], rax
0x18022cb6b  mov     [rbx+0B0h], rsi
0x18022cb72  lea     rdx, aOptions; "options"
0x18022cb79  lea     rcx, [rbx+0B8h]; this
0x18022cb80  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18022cb85  lea     r8, [rbx+0A0h]; struct winrt::impl::slim_source_location *
0x18022cb8c  lea     rdx, [rbx+0B8h]; struct winrt::param::hstring *
0x18022cb93  lea     rcx, [rsp+158h+pExceptionObject]; this
0x18022cb98  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18022cb9d  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18022cba4  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x18022cba9  call    _CxxThrowException
0x18022cbae  mov     [rbx+0D8h], rcx
0x18022cbb5  mov     rax, [rcx]
0x18022cbb8  mov     rax, [rax+8]
0x18022cbbc  call    cs:__guard_dispatch_icall_fptr
0x18022cbc2  lea     rcx, [rbx+0E0h]
0x18022cbc9  lea     rdx, [rbx+0D8h]
0x18022cbd0  call    ?GetDbAesKeyStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUDbAesKeyStore@Sqlite@asg@@USemanticImageIndexStoreOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions)
0x18022cbd5  nop
0x18022cbd6  mov     byte ptr [rbx+120h], 0
0x18022cbdd  mov     [rbx+1C8h], rsi
0x18022cbe4  mov     rcx, [rbx+90h]
0x18022cbeb  mov     dword ptr [rbx+1D0h], 72Dh
0x18022cbf5  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022cbfc  mov     [rbx+1D8h], rax
0x18022cc03  mov     [rbx+1E0h], rsi
0x18022cc0a  mov     rax, [rcx]
0x18022cc0d  lea     rdx, [rbx+1C8h]
0x18022cc14  mov     rax, [rax+30h]
0x18022cc18  call    cs:__guard_dispatch_icall_fptr
0x18022cc1e  test    eax, eax
0x18022cc20  jns     short loc_18022CC33
0x18022cc22  lfence
0x18022cc25  lea     rdx, [rbx+1D0h]
0x18022cc2c  mov     ecx, eax
0x18022cc2e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18022cc33  mov     rdi, [rbx+1C8h]
0x18022cc3a  mov     [rbx+128h], rdi
0x18022cc41  mov     rcx, [rbx+0E8h]
0x18022cc48  mov     [rbx+130h], rcx
0x18022cc4f  mov     rax, [rbx+0F0h]
0x18022cc56  mov     [rsp+158h+var_A0], rax
0x18022cc5e  mov     [rsp+158h+var_A8], rcx
0x18022cc66  sub     rax, rcx
0x18022cc69  mov     [rbx+138h], rax
0x18022cc70  mov     [rbx+1C0h], esi
0x18022cc76  mov     rcx, [rbx+90h]
0x18022cc7d  mov     dword ptr [rbx+1E8h], 73Fh
0x18022cc87  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022cc8e  mov     [rbx+1F0h], rax
0x18022cc95  mov     [rbx+1F8h], rsi
0x18022cc9c  mov     rax, [rcx]
0x18022cc9f  lea     rdx, [rbx+1C0h]
0x18022cca6  mov     rax, [rax+38h]
0x18022ccaa  call    cs:__guard_dispatch_icall_fptr
0x18022ccb0  test    eax, eax
0x18022ccb2  jns     short loc_18022CCC5
0x18022ccb4  lfence
0x18022ccb7  lea     rdx, [rbx+1E8h]
0x18022ccbe  mov     ecx, eax
0x18022ccc0  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18022ccc5  mov     eax, [rbx+1C0h]
0x18022cccb  mov     [rbx+140h], eax
0x18022ccd1  cmp     byte ptr [rbx+120h], 0
0x18022ccd8  jz      short loc_18022CD12
0x18022ccda  lea     rdx, [rbx+128h]
0x18022cce1  lea     rcx, [rbx+100h]
0x18022cce8  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18022cced  movups  xmm0, xmmword ptr [rbx+130h]
0x18022ccf4  movups  [rsp+158h+var_100], xmm0
0x18022ccf9  movups  xmmword ptr [rbx+108h], xmm0
0x18022cd00  mov     eax, [rbx+140h]
0x18022cd06  mov     [rsp+158h+var_F0], eax
0x18022cd0a  mov     [rbx+118h], eax
0x18022cd10  jmp     short loc_18022CD4C
0x18022cd12  mov     [rbx+128h], rsi
0x18022cd19  mov     [rsp+158h+var_E8], rdi
0x18022cd1e  mov     [rbx+100h], rdi
0x18022cd25  movups  xmm0, xmmword ptr [rbx+130h]
0x18022cd2c  movups  [rsp+158h+var_100], xmm0
0x18022cd31  movups  xmmword ptr [rbx+108h], xmm0
0x18022cd38  mov     [rsp+158h+arg_8], eax
0x18022cd3f  mov     [rbx+118h], eax
0x18022cd45  mov     byte ptr [rbx+120h], 1
0x18022cd4c  mov     r14, [rbx+128h]
0x18022cd53  mov     edi, 0FFFFFFFFh
0x18022cd58  test    r14, r14
0x18022cd5b  jz      short loc_18022CD92
0x18022cd5d  mov     [rsp+158h+var_108], r14
0x18022cd62  mov     eax, edi
0x18022cd64  lock xadd [r14+18h], eax
0x18022cd6a  sub     eax, 1
0x18022cd6d  jnz     short loc_18022CD88
0x18022cd6f  mov     [rsp+158h+var_108], r14
0x18022cd74  call    WINRT_IMPL_GetProcessHeap
0x18022cd79  mov     rcx, rax; hHeap
0x18022cd7c  mov     r8, r14; lpMem
0x18022cd7f  xor     edx, edx; dwFlags
0x18022cd81  call    WINRT_IMPL_HeapFree
0x18022cd86  jmp     short loc_18022CD92
0x18022cd88  test    eax, eax
0x18022cd8a  jns     short loc_18022CD92
0x18022cd8c  call    abort
0x18022cd92  lea     r14, [rbx+148h]
0x18022cd99  mov     [rbx+170h], r14
0x18022cda0  mov     byte ptr [rbx+168h], 0
0x18022cda7  cmp     byte ptr [rbx+120h], 0
0x18022cdae  jz      short loc_18022CDEE
0x18022cdb0  mov     rcx, [rbx+100h]; this
0x18022cdb7  mov     [rsp+158h+var_130], rcx
0x18022cdbc  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18022cdc1  mov     [r14], rax
0x18022cdc4  movups  xmm0, xmmword ptr [rbx+108h]
0x18022cdcb  movups  [rsp+158h+var_128], xmm0
0x18022cdd0  movups  xmmword ptr [rbx+150h], xmm0
0x18022cdd7  mov     eax, [rbx+118h]
0x18022cddd  mov     [rsp+158h+var_118], eax
0x18022cde1  mov     [rbx+160h], eax
0x18022cde7  mov     byte ptr [rbx+168h], 1
0x18022cdee  lea     rdx, [rbx+178h]
0x18022cdf5  mov     r8, r14
0x18022cdf8  mov     rcx, [rbx+88h]
0x18022cdff  call    ?TryLoadCoreAsync@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AU?$IAsyncOperation@_N@Foundation@Windows@8@V?$optional@UVectorSpaceResolutionOptions@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadCoreAsync(std::optional<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::VectorSpaceResolutionOptions>)
0x18022ce04  nop
0x18022ce05  mov     ecx, [rbx+70h]
0x18022ce08  cmp     ecx, 2
0x18022ce0b  jnz     short loc_18022CE50
0x18022ce0d  lea     rdx, [rbx+200h]; struct winrt::impl::slim_source_location *
0x18022ce14  mov     dword ptr [rdx], 1628h
0x18022ce1a  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022ce21  mov     [rbx+208h], rax
0x18022ce28  mov     [rbx+210h], rsi
0x18022ce2f  lea     rcx, [rsp+158h+var_C8]; this
0x18022ce37  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022ce3c  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022ce43  lea     rcx, [rsp+158h+var_C8]; pExceptionObject
0x18022ce4b  call    _CxxThrowException
0x18022ce50  lea     rcx, [rbx+180h]
0x18022ce57  mov     [rcx], rsi
0x18022ce5a  mov     [rbx+188h], rax
0x18022ce61  mov     [rbx+190h], rsi
0x18022ce68  mov     byte ptr [rbx+198h], 1
0x18022ce6f  mov     eax, 4
0x18022ce74  mov     [r15], ax
0x18022ce78  mov     rdx, rbx
0x18022ce7b  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x18022ce80  test    al, al
0x18022ce82  jz      loc_18022CF55
0x18022ce88  jmp     loc_18022D0C8
0x18022ce8d  mov     rdi, [rbx+180h]; jumptable 000000018022CB39 case 5
0x18022ce94  xor     esi, esi
0x18022ce96  test    rdi, rdi
0x18022ce99  jz      short loc_18022CEC1
0x18022ce9b  mov     [rsp+158h+var_90], rdi
0x18022cea3  mov     eax, esi
0x18022cea5  xchg    rax, [rdi]
0x18022cea8  cmp     rax, 1
0x18022ceac  jnz     short loc_18022CEC1
0x18022ceae  xchg    ax, ax
0x18022ceb0  call    _Thrd_yield
0x18022ceb5  mov     rax, rsi
0x18022ceb8  xchg    rax, [rdi]
0x18022cebb  cmp     rax, 1
0x18022cebf  jz      short loc_18022CEB0
0x18022cec1  lea     rcx, [rbx+178h]
0x18022cec8  mov     rax, [rcx]
0x18022cecb  mov     [rsp+158h+arg_10], rax
0x18022ced3  test    rax, rax
0x18022ced6  jz      short loc_18022CEDE
0x18022ced8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022cedd  nop
0x18022cede  movzx   eax, byte ptr [rbx+120h]
0x18022cee5  mov     [rsp+158h+var_110], al
0x18022cee9  test    al, al
0x18022ceeb  jz      short loc_18022CF37
0x18022ceed  mov     r14, [rbx+100h]
0x18022cef4  test    r14, r14
0x18022cef7  jz      short loc_18022CF37
0x18022cef9  mov     [rsp+158h+var_130], r14
0x18022cefe  mov     edi, 0FFFFFFFFh
0x18022cf03  mov     eax, edi
0x18022cf05  lock xadd [r14+18h], eax
0x18022cf0b  sub     eax, 1
0x18022cf0e  jnz     short loc_18022CF24
0x18022cf10  call    WINRT_IMPL_GetProcessHeap
0x18022cf15  mov     rcx, rax; hHeap
0x18022cf18  mov     r8, r14; lpMem
0x18022cf1b  xor     edx, edx; dwFlags
0x18022cf1d  call    WINRT_IMPL_HeapFree
0x18022cf22  jmp     short loc_18022CF2E
0x18022cf24  test    eax, eax
0x18022cf26  jns     short loc_18022CF2E
0x18022cf28  call    abort
0x18022cf2e  mov     [rbx+100h], rsi
0x18022cf35  jmp     short loc_18022CF3C
0x18022cf37  mov     edi, 0FFFFFFFFh
0x18022cf3c  lea     rcx, [rbx+0E0h]
0x18022cf43  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x18022cf48  nop
0x18022cf49  jmp     loc_18022D055
0x18022cf4e  xor     esi, esi; jumptable 000000018022CB39 case 4
0x18022cf50  mov     edi, 0FFFFFFFFh
0x18022cf55  lea     rcx, [rbx+180h]
0x18022cf5c  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x18022cf61  mov     [rbx+78h], al
0x18022cf64  mov     r14, [rbx+180h]
0x18022cf6b  test    r14, r14
0x18022cf6e  jz      short loc_18022CF95
0x18022cf70  mov     [rsp+158h+var_90], r14
0x18022cf78  mov     rax, rsi
0x18022cf7b  xchg    rax, [r14]
0x18022cf7e  cmp     rax, 1
0x18022cf82  jnz     short loc_18022CF95
0x18022cf84  call    _Thrd_yield
0x18022cf89  mov     rax, rsi
0x18022cf8c  xchg    rax, [r14]
0x18022cf8f  cmp     rax, 1
0x18022cf93  jz      short loc_18022CF84
0x18022cf95  lea     rcx, [rbx+178h]
0x18022cf9c  mov     rax, [rcx]
0x18022cf9f  mov     [rsp+158h+arg_10], rax
0x18022cfa7  test    rax, rax
0x18022cfaa  jz      short loc_18022CFB2
0x18022cfac  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022cfb1  nop
0x18022cfb2  movzx   eax, byte ptr [rbx+120h]
0x18022cfb9  mov     [rsp+158h+var_110], al
0x18022cfbd  test    al, al
0x18022cfbf  jz      short loc_18022D004
0x18022cfc1  mov     r14, [rbx+100h]
0x18022cfc8  test    r14, r14
0x18022cfcb  jz      short loc_18022D004
0x18022cfcd  mov     [rsp+158h+var_130], r14
0x18022cfd2  mov     eax, edi
0x18022cfd4  lock xadd [r14+18h], eax
0x18022cfda  sub     eax, 1
0x18022cfdd  jnz     short loc_18022CFF3
0x18022cfdf  call    WINRT_IMPL_GetProcessHeap
0x18022cfe4  mov     rcx, rax; hHeap
0x18022cfe7  mov     r8, r14; lpMem
0x18022cfea  xor     edx, edx; dwFlags
0x18022cfec  call    WINRT_IMPL_HeapFree
0x18022cff1  jmp     short loc_18022CFFD
0x18022cff3  test    eax, eax
0x18022cff5  jns     short loc_18022CFFD
0x18022cff7  call    abort
0x18022cffd  mov     [rbx+100h], rsi
0x18022d004  lea     rcx, [rbx+0E0h]
0x18022d00b  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x18022d010  nop
0x18022d011  jmp     short loc_18022D02A
0x18022d013  xor     esi, esi
0x18022d015  mov     edi, 0FFFFFFFFh
0x18022d01a  mov     rbx, [rsp+158h+Block]
0x18022d022  mov     r15, [rsp+158h+arg_18]
0x18022d02a  lea     rax, [rbx+10h]
0x18022d02e  lea     rcx, [rbx+1A0h]
0x18022d035  mov     [rcx], rax
0x18022d038  xor     eax, eax
0x18022d03a  mov     [r15], ax
0x18022d03e  mov     [rbx], rsi
0x18022d041  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@AEBUQueryEmbeddings@789Asg@Microsoft@4@USemanticQueryOptions@789Asg@Microsoft@4@@std@@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18022d046  test    al, al
0x18022d048  jz      short loc_18022D055
0x18022d04a  jmp     short loc_18022D0C8
0x18022d050  mov     edi, 0FFFFFFFFh; jumptable 000000018022CB39 cases -1,1
0x18022d055  lea     rcx, [rbx+68h]
0x18022d059  cmp     qword ptr [rcx], 0
0x18022d05d  jz      short loc_18022D064
  ... truncated ...
```
