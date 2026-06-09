# winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::CreateAndAddDependencyWithFileArtifact(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,winrt::Windows::ApplicationModel::PackageVersion,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180008a50`
- end: `0x180008c51`
- name: `?CreateAndAddDependencyWithFileArtifact@ApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV78@UPackageVersion@ApplicationModel@46@0@Z`
- size: `513`
- prototype: `__int64 __fastcall(__int64, __int64, const char *, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180007a20`

## callees

- `0x180001000`
- `0x1800029f0`
- `0x180008a50`
- `0x18000a0f0`
- `0x1800119b0`
- `0x180013330`
- `0x180013420`
- `0x180034ef0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180008bd5`
- `KERNEL32!HeapFree` at `0x180008bd5`
- `KERNEL32!GetProcessHeap` at `0x180008bc7`
- `KERNEL32!GetProcessHeap` at `0x180008bc7`
- `api-ms-win-appmodel-runtime-l1-1-5!TryCreatePackageDependency` at `0x180008b52`
- `api-ms-win-appmodel-runtime-l1-1-5!TryCreatePackageDependency` at `0x180008b52`

## string_xrefs

- `0x180008b60`: `Failed to create package dependency: %ws`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::CreateAndAddDependencyWithFileArtifact(
        __int64 a1,
        __int64 a2,
        const char *a3,
        __int64 a4,
        const wchar_t *a5)
{
  const wchar_t *v5; // rsi
  const char *v6; // rdi
  const wchar_t *v8; // r14
  const wchar_t *v9; // rbx
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned __int64 v13; // rax
  const char *v14; // rbx
  const wchar_t *v15; // rcx
  const char *v16; // rdx
  unsigned int v17; // eax
  _WORD *v18; // rdx
  unsigned __int64 v19; // r8
  void *v20; // rbx
  HANDLE ProcessHeap; // rax
  bool v22; // cc
  int v24; // [rsp+20h] [rbp-78h]
  __int64 v25; // [rsp+40h] [rbp-58h]
  const wchar_t *v26; // [rsp+48h] [rbp-50h] BYREF
  const wchar_t *v27[2]; // [rsp+50h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v5 = a5;
  WORD2(v25) = WORD1(a4);
  v6 = a3;
  HIWORD(v25) = a4;
  v8 = a5;
  v26 = (const wchar_t *)a2;
  WORD1(v25) = WORD2(a4);
  LOWORD(v25) = HIWORD(a4);
  if ( *((_QWORD *)a5 + 3) > 7u )
    v8 = *(const wchar_t **)a5;
  v9 = (const wchar_t *)a3;
  if ( *((_QWORD *)a3 + 3) > 7u )
    v9 = *(const wchar_t **)a3;
  v10 = TraceLogger::Provider();
  if ( *(_DWORD *)v10 > 5u )
  {
    v27[0] = v8;
    v26 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      (__int64)v10,
      (unsigned __int8 *)byte_18004D0B1,
      v11,
      v12,
      &v26,
      v27);
  }
  v13 = *((_QWORD *)v6 + 3);
  v14 = v6;
  lpMem = 0;
  if ( v13 > 7 )
    v14 = *(const char **)v6;
  v15 = a5;
  if ( *((_QWORD *)a5 + 3) > 7u )
    v15 = *(const wchar_t **)a5;
  v16 = v6;
  if ( v13 > 7 )
    v16 = *(const char **)v6;
  v17 = TryCreatePackageDependency(0, v16, v25, 0, 1, v15, 0, &lpMem);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1D1,
    (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Workloads\\ApiInfo.cpp",
    (const char *)v17,
    (int)"Failed to create package dependency: %ws",
    v14);
  v18 = lpMem;
  if ( !lpMem )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1D3,
      (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Workloads\\ApiInfo.cpp",
      (const char *)0x8000FFFFLL,
      v24);
  v19 = -1;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  do
    ++v19;
  while ( v18[v19] );
  std::wstring::_Construct<1,wchar_t const *>((_QWORD *)a2, v18, v19);
  v20 = lpMem;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v20);
  if ( *((_QWORD *)a5 + 3) > 7u )
    v5 = *(const wchar_t **)a5;
  v22 = *((_QWORD *)v6 + 3) <= 7u;
  v26 = v5;
  if ( !v22 )
    v6 = *(const char **)v6;
  v27[0] = (const wchar_t *)v6;
  TraceLogger::ApiInfoCreateDependencyWithFileArtifactEnd<wchar_t const *,wchar_t const *,wchar_t * &>(
    v27,
    &v26,
    (const wchar_t **)&lpMem);
  return a2;
}

