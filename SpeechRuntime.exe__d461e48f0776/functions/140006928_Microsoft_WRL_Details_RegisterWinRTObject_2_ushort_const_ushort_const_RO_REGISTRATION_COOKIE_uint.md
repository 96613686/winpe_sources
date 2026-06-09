# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x140006928`
- end: `0x140006a28`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d910`

## callees

- `0x140002d54`
- `0x140002ff4`
- `0x140006928`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400069f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400069f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1400069bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1400069bf`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1400069dd`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1400069dd`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RegisterWinRTObject<2>(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v7; // rax
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

  v5 = a4;
  v7 = 8LL * a4;
  if ( !is_mul_ok(a4, 8u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v8 && v10 )
  {
    v12 = 0;
    v13 = 0;
    if ( (_DWORD)v5 )
    {
      while ( v12 >= 0 )
      {
        v14 = -1;
        v8[v13] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
        v15 = *(const WCHAR **)(a2 + 8LL * v13);
        do
          ++v14;
        while ( v15[v14] );
        String = WindowsCreateString(v15, v14, &v11[v13++]);
        v12 = String;
        if ( v13 >= (unsigned int)v5 )
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
      v12 = RoRegisterActivationFactories(v11, v8, (unsigned int)v5, a3);
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
0x140006928  push    rbx
0x14000692a  push    rbp
0x14000692b  push    rsi
0x14000692c  push    rdi
0x14000692d  push    r12
0x14000692f  push    r13
0x140006931  push    r14
0x140006933  push    r15
0x140006935  sub     rsp, 28h
0x140006939  mov     r12, rdx
0x14000693c  mov     edi, r9d
0x14000693f  mov     esi, 8
0x140006944  mov     rbp, r8
0x140006947  mov     eax, esi
0x140006949  mul     rdi
0x14000694c  lea     r14, [rsi-9]
0x140006950  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140006957  cmovb   rax, r14
0x14000695b  mov     rcx, rax; unsigned __int64
0x14000695e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140006963  mov     r15, rax
0x140006966  mov     eax, esi
0x140006968  mul     rdi
0x14000696b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140006972  cmovb   rax, r14
0x140006976  mov     rcx, rax; unsigned __int64
0x140006979  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000697e  xor     r13d, r13d
0x140006981  mov     r14, rax
0x140006984  test    r15, r15
0x140006987  jz      short loc_140006A00
0x140006989  test    rax, rax
0x14000698c  jz      short loc_140006A00
0x14000698e  mov     ebx, r13d
0x140006991  mov     esi, r13d
0x140006994  test    edi, edi
0x140006996  jz      short loc_1400069D1
0x140006998  test    ebx, ebx
0x14000699a  js      short loc_1400069E5
0x14000699c  mov     eax, esi
0x14000699e  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x1400069a5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400069a9  mov     [r15+rax*8], rcx
0x1400069ad  mov     rcx, [r12+rax*8]; sourceString
0x1400069b1  inc     rdx; length
0x1400069b4  cmp     [rcx+rdx*2], r13w
0x1400069b9  jnz     short loc_1400069B1
0x1400069bb  lea     r8, [r14+rax*8]; string
0x1400069bf  call    cs:__imp_WindowsCreateString
0x1400069c5  inc     esi
0x1400069c7  mov     ebx, eax
0x1400069c9  cmp     esi, edi
0x1400069cb  jb      short loc_140006998
0x1400069cd  test    eax, eax
0x1400069cf  js      short loc_1400069E5
0x1400069d1  mov     r9, rbp
0x1400069d4  mov     r8d, edi
0x1400069d7  mov     rdx, r15
0x1400069da  mov     rcx, r14
0x1400069dd  call    cs:__imp_RoRegisterActivationFactories
0x1400069e3  mov     ebx, eax
0x1400069e5  mov     edi, r13d
0x1400069e8  test    esi, esi
0x1400069ea  jz      short loc_140006A05
0x1400069ec  mov     ecx, edi
0x1400069ee  mov     rcx, [r14+rcx*8]; string
0x1400069f2  call    cs:__imp_WindowsDeleteString
0x1400069f8  inc     edi
0x1400069fa  cmp     edi, esi
0x1400069fc  jb      short loc_1400069EC
0x1400069fe  jmp     short loc_140006A05
0x140006a00  mov     ebx, 8007000Eh
0x140006a05  mov     rcx, r15; Block
0x140006a08  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006a0d  mov     rcx, r14; Block
0x140006a10  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006a15  mov     eax, ebx
0x140006a17  add     rsp, 28h
0x140006a1b  pop     r15
0x140006a1d  pop     r14
0x140006a1f  pop     r13
0x140006a21  pop     r12
0x140006a23  pop     rdi
0x140006a24  pop     rsi
0x140006a25  pop     rbp
0x140006a26  pop     rbx
0x140006a27  retn
```
