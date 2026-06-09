# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x1400064ec`
- end: `0x1400065ec`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140006e10`

## callees

- `0x140001f14`
- `0x140001f4c`
- `0x1400064ec`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1400065a1`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1400065a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400065b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400065b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140006583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140006583`

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
  v8 = operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
  v9 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
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
0x1400064ec  push    rbx
0x1400064ee  push    rbp
0x1400064ef  push    rsi
0x1400064f0  push    rdi
0x1400064f1  push    r12
0x1400064f3  push    r13
0x1400064f5  push    r14
0x1400064f7  push    r15
0x1400064f9  sub     rsp, 28h
0x1400064fd  mov     r12, rdx
0x140006500  mov     edi, r9d
0x140006503  mov     esi, 8
0x140006508  mov     rbp, r8
0x14000650b  mov     eax, esi
0x14000650d  mul     rdi
0x140006510  lea     r14, [rsi-9]
0x140006514  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000651b  cmovb   rax, r14
0x14000651f  mov     rcx, rax; unsigned __int64
0x140006522  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140006527  mov     r15, rax
0x14000652a  mov     eax, esi
0x14000652c  mul     rdi
0x14000652f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140006536  cmovb   rax, r14
0x14000653a  mov     rcx, rax; unsigned __int64
0x14000653d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140006542  xor     r13d, r13d
0x140006545  mov     r14, rax
0x140006548  test    r15, r15
0x14000654b  jz      short loc_1400065C4
0x14000654d  test    rax, rax
0x140006550  jz      short loc_1400065C4
0x140006552  mov     ebx, r13d
0x140006555  mov     esi, r13d
0x140006558  test    edi, edi
0x14000655a  jz      short loc_140006595
0x14000655c  test    ebx, ebx
0x14000655e  js      short loc_1400065A9
0x140006560  mov     eax, esi
0x140006562  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x140006569  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000656d  mov     [r15+rax*8], rcx
0x140006571  mov     rcx, [r12+rax*8]; sourceString
0x140006575  inc     rdx; length
0x140006578  cmp     [rcx+rdx*2], r13w
0x14000657d  jnz     short loc_140006575
0x14000657f  lea     r8, [r14+rax*8]; string
0x140006583  call    cs:__imp_WindowsCreateString
0x140006589  inc     esi
0x14000658b  mov     ebx, eax
0x14000658d  cmp     esi, edi
0x14000658f  jb      short loc_14000655C
0x140006591  test    eax, eax
0x140006593  js      short loc_1400065A9
0x140006595  mov     r9, rbp
0x140006598  mov     r8d, edi
0x14000659b  mov     rdx, r15
0x14000659e  mov     rcx, r14
0x1400065a1  call    cs:__imp_RoRegisterActivationFactories
0x1400065a7  mov     ebx, eax
0x1400065a9  mov     edi, r13d
0x1400065ac  test    esi, esi
0x1400065ae  jz      short loc_1400065C9
0x1400065b0  mov     ecx, edi
0x1400065b2  mov     rcx, [r14+rcx*8]; string
0x1400065b6  call    cs:__imp_WindowsDeleteString
0x1400065bc  inc     edi
0x1400065be  cmp     edi, esi
0x1400065c0  jb      short loc_1400065B0
0x1400065c2  jmp     short loc_1400065C9
0x1400065c4  mov     ebx, 8007000Eh
0x1400065c9  mov     rcx, r15; void *
0x1400065cc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400065d1  mov     rcx, r14; void *
0x1400065d4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400065d9  mov     eax, ebx
0x1400065db  add     rsp, 28h
0x1400065df  pop     r15
0x1400065e1  pop     r14
0x1400065e3  pop     r13
0x1400065e5  pop     r12
0x1400065e7  pop     rdi
0x1400065e8  pop     rsi
0x1400065e9  pop     rbp
0x1400065ea  pop     rbx
0x1400065eb  retn
```
