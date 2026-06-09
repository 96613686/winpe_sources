# Microsoft::WRL::Module<2,LanguageOverlayServiceModule>::RegisterWinRTObject(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x18000fe10`
- end: `0x18000ff14`
- name: `?RegisterWinRTObject@?$Module@$01VLanguageOverlayServiceModule@@@WRL@Microsoft@@UEAAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003ea0`
- `0x180005d90`
- `0x18000fe10`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000fec9`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000fec9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000feab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000feab`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Module<2,LanguageOverlayServiceModule>::RegisterWinRTObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  unsigned __int64 v6; // rax
  _QWORD *v8; // r15
  unsigned __int64 v9; // rax
  HSTRING *v10; // rax
  HSTRING *v11; // r14
  int v12; // ebx
  unsigned int v13; // esi
  __int64 v14; // rdx
  const WCHAR *v15; // rcx
  HRESULT String; // eax
  unsigned int i; // edi

  v6 = 8LL * a5;
  if ( !is_mul_ok(a5, 8u) )
    v6 = -1;
  v8 = operator new[](v6, (const struct std::nothrow_t *)std::nothrow);
  v9 = 8LL * a5;
  if ( !is_mul_ok(a5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
  v11 = v10;
  if ( v8 && v10 )
  {
    v12 = 0;
    v13 = 0;
    if ( a5 )
    {
      while ( v12 >= 0 )
      {
        v14 = -1;
        v8[v13] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
        v15 = *(const WCHAR **)(a3 + 8LL * v13);
        do
          ++v14;
        while ( v15[v14] );
        String = WindowsCreateString(v15, v14, &v11[v13++]);
        v12 = String;
        if ( v13 >= a5 )
        {
          if ( String < 0 )
            break;
          goto LABEL_13;
        }
      }
    }
    else
    {
LABEL_13:
      v12 = RoRegisterActivationFactories(v11, v8, a5, a4);
    }
    for ( i = 0; i < v13; ++i )
      WindowsDeleteString(v11[i]);
  }
  else
  {
    v12 = -2147024882;
  }
  operator delete(v8);
  operator delete(v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000fe10  push    rbx
0x18000fe12  push    rbp
0x18000fe13  push    rsi
0x18000fe14  push    rdi
0x18000fe15  push    r12
0x18000fe17  push    r13
0x18000fe19  push    r14
0x18000fe1b  push    r15
0x18000fe1d  sub     rsp, 28h
0x18000fe21  mov     edi, [rsp+68h+arg_20]
0x18000fe28  mov     esi, 8
0x18000fe2d  mov     eax, esi
0x18000fe2f  mov     rbp, r9
0x18000fe32  mul     rdi
0x18000fe35  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fe3c  mov     r12, r8
0x18000fe3f  lea     r14, [rsi-9]
0x18000fe43  cmovb   rax, r14
0x18000fe47  mov     rcx, rax; unsigned __int64
0x18000fe4a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000fe4f  mov     r15, rax
0x18000fe52  mov     eax, esi
0x18000fe54  mul     rdi
0x18000fe57  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fe5e  cmovb   rax, r14
0x18000fe62  mov     rcx, rax; unsigned __int64
0x18000fe65  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000fe6a  xor     r13d, r13d
0x18000fe6d  mov     r14, rax
0x18000fe70  test    r15, r15
0x18000fe73  jz      short loc_18000FEEC
0x18000fe75  test    rax, rax
0x18000fe78  jz      short loc_18000FEEC
0x18000fe7a  mov     ebx, r13d
0x18000fe7d  mov     esi, r13d
0x18000fe80  test    edi, edi
0x18000fe82  jz      short loc_18000FEBD
0x18000fe84  test    ebx, ebx
0x18000fe86  js      short loc_18000FED1
0x18000fe88  mov     eax, esi
0x18000fe8a  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x18000fe91  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000fe95  mov     [r15+rax*8], rcx
0x18000fe99  mov     rcx, [r12+rax*8]; sourceString
0x18000fe9d  inc     rdx; length
0x18000fea0  cmp     [rcx+rdx*2], r13w
0x18000fea5  jnz     short loc_18000FE9D
0x18000fea7  lea     r8, [r14+rax*8]; string
0x18000feab  call    cs:__imp_WindowsCreateString
0x18000feb1  inc     esi
0x18000feb3  mov     ebx, eax
0x18000feb5  cmp     esi, edi
0x18000feb7  jb      short loc_18000FE84
0x18000feb9  test    eax, eax
0x18000febb  js      short loc_18000FED1
0x18000febd  mov     r9, rbp
0x18000fec0  mov     r8d, edi
0x18000fec3  mov     rdx, r15
0x18000fec6  mov     rcx, r14
0x18000fec9  call    cs:__imp_RoRegisterActivationFactories
0x18000fecf  mov     ebx, eax
0x18000fed1  mov     edi, r13d
0x18000fed4  test    esi, esi
0x18000fed6  jz      short loc_18000FEF1
0x18000fed8  mov     ecx, edi
0x18000feda  mov     rcx, [r14+rcx*8]; string
0x18000fede  call    cs:__imp_WindowsDeleteString
0x18000fee4  inc     edi
0x18000fee6  cmp     edi, esi
0x18000fee8  jb      short loc_18000FED8
0x18000feea  jmp     short loc_18000FEF1
0x18000feec  mov     ebx, 8007000Eh
0x18000fef1  mov     rcx, r15; void *
0x18000fef4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fef9  mov     rcx, r14; void *
0x18000fefc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ff01  mov     eax, ebx
0x18000ff03  add     rsp, 28h
0x18000ff07  pop     r15
0x18000ff09  pop     r14
0x18000ff0b  pop     r13
0x18000ff0d  pop     r12
0x18000ff0f  pop     rdi
0x18000ff10  pop     rsi
0x18000ff11  pop     rbp
0x18000ff12  pop     rbx
0x18000ff13  retn
```
