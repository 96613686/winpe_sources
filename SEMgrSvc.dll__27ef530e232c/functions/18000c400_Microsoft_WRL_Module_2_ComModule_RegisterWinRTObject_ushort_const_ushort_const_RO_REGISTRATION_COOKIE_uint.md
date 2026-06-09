# Microsoft::WRL::Module<2,ComModule>::RegisterWinRTObject(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x18000c400`
- end: `0x18000c504`
- name: `?RegisterWinRTObject@?$Module@$01VComModule@@@WRL@Microsoft@@UEAAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800049c4`
- `0x180004e4c`
- `0x18000c400`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c4ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c4ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c49b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c49b`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000c4b9`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18000c4b9`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Module<2,ComModule>::RegisterWinRTObject(
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
0x18000c400  push    rbx
0x18000c402  push    rbp
0x18000c403  push    rsi
0x18000c404  push    rdi
0x18000c405  push    r12
0x18000c407  push    r13
0x18000c409  push    r14
0x18000c40b  push    r15
0x18000c40d  sub     rsp, 28h
0x18000c411  mov     edi, [rsp+68h+arg_20]
0x18000c418  mov     esi, 8
0x18000c41d  mov     eax, esi
0x18000c41f  mov     rbp, r9
0x18000c422  mul     rdi
0x18000c425  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c42c  mov     r12, r8
0x18000c42f  lea     r14, [rsi-9]
0x18000c433  cmovb   rax, r14
0x18000c437  mov     rcx, rax; unsigned __int64
0x18000c43a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000c43f  mov     r15, rax
0x18000c442  mov     eax, esi
0x18000c444  mul     rdi
0x18000c447  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c44e  cmovb   rax, r14
0x18000c452  mov     rcx, rax; unsigned __int64
0x18000c455  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000c45a  xor     r13d, r13d
0x18000c45d  mov     r14, rax
0x18000c460  test    r15, r15
0x18000c463  jz      short loc_18000C4DC
0x18000c465  test    rax, rax
0x18000c468  jz      short loc_18000C4DC
0x18000c46a  mov     ebx, r13d
0x18000c46d  mov     esi, r13d
0x18000c470  test    edi, edi
0x18000c472  jz      short loc_18000C4AD
0x18000c474  test    ebx, ebx
0x18000c476  js      short loc_18000C4C1
0x18000c478  mov     eax, esi
0x18000c47a  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x18000c481  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000c485  mov     [r15+rax*8], rcx
0x18000c489  mov     rcx, [r12+rax*8]; sourceString
0x18000c48d  inc     rdx; length
0x18000c490  cmp     [rcx+rdx*2], r13w
0x18000c495  jnz     short loc_18000C48D
0x18000c497  lea     r8, [r14+rax*8]; string
0x18000c49b  call    cs:__imp_WindowsCreateString
0x18000c4a1  inc     esi
0x18000c4a3  mov     ebx, eax
0x18000c4a5  cmp     esi, edi
0x18000c4a7  jb      short loc_18000C474
0x18000c4a9  test    eax, eax
0x18000c4ab  js      short loc_18000C4C1
0x18000c4ad  mov     r9, rbp
0x18000c4b0  mov     r8d, edi
0x18000c4b3  mov     rdx, r15
0x18000c4b6  mov     rcx, r14
0x18000c4b9  call    cs:__imp_RoRegisterActivationFactories
0x18000c4bf  mov     ebx, eax
0x18000c4c1  mov     edi, r13d
0x18000c4c4  test    esi, esi
0x18000c4c6  jz      short loc_18000C4E1
0x18000c4c8  mov     ecx, edi
0x18000c4ca  mov     rcx, [r14+rcx*8]; string
0x18000c4ce  call    cs:__imp_WindowsDeleteString
0x18000c4d4  inc     edi
0x18000c4d6  cmp     edi, esi
0x18000c4d8  jb      short loc_18000C4C8
0x18000c4da  jmp     short loc_18000C4E1
0x18000c4dc  mov     ebx, 8007000Eh
0x18000c4e1  mov     rcx, r15; Block
0x18000c4e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c4e9  mov     rcx, r14; Block
0x18000c4ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c4f1  mov     eax, ebx
0x18000c4f3  add     rsp, 28h
0x18000c4f7  pop     r15
0x18000c4f9  pop     r14
0x18000c4fb  pop     r13
0x18000c4fd  pop     r12
0x18000c4ff  pop     rdi
0x18000c500  pop     rsi
0x18000c501  pop     rbp
0x18000c502  pop     rbx
0x18000c503  retn
```
