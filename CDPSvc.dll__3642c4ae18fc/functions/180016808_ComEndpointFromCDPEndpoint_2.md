# ComEndpointFromCDPEndpoint_2

- ea: `0x180016808`
- end: `0x180016b6b`
- name: `ComEndpointFromCDPEndpoint_2`
- size: `867`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000cd08`
- `0x180016618`

## callees

- `0x1800085e0`
- `0x180008b10`
- `0x18000cce4`
- `0x18000e9c8`
- `0x1800108e8`
- `0x180016808`
- `0x180016b74`
- `0x180022a90`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800168bc`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18001692d`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800168bc`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18001692d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800168f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800169f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800168f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800169f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComEndpointFromCDPEndpoint_2(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v4; // r13
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rcx
  rsize_t v9; // r15
  LPVOID v10; // rax
  char *v11; // r12
  int v12; // ebx
  const char *v13; // rax
  __int64 v14; // rax
  LPVOID v15; // rax
  const char *v16; // rax
  unsigned __int16 v17; // ax
  char *v18; // rdi
  int v19; // r15d
  _QWORD *unique; // rax
  void *v21; // rcx
  int v22; // r12d
  LPVOID v23; // rax
  __int64 v24; // rdx
  int v25; // esi
  __int64 v26; // rax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  char *v31; // rsi
  char *v32; // r14
  unsigned __int64 v33; // rdx
  char *v34; // [rsp+30h] [rbp-30h] BYREF
  __int64 v35; // [rsp+38h] [rbp-28h] BYREF
  char *Destination; // [rsp+40h] [rbp-20h] BYREF
  char *v37; // [rsp+48h] [rbp-18h]
  char *v38; // [rsp+50h] [rbp-10h] BYREF
  char *v39; // [rsp+58h] [rbp-8h]
  __int16 v41; // [rsp+A8h] [rbp+48h]
  unsigned __int16 v42; // [rsp+B0h] [rbp+50h] BYREF
  void *v43; // [rsp+B8h] [rbp+58h] BYREF

  v2 = a2;
  v4 = 0;
  if ( !a2 )
    return 2147500035LL;
  if ( !a1 )
    return 2147942487LL;
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  Destination = 0;
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( *(_BYTE *)(v6 + v8) );
  v9 = v8 + 1;
  v10 = CoTaskMemAlloc(v8 + 1);
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &Destination,
    v10);
  v11 = Destination;
  v39 = Destination;
  if ( Destination )
  {
    v12 = 0;
    v13 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
    strcpy_s(v11, v9, v13);
  }
  else
  {
    v12 = -2147024882;
  }
  v37 = 0;
  v34 = 0;
  if ( v12 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    do
      ++v7;
    while ( *(_BYTE *)(v14 + v7) );
    v15 = CoTaskMemAlloc(v7 + 1);
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v34,
      v15);
    if ( v11 )
    {
      v16 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
      v37 = v34;
      strcpy_s(v34, v7 + 1, v16);
      v42 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(
              a1,
              0,
              0,
              &v42);
      v17 = v42;
      goto LABEL_17;
    }
    v12 = -2147024882;
    v37 = v34;
  }
  v17 = 0;
  v42 = 0;
LABEL_17:
  v18 = 0;
  v38 = 0;
  v35 = 0;
  if ( v12 >= 0 )
  {
    v19 = 0;
    if ( !v17 )
      goto LABEL_29;
    unique = wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(&v43, v17);
    wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(
      &v38,
      unique);
    v21 = v43;
    v43 = 0;
    if ( v21 )
      operator delete(v21, 0);
    v18 = v38;
    if ( !v38 )
    {
      v12 = -2147024882;
      goto LABEL_35;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(
            a1,
            v38,
            v42,
            &v42);
    v22 = v12;
    if ( v12 >= 0 )
    {
      v23 = CoTaskMemAlloc(16LL * v42);
      wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v35,
        v23);
      v4 = v35;
      v24 = 0;
      if ( v35 )
      {
        v19 = v12;
        if ( v42 )
        {
          v25 = 0;
          do
          {
            v26 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&v18[8 * v25] + 32LL))(
                    *(_QWORD *)&v18[8 * v25],
                    v24);
            v12 = CDPComAccountFromCDPAccount(v26, v4 + 16LL * v25++);
          }
          while ( v25 < v42 );
          v2 = a2;
          if ( v12 < 0 )
          {
LABEL_35:
            if ( v18 )
            {
              if ( v19 >= 0 )
              {
                v31 = v18;
                v32 = &v18[8 * v42];
                if ( v18 != v32 )
                {
                  do
                  {
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 16LL))(*(_QWORD *)v31);
                    v31 += 8;
                  }
                  while ( v31 != v32 );
                }
              }
            }
            goto LABEL_39;
          }
        }
        v11 = v39;
