# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x140006d44`
- end: `0x140006e46`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `258`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140008450`

## callees

- `0x1400021d0`
- `0x140006d44`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x140006e24`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140006e2d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140006e24`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140006e2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140006ddb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140006ddb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140006e0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140006e0e`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x140006df9`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x140006df9`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RegisterWinRTObject<2>(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v7; // rax
  _QWORD *v8; // r15
  unsigned __int64 v9; // rax
  HSTRING *v10; // rax
  HSTRING *v11; // r14
  int v12; // ebx
  unsigned int v13; // esi
  __int64 v14; // rdx
  const WCHAR *v15; // rcx
  HRESULT String; // eax
  unsigned int i; // edi

  v5 = a4;
  v7 = 8LL * a4;
  if ( !is_mul_ok(a4, 8u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v8 && v10 )
  {
    v12 = 0;
    v13 = 0;
    if ( (_DWORD)v5 )
    {
      while ( v12 >= 0 )
      {
        v14 = -1;
        v8[v13] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
        v15 = *(const WCHAR **)(a2 + 8LL * v13);
        do
          ++v14;
        while ( v15[v14] );
        String = WindowsCreateString(v15, v14, &v11[v13++]);
        v12 = String;
        if ( v13 >= (unsigned int)v5 )
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
      v12 = RoRegisterActivationFactories(v11, v8, (unsigned int)v5, a3);
    }
    for ( i = 0; i < v13; ++i )
      WindowsDeleteString(v11[i]);
  }
  else
  {
    v12 = -2147024882;
  }
  operator delete[](v8);
  operator delete[](v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140006d44  push    rbx
0x140006d46  push    rbp
0x140006d47  push    rsi
0x140006d48  push    rdi
0x140006d49  push    r12
0x140006d4b  push    r13
0x140006d4d  push    r14
0x140006d4f  push    r15
0x140006d51  sub     rsp, 28h
0x140006d55  mov     r12, rdx
0x140006d58  mov     edi, r9d
0x140006d5b  mov     esi, 8
0x140006d60  mov     rbp, r8
0x140006d63  mov     eax, esi
0x140006d65  mul     rdi
0x140006d68  lea     r14, [rsi-9]
0x140006d6c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140006d73  cmovb   rax, r14
0x140006d77  mov     rcx, rax; unsigned __int64
0x140006d7a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140006d7f  mov     r15, rax
0x140006d82  mov     eax, esi
0x140006d84  mul     rdi
0x140006d87  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140006d8e  cmovb   rax, r14
0x140006d92  mov     rcx, rax; unsigned __int64
0x140006d95  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140006d9a  xor     r13d, r13d
0x140006d9d  mov     r14, rax
0x140006da0  test    r15, r15
0x140006da3  jz      short loc_140006E1C
0x140006da5  test    rax, rax
0x140006da8  jz      short loc_140006E1C
0x140006daa  mov     ebx, r13d
0x140006dad  mov     esi, r13d
0x140006db0  test    edi, edi
0x140006db2  jz      short loc_140006DED
0x140006db4  test    ebx, ebx
0x140006db6  js      short loc_140006E01
0x140006db8  mov     eax, esi
0x140006dba  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x140006dc1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140006dc5  mov     [r15+rax*8], rcx
0x140006dc9  mov     rcx, [r12+rax*8]; sourceString
0x140006dcd  inc     rdx; length
0x140006dd0  cmp     [rcx+rdx*2], r13w
0x140006dd5  jnz     short loc_140006DCD
0x140006dd7  lea     r8, [r14+rax*8]; string
0x140006ddb  call    cs:__imp_WindowsCreateString
0x140006de1  inc     esi
0x140006de3  mov     ebx, eax
0x140006de5  cmp     esi, edi
0x140006de7  jb      short loc_140006DB4
0x140006de9  test    eax, eax
0x140006deb  js      short loc_140006E01
0x140006ded  mov     r9, rbp
0x140006df0  mov     r8d, edi
0x140006df3  mov     rdx, r15
0x140006df6  mov     rcx, r14
0x140006df9  call    cs:__imp_RoRegisterActivationFactories
0x140006dff  mov     ebx, eax
0x140006e01  mov     edi, r13d
0x140006e04  test    esi, esi
0x140006e06  jz      short loc_140006E21
0x140006e08  mov     ecx, edi
0x140006e0a  mov     rcx, [r14+rcx*8]; string
0x140006e0e  call    cs:__imp_WindowsDeleteString
0x140006e14  inc     edi
0x140006e16  cmp     edi, esi
0x140006e18  jb      short loc_140006E08
0x140006e1a  jmp     short loc_140006E21
0x140006e1c  mov     ebx, 8007000Eh
0x140006e21  mov     rcx, r15
0x140006e24  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140006e2a  mov     rcx, r14
0x140006e2d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140006e33  mov     eax, ebx
0x140006e35  add     rsp, 28h
0x140006e39  pop     r15
0x140006e3b  pop     r14
0x140006e3d  pop     r13
0x140006e3f  pop     r12
0x140006e41  pop     rdi
0x140006e42  pop     rsi
0x140006e43  pop     rbp
0x140006e44  pop     rbx
0x140006e45  retn
```
