# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x1800623e8`
- end: `0x1800624e8`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800629d0`

## callees

- `0x18005b33c`
- `0x18005b3a0`
- `0x1800623e8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800624b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800624b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006247f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006247f`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18006249d`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x18006249d`

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
0x1800623e8  push    rbx
0x1800623ea  push    rbp
0x1800623eb  push    rsi
0x1800623ec  push    rdi
0x1800623ed  push    r12
0x1800623ef  push    r13
0x1800623f1  push    r14
0x1800623f3  push    r15
0x1800623f5  sub     rsp, 28h
0x1800623f9  mov     r12, rdx
0x1800623fc  mov     edi, r9d
0x1800623ff  mov     esi, 8
0x180062404  mov     rbp, r8
0x180062407  mov     eax, esi
0x180062409  mul     rdi
0x18006240c  lea     r14, [rsi-9]
0x180062410  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180062417  cmovb   rax, r14
0x18006241b  mov     rcx, rax; unsigned __int64
0x18006241e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180062423  mov     r15, rax
0x180062426  mov     eax, esi
0x180062428  mul     rdi
0x18006242b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180062432  cmovb   rax, r14
0x180062436  mov     rcx, rax; unsigned __int64
0x180062439  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006243e  xor     r13d, r13d
0x180062441  mov     r14, rax
0x180062444  test    r15, r15
0x180062447  jz      short loc_1800624C0
0x180062449  test    rax, rax
0x18006244c  jz      short loc_1800624C0
0x18006244e  mov     ebx, r13d
0x180062451  mov     esi, r13d
0x180062454  test    edi, edi
0x180062456  jz      short loc_180062491
0x180062458  test    ebx, ebx
0x18006245a  js      short loc_1800624A5
0x18006245c  mov     eax, esi
0x18006245e  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x180062465  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180062469  mov     [r15+rax*8], rcx
0x18006246d  mov     rcx, [r12+rax*8]; sourceString
0x180062471  inc     rdx; length
0x180062474  cmp     [rcx+rdx*2], r13w
0x180062479  jnz     short loc_180062471
0x18006247b  lea     r8, [r14+rax*8]; string
0x18006247f  call    cs:__imp_WindowsCreateString
0x180062485  inc     esi
0x180062487  mov     ebx, eax
0x180062489  cmp     esi, edi
0x18006248b  jb      short loc_180062458
0x18006248d  test    eax, eax
0x18006248f  js      short loc_1800624A5
0x180062491  mov     r9, rbp
0x180062494  mov     r8d, edi
0x180062497  mov     rdx, r15
0x18006249a  mov     rcx, r14
0x18006249d  call    cs:__imp_RoRegisterActivationFactories
0x1800624a3  mov     ebx, eax
0x1800624a5  mov     edi, r13d
0x1800624a8  test    esi, esi
0x1800624aa  jz      short loc_1800624C5
0x1800624ac  mov     ecx, edi
0x1800624ae  mov     rcx, [r14+rcx*8]; string
0x1800624b2  call    cs:__imp_WindowsDeleteString
0x1800624b8  inc     edi
0x1800624ba  cmp     edi, esi
0x1800624bc  jb      short loc_1800624AC
0x1800624be  jmp     short loc_1800624C5
0x1800624c0  mov     ebx, 8007000Eh
0x1800624c5  mov     rcx, r15; void *
0x1800624c8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800624cd  mov     rcx, r14; void *
0x1800624d0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800624d5  mov     eax, ebx
0x1800624d7  add     rsp, 28h
0x1800624db  pop     r15
0x1800624dd  pop     r14
0x1800624df  pop     r13
0x1800624e1  pop     r12
0x1800624e3  pop     rdi
0x1800624e4  pop     rsi
0x1800624e5  pop     rbp
0x1800624e6  pop     rbx
0x1800624e7  retn
```
