# ComResourceFromCDPResource_2

- ea: `0x180012da0`
- end: `0x1800130e4`
- name: `ComResourceFromCDPResource_2`
- size: `836`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000cd08`

## callees

- `0x1800085e0`
- `0x18000cce4`
- `0x18000e9c8`
- `0x180012da0`
- `0x1800130ec`
- `0x180016b74`
- `0x180018d18`
- `0x180022a90`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012f67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012f67`

## string_xrefs

- `0x180012dc8`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180012e76`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180012f31`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180012fb4`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180013089`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComResourceFromCDPResource_2(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  char *v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  char *v10; // rax
  unsigned __int64 v11; // r9
  char *v12; // rax
  void *v13; // rbx
  int v14; // eax
  unsigned int v15; // edi
  unsigned __int64 v16; // rdx
  LPVOID v17; // rax
  void *v18; // r15
  unsigned __int16 i; // di
  unsigned __int16 v20; // cx
  int v21; // eax
  unsigned int v22; // r14d
  unsigned __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  __int64 v29; // [rsp+20h] [rbp-10h] BYREF
  void *v30; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  unsigned __int16 v32; // [rsp+68h] [rbp+38h] BYREF
  __int64 v33; // [rsp+70h] [rbp+40h] BYREF
  __int64 v34; // [rsp+78h] [rbp+48h] BYREF

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
      v29);
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
  v29 = 0;
  v34 = 0;
  v33 = 0;
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v29,
    0);
  v7 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  v8 = CopyString_0(v7);
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
      v29);
LABEL_30:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v33);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v34);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v29);
    return v4;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v34,
    0);
  v10 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  v8 = CopyString_0(v10);
  v4 = v8;
  if ( v8 < 0 )
  {
    v9 = 233;
    goto LABEL_11;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v33,
    0);
  v12 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
  v8 = CopyString_0(v12);
  v4 = v8;
  if ( v8 < 0 )
  {
    v9 = 234;
    goto LABEL_11;
  }
  v32 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(a1, 0, &v32);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147221235 )
  {
    v11 = v4;
    v9 = 238;
    goto LABEL_12;
  }
  wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(&v30, v32);
  v13 = v30;
  v14 = (*(__int64 (__fastcall **)(__int64, void *, unsigned __int16 *))(*(_QWORD *)a1 + 48LL))(a1, v30, &v32);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF1,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v14,
      v29);
    if ( v13 )
      operator delete(v13, v16);
    v4 = v15;
    goto LABEL_30;
  }
  v30 = 0;
  v17 = CoTaskMemAlloc(8LL * v32);
  wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v30,
    v17);
  v18 = v30;
  if ( v30 )
  {
    for ( i = 0; ; ++i )
    {
      v20 = v32;
      if ( i >= v32 )
        break;
      v21 = CopyString_0(*((char **)v13 + i));
      v22 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFA,
          (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
          (const char *)(unsigned int)v21,
          v29);
        wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v30,
          0);
        if ( v13 )
          operator delete(v13, v23);
        v4 = v22;
        goto LABEL_30;
      }
    }
    v24 = v29;
    v29 = 0;
    *(_QWORD *)a2 = v24;
    v25 = v34;
    v34 = 0;
    *(_QWORD *)(a2 + 8) = v25;
    v26 = v33;
    v33 = 0;
    *(_QWORD *)(a2 + 16) = v26;
    v30 = 0;
    *(_QWORD *)(a2 + 24) = v18;
    *(_WORD *)(a2 + 32) = v20;
    wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v30,
      0);
    if ( v13 )
      operator delete(v13, v27);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v33);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v34);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v29);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x8007000ELL,
      v29);
    wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v30,
      0);
    if ( v13 )
      operator delete(v13, v28);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v33);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v34);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v29);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180012da0  mov     [rsp-28h+arg_0], rbx
