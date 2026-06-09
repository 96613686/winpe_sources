# wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18000e0fc`
- end: `0x18000e2d9`
- name: `??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e0a0`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x18000bbd4`
- `0x18000e0fc`
- `0x1800111f4`
- `0x18001da80`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e235`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e248`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e248`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e240`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e25b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e294`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e240`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e25b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e294`

## string_xrefs

- `0x18000e277`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
        __int64 a1,
        __int64 a2,
        char *a3)
{
  int v4; // edi
  unsigned __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rdx
  void *v8; // rbx
  unsigned __int64 v9; // rsi
  void *v10; // rsi
  DWORD LastError; // edi
  void *v12; // rcx
  LPVOID pv; // [rsp+28h] [rbp-E0h] BYREF
  unsigned __int64 v15; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v16; // [rsp+38h] [rbp-D0h] BYREF
  char v17; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v19[13]; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD *v20; // [rsp+B8h] [rbp-50h]
  _BYTE v21[256]; // [rsp+C8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F0h] [rbp+E8h]
  __int64 v23; // [rsp+200h] [rbp+F8h] BYREF

  v23 = a2;
  v16 = 0;
  v19[0] = &wistd::__function::__func<_lambda_21f43f16d02b49269b53009b18da9143_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v19[1] = &v16;
  v19[2] = &v23;
  v20 = v19;
  pv = 0;
  memset_0(v21, 0, sizeof(v21));
  v15 = 0;
  v4 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(&v18, v21, 128, &v15);
  if ( v4 >= 0 )
  {
    v5 = v15;
    if ( v15 > 0x80 )
    {
      while ( 1 )
      {
        v9 = v5;
        v6 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
               &pv,
               0,
               v5 - 1);
        v4 = v6;
        if ( v6 < 0 )
        {
          v7 = 378;
          goto LABEL_19;
        }
        v8 = pv;
        v4 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
               &v18,
               pv,
               v9,
               &v15);
        if ( v4 < 0 )
          break;
        v5 = v15;
        if ( v15 <= v9 )
          goto LABEL_9;
      }
      if ( !v8 )
        goto LABEL_21;
      v12 = v8;
      goto LABEL_20;
    }
    v6 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
           &pv,
           v21,
           v15 - 1);
    v4 = v6;
    if ( v6 >= 0 )
    {
      v8 = pv;
LABEL_9:
      if ( a3 == &v17 )
      {
        if ( v8 )
          CoTaskMemFree(v8);
      }
      else
      {
        v10 = *(void **)a3;
        if ( *(_QWORD *)a3 )
        {
          LastError = GetLastError();
          CoTaskMemFree(v10);
          SetLastError(LastError);
        }
        *(_QWORD *)a3 = v8;
      }
      v4 = 0;
    }
    else
    {
      v7 = 367;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)(unsigned int)v6,
        (int)pv);
      v12 = pv;
      if ( pv )
LABEL_20:
        CoTaskMemFree(v12);
    }
  }
LABEL_21:
  if ( v20 )
    (*(void (__fastcall **)(_QWORD *))(*v20 + 24LL))(v20);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e0fc  mov     rax, rsp
