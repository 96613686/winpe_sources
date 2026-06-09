# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x180003c58`
- end: `0x180003d58`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800060c0`

## callees

- `0x180001b6c`
- `0x180002188`
- `0x180003c58`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180003d0d`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180003d0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180003cef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180003cef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003d22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003d22`

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
0x180003c58  push    rbx
0x180003c5a  push    rbp
0x180003c5b  push    rsi
0x180003c5c  push    rdi
0x180003c5d  push    r12
0x180003c5f  push    r13
0x180003c61  push    r14
0x180003c63  push    r15
0x180003c65  sub     rsp, 28h
0x180003c69  mov     r12, rdx
0x180003c6c  mov     edi, r9d
0x180003c6f  mov     esi, 8
0x180003c74  mov     rbp, r8
0x180003c77  mov     eax, esi
0x180003c79  mul     rdi
0x180003c7c  lea     r14, [rsi-9]
0x180003c80  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003c87  cmovb   rax, r14
0x180003c8b  mov     rcx, rax; unsigned __int64
0x180003c8e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180003c93  mov     r15, rax
0x180003c96  mov     eax, esi
0x180003c98  mul     rdi
0x180003c9b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003ca2  cmovb   rax, r14
0x180003ca6  mov     rcx, rax; unsigned __int64
0x180003ca9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180003cae  xor     r13d, r13d
0x180003cb1  mov     r14, rax
0x180003cb4  test    r15, r15
0x180003cb7  jz      short loc_180003D30
0x180003cb9  test    rax, rax
0x180003cbc  jz      short loc_180003D30
0x180003cbe  mov     ebx, r13d
0x180003cc1  mov     esi, r13d
0x180003cc4  test    edi, edi
0x180003cc6  jz      short loc_180003D01
0x180003cc8  test    ebx, ebx
0x180003cca  js      short loc_180003D15
0x180003ccc  mov     eax, esi
0x180003cce  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x180003cd5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180003cd9  mov     [r15+rax*8], rcx
0x180003cdd  mov     rcx, [r12+rax*8]; sourceString
0x180003ce1  inc     rdx; length
0x180003ce4  cmp     [rcx+rdx*2], r13w
0x180003ce9  jnz     short loc_180003CE1
0x180003ceb  lea     r8, [r14+rax*8]; string
0x180003cef  call    cs:__imp_WindowsCreateString
0x180003cf5  inc     esi
0x180003cf7  mov     ebx, eax
0x180003cf9  cmp     esi, edi
0x180003cfb  jb      short loc_180003CC8
0x180003cfd  test    eax, eax
0x180003cff  js      short loc_180003D15
0x180003d01  mov     r9, rbp
0x180003d04  mov     r8d, edi
0x180003d07  mov     rdx, r15
0x180003d0a  mov     rcx, r14
0x180003d0d  call    cs:__imp_RoRegisterActivationFactories
0x180003d13  mov     ebx, eax
0x180003d15  mov     edi, r13d
0x180003d18  test    esi, esi
0x180003d1a  jz      short loc_180003D35
0x180003d1c  mov     ecx, edi
0x180003d1e  mov     rcx, [r14+rcx*8]; string
0x180003d22  call    cs:__imp_WindowsDeleteString
0x180003d28  inc     edi
0x180003d2a  cmp     edi, esi
0x180003d2c  jb      short loc_180003D1C
0x180003d2e  jmp     short loc_180003D35
0x180003d30  mov     ebx, 8007000Eh
0x180003d35  mov     rcx, r15; void *
0x180003d38  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003d3d  mov     rcx, r14; void *
0x180003d40  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003d45  mov     eax, ebx
0x180003d47  add     rsp, 28h
0x180003d4b  pop     r15
0x180003d4d  pop     r14
0x180003d4f  pop     r13
0x180003d51  pop     r12
0x180003d53  pop     rdi
0x180003d54  pop     rsi
0x180003d55  pop     rbp
0x180003d56  pop     rbx
0x180003d57  retn
```
