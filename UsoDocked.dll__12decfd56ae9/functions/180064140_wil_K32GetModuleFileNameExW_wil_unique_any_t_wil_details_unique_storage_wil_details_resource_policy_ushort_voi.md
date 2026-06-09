# wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180064140`
- end: `0x18006431d`
- name: `??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800640e4`

## callees

- `0x180007660`
- `0x18000856c`
- `0x1800183f4`
- `0x1800584d0`
- `0x18005a1c0`
- `0x180064140`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064279`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006428c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006428c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006429f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800642d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006429f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800642d8`

## string_xrefs

- `0x1800642bb`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

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
0x180064140  mov     rax, rsp
0x180064143  mov     [rax+8], rbx
0x180064147  mov     [rax+20h], rsi
0x18006414b  mov     [rax+10h], rdx
0x18006414f  push    rbp
0x180064150  push    rdi
0x180064151  push    r14
0x180064153  lea     rbp, [rax-0E8h]
0x18006415a  sub     rsp, 1D0h
0x180064161  mov     rax, cs:__security_cookie
0x180064168  xor     rax, rsp
0x18006416b  mov     [rbp+0E0h+var_20], rax
0x180064172  mov     r14, r8
0x180064175  mov     [rsp+1E0h+var_1B0], 0
0x18006417e  lea     rax, ??_7?$__func@V_lambda_21f43f16d02b49269b53009b18da9143_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_21f43f16d02b49269b53009b18da9143_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x180064185  mov     [rsp+1E0h+var_198], rax
0x18006418a  lea     rax, [rsp+1E0h+var_1B0]
0x18006418f  mov     [rsp+1E0h+var_190], rax
0x180064194  lea     rax, [rbp+0E0h+arg_8]
0x18006419b  mov     [rsp+1E0h+var_188], rax
0x1800641a0  lea     rax, [rsp+1E0h+var_198]
0x1800641a5  mov     [rbp+0E0h+var_130], rax
0x1800641a9  mov     [rsp+1E0h+pv], 0; int
0x1800641b2  xor     edx, edx; Val
0x1800641b4  mov     r8d, 100h; Size
0x1800641ba  lea     rcx, [rbp+0E0h+var_120]; void *
0x1800641be  call    memset_0
0x1800641c3  mov     [rsp+1E0h+var_1B8], 0
0x1800641cc  lea     r9, [rsp+1E0h+var_1B8]
0x1800641d1  mov     ebx, 80h
0x1800641d6  mov     r8d, ebx
0x1800641d9  lea     rdx, [rbp+0E0h+var_120]
0x1800641dd  lea     rcx, [rsp+1E0h+var_1A0]
0x1800641e2  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x1800641e7  mov     edi, eax
0x1800641e9  test    eax, eax
0x1800641eb  js      loc_1800642DF
0x1800641f1  mov     rax, [rsp+1E0h+var_1B8]
0x1800641f6  cmp     rax, rbx
0x1800641f9  ja      short loc_180064224
0x1800641fb  lea     r8, [rax-1]
0x1800641ff  lea     rdx, [rbp+0E0h+var_120]
0x180064203  lea     rcx, [rsp+1E0h+pv]
0x180064208  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18006420d  mov     edi, eax
0x18006420f  test    eax, eax
0x180064211  jns     short loc_18006421D
0x180064213  mov     edx, 16Fh
0x180064218  jmp     loc_1800642B8
0x18006421d  mov     rbx, [rsp+1E0h+pv]
0x180064222  jmp     short loc_180064267
0x180064224  mov     rsi, rax
0x180064227  lea     r8, [rax-1]
0x18006422b  xor     edx, edx
0x18006422d  lea     rcx, [rsp+1E0h+pv]
0x180064232  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180064237  mov     edi, eax
0x180064239  test    eax, eax
0x18006423b  js      short loc_1800642B3
0x18006423d  lea     r9, [rsp+1E0h+var_1B8]
0x180064242  mov     r8, rsi
0x180064245  mov     rbx, [rsp+1E0h+pv]
0x18006424a  mov     rdx, rbx
0x18006424d  lea     rcx, [rsp+1E0h+var_1A0]
0x180064252  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180064257  mov     edi, eax
0x180064259  test    eax, eax
0x18006425b  js      short loc_1800642A9
0x18006425d  mov     rax, [rsp+1E0h+var_1B8]
0x180064262  cmp     rax, rsi
0x180064265  ja      short loc_180064224
0x180064267  lea     rax, [rsp+1E0h+var_1A8]
0x18006426c  cmp     r14, rax
0x18006426f  jz      short loc_180064297
0x180064271  mov     rsi, [r14]
0x180064274  test    rsi, rsi
0x180064277  jz      short loc_180064292
0x180064279  call    cs:__imp_GetLastError
0x18006427f  mov     edi, eax
0x180064281  mov     rcx, rsi; pv
0x180064284  call    cs:__imp_CoTaskMemFree
0x18006428a  mov     ecx, edi; dwErrCode
0x18006428c  call    cs:__imp_SetLastError
0x180064292  mov     [r14], rbx
0x180064295  jmp     short loc_1800642A5
0x180064297  test    rbx, rbx
0x18006429a  jz      short loc_1800642A5
0x18006429c  mov     rcx, rbx; pv
0x18006429f  call    cs:__imp_CoTaskMemFree
0x1800642a5  xor     edi, edi
0x1800642a7  jmp     short loc_1800642DF
0x1800642a9  test    rbx, rbx
0x1800642ac  jz      short loc_1800642DF
0x1800642ae  mov     rcx, rbx
0x1800642b1  jmp     short loc_1800642D8
0x1800642b3  mov     edx, 17Ah; void *
0x1800642b8  mov     r9d, eax; char *
0x1800642bb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800642c2  mov     rcx, [rbp+0E8h]; this
0x1800642c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800642ce  mov     rcx, [rsp+1E0h+pv]; pv
0x1800642d3  test    rcx, rcx
0x1800642d6  jz      short loc_1800642DF
0x1800642d8  call    cs:__imp_CoTaskMemFree
0x1800642de  nop
0x1800642df  mov     rcx, [rbp+0E0h+var_130]
0x1800642e3  test    rcx, rcx
0x1800642e6  jz      short loc_1800642F4
0x1800642e8  mov     rdx, [rcx]
0x1800642eb  mov     rax, [rdx+18h]
0x1800642ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642f4  mov     eax, edi
0x1800642f6  mov     rcx, [rbp+0E0h+var_20]
0x1800642fd  xor     rcx, rsp; StackCookie
0x180064300  call    __security_check_cookie
0x180064305  lea     r11, [rsp+1E0h+var_10]
0x18006430d  mov     rbx, [r11+20h]
0x180064311  mov     rsi, [r11+38h]
0x180064315  mov     rsp, r11
0x180064318  pop     r14
0x18006431a  pop     rdi
0x18006431b  pop     rbp
0x18006431c  retn
```
