# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)

- ea: `0x18001bc58`
- end: `0x18001bdaf`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z`
- size: `343`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019eec`
- `0x18001be1c`

## callees

- `0x1800079b4`
- `0x18001bc58`
- `0x180061837`
- `0x180061873`
- `0x180068f20`
- `0x1800692e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bd51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bd51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bcd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bcd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bd49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bd64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bd49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bd64`

## string_xrefs

- `0x18001bd9d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rsi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  size_t v12; // rbx
  void *v13; // rsi
  DWORD LastError; // ebx
  char v16; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a3;
  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xDB5,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v7 = a3;
  if ( a2 )
  {
    v8 = 0x7FFFFFFF;
    v9 = a2;
    if ( a3 < 0x7FFFFFFF )
      v8 = a3;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
  }
  if ( a3 == -1 )
    v4 = v7;
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v7;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset(v10, 0, 2 * v4 + 2);
          *(_DWORD *)o__errno_0() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memmove(v10, a2, v12);
        }
      }
      v11[v12 / 2] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
  if ( a1 == &v16 )
  {
    if ( v11 )
      CoTaskMemFree(v11);
  }
  else
  {
    v13 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v13);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v11;
  }
  return *(_QWORD *)a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18001bc58  mov     rax, rsp
0x18001bc5b  mov     [rax+8], rbx
0x18001bc5f  mov     [rax+10h], rbp
0x18001bc63  mov     [rax+18h], rsi
0x18001bc67  mov     [rax+20h], rdi
0x18001bc6b  push    r12
0x18001bc6d  push    r14
0x18001bc6f  push    r15
0x18001bc71  sub     rsp, 30h
0x18001bc75  xor     r12d, r12d
0x18001bc78  mov     rsi, r8
0x18001bc7b  mov     rbp, rdx
0x18001bc7e  mov     r14, rcx
0x18001bc81  test    rdx, rdx
0x18001bc84  jnz     short loc_18001BC90
0x18001bc86  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001bc8a  jz      loc_18001BD98
0x18001bc90  mov     rbx, rsi
0x18001bc93  test    rbp, rbp
0x18001bc96  jz      short loc_18001BCC2
0x18001bc98  mov     eax, 7FFFFFFFh
0x18001bc9d  mov     rbx, rbp
0x18001bca0  cmp     rsi, rax
0x18001bca3  cmovb   rax, rsi
0x18001bca7  test    rax, rax
0x18001bcaa  jz      short loc_18001BCBC
0x18001bcac  cmp     [rbx], r12w
0x18001bcb0  jz      short loc_18001BCBC
0x18001bcb2  add     rbx, 2
0x18001bcb6  sub     rax, 1
0x18001bcba  jnz     short loc_18001BCAC
0x18001bcbc  sub     rbx, rbp
0x18001bcbf  sar     rbx, 1
0x18001bcc2  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001bcc6  cmovz   rsi, rbx
0x18001bcca  lea     r15, ds:2[rsi*2]
0x18001bcd2  mov     rcx, r15; cb
0x18001bcd5  call    cs:__imp_CoTaskMemAlloc
0x18001bcdb  mov     rdi, rax
0x18001bcde  test    rax, rax
0x18001bce1  jz      short loc_18001BD2C
0x18001bce3  test    rbp, rbp
0x18001bce6  jz      short loc_18001BD23
0x18001bce8  add     rbx, rbx
0x18001bceb  jz      short loc_18001BD1C
0x18001bced  mov     rcx, rax; void *
0x18001bcf0  cmp     r15, rbx
0x18001bcf3  jb      short loc_18001BD02
0x18001bcf5  mov     r8, rbx; Size
0x18001bcf8  mov     rdx, rbp; Src
0x18001bcfb  call    memmove
0x18001bd00  jmp     short loc_18001BD1C
0x18001bd02  mov     r8, r15; Size
0x18001bd05  xor     edx, edx; Val
0x18001bd07  call    memset
0x18001bd0c  call    _o__errno_0
0x18001bd11  mov     dword ptr [rax], 22h ; '"'
0x18001bd17  call    _invalid_parameter_noinfo
0x18001bd1c  mov     [rbx+rdi], r12w
0x18001bd21  jmp     short loc_18001BD27
0x18001bd23  mov     [rax], r12w
0x18001bd27  mov     [rdi+rsi*2], r12w
0x18001bd2c  lea     rax, [rsp+48h+var_28]
0x18001bd31  cmp     r14, rax
0x18001bd34  jz      short loc_18001BD5C
0x18001bd36  mov     rsi, [r14]
0x18001bd39  test    rsi, rsi
0x18001bd3c  jz      short loc_18001BD57
0x18001bd3e  call    cs:__imp_GetLastError
0x18001bd44  mov     rcx, rsi; pv
0x18001bd47  mov     ebx, eax
0x18001bd49  call    cs:__imp_CoTaskMemFree
0x18001bd4f  mov     ecx, ebx; dwErrCode
0x18001bd51  call    cs:__imp_SetLastError
0x18001bd57  mov     [r14], rdi
0x18001bd5a  jmp     short loc_18001BD6A
0x18001bd5c  test    rdi, rdi
0x18001bd5f  jz      short loc_18001BD6A
0x18001bd61  mov     rcx, rdi; pv
0x18001bd64  call    cs:__imp_CoTaskMemFree
0x18001bd6a  mov     rax, [r14]
0x18001bd6d  mov     rbx, [rsp+48h+arg_0]
0x18001bd72  neg     rax
0x18001bd75  mov     rbp, [rsp+48h+arg_8]
0x18001bd7a  mov     rsi, [rsp+48h+arg_10]
0x18001bd7f  sbb     eax, eax
0x18001bd81  mov     rdi, [rsp+48h+arg_18]
0x18001bd86  not     eax
0x18001bd88  and     eax, 8007000Eh
0x18001bd8d  add     rsp, 30h
0x18001bd91  pop     r15
0x18001bd93  pop     r14
0x18001bd95  pop     r12
0x18001bd97  retn
0x18001bd98  mov     rcx, [rsp+48h]; this
0x18001bd9d  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18001bda4  mov     edx, 0DB5h; void *
0x18001bda9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
