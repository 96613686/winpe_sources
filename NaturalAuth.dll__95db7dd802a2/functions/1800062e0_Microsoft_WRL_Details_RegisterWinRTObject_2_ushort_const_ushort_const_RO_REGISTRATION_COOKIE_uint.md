# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x1800062e0`
- end: `0x1800063e0`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008f00`

## callees

- `0x180004194`
- `0x18000454c`
- `0x1800062e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800063aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800063aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180006377`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180006377`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180006395`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180006395`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::RegisterWinRTObject<2>(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v7; // rax
  _QWORD *v8; // r15
  unsigned __int64 v9; // rax
  HSTRING *v10; // rax
  const struct std::nothrow_t *v11; // rdx
  HSTRING *v12; // r14
  int v13; // ebx
  unsigned int v14; // esi
  __int64 v15; // rdx
  const WCHAR *v16; // rcx
  HRESULT String; // eax
  unsigned int i; // edi
  const struct std::nothrow_t *v19; // rdx

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
0x1800062e0  push    rbx
0x1800062e2  push    rbp
0x1800062e3  push    rsi
0x1800062e4  push    rdi
0x1800062e5  push    r12
0x1800062e7  push    r13
0x1800062e9  push    r14
0x1800062eb  push    r15
0x1800062ed  sub     rsp, 28h
0x1800062f1  mov     r12, rdx
0x1800062f4  mov     edi, r9d
0x1800062f7  mov     esi, 8
0x1800062fc  mov     rbp, r8
0x1800062ff  mov     eax, esi
0x180006301  mul     rdi
0x180006304  lea     r14, [rsi-9]
0x180006308  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000630f  cmovb   rax, r14
0x180006313  mov     rcx, rax; unsigned __int64
0x180006316  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000631b  mov     r15, rax
0x18000631e  mov     eax, esi
0x180006320  mul     rdi
0x180006323  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000632a  cmovb   rax, r14
0x18000632e  mov     rcx, rax; unsigned __int64
0x180006331  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006336  xor     r13d, r13d
0x180006339  mov     r14, rax
0x18000633c  test    r15, r15
0x18000633f  jz      short loc_1800063B8
0x180006341  test    rax, rax
0x180006344  jz      short loc_1800063B8
0x180006346  mov     ebx, r13d
0x180006349  mov     esi, r13d
0x18000634c  test    edi, edi
0x18000634e  jz      short loc_180006389
0x180006350  test    ebx, ebx
0x180006352  js      short loc_18000639D
0x180006354  mov     eax, esi
0x180006356  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x18000635d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180006361  mov     [r15+rax*8], rcx
0x180006365  mov     rcx, [r12+rax*8]; sourceString
0x180006369  inc     rdx; length
0x18000636c  cmp     [rcx+rdx*2], r13w
0x180006371  jnz     short loc_180006369
0x180006373  lea     r8, [r14+rax*8]; string
0x180006377  call    cs:__imp_WindowsCreateString
0x18000637d  inc     esi
0x18000637f  mov     ebx, eax
0x180006381  cmp     esi, edi
0x180006383  jb      short loc_180006350
0x180006385  test    eax, eax
0x180006387  js      short loc_18000639D
0x180006389  mov     r9, rbp
0x18000638c  mov     r8d, edi
0x18000638f  mov     rdx, r15
0x180006392  mov     rcx, r14
0x180006395  call    cs:__imp_RoRegisterActivationFactories
0x18000639b  mov     ebx, eax
0x18000639d  mov     edi, r13d
0x1800063a0  test    esi, esi
0x1800063a2  jz      short loc_1800063BD
0x1800063a4  mov     ecx, edi
0x1800063a6  mov     rcx, [r14+rcx*8]; string
0x1800063aa  call    cs:__imp_WindowsDeleteString
0x1800063b0  inc     edi
0x1800063b2  cmp     edi, esi
0x1800063b4  jb      short loc_1800063A4
0x1800063b6  jmp     short loc_1800063BD
0x1800063b8  mov     ebx, 8007000Eh
0x1800063bd  mov     rcx, r15; void *
0x1800063c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800063c5  mov     rcx, r14; void *
0x1800063c8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800063cd  mov     eax, ebx
0x1800063cf  add     rsp, 28h
0x1800063d3  pop     r15
0x1800063d5  pop     r14
0x1800063d7  pop     r13
0x1800063d9  pop     r12
0x1800063db  pop     rdi
0x1800063dc  pop     rsi
0x1800063dd  pop     rbp
0x1800063de  pop     rbx
0x1800063df  retn
```
