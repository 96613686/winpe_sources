# DllGetActivationFactory

- ea: `0x180012a10`
- end: `0x180012bbb`
- name: `DllGetActivationFactory`
- size: `427`
- prototype: `__int64 __fastcall(HSTRING string, PVOID Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002240`
- `0x18000b310`
- `0x180012a10`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180012b90`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180012b90`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180012b25`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180012b25`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180012a4b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180012a4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012a9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180012a9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180012a80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180012a80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180012a6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180012a6a`

## string_xrefs

- `0x180012b59`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  byte_180082A48 = 1;
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
0x180012a10  mov     [rsp+arg_10], rbx
0x180012a15  mov     [rsp+arg_18], rbp
0x180012a1a  push    rsi
0x180012a1b  push    rdi
0x180012a1c  push    r14
0x180012a1e  sub     rsp, 70h
0x180012a22  mov     rax, cs:__security_cookie
0x180012a29  xor     rax, rsp
0x180012a2c  mov     [rsp+88h+var_28], rax
0x180012a31  mov     rsi, rdx
0x180012a34  mov     rdi, rcx
0x180012a37  xor     r9d, r9d; Context
0x180012a3a  xor     r8d, r8d; Parameter
0x180012a3d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180012a44  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180012a4b  call    cs:__imp_InitOnceExecuteOnce
0x180012a51  mov     cs:byte_180082A48, 1
0x180012a58  mov     qword ptr [rsi], 0
0x180012a5f  mov     [rsp+88h+hasEmbedNull], 0
0x180012a67  mov     rcx, rdi; string
0x180012a6a  call    cs:__imp_WindowsIsStringEmpty
0x180012a70  test    eax, eax
0x180012a72  jnz     loc_180012B59
0x180012a78  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x180012a7d  mov     rcx, rdi; string
0x180012a80  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180012a86  test    eax, eax
0x180012a88  js      loc_180012B59
0x180012a8e  cmp     [rsp+88h+hasEmbedNull], 1
0x180012a93  jz      loc_180012B59
0x180012a99  xor     edx, edx; length
0x180012a9b  mov     rcx, rdi; string
0x180012a9e  call    cs:__imp_WindowsGetStringRawBuffer
0x180012aa4  mov     r14, rax
0x180012aa7  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180012aae  mov     rax, [rcx+28h]
0x180012ab2  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180012ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012abe  lea     rbx, [rax+8]
0x180012ac2  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180012ac9  mov     rax, [rcx+30h]
0x180012acd  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180012ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ad9  mov     rbp, rax
0x180012adc  cmp     rbx, rax
0x180012adf  jnb     short loc_180012B1B
0x180012ae1  mov     rax, [rbx]
0x180012ae4  test    rax, rax
0x180012ae7  jz      short loc_180012B12
0x180012ae9  mov     rax, [rax+8]
0x180012aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012af2  mov     rcx, r14
0x180012af5  sub     rax, r14
0x180012af8  movzx   edx, word ptr [rcx]
0x180012afb  movzx   r8d, word ptr [rcx+rax]
0x180012b00  sub     edx, r8d
0x180012b03  jnz     short loc_180012B0E
0x180012b05  add     rcx, 2
0x180012b09  test    r8d, r8d
0x180012b0c  jnz     short loc_180012AF8
0x180012b0e  test    edx, edx
0x180012b10  jz      short loc_180012B2D
0x180012b12  add     rbx, 8
0x180012b16  cmp     rbx, rbp
0x180012b19  jb      short loc_180012AE1
0x180012b1b  mov     rdx, rdi
0x180012b1e  mov     ebx, 80040111h
0x180012b23  mov     ecx, ebx
0x180012b25  call    cs:__imp_RoOriginateError
0x180012b2b  jmp     short loc_180012B97
0x180012b2d  mov     [rsp+88h+var_54], 1
0x180012b35  mov     [rsp+88h+Ptr], rsi; Ptr
0x180012b3a  mov     r9, [rbx]; struct _GUID *
0x180012b3d  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180012b44  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x180012b49  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180012b50  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180012b55  mov     ebx, eax
0x180012b57  jmp     short loc_180012B97
0x180012b59  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180012b60  movups  [rsp+88h+var_50], xmm0
0x180012b65  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180012b6c  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x180012b71  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180012b79  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x180012b7f  lea     r8, [rsp+88h+var_50]
0x180012b84  mov     edx, 12h
0x180012b89  mov     ebx, 80070057h
0x180012b8e  mov     ecx, ebx
0x180012b90  call    cs:__imp_RoOriginateErrorW
0x180012b96  nop
0x180012b97  mov     eax, ebx
0x180012b99  mov     rcx, [rsp+88h+var_28]
0x180012b9e  xor     rcx, rsp; StackCookie
0x180012ba1  call    __security_check_cookie
0x180012ba6  lea     r11, [rsp+88h+var_18]
0x180012bab  mov     rbx, [r11+30h]
0x180012baf  mov     rbp, [r11+38h]
0x180012bb3  mov     rsp, r11
0x180012bb6  pop     r14
0x180012bb8  pop     rdi
0x180012bb9  pop     rsi
0x180012bba  retn
```
