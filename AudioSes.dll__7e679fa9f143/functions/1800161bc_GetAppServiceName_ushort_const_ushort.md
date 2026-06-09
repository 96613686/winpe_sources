# GetAppServiceName(ushort const *,ushort * *)

- ea: `0x1800161bc`
- end: `0x180016398`
- name: `?GetAppServiceName@@YAJPEBGPEAPEAG@Z`
- size: `476`
- prototype: `int(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180110888`

## callees

- `0x18000cb1c`
- `0x180010a90`
- `0x1800161bc`
- `0x1800163a0`
- `0x1800165ac`
- `0x1800aa314`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001627b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001627b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800162bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016323`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800162bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016323`

## string_xrefs

- `0x180016297`: `com.%s`
- `0x1800162db`: `OneCoreUap\Private\AVCore\inc\SpatialAudioLicenseBrokerUtil.h`
- `0x180016307`: `OneCoreUap\Private\AVCore\inc\SpatialAudioLicenseBrokerUtil.h`
- `0x180016346`: `OneCoreUap\Private\AVCore\inc\SpatialAudioLicenseBrokerUtil.h`
- `0x18001637f`: `OneCoreUap\Private\AVCore\inc\SpatialAudioLicenseBrokerUtil.h`

## pseudocode

```c
__int64 __fastcall GetAppServiceName(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  const unsigned __int16 *v3; // rax
  __int64 v4; // r8
  unsigned int v5; // ebx
  unsigned __int64 v6; // rdi
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  _WORD *v10; // rsi
  unsigned __int64 i; // rax
  unsigned __int64 v12; // rdi
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rbx
  int v15; // eax
  unsigned int v16; // edi
  int v18; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 *v21; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  if ( !a1 )
  {
    v5 = -2147024809;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"OneCoreUap\\Private\\AVCore\\inc\\SpatialAudioLicenseBrokerUtil.h",
      (const char *)v5,
      v18);
    return v5;
  }
  v3 = a1;
  v4 = 65;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v4;
  }
  while ( v4 );
  v5 = v4 == 0 ? 0x80070057 : 0;
  v6 = (65 - v4) & -(__int64)(v4 != 0);
  if ( !v4 )
    goto LABEL_23;
  if ( v6 > 0x1E )
    v6 = 30;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &pv,
    a1,
    v6);
  v10 = pv;
  if ( !pv )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"OneCoreUap\\Private\\AVCore\\inc\\SpatialAudioLicenseBrokerUtil.h",
      (const char *)0x8007000ELL,
      v18);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
    return v5;
  }
  for ( i = 0; i < v6; ++i )
  {
    if ( v10[i] == 95 )
      v10[i] = 46;
  }
  v12 = v6 + 7;
  if ( v12 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, v7, v8, v9);
  v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * v12 + 2);
  v14 = v13;
  if ( !v13 )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"OneCoreUap\\Private\\AVCore\\inc\\SpatialAudioLicenseBrokerUtil.h",
      (const char *)0x8007000ELL,
      v18);
    CoTaskMemFree(v10);
    return v5;
  }
  *v13 = 0;
  v13[v12] = 0;
  v21 = v13;
  v15 = StringCchPrintfW(v13, v12 + 1, L"com.%s", v10);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"OneCoreUap\\Private\\AVCore\\inc\\SpatialAudioLicenseBrokerUtil.h",
      (const char *)(unsigned int)v15,
      v18);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v21);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
    return v16;
  }
  else
  {
    *a2 = v14;
    CoTaskMemFree(v10);
    return 0;
  }
}

```

## disassembly

