# wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x140015920`
- end: `0x140015ad9`
- name: `??$str_build_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEB_WPEB_WPEB_WPEB_W@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W111@Z`
- size: `441`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001515c`

## callees

- `0x140008de4`
- `0x14000db18`
- `0x140015920`
- `0x140015ae0`
- `0x140015b94`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400159c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015a7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015ad1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400159c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015a7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015ad1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400159ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015a6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015ac3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400159ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015a6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015ac3`

## string_xrefs

- `0x1400159eb`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140015aaf`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v6; // rsi
  _QWORD *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  STRSAFE_LPWSTR v12; // rbx
  unsigned int v13; // edi
  wchar_t *v14; // rcx
  wchar_t *v15; // r14
  const wchar_t **v16; // rsi
  int v17; // eax
  STRSAFE_LPWSTR v18; // rbx
  HANDLE v19; // rax
  HANDLE v21; // rax
  int v22; // [rsp+20h] [rbp-50h]
  int v23; // [rsp+20h] [rbp-50h]
  STRSAFE_LPWSTR pszDest; // [rsp+30h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v26[4]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v27[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v26[3] = a5;
  v6 = 0;
  v26[0] = a2;
  v26[1] = a3;
  v7 = v26;
  v26[2] = a4;
  do
  {
    if ( *v7 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(*v7 + 2 * v8) );
    }
    else
    {
      v8 = 0;
    }
    v6 += v8;
    ++v7;
  }
  while ( v7 != v27 );
  pszDest = 0;
  v9 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
         &lpMem,
         0,
         v6);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
    &pszDest,
    v9);
  v10 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  v12 = pszDest;
  v13 = pszDest == 0 ? 0x8007000E : 0;
  if ( pszDest )
  {
    v14 = pszDest;
    v15 = &pszDest[v6 + 1];
    v16 = (const wchar_t **)v26;
    do
    {
      if ( *v16 )
      {
        v17 = StringCchCopyExW(v14, v15 - v14, *v16, &pszDest, 0, 0x100u);
        v13 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x73F,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v17,
            v23);
          v21 = GetProcessHeap();
          HeapFree(v21, 0, v12);
          return v13;
        }
        v14 = pszDest;
      }
      ++v16;
    }
    while ( v16 != v27 );
    pszDest = v12;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
      a1,
      &pszDest);
    v18 = pszDest;
    if ( pszDest )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v18);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x737,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)v13,
      v22);
  }
  return v13;
}

```

## disassembly

