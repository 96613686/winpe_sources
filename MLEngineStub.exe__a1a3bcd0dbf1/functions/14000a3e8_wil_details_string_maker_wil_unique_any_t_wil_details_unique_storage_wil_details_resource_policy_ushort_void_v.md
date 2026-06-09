# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x14000a3e8`
- end: `0x14000a51b`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `307`
- prototype: `__int64 __fastcall(char *, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140006614`

## callees

- `0x140002bca`
- `0x140002c58`
- `0x140009c84`
- `0x14000a3e8`
- `0x14000ad14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a493`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a493`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a4d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a4c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a4c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a4d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a4ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a4d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a4ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000a45c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000a45c`

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
0x14000a3e8  push    rbx
0x14000a3ea  push    rbp
0x14000a3eb  push    rsi
0x14000a3ec  push    rdi
0x14000a3ed  push    r12
0x14000a3ef  push    r14
0x14000a3f1  push    r15
0x14000a3f3  sub     rsp, 30h
0x14000a3f7  xor     r12d, r12d
0x14000a3fa  mov     rsi, r8
0x14000a3fd  mov     rbp, rdx
0x14000a400  mov     r14, rcx
0x14000a403  test    rdx, rdx
0x14000a406  jnz     short loc_14000A412
0x14000a408  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000a40c  jz      loc_14000A510
0x14000a412  test    rbp, rbp
0x14000a415  jz      short loc_14000A446
0x14000a417  mov     ecx, 7FFFFFFFh
0x14000a41c  mov     rax, rsi
0x14000a41f  cmp     rsi, rcx
0x14000a422  mov     rbx, rbp
0x14000a425  cmovnb  rax, rcx
0x14000a429  test    rax, rax
0x14000a42c  jz      short loc_14000A43E
0x14000a42e  cmp     [rbx], r12w
0x14000a432  jz      short loc_14000A43E
0x14000a434  add     rbx, 2
0x14000a438  sub     rax, 1
0x14000a43c  jnz     short loc_14000A42E
0x14000a43e  sub     rbx, rbp
0x14000a441  sar     rbx, 1
0x14000a444  jmp     short loc_14000A449
0x14000a446  mov     rbx, rsi
0x14000a449  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000a44d  cmovz   rsi, rbx
0x14000a451  lea     r15, ds:2[rsi*2]
0x14000a459  mov     rcx, r15; cb
0x14000a45c  call    cs:__imp_CoTaskMemAlloc
0x14000a462  mov     rdi, rax
0x14000a465  test    rax, rax
0x14000a468  jz      short loc_14000A4B4
0x14000a46a  test    rbp, rbp
0x14000a46d  jz      short loc_14000A4AB
0x14000a46f  add     rbx, rbx
0x14000a472  jz      short loc_14000A4A4
0x14000a474  mov     rcx, rax; void *
0x14000a477  cmp     r15, rbx
0x14000a47a  jb      short loc_14000A489
0x14000a47c  mov     r8, rbx; Size
0x14000a47f  mov     rdx, rbp; Src
0x14000a482  call    memcpy_0
0x14000a487  jmp     short loc_14000A4A4
0x14000a489  mov     r8, r15; Size
0x14000a48c  xor     edx, edx; Val
0x14000a48e  call    memset_0
0x14000a493  call    cs:__imp__o__errno
0x14000a499  mov     dword ptr [rax], 22h ; '"'
0x14000a49f  call    _invalid_parameter_noinfo
0x14000a4a4  mov     [rbx+rdi], r12w
0x14000a4a9  jmp     short loc_14000A4AF
0x14000a4ab  mov     [rax], r12w
0x14000a4af  mov     [rdi+rsi*2], r12w
0x14000a4b4  lea     rax, [rsp+68h+var_48]
0x14000a4b9  cmp     r14, rax
0x14000a4bc  jz      short loc_14000A4E4
0x14000a4be  mov     rsi, [r14]
0x14000a4c1  test    rsi, rsi
0x14000a4c4  jz      short loc_14000A4DF
0x14000a4c6  call    cs:__imp_GetLastError
0x14000a4cc  mov     rcx, rsi; pv
0x14000a4cf  mov     ebx, eax
0x14000a4d1  call    cs:__imp_CoTaskMemFree
0x14000a4d7  mov     ecx, ebx; dwErrCode
0x14000a4d9  call    cs:__imp_SetLastError
0x14000a4df  mov     [r14], rdi
0x14000a4e2  jmp     short loc_14000A4F2
0x14000a4e4  test    rdi, rdi
0x14000a4e7  jz      short loc_14000A4F2
0x14000a4e9  mov     rcx, rdi; pv
0x14000a4ec  call    cs:__imp_CoTaskMemFree
0x14000a4f2  mov     rax, [r14]
0x14000a4f5  neg     rax
0x14000a4f8  sbb     eax, eax
0x14000a4fa  not     eax
0x14000a4fc  and     eax, 8007000Eh
0x14000a501  add     rsp, 30h
0x14000a505  pop     r15
0x14000a507  pop     r14
0x14000a509  pop     r12
0x14000a50b  pop     rdi
0x14000a50c  pop     rsi
0x14000a50d  pop     rbp
0x14000a50e  pop     rbx
0x14000a50f  retn
0x14000a510  mov     rcx, [rsp+68h]; this
0x14000a515  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
