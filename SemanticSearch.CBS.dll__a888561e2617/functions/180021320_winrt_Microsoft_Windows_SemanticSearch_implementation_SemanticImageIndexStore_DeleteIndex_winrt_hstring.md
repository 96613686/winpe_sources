# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::DeleteIndex(winrt::hstring)

- ea: `0x180021320`
- end: `0x1800213ff`
- name: `?DeleteIndex@SemanticImageIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@SAXUhstring@6@@Z`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800220a0`

## callees

- `0x180009580`
- `0x180021320`
- `0x1800301b0`
- `0x180051379`
- `0x18005137f`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800213e8`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800213e8`

## string_xrefs

- `0x180021369`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::DeleteIndex(
        _QWORD *a1)
{
  int result; // eax
  volatile signed __int32 *v3; // rdi
  HANDLE ProcessHeap; // rax
  _QWORD *v5[4]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v6; // [rsp+40h] [rbp-28h] BYREF

  v5[2] = a1;
  v6 = *a1;
  v5[0] = &v6;
  v5[3] = &qword_180086938;
  _InterlockedIncrement64(&qword_180086938);
  if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> )
  {
    LODWORD(v5[0]) = 763;
    v5[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt"
            "\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
                                                         + 168LL))(
               winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
               v6);
    if ( result < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)result, v5);
    }
    _InterlockedDecrement64(&qword_180086938);
  }
  else
  {
    _InterlockedDecrement64(&qword_180086938);
    result = ___call_AEAV_lambda_1___1__DeleteIndex_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUhstring_param_9__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__DeleteIndex_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUhstring_param_2__Z__Z(
               0,
               v5);
  }
  v3 = (volatile signed __int32 *)*a1;
  if ( *a1 )
  {
    result = _InterlockedDecrement(v3 + 6);
    if ( result )
    {
      if ( result < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      result = WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v3);
    }
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180021320  mov     r11, rsp
0x180021323  mov     [r11+10h], rbx
0x180021327  push    rdi
0x180021328  sub     rsp, 60h
0x18002132c  mov     rbx, rcx
0x18002132f  mov     [r11-38h], rcx
0x180021333  mov     rax, [rcx]
0x180021336  mov     [r11-28h], rax
0x18002133a  lea     rax, [r11-28h]
0x18002133e  mov     [r11-48h], rax
0x180021342  lea     rax, qword_180086938
0x180021349  mov     [r11-30h], rax
0x18002134d  lock inc cs:qword_180086938
0x180021355  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x18002135c  test    rcx, rcx
0x18002135f  jz      short loc_180021396
0x180021361  mov     [rsp+68h+var_48], 2FBh
0x180021369  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180021370  mov     [r11-40h], rax
0x180021374  mov     rax, [rcx]
0x180021377  mov     rdx, [r11-28h]
0x18002137b  mov     rax, [rax+0A8h]
0x180021382  call    cs:__guard_dispatch_icall_fptr
0x180021388  test    eax, eax
0x18002138a  js      short loc_1800213EF
0x18002138c  lock dec cs:qword_180086938
0x180021394  jmp     short loc_1800213A9
0x180021396  lock dec cs:qword_180086938
0x18002139e  lea     rdx, [rsp+68h+var_48]
0x1800213a3  call    ??$call@AEAV_lambda_1_@?1??DeleteIndex@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUhstring@param@9@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??DeleteIndex@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUhstring@param@2@@Z@@Z
0x1800213a8  nop
0x1800213a9  mov     rdi, [rbx]
0x1800213ac  test    rdi, rdi
0x1800213af  jz      short loc_1800213D9
0x1800213b1  mov     eax, 0FFFFFFFFh
0x1800213b6  lock xadd [rdi+18h], eax
0x1800213bb  sub     eax, 1
0x1800213be  jnz     short loc_1800213E4
0x1800213c0  call    WINRT_IMPL_GetProcessHeap
0x1800213c5  mov     rcx, rax; hHeap
0x1800213c8  mov     r8, rdi; lpMem
0x1800213cb  xor     edx, edx; dwFlags
0x1800213cd  call    WINRT_IMPL_HeapFree
0x1800213d2  mov     qword ptr [rbx], 0
0x1800213d9  mov     rbx, [rsp+68h+arg_8]
0x1800213de  add     rsp, 60h
0x1800213e2  pop     rdi
0x1800213e3  retn
0x1800213e4  test    eax, eax
0x1800213e6  jns     short loc_1800213D2
0x1800213e8  call    cs:__imp_abort
0x1800213ef  lfence
0x1800213f2  lea     rdx, [rsp+68h+var_48]
0x1800213f7  mov     ecx, eax
0x1800213f9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
