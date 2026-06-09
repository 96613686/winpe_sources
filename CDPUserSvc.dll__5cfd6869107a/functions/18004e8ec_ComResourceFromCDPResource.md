# ComResourceFromCDPResource

- ea: `0x18004e8ec`
- end: `0x18004ec2b`
- name: `ComResourceFromCDPResource`
- size: `831`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001d9d0`

## callees

- `0x18001509c`
- `0x180016664`
- `0x18001e798`
- `0x18002ca90`
- `0x18002cad8`
- `0x18002d1c8`
- `0x18004e8ec`
- `0x18004ec34`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eb30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eb30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004eadc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004eadc`

## string_xrefs

- `0x18004e914`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18004e9c2`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18004eab1`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18004eb1c`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18004ebdb`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComResourceFromCDPResource(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  char *v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  char *v10; // rax
  unsigned __int64 v11; // r9
  char *v12; // rax
  unsigned __int64 v13; // r14
  void *v14; // rax
  void *v15; // rbx
  int v16; // eax
  unsigned int v17; // edi
  void *v18; // r14
  unsigned __int16 i; // di
  unsigned __int16 v20; // cx
  int v21; // eax
  unsigned int v22; // r15d
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  _QWORD v26[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  unsigned __int16 v28; // [rsp+68h] [rbp+38h] BYREF
  __int64 v29; // [rsp+70h] [rbp+40h] BYREF
  __int64 v30; // [rsp+78h] [rbp+48h] BYREF

  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 223;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)v4,
      v26[0]);
    return v4;
  }
  if ( !a1 )
  {
    v4 = -2147024809;
    v5 = 224;
    goto LABEL_3;
  }
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  v26[0] = 0;
  v30 = 0;
  v29 = 0;
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    v26,
    0);
  v7 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  v8 = CopyString_1(v7);
  v4 = v8;
  if ( v8 < 0 )
  {
    v9 = 232;
LABEL_11:
    v11 = (unsigned int)v8;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)v11,
      v26[0]);
LABEL_35:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v29);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v30);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v26);
    return v4;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v30,
    0);
  v10 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  v8 = CopyString_1(v10);
  v4 = v8;
  if ( v8 < 0 )
  {
    v9 = 233;
    goto LABEL_11;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v29,
    0);
  v12 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
  v8 = CopyString_1(v12);
  v4 = v8;
  if ( v8 < 0 )
  {
    v9 = 234;
    goto LABEL_11;
  }
  v28 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(a1, 0, &v28);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147221235 )
  {
    v11 = v4;
    v9 = 238;
    goto LABEL_12;
  }
  v13 = 8LL * v28;
  if ( !is_mul_ok(v28, 8u) )
    v13 = -1;
  v14 = operator new[](v13, (const struct std::nothrow_t *)std::nothrow);
  v15 = v14;
  if ( v14 )
    memset_0(v14, 0, v13);
  else
    v15 = 0;
  v26[1] = v15;
  v16 = (*(__int64 (__fastcall **)(__int64, void *, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(a1, v15, &v28);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF1,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v16,
      v26[0]);
    if ( v15 )
      operator delete(v15);
    v4 = v17;
    goto LABEL_35;
  }
  v18 = CoTaskMemAlloc(8LL * v28);
  if ( v18 )
  {
    for ( i = 0; ; ++i )
    {
      v20 = v28;
      if ( i >= v28 )
        break;
      v21 = CopyString_1(*((char **)v15 + i));
      v22 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFA,
          (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
          (const char *)(unsigned int)v21,
          v26[0]);
        CoTaskMemFree(v18);
        if ( v15 )
          operator delete(v15);
        v4 = v22;
        goto LABEL_35;
      }
    }
    v23 = v26[0];
    v26[0] = 0;
    *(_QWORD *)a2 = v23;
    v24 = v30;
    v30 = 0;
    *(_QWORD *)(a2 + 8) = v24;
    v25 = v29;
    v29 = 0;
    *(_QWORD *)(a2 + 16) = v25;
    *(_QWORD *)(a2 + 24) = v18;
    *(_WORD *)(a2 + 32) = v20;
    if ( v15 )
      operator delete(v15);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v29);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v30);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v26);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x8007000ELL,
      v26[0]);
    if ( v15 )
      operator delete(v15);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v29);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v30);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v26);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18004e8ec  mov     [rsp-28h+arg_0], rbx
