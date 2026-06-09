# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x18000b644`
- end: `0x18000b777`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `307`
- prototype: `__int64 __fastcall(char *, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006d54`

## callees

- `0x180002f2a`
- `0x180002f7c`
- `0x18000a984`
- `0x18000b644`
- `0x18000bd94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b6ef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b6ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b735`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b72d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b748`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b72d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b748`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b6b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b6b8`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rsi
  __int64 v7; // rax
  char *v8; // rbx
  __int64 v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  size_t v12; // rbx
  void *v13; // rsi
  DWORD LastError; // ebx
  char v16; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = a3;
  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, 0xFFFFFFFF, a4);
  if ( a2 )
  {
    v7 = a3;
    v8 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v7 = 0x7FFFFFFF;
    for ( ; v7; --v7 )
    {
      if ( !*(_WORD *)v8 )
        break;
      v8 += 2;
    }
    v9 = (v8 - a2) >> 1;
  }
  else
  {
    v9 = a3;
  }
  if ( a3 == -1 )
    v4 = v9;
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v9;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v10, a2, v12);
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
0x18000b644  push    rbx
0x18000b646  push    rbp
0x18000b647  push    rsi
0x18000b648  push    rdi
0x18000b649  push    r12
0x18000b64b  push    r14
0x18000b64d  push    r15
0x18000b64f  sub     rsp, 30h
0x18000b653  xor     r12d, r12d
0x18000b656  mov     rsi, r8
0x18000b659  mov     rbp, rdx
0x18000b65c  mov     r14, rcx
0x18000b65f  test    rdx, rdx
0x18000b662  jnz     short loc_18000B66E
0x18000b664  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000b668  jz      loc_18000B76C
0x18000b66e  test    rbp, rbp
0x18000b671  jz      short loc_18000B6A2
0x18000b673  mov     ecx, 7FFFFFFFh
0x18000b678  mov     rax, rsi
0x18000b67b  cmp     rsi, rcx
0x18000b67e  mov     rbx, rbp
0x18000b681  cmovnb  rax, rcx
0x18000b685  test    rax, rax
0x18000b688  jz      short loc_18000B69A
0x18000b68a  cmp     [rbx], r12w
0x18000b68e  jz      short loc_18000B69A
0x18000b690  add     rbx, 2
0x18000b694  sub     rax, 1
0x18000b698  jnz     short loc_18000B68A
0x18000b69a  sub     rbx, rbp
0x18000b69d  sar     rbx, 1
0x18000b6a0  jmp     short loc_18000B6A5
0x18000b6a2  mov     rbx, rsi
0x18000b6a5  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000b6a9  cmovz   rsi, rbx
0x18000b6ad  lea     r15, ds:2[rsi*2]
0x18000b6b5  mov     rcx, r15; cb
0x18000b6b8  call    cs:__imp_CoTaskMemAlloc
0x18000b6be  mov     rdi, rax
0x18000b6c1  test    rax, rax
0x18000b6c4  jz      short loc_18000B710
0x18000b6c6  test    rbp, rbp
0x18000b6c9  jz      short loc_18000B707
0x18000b6cb  add     rbx, rbx
0x18000b6ce  jz      short loc_18000B700
0x18000b6d0  mov     rcx, rax; void *
0x18000b6d3  cmp     r15, rbx
0x18000b6d6  jb      short loc_18000B6E5
0x18000b6d8  mov     r8, rbx; Size
0x18000b6db  mov     rdx, rbp; Src
0x18000b6de  call    memcpy_0
0x18000b6e3  jmp     short loc_18000B700
0x18000b6e5  mov     r8, r15; Size
0x18000b6e8  xor     edx, edx; Val
0x18000b6ea  call    memset_0
0x18000b6ef  call    cs:__imp__o__errno
0x18000b6f5  mov     dword ptr [rax], 22h ; '"'
0x18000b6fb  call    _invalid_parameter_noinfo
0x18000b700  mov     [rbx+rdi], r12w
0x18000b705  jmp     short loc_18000B70B
0x18000b707  mov     [rax], r12w
0x18000b70b  mov     [rdi+rsi*2], r12w
0x18000b710  lea     rax, [rsp+68h+var_48]
0x18000b715  cmp     r14, rax
0x18000b718  jz      short loc_18000B740
0x18000b71a  mov     rsi, [r14]
0x18000b71d  test    rsi, rsi
0x18000b720  jz      short loc_18000B73B
0x18000b722  call    cs:__imp_GetLastError
0x18000b728  mov     rcx, rsi; pv
0x18000b72b  mov     ebx, eax
0x18000b72d  call    cs:__imp_CoTaskMemFree
0x18000b733  mov     ecx, ebx; dwErrCode
0x18000b735  call    cs:__imp_SetLastError
0x18000b73b  mov     [r14], rdi
0x18000b73e  jmp     short loc_18000B74E
0x18000b740  test    rdi, rdi
0x18000b743  jz      short loc_18000B74E
0x18000b745  mov     rcx, rdi; pv
0x18000b748  call    cs:__imp_CoTaskMemFree
0x18000b74e  mov     rax, [r14]
0x18000b751  neg     rax
0x18000b754  sbb     eax, eax
0x18000b756  not     eax
0x18000b758  and     eax, 8007000Eh
0x18000b75d  add     rsp, 30h
0x18000b761  pop     r15
0x18000b763  pop     r14
0x18000b765  pop     r12
0x18000b767  pop     rdi
0x18000b768  pop     rsi
0x18000b769  pop     rbp
0x18000b76a  pop     rbx
0x18000b76b  retn
0x18000b76c  mov     rcx, [rsp+68h]; this
0x18000b771  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
