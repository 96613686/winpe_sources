# DllGetActivationFactory(HSTRING__ *,IActivationFactory * *)

- ea: `0x180008c10`
- end: `0x180008dbb`
- name: `?DllGetActivationFactory@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `427`
- prototype: `__int64 __fastcall(HSTRING string, _QWORD *Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008c10`
- `0x180008dc4`
- `0x180011460`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180008c80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180008c80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008c9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008c9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180008c6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180008c6a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180008d90`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180008d90`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008d25`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008d25`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008c4b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008c4b`

## string_xrefs

- `0x180008d59`: `activatibleClassId`

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
  byte_180022C18 = 1;
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
0x180008c10  mov     [rsp+arg_10], rbx
0x180008c15  mov     [rsp+arg_18], rbp
0x180008c1a  push    rsi
0x180008c1b  push    rdi
0x180008c1c  push    r14
0x180008c1e  sub     rsp, 70h
0x180008c22  mov     rax, cs:__security_cookie
0x180008c29  xor     rax, rsp
0x180008c2c  mov     [rsp+88h+var_28], rax
0x180008c31  mov     rsi, rdx
0x180008c34  mov     rdi, rcx
0x180008c37  xor     r9d, r9d; Context
0x180008c3a  xor     r8d, r8d; Parameter
0x180008c3d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180008c44  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180008c4b  call    cs:__imp_InitOnceExecuteOnce
0x180008c51  mov     cs:byte_180022C18, 1
0x180008c58  mov     qword ptr [rsi], 0
0x180008c5f  mov     [rsp+88h+hasEmbedNull], 0
0x180008c67  mov     rcx, rdi; string
0x180008c6a  call    cs:__imp_WindowsIsStringEmpty
0x180008c70  test    eax, eax
0x180008c72  jnz     loc_180008D59
0x180008c78  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x180008c7d  mov     rcx, rdi; string
0x180008c80  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180008c86  test    eax, eax
0x180008c88  js      loc_180008D59
0x180008c8e  cmp     [rsp+88h+hasEmbedNull], 1
0x180008c93  jz      loc_180008D59
0x180008c99  xor     edx, edx; length
0x180008c9b  mov     rcx, rdi; string
0x180008c9e  call    cs:__imp_WindowsGetStringRawBuffer
0x180008ca4  mov     r14, rax
0x180008ca7  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008cae  mov     rax, [rcx+28h]
0x180008cb2  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cbe  lea     rbx, [rax+8]
0x180008cc2  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008cc9  mov     rax, [rcx+30h]
0x180008ccd  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cd9  mov     rbp, rax
0x180008cdc  cmp     rbx, rax
0x180008cdf  jnb     short loc_180008D1B
0x180008ce1  mov     rax, [rbx]
0x180008ce4  test    rax, rax
0x180008ce7  jz      short loc_180008D12
0x180008ce9  mov     rax, [rax+8]
0x180008ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cf2  mov     rcx, r14
0x180008cf5  sub     rax, r14
0x180008cf8  movzx   edx, word ptr [rcx]
0x180008cfb  movzx   r8d, word ptr [rcx+rax]
0x180008d00  sub     edx, r8d
0x180008d03  jnz     short loc_180008D0E
0x180008d05  add     rcx, 2
0x180008d09  test    r8d, r8d
0x180008d0c  jnz     short loc_180008CF8
0x180008d0e  test    edx, edx
0x180008d10  jz      short loc_180008D2D
0x180008d12  add     rbx, 8
0x180008d16  cmp     rbx, rbp
0x180008d19  jb      short loc_180008CE1
0x180008d1b  mov     rdx, rdi
0x180008d1e  mov     ebx, 80040111h
0x180008d23  mov     ecx, ebx
0x180008d25  call    cs:__imp_RoOriginateError
0x180008d2b  jmp     short loc_180008D97
0x180008d2d  mov     [rsp+88h+var_54], 1
0x180008d35  mov     [rsp+88h+Ptr], rsi; Ptr
0x180008d3a  mov     r9, [rbx]; struct _GUID *
0x180008d3d  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180008d44  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x180008d49  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180008d50  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180008d55  mov     ebx, eax
0x180008d57  jmp     short loc_180008D97
0x180008d59  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180008d60  movups  [rsp+88h+var_50], xmm0
0x180008d65  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180008d6c  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x180008d71  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180008d79  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x180008d7f  lea     r8, [rsp+88h+var_50]
0x180008d84  mov     edx, 12h
0x180008d89  mov     ebx, 80070057h
0x180008d8e  mov     ecx, ebx
0x180008d90  call    cs:__imp_RoOriginateErrorW
0x180008d96  nop
0x180008d97  mov     eax, ebx
0x180008d99  mov     rcx, [rsp+88h+var_28]
0x180008d9e  xor     rcx, rsp; StackCookie
0x180008da1  call    __security_check_cookie
0x180008da6  lea     r11, [rsp+88h+var_18]
0x180008dab  mov     rbx, [r11+30h]
0x180008daf  mov     rbp, [r11+38h]
0x180008db3  mov     rsp, r11
0x180008db6  pop     r14
0x180008db8  pop     rdi
0x180008db9  pop     rsi
0x180008dba  retn
```
