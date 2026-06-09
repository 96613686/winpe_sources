# Microsoft::WRL::Details::RegisterWinRTObject<2>(wchar_t const *,wchar_t const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x180019ba4`
- end: `0x180019ca4`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEB_WPEAPEB_WPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001fab0`

## callees

- `0x18000d2c4`
- `0x18000d7ec`
- `0x180019ba4`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180019c59`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180019c59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019c6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019c6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180019c3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180019c3b`

## pseudocode

```c
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
0x180019ba4  push    rbx
0x180019ba6  push    rbp
0x180019ba7  push    rsi
0x180019ba8  push    rdi
0x180019ba9  push    r12
0x180019bab  push    r13
0x180019bad  push    r14
0x180019baf  push    r15
0x180019bb1  sub     rsp, 28h
0x180019bb5  mov     r12, rdx
0x180019bb8  mov     edi, r9d
0x180019bbb  mov     esi, 8
0x180019bc0  mov     rbp, r8
0x180019bc3  mov     eax, esi
0x180019bc5  mul     rdi
0x180019bc8  lea     r14, [rsi-9]
0x180019bcc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019bd3  cmovb   rax, r14
0x180019bd7  mov     rcx, rax; unsigned __int64
0x180019bda  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180019bdf  mov     r15, rax
0x180019be2  mov     eax, esi
0x180019be4  mul     rdi
0x180019be7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019bee  cmovb   rax, r14
0x180019bf2  mov     rcx, rax; unsigned __int64
0x180019bf5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180019bfa  xor     r13d, r13d
0x180019bfd  mov     r14, rax
0x180019c00  test    r15, r15
0x180019c03  jz      short loc_180019C7C
0x180019c05  test    rax, rax
0x180019c08  jz      short loc_180019C7C
0x180019c0a  mov     ebx, r13d
0x180019c0d  mov     esi, r13d
0x180019c10  test    edi, edi
0x180019c12  jz      short loc_180019C4D
0x180019c14  test    ebx, ebx
0x180019c16  js      short loc_180019C61
0x180019c18  mov     eax, esi
0x180019c1a  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x180019c21  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019c25  mov     [r15+rax*8], rcx
0x180019c29  mov     rcx, [r12+rax*8]; sourceString
0x180019c2d  inc     rdx; length
0x180019c30  cmp     [rcx+rdx*2], r13w
0x180019c35  jnz     short loc_180019C2D
0x180019c37  lea     r8, [r14+rax*8]; string
0x180019c3b  call    cs:__imp_WindowsCreateString
0x180019c41  inc     esi
0x180019c43  mov     ebx, eax
0x180019c45  cmp     esi, edi
0x180019c47  jb      short loc_180019C14
0x180019c49  test    eax, eax
0x180019c4b  js      short loc_180019C61
0x180019c4d  mov     r9, rbp
0x180019c50  mov     r8d, edi
0x180019c53  mov     rdx, r15
0x180019c56  mov     rcx, r14
0x180019c59  call    cs:__imp_RoRegisterActivationFactories
0x180019c5f  mov     ebx, eax
0x180019c61  mov     edi, r13d
0x180019c64  test    esi, esi
0x180019c66  jz      short loc_180019C81
0x180019c68  mov     ecx, edi
0x180019c6a  mov     rcx, [r14+rcx*8]; string
0x180019c6e  call    cs:__imp_WindowsDeleteString
0x180019c74  inc     edi
0x180019c76  cmp     edi, esi
0x180019c78  jb      short loc_180019C68
0x180019c7a  jmp     short loc_180019C81
0x180019c7c  mov     ebx, 8007000Eh
0x180019c81  mov     rcx, r15; void *
0x180019c84  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019c89  mov     rcx, r14; void *
0x180019c8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019c91  mov     eax, ebx
0x180019c93  add     rsp, 28h
0x180019c97  pop     r15
0x180019c99  pop     r14
0x180019c9b  pop     r13
0x180019c9d  pop     r12
0x180019c9f  pop     rdi
0x180019ca0  pop     rsi
0x180019ca1  pop     rbp
0x180019ca2  pop     rbx
0x180019ca3  retn
```
