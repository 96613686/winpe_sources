# DllGetActivationFactory(HSTRING__ *,IActivationFactory * *)

- ea: `0x1800068b0`
- end: `0x180006a5b`
- name: `?DllGetActivationFactory@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `427`
- prototype: `__int64 __fastcall(HSTRING string, _QWORD *Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002590`
- `0x1800068b0`
- `0x1800070b4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000690a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000690a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000693e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000693e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180006920`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180006920`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180006a30`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180006a30`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800069c5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800069c5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800068eb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800068eb`

## string_xrefs

- `0x1800069f9`: `activatibleClassId`

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
  byte_180042240 = 1;
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
0x1800068b0  mov     [rsp+arg_10], rbx
0x1800068b5  mov     [rsp+arg_18], rbp
0x1800068ba  push    rsi
0x1800068bb  push    rdi
0x1800068bc  push    r14
0x1800068be  sub     rsp, 70h
0x1800068c2  mov     rax, cs:__security_cookie
0x1800068c9  xor     rax, rsp
0x1800068cc  mov     [rsp+88h+var_28], rax
0x1800068d1  mov     rsi, rdx
0x1800068d4  mov     rdi, rcx
0x1800068d7  xor     r9d, r9d; Context
0x1800068da  xor     r8d, r8d; Parameter
0x1800068dd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800068e4  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800068eb  call    cs:__imp_InitOnceExecuteOnce
0x1800068f1  mov     cs:byte_180042240, 1
0x1800068f8  mov     qword ptr [rsi], 0
0x1800068ff  mov     [rsp+88h+hasEmbedNull], 0
0x180006907  mov     rcx, rdi; string
0x18000690a  call    cs:__imp_WindowsIsStringEmpty
0x180006910  test    eax, eax
0x180006912  jnz     loc_1800069F9
0x180006918  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x18000691d  mov     rcx, rdi; string
0x180006920  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180006926  test    eax, eax
0x180006928  js      loc_1800069F9
0x18000692e  cmp     [rsp+88h+hasEmbedNull], 1
0x180006933  jz      loc_1800069F9
0x180006939  xor     edx, edx; length
0x18000693b  mov     rcx, rdi; string
0x18000693e  call    cs:__imp_WindowsGetStringRawBuffer
0x180006944  mov     r14, rax
0x180006947  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000694e  mov     rax, [rcx+28h]
0x180006952  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000695e  lea     rbx, [rax+8]
0x180006962  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006969  mov     rax, [rcx+30h]
0x18000696d  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006979  mov     rbp, rax
0x18000697c  cmp     rbx, rax
0x18000697f  jnb     short loc_1800069BB
0x180006981  mov     rax, [rbx]
0x180006984  test    rax, rax
0x180006987  jz      short loc_1800069B2
0x180006989  mov     rax, [rax+8]
0x18000698d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006992  mov     rcx, r14
0x180006995  sub     rax, r14
0x180006998  movzx   edx, word ptr [rcx]
0x18000699b  movzx   r8d, word ptr [rcx+rax]
0x1800069a0  sub     edx, r8d
0x1800069a3  jnz     short loc_1800069AE
0x1800069a5  add     rcx, 2
0x1800069a9  test    r8d, r8d
0x1800069ac  jnz     short loc_180006998
0x1800069ae  test    edx, edx
0x1800069b0  jz      short loc_1800069CD
0x1800069b2  add     rbx, 8
0x1800069b6  cmp     rbx, rbp
0x1800069b9  jb      short loc_180006981
0x1800069bb  mov     rdx, rdi
0x1800069be  mov     ebx, 80040111h
0x1800069c3  mov     ecx, ebx
0x1800069c5  call    cs:__imp_RoOriginateError
0x1800069cb  jmp     short loc_180006A37
0x1800069cd  mov     [rsp+88h+var_54], 1
0x1800069d5  mov     [rsp+88h+Ptr], rsi; Ptr
0x1800069da  mov     r9, [rbx]; struct _GUID *
0x1800069dd  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x1800069e4  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x1800069e9  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x1800069f0  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x1800069f5  mov     ebx, eax
0x1800069f7  jmp     short loc_180006A37
0x1800069f9  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180006a00  movups  [rsp+88h+var_50], xmm0
0x180006a05  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180006a0c  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x180006a11  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180006a19  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x180006a1f  lea     r8, [rsp+88h+var_50]
0x180006a24  mov     edx, 12h
0x180006a29  mov     ebx, 80070057h
0x180006a2e  mov     ecx, ebx
0x180006a30  call    cs:__imp_RoOriginateErrorW
0x180006a36  nop
0x180006a37  mov     eax, ebx
0x180006a39  mov     rcx, [rsp+88h+var_28]
0x180006a3e  xor     rcx, rsp; StackCookie
0x180006a41  call    __security_check_cookie
0x180006a46  lea     r11, [rsp+88h+var_18]
0x180006a4b  mov     rbx, [r11+30h]
0x180006a4f  mov     rbp, [r11+38h]
0x180006a53  mov     rsp, r11
0x180006a56  pop     r14
0x180006a58  pop     rdi
0x180006a59  pop     rsi
0x180006a5a  retn
```