```

## disassembly

```asm
0x180008a50  mov     [rsp+arg_0], rbx
0x180008a55  push    rbp
0x180008a56  push    rsi
0x180008a57  push    rdi
0x180008a58  push    r14
0x180008a5a  push    r15
0x180008a5c  sub     rsp, 70h
0x180008a60  mov     rax, cs:__security_cookie
0x180008a67  xor     rax, rsp
0x180008a6a  mov     [rsp+98h+var_30], rax
0x180008a6f  mov     rsi, [rsp+98h+arg_20]
0x180008a77  mov     rax, r9
0x180008a7a  shr     rax, 10h
0x180008a7e  xor     r15d, r15d
0x180008a81  mov     word ptr [rsp+98h+var_58+4], ax
0x180008a86  mov     rdi, r8
0x180008a89  mov     rax, r9
0x180008a8c  mov     word ptr [rsp+98h+var_58+6], r9w
0x180008a92  shr     rax, 20h
0x180008a96  mov     rbp, rdx
0x180008a99  shr     r9, 30h
0x180008a9d  mov     r14, rsi
0x180008aa0  mov     [rsp+98h+var_50], rdx
0x180008aa5  cmp     qword ptr [rsi+18h], 7
0x180008aaa  mov     word ptr [rsp+98h+var_58+2], ax
0x180008aaf  mov     word ptr [rsp+98h+var_58], r9w
0x180008ab5  jbe     short loc_180008ABA
0x180008ab7  mov     r14, [rsi]
0x180008aba  cmp     qword ptr [r8+18h], 7
0x180008abf  mov     rbx, rdi
0x180008ac2  jbe     short loc_180008AC7
0x180008ac4  mov     rbx, [r8]
0x180008ac7  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x180008acc  cmp     dword ptr [rax], 5
0x180008acf  jbe     short loc_180008AFE
0x180008ad1  lea     rcx, [rsp+98h+var_48]
0x180008ad6  mov     [rsp+98h+var_48], r14
0x180008adb  mov     [rsp+98h+var_70], rcx
0x180008ae0  lea     rdx, byte_18004D0B1
0x180008ae7  lea     rcx, [rsp+98h+var_50]
0x180008aec  mov     [rsp+98h+var_50], rbx
0x180008af1  mov     qword ptr [rsp+98h+var_78], rcx
0x180008af6  mov     rcx, rax
0x180008af9  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180008afe  mov     rax, [rdi+18h]
0x180008b02  mov     rbx, rdi
0x180008b05  mov     [rsp+98h+lpMem], r15
0x180008b0a  cmp     rax, 7
0x180008b0e  jbe     short loc_180008B13
0x180008b10  mov     rbx, [rdi]
0x180008b13  cmp     qword ptr [rsi+18h], 7
0x180008b18  mov     rcx, rsi
0x180008b1b  jbe     short loc_180008B20
0x180008b1d  mov     rcx, [rsi]
0x180008b20  mov     rdx, rdi
0x180008b23  cmp     rax, 7
0x180008b27  jbe     short loc_180008B2C
0x180008b29  mov     rdx, [rdi]
0x180008b2c  mov     r8, [rsp+98h+var_58]
0x180008b31  lea     rax, [rsp+98h+lpMem]
0x180008b36  mov     [rsp+98h+var_60], rax
0x180008b3b  xor     r9d, r9d
0x180008b3e  mov     [rsp+98h+var_68], r15d
0x180008b43  mov     [rsp+98h+var_70], rcx
0x180008b48  xor     ecx, ecx
0x180008b4a  mov     [rsp+98h+var_78], 1
0x180008b52  call    cs:__imp_TryCreatePackageDependency
0x180008b58  mov     rcx, [rsp+98h]; this
0x180008b60  lea     rdx, aFailedToCreate; "Failed to create package dependency: %w"...
0x180008b67  mov     [rsp+98h+var_70], rbx; char *
0x180008b6c  lea     r8, aCW1SProductApi; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180008b73  mov     qword ptr [rsp+98h+var_78], rdx; int
0x180008b78  mov     r9d, eax; char *
0x180008b7b  mov     edx, 1D1h; void *
0x180008b80  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180008b85  mov     rdx, [rsp+98h+lpMem]
0x180008b8a  test    rdx, rdx
0x180008b8d  jz      loc_180008C31
0x180008b93  xorps   xmm0, xmm0
0x180008b96  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180008b9d  movups  xmmword ptr [rbp+0], xmm0
0x180008ba1  mov     [rbp+10h], r15
0x180008ba5  mov     [rbp+18h], r15
0x180008ba9  nop     dword ptr [rax+00000000h]
0x180008bb0  inc     r8
0x180008bb3  cmp     [rdx+r8*2], r15w
0x180008bb8  jnz     short loc_180008BB0
0x180008bba  mov     rcx, rbp
0x180008bbd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180008bc2  mov     rbx, [rsp+98h+lpMem]
0x180008bc7  call    cs:__imp_GetProcessHeap
0x180008bcd  mov     r8, rbx; lpMem
0x180008bd0  xor     edx, edx; dwFlags
0x180008bd2  mov     rcx, rax; hHeap
0x180008bd5  call    cs:__imp_HeapFree
0x180008bdb  cmp     qword ptr [rsi+18h], 7
0x180008be0  jbe     short loc_180008BE5
0x180008be2  mov     rsi, [rsi]
0x180008be5  cmp     qword ptr [rdi+18h], 7
0x180008bea  mov     [rsp+98h+var_50], rsi
0x180008bef  jbe     short loc_180008BF4
0x180008bf1  mov     rdi, [rdi]
0x180008bf4  lea     r8, [rsp+98h+lpMem]
0x180008bf9  mov     [rsp+98h+var_48], rdi
0x180008bfe  lea     rdx, [rsp+98h+var_50]
0x180008c03  lea     rcx, [rsp+98h+var_48]
0x180008c08  call    ??$ApiInfoCreateDependencyWithFileArtifactEnd@PEB_WPEB_WAEAPEA_W@TraceLogger@@SAX$$QEAPEB_W0AEAPEA_W@Z; TraceLogger::ApiInfoCreateDependencyWithFileArtifactEnd<wchar_t const *,wchar_t const *,wchar_t * &>(wchar_t const * &&,wchar_t const * &&,wchar_t * &)
0x180008c0d  mov     rax, rbp
0x180008c10  mov     rcx, [rsp+98h+var_30]
0x180008c15  xor     rcx, rsp; StackCookie
0x180008c18  call    __security_check_cookie
0x180008c1d  mov     rbx, [rsp+98h+arg_0]
0x180008c25  add     rsp, 70h
0x180008c29  pop     r15
0x180008c2b  pop     r14
0x180008c2d  pop     rdi
0x180008c2e  pop     rsi
0x180008c2f  pop     rbp
0x180008c30  retn
0x180008c31  mov     rcx, [rsp+98h]; this
0x180008c39  lea     r8, aCW1SProductApi; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180008c40  mov     r9d, 8000FFFFh; char *
0x180008c46  mov     edx, 1D3h; void *
0x180008c4b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
