# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x180005be8`
- end: `0x180005ce8`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000be30`

## callees

- `0x180003a84`
- `0x180003ec0`
- `0x180005be8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005cb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005cb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180005c7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180005c7f`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180005c9d`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180005c9d`

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
0x180005be8  push    rbx
0x180005bea  push    rbp
0x180005beb  push    rsi
0x180005bec  push    rdi
0x180005bed  push    r12
0x180005bef  push    r13
0x180005bf1  push    r14
0x180005bf3  push    r15
0x180005bf5  sub     rsp, 28h
0x180005bf9  mov     r12, rdx
0x180005bfc  mov     edi, r9d
0x180005bff  mov     esi, 8
0x180005c04  mov     rbp, r8
0x180005c07  mov     eax, esi
0x180005c09  mul     rdi
0x180005c0c  lea     r14, [rsi-9]
0x180005c10  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005c17  cmovb   rax, r14
0x180005c1b  mov     rcx, rax; unsigned __int64
0x180005c1e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005c23  mov     r15, rax
0x180005c26  mov     eax, esi
0x180005c28  mul     rdi
0x180005c2b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005c32  cmovb   rax, r14
0x180005c36  mov     rcx, rax; unsigned __int64
0x180005c39  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005c3e  xor     r13d, r13d
0x180005c41  mov     r14, rax
0x180005c44  test    r15, r15
0x180005c47  jz      short loc_180005CC0
0x180005c49  test    rax, rax
0x180005c4c  jz      short loc_180005CC0
0x180005c4e  mov     ebx, r13d
0x180005c51  mov     esi, r13d
0x180005c54  test    edi, edi
0x180005c56  jz      short loc_180005C91
0x180005c58  test    ebx, ebx
0x180005c5a  js      short loc_180005CA5
0x180005c5c  mov     eax, esi
0x180005c5e  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x180005c65  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180005c69  mov     [r15+rax*8], rcx
0x180005c6d  mov     rcx, [r12+rax*8]; sourceString
0x180005c71  inc     rdx; length
0x180005c74  cmp     [rcx+rdx*2], r13w
0x180005c79  jnz     short loc_180005C71
0x180005c7b  lea     r8, [r14+rax*8]; string
0x180005c7f  call    cs:__imp_WindowsCreateString
0x180005c85  inc     esi
0x180005c87  mov     ebx, eax
0x180005c89  cmp     esi, edi
0x180005c8b  jb      short loc_180005C58
0x180005c8d  test    eax, eax
0x180005c8f  js      short loc_180005CA5
0x180005c91  mov     r9, rbp
0x180005c94  mov     r8d, edi
0x180005c97  mov     rdx, r15
0x180005c9a  mov     rcx, r14
0x180005c9d  call    cs:__imp_RoRegisterActivationFactories
0x180005ca3  mov     ebx, eax
0x180005ca5  mov     edi, r13d
0x180005ca8  test    esi, esi
0x180005caa  jz      short loc_180005CC5
0x180005cac  mov     ecx, edi
0x180005cae  mov     rcx, [r14+rcx*8]; string
0x180005cb2  call    cs:__imp_WindowsDeleteString
0x180005cb8  inc     edi
0x180005cba  cmp     edi, esi
0x180005cbc  jb      short loc_180005CAC
0x180005cbe  jmp     short loc_180005CC5
0x180005cc0  mov     ebx, 8007000Eh
0x180005cc5  mov     rcx, r15; void *
0x180005cc8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005ccd  mov     rcx, r14; void *
0x180005cd0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005cd5  mov     eax, ebx
0x180005cd7  add     rsp, 28h
0x180005cdb  pop     r15
0x180005cdd  pop     r14
0x180005cdf  pop     r13
0x180005ce1  pop     r12
0x180005ce3  pop     rdi
0x180005ce4  pop     rsi
0x180005ce5  pop     rbp
0x180005ce6  pop     rbx
0x180005ce7  retn
```
