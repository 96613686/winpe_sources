# DllGetActivationFactory

- ea: `0x18000b940`
- end: `0x18000baeb`
- name: `DllGetActivationFactory`
- size: `427`
- prototype: `__int64 __fastcall(HSTRING string, _QWORD *Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002350`
- `0x18000b158`
- `0x18000b940`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000bac0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000bac0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ba55`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ba55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000b9b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000b9b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000b99a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000b99a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b9ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b9ce`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b97b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b97b`

## string_xrefs

- `0x18000ba89`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(HSTRING string, _QWORD *Ptr)
{
  PCWSTR StringRawBuffer; // r14
  const struct _GUID **v5; // rbx
  unsigned __int64 v6; // rbp
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // r8d
  int v11; // edx
  unsigned int v12; // ebx
  struct IUnknown **v14; // [rsp+28h] [rbp-60h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-58h] BYREF
  int v16; // [rsp+34h] [rbp-54h] BYREF
  __int128 v17; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v18[22]; // [rsp+48h] [rbp-40h]

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18005A058 = 1;
  *Ptr = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v17 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v18 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v18[14] = *(_QWORD *)L"sId";
    v12 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v17);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                   + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                               + 8);
    v6 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                           + 48LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
    if ( (unsigned __int64)v5 >= v6 )
    {
LABEL_11:
      v12 = -2147221231;
      RoOriginateError(2147746065LL, string);
    }
    else
    {
      while ( 1 )
      {
        if ( *v5 )
        {
          v7 = (*(__int64 (**)(void))(*v5)->Data4)();
          v8 = (unsigned __int16 *)StringRawBuffer;
          v9 = v7 - (_QWORD)StringRawBuffer;
          do
          {
            v10 = *(unsigned __int16 *)((char *)v8 + v9);
            v11 = *v8 - v10;
            if ( v11 )
              break;
            ++v8;
          }
          while ( v10 );
          if ( !v11 )
            break;
        }
        if ( (unsigned __int64)++v5 >= v6 )
          goto LABEL_11;
      }
      v16 = 1;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v16,
                             &GUID_00000035_0000_0000_c000_000000000046.Data1,
                             *v5,
                             Ptr,
                             v14);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18000b940  mov     [rsp+arg_10], rbx
0x18000b945  mov     [rsp+arg_18], rbp
0x18000b94a  push    rsi
0x18000b94b  push    rdi
0x18000b94c  push    r14
0x18000b94e  sub     rsp, 70h
0x18000b952  mov     rax, cs:__security_cookie
0x18000b959  xor     rax, rsp
0x18000b95c  mov     [rsp+88h+var_28], rax
0x18000b961  mov     rsi, rdx
0x18000b964  mov     rdi, rcx
0x18000b967  xor     r9d, r9d; Context
0x18000b96a  xor     r8d, r8d; Parameter
0x18000b96d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000b974  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000b97b  call    cs:__imp_InitOnceExecuteOnce
0x18000b981  mov     cs:byte_18005A058, 1
0x18000b988  mov     qword ptr [rsi], 0
0x18000b98f  mov     [rsp+88h+hasEmbedNull], 0
0x18000b997  mov     rcx, rdi; string
0x18000b99a  call    cs:__imp_WindowsIsStringEmpty
0x18000b9a0  test    eax, eax
0x18000b9a2  jnz     loc_18000BA89
0x18000b9a8  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x18000b9ad  mov     rcx, rdi; string
0x18000b9b0  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18000b9b6  test    eax, eax
0x18000b9b8  js      loc_18000BA89
0x18000b9be  cmp     [rsp+88h+hasEmbedNull], 1
0x18000b9c3  jz      loc_18000BA89
0x18000b9c9  xor     edx, edx; length
0x18000b9cb  mov     rcx, rdi; string
0x18000b9ce  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b9d4  mov     r14, rax
0x18000b9d7  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b9de  mov     rax, [rcx+28h]
0x18000b9e2  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9ee  lea     rbx, [rax+8]
0x18000b9f2  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b9f9  mov     rax, [rcx+30h]
0x18000b9fd  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000ba04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba09  mov     rbp, rax
0x18000ba0c  cmp     rbx, rax
0x18000ba0f  jnb     short loc_18000BA4B
0x18000ba11  mov     rax, [rbx]
0x18000ba14  test    rax, rax
0x18000ba17  jz      short loc_18000BA42
0x18000ba19  mov     rax, [rax+8]
0x18000ba1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba22  mov     rcx, r14
0x18000ba25  sub     rax, r14
0x18000ba28  movzx   edx, word ptr [rcx]
0x18000ba2b  movzx   r8d, word ptr [rcx+rax]
0x18000ba30  sub     edx, r8d
0x18000ba33  jnz     short loc_18000BA3E
0x18000ba35  add     rcx, 2
0x18000ba39  test    r8d, r8d
0x18000ba3c  jnz     short loc_18000BA28
0x18000ba3e  test    edx, edx
0x18000ba40  jz      short loc_18000BA5D
0x18000ba42  add     rbx, 8
0x18000ba46  cmp     rbx, rbp
0x18000ba49  jb      short loc_18000BA11
0x18000ba4b  mov     rdx, rdi
0x18000ba4e  mov     ebx, 80040111h
0x18000ba53  mov     ecx, ebx
0x18000ba55  call    cs:__imp_RoOriginateError
0x18000ba5b  jmp     short loc_18000BAC7
0x18000ba5d  mov     [rsp+88h+var_54], 1
0x18000ba65  mov     [rsp+88h+Ptr], rsi; Ptr
0x18000ba6a  mov     r9, [rbx]; struct _GUID *
0x18000ba6d  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x18000ba74  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x18000ba79  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000ba80  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000ba85  mov     ebx, eax
0x18000ba87  jmp     short loc_18000BAC7
0x18000ba89  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x18000ba90  movups  [rsp+88h+var_50], xmm0
0x18000ba95  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18000ba9c  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x18000baa1  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x18000baa9  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x18000baaf  lea     r8, [rsp+88h+var_50]
0x18000bab4  mov     edx, 12h
0x18000bab9  mov     ebx, 80070057h
0x18000babe  mov     ecx, ebx
0x18000bac0  call    cs:__imp_RoOriginateErrorW
0x18000bac6  nop
0x18000bac7  mov     eax, ebx
0x18000bac9  mov     rcx, [rsp+88h+var_28]
0x18000bace  xor     rcx, rsp; StackCookie
0x18000bad1  call    __security_check_cookie
0x18000bad6  lea     r11, [rsp+88h+var_18]
0x18000badb  mov     rbx, [r11+30h]
0x18000badf  mov     rbp, [r11+38h]
0x18000bae3  mov     rsp, r11
0x18000bae6  pop     r14
0x18000bae8  pop     rdi
0x18000bae9  pop     rsi
0x18000baea  retn
```
