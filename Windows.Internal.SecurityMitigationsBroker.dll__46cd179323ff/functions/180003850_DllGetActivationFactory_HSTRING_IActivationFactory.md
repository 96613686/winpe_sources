# DllGetActivationFactory(HSTRING__ *,IActivationFactory * *)

- ea: `0x180003850`
- end: `0x1800039fa`
- name: `?DllGetActivationFactory@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(HSTRING string, _QWORD *Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003850`
- `0x180003a00`
- `0x180006980`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800038de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800038de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800038c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800038c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800038aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800038aa`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800039d0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800039d0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003965`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003965`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000388b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000388b`

## string_xrefs

- `0x180003999`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(HSTRING string, _QWORD *Ptr)
{
  PCWSTR StringRawBuffer; // r14
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rbp
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // r8d
  int v11; // edx
  unsigned int v12; // ebx
  const struct _GUID *v13; // r9
  struct IUnknown **v15; // [rsp+28h] [rbp-60h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-58h] BYREF
  int v17; // [rsp+34h] [rbp-54h] BYREF
  __int128 v18; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v19[22]; // [rsp+48h] [rbp-40h]

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18000C8B8 = 1;
  *Ptr = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v12 = -2147024809;
    v18 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v19 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v19[14] = *(_QWORD *)L"sId";
    RoOriginateErrorW(2147942487LL, 18, &v18);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                           + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
       + 8;
    v6 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                           + 48LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
    if ( v5 >= v6 )
    {
LABEL_11:
      v12 = -2147221231;
      RoOriginateError(2147746065LL, string);
    }
    else
    {
      while ( 1 )
      {
        if ( *(_QWORD *)v5 )
        {
          v7 = (*(__int64 (**)(void))(*(_QWORD *)v5 + 8LL))();
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
        v5 += 8LL;
        if ( v5 >= v6 )
          goto LABEL_11;
      }
      v13 = *(const struct _GUID **)v5;
      v17 = 1;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v17,
                             &GUID_00000035_0000_0000_c000_000000000046.Data1,
                             v13,
                             Ptr,
                             v15);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180003850  mov     [rsp+arg_10], rbx
0x180003855  mov     [rsp+arg_18], rbp
0x18000385a  push    rsi
0x18000385b  push    rdi
0x18000385c  push    r14
0x18000385e  sub     rsp, 70h
0x180003862  mov     rax, cs:__security_cookie
0x180003869  xor     rax, rsp
0x18000386c  mov     [rsp+88h+var_28], rax
0x180003871  mov     rsi, rdx
0x180003874  mov     rdi, rcx
0x180003877  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000387e  xor     r9d, r9d; Context
0x180003881  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180003888  xor     r8d, r8d; Parameter
0x18000388b  call    cs:__imp_InitOnceExecuteOnce
0x180003891  mov     cs:byte_18000C8B8, 1
0x180003898  mov     rcx, rdi; string
0x18000389b  mov     qword ptr [rsi], 0
0x1800038a2  mov     [rsp+88h+hasEmbedNull], 0
0x1800038aa  call    cs:__imp_WindowsIsStringEmpty
0x1800038b0  test    eax, eax
0x1800038b2  jnz     loc_180003999
0x1800038b8  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x1800038bd  mov     rcx, rdi; string
0x1800038c0  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1800038c6  test    eax, eax
0x1800038c8  js      loc_180003999
0x1800038ce  cmp     [rsp+88h+hasEmbedNull], 1
0x1800038d3  jz      loc_180003999
0x1800038d9  xor     edx, edx; length
0x1800038db  mov     rcx, rdi; string
0x1800038de  call    cs:__imp_WindowsGetStringRawBuffer
0x1800038e4  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800038eb  mov     r14, rax
0x1800038ee  mov     rax, [rcx+28h]
0x1800038f2  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800038f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038fe  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003905  lea     rbx, [rax+8]
0x180003909  mov     rax, [rcx+30h]
0x18000390d  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180003914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003919  mov     rbp, rax
0x18000391c  cmp     rbx, rax
0x18000391f  jnb     short loc_18000395B
0x180003921  mov     rax, [rbx]
0x180003924  test    rax, rax
0x180003927  jz      short loc_180003952
0x180003929  mov     rax, [rax+8]
0x18000392d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003932  mov     rcx, r14
0x180003935  sub     rax, r14
0x180003938  movzx   edx, word ptr [rcx]
0x18000393b  movzx   r8d, word ptr [rcx+rax]
0x180003940  sub     edx, r8d
0x180003943  jnz     short loc_18000394E
0x180003945  add     rcx, 2
0x180003949  test    r8d, r8d
0x18000394c  jnz     short loc_180003938
0x18000394e  test    edx, edx
0x180003950  jz      short loc_18000396D
0x180003952  add     rbx, 8
0x180003956  cmp     rbx, rbp
0x180003959  jb      short loc_180003921
0x18000395b  mov     ebx, 80040111h
0x180003960  mov     rdx, rdi
0x180003963  mov     ecx, ebx
0x180003965  call    cs:__imp_RoOriginateError
0x18000396b  jmp     short loc_1800039D6
0x18000396d  mov     r9, [rbx]; struct _GUID *
0x180003970  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180003977  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x18000397c  mov     [rsp+88h+var_54], 1
0x180003984  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000398b  mov     [rsp+88h+Ptr], rsi; Ptr
0x180003990  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180003995  mov     ebx, eax
0x180003997  jmp     short loc_1800039D6
0x180003999  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x1800039a0  mov     ebx, 80070057h
0x1800039a5  lea     r8, [rsp+88h+var_50]
0x1800039aa  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x1800039b1  mov     edx, 12h
0x1800039b6  mov     ecx, ebx
0x1800039b8  movups  [rsp+88h+var_50], xmm0
0x1800039bd  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x1800039c5  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x1800039ca  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x1800039d0  call    cs:__imp_RoOriginateErrorW
0x1800039d6  mov     eax, ebx
0x1800039d8  mov     rcx, [rsp+88h+var_28]
0x1800039dd  xor     rcx, rsp; StackCookie
0x1800039e0  call    __security_check_cookie
0x1800039e5  lea     r11, [rsp+88h+var_18]
0x1800039ea  mov     rbx, [r11+30h]
0x1800039ee  mov     rbp, [r11+38h]
0x1800039f2  mov     rsp, r11
0x1800039f5  pop     r14
0x1800039f7  pop     rdi
0x1800039f8  pop     rsi
0x1800039f9  retn
```
