# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::DeleteIndex(winrt::hstring)

- ea: `0x180038c70`
- end: `0x180038d4c`
- name: `?DeleteIndex@SemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@SAXUhstring@6@@Z`
- size: `220`
- prototype: `int __fastcall(volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180039ff0`

## callees

- `0x180009580`
- `0x180038c70`
- `0x18003ca30`
- `0x180051379`
- `0x18005137f`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180038d35`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180038d35`

## string_xrefs

- `0x180038cb9`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::DeleteIndex(
        volatile signed __int32 **a1)
{
  int result; // eax
  volatile signed __int32 *v3; // rdi
  HANDLE ProcessHeap; // rax
  _QWORD v5[4]; // [rsp+20h] [rbp-48h] BYREF
  volatile signed __int32 *v6; // [rsp+40h] [rbp-28h] BYREF

  v5[2] = a1;
  v6 = *a1;
  v5[0] = &v6;
  v5[3] = &qword_180086A78;
  _InterlockedIncrement64(&qword_180086A78);
  if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> )
  {
    LODWORD(v5[0]) = 1209;
    v5[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt"
            "\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    result = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
                                                                           + 120LL))(
               winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
               v6);
    if ( result < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)result, v5);
    }
    _InterlockedDecrement64(&qword_180086A78);
  }
  else
  {
    _InterlockedDecrement64(&qword_180086A78);
    result = ___call_AEAV_lambda_1___1__DeleteIndex_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUhstring_param_9__Z____factory_cache_entry_USemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticTextIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__DeleteIndex_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUhstring_param_2__Z__Z(
               0,
               v5);
  }
  v3 = *a1;
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
0x180038c70  mov     r11, rsp
0x180038c73  mov     [r11+10h], rbx
0x180038c77  push    rdi
0x180038c78  sub     rsp, 60h
0x180038c7c  mov     rbx, rcx
0x180038c7f  mov     [r11-38h], rcx
0x180038c83  mov     rax, [rcx]
0x180038c86  mov     [r11-28h], rax
0x180038c8a  lea     rax, [r11-28h]
0x180038c8e  mov     [r11-48h], rax
0x180038c92  lea     rax, qword_180086A78
0x180038c99  mov     [r11-30h], rax
0x180038c9d  lock inc cs:qword_180086A78
0x180038ca5  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x180038cac  test    rcx, rcx
0x180038caf  jz      short loc_180038CE3
0x180038cb1  mov     dword ptr [rsp+68h+var_48], 4B9h
0x180038cb9  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180038cc0  mov     [r11-40h], rax
0x180038cc4  mov     rax, [rcx]
0x180038cc7  mov     rdx, [r11-28h]
0x180038ccb  mov     rax, [rax+78h]
0x180038ccf  call    cs:__guard_dispatch_icall_fptr
0x180038cd5  test    eax, eax
0x180038cd7  js      short loc_180038D3C
0x180038cd9  lock dec cs:qword_180086A78
0x180038ce1  jmp     short loc_180038CF6
0x180038ce3  lock dec cs:qword_180086A78
0x180038ceb  lea     rdx, [rsp+68h+var_48]
0x180038cf0  call    ??$call@AEAV_lambda_1_@?1??DeleteIndex@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUhstring@param@9@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??DeleteIndex@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUhstring@param@2@@Z@@Z
0x180038cf5  nop
0x180038cf6  mov     rdi, [rbx]
0x180038cf9  test    rdi, rdi
0x180038cfc  jz      short loc_180038D26
0x180038cfe  mov     eax, 0FFFFFFFFh
0x180038d03  lock xadd [rdi+18h], eax
0x180038d08  sub     eax, 1
0x180038d0b  jnz     short loc_180038D31
0x180038d0d  call    WINRT_IMPL_GetProcessHeap
0x180038d12  mov     rcx, rax; hHeap
0x180038d15  mov     r8, rdi; lpMem
0x180038d18  xor     edx, edx; dwFlags
0x180038d1a  call    WINRT_IMPL_HeapFree
0x180038d1f  mov     qword ptr [rbx], 0
0x180038d26  mov     rbx, [rsp+68h+arg_8]
0x180038d2b  add     rsp, 60h
0x180038d2f  pop     rdi
0x180038d30  retn
0x180038d31  test    eax, eax
0x180038d33  jns     short loc_180038D1F
0x180038d35  call    cs:__imp_abort
0x180038d3c  lfence
0x180038d3f  lea     rdx, [rsp+68h+var_48]
0x180038d44  mov     ecx, eax
0x180038d46  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