0x18000e0ff  mov     [rax+8], rbx
0x18000e103  mov     [rax+20h], rsi
0x18000e107  mov     [rax+10h], rdx
0x18000e10b  push    rbp
0x18000e10c  push    rdi
0x18000e10d  push    r14
0x18000e10f  lea     rbp, [rax-0E8h]
0x18000e116  sub     rsp, 1D0h
0x18000e11d  mov     rax, cs:__security_cookie
0x18000e124  xor     rax, rsp
0x18000e127  mov     [rbp+0E0h+var_20], rax
0x18000e12e  mov     r14, r8
0x18000e131  mov     [rsp+1E0h+var_1B0], 0
0x18000e13a  lea     rax, ??_7?$__func@V_lambda_21f43f16d02b49269b53009b18da9143_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_21f43f16d02b49269b53009b18da9143_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18000e141  mov     [rsp+1E0h+var_198], rax
0x18000e146  lea     rax, [rsp+1E0h+var_1B0]
0x18000e14b  mov     [rsp+1E0h+var_190], rax
0x18000e150  lea     rax, [rbp+0E0h+arg_8]
0x18000e157  mov     [rsp+1E0h+var_188], rax
0x18000e15c  lea     rax, [rsp+1E0h+var_198]
0x18000e161  mov     [rbp+0E0h+var_130], rax
0x18000e165  mov     [rsp+1E0h+pv], 0; int
0x18000e16e  xor     edx, edx; Val
0x18000e170  mov     r8d, 100h; Size
0x18000e176  lea     rcx, [rbp+0E0h+var_120]; void *
0x18000e17a  call    memset_0
0x18000e17f  mov     [rsp+1E0h+var_1B8], 0
0x18000e188  lea     r9, [rsp+1E0h+var_1B8]
0x18000e18d  mov     ebx, 80h
0x18000e192  mov     r8d, ebx
0x18000e195  lea     rdx, [rbp+0E0h+var_120]
0x18000e199  lea     rcx, [rsp+1E0h+var_1A0]
0x18000e19e  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18000e1a3  mov     edi, eax
0x18000e1a5  test    eax, eax
0x18000e1a7  js      loc_18000E29B
0x18000e1ad  mov     rax, [rsp+1E0h+var_1B8]
0x18000e1b2  cmp     rax, rbx
0x18000e1b5  ja      short loc_18000E1E0
0x18000e1b7  lea     r8, [rax-1]
0x18000e1bb  lea     rdx, [rbp+0E0h+var_120]
0x18000e1bf  lea     rcx, [rsp+1E0h+pv]
0x18000e1c4  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18000e1c9  mov     edi, eax
0x18000e1cb  test    eax, eax
0x18000e1cd  jns     short loc_18000E1D9
0x18000e1cf  mov     edx, 16Fh
0x18000e1d4  jmp     loc_18000E274
0x18000e1d9  mov     rbx, [rsp+1E0h+pv]
0x18000e1de  jmp     short loc_18000E223
0x18000e1e0  mov     rsi, rax
0x18000e1e3  lea     r8, [rax-1]
0x18000e1e7  xor     edx, edx
0x18000e1e9  lea     rcx, [rsp+1E0h+pv]
0x18000e1ee  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18000e1f3  mov     edi, eax
0x18000e1f5  test    eax, eax
0x18000e1f7  js      short loc_18000E26F
0x18000e1f9  lea     r9, [rsp+1E0h+var_1B8]
0x18000e1fe  mov     r8, rsi
0x18000e201  mov     rbx, [rsp+1E0h+pv]
0x18000e206  mov     rdx, rbx
0x18000e209  lea     rcx, [rsp+1E0h+var_1A0]
0x18000e20e  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18000e213  mov     edi, eax
0x18000e215  test    eax, eax
0x18000e217  js      short loc_18000E265
0x18000e219  mov     rax, [rsp+1E0h+var_1B8]
0x18000e21e  cmp     rax, rsi
0x18000e221  ja      short loc_18000E1E0
0x18000e223  lea     rax, [rsp+1E0h+var_1A8]
0x18000e228  cmp     r14, rax
0x18000e22b  jz      short loc_18000E253
0x18000e22d  mov     rsi, [r14]
0x18000e230  test    rsi, rsi
0x18000e233  jz      short loc_18000E24E
0x18000e235  call    cs:__imp_GetLastError
0x18000e23b  mov     edi, eax
0x18000e23d  mov     rcx, rsi; pv
0x18000e240  call    cs:__imp_CoTaskMemFree
0x18000e246  mov     ecx, edi; dwErrCode
0x18000e248  call    cs:__imp_SetLastError
0x18000e24e  mov     [r14], rbx
0x18000e251  jmp     short loc_18000E261
0x18000e253  test    rbx, rbx
0x18000e256  jz      short loc_18000E261
0x18000e258  mov     rcx, rbx; pv
0x18000e25b  call    cs:__imp_CoTaskMemFree
0x18000e261  xor     edi, edi
0x18000e263  jmp     short loc_18000E29B
0x18000e265  test    rbx, rbx
0x18000e268  jz      short loc_18000E29B
0x18000e26a  mov     rcx, rbx
0x18000e26d  jmp     short loc_18000E294
0x18000e26f  mov     edx, 17Ah; void *
0x18000e274  mov     r9d, eax; char *
0x18000e277  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e27e  mov     rcx, [rbp+0E8h]; this
0x18000e285  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e28a  mov     rcx, [rsp+1E0h+pv]; pv
0x18000e28f  test    rcx, rcx
0x18000e292  jz      short loc_18000E29B
0x18000e294  call    cs:__imp_CoTaskMemFree
0x18000e29a  nop
0x18000e29b  mov     rcx, [rbp+0E0h+var_130]
0x18000e29f  test    rcx, rcx
0x18000e2a2  jz      short loc_18000E2B0
0x18000e2a4  mov     rdx, [rcx]
0x18000e2a7  mov     rax, [rdx+18h]
0x18000e2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2b0  mov     eax, edi
0x18000e2b2  mov     rcx, [rbp+0E0h+var_20]
0x18000e2b9  xor     rcx, rsp; StackCookie
0x18000e2bc  call    __security_check_cookie
0x18000e2c1  lea     r11, [rsp+1E0h+var_10]
0x18000e2c9  mov     rbx, [r11+20h]
0x18000e2cd  mov     rsi, [r11+38h]
0x18000e2d1  mov     rsp, r11
0x18000e2d4  pop     r14
0x18000e2d6  pop     rdi
0x18000e2d7  pop     rbp
0x18000e2d8  retn
```
