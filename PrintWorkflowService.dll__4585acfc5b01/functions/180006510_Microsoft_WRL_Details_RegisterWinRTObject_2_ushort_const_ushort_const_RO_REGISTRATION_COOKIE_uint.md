# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x180006510`
- end: `0x180006610`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010100`

## callees

- `0x180003cc4`
- `0x1800041c0`
- `0x180006510`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800065da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800065da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800065a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800065a7`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1800065c5`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1800065c5`

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
0x180006510  push    rbx
0x180006512  push    rbp
0x180006513  push    rsi
0x180006514  push    rdi
0x180006515  push    r12
0x180006517  push    r13
0x180006519  push    r14
0x18000651b  push    r15
0x18000651d  sub     rsp, 28h
0x180006521  mov     r12, rdx
0x180006524  mov     edi, r9d
0x180006527  mov     esi, 8
0x18000652c  mov     rbp, r8
0x18000652f  mov     eax, esi
0x180006531  mul     rdi
0x180006534  lea     r14, [rsi-9]
0x180006538  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000653f  cmovb   rax, r14
0x180006543  mov     rcx, rax; unsigned __int64
0x180006546  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000654b  mov     r15, rax
0x18000654e  mov     eax, esi
0x180006550  mul     rdi
0x180006553  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000655a  cmovb   rax, r14
0x18000655e  mov     rcx, rax; unsigned __int64
0x180006561  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006566  xor     r13d, r13d
0x180006569  mov     r14, rax
0x18000656c  test    r15, r15
0x18000656f  jz      short loc_1800065E8
0x180006571  test    rax, rax
0x180006574  jz      short loc_1800065E8
0x180006576  mov     ebx, r13d
0x180006579  mov     esi, r13d
0x18000657c  test    edi, edi
0x18000657e  jz      short loc_1800065B9
0x180006580  test    ebx, ebx
0x180006582  js      short loc_1800065CD
0x180006584  mov     eax, esi
0x180006586  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x18000658d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180006591  mov     [r15+rax*8], rcx
0x180006595  mov     rcx, [r12+rax*8]; sourceString
0x180006599  inc     rdx; length
0x18000659c  cmp     [rcx+rdx*2], r13w
0x1800065a1  jnz     short loc_180006599
0x1800065a3  lea     r8, [r14+rax*8]; string
0x1800065a7  call    cs:__imp_WindowsCreateString
0x1800065ad  inc     esi
0x1800065af  mov     ebx, eax
0x1800065b1  cmp     esi, edi
0x1800065b3  jb      short loc_180006580
0x1800065b5  test    eax, eax
0x1800065b7  js      short loc_1800065CD
0x1800065b9  mov     r9, rbp
0x1800065bc  mov     r8d, edi
0x1800065bf  mov     rdx, r15
0x1800065c2  mov     rcx, r14
0x1800065c5  call    cs:__imp_RoRegisterActivationFactories
0x1800065cb  mov     ebx, eax
0x1800065cd  mov     edi, r13d
0x1800065d0  test    esi, esi
0x1800065d2  jz      short loc_1800065ED
0x1800065d4  mov     ecx, edi
0x1800065d6  mov     rcx, [r14+rcx*8]; string
0x1800065da  call    cs:__imp_WindowsDeleteString
0x1800065e0  inc     edi
0x1800065e2  cmp     edi, esi
0x1800065e4  jb      short loc_1800065D4
0x1800065e6  jmp     short loc_1800065ED
0x1800065e8  mov     ebx, 8007000Eh
0x1800065ed  mov     rcx, r15; void *
0x1800065f0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800065f5  mov     rcx, r14; void *
0x1800065f8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800065fd  mov     eax, ebx
0x1800065ff  add     rsp, 28h
0x180006603  pop     r15
0x180006605  pop     r14
0x180006607  pop     r13
0x180006609  pop     r12
0x18000660b  pop     rdi
0x18000660c  pop     rsi
0x18000660d  pop     rbp
0x18000660e  pop     rbx
0x18000660f  retn
```