LABEL_29:
        v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1);
        v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
        *(_DWORD *)(v2 + 16) = v27;
        v28 = v27 - 1;
        if ( v28 )
        {
          v29 = v28 - 2;
          if ( !v29 )
          {
            *(_DWORD *)(v2 + 20) |= 4u;
            goto LABEL_34;
          }
          v30 = v29 - 2;
          if ( v30 && v30 != 2 )
            goto LABEL_34;
        }
        *(_DWORD *)(v2 + 20) |= 1u;
LABEL_34:
        Destination = 0;
        *(_QWORD *)v2 = v11;
        v34 = 0;
        *(_QWORD *)(v2 + 8) = v37;
        *(_WORD *)(v2 + 34) = v41;
        v35 = 0;
        *(_QWORD *)(v2 + 24) = v4;
        *(_WORD *)(v2 + 32) = v42;
        goto LABEL_35;
      }
      v12 = -2147024882;
    }
    v19 = v22;
    goto LABEL_35;
  }
LABEL_39:
  wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v35,
    0);
  if ( v18 )
    operator delete(v18, v33);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v34);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&Destination);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180016808  mov     [rsp-38h+arg_0], rbx
0x18001680d  mov     [rsp-38h+arg_8], rdx
0x180016812  push    rbp
0x180016813  push    rsi
0x180016814  push    rdi
0x180016815  push    r12
0x180016817  push    r13
0x180016819  push    r14
0x18001681b  push    r15
0x18001681d  mov     rbp, rsp
0x180016820  sub     rsp, 60h
0x180016824  mov     rsi, rdx
0x180016827  mov     r14, rcx
0x18001682a  xor     r13d, r13d
0x18001682d  test    rdx, rdx
0x180016830  jnz     short loc_18001683C
0x180016832  mov     eax, 80004003h
0x180016837  jmp     loc_180016B32
0x18001683c  test    r14, r14
0x18001683f  jnz     short loc_18001684B
0x180016841  mov     eax, 80070057h
0x180016846  jmp     loc_180016B32
0x18001684b  xorps   xmm0, xmm0
0x18001684e  xor     eax, eax
0x180016850  movups  xmmword ptr [rdx], xmm0
0x180016853  movups  xmmword ptr [rdx+10h], xmm0
0x180016857  mov     [rdx+20h], rax
0x18001685b  mov     [rbp+Destination], r13
0x18001685f  mov     rax, [rcx]
0x180016862  mov     rax, [rax+18h]
0x180016866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001686b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001686f  mov     rcx, rdi
0x180016872  inc     rcx
0x180016875  cmp     [rax+rcx], r13b
0x180016879  jnz     short loc_180016872
0x18001687b  lea     r15, [rcx+1]
0x18001687f  mov     rcx, r15; cb
0x180016882  call    cs:__imp_CoTaskMemAlloc
0x180016888  mov     rdx, rax
0x18001688b  lea     rcx, [rbp+Destination]
0x18001688f  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180016894  mov     r12, [rbp+Destination]
0x180016898  mov     [rbp+var_8], r12
0x18001689c  test    r12, r12
0x18001689f  jz      short loc_1800168C4
0x1800168a1  mov     ebx, r13d
0x1800168a4  mov     rax, [r14]
0x1800168a7  mov     rcx, r14
0x1800168aa  mov     rax, [rax+18h]
0x1800168ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168b3  mov     r8, rax; Source
0x1800168b6  mov     rdx, r15; SizeInBytes
0x1800168b9  mov     rcx, r12; Destination
0x1800168bc  call    cs:__imp_strcpy_s
0x1800168c2  jmp     short loc_1800168C9
0x1800168c4  mov     ebx, 8007000Eh
0x1800168c9  mov     [rbp+var_18], r13
0x1800168cd  mov     [rbp+var_30], r13
0x1800168d1  test    ebx, ebx
0x1800168d3  js      loc_180016965
0x1800168d9  mov     rax, [r14]
0x1800168dc  mov     rcx, r14
0x1800168df  mov     rax, [rax+20h]
0x1800168e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168e8  inc     rdi
0x1800168eb  cmp     [rax+rdi], r13b
0x1800168ef  jnz     short loc_1800168E8
0x1800168f1  lea     rcx, [rdi+1]; cb
0x1800168f5  call    cs:__imp_CoTaskMemAlloc
0x1800168fb  mov     rdx, rax
0x1800168fe  lea     rcx, [rbp+var_30]
0x180016902  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180016907  test    r12, r12
0x18001690a  jz      short loc_180016958
0x18001690c  mov     rax, [r14]
0x18001690f  mov     rcx, r14
0x180016912  mov     rax, [rax+20h]
0x180016916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001691b  mov     r8, rax; Source
0x18001691e  lea     rdx, [rdi+1]; SizeInBytes
0x180016922  mov     r15, [rbp+var_30]
0x180016926  mov     [rbp+var_18], r15
0x18001692a  mov     rcx, r15; Destination
0x18001692d  call    cs:__imp_strcpy_s
0x180016933  mov     [rbp+arg_10], r13w
0x180016938  mov     rax, [r14]
0x18001693b  xor     r8d, r8d
0x18001693e  lea     r9, [rbp+arg_10]
0x180016942  xor     edx, edx
0x180016944  mov     rcx, r14
0x180016947  mov     rax, [rax+30h]
0x18001694b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016950  mov     ebx, eax
0x180016952  movzx   eax, [rbp+arg_10]
0x180016956  jmp     short loc_18001696C
0x180016958  mov     ebx, 8007000Eh
0x18001695d  mov     rcx, [rbp+var_30]
0x180016961  mov     [rbp+var_18], rcx
0x180016965  mov     eax, r13d
0x180016968  mov     [rbp+arg_10], ax
0x18001696c  mov     rdi, r13
0x18001696f  mov     [rbp+var_10], r13
0x180016973  mov     [rbp+var_28], r13
0x180016977  xor     ecx, ecx
0x180016979  test    ebx, ebx
0x18001697b  js      loc_180016B03
0x180016981  mov     r15d, ecx
0x180016984  test    ax, ax
0x180016987  jz      loc_180016A63
0x18001698d  movzx   edx, ax
0x180016990  lea     rcx, [rbp+arg_18]
0x180016994  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPEndpointAccount@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(unsigned __int64)
0x180016999  mov     rdx, rax
0x18001699c  lea     rcx, [rbp+var_10]
0x1800169a0  call    ??4?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>> &&)
0x1800169a5  mov     rcx, [rbp+arg_18]; void *
0x1800169a9  xor     edx, edx; unsigned __int64
0x1800169ab  mov     [rbp+arg_18], rdx
0x1800169af  test    rcx, rcx
0x1800169b2  jz      short loc_1800169B9
0x1800169b4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800169b9  mov     rdi, [rbp+var_10]
0x1800169bd  test    rdi, rdi
0x1800169c0  jz      loc_180016B57
0x1800169c6  mov     rax, [r14]
0x1800169c9  lea     r9, [rbp+arg_10]
0x1800169cd  movzx   r8d, [rbp+arg_10]
0x1800169d2  mov     rdx, rdi
0x1800169d5  mov     rcx, r14
0x1800169d8  mov     rax, [rax+30h]
0x1800169dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169e1  mov     ebx, eax
0x1800169e3  mov     r12d, eax
0x1800169e6  test    eax, eax
0x1800169e8  js      loc_180016B4F
0x1800169ee  movzx   ecx, [rbp+arg_10]
0x1800169f2  shl     rcx, 4; cb
0x1800169f6  call    cs:__imp_CoTaskMemAlloc
0x1800169fc  mov     rdx, rax
0x1800169ff  lea     rcx, [rbp+var_28]
0x180016a03  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x180016a08  mov     r13, [rbp+var_28]
0x180016a0c  xor     edx, edx
0x180016a0e  test    r13, r13
0x180016a11  jz      loc_180016B4A
0x180016a17  mov     r15d, ebx
0x180016a1a  cmp     dx, [rbp+arg_10]
0x180016a1e  jnb     short loc_180016A5F
0x180016a20  mov     esi, edx
0x180016a22  movsxd  rbx, esi
0x180016a25  mov     rcx, [rdi+rbx*8]
0x180016a29  mov     rax, [rcx]
0x180016a2c  mov     rax, [rax+20h]
0x180016a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a35  add     rbx, rbx
0x180016a38  lea     rdx, ds:0[rbx*8]
0x180016a40  add     rdx, r13
0x180016a43  mov     rcx, rax
0x180016a46  call    CDPComAccountFromCDPAccount
0x180016a4b  mov     ebx, eax
0x180016a4d  inc     esi
0x180016a4f  movzx   eax, [rbp+arg_10]
0x180016a53  cmp     esi, eax
0x180016a55  jl      short loc_180016A22
0x180016a57  test    ebx, ebx
0x180016a59  mov     rsi, [rbp+arg_8]
0x180016a5d  js      short loc_180016AD1
0x180016a5f  mov     r12, [rbp+var_8]
0x180016a63  mov     rax, [r14]
0x180016a66  mov     rcx, r14
0x180016a69  mov     rax, [rax+38h]
0x180016a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a72  mov     word ptr [rbp+arg_8], ax
0x180016a76  mov     rcx, [r14]
0x180016a79  mov     rax, [rcx+28h]
0x180016a7d  mov     rcx, r14
0x180016a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a85  mov     [rsi+10h], eax
0x180016a88  sub     eax, 1
0x180016a8b  jz      short loc_180016AA0
0x180016a8d  sub     eax, 2
0x180016a90  jz      loc_180016B61
0x180016a96  sub     eax, 2
0x180016a99  jz      short loc_180016AA0
0x180016a9b  cmp     eax, 2
0x180016a9e  jnz     short loc_180016AA4
0x180016aa0  or      dword ptr [rsi+14h], 1
0x180016aa4  xor     edx, edx
0x180016aa6  mov     [rbp+Destination], rdx
0x180016aaa  mov     [rsi], r12
0x180016aad  mov     [rbp+var_30], rdx
0x180016ab1  mov     rax, [rbp+var_18]
0x180016ab5  mov     [rsi+8], rax
0x180016ab9  movzx   eax, word ptr [rbp+arg_8]
0x180016abd  mov     [rsi+22h], ax
0x180016ac1  mov     [rbp+var_28], rdx
0x180016ac5  mov     [rsi+18h], r13
0x180016ac9  movzx   eax, [rbp+arg_10]
0x180016acd  mov     [rsi+20h], ax
0x180016ad1  test    rdi, rdi
0x180016ad4  jz      short loc_180016B03
0x180016ad6  test    r15d, r15d
0x180016ad9  js      short loc_180016B03
0x180016adb  mov     rsi, rdi
0x180016ade  movzx   eax, [rbp+arg_10]
0x180016ae2  lea     r14, [rdi+rax*8]
0x180016ae6  cmp     rdi, r14
0x180016ae9  jz      short loc_180016B03
0x180016aeb  mov     rcx, [rsi]
0x180016aee  mov     rax, [rcx]
0x180016af1  mov     rax, [rax+10h]
0x180016af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016afa  add     rsi, 8
0x180016afe  cmp     rsi, r14
0x180016b01  jnz     short loc_180016AEB
0x180016b03  xor     edx, edx
0x180016b05  lea     rcx, [rbp+var_28]
0x180016b09  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x180016b0e  nop
0x180016b0f  test    rdi, rdi
0x180016b12  jz      short loc_180016B1D
0x180016b14  mov     rcx, rdi; void *
0x180016b17  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016b1c  nop
0x180016b1d  lea     rcx, [rbp+var_30]
0x180016b21  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180016b26  nop
0x180016b27  lea     rcx, [rbp+Destination]
0x180016b2b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180016b30  mov     eax, ebx
0x180016b32  mov     rbx, [rsp+60h+arg_0]
0x180016b3a  add     rsp, 60h
0x180016b3e  pop     r15
0x180016b40  pop     r14
0x180016b42  pop     r13
0x180016b44  pop     r12
0x180016b46  pop     rdi
0x180016b47  pop     rsi
0x180016b48  pop     rbp
0x180016b49  retn
0x180016b4a  mov     ebx, 8007000Eh
0x180016b4f  mov     r15d, r12d
0x180016b52  jmp     loc_180016AD1
0x180016b57  mov     ebx, 8007000Eh
0x180016b5c  jmp     loc_180016AD1
0x180016b61  or      dword ptr [rsi+14h], 4
0x180016b65  jmp     loc_180016AA4
```
