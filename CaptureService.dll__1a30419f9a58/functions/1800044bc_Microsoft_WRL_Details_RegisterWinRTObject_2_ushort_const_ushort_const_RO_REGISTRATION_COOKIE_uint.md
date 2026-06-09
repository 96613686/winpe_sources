# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x1800044bc`
- end: `0x1800045bc`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008ec0`

## callees

- `0x180002e84`
- `0x18000330c`
- `0x1800044bc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180004553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180004553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004586`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180004586`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180004571`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180004571`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
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
0x1800044bc  push    rbx
0x1800044be  push    rbp
0x1800044bf  push    rsi
0x1800044c0  push    rdi
0x1800044c1  push    r12
0x1800044c3  push    r13
0x1800044c5  push    r14
0x1800044c7  push    r15
0x1800044c9  sub     rsp, 28h
0x1800044cd  mov     r12, rdx
0x1800044d0  mov     edi, r9d
0x1800044d3  mov     esi, 8
0x1800044d8  mov     rbp, r8
0x1800044db  mov     eax, esi
0x1800044dd  mul     rdi
0x1800044e0  lea     r14, [rsi-9]
0x1800044e4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800044eb  cmovb   rax, r14
0x1800044ef  mov     rcx, rax; unsigned __int64
0x1800044f2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800044f7  mov     r15, rax
0x1800044fa  mov     eax, esi
0x1800044fc  mul     rdi
0x1800044ff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004506  cmovb   rax, r14
0x18000450a  mov     rcx, rax; unsigned __int64
0x18000450d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004512  xor     r13d, r13d
0x180004515  mov     r14, rax
0x180004518  test    r15, r15
0x18000451b  jz      short loc_180004594
0x18000451d  test    rax, rax
0x180004520  jz      short loc_180004594
0x180004522  mov     ebx, r13d
0x180004525  mov     esi, r13d
0x180004528  test    edi, edi
0x18000452a  jz      short loc_180004565
0x18000452c  test    ebx, ebx
0x18000452e  js      short loc_180004579
0x180004530  mov     eax, esi
0x180004532  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x180004539  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000453d  mov     [r15+rax*8], rcx
0x180004541  mov     rcx, [r12+rax*8]; sourceString
0x180004545  inc     rdx; length
0x180004548  cmp     [rcx+rdx*2], r13w
0x18000454d  jnz     short loc_180004545
0x18000454f  lea     r8, [r14+rax*8]; string
0x180004553  call    cs:__imp_WindowsCreateString
0x180004559  inc     esi
0x18000455b  mov     ebx, eax
0x18000455d  cmp     esi, edi
0x18000455f  jb      short loc_18000452C
0x180004561  test    eax, eax
0x180004563  js      short loc_180004579
0x180004565  mov     r9, rbp
0x180004568  mov     r8d, edi
0x18000456b  mov     rdx, r15
0x18000456e  mov     rcx, r14
0x180004571  call    cs:__imp_RoRegisterActivationFactories
0x180004577  mov     ebx, eax
0x180004579  mov     edi, r13d
0x18000457c  test    esi, esi
0x18000457e  jz      short loc_180004599
0x180004580  mov     ecx, edi
0x180004582  mov     rcx, [r14+rcx*8]; string
0x180004586  call    cs:__imp_WindowsDeleteString
0x18000458c  inc     edi
0x18000458e  cmp     edi, esi
0x180004590  jb      short loc_180004580
0x180004592  jmp     short loc_180004599
0x180004594  mov     ebx, 8007000Eh
0x180004599  mov     rcx, r15; void *
0x18000459c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800045a1  mov     rcx, r14; void *
0x1800045a4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800045a9  mov     eax, ebx
0x1800045ab  add     rsp, 28h
0x1800045af  pop     r15
0x1800045b1  pop     r14
0x1800045b3  pop     r13
0x1800045b5  pop     r12
0x1800045b7  pop     rdi
0x1800045b8  pop     rsi
0x1800045b9  pop     rbp
0x1800045ba  pop     rbx
0x1800045bb  retn
```
