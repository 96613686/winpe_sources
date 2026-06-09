# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)

- ea: `0x1800055a0`
- end: `0x1800056eb`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004ea4`

## callees

- `0x1800055a0`
- `0x1800077c8`
- `0x18000ec79`
- `0x18000ecb5`
- `0x1800154b0`
- `0x180015870`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005691`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800056ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005691`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800056ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000561d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000561d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005686`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005699`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005699`

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
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, 0xFFFFFFFF, a4);
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
0x1800055a0  mov     rax, rsp
0x1800055a3  mov     [rax+8], rbx
0x1800055a7  mov     [rax+10h], rbp
0x1800055ab  mov     [rax+18h], rsi
0x1800055af  mov     [rax+20h], rdi
0x1800055b3  push    r12
0x1800055b5  push    r14
0x1800055b7  push    r15
0x1800055b9  sub     rsp, 30h
0x1800055bd  xor     r12d, r12d
0x1800055c0  mov     rsi, r8
0x1800055c3  mov     rbp, rdx
0x1800055c6  mov     r14, rcx
0x1800055c9  test    rdx, rdx
0x1800055cc  jnz     short loc_1800055D8
0x1800055ce  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800055d2  jz      loc_1800056E0
0x1800055d8  mov     rbx, rsi
0x1800055db  test    rbp, rbp
0x1800055de  jz      short loc_18000560A
0x1800055e0  mov     eax, 7FFFFFFFh
0x1800055e5  mov     rbx, rbp
0x1800055e8  cmp     rsi, rax
0x1800055eb  cmovb   rax, rsi
0x1800055ef  test    rax, rax
0x1800055f2  jz      short loc_180005604
0x1800055f4  cmp     [rbx], r12w
0x1800055f8  jz      short loc_180005604
0x1800055fa  add     rbx, 2
0x1800055fe  sub     rax, 1
0x180005602  jnz     short loc_1800055F4
0x180005604  sub     rbx, rbp
0x180005607  sar     rbx, 1
0x18000560a  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000560e  cmovz   rsi, rbx
0x180005612  lea     r15, ds:2[rsi*2]
0x18000561a  mov     rcx, r15; cb
0x18000561d  call    cs:__imp_CoTaskMemAlloc
0x180005623  mov     rdi, rax
0x180005626  test    rax, rax
0x180005629  jz      short loc_180005674
0x18000562b  test    rbp, rbp
0x18000562e  jz      short loc_18000566B
0x180005630  add     rbx, rbx
0x180005633  jz      short loc_180005664
0x180005635  mov     rcx, rax; void *
0x180005638  cmp     r15, rbx
0x18000563b  jb      short loc_18000564A
0x18000563d  mov     r8, rbx; Size
0x180005640  mov     rdx, rbp; Src
0x180005643  call    memmove
0x180005648  jmp     short loc_180005664
0x18000564a  mov     r8, r15; Size
0x18000564d  xor     edx, edx; Val
0x18000564f  call    memset
0x180005654  call    _o__errno_0
0x180005659  mov     dword ptr [rax], 22h ; '"'
0x18000565f  call    _invalid_parameter_noinfo
0x180005664  mov     [rbx+rdi], r12w
0x180005669  jmp     short loc_18000566F
0x18000566b  mov     [rax], r12w
0x18000566f  mov     [rdi+rsi*2], r12w
0x180005674  lea     rax, [rsp+48h+var_28]
0x180005679  cmp     r14, rax
0x18000567c  jz      short loc_1800056A4
0x18000567e  mov     rsi, [r14]
0x180005681  test    rsi, rsi
0x180005684  jz      short loc_18000569F
0x180005686  call    cs:__imp_GetLastError
0x18000568c  mov     rcx, rsi; pv
0x18000568f  mov     ebx, eax
0x180005691  call    cs:__imp_CoTaskMemFree
0x180005697  mov     ecx, ebx; dwErrCode
0x180005699  call    cs:__imp_SetLastError
0x18000569f  mov     [r14], rdi
0x1800056a2  jmp     short loc_1800056B2
0x1800056a4  test    rdi, rdi
0x1800056a7  jz      short loc_1800056B2
0x1800056a9  mov     rcx, rdi; pv
0x1800056ac  call    cs:__imp_CoTaskMemFree
0x1800056b2  mov     rax, [r14]
0x1800056b5  mov     rbx, [rsp+48h+arg_0]
0x1800056ba  neg     rax
0x1800056bd  mov     rbp, [rsp+48h+arg_8]
0x1800056c2  mov     rsi, [rsp+48h+arg_10]
0x1800056c7  sbb     eax, eax
0x1800056c9  mov     rdi, [rsp+48h+arg_18]
0x1800056ce  not     eax
0x1800056d0  and     eax, 8007000Eh
0x1800056d5  add     rsp, 30h
0x1800056d9  pop     r15
0x1800056db  pop     r14
0x1800056dd  pop     r12
0x1800056df  retn
0x1800056e0  mov     rcx, [rsp+48h]; this
0x1800056e5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
