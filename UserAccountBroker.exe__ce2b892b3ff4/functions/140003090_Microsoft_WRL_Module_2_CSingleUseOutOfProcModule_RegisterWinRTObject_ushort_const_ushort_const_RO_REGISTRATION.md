# Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::RegisterWinRTObject(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x140003090`
- end: `0x140003194`
- name: `?RegisterWinRTObject@?$Module@$01VCSingleUseOutOfProcModule@@@WRL@Microsoft@@UEAAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `260`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001184`
- `0x14000164c`
- `0x140003090`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000315e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000315e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000312b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000312b`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x140003149`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x140003149`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::RegisterWinRTObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  size_t v6; // rax
  _QWORD *v8; // r15
  size_t v9; // rax
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
  v8 = operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 8LL * a5;
  if ( !is_mul_ok(a5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
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
0x140003090  push    rbx
0x140003092  push    rbp
0x140003093  push    rsi
0x140003094  push    rdi
0x140003095  push    r12
0x140003097  push    r13
0x140003099  push    r14
0x14000309b  push    r15
0x14000309d  sub     rsp, 28h
0x1400030a1  mov     edi, [rsp+68h+arg_20]
0x1400030a8  mov     esi, 8
0x1400030ad  mov     eax, esi
0x1400030af  mov     rbp, r9
0x1400030b2  mul     rdi
0x1400030b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400030bc  mov     r12, r8
0x1400030bf  lea     r14, [rsi-9]
0x1400030c3  cmovb   rax, r14
0x1400030c7  mov     rcx, rax; unsigned __int64
0x1400030ca  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400030cf  mov     r15, rax
0x1400030d2  mov     eax, esi
0x1400030d4  mul     rdi
0x1400030d7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400030de  cmovb   rax, r14
0x1400030e2  mov     rcx, rax; unsigned __int64
0x1400030e5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400030ea  xor     r13d, r13d
0x1400030ed  mov     r14, rax
0x1400030f0  test    r15, r15
0x1400030f3  jz      short loc_14000316C
0x1400030f5  test    rax, rax
0x1400030f8  jz      short loc_14000316C
0x1400030fa  mov     ebx, r13d
0x1400030fd  mov     esi, r13d
0x140003100  test    edi, edi
0x140003102  jz      short loc_14000313D
0x140003104  test    ebx, ebx
0x140003106  js      short loc_140003151
0x140003108  mov     eax, esi
0x14000310a  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x140003111  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140003115  mov     [r15+rax*8], rcx
0x140003119  mov     rcx, [r12+rax*8]; sourceString
0x14000311d  inc     rdx; length
0x140003120  cmp     [rcx+rdx*2], r13w
0x140003125  jnz     short loc_14000311D
0x140003127  lea     r8, [r14+rax*8]; string
0x14000312b  call    cs:__imp_WindowsCreateString
0x140003131  inc     esi
0x140003133  mov     ebx, eax
0x140003135  cmp     esi, edi
0x140003137  jb      short loc_140003104
0x140003139  test    eax, eax
0x14000313b  js      short loc_140003151
0x14000313d  mov     r9, rbp
0x140003140  mov     r8d, edi
0x140003143  mov     rdx, r15
0x140003146  mov     rcx, r14
0x140003149  call    cs:__imp_RoRegisterActivationFactories
0x14000314f  mov     ebx, eax
0x140003151  mov     edi, r13d
0x140003154  test    esi, esi
0x140003156  jz      short loc_140003171
0x140003158  mov     ecx, edi
0x14000315a  mov     rcx, [r14+rcx*8]; string
0x14000315e  call    cs:__imp_WindowsDeleteString
0x140003164  inc     edi
0x140003166  cmp     edi, esi
0x140003168  jb      short loc_140003158
0x14000316a  jmp     short loc_140003171
0x14000316c  mov     ebx, 8007000Eh
0x140003171  mov     rcx, r15; Block
0x140003174  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003179  mov     rcx, r14; Block
0x14000317c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003181  mov     eax, ebx
0x140003183  add     rsp, 28h
0x140003187  pop     r15
0x140003189  pop     r14
0x14000318b  pop     r13
0x14000318d  pop     r12
0x14000318f  pop     rdi
0x140003190  pop     rsi
0x140003191  pop     rbp
0x140003192  pop     rbx
0x140003193  retn
```
