# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x1800065d4`
- end: `0x1800066d4`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800089d0`

## callees

- `0x180003554`
- `0x180003938`
- `0x1800065d4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000666b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000666b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000669e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000669e`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180006689`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180006689`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RegisterWinRTObject<2>(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v7; // rax
  _QWORD *v8; // r15
  unsigned __int64 v9; // rax
  HSTRING *v10; // rax
  unsigned __int64 v11; // rdx
  HSTRING *v12; // r14
  int v13; // ebx
  unsigned int v14; // esi
  __int64 v15; // rdx
  const WCHAR *v16; // rcx
  HRESULT String; // eax
  unsigned int i; // edi
  unsigned __int64 v19; // rdx

  v5 = a4;
  v7 = 8LL * a4;
  if ( !is_mul_ok(a4, 8u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v10;
  if ( v8 && v10 )
  {
    v13 = 0;
    v14 = 0;
    if ( (_DWORD)v5 )
    {
      while ( v13 >= 0 )
      {
        v15 = -1;
        v8[v14] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
        v16 = *(const WCHAR **)(a2 + 8LL * v14);
        do
          ++v15;
        while ( v16[v15] );
        String = WindowsCreateString(v16, v15, &v12[v14++]);
        v13 = String;
        if ( v14 >= (unsigned int)v5 )
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
      v13 = RoRegisterActivationFactories(v12, v8, (unsigned int)v5, a3);
    }
    for ( i = 0; i < v14; ++i )
      WindowsDeleteString(v12[i]);
  }
  else
  {
    v13 = -2147024882;
  }
  operator delete(v8, v11);
  operator delete(v12, v19);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800065d4  push    rbx
0x1800065d6  push    rbp
0x1800065d7  push    rsi
0x1800065d8  push    rdi
0x1800065d9  push    r12
0x1800065db  push    r13
0x1800065dd  push    r14
0x1800065df  push    r15
0x1800065e1  sub     rsp, 28h
0x1800065e5  mov     r12, rdx
0x1800065e8  mov     edi, r9d
0x1800065eb  mov     esi, 8
0x1800065f0  mov     rbp, r8
0x1800065f3  mov     eax, esi
0x1800065f5  mul     rdi
0x1800065f8  lea     r14, [rsi-9]
0x1800065fc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006603  cmovb   rax, r14
0x180006607  mov     rcx, rax; unsigned __int64
0x18000660a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000660f  mov     r15, rax
0x180006612  mov     eax, esi
0x180006614  mul     rdi
0x180006617  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000661e  cmovb   rax, r14
0x180006622  mov     rcx, rax; unsigned __int64
0x180006625  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000662a  xor     r13d, r13d
0x18000662d  mov     r14, rax
0x180006630  test    r15, r15
0x180006633  jz      short loc_1800066AC
0x180006635  test    rax, rax
0x180006638  jz      short loc_1800066AC
0x18000663a  mov     ebx, r13d
0x18000663d  mov     esi, r13d
0x180006640  test    edi, edi
0x180006642  jz      short loc_18000667D
0x180006644  test    ebx, ebx
0x180006646  js      short loc_180006691
0x180006648  mov     eax, esi
0x18000664a  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x180006651  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180006655  mov     [r15+rax*8], rcx
0x180006659  mov     rcx, [r12+rax*8]; sourceString
0x18000665d  inc     rdx; length
0x180006660  cmp     [rcx+rdx*2], r13w
0x180006665  jnz     short loc_18000665D
0x180006667  lea     r8, [r14+rax*8]; string
0x18000666b  call    cs:__imp_WindowsCreateString
0x180006671  inc     esi
0x180006673  mov     ebx, eax
0x180006675  cmp     esi, edi
0x180006677  jb      short loc_180006644
0x180006679  test    eax, eax
0x18000667b  js      short loc_180006691
0x18000667d  mov     r9, rbp
0x180006680  mov     r8d, edi
0x180006683  mov     rdx, r15
0x180006686  mov     rcx, r14
0x180006689  call    cs:__imp_RoRegisterActivationFactories
0x18000668f  mov     ebx, eax
0x180006691  mov     edi, r13d
0x180006694  test    esi, esi
0x180006696  jz      short loc_1800066B1
0x180006698  mov     ecx, edi
0x18000669a  mov     rcx, [r14+rcx*8]; string
0x18000669e  call    cs:__imp_WindowsDeleteString
0x1800066a4  inc     edi
0x1800066a6  cmp     edi, esi
0x1800066a8  jb      short loc_180006698
0x1800066aa  jmp     short loc_1800066B1
0x1800066ac  mov     ebx, 8007000Eh
0x1800066b1  mov     rcx, r15; void *
0x1800066b4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800066b9  mov     rcx, r14; void *
0x1800066bc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800066c1  mov     eax, ebx
0x1800066c3  add     rsp, 28h
0x1800066c7  pop     r15
0x1800066c9  pop     r14
0x1800066cb  pop     r13
0x1800066cd  pop     r12
0x1800066cf  pop     rdi
0x1800066d0  pop     rsi
0x1800066d1  pop     rbp
0x1800066d2  pop     rbx
0x1800066d3  retn
```