0x18004e8f1  push    rbp
0x18004e8f2  push    rsi
0x18004e8f3  push    rdi
0x18004e8f4  push    r14
0x18004e8f6  push    r15
0x18004e8f8  mov     rbp, rsp
0x18004e8fb  sub     rsp, 30h
0x18004e8ff  mov     rsi, rdx
0x18004e902  mov     rdi, rcx
0x18004e905  test    rdx, rdx
0x18004e908  jnz     short loc_18004E92E
0x18004e90a  mov     ebx, 80004003h
0x18004e90f  mov     edx, 0DFh; void *
0x18004e914  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18004e91b  mov     r9d, ebx; char *
0x18004e91e  mov     rcx, [rbp+28h]; this
0x18004e922  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e927  mov     eax, ebx
0x18004e929  jmp     loc_18004EC1A
0x18004e92e  test    rdi, rdi
0x18004e931  jnz     short loc_18004E93F
0x18004e933  mov     ebx, 80070057h
0x18004e938  mov     edx, 0E0h
0x18004e93d  jmp     short loc_18004E914
0x18004e93f  xorps   xmm0, xmm0
0x18004e942  xor     eax, eax
0x18004e944  movups  xmmword ptr [rdx], xmm0
0x18004e947  movups  xmmword ptr [rdx+10h], xmm0
0x18004e94b  mov     [rdx+20h], rax
0x18004e94f  mov     [rbp+var_10], rax
0x18004e953  mov     [rbp+arg_18], rax
0x18004e957  mov     [rbp+arg_10], rax
0x18004e95b  xor     edx, edx
0x18004e95d  lea     rcx, [rbp+var_10]
0x18004e961  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x18004e966  mov     rax, [rdi]
0x18004e969  mov     rcx, rdi
0x18004e96c  mov     rax, [rax+18h]
0x18004e970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e975  lea     r8, [rbp+var_10]
0x18004e979  mov     rcx, rax; Source
0x18004e97c  call    CopyString_1
0x18004e981  mov     ebx, eax
0x18004e983  test    eax, eax
0x18004e985  jns     short loc_18004E98E
0x18004e987  mov     edx, 0E8h
0x18004e98c  jmp     short loc_18004E9BF
0x18004e98e  xor     edx, edx
0x18004e990  lea     rcx, [rbp+arg_18]
0x18004e994  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x18004e999  mov     rax, [rdi]
0x18004e99c  mov     rcx, rdi
0x18004e99f  mov     rax, [rax+20h]
0x18004e9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9a8  lea     r8, [rbp+arg_18]
0x18004e9ac  mov     rcx, rax; Source
0x18004e9af  call    CopyString_1
0x18004e9b4  mov     ebx, eax
0x18004e9b6  test    eax, eax
0x18004e9b8  jns     short loc_18004E9D7
0x18004e9ba  mov     edx, 0E9h; void *
0x18004e9bf  mov     r9d, eax; char *
0x18004e9c2  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18004e9c9  mov     rcx, [rbp+28h]; this
0x18004e9cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e9d2  jmp     loc_18004EB47
0x18004e9d7  xor     edx, edx
0x18004e9d9  lea     rcx, [rbp+arg_10]
0x18004e9dd  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x18004e9e2  mov     rax, [rdi]
0x18004e9e5  mov     rcx, rdi
0x18004e9e8  mov     rax, [rax+28h]
0x18004e9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9f1  lea     r8, [rbp+arg_10]
0x18004e9f5  mov     rcx, rax; Source
0x18004e9f8  call    CopyString_1
0x18004e9fd  mov     ebx, eax
0x18004e9ff  test    eax, eax
0x18004ea01  jns     short loc_18004EA0A
0x18004ea03  mov     edx, 0EAh
0x18004ea08  jmp     short loc_18004E9BF
0x18004ea0a  xor     eax, eax
0x18004ea0c  mov     [rbp+arg_8], ax
0x18004ea10  mov     rax, [rdi]
0x18004ea13  lea     r8, [rbp+arg_8]
0x18004ea17  xor     edx, edx
0x18004ea19  mov     rcx, rdi
0x18004ea1c  mov     rax, [rax+30h]
0x18004ea20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea25  mov     ebx, eax
0x18004ea27  mov     eax, 80000000h
0x18004ea2c  lea     ecx, [rbx+rax]
0x18004ea2f  test    eax, ecx
0x18004ea31  jnz     short loc_18004EA48
0x18004ea33  cmp     ebx, 8004010Dh
0x18004ea39  jz      short loc_18004EA48
0x18004ea3b  mov     r9d, ebx
0x18004ea3e  mov     edx, 0EEh
0x18004ea43  jmp     loc_18004E9C2
0x18004ea48  movzx   ecx, [rbp+arg_8]
0x18004ea4c  mov     eax, 8
0x18004ea51  mul     rcx
0x18004ea54  mov     r14, rax
0x18004ea57  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004ea5e  cmovb   r14, rax
0x18004ea62  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004ea69  mov     rcx, r14; unsigned __int64
0x18004ea6c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004ea71  mov     rbx, rax
0x18004ea74  test    rax, rax
0x18004ea77  jz      short loc_18004EA88
0x18004ea79  mov     r8, r14; Size
0x18004ea7c  xor     edx, edx; Val
0x18004ea7e  mov     rcx, rax; void *
0x18004ea81  call    memset_0
0x18004ea86  jmp     short loc_18004EA8A
0x18004ea88  xor     ebx, ebx
0x18004ea8a  mov     [rbp+var_8], rbx
0x18004ea8e  mov     rax, [rdi]
0x18004ea91  lea     r8, [rbp+arg_8]
0x18004ea95  mov     rdx, rbx
0x18004ea98  mov     rcx, rdi
0x18004ea9b  mov     rax, [rax+30h]
0x18004ea9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eaa4  mov     edi, eax
0x18004eaa6  test    eax, eax
0x18004eaa8  jns     short loc_18004EAD4
0x18004eaaa  mov     rcx, [rbp+28h]; this
0x18004eaae  mov     r9d, eax; char *
0x18004eab1  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18004eab8  mov     edx, 0F1h; void *
0x18004eabd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eac2  nop
0x18004eac3  test    rbx, rbx
0x18004eac6  jz      short loc_18004EAD0
0x18004eac8  mov     rcx, rbx; Block
0x18004eacb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004ead0  mov     ebx, edi
0x18004ead2  jmp     short loc_18004EB47
0x18004ead4  movzx   ecx, [rbp+arg_8]
0x18004ead8  shl     rcx, 3; cb
0x18004eadc  call    cs:__imp_CoTaskMemAlloc
0x18004eae2  mov     r14, rax
0x18004eae5  test    rax, rax
0x18004eae8  jz      loc_18004EBCF
0x18004eaee  xor     edi, edi
0x18004eaf0  movzx   ecx, [rbp+arg_8]
0x18004eaf4  cmp     di, cx
0x18004eaf7  jnb     short loc_18004EB69
0x18004eaf9  movzx   ecx, di
0x18004eafc  lea     r8, [r14+rcx*8]
0x18004eb00  mov     rcx, [rbx+rcx*8]; Source
0x18004eb04  call    CopyString_1
0x18004eb09  mov     r15d, eax
0x18004eb0c  test    eax, eax
0x18004eb0e  js      short loc_18004EB15
0x18004eb10  inc     di
0x18004eb13  jmp     short loc_18004EAF0
0x18004eb15  mov     rcx, [rbp+28h]; this
0x18004eb19  mov     r9d, r15d; char *
0x18004eb1c  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18004eb23  mov     edx, 0FAh; void *
0x18004eb28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eb2d  mov     rcx, r14; pv
0x18004eb30  call    cs:__imp_CoTaskMemFree
0x18004eb36  nop
0x18004eb37  test    rbx, rbx
0x18004eb3a  jz      short loc_18004EB44
0x18004eb3c  mov     rcx, rbx; Block
0x18004eb3f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004eb44  mov     ebx, r15d
0x18004eb47  lea     rcx, [rbp+arg_10]
0x18004eb4b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004eb50  nop
0x18004eb51  lea     rcx, [rbp+arg_18]
0x18004eb55  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004eb5a  nop
0x18004eb5b  lea     rcx, [rbp+var_10]
0x18004eb5f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004eb64  jmp     loc_18004E927
0x18004eb69  mov     rax, [rbp+var_10]
0x18004eb6d  mov     [rbp+var_10], 0
0x18004eb75  mov     [rsi], rax
0x18004eb78  mov     rax, [rbp+arg_18]
0x18004eb7c  mov     [rbp+arg_18], 0
0x18004eb84  mov     [rsi+8], rax
0x18004eb88  mov     rax, [rbp+arg_10]
0x18004eb8c  mov     [rbp+arg_10], 0
0x18004eb94  mov     [rsi+10h], rax
0x18004eb98  mov     [rsi+18h], r14
0x18004eb9c  mov     [rsi+20h], cx
0x18004eba0  test    rbx, rbx
0x18004eba3  jz      short loc_18004EBAE
0x18004eba5  mov     rcx, rbx; Block
0x18004eba8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004ebad  nop
0x18004ebae  lea     rcx, [rbp+arg_10]
0x18004ebb2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004ebb7  nop
0x18004ebb8  lea     rcx, [rbp+arg_18]
0x18004ebbc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004ebc1  nop
0x18004ebc2  lea     rcx, [rbp+var_10]
0x18004ebc6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004ebcb  xor     eax, eax
0x18004ebcd  jmp     short loc_18004EC1A
0x18004ebcf  mov     rcx, [rbp+28h]; this
0x18004ebd3  mov     edi, 8007000Eh
0x18004ebd8  mov     r9d, edi; char *
0x18004ebdb  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18004ebe2  mov     edx, 0F6h; void *
0x18004ebe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ebec  nop
0x18004ebed  test    rbx, rbx
0x18004ebf0  jz      short loc_18004EBFB
0x18004ebf2  mov     rcx, rbx; Block
0x18004ebf5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004ebfa  nop
0x18004ebfb  lea     rcx, [rbp+arg_10]
0x18004ebff  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004ec04  nop
0x18004ec05  lea     rcx, [rbp+arg_18]
0x18004ec09  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004ec0e  nop
0x18004ec0f  lea     rcx, [rbp+var_10]
0x18004ec13  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004ec18  mov     eax, edi
0x18004ec1a  mov     rbx, [rsp+30h+arg_0]
0x18004ec1f  add     rsp, 30h
0x18004ec23  pop     r15
0x18004ec25  pop     r14
0x18004ec27  pop     rdi
0x18004ec28  pop     rsi
0x18004ec29  pop     rbp
0x18004ec2a  retn
```