```asm
0x140015920  mov     [rsp-28h+arg_8], rbx
0x140015925  mov     [rsp-28h+arg_10], rsi
0x14001592a  push    rbp
0x14001592b  push    rdi
0x14001592c  push    r12
0x14001592e  push    r14
0x140015930  push    r15
0x140015932  mov     rbp, rsp
0x140015935  sub     rsp, 70h
0x140015939  mov     rax, cs:__security_cookie
0x140015940  xor     rax, rsp
0x140015943  mov     [rbp+var_10], rax
0x140015947  mov     rax, [rbp+arg_20]
0x14001594b  xor     r12d, r12d
0x14001594e  mov     r15, rcx
0x140015951  mov     [rbp+var_18], rax
0x140015955  mov     esi, r12d
0x140015958  mov     [rbp+var_30], rdx
0x14001595c  mov     [rbp+var_28], r8
0x140015960  lea     rcx, [rbp+var_30]
0x140015964  mov     [rbp+var_20], r9
0x140015968  mov     rdx, [rcx]
0x14001596b  test    rdx, rdx
0x14001596e  jz      short loc_140015980
0x140015970  or      rax, 0FFFFFFFFFFFFFFFFh
0x140015974  inc     rax
0x140015977  cmp     [rdx+rax*2], r12w
0x14001597c  jnz     short loc_140015974
0x14001597e  jmp     short loc_140015983
0x140015980  mov     rax, r12
0x140015983  add     rsi, rax
0x140015986  add     rcx, 8
0x14001598a  lea     rax, [rbp+var_10]
0x14001598e  cmp     rcx, rax
0x140015991  jnz     short loc_140015968
0x140015993  mov     r8, rsi
0x140015996  mov     [rbp+pszDest], r12
0x14001599a  xor     edx, edx
0x14001599c  lea     rcx, [rbp+lpMem]
0x1400159a0  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x1400159a5  mov     rdx, rax
0x1400159a8  lea     rcx, [rbp+pszDest]
0x1400159ac  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x1400159b1  mov     rbx, [rbp+lpMem]
0x1400159b5  test    rbx, rbx
0x1400159b8  jz      short loc_1400159CE
0x1400159ba  call    cs:__imp_GetProcessHeap
0x1400159c0  mov     r8, rbx; lpMem
0x1400159c3  xor     edx, edx; dwFlags
0x1400159c5  mov     rcx, rax; hHeap
0x1400159c8  call    cs:__imp_HeapFree
0x1400159ce  mov     rbx, [rbp+pszDest]
0x1400159d2  mov     rax, rbx
0x1400159d5  neg     rax
0x1400159d8  sbb     edi, edi
0x1400159da  not     edi
0x1400159dc  and     edi, 8007000Eh
0x1400159e2  test    rbx, rbx
0x1400159e5  jnz     short loc_140015A04
0x1400159e7  mov     rcx, [rbp+28h]; this
0x1400159eb  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1400159f2  mov     r9d, edi; char *
0x1400159f5  mov     edx, 737h; void *
0x1400159fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400159ff  jmp     loc_140015A84
0x140015a04  inc     rsi
0x140015a07  mov     [rbp+pszDest], rbx
0x140015a0b  mov     rcx, rbx; pszDest
0x140015a0e  lea     r14, [rbx+rsi*2]
0x140015a12  lea     rsi, [rbp+var_30]
0x140015a16  mov     r8, [rsi]; wchar_t *
0x140015a19  test    r8, r8
0x140015a1c  jz      short loc_140015A47
0x140015a1e  mov     rdx, r14
0x140015a21  mov     [rsp+70h+var_48], 100h; unsigned int
0x140015a29  sub     rdx, rcx
0x140015a2c  mov     [rsp+70h+var_50], r12; int
0x140015a31  sar     rdx, 1; unsigned __int64
0x140015a34  lea     r9, [rbp+pszDest]; wchar_t **
0x140015a38  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140015a3d  mov     edi, eax
0x140015a3f  test    eax, eax
0x140015a41  js      short loc_140015AAB
0x140015a43  mov     rcx, [rbp+pszDest]
0x140015a47  add     rsi, 8
0x140015a4b  lea     rax, [rbp+var_10]
0x140015a4f  cmp     rsi, rax
0x140015a52  jnz     short loc_140015A16
0x140015a54  lea     rdx, [rbp+pszDest]
0x140015a58  mov     [rbp+pszDest], rbx
0x140015a5c  mov     rcx, r15
0x140015a5f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x140015a64  mov     rbx, [rbp+pszDest]
0x140015a68  test    rbx, rbx
0x140015a6b  jz      short loc_140015A81
0x140015a6d  call    cs:__imp_GetProcessHeap
0x140015a73  mov     r8, rbx; lpMem
0x140015a76  xor     edx, edx; dwFlags
0x140015a78  mov     rcx, rax; hHeap
0x140015a7b  call    cs:__imp_HeapFree
0x140015a81  mov     edi, r12d
0x140015a84  mov     eax, edi
0x140015a86  mov     rcx, [rbp+var_10]
0x140015a8a  xor     rcx, rsp; StackCookie
0x140015a8d  call    __security_check_cookie
0x140015a92  lea     r11, [rsp+70h+var_s0]
0x140015a97  mov     rbx, [r11+38h]
0x140015a9b  mov     rsi, [r11+40h]
0x140015a9f  mov     rsp, r11
0x140015aa2  pop     r15
0x140015aa4  pop     r14
0x140015aa6  pop     r12
0x140015aa8  pop     rdi
0x140015aa9  pop     rbp
0x140015aaa  retn
0x140015aab  mov     rcx, [rbp+28h]; this
0x140015aaf  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140015ab6  mov     r9d, eax; char *
0x140015ab9  mov     edx, 73Fh; void *
0x140015abe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015ac3  call    cs:__imp_GetProcessHeap
0x140015ac9  mov     r8, rbx; lpMem
0x140015acc  xor     edx, edx; dwFlags
0x140015ace  mov     rcx, rax; hHeap
0x140015ad1  call    cs:__imp_HeapFree
0x140015ad7  jmp     short loc_140015A84
```