```asm
0x1800161bc  mov     [rsp+arg_10], rbx
0x1800161c1  mov     [rsp+arg_18], rbp
0x1800161c6  push    rsi
0x1800161c7  push    rdi
0x1800161c8  push    r14; int
0x1800161ca  sub     rsp, 20h
0x1800161ce  xor     ebp, ebp
0x1800161d0  mov     r14, rdx
0x1800161d3  mov     [rdx], rbp
0x1800161d6  test    rcx, rcx
0x1800161d9  jz      loc_180016375
0x1800161df  lea     r9d, [rbp+41h]
0x1800161e3  mov     rax, rcx
0x1800161e6  mov     r8d, r9d
0x1800161e9  cmp     [rax], bp
0x1800161ec  jz      short loc_1800161F8
0x1800161ee  add     rax, 2
0x1800161f2  sub     r8, 1
0x1800161f6  jnz     short loc_1800161E9
0x1800161f8  mov     rax, r8
0x1800161fb  neg     rax
0x1800161fe  mov     rax, r8
0x180016201  sbb     ebx, ebx
0x180016203  sub     r9, r8
0x180016206  not     ebx
0x180016208  and     ebx, 80070057h
0x18001620e  neg     rax
0x180016211  sbb     rdi, rdi
0x180016214  and     rdi, r9
0x180016217  test    r8, r8
0x18001621a  jz      loc_18001637A
0x180016220  mov     eax, 1Eh
0x180016225  mov     rdx, rcx
0x180016228  cmp     rdi, rax
0x18001622b  lea     rcx, [rsp+38h+pv]
0x180016230  cmova   rdi, rax
0x180016234  mov     r8, rdi
0x180016237  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001623c  mov     rsi, [rsp+38h+pv]
0x180016241  test    rsi, rsi
0x180016244  jz      loc_1800162D6
0x18001624a  mov     rax, rbp
0x18001624d  test    rdi, rdi
0x180016250  jz      short loc_180016265
0x180016252  cmp     word ptr [rsi+rax*2], 5Fh ; '_'
0x180016257  jz      loc_18001632B
0x18001625d  inc     rax
0x180016260  cmp     rax, rdi
0x180016263  jb      short loc_180016252
0x180016265  add     rdi, 7
0x180016269  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001626d  jz      loc_180016336
0x180016273  lea     rcx, ds:2[rdi*2]; cb
0x18001627b  call    cs:__imp_CoTaskMemAlloc
0x180016281  mov     rbx, rax
0x180016284  test    rax, rax
0x180016287  jz      short loc_180016302
0x180016289  mov     [rax], bp
0x18001628c  lea     rdx, [rdi+1]; unsigned __int64
0x180016290  mov     r9, rsi
0x180016293  mov     [rax+rdi*2], bp
0x180016297  lea     r8, aComS; "com.%s"
0x18001629e  mov     [rsp+38h+arg_8], rax
0x1800162a3  mov     rcx, rax; unsigned __int16 *
0x1800162a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800162ab  mov     edi, eax
0x1800162ad  test    eax, eax
0x1800162af  js      loc_180016341
0x1800162b5  mov     rcx, rsi; pv
0x1800162b8  mov     [r14], rbx
0x1800162bb  call    cs:__imp_CoTaskMemFree
0x1800162c1  xor     eax, eax
0x1800162c3  mov     rbx, [rsp+38h+arg_10]
0x1800162c8  mov     rbp, [rsp+38h+arg_18]
0x1800162cd  add     rsp, 20h
0x1800162d1  pop     r14
0x1800162d3  pop     rdi
0x1800162d4  pop     rsi
0x1800162d5  retn
0x1800162d6  mov     rcx, [rsp+38h]; this
0x1800162db  lea     r8, aOnecoreuapPriv; "OneCoreUap\\Private\\AVCore\\inc\\Spati"...
0x1800162e2  mov     ebx, 8007000Eh
0x1800162e7  mov     edx, 0C1h; void *
0x1800162ec  mov     r9d, ebx; char *
0x1800162ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800162f4  lea     rcx, [rsp+38h+pv]
0x1800162f9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800162fe  mov     eax, ebx
0x180016300  jmp     short loc_1800162C3
0x180016302  mov     rcx, [rsp+38h]; this
0x180016307  lea     r8, aOnecoreuapPriv; "OneCoreUap\\Private\\AVCore\\inc\\Spati"...
0x18001630e  mov     ebx, 8007000Eh
0x180016313  mov     edx, 0D3h; void *
0x180016318  mov     r9d, ebx; char *
0x18001631b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016320  mov     rcx, rsi; pv
0x180016323  call    cs:__imp_CoTaskMemFree
0x180016329  jmp     short loc_1800162FE
0x18001632b  mov     word ptr [rsi+rax*2], 2Eh ; '.'
0x180016331  jmp     loc_18001625D
0x180016336  mov     rcx, [rsp+38h]; this
0x18001633b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016341  mov     rcx, [rsp+38h]; this
0x180016346  lea     r8, aOnecoreuapPriv; "OneCoreUap\\Private\\AVCore\\inc\\Spati"...
0x18001634d  mov     r9d, edi; char *
0x180016350  mov     edx, 0D5h; void *
0x180016355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001635a  lea     rcx, [rsp+38h+arg_8]
0x18001635f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180016364  lea     rcx, [rsp+38h+pv]
0x180016369  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18001636e  mov     eax, edi
0x180016370  jmp     loc_1800162C3
0x180016375  mov     ebx, 80070057h
0x18001637a  mov     rcx, [rsp+38h]; this
0x18001637f  lea     r8, aOnecoreuapPriv; "OneCoreUap\\Private\\AVCore\\inc\\Spati"...
0x180016386  mov     r9d, ebx; char *
0x180016389  mov     edx, 0B8h; void *
0x18001638e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016393  jmp     loc_1800162FE
```
