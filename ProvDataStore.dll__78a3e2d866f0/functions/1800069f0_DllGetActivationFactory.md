# DllGetActivationFactory

- ea: `0x1800069f0`
- end: `0x180006b9b`
- name: `DllGetActivationFactory`
- size: `427`
- prototype: `__int64 __fastcall(HSTRING string, _QWORD *Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003ea4`
- `0x1800069f0`
- `0x180010f80`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006a2b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006a2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180006a60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180006a60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180006a4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180006a4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180006a7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180006a7e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180006b70`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180006b70`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006b05`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006b05`

## string_xrefs

- `0x180006b39`: `activatibleClassId`

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
  BOOL hasEmbedNull; // [rsp+30h] [rbp-58h] BYREF
  int v15; // [rsp+34h] [rbp-54h] BYREF
  __int128 v16; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v17[22]; // [rsp+48h] [rbp-40h]

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_1800199D8 = 1;
  *Ptr = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v16 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v17 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v17[14] = *(_QWORD *)L"sId";
    v12 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v16);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (const struct _GUID **)((*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                      + 40))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                               + 8);
    v6 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                              + 48))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
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
      v15 = 1;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v15,
                             &GUID_00000035_0000_0000_c000_000000000046.Data1,
                             *v5,
                             Ptr);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x1800069f0  mov     [rsp+arg_10], rbx
0x1800069f5  mov     [rsp+arg_18], rbp
0x1800069fa  push    rsi
0x1800069fb  push    rdi
0x1800069fc  push    r14
0x1800069fe  sub     rsp, 70h
0x180006a02  mov     rax, cs:__security_cookie
0x180006a09  xor     rax, rsp
0x180006a0c  mov     [rsp+88h+var_28], rax
0x180006a11  mov     rsi, rdx
0x180006a14  mov     rdi, rcx
0x180006a17  xor     r9d, r9d; Context
0x180006a1a  xor     r8d, r8d; Parameter
0x180006a1d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180006a24  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180006a2b  call    cs:__imp_InitOnceExecuteOnce
0x180006a31  mov     cs:byte_1800199D8, 1
0x180006a38  mov     qword ptr [rsi], 0
0x180006a3f  mov     [rsp+88h+hasEmbedNull], 0
0x180006a47  mov     rcx, rdi; string
0x180006a4a  call    cs:__imp_WindowsIsStringEmpty
0x180006a50  test    eax, eax
0x180006a52  jnz     loc_180006B39
0x180006a58  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x180006a5d  mov     rcx, rdi; string
0x180006a60  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180006a66  test    eax, eax
0x180006a68  js      loc_180006B39
0x180006a6e  cmp     [rsp+88h+hasEmbedNull], 1
0x180006a73  jz      loc_180006B39
0x180006a79  xor     edx, edx; length
0x180006a7b  mov     rcx, rdi; string
0x180006a7e  call    cs:__imp_WindowsGetStringRawBuffer
0x180006a84  mov     r14, rax
0x180006a87  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006a8e  mov     rax, [rcx+28h]
0x180006a92  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a9e  lea     rbx, [rax+8]
0x180006aa2  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006aa9  mov     rax, [rcx+30h]
0x180006aad  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab9  mov     rbp, rax
0x180006abc  cmp     rbx, rax
0x180006abf  jnb     short loc_180006AFB
0x180006ac1  mov     rax, [rbx]
0x180006ac4  test    rax, rax
0x180006ac7  jz      short loc_180006AF2
0x180006ac9  mov     rax, [rax+8]
0x180006acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ad2  mov     rcx, r14
0x180006ad5  sub     rax, r14
0x180006ad8  movzx   edx, word ptr [rcx]
0x180006adb  movzx   r8d, word ptr [rcx+rax]
0x180006ae0  sub     edx, r8d
0x180006ae3  jnz     short loc_180006AEE
0x180006ae5  add     rcx, 2
0x180006ae9  test    r8d, r8d
0x180006aec  jnz     short loc_180006AD8
0x180006aee  test    edx, edx
0x180006af0  jz      short loc_180006B0D
0x180006af2  add     rbx, 8
0x180006af6  cmp     rbx, rbp
0x180006af9  jb      short loc_180006AC1
0x180006afb  mov     rdx, rdi
0x180006afe  mov     ebx, 80040111h
0x180006b03  mov     ecx, ebx
0x180006b05  call    cs:__imp_RoOriginateError
0x180006b0b  jmp     short loc_180006B77
0x180006b0d  mov     [rsp+88h+var_54], 1
0x180006b15  mov     [rsp+88h+Ptr], rsi; Ptr
0x180006b1a  mov     r9, [rbx]; struct _GUID *
0x180006b1d  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180006b24  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x180006b29  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180006b30  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180006b35  mov     ebx, eax
0x180006b37  jmp     short loc_180006B77
0x180006b39  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180006b40  movups  [rsp+88h+var_50], xmm0
0x180006b45  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180006b4c  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x180006b51  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180006b59  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x180006b5f  lea     r8, [rsp+88h+var_50]
0x180006b64  mov     edx, 12h
0x180006b69  mov     ebx, 80070057h
0x180006b6e  mov     ecx, ebx
0x180006b70  call    cs:__imp_RoOriginateErrorW
0x180006b76  nop
0x180006b77  mov     eax, ebx
0x180006b79  mov     rcx, [rsp+88h+var_28]
0x180006b7e  xor     rcx, rsp; StackCookie
0x180006b81  call    __security_check_cookie
0x180006b86  lea     r11, [rsp+88h+var_18]
0x180006b8b  mov     rbx, [r11+30h]
0x180006b8f  mov     rbp, [r11+38h]
0x180006b93  mov     rsp, r11
0x180006b96  pop     r14
0x180006b98  pop     rdi
0x180006b99  pop     rsi
0x180006b9a  retn
```
