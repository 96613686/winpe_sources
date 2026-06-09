# wil::cloud_store::call_get_collection_items<Windows::Data::Nlm::NlmSignature>(ushort const *,wil::cloud_store_load_options,wil::cloud_store_collection_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18001aed8`
- end: `0x18001b209`
- name: `??$call_get_collection_items@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@AEAA?AV?$vector@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@PEBGW4cloud_store_load_options@1@W4cloud_store_collection_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z`
- size: `817`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18001ae10`

## callees

- `0x180005ac0`
- `0x1800062c0`
- `0x180007564`
- `0x1800075bc`
- `0x180009240`
- `0x18001aed8`
- `0x180025308`
- `0x18002a030`
- `0x18002e2d0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001af9f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b00a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b055`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b193`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b1a6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b1b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001af9f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b00a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b055`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b193`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b1a6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b1b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001afb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b020`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001afb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b020`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b074`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall wil::cloud_store::call_get_collection_items<Windows::Data::Nlm::NlmSignature>(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v10; // rax
  const WCHAR *v11; // rcx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rdx
  signed int v14; // eax
  const WCHAR *v15; // rcx
  unsigned __int64 v16; // rdx
  signed int v17; // eax
  signed int v18; // eax
  __int64 *v19; // rax
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // rcx
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h]
  __int64 *v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  char v28; // [rsp+70h] [rbp-90h]
  __int64 *v29; // [rsp+80h] [rbp-80h]
  PCWSTR sourceString[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v31; // [rsp+A0h] [rbp-60h]
  HSTRING_HEADER v32; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING v33; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER v34; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v35; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING string; // [rsp+100h] [rbp+0h] BYREF
  void *v38; // [rsp+108h] [rbp+8h] BYREF
  __m128i si128; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v25 = a2;
  wil::cloud_store::get_type_name_wide_string<Windows::Data::Nlm::NlmSignature>(sourceString);
  v24 = 0;
  v29 = *(__int64 **)wil::details::shared_cloud_store_state::get_cloud_store(*(_QWORD *)a1);
  v25 = *v29;
  v26 = &v24;
  v27 = 0;
  v28 = 1;
  v10 = wil::cloud_store::widen_string(&v38, a6);
  v11 = (const WCHAR *)v10;
  if ( *(_QWORD *)(v10 + 24) > 7u )
    v11 = *(const WCHAR **)v10;
  string = 0;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( v11[v13] );
  if ( v13 > 0xFFFFFFFF || (int)v13 + 1 < (unsigned int)v13 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v14 = WindowsCreateStringReference(v11, v13, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    RaiseException(v14, 1u, 0, 0);
LABEL_37:
    RaiseException(v17, 1u, 0, 0);
LABEL_38:
    RaiseException(v18, 1u, 0, 0);
    goto LABEL_39;
  }
  wil::cloud_store::convert_cloud_store_load_options(a4);
  v15 = (const WCHAR *)sourceString;
  if ( v31 > 7 )
    v15 = sourceString[0];
  a4 = 0;
  v35 = 0;
  v16 = -1;
  do
    ++v16;
  while ( v15[v16] );
  if ( v16 > 0xFFFFFFFF || (int)v16 + 1 < (unsigned int)v16 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v17 = WindowsCreateStringReference(v15, v16, &v34, &v35);
  if ( v17 < 0 )
    goto LABEL_37;
  v33 = 0;
  do
    ++v12;
  while ( a3[v12] );
  if ( v12 > 0xFFFFFFFF || (int)v12 + 1 < (unsigned int)v12 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  a4 = (unsigned int)v35;
  v18 = WindowsCreateStringReference(a3, v12, &v32, &v33);
  v12 = 0;
  if ( v18 < 0 )
    goto LABEL_38;
  v19 = *(__int64 **)(a1 + 24);
  if ( !v19 )
  {
    v20 = 0;
    goto LABEL_25;
  }
LABEL_39:
  v20 = *v19;
LABEL_25:
  v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, HSTRING))(v25 + 80))(
          v29,
          *(unsigned int *)(a1 + 16),
          v20,
          v33);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x553,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v21,
      a4);
  v33 = (HSTRING)v12;
  v35 = (HSTRING)v12;
  string = (HSTRING)v12;
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v38, 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v38) = v12;
  if ( v28 != (_BYTE)v12 )
  {
    v22 = *v26;
    *v26 = v27;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Nlm::NlmSignature>(a2, v24);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v31 > 7 )
    std::_Deallocate<16>((void *)sourceString[0], 2 * v31 + 2);
  return a2;
}

```

