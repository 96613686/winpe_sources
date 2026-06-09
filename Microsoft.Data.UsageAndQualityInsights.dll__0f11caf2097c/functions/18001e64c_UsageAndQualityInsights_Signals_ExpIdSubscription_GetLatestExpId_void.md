# UsageAndQualityInsights::Signals::ExpIdSubscription::GetLatestExpId(void)

- ea: `0x18001e64c`
- end: `0x18001e89d`
- name: `?GetLatestExpId@ExpIdSubscription@Signals@UsageAndQualityInsights@@AEAA?AU?$pair@_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@XZ`
- size: `593`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e18c`
- `0x18001f870`

## callees

- `0x1800033d0`
- `0x1800040a0`
- `0x180004140`
- `0x18000c844`
- `0x18000d9d4`
- `0x18000eee0`
- `0x180012dd4`
- `0x180016628`
- `0x18001e64c`
- `0x180020650`
- `0x180022230`
- `0x180022bb0`
- `0x180022d38`
- `0x180022fac`
- `0x18002379c`
- `0x180108010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e796`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e7a6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e796`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e7a6`

## string_xrefs

- `0x18001e6c2`: `onecore\base\usageandqualityinsights\service\lib\signals\expidsubscription.cpp`
- `0x18001e88b`: `onecore\base\usageandqualityinsights\service\lib\signals\expidsubscription.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall UsageAndQualityInsights::Signals::ExpIdSubscription::GetLatestExpId(__int64 a1, _QWORD *a2)
{
  int v3; // eax
  int v4; // eax
  __int64 v5; // r8
  int v6; // edi
  HANDLE ProcessHeap; // rax
  __int128 *v8; // rcx
  __int64 v9; // rbx
  int v11; // [rsp+20h] [rbp-69h]
  LPVOID lpMem; // [rsp+30h] [rbp-59h] BYREF
  __int64 v13; // [rsp+38h] [rbp-51h] BYREF
  _QWORD *v14; // [rsp+40h] [rbp-49h] BYREF
  int v15; // [rsp+48h] [rbp-41h]
  __int64 v16; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v17[2]; // [rsp+58h] [rbp-31h] BYREF
  _DWORD *v18; // [rsp+68h] [rbp-21h] BYREF
  _DWORD v19[4]; // [rsp+70h] [rbp-19h] BYREF
  __int128 *v20; // [rsp+80h] [rbp-9h]
  __int64 v21; // [rsp+88h] [rbp-1h]
  __int128 v22; // [rsp+A8h] [rbp+1Fh] BYREF
  __int128 v23; // [rsp+B8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v14 = a2;
  v13 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 16) + 32LL))(*(_QWORD *)(a1 + 16), &v13);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\signals\\expidsubscription.cpp",
      (const char *)(unsigned int)v3,
      v11);
  v16 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 40LL))(v13, &v16);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\signals\\expidsubscription.cpp",
      (const char *)(unsigned int)v4,
      v11);
  LOBYTE(v11) = v16 == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x35,
    (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\signals\\expidsubscription.cpp",
    (const char *)0x8000FFFFLL,
    v11,
    (bool)"Unexpected: flightId is null or empty.",
    (const char *)lpMem);
  v22 = 0;
  v23 = 0;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(v16 + 2 * v5) );
  std::wstring::_Construct<1,wchar_t const *>(&v22, v16, v5);
  v21 = *(_QWORD *)winrt::Windows::Security::Cryptography::Core::HashAlgorithmNames::Sha256();
  winrt::Windows::Security::Cryptography::Core::HashAlgorithmProvider::OpenAlgorithm((const struct winrt::param::hstring *)&v14);
  if ( lpMem )
  {
    v6 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v6 )
    {
      if ( v6 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, lpMem);
    }
    lpMem = 0;
  }
  v15 = 0;
  v8 = &v22;
  if ( *((_QWORD *)&v23 + 1) > 7u )
    v8 = (__int128 *)v22;
  if ( (_DWORD)v23 )
  {
    if ( *((_WORD *)v8 + (unsigned int)v23) )
      abort();
    v19[0] = 1;
    v19[1] = v23;
    v20 = v8;
    v18 = v19;
  }
  else
  {
    v18 = 0;
  }
  winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(
    (const struct winrt::param::hstring *)v17,
    (const enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *)&v18);
  winrt::impl::consume_Windows_Security_Cryptography_Core_IHashAlgorithmProvider<winrt::Windows::Security::Cryptography::Core::IHashAlgorithmProvider>::HashData(
    &v14,
    &lpMem,
    v17);
  v9 = *(_QWORD *)winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(&lpMem);
  if ( lpMem )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&lpMem);
  if ( v17[0] )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v17);
  if ( v14 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v14);
  *a2 = v9;
  std::wstring::wstring(a2 + 1, &v22);
  std::wstring::~wstring(&v22);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return a2;
}

