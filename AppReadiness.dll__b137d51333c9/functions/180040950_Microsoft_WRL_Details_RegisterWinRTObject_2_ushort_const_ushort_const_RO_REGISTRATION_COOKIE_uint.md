# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x180040950`
- end: `0x180040a50`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180043120`

## callees

- `0x18003e234`
- `0x18003e5ec`
- `0x180040950`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800409e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800409e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040a1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040a1a`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180040a05`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180040a05`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180040950  push    rbx
0x180040952  push    rbp
0x180040953  push    rsi
0x180040954  push    rdi
0x180040955  push    r12
0x180040957  push    r13
0x180040959  push    r14
0x18004095b  push    r15
0x18004095d  sub     rsp, 28h
0x180040961  mov     r12, rdx
0x180040964  mov     edi, r9d
0x180040967  mov     esi, 8
0x18004096c  mov     rbp, r8
0x18004096f  mov     eax, esi
0x180040971  mul     rdi
0x180040974  lea     r14, [rsi-9]
0x180040978  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004097f  cmovb   rax, r14
0x180040983  mov     rcx, rax; unsigned __int64
0x180040986  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004098b  mov     r15, rax
0x18004098e  mov     eax, esi
0x180040990  mul     rdi
0x180040993  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004099a  cmovb   rax, r14
0x18004099e  mov     rcx, rax; unsigned __int64
0x1800409a1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800409a6  xor     r13d, r13d
0x1800409a9  mov     r14, rax
0x1800409ac  test    r15, r15
0x1800409af  jz      short loc_180040A28
0x1800409b1  test    rax, rax
0x1800409b4  jz      short loc_180040A28
0x1800409b6  mov     ebx, r13d
0x1800409b9  mov     esi, r13d
0x1800409bc  test    edi, edi
0x1800409be  jz      short loc_1800409F9
0x1800409c0  test    ebx, ebx
0x1800409c2  js      short loc_180040A0D
0x1800409c4  mov     eax, esi
0x1800409c6  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x1800409cd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800409d1  mov     [r15+rax*8], rcx
0x1800409d5  mov     rcx, [r12+rax*8]; sourceString
0x1800409d9  inc     rdx; length
0x1800409dc  cmp     [rcx+rdx*2], r13w
0x1800409e1  jnz     short loc_1800409D9
0x1800409e3  lea     r8, [r14+rax*8]; string
0x1800409e7  call    cs:__imp_WindowsCreateString
0x1800409ed  inc     esi
0x1800409ef  mov     ebx, eax
0x1800409f1  cmp     esi, edi
0x1800409f3  jb      short loc_1800409C0
0x1800409f5  test    eax, eax
0x1800409f7  js      short loc_180040A0D
0x1800409f9  mov     r9, rbp
0x1800409fc  mov     r8d, edi
0x1800409ff  mov     rdx, r15
0x180040a02  mov     rcx, r14
0x180040a05  call    cs:__imp_RoRegisterActivationFactories
0x180040a0b  mov     ebx, eax
0x180040a0d  mov     edi, r13d
0x180040a10  test    esi, esi
0x180040a12  jz      short loc_180040A2D
0x180040a14  mov     ecx, edi
0x180040a16  mov     rcx, [r14+rcx*8]; string
0x180040a1a  call    cs:__imp_WindowsDeleteString
0x180040a20  inc     edi
0x180040a22  cmp     edi, esi
0x180040a24  jb      short loc_180040A14
0x180040a26  jmp     short loc_180040A2D
0x180040a28  mov     ebx, 8007000Eh
0x180040a2d  mov     rcx, r15; void *
0x180040a30  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180040a35  mov     rcx, r14; void *
0x180040a38  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180040a3d  mov     eax, ebx
0x180040a3f  add     rsp, 28h
0x180040a43  pop     r15
0x180040a45  pop     r14
0x180040a47  pop     r13
0x180040a49  pop     r12
0x180040a4b  pop     rdi
0x180040a4c  pop     rsi
0x180040a4d  pop     rbp
0x180040a4e  pop     rbx
0x180040a4f  retn
```