## disassembly

```asm
0x18001aed8  push    rbp
0x18001aeda  push    rbx
0x18001aedb  push    rsi
0x18001aedc  push    rdi
0x18001aedd  push    r12
0x18001aedf  push    r13
0x18001aee1  push    r14
0x18001aee3  push    r15
0x18001aee5  lea     rbp, [rsp-38h]
0x18001aeea  sub     rsp, 138h
0x18001aef1  mov     rax, cs:__security_cookie
0x18001aef8  xor     rax, rsp
0x18001aefb  mov     [rbp+70h+var_48], rax
0x18001aeff  mov     edi, r9d
0x18001af02  mov     r14, r8
0x18001af05  mov     rsi, rdx
0x18001af08  mov     r15, rcx
0x18001af0b  mov     [rsp+170h+var_118], rdx
0x18001af10  mov     rbx, [rbp+70h+arg_28]
0x18001af17  xor     r12d, r12d
0x18001af1a  lea     rcx, [rbp+70h+sourceString]
0x18001af1e  call    ??$get_type_name_wide_string@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::cloud_store::get_type_name_wide_string<Windows::Data::Nlm::NlmSignature>(void)
0x18001af23  nop
0x18001af24  mov     [rsp+170h+var_120], r12
0x18001af29  mov     rcx, [r15]
0x18001af2c  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x18001af31  mov     rax, [rax]
0x18001af34  mov     [rbp+70h+var_F0], rax
0x18001af38  mov     rax, [rax]
0x18001af3b  mov     [rsp+170h+var_118], rax
0x18001af40  lea     rcx, [rsp+170h+var_120]
0x18001af45  mov     [rsp+170h+var_110], rcx
0x18001af4a  mov     [rsp+170h+var_108], r12
0x18001af4f  lea     r13d, [r12+1]
0x18001af54  mov     [rsp+170h+var_100], r13b
0x18001af59  mov     rdx, rbx
0x18001af5c  lea     rcx, [rbp+70h+var_68]
0x18001af60  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x18001af65  mov     rcx, rax
0x18001af68  cmp     qword ptr [rax+18h], 7
0x18001af6d  jbe     short loc_18001AF72
0x18001af6f  mov     rcx, [rax]; sourceString
0x18001af72  mov     [rbp+70h+string], r12
0x18001af76  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001af7a  mov     rdx, rbx
0x18001af7d  inc     rdx; length
0x18001af80  cmp     [rcx+rdx*2], r12w
0x18001af85  jnz     short loc_18001AF7D
0x18001af87  mov     eax, 0FFFFFFFFh
0x18001af8c  cmp     rdx, rax
0x18001af8f  jbe     short loc_18001AFA6
0x18001af91  xor     r9d, r9d; lpArguments
0x18001af94  xor     r8d, r8d; nNumberOfArguments
0x18001af97  mov     edx, r13d; dwExceptionFlags
0x18001af9a  mov     ecx, 80070216h; dwExceptionCode
0x18001af9f  call    cs:__imp_RaiseException
0x18001afa5  int     3; Trap to Debugger
0x18001afa6  lea     eax, [rdx+1]
0x18001afa9  cmp     eax, edx
0x18001afab  jb      short loc_18001AF91
0x18001afad  lea     r9, [rbp+70h+string]; string
0x18001afb1  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x18001afb5  call    cs:__imp_WindowsCreateStringReference
0x18001afbb  test    eax, eax
0x18001afbd  js      loc_18001B188
0x18001afc3  mov     r12, [rbp+70h+string]
0x18001afc7  mov     ecx, edi
0x18001afc9  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x18001afce  mov     r13d, eax
0x18001afd1  lea     rcx, [rbp+70h+sourceString]
0x18001afd5  cmp     [rbp+70h+var_D0], 7
0x18001afda  cmova   rcx, [rbp+70h+sourceString]; sourceString
0x18001afdf  xor     edi, edi
0x18001afe1  mov     [rbp+70h+var_90], rdi
0x18001afe5  mov     rdx, rbx
0x18001afe8  inc     rdx; length
0x18001afeb  cmp     [rcx+rdx*2], di
0x18001afef  jnz     short loc_18001AFE8
0x18001aff1  mov     eax, 0FFFFFFFFh
0x18001aff6  cmp     rdx, rax
0x18001aff9  jbe     short loc_18001B011
0x18001affb  xor     r9d, r9d; lpArguments
0x18001affe  xor     r8d, r8d; nNumberOfArguments
0x18001b001  lea     edx, [r9+1]; dwExceptionFlags
0x18001b005  mov     ecx, 80070216h; dwExceptionCode
0x18001b00a  call    cs:__imp_RaiseException
0x18001b010  int     3; Trap to Debugger
0x18001b011  lea     eax, [rdx+1]
0x18001b014  cmp     eax, edx
0x18001b016  jb      short loc_18001AFFB
0x18001b018  lea     r9, [rbp+70h+var_90]; string
0x18001b01c  lea     r8, [rbp+70h+var_A8]; hstringHeader
0x18001b020  call    cs:__imp_WindowsCreateStringReference
0x18001b026  test    eax, eax
0x18001b028  js      loc_18001B19A
0x18001b02e  mov     [rbp+70h+var_B0], rdi
0x18001b032  inc     rbx
0x18001b035  cmp     [r14+rbx*2], di
0x18001b03a  jnz     short loc_18001B032
0x18001b03c  mov     eax, 0FFFFFFFFh
0x18001b041  cmp     rbx, rax
0x18001b044  jbe     short loc_18001B05C
0x18001b046  xor     r9d, r9d; lpArguments
0x18001b049  xor     r8d, r8d; nNumberOfArguments
0x18001b04c  lea     edx, [r9+1]; dwExceptionFlags
0x18001b050  mov     ecx, 80070216h; dwExceptionCode
0x18001b055  call    cs:__imp_RaiseException
0x18001b05b  int     3; Trap to Debugger
0x18001b05c  lea     eax, [rbx+1]
0x18001b05f  cmp     eax, ebx
0x18001b061  jb      short loc_18001B046
0x18001b063  mov     rdi, [rbp+70h+var_90]
0x18001b067  lea     r9, [rbp+70h+var_B0]; string
0x18001b06b  lea     r8, [rbp+70h+var_C8]; hstringHeader
0x18001b06f  mov     edx, ebx; length
0x18001b071  mov     rcx, r14; sourceString
0x18001b074  call    cs:__imp_WindowsCreateStringReference
0x18001b07a  xor     ebx, ebx
0x18001b07c  test    eax, eax
0x18001b07e  js      loc_18001B1AD
0x18001b084  mov     rax, [r15+18h]
0x18001b088  test    rax, rax
0x18001b08b  jnz     loc_18001B1C0
0x18001b091  mov     r8d, ebx
0x18001b094  lea     rax, [rsp+170h+var_108]
0x18001b099  mov     [rsp+170h+var_130], rax
0x18001b09e  mov     [rsp+170h+var_138], r12
0x18001b0a3  mov     r10d, [rbp+70h+arg_20]
0x18001b0aa  mov     [rsp+170h+var_140], r10d
0x18001b0af  mov     [rsp+170h+var_148], r13d
0x18001b0b4  mov     qword ptr [rsp+170h+var_150], rdi; int
0x18001b0b9  mov     r9, [rbp+70h+var_B0]
0x18001b0bd  mov     edx, [r15+10h]
0x18001b0c1  mov     rcx, [rbp+70h+var_F0]
0x18001b0c5  mov     rax, [rsp+170h+var_118]
0x18001b0ca  mov     rax, [rax+50h]
0x18001b0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0d3  mov     rcx, [rbp+78h]; this
0x18001b0d7  test    eax, eax
0x18001b0d9  js      loc_18001B1C8
0x18001b0df  mov     [rbp+70h+var_B0], rbx
0x18001b0e3  mov     [rbp+70h+var_90], rbx
0x18001b0e7  mov     [rbp+70h+string], rbx
0x18001b0eb  mov     rdx, [rbp+70h+var_50]
0x18001b0ef  cmp     rdx, 7
0x18001b0f3  ja      loc_18001B1DD
0x18001b0f9  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001b101  movdqu  xmmword ptr [rbp+18h], xmm0
0x18001b106  mov     word ptr [rbp+70h+var_68], bx
0x18001b10a  cmp     [rsp+170h+var_100], bl
0x18001b10e  jz      short loc_18001B132
0x18001b110  mov     rdx, [rsp+170h+var_108]
0x18001b115  mov     rax, [rsp+170h+var_110]
0x18001b11a  mov     rcx, [rax]
0x18001b11d  mov     [rax], rdx
0x18001b120  test    rcx, rcx
0x18001b123  jz      short loc_18001B132
0x18001b125  mov     rax, [rcx]
0x18001b128  mov     rax, [rax+10h]
0x18001b12c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b131  nop
0x18001b132  mov     rdx, [rsp+170h+var_120]
0x18001b137  mov     rcx, rsi
0x18001b13a  call    ??$make_cloud_store_reference_vector@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@CA?AV?$vector@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@PEAU?$IVectorView@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@@Collections@Foundation@Windows@@@Z; wil::cloud_store::make_cloud_store_reference_vector<Windows::Data::Nlm::NlmSignature>(Windows::Foundation::Collections::IVectorView<Windows::Internal::Storage::Cloud::CloudStoreItemName *> *)
0x18001b13f  nop
0x18001b140  mov     rcx, [rsp+170h+var_120]
0x18001b145  test    rcx, rcx
0x18001b148  jz      short loc_18001B157
0x18001b14a  mov     rax, [rcx]
0x18001b14d  mov     rax, [rax+10h]
0x18001b151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b156  nop
0x18001b157  mov     rdx, [rbp+70h+var_D0]
0x18001b15b  cmp     rdx, 7
0x18001b15f  ja      loc_18001B1F3
0x18001b165  mov     rax, rsi
0x18001b168  mov     rcx, [rbp+70h+var_48]
0x18001b16c  xor     rcx, rsp; StackCookie
0x18001b16f  call    __security_check_cookie
0x18001b174  add     rsp, 138h
0x18001b17b  pop     r15
0x18001b17d  pop     r14
0x18001b17f  pop     r13
0x18001b181  pop     r12
0x18001b183  pop     rdi
0x18001b184  pop     rsi
0x18001b185  pop     rbx
0x18001b186  pop     rbp
0x18001b187  retn
0x18001b188  xor     r9d, r9d; lpArguments
0x18001b18b  xor     r8d, r8d; nNumberOfArguments
0x18001b18e  mov     edx, r13d; dwExceptionFlags
0x18001b191  mov     ecx, eax; dwExceptionCode
0x18001b193  call    cs:__imp_RaiseException
0x18001b199  nop
0x18001b19a  xor     r9d, r9d; lpArguments
0x18001b19d  xor     r8d, r8d; nNumberOfArguments
0x18001b1a0  lea     edx, [r9+1]; dwExceptionFlags
0x18001b1a4  mov     ecx, eax; dwExceptionCode
0x18001b1a6  call    cs:__imp_RaiseException
0x18001b1ac  nop
0x18001b1ad  xor     r9d, r9d; lpArguments
0x18001b1b0  xor     r8d, r8d; nNumberOfArguments
0x18001b1b3  lea     edx, [r9+1]; dwExceptionFlags
0x18001b1b7  mov     ecx, eax; dwExceptionCode
0x18001b1b9  call    cs:__imp_RaiseException
0x18001b1bf  nop
0x18001b1c0  mov     r8, [rax]
0x18001b1c3  jmp     loc_18001B094
0x18001b1c8  mov     r9d, eax; char *
0x18001b1cb  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18001b1d2  mov     edx, 553h; void *
0x18001b1d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001b1dd  lea     rdx, ds:2[rdx*2]
0x18001b1e5  mov     rcx, [rbp+70h+var_68]
0x18001b1e9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001b1ee  jmp     loc_18001B0F9
0x18001b1f3  lea     rdx, ds:2[rdx*2]
0x18001b1fb  mov     rcx, [rbp+70h+sourceString]
0x18001b1ff  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001b204  jmp     loc_18001B165
```
