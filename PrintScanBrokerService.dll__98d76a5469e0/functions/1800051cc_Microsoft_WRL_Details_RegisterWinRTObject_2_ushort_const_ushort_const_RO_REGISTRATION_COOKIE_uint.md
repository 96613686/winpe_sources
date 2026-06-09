# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x1800051cc`
- end: `0x1800052cc`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d440`

## callees

- `0x180002d64`
- `0x180003260`
- `0x1800051cc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005296`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005296`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180005263`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180005263`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180005281`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180005281`

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
0x1800051cc  push    rbx
0x1800051ce  push    rbp
0x1800051cf  push    rsi
0x1800051d0  push    rdi
0x1800051d1  push    r12
0x1800051d3  push    r13
0x1800051d5  push    r14
0x1800051d7  push    r15
0x1800051d9  sub     rsp, 28h
0x1800051dd  mov     r12, rdx
0x1800051e0  mov     edi, r9d
0x1800051e3  mov     esi, 8
0x1800051e8  mov     rbp, r8
0x1800051eb  mov     eax, esi
0x1800051ed  mul     rdi
0x1800051f0  lea     r14, [rsi-9]
0x1800051f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800051fb  cmovb   rax, r14
0x1800051ff  mov     rcx, rax; unsigned __int64
0x180005202  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005207  mov     r15, rax
0x18000520a  mov     eax, esi
0x18000520c  mul     rdi
0x18000520f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005216  cmovb   rax, r14
0x18000521a  mov     rcx, rax; unsigned __int64
0x18000521d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005222  xor     r13d, r13d
0x180005225  mov     r14, rax
0x180005228  test    r15, r15
0x18000522b  jz      short loc_1800052A4
0x18000522d  test    rax, rax
0x180005230  jz      short loc_1800052A4
0x180005232  mov     ebx, r13d
0x180005235  mov     esi, r13d
0x180005238  test    edi, edi
0x18000523a  jz      short loc_180005275
0x18000523c  test    ebx, ebx
0x18000523e  js      short loc_180005289
0x180005240  mov     eax, esi
0x180005242  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x180005249  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000524d  mov     [r15+rax*8], rcx
0x180005251  mov     rcx, [r12+rax*8]; sourceString
0x180005255  inc     rdx; length
0x180005258  cmp     [rcx+rdx*2], r13w
0x18000525d  jnz     short loc_180005255
0x18000525f  lea     r8, [r14+rax*8]; string
0x180005263  call    cs:__imp_WindowsCreateString
0x180005269  inc     esi
0x18000526b  mov     ebx, eax
0x18000526d  cmp     esi, edi
0x18000526f  jb      short loc_18000523C
0x180005271  test    eax, eax
0x180005273  js      short loc_180005289
0x180005275  mov     r9, rbp
0x180005278  mov     r8d, edi
0x18000527b  mov     rdx, r15
0x18000527e  mov     rcx, r14
0x180005281  call    cs:__imp_RoRegisterActivationFactories
0x180005287  mov     ebx, eax
0x180005289  mov     edi, r13d
0x18000528c  test    esi, esi
0x18000528e  jz      short loc_1800052A9
0x180005290  mov     ecx, edi
0x180005292  mov     rcx, [r14+rcx*8]; string
0x180005296  call    cs:__imp_WindowsDeleteString
0x18000529c  inc     edi
0x18000529e  cmp     edi, esi
0x1800052a0  jb      short loc_180005290
0x1800052a2  jmp     short loc_1800052A9
0x1800052a4  mov     ebx, 8007000Eh
0x1800052a9  mov     rcx, r15; void *
0x1800052ac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800052b1  mov     rcx, r14; void *
0x1800052b4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800052b9  mov     eax, ebx
0x1800052bb  add     rsp, 28h
0x1800052bf  pop     r15
0x1800052c1  pop     r14
0x1800052c3  pop     r13
0x1800052c5  pop     r12
0x1800052c7  pop     rdi
0x1800052c8  pop     rsi
0x1800052c9  pop     rbp
0x1800052ca  pop     rbx
0x1800052cb  retn
```