0x180012da5  push    rbp
0x180012da6  push    rsi
0x180012da7  push    rdi
0x180012da8  push    r14
0x180012daa  push    r15
0x180012dac  mov     rbp, rsp
0x180012daf  sub     rsp, 30h
0x180012db3  mov     rsi, rdx
0x180012db6  mov     rdi, rcx
0x180012db9  test    rdx, rdx
0x180012dbc  jnz     short loc_180012DE2
0x180012dbe  mov     ebx, 80004003h
0x180012dc3  mov     edx, 0DFh; void *
0x180012dc8  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180012dcf  mov     r9d, ebx; char *
0x180012dd2  mov     rcx, [rbp+28h]; this
0x180012dd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ddb  mov     eax, ebx
0x180012ddd  jmp     loc_1800130D3
0x180012de2  test    rdi, rdi
0x180012de5  jnz     short loc_180012DF3
0x180012de7  mov     ebx, 80070057h
0x180012dec  mov     edx, 0E0h
0x180012df1  jmp     short loc_180012DC8
0x180012df3  xorps   xmm0, xmm0
0x180012df6  xor     eax, eax
0x180012df8  movups  xmmword ptr [rdx], xmm0
0x180012dfb  movups  xmmword ptr [rdx+10h], xmm0
0x180012dff  mov     [rdx+20h], rax
0x180012e03  mov     [rbp+var_10], rax
0x180012e07  mov     [rbp+arg_18], rax
0x180012e0b  mov     [rbp+arg_10], rax
0x180012e0f  xor     edx, edx
0x180012e11  lea     rcx, [rbp+var_10]
0x180012e15  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180012e1a  mov     rax, [rdi]
0x180012e1d  mov     rcx, rdi
0x180012e20  mov     rax, [rax+18h]
0x180012e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e29  lea     r8, [rbp+var_10]
0x180012e2d  mov     rcx, rax; Source
0x180012e30  call    CopyString_0
0x180012e35  mov     ebx, eax
0x180012e37  test    eax, eax
0x180012e39  jns     short loc_180012E42
0x180012e3b  mov     edx, 0E8h
0x180012e40  jmp     short loc_180012E73
0x180012e42  xor     edx, edx
0x180012e44  lea     rcx, [rbp+arg_18]
0x180012e48  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180012e4d  mov     rax, [rdi]
0x180012e50  mov     rcx, rdi
0x180012e53  mov     rax, [rax+20h]
0x180012e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e5c  lea     r8, [rbp+arg_18]
0x180012e60  mov     rcx, rax; Source
0x180012e63  call    CopyString_0
0x180012e68  mov     ebx, eax
0x180012e6a  test    eax, eax
0x180012e6c  jns     short loc_180012E8B
0x180012e6e  mov     edx, 0E9h; void *
0x180012e73  mov     r9d, eax; char *
0x180012e76  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180012e7d  mov     rcx, [rbp+28h]; this
0x180012e81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e86  jmp     loc_180012FE1
0x180012e8b  xor     edx, edx
0x180012e8d  lea     rcx, [rbp+arg_10]
0x180012e91  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180012e96  mov     rax, [rdi]
0x180012e99  mov     rcx, rdi
0x180012e9c  mov     rax, [rax+28h]
0x180012ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ea5  lea     r8, [rbp+arg_10]
0x180012ea9  mov     rcx, rax; Source
0x180012eac  call    CopyString_0
0x180012eb1  mov     ebx, eax
0x180012eb3  test    eax, eax
0x180012eb5  jns     short loc_180012EBE
0x180012eb7  mov     edx, 0EAh
0x180012ebc  jmp     short loc_180012E73
0x180012ebe  xor     eax, eax
0x180012ec0  mov     [rbp+arg_8], ax
0x180012ec4  mov     rax, [rdi]
0x180012ec7  lea     r8, [rbp+arg_8]
0x180012ecb  xor     edx, edx
0x180012ecd  mov     rcx, rdi
0x180012ed0  mov     rax, [rax+30h]
0x180012ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ed9  mov     ebx, eax
0x180012edb  mov     eax, 80000000h
0x180012ee0  lea     ecx, [rbx+rax]
0x180012ee3  test    eax, ecx
0x180012ee5  jnz     short loc_180012EFC
0x180012ee7  cmp     ebx, 8004010Dh
0x180012eed  jz      short loc_180012EFC
0x180012eef  mov     r9d, ebx
0x180012ef2  mov     edx, 0EEh
0x180012ef7  jmp     loc_180012E76
0x180012efc  movzx   edx, [rbp+arg_8]
0x180012f00  lea     rcx, [rbp+var_8]
0x180012f04  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPEndpointAccount@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(unsigned __int64)
0x180012f09  nop
0x180012f0a  mov     rax, [rdi]
0x180012f0d  lea     r8, [rbp+arg_8]
0x180012f11  mov     rbx, [rbp+var_8]
0x180012f15  mov     rdx, rbx
0x180012f18  mov     rcx, rdi
0x180012f1b  mov     rax, [rax+30h]
0x180012f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f24  mov     edi, eax
0x180012f26  test    eax, eax
0x180012f28  jns     short loc_180012F57
0x180012f2a  mov     rcx, [rbp+28h]; this
0x180012f2e  mov     r9d, eax; char *
0x180012f31  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180012f38  mov     edx, 0F1h; void *
0x180012f3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f42  nop
0x180012f43  test    rbx, rbx
0x180012f46  jz      short loc_180012F50
0x180012f48  mov     rcx, rbx; void *
0x180012f4b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012f50  mov     ebx, edi
0x180012f52  jmp     loc_180012FE1
0x180012f57  mov     [rbp+var_8], 0
0x180012f5f  movzx   ecx, [rbp+arg_8]
0x180012f63  shl     rcx, 3; cb
0x180012f67  call    cs:__imp_CoTaskMemAlloc
0x180012f6d  mov     rdx, rax
0x180012f70  lea     rcx, [rbp+var_8]
0x180012f74  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x180012f79  mov     r15, [rbp+var_8]
0x180012f7d  test    r15, r15
0x180012f80  jz      loc_18001307D
0x180012f86  xor     edi, edi
0x180012f88  movzx   ecx, [rbp+arg_8]
0x180012f8c  cmp     di, cx
0x180012f8f  jnb     short loc_180013003
0x180012f91  movzx   ecx, di
0x180012f94  lea     r8, [r15+rcx*8]
0x180012f98  mov     rcx, [rbx+rcx*8]; Source
0x180012f9c  call    CopyString_0
0x180012fa1  mov     r14d, eax
0x180012fa4  test    eax, eax
0x180012fa6  js      short loc_180012FAD
0x180012fa8  inc     di
0x180012fab  jmp     short loc_180012F88
0x180012fad  mov     rcx, [rbp+28h]; this
0x180012fb1  mov     r9d, r14d; char *
0x180012fb4  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180012fbb  mov     edx, 0FAh; void *
0x180012fc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012fc5  xor     edx, edx
0x180012fc7  lea     rcx, [rbp+var_8]
0x180012fcb  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x180012fd0  nop
0x180012fd1  test    rbx, rbx
0x180012fd4  jz      short loc_180012FDE
0x180012fd6  mov     rcx, rbx; void *
0x180012fd9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012fde  mov     ebx, r14d
0x180012fe1  lea     rcx, [rbp+arg_10]
0x180012fe5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180012fea  nop
0x180012feb  lea     rcx, [rbp+arg_18]
0x180012fef  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180012ff4  nop
0x180012ff5  lea     rcx, [rbp+var_10]
0x180012ff9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180012ffe  jmp     loc_180012DDB
0x180013003  mov     rax, [rbp+var_10]
0x180013007  mov     [rbp+var_10], 0
0x18001300f  mov     [rsi], rax
0x180013012  mov     rax, [rbp+arg_18]
0x180013016  mov     [rbp+arg_18], 0
0x18001301e  mov     [rsi+8], rax
0x180013022  mov     rax, [rbp+arg_10]
0x180013026  mov     [rbp+arg_10], 0
0x18001302e  mov     [rsi+10h], rax
0x180013032  mov     [rbp+var_8], 0
0x18001303a  mov     [rsi+18h], r15
0x18001303e  mov     [rsi+20h], cx
0x180013042  xor     edx, edx
0x180013044  lea     rcx, [rbp+var_8]
0x180013048  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x18001304d  nop
0x18001304e  test    rbx, rbx
0x180013051  jz      short loc_18001305C
0x180013053  mov     rcx, rbx; void *
0x180013056  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001305b  nop
0x18001305c  lea     rcx, [rbp+arg_10]
0x180013060  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180013065  nop
0x180013066  lea     rcx, [rbp+arg_18]
0x18001306a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18001306f  nop
0x180013070  lea     rcx, [rbp+var_10]
0x180013074  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180013079  xor     eax, eax
0x18001307b  jmp     short loc_1800130D3
0x18001307d  mov     rcx, [rbp+28h]; this
0x180013081  mov     edi, 8007000Eh
0x180013086  mov     r9d, edi; char *
0x180013089  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180013090  mov     edx, 0F6h; void *
0x180013095  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001309a  xor     edx, edx
0x18001309c  lea     rcx, [rbp+var_8]
0x1800130a0  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x1800130a5  nop
0x1800130a6  test    rbx, rbx
0x1800130a9  jz      short loc_1800130B4
0x1800130ab  mov     rcx, rbx; void *
0x1800130ae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800130b3  nop
0x1800130b4  lea     rcx, [rbp+arg_10]
0x1800130b8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800130bd  nop
0x1800130be  lea     rcx, [rbp+arg_18]
0x1800130c2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800130c7  nop
0x1800130c8  lea     rcx, [rbp+var_10]
0x1800130cc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800130d1  mov     eax, edi
0x1800130d3  mov     rbx, [rsp+30h+arg_0]
0x1800130d8  add     rsp, 30h
0x1800130dc  pop     r15
0x1800130de  pop     r14
0x1800130e0  pop     rdi
0x1800130e1  pop     rsi
0x1800130e2  pop     rbp
0x1800130e3  retn
```