```

## disassembly

```asm
0x18001e64c  mov     [rsp-8+arg_10], rbx
0x18001e651  mov     [rsp-8+arg_18], rsi
0x18001e656  push    rbp
0x18001e657  push    rdi
0x18001e658  push    r14
0x18001e65a  lea     rbp, [rsp-47h]
0x18001e65f  sub     rsp, 0D0h
0x18001e666  mov     rax, cs:__security_cookie
0x18001e66d  xor     rax, rsp
0x18001e670  mov     [rbp+57h+var_18], rax
0x18001e674  mov     rsi, rdx
0x18001e677  mov     [rbp+57h+var_A0], rdx
0x18001e67b  xor     r14d, r14d
0x18001e67e  mov     [rbp+57h+var_A8], r14
0x18001e682  mov     rcx, [rcx+10h]
0x18001e686  mov     rax, [rcx]
0x18001e689  mov     [rbp+57h+var_A8], r14
0x18001e68d  lea     rdx, [rbp+57h+var_A8]
0x18001e691  mov     rax, [rax+20h]
0x18001e695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e69a  mov     rcx, [rbp+5Fh]; this
0x18001e69e  test    eax, eax
0x18001e6a0  js      loc_18001E888
0x18001e6a6  mov     [rbp+57h+var_90], r14
0x18001e6aa  mov     rcx, [rbp+57h+var_A8]
0x18001e6ae  mov     rax, [rcx]
0x18001e6b1  lea     rdx, [rbp+57h+var_90]
0x18001e6b5  mov     rax, [rax+28h]
0x18001e6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6be  mov     rcx, [rbp+5Fh]; this
0x18001e6c2  lea     r8, aOnecoreBaseUsa_9; "onecore\\base\\usageandqualityinsights"...
0x18001e6c9  test    eax, eax
0x18001e6cb  js      loc_18001E87A
0x18001e6d1  cmp     [rbp+57h+var_90], r14
0x18001e6d5  setz    al
0x18001e6d8  mov     rcx, [rbp+5Fh]; this
0x18001e6dc  lea     rdx, aUnexpectedFlig; "Unexpected: flightId is null or empty."
0x18001e6e3  mov     qword ptr [rsp+0E0h+var_B8], rdx; bool
0x18001e6e8  mov     byte ptr [rsp+0E0h+var_C0], al; int
0x18001e6ec  mov     r9d, 8000FFFFh; char *
0x18001e6f2  lea     edx, [r14+35h]; void *
0x18001e6f6  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001e6fb  mov     rdx, [rbp+57h+var_90]
0x18001e6ff  xorps   xmm0, xmm0
0x18001e702  movups  [rbp+57h+var_38], xmm0
0x18001e706  xorps   xmm1, xmm1
0x18001e709  movdqu  [rbp+57h+var_28], xmm1
0x18001e70e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001e712  mov     r8, rdi
0x18001e715  inc     r8
0x18001e718  cmp     [rdx+r8*2], r14w
0x18001e71d  jnz     short loc_18001E715
0x18001e71f  lea     rcx, [rbp+57h+var_38]
0x18001e723  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001e728  nop
0x18001e729  lea     rcx, [rbp+57h+lpMem]
0x18001e72d  call    ?Sha256@HashAlgorithmNames@Core@Cryptography@Security@Windows@winrt@@SA@XZ; winrt::Windows::Security::Cryptography::Core::HashAlgorithmNames::Sha256(void)
0x18001e732  nop
0x18001e733  mov     rax, [rax]
0x18001e736  mov     [rbp+57h+var_58], rax
0x18001e73a  lea     rdx, [rbp+57h+var_58]
0x18001e73e  lea     rcx, [rbp+57h+var_A0]; struct winrt::param::hstring *
0x18001e742  call    ?OpenAlgorithm@HashAlgorithmProvider@Core@Cryptography@Security@Windows@winrt@@SA@AEBUhstring@param@6@@Z; winrt::Windows::Security::Cryptography::Core::HashAlgorithmProvider::OpenAlgorithm(winrt::param::hstring const &)
0x18001e747  nop
0x18001e748  mov     rbx, [rbp+57h+lpMem]
0x18001e74c  test    rbx, rbx
0x18001e74f  jz      short loc_18001E772
0x18001e751  lock xadd [rbx+18h], edi
0x18001e756  sub     edi, 1
0x18001e759  jnz     short loc_18001E792
0x18001e75b  nop
0x18001e75c  call    WINRT_IMPL_GetProcessHeap
0x18001e761  mov     rcx, rax; hHeap
0x18001e764  mov     r8, rbx; lpMem
0x18001e767  xor     edx, edx; dwFlags
0x18001e769  call    WINRT_IMPL_HeapFree
0x18001e76e  mov     [rbp+57h+lpMem], r14
0x18001e772  mov     [rbp+57h+var_98], r14d
0x18001e776  mov     rdx, qword ptr [rbp+57h+var_28]
0x18001e77a  lea     rcx, [rbp+57h+var_38]
0x18001e77e  cmp     qword ptr [rbp+57h+var_28+8], 7
0x18001e783  cmova   rcx, qword ptr [rbp+57h+var_38]
0x18001e788  test    edx, edx
0x18001e78a  jnz     short loc_18001E79D
0x18001e78c  mov     [rbp+57h+var_78], r14
0x18001e790  jmp     short loc_18001E7C3
0x18001e792  test    edi, edi
0x18001e794  jns     short loc_18001E76E
0x18001e796  call    cs:__imp_abort
0x18001e79d  mov     eax, edx
0x18001e79f  cmp     [rcx+rax*2], r14w
0x18001e7a4  jz      short loc_18001E7AD
0x18001e7a6  call    cs:__imp_abort
0x18001e7ad  mov     [rbp+57h+var_70], 1
0x18001e7b4  mov     [rbp+57h+var_6C], edx
0x18001e7b7  mov     [rbp+57h+var_60], rcx
0x18001e7bb  lea     rax, [rbp+57h+var_70]
0x18001e7bf  mov     [rbp+57h+var_78], rax
0x18001e7c3  lea     r8, [rbp+57h+var_98]
0x18001e7c7  lea     rdx, [rbp+57h+var_78]; enum winrt::Windows::Security::Cryptography::BinaryStringEncoding *
0x18001e7cb  lea     rcx, [rbp+57h+var_88]; struct winrt::param::hstring *
0x18001e7cf  call    ?ConvertStringToBinary@CryptographicBuffer@Cryptography@Security@Windows@winrt@@SA@AEBUhstring@param@5@AEBW4BinaryStringEncoding@2345@@Z; winrt::Windows::Security::Cryptography::CryptographicBuffer::ConvertStringToBinary(winrt::param::hstring const &,winrt::Windows::Security::Cryptography::BinaryStringEncoding const &)
0x18001e7d4  nop
0x18001e7d5  lea     r8, [rbp+57h+var_88]
0x18001e7d9  lea     rdx, [rbp+57h+lpMem]
0x18001e7dd  lea     rcx, [rbp+57h+var_A0]
0x18001e7e1  call    ?HashData@?$consume_Windows_Security_Cryptography_Core_IHashAlgorithmProvider@UIHashAlgorithmProvider@Core@Cryptography@Security@Windows@winrt@@@impl@winrt@@QEBA@AEBUIBuffer@Streams@Storage@Windows@3@@Z; winrt::impl::consume_Windows_Security_Cryptography_Core_IHashAlgorithmProvider<winrt::Windows::Security::Cryptography::Core::IHashAlgorithmProvider>::HashData(winrt::Windows::Storage::Streams::IBuffer const &)
0x18001e7e6  nop
0x18001e7e7  lea     rcx, [rbp+57h+lpMem]
0x18001e7eb  call    ?data@?$consume_Windows_Storage_Streams_IBuffer@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(void)
0x18001e7f0  mov     rbx, [rax]
0x18001e7f3  cmp     [rbp+57h+lpMem], r14
0x18001e7f7  jz      short loc_18001E803
0x18001e7f9  lea     rcx, [rbp+57h+lpMem]
0x18001e7fd  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001e802  nop
0x18001e803  cmp     [rbp+57h+var_88], r14
0x18001e807  jz      short loc_18001E813
0x18001e809  lea     rcx, [rbp+57h+var_88]
0x18001e80d  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001e812  nop
0x18001e813  cmp     [rbp+57h+var_A0], r14
0x18001e817  jz      short loc_18001E822
0x18001e819  lea     rcx, [rbp+57h+var_A0]
0x18001e81d  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001e822  mov     [rsi], rbx
0x18001e825  lea     rcx, [rsi+8]
0x18001e829  lea     rdx, [rbp+57h+var_38]
0x18001e82d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001e832  nop
0x18001e833  lea     rcx, [rbp+57h+var_38]; void *
0x18001e837  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e83c  nop
0x18001e83d  mov     rcx, [rbp+57h+var_A8]
0x18001e841  test    rcx, rcx
0x18001e844  jz      short loc_18001E853
0x18001e846  mov     rdx, [rcx]
0x18001e849  mov     rax, [rdx+10h]
0x18001e84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e852  nop
0x18001e853  mov     rax, rsi
0x18001e856  mov     rcx, [rbp+57h+var_18]
0x18001e85a  xor     rcx, rsp; StackCookie
0x18001e85d  call    __security_check_cookie
0x18001e862  lea     r11, [rsp+0E0h+var_10]
0x18001e86a  mov     rbx, [r11+30h]
0x18001e86e  mov     rsi, [r11+38h]
0x18001e872  mov     rsp, r11
0x18001e875  pop     r14
0x18001e877  pop     rdi
0x18001e878  pop     rbp
0x18001e879  retn
0x18001e87a  mov     r9d, eax; char *
0x18001e87d  mov     edx, 34h ; '4'; void *
0x18001e882  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e888  mov     r9d, eax; char *
0x18001e88b  lea     r8, aOnecoreBaseUsa_9; "onecore\\base\\usageandqualityinsights"...
0x18001e892  mov     edx, 31h ; '1'; void *
0x18001e897  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
